---
title: Konfigurera Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
ms.openlocfilehash: e635b828609fc47cd8b92bb179a25bcc43cb0a1a
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660908"
---
# <a name="set-up-microsoft-365-business"></a><span data-ttu-id="a0b26-103">Konfigurera Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="a0b26-103">Set up Microsoft 365 Business</span></span>

<span data-ttu-id="a0b26-104">Innan du börjar [Hämta Microsoft 365 Business](get-microsoft-365-business.md) anmälan information finns.</span><span class="sxs-lookup"><span data-stu-id="a0b26-104">Before you get started, see [Get Microsoft 365 Business](get-microsoft-365-business.md) for sign-up details.</span></span>

<span data-ttu-id="a0b26-105">Titta på en [kort video om hur du konfigurerar Microsoft 365 Business](https://support.office.com/article/38003e30-9d10-44cf-b596-f1b5f662bfa1) med uppsättningen upp guiden och du inte har en lokal Active Directory</span><span class="sxs-lookup"><span data-stu-id="a0b26-105">Watch a [short video on how to set up Microsoft 365 Business](https://support.office.com/article/38003e30-9d10-44cf-b596-f1b5f662bfa1) by using the set up wizard, and when you don't have an on-premises Active Directory</span></span>
  

## <a name="overview"></a><span data-ttu-id="a0b26-106">Översikt</span><span class="sxs-lookup"><span data-stu-id="a0b26-106">Overview</span></span>

<span data-ttu-id="a0b26-107">Kan du göra de flesta av stegen i guiden, men andra alternativ finns.</span><span class="sxs-lookup"><span data-stu-id="a0b26-107">Most of the set up steps can be done in the setup wizard, but the other options are also listed.</span></span>

1. <span data-ttu-id="a0b26-108">[Lägg till din domän](#add-your-domain-to-personalize-sign-in) (om du har köpt din domän under [registrera](sign-up.md)görs redan det här steget.)</span><span class="sxs-lookup"><span data-stu-id="a0b26-108">[Add your domain](#add-your-domain-to-personalize-sign-in) (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>
2. <span data-ttu-id="a0b26-109">Lägg till användare.</span><span class="sxs-lookup"><span data-stu-id="a0b26-109">Add users.</span></span> <span data-ttu-id="a0b26-110">Du kan göra detta på något av tre sätt:</span><span class="sxs-lookup"><span data-stu-id="a0b26-110">You can do this in any of the three ways:</span></span>
    - <span data-ttu-id="a0b26-111">I [installationsguiden](#add-users-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="a0b26-111">In the [setup wizard](#add-users-in-the-wizard).</span></span>
    - <span data-ttu-id="a0b26-112">Använda katalogsynkronisering för att [lägga till användare med hjälp av Azure AD Connect](#add-users-by-using-azure-ad-connect) om du har en lokal Active directory.</span><span class="sxs-lookup"><span data-stu-id="a0b26-112">Use directory synchronization to [add users by using Azure AD Connect](#add-users-by-using-azure-ad-connect) if you have an on-premises Active directory.</span></span>
    - <span data-ttu-id="a0b26-113">Du kan också [lägga till användare senare](add-users-m365b.md) i administratörscenter.</span><span class="sxs-lookup"><span data-stu-id="a0b26-113">You can also [add users later](add-users-m365b.md) in the admin center.</span></span>
3. <span data-ttu-id="a0b26-114">Ställa in IPSec-principer och konfigurera enheter.</span><span class="sxs-lookup"><span data-stu-id="a0b26-114">Set up security policies and configure devices.</span></span> <span data-ttu-id="a0b26-115">Du kan göra detta på något av tre sätt:</span><span class="sxs-lookup"><span data-stu-id="a0b26-115">You can do this in any of the three ways:</span></span>
    - <span data-ttu-id="a0b26-116">I [installationsguiden](#set-up-policies-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="a0b26-116">In the [setup wizard](#set-up-policies-in-the-wizard).</span></span>  
    - <span data-ttu-id="a0b26-117">I [administratörscenter](#modify-or-add-policies-in-the-admin-center).</span><span class="sxs-lookup"><span data-stu-id="a0b26-117">In the [admin center](#modify-or-add-policies-in-the-admin-center).</span></span>
    - <span data-ttu-id="a0b26-118">I [Intune administratörscenter](https://docs.microsoft.com/intune/what-is-device-management).</span><span class="sxs-lookup"><span data-stu-id="a0b26-118">In the [Intune admin center](https://docs.microsoft.com/intune/what-is-device-management).</span></span>
4. <span data-ttu-id="a0b26-119">Ställ in och hantera Windows 10 enheter.</span><span class="sxs-lookup"><span data-stu-id="a0b26-119">Set up and manage Windows 10 devices.</span></span>

    <span data-ttu-id="a0b26-120">När du ansluter en enhet med WIndows 10 till Azure AD tillämpas alla principer den.</span><span class="sxs-lookup"><span data-stu-id="a0b26-120">When you join a WIndows 10 device to Azure AD, all the policies get applied to it.</span></span>
    - <span data-ttu-id="a0b26-121">Ställa in Windows 10 enhetskonfigurationer i [installationsguiden](#set-up-policies-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="a0b26-121">Set up Windows 10 device configurations in the [setup wizard](#set-up-policies-in-the-wizard).</span></span>
    - <span data-ttu-id="a0b26-122">Ansluta till en [ny enhet med Windows 10](set-up-windows-devices.md#for-a-brand-new-or-newly-upgraded-windows-10-pro-device) till Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a0b26-122">Join a [new Windows 10 device](set-up-windows-devices.md#for-a-brand-new-or-newly-upgraded-windows-10-pro-device) to Azure AD.</span></span>
    - <span data-ttu-id="a0b26-123">Ansluta till en [befintlig Windows 10-enhet](set-up-windows-devices.md#for-a-device-already-set-up-and-running-windows-10-pro) till Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a0b26-123">Join an [existing Windows 10 device](set-up-windows-devices.md#for-a-device-already-set-up-and-running-windows-10-pro) to Azure AD.</span></span>
1. <span data-ttu-id="a0b26-124">Installera Office 365 Business.</span><span class="sxs-lookup"><span data-stu-id="a0b26-124">Install Office 365 Business.</span></span>
    - <span data-ttu-id="a0b26-125">Du kan automatiskt installera Office i Windows-enheter med hjälp av [installationsguiden](#set-up-policies-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="a0b26-125">You can automatically install Office in the Windows devices by using the [setup wizard](#set-up-policies-in-the-wizard).</span></span>
    - <span data-ttu-id="a0b26-126">Automatiskt [installera Office](auto-install-or-uninstall-office.md) admin Center.</span><span class="sxs-lookup"><span data-stu-id="a0b26-126">Automatically [install Office](auto-install-or-uninstall-office.md) from the admin center.</span></span>
    - <span data-ttu-id="a0b26-127">Låt användarna [installera Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) för Windows och enheter.</span><span class="sxs-lookup"><span data-stu-id="a0b26-127">Let users [install Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
1. <span data-ttu-id="a0b26-128">Ställ in ytterligare säkerhet.</span><span class="sxs-lookup"><span data-stu-id="a0b26-128">Set up additional security.</span></span>
    - <span data-ttu-id="a0b26-129">Guiden lägger till principer för att säkra dina enheter, men du kan också dra nytta av [ytterligare](#additional-security-settings) säkerhetsfunktioner till hjälper till att säkra data, konton och e-post.</span><span class="sxs-lookup"><span data-stu-id="a0b26-129">The setup wizard adds policies to secure your devices, but you can also take advantage of [additional security](#additional-security-settings) capabilities to helps secure your data, accounts, and emails.</span></span> 

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="a0b26-130">Lägg till din domän, användare och konfigurera principer</span><span class="sxs-lookup"><span data-stu-id="a0b26-130">Add your domain, users and set up policies</span></span>

![Banderoll som pekar på https://aka.ms/aboutM365preview.](media/m365admincenterchanging.png)

<span data-ttu-id="a0b26-132">När du köper Microsoft 365 Business har du möjlighet att använda en domän som du äger eller köpa något under den [anmälan](sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="a0b26-132">When you purchase Microsoft 365 Business, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="a0b26-133">Om du har köpt en ny domän när du har registrerat din domän är alla upp och det går att [lägga till användare](#add-users-and-assign-licenses)och tilldela licenser.</span><span class="sxs-lookup"><span data-stu-id="a0b26-133">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="a0b26-134">Lägg till din domän om du vill anpassa logga in</span><span class="sxs-lookup"><span data-stu-id="a0b26-134">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="a0b26-135">Logga in på [Microsoft 365 administratörscenter](https://admin.microsoft.com) med global administration-referenser.</span><span class="sxs-lookup"><span data-stu-id="a0b26-135">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="a0b26-136">Välj **Lägg till en domän** för att starta guiden.</span><span class="sxs-lookup"><span data-stu-id="a0b26-136">Choose **Add a domain** to start the wizard.</span></span>

    ![Välj Lägg till en domän.](media/addadomainadmincenter.png)
    
3. <span data-ttu-id="a0b26-138">Ange det domännamn som du vill använda (till exempel contoso.com) i guiden.</span><span class="sxs-lookup"><span data-stu-id="a0b26-138">In the wizard, enter the domain name you want to use (like contoso.com).</span></span>


    ![Skärmbild av Anpassa din inloggningssida.](media/personalizesignin.png)

    
4. <span data-ttu-id="a0b26-140">Följ stegen i guiden för att [Skapa DNS-poster på en DNS-värd leverantör för Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) som verifierar att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="a0b26-140">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="a0b26-141">Om du känner till din domän värd, se även [värd specifika instruktioner](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="a0b26-141">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="a0b26-142">Om din Internet-leverantör är GoDaddy, processen är enkel och uppmanas du automatiskt att logga in och låta Microsoft autentisera för din räkning:</span><span class="sxs-lookup"><span data-stu-id="a0b26-142">If your hosting provider is GoDaddy, the process is easy and you will be automatically asked to sign in and let Microsoft authenticate on your behalf:</span></span>

    ![Välj auktorisera GoDaddy Bekräfta åtkomst på sidan.](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="a0b26-144">Lägga till användare och tilldela licenser</span><span class="sxs-lookup"><span data-stu-id="a0b26-144">Add users and assign licenses</span></span>

<span data-ttu-id="a0b26-145">Du kan lägga till användare i guiden, men du kan också [lägga till användare senare](add-users-m365b.md) i administratörscenter.</span><span class="sxs-lookup"><span data-stu-id="a0b26-145">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="a0b26-146">Om du har en lokal domänkontrollant kan du dessutom lägga till användare med [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="a0b26-146">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="a0b26-147">Lägga till användare i guiden</span><span class="sxs-lookup"><span data-stu-id="a0b26-147">Add users in the wizard</span></span>

<span data-ttu-id="a0b26-148">Alla användare som du lägger till i guiden hämta tilldelas automatiskt en licens för Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="a0b26-148">Any users you add in the wizard get automatically assigned a Microsoft 365 Business license.</span></span>
<span data-ttu-id="a0b26-149">Om du har en lokal domänkontrollant och använder Active Directory, kan du se [hur du ddd användare med Azure AD Connect](#add-users-by-using-azure-ad-connect).</span><span class="sxs-lookup"><span data-stu-id="a0b26-149">If you have a local domain controller, and are using Active Directory, see [how to ddd users by using Azure AD Connect](#add-users-by-using-azure-ad-connect).</span></span>

![Skärmbild av sidan Lägg till nya användare i guiden](media/addnewuserspage.png)

1. <span data-ttu-id="a0b26-p106">Om ditt Microsoft 365 Business-abonnemang har befintliga användare (till exempel om du använde Azure AD Connect), får du möjlighet att tilldela licenser till dem nu. Lägg till licenser till dem också.</span><span class="sxs-lookup"><span data-stu-id="a0b26-p106">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you will get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>

3. <span data-ttu-id="a0b26-153">När du har lagt till användare kan få du också möjlighet att dela referenser med nya användare som du har lagt till.</span><span class="sxs-lookup"><span data-stu-id="a0b26-153">After you have added the users, you will also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="a0b26-154">Du kan välja att skriva ut, e-posta eller ladda ned.</span><span class="sxs-lookup"><span data-stu-id="a0b26-154">You can choose to print them out, email them, or download them.</span></span>

4. <span data-ttu-id="a0b26-155">Hoppa över steget att föra över e-postmeddelanden och välj **Nästa** på sidan **Migrera e-postmeddelanden**.</span><span class="sxs-lookup"><span data-stu-id="a0b26-155">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 

    <span data-ttu-id="a0b26-156">Om du flyttar från en annan leverantör av e-post och vill kopiera data senare, kan du [migrera e-post och kontakter till Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span><span class="sxs-lookup"><span data-stu-id="a0b26-156">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>

#### <a name="add-users-by-using-azure-ad-connect"></a><span data-ttu-id="a0b26-157">Lägga till användare med hjälp av Azure AD Anslut</span><span class="sxs-lookup"><span data-stu-id="a0b26-157">Add users by using Azure AD Connect</span></span>

 <span data-ttu-id="a0b26-158">Om du har en lokal domänkontrollant med Active Directory kan synkronisera du användarna med Microsoft 365 Business [Azure AD Anslut](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="a0b26-158">If you have a local domain controller with Active Directory, you synchronize your users with Microsoft 365 Business by using [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span> <span data-ttu-id="a0b26-159">Komplettera detta innan du startar guiden.</span><span class="sxs-lookup"><span data-stu-id="a0b26-159">Complete this before you start the setup wizard.</span></span> <span data-ttu-id="a0b26-160">Du kan hämta det i administratörscenter:</span><span class="sxs-lookup"><span data-stu-id="a0b26-160">You can download it in the admin center:</span></span>

- <span data-ttu-id="a0b26-161">Gå till **användare** \> **aktiva användare**, Välj punkter högst upp på sidan och välj sedan **katalogsynkronisering** hämta Azure AD Anslut.</span><span class="sxs-lookup"><span data-stu-id="a0b26-161">Go to **Users** \> **Active users**, select the ellipses on the top of the page and then select **Directory synchronization** to download Azure AD Connect.</span></span>

    ![Välj punkter > Directory snchronization på sidan aktiv användare.](media/setupdirsync.png)

    > [!IMPORTANT]
    > <span data-ttu-id="a0b26-163">Om du skapar användare på det här sättet har du fortfarande tilldela licenser till dem i administratörscenter.</span><span class="sxs-lookup"><span data-stu-id="a0b26-163">If you create users this way, you will still have to assign licenses to them in the admin center.</span></span>

##### <a name="continue-to-access-domain-joined-apps-and-devices"></a><span data-ttu-id="a0b26-164">Fortsätta använda domänanslutna appar och enheter</span><span class="sxs-lookup"><span data-stu-id="a0b26-164">Continue to access domain-joined apps and devices</span></span>

<span data-ttu-id="a0b26-165">Om du vill fortsätta använda domänanslutna appar och enheter läser du följande artiklar för två olika sätt att aktivera som:</span><span class="sxs-lookup"><span data-stu-id="a0b26-165">If you want to continue to access domain-joined apps and devices, read the following articles for two different way of enabling that:</span></span>
  
- [<span data-ttu-id="a0b26-166">Aktivera domänanslutna Windows 10-enheter för hantering i Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="a0b26-166">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>](manage-windows-devices.md)
    - <span data-ttu-id="a0b26-167">Detta är det rekommenderade sättet.</span><span class="sxs-lookup"><span data-stu-id="a0b26-167">This is the recommended way.</span></span>

- [<span data-ttu-id="a0b26-168">Åtkomst på lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="a0b26-168">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>](access-resources.md)

### <a name="connect-your-domain"></a><span data-ttu-id="a0b26-169">Koppla din domän</span><span class="sxs-lookup"><span data-stu-id="a0b26-169">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="a0b26-170">Om du väljer att använda .onmicrosoft-domän eller Azure AD Anslut används för att ställa in användare, visas inte det här steget.</span><span class="sxs-lookup"><span data-stu-id="a0b26-170">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="a0b26-171">För att få igång tjänsten måste du uppdatera några poster hos din DNS-värd eller domänregistrator.</span><span class="sxs-lookup"><span data-stu-id="a0b26-171">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="a0b26-172">Installationsguiden identifierar normalt din domänregistrator och ger dig en länk till stegvisa instruktioner för att uppdatera dina NS-poster på registratorns webbplats.</span><span class="sxs-lookup"><span data-stu-id="a0b26-172">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="a0b26-173">Om den inte [Ändra nameservers att ställa in Office 365 med något domänregistrerare](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span><span class="sxs-lookup"><span data-stu-id="a0b26-173">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span> 

    - <span data-ttu-id="a0b26-174">Om du har en befintlig DNS-poster, till exempel en befintlig webbplats, kommer du vill hantera dina egna DNS-poster så att befintliga tjänster vara ansluten.</span><span class="sxs-lookup"><span data-stu-id="a0b26-174">If you have existing DNS records, for example an existing web site, you will want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="a0b26-175">Se [domän grunderna](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) för mer information.</span><span class="sxs-lookup"><span data-stu-id="a0b26-175">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Anslut din domän med jag ska hantera min egen DNS-poster.](media/connectyourdomainpage.png)

2. <span data-ttu-id="a0b26-177">Följ instruktionerna i guiden och e-post och andra tjänster kan ställas in för dig.</span><span class="sxs-lookup"><span data-stu-id="a0b26-177">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="set-up-security-policies-and-device-configurations"></a><span data-ttu-id="a0b26-178">Ställa in IPSec-principer och enhetskonfigurationer</span><span class="sxs-lookup"><span data-stu-id="a0b26-178">Set up security policies and device configurations</span></span> 

<span data-ttu-id="a0b26-179">Dessa principer gäller alla användare som du ger en licens till, eller en grupp av användare om du vill tilldela olika principer för en användare.</span><span class="sxs-lookup"><span data-stu-id="a0b26-179">These policies apply to every user you give a license to, or to a group of users if you decide to assign different policies to a set of users.</span></span>

#### <a name="set-up-policies-in-the-wizard"></a><span data-ttu-id="a0b26-180">Ställ in policyer i guiden</span><span class="sxs-lookup"><span data-stu-id="a0b26-180">Set up policies in the wizard</span></span>

<span data-ttu-id="a0b26-181">De principer som angetts i guiden används automatiskt till en [säkerhetsgrupp](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) som kallas för *Alla användare*.</span><span class="sxs-lookup"><span data-stu-id="a0b26-181">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span>

1. <span data-ttu-id="a0b26-182">På den **skydda ditt arbete filer på mobila enheter** alternativet är **skydda arbetsfält när enheter försvinner eller blir stulen** markerad som standard.</span><span class="sxs-lookup"><span data-stu-id="a0b26-182">On the **Protect your work files on mobile devices** the option **Protect work files when devices are lost or stolen** is selected by default.</span></span> <span data-ttu-id="a0b26-183">Har du möjlighet att aktivera **hantera hur användare kan komma åt Office-filer på mobila enheter**, och detta rekommenderas.</span><span class="sxs-lookup"><span data-stu-id="a0b26-183">You have an option to turn on **Manage how users access Office files on mobile devices**, and this is recommended.</span></span>

    ![Skärmbild av skydda arbetsfält på sidan mobila enheter.](media/protectworkfilesondevices.png)

     - <span data-ttu-id="a0b26-185">Om du expanderar **skydda arbetsfält när enheter försvinner eller blir stulen**är det förvalda [standardvärden](protect-work-files-on-lost-or-stolen-device.md) :</span><span class="sxs-lookup"><span data-stu-id="a0b26-185">If you expand **Protect work files when devices are lost or stolen**, the [default values](protect-work-files-on-lost-or-stolen-device.md) are pre-selected:</span></span>

        ![Skärmbild av standardvärden för att skydda filer på enheter som förlorade.](media/protectworkfilesondevicesdefault.png)

    - <span data-ttu-id="a0b26-187">Om du väljer att **hantera hur användare kan komma åt Office-filer på mobila enheter** och expandera den visas [standardvärden](manage-user-access-on-mobile-devices.md) .</span><span class="sxs-lookup"><span data-stu-id="a0b26-187">If you select **Manage how users access Office files on mobile devices** and expand it, the [default values](manage-user-access-on-mobile-devices.md) are shown.</span></span> <span data-ttu-id="a0b26-188">Vi rekommenderar att du godkänner standardvärdena vid installationen för att skapa programprinciper för alla användare i Android, iOS och Windows 10.</span><span class="sxs-lookup"><span data-stu-id="a0b26-188">We recommend you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="a0b26-189">Du kan skapa fler principer när installationen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="a0b26-189">You can create more policies after setup completes.</span></span>

        ![Skärmbild av skyddsinställningarna för mobile Office-filer.](media/useraccessonmobile.png)

2. <span data-ttu-id="a0b26-191">Det sista steget för att skydda data och enheter kan du ställa in principer för att säkra Windows 10 enheter.</span><span class="sxs-lookup"><span data-stu-id="a0b26-191">The last step on protect data and devices allows you to set up policies to secure Windows 10 devices.</span></span> <span data-ttu-id="a0b26-192">Dessa inställningar används automatiskt när en användare Windows 10 ansluter till din organisation.</span><span class="sxs-lookup"><span data-stu-id="a0b26-192">These settings are applied automatically when a user's Windows 10 connects to your organization.</span></span> <span data-ttu-id="a0b26-193">Du kan expandera **skydda Windows-10 enheter** för att se och ändra [standardvärdena](secure-windows-10-devices.md).</span><span class="sxs-lookup"><span data-stu-id="a0b26-193">You can expand **Secure Windows 10 devices** to see and modify the [default values](secure-windows-10-devices.md).</span></span>
3. <span data-ttu-id="a0b26-194">Du kan också välja att [automatiskt installera Office](install-office-on-windows-10-during-setup.md) på Windows 10 enheter.</span><span class="sxs-lookup"><span data-stu-id="a0b26-194">You can also choose to [automatically install Office](install-office-on-windows-10-during-setup.md) on Windows 10 devices.</span></span>

    ![Skärmbild av ange konfigurationssidan för Windows 10-enhet.](media/setwin10config.png)

#### <a name="modify-or-add-policies-in-the-admin-center"></a><span data-ttu-id="a0b26-196">Ändra eller lägga till principer i administratörscenter</span><span class="sxs-lookup"><span data-stu-id="a0b26-196">Modify or add policies in the admin center</span></span>

<span data-ttu-id="a0b26-197">Se [Hantera Microsoft 365 Business](manage.md) för länkar till avsnitt om hur du visar och ändrar enhet och app skydd principer och ta bort data från eller återställa användarenhet.</span><span class="sxs-lookup"><span data-stu-id="a0b26-197">See [manage Microsoft 365 Business](manage.md) for links to topics on how to view and modify device and app protection polices, and how to remove data from, or reset user devices.</span></span>

## <a name="deploy-and-manage-windows-10"></a><span data-ttu-id="a0b26-198">Distribuera och hantera Windows 10</span><span class="sxs-lookup"><span data-stu-id="a0b26-198">Deploy and manage Windows 10</span></span>
<span data-ttu-id="a0b26-199">Se [ställa in Windows-enheter för Microsoft 365 företagsanvändare](set-up-windows-devices.md) manuellt ansluta till Azure AD, antingen under installationen för nya datorer eller genom att ändra profil logga in för befintliga datorer.</span><span class="sxs-lookup"><span data-stu-id="a0b26-199">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) to manually connect to Azure AD, either during setup for new computers, or by changing sign-in profile for existing computers.</span></span> 

### <a name="use-autopilot-to-set-up-new-devices"></a><span data-ttu-id="a0b26-200">Använda Autopilot för att skapa nya enheter</span><span class="sxs-lookup"><span data-stu-id="a0b26-200">Use Autopilot to set up new devices</span></span>

<span data-ttu-id="a0b26-201">Du kan använda [Windows Autopilot](add-autopilot-devices-and-profile.md) före automatiskt konfigurera **nya** Windows 10-enheter för en användare, men kan det vara enklare att få en [partner](https://www.microsoft.com/solution-providers/search) som kan göra detta åt dig.</span><span class="sxs-lookup"><span data-stu-id="a0b26-201">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="a0b26-202">Du kan också gå till [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) och be en expert moln teknik skapa nya enheter du köper du.</span><span class="sxs-lookup"><span data-stu-id="a0b26-202">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) and ask a cloud technology expert set up new devices you purchase for you.</span></span>

### <a name="access-on-premises-resources"></a><span data-ttu-id="a0b26-203">Komma åt lokala resurser</span><span class="sxs-lookup"><span data-stu-id="a0b26-203">Access on-premises resources</span></span>

<span data-ttu-id="a0b26-204">Om organisationen använder Windows Server Active Directory på lokaler, kan du ställa in Microsoft 365 Business att skydda din Windows 10-enheter, men fortfarande åtkomst till lokala resurser som kräver autentisering med lokala.</span><span class="sxs-lookup"><span data-stu-id="a0b26-204">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="a0b26-205">Följ stegen i [Aktivera domänanslutna Windows 10-enheter som ska hanteras av Microsoft 365 Business](manage-windows-devices.md) att ställa in.</span><span class="sxs-lookup"><span data-stu-id="a0b26-205">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="a0b26-206">Detta är den bästa metoden och enheter i det här tillståndet kallas Hybrid Azure AD anslutna enheter.</span><span class="sxs-lookup"><span data-stu-id="a0b26-206">This is the preferred method and devices in this state are called Hybrid Azure AD joined devices.</span></span>

<span data-ttu-id="a0b26-207">Om ditt företag har en lokal Active Directory som innehåller vissa lokala resurser (till exempel filresurser och skrivare), du kan ge din Azure AD-anslutna enheter åtkomst till dessa resurser genom att följa instruktionerna här: [Access lokal resurser från en Azure AD-ansluten enhet i Microsoft 365 Business](access-resources.md).</span><span class="sxs-lookup"><span data-stu-id="a0b26-207">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers) , you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business](access-resources.md).</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="a0b26-208">Distribuera Office 365-klientprogram</span><span class="sxs-lookup"><span data-stu-id="a0b26-208">Deploy Office 365 client apps</span></span>

<span data-ttu-id="a0b26-209">Om du väljer att automatiskt installera Office apps i under uppsättningen upp installera apparna på Windows 10-enheter, när användaren har loggat in på Azure AD från sina Windows-enheter med sina autentiseringsuppgifter för arbete.</span><span class="sxs-lookup"><span data-stu-id="a0b26-209">If you chose to automatically install Office apps in during the set up, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices with their work credentials.</span></span>
<span data-ttu-id="a0b26-210">Om du vill installera Office på mobila iOS- eller Android-enheter finns i [Konfigurera mobila enheter för Microsoft 365 företagsanvändare](set-up-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="a0b26-210">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="a0b26-211">Du kan också installera Office individuellt.</span><span class="sxs-lookup"><span data-stu-id="a0b26-211">You can also install Office individually.</span></span> <span data-ttu-id="a0b26-212">Se [installera Office på en PC eller Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc471665) för instruktioner.</span><span class="sxs-lookup"><span data-stu-id="a0b26-212">See [install Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc471665) for instructions.</span></span>

## <a name="additional-security-settings"></a><span data-ttu-id="a0b26-213">Ytterligare säkerhetsinställningar</span><span class="sxs-lookup"><span data-stu-id="a0b26-213">Additional security settings</span></span>

<span data-ttu-id="a0b26-214">Förutom säkerhet och regelefterlevnad inställning i guiden kan du också ange följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="a0b26-214">In addition to the security and compliance setting in the setup wizard, you can also set up the following additional settings:</span></span>
  
- <span data-ttu-id="a0b26-215">**Skydd mot skadlig programvara för e-post**</span><span class="sxs-lookup"><span data-stu-id="a0b26-215">**Email malware protection**</span></span>
- <span data-ttu-id="a0b26-216">**Avancerade hot skydd (ATP) säkra bifogade filer**</span><span class="sxs-lookup"><span data-stu-id="a0b26-216">**Advanced Threat Protection (ATP) Safe Attachments**</span></span>
- <span data-ttu-id="a0b26-217">**ATP-Safe länkar**</span><span class="sxs-lookup"><span data-stu-id="a0b26-217">**ATP Safe Links**</span></span>
- <span data-ttu-id="a0b26-218">**STORGATAN anti-phishing**</span><span class="sxs-lookup"><span data-stu-id="a0b26-218">**APT anti-phishing**</span></span>
- <span data-ttu-id="a0b26-219">**Exchange Online - arkivering**</span><span class="sxs-lookup"><span data-stu-id="a0b26-219">**Exchange Online Archiving**</span></span>
- <span data-ttu-id="a0b26-220">**Förhindra dataförlust (DLP)**</span><span class="sxs-lookup"><span data-stu-id="a0b26-220">**Data loss prevention (DLP)**</span></span>
- <span data-ttu-id="a0b26-221">**Azure informationsskydd** (Plan 1)</span><span class="sxs-lookup"><span data-stu-id="a0b26-221">**Azure Information Protection** (Plan 1)</span></span>
- <span data-ttu-id="a0b26-222">**Intune portal tillgänglighet**</span><span class="sxs-lookup"><span data-stu-id="a0b26-222">**Intune portal availability**</span></span>

<span data-ttu-id="a0b26-223">Att komma igång finns i [ställa in avancerade IPSec-principer](set-up-advanced-security.md).</span><span class="sxs-lookup"><span data-stu-id="a0b26-223">To get started see, [set up advanced security policies](set-up-advanced-security.md).</span></span>

<span data-ttu-id="a0b26-224">Se även [top 10 sätt att skydda verksamheten Microsoft 365](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) för en översikt av bästa säkerhetspraxis.</span><span class="sxs-lookup"><span data-stu-id="a0b26-224">See also [top 10 ways to secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a roadmap of best security practices.</span></span>