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
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a><span data-ttu-id="d4f34-103">Migrera företags-e-post och -kalender från Google Workspace</span><span class="sxs-lookup"><span data-stu-id="d4f34-103">Migrate business email and calendar from Google Workspace</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

<span data-ttu-id="d4f34-104">Du kan använda en migrering som administratör till Exchange Online från Google Workspace.</span><span class="sxs-lookup"><span data-stu-id="d4f34-104">You can use an admin-ran migration to Exchange Online from Google Workspace.</span></span> <span data-ttu-id="d4f34-105">Du kan migrera e-post antingen på en gång eller stegvis.</span><span class="sxs-lookup"><span data-stu-id="d4f34-105">You can migrate the mail either all at once, or in stages.</span></span> <span data-ttu-id="d4f34-106">I följande steg visas hur du migrerar e-postdata på en gång.</span><span class="sxs-lookup"><span data-stu-id="d4f34-106">The following steps show how to migrate the email data at once.</span></span> <span data-ttu-id="d4f34-107">Mer information finns i Utföra [en G Suite-migrering.](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration)</span><span class="sxs-lookup"><span data-stu-id="d4f34-107">For more information, see [Perform a G Suite migration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration).</span></span>

<span data-ttu-id="d4f34-108">Migreringsprocessen tar flera steg och kan ta från flera timmar till några dagar beroende på hur mycket data du migrerar.</span><span class="sxs-lookup"><span data-stu-id="d4f34-108">The migration process takes several steps and can take from several hours to a couple of days depending on the amount of data you are migrating.</span></span>

## <a name="try-it"></a><span data-ttu-id="d4f34-109">Prova!</span><span class="sxs-lookup"><span data-stu-id="d4f34-109">Try it!</span></span>

### <a name="create-a-google-service-account"></a><span data-ttu-id="d4f34-110">Skapa ett Google Service-konto</span><span class="sxs-lookup"><span data-stu-id="d4f34-110">Create a Google Service Account</span></span>

1. <span data-ttu-id="d4f34-111">Använd en Chrome-webbläsare och logga in på administratörskonsolen för Google Workspace [admin.google.com.](https://admin.google.com)</span><span class="sxs-lookup"><span data-stu-id="d4f34-111">Using a Chrome browser, sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span> 
1. <span data-ttu-id="d4f34-112">I en ny flik eller ett nytt fönster går du till [sidan Tjänstkonton.](https://console.developers.google.com/iam-admin/serviceaccounts)</span><span class="sxs-lookup"><span data-stu-id="d4f34-112">In a new tab or window, navigate to the [Service Accounts](https://console.developers.google.com/iam-admin/serviceaccounts) page.</span></span> 
1. <span data-ttu-id="d4f34-113">Välj **Skapa projekt,** namnge projektet och välj **Skapa.**</span><span class="sxs-lookup"><span data-stu-id="d4f34-113">Select **Create project**, name the project and choose **Create**.</span></span> 
1. <span data-ttu-id="d4f34-114">Välj **Skapa tjänstkonto,** ange ett namn, välj **Skapa** och sedan **Klar.**</span><span class="sxs-lookup"><span data-stu-id="d4f34-114">Select **Create service account**, enter a name, choose **Create** and then **Done**.</span></span> 
1. <span data-ttu-id="d4f34-115">Öppna menyn **Åtgärder,** välj **Redigera** och notera unikt ID.</span><span class="sxs-lookup"><span data-stu-id="d4f34-115">Open the **Actions** menu, select **Edit**, and take note of the Unique ID.</span></span> <span data-ttu-id="d4f34-116">Du behöver detta ID senare i processen.</span><span class="sxs-lookup"><span data-stu-id="d4f34-116">You’ll need this ID later in the process.</span></span> 
1. <span data-ttu-id="d4f34-117">Öppna avsnittet **Visa delegering för hela** domänen.</span><span class="sxs-lookup"><span data-stu-id="d4f34-117">Open the **Show domain-wide delegation** section.</span></span> 
1. <span data-ttu-id="d4f34-118">Välj **Aktivera delegering för hela domänen** för G Suite, ange ett produktnamn för medgivandeskärmen och välj **Spara.**</span><span class="sxs-lookup"><span data-stu-id="d4f34-118">Select **Enable G Suite Domain-wide Delegation**, enter a product name for the consent screen, and choose **Save**.</span></span> 

    > [!NOTE]
> <span data-ttu-id="d4f34-119">Produktnamnet används inte av migreringsprocessen, men måste sparas i dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="d4f34-119">The product name is not used by the migration process, but is needed to save in the dialog.</span></span>     

1. <span data-ttu-id="d4f34-120">Öppna menyn **Åtgärder** igen och välj **Skapa nyckel.**</span><span class="sxs-lookup"><span data-stu-id="d4f34-120">Open the **Actions** menu again and select **Create key**.</span></span> 
1. <span data-ttu-id="d4f34-121">Välj **JSON** och sedan **Skapa.**</span><span class="sxs-lookup"><span data-stu-id="d4f34-121">Choose **JSON**, then **Create**.</span></span> 

     <span data-ttu-id="d4f34-122">Den privata nyckeln sparas i nedladdningsmappen på din enhet.</span><span class="sxs-lookup"><span data-stu-id="d4f34-122">The private key is saved to the download folder on your device.</span></span>
 
1. <span data-ttu-id="d4f34-123">Välj **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="d4f34-123">Select **Close**.</span></span> 

### <a name="enable-api-usage-for-the-project"></a><span data-ttu-id="d4f34-124">Aktivera API-användning för projektet</span><span class="sxs-lookup"><span data-stu-id="d4f34-124">Enable API usage for the project</span></span>

1. <span data-ttu-id="d4f34-125">Gå till [sidan API:er.](https://console.developers.google.com/apis/library)</span><span class="sxs-lookup"><span data-stu-id="d4f34-125">Navigate to the [APIs page](https://console.developers.google.com/apis/library).</span></span> 
1. <span data-ttu-id="d4f34-126">Ange Gmail API i **sökfältet.**</span><span class="sxs-lookup"><span data-stu-id="d4f34-126">In the search bar, enter **Gmail API**.</span></span>
1. <span data-ttu-id="d4f34-127">Markera den och välj sedan **Aktivera.**</span><span class="sxs-lookup"><span data-stu-id="d4f34-127">Select it and then choose **Enable**.</span></span>
1. <span data-ttu-id="d4f34-128">Upprepa proceduren för GOOGLE Calendar API och API för Kontakter.</span><span class="sxs-lookup"><span data-stu-id="d4f34-128">Repeat this process for Google Calendar API and Contacts API.</span></span> 

### <a name="grant-access-to-the-service-account"></a><span data-ttu-id="d4f34-129">Bevilja åtkomst till tjänstkontot</span><span class="sxs-lookup"><span data-stu-id="d4f34-129">Grant access to the service account</span></span>

1. <span data-ttu-id="d4f34-130">Återgå till administratörskonsolen för Google Workspace.</span><span class="sxs-lookup"><span data-stu-id="d4f34-130">Return to the Google Workspace admin console.</span></span> 
1. <span data-ttu-id="d4f34-131">Välj **Säkerhet,** rulla nedåt och öppna **API-kontroller.**</span><span class="sxs-lookup"><span data-stu-id="d4f34-131">Select **Security**, scroll down and open **API controls**.</span></span> 
1. <span data-ttu-id="d4f34-132">Rulla nedåt och välj **Hantera delegering för hela domänen.**</span><span class="sxs-lookup"><span data-stu-id="d4f34-132">Scroll down and select **Manage Domain-wide Delegation**.</span></span>
1. <span data-ttu-id="d4f34-133">Välj **Lägg till ny** och ange det klient-ID du antecknade tidigare.</span><span class="sxs-lookup"><span data-stu-id="d4f34-133">Select **Add new** and enter the Client ID you made note of earlier.</span></span>
1. <span data-ttu-id="d4f34-134">Ange sedan OAuth-omfattningarna för Google-API:er.</span><span class="sxs-lookup"><span data-stu-id="d4f34-134">Then enter the OAuth scopes for Google APIs.</span></span> <span data-ttu-id="d4f34-135">De är tillgängliga [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) i steg 5 och är:</span><span class="sxs-lookup"><span data-stu-id="d4f34-135">These are available at [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) in step 5 and are:</span></span>

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. <span data-ttu-id="d4f34-136">Välj **Godkänn.**</span><span class="sxs-lookup"><span data-stu-id="d4f34-136">Choose **Authorize**.</span></span> 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a><span data-ttu-id="d4f34-137">Skapa en underdomän för e-post till Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d4f34-137">Create a sub-domain for mail going to Microsoft 365</span></span>

1. <span data-ttu-id="d4f34-138">Återgå till **administratörskonsolen för Google Workspace.**</span><span class="sxs-lookup"><span data-stu-id="d4f34-138">Return to the **Google Workspace admin** console.</span></span>
1. <span data-ttu-id="d4f34-139">Välj **Domäner,** **Hantera domäner** och lägg sedan till ett **domänalias.**</span><span class="sxs-lookup"><span data-stu-id="d4f34-139">Select **Domains**, **Manage domains**, then, **Add a domain alias**.</span></span> 
1. <span data-ttu-id="d4f34-140">Ange ett domänalias som `m365.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="d4f34-140">Enter a domain alias like `m365.contoso.com`.</span></span>
1. <span data-ttu-id="d4f34-141">Välj sedan **Fortsätt och verifiera domänägarskap.**</span><span class="sxs-lookup"><span data-stu-id="d4f34-141">Then select **Continue and verify domain ownership**.</span></span> 

    <span data-ttu-id="d4f34-142">Domänverifieringen tar vanligtvis bara några minuter, men det kan ta upp till 48 timmar.</span><span class="sxs-lookup"><span data-stu-id="d4f34-142">Domain verification usually takes just a few minutes, but it can take up to 48 hours.</span></span>

1. <span data-ttu-id="d4f34-143">Gå till [administrationscentret för Microsoft 365.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="d4f34-143">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="d4f34-144">I det vänstra navigeringsfältet i administrationscentret för **Microsoft 365** väljer du Visa **alla,** **Inställningar,** **Domäner** och sedan Lägg **till domän.**</span><span class="sxs-lookup"><span data-stu-id="d4f34-144">In the **Microsoft 365 admin center**, in the left nav, select **Show all**, **Settings**, **Domains**, and then **Add domain**.</span></span> 
1. <span data-ttu-id="d4f34-145">Ange den underdomän som du skapat tidigare och välj sedan **Använd den här domänen.**</span><span class="sxs-lookup"><span data-stu-id="d4f34-145">Enter the subdomain you previously created, then select **Use this domain**.</span></span> 
1. <span data-ttu-id="d4f34-146">Välj Fortsätt för att ansluta **domänen.**</span><span class="sxs-lookup"><span data-stu-id="d4f34-146">To connect the domain, select **Continue**.</span></span> 
1. <span data-ttu-id="d4f34-147">Bläddra nedåt och notera MX-poster, CNAME-poster och TXT-poster.</span><span class="sxs-lookup"><span data-stu-id="d4f34-147">Scroll down and take note of the MX records, CNAME records, and TXT records.</span></span> 
1. <span data-ttu-id="d4f34-148">Återgå till **Administratörskonsolen för Google.**</span><span class="sxs-lookup"><span data-stu-id="d4f34-148">Return to the **Google admin console**.</span></span>
1. <span data-ttu-id="d4f34-149">Välj **Domäner,** välj **Hantera domäner,** **Verifiera** information och sedan **Hantera domän.**</span><span class="sxs-lookup"><span data-stu-id="d4f34-149">Select **Domains**, select **Manage domains**, **Verify Details** and then, **Manage domain**.</span></span> 
1. <span data-ttu-id="d4f34-150">Välj DNS i det vänstra **navigeringsfältet** och bläddra ned till **Anpassade resursposter.**</span><span class="sxs-lookup"><span data-stu-id="d4f34-150">In the left nav, choose **DNS** and scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="d4f34-151">Öppna listrutan posttyp och välj **MX,** ange eller kopiera och klistra in den MX-postinformation du tidigare nämnt och välj sedan **Lägg till.**</span><span class="sxs-lookup"><span data-stu-id="d4f34-151">Open the record type dropdown and select **MX**, enter or copy and paste the MX record information you previously noted,then choose **Add**.</span></span> 
1. <span data-ttu-id="d4f34-152">Upprepa processen för CNAME-posten och TXT-posten.</span><span class="sxs-lookup"><span data-stu-id="d4f34-152">Repeat the process for the CNAME record and the TXT record.</span></span> 

    <span data-ttu-id="d4f34-153">Det kan ta lite tid innan ändringarna verkställs.</span><span class="sxs-lookup"><span data-stu-id="d4f34-153">It may take some time for these changes to take effect.</span></span>  

1. <span data-ttu-id="d4f34-154">Gå tillbaka till där du slutade i administrationscentret för **Microsoft 365** och välj **Fortsätt.**</span><span class="sxs-lookup"><span data-stu-id="d4f34-154">Return to where you left off in **Microsoft 365 admin center**, and select **Continue**.</span></span> 

<span data-ttu-id="d4f34-155">Domänen är nu konfigurerad.</span><span class="sxs-lookup"><span data-stu-id="d4f34-155">Your domain is now set up.</span></span>  

### <a name="create-email-aliases-in-microsoft-365"></a><span data-ttu-id="d4f34-156">Skapa e-postalias i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d4f34-156">Create email aliases in Microsoft 365</span></span>

<span data-ttu-id="d4f34-157">Innan migreringen kan påbörjas måste du skapa e-postalias för användarna med den nya underdomänen.</span><span class="sxs-lookup"><span data-stu-id="d4f34-157">Before migration can begin, you need to create email aliases for your users with the new subdomain.</span></span> 

1. <span data-ttu-id="d4f34-158">Starta nästa steg genom att gå till **guiden Lägg** till domäner i administrationscentret för Microsoft 365 och välja Gå till **Aktiva användare.**</span><span class="sxs-lookup"><span data-stu-id="d4f34-158">To start the next step, in the **Add Domains** wizard in the Microsoft 365 admin center, select **Go to Active users**.</span></span> 
1. <span data-ttu-id="d4f34-159">Välj en användare och hantera sedan användarnamn **och e-post.**</span><span class="sxs-lookup"><span data-stu-id="d4f34-159">Select a user, then, **Manage username and email**.</span></span> 
1. <span data-ttu-id="d4f34-160">Välj **underdomänen** du skapade tidigare i listrutan Domäner.</span><span class="sxs-lookup"><span data-stu-id="d4f34-160">From the **Domains** dropdown, select the subdomain you previously created.</span></span> 
1. <span data-ttu-id="d4f34-161">Ange ett användarnamn, **välj Lägg** **till,** Spara ändringar och stäng fönstret.</span><span class="sxs-lookup"><span data-stu-id="d4f34-161">Enter a username, select **Add**, **Save changes**, and close the window.</span></span> 

    <span data-ttu-id="d4f34-162">Upprepa proceduren för varje användare.</span><span class="sxs-lookup"><span data-stu-id="d4f34-162">Repeat this process for each user.</span></span> 

### <a name="start-the-migration-process"></a><span data-ttu-id="d4f34-163">Starta migreringsprocessen</span><span class="sxs-lookup"><span data-stu-id="d4f34-163">Start the migration process</span></span>

<span data-ttu-id="d4f34-164">När du är klar är du redo att migrera.</span><span class="sxs-lookup"><span data-stu-id="d4f34-164">Once you’ve finished, you’re ready to migrate.</span></span> 

1. <span data-ttu-id="d4f34-165">Rulla ned till Administrationscenter till vänster i administrationscentret för **Microsoft 365** och välj **Exchange.**</span><span class="sxs-lookup"><span data-stu-id="d4f34-165">In the left nav of the **Microsoft 365 admin center**, scroll down to **Admin centers**,and select **Exchange**.</span></span> 
1. <span data-ttu-id="d4f34-166">Välj **Migrering** under **Mottagare,** välj **Ny,** **Migrera till Exchange Online,** välj G **Suite-migrering** och sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="d4f34-166">Under **recipients**, choose **migration**, select **New**, **Migrate to Exchange Online**, choose **G Suite migration**, and then **Next**.</span></span> 
1. <span data-ttu-id="d4f34-167">Skapa en CSV-fil med en lista över postlådorna som du vill migrera.</span><span class="sxs-lookup"><span data-stu-id="d4f34-167">Create a CSV file with a list of the mailboxes you want to migrate.</span></span> <span data-ttu-id="d4f34-168">Se till att filen följer det här formatet:</span><span class="sxs-lookup"><span data-stu-id="d4f34-168">Make sure the file follows this format:</span></span> 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      <span data-ttu-id="d4f34-169">Mer information finns [i aka.ms/GoogleWorkspaceMigration.](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac)</span><span class="sxs-lookup"><span data-stu-id="d4f34-169">For details see [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac).</span></span> 

1. <span data-ttu-id="d4f34-170">Välj **Välj fil,** gå till CSV-filen, välj den, **välj Öppna** och sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="d4f34-170">Select **Choose File**, navigate to the CSV file, choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="d4f34-171">Kontrollera den administratörs-e-postadress som du vill använda för att testa.</span><span class="sxs-lookup"><span data-stu-id="d4f34-171">Verify the admin email address you want to use for testing.</span></span> 
1. <span data-ttu-id="d4f34-172">Välj **Välj fil,** gå till den JSON-fil du skapade tidigare (vanligtvis i mappen Nedladdningar på datorn), välj den, välj **Öppna** och sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="d4f34-172">Select **Choose File**, navigate to the JSON file you created earlier (usually in the Downloads folder on your computer), choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="d4f34-173">Ange ett namn i namnfältet **Ny migreringsbatch.**</span><span class="sxs-lookup"><span data-stu-id="d4f34-173">Enter a name in the **New migration batch name field**.</span></span>
1. <span data-ttu-id="d4f34-174">Ange den underdomän som du skapade i **fältet Målleveransdomän,** **välj** Nästa och sedan **Ny.**</span><span class="sxs-lookup"><span data-stu-id="d4f34-174">Enter the subdomain you created in the **Target delivery domain** field, select **Next**, and then **New**.</span></span> 
1. <span data-ttu-id="d4f34-175">När informationen har sparats väljer du **OK.**</span><span class="sxs-lookup"><span data-stu-id="d4f34-175">Once the information is saved, select **OK**.</span></span> 

    <span data-ttu-id="d4f34-176">Du kan nu visa status för migreringen.</span><span class="sxs-lookup"><span data-stu-id="d4f34-176">You can now view the status of your migration.</span></span> 

1. <span data-ttu-id="d4f34-177">När det har gått en tid väljer du Uppdatera, beroende på hur många användare du **migrerar.**</span><span class="sxs-lookup"><span data-stu-id="d4f34-177">After some time has passed, depending on how many users you are migrating, select **Refresh**.</span></span> 
1. <span data-ttu-id="d4f34-178">När statusen har ändrats till **Synkroniserad** väljer du **Slutför migreringsbatchen** och sedan **Ja.**</span><span class="sxs-lookup"><span data-stu-id="d4f34-178">Once the status has changed to **Synced**, select **Complete this migration batch**,then **Yes**.</span></span> 
1. <span data-ttu-id="d4f34-179">När processen är klar ändras din status till **Slutförd.**</span><span class="sxs-lookup"><span data-stu-id="d4f34-179">Once the process is complete, your status will change to **Completed**.</span></span> 
1. <span data-ttu-id="d4f34-180">Om du vill kan du välja **Visa information för** mer information om migreringen.</span><span class="sxs-lookup"><span data-stu-id="d4f34-180">If you want, you can select **View details** for more information about the migration.</span></span> 
1. <span data-ttu-id="d4f34-181">Välj **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="d4f34-181">Select **Close**.</span></span> 
1. <span data-ttu-id="d4f34-182">Öppna Outlook för att kontrollera att alla e-postmeddelanden från Google Workspace har migrerats.</span><span class="sxs-lookup"><span data-stu-id="d4f34-182">Open Outlook to verify that all the emails from Google Workspace were successfully migrated.</span></span>
<span data-ttu-id="d4f34-183">Du kan även upprepa detta för kalenderobjekt och kontakter.</span><span class="sxs-lookup"><span data-stu-id="d4f34-183">You can repeat this for calendar items and contacts as well.</span></span>