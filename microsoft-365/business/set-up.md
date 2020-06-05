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
description: Upptäck installationsstegen för Microsoft 365 Business Premium, inklusive att lägga till en domän och användare, konfigurera säkerhetsprinciper med mera.
ms.openlocfilehash: 58dc5eb71b41f5b9316e8d68cc3fc3c8c91748b3
ms.sourcegitcommit: e6e704cbd9a50fc7db1e6a0cf5d3f8c6cbb94363
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2020
ms.locfileid: "44564913"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a><span data-ttu-id="143df-103">Konfigurera Microsoft 365 Business Premium i installationsguiden</span><span class="sxs-lookup"><span data-stu-id="143df-103">Set up Microsoft 365 Business Premium in the setup wizard</span></span>

<span data-ttu-id="143df-104">Titta på det här videoklippet om du vill ha en översikt över installationen av Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="143df-104">Watch this video for an overview of Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

<span data-ttu-id="143df-105">Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="143df-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="143df-106">Lägga till domän, användare och konfigurera principer</span><span class="sxs-lookup"><span data-stu-id="143df-106">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="143df-107">När du köper Microsoft 365 Business Premium kan du välja att använda en domän som du äger eller köpa en domän under [registreringen.](sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="143df-107">When you purchase Microsoft 365 Business Premium, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="143df-108">Om du köpte en ny domän när du registrerade dig är domänen konfigurerad och du kan flytta till [Lägg till användare och tilldela licenser](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="143df-108">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="143df-109">Lägga till din domän för att anpassa inloggningen</span><span class="sxs-lookup"><span data-stu-id="143df-109">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="143df-110">Logga in på [Microsoft 365 administrationscenter](https://admin.microsoft.com) med hjälp av dina globala administratörsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="143df-110">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="143df-111">Välj **Gå till installation för** att starta guiden.</span><span class="sxs-lookup"><span data-stu-id="143df-111">Choose **Go to setup** to start the wizard.</span></span>

    ![Välj Gå till installation.](../media/gotosetupinadmincenter.png)

3. <span data-ttu-id="143df-113">På sidan **Installera dina Office-appar** kan du också installera apparna på din egen dator.</span><span class="sxs-lookup"><span data-stu-id="143df-113">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="143df-114">I steget **Lägg till domän** anger du det domännamn som du vill använda (t.ex. contoso.com).</span><span class="sxs-lookup"><span data-stu-id="143df-114">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="143df-115">Om du köpte en domän under registreringen visas inte **Lägg till ett domänsteg** här.</span><span class="sxs-lookup"><span data-stu-id="143df-115">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="143df-116">Gå till [Lägg till användare](#add-users-and-assign-licenses) i stället.</span><span class="sxs-lookup"><span data-stu-id="143df-116">Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    ![Skärmbild av sidan Anpassa inloggningen.](../media/adddomain.png)

    
4. <span data-ttu-id="143df-118">Följ stegen i guiden för att [skapa DNS-poster hos alla DNS-värdar för Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) som verifierar att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="143df-118">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="143df-119">Om du känner din domänvärd läser du även [värdspecifika instruktioner](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="143df-119">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="143df-120">Om din värdleverantör är GoDaddy eller en annan värd aktiverad med [domänanslutning](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)är processen enkel och du blir automatiskt ombedd att logga in och låta Microsoft autentisera för din räkning.</span><span class="sxs-lookup"><span data-stu-id="143df-120">If your hosting provider is GoDaddy or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![På GoDaddy Confirm Access-sidan väljer du Auktorisera.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="143df-122">Lägga till användare och tilldela licenser</span><span class="sxs-lookup"><span data-stu-id="143df-122">Add users and assign licenses</span></span>

<span data-ttu-id="143df-123">Du kan lägga till användare i guiden, men du kan också [lägga till användare senare](add-users-m365b.md) i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="143df-123">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="143df-124">Om du har en lokal domänkontrollant kan du dessutom lägga till användare med [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="143df-124">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="143df-125">Lägga till användare i guiden</span><span class="sxs-lookup"><span data-stu-id="143df-125">Add users in the wizard</span></span>

<span data-ttu-id="143df-126">Alla användare som du lägger till i guiden tilldelas automatiskt en Microsoft 365 Business Premium-licens.</span><span class="sxs-lookup"><span data-stu-id="143df-126">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Premium license.</span></span>

![Skärmbild av sidan Lägg till nya användare i guiden](../media/addnewuserspage.png)

1. <span data-ttu-id="143df-128">Om din Microsoft 365 Business Premium-prenumeration har befintliga användare (till exempel om du använde Azure AD Connect) får du ett alternativ för att tilldela licenser till dem nu.</span><span class="sxs-lookup"><span data-stu-id="143df-128">If your Microsoft 365 Business Premium subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="143df-129">Lägg till licenser till dem också.</span><span class="sxs-lookup"><span data-stu-id="143df-129">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="143df-130">När du har lagt till användarna får du också möjlighet att dela autentiseringsuppgifter med de nya användarna som du har lagt till.</span><span class="sxs-lookup"><span data-stu-id="143df-130">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="143df-131">Du kan välja att skriva ut, e-posta eller ladda ned.</span><span class="sxs-lookup"><span data-stu-id="143df-131">You can choose to print them out, email them, or download them.</span></span>

### <a name="connect-your-domain"></a><span data-ttu-id="143df-132">Koppla din domän</span><span class="sxs-lookup"><span data-stu-id="143df-132">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="143df-133">Om du valde att använda .onmicrosoft-domänen eller använde Azure AD Connect för att konfigurera användare, visas inte det här steget.</span><span class="sxs-lookup"><span data-stu-id="143df-133">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="143df-134">För att få igång tjänsten måste du uppdatera några poster hos din DNS-värd eller domänregistrator.</span><span class="sxs-lookup"><span data-stu-id="143df-134">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="143df-135">Installationsguiden identifierar normalt din domänregistrator och ger dig en länk till stegvisa instruktioner för att uppdatera dina NS-poster på registratorns webbplats.</span><span class="sxs-lookup"><span data-stu-id="143df-135">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="143df-136">Om den inte gör det [ändrar du namnservrar för att konfigurera Office 365 med valfri domänregistrare](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar).</span><span class="sxs-lookup"><span data-stu-id="143df-136">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar).</span></span> 

    - <span data-ttu-id="143df-137">Om du har befintliga DNS-poster, till exempel en befintlig webbplats, men DNS-värden är aktiverad för [domänanslutning,](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)väljer **du Lägg till poster åt mig**.</span><span class="sxs-lookup"><span data-stu-id="143df-137">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="143df-138">På sidan **Välj dina onlinetjänster** godkänner du alla standardinställningar och väljer **Nästa**och väljer **Auktorisera** på DNS-värdens sida.</span><span class="sxs-lookup"><span data-stu-id="143df-138">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="143df-139">Om du har befintliga DNS-poster med andra DNS-värdar (inte aktiverat för domänanslutning) vill du hantera dina egna DNS-poster för att se till att de befintliga tjänsterna förblir anslutna.</span><span class="sxs-lookup"><span data-stu-id="143df-139">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="143df-140">Mer information finns i grunderna för [domänen.](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics)</span><span class="sxs-lookup"><span data-stu-id="143df-140">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Aktivera arkiven.](../media/activaterecords.png)

2. <span data-ttu-id="143df-142">Följ stegen i guiden och e-post och andra tjänster kommer att ställas in åt dig.</span><span class="sxs-lookup"><span data-stu-id="143df-142">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-your-organization"></a><span data-ttu-id="143df-143">Skydda din organisation</span><span class="sxs-lookup"><span data-stu-id="143df-143">Protect your organization</span></span> 

<span data-ttu-id="143df-144">De principer som du ställer in i guiden tillämpas automatiskt på en [säkerhetsgrupp](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) som heter *Alla användare*.</span><span class="sxs-lookup"><span data-stu-id="143df-144">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="143df-145">Du kan också skapa ytterligare grupper som du kan tilldela principer till i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="143df-145">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="143df-146">När det **gäller öka skyddet mot avancerade cyberhot**rekommenderar vi att du accepterar standardinställningarna för att låta Office [365 Advance Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) skanna filer och länkar i Office-appar.</span><span class="sxs-lookup"><span data-stu-id="143df-146">On the **Increase protection from advanced cyber threats**, it is recommended that you accept the defaults to let [Office 365 Advance Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) scan files and links in Office apps.</span></span>

    ![Skärmbild av sidan Öka skydd.](../media/increasetreatprotection.png)


2. <span data-ttu-id="143df-148">På sidan **Förhindra läckor av känsliga data** accepterar du standardinställningarna för att aktivera Office 365 Data Loss Prevention (DLP) för att spåra känsliga data i Office-appar och förhindra oavsiktlig delning av dessa utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="143df-148">On the **Prevent leaks of sensitive data** page, accept the defaults to turn on Office 365 Data Loss Prevention (DLP) to track sensitive data in Office apps and prevent the accidental sharing of these outside your organization.</span></span>

3. <span data-ttu-id="143df-149">På sidan Skydda data på sidan **Skydda data i Office för mobil** lämnar du hanteringen av mobilappar på, expanderar inställningarna och granskar dem och väljer sedan Skapa princip för hantering av **mobilappar**.</span><span class="sxs-lookup"><span data-stu-id="143df-149">On the **Protect data in Office for mobile** page, leave mobile app management on, expand the settings and review them, and then select **Create mobile app management policy**.</span></span>

    ![Skärmbild av Skydda data på sidan Skydda data för mobila enheter.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a><span data-ttu-id="143df-151">Säkra Windows 10-datorer</span><span class="sxs-lookup"><span data-stu-id="143df-151">Secure Windows 10 PCs</span></span>

<span data-ttu-id="143df-152">På den vänstra navigeringsfältet väljer du **Installationsprogrammet** och väljer sedan **Skydda dina Windows 10-datorer**under **Inloggning och säkerhet**.</span><span class="sxs-lookup"><span data-stu-id="143df-152">On the left nav, select **Setup** and then, under **Sign-in and security**, choose **Secure your Windows 10 computers**.</span></span> <span data-ttu-id="143df-153">Välj **Visa** för att komma igång.</span><span class="sxs-lookup"><span data-stu-id="143df-153">Choose **View** to get started.</span></span> <span data-ttu-id="143df-154">Se [säkra dina Windows 10-datorer](secure-win-10-pcs.md) för fullständiga instruktioner.</span><span class="sxs-lookup"><span data-stu-id="143df-154">See [secure your Windows 10 computers](secure-win-10-pcs.md) for complete instructions.</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="143df-155">Distribuera Office 365-klientappar</span><span class="sxs-lookup"><span data-stu-id="143df-155">Deploy Office 365 client apps</span></span>

<span data-ttu-id="143df-156">Om du väljer att automatiskt installera Office-appar under installationen installeras apparna på Windows 10-enheterna när användarna har loggat in på Azure AD från sina Windows-enheter med hjälp av deras arbetsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="143df-156">If you chose to automatically install Office apps during setup, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices, using their work credentials.</span></span>

<span data-ttu-id="143df-157">Om du vill installera Office på mobila iOS- eller Android-enheter finns i [Konfigurera mobila enheter för Microsoft 365 Business Premium-användare](set-up-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="143df-157">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="143df-158">Du kan också installera Office individuellt.</span><span class="sxs-lookup"><span data-stu-id="143df-158">You can also install Office individually.</span></span> <span data-ttu-id="143df-159">Instruktioner [finns i installera Office på en PC eller Mac.](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658)</span><span class="sxs-lookup"><span data-stu-id="143df-159">See [install Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>

## <a name="see-also"></a><span data-ttu-id="143df-160">Se även</span><span class="sxs-lookup"><span data-stu-id="143df-160">See also</span></span>

[<span data-ttu-id="143df-161">Utbildningsvideor för Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="143df-161">Microsoft 365 for business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
