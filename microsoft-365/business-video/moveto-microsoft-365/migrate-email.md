---
title: Migrera e-post och kalender från Google Workspace
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
ms.openlocfilehash: d6639032b379a2cd632b6ab6ee7e4082b1e7be0b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913628"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a><span data-ttu-id="042a7-103">Migrera e-post och kalender från Google Workspace</span><span class="sxs-lookup"><span data-stu-id="042a7-103">Migrate business email and calendar from Google Workspace</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

<span data-ttu-id="042a7-104">Du kan använda en migrering som kördes av administratören för Exchange Online från Google Workspace.</span><span class="sxs-lookup"><span data-stu-id="042a7-104">You can use an admin-ran migration to Exchange Online from Google Workspace.</span></span> <span data-ttu-id="042a7-105">Du kan migrera e-posten antingen samtidigt eller stegvis.</span><span class="sxs-lookup"><span data-stu-id="042a7-105">You can migrate the mail either all at once, or in stages.</span></span> <span data-ttu-id="042a7-106">Följande steg visar hur du migrerar e-postdata på en gång.</span><span class="sxs-lookup"><span data-stu-id="042a7-106">The following steps show how to migrate the email data at once.</span></span> <span data-ttu-id="042a7-107">Mer information finns i Utföra [en G Suite-migrering.](/exchange/mailbox-migration/perform-g-suite-migration)</span><span class="sxs-lookup"><span data-stu-id="042a7-107">For more information, see [Perform a G Suite migration](/exchange/mailbox-migration/perform-g-suite-migration).</span></span>

<span data-ttu-id="042a7-108">Migreringsprocessen tar flera steg och kan ta från flera timmar till ett par dagar beroende på mängden data du migrerar.</span><span class="sxs-lookup"><span data-stu-id="042a7-108">The migration process takes several steps and can take from several hours to a couple of days depending on the amount of data you are migrating.</span></span>

## <a name="try-it"></a><span data-ttu-id="042a7-109">Prova själv!</span><span class="sxs-lookup"><span data-stu-id="042a7-109">Try it!</span></span>

### <a name="create-a-google-service-account"></a><span data-ttu-id="042a7-110">Skapa ett Google Service-konto</span><span class="sxs-lookup"><span data-stu-id="042a7-110">Create a Google Service Account</span></span>

1. <span data-ttu-id="042a7-111">Logga in på administratörskonsolen för Google Workspace i webbläsaren Chrome [admin.google.com](https://admin.google.com).</span><span class="sxs-lookup"><span data-stu-id="042a7-111">Using a Chrome browser, sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span> 
1. <span data-ttu-id="042a7-112">Gå till sidan Tjänstkonton i en ny [flik eller ett nytt](https://console.developers.google.com/iam-admin/serviceaccounts) fönster.</span><span class="sxs-lookup"><span data-stu-id="042a7-112">In a new tab or window, navigate to the [Service Accounts](https://console.developers.google.com/iam-admin/serviceaccounts) page.</span></span> 
1. <span data-ttu-id="042a7-113">Välj **Skapa projekt**, namnge projektet och välj **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="042a7-113">Select **Create project**, name the project and choose **Create**.</span></span> 
1. <span data-ttu-id="042a7-114">Välj **Skapa tjänstkonto**, ange ett namn, välj **Skapa** och sedan **Klar**.</span><span class="sxs-lookup"><span data-stu-id="042a7-114">Select **Create service account**, enter a name, choose **Create** and then **Done**.</span></span> 
1. <span data-ttu-id="042a7-115">Öppna menyn **Åtgärder,** välj **Redigera** och notera unikt ID.</span><span class="sxs-lookup"><span data-stu-id="042a7-115">Open the **Actions** menu, select **Edit**, and take note of the Unique ID.</span></span> <span data-ttu-id="042a7-116">Du behöver detta ID senare i processen.</span><span class="sxs-lookup"><span data-stu-id="042a7-116">You’ll need this ID later in the process.</span></span> 
1. <span data-ttu-id="042a7-117">Öppna avsnittet **Visa delegering för hela** domänen.</span><span class="sxs-lookup"><span data-stu-id="042a7-117">Open the **Show domain-wide delegation** section.</span></span> 
1. <span data-ttu-id="042a7-118">Välj **Aktivera delegering för hela domänen för G Suite**, ange ett produktnamn för medgivandeskärmen och välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="042a7-118">Select **Enable G Suite Domain-wide Delegation**, enter a product name for the consent screen, and choose **Save**.</span></span> 

    > [!NOTE]
> <span data-ttu-id="042a7-119">Produktnamnet används inte i migreringsprocessen, men måste sparas i dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="042a7-119">The product name is not used by the migration process, but is needed to save in the dialog.</span></span>     

1. <span data-ttu-id="042a7-120">Öppna menyn **Åtgärder** igen och välj **Skapa nyckel**.</span><span class="sxs-lookup"><span data-stu-id="042a7-120">Open the **Actions** menu again and select **Create key**.</span></span> 
1. <span data-ttu-id="042a7-121">Välj **JSON** och sedan **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="042a7-121">Choose **JSON**, then **Create**.</span></span> 

     <span data-ttu-id="042a7-122">Den privata nyckeln sparas i nedladdningsmappen på din enhet.</span><span class="sxs-lookup"><span data-stu-id="042a7-122">The private key is saved to the download folder on your device.</span></span>
 
1. <span data-ttu-id="042a7-123">Välj **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="042a7-123">Select **Close**.</span></span> 

### <a name="enable-api-usage-for-the-project"></a><span data-ttu-id="042a7-124">Aktivera API-användning för projektet</span><span class="sxs-lookup"><span data-stu-id="042a7-124">Enable API usage for the project</span></span>

1. <span data-ttu-id="042a7-125">Gå till [SIDAN API:er.](https://console.developers.google.com/apis/library)</span><span class="sxs-lookup"><span data-stu-id="042a7-125">Navigate to the [APIs page](https://console.developers.google.com/apis/library).</span></span> 
1. <span data-ttu-id="042a7-126">Ange Gmail API i **sökfältet.**</span><span class="sxs-lookup"><span data-stu-id="042a7-126">In the search bar, enter **Gmail API**.</span></span>
1. <span data-ttu-id="042a7-127">Markera den och välj sedan **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="042a7-127">Select it and then choose **Enable**.</span></span>
1. <span data-ttu-id="042a7-128">Upprepa proceduren för Google Kalender-API och API för kontakter.</span><span class="sxs-lookup"><span data-stu-id="042a7-128">Repeat this process for Google Calendar API and Contacts API.</span></span> 

### <a name="grant-access-to-the-service-account"></a><span data-ttu-id="042a7-129">Bevilja åtkomst till tjänstkontot</span><span class="sxs-lookup"><span data-stu-id="042a7-129">Grant access to the service account</span></span>

1. <span data-ttu-id="042a7-130">Gå tillbaka till administratörskonsolen för Google Workspace.</span><span class="sxs-lookup"><span data-stu-id="042a7-130">Return to the Google Workspace admin console.</span></span> 
1. <span data-ttu-id="042a7-131">Välj **Säkerhet**, rulla nedåt och öppna **API-kontroller.**</span><span class="sxs-lookup"><span data-stu-id="042a7-131">Select **Security**, scroll down and open **API controls**.</span></span> 
1. <span data-ttu-id="042a7-132">Rulla nedåt och välj **Hantera domänomfattande delegering**.</span><span class="sxs-lookup"><span data-stu-id="042a7-132">Scroll down and select **Manage Domain-wide Delegation**.</span></span>
1. <span data-ttu-id="042a7-133">Välj **Lägg till ny** och ange det klient-ID du antecknade tidigare.</span><span class="sxs-lookup"><span data-stu-id="042a7-133">Select **Add new** and enter the Client ID you made note of earlier.</span></span>
1. <span data-ttu-id="042a7-134">Ange sedan OAuth-omfattningar för Google-API:er.</span><span class="sxs-lookup"><span data-stu-id="042a7-134">Then enter the OAuth scopes for Google APIs.</span></span> <span data-ttu-id="042a7-135">De finns tillgängliga [aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) i steg 5 och är:</span><span class="sxs-lookup"><span data-stu-id="042a7-135">These are available at [aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) in step 5 and are:</span></span>

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. <span data-ttu-id="042a7-136">Välj **Godkänn.**</span><span class="sxs-lookup"><span data-stu-id="042a7-136">Choose **Authorize**.</span></span> 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a><span data-ttu-id="042a7-137">Skapa en underdomän för e-post som ska Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="042a7-137">Create a sub-domain for mail going to Microsoft 365</span></span>

1. <span data-ttu-id="042a7-138">Gå tillbaka till **administratörskonsolen för Google Workspace.**</span><span class="sxs-lookup"><span data-stu-id="042a7-138">Return to the **Google Workspace admin** console.</span></span>
1. <span data-ttu-id="042a7-139">Välj **Domäner**, **Hantera domäner** och sedan Lägg till ett **domänalias**.</span><span class="sxs-lookup"><span data-stu-id="042a7-139">Select **Domains**, **Manage domains**, then, **Add a domain alias**.</span></span> 
1. <span data-ttu-id="042a7-140">Ange ett domänalias, till exempel `m365.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="042a7-140">Enter a domain alias like `m365.contoso.com`.</span></span>
1. <span data-ttu-id="042a7-141">Välj sedan **Fortsätt och verifiera domänägarskap.**</span><span class="sxs-lookup"><span data-stu-id="042a7-141">Then select **Continue and verify domain ownership**.</span></span> 

    <span data-ttu-id="042a7-142">Domänverifieringen tar vanligtvis bara några minuter, men det kan ta upp till 48 timmar.</span><span class="sxs-lookup"><span data-stu-id="042a7-142">Domain verification usually takes just a few minutes, but it can take up to 48 hours.</span></span>

1. <span data-ttu-id="042a7-143">Gå till [Microsoft 365 administrationscentret.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="042a7-143">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="042a7-144">I **det Microsoft 365 vänstra** navigeringsfältet i administrationscentret väljer du Visa **alla**, **Inställningar**, **Domäner** och sedan Lägg **till domän.**</span><span class="sxs-lookup"><span data-stu-id="042a7-144">In the **Microsoft 365 admin center**, in the left nav, select **Show all**, **Settings**, **Domains**, and then **Add domain**.</span></span> 
1. <span data-ttu-id="042a7-145">Ange den underdomän som du skapade tidigare och välj sedan **Använd den här domänen.**</span><span class="sxs-lookup"><span data-stu-id="042a7-145">Enter the subdomain you previously created, then select **Use this domain**.</span></span> 
1. <span data-ttu-id="042a7-146">Om du vill ansluta domänen väljer du **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="042a7-146">To connect the domain, select **Continue**.</span></span> 
1. <span data-ttu-id="042a7-147">Bläddra nedåt och notera MX-poster, CNAME-poster och TXT-poster.</span><span class="sxs-lookup"><span data-stu-id="042a7-147">Scroll down and take note of the MX records, CNAME records, and TXT records.</span></span> 
1. <span data-ttu-id="042a7-148">Gå tillbaka till **administratörskonsolen för Google.**</span><span class="sxs-lookup"><span data-stu-id="042a7-148">Return to the **Google admin console**.</span></span>
1. <span data-ttu-id="042a7-149">Välj **Domäner**, välj **Hantera domäner**, Verifiera **information** och sedan Hantera **domän**.</span><span class="sxs-lookup"><span data-stu-id="042a7-149">Select **Domains**, select **Manage domains**, **Verify Details** and then, **Manage domain**.</span></span> 
1. <span data-ttu-id="042a7-150">I det vänstra navigeringsfältet väljer **du DNS** och rullar ned till **Anpassade resursposter.**</span><span class="sxs-lookup"><span data-stu-id="042a7-150">In the left nav, choose **DNS** and scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="042a7-151">Öppna listrutan posttyp och välj **MX**, ange eller kopiera och klistra in den MX-postinformation du tidigare nämnt och välj sedan **Add**.</span><span class="sxs-lookup"><span data-stu-id="042a7-151">Open the record type dropdown and select **MX**, enter or copy and paste the MX record information you previously noted,then choose **Add**.</span></span> 
1. <span data-ttu-id="042a7-152">Upprepa processen för CNAME-posten och TXT-posten.</span><span class="sxs-lookup"><span data-stu-id="042a7-152">Repeat the process for the CNAME record and the TXT record.</span></span> 

    <span data-ttu-id="042a7-153">Det kan ta lite tid innan ändringarna verkställs.</span><span class="sxs-lookup"><span data-stu-id="042a7-153">It may take some time for these changes to take effect.</span></span>  

1. <span data-ttu-id="042a7-154">Återgå till där du slutade i **Microsoft 365 och** välj **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="042a7-154">Return to where you left off in **Microsoft 365 admin center**, and select **Continue**.</span></span> 

<span data-ttu-id="042a7-155">Domänen är nu konfigurerad.</span><span class="sxs-lookup"><span data-stu-id="042a7-155">Your domain is now set up.</span></span>  

### <a name="create-email-aliases-in-microsoft-365"></a><span data-ttu-id="042a7-156">Skapa e-postalias i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="042a7-156">Create email aliases in Microsoft 365</span></span>

<span data-ttu-id="042a7-157">Innan migreringen kan påbörjas måste du skapa e-postalias för användarna med den nya underdomänen.</span><span class="sxs-lookup"><span data-stu-id="042a7-157">Before migration can begin, you need to create email aliases for your users with the new subdomain.</span></span> 

1. <span data-ttu-id="042a7-158">Om du vill börja med nästa steg går **du till** guiden Lägg till domäner Microsoft 365 administrationscentret och väljer Gå till **Aktiva användare.**</span><span class="sxs-lookup"><span data-stu-id="042a7-158">To start the next step, in the **Add Domains** wizard in the Microsoft 365 admin center, select **Go to Active users**.</span></span> 
1. <span data-ttu-id="042a7-159">Välj en användare och sedan Hantera **användarnamn och e-post.**</span><span class="sxs-lookup"><span data-stu-id="042a7-159">Select a user, then, **Manage username and email**.</span></span> 
1. <span data-ttu-id="042a7-160">Välj **underdomänen** du skapade tidigare i listrutan Domains.</span><span class="sxs-lookup"><span data-stu-id="042a7-160">From the **Domains** dropdown, select the subdomain you previously created.</span></span> 
1. <span data-ttu-id="042a7-161">Ange ett användarnamn, **välj Lägg** till **,** Spara ändringar och stäng fönstret.</span><span class="sxs-lookup"><span data-stu-id="042a7-161">Enter a username, select **Add**, **Save changes**, and close the window.</span></span> 

    <span data-ttu-id="042a7-162">Upprepa proceduren för varje användare.</span><span class="sxs-lookup"><span data-stu-id="042a7-162">Repeat this process for each user.</span></span> 

### <a name="start-the-migration-process"></a><span data-ttu-id="042a7-163">Starta migreringsprocessen</span><span class="sxs-lookup"><span data-stu-id="042a7-163">Start the migration process</span></span>

<span data-ttu-id="042a7-164">När du är klar är du redo att migrera.</span><span class="sxs-lookup"><span data-stu-id="042a7-164">Once you’ve finished, you’re ready to migrate.</span></span> 

1. <span data-ttu-id="042a7-165">I det vänstra navigeringsfältet **i Microsoft 365 administrationscenter** bläddrar du ned till **Administrationscenter** och väljer **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="042a7-165">In the left nav of the **Microsoft 365 admin center**, scroll down to **Admin centers**,and select **Exchange**.</span></span> 
1. <span data-ttu-id="042a7-166">Välj **Migrering** under Mottagare **,** välj **Ny**, Migrera **till Exchange Online**, välj G **Suite-migrering** och sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="042a7-166">Under **recipients**, choose **migration**, select **New**, **Migrate to Exchange Online**, choose **G Suite migration**, and then **Next**.</span></span> 
1. <span data-ttu-id="042a7-167">Skapa en CSV-fil med en lista över postlådorna som du vill migrera.</span><span class="sxs-lookup"><span data-stu-id="042a7-167">Create a CSV file with a list of the mailboxes you want to migrate.</span></span> <span data-ttu-id="042a7-168">Se till att filen följer det här formatet:</span><span class="sxs-lookup"><span data-stu-id="042a7-168">Make sure the file follows this format:</span></span> 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      <span data-ttu-id="042a7-169">Mer information finns [i aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac).</span><span class="sxs-lookup"><span data-stu-id="042a7-169">For details see [aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac).</span></span> 

1. <span data-ttu-id="042a7-170">Välj **Välj fil**, gå till CSV-filen, välj den, välj **Öppna** och sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="042a7-170">Select **Choose File**, navigate to the CSV file, choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="042a7-171">Kontrollera den administratörs-e-postadress som du vill använda för att testa.</span><span class="sxs-lookup"><span data-stu-id="042a7-171">Verify the admin email address you want to use for testing.</span></span> 
1. <span data-ttu-id="042a7-172">Välj **Välj fil**, gå till den JSON-fil du skapade tidigare (vanligtvis i mappen Hämtade filer på datorn), välj den, välj **Öppna** och sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="042a7-172">Select **Choose File**, navigate to the JSON file you created earlier (usually in the Downloads folder on your computer), choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="042a7-173">Ange ett namn i namnfältet **Ny migreringsbatch.**</span><span class="sxs-lookup"><span data-stu-id="042a7-173">Enter a name in the **New migration batch name field**.</span></span>
1. <span data-ttu-id="042a7-174">Ange den underdomän som du skapade i **fältet Målleveransdomän,** välj **Nästa** och sedan **Ny.**</span><span class="sxs-lookup"><span data-stu-id="042a7-174">Enter the subdomain you created in the **Target delivery domain** field, select **Next**, and then **New**.</span></span> 
1. <span data-ttu-id="042a7-175">När informationen har sparats väljer du **OK.**</span><span class="sxs-lookup"><span data-stu-id="042a7-175">Once the information is saved, select **OK**.</span></span> 

    <span data-ttu-id="042a7-176">Du kan nu visa status för migreringen.</span><span class="sxs-lookup"><span data-stu-id="042a7-176">You can now view the status of your migration.</span></span> 

1. <span data-ttu-id="042a7-177">När det har gått en tid, beroende på hur många användare du migrerar, väljer du **Uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="042a7-177">After some time has passed, depending on how many users you are migrating, select **Refresh**.</span></span> 
1. <span data-ttu-id="042a7-178">När statusen har ändrats till **Synkroniserad väljer** du **Slutför migreringsbatchen** och sedan **Ja.**</span><span class="sxs-lookup"><span data-stu-id="042a7-178">Once the status has changed to **Synced**, select **Complete this migration batch**,then **Yes**.</span></span> 
1. <span data-ttu-id="042a7-179">När processen är klar ändras din status till **Slutförd**.</span><span class="sxs-lookup"><span data-stu-id="042a7-179">Once the process is complete, your status will change to **Completed**.</span></span> 
1. <span data-ttu-id="042a7-180">Om du vill kan du välja **Visa information för** mer information om migreringen.</span><span class="sxs-lookup"><span data-stu-id="042a7-180">If you want, you can select **View details** for more information about the migration.</span></span> 
1. <span data-ttu-id="042a7-181">Välj **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="042a7-181">Select **Close**.</span></span> 
1. <span data-ttu-id="042a7-182">Öppna Outlook för att kontrollera att alla e-postmeddelanden från Google Workspace har migrerats.</span><span class="sxs-lookup"><span data-stu-id="042a7-182">Open Outlook to verify that all the emails from Google Workspace were successfully migrated.</span></span>
<span data-ttu-id="042a7-183">Du kan även upprepa detta för kalenderobjekt och kontakter.</span><span class="sxs-lookup"><span data-stu-id="042a7-183">You can repeat this for calendar items and contacts as well.</span></span>