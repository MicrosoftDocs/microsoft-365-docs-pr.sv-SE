---
title: Konfigurera Microsoft 365 Business
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
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Lär dig hur du konfigurerar Microsoft 365 Business.
ms.openlocfilehash: ac9c8b828ff131a15bf057fa8bdc0bf56dd00987
ms.sourcegitcommit: 75b97d1ff617bc4b1b0ef9135dfe6a8842ea1b52
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/18/2019
ms.locfileid: "35772576"
---
# <a name="set-up-microsoft-365-business-in-the-setup-wizard"></a><span data-ttu-id="77796-103">Ställ in Microsoft 365 Business i installationsguiden</span><span class="sxs-lookup"><span data-stu-id="77796-103">Set up Microsoft 365 Business in the setup wizard</span></span>

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="77796-104">Lägga till din domän användare och konfigurera principer</span><span class="sxs-lookup"><span data-stu-id="77796-104">Add your domain, users, and set up policies</span></span>

![Banderoll som pekar på https://aka.ms/aboutM365preview.](media/m365admincenterchanging.png)

<span data-ttu-id="77796-106">När du köper Microsoft 365 Business har du möjlighet att använda en domän som du äger eller köpa något under den [anmälan](sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="77796-106">When you purchase Microsoft 365 Business, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="77796-107">Om du har köpt en ny domän när du har registrerat din domän är alla upp och det går att [lägga till användare](#add-users-and-assign-licenses)och tilldela licenser.</span><span class="sxs-lookup"><span data-stu-id="77796-107">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="77796-108">Lägg till din domän om du vill anpassa logga in</span><span class="sxs-lookup"><span data-stu-id="77796-108">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="77796-109">Logga in på [Microsoft 365 administratörscenter](https://admin.microsoft.com) med global administration-referenser.</span><span class="sxs-lookup"><span data-stu-id="77796-109">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="77796-110">Välj **Lägg till en domän** eller **lägga till användare** för att starta guiden.</span><span class="sxs-lookup"><span data-stu-id="77796-110">Choose **Add a domain** or **Add users** to start the wizard.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="77796-111">Om du har köpt en domän under registreringen kommer **inte se Lägg till en domän** steg här.</span><span class="sxs-lookup"><span data-stu-id="77796-111">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="77796-112">Gå till [Lägg till användare](#add-users-and-assign-licenses) i stället.</span><span class="sxs-lookup"><span data-stu-id="77796-112">Go to [Add users ](#add-users-and-assign-licenses) instead.</span></span>

    ![Välj Lägg till en domän.](media/addadomainadmincenter.png)
    
3. <span data-ttu-id="77796-114">Ange det domännamn som du vill använda (till exempel contoso.com) i guiden.</span><span class="sxs-lookup"><span data-stu-id="77796-114">In the wizard, enter the domain name you want to use (like contoso.com).</span></span>


    ![Skärmbild av Anpassa din inloggningssida.](media/personalizesignin.png)

    
4. <span data-ttu-id="77796-116">Följ stegen i guiden för att [Skapa DNS-poster på en DNS-värd leverantör för Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) som verifierar att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="77796-116">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="77796-117">Om du känner till din domän värd, se även [värd specifika instruktioner](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="77796-117">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="77796-118">Om din Internet-leverantör är GoDaddy, processen är enkel och uppmanas du automatiskt att logga in och låta Microsoft autentisera för din räkning:</span><span class="sxs-lookup"><span data-stu-id="77796-118">If your hosting provider is GoDaddy, the process is easy and you will be automatically asked to sign in and let Microsoft authenticate on your behalf:</span></span>

    ![Välj auktorisera GoDaddy Bekräfta åtkomst på sidan.](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="77796-120">Lägga till användare och tilldela licenser</span><span class="sxs-lookup"><span data-stu-id="77796-120">Add users and assign licenses</span></span>

<span data-ttu-id="77796-121">Du kan lägga till användare i guiden, men du kan också [lägga till användare senare](add-users-m365b.md) i administratörscenter.</span><span class="sxs-lookup"><span data-stu-id="77796-121">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="77796-122">Om du har en lokal domänkontrollant kan du dessutom lägga till användare med [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="77796-122">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="77796-123">Lägga till användare i guiden</span><span class="sxs-lookup"><span data-stu-id="77796-123">Add users in the wizard</span></span>

<span data-ttu-id="77796-124">Alla användare som du lägger till i guiden hämta tilldelas automatiskt en licens för Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="77796-124">Any users you add in the wizard get automatically assigned a Microsoft 365 Business license.</span></span>

![Skärmbild av sidan Lägg till nya användare i guiden](media/addnewuserspage.png)

1. <span data-ttu-id="77796-126">Om din Microsoft 365 Business-prenumeration har befintliga användare (till exempel om du har använt Azure AD Anslut), får du ett alternativ för att tilldela licenser till dem nu.</span><span class="sxs-lookup"><span data-stu-id="77796-126">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you get an option to assign licenses to them now.</span></span> <span data-ttu-id="77796-127">Lägg till licenser till dem också.</span><span class="sxs-lookup"><span data-stu-id="77796-127">Go ahead and add licenses to them as well.</span></span>

3. <span data-ttu-id="77796-128">När du har lagt till användare kan få du också möjlighet att dela referenser med nya användare som du har lagt till.</span><span class="sxs-lookup"><span data-stu-id="77796-128">After you have added the users, you will also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="77796-129">Du kan välja att skriva ut, e-posta eller ladda ned.</span><span class="sxs-lookup"><span data-stu-id="77796-129">You can choose to print them out, email them, or download them.</span></span>

4. <span data-ttu-id="77796-130">Hoppa över steget att föra över e-postmeddelanden och välj **Nästa** på sidan **Migrera e-postmeddelanden**.</span><span class="sxs-lookup"><span data-stu-id="77796-130">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 

    <span data-ttu-id="77796-131">Om du flyttar från en annan leverantör av e-post och vill kopiera data senare, kan du [migrera e-post och kontakter till Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span><span class="sxs-lookup"><span data-stu-id="77796-131">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>


### <a name="connect-your-domain"></a><span data-ttu-id="77796-132">Koppla din domän</span><span class="sxs-lookup"><span data-stu-id="77796-132">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="77796-133">Om du väljer att använda .onmicrosoft-domän eller Azure AD Anslut används för att ställa in användare, visas inte det här steget.</span><span class="sxs-lookup"><span data-stu-id="77796-133">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="77796-134">För att få igång tjänsten måste du uppdatera några poster hos din DNS-värd eller domänregistrator.</span><span class="sxs-lookup"><span data-stu-id="77796-134">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="77796-135">Installationsguiden identifierar normalt din domänregistrator och ger dig en länk till stegvisa instruktioner för att uppdatera dina NS-poster på registratorns webbplats.</span><span class="sxs-lookup"><span data-stu-id="77796-135">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="77796-136">Om den inte [Ändra nameservers att ställa in Office 365 med något domänregistrerare](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span><span class="sxs-lookup"><span data-stu-id="77796-136">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span> 

    - <span data-ttu-id="77796-137">Om du har en befintlig DNS-poster, till exempel en befintlig webbplats, kommer du vill hantera dina egna DNS-poster så att befintliga tjänster vara ansluten.</span><span class="sxs-lookup"><span data-stu-id="77796-137">If you have existing DNS records, for example an existing web site, you will want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="77796-138">Se [domän grunderna](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) för mer information.</span><span class="sxs-lookup"><span data-stu-id="77796-138">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Anslut din domän med jag ska hantera min egen DNS-poster.](media/connectyourdomainpage.png)

2. <span data-ttu-id="77796-140">Följ instruktionerna i guiden och e-post och andra tjänster kan ställas in för dig.</span><span class="sxs-lookup"><span data-stu-id="77796-140">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="set-up-security-policies-and-device-configurations"></a><span data-ttu-id="77796-141">Ställa in IPSec-principer och enhetskonfigurationer</span><span class="sxs-lookup"><span data-stu-id="77796-141">Set up security policies and device configurations</span></span> 

<span data-ttu-id="77796-142">De principer som angetts i guiden används automatiskt till en [säkerhetsgrupp](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) som kallas för *Alla användare*.</span><span class="sxs-lookup"><span data-stu-id="77796-142">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="77796-143">Du kan också skapa ytterligare grupper om du vill tilldela principer för admin Center.</span><span class="sxs-lookup"><span data-stu-id="77796-143">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="77796-144">På den **skydda ditt arbete filer på mobila enheter** alternativet är **skydda arbetsfält när enheter försvinner eller blir stulen** markerad som standard.</span><span class="sxs-lookup"><span data-stu-id="77796-144">On the **Protect your work files on mobile devices** the option **Protect work files when devices are lost or stolen** is selected by default.</span></span> <span data-ttu-id="77796-145">Har du möjlighet att aktivera **hantera hur användare kan komma åt Office-filer på mobila enheter**, och detta rekommenderas.</span><span class="sxs-lookup"><span data-stu-id="77796-145">You have an option to turn on **Manage how users access Office files on mobile devices**, and this is recommended.</span></span>

    ![Skärmbild av skydda arbetsfält på sidan mobila enheter.](media/protectworkfilesondevices.png)

     - <span data-ttu-id="77796-147">Expandera **skydda arbetsfält när enheterna är stulen eller** om du vill visa [standardvärden](protect-work-files-on-lost-or-stolen-device.md):</span><span class="sxs-lookup"><span data-stu-id="77796-147">Expand **Protect work files when devices are lost or stolen** to display the [default values](protect-work-files-on-lost-or-stolen-device.md):</span></span>

        ![Skärmbild av standardvärden för att skydda filer på enheter som förlorade.](media/protectworkfilesondevicesdefault.png)

    - <span data-ttu-id="77796-149">Välj **hantera hur användare kan komma åt Office-filer på mobila enheter** och expandera den [standardvärden](manage-user-access-on-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="77796-149">Select **Manage how users access Office files on mobile devices** and expand it to display the [default values](manage-user-access-on-mobile-devices.md).</span></span> <span data-ttu-id="77796-150">Vi rekommenderar att du accepterar standardvärden under installationen för att skapa användningsprinciper för Android, iOS och Windows 10 som gäller för alla användare.</span><span class="sxs-lookup"><span data-stu-id="77796-150">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="77796-151">Du kan skapa fler principer när installationen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="77796-151">You can create more policies after setup completes.</span></span>

        ![Skärmbild av skyddsinställningarna för mobile Office-filer.](media/useraccessonmobile.png)

2. <span data-ttu-id="77796-153">Det sista steget för att skydda data och enheter kan du ställa in principer för att säkra Windows 10 enheter.</span><span class="sxs-lookup"><span data-stu-id="77796-153">The last step on protect data and devices allows you to set up policies to secure Windows 10 devices.</span></span> <span data-ttu-id="77796-154">Dessa inställningar används automatiskt när en användare Windows 10 ansluter till din organisation.</span><span class="sxs-lookup"><span data-stu-id="77796-154">These settings are applied automatically when a user's Windows 10 connects to your organization.</span></span> <span data-ttu-id="77796-155">Du kan expandera **skydda Windows-10 enheter** för att se och ändra [standardvärdena](secure-windows-10-devices.md).</span><span class="sxs-lookup"><span data-stu-id="77796-155">You can expand **Secure Windows 10 devices** to see and modify the [default values](secure-windows-10-devices.md).</span></span>
3. <span data-ttu-id="77796-156">Du kan också välja att [automatiskt installera Office](install-office-on-windows-10-during-setup.md) på Windows 10 enheter.</span><span class="sxs-lookup"><span data-stu-id="77796-156">You can also choose to [automatically install Office](install-office-on-windows-10-during-setup.md) on Windows 10 devices.</span></span>

    ![Skärmbild av ange konfigurationssidan för Windows 10-enhet.](media/setwin10config.png)



## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="77796-158">Distribuera Office 365-klientprogram</span><span class="sxs-lookup"><span data-stu-id="77796-158">Deploy Office 365 client apps</span></span>

<span data-ttu-id="77796-159">Om du väljer att automatiskt installera Office apps i under uppsättningen upp installera apparna på Windows 10-enheter, när användaren har loggat in på Azure AD från sina Windows-enheter med sina autentiseringsuppgifter för arbete.</span><span class="sxs-lookup"><span data-stu-id="77796-159">If you chose to automatically install Office apps in during the set up, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices with their work credentials.</span></span>
<span data-ttu-id="77796-160">Om du vill installera Office på mobila iOS- eller Android-enheter finns i [Konfigurera mobila enheter för Microsoft 365 företagsanvändare](set-up-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="77796-160">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="77796-161">Du kan också installera Office individuellt.</span><span class="sxs-lookup"><span data-stu-id="77796-161">You can also install Office individually.</span></span> <span data-ttu-id="77796-162">Se [installera Office på en PC eller Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) för instruktioner.</span><span class="sxs-lookup"><span data-stu-id="77796-162">See [install Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>
