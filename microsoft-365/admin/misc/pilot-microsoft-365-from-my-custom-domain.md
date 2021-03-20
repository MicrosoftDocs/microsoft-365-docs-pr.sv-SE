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
ms.openlocfilehash: 019f1786756a036132f95fd5e8ef8a1d42cd515b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914720"
---
# <a name="pilot-microsoft-365-from-my-custom-domain"></a><span data-ttu-id="bb85f-103">Pilot Microsoft 365 från min anpassade domän</span><span class="sxs-lookup"><span data-stu-id="bb85f-103">Pilot Microsoft 365 from my custom domain</span></span>

<span data-ttu-id="bb85f-104">Du kan pilot Microsoft 365 med följande krav och begränsningar:</span><span class="sxs-lookup"><span data-stu-id="bb85f-104">You can pilot Microsoft 365 with these requirements and limitations:</span></span>

- <span data-ttu-id="bb85f-105">Din aktuella e-postleverantör måste tillhandahålla vidarebefordran av e-post.</span><span class="sxs-lookup"><span data-stu-id="bb85f-105">Your current email provider must provide email forwarding.</span></span>

- <span data-ttu-id="bb85f-106">Du måste hantera dina Microsoft 365 DNS-poster hos din DNS-värd, i stället för att låta Microsoft 365 hantera posterna åt dig.</span><span class="sxs-lookup"><span data-stu-id="bb85f-106">You must manage your Microsoft 365 DNS records at your DNS hosting provider, rather than have Microsoft 365 manage these records for you.</span></span>

    <span data-ttu-id="bb85f-107">Mer information finns i [Lägg till DNS-poster för att ansluta din domän](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="bb85f-107">To learn more, see [Add DNS records to connect your domain](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

- <span data-ttu-id="bb85f-108">Ledig/upptagen-information för användare på den andra e-postservern är inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="bb85f-108">Free/busy information for users on the other email server is not available.</span></span>

- <span data-ttu-id="bb85f-109">Administratörer kan inte administrera alla användarkonton från en enda plats.</span><span class="sxs-lookup"><span data-stu-id="bb85f-109">Admins can't administer all user accounts from a single location.</span></span>

- <span data-ttu-id="bb85f-110">Användare kanske inte kan använda Microsoft 365 spam enfilter.</span><span class="sxs-lookup"><span data-stu-id="bb85f-110">Users might not be able to use Microsoft 365 spam filtering.</span></span>

- <span data-ttu-id="bb85f-111">Detta rekommenderas för ett mycket litet antal användare och gäller endast användningen av e-post för en pilot.</span><span class="sxs-lookup"><span data-stu-id="bb85f-111">This is recommended for a very small number of users and only applies to the use of email for a pilot.</span></span>

## <a name="set-up-a-microsoft-365-pilot"></a><span data-ttu-id="bb85f-112">Konfigurera en Microsoft 365-pilot</span><span class="sxs-lookup"><span data-stu-id="bb85f-112">Set up a Microsoft 365 pilot</span></span>

<span data-ttu-id="bb85f-113">Följ dessa steg för att konfigurera en Microsoft 365-pilot:</span><span class="sxs-lookup"><span data-stu-id="bb85f-113">Follow these steps to set up a Microsoft 365 pilot:</span></span>

### <a name="step-1-sign-in-to-the-microsoft-365-admin-center"></a><span data-ttu-id="bb85f-114">Steg 1: Logga in på Administrationscenter för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bb85f-114">Step 1: Sign in to the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="bb85f-115">Logga in på [Administrationscenter för Microsoft 365](https://admin.microsoft.com) med ditt arbets-eller skol konto.</span><span class="sxs-lookup"><span data-stu-id="bb85f-115">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with your work or school account.</span></span>

2. <span data-ttu-id="bb85f-116">Välj **inställningar** > **domäner** i det vänstra navigerings fönstret.</span><span class="sxs-lookup"><span data-stu-id="bb85f-116">Select **Settings** > **Domains** in the left navigation pane.</span></span>

### <a name="step-2-verify-that-you-own-the-domain-you-want-to-use"></a><span data-ttu-id="bb85f-117">Steg 2: Kontrollera att du äger den domän som du vill använda</span><span class="sxs-lookup"><span data-stu-id="bb85f-117">Step 2: Verify that you own the domain you want to use</span></span>

1. <span data-ttu-id="bb85f-118">På sidan **Domains** väljer du **Lägg till domän**.</span><span class="sxs-lookup"><span data-stu-id="bb85f-118">On the **Domains** page, select **Add domain**.</span></span>

2. <span data-ttu-id="bb85f-119">Skriv domän namnet i rutan. Välj **Använd den här domänen** och välj sedan **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="bb85f-119">Type the domain name in the box, select **Use this domain**, and then select **Continue**.</span></span>

3. <span data-ttu-id="bb85f-120">Välj de tjänster som du vill testa med din domän, t. ex. e-post och snabb meddelanden.</span><span class="sxs-lookup"><span data-stu-id="bb85f-120">Select the services you want to test with your domain, like email and instant messaging.</span></span>

5. <span data-ttu-id="bb85f-121">På sidan **verifiera** domän följer du de stegvisa anvisningarna, AMD väljer **verifiera**.</span><span class="sxs-lookup"><span data-stu-id="bb85f-121">On the **Verify** domain page, follow the step-by-step instructions, amd then select **Verify**.</span></span>

    <span data-ttu-id="bb85f-122">Det tar mellan några minuter och 72 timmar för DNS-ändringarna att börja gälla.</span><span class="sxs-lookup"><span data-stu-id="bb85f-122">It takes between a few minutes and 72 hours for DNS changes to take effect.</span></span>

    <span data-ttu-id="bb85f-123">När verifieringen lyckas ombeds du ändra dina DNS-poster.</span><span class="sxs-lookup"><span data-stu-id="bb85f-123">When verification is successful, you are asked to modify your DNS records.</span></span>

### <a name="step-3-mark-the-domain-as-shared-in-exchange-online"></a><span data-ttu-id="bb85f-124">Steg 3: Markera domänen som delad i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="bb85f-124">Step 3: Mark the domain as shared in Exchange Online</span></span>

1. <span data-ttu-id="bb85f-125">I administrations centret för Exchange går du till avsnittet **e-postflöde**. Välj **godkända domäner** och välj sedan den domän som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="bb85f-125">In the Exchange admin center, in the **Mail flow** section, select **Accepted domains**, and then select the domain you want to modify.</span></span>

2. <span data-ttu-id="bb85f-126">Dubbelklicka på fönstret för att öppna det och välj **internt relä**.</span><span class="sxs-lookup"><span data-stu-id="bb85f-126">Double-click to open the window, and then select **Internal Relay**.</span></span> 

3. <span data-ttu-id="bb85f-127">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="bb85f-127">Select **Save**.</span></span>

    <span data-ttu-id="bb85f-128">Den här inställningen kan kräva ett par minuter för att börja gälla.</span><span class="sxs-lookup"><span data-stu-id="bb85f-128">This setting might require a few minutes to take effect.</span></span>

### <a name="step-4-unblock-the-existing-email-server-optional"></a><span data-ttu-id="bb85f-129">Steg 4: Häv blockering av den befintliga e-postservern (valfritt)</span><span class="sxs-lookup"><span data-stu-id="bb85f-129">Step 4: Unblock the existing email server (optional)</span></span>

<span data-ttu-id="bb85f-130">I Microsoft 365 används Exchange Online Protection (EOP) för skräp post skydd.</span><span class="sxs-lookup"><span data-stu-id="bb85f-130">Microsoft 365 uses Exchange Online Protection (EOP) for spam protection.</span></span> <span data-ttu-id="bb85f-131">EOP kanske blockerar din befintliga e-postserver om en stor volym skräp post överförs av den aktuella e-postservern.</span><span class="sxs-lookup"><span data-stu-id="bb85f-131">EOP might block your existing mail server if it detects a high volume of spam being forwarded by your current mail server.</span></span> <span data-ttu-id="bb85f-132">Om du litar på skräp post skyddet för den andra e-postleverantören kan du häva blockeringen av servern i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bb85f-132">If you trust the spam protection for your other email provider, you can unblock the server in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="bb85f-133">Om du tar bort blockeringen av den befintliga e-postservern får all skräp post som kommer via din ursprungliga server till gång till Microsoft 365-post lådorna och du kan inte utvärdera hur bra Microsoft 365 hindrar skräp post.</span><span class="sxs-lookup"><span data-stu-id="bb85f-133">Unblocking your existing email server allows any spam that arrives through your original server to come to the Microsoft 365 mailboxes, and you can’t evaluate how well Microsoft 365 prevents spam.</span></span>

1. <span data-ttu-id="bb85f-134">I navigerings fönstret i administrations centret för Exchange väljer du **skydd** och väljer sedan **anslutnings filter**.</span><span class="sxs-lookup"><span data-stu-id="bb85f-134">In the Exchange admin center navigation pane, select **Protection**, and then select **Connection filter**.</span></span>

2. <span data-ttu-id="bb85f-135">Välj **+\*\*\*\*i listan med lista över tillåtna IP-** och e-postservern.</span><span class="sxs-lookup"><span data-stu-id="bb85f-135">In the **IP Allow list**, select **+**, and add the mail server IP address for your current email provider.</span></span> 

### <a name="step-5-create-user-accounts-and-set-the-primary-reply-to-address"></a><span data-ttu-id="bb85f-136">Steg 5: skapa användarkonton och ange primär svars adress</span><span class="sxs-lookup"><span data-stu-id="bb85f-136">Step 5: Create user accounts and set the primary reply-to address</span></span>

1. <span data-ttu-id="bb85f-137">Välj **användare** > **aktiva användare** i det vänstra navigerings fältet i Administrationscenter för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bb85f-137">In the Microsoft 365 admin center left navigation, select **Users** > **Active Users**.</span></span>

2. <span data-ttu-id="bb85f-138">Skapa två test konton genom att lägga till två befintliga användare.</span><span class="sxs-lookup"><span data-stu-id="bb85f-138">Create two test accounts by adding two existing users.</span></span>

    <span data-ttu-id="bb85f-139">För varje konto väljer du **+ Lägg till en användare** och fyller i den information som krävs, inklusive den metod för lösen ord som du vill testa.</span><span class="sxs-lookup"><span data-stu-id="bb85f-139">For each account, select **+ Add a user**, and fill out the required information, including the password method you want to test.</span></span>

    <span data-ttu-id="bb85f-140">Om du vill vara säker på att användarens e-postadress är densamma måste fältet **användarnamn** matcha användarens aktuella e-postadress.</span><span class="sxs-lookup"><span data-stu-id="bb85f-140">To ensure a user’s email stays the same, the **User name** field must match the user’s current email address.</span></span>

3. <span data-ttu-id="bb85f-141">Välj en licens, klicka på **nästa** och klicka sedan **Slutför lägga till**.</span><span class="sxs-lookup"><span data-stu-id="bb85f-141">Choose the appropriate license, click **Next**, and then click **Finish adding**.</span></span> 

4. <span data-ttu-id="bb85f-142">Bredvid **Användarnamn** väljer du det anpassade domännamnet i listrutan.</span><span class="sxs-lookup"><span data-stu-id="bb85f-142">Next to **User name**, select your custom domain name from the drop-down list.</span></span> 

5. <span data-ttu-id="bb85f-143">Välj **skapa** > **stänga**.</span><span class="sxs-lookup"><span data-stu-id="bb85f-143">Select **Create** > **Close**.</span></span>

### <a name="step-6-configure-mail-to-flow-from-microsoft-365-or-office-365-to-email-server"></a><span data-ttu-id="bb85f-144">Steg 6: \*\*Konfigurera e-post att flytta från Microsoft 365 eller Office 365 till e-postservern</span><span class="sxs-lookup"><span data-stu-id="bb85f-144">Step 6: \*\*Configure mail to flow from Microsoft 365 or Office 365 to Email server</span></span>

<span data-ttu-id="bb85f-145">Det finns två steg för detta:</span><span class="sxs-lookup"><span data-stu-id="bb85f-145">There are two steps for this:</span></span>

1. <span data-ttu-id="bb85f-146">Konfigurera din Microsoft 365 eller Office 365-miljö.</span><span class="sxs-lookup"><span data-stu-id="bb85f-146">Configure your Microsoft 365 or Office 365 environment.</span></span>

2. <span data-ttu-id="bb85f-147">Konfigurera en anslutning från Microsoft 365 eller Office 365 till din e-postserver.</span><span class="sxs-lookup"><span data-stu-id="bb85f-147">Set up a connector from Microsoft 365 or Office 365 to your email server.</span></span>

### <a name="1-configure-your-microsoft-365-or-office-365-environment"></a><span data-ttu-id="bb85f-148">1. Konfigurera din Microsoft 365 eller Office 365-miljö.</span><span class="sxs-lookup"><span data-stu-id="bb85f-148">1. Configure your Microsoft 365 or Office 365 environment</span></span>

<span data-ttu-id="bb85f-149">Kontrollera att du är klar med följande i Microsoft 365 eller Office 365:</span><span class="sxs-lookup"><span data-stu-id="bb85f-149">Make sure you have completed the following in Microsoft 365 or Office 365:</span></span>

1. <span data-ttu-id="bb85f-150">För att konfigurera anslutningar behöver du ha behörigheter tilldelade innan du kan börja.</span><span class="sxs-lookup"><span data-stu-id="bb85f-150">To set up connectors, you need permissions assigned before you can begin.</span></span> <span data-ttu-id="bb85f-151">Om du vill kontrollera vilka behörigheter du behöver, kolla i Microsoft 365 och Office 365 anslutningspost i [Funktionsbehörigheter i EOP](../../security/office-365-security/feature-permissions-in-eop.md) avsnittet.</span><span class="sxs-lookup"><span data-stu-id="bb85f-151">To check what permissions you need, see the Microsoft 365 and Office 365 connectors entry in the [Feature permissions in EOP](../../security/office-365-security/feature-permissions-in-eop.md) topic.</span></span>

2. <span data-ttu-id="bb85f-152">Om du vill att EOP eller Exchange Online skickar e-post från din e-postserver till Internet gör du något av följande:</span><span class="sxs-lookup"><span data-stu-id="bb85f-152">If you want EOP or Exchange Online to relay email from your email servers to the Internet, either:</span></span>

   - <span data-ttu-id="bb85f-153">Använd ett certifikat konfigurerat med ett ämnesnamn som överensstämmer med en godkänd domän i Microsoft 365 eller Office 365.</span><span class="sxs-lookup"><span data-stu-id="bb85f-153">Use a certificate configured with a subject name that matches an accepted domain in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="bb85f-154">Vi rekommenderar att ditt certifikats namn eller ämnets alternativa namn överensstämmer med din organisations primära SMTP-domän.</span><span class="sxs-lookup"><span data-stu-id="bb85f-154">We recommend that your certificate's common name or subject alternative name matches the primary SMTP domain for your organization.</span></span> <span data-ttu-id="bb85f-155">Mer information finns i[Förutsättningar för din lokala e-postmiljö](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#prerequisites-for-your-on-premises-email-environment).</span><span class="sxs-lookup"><span data-stu-id="bb85f-155">For details, see [Prerequisites for your on-premises email environment](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#prerequisites-for-your-on-premises-email-environment).</span></span>

   <span data-ttu-id="bb85f-156">– ELLER –</span><span class="sxs-lookup"><span data-stu-id="bb85f-156">-OR-</span></span>

   - <span data-ttu-id="bb85f-157">Kontrollera att alla din organisations avsändardomäner och underdomäner är konfigurerade som godkända domäner i Microsoft 365 eller Office 365.</span><span class="sxs-lookup"><span data-stu-id="bb85f-157">Make sure that all your organization sender domains and subdomains are configured as accepted domains in Microsoft 365 or Office 365.</span></span>

   <span data-ttu-id="bb85f-158">Mer information om definiering av godkända domäner finns i [Hantera godkända domäner i Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) och [Aktivera e-postflöde för underdomäner i Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span><span class="sxs-lookup"><span data-stu-id="bb85f-158">For more information about defining accepted domains, see [Manage accepted domains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) and [Enable mail flow for subdomains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

3. <span data-ttu-id="bb85f-159">Bestäm om du vill använda regler för e-postflöde (kallas även transportregler) eller domän namn for att leverera e-post från Microsoft 365 eller Office 365 till dina e-postservrar.</span><span class="sxs-lookup"><span data-stu-id="bb85f-159">Decide whether you want to use mail flow rules (also known as transport rules) or domain names to deliver mail from Microsoft 365 or Office 365 to your email servers.</span></span> <span data-ttu-id="bb85f-160">De flesta företag väljer att skicka e-post för alla godkända domäner.</span><span class="sxs-lookup"><span data-stu-id="bb85f-160">Most businesses choose to deliver mail for all accepted domains.</span></span> <span data-ttu-id="bb85f-161">Mer information finns i [Scenario: Villkorsstyrd e-postdirigering i Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing).</span><span class="sxs-lookup"><span data-stu-id="bb85f-161">For more information, see [Scenario: Conditional mail routing in Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing).</span></span>

> [!NOTE]
> <span data-ttu-id="bb85f-162">Du kan konfigurera regler för e-postflöde enligt beskrivningen i [Åtgärder för e-postflödesregler i Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="bb85f-162">You can set up mail flow rules as described in [Mail flow rule actions in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span> <span data-ttu-id="bb85f-163">Du vill, till exempel, kanske använda regler för e-postflöde med anslutningar om din e-post för närvarande är dirigerad via distributionslistor till flera webbplatser.</span><span class="sxs-lookup"><span data-stu-id="bb85f-163">For example, you might want to use mail flow rules with connectors if your mail is currently directed via distribution lists to multiple sites.</span></span>

### <a name="2-set-up-a-connector-from-microsoft-365-or-office-365-to-your-email-server"></a><span data-ttu-id="bb85f-164">2. Konfigurera en anslutning från Microsoft 365 eller Office 365 till din e-postserver</span><span class="sxs-lookup"><span data-stu-id="bb85f-164">2. Set up a connector from Microsoft 365 or Office 365 to your email server</span></span>

<span data-ttu-id="bb85f-165">För att skapa en anslutning i Microsoft 365 eller Office 365, klicka på **Admin** och klicka sedan på **Exchange** för att gå till Administrations centret för Exchange.</span><span class="sxs-lookup"><span data-stu-id="bb85f-165">To create a connector in Microsoft 365 or Office 365, click **Admin**, and then click **Exchange** to go to the Exchange admin center.</span></span> <span data-ttu-id="bb85f-166">Sedan klickar du på **e-postflöde** och klickar på **anslutningar**.</span><span class="sxs-lookup"><span data-stu-id="bb85f-166">Next, click **mail flow**, and click **connectors**.</span></span>

<span data-ttu-id="bb85f-167">Konfigurera anslutningar med hjälp av guiden.</span><span class="sxs-lookup"><span data-stu-id="bb85f-167">Set up connectors using the wizard.</span></span>

<span data-ttu-id="bb85f-168">Starta guiden genom att klicka på plustecknet **+**.</span><span class="sxs-lookup"><span data-stu-id="bb85f-168">To start the wizard, click the plus symbol **+**.</span></span> <span data-ttu-id="bb85f-169">På den första skärmen välj **Från** Office 365 och **Till** Din Organisations e-postserver.</span><span class="sxs-lookup"><span data-stu-id="bb85f-169">On the first screen, choose **From** Office 365 and **To** Your Organization Mail server.</span></span>

<span data-ttu-id="bb85f-170">Klicka **Nästa** och följ instruktionerna i guiden.</span><span class="sxs-lookup"><span data-stu-id="bb85f-170">Click **Next**, and follow the instructions in the wizard.</span></span> <span data-ttu-id="bb85f-171">Klicka på **Hjälp** eller **Läs Mer** länkarna om du behöver mer information.</span><span class="sxs-lookup"><span data-stu-id="bb85f-171">Click the **Help** or **Learn More** links if you need more information.</span></span> <span data-ttu-id="bb85f-172">Guiden tar dig igenom konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="bb85f-172">The wizard will guide you through setup.</span></span> <span data-ttu-id="bb85f-173">På slutet kontrollera att din anslutningen har verifierats.</span><span class="sxs-lookup"><span data-stu-id="bb85f-173">At the end, make sure your connector validates.</span></span> <span data-ttu-id="bb85f-174">Om anslutningen inte validerar dubbelklicka på det meddelande som visas för mer information och läsa [Verifiera anslutningar ](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors) för hjälp med problemlösning.</span><span class="sxs-lookup"><span data-stu-id="bb85f-174">If the connector does not validate, double-click the message displayed to get more information, and see [Validate connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors) for help resolving issues.</span></span>



### <a name="step-7-update-dns-records-at-your-dns-hosting-provider"></a><span data-ttu-id="bb85f-175">Steg 7: Uppdatera DNS-posterna hos DNS-värden</span><span class="sxs-lookup"><span data-stu-id="bb85f-175">Step 7: Update DNS records at your DNS hosting provider</span></span>

<span data-ttu-id="bb85f-176">Logga in på din DNS-värds webbplats och följ anvisningarna i [lägga till DNS-poster för att ansluta domänen](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="bb85f-176">Sign in to your DNS hosting provider's website, and follow the instructions at [Add DNS records to connect your domain](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

<span data-ttu-id="bb85f-177">**Gör följande två undantag:**</span><span class="sxs-lookup"><span data-stu-id="bb85f-177">**Make the following two exceptions:**</span></span>

- <span data-ttu-id="bb85f-178">Skapa inte en ny MX-post samt ändra inte den befintliga MX-posten.</span><span class="sxs-lookup"><span data-stu-id="bb85f-178">Do not create a new MX record or change your existing MX record.</span></span>

- <span data-ttu-id="bb85f-179">Om du redan har en SPF-post (Sender Policy Framework) för din tidigare e-postleverantör, ska du i stället för att skapa en ny SPF-post (TXT) för Exchange Online lägga till "include: SPF. Protection. Outlook. com" i den aktuella TXT-posten.</span><span class="sxs-lookup"><span data-stu-id="bb85f-179">If you already have a Sender Policy Framework (SPF) record for your previous email provider, instead of creating a new SPF (TXT) record for Exchange Online, add "include:spf.protection.outlook.com" to the current TXT record.</span></span>

    <span data-ttu-id="bb85f-180">Exempel: "v = spf1 MX include: adatum. com inkluderar: SPF. Protection. Outlook. com ~ all".</span><span class="sxs-lookup"><span data-stu-id="bb85f-180">For example, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span></span>

    <span data-ttu-id="bb85f-181">Om du inte har en SPF-post ändrar du den som rekommenderas av Microsoft 365 för att inkludera domänen för din aktuella e-postleverantör och lägga till spf.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="bb85f-181">If you don't have an SPF record, modify the one recommended by Microsoft 365 to include the domain for your current email provider, and add spf.protection.outlook.com.</span></span> <span data-ttu-id="bb85f-182">Detta godkänner utgående meddelanden från båda e-postsystemen.</span><span class="sxs-lookup"><span data-stu-id="bb85f-182">This authorizes outgoing messages from both email systems.</span></span>

### <a name="step-8-set-up-email-forwarding-at-your-current-provider"></a><span data-ttu-id="bb85f-183">Steg 8: Konfigurera vidarebefordran av e-post hos din nuvarande leverantör</span><span class="sxs-lookup"><span data-stu-id="bb85f-183">Step 8: Set up email forwarding at your current provider</span></span>

<span data-ttu-id="bb85f-184">På din aktuella e-postleverantör ställer du in vidarebefordring för dina användares e-postkonton i din onmicrosoft.com-domän:</span><span class="sxs-lookup"><span data-stu-id="bb85f-184">At your current email provider, set up forwarding for your users email accounts to your onmicrosoft.com domain:</span></span>

- <span data-ttu-id="bb85f-185">Vidarebefordra en användare en post låda till usera@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="bb85f-185">Forward User A mailbox to usera@yourcompany.onmicrosoft.com</span></span>

- <span data-ttu-id="bb85f-186">Vidarebefordra användarens e-postlåda till userb@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="bb85f-186">Forward User B mailbox to userb@yourcompany.onmicrosoft.com</span></span>

<span data-ttu-id="bb85f-187">När du slutför det här steget blir all e-post som skickas till usera@yourcompany.com och userb@yourcompany.com tillgänglig i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bb85f-187">When you complete this step, all email sent to usera@yourcompany.com and userb@yourcompany.com is available in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="bb85f-188">Kontakta din aktuella e-postleverantör för att få de exakta stegen för att konfigurera vidarebefordran av e-post.</span><span class="sxs-lookup"><span data-stu-id="bb85f-188">Contact your current email provider for the exact steps to set up email forwarding.</span></span><br/>
> <span data-ttu-id="bb85f-189">Du behöver inte spara en kopia av meddelanden hos den aktuella e-postleverantören.</span><span class="sxs-lookup"><span data-stu-id="bb85f-189">You don't need to keep a copy of messages at the current email provider.</span></span><br/>
> <span data-ttu-id="bb85f-190">De flesta leverantörer vidarebefordrar e-post genom att lämna svar till avsändarens e-postadress intakt så att svar går till den ursprungliga avsändaren.</span><span class="sxs-lookup"><span data-stu-id="bb85f-190">Most providers forward email by leaving the Reply-to address of the sender intact so that replies go to the original sender.</span></span>

### <a name="step-9-test-mail-flow"></a><span data-ttu-id="bb85f-191">Steg 9: Testa e-postflöde</span><span class="sxs-lookup"><span data-stu-id="bb85f-191">Step 9: Test mail flow</span></span>

1. <span data-ttu-id="bb85f-192">Logga in på Outlook Web App med inloggnings uppgifterna för användaren A.</span><span class="sxs-lookup"><span data-stu-id="bb85f-192">Sign in to Outlook Web App using the credentials for User A.</span></span>

2. <span data-ttu-id="bb85f-193">Utför följande tester:</span><span class="sxs-lookup"><span data-stu-id="bb85f-193">Perform these tests:</span></span>

    - <span data-ttu-id="bb85f-194">Testa lokala Microsoft-e-postmeddelanden genom att till exempel skicka ett e-postmeddelande till användare B. E-postmeddelandet levereras omedelbart.</span><span class="sxs-lookup"><span data-stu-id="bb85f-194">Test local Microsoft email by sending an email, for example, to User B. The email is delivered immediately.</span></span> <span data-ttu-id="bb85f-195">I det här scenariot dirigeras inte meddelandet till post lådan för användare B på din ursprungliga server eftersom Microsoft 365-post lådan är lokal.</span><span class="sxs-lookup"><span data-stu-id="bb85f-195">In this scenario, the message is not routed to the mailbox for User B on your original server because the Microsoft 365 mailbox is local.</span></span>

    - <span data-ttu-id="bb85f-196">Testa e-post till en användare på det befintliga e-postsystemet genom att t. ex. Skicka ett e-postmeddelande till användare C. E-postmeddelandet skickas till användarens e-postserver på din ursprungliga e-postserver.</span><span class="sxs-lookup"><span data-stu-id="bb85f-196">Test email to a user on the existing email system by sending an email, for example, to User C. The email is delivered to the mailbox for User C on your original mail server.</span></span>

    - <span data-ttu-id="bb85f-197">Kontrollera att vidarebefordran är rätt konfigurerat från ett externt konto eller från ett e-postkonto i det befintliga e-postsystemet.</span><span class="sxs-lookup"><span data-stu-id="bb85f-197">Verify that forwarding is set up properly from an outside account, or from an employee email account on the existing email system.</span></span> <span data-ttu-id="bb85f-198">Skicka till exempel ett e-postmeddelande från det ursprungliga serverkontot för User C eller ett Hotmail-konto och verifiera att det anländer till Microsoft 365-postlådan för användare A.</span><span class="sxs-lookup"><span data-stu-id="bb85f-198">For example, from the original server account for User C or a Hotmail account, send User A an email and verify that it arrives in the Microsoft 365 mailbox for User A.</span></span>

### <a name="step-10-move-mailbox-contents"></a><span data-ttu-id="bb85f-199">Steg 10: Flytta postlådeinnehåll</span><span class="sxs-lookup"><span data-stu-id="bb85f-199">Step 10: Move mailbox contents</span></span>

<span data-ttu-id="bb85f-200">Eftersom du bara flyttar två test användare, och användare A och användare B båda använder Outlook, kan du flytta e-postmeddelandet genom att öppna det gamla. PST-filen i den nya Outlook-profilen och kopiera meddelanden, Kalender objekt, kontakter och så vidare.</span><span class="sxs-lookup"><span data-stu-id="bb85f-200">Because you are moving only two test users, and User A and User B are both using Outlook, you can move the email by opening the old .PST file in the new Outlook profile and copying the messages, calendar items, contacts, and so on.</span></span> <span data-ttu-id="bb85f-201">Mer information finns i [importera e-post, kontakter och kalender från en Outlook. PST-fil](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac).</span><span class="sxs-lookup"><span data-stu-id="bb85f-201">For more information, see [Import email, contacts, and calendar from an Outlook .pst file](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac).</span></span>

<span data-ttu-id="bb85f-202">När de har importer ATS till lämpliga platser i Microsoft 365-post lådan kan objekten vara tillgängliga från vilken enhet som helst, var som helst.</span><span class="sxs-lookup"><span data-stu-id="bb85f-202">After they’re imported to the appropriate locations in the Microsoft 365 mailbox, the items can be accessed from any device, anywhere.</span></span>