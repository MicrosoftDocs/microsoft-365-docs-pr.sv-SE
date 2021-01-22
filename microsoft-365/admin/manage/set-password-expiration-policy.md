---
title: Ange förfalloprincip för lösenord i organisationen
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: Lär dig hur du anger en förfalloprincip för lösenord i organisationen i administrationscentret för Microsoft 365.
ms.openlocfilehash: 471a881bd9808861b9fa2c67d007f1ebe1c10885
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926180"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="d2b72-103">Ange förfalloprincip för lösenord i organisationen</span><span class="sxs-lookup"><span data-stu-id="d2b72-103">Set the password expiration policy for your organization</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="d2b72-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="d2b72-104">The admin center is changing.</span></span> <span data-ttu-id="d2b72-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="d2b72-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-worldwide).</span></span>

::: moniker-end

## <a name="before-you-begin"></a><span data-ttu-id="d2b72-106">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="d2b72-106">Before you begin</span></span>

<span data-ttu-id="d2b72-107">Den här artikeln är avsedd för personer som anger en förfalloprincip för lösenord för ett företag, en skola eller en ideell förening.</span><span class="sxs-lookup"><span data-stu-id="d2b72-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="d2b72-108">Du måste logga in med ditt administratörskonto för Microsoft 365 för att slutföra de här stegen.</span><span class="sxs-lookup"><span data-stu-id="d2b72-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="d2b72-109">[Vad är ett administratörskonto?](../admin-overview/admin-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d2b72-109">[What's an admin account?](../admin-overview/admin-overview.md).</span></span>

<span data-ttu-id="d2b72-110">Du måste vara [global administratör eller lösenordsadministratör](../add-users/about-admin-roles.md) för att utföra de här stegen.</span><span class="sxs-lookup"><span data-stu-id="d2b72-110">You must be a [global admin or password admin](../add-users/about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="d2b72-111">Om du är en användare har du inte behörighet att ange att ditt lösenord aldrig ska upphöra.</span><span class="sxs-lookup"><span data-stu-id="d2b72-111">If you're a user, you don't have the permissions to set your password to never expire.</span></span> <span data-ttu-id="d2b72-112">Be den tekniska supporten på ditt företag eller din skola att göra stegen i denna artikel åt dig.</span><span class="sxs-lookup"><span data-stu-id="d2b72-112">Ask your work or school technical support to do the steps in this article for you.</span></span>

<span data-ttu-id="d2b72-113">Som administratör kan du göra så att användarlösenord upphör efter ett visst antal dagar, eller ställa in så att lösenord aldrig upphör.</span><span class="sxs-lookup"><span data-stu-id="d2b72-113">As an admin, you can make user passwords expire after a certain number of days, or set passwords to never expire.</span></span>

## <a name="set-password-expiration-policy"></a><span data-ttu-id="d2b72-114">Ange förfalloprincip för lösenordet</span><span class="sxs-lookup"><span data-stu-id="d2b72-114">Set password expiration policy</span></span>

> [!Tip]
> <span data-ttu-id="d2b72-115">Standard är att lösenord är inställda på att upphöra efter 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="d2b72-115">By default, passwords are set to expire in 90 days.</span></span> <span data-ttu-id="d2b72-116">Aktuella undersökningar tyder starkt på att tvingande lösenordsändringar gör mer skada än nytta.</span><span class="sxs-lookup"><span data-stu-id="d2b72-116">Current research strongly indicates that mandated password changes do more harm than good.</span></span> <span data-ttu-id="d2b72-117">Det får användarna att välja svagare lösenord, återanvända lösenord eller uppdatera gamla lösenord på ett sätt som gör det enkelt för hackare att gissa sig till dem.</span><span class="sxs-lookup"><span data-stu-id="d2b72-117">They drive users to choose weaker passwords, re-use passwords, or update old passwords in ways that are easily guessed by hackers.</span></span> <span data-ttu-id="d2b72-118">Om du ställer in lösenord att aldrig upphöra rekommenderar vi att du aktiverar [multifaktorautentisering](../security-and-compliance/set-up-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="d2b72-118">If setting password to never expire, we recommend enabling [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

<span data-ttu-id="d2b72-119">Följ anvisningarna nedan om du vill ställa in så att användarlösenorden ska upphöra efter en viss tid.</span><span class="sxs-lookup"><span data-stu-id="d2b72-119">Follow the steps below if you want to set user passwords to expire after a specific amount of time.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="d2b72-120">Endast [globala administratörer](../add-users/about-admin-roles.md) kan utföra de här stegen.</span><span class="sxs-lookup"><span data-stu-id="d2b72-120">Only [global admins](../add-users/about-admin-roles.md) can perform these steps.</span></span>
  
1. <span data-ttu-id="d2b72-121">I administrationscentret för går du till fliken **inställningar** \> **organisationsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="d2b72-121">In the admin center, go to the **Settings** \> **Org Settings**.</span></span>

2. <span data-ttu-id="d2b72-122">Gå till sidan <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Säkerhet och sekretess</a>.</span><span class="sxs-lookup"><span data-stu-id="d2b72-122">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
 <span data-ttu-id="d2b72-123">Om du inte är global administratör visas inte alternativet Säkerhet och sekretess.</span><span class="sxs-lookup"><span data-stu-id="d2b72-123">If you aren't a global admin, you won't see the Security and privacy option.</span></span>
  
3. <span data-ttu-id="d2b72-124">Välj **Förfalloprincip för lösenordet**.</span><span class="sxs-lookup"><span data-stu-id="d2b72-124">Select **Password expiration policy**.</span></span>
  
4. <span data-ttu-id="d2b72-125">Om du inte vill att användarna ska behöva ändra lösenord avmarkerar du rutan bredvid **Ställ in så att användarlösenord upphör att gälla efter ett visst antal dagar**.</span><span class="sxs-lookup"><span data-stu-id="d2b72-125">If you don't want users to have to change passwords, uncheck the box next to **Set user passwords to expire after a number of days**.</span></span>
  
5. <span data-ttu-id="d2b72-126">Ange hur ofta lösenord ska upphöra.</span><span class="sxs-lookup"><span data-stu-id="d2b72-126">Type how often passwords should expire.</span></span> <span data-ttu-id="d2b72-127">Välj ett antal dagar mellan 14 och 730.</span><span class="sxs-lookup"><span data-stu-id="d2b72-127">Choose a number of days from 14 to 730.</span></span>
  
6. <span data-ttu-id="d2b72-128">I den andra rutan anger du när användarna underrättas om att deras lösenord upphör att gälla och väljer sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d2b72-128">In the second box type when users are notified that their password will expire, and then select **Save**.</span></span> <span data-ttu-id="d2b72-129">Du kan välja ett antal dagar mellan 1 och 30.</span><span class="sxs-lookup"><span data-stu-id="d2b72-129">Choose a number of days from 1 to 30.</span></span>

7. <span data-ttu-id="d2b72-130">När användarens lösenord slutar gälla, visas ett meddelande om detta i det nedre högra hörnet på skärmen.</span><span class="sxs-lookup"><span data-stu-id="d2b72-130">When the user's password expires, they'll get a notification that appears in the lower right corner of their screen.</span></span>
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a><span data-ttu-id="d2b72-131">Viktiga saker du behöver veta om funktionen för lösenords giltighetstid</span><span class="sxs-lookup"><span data-stu-id="d2b72-131">Important things you need to know about the password expiration feature</span></span>
  
- <span data-ttu-id="d2b72-p108">Personer som endast använder Outlook-appen tvingas inte återställa lösenordet för Microsoft 365 förrän det slutar gälla i cachen. Det kan dröja flera dagar från det faktiska utgångsdatumet. Det finns ingen lösning på det här felet på administratörsnivå.</span><span class="sxs-lookup"><span data-stu-id="d2b72-p108">People who only use the Outlook app won't be forced to reset their Microsoft 365 password until it expires in the cache. This can be several days after the actual expiration date. There's no workaround for this at the admin level.</span></span>

## <a name="prevent-last-password-from-being-used-again"></a><span data-ttu-id="d2b72-135">Förhindra att det senaste lösenordet används igen</span><span class="sxs-lookup"><span data-stu-id="d2b72-135">Prevent last password from being used again</span></span>

<span data-ttu-id="d2b72-136">Om du inte vill att användarna ska kunna återanvända gamla lösenord kan du aktivera lösenordshistorik i lokala Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="d2b72-136">If you want to prevent your users from recycling old passwords, you can do so by enforcing password history in on-premises Active Directory (AD).</span></span> <span data-ttu-id="d2b72-137">Se [Skapa en anpassad lösenordspolicy](https://docs.microsoft.com/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).</span><span class="sxs-lookup"><span data-stu-id="d2b72-137">See [Create a custom password policy](https://docs.microsoft.com/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).</span></span>

<span data-ttu-id="d2b72-138">Det går inte att använda det senaste lösenordet igen när användaren byter lösenord i Microsoft Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d2b72-138">In Azure AD, The last password can't be used again when the user changes a password.</span></span> <span data-ttu-id="d2b72-139">Lösenordsprincipen tillämpas på alla användarkonton som skapas och hanteras direkt i Microsoft Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d2b72-139">The password policy is applied to all user accounts that are created and managed directly in Azure AD.</span></span> <span data-ttu-id="d2b72-140">Du kan inte ändra den här lösenordsprincipen.</span><span class="sxs-lookup"><span data-stu-id="d2b72-140">This password policy can't be modified.</span></span> <span data-ttu-id="d2b72-141">Se [Lösenordsprinciper för Microsoft Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).</span><span class="sxs-lookup"><span data-stu-id="d2b72-141">See [Azure AD password policies](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).</span></span>

## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a><span data-ttu-id="d2b72-142">Synkronisera användares lösenords-hashar från lokal Active Directory till Azure AD (Microsoft 365)</span><span class="sxs-lookup"><span data-stu-id="d2b72-142">Synchronize user passwords hashes from an on-premises Active Directory to Azure AD (Microsoft 365)</span></span>

<span data-ttu-id="d2b72-143">Den här artikeln handlar om att ange förfalloprincipen för användare som bara använder molnet (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="d2b72-143">This article is for setting the expiration policy for cloud-only users (Azure AD).</span></span> <span data-ttu-id="d2b72-144">Den gäller inte för hybrididentitetsanvändare som använder synkronisering av lösenords-hashar, direktautentisering och lokal federation som ADFS.</span><span class="sxs-lookup"><span data-stu-id="d2b72-144">It doesn't apply to hybrid identity users who use password hash sync, pass-through authentication, or on-premises federation like ADFS.</span></span>
  
<span data-ttu-id="d2b72-145">Information om hur du synkroniserar användarlösenordshashar från lokal AD till Azure AD finns i [Implementera synkronisering av lösenordshashar med Azure AD Connect-synkronisering](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span><span class="sxs-lookup"><span data-stu-id="d2b72-145">To learn how to synchronize user password hashes from on premises AD to Azure AD, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>

## <a name="password-policies-and-account-restrictions-in-azure-active-directory"></a><span data-ttu-id="d2b72-146">Lösenordsprinciper och kontobegränsningar i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d2b72-146">Password policies and account restrictions in Azure Active Directory</span></span>

<span data-ttu-id="d2b72-147">Du kan konfigurera fler lösenordsprinciper och begränsningar i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d2b72-147">You can set more password policies and restrictions in Azure active directory.</span></span> <span data-ttu-id="d2b72-148">Gå till [Lösenordsprinciper och kontobegränsningar i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy) för mer information.</span><span class="sxs-lookup"><span data-stu-id="d2b72-148">Check out [Password policies and account restrictions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy) for more info.</span></span>

## <a name="update-password-policy"></a><span data-ttu-id="d2b72-149">Uppdatera lösenordspolicy</span><span class="sxs-lookup"><span data-stu-id="d2b72-149">Update password Policy</span></span>

<span data-ttu-id="d2b72-150">Set-MsolPasswordPolicy cmdlet uppdaterar lösenordspolicyn för en specificerad domän eller hyresgäst.</span><span class="sxs-lookup"><span data-stu-id="d2b72-150">The Set-MsolPasswordPolicy cmdlet updates the password policy of a specified domain or tenant.</span></span> <span data-ttu-id="d2b72-151">Två inställningar krävs; den första är att ange hur lång tid ett lösenord förblir giltigt innan det måste ändras och det andra är att ange antalet dagar innan lösenordets utgångsdatum som kommer att trigga när användare kommer att få sitt första meddelande om att deras lösenord snart kommer att löpa ut.</span><span class="sxs-lookup"><span data-stu-id="d2b72-151">Two settings are required; the first is to indicate the length of time that a password remains valid before it must be changed and the second is to indicate the number of days before the password expiration date that will trigger when users will receive their first notification that their password will soon expire.</span></span>

<span data-ttu-id="d2b72-152">Information om hur du uppdaterar lösenordspolicyn för en specifik domän eller hyresgäst finns i [Set-MsolPasswordPolicy](https://docs.microsoft.com/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="d2b72-152">To learn how to update password policy for a specific domain or tenant, see [Set-MsolPasswordPolicy](https://docs.microsoft.com/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0).</span></span>

## <a name="related-content"></a><span data-ttu-id="d2b72-153">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="d2b72-153">Related content</span></span>

[<span data-ttu-id="d2b72-154">Låt användare återställa sina egna lösenord</span><span class="sxs-lookup"><span data-stu-id="d2b72-154">Let users reset their own passwords</span></span>](../add-users/let-users-reset-passwords.md)

[<span data-ttu-id="d2b72-155">Återställa lösenord</span><span class="sxs-lookup"><span data-stu-id="d2b72-155">Reset passwords</span></span>](../add-users/reset-passwords.md)
