---
title: Pilot Microsoft 365 från min anpassade domän
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
ms.custom: ''
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du utvärderar e-post från min egen domän till en Microsoft 365-postlåda genom att bara använda två test konton.
ms.openlocfilehash: bfcb2bda4d560ab629ddebed88ac1d55e6224c05
ms.sourcegitcommit: 5f980a9eb5aca61cf3662ef0bc65dec215e21656
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/20/2020
ms.locfileid: "45186053"
---
# <a name="pilot-microsoft-365-from-my-custom-domain"></a><span data-ttu-id="0f8fe-103">Pilot Microsoft 365 från min anpassade domän</span><span class="sxs-lookup"><span data-stu-id="0f8fe-103">Pilot Microsoft 365 from my custom domain</span></span>

<span data-ttu-id="0f8fe-104">Du kan pilot Microsoft 365 med följande krav och begränsningar:</span><span class="sxs-lookup"><span data-stu-id="0f8fe-104">You can pilot Microsoft 365 with these requirements and limitations:</span></span>

- <span data-ttu-id="0f8fe-105">Din aktuella e-postleverantör måste tillhandahålla vidarebefordran av e-post.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-105">Your current email provider must provide email forwarding.</span></span>

- <span data-ttu-id="0f8fe-106">Du måste hantera dina Microsoft 365 DNS-poster hos din DNS-värd, i stället för att låta Microsoft 365 hantera posterna åt dig.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-106">You must manage your Microsoft 365 DNS records at your DNS hosting provider, rather than have Microsoft 365 manage these records for you.</span></span>

    <span data-ttu-id="0f8fe-107">Mer information finns i [Lägg till DNS-poster för att ansluta din domän](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span><span class="sxs-lookup"><span data-stu-id="0f8fe-107">To learn more, see [Add DNS records to connect your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>

- <span data-ttu-id="0f8fe-108">Ledig/upptagen-information för användare på den andra e-postservern är inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-108">Free/busy information for users on the other email server is not available.</span></span>

- <span data-ttu-id="0f8fe-109">Administratörer kan inte administrera alla användarkonton från en enda plats.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-109">Admins can't administer all user accounts from a single location.</span></span>

- <span data-ttu-id="0f8fe-110">Användare kanske inte kan använda Microsoft 365 spam enfilter.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-110">Users might not be able to use Microsoft 365 spam filtering.</span></span>

## <a name="set-up-a-microsoft-365-pilot"></a><span data-ttu-id="0f8fe-111">Konfigurera en Microsoft 365-pilot</span><span class="sxs-lookup"><span data-stu-id="0f8fe-111">Set up a Microsoft 365 pilot</span></span>

<span data-ttu-id="0f8fe-112">Följ dessa steg för att konfigurera en Microsoft 365-pilot:</span><span class="sxs-lookup"><span data-stu-id="0f8fe-112">Follow these steps to set up a Microsoft 365 pilot:</span></span>

### <a name="step-1-sign-in-to-the-microsoft-365-admin-center"></a><span data-ttu-id="0f8fe-113">Steg 1: Logga in på Administrationscenter för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0f8fe-113">Step 1: Sign in to the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="0f8fe-114">Logga in på [Administrationscenter för Microsoft 365](https://admin.microsoft.com) med ditt arbets-eller skol konto.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-114">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with your work or school account.</span></span>

2. <span data-ttu-id="0f8fe-115">Välj **inställningar** > **domäner** i det vänstra navigerings fönstret.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-115">Select **Settings** > **Domains** in the left navigation pane.</span></span>

### <a name="step-2-verify-that-you-own-the-domain-you-want-to-use"></a><span data-ttu-id="0f8fe-116">Steg 2: Kontrollera att du äger den domän som du vill använda</span><span class="sxs-lookup"><span data-stu-id="0f8fe-116">Step 2: Verify that you own the domain you want to use</span></span>

1. <span data-ttu-id="0f8fe-117">På sidan **Domains** väljer du **Lägg till domän**.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-117">On the **Domains** page, select **Add domain**.</span></span>

2. <span data-ttu-id="0f8fe-118">Skriv domän namnet i rutan. Välj **Använd den här domänen**och välj sedan **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-118">Type the domain name in the box, select **Use this domain**, and then select **Continue**.</span></span>

3. <span data-ttu-id="0f8fe-119">Välj de tjänster som du vill testa med din domän, t. ex. e-post och snabb meddelanden.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-119">Select the services you want to test with your domain, like email and instant messaging.</span></span>

5. <span data-ttu-id="0f8fe-120">På sidan **verifiera** domän följer du de stegvisa anvisningarna, AMD väljer **verifiera**.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-120">On the **Verify** domain page, follow the step-by-step instructions, amd then select **Verify**.</span></span>

    <span data-ttu-id="0f8fe-121">Det tar mellan några minuter och 72 timmar för DNS-ändringarna att börja gälla.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-121">It takes between a few minutes and 72 hours for DNS changes to take effect.</span></span>

    <span data-ttu-id="0f8fe-122">När verifieringen lyckas ombeds du ändra dina DNS-poster.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-122">When verification is successful, you are asked to modify your DNS records.</span></span>

### <a name="step-3-mark-the-domain-as-shared-in-exchange-online"></a><span data-ttu-id="0f8fe-123">Steg 3: Markera domänen som delad i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0f8fe-123">Step 3: Mark the domain as shared in Exchange Online</span></span>

1. <span data-ttu-id="0f8fe-124">I administrations centret för Exchange går du till avsnittet **e-postflöde**. Välj **godkända domäner**och välj sedan den domän som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-124">In the Exchange admin center, in the **Mail flow** section, select **Accepted domains**, and then select the domain you want to modify.</span></span>

2. <span data-ttu-id="0f8fe-125">Dubbelklicka på fönstret för att öppna det och välj **internt relä**.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-125">Double-click to open the window, and then select **Internal Relay**.</span></span> 

3. <span data-ttu-id="0f8fe-126">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-126">Select **Save**.</span></span>

    <span data-ttu-id="0f8fe-127">Den här inställningen kan kräva ett par minuter för att börja gälla.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-127">This setting might require a few minutes to take effect.</span></span>

### <a name="step-4-unblock-the-existing-email-server-optional"></a><span data-ttu-id="0f8fe-128">Steg 4: Häv blockering av den befintliga e-postservern (valfritt)</span><span class="sxs-lookup"><span data-stu-id="0f8fe-128">Step 4: Unblock the existing email server (optional)</span></span>

<span data-ttu-id="0f8fe-129">I Microsoft 365 används Exchange Online Protection (EOP) för skräp post skydd.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-129">Microsoft 365 uses Exchange Online Protection (EOP) for spam protection.</span></span> <span data-ttu-id="0f8fe-130">EOP kanske blockerar din befintliga e-postserver om en stor volym skräp post överförs av den aktuella e-postservern.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-130">EOP might block your existing mail server if it detects a high volume of spam being forwarded by your current mail server.</span></span> <span data-ttu-id="0f8fe-131">Om du litar på skräp post skyddet för den andra e-postleverantören kan du häva blockeringen av servern i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-131">If you trust the spam protection for your other email provider, you can unblock the server in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="0f8fe-132">Om du tar bort blockeringen av den befintliga e-postservern får all skräp post som kommer via din ursprungliga server till gång till Microsoft 365-post lådorna och du kan inte utvärdera hur bra Microsoft 365 hindrar skräp post.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-132">Unblocking your existing email server allows any spam that arrives through your original server to come to the Microsoft 365 mailboxes, and you can’t evaluate how well Microsoft 365 prevents spam.</span></span>

1. <span data-ttu-id="0f8fe-133">I navigerings fönstret i administrations centret för Exchange väljer du **skydd**och väljer sedan **anslutnings filter**.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-133">In the Exchange admin center navigation pane, select **Protection**, and then select **Connection filter**.</span></span>

2. <span data-ttu-id="0f8fe-134">Välj **+\*\*\*\*i listan med lista över tillåtna IP-** och e-postservern.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-134">In the **IP Allow list**, select **+**, and add the mail server IP address for your current email provider.</span></span> 

### <a name="step-5-create-user-accounts-and-set-the-primary-reply-to-address"></a><span data-ttu-id="0f8fe-135">Steg 5: skapa användarkonton och ange primär svars adress</span><span class="sxs-lookup"><span data-stu-id="0f8fe-135">Step 5: Create user accounts and set the primary reply-to address</span></span>

1. <span data-ttu-id="0f8fe-136">Välj **användare** > **aktiva användare**i det vänstra navigerings fältet i Administrationscenter för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-136">In the Microsoft 365 admin center left navigation, select **Users** > **Active Users**.</span></span>

2. <span data-ttu-id="0f8fe-137">Skapa två test konton genom att lägga till två befintliga användare.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-137">Create two test accounts by adding two existing users.</span></span>

    <span data-ttu-id="0f8fe-138">För varje konto väljer du **+ Lägg till en användare**och fyller i den information som krävs, inklusive den metod för lösen ord som du vill testa.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-138">For each account, select **+ Add a user**, and fill out the required information, including the password method you want to test.</span></span>

    <span data-ttu-id="0f8fe-139">Om du vill vara säker på att användarens e-postadress är densamma måste fältet **användarnamn** matcha användarens aktuella e-postadress.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-139">To ensure a user’s email stays the same, the **User name** field must match the user’s current email address.</span></span>

3. <span data-ttu-id="0f8fe-140">Välj en licens, klicka på **nästa**och klicka sedan **Slutför lägga till**.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-140">Choose the appropriate license, click **Next**, and then click **Finish adding**.</span></span> 

4. <span data-ttu-id="0f8fe-141">Bredvid **Användarnamn** väljer du det anpassade domännamnet i listrutan.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-141">Next to **User name**, select your custom domain name from the drop-down list.</span></span> 

5. <span data-ttu-id="0f8fe-142">Välj **skapa** > **stänga**.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-142">Select **Create** > **Close**.</span></span>

### <a name="step-6-update-dns-records-at-your-dns-hosting-provider"></a><span data-ttu-id="0f8fe-143">Steg 6: Uppdatera DNS-posterna hos DNS-värden</span><span class="sxs-lookup"><span data-stu-id="0f8fe-143">Step 6: Update DNS records at your DNS hosting provider</span></span>

<span data-ttu-id="0f8fe-144">Logga in på din DNS-värds webbplats och följ anvisningarna i [lägga till DNS-poster för att ansluta domänen](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span><span class="sxs-lookup"><span data-stu-id="0f8fe-144">Sign in to your DNS hosting provider's website, and follow the instructions at [Add DNS records to connect your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>

<span data-ttu-id="0f8fe-145">**Gör följande två undantag:**</span><span class="sxs-lookup"><span data-stu-id="0f8fe-145">**Make the following two exceptions:**</span></span>

- <span data-ttu-id="0f8fe-146">Skapa inte en ny MX-post samt ändra inte den befintliga MX-posten.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-146">Do not create a new MX record or change your existing MX record.</span></span>

- <span data-ttu-id="0f8fe-147">Om du redan har en SPF-post (Sender Policy Framework) för din tidigare e-postleverantör, ska du i stället för att skapa en ny SPF-post (TXT) för Exchange Online lägga till "include: SPF. Protection. Outlook. com" i den aktuella TXT-posten.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-147">If you already have a Sender Policy Framework (SPF) record for your previous email provider, instead of creating a new SPF (TXT) record for Exchange Online, add "include:spf.protection.outlook.com" to the current TXT record.</span></span>

    <span data-ttu-id="0f8fe-148">Exempel: "v = spf1 MX include: adatum. com inkluderar: SPF. Protection. Outlook. com ~ all".</span><span class="sxs-lookup"><span data-stu-id="0f8fe-148">For example, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span></span>

    <span data-ttu-id="0f8fe-149">Om du inte har en SPF-post ändrar du den som rekommenderas av Microsoft 365 för att inkludera domänen för din aktuella e-postleverantör och lägga till spf.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-149">If you don't have an SPF record, modify the one recommended by Microsoft 365 to include the domain for your current email provider, and add spf.protection.outlook.com.</span></span> <span data-ttu-id="0f8fe-150">Detta godkänner utgående meddelanden från båda e-postsystemen.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-150">This authorizes outgoing messages from both email systems.</span></span>

### <a name="step-7-set-up-email-forwarding-at-your-current-provider"></a><span data-ttu-id="0f8fe-151">Steg 7: Konfigurera vidarebefordran av e-post hos din nuvarande leverantör</span><span class="sxs-lookup"><span data-stu-id="0f8fe-151">Step 7: Set up email forwarding at your current provider</span></span>

<span data-ttu-id="0f8fe-152">På din aktuella e-postleverantör ställer du in vidarebefordring för dina användares e-postkonton i din onmicrosoft.com-domän:</span><span class="sxs-lookup"><span data-stu-id="0f8fe-152">At your current email provider, set up forwarding for your users email accounts to your onmicrosoft.com domain:</span></span>

- <span data-ttu-id="0f8fe-153">Vidarebefordra en användare en post låda till usera@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="0f8fe-153">Forward User A mailbox to usera@yourcompany.onmicrosoft.com</span></span>

- <span data-ttu-id="0f8fe-154">Vidarebefordra användarens e-postlåda till userb@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="0f8fe-154">Forward User B mailbox to userb@yourcompany.onmicrosoft.com</span></span>

<span data-ttu-id="0f8fe-155">När du slutför det här steget blir all e-post som skickas till usera@yourcompany.com och userb@yourcompany.com tillgänglig i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-155">When you complete this step, all email sent to usera@yourcompany.com and userb@yourcompany.com is available in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="0f8fe-156">Kontakta din aktuella e-postleverantör för att få de exakta stegen för att konfigurera vidarebefordran av e-post.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-156">Contact your current email provider for the exact steps to set up email forwarding.</span></span><br/>
> <span data-ttu-id="0f8fe-157">Du behöver inte spara en kopia av meddelanden hos den aktuella e-postleverantören.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-157">You don't need to keep a copy of messages at the current email provider.</span></span><br/>
> <span data-ttu-id="0f8fe-158">De flesta leverantörer vidarebefordrar e-post genom att lämna svar till avsändarens e-postadress intakt så att svar går till den ursprungliga avsändaren.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-158">Most providers forward email by leaving the Reply-to address of the sender intact so that replies go to the original sender.</span></span>

### <a name="step-8-test-mail-flow"></a><span data-ttu-id="0f8fe-159">Steg 8: Testa e-postflöde</span><span class="sxs-lookup"><span data-stu-id="0f8fe-159">Step 8: Test mail flow</span></span>

1. <span data-ttu-id="0f8fe-160">Logga in på Outlook Web App med inloggnings uppgifterna för användaren A.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-160">Sign in to Outlook Web App using the credentials for User A.</span></span>

2. <span data-ttu-id="0f8fe-161">Utför följande tester:</span><span class="sxs-lookup"><span data-stu-id="0f8fe-161">Perform these tests:</span></span>

    - <span data-ttu-id="0f8fe-162">Testa lokala Microsoft-e-postmeddelanden genom att till exempel skicka ett e-postmeddelande till användare B. E-postmeddelandet levereras omedelbart.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-162">Test local Microsoft email by sending an email, for example, to User B. The email is delivered immediately.</span></span> <span data-ttu-id="0f8fe-163">I det här scenariot dirigeras inte meddelandet till post lådan för användare B på din ursprungliga server eftersom Microsoft 365-post lådan är lokal.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-163">In this scenario, the message is not routed to the mailbox for User B on your original server because the Microsoft 365 mailbox is local.</span></span>

    - <span data-ttu-id="0f8fe-164">Testa e-post till en användare på det befintliga e-postsystemet genom att t. ex. Skicka ett e-postmeddelande till användare C. E-postmeddelandet skickas till användarens e-postserver på din ursprungliga e-postserver.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-164">Test email to a user on the existing email system by sending an email, for example, to User C. The email is delivered to the mailbox for User C on your original mail server.</span></span>

    - <span data-ttu-id="0f8fe-165">Kontrollera att vidarebefordran är rätt konfigurerat från ett externt konto eller från ett e-postkonto i det befintliga e-postsystemet.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-165">Verify that forwarding is set up properly from an outside account, or from an employee email account on the existing email system.</span></span> <span data-ttu-id="0f8fe-166">Skicka till exempel ett e-postmeddelande från det ursprungliga serverkontot för User C eller ett Hotmail-konto och verifiera att det anländer till Microsoft 365-postlådan för användare A.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-166">For example, from the original server account for User C or a Hotmail account, send User A an email and verify that it arrives in the Microsoft 365 mailbox for User A.</span></span>

### <a name="step-9-move-mailbox-contents"></a><span data-ttu-id="0f8fe-167">Steg 9: Flytta postlådeinnehåll</span><span class="sxs-lookup"><span data-stu-id="0f8fe-167">Step 9: Move mailbox contents</span></span>

<span data-ttu-id="0f8fe-168">Eftersom du bara flyttar två test användare, och användare A och användare B båda använder Outlook, kan du flytta e-postmeddelandet genom att öppna det gamla. PST-filen i den nya Outlook-profilen och kopiera meddelanden, Kalender objekt, kontakter och så vidare.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-168">Because you are moving only two test users, and User A and User B are both using Outlook, you can move the email by opening the old .PST file in the new Outlook profile and copying the messages, calendar items, contacts, and so on.</span></span> <span data-ttu-id="0f8fe-169">Mer information finns i [importera e-post, kontakter och kalender från en Outlook. PST-fil](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac).</span><span class="sxs-lookup"><span data-stu-id="0f8fe-169">For more information, see [Import email, contacts, and calendar from an Outlook .pst file](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac).</span></span>

<span data-ttu-id="0f8fe-170">När de har importer ATS till lämpliga platser i Microsoft 365-post lådan kan objekten vara tillgängliga från vilken enhet som helst, var som helst.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-170">After they’re imported to the appropriate locations in the Microsoft 365 mailbox, the items can be accessed from any device, anywhere.</span></span>

<span data-ttu-id="0f8fe-171">När flera post lådor är inblandade, eller om anställda inte använder Outlook, kan du använda de Migreringsverktyg som finns tillgängliga i administrations centret för Exchange.</span><span class="sxs-lookup"><span data-stu-id="0f8fe-171">When more mailboxes are involved, or if employees are not using Outlook, you can use the migration tools available in the Exchange admin center.</span></span> <span data-ttu-id="0f8fe-172">Kom igång genom att gå till administrations centret för Exchange och följa anvisningarna i [migrera e-post från en IMAP-server till Exchange Online-postlådor – vi behöver en ny artikel resurs].</span><span class="sxs-lookup"><span data-stu-id="0f8fe-172">To get started, go to Exchange admin center, and follow the directions in [Migrate Email from an IMAP Server to Exchange Online Mailboxes – we need a new article resource].</span></span>