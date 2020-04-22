---
title: Skydda dina administratörskonton
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Läs om hur du konfigurerar och skyddar administratörskontona.
ms.openlocfilehash: 2104697320308b329f9fde1b6984c15f9814f9ef
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633659"
---
# <a name="protect-your-administrator-accounts"></a><span data-ttu-id="83259-103">Skydda dina administratörskonton</span><span class="sxs-lookup"><span data-stu-id="83259-103">Protect your administrator accounts</span></span>

<span data-ttu-id="83259-104">Eftersom administratörskonton levereras med förhöjda privilegier är de värdefulla mål för hackare och cyberbrottslingar.</span><span class="sxs-lookup"><span data-stu-id="83259-104">Because admin accounts come with elevated privileges, they're valuable targets for hackers and cyber criminals.</span></span> <span data-ttu-id="83259-105">I den här artikeln beskrivs:</span><span class="sxs-lookup"><span data-stu-id="83259-105">This article describes:</span></span>

- <span data-ttu-id="83259-106">Så här konfigurerar du ytterligare ett administratörskonto för nödsituationer.</span><span class="sxs-lookup"><span data-stu-id="83259-106">How to set up an additional administrator account for emergencies.</span></span>
- <span data-ttu-id="83259-107">Hur man skyddar dessa konton.</span><span class="sxs-lookup"><span data-stu-id="83259-107">How to protect these accounts.</span></span>
 
<span data-ttu-id="83259-108">När du registrerar dig för Microsoft 365 och anger din information blir du automatiskt global administratör. En global administratör har den ultimata kontrollen över användarkonton och alla andra inställningar i Microsofts administrationscenter, men det finns många olika typer av administratörskonton med varierande grad av åtkomst.</span><span class="sxs-lookup"><span data-stu-id="83259-108">When you sign up for Microsoft 365 and enter your information, you automatically become the global admin. A global admin has the ultimate control of user accounts and all the other settings in the Microsoft admin center, but there are many different kinds of admin accounts with varying degrees of access.</span></span> <span data-ttu-id="83259-109">Mer information om de olika åtkomstnivåerna för varje typ av administratörsroll finns i [om administratörsrollen.](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="83259-109">See [about admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) for information about the different access levels for each kind of admin role.</span></span>


## <a name="create-additional-admin-accounts"></a><span data-ttu-id="83259-110">Skapa ytterligare administratörskonton</span><span class="sxs-lookup"><span data-stu-id="83259-110">Create additional admin accounts</span></span>

<span data-ttu-id="83259-111">Använd endast administratörskonton för administration.</span><span class="sxs-lookup"><span data-stu-id="83259-111">Use admin accounts only for administration.</span></span> <span data-ttu-id="83259-112">Administratörer bör ha ett separat användarkonto för regelbunden användning av Office-appar och endast använda sitt administrativa konto när det behövs för att hantera konton och enheter och när du arbetar med andra administratörsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="83259-112">Admins should have a separate user account for regular use of Office apps and only use their administrative account when necessary to manage accounts and devices, and while working on other admin functions.</span></span> <span data-ttu-id="83259-113">Det är också en bra idé att ta bort Microsoft 365-licensen från administratörskontona så att du inte behöver betala för dem.</span><span class="sxs-lookup"><span data-stu-id="83259-113">It's also a good idea to remove the Microsoft 365 license from the admin accounts so you don't have to pay for them.</span></span>

<span data-ttu-id="83259-114">Du bör konfigurera minst ett ytterligare globalt administratörskonto för att ge administratörsåtkomst till en annan betrodd medarbetare.</span><span class="sxs-lookup"><span data-stu-id="83259-114">You'll want to set up at least one additional global admin account to give admin access to another trusted employee.</span></span> <span data-ttu-id="83259-115">Du kan också skapa separata administratörskonton för användarhantering (den här rollen kallas **Administratör för användarhantering**).</span><span class="sxs-lookup"><span data-stu-id="83259-115">You can also create separate admin accounts for user management (this role is called **User management administrator**).</span></span> <span data-ttu-id="83259-116">Mer information finns i [om administratörsroller](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="83259-116">For more information, see [about admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="83259-117">Så här skapar du ytterligare administratörskonton:</span><span class="sxs-lookup"><span data-stu-id="83259-117">To create additional admin accounts:</span></span>

 1. <span data-ttu-id="83259-118">Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">administrationscentret</a> och välj sedan **Aktiva användare** \> **Active users** i den vänstra navigeringscentralen.</span><span class="sxs-lookup"><span data-stu-id="83259-118">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>

    ![Välj Användare och sedan Aktiva användare i den vänstra navigeringsfältet](../media/Activeusers.png)

2. <span data-ttu-id="83259-120">På sidan **Aktiva användare** väljer du Lägg till **en användare** högst upp på sidan och ange namnet och annan information på den **nya användarpanelen.**</span><span class="sxs-lookup"><span data-stu-id="83259-120">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
3. <span data-ttu-id="83259-121">Expandera avsnittet **Roller** och välj **Global administratör** för att ge den här användaren global administratör åtkomst.</span><span class="sxs-lookup"><span data-stu-id="83259-121">Expand the **Roles** section, and choose **Global administrator** to give this user global admin access.</span></span> <span data-ttu-id="83259-122">Du kan också välja **Anpassad administratör** och välja någon av de roller som visas.</span><span class="sxs-lookup"><span data-stu-id="83259-122">You can also choose **Customized administrator** and choose any of the roles that are displayed.</span></span>

    <span data-ttu-id="83259-123">Ange ett alternativt e-postmeddelande i textrutan **Alternativ e-postadress.**</span><span class="sxs-lookup"><span data-stu-id="83259-123">Enter an alternate email in the **Alternative email address** text box.</span></span> <span data-ttu-id="83259-124">Du kan använda den här adressen för att återställa din lösenordsinformation om du blir utelåst. För globala administratörer skickas även ett faktureringsutdrag till den här adressen.</span><span class="sxs-lookup"><span data-stu-id="83259-124">You can use this address to recover your password information if you get locked out. For global admins, a billing statement will also be sent to this address.</span></span>

    ![Välj administratörsroll](../media/adminroles.png)
    
4. <span data-ttu-id="83259-126">I avsnittet **Produktlicenser** flyttar du väljaren för **Microsoft 365 Business** till **Av** och **skapa användare utan produktlicens** till **På**.</span><span class="sxs-lookup"><span data-stu-id="83259-126">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **Off** and the **Create user without product license** to **On**.</span></span>

    ![Välj produktlicens](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a><span data-ttu-id="83259-128">Skapa ett administratörskonto för nödsituationer</span><span class="sxs-lookup"><span data-stu-id="83259-128">Create an emergency admin account</span></span>

<span data-ttu-id="83259-129">Du bör också skapa ett säkerhetskopieringskonto som inte är konfigurerat med MFA (Multifaktorautentisering) så att du inte av misstag låser ut dig själv (till exempel om du förlorar telefonen som du använder som en andra form av verifiering).</span><span class="sxs-lookup"><span data-stu-id="83259-129">You should also create a backup account that isn't set up with multi-factor authentication (MFA) so you don't accidentally lock yourself out (for example if you lose your phone that you're using as a second form of verification).</span></span> <span data-ttu-id="83259-130">Kontrollera att lösenordet för det här kontot är en fras eller minst 16 tecken långt.</span><span class="sxs-lookup"><span data-stu-id="83259-130">Make sure that the password for this account is a phrase or at least 16 characters long.</span></span> <span data-ttu-id="83259-131">Detta kallas ofta för ett "break-glass-konto".</span><span class="sxs-lookup"><span data-stu-id="83259-131">This is often referred to as a "break-glass account."</span></span>

## <a name="create-a-user-account-for-yourself"></a><span data-ttu-id="83259-132">Skapa ett användarkonto åt dig själv</span><span class="sxs-lookup"><span data-stu-id="83259-132">Create a user account for yourself</span></span>

<span data-ttu-id="83259-133">Använd ditt användarkonto för att delta i samarbete med din organisation, inklusive att kontrollera e-post.</span><span class="sxs-lookup"><span data-stu-id="83259-133">Use your user account to participate in collaboration with your organization, including checking mail.</span></span> <span data-ttu-id="83259-134">Det innebär att administratörsuppgifterna kan likna *Alice.Chavez<span></span>@Contoso.org* och ditt vanliga användarkonto kan likna *Alice<span></span>@Contoso.com*.</span><span class="sxs-lookup"><span data-stu-id="83259-134">This means your admin credentials might be similar to  *Alice.Chavez<span></span>@Contoso.org* and your regular user account might be similar to *Alice<span></span>@Contoso.com*.</span></span>

<span data-ttu-id="83259-135">Så här skapar du ett nytt användarkonto:</span><span class="sxs-lookup"><span data-stu-id="83259-135">To create a new user account:</span></span>
1. <span data-ttu-id="83259-136">Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">administrationscentret</a> och välj sedan **Aktiva användare** \> **Active users** i den vänstra navigeringscentralen.</span><span class="sxs-lookup"><span data-stu-id="83259-136">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>
2. <span data-ttu-id="83259-137">På sidan **Aktiva användare** väljer du Lägg till **en användare** högst upp på sidan och ange namnet och annan information på den **nya användarpanelen.**</span><span class="sxs-lookup"><span data-stu-id="83259-137">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
3. <span data-ttu-id="83259-138">Expandera avsnittet **Roller** och välj **Användare (ingen administrativ åtkomst)**.</span><span class="sxs-lookup"><span data-stu-id="83259-138">Expand the **Roles** section, and choose **User (no administrative access)**.</span></span>
1. <span data-ttu-id="83259-139">I avsnittet **Produktlicenser** flyttar du väljaren för **Microsoft 365 Business** till **På**.</span><span class="sxs-lookup"><span data-stu-id="83259-139">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **On**.</span></span> 

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a><span data-ttu-id="83259-140">Registrera vart och ett av dessa konton för multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="83259-140">Register each of these accounts for multi-factor authentication</span></span>


## <a name="additional-recommendations"></a><span data-ttu-id="83259-141">Ytterligare rekommendationer</span><span class="sxs-lookup"><span data-stu-id="83259-141">Additional recommendations</span></span>

- <span data-ttu-id="83259-142">Kontrollera att administratörskonton också är konfigurerade för multifaktorautentisering.</span><span class="sxs-lookup"><span data-stu-id="83259-142">Be sure that admin accounts are also set up for multi-factor authentication.</span></span> <span data-ttu-id="83259-143">Vi visar dig hur du gör detta i [Konfigurera principer för villkorlig åtkomst](m365-campaigns-conditional-access.md).</span><span class="sxs-lookup"><span data-stu-id="83259-143">We'll show you how to do this in [Configure conditional access policies](m365-campaigns-conditional-access.md).</span></span>
- <span data-ttu-id="83259-144">Innan du använder administratörskonton stänger du alla orelaterade webbläsarsessioner och appar, inklusive personliga e-postkonton.</span><span class="sxs-lookup"><span data-stu-id="83259-144">Before using admin accounts, close out all unrelated browser sessions and apps, including personal email accounts.</span></span> <span data-ttu-id="83259-145">Du kan också använda i privata eller inkognitowebbläsare.</span><span class="sxs-lookup"><span data-stu-id="83259-145">You can also use in private, or incognito browser windows.</span></span>
- <span data-ttu-id="83259-146">När du har slutfört administratörsuppgifter måste du logga ut från webbläsarsessionen.</span><span class="sxs-lookup"><span data-stu-id="83259-146">After completing admin tasks, be sure to sign out of the browser session.</span></span>
