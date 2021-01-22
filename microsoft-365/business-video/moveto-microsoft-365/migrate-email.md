---
title: Migrera företags-e-post och -kalender från Google Workspace
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du migrerar e-post, kontakter och kalender från Google Workspace till Microsoft 365 för företag.
ms.openlocfilehash: cb751b1d2f18b226021bb6f218b62f3ae426f6a4
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928252"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a>Migrera företags-e-post och -kalender från Google Workspace

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

Du kan använda en migrering som administratör till Exchange Online från Google Workspace. Du kan migrera e-post antingen på en gång eller stegvis. I följande steg visas hur du migrerar e-postdata på en gång. Mer information finns i Utföra [en G Suite-migrering.](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration)

Migreringsprocessen tar flera steg och kan ta från flera timmar till några dagar beroende på hur mycket data du migrerar.

## <a name="try-it"></a>Prova!

### <a name="create-a-google-service-account"></a>Skapa ett Google Service-konto

1. Använd en Chrome-webbläsare och logga in på administratörskonsolen för Google Workspace [admin.google.com.](https://admin.google.com) 
1. I en ny flik eller ett nytt fönster går du till [sidan Tjänstkonton.](https://console.developers.google.com/iam-admin/serviceaccounts) 
1. Välj **Skapa projekt,** namnge projektet och välj **Skapa.** 
1. Välj **Skapa tjänstkonto,** ange ett namn, välj **Skapa** och sedan **Klar.** 
1. Öppna menyn **Åtgärder,** välj **Redigera** och notera unikt ID. Du behöver detta ID senare i processen. 
1. Öppna avsnittet **Visa delegering för hela** domänen. 
1. Välj **Aktivera delegering för hela domänen** för G Suite, ange ett produktnamn för medgivandeskärmen och välj **Spara.** 

    > [!NOTE]
> Produktnamnet används inte av migreringsprocessen, men måste sparas i dialogrutan.     

1. Öppna menyn **Åtgärder** igen och välj **Skapa nyckel.** 
1. Välj **JSON** och sedan **Skapa.** 

     Den privata nyckeln sparas i nedladdningsmappen på din enhet.
 
1. Välj **Stäng**. 

### <a name="enable-api-usage-for-the-project"></a>Aktivera API-användning för projektet

1. Gå till [sidan API:er.](https://console.developers.google.com/apis/library) 
1. Ange Gmail API i **sökfältet.**
1. Markera den och välj sedan **Aktivera.**
1. Upprepa proceduren för GOOGLE Calendar API och API för Kontakter. 

### <a name="grant-access-to-the-service-account"></a>Bevilja åtkomst till tjänstkontot

1. Återgå till administratörskonsolen för Google Workspace. 
1. Välj **Säkerhet,** rulla nedåt och öppna **API-kontroller.** 
1. Rulla nedåt och välj **Hantera delegering för hela domänen.**
1. Välj **Lägg till ny** och ange det klient-ID du antecknade tidigare.
1. Ange sedan OAuth-omfattningarna för Google-API:er. De är tillgängliga [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) i steg 5 och är:

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. Välj **Godkänn.** 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a>Skapa en underdomän för e-post till Microsoft 365

1. Återgå till **administratörskonsolen för Google Workspace.**
1. Välj **Domäner,** **Hantera domäner** och lägg sedan till ett **domänalias.** 
1. Ange ett domänalias som `m365.contoso.com` .
1. Välj sedan **Fortsätt och verifiera domänägarskap.** 

    Domänverifieringen tar vanligtvis bara några minuter, men det kan ta upp till 48 timmar.

1. Gå till [administrationscentret för Microsoft 365.](https://admin.microsoft.com)
1. I det vänstra navigeringsfältet i administrationscentret för **Microsoft 365** väljer du Visa **alla,** **Inställningar,** **Domäner** och sedan Lägg **till domän.** 
1. Ange den underdomän som du skapat tidigare och välj sedan **Använd den här domänen.** 
1. Välj Fortsätt för att ansluta **domänen.** 
1. Bläddra nedåt och notera MX-poster, CNAME-poster och TXT-poster. 
1. Återgå till **Administratörskonsolen för Google.**
1. Välj **Domäner,** välj **Hantera domäner,** **Verifiera** information och sedan **Hantera domän.** 
1. Välj DNS i det vänstra **navigeringsfältet** och bläddra ned till **Anpassade resursposter.** 
1. Öppna listrutan posttyp och välj **MX,** ange eller kopiera och klistra in den MX-postinformation du tidigare nämnt och välj sedan **Lägg till.** 
1. Upprepa processen för CNAME-posten och TXT-posten. 

    Det kan ta lite tid innan ändringarna verkställs.  

1. Gå tillbaka till där du slutade i administrationscentret för **Microsoft 365** och välj **Fortsätt.** 

Domänen är nu konfigurerad.  

### <a name="create-email-aliases-in-microsoft-365"></a>Skapa e-postalias i Microsoft 365

Innan migreringen kan påbörjas måste du skapa e-postalias för användarna med den nya underdomänen. 

1. Starta nästa steg genom att gå till **guiden Lägg** till domäner i administrationscentret för Microsoft 365 och välja Gå till **Aktiva användare.** 
1. Välj en användare och hantera sedan användarnamn **och e-post.** 
1. Välj **underdomänen** du skapade tidigare i listrutan Domäner. 
1. Ange ett användarnamn, **välj Lägg** **till,** Spara ändringar och stäng fönstret. 

    Upprepa proceduren för varje användare. 

### <a name="start-the-migration-process"></a>Starta migreringsprocessen

När du är klar är du redo att migrera. 

1. Rulla ned till Administrationscenter till vänster i administrationscentret för **Microsoft 365** och välj **Exchange.** 
1. Välj **Migrering** under **Mottagare,** välj **Ny,** **Migrera till Exchange Online,** välj G **Suite-migrering** och sedan **Nästa.** 
1. Skapa en CSV-fil med en lista över postlådorna som du vill migrera. Se till att filen följer det här formatet: 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      Mer information finns [i aka.ms/GoogleWorkspaceMigration.](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac) 

1. Välj **Välj fil,** gå till CSV-filen, välj den, **välj Öppna** och sedan **Nästa.** 
1. Kontrollera den administratörs-e-postadress som du vill använda för att testa. 
1. Välj **Välj fil,** gå till den JSON-fil du skapade tidigare (vanligtvis i mappen Nedladdningar på datorn), välj den, välj **Öppna** och sedan **Nästa.** 
1. Ange ett namn i namnfältet **Ny migreringsbatch.**
1. Ange den underdomän som du skapade i **fältet Målleveransdomän,** **välj** Nästa och sedan **Ny.** 
1. När informationen har sparats väljer du **OK.** 

    Du kan nu visa status för migreringen. 

1. När det har gått en tid väljer du Uppdatera, beroende på hur många användare du **migrerar.** 
1. När statusen har ändrats till **Synkroniserad** väljer du **Slutför migreringsbatchen** och sedan **Ja.** 
1. När processen är klar ändras din status till **Slutförd.** 
1. Om du vill kan du välja **Visa information för** mer information om migreringen. 
1. Välj **Stäng**. 
1. Öppna Outlook för att kontrollera att alla e-postmeddelanden från Google Workspace har migrerats.
Du kan även upprepa detta för kalenderobjekt och kontakter.