---
title: Planera konfigurationen av Microsoft 365 för företag
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- MET150
- MOE150
ms.assetid: eb926624-018b-4486-bf11-5fba6ee4d645
description: Läs mer om kraven och övervägandena när det gäller att gå över till Microsoft 365 för företag.
ms.openlocfilehash: b4d2b5d500b73b62c67d3f8126b6313484e2bc78
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297038"
---
# <a name="plan-your-setup-of-microsoft-365-for-business"></a>Planera konfigurationen av Microsoft 365 för företag

Den här artikeln är till för personer som prenumererar på ett Microsoft 365 för företag-abonnemang.
  
Innan du flyttar organisationen till Microsoft 365 finns det krav som du måste uppfylla, information du behöver ha till hands och beslut du måste fatta.


  
## <a name="info-to-have-on-hand-before-you-run-the-setup-wizard"></a>Information du behöver ha till hands innan du kör installationsguiden

När du är redo att köra installationsguiden och flytta din domän till Microsoft 365 behöver du ha den här informationen till hands:
  
- Lista över personer som du vill lägga till i Microsoft 365. Även om du redan har lagt till dem i Microsoft 365 måste du ange deras namn här om du uppdaterar domäninformationen.

- Hur du meddelar de anställda om deras användar-ID och lösenord så att de kan logga in. Ger du dem informationen över telefon? Eller skickar du den till deras privata e-postadresser? De har inte åtkomst till sin e-post, så du kan inte använda den.

- Om du har ett domännamn för din organisation (till exempel **contoso.com)** och planerar att använda Microsofts e-post, måste du veta var domänen är registrerad och ha inloggningsinformation.

## <a name="what-happens-when-you-run-the-microsoft-365-setup-wizard"></a>Vad händer när du kör Microsoft 365-installationsguiden?

I installationsguiden får du hjälp med att installera Microsoft 365-appar på datorn, lägga till och verifiera din domän, lägga till användare och tilldela licenser till dem och ansluta domänen.

> [!NOTE]
> Om du behöver tilldela [administratörsroller](../add-users/assign-admin-roles.md) i Microsoft 365 för företag till de användare som du lägger till i guiden kan du göra det senare på **sidan** Användare. 
  
Om du inte har slutfört installationsguiden kan du slutföra installationsuppgifterna när som helst från [installationsprogrammet för](https://go.microsoft.com/fwlink/p/?linkid=2024339)  >  **administrationscentret.** Härifrån kan du migrera e-post och kontakter från en annan e-posttjänst, ändra domänen för ditt administratörskonto, hantera din faktureringsinformation, lägga till eller ta bort användare, återställa lösenord och göra andra affärsfunktioner. Mer information om skillnaderna mellan installationsguiden  och sidan Inställningar finns i Skillnader mellan Microsoft 365 [och installationsprogrammet.](o365-setup-wizard-and-setup-page.md)

Kontakta oss om du kör fast. [Vi hjälper gärna till!](../../business-video/get-help-support.md)
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>När du inte ska använda installationsguiden: Active Directory-synkronisering och hybridmiljöer

Det finns några scenarier som omfattar att migrera data eller användare från lokala miljöer eller konfigurera ett hybridsystem som inkluderar katalogsynkronisering. Om du är i någon av kategorierna följer du anvisningarna i följande artiklar:
  
- Om du vill konfigurera katalogsynkronisering med din lokala Active Directory läser du Konfigurera katalogsynkronisering för [Microsoft 365](../../enterprise/set-up-directory-synchronization.md)och om du vill förstå de olika identitetsmodellerna i Microsoft 365 kan du läsa Förstå Microsoft 365 identitet [och Azure Active Directory.](../../enterprise/about-microsoft-365-identity.md)

- Här finns fullständiga instruktioner som hjälper dig igenom alla olika sätt att konfigurera en Exchange-hybrid (inklusive hur du konfigurerar DNS-poster): [Exchange Server Deployment Assistant](/exchange/exchange-deployment-assistant)

- Om du vill konfigurera en SharePoint-hybrid, och då främst sök- och webbplatsfunktioner, går du till [Hybridsökning i SharePoint](/SharePoint/hybrid/hybrid-search-in-sharepoint).

## <a name="move-to-microsoft-365-all-at-once-or-in-stages"></a>Flytta till Microsoft 365 allt på en gång eller i faser

- **Vill du flytta hela organisationen till Microsoft 365 gång?** I så fall bör du planera att flytta din domän Microsoft 365 omedelbart. Börja med att Microsoft 365 installationsguiden. uppmanas du att konfigurera din domän.

- **Vill du flytta till Microsoft 365 gradvis?** Om du vill gå Microsoft 365 stegvis hoppar du över Microsoft 365 installationsguiden och överväg att införa Microsoft 365 funktioner i följande ordning:

    1. [Lägg till dina anställda Microsoft 365](../add-users/add-users.md) så att de kan ladda ned och installera Office program.

    2. [Ladda ned och installera Office-programmen](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) för att kunna använda Word, Excel och PowerPoint på datorer och enheter.

    3. [Konfigurera Microsoft Teams](#plan-for-teams) för möten.

    4. [Flytta innehåll till Microsoft 365 molnlagring (OneDrive](set-up-file-storage-and-sharing.md) eller SharePoint gruppwebbplatser).

    5. När du är klar går du  till administrationscentret [,](https://go.microsoft.com/fwlink/p/?linkid=2024339)väljer Konfigurera  i det vänstra navigeringsfönstret och använder sidan Inställningar för att flytta din [domän och e-post.](add-domain.md)

## <a name="check-that-your-devices-meet-system-requirements"></a>Kontrollera att enheterna uppfyller systemkraven

Varje person i organisationen kan installera Office 2016-programsviten (Word, Excel, PowerPoint och så vidare) på upp till fem PC- och Mac-datorer. Se operativsystem- och datorkraven för installation av [Office 2016-paket](https://go.microsoft.com/fwlink/?LinkId=534827) för företag.
  
Mobilappar kan installeras på iOS-, Android- och Windows enheter. Du hittar mer information om stöd för mobila enheter och webbläsare i [Systemkrav för Office](https://go.microsoft.com/fwlink/?LinkId=534827).
  
## <a name="plan-for-email"></a>Planera för e-post

Om du planerar att flytta från en befintlig e-posttjänst till Microsoft 365 tar det vanligtvis två dagar att byta.
  
### <a name="plan-for-email-downtime"></a>Planera för driftsavbrott för e-post
  
Om du kommer att använda Microsoft 365 för din e-post:
  
- Om du vill flytta din e-postadress för företaget (till exempel *rob \@ contoso.com)* från en annan e-posttjänst till Microsoft 365 måste du dirigera din e-post så att den levereras till din nya Microsoft 365 postlåda. Det gör du genom att välja  Migrera användarnas **data** på sidan Installation, där du vägleder dig genom de uppdateringar du behöver göra hos värden för domänen, steg för steg.

- När du har uppdaterat värden för domänen börjar ändringarna vanligtvis att gälla efter bara en timme eller två. Men tänk på att det ibland kan ta upp till 72 timmar innan ändringarna har uppdaterats på hela Internet.

- Eftersom det kan leda till avbrott i e-posten rekommenderar vi att du planerar att byta till Microsoft-e-post under en kväll eller helg när du får färre e-postmeddelanden.

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>Planera att flytta dina befintliga e-postmeddelanden, kontakter och kalendrar
  
Om du kommer att använda Microsoft 365 för ditt e-postkonto kan du ta med dig befintliga e-postmeddelanden, kontakter och kalendrar. På **sidan Konfigurera** kan du flytta befintliga e-postmeddelanden och kontakter för de flesta scenarier. Det finns även stegvisa instruktioner för att flytta en eller flera postlådor.
  
|**Hur många postlådor?**|**Rekommendation**|
|:-----|:-----|
|Några få  <br/> |Om du inte vill använda  sidan Konfigurera för att migrera postlådorna kan du låta postlådeägare migrera sina egna e-postmeddelanden och kontakter. Se [Migrera e-post och kontakter till Microsoft 365 för företag.](migrate-email-and-contacts-admin.md)  <br/> |
|Flera  <br/> |Om du migrerar från Gmail kan du gå till [Migrera G Suite-postlådor till Microsoft 365.](/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes)  <br/> Om du migrerar från en annan e-postleverantör, inklusive e Exchange finns information i Olika sätt att migrera flera [e-postkonton till Microsoft 365.](/Exchange/mailbox-migration/mailbox-migration)  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>Planera för lagring och migrering av filer

Microsoft 365 ger molnlagring för individer, små organisationer och företag. Information om vad du lagrar var finns i [Var du kan lagra dokument i Microsoft 365](../../business-video/store-files.md).
  
- **Du kan flytta hundratals filer till** OneDrive eller till en SharePoint [gruppwebbplats.](https://support.microsoft.com/office/da549fb1-1fcb-4167-87d0-4693e93cb7a0#__toc384119242) [](https://support.microsoft.com/office/45114744-6D42-45CD-8975-F9617819BDEB) Du kan ladda upp 100 filer åt gången. Undvik att ladda upp filer som är större än 2 GB, eftersom det är den största tillåtna filstorleken som standard.
  
- **Om du vill flytta flera tusen filer till Microsoft 365** lagringsutrymme kan du läsa mer SharePoint [onlinebegränsningar.](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) Vi rekommenderar att du använder ett migreringsverktyg och överväger att anlita en [partner](https://go.microsoft.com/fwlink/?linkid=391089) som kan hjälpa dig med migreringen. Mer information om hur du migrerar ett stort antal filer finns i [Användarhandbok om SharePoint Online- och OneDrive-migrering](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets).
  
## <a name="plan-for-teams"></a>Planera för Teams

Du kan använda Microsoft Teams ringa samtal till andra i organisationen som ingår i din prenumeration. Om ni till exempel har 10 anställda i organisationen kan ni ringa och snabbmeddelandekonversera varandra Teams någon särskild konfiguration. Mer information finns i [Komma igång med Microsoft Teams](/MicrosoftTeams/get-started-with-teams-quick-start).

För större organisationer eller om du börjar Skype för företag, lokalt eller hybriddistribution finns mer information i [Distribuera Microsoft Teams](/MicrosoftTeams/how-to-roll-out-teams).
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>Planera för integrering med Active Directory eller annan programvara

- **Vill du integrera med din lokala Active Directory?** Du kan integrera din lokala Active Directory med Microsoft 365 med hjälp av Azure Active Directory Anslut. Anvisningar finns i Konfigurera [katalogsynkronisering för Microsoft 365](../../enterprise/set-up-directory-synchronization.md).
  
- **Vill du integrera Microsoft 365 programvara som har gjorts av andra företag?** Om du behöver integrera Microsoft 365 med annan programvara i organisationen rekommenderar vi att du överväger att anlita en [partner](https://go.microsoft.com/fwlink/?linkid=391089) som kan hjälpa dig med distributionen.
  
## <a name="do-you-want-someone-to-help-you-set-up-microsoft-365"></a>Vill du att någon ska hjälpa dig att Microsoft 365?

- **Om du har färre än 50 anställda:**

  - **Be om hjälp så ringer vi dig**. När du Microsoft 365 administratörscentret (du behöver inte köra konfigurationen för att komma åt det). Välj Behöver du hjälp längst ned i **administrationscentret?** Beskriv problemet så ringer vi upp dig. 
  - **Ring [Microsoft 365 för företag-supporten](../../business-video/get-help-support.md) med dina frågor.** Vi hjälper gärna till! 
  - **Du kan även anlita en [Microsoft-partner](https://go.microsoft.com/fwlink/?linkid=391089)**. Om du har ont om tid eller har avancerade krav (som att flytta tusentals filer till Microsoft 365 molnlagring eller att integrera med annan programvara) kan en erfaren partner vara till stor hjälp. 

- **Om du har fler än 50 anställda** kan [FastTrack-introduktionscentret](https://go.microsoft.com/fwlink/?LinkId=517115) hjälpa dig med distributionen.