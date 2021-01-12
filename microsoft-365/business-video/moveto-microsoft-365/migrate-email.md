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
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a><span data-ttu-id="145d3-103">Migrera företagets e-post och kalender från Google Workspace</span><span class="sxs-lookup"><span data-stu-id="145d3-103">Migrate business email and calendar from Google Workspace</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

<span data-ttu-id="145d3-104">Du kan använda en administratör-har migrerat till Exchange Online från Google Workspace.</span><span class="sxs-lookup"><span data-stu-id="145d3-104">You can use an admin-ran migration to Exchange Online from Google Workspace.</span></span> <span data-ttu-id="145d3-105">Du kan migrera hela e-postmeddelandet på en gång eller i steg.</span><span class="sxs-lookup"><span data-stu-id="145d3-105">You can migrate the mail either all at once, or in stages.</span></span> <span data-ttu-id="145d3-106">Anvisningarna nedan visar hur du migrerar e-postdata samtidigt.</span><span class="sxs-lookup"><span data-stu-id="145d3-106">The following steps show how to migrate the email data at once.</span></span> <span data-ttu-id="145d3-107">Mer information finns i [genomföra en G Suite-migrering](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration).</span><span class="sxs-lookup"><span data-stu-id="145d3-107">For more information, see [Perform a G Suite migration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration).</span></span>

<span data-ttu-id="145d3-108">Migreringen tar flera steg och kan ta från flera timmar till några dagar, beroende på hur mycket data du migrerar.</span><span class="sxs-lookup"><span data-stu-id="145d3-108">The migration process takes several steps and can take from several hours to a couple of days depending on the amount of data you are migrating.</span></span>

## <a name="try-it"></a><span data-ttu-id="145d3-109">Prova!</span><span class="sxs-lookup"><span data-stu-id="145d3-109">Try it!</span></span>

### <a name="create-a-google-service-account"></a><span data-ttu-id="145d3-110">Skapa ett Google-tjänstkonto</span><span class="sxs-lookup"><span data-stu-id="145d3-110">Create a Google Service Account</span></span>

1. <span data-ttu-id="145d3-111">Använd webbläsare för att logga in på din Google Workspace-administratör på [admin.Google.com](https://admin.google.com).</span><span class="sxs-lookup"><span data-stu-id="145d3-111">Using a Chrome browser, sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span> 
1. <span data-ttu-id="145d3-112">Gå till sidan [tjänst konton](https://console.developers.google.com/iam-admin/serviceaccounts) på en ny flik eller ett nytt fönster.</span><span class="sxs-lookup"><span data-stu-id="145d3-112">In a new tab or window, navigate to the [Service Accounts](https://console.developers.google.com/iam-admin/serviceaccounts) page.</span></span> 
1. <span data-ttu-id="145d3-113">Välj **skapa projekt**, namnge projektet och välj **skapa**.</span><span class="sxs-lookup"><span data-stu-id="145d3-113">Select **Create project**, name the project and choose **Create**.</span></span> 
1. <span data-ttu-id="145d3-114">Välj **create service account**, ange ett namn, Välj **skapa** och sedan **klar**.</span><span class="sxs-lookup"><span data-stu-id="145d3-114">Select **Create service account**, enter a name, choose **Create** and then **Done**.</span></span> 
1. <span data-ttu-id="145d3-115">Öppna menyn **åtgärder** , Välj **Redigera** och notera ett unikt ID.</span><span class="sxs-lookup"><span data-stu-id="145d3-115">Open the **Actions** menu, select **Edit**, and take note of the Unique ID.</span></span> <span data-ttu-id="145d3-116">Du behöver detta ID senare i processen.</span><span class="sxs-lookup"><span data-stu-id="145d3-116">You’ll need this ID later in the process.</span></span> 
1. <span data-ttu-id="145d3-117">Öppna avsnittet **Visa delegering av domän** .</span><span class="sxs-lookup"><span data-stu-id="145d3-117">Open the **Show domain-wide delegation** section.</span></span> 
1. <span data-ttu-id="145d3-118">Välj **Aktivera G Suite Domain-wide delegering**, ange ett produkt namn för skärmen godkännande och välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="145d3-118">Select **Enable G Suite Domain-wide Delegation**, enter a product name for the consent screen, and choose **Save**.</span></span> 

    > [!NOTE]
> <span data-ttu-id="145d3-119">Produkt namnet används inte i migreringsprocessen, men behövs för att spara i dialog rutan.</span><span class="sxs-lookup"><span data-stu-id="145d3-119">The product name is not used by the migration process, but is needed to save in the dialog.</span></span>     

1. <span data-ttu-id="145d3-120">Öppna menyn **åtgärder** igen och välj **skapa en knapp**.</span><span class="sxs-lookup"><span data-stu-id="145d3-120">Open the **Actions** menu again and select **Create key**.</span></span> 
1. <span data-ttu-id="145d3-121">Välj **JSON** och sedan **skapa**.</span><span class="sxs-lookup"><span data-stu-id="145d3-121">Choose **JSON**, then **Create**.</span></span> 

     <span data-ttu-id="145d3-122">Den privata knappen sparas i mappen Ladda ned på enheten.</span><span class="sxs-lookup"><span data-stu-id="145d3-122">The private key is saved to the download folder on your device.</span></span>
 
1. <span data-ttu-id="145d3-123">Välj **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="145d3-123">Select **Close**.</span></span> 

### <a name="enable-api-usage-for-the-project"></a><span data-ttu-id="145d3-124">Aktivera API-användning för projektet</span><span class="sxs-lookup"><span data-stu-id="145d3-124">Enable API usage for the project</span></span>

1. <span data-ttu-id="145d3-125">Gå till [API-sidan](https://console.developers.google.com/apis/library).</span><span class="sxs-lookup"><span data-stu-id="145d3-125">Navigate to the [APIs page](https://console.developers.google.com/apis/library).</span></span> 
1. <span data-ttu-id="145d3-126">I Sök fältet skriver du **Gmail API**.</span><span class="sxs-lookup"><span data-stu-id="145d3-126">In the search bar, enter **Gmail API**.</span></span>
1. <span data-ttu-id="145d3-127">Markera det och välj **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="145d3-127">Select it and then choose **Enable**.</span></span>
1. <span data-ttu-id="145d3-128">Upprepa den här processen för Google Kalender API och kontakter API.</span><span class="sxs-lookup"><span data-stu-id="145d3-128">Repeat this process for Google Calendar API and Contacts API.</span></span> 

### <a name="grant-access-to-the-service-account"></a><span data-ttu-id="145d3-129">Bevilja åtkomst till tjänst kontot</span><span class="sxs-lookup"><span data-stu-id="145d3-129">Grant access to the service account</span></span>

1. <span data-ttu-id="145d3-130">Gå tillbaka till arbets ytans administratörs konsol.</span><span class="sxs-lookup"><span data-stu-id="145d3-130">Return to the Google Workspace admin console.</span></span> 
1. <span data-ttu-id="145d3-131">Välj **säkerhet**, Bläddra ned och öppna **API-kontroller**.</span><span class="sxs-lookup"><span data-stu-id="145d3-131">Select **Security**, scroll down and open **API controls**.</span></span> 
1. <span data-ttu-id="145d3-132">Rulla nedåt och välj **Hantera domänomfattande delegering**.</span><span class="sxs-lookup"><span data-stu-id="145d3-132">Scroll down and select **Manage Domain-wide Delegation**.</span></span>
1. <span data-ttu-id="145d3-133">Välj **Lägg till ny** och ange det klient-ID som du antecknade tidigare.</span><span class="sxs-lookup"><span data-stu-id="145d3-133">Select **Add new** and enter the Client ID you made note of earlier.</span></span>
1. <span data-ttu-id="145d3-134">Ange OAuth-scope för Google API: er.</span><span class="sxs-lookup"><span data-stu-id="145d3-134">Then enter the OAuth scopes for Google APIs.</span></span> <span data-ttu-id="145d3-135">Dessa är tillgängliga på [aka.MS/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) i steg 5 och är följande:</span><span class="sxs-lookup"><span data-stu-id="145d3-135">These are available at [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) in step 5 and are:</span></span>

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. <span data-ttu-id="145d3-136">Välj **Godkänn**.</span><span class="sxs-lookup"><span data-stu-id="145d3-136">Choose **Authorize**.</span></span> 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a><span data-ttu-id="145d3-137">Skapa en under domän för e-post som skickas till Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="145d3-137">Create a sub-domain for mail going to Microsoft 365</span></span>

1. <span data-ttu-id="145d3-138">Gå tillbaka till arbets **ytans administratörs** konsol.</span><span class="sxs-lookup"><span data-stu-id="145d3-138">Return to the **Google Workspace admin** console.</span></span>
1. <span data-ttu-id="145d3-139">Välj **domäner**, **hantera domäner** och Lägg sedan **till ett domän Ali Aset**.</span><span class="sxs-lookup"><span data-stu-id="145d3-139">Select **Domains**, **Manage domains**, then, **Add a domain alias**.</span></span> 
1. <span data-ttu-id="145d3-140">Ange ett domän Ali Aset som `m365.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="145d3-140">Enter a domain alias like `m365.contoso.com`.</span></span>
1. <span data-ttu-id="145d3-141">Välj sedan **Fortsätt och bekräfta domänens ägarskap**.</span><span class="sxs-lookup"><span data-stu-id="145d3-141">Then select **Continue and verify domain ownership**.</span></span> 

    <span data-ttu-id="145d3-142">Domän verifiering tar vanligt vis bara några minuter, men det kan ta upp till 48 timmar.</span><span class="sxs-lookup"><span data-stu-id="145d3-142">Domain verification usually takes just a few minutes, but it can take up to 48 hours.</span></span>

1. <span data-ttu-id="145d3-143">Gå till [administrations centret för Microsoft 365](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="145d3-143">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="145d3-144">I **administrations centret för Microsoft 365** väljer du **Visa alla**, **Inställningar**, **domäner** och sedan **Lägg till domän** i det vänstra navigerings fältet.</span><span class="sxs-lookup"><span data-stu-id="145d3-144">In the **Microsoft 365 admin center**, in the left nav, select **Show all**, **Settings**, **Domains**, and then **Add domain**.</span></span> 
1. <span data-ttu-id="145d3-145">Ange den under domän som du har skapat tidigare och välj sedan **Använd den här domänen**.</span><span class="sxs-lookup"><span data-stu-id="145d3-145">Enter the subdomain you previously created, then select **Use this domain**.</span></span> 
1. <span data-ttu-id="145d3-146">Om du vill ansluta domänen väljer du **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="145d3-146">To connect the domain, select **Continue**.</span></span> 
1. <span data-ttu-id="145d3-147">Rulla nedåt och ta del av MX-posterna, CNAME-posterna och TXT-posterna.</span><span class="sxs-lookup"><span data-stu-id="145d3-147">Scroll down and take note of the MX records, CNAME records, and TXT records.</span></span> 
1. <span data-ttu-id="145d3-148">Återvänd till **Google Admin Console**.</span><span class="sxs-lookup"><span data-stu-id="145d3-148">Return to the **Google admin console**.</span></span>
1. <span data-ttu-id="145d3-149">Välj **domäner**, Välj **hantera domäner**, **Verifiera** och sedan **Hantera domän**.</span><span class="sxs-lookup"><span data-stu-id="145d3-149">Select **Domains**, select **Manage domains**, **Verify Details** and then, **Manage domain**.</span></span> 
1. <span data-ttu-id="145d3-150">I det vänstra navigerings fältet väljer du **DNS** och bläddrar ned till **anpassade resurs poster**.</span><span class="sxs-lookup"><span data-stu-id="145d3-150">In the left nav, choose **DNS** and scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="145d3-151">Öppna List rutan Record Type och välj **MX**, ange eller kopiera och klistra in MX-postinformationen du tidigare noterade och välj sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="145d3-151">Open the record type dropdown and select **MX**, enter or copy and paste the MX record information you previously noted,then choose **Add**.</span></span> 
1. <span data-ttu-id="145d3-152">Upprepa processen för CNAME-posten och TXT-posten.</span><span class="sxs-lookup"><span data-stu-id="145d3-152">Repeat the process for the CNAME record and the TXT record.</span></span> 

    <span data-ttu-id="145d3-153">Det kan ta en stund innan ändringarna börjar gälla.</span><span class="sxs-lookup"><span data-stu-id="145d3-153">It may take some time for these changes to take effect.</span></span>  

1. <span data-ttu-id="145d3-154">Gå tillbaka till den plats där du slutade i **Microsoft 365 Admin Center** och välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="145d3-154">Return to where you left off in **Microsoft 365 admin center**, and select **Continue**.</span></span> 

<span data-ttu-id="145d3-155">Din domän är nu konfigurerad.</span><span class="sxs-lookup"><span data-stu-id="145d3-155">Your domain is now set up.</span></span>  

### <a name="create-email-aliases-in-microsoft-365"></a><span data-ttu-id="145d3-156">Skapa e-postalias i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="145d3-156">Create email aliases in Microsoft 365</span></span>

<span data-ttu-id="145d3-157">Innan migreringen kan börja måste du skapa e-postalias för dina användare med den nya under domänen.</span><span class="sxs-lookup"><span data-stu-id="145d3-157">Before migration can begin, you need to create email aliases for your users with the new subdomain.</span></span> 

1. <span data-ttu-id="145d3-158">Om du vill starta nästa steg väljer du **gå till aktiva användare** i guiden **Lägg till domäner** i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="145d3-158">To start the next step, in the **Add Domains** wizard in the Microsoft 365 admin center, select **Go to Active users**.</span></span> 
1. <span data-ttu-id="145d3-159">Välj en användare, sedan **hantera användar namn och e-post**.</span><span class="sxs-lookup"><span data-stu-id="145d3-159">Select a user, then, **Manage username and email**.</span></span> 
1. <span data-ttu-id="145d3-160">Välj den under domän som du har skapat i list rutan **Domains** .</span><span class="sxs-lookup"><span data-stu-id="145d3-160">From the **Domains** dropdown, select the subdomain you previously created.</span></span> 
1. <span data-ttu-id="145d3-161">Ange ett användar namn, Välj **Lägg till**, **Spara ändringar** och Stäng fönstret.</span><span class="sxs-lookup"><span data-stu-id="145d3-161">Enter a username, select **Add**, **Save changes**, and close the window.</span></span> 

    <span data-ttu-id="145d3-162">Upprepa proceduren för varje användare.</span><span class="sxs-lookup"><span data-stu-id="145d3-162">Repeat this process for each user.</span></span> 

### <a name="start-the-migration-process"></a><span data-ttu-id="145d3-163">Starta migreringsprocessen</span><span class="sxs-lookup"><span data-stu-id="145d3-163">Start the migration process</span></span>

<span data-ttu-id="145d3-164">När du är klar kan du migrera.</span><span class="sxs-lookup"><span data-stu-id="145d3-164">Once you’ve finished, you’re ready to migrate.</span></span> 

1. <span data-ttu-id="145d3-165">I det vänstra navigerings fältet i **Microsoft 365 Admin Center** bläddrar du ned till **administrations** Center och väljer **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="145d3-165">In the left nav of the **Microsoft 365 admin center**, scroll down to **Admin centers**,and select **Exchange**.</span></span> 
1. <span data-ttu-id="145d3-166">Välj **migrering** under **mottagare**, Välj **ny**, **migrera till Exchange Online**, Välj **G Suite-migrering** och sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="145d3-166">Under **recipients**, choose **migration**, select **New**, **Migrate to Exchange Online**, choose **G Suite migration**, and then **Next**.</span></span> 
1. <span data-ttu-id="145d3-167">Skapa en CSV-fil med en lista över de post lådor som du vill migrera.</span><span class="sxs-lookup"><span data-stu-id="145d3-167">Create a CSV file with a list of the mailboxes you want to migrate.</span></span> <span data-ttu-id="145d3-168">Kontrol lera att filen följer det här formatet:</span><span class="sxs-lookup"><span data-stu-id="145d3-168">Make sure the file follows this format:</span></span> 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      <span data-ttu-id="145d3-169">Mer information finns i [aka.MS/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac).</span><span class="sxs-lookup"><span data-stu-id="145d3-169">For details see [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac).</span></span> 

1. <span data-ttu-id="145d3-170">Välj **Välj fil**, gå till CSV-filen, Välj den, Välj **Öppna** och sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="145d3-170">Select **Choose File**, navigate to the CSV file, choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="145d3-171">Verifiera administratörs-e-postadressen som du vill använda för testning.</span><span class="sxs-lookup"><span data-stu-id="145d3-171">Verify the admin email address you want to use for testing.</span></span> 
1. <span data-ttu-id="145d3-172">Välj **Välj fil**, gå till den JSON-fil som du skapade tidigare (vanligt vis i mappen Hämtade filer på datorn), Välj **Öppna** och sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="145d3-172">Select **Choose File**, navigate to the JSON file you created earlier (usually in the Downloads folder on your computer), choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="145d3-173">Ange ett namn i **fältet ny migration**.</span><span class="sxs-lookup"><span data-stu-id="145d3-173">Enter a name in the **New migration batch name field**.</span></span>
1. <span data-ttu-id="145d3-174">Ange den under domän du skapade i fältet **mål domän för leverans** , Välj **Nästa** och sedan **ny**.</span><span class="sxs-lookup"><span data-stu-id="145d3-174">Enter the subdomain you created in the **Target delivery domain** field, select **Next**, and then **New**.</span></span> 
1. <span data-ttu-id="145d3-175">När informationen har sparats väljer du **OK**.</span><span class="sxs-lookup"><span data-stu-id="145d3-175">Once the information is saved, select **OK**.</span></span> 

    <span data-ttu-id="145d3-176">Nu kan du Visa status för migreringen.</span><span class="sxs-lookup"><span data-stu-id="145d3-176">You can now view the status of your migration.</span></span> 

1. <span data-ttu-id="145d3-177">Beroende på hur många användare du migrerar efter tiden kan du välja **Uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="145d3-177">After some time has passed, depending on how many users you are migrating, select **Refresh**.</span></span> 
1. <span data-ttu-id="145d3-178">När statusen har ändrats till **synkronisering** väljer du **Slutför den här migreringstabellen** och sedan **Ja**.</span><span class="sxs-lookup"><span data-stu-id="145d3-178">Once the status has changed to **Synced**, select **Complete this migration batch**,then **Yes**.</span></span> 
1. <span data-ttu-id="145d3-179">När processen är klar ändras din status till **slutförd**.</span><span class="sxs-lookup"><span data-stu-id="145d3-179">Once the process is complete, your status will change to **Completed**.</span></span> 
1. <span data-ttu-id="145d3-180">Om du vill kan du välja **Visa information** om du vill ha mer information om migreringen.</span><span class="sxs-lookup"><span data-stu-id="145d3-180">If you want, you can select **View details** for more information about the migration.</span></span> 
1. <span data-ttu-id="145d3-181">Välj **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="145d3-181">Select **Close**.</span></span> 
1. <span data-ttu-id="145d3-182">Öppna Outlook och kontrol lera att alla e-postmeddelanden från Google Workspace lyckades migreras.</span><span class="sxs-lookup"><span data-stu-id="145d3-182">Open Outlook to verify that all the emails from Google Workspace were successfully migrated.</span></span>
<span data-ttu-id="145d3-183">Du kan upprepa detta för Kalender objekt och kontakter.</span><span class="sxs-lookup"><span data-stu-id="145d3-183">You can repeat this for calendar items and contacts as well.</span></span>