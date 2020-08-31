---
title: Planera konfigurationen av Microsoft 365 för företag
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: eb926624-018b-4486-bf11-5fba6ee4d645
description: Läs mer om kraven och överväganden för att flytta till Microsoft 365 för företag.
ms.openlocfilehash: 14543e3859f06e7f89cf74e2159a70483c7ec228
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307549"
---
# <a name="plan-your-setup-of-microsoft-365-for-business"></a>Planera konfigurationen av Microsoft 365 för företag

Den här artikeln är till för personer som prenumererar på ett Microsoft 365 för företag-abonnemang.
  
Innan du flyttar din organisation till Microsoft 365 måste du uppfylla alla krav som du behöver för att få till hands och få beslut.


  
## <a name="info-to-have-on-hand-before-you-run-the-setup-wizard"></a>Information att ha till hands innan du kör installations guiden

När du är redo att köra installations guiden och flytta domänen till Microsoft 365 måste du ha till gång till följande uppgifter:
  
- Lista över personer som du vill lägga till i Microsoft 365. Även om du redan har lagt till dem i Microsoft 365 måste du ange deras namn här.

- Hur du kommer att meddela dina anställda om deras användar-ID och lösen ord så att de kan logga in. Ger du dem informationen över telefon? Eller skickar du den till deras privata e-postadresser? De har ingen åtkomst till deras e-post, så du kan inte använda det.

- Om du har ett domän namn för organisationen (till exempel contoso.com) **och** du planerar att använda Microsoft-e-post måste du veta var domänen är registrerad och ha inloggnings information.

## <a name="what-happens-when-you-run-the-microsoft-365-setup-wizard"></a>Vad händer när du kör installations guiden för Microsoft 365

I installations guiden får du hjälp med att installera Microsoft 365-programmen på datorn, lägga till och verifiera din domän, lägga till användare och tilldela licenser till dem och ansluta din domän.

> [!NOTE]
> Om du behöver [tilldela administratörs roller i Microsoft 365 för företag](../add-users/assign-admin-roles.md) till de användare du lägger till i guiden kan du göra det senare på sidan **användare** . 
  
Om du inte slutför installations guiden kan du slutföra installations uppgifter när som helst från installationen av [administrations centret](https://go.microsoft.com/fwlink/p/?linkid=2024339)  >  **Setup**. Härifrån kan du migrera e-post och kontakter från en annan e-posttjänst, ändra domänen för administratörs kontot, hantera fakturerings uppgifter, lägga till eller ta bort användare, återställa lösen ord och göra andra affärs funktioner. Mer information om skillnaderna mellan installations guiden och sidan **konfiguration** finns i [skillnader mellan Microsoft 365-installationsprogrammet och inställnings sidan](o365-setup-wizard-and-setup-page.md).

Kontakta oss om du kör fast. [Vi hjälper gärna till!](../contact-support-for-business-products.md)
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>När du inte ska använda installationsguiden: Active Directory-synkronisering och hybridmiljöer

Det finns ett par scenarion som inkluderar att migrera data eller användare från lokala miljöer eller att konfigurera ett hybrid system som inkluderar katalog-synkronisering. Om du befinner dig i någon av kategorierna följer du anvisningarna i de här artiklarna:
  
- Om du vill konfigurera profilsynkronisering med den lokala Active Directory-funktionen läser du [Konfigurera katalogs-synkronisering för microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)och förstår de olika identitets modellerna i Microsoft 365, läser du [förstå Microsoft 365 Identity och Azure Active Directory](https://docs.microsoft.com/microsoft-365/enterprise/about-microsoft-365-identity).

- Här finns fullständiga instruktioner som hjälper dig igenom alla olika sätt att konfigurera en Exchange-hybrid (inklusive hur du konfigurerar DNS-poster): [Exchange Server Deployment Assistant](https://aka.ms/exdeploy)

- Om du vill konfigurera en SharePoint-hybrid, och då främst sök- och webbplatsfunktioner, går du till [Hybridsökning i SharePoint](https://docs.microsoft.com/SharePoint/hybrid/hybrid-search-in-sharepoint).

## <a name="move-to-microsoft-365-all-at-once-or-in-stages"></a>Flytta till Microsoft 365 alla på en gång eller i olika faser

- **Vill du flytta din organisation till Microsoft 365 samtidigt?** I så fall kan du planera för att flytta domänen till Microsoft 365 direkt. Börja med att köra installations guiden för Microsoft 365. du uppmanas att konfigurera din domän.

- **Vill du flytta till Microsoft 365 gradvis?** Om du vill gå till Microsoft 365 i steg kan du hoppa över att köra installations guiden för Microsoft 365 och överväga att använda Microsoft 365-funktioner i följande ordning:

    1. [Lägg till dina anställda till Microsoft 365](../add-users/add-users.md) så att de kan ladda ned och installera Office-apparna.

    2. [Ladda ned och installera Office-programmen](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) för att kunna använda Word, Excel och PowerPoint på datorer och enheter.

    3. [Konfigurera Microsoft Teams](#plan-for-teams) för möten.

    4. [Flytta innehållet till Microsoft 365 Cloud Storage](set-up-file-storage-and-sharing.md) (OneDrive eller SharePoint-gruppwebbplatser).

    5. När du är klar väljer du **Konfigurera** i det vänstra navigerings fönstret i [administrations centret](https://go.microsoft.com/fwlink/p/?linkid=2024339)och använder sidan **konfiguration** för att [Flytta domänen och e-postmeddelandet](add-domain.md).

## <a name="check-that-your-devices-meet-system-requirements"></a>Kontrollera att enheterna uppfyller systemkraven

Varje person i organisationen kan installera Office 2016-sviten (Word, Excel, PowerPoint och så vidare) på upp till fem PC-och Mac-datorer. Se operativsystem- och datorkraven för installation av [Office 2016-paket](https://go.microsoft.com/fwlink/?LinkId=534827) för företag.
  
Mobil program kan installeras på iOS-, Android-och Windows-enheter. Du hittar mer information om stöd för mobila enheter och webbläsare i [Systemkrav för Office](https://go.microsoft.com/fwlink/?LinkId=534827).
  
## <a name="plan-for-email"></a>Planera för e-post

Om du planerar att flytta från en befintlig e-posttjänst till Microsoft 365 tar det vanligt vis två dagar att byta.
  
### <a name="plan-for-email-downtime"></a>Planera för driftsavbrott för e-post
  
Om du ska använda Microsoft 365 för din e-post:
  
- Om du vill flytta din företags e-postadress (till exempel *anders \@ contoso.com*) från en annan e-posttjänst till Microsoft 365 måste du skicka din e-post till din nya Microsoft 365-postlåda. Det gör du genom att välja **migrera användarnas data** på **konfigurations** sidan, där vi vägleder dig genom de uppdateringar som du måste göra på din domän värd, steg för steg.

- När du har uppdaterat värden för domänen börjar ändringarna vanligtvis att gälla efter bara en timme eller två. Men det kan ta upp till 72 timmar för ändringarna att uppdatera på Internet.

- Eftersom du kan ha e-postnertid rekommenderar vi att du planerar att byta till Microsoft-e-post under en kväll eller helg när du får färre e-postmeddelanden.

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>Planera att flytta dina befintliga e-postmeddelanden, kontakter och kalendrar
  
Om du ska använda Microsoft 365 för ditt e-postkonto kan du ta med dig din befintliga e-post, dina kontakter och din kalender. Med **installations** sidan kan du flytta dina befintliga e-postmeddelanden och kontakter till de flesta tillfällen. Det finns även stegvisa instruktioner för att flytta en eller flera postlådor.
  
|**Hur många postlådor?**|**Rekommendation**|
|:-----|:-----|
|Några få  <br/> |Om du inte vill använda sidan **Inställningar** för att migrera post lådorna kan du låta post lådor migrera sina egna e-postmeddelanden och kontakter. Se [migrera e-post och kontakter till Microsoft 365 för företag](migrate-email-and-contacts-admin.md).  <br/> |
|Flera  <br/> |Om du migrerar från Gmail läser du [migrera G Suite-postlådor till Microsoft 365](https://docs.microsoft.com/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes).  <br/> Om du migrerar från en annan e-postleverantör, inklusive Exchange, se [olika sätt att migrera flera e-postkonton till Microsoft 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>Planera för lagring och migrering av filer

Microsoft 365 tillhandahåller moln lagring för enskilda personer, små organisationer och företag. Information om vad du kan lagra finns i [var du ska kunna lagra dokument i Microsoft 365](https://support.microsoft.com/office/c7c20284-bc94-47f4-9728-d28e9daf0790).
  
- **Du kan flytta hundratals filer** till [OneDrive](https://support.microsoft.com/office/45114744-6D42-45CD-8975-F9617819BDEB) eller till en [SharePoint-gruppwebbplats](https://support.microsoft.com/office/da549fb1-1fcb-4167-87d0-4693e93cb7a0#__toc384119242). Du kan ladda upp 100 filer åt gången. Undvik att ladda upp filer som är större än 2 GB, eftersom det är den största tillåtna filstorleken som standard.
  
- **Om du vill flytta flera tusen filer** till Microsoft 365-lagring granskar du [gränserna för SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=856113). Vi rekommenderar att du använder ett migreringsverktyg och överväger att anlita en [partner](https://go.microsoft.com/fwlink/?linkid=391089) som kan hjälpa dig med migreringen. Mer information om hur du migrerar ett stort antal filer finns i [Användarhandbok om SharePoint Online- och OneDrive-migrering](https://go.microsoft.com/fwlink/?LinkId=723574).
  
## <a name="plan-for-teams"></a>Planera för Teams

Du kan använda Microsoft Teams för att ringa till andra personer i organisationen som är på ditt abonnemang. Om din organisation till exempel har tio personer kan du ringa och chatta med varandra genom att använda Teams utan någon särskild installation. Mer information finns i [komma igång med Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-quick-start).

För större organisationer eller om du startar från Skype för företag, lokala eller hybrid installationer kan du läsa [hur du kan lansera Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/how-to-roll-out-teams).
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>Planera för integrering med Active Directory eller annan programvara

- **Vill du integrera med din lokala Active Directory?** Du kan integrera din lokala Active Directory med Microsoft 365 genom att använda Azure Active Directory Connect. Anvisningar finns i [Konfigurera katalog synkronisering för Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization).
  
- **Vill du integrera Microsoft 365 med program som har gjorts av andra företag?** Om du behöver integrera Microsoft 365 med andra program i organisationen rekommenderar vi att du [anställer en partner](https://go.microsoft.com/fwlink/?linkid=391089) för att hjälpa dig med din distribution.
  
## <a name="do-you-want-someone-to-help-you-set-up-microsoft-365"></a>Vill du att någon ska hjälpa dig att konfigurera Microsoft 365?

- **Om du har färre än 50 anställda:**

  - **Be om hjälp så ringer vi dig**. När du har köpt Microsoft 365 kan du få till gång till administrations centret (du behöver inte köra installations programmet för att komma till det). Välj **behöver du hjälp** längst ned i administrations centret? Beskriv problemet så ringer vi upp dig. 
  - **Ring [supporten för Microsoft 365 för företag](../contact-support-for-business-products.md) med dina frågor**. Vi hjälper gärna till! 
  - **Du kan även anlita en [Microsoft-partner](https://go.microsoft.com/fwlink/?linkid=391089)**. Om du är kort på tid eller har avancerade krav (som att flytta tusen filer till Microsoft 365-molnet eller integrera med annan program vara) kan en erfaren partner vara en omfattande hjälp. 

- **Om du har fler än 50 anställda** kan [FastTrack-introduktionscentret](https://go.microsoft.com/fwlink/?LinkId=517115) hjälpa dig med distributionen. 
