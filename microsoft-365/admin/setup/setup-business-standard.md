---
title: Konfigurera Microsoft 365 Business Standard
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
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
- okr_smb
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- BEA160
description: Lär dig hur du konfigurerar din Microsoft 365 Business Standard-abonnemang.
ms.openlocfilehash: 61ba3b0a8a753c9c441fc5a2ffa66b63da9af675
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572423"
---
# <a name="set-up-microsoft-business-standard"></a><span data-ttu-id="6c3e3-103">Konfigurera Microsoft Business Standard</span><span class="sxs-lookup"><span data-stu-id="6c3e3-103">Set up Microsoft Business Standard</span></span>



## <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="6c3e3-104">Lägga till din domän för att personanpassa inloggning</span><span class="sxs-lookup"><span data-stu-id="6c3e3-104">Add your domain to personalize sign-in</span></span>

<span data-ttu-id="6c3e3-105">När du köper Microsoft 365 Business Standard får du möjlighet att använda en domän som du äger eller köpa en under registreringen.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-105">When you purchase Microsoft 365 Business Standard, you have the option of using a domain you own, or buying one during the sign-up.</span></span>

- <span data-ttu-id="6c3e3-106">Om du har köpt en ny domän när du registrerade dig kommer din domän att konfigureras, och du kan gå vidare till [Lägga till användare och tilldela licenser](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="6c3e3-106">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

1. <span data-ttu-id="6c3e3-107">Logga in på [Administrationscenter för Microsoft 365](https://admin.microsoft.com) som global administratör.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-107">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="6c3e3-108">Starta guiden genom att välja **Gå till inställningar**.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-108">Choose **Go to setup** to start the wizard.</span></span>

3. <span data-ttu-id="6c3e3-109">På sidan **Installera Office-apparna** kan du välja att installera apparna på din egen dator.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-109">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="6c3e3-110">Under steget **Lägg till domän** anger du domännamnet du vill använda (t.ex. contoso.com).</span><span class="sxs-lookup"><span data-stu-id="6c3e3-110">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="6c3e3-111">Om du har köpt en domän under registreringen ser du inte steget **Lägg till en domän** här.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-111">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="6c3e3-112">Gå istället till [Lägg till användare](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="6c3e3-112">Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    
4. <span data-ttu-id="6c3e3-113">Följ anvisningarna i guiden för att [Skapa DNS-poster på vilken DNS-värd som helst för Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) som verifierar att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-113">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="6c3e3-114">Om du vet vilken din domänvärd är kan du även se [Värdspecifika anvisningar](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="6c3e3-114">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="6c3e3-115">Om din värd är GoDaddy eller en annan värd som är aktiverad med [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)är processen enkel och du blir automatiskt ombedd att logga in och låta Microsoft autentisera.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-115">If your hosting provider is GoDaddy or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![Välj Auktorisera på sidan Bekräfta Åtkomst hos GoDaddy.](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a><span data-ttu-id="6c3e3-117">Lägga till användare och tilldela licenser</span><span class="sxs-lookup"><span data-stu-id="6c3e3-117">Add users and assign licenses</span></span>

<span data-ttu-id="6c3e3-118">Du kan lägga till användare i guiden eller så kan du [lägga till användare senare](../add-users/add-users.md) i administratörscentret.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-118">You can add users in the wizard, but you can also [add users later](../add-users/add-users.md) in the admin center.</span></span> <span data-ttu-id="6c3e3-119">Om du har en lokal domänkontrollant kan du även lägga till användare med [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="6c3e3-119">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

## <a name="add-users-in-the-wizard"></a><span data-ttu-id="6c3e3-120">Lägg till användare i guiden</span><span class="sxs-lookup"><span data-stu-id="6c3e3-120">Add users in the wizard</span></span>

<span data-ttu-id="6c3e3-121">Alla användare som du lägger till i guiden får automatiskt en Microsoft 365 Business Standard-licens.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-121">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Standard license.</span></span>

1. <span data-ttu-id="6c3e3-122">Om ditt Microsoft 365 Business Standard-abonnemang har befintliga användare (till exempel om du använde Azure AD Connect), får du möjlighet att tilldela licenser till dem nu.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-122">If your Microsoft 365 Business Standard subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="6c3e3-123">Lägg till licenser till dem också.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-123">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="6c3e3-124">Efter att ha lagt till användarna får du också möjlighet att dela autentiseringsuppgifter med de nya användarna som du har lagt till.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-124">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="6c3e3-125">Du kan välja att skriva ut, e-posta eller ladda ned.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-125">You can choose to print them out, email them, or download them.</span></span>

## <a name="connect-your-domain"></a><span data-ttu-id="6c3e3-126">Koppla din domän</span><span class="sxs-lookup"><span data-stu-id="6c3e3-126">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="6c3e3-127">Om du väljer att använda .onmicrosoft-domänen, eller använde Azure AD Connect för att konfigurera användare, kommer du inte att se det här steget.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-127">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="6c3e3-128">För att få igång tjänsten måste du uppdatera några poster hos din DNS-värd eller domänregistrator.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-128">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="6c3e3-129">Installationsguiden identifierar normalt din domänregistrator och ger dig en länk till stegvisa instruktioner för att uppdatera dina NS-poster på registratorns webbplats.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-129">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="6c3e3-130">Om det inte gör det, [ ändra namnservrar för att konfigurera Office 365 med valfri domänregistrator](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar).</span><span class="sxs-lookup"><span data-stu-id="6c3e3-130">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar).</span></span> 

    - <span data-ttu-id="6c3e3-131">Om du har befintliga DNS-poster, t. ex. en befintlig webbplats, men din DNS-värd är aktiverad för [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)väljer du **Lägga till poster för mig**.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-131">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="6c3e3-132">På sidan **Välj onlinetjänster** accepterar du alla standardinställningar och väljer **Nästa** och väljer **Auktorisera** på DNS-värdens sida.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-132">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="6c3e3-133">Om du har befintliga DNS-poster med andra DNS-värdar (inte aktiverad för domänanslutning), ska du hantera dina egna DNS-poster för att se till att de befintliga tjänsterna fortsätter att vara anslutna.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-133">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="6c3e3-134">Mer information finns i [domängrunder](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics).</span><span class="sxs-lookup"><span data-stu-id="6c3e3-134">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

2. <span data-ttu-id="6c3e3-135">Följ stegen i guiden så kommer e-postmeddelanden och andra tjänster att konfigureras åt dig.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-135">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

    <span data-ttu-id="6c3e3-136">När registreringsprocessen är klar dirigeras du till administrationscentret, där du kommer att följa en guide för att installera Office-program, lägga till din domän, lägga till användare och tilldela licenser.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-136">When the signup process is complete, you'll be directed to the admin center, where you'll follow a wizard to install Office apps, add your domain, add users, and assign licenses.</span></span> <span data-ttu-id="6c3e3-137">När du har slutfört den första konfigurationen kan du använda **konfigurationssidan** i administrationscentret och fortsätta att installera och konfigurera tjänsterna som medföljer prenumerationerna.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-137">After you complete the initial setup, you can use the **Setup** page in the admin center to continue setting up and configuring the services that come with your subscriptions.</span></span>

    <span data-ttu-id="6c3e3-138">Mer information om installationsguiden för och administrationscentrets **konfigurationssida** finns i [Skillnaden mellan installationsguiden och sidan Konfigurera](o365-setup-wizard-and-setup-page.md).</span><span class="sxs-lookup"><span data-stu-id="6c3e3-138">For more information about the setup wizard and the admin center **Setup** page, see [Difference between the setup wizard and the Setup page](o365-setup-wizard-and-setup-page.md).</span></span>

## <a name="finish-setting-up"></a><span data-ttu-id="6c3e3-139">Slutför konfigureringen</span><span class="sxs-lookup"><span data-stu-id="6c3e3-139">Finish setting up</span></span>

### <a name="set-up-outlook-for-email"></a><span data-ttu-id="6c3e3-140">Konfigurera Outlook för e-post</span><span class="sxs-lookup"><span data-stu-id="6c3e3-140">Set up Outlook for email</span></span>

1. <span data-ttu-id="6c3e3-141">Sök efter Outlook i Windows startmeny och välj det.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-141">On the Windows Start menu, search for Outlook, and select it.</span></span>

    <span data-ttu-id="6c3e3-142">(Om du använder en Mac öppnar du Outlook från verktygsfältet eller söker efter det med Finder.)</span><span class="sxs-lookup"><span data-stu-id="6c3e3-142">(If you're using a Mac, open Outlook from the toolbar or locate it using the Finder.)</span></span>

    <span data-ttu-id="6c3e3-143">Om du just installerat Outlook väljer du **Nästa** på välkomstsidan.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-143">If you've just installed Outlook, on the Welcome page, select **Next**.</span></span>

2. <span data-ttu-id="6c3e3-144">Välj **Arkiv** \> **Information** \> **Lägg till konto**.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-144">Choose **File** \> **Info** \> **Add Account**.</span></span>

3. <span data-ttu-id="6c3e3-145">Ange din Microsoft e-postadress och välj **Anslut**.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-145">Enter your Microsoft email address and select **Connect**.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/9fe86884-8a83-42cc-bca9-61a12e6dad31?autoplay=false]
  
<span data-ttu-id="6c3e3-146">Mer information finns i [Konfigurera Outlook för e-post](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f).</span><span class="sxs-lookup"><span data-stu-id="6c3e3-146">More at [Set up Outlook for email](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f).</span></span>
  
### <a name="import-email"></a><span data-ttu-id="6c3e3-147">Importera e-post</span><span class="sxs-lookup"><span data-stu-id="6c3e3-147">Import email</span></span>

<span data-ttu-id="6c3e3-148">Om du tidigare använde Outlook med ett annat e-postkonto kan du importera din tidigare e-post, kalender och dina tidigare kontakter till ditt nya Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-148">If you were using Outlook with another email account, you can import your previous email, calendar, and contacts into your new Microsoft account.</span></span>
  
1. <span data-ttu-id="6c3e3-149">**Exportera din gamla e-post**</span><span class="sxs-lookup"><span data-stu-id="6c3e3-149">**Export your old email**</span></span>

    <span data-ttu-id="6c3e3-150">Välj **Arkiv** \> **Öppna &amp; Exportera** \> **Importera/Exportera** i Outlook.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-150">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>

    <span data-ttu-id="6c3e3-151">Välj **Exportera till en fil** och följ sedan anvisningarna för att exportera din Outlook-datafil (.pst) och undermappar.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-151">Select **Export to a File** and then follow the steps to export your Outlook Data File (.pst) and any subfolders.</span></span>

2. <span data-ttu-id="6c3e3-152">**Importera din gamla e-post**</span><span class="sxs-lookup"><span data-stu-id="6c3e3-152">**Import your old email**</span></span>

    <span data-ttu-id="6c3e3-153">Välj återigen **Arkiv** \> **Öppna &amp; Exportera** \> **Importera/Exportera** i Outlook.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-153">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export** again.</span></span>

    <span data-ttu-id="6c3e3-154">Den här gången väljer du **Importera från ett annat program eller en fil** och följer anvisningarna för att importera säkerhetskopian som du skapade när du exporterade din gamla e-post.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-154">This time, select **Import from another program or file** and follow the steps to import the backup file you created when you exported your old email.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/40f7df36-9e24-44e5-8791-e9ed0dd8fd21?autoplay=false]
  
<span data-ttu-id="6c3e3-155">Mer information finns i [Importera e-post med Outlook](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de).</span><span class="sxs-lookup"><span data-stu-id="6c3e3-155">More at [Import email with Outlook](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de).</span></span>

<span data-ttu-id="6c3e3-156">Du kan också använda administrationscentret för Exchange för att importera alla användares e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-156">You can also use Exchange admin center to import everyone's email.</span></span> <span data-ttu-id="6c3e3-157">Mer information finns i [migrera flera e-postkonton](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span><span class="sxs-lookup"><span data-stu-id="6c3e3-157">For more information, see [migrate multiple email accounts](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span></span>
  
### <a name="use-a-public-website"></a><span data-ttu-id="6c3e3-158">Använda en offentlig webbplats</span><span class="sxs-lookup"><span data-stu-id="6c3e3-158">Use a public website</span></span>

<span data-ttu-id="6c3e3-159">Microsoft 365 inkluderar inte en offentlig webbplats för ditt företag.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-159">Microsoft 365 doesn't include a public website for your business.</span></span> <span data-ttu-id="6c3e3-160">Om du vill skapa en bör du överväga att använda en Microsoft-partner som GoDaddy eller WIX.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-160">If you want to set one up, consider using a Microsoft partner, such as GoDaddy or WIX.</span></span>
  
1. <span data-ttu-id="6c3e3-161">Från administrationscentret går du till **Resurser** och väljer **Offentlig webbplats**.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-161">From the admin center, go to **Resources**, and then select **Public website**.</span></span>

2. <span data-ttu-id="6c3e3-162">Välj **Mer information** under något av alternativen och registrera dig sedan med en webbplatspartner och använd deras verktyg för att konfigurera och utforma webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="6c3e3-162">Select **Learn more** under one of the options, and then sign up with a website partner and use their tools to set up and design your site.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/4839abc6-9323-4cbf-a79d-2907235f9ebb]

<span data-ttu-id="6c3e3-163">Se mer på [Använda en offentlig webbplats](https://support.microsoft.com/office/3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="6c3e3-163">More at [Use a public website](https://support.microsoft.com/office/3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>