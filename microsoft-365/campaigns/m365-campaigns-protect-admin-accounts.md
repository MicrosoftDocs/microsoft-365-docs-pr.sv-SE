---
title: Skydda dina administratörskonton
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Lär dig att konfigurera och skydda dina administratörskonton.
ms.openlocfilehash: 0d687407fad1cec5da49dbc33ffeb84366f1c309
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398247"
---
# <a name="protect-your-administrator-accounts"></a><span data-ttu-id="1149e-103">Skydda dina administratörskonton</span><span class="sxs-lookup"><span data-stu-id="1149e-103">Protect your administrator accounts</span></span>

<span data-ttu-id="1149e-104">Eftersom administratörskonton har förhöjd behörighet är de värdefulla mål för hackare och cyberbrottsligheter.</span><span class="sxs-lookup"><span data-stu-id="1149e-104">Because admin accounts come with elevated privileges, they're valuable targets for hackers and cyber criminals.</span></span> <span data-ttu-id="1149e-105">I den här artikeln beskrivs:</span><span class="sxs-lookup"><span data-stu-id="1149e-105">This article describes:</span></span>

- <span data-ttu-id="1149e-106">Konfigurera ytterligare ett administratörskonto för nödsituationer.</span><span class="sxs-lookup"><span data-stu-id="1149e-106">How to set up an additional administrator account for emergencies.</span></span>
- <span data-ttu-id="1149e-107">Hur du skyddar dessa konton.</span><span class="sxs-lookup"><span data-stu-id="1149e-107">How to protect these accounts.</span></span>

<span data-ttu-id="1149e-108">När du registrerar dig för Microsoft 365 och anger din information blir du automatiskt global administratör. En global administratör har den slutgiltiga kontrollen över användarkonton och alla andra inställningar i administrationscentret för Microsoft, men det finns många olika typer av administratörskonton med varierande åtkomstgrad.</span><span class="sxs-lookup"><span data-stu-id="1149e-108">When you sign up for Microsoft 365 and enter your information, you automatically become the Global admin. A Global admin has the ultimate control of user accounts and all the other settings in the Microsoft admin center, but there are many different kinds of admin accounts with varying degrees of access.</span></span> <span data-ttu-id="1149e-109">Mer [information om de](/office365/admin/add-users/about-admin-roles) olika åtkomstnivåerna för varje typ av administratörsroll finns i om administratörsroller.</span><span class="sxs-lookup"><span data-stu-id="1149e-109">See [about admin roles](/office365/admin/add-users/about-admin-roles) for information about the different access levels for each kind of admin role.</span></span>

## <a name="create-additional-admin-accounts"></a><span data-ttu-id="1149e-110">Skapa ytterligare administratörskonton</span><span class="sxs-lookup"><span data-stu-id="1149e-110">Create additional admin accounts</span></span>

<span data-ttu-id="1149e-111">Använd endast administratörskonton för administration.</span><span class="sxs-lookup"><span data-stu-id="1149e-111">Use admin accounts only for administration.</span></span> <span data-ttu-id="1149e-112">Administratörer bör ha ett separat användarkonto för normal användning av Office-appar och bara använda sitt administratörskonto när det behövs för att hantera konton och enheter och medan de arbetar med andra administratörsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="1149e-112">Admins should have a separate user account for regular use of Office apps and only use their administrative account when necessary to manage accounts and devices, and while working on other admin functions.</span></span> <span data-ttu-id="1149e-113">Det är också en bra idé att ta Microsoft 365 licens från administratörskontona så att du inte behöver betala för dem.</span><span class="sxs-lookup"><span data-stu-id="1149e-113">It's also a good idea to remove the Microsoft 365 license from the admin accounts so you don't have to pay for them.</span></span>

<span data-ttu-id="1149e-114">Du bör konfigurera minst ett globalt administratörskonto för att ge administratörsåtkomst till en annan betrodd anställd.</span><span class="sxs-lookup"><span data-stu-id="1149e-114">You'll want to set up at least one additional Global admin account to give admin access to another trusted employee.</span></span> <span data-ttu-id="1149e-115">Du kan också skapa separata administratörskonton för användarhantering (den här rollen kallas **användarhanteringsadministratör).**</span><span class="sxs-lookup"><span data-stu-id="1149e-115">You can also create separate admin accounts for user management (this role is called **User management administrator**).</span></span> <span data-ttu-id="1149e-116">Mer information finns i om [administratörsroller](/office365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="1149e-116">For more information, see [about admin roles](/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="1149e-117">Så här skapar du ytterligare administratörskonton:</span><span class="sxs-lookup"><span data-stu-id="1149e-117">To create additional admin accounts:</span></span>

 1. <span data-ttu-id="1149e-118">Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">administrationscentret och</a> välj sedan **Användare aktiva** användare \> **i** det vänstra navigeringsfältet.</span><span class="sxs-lookup"><span data-stu-id="1149e-118">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>

    ![Välj Användare och sedan Aktiva användare i det vänstra navigeringsfältet](../media/Activeusers.png)

 2. <span data-ttu-id="1149e-120">På sidan **Aktiva** användare väljer du **Lägg** till en användare  längst upp på sidan. På panelen Ny användare anger du namn och annan information.</span><span class="sxs-lookup"><span data-stu-id="1149e-120">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
 3. <span data-ttu-id="1149e-121">Expandera avsnittet **Roller** och välj Global **administratör för att ge** användaren global administratörsåtkomst.</span><span class="sxs-lookup"><span data-stu-id="1149e-121">Expand the **Roles** section, and choose **Global administrator** to give this user global admin access.</span></span> <span data-ttu-id="1149e-122">Du kan också **välja Anpassad administratör** och välja någon av rollerna som visas.</span><span class="sxs-lookup"><span data-stu-id="1149e-122">You can also choose **Customized administrator** and choose any of the roles that are displayed.</span></span>

    <span data-ttu-id="1149e-123">Ange ett alternativt e-postmeddelande i **textrutan Alternativ e-postadress.**</span><span class="sxs-lookup"><span data-stu-id="1149e-123">Enter an alternate email in the **Alternative email address** text box.</span></span> <span data-ttu-id="1149e-124">Du kan använda den här adressen för att återställa lösenordsinformationen om du blir utelåst. För globala administratörer skickas även ett faktureringsutdrag till den här adressen.</span><span class="sxs-lookup"><span data-stu-id="1149e-124">You can use this address to recover your password information if you get locked out. For Global admins, a billing statement will also be sent to this address.</span></span>

    ![Välj administratörsroll](../media/adminroles.png)

 4. <span data-ttu-id="1149e-126">I avsnittet **Produktlicenser** flyttar du väljaren för **att Microsoft 365 Business** **till Av** och Skapa användare utan **produktlicens** till **På.**</span><span class="sxs-lookup"><span data-stu-id="1149e-126">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **Off** and the **Create user without product license** to **On**.</span></span>

    ![Välj produktlicensen](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a><span data-ttu-id="1149e-128">Skapa ett nödsituationsadministratörskonto</span><span class="sxs-lookup"><span data-stu-id="1149e-128">Create an emergency admin account</span></span>

<span data-ttu-id="1149e-129">Du bör också skapa ett konto för säkerhetskopiering som inte är konfigurerat med multifaktorautentisering (MFA) så att du inte oavsiktligt låser ut dig själv (till exempel om du förlorar telefonen som du använder som en andra form av verifiering).</span><span class="sxs-lookup"><span data-stu-id="1149e-129">You should also create a backup account that isn't set up with multi-factor authentication (MFA) so you don't accidentally lock yourself out (for example if you lose your phone that you're using as a second form of verification).</span></span> <span data-ttu-id="1149e-130">Kontrollera att lösenordet för det här kontot är en fras eller minst 16 tecken långt.</span><span class="sxs-lookup"><span data-stu-id="1149e-130">Make sure that the password for this account is a phrase or at least 16 characters long.</span></span> <span data-ttu-id="1149e-131">Det här kallas ofta för ett "break-glass-konto".</span><span class="sxs-lookup"><span data-stu-id="1149e-131">This is often referred to as a "break-glass account."</span></span>

## <a name="create-a-user-account-for-yourself"></a><span data-ttu-id="1149e-132">Skapa ett användarkonto åt dig själv</span><span class="sxs-lookup"><span data-stu-id="1149e-132">Create a user account for yourself</span></span>

<span data-ttu-id="1149e-133">Använd ditt användarkonto för att delta i samarbete med din organisation, inklusive att kontrollera e-post.</span><span class="sxs-lookup"><span data-stu-id="1149e-133">Use your user account to participate in collaboration with your organization, including checking mail.</span></span> <span data-ttu-id="1149e-134">Det innebär att dina administratörsautentiseringsuppgifter kan vara ungefär som  *Chavez <span></span> @Contoso.org* och ditt vanliga användarkonto kan vara ungefär som *<span></span> @Contoso.com*.</span><span class="sxs-lookup"><span data-stu-id="1149e-134">This means your admin credentials might be similar to  *Alice.Chavez <span></span>@Contoso.org* and your regular user account might be similar to *Alice<span></span>@Contoso.com*.</span></span>

<span data-ttu-id="1149e-135">Så här skapar du ett nytt användarkonto:</span><span class="sxs-lookup"><span data-stu-id="1149e-135">To create a new user account:</span></span>

1. <span data-ttu-id="1149e-136">Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">administrationscentret och</a> välj sedan **Användare aktiva** användare \> **i** det vänstra navigeringsfältet.</span><span class="sxs-lookup"><span data-stu-id="1149e-136">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>
2. <span data-ttu-id="1149e-137">På sidan **Aktiva** användare väljer du **Lägg** till en användare  längst upp på sidan. På panelen Ny användare anger du namn och annan information.</span><span class="sxs-lookup"><span data-stu-id="1149e-137">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
3. <span data-ttu-id="1149e-138">Expandera avsnittet **Roller** och välj **Användare (ingen administrativ åtkomst).**</span><span class="sxs-lookup"><span data-stu-id="1149e-138">Expand the **Roles** section, and choose **User (no administrative access)**.</span></span>
4. <span data-ttu-id="1149e-139">I avsnittet **Produktlicenser** flyttar du väljaren för att **Microsoft 365 Business** till **På**.</span><span class="sxs-lookup"><span data-stu-id="1149e-139">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **On**.</span></span>

## <a name="turn-on-security-defaults"></a><span data-ttu-id="1149e-140">Aktivera säkerhetsstandarder</span><span class="sxs-lookup"><span data-stu-id="1149e-140">Turn on security defaults</span></span>

<span data-ttu-id="1149e-141">Säkerhetsstandarder hjälper till att skydda organisationen från identitetsrelaterade attacker genom att tillhandahålla förkonfigurerade säkerhetsinställningar som Microsoft hanterar för din organisations räkning.</span><span class="sxs-lookup"><span data-stu-id="1149e-141">Security defaults help protect your organization from identity-related attacks by providing preconfigured security settings that Microsoft manages on behalf of your organization.</span></span> <span data-ttu-id="1149e-142">De här inställningarna omfattar aktivering av multifaktorautentisering (MFA) för alla administratörer och användarkonton.</span><span class="sxs-lookup"><span data-stu-id="1149e-142">These settings include enabling multi-factor authentication (MFA) for all admins and user accounts.</span></span> <span data-ttu-id="1149e-143">Mer information om standardinställningar för säkerhet och hur du aktiverar dem finns i [Aktivera standardinställningar för säkerhet.](m365-campaigns-conditional-access.md)</span><span class="sxs-lookup"><span data-stu-id="1149e-143">For more information about security defaults and to learn how to enable them on, see [Turn on security defaults](m365-campaigns-conditional-access.md).</span></span>

## <a name="additional-recommendations"></a><span data-ttu-id="1149e-144">Ytterligare rekommendationer</span><span class="sxs-lookup"><span data-stu-id="1149e-144">Additional recommendations</span></span>

- <span data-ttu-id="1149e-145">Stäng alla orelaterade webbläsarsessioner och appar, inklusive personliga e-postkonton, innan du använder administratörskonton.</span><span class="sxs-lookup"><span data-stu-id="1149e-145">Before using admin accounts, close out all unrelated browser sessions and apps, including personal email accounts.</span></span> <span data-ttu-id="1149e-146">Du kan också använda i privata webbläsarfönster eller inkognitofönster.</span><span class="sxs-lookup"><span data-stu-id="1149e-146">You can also use in private, or incognito browser windows.</span></span>
- <span data-ttu-id="1149e-147">Se till att logga ut från webbläsarsessionen när du har slutfört administratörsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="1149e-147">After completing admin tasks, be sure to sign out of the browser session.</span></span>
