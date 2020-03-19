---
title: Konfigurera Microsoft 365 Business
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
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Upptäck installationsstegen för Microsoft 365 Business, inklusive att lägga till en domän och användare, konfigurera säkerhetsprinciper med mera.
ms.openlocfilehash: 99994b6f1e9e817b4858aeafe4ce3ceaaf4c3c37
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42809669"
---
# <a name="set-up-microsoft-365-business-in-the-setup-wizard"></a><span data-ttu-id="103f7-103">Konfigurera Microsoft 365 Business i installationsguiden</span><span class="sxs-lookup"><span data-stu-id="103f7-103">Set up Microsoft 365 Business in the setup wizard</span></span>

<span data-ttu-id="103f7-104">Titta på det här videoklippet om du vill ha en översikt över installationen av Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="103f7-104">Watch this video for an overview of Microsoft 365 Business setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

<span data-ttu-id="103f7-105">Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="103f7-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="103f7-106">Lägga till domän, användare och konfigurera principer</span><span class="sxs-lookup"><span data-stu-id="103f7-106">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="103f7-107">[![Etikett som gör att du kan se att administrationscentret ändras och mer information finns på aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="103f7-107">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="103f7-108">När du köper Microsoft 365 Business kan du välja att använda en domän som du äger eller köpa en domän under [registreringen.](sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="103f7-108">When you purchase Microsoft 365 Business, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="103f7-109">Om du köpte en ny domän när du registrerade dig är domänen konfigurerad och du kan flytta till [Lägg till användare och tilldela licenser](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="103f7-109">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="103f7-110">Lägga till din domän för att anpassa inloggningen</span><span class="sxs-lookup"><span data-stu-id="103f7-110">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="103f7-111">Logga in på [Microsoft 365 administrationscenter](https://admin.microsoft.com) med hjälp av dina globala administratörsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="103f7-111">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="103f7-112">Välj **Gå till installation för** att starta guiden.</span><span class="sxs-lookup"><span data-stu-id="103f7-112">Choose **Go to setup** to start the wizard.</span></span>

    ![Välj Gå till installation.](../media/gotosetupinadmincenter.png)

3. <span data-ttu-id="103f7-114">På sidan **Installera dina Office-appar** kan du också installera apparna på din egen dator.</span><span class="sxs-lookup"><span data-stu-id="103f7-114">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="103f7-115">I steget **Lägg till domän** anger du det domännamn som du vill använda (t.ex. contoso.com).</span><span class="sxs-lookup"><span data-stu-id="103f7-115">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="103f7-116">Om du köpte en domän under registreringen visas inte **Lägg till ett domänsteg** här.</span><span class="sxs-lookup"><span data-stu-id="103f7-116">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="103f7-117">Gå till [Lägg till användare](#add-users-and-assign-licenses) i stället.</span><span class="sxs-lookup"><span data-stu-id="103f7-117">Go to [Add users ](#add-users-and-assign-licenses) instead.</span></span>

    ![Skärmbild av sidan Anpassa inloggningen.](../media/adddomain.png)

    
4. <span data-ttu-id="103f7-119">Följ stegen i guiden för att [skapa DNS-poster hos alla DNS-värdar för Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) som verifierar att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="103f7-119">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="103f7-120">Om du känner din domänvärd läser du även [värdspecifika instruktioner](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="103f7-120">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="103f7-121">Om din värdleverantör är GoDaddy eller en annan värd aktiverad med [domänanslutning](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)är processen enkel och du blir automatiskt ombedd att logga in och låta Microsoft autentisera för din räkning.</span><span class="sxs-lookup"><span data-stu-id="103f7-121">If your hosting provider is GoDaddy or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![På GoDaddy Confirm Access-sidan väljer du Auktorisera.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="103f7-123">Lägga till användare och tilldela licenser</span><span class="sxs-lookup"><span data-stu-id="103f7-123">Add users and assign licenses</span></span>

<span data-ttu-id="103f7-124">Du kan lägga till användare i guiden, men du kan också [lägga till användare senare](add-users-m365b.md) i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="103f7-124">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="103f7-125">Om du har en lokal domänkontrollant kan du dessutom lägga till användare med [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="103f7-125">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="103f7-126">Lägga till användare i guiden</span><span class="sxs-lookup"><span data-stu-id="103f7-126">Add users in the wizard</span></span>

<span data-ttu-id="103f7-127">Alla användare som du lägger till i guiden tilldelas automatiskt en Microsoft 365 Business-licens.</span><span class="sxs-lookup"><span data-stu-id="103f7-127">Any users you add in the wizard get automatically assigned a Microsoft 365 Business license.</span></span>

![Skärmbild av sidan Lägg till nya användare i guiden](../media/addnewuserspage.png)

1. <span data-ttu-id="103f7-129">Om din Microsoft 365 Business-prenumeration har befintliga användare (till exempel om du använde Azure AD Connect) får du ett alternativ för att tilldela licenser till dem nu.</span><span class="sxs-lookup"><span data-stu-id="103f7-129">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="103f7-130">Lägg till licenser till dem också.</span><span class="sxs-lookup"><span data-stu-id="103f7-130">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="103f7-131">När du har lagt till användarna får du också möjlighet att dela autentiseringsuppgifter med de nya användarna som du har lagt till.</span><span class="sxs-lookup"><span data-stu-id="103f7-131">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="103f7-132">Du kan välja att skriva ut, e-posta eller ladda ned.</span><span class="sxs-lookup"><span data-stu-id="103f7-132">You can choose to print them out, email them, or download them.</span></span>

### <a name="connect-your-domain"></a><span data-ttu-id="103f7-133">Koppla din domän</span><span class="sxs-lookup"><span data-stu-id="103f7-133">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="103f7-134">Om du valde att använda .onmicrosoft-domänen eller använde Azure AD Connect för att konfigurera användare, visas inte det här steget.</span><span class="sxs-lookup"><span data-stu-id="103f7-134">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="103f7-135">För att få igång tjänsten måste du uppdatera några poster hos din DNS-värd eller domänregistrator.</span><span class="sxs-lookup"><span data-stu-id="103f7-135">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="103f7-136">Installationsguiden identifierar normalt din domänregistrator och ger dig en länk till stegvisa instruktioner för att uppdatera dina NS-poster på registratorns webbplats.</span><span class="sxs-lookup"><span data-stu-id="103f7-136">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="103f7-137">Om den inte gör det [ändrar du namnservrar för att konfigurera Office 365 med valfri domänregistrare](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span><span class="sxs-lookup"><span data-stu-id="103f7-137">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span> 

    - <span data-ttu-id="103f7-138">Om du har befintliga DNS-poster, till exempel en befintlig webbplats, men DNS-värden är aktiverad för [domänanslutning,](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)väljer **du Lägg till poster åt mig**.</span><span class="sxs-lookup"><span data-stu-id="103f7-138">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="103f7-139">På sidan **Välj dina onlinetjänster** godkänner du alla standardinställningar och väljer **Nästa**och väljer **Auktorisera** på DNS-värdens sida.</span><span class="sxs-lookup"><span data-stu-id="103f7-139">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="103f7-140">Om du har befintliga DNS-poster med andra DNS-värdar (inte aktiverat för domänanslutning) vill du hantera dina egna DNS-poster för att se till att de befintliga tjänsterna förblir anslutna.</span><span class="sxs-lookup"><span data-stu-id="103f7-140">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="103f7-141">Mer information finns i grunderna för [domänen.](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics)</span><span class="sxs-lookup"><span data-stu-id="103f7-141">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Aktivera arkiven.](../media/activaterecords.png)

2. <span data-ttu-id="103f7-143">Följ stegen i guiden och e-post och andra tjänster kommer att ställas in åt dig.</span><span class="sxs-lookup"><span data-stu-id="103f7-143">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-your-organization"></a><span data-ttu-id="103f7-144">Skydda din organisation</span><span class="sxs-lookup"><span data-stu-id="103f7-144">Protect your organization</span></span> 

<span data-ttu-id="103f7-145">De principer som du ställer in i guiden tillämpas automatiskt på en [säkerhetsgrupp](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) som heter *Alla användare*.</span><span class="sxs-lookup"><span data-stu-id="103f7-145">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="103f7-146">Du kan också skapa ytterligare grupper som du kan tilldela principer till i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="103f7-146">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="103f7-147">När det **gäller öka skyddet mot avancerade cyberhot**rekommenderar vi att du accepterar standardinställningarna för att låta Office [365 Advance Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) skanna filer och länkar i Office-appar.</span><span class="sxs-lookup"><span data-stu-id="103f7-147">On the **Increase protection from advanced cyber threats**, it is recommended that you accept the defaults to let [Office 365 Advance Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) scan files and links in Office apps.</span></span>

    ![Skärmbild av sidan Öka skydd.](../media/increasetreatprotection.png)


2. <span data-ttu-id="103f7-149">På sidan **Förhindra läckor av känsliga data** accepterar du standardinställningarna för att aktivera Office 365 Data Loss Prevention (DLP) för att spåra känsliga data i Office-appar och förhindra oavsiktlig delning av dessa utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="103f7-149">On the **Prevent leaks of sensitive data** page, accept the defaults to turn on Office 365 Data Loss Prevention (DLP) to track sensitive data in Office apps and prevent the accidental sharing of these outside your organization.</span></span>

3. <span data-ttu-id="103f7-150">På sidan Skydda data på sidan **Skydda data i Office för mobil** lämnar du hanteringen av mobilappar på, expanderar inställningarna och granskar dem och väljer sedan Skapa princip för hantering av **mobilappar**.</span><span class="sxs-lookup"><span data-stu-id="103f7-150">On the **Protect data in Office for mobile** page, leave mobile app management on, expand the settings and review them, and then select **Create mobile app management policy**.</span></span>

    ![Skärmbild av Skydda data på sidan Skydda data för mobila enheter.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a><span data-ttu-id="103f7-152">Säkra Windows 10-datorer</span><span class="sxs-lookup"><span data-stu-id="103f7-152">Secure Windows 10 PCs</span></span>

<span data-ttu-id="103f7-153">På den vänstra navigeringsfältet väljer du **Installationsprogrammet** och väljer sedan **Säkra dina Windows 10-datorer**under **Sing-in och säkerhet**.</span><span class="sxs-lookup"><span data-stu-id="103f7-153">On the left nav, select **Setup** and then, under **Sing-in and security**, choose **Secure your Windows 10 computers**.</span></span> <span data-ttu-id="103f7-154">Välj **Visa** för att komma igång.</span><span class="sxs-lookup"><span data-stu-id="103f7-154">Choose **View** to get started.</span></span> <span data-ttu-id="103f7-155">Se [säkra dina Windows 10-datorer](secure-win-10-pcs.md) för fullständiga instruktioner.</span><span class="sxs-lookup"><span data-stu-id="103f7-155">See [secure your Windows 10 computers](secure-win-10-pcs.md) for complete instructions.</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="103f7-156">Distribuera Office 365-klientappar</span><span class="sxs-lookup"><span data-stu-id="103f7-156">Deploy Office 365 client apps</span></span>

<span data-ttu-id="103f7-157">Om du väljer att automatiskt installera Office-appar under installationen installeras apparna på Windows 10-enheterna när användarna har loggat in på Azure AD från sina Windows-enheter med hjälp av deras arbetsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="103f7-157">If you chose to automatically install Office apps during setup, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices, using their work credentials.</span></span>

<span data-ttu-id="103f7-158">Om du vill installera Office på mobila iOS- eller Android-enheter finns i [Konfigurera mobila enheter för Microsoft 365 Business-användare](set-up-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="103f7-158">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="103f7-159">Du kan också installera Office individuellt.</span><span class="sxs-lookup"><span data-stu-id="103f7-159">You can also install Office individually.</span></span> <span data-ttu-id="103f7-160">Instruktioner [finns i installera Office på en PC eller Mac.](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658)</span><span class="sxs-lookup"><span data-stu-id="103f7-160">See [install Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>

## <a name="see-also"></a><span data-ttu-id="103f7-161">Se även</span><span class="sxs-lookup"><span data-stu-id="103f7-161">See also</span></span>

[<span data-ttu-id="103f7-162">Utbildningsvideor för Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="103f7-162">Microsoft 365 Business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
