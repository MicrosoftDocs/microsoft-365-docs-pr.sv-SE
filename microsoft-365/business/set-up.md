---
title: Konfigurera Microsoft 365 Business Premium
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- TRN_SMB
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Upptäck konfigurationsstegen för Microsoft 365 Business Premium, inklusive att lägga till en domän och användare, konfigurera säkerhetsprinciper med mera.
ms.openlocfilehash: 3e15f16db2a233d2e11d444600398102b075932d
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624398"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a><span data-ttu-id="b9e0d-103">Konfigurera Microsoft 365 Business Premium i installationsguiden</span><span class="sxs-lookup"><span data-stu-id="b9e0d-103">Set up Microsoft 365 Business Premium in the setup wizard</span></span>

## <a name="watch-overview-of-microsoft-365-setup"></a><span data-ttu-id="b9e0d-104">Titta: Översikt över Microsoft 365 konfiguration</span><span class="sxs-lookup"><span data-stu-id="b9e0d-104">Watch: Overview of Microsoft 365 setup</span></span>

<span data-ttu-id="b9e0d-105">Titta på den här videon för en översikt över Microsoft 365 Business Premium konfiguration.</span><span class="sxs-lookup"><span data-stu-id="b9e0d-105">Watch this video for an overview of Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="b9e0d-106">Lägga till domän, användare och konfigurera principer</span><span class="sxs-lookup"><span data-stu-id="b9e0d-106">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="b9e0d-107">När du köper Microsoft 365 Business Premium domän kan du välja att använda en domän som du äger eller köpa en i [samband med köpet.](sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="b9e0d-107">When you purchase Microsoft 365 Business Premium, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="b9e0d-108">Om du har köpt en ny domän när du registrerade dig kommer din domän att konfigureras, och du kan gå vidare till [Lägga till användare och tilldela licenser](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="b9e0d-108">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="b9e0d-109">Lägga till din domän för att personanpassa inloggning</span><span class="sxs-lookup"><span data-stu-id="b9e0d-109">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="b9e0d-110">Logga in på [Administrationscenter för Microsoft 365](https://admin.microsoft.com) som global administratör.</span><span class="sxs-lookup"><span data-stu-id="b9e0d-110">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="b9e0d-111">Starta guiden genom att välja **Gå till inställningar**.</span><span class="sxs-lookup"><span data-stu-id="b9e0d-111">Choose **Go to setup** to start the wizard.</span></span>

    ![Välj Gå till inställningar.](../media/gotosetupinadmincenter.png)

3. <span data-ttu-id="b9e0d-113">På sidan **Installera Office-apparna** kan du välja att installera apparna på din egen dator.</span><span class="sxs-lookup"><span data-stu-id="b9e0d-113">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="b9e0d-114">Under steget **Lägg till domän** anger du domännamnet du vill använda (t.ex. contoso.com).</span><span class="sxs-lookup"><span data-stu-id="b9e0d-114">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="b9e0d-p101">Om du har köpt en domän under registreringen ser du inte steget **Lägg till en domän** här. Gå i stället till [Lägg till användare](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="b9e0d-p101">If you purchased a domain during the sign-up, you will not see **Add a domain** step here. Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    ![Skärmbild av sidan Anpassa din inloggning.](../media/adddomain.png)

    
4. <span data-ttu-id="b9e0d-118">Följ stegen i guiden för att [Skapa DNS-poster hos en DNS-värd](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) för Microsoft 365 som verifierar att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="b9e0d-118">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Microsoft 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="b9e0d-119">Om du vet vilken din domänvärd är kan du även se [Värdspecifika anvisningar](/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="b9e0d-119">If you know your domain host, see also the [host specific instructions](/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="b9e0d-120">Om din värd är GoDaddy eller en annan värd som är aktiverad med [Domain Connect](/office365/admin/get-help-with-domains/domain-connect)är processen enkel och du blir automatiskt ombedd att logga in och låta Microsoft autentisera.</span><span class="sxs-lookup"><span data-stu-id="b9e0d-120">If your hosting provider is GoDaddy or another host enabled with [domain connect](/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![Välj Auktorisera på sidan Bekräfta Åtkomst hos GoDaddy.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="b9e0d-122">Lägga till användare och tilldela licenser</span><span class="sxs-lookup"><span data-stu-id="b9e0d-122">Add users and assign licenses</span></span>

<span data-ttu-id="b9e0d-123">Du kan lägga till användare i guiden eller så kan du [lägga till användare senare](../admin/add-users/add-users.md) i administratörscentret.</span><span class="sxs-lookup"><span data-stu-id="b9e0d-123">You can add users in the wizard, but you can also [add users later](../admin/add-users/add-users.md) in the admin center.</span></span> <span data-ttu-id="b9e0d-124">Om du har en lokal domänkontrollant kan du även lägga till användare med [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="b9e0d-124">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="b9e0d-125">Lägg till användare i guiden</span><span class="sxs-lookup"><span data-stu-id="b9e0d-125">Add users in the wizard</span></span>

<span data-ttu-id="b9e0d-126">Alla användare som du lägger till i guiden tilldelas automatiskt en Microsoft 365 Business Premium licens.</span><span class="sxs-lookup"><span data-stu-id="b9e0d-126">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Premium license.</span></span>

![Skärmbild av sidan Lägg till nya användare i guiden](../media/addnewuserspage.png)

1. <span data-ttu-id="b9e0d-128">Om din Microsoft 365 Business Premium-prenumeration har befintliga användare (till exempel om du använde Azure AD Anslut) får du möjlighet att tilldela licenser till dem nu.</span><span class="sxs-lookup"><span data-stu-id="b9e0d-128">If your Microsoft 365 Business Premium subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="b9e0d-129">Lägg till licenser till dem också.</span><span class="sxs-lookup"><span data-stu-id="b9e0d-129">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="b9e0d-p105">När du har lagt till användarna får du även ett alternativ för att dela autentiseringsuppgifter med dem. Du kan välja att skriva ut, skicka via e-post eller ladda ned dem.</span><span class="sxs-lookup"><span data-stu-id="b9e0d-p105">After you've added the users, you'll also get an option to share credentials with the new users you added. You can choose to print them out, email them, or download them.</span></span>

### <a name="connect-your-domain"></a><span data-ttu-id="b9e0d-132">Koppla din domän</span><span class="sxs-lookup"><span data-stu-id="b9e0d-132">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="b9e0d-133">Om du väljer att använda .onmicrosoft-domänen, eller använde Azure AD Connect för att konfigurera användare, kommer du inte att se det här steget.</span><span class="sxs-lookup"><span data-stu-id="b9e0d-133">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="b9e0d-134">För att få igång tjänsten måste du uppdatera några poster hos din DNS-värd eller domänregistrator.</span><span class="sxs-lookup"><span data-stu-id="b9e0d-134">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="b9e0d-135">Installationsguiden identifierar normalt din domänregistrator och ger dig en länk till stegvisa instruktioner för att uppdatera dina NS-poster på registratorns webbplats.</span><span class="sxs-lookup"><span data-stu-id="b9e0d-135">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="b9e0d-136">Om det inte fungerar kan [du ändra namnservrar för att konfigurera Microsoft 365 med valfri domänregistrator](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="b9e0d-136">If it doesn't, [Change nameservers to set up Microsoft 365 with any domain registrar](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md).</span></span> 

    - <span data-ttu-id="b9e0d-137">Om du har befintliga DNS-poster, t. ex. en befintlig webbplats, men din DNS-värd är aktiverad för [Domain Connect](/office365/admin/get-help-with-domains/domain-connect)väljer du **Lägga till poster för mig**.</span><span class="sxs-lookup"><span data-stu-id="b9e0d-137">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="b9e0d-138">På sidan **Välj onlinetjänster** accepterar du alla standardinställningar och väljer **Nästa** och väljer **Auktorisera** på DNS-värdens sida.</span><span class="sxs-lookup"><span data-stu-id="b9e0d-138">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="b9e0d-p108">Om du har befintliga DNS-poster med andra DNS-värdar (inte aktiverad för domänanslutning), ska du hantera dina egna DNS-poster för att se till att de befintliga tjänsterna fortsätter att vara anslutna. Mer information finns i [grundläggande information för domän](/office365/admin/get-help-with-domains/dns-basics).</span><span class="sxs-lookup"><span data-stu-id="b9e0d-p108">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected. See [domain basics](/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Sidan Aktivera poster.](../media/activaterecords.png)

2. <span data-ttu-id="b9e0d-142">Följ stegen i guiden så kommer e-postmeddelanden och andra tjänster att konfigureras åt dig.</span><span class="sxs-lookup"><span data-stu-id="b9e0d-142">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-your-organization"></a><span data-ttu-id="b9e0d-143">Skydda din organisation</span><span class="sxs-lookup"><span data-stu-id="b9e0d-143">Protect your organization</span></span> 

<span data-ttu-id="b9e0d-144">Principerna som du skapar i guiden tillämpas automatiskt på säkerhetsgruppen [Alla](/office365/admin/create-groups/compare-groups#security-groups) *användare.*</span><span class="sxs-lookup"><span data-stu-id="b9e0d-144">The policies you set up in the wizard are applied automatically to a [Security group](/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="b9e0d-145">Du kan också skapa ytterligare grupper att tilldela principer till i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="b9e0d-145">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="b9e0d-146">Om du vill öka skyddet mot avancerade **cyberhot** rekommenderar vi att du accepterar standardinställningarna för att [låta Office 365 Advance Threat Protection](../security/office-365-security/defender-for-office-365.md) söka igenom filer och länkar i Office appar.</span><span class="sxs-lookup"><span data-stu-id="b9e0d-146">On the **Increase protection from advanced cyber threats**, it is recommended that you accept the defaults to let [Office 365 Advance Threat Protection](../security/office-365-security/defender-for-office-365.md) scan files and links in Office apps.</span></span>

    ![Skärmbild av sidan Öka skydd.](../media/increasetreatprotection.png)


2. <span data-ttu-id="b9e0d-148">På sidan Förhindra läckage av känsliga **data** godkänner du standardinställningarna för att aktivera Office 365 Skydd mot dataförlust (DLP) för att spåra känsliga data i Office-appar och förhindra oavsiktlig delning av dessa utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="b9e0d-148">On the **Prevent leaks of sensitive data** page, accept the defaults to turn on Office 365 Data Loss Prevention (DLP) to track sensitive data in Office apps and prevent the accidental sharing of these outside your organization.</span></span>

3. <span data-ttu-id="b9e0d-149">På sidan **Skydda data i Office** för mobila enheter lämnar du hantering av mobilappar på, expanderar inställningarna och granskar dem och väljer sedan Skapa policy för hantering av **mobilappar.**</span><span class="sxs-lookup"><span data-stu-id="b9e0d-149">On the **Protect data in Office for mobile** page, leave mobile app management on, expand the settings and review them, and then select **Create mobile app management policy**.</span></span>

    ![Skärmbild av Skydda data i Office för mobil.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a><span data-ttu-id="b9e0d-151">Skydda Windows 10-datorer</span><span class="sxs-lookup"><span data-stu-id="b9e0d-151">Secure Windows 10 PCs</span></span>

<span data-ttu-id="b9e0d-152">Välj Konfigurera i det vänstra **navigeringsfältet** och välj sedan Skydda dina **e-Windows 10** under **Inloggning och säkerhet.**</span><span class="sxs-lookup"><span data-stu-id="b9e0d-152">On the left nav, select **Setup** and then, under **Sign-in and security**, choose **Secure your Windows 10 computers**.</span></span> <span data-ttu-id="b9e0d-153">Kom **igång genom** att välja Visa.</span><span class="sxs-lookup"><span data-stu-id="b9e0d-153">Choose **View** to get started.</span></span> <span data-ttu-id="b9e0d-154">Se [Skydda Windows 10 för](secure-win-10-pcs.md) fullständiga instruktioner.</span><span class="sxs-lookup"><span data-stu-id="b9e0d-154">See [secure your Windows 10 computers](secure-win-10-pcs.md) for complete instructions.</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="b9e0d-155">Distribuera Office 365-klientprogram</span><span class="sxs-lookup"><span data-stu-id="b9e0d-155">Deploy Office 365 client apps</span></span>

<span data-ttu-id="b9e0d-156">Om du väljer att installera Office-appar automatiskt under installationen installeras apparna på Windows 10-enheterna när användarna har loggat in i Azure AD från sina Windows-enheter med sina arbetsautentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="b9e0d-156">If you chose to automatically install Office apps during setup, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices, using their work credentials.</span></span>

<span data-ttu-id="b9e0d-157">Information om Office för mobila iOS- och Android-enheter finns i [Konfigurera mobila enheter för Microsoft 365 Business Premium användare.](set-up-mobile-devices.md)</span><span class="sxs-lookup"><span data-stu-id="b9e0d-157">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="b9e0d-158">Du kan också installera Office individuellt.</span><span class="sxs-lookup"><span data-stu-id="b9e0d-158">You can also install Office individually.</span></span> <span data-ttu-id="b9e0d-159">Anvisningar finns Office installera på en PC eller [Mac.](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)</span><span class="sxs-lookup"><span data-stu-id="b9e0d-159">See [install Office on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>

## <a name="related-content"></a><span data-ttu-id="b9e0d-160">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="b9e0d-160">Related content</span></span>

<span data-ttu-id="b9e0d-161">[Microsoft 365 om utbildningsvideor för företag](../business-video/index.yml) (länksida)</span><span class="sxs-lookup"><span data-stu-id="b9e0d-161">[Microsoft 365 for business training videos](../business-video/index.yml) (link page)</span></span>
