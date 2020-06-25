---
title: Konfigurera Microsoft 365 Business Basic
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
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
description: Lär dig hur du konfigurerar din Microsoft 365 Business Basic-abonnemang.
ms.openlocfilehash: 9b448db2a6b8c78bb5265b1e80a01e93c9a6c6ca
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44778907"
---
# <a name="set-up-microsoft-365-business-basic"></a><span data-ttu-id="e1947-103">Konfigurera Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="e1947-103">Set up Microsoft 365 Business Basic</span></span>

 <span data-ttu-id="e1947-104">Titta på en kort video om hur du konfigurerar Microsoft 365 Business Basic.</span><span class="sxs-lookup"><span data-stu-id="e1947-104">Watch a short video about setting up Microsoft 365 Business Basic.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vk3W]

<span data-ttu-id="e1947-105">Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="e1947-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="e1947-106">Lägga till din domän för att personanpassa inloggning</span><span class="sxs-lookup"><span data-stu-id="e1947-106">Add your domain to personalize sign-in</span></span>

<span data-ttu-id="e1947-107">När du köper Microsoft 365 Business Basic får du möjlighet att använda en domän som du äger eller köpa en under registreringen.</span><span class="sxs-lookup"><span data-stu-id="e1947-107">When you purchase Microsoft 365 Business Basic, you have the option of using a domain you own, or buying one during the sign-up.</span></span>

- <span data-ttu-id="e1947-108">Om du har köpt en ny domän när du registrerade dig kommer din domän att konfigureras, och du kan gå vidare till [Lägga till användare och tilldela licenser](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="e1947-108">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

 ::: moniker range="o365-worldwide"

1. <span data-ttu-id="e1947-109">Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="e1947-109">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e1947-110">Om du använder Office 365 Germany går du till [det här administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=848041).</span><span class="sxs-lookup"><span data-stu-id="e1947-110">If you're using Office 365 Germany, go to [this admin center](https://go.microsoft.com/fwlink/p/?linkid=848041).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e1947-111">Om du använder Office 365 som drivs av 21Vianet går du till [det här administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=850627).</span><span class="sxs-lookup"><span data-stu-id="e1947-111">If you're using Office 365 operated by 21Vianet, go to [this admin center.](https://go.microsoft.com/fwlink/p/?linkid=850627).</span></span>

::: moniker-end 

2. <span data-ttu-id="e1947-112">Starta guiden genom att välja **Gå till inställningar**.</span><span class="sxs-lookup"><span data-stu-id="e1947-112">Choose **Go to setup** to start the wizard.</span></span>
    
3. <span data-ttu-id="e1947-113">Under steget **Lägg till domän** anger du domännamnet du vill använda (t.ex. contoso.com).</span><span class="sxs-lookup"><span data-stu-id="e1947-113">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e1947-114">Om du har köpt en domän under registreringen ser du inte steget **Lägg till en domän** här.</span><span class="sxs-lookup"><span data-stu-id="e1947-114">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="e1947-115">Gå istället till [Lägg till användare](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="e1947-115">Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    
4. <span data-ttu-id="e1947-116">Följ anvisningarna i guiden för att [Skapa DNS-poster på vilken DNS-värd som helst för Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) som verifierar att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="e1947-116">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="e1947-117">Om du vet vilken din domänvärd är kan du även se [Värdspecifika anvisningar](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="e1947-117">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="e1947-118">Om din värd är GoDaddy eller en annan värd som är aktiverad med [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)är processen enkel och du blir automatiskt ombedd att logga in och låta Microsoft autentisera.</span><span class="sxs-lookup"><span data-stu-id="e1947-118">If your hosting provider is GoDaddy or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![Välj Auktorisera på sidan Bekräfta Åtkomst hos GoDaddy.](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a><span data-ttu-id="e1947-120">Lägga till användare och tilldela licenser</span><span class="sxs-lookup"><span data-stu-id="e1947-120">Add users and assign licenses</span></span>

<span data-ttu-id="e1947-121">Du kan lägga till användare i guiden eller så kan du [lägga till användare senare](../add-users/add-users.md) i administratörscentret.</span><span class="sxs-lookup"><span data-stu-id="e1947-121">You can add users in the wizard, but you can also [add users later](../add-users/add-users.md) in the admin center.</span></span> <span data-ttu-id="e1947-122">Om du har en lokal domänkontrollant kan du även lägga till användare med [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="e1947-122">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

## <a name="add-users-in-the-wizard"></a><span data-ttu-id="e1947-123">Lägg till användare i guiden</span><span class="sxs-lookup"><span data-stu-id="e1947-123">Add users in the wizard</span></span>

<span data-ttu-id="e1947-124">Alla användare som du lägger till i guiden får automatiskt en Microsoft 365 Business Basic-licens.</span><span class="sxs-lookup"><span data-stu-id="e1947-124">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Basic license.</span></span>

1. <span data-ttu-id="e1947-125">Om ditt Microsoft 365 Business Basic-abonnemang har befintliga användare (till exempel om du använde Azure AD Connect), får du möjlighet att tilldela licenser till dem nu.</span><span class="sxs-lookup"><span data-stu-id="e1947-125">If your Microsoft 365 Business Basic subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="e1947-126">Lägg till licenser till dem också.</span><span class="sxs-lookup"><span data-stu-id="e1947-126">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="e1947-127">Efter att ha lagt till användarna får du också möjlighet att dela autentiseringsuppgifter med de nya användarna som du har lagt till.</span><span class="sxs-lookup"><span data-stu-id="e1947-127">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="e1947-128">Du kan välja att skriva ut, e-posta eller ladda ned.</span><span class="sxs-lookup"><span data-stu-id="e1947-128">You can choose to print them out, email them, or download them.</span></span>

## <a name="connect-your-domain"></a><span data-ttu-id="e1947-129">Koppla din domän</span><span class="sxs-lookup"><span data-stu-id="e1947-129">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="e1947-130">Om du väljer att använda .onmicrosoft-domänen, eller använde Azure AD Connect för att konfigurera användare, kommer du inte att se det här steget.</span><span class="sxs-lookup"><span data-stu-id="e1947-130">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="e1947-131">För att få igång tjänsten måste du uppdatera några poster hos din DNS-värd eller domänregistrator.</span><span class="sxs-lookup"><span data-stu-id="e1947-131">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="e1947-132">Installationsguiden identifierar normalt din domänregistrator och ger dig en länk till stegvisa instruktioner för att uppdatera dina NS-poster på registratorns webbplats.</span><span class="sxs-lookup"><span data-stu-id="e1947-132">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="e1947-133">Om det inte gör det, [ ändra namnservrar för att konfigurera Office 365 med valfri domänregistrator](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar).</span><span class="sxs-lookup"><span data-stu-id="e1947-133">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar).</span></span> 

    - <span data-ttu-id="e1947-134">Om du har befintliga DNS-poster, t. ex. en befintlig webbplats, men din DNS-värd är aktiverad för [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)väljer du **Lägga till poster för mig**.</span><span class="sxs-lookup"><span data-stu-id="e1947-134">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="e1947-135">På sidan **Välj onlinetjänster** accepterar du alla standardinställningar och väljer **Nästa**och väljer **Auktorisera** på DNS-värdens sida.</span><span class="sxs-lookup"><span data-stu-id="e1947-135">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="e1947-136">Om du har befintliga DNS-poster med andra DNS-värdar (inte aktiverad för domänanslutning), ska du hantera dina egna DNS-poster för att se till att de befintliga tjänsterna fortsätter att vara anslutna.</span><span class="sxs-lookup"><span data-stu-id="e1947-136">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="e1947-137">Mer information finns i [domängrunder](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics).</span><span class="sxs-lookup"><span data-stu-id="e1947-137">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

2. <span data-ttu-id="e1947-138">Följ stegen i guiden så kommer e-postmeddelanden och andra tjänster att konfigureras åt dig.</span><span class="sxs-lookup"><span data-stu-id="e1947-138">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

    <span data-ttu-id="e1947-139">När registreringsprocessen är klar dirigeras du till administrationscentret, där du kan lägga till användare och tilldela licenser.</span><span class="sxs-lookup"><span data-stu-id="e1947-139">When the signup process is complete, you'll be directed to the admin center, where you can add users, and assign licenses.</span></span> <span data-ttu-id="e1947-140">När du har slutfört den första konfigurationen kan du använda **konfigurationssidan** i administrationscentret och fortsätta att installera och konfigurera tjänsterna som medföljer prenumerationerna.</span><span class="sxs-lookup"><span data-stu-id="e1947-140">After you complete the initial setup, you can use the **Setup** page in the admin center to continue setting up and configuring the services that come with your subscriptions.</span></span>

    <span data-ttu-id="e1947-141">Mer information om installationsguiden för och administrationscentrets **konfigurationssida** finns i [Skillnaden mellan installationsguiden och sidan Konfigurera](o365-setup-wizard-and-setup-page.md).</span><span class="sxs-lookup"><span data-stu-id="e1947-141">For more information about the setup wizard and the admin center **Setup** page, see [Difference between the setup wizard and the Setup page](o365-setup-wizard-and-setup-page.md).</span></span>