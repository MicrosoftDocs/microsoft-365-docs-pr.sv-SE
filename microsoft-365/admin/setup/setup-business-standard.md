---
title: Konfigurera Microsoft 365 Business Standard
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
- TRN_SMB
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- BEA160
description: När du köper Microsoft 365 Business Standard får du möjlighet att använda en domän som du äger eller köpa en under registreringen.
ms.openlocfilehash: 188f6c396cfb3a4448306070da0fd75dd11a46b3
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227733"
---
# <a name="set-up-microsoft-business-standard"></a><span data-ttu-id="9f7a9-103">Konfigurera Microsoft Business Standard</span><span class="sxs-lookup"><span data-stu-id="9f7a9-103">Set up Microsoft Business Standard</span></span>



## <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="9f7a9-104">Lägga till din domän för att personanpassa inloggning</span><span class="sxs-lookup"><span data-stu-id="9f7a9-104">Add your domain to personalize sign-in</span></span>

<span data-ttu-id="9f7a9-105">När du köper Microsoft 365 Business Standard får du möjlighet att använda en domän som du äger eller köpa en under registreringen.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-105">When you purchase Microsoft 365 Business Standard, you have the option of using a domain you own, or buying one during the sign-up.</span></span>

- <span data-ttu-id="9f7a9-106">Om du har köpt en ny domän när du registrerade dig kommer din domän att konfigureras, och du kan gå vidare till [Lägga till användare och tilldela licenser](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="9f7a9-106">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

1. <span data-ttu-id="9f7a9-107">Logga in på [Administrationscenter för Microsoft 365](https://admin.microsoft.com) som global administratör.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-107">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="9f7a9-108">Starta guiden genom att välja **Gå till inställningar**.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-108">Choose **Go to setup** to start the wizard.</span></span>

3. <span data-ttu-id="9f7a9-109">På sidan **Installera Office-apparna** kan du välja att installera apparna på din egen dator.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-109">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="9f7a9-110">Under steget **Lägg till domän** anger du domännamnet du vill använda (t.ex. contoso.com).</span><span class="sxs-lookup"><span data-stu-id="9f7a9-110">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="9f7a9-p101">Om du har köpt en domän under registreringen ser du inte steget **Lägg till en domän** här. Gå i stället till [Lägg till användare](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="9f7a9-p101">If you purchased a domain during the sign-up, you will not see **Add a domain** step here. Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    
4. <span data-ttu-id="9f7a9-113">Följ anvisningarna i guiden för att [Skapa DNS-poster på vilken DNS-värd som helst för Office 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) som verifierar att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-113">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="9f7a9-114">Om du känner till din domänvärd kan du även läsa [Lägga till en domän i Microsoft 365](/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="9f7a9-114">If you know your domain host, see also [Add a domain to Microsoft 365](/microsoft-365/admin/setup/add-domain).</span></span>

    <span data-ttu-id="9f7a9-115">Om din värd är GoDaddy eller en annan värd som är aktiverad med [Domain Connect](/office365/admin/get-help-with-domains/domain-connect)är processen enkel och du blir automatiskt ombedd att logga in och låta Microsoft autentisera.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-115">If your hosting provider is GoDaddy or another host enabled with [domain connect](/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![Välj Auktorisera på sidan Bekräfta Åtkomst hos GoDaddy.](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a><span data-ttu-id="9f7a9-117">Lägga till användare och tilldela licenser</span><span class="sxs-lookup"><span data-stu-id="9f7a9-117">Add users and assign licenses</span></span>

<span data-ttu-id="9f7a9-118">Du kan lägga till användare i guiden eller så kan du [lägga till användare senare](../add-users/add-users.md) i administratörscentret.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-118">You can add users in the wizard, but you can also [add users later](../add-users/add-users.md) in the admin center.</span></span> <span data-ttu-id="9f7a9-119">Om du har en lokal domänkontrollant kan du även lägga till användare med [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="9f7a9-119">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

## <a name="add-users-in-the-wizard"></a><span data-ttu-id="9f7a9-120">Lägg till användare i guiden</span><span class="sxs-lookup"><span data-stu-id="9f7a9-120">Add users in the wizard</span></span>

<span data-ttu-id="9f7a9-121">Alla användare som du lägger till i guiden får automatiskt en Microsoft 365 Business Standard-licens.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-121">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Standard license.</span></span>

1. <span data-ttu-id="9f7a9-p104">Om din prenumeration på Microsoft 365 Business Standard har befintliga användare (till exempel om du använde Azure AD Connect), får du möjlighet att tilldela licenser till dem nu. Lägg till licenser till dem också.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-p104">If your Microsoft 365 Business Standard subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="9f7a9-p105">När du har lagt till användarna får du även ett alternativ för att dela autentiseringsuppgifter med dem. Du kan välja att skriva ut, skicka via e-post eller ladda ned dem.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-p105">After you've added the users, you'll also get an option to share credentials with the new users you added. You can choose to print them out, email them, or download them.</span></span>

## <a name="connect-your-domain"></a><span data-ttu-id="9f7a9-126">Koppla din domän</span><span class="sxs-lookup"><span data-stu-id="9f7a9-126">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="9f7a9-127">Om du väljer att använda .onmicrosoft-domänen, eller använde Azure AD Connect för att konfigurera användare, kommer du inte att se det här steget.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-127">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="9f7a9-128">För att få igång tjänsten måste du uppdatera några poster hos din DNS-värd eller domänregistrator.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-128">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="9f7a9-129">Installationsguiden identifierar normalt din domänregistrator och ger dig en länk till stegvisa instruktioner för att uppdatera dina NS-poster på registratorns webbplats.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-129">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="9f7a9-130">Om det inte gör det, [ ändra namnservrar för att konfigurera Office 365 med valfri domänregistrator](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="9f7a9-130">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md).</span></span> 

    - <span data-ttu-id="9f7a9-131">Om du har befintliga DNS-poster, t. ex. en befintlig webbplats, men din DNS-värd är aktiverad för [Domain Connect](/office365/admin/get-help-with-domains/domain-connect)väljer du **Lägga till poster för mig**.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-131">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="9f7a9-132">På sidan **Välj onlinetjänster** accepterar du alla standardinställningar och väljer **Nästa** och väljer **Auktorisera** på DNS-värdens sida.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-132">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="9f7a9-p108">Om du har befintliga DNS-poster med andra DNS-värdar (inte aktiverad för domänanslutning), ska du hantera dina egna DNS-poster för att se till att de befintliga tjänsterna fortsätter att vara anslutna. Mer information finns i [grundläggande information för domän](/office365/admin/get-help-with-domains/dns-basics).</span><span class="sxs-lookup"><span data-stu-id="9f7a9-p108">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected. See [domain basics](/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

2. <span data-ttu-id="9f7a9-135">Följ stegen i guiden så kommer e-postmeddelanden och andra tjänster att konfigureras åt dig.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-135">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

    <span data-ttu-id="9f7a9-136">När registreringsprocessen är klar dirigeras du till administrationscentret, där du kommer att följa en guide för att installera Office-program, lägga till din domän, lägga till användare och tilldela licenser.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-136">When the signup process is complete, you'll be directed to the admin center, where you'll follow a wizard to install Office apps, add your domain, add users, and assign licenses.</span></span> <span data-ttu-id="9f7a9-137">När du har slutfört den första konfigurationen kan du använda **konfigurationssidan** i administrationscentret och fortsätta att installera och konfigurera tjänsterna som medföljer prenumerationerna.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-137">After you complete the initial setup, you can use the **Setup** page in the admin center to continue setting up and configuring the services that come with your subscriptions.</span></span>

    <span data-ttu-id="9f7a9-138">Mer information om installationsguiden för och administrationscentrets **konfigurationssida** finns i [Skillnaden mellan installationsguiden och sidan Konfigurera](o365-setup-wizard-and-setup-page.md).</span><span class="sxs-lookup"><span data-stu-id="9f7a9-138">For more information about the setup wizard and the admin center **Setup** page, see [Difference between the setup wizard and the Setup page](o365-setup-wizard-and-setup-page.md).</span></span>

## <a name="finish-setting-up"></a><span data-ttu-id="9f7a9-139">Slutför konfigureringen</span><span class="sxs-lookup"><span data-stu-id="9f7a9-139">Finish setting up</span></span>

### <a name="set-up-outlook-for-email"></a><span data-ttu-id="9f7a9-140">Konfigurera Outlook för e-post</span><span class="sxs-lookup"><span data-stu-id="9f7a9-140">Set up Outlook for email</span></span>

1. <span data-ttu-id="9f7a9-141">Sök efter Outlook i Windows startmeny och välj det.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-141">On the Windows Start menu, search for Outlook, and select it.</span></span>

    <span data-ttu-id="9f7a9-142">(Om du använder en Mac öppnar du Outlook från verktygsfältet eller söker efter det med Finder.)</span><span class="sxs-lookup"><span data-stu-id="9f7a9-142">(If you're using a Mac, open Outlook from the toolbar or locate it using the Finder.)</span></span>

    <span data-ttu-id="9f7a9-143">Om du just installerat Outlook väljer du **Nästa** på välkomstsidan.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-143">If you've just installed Outlook, on the Welcome page, select **Next**.</span></span>

2. <span data-ttu-id="9f7a9-144">Välj **Arkiv** \> **Information** \> **Lägg till konto**.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-144">Choose **File** \> **Info** \> **Add Account**.</span></span>

3. <span data-ttu-id="9f7a9-145">Ange din Microsoft e-postadress och välj **Anslut**.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-145">Enter your Microsoft email address and select **Connect**.</span></span>

## <a name="watch-set-up-outlook-for-email"></a><span data-ttu-id="9f7a9-146">Titta: Konfigurera Outlook för e-post</span><span class="sxs-lookup"><span data-stu-id="9f7a9-146">Watch: Set up Outlook for email</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/9fe86884-8a83-42cc-bca9-61a12e6dad31?autoplay=false]
  
<span data-ttu-id="9f7a9-147">Mer information finns i [Konfigurera Outlook för e-post](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f).</span><span class="sxs-lookup"><span data-stu-id="9f7a9-147">More at [Set up Outlook for email](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f).</span></span>
  
### <a name="import-email"></a><span data-ttu-id="9f7a9-148">Importera e-post</span><span class="sxs-lookup"><span data-stu-id="9f7a9-148">Import email</span></span>

<span data-ttu-id="9f7a9-149">Om du tidigare använde Outlook med ett annat e-postkonto kan du importera din tidigare e-post, kalender och dina tidigare kontakter till ditt nya Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-149">If you were using Outlook with another email account, you can import your previous email, calendar, and contacts into your new Microsoft account.</span></span>
  
1. <span data-ttu-id="9f7a9-150">**Exportera din gamla e-post**</span><span class="sxs-lookup"><span data-stu-id="9f7a9-150">**Export your old email**</span></span>

    <span data-ttu-id="9f7a9-151">Välj **Arkiv** \> **Öppna &amp; Exportera** \> **Importera/Exportera** i Outlook.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-151">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>

    <span data-ttu-id="9f7a9-152">Välj **Exportera till en fil** och följ sedan anvisningarna för att exportera din Outlook-datafil (.pst) och undermappar.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-152">Select **Export to a File** and then follow the steps to export your Outlook Data File (.pst) and any subfolders.</span></span>

2. <span data-ttu-id="9f7a9-153">**Importera din gamla e-post**</span><span class="sxs-lookup"><span data-stu-id="9f7a9-153">**Import your old email**</span></span>

    <span data-ttu-id="9f7a9-154">Välj återigen **Arkiv** \> **Öppna &amp; Exportera** \> **Importera/Exportera** i Outlook.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-154">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export** again.</span></span>

    <span data-ttu-id="9f7a9-155">Den här gången väljer du **Importera från ett annat program eller en fil** och följer anvisningarna för att importera säkerhetskopian som du skapade när du exporterade din gamla e-post.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-155">This time, select **Import from another program or file** and follow the steps to import the backup file you created when you exported your old email.</span></span>

## <a name="watch-import-and-redirect-email"></a><span data-ttu-id="9f7a9-156">Titta: importera och omdirigera e-post</span><span class="sxs-lookup"><span data-stu-id="9f7a9-156">Watch: Import and redirect email</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/40f7df36-9e24-44e5-8791-e9ed0dd8fd21?autoplay=false]
  
<span data-ttu-id="9f7a9-157">Mer information finns i [Importera e-post med Outlook](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de).</span><span class="sxs-lookup"><span data-stu-id="9f7a9-157">More at [Import email with Outlook](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de).</span></span>

<span data-ttu-id="9f7a9-158">Du kan också använda administrationscentret för Exchange för att importera alla användares e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-158">You can also use Exchange admin center to import everyone's email.</span></span> <span data-ttu-id="9f7a9-159">Mer information finns i [migrera flera e-postkonton](/Exchange/mailbox-migration/mailbox-migration).</span><span class="sxs-lookup"><span data-stu-id="9f7a9-159">For more information, see [migrate multiple email accounts](/Exchange/mailbox-migration/mailbox-migration).</span></span>
  
### <a name="use-a-public-website"></a><span data-ttu-id="9f7a9-160">Använda en offentlig webbplats</span><span class="sxs-lookup"><span data-stu-id="9f7a9-160">Use a public website</span></span>

<span data-ttu-id="9f7a9-161">Microsoft 365 inkluderar inte en offentlig webbplats för ditt företag.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-161">Microsoft 365 doesn't include a public website for your business.</span></span> <span data-ttu-id="9f7a9-162">Om du vill skapa en bör du överväga att använda en Microsoft-partner som GoDaddy eller WIX.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-162">If you want to set one up, consider using a Microsoft partner, such as GoDaddy or WIX.</span></span>
  
1. <span data-ttu-id="9f7a9-163">Från administrationscentret går du till **Resurser** och väljer **Offentlig webbplats**.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-163">From the admin center, go to **Resources**, and then select **Public website**.</span></span>

2. <span data-ttu-id="9f7a9-164">Välj **Mer information** under något av alternativen och registrera dig sedan med en webbplatspartner och använd deras verktyg för att konfigurera och utforma webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="9f7a9-164">Select **Learn more** under one of the options, and then sign up with a website partner and use their tools to set up and design your site.</span></span>

## <a name="watch-create-your-business-website"></a><span data-ttu-id="9f7a9-165">Titta: skapa din företagswebbplats</span><span class="sxs-lookup"><span data-stu-id="9f7a9-165">Watch: Create your business website</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/4839abc6-9323-4cbf-a79d-2907235f9ebb]

## <a name="related-content"></a><span data-ttu-id="9f7a9-166">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="9f7a9-166">Related content</span></span>

<span data-ttu-id="9f7a9-167">[Skapa en webbplats](../../business-video/create-web-site.md) (video)</span><span class="sxs-lookup"><span data-stu-id="9f7a9-167">[Create a website](../../business-video/create-web-site.md) (video)</span></span>\
<span data-ttu-id="9f7a9-168">[Microsoft 365 för företaget](../../business-video/index.yml) (länksida)</span><span class="sxs-lookup"><span data-stu-id="9f7a9-168">[Microsoft 365 for your business](../../business-video/index.yml) (link page)</span></span>
