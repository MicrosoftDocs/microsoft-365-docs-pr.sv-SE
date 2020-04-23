---
title: Planera installationen av Microsoft 365 för företag
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
search.appverid:
- MET150
- MOE150
ms.assetid: eb926624-018b-4486-bf11-5fba6ee4d645
description: Läs om vad du behöver göra för att konfigurera Microsoft 365 för företag.
ms.openlocfilehash: d02e1aaf03449bd976b8db549274002b3ebb6ed6
ms.sourcegitcommit: b458277f0a9937555bc6c5b3fb2a41613f7cc9a9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/23/2020
ms.locfileid: "43794045"
---
# <a name="plan-your-setup-of-microsoft-365-for-business"></a>Planera installationen av Microsoft 365 för företag

Den här artikeln är avsedd för personer som prenumererar på en Microsoft 365 for Business-plan.
  
Det finns några saker du måste bestämma och information som du måste ha till hands innan du flyttar organisationen till Microsoft 365.
  
## <a name="info-to-have-on-hand-before-you-run-the-setup-wizard"></a>Information som du kan ha till hands innan du kör installationsguiden

När du är redo att köra installationsguiden och flytta domänen till Microsoft 365 måste du ha den information du behöver ha till hands:
  
- Lista över personer som du vill lägga till i Microsoft 365. Även om du redan har lagt till dem i Microsoft 365 måste du ange deras namn här om du uppdaterar domäninformationen.

- Hur du ska meddela dina anställda om deras användar-ID och lösenord så att de kan logga in. Ger du dem informationen över telefon? Eller skickar du den till deras privata e-postadresser? De har inte tillgång till sin e-post, så du kan inte använda den.

- Om du har ett domännamn för din organisation (till exempel contoso.com) **och** du planerar att använda Microsoft-e-post måste du veta var din domän är registrerad och ha inloggningsinformation.

## <a name="what-happens-when-you-run-the-microsoft-365-setup-wizard"></a>Vad händer när du kör installationsguiden för Microsoft 365

I installationsguiden går du igenom installation av Microsoft 365-appar på datorn, lägger till och verifierar domänen, lägger till användare och tilldelar licenser till dem och ansluter domänen.

> [!NOTE]
> Om du behöver [tilldela administratörsroller i Microsoft 365 för företag](../add-users/assign-admin-roles.md) till de användare som du lägger till i guiden kan du göra det senare på sidan **Användare.** 
  
Om du inte slutför installationsguiden kan du när som helst slutföra installationsuppgifterna från**installationsprogrammet för** [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=2024339) > . Härifrån kan du migrera e-post och kontakter från en annan e-posttjänst, ändra domänen för ditt administratörskonto, hantera din faktureringsinformation, lägga till eller ta bort användare, återställa lösenord och utföra andra affärsfunktioner. Mer information om skillnaderna mellan installationsguiden och **installationssidan** finns i [Skillnader mellan installationsguiden för Microsoft 365 och installationssidan](o365-setup-wizard-and-setup-page.md).

Kontakta oss om du kör fast. [Vi hjälper gärna till!](../contact-support-for-business-products.md)
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>När du inte ska använda installationsguiden: Active Directory-synkronisering och hybridmiljöer

Det finns ett par scenarier som inkluderar antingen migrera data eller användare från lokala miljöer eller ställa in ett hybridsystem som innehåller katalogsynkronisering. Om du är i någon av kategorierna följer du instruktionerna i följande artiklar:
  
- Information om hur du konfigurerar katalogsynkronisering med din lokala Active Directory finns i [Konfigurera katalogsynkronisering för Microsoft 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)och förstå de olika identitetsmodellerna i Microsoft 365 genom att läsa [Förstå Microsoft 365-identitet och Azure Active Directory](https://docs.microsoft.com/office365/enterprise/about-office-365-identity).

- Här finns fullständiga instruktioner som hjälper dig igenom alla olika sätt att konfigurera en Exchange-hybrid (inklusive hur du konfigurerar DNS-poster): [Exchange Server Deployment Assistant](https://aka.ms/exdeploy)

- Om du vill konfigurera en SharePoint-hybrid, och då främst sök- och webbplatsfunktioner, går du till [Hybridsökning i SharePoint](https://docs.microsoft.com/SharePoint/hybrid/hybrid-search-in-sharepoint).

## <a name="move-to-microsoft-365-all-at-once-or-in-stages"></a>Flytta till Microsoft 365 på en gång eller i etapper

- **Vill du flytta din organisation till Microsoft 365 på en gång?** Om så är fallet planerar du att flytta domänen till Microsoft 365 direkt. Börja med att köra installationsguiden för Microsoft 365. Det kommer att uppmana dig att ställa in din domän.

- **Vill du flytta till Microsoft 365 gradvis?** Om du vill flytta till Microsoft 365 stegvis hoppar du över att köra installationsguiden för Microsoft 365 och överväg att använda Microsoft 365-funktioner i följande ordning:

    1. [Lägg till dina anställda i Microsoft 365](../add-users/add-users.md) så att de kan hämta och installera Office-programmen.

    2. [Ladda ned och installera Office-programmen](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx) för att kunna använda Word, Excel och PowerPoint på datorer och enheter.

    3. [Konfigurera Microsoft Teams](#plan-for-teams) som ska användas för dina möten.

    4. [Flytta ditt innehåll till Microsoft 365-molnlagring](set-up-file-storage-and-sharing.md) (OneDrive- eller SharePoint-gruppwebbplatser).

    5. När du är klar väljer du **Inställningar** i det vänstra navigeringsfönstret i [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=2024339)och använder **inställningssidan** för att [flytta domänen och e-postmeddelandet](add-domain.md).

## <a name="check-that-your-devices-meet-system-requirements"></a>Kontrollera att enheterna uppfyller systemkraven

Varje person i organisationen kan installera Office 2016-paketet med appar (Word, Excel, PowerPoint och så vidare) på upp till fem datorer och Mac-datorer. Se operativsystem- och datorkraven för installation av [Office 2016-paket](https://go.microsoft.com/fwlink/?LinkId=534827) för företag.
  
Mobilappar kan installeras på iOS-, Android- och Windows-enheter. Du hittar mer information om stöd för mobila enheter och webbläsare i [Systemkrav för Office](https://go.microsoft.com/fwlink/?LinkId=534827).
  
## <a name="plan-for-email"></a>Planera för e-post

Om du planerar att flytta från en befintlig e-posttjänst till Microsoft 365 tar det vanligtvis två dagar att byta.
  
### <a name="plan-for-email-downtime"></a>Planera för driftsavbrott för e-post
  
Om du ska använda Microsoft 365 för din e-post:
  
- Om du vill flytta företagets e-postadress (till exempel *\@rob contoso.com)* från en annan e-posttjänst till Microsoft 365 måste du dirigera din e-post som ska levereras till din nya Microsoft 365-postlåda. Du gör detta genom att välja **Migrera användarnas data** på **installationssidan,** där vi guidar dig genom de uppdateringar du behöver göra på din domänvärd, steg för steg.

- När du har uppdaterat värden för domänen börjar ändringarna vanligtvis att gälla efter bara en timme eller två. Men tänk på att det ibland kan ta upp till 72 timmar för ändringarna att uppdatera över internet.

- Eftersom du kan ha avbrott i e-post rekommenderar vi att du planerar att byta till Microsoft-e-post under en kväll eller helg när du får färre e-postmeddelanden.

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>Planera att flytta dina befintliga e-postmeddelanden, kontakter och kalendrar
  
Om du ska använda Microsoft 365 för ditt e-postkonto kan du ta med dig din befintliga e-post, dina kontakter och din kalender. På **inställningssidan** kan du flytta din befintliga e-post och dina kontakter för de flesta scenarier. Det finns även stegvisa instruktioner för att flytta en eller flera postlådor.
  
|**Hur många postlådor?**|**Rekommendation**|
|:-----|:-----|
|Några få  <br/> |Om du inte vill använda **sidan Inställningar** för att migrera postlådorna kan du låta postlådeägare migrera sin egen e-post och sina egna kontakter. Se [Migrera e-post och kontakter till Microsoft 365 för företag](migrate-email-and-contacts-admin.md).  <br/> |
|Flera  <br/> |Om du migrerar från Gmail läser du [Migrera G Suite-postlådor till Microsoft 365](https://docs.microsoft.com/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes).  <br/> Om du migrerar från en annan e-postleverantör, inklusive Exchange, läser du [Olika sätt att migrera flera e-postkonton till Microsoft 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>Planera för lagring och migrering av filer

Microsoft 365 tillhandahåller molnlagring för enskilda personer, små organisationer och företag. Mer information om vad du vill lagra var finns [i Var du kan lagra dokument i Microsoft 365](https://support.office.com/article/c7c20284-bc94-47f4-9728-d28e9daf0790.aspx).
  
- **Du kan flytta hundratals filer** till [OneDrive](https://support.office.com/article/45114744-6D42-45CD-8975-F9617819BDEB.aspx) eller till en [SharePoint-gruppwebbplats](https://support.office.com/article/da549fb1-1fcb-4167-87d0-4693e93cb7a0.aspx#__toc384119242). Du kan ladda upp 100 filer åt gången. Undvik att ladda upp filer som är större än 2 GB, eftersom det är den största tillåtna filstorleken som standard.
  
- **Om du vill flytta flera tusen filer** till Microsoft 365-lagring läser du [SharePoint Online Limits](https://go.microsoft.com/fwlink/p/?LinkID=856113). Vi rekommenderar att du använder ett migreringsverktyg och överväger att anlita en [partner](https://go.microsoft.com/fwlink/?linkid=391089) som kan hjälpa dig med migreringen. Mer information om hur du migrerar ett stort antal filer finns i [Användarhandbok om SharePoint Online- och OneDrive-migrering](https://go.microsoft.com/fwlink/?LinkId=723574).
  
## <a name="plan-for-teams"></a>Planera för team

Du kan använda Microsoft Teams för att ringa samtal till andra personer i organisationen som finns med i din prenumeration. Om din organisation till exempel har 10 personer kan du ringa och snabbmeddelanden till varandra med Teams utan någon särskild konfiguration. Mer information finns i [Komma igång med Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-quick-start).

För större organisationer eller om du börjar från Skype för företag, lokala eller hybriddistributioner finns i [Så här distribuerar](https://docs.microsoft.com/MicrosoftTeams/how-to-roll-out-teams)du Microsoft Teams .
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>Planera för integrering med Active Directory eller annan programvara

- **Vill du integrera med din lokala Active Directory?** Du kan integrera din lokala Active Directory med Microsoft 365 med hjälp av Azure Active Directory Connect. Instruktioner finns i [Konfigurera katalogsynkronisering för Microsoft 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).
  
- **Vill du integrera Microsoft 365 med programvara från andra företag?** Om du behöver integrera Microsoft 365 med annan programvara i organisationen rekommenderar vi att du överväger att [anlita en partner](https://go.microsoft.com/fwlink/?linkid=391089) för att hjälpa dig med distributionen.
  
## <a name="do-you-want-someone-to-help-you-set-up-microsoft-365"></a>Vill du att någon ska hjälpa dig att konfigurera Microsoft 365?

- **Om du har färre än 50 anställda:**

  - **Be om hjälp så ringer vi dig**. När du har köpt Microsoft 365 kan du komma åt administrationscentret (du behöver inte köra installationen för att komma åt det). Längst ned i administrationscentret väljer du **Behöver du hjälp?** Beskriv problemet så ringer vi upp dig. 
  - **Ring [Microsoft 365 för företagssupport](../contact-support-for-business-products.md) med dina frågor**. Vi hjälper gärna till! 
  - **Du kan även anlita en [Microsoft-partner](https://go.microsoft.com/fwlink/?linkid=391089)**. Om du har ont om tid eller har avancerade krav (som att flytta tusentals filer till Microsoft 365-molnlagring eller integrera med annan programvara) kan en erfaren partner vara till stor hjälp. 

- **Om du har fler än 50 anställda** kan [FastTrack-introduktionscentret](https://go.microsoft.com/fwlink/?LinkId=517115) hjälpa dig med distributionen. 
