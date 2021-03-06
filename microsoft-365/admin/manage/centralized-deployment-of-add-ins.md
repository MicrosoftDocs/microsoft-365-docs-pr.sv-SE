---
title: Avgöra om centraliserad distribution av tillägg fungerar för din organisation
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: Avgör om klientorganisationen och användarna uppfyller kraven, så att du kan använda centraliserad distribution för Office tillägg.
ms.openlocfilehash: 5d6f225acb56d1ec092046297d708444bb8d93d2
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227962"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a>Avgöra om centraliserad distribution av tillägg fungerar för din organisation

Centraliserad distribution är den rekommenderade och mest funktionsrika sättet för de flesta kunder att Office tillägg till användare och grupper i organisationen. Om du är administratör kan du använda den här vägledningen för att ta reda på om organisationen och användarna uppfyller kraven för centraliserad distribution.

Centraliserad distribution har följande fördelar:

- En global administratör kan tilldela ett tillägg direkt till en användare, till flera användare via en grupp eller till alla i organisationen.

- När det Office programmet startas laddas tillägget ned automatiskt. Om tillägget har stöd för tilläggskommandon visas det automatiskt i menyfliksområdet i Office program.

- Tillägg visas inte längre för användare om administratören stänger av eller tar bort tillägget, eller om användaren tas bort från Azure Active Directory eller från en grupp som tillägget har tilldelats.

Centraliserad distribution har stöd för tre plattformar Windows, Mac och Online Office program. Centraliserad distribution har också stöd för iOS Outlook Android (endast för mobila tillägg).

Det kan ta upp till 24 timmar för ett tillägg att visas för klienten och alla användare.

## <a name="before-you-begin"></a>Innan du börjar

Centraliserad distribution av tillägg kräver att användarna använder Microsoft 365 Enterprise SKU:er: E3/E5/F3 eller Företags-SKU:er: Business Basic, Business Standard, Business Premium (och är inloggade på Office med sitt organisations-ID) och har Exchange Online och aktiva Exchange Online-postlådor. Prenumerationskatalogen måste finnas i eller vara extern till Azure Active Directory.
Du kan visa specifika krav för Office och Exchange nedan, eller använda kompatibilitetskontrollen för [centraliserad distribution.](#centralized-deployment-compatibility-checker)

Centraliserad distribution stöder inte följande:

- Tillägg som är inriktade på Word, Excel eller PowerPoint i Office 2013
- En lokal katalogtjänst
- Tilläggsdistribution till en Exchange-postlåda
- Tilläggsdistribution till SharePoint
- Teams appar
- Distribution av COM- (Component Object Model) Visual Studio VSTO-tillägg (Component Object Model) Office Tools for Office.
- Distributioner av Microsoft 365 som inte inkluderar Exchange Online som SKU:er: Microsoft 365-applikationer för företag och Microsoft 365-applikationer för företag.

### <a name="office-requirements"></a>Office Krav

- För Word Excel och PowerPoint tillägg måste användarna använda något av följande:
  - På en Windows enhet, version 1704 eller senare av Microsoft 365 Enterprise-SKU:er: E3/E5/F3 eller företags-SKU:er: Business Basic, Business Standard, Business Premium.
  - På Mac, version 15.34 eller senare.

- Användarna Outlook till exempel använda något av följande:
  - Version 1701 eller senare av Microsoft 365 Enterprise: E3/E5/F3 eller företags-SKU:er: Business Basic, Business Standard, Business Premium.
  - Version 1808 eller senare av Office Professional Plus 2019 eller Office Standard 2019.
  - Version 16.0.4494.1000 eller senare av Office Professional Plus 2016 (MSI) eller Office Standard 2016 (MSI)\*
  - Version 15.0.4937.1000 eller senare av Office Professional Plus 2013 (MSI) eller Office Standard 2013 (MSI)\*
  - Version 16.0.9318.1000 eller senare av Office 2016 för Mac
- Version 2.75.0 eller senare av Outlook för iOS
- Version 2.2.145 eller senare av Outlook för Android

    *MSI-Outlook visar administratörsinstallerade tillägg i rätt menyfliksområde Outlook program, inte avsnittet Mina tillägg.

### <a name="exchange-online-requirements"></a>Exchange Online krav

Microsoft Exchange lagrar tilläggsmanifesten i organisationens klientorganisation. Administratören som distribuerar tillägg och användarna som tar emot dessa tillägg måste använda en version av Exchange Online som stöder OAuth-autentisering.

Fråga organisationens Exchange-administratör om vilken konfiguration som används. OAuth-anslutning per användare kan verifieras med hjälp av PowerShell-cmdleten [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity).


### <a name="centralized-deployment-compatibility-checker"></a>Kompatibilitetskontroll för centraliserad distribution

Med hjälp av kompatibilitetskontrollen för centraliserad distribution kan du kontrollera om användarna i klientorganisationen är konfigurerade för att använda centraliserad distribution för Word, Excel och PowerPoint. Kompatibilitetskontrollen krävs inte för Outlook-stöd. Ladda [ned kompatibilitetskontrollen](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).

#### <a name="run-the-compatibility-checker"></a>Köra kompatibilitetskontrollen

1. Öppna ett PowerShell.exe-fönster med förhöjd rättighet.

2. Kör följande kommando:

   ```powershell
   Import-Module O365CompatibilityChecker
   ```

3. Kör **kommandot Invoke-CompatabilityCheck:**

   ```powershell
   Invoke-CompatibilityCheck
   ```
   Det här kommandot uppmanar dig att  *_ange TenantDomain_* (till exempel *TailspinToysIncorporated.onmicrosoft. </span> com*) och  *_TenantAdmin-autentiseringsuppgifter_* (använd dina autentiseringsuppgifter som global administratör) och begär sedan medgivande.

   > [!NOTE]
   > Beroende på antalet användare i klientorganisationen kan det ta några minuter eller några timmar att slutföra åtgärden.

När verktyget körts klart har en utdatafil i kommaavgränsat format (.csv) genererats. Filen sparas som standard **till C:\windows\system32.** Utdatafilen innehåller följande information:

- Användarnamn

- Användar-ID (användarens e-postadress)

- Centraliserad distribution är klar - om de återstående objekten har värdet sant

- Office – abonnemanget de Office är licensierade för

- Office aktiverat - om de har aktiverat Office

- Postlåda som stöds - om de finns på en OAuth-aktiverad postlåda

> [!NOTE]
> Multifaktorautentisering stöds inte när du använder PowerShell-modulen för central distribution. Modulen fungerar bara med grundläggande autentisering.

## <a name="user-and-group-assignments"></a>Användar- och grupptilldelningar

Funktionen för centraliserad distribution har för närvarande stöd för de flesta grupper som stöds av Azure Active Directory, inklusive Microsoft 365, distributionslistor och säkerhetsgrupper.

> [!NOTE]
> Säkerhetsgrupper utan e-postaktivering stöds inte för närvarande.

Centraliserad distribution har stöd för tilldelningar till enskilda användare, grupper och alla i klientorganisationen. Centraliserad distribution har stöd för användare i grupper på översta nivå och grupper utan överordnade grupper, men inte för användare i kapslade grupper och grupper som har överordnade grupper.

Ta en titt på följande exempel där Sandra, Sheila och gruppen Sales Department har tilldelats till ett tillägg. Eftersom West Coast Sales Department är en kapslad grupp, tilldelas Jens och Erik inte till ett tillägg.

![Diagram över försäljningsavdelningen](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)


### <a name="find-out-if-a-group-contains-nested-groups"></a>Ta reda på om en grupp innehåller kapslade grupper

Det enklaste sättet att upptäcka om en grupp innehåller kapslade grupper är att visa gruppens kontaktkort i Outlook. Om du anger gruppens  namn i fältet Till i ett e-postmeddelande och sedan väljer gruppens namn när det matchas visas om den innehåller användare eller kapslade grupper. I exemplet nedan visas inga användare och bara två undergrupper på fliken **Medlemmar** för Outlook-kontaktkortet för Test Group.

![Fliken Medlemmar på Outlook kontaktkort](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)

Du kan göra motsatt fråga genom att matcha gruppen och ta reda på om den är medlem i en grupp. I exemplet nedan kan du se att Sub Group 1 är medlem i Test Group under fliken **medlemskap** för Outlook-kontaktkortet.

![Fliken Medlemskap på Outlook kontaktkort](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)

Du kan också använda Azure Active Directory Graph API till att köra frågor för att hitta listan med grupper inom en grupp. Mer information finns i [Åtgärder för grupper | Referens för Graph API](/previous-versions/azure/ad/graph/api/groups-operations).

### <a name="contacting-microsoft-for-support"></a>Kontakta Microsoft om du behöver support

Om du eller dina användare stöter på problem med att läsa in tillägget när du använder Office-appar för webben (Word, Excel osv.), som distribuerats centralt, kan du behöva kontakta Microsofts support (så här[gör du).](../../business-video/get-help-support.md) Ange följande information om din Microsoft 365 i supporten.

|**Plattform**|**Felsökningsinformation**|
|:-----|:-----|
|Office  <br/> | Charles-/Fiddler-loggar  <br/>  Klientorganisations-ID ([så här gör du](/onedrive/find-your-office-365-tenant-id))  <br/>  CorrelationID. Visa källan för en av Office-sidorna, leta efter värdet för Korrelations-ID och skicka det till supporten:  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|RTF-klienter (Windows, Mac)  <br/> | Charles-/Fiddler-loggar  <br/>  Versionsnummer för klientappen (helst som en skärmbild från **Arkiv/Konto**)  <br/> |

## <a name="related-content"></a>Relaterat innehåll

[Distribuera tillägg i administrationscentret](../manage/manage-deployment-of-add-ins.md) (artikel)\
[Hantera tillägg i administrationscentret](manage-addins-in-the-admin-center.md) (artikel)\
[Vanliga frågor och svar om centraliserad](../manage/centralized-deployment-faq.md) distribution (artikel)\
[Uppgradera dina Microsoft 365 för företag-användare till den senaste Office klient](../setup/upgrade-users-to-latest-office-client.md) (artikel)
 