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
description: Läs om hur du konfigurerar Microsoft 365 Business.
ms.openlocfilehash: dbd2e740c85f52d3f43e6cd3d6ce45c478a9b1a9
ms.sourcegitcommit: 7690c8bfdea6e6d245cfa7c5b09b913b092cde0a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2019
ms.locfileid: "37121327"
---
# <a name="set-up-microsoft-365-business-in-the-setup-wizard"></a><span data-ttu-id="05784-103">Konfigurera Microsoft 365 Business i installationsguiden</span><span class="sxs-lookup"><span data-stu-id="05784-103">Set up Microsoft 365 Business in the setup wizard</span></span>

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="05784-104">Lägg till din domän, användare och Ställ in policyer</span><span class="sxs-lookup"><span data-stu-id="05784-104">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="05784-105">[![Etiketten så att du vet att Admin Center förändras och du kan hitta mer information på aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="05784-105">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="05784-106">När du köper Microsoft 365 Business har du möjlighet att använda en domän som du äger eller köpa en under [registreringen](sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="05784-106">When you purchase Microsoft 365 Business, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="05784-107">Om du har köpt en ny domän när du registrerade dig, är din domän alla inställd och du kan flytta för att [lägga till användare och tilldela licenser](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="05784-107">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="05784-108">Lägg till din domän för att anpassa inloggningen</span><span class="sxs-lookup"><span data-stu-id="05784-108">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="05784-109">Logga in på [Microsoft 365 administratörscenter](https://admin.microsoft.com) med hjälp av autentiseringsuppgifterna för global administratör.</span><span class="sxs-lookup"><span data-stu-id="05784-109">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="05784-110">Välj **Lägg till en domän** eller **Lägg till användare** för att starta guiden.</span><span class="sxs-lookup"><span data-stu-id="05784-110">Choose **Add a domain** or **Add users** to start the wizard.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="05784-111">Om du har köpt en domän under registreringen kommer du inte att se **Lägg till ett domän** steg här.</span><span class="sxs-lookup"><span data-stu-id="05784-111">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="05784-112">Gå till [Lägg till användare](#add-users-and-assign-licenses) i stället.</span><span class="sxs-lookup"><span data-stu-id="05784-112">Go to [Add users ](#add-users-and-assign-licenses) instead.</span></span>

    ![Välj Lägg till en domän.](media/addadomainadmincenter.png)
    
3. <span data-ttu-id="05784-114">I guiden anger du det domännamn du vill använda (som contoso.com).</span><span class="sxs-lookup"><span data-stu-id="05784-114">In the wizard, enter the domain name you want to use (like contoso.com).</span></span>


    ![Skärmbild av anpassa din inloggningssida.](media/personalizesignin.png)

    
4. <span data-ttu-id="05784-116">Följ stegen i guiden för att [Skapa DNS-poster hos valfri DNS-Värdleverantör för Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) som verifierar att du äger domänen.</span><span class="sxs-lookup"><span data-stu-id="05784-116">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="05784-117">Om du känner till din domänvärd, se även [värdspecifika instruktioner](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="05784-117">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="05784-118">Om din webbhotellsleverantör är GoDaddy, eller en annan värd som är aktiverad med [domänanslutning](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), är processen enkel och du kommer automatiskt att bli ombedd att logga in och låta Microsoft autentisera för din räkning:</span><span class="sxs-lookup"><span data-stu-id="05784-118">If your hosting provider is GoDaddy, or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect),the process is easy and you will be automatically asked to sign in and let Microsoft authenticate on your behalf:</span></span>

    ![På GoDaddy bekräfta åtkomstsidan, Välj Auktorisera.](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="05784-120">Lägga till användare och tilldela licenser</span><span class="sxs-lookup"><span data-stu-id="05784-120">Add users and assign licenses</span></span>

<span data-ttu-id="05784-121">Du kan lägga till användare i guiden, men du kan också [lägga till användare senare](add-users-m365b.md) i administratörscenter.</span><span class="sxs-lookup"><span data-stu-id="05784-121">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="05784-122">Om du har en lokal domänkontrollant kan du dessutom lägga till användare med [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="05784-122">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="05784-123">Lägga till användare i guiden</span><span class="sxs-lookup"><span data-stu-id="05784-123">Add users in the wizard</span></span>

<span data-ttu-id="05784-124">Alla användare som du lägger till i guiden tilldelas automatiskt en Microsoft 365 Business-licens.</span><span class="sxs-lookup"><span data-stu-id="05784-124">Any users you add in the wizard get automatically assigned a Microsoft 365 Business license.</span></span>

![Skärmbild av sidan Lägg till nya användare i guiden](media/addnewuserspage.png)

1. <span data-ttu-id="05784-126">Om din Microsoft 365 Business-prenumeration har befintliga användare (till exempel om du har använt Azure AD Connect), får du ett alternativ för att tilldela licenser till dem nu.</span><span class="sxs-lookup"><span data-stu-id="05784-126">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you get an option to assign licenses to them now.</span></span> <span data-ttu-id="05784-127">Lägg till licenser till dem också.</span><span class="sxs-lookup"><span data-stu-id="05784-127">Go ahead and add licenses to them as well.</span></span>

3. <span data-ttu-id="05784-128">När du har lagt till användarna får du också ett alternativ för att dela autentiseringsuppgifter med de nya användare som du har lagt till.</span><span class="sxs-lookup"><span data-stu-id="05784-128">After you have added the users, you will also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="05784-129">Du kan välja att skriva ut, e-posta eller ladda ned.</span><span class="sxs-lookup"><span data-stu-id="05784-129">You can choose to print them out, email them, or download them.</span></span>

4. <span data-ttu-id="05784-130">Hoppa över steget att föra över e-postmeddelanden och välj **Nästa** på sidan **Migrera e-postmeddelanden**.</span><span class="sxs-lookup"><span data-stu-id="05784-130">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 

    <span data-ttu-id="05784-131">Om du flyttar från en annan e-postleverantör och vill kopiera dina data senare kan du [migrera e-post och kontakter till Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span><span class="sxs-lookup"><span data-stu-id="05784-131">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>


### <a name="connect-your-domain"></a><span data-ttu-id="05784-132">Koppla din domän</span><span class="sxs-lookup"><span data-stu-id="05784-132">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="05784-133">Om du väljer att använda den. onmicrosoft domän eller används Azure AD Connect för att ställa in användare, kommer du inte att se det här steget.</span><span class="sxs-lookup"><span data-stu-id="05784-133">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="05784-134">För att få igång tjänsten måste du uppdatera några poster hos din DNS-värd eller domänregistrator.</span><span class="sxs-lookup"><span data-stu-id="05784-134">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="05784-135">Installationsguiden identifierar normalt din domänregistrator och ger dig en länk till stegvisa instruktioner för att uppdatera dina NS-poster på registratorns webbplats.</span><span class="sxs-lookup"><span data-stu-id="05784-135">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="05784-136">Om den inte gör det [ändrar du namnservrar till konfigurera Office 365 med alla domänregistratorn](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span><span class="sxs-lookup"><span data-stu-id="05784-136">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span> 

    - <span data-ttu-id="05784-137">Om du har befintliga DNS-poster, till exempel en befintlig webbplats, men DNS-värden har aktiverats för [domänanslutning](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), väljer du **Lägg till poster åt mig**.</span><span class="sxs-lookup"><span data-stu-id="05784-137">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> 
    - <span data-ttu-id="05784-138">Om du har befintliga DNS-poster med andra DNS-värdar (inte aktiverat för domänanslutning), kommer du att vilja hantera dina egna DNS-poster för att se till att de befintliga tjänsterna förblir anslutna.</span><span class="sxs-lookup"><span data-stu-id="05784-138">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you will want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="05784-139">Mer information finns i [grunderna om domäner](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) .</span><span class="sxs-lookup"><span data-stu-id="05784-139">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Anslut din domän sida med jag ska hantera mina egna DNS-poster.](media/connectyourdomainpage.png)

2. <span data-ttu-id="05784-141">Följ stegen i guiden och e-post och andra tjänster kommer att ställas in för dig.</span><span class="sxs-lookup"><span data-stu-id="05784-141">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="set-up-security-policies-and-device-configurations"></a><span data-ttu-id="05784-142">Ställ in säkerhetsprinciper och enhetskonfigurationer</span><span class="sxs-lookup"><span data-stu-id="05784-142">Set up security policies and device configurations</span></span> 

<span data-ttu-id="05784-143">De principer som du ställer in i guiden tillämpas automatiskt på en [säkerhetsgrupp](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) som kallas *alla användare*.</span><span class="sxs-lookup"><span data-stu-id="05784-143">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="05784-144">Du kan också skapa ytterligare grupper för att tilldela principer till i administratörscenter.</span><span class="sxs-lookup"><span data-stu-id="05784-144">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="05784-145">På **skydda dina arbetsfiler på mobila enheter** alternativet **skydda arbetsfiler när enheter förloras eller stjäls** är markerad som standard.</span><span class="sxs-lookup"><span data-stu-id="05784-145">On the **Protect your work files on mobile devices** the option **Protect work files when devices are lost or stolen** is selected by default.</span></span> <span data-ttu-id="05784-146">Du har möjlighet att aktivera **hantera hur användare får åtkomst till Office-filer på mobila enheter**, och detta rekommenderas.</span><span class="sxs-lookup"><span data-stu-id="05784-146">You have an option to turn on **Manage how users access Office files on mobile devices**, and this is recommended.</span></span>

    ![Skärmbild av skydda jobbfiler på sidan mobila enheter.](media/protectworkfilesondevices.png)

     - <span data-ttu-id="05784-148">Expandera **skydda arbetsfiler när enheter förloras eller stjäls** för att visa [standardvärdena](protect-work-files-on-lost-or-stolen-device.md):</span><span class="sxs-lookup"><span data-stu-id="05784-148">Expand **Protect work files when devices are lost or stolen** to display the [default values](protect-work-files-on-lost-or-stolen-device.md):</span></span>

        ![Skärmbild av standardvärden för att skydda filer på borttappade enheter.](media/protectworkfilesondevicesdefault.png)

    - <span data-ttu-id="05784-150">Välj **hantera hur användare öppnar Office-filer på mobila enheter** och expandera den för att visa [standardvärdena](manage-user-access-on-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="05784-150">Select **Manage how users access Office files on mobile devices** and expand it to display the [default values](manage-user-access-on-mobile-devices.md).</span></span> <span data-ttu-id="05784-151">Vi rekommenderar att du accepterar standardvärdena under installationen för att skapa användningsprinciper för Android, iOS och Windows 10 som gäller för alla användare.</span><span class="sxs-lookup"><span data-stu-id="05784-151">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="05784-152">Du kan skapa fler principer när installationen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="05784-152">You can create more policies after setup completes.</span></span>

        ![Skärmbild av skyddsinställningar för Office-filer på mobilen.](media/useraccessonmobile.png)

2. <span data-ttu-id="05784-154">Det sista steget på skydda data och enheter kan du ställa in principer för att skydda Windows 10-enheter.</span><span class="sxs-lookup"><span data-stu-id="05784-154">The last step on protect data and devices allows you to set up policies to secure Windows 10 devices.</span></span> <span data-ttu-id="05784-155">Dessa inställningar tillämpas automatiskt när en användares Windows 10 ansluts till din organisation.</span><span class="sxs-lookup"><span data-stu-id="05784-155">These settings are applied automatically when a user's Windows 10 connects to your organization.</span></span> <span data-ttu-id="05784-156">Du kan expandera **säkra Windows 10-enheter** för att visa och ändra [standardvärdena](secure-windows-10-devices.md).</span><span class="sxs-lookup"><span data-stu-id="05784-156">You can expand **Secure Windows 10 devices** to see and modify the [default values](secure-windows-10-devices.md).</span></span>
3. <span data-ttu-id="05784-157">Du kan också välja att [automatiskt installera Office](install-office-on-windows-10-during-setup.md) på Windows 10-enheter.</span><span class="sxs-lookup"><span data-stu-id="05784-157">You can also choose to [automatically install Office](install-office-on-windows-10-during-setup.md) on Windows 10 devices.</span></span>

    ![Skärmbild av Ställ in konfigurationssidan för Windows 10-enhet.](media/setwin10config.png)



## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="05784-159">Distribuera Office 365-klientappar</span><span class="sxs-lookup"><span data-stu-id="05784-159">Deploy Office 365 client apps</span></span>

<span data-ttu-id="05784-160">Om du väljer att automatiskt installera Office-appar i under installationen installeras apparna på Windows 10-enheterna när användarna har loggat in på Azure AD från sina Windows-enheter med sina arbetsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="05784-160">If you chose to automatically install Office apps in during the set up, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices with their work credentials.</span></span>
<span data-ttu-id="05784-161">Om du vill installera Office på mobila iOS-eller Android-enheter läser [du konfigurera mobila enheter för Microsoft 365 företagsanvändare](set-up-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="05784-161">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="05784-162">Du kan också installera Office individuellt.</span><span class="sxs-lookup"><span data-stu-id="05784-162">You can also install Office individually.</span></span> <span data-ttu-id="05784-163">Mer information finns i [installera Office på en PC eller Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) .</span><span class="sxs-lookup"><span data-stu-id="05784-163">See [install Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>
