---
title: Konfigurera Microsoft 365 Business Premium
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Upptäck konfigurationsstegen för Microsoft 365 Business Premium, inklusive att lägga till en domän och användare, konfigurera säkerhetsprinciper och mycket mer.
ms.openlocfilehash: e7ebe179c67077dc71ae4873b0711d0e810c701a
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044739"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a><span data-ttu-id="051f8-103">Konfigurera Microsoft 365 Business Premium i installationsguiden</span><span class="sxs-lookup"><span data-stu-id="051f8-103">Set up Microsoft 365 Business Premium in the setup wizard</span></span>

<span data-ttu-id="051f8-104">Titta på den här videon för en översikt över konfigurationen av Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="051f8-104">Watch this video for an overview of Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="051f8-105">Lägga till domän, användare och konfigurera principer</span><span class="sxs-lookup"><span data-stu-id="051f8-105">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="051f8-106">När du köper Microsoft 365 Business Premium kan du välja att använda en domän som du äger eller köpa en [under inloggningen.](sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="051f8-106">When you purchase Microsoft 365 Business Premium, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="051f8-107">Om du har köpt en ny domän när du registrerade dig kommer din domän att konfigureras, och du kan gå vidare till [Lägga till användare och tilldela licenser](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="051f8-107">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="051f8-108">Lägga till din domän för att personanpassa inloggning</span><span class="sxs-lookup"><span data-stu-id="051f8-108">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="051f8-109">Logga in på [Administrationscenter för Microsoft 365](https://admin.microsoft.com) som global administratör.</span><span class="sxs-lookup"><span data-stu-id="051f8-109">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="051f8-110">Starta guiden genom att välja **Gå till inställningar**.</span><span class="sxs-lookup"><span data-stu-id="051f8-110">Choose **Go to setup** to start the wizard.</span></span>

    ![Välj Gå till inställningar.](../media/gotosetupinadmincenter.png)

3. <span data-ttu-id="051f8-112">På sidan **Installera Office-apparna** kan du välja att installera apparna på din egen dator.</span><span class="sxs-lookup"><span data-stu-id="051f8-112">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="051f8-113">Under steget **Lägg till domän** anger du domännamnet du vill använda (t.ex. contoso.com).</span><span class="sxs-lookup"><span data-stu-id="051f8-113">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="051f8-114">Om du har köpt en domän under registreringen ser du inte steget **Lägg till en domän** här.</span><span class="sxs-lookup"><span data-stu-id="051f8-114">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="051f8-115">Gå istället till [Lägg till användare](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="051f8-115">Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    ![Skärmbild av sidan Anpassa din inloggning.](../media/adddomain.png)

    
4. <span data-ttu-id="051f8-117">Följ stegen i guiden för att skapa DNS-poster hos valfri [DNS-värd för Microsoft 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) som verifierar att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="051f8-117">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Microsoft 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="051f8-118">Om du vet vilken din domänvärd är kan du även se [Värdspecifika anvisningar](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="051f8-118">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="051f8-119">Om din värd är GoDaddy eller en annan värd som är aktiverad med [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)är processen enkel och du blir automatiskt ombedd att logga in och låta Microsoft autentisera.</span><span class="sxs-lookup"><span data-stu-id="051f8-119">If your hosting provider is GoDaddy or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![Välj Auktorisera på sidan Bekräfta Åtkomst hos GoDaddy.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="051f8-121">Lägga till användare och tilldela licenser</span><span class="sxs-lookup"><span data-stu-id="051f8-121">Add users and assign licenses</span></span>

<span data-ttu-id="051f8-122">Du kan lägga till användare i guiden eller så kan du [lägga till användare senare](add-users-m365b.md) i administratörscentret.</span><span class="sxs-lookup"><span data-stu-id="051f8-122">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="051f8-123">Om du har en lokal domänkontrollant kan du även lägga till användare med [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="051f8-123">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="051f8-124">Lägg till användare i guiden</span><span class="sxs-lookup"><span data-stu-id="051f8-124">Add users in the wizard</span></span>

<span data-ttu-id="051f8-125">Alla användare som du lägger till i guiden tilldelas automatiskt en Microsoft 365 Business Premium-licens.</span><span class="sxs-lookup"><span data-stu-id="051f8-125">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Premium license.</span></span>

![Skärmbild av sidan Lägg till nya användare i guiden](../media/addnewuserspage.png)

1. <span data-ttu-id="051f8-127">Om microsoft 365 Business Premium-prenumerationen har befintliga användare (till exempel om du använde Azure AD Connect) får du möjlighet att tilldela licenser till dem nu.</span><span class="sxs-lookup"><span data-stu-id="051f8-127">If your Microsoft 365 Business Premium subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="051f8-128">Lägg till licenser till dem också.</span><span class="sxs-lookup"><span data-stu-id="051f8-128">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="051f8-129">Efter att ha lagt till användarna får du också möjlighet att dela autentiseringsuppgifter med de nya användarna som du har lagt till.</span><span class="sxs-lookup"><span data-stu-id="051f8-129">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="051f8-130">Du kan välja att skriva ut, e-posta eller ladda ned.</span><span class="sxs-lookup"><span data-stu-id="051f8-130">You can choose to print them out, email them, or download them.</span></span>

### <a name="connect-your-domain"></a><span data-ttu-id="051f8-131">Koppla din domän</span><span class="sxs-lookup"><span data-stu-id="051f8-131">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="051f8-132">Om du väljer att använda .onmicrosoft-domänen, eller använde Azure AD Connect för att konfigurera användare, kommer du inte att se det här steget.</span><span class="sxs-lookup"><span data-stu-id="051f8-132">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="051f8-133">För att få igång tjänsten måste du uppdatera några poster hos din DNS-värd eller domänregistrator.</span><span class="sxs-lookup"><span data-stu-id="051f8-133">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="051f8-134">Installationsguiden identifierar normalt din domänregistrator och ger dig en länk till stegvisa instruktioner för att uppdatera dina NS-poster på registratorns webbplats.</span><span class="sxs-lookup"><span data-stu-id="051f8-134">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="051f8-135">Om det inte gör det kan [du ändra namnservrar för att konfigurera Microsoft 365 med valfri domänregistrator.](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar)</span><span class="sxs-lookup"><span data-stu-id="051f8-135">If it doesn't, [Change nameservers to set up Microsoft 365 with any domain registrar](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar).</span></span> 

    - <span data-ttu-id="051f8-136">Om du har befintliga DNS-poster, t. ex. en befintlig webbplats, men din DNS-värd är aktiverad för [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)väljer du **Lägga till poster för mig**.</span><span class="sxs-lookup"><span data-stu-id="051f8-136">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="051f8-137">På sidan **Välj onlinetjänster** accepterar du alla standardinställningar och väljer **Nästa** och väljer **Auktorisera** på DNS-värdens sida.</span><span class="sxs-lookup"><span data-stu-id="051f8-137">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="051f8-138">Om du har befintliga DNS-poster med andra DNS-värdar (inte aktiverad för domänanslutning), ska du hantera dina egna DNS-poster för att se till att de befintliga tjänsterna fortsätter att vara anslutna.</span><span class="sxs-lookup"><span data-stu-id="051f8-138">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="051f8-139">Mer information finns i [domängrunder](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics).</span><span class="sxs-lookup"><span data-stu-id="051f8-139">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Sidan Aktivera poster.](../media/activaterecords.png)

2. <span data-ttu-id="051f8-141">Följ stegen i guiden så kommer e-postmeddelanden och andra tjänster att konfigureras åt dig.</span><span class="sxs-lookup"><span data-stu-id="051f8-141">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-your-organization"></a><span data-ttu-id="051f8-142">Skydda din organisation</span><span class="sxs-lookup"><span data-stu-id="051f8-142">Protect your organization</span></span> 

<span data-ttu-id="051f8-143">Principerna som du konfigurerade i guiden används automatiskt i en [säkerhetsgrupp som](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) kallas *Alla användare.*</span><span class="sxs-lookup"><span data-stu-id="051f8-143">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="051f8-144">Du kan också skapa ytterligare grupper att tilldela principer till i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="051f8-144">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="051f8-145">Om du vill öka skyddet mot avancerade **cyberhot** rekommenderar vi att du accepterar standardinställningarna för att kunna söka igenom filer och länkar i [Office 365 Advance Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) i Office-appar.</span><span class="sxs-lookup"><span data-stu-id="051f8-145">On the **Increase protection from advanced cyber threats**, it is recommended that you accept the defaults to let [Office 365 Advance Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) scan files and links in Office apps.</span></span>

    ![Skärmbild av sidan Öka skydd.](../media/increasetreatprotection.png)


2. <span data-ttu-id="051f8-147">På sidan Förhindra läckage av känsliga **data** godkänner du standardinställningarna för att aktivera Office 365 Data Loss Prevention (DLP) för att spåra känsliga data i Office-program och förhindra oavsiktlig delning av dessa utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="051f8-147">On the **Prevent leaks of sensitive data** page, accept the defaults to turn on Office 365 Data Loss Prevention (DLP) to track sensitive data in Office apps and prevent the accidental sharing of these outside your organization.</span></span>

3. <span data-ttu-id="051f8-148">På sidan **Skydda data i Office** för mobila enheter, låt hantering av mobilappar vara på, expandera inställningarna och granska dem och välj sedan Skapa princip för hantering av **mobilappar.**</span><span class="sxs-lookup"><span data-stu-id="051f8-148">On the **Protect data in Office for mobile** page, leave mobile app management on, expand the settings and review them, and then select **Create mobile app management policy**.</span></span>

    ![Skärmbild av sidan Skydda data i Office för mobilen.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a><span data-ttu-id="051f8-150">Skydda Windows 10-datorer</span><span class="sxs-lookup"><span data-stu-id="051f8-150">Secure Windows 10 PCs</span></span>

<span data-ttu-id="051f8-151">Välj Installation under Inloggning och **säkerhet** på det vänstra navigeringsfältet och välj sedan Skydda **dina Windows 10-datorer.** </span><span class="sxs-lookup"><span data-stu-id="051f8-151">On the left nav, select **Setup** and then, under **Sign-in and security**, choose **Secure your Windows 10 computers**.</span></span> <span data-ttu-id="051f8-152">Välj **Visa för** att komma igång.</span><span class="sxs-lookup"><span data-stu-id="051f8-152">Choose **View** to get started.</span></span> <span data-ttu-id="051f8-153">Se [skydda dina Windows 10-datorer för](secure-win-10-pcs.md) fullständiga instruktioner.</span><span class="sxs-lookup"><span data-stu-id="051f8-153">See [secure your Windows 10 computers](secure-win-10-pcs.md) for complete instructions.</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="051f8-154">Distribuera Office 365-klientprogram</span><span class="sxs-lookup"><span data-stu-id="051f8-154">Deploy Office 365 client apps</span></span>

<span data-ttu-id="051f8-155">Om du valde att installera Office-appar automatiskt under installationen installeras apparna på Windows 10-enheter när användarna har loggat in på Azure AD från sina Windows-enheter med sina arbetsautentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="051f8-155">If you chose to automatically install Office apps during setup, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices, using their work credentials.</span></span>

<span data-ttu-id="051f8-156">Information om hur du installerar Office på mobila iOS- eller Android-enheter finns i Konfigurera [mobila enheter för Microsoft 365 Business Premium-användare.](set-up-mobile-devices.md)</span><span class="sxs-lookup"><span data-stu-id="051f8-156">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="051f8-157">Du kan också installera Office individuellt.</span><span class="sxs-lookup"><span data-stu-id="051f8-157">You can also install Office individually.</span></span> <span data-ttu-id="051f8-158">Anvisningar finns i installera Office på en PC eller [Mac.](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)</span><span class="sxs-lookup"><span data-stu-id="051f8-158">See [install Office on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>

## <a name="see-also"></a><span data-ttu-id="051f8-159">Se även</span><span class="sxs-lookup"><span data-stu-id="051f8-159">See also</span></span>

[<span data-ttu-id="051f8-160">Utbildningsvideor för Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="051f8-160">Microsoft 365 for business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
