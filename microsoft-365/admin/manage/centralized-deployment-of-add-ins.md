---
title: Avgöra om centraliserad distribution av tillägg fungerar för din organisation
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: Ta reda på om din klient organisation och användare uppfyller kraven och Använd centraliserad distribution för att distribuera Office-tillägg.
ms.openlocfilehash: c3e306789f5b1c09e835d8d2c5ebea668bf14874
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235424"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a>Avgöra om centraliserad distribution av tillägg fungerar för din organisation

Centraliserad distribution är det rekommenderade och mest omfattande sättet för de flesta kunder att distribuera Office-tillägg till användare och grupper inom din organisation. Om du är administratör kan du använda den här vägledningen för att ta reda på om din organisation och dina användare uppfyller kraven för att kunna använda centraliserad distribution.

Centraliserad distribution har följande fördelar:
  
- En global administratör kan tilldela ett tillägg direkt till en användare, till flera användare via en grupp eller till alla i organisationen.
    
- När det relevanta Office-programmet startas hämtas tillägget automatiskt. Om tillägget har stöd för tilläggs kommandon visas tillägget automatiskt i menyfliksområdet i Office-programmet.
    
- Tillägg visas inte längre för användare om administratören inaktiverar eller tar bort tillägget, eller om användaren tas bort från Azure Active Directory eller från en grupp som tillägget är tilldelat till.

Centraliserad distribution stöder tre Station ära datorer, Mac och online Office-appar. Centraliserad distribution stöder även iOS och Android (endast Outlook Mobile-tillägg).

Det kan ta upp till 24 timmar för ett tillägg att visas för klienten och alla användare.
  
## <a name="requirements"></a>Krav

Centraliserad distribution av tillägg kräver att användarna använder Microsoft 365-appar för Enterprise eller Microsoft 365 Business Premium (och är inloggade på Office med deras organisations-ID) och har Exchange Online och aktiva Exchange Online-postlådor. Abonnemangs katalogen måste antingen vara i eller sammankopplad till Azure Active Directory.
Du kan se specifika krav för Office och Exchange nedan eller använda kompatibilitetskontrollen för[centraliserad distribution](#centralized-deployment-compatibility-checker).

Centraliserad distribution stöder inte följande:
  
- Tillägg som är inriktade på Word, Excel eller PowerPoint i Office 2013 
- En lokal katalogtjänst
- Tillägg distribution till en Exchange On-lokala-postlåda
- Tilläggsdistribution till SharePoint  
- Teams-appar
- Distribution av COM- (Component Object Model) och VSTO-tilläggen (Visual Studio Tools for Office)
- Distributioner av Microsoft 365 som inte innehåller Exchange, till exempel Microsoft 365-appar för företag

### <a name="office-requirements"></a>Office-krav

- För Word-, Excel-och PowerPoint-tillägg måste användarna använda något av följande:
  - På en Windows-enhet, version 1704 eller senare av Microsoft 365-program för företag eller Microsoft 365 Business Premium.
  - På en Mac, version 15,34 eller senare.

- För Outlook måste användarna använda något av följande: 
  - Version 1701 eller senare av Microsoft 365-appar för Enterprise eller Microsoft 365 Business Premium.
  - Version 1808 eller senare av Office Professional Plus 2019 eller Office Standard 2019.
  - Version 16.0.4494.1000 eller senare av Office Professional Plus 2016 (MSI) eller Office Standard 2016 (MSI)\*
  - Version 15.0.4937.1000 eller senare av Office Professional Plus 2013 (MSI) eller Office Standard 2013 (MSI)\*
  - Version 16.0.9318.1000 eller senare av Office 2016 för Mac 
- Version 2.75.0 eller senare av Outlook Mobile för iOS 
- Version 2.2.145 eller senare av Outlook Mobile för Android 
    
    * MSI-versioner av Outlook Visa installerade tillägg i Outlook-menyfliksområdet, inte avsnittet "mina tillägg".
    

#### <a name="find-out-if-microsoft-365-apps-for-enterprise-is-installed"></a>Ta reda på om Microsoft 365-appar för företag är installerat

För att använda Microsoft 365-appar för företag måste en användare ha ett Microsoft 365-konto och ha tilldelats en licens. Mer information finns i [Översikt över Microsoft 365-appar för företag](https://go.microsoft.com/fwlink/p/?linkid=846328).

Det enklaste sättet att upptäcka om en användare har Microsoft 365-appar för företag installerat och har använt det nyligen, är att använda Microsoft Office-aktiverings rapporten, som är tillgänglig i administrations centret för Microsoft 365. I rapporten visas en lista med alla användare som har aktiverat Microsoft 365-appar för företag under de senaste 7, 30, dagar, 90 eller 180 dagar. De kolumner i rapporten som är viktiga för centraliserad distribution är de för datoraktiveringar för Windows och Mac. Du kan exportera rapporten till Excel. Mer information om rapporten finns i [Microsoft 365-rapporter i administrations centret – Microsoft Office-aktiveringar](../activity-reports/microsoft-office-activations.md).
  
Om du inte vill använda aktiverings rapporten kan du be en användare öppna ett Office-program som Word på sin dator och sedan välja ett **fil** \> **konto**. Under **produkt information**bör du se **abonnemangs produkten** och **Microsoft 365 för företag**eller Microsoft 365 Business Premium, liknande vad som visas i följande bild.

![Produkt information i ett Office-program](../../media/product-information-microsoft-365-enterprise.png)
  
Om du behöver hjälp med Microsoft 365-appar för företag kan du läsa [fel söknings tips för microsoft 365-appar för företag](https://go.microsoft.com/fwlink/p/?linkid=846339).


### <a name="exchange-online-requirements"></a>Exchange Online-krav

Microsoft Exchange lagrar tilläggsmanifesten i organisationens klientorganisation. Administratörs distributionen av tillägg och de användare som tar emot dessa tillägg måste finnas i en version av Exchange Online som stöder OAuth-autentisering.
  
Fråga organisationens Exchange-administratör om vilken konfiguration som används. OAuth-anslutning per användare kan verifieras med hjälp av PowerShell-cmdleten [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351). 


### <a name="centralized-deployment-compatibility-checker"></a>Kompatibilitetskontroll för centraliserad distribution

Med kompatibilitetskontrollen för centraliserad distribution kan du kontrol lera om användarna på din klient organisation har ställts in för att använda centraliserad distribution för Word, Excel och PowerPoint. Kompatibilitetskontrollen krävs inte för Outlook-stöd. Ladda ned kompatibilitetskontrollen [här](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).
  
#### <a name="run-the-compatibility-checker"></a>Köra kompatibilitetskontrollen
  
1. Öppna ett PowerShell.exe-fönster med förhöjd rättighet.
    
2. Kör följande kommando:

   ```powershell
   Import-Module O365CompatibilityChecker
   ```
    
3. Kör kommandot **Invoke-CompatabilityCheck** :

   ```powershell
   Invoke-CompatibilityCheck
   ```
   I det här kommandot uppmanas du att ange  *_TenantDomain_* (till exempel *TailspinToysIncorporated. onmicrosoft. </span> com*) och  *_TenantAdmin_* -autentiseringsuppgifter (Använd dina globala administratörs uppgifter) och begär sedan medgivande.
    
   > [!NOTE]
   > Beroende på antalet användare i klientorganisationen kan det ta några minuter eller några timmar att slutföra åtgärden. 
  
När verktyget körts klart har en utdatafil i kommaavgränsat format (.csv) genererats. Filen sparas som standard till **C:\Windows\System32** . Utdatafilen innehåller följande information:
  
- Användarnamn
    
- Användar-ID (användarens e-postadress)
    
- Centraliserad distribution är klar - om de återstående objekten har värdet sant
    
- Kontors plan – den plan där Office de är licensierade för
    
- Office aktiverat - om de har aktiverat Office
    
- Postlåda som stöds - om de finns på en OAuth-aktiverad postlåda


  
## <a name="user-and-group-assignments"></a>Användar- och grupptilldelningar

Funktionen för centraliserad distribution stöder för närvarande de flesta av grupperna som stöds av Azure Active Directory, inklusive Microsoft 365-grupper, distributions listor och säkerhets grupper.
  
> [!NOTE]
> Säkerhetsgrupper utan e-postaktivering stöds inte för närvarande. 
  
Centraliserad distribution stöder tilldelningar till enskilda användare, grupper och alla i klient organisationen. Centraliserad distribution har stöd för användare i grupper på översta nivå och grupper utan överordnade grupper, men inte för användare i kapslade grupper och grupper som har överordnade grupper.
   
Ta en titt på följande exempel där Sandra, Sheila och gruppen Sales Department har tilldelats till ett tillägg. Eftersom West Coast Sales Department är en kapslad grupp, tilldelas Jens och Erik inte till ett tillägg.
  
![Diagram över försäljnings avdelning](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a>Ta reda på om en grupp innehåller kapslade grupper

Det enklaste sättet att upptäcka om en grupp innehåller kapslade grupper är att visa gruppens kontaktkort i Outlook. Om du anger grupp namnet i fältet **till** i ett e-postmeddelande och sedan väljer grupp namnet när det matchas visas det om det innehåller användare eller kapslade grupper. I exemplet nedan visas inga användare och bara två undergrupper på fliken **Medlemmar** för Outlook-kontaktkortet för Test Group. 
  
![Fliken medlemmar på kontakt kortet i Outlook](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
Du kan göra motsatt fråga genom att matcha gruppen och ta reda på om den är medlem i en grupp. I exemplet nedan kan du se att Sub Group 1 är medlem i Test Group under fliken **medlemskap** för Outlook-kontaktkortet. 
  
![Fliken medlemskap på kontakt kortet i Outlook](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
Du kan också använda Azure Active Directory Graph API till att köra frågor för att hitta listan med grupper inom en grupp. Mer information finns i [Åtgärder för grupper | Referens för Graph API](https://go.microsoft.com/fwlink/p/?linkid=846342).
  
### <a name="contacting-microsoft-for-support"></a>Kontakta Microsoft om du behöver support

Om du eller användarna drabbas av problem med att ladda tillägget när du använder Office-program för webben (Word, Excel, osv.), kan det hända att du måste kontakta Microsoft Support ([Läs mer](../contact-support-for-business-products.md)). Ange följande information om din Microsoft 365-miljö i support ärendet.
  
|**Plattform**|**Felsökningsinformation**|
|:-----|:-----|
|Office  <br/> | Charles-/Fiddler-loggar  <br/>  Klientorganisationens id ( [så här gör du](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))  <br/>  CorrelationID. Visa källan för en av Office-sidorna och leta efter Correlation-ID-värdet och skicka det till stöd:  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|RTF-klienter (Windows, Mac)  <br/> | Charles-/Fiddler-loggar  <br/>  Build-nummer för klient programmet (helst som en skärm bild från **fil/konto**)  <br/> |
   

