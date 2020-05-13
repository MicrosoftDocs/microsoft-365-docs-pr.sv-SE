---
title: Ta reda på om centraliserad distribution av tillägg fungerar för din organisation
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: Ta reda på om din klient och dina användare uppfyller kraven, så att du kan använda centraliserad distribution för att distribuera Office-tillägg.
ms.openlocfilehash: bd1c9ca0a034494f6556f0badca66284c3d9e1de
ms.sourcegitcommit: 1c90bcc5c56f24895f01c3e0423c3f6b73715c13
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44214258"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a>Ta reda på om centraliserad distribution av tillägg fungerar för din organisation

Centraliserad distribution är det rekommenderade och mest funktionsrika sättet för de flesta kunder att distribuera Office-tillägg till användare och grupper inom organisationen. Om du är administratör kan du använda den här vägledningen för att avgöra om din klient och dina användare uppfyller kraven så att du kan använda centraliserad distribution.
Centraliserad distribution stöder Windows-, Mac-, iOS-, Android- och Online Office-appar.
Det kan ta upp till 12 timmar innan ett tillägg visas för klienten för alla användare.
  
## <a name="requirements"></a>Krav

Centraliserad distribution av tillägg kräver att användarna använder Microsoft 365 Apps for Enterprise (och är inloggade på Office med sitt organisations-ID) och har Exchange Online- och aktiva Exchange Online-postlådor. Din prenumerationskatalog måste antingen vara i eller federeras med Azure Active Directory.
Du kan visa specifika krav för Office och Exchange nedan eller använda den [centraliserade kompatibilitetskontrollen för distribution](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker).

Centraliserad distribution stöder inte följande:
  
- Tillägg som är inriktade på Word, Excel eller PowerPoint i Office 2013
    
- En lokal katalogtjänst
    
- Tilläggsdistribution till SharePoint  

- Team-appar
   
- Distribution av COM- (Component Object Model) och VSTO-tilläggen (Visual Studio Tools for Office)
    
- Distributioner av Microsoft 365 som inte inkluderar Exchange, till exempel Microsoft 365 Apps for business

### <a name="office-requirements"></a>Office-krav

- För Word-, Excel- och PowerPoint-tillägg måste användarna använda något av följande:
  - På en Windows-enhet, version 1704 eller senare av Microsoft 365 Apps för företag.
  - På en Mac, version 15.34 eller senare.

- För Outlook måste användarna använda något av följande: 
  - Version 1701 eller senare av Microsoft 365 Apps för företag.
  - Version 1808 eller senare av Office Professional Plus 2019 eller Office Standard 2019.
  - Version 16.0.4494.1000 eller senare av Office Professional Plus 2016 (MSI) eller Office Standard 2016 (MSI)\*
  - Version 15.0.4937.1000 eller senare av Office Professional Plus 2013 (MSI) eller Office Standard 2013 (MSI)\*
  - Version 16.0.9318.1000 eller senare av Office 2016 för Mac 
- Version 2.75.0 eller senare av Outlook Mobile för iOS 
- Version 2.2.145 eller senare av Outlook Mobile för Android 
    
    *MSI-versioner av Outlook visar administratörsinstallerade tillägg i lämpligt menyfliksområdet i Outlook, inte avsnittet "Mina tillägg".
    

#### <a name="find-out-if-microsoft-365-apps-for-enterprise-is-installed"></a>Ta reda på om Microsoft 365 Apps for Enterprise är installerat

Om du vill använda Microsoft 365 Apps för företag måste en användare ha ett Microsoft 365-konto och ha tilldelats en licens. Mer information finns i [Översikt över Microsoft 365 Apps för företag](https://go.microsoft.com/fwlink/p/?linkid=846328).

Det enklaste sättet att identifiera om en användare har Microsoft 365 Apps för företag installerat och har använt det nyligen är att använda Microsoft Office Aktiveringsrapporten, som finns i Microsoft 365 admin center. Rapporten innehåller en lista över alla användare som har aktiverat Microsoft 365 Apps för företag under de senaste 7 dagarna, 30 dagarna, 90 dagarna eller 180 dagarna. De kolumner i rapporten som är viktiga för centraliserad distribution är de för datoraktiveringar för Windows och Mac. Du kan exportera rapporten till Excel. Mer information om rapporten finns [i Microsoft 365 Reports i Administrationscenter – Microsoft Office-aktiveringar](../activity-reports/microsoft-office-activations.md).
  
Om du inte vill använda rapporten Aktiveringar kan du be en användare att öppna ett Office-program som Word på datorn och sedan välja **File** \> **Arkivkonto**. Under **Produktinformation**bör du se **Prenumerationsprodukt** och **Microsoft 365 för företag**, vilket visas i följande bild.

![Produktinformation i ett Office-program](../../media/product-information-microsoft-365-enterprise.png)
  
Mer information om Microsoft 365 Apps for enterprise finns i [Felsökningstips för Microsoft 365 Apps for enterprise](https://go.microsoft.com/fwlink/p/?linkid=846339).


### <a name="exchange-online-requirements"></a>Exchange Online-krav

Microsoft Exchange lagrar tilläggsmanifesten i organisationens klientorganisation. Administratören som distribuerar tillägg och de användare som tar emot dessa tillägg måste finnas på en version av Exchange Online som stöder OAuth-autentisering.
  
Fråga organisationens Exchange-administratör om vilken konfiguration som används. OAuth-anslutning per användare kan verifieras med hjälp av PowerShell-cmdleten [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351). 


### <a name="centralized-deployment-compatibility-checker"></a>Centraliserad kompatibilitetskontroll för distribution

Med hjälp av den centraliserade kompatibilitetskontrollen för distribution kan du kontrollera om användarna på klienten är konfigurerade för att använda centraliserad distribution för Word, Excel och PowerPoint. Kompatibilitetskontrollen krävs inte för Outlook-stöd. Ladda ned kompatibilitetskontrollen [här](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).
  
#### <a name="run-the-compatibility-checker"></a>Kör kompatibilitetskontrollen
  
1. Öppna ett PowerShell.exe-fönster med förhöjd rättighet.
    
2. Kör följande kommando:

```powershell
Import-Module O365CompatibilityChecker
```
    
3. Kör kommandot **Anropa-CompatabilityCheck:**

```powershell
Invoke-CompatibilityCheck
```
   som uppmanar dig för *_TenantDomain_* (till exempel *TailspinToysIncorporated.onmicrosoft. </span> com*) och *_TenantAdmin-autentiseringsuppgifter_* (använd dina globala administratörsautentiseringsuppgifter) och begär sedan samtycke.
    
> [!NOTE]
> Beroende på antalet användare i klientorganisationen kan det ta några minuter eller några timmar att slutföra åtgärden. 
  
När verktyget körts klart har en utdatafil i kommaavgränsat format (.csv) genererats. Filen sparas i **C:\windows\system32** som standard. Utdatafilen innehåller följande information:
  
- Användarnamn
    
- Användar-ID (användarens e-postadress)
    
- Centraliserad distribution är klar - om de återstående objekten har värdet sant
    
- Office-plan - Planen för Office de är licensierade för
    
- Office aktiverat - om de har aktiverat Office
    
- Postlåda som stöds - om de finns på en OAuth-aktiverad postlåda


  
## <a name="user-and-group-assignments"></a>Användar- och grupptilldelningar

Funktionen Centraliserad distribution stöder för närvarande de flesta grupper som stöds av Azure Active Directory, inklusive Microsoft 365-grupper, distributionslistor och säkerhetsgrupper.
  
> [!NOTE]
> Säkerhetsgrupper utan e-postaktivering stöds inte för närvarande. 
  
Centraliserad distribution stöder tilldelningar till enskilda användare, grupper och alla i klienten. Centraliserad distribution har stöd för användare i grupper på översta nivå och grupper utan överordnade grupper, men inte för användare i kapslade grupper och grupper som har överordnade grupper.
   
Ta en titt på följande exempel där Sandra, Sheila och gruppen Sales Department har tilldelats till ett tillägg. Eftersom West Coast Sales Department är en kapslad grupp, tilldelas Jens och Erik inte till ett tillägg.
  
![Diagram över försäljningsavdelningen](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a>Ta reda på om en grupp innehåller kapslade grupper

Det enklaste sättet att upptäcka om en grupp innehåller kapslade grupper är att visa gruppens kontaktkort i Outlook. Om du anger gruppnamnet i fältet **Till** i ett e-postmeddelande och sedan väljer gruppnamnet när det lösers visas om det innehåller användare eller kapslade grupper. I exemplet nedan visas inga användare och bara två undergrupper på fliken **Medlemmar** för Outlook-kontaktkortet för Test Group. 
  
![Fliken Medlemmar på Kontaktkortet i Outlook](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
Du kan göra motsatt fråga genom att matcha gruppen och ta reda på om den är medlem i en grupp. I exemplet nedan kan du se att Sub Group 1 är medlem i Test Group under fliken **medlemskap** för Outlook-kontaktkortet. 
  
![Fliken Medlemskap i Outlook-kontaktkortet](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
Du kan också använda Azure Active Directory Graph API till att köra frågor för att hitta listan med grupper inom en grupp. Mer information finns i [Åtgärder för grupper | Referens för Graph API](https://go.microsoft.com/fwlink/p/?linkid=846342).
  
### <a name="contacting-microsoft-for-support"></a>Kontakta Microsoft om du behöver support

Om du eller dina användare stöter på problem med att läsa in tillägget när du använder Office-appar för webben (Word, Excel osv.), som har distribuerats centralt, kan du behöva kontakta Microsoft-supporten ([läs mer](../contact-support-for-business-products.md)). Ange följande information om din Microsoft 365-miljö i supportbiljetten.
  
|**Plattform**|**Felsökningsinformation**|
|:-----|:-----|
|Office  <br/> | Charles-/Fiddler-loggar  <br/>  Klientorganisationens id ( [så här gör du](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))  <br/>  CorrelationID. Visa källan till en av kontorssidorna och leta efter värdet för korrelations-ID och skicka det till stöd:  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|RTF-klienter (Windows, Mac)  <br/> | Charles-/Fiddler-loggar  <br/>  Bygg nummer på klientappen (helst som en skärmdump från **Arkiv/Konto)**  <br/> |
   

