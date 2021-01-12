---
title: Migrera företagets e-post och kalender från Google Workspace
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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du migrerar e-post, kontakter och kalender från Google Workspace till Microsoft 365 för företag.
ms.openlocfilehash: ab70a43fb7c26c23ebc9024b1cd2803c164a0aa4
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794709"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a>Migrera företagets e-post och kalender från Google Workspace

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

Du kan använda en administratör-har migrerat till Exchange Online från Google Workspace. Du kan migrera hela e-postmeddelandet på en gång eller i steg. Anvisningarna nedan visar hur du migrerar e-postdata samtidigt. Mer information finns i [genomföra en G Suite-migrering](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration).

Migreringen tar flera steg och kan ta från flera timmar till några dagar, beroende på hur mycket data du migrerar.

## <a name="try-it"></a>Prova!

### <a name="create-a-google-service-account"></a>Skapa ett Google-tjänstkonto

1. Använd webbläsare för att logga in på din Google Workspace-administratör på [admin.Google.com](https://admin.google.com). 
1. Gå till sidan [tjänst konton](https://console.developers.google.com/iam-admin/serviceaccounts) på en ny flik eller ett nytt fönster. 
1. Välj **skapa projekt**, namnge projektet och välj **skapa**. 
1. Välj **create service account**, ange ett namn, Välj **skapa** och sedan **klar**. 
1. Öppna menyn **åtgärder** , Välj **Redigera** och notera ett unikt ID. Du behöver detta ID senare i processen. 
1. Öppna avsnittet **Visa delegering av domän** . 
1. Välj **Aktivera G Suite Domain-wide delegering**, ange ett produkt namn för skärmen godkännande och välj **Spara**. 

    > [!NOTE]
> Produkt namnet används inte i migreringsprocessen, men behövs för att spara i dialog rutan.     

1. Öppna menyn **åtgärder** igen och välj **skapa en knapp**. 
1. Välj **JSON** och sedan **skapa**. 

     Den privata knappen sparas i mappen Ladda ned på enheten.
 
1. Välj **Stäng**. 

### <a name="enable-api-usage-for-the-project"></a>Aktivera API-användning för projektet

1. Gå till [API-sidan](https://console.developers.google.com/apis/library). 
1. I Sök fältet skriver du **Gmail API**.
1. Markera det och välj **Aktivera**.
1. Upprepa den här processen för Google Kalender API och kontakter API. 

### <a name="grant-access-to-the-service-account"></a>Bevilja åtkomst till tjänst kontot

1. Gå tillbaka till arbets ytans administratörs konsol. 
1. Välj **säkerhet**, Bläddra ned och öppna **API-kontroller**. 
1. Rulla nedåt och välj **Hantera domänomfattande delegering**.
1. Välj **Lägg till ny** och ange det klient-ID som du antecknade tidigare.
1. Ange OAuth-scope för Google API: er. Dessa är tillgängliga på [aka.MS/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) i steg 5 och är följande:

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. Välj **Godkänn**. 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a>Skapa en under domän för e-post som skickas till Microsoft 365

1. Gå tillbaka till arbets **ytans administratörs** konsol.
1. Välj **domäner**, **hantera domäner** och Lägg sedan **till ett domän Ali Aset**. 
1. Ange ett domän Ali Aset som `m365.contoso.com` .
1. Välj sedan **Fortsätt och bekräfta domänens ägarskap**. 

    Domän verifiering tar vanligt vis bara några minuter, men det kan ta upp till 48 timmar.

1. Gå till [administrations centret för Microsoft 365](https://admin.microsoft.com).
1. I **administrations centret för Microsoft 365** väljer du **Visa alla**, **Inställningar**, **domäner** och sedan **Lägg till domän** i det vänstra navigerings fältet. 
1. Ange den under domän som du har skapat tidigare och välj sedan **Använd den här domänen**. 
1. Om du vill ansluta domänen väljer du **Fortsätt**. 
1. Rulla nedåt och ta del av MX-posterna, CNAME-posterna och TXT-posterna. 
1. Återvänd till **Google Admin Console**.
1. Välj **domäner**, Välj **hantera domäner**, **Verifiera** och sedan **Hantera domän**. 
1. I det vänstra navigerings fältet väljer du **DNS** och bläddrar ned till **anpassade resurs poster**. 
1. Öppna List rutan Record Type och välj **MX**, ange eller kopiera och klistra in MX-postinformationen du tidigare noterade och välj sedan **Lägg till**. 
1. Upprepa processen för CNAME-posten och TXT-posten. 

    Det kan ta en stund innan ändringarna börjar gälla.  

1. Gå tillbaka till den plats där du slutade i **Microsoft 365 Admin Center** och välj **Fortsätt**. 

Din domän är nu konfigurerad.  

### <a name="create-email-aliases-in-microsoft-365"></a>Skapa e-postalias i Microsoft 365

Innan migreringen kan börja måste du skapa e-postalias för dina användare med den nya under domänen. 

1. Om du vill starta nästa steg väljer du **gå till aktiva användare** i guiden **Lägg till domäner** i administrations centret för Microsoft 365. 
1. Välj en användare, sedan **hantera användar namn och e-post**. 
1. Välj den under domän som du har skapat i list rutan **Domains** . 
1. Ange ett användar namn, Välj **Lägg till**, **Spara ändringar** och Stäng fönstret. 

    Upprepa proceduren för varje användare. 

### <a name="start-the-migration-process"></a>Starta migreringsprocessen

När du är klar kan du migrera. 

1. I det vänstra navigerings fältet i **Microsoft 365 Admin Center** bläddrar du ned till **administrations** Center och väljer **Exchange**. 
1. Välj **migrering** under **mottagare**, Välj **ny**, **migrera till Exchange Online**, Välj **G Suite-migrering** och sedan **Nästa**. 
1. Skapa en CSV-fil med en lista över de post lådor som du vill migrera. Kontrol lera att filen följer det här formatet: 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      Mer information finns i [aka.MS/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac). 

1. Välj **Välj fil**, gå till CSV-filen, Välj den, Välj **Öppna** och sedan **Nästa**. 
1. Verifiera administratörs-e-postadressen som du vill använda för testning. 
1. Välj **Välj fil**, gå till den JSON-fil som du skapade tidigare (vanligt vis i mappen Hämtade filer på datorn), Välj **Öppna** och sedan **Nästa**. 
1. Ange ett namn i **fältet ny migration**.
1. Ange den under domän du skapade i fältet **mål domän för leverans** , Välj **Nästa** och sedan **ny**. 
1. När informationen har sparats väljer du **OK**. 

    Nu kan du Visa status för migreringen. 

1. Beroende på hur många användare du migrerar efter tiden kan du välja **Uppdatera**. 
1. När statusen har ändrats till **synkronisering** väljer du **Slutför den här migreringstabellen** och sedan **Ja**. 
1. När processen är klar ändras din status till **slutförd**. 
1. Om du vill kan du välja **Visa information** om du vill ha mer information om migreringen. 
1. Välj **Stäng**. 
1. Öppna Outlook och kontrol lera att alla e-postmeddelanden från Google Workspace lyckades migreras.
Du kan upprepa detta för Kalender objekt och kontakter.