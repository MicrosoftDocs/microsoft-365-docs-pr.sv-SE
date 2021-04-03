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
ms.openlocfilehash: 0280f4fd43034f9ffb70104771fa4a099943af2d
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500238"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="780f3-103">Ange förfalloprincip för lösenord i organisationen</span><span class="sxs-lookup"><span data-stu-id="780f3-103">Set the password expiration policy for your organization</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="780f3-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="780f3-104">The admin center is changing.</span></span> <span data-ttu-id="780f3-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](../microsoft-365-admin-center-preview.md?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="780f3-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?view=o365-worldwide).</span></span>

::: moniker-end

## <a name="before-you-begin"></a><span data-ttu-id="780f3-106">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="780f3-106">Before you begin</span></span>

<span data-ttu-id="780f3-107">Den här artikeln är avsedd för personer som anger en förfalloprincip för lösenord för ett företag, en skola eller en ideell förening.</span><span class="sxs-lookup"><span data-stu-id="780f3-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="780f3-108">Du måste logga in med ditt administratörskonto för Microsoft 365 för att slutföra de här stegen.</span><span class="sxs-lookup"><span data-stu-id="780f3-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="780f3-109">[Vad är ett administratörskonto?](https://docs.microsoft.com/microsoft-365/business-video/admin-center-overview).</span><span class="sxs-lookup"><span data-stu-id="780f3-109">[What's an admin account?](https://docs.microsoft.com/microsoft-365/business-video/admin-center-overview).</span></span>

<span data-ttu-id="780f3-110">Som administratör kan du göra så att användarlösenord upphör efter ett visst antal dagar, eller ställa in så att lösenord aldrig upphör.</span><span class="sxs-lookup"><span data-stu-id="780f3-110">As an admin, you can make user passwords expire after a certain number of days, or set passwords to never expire.</span></span> <span data-ttu-id="780f3-111">Som standard är lösenord inställda på att aldrig upphöra att gälla för din organisation.</span><span class="sxs-lookup"><span data-stu-id="780f3-111">By default, passwords are set to never expire for your organization.</span></span>

<span data-ttu-id="780f3-112">Aktuella undersökningar tyder starkt på att tvingande lösenordsändringar gör mer skada än nytta.</span><span class="sxs-lookup"><span data-stu-id="780f3-112">Current research strongly indicates that mandated password changes do more harm than good.</span></span> <span data-ttu-id="780f3-113">Det får användarna att välja svagare lösenord, återanvända lösenord eller uppdatera gamla lösenord på ett sätt som gör det enkelt för hackare att gissa sig till dem.</span><span class="sxs-lookup"><span data-stu-id="780f3-113">They drive users to choose weaker passwords, re-use passwords, or update old passwords in ways that are easily guessed by hackers.</span></span> <span data-ttu-id="780f3-114">Vi rekommenderar att du [multifaktorautentisering](../security-and-compliance/set-up-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="780f3-114">We recommend enabling [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

<span data-ttu-id="780f3-115">Du måste vara [global administratör](../add-users/about-admin-roles.md) för att utföra de här stegen.</span><span class="sxs-lookup"><span data-stu-id="780f3-115">You must be a [global admin](../add-users/about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="780f3-116">Om du är en användare har du inte behörighet att ange att ditt lösenord aldrig ska upphöra.</span><span class="sxs-lookup"><span data-stu-id="780f3-116">If you're a user, you don't have the permissions to set your password to never expire.</span></span> <span data-ttu-id="780f3-117">Be den tekniska supporten på ditt företag eller din skola att göra stegen i denna artikel åt dig.</span><span class="sxs-lookup"><span data-stu-id="780f3-117">Ask your work or school technical support to do the steps in this article for you.</span></span>

## <a name="set-password-expiration-policy"></a><span data-ttu-id="780f3-118">Ange förfalloprincip för lösenordet</span><span class="sxs-lookup"><span data-stu-id="780f3-118">Set password expiration policy</span></span>

<span data-ttu-id="780f3-119">Följ anvisningarna nedan om du vill ställa in så att användarlösenorden ska upphöra efter en viss tid.</span><span class="sxs-lookup"><span data-stu-id="780f3-119">Follow the steps below if you want to set user passwords to expire after a specific amount of time.</span></span>

1. <span data-ttu-id="780f3-120">I administrationscentret för går du till fliken **inställningar** \> **organisationsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="780f3-120">In the admin center, go to the **Settings** \> **Org Settings**.</span></span>

2. <span data-ttu-id="780f3-121">Gå till sidan <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Säkerhet och sekretess</a>.</span><span class="sxs-lookup"><span data-stu-id="780f3-121">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
 <span data-ttu-id="780f3-122">Om du inte är global administratör visas inte alternativet Säkerhet och sekretess.</span><span class="sxs-lookup"><span data-stu-id="780f3-122">If you aren't a global admin, you won't see the Security and privacy option.</span></span>
  
3. <span data-ttu-id="780f3-123">Välj **Förfalloprincip för lösenordet**.</span><span class="sxs-lookup"><span data-stu-id="780f3-123">Select **Password expiration policy**.</span></span>
  
4. <span data-ttu-id="780f3-124">Om du inte vill att användarna ska behöva ändra lösenord avmarkerar du rutan bredvid **Ställ in så att användarlösenord upphör att gälla efter ett visst antal dagar**.</span><span class="sxs-lookup"><span data-stu-id="780f3-124">If you don't want users to have to change passwords, uncheck the box next to **Set user passwords to expire after a number of days**.</span></span>
  
5. <span data-ttu-id="780f3-125">Ange hur ofta lösenord ska upphöra.</span><span class="sxs-lookup"><span data-stu-id="780f3-125">Type how often passwords should expire.</span></span> <span data-ttu-id="780f3-126">Välj ett antal dagar mellan 14 och 730.</span><span class="sxs-lookup"><span data-stu-id="780f3-126">Choose a number of days from 14 to 730.</span></span>
  
6. <span data-ttu-id="780f3-127">I den andra rutan anger du när användarna underrättas om att deras lösenord upphör att gälla och väljer sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="780f3-127">In the second box type when users are notified that their password will expire, and then select **Save**.</span></span> <span data-ttu-id="780f3-128">Du kan välja ett antal dagar mellan 1 och 30.</span><span class="sxs-lookup"><span data-stu-id="780f3-128">Choose a number of days from 1 to 30.</span></span>
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a><span data-ttu-id="780f3-129">Viktiga saker du behöver veta om funktionen för lösenords giltighetstid</span><span class="sxs-lookup"><span data-stu-id="780f3-129">Important things you need to know about the password expiration feature</span></span>
  
- <span data-ttu-id="780f3-p109">Personer som endast använder Outlook-appen tvingas inte återställa lösenordet för Microsoft 365 förrän det slutar gälla i cachen. Det kan dröja flera dagar från det faktiska utgångsdatumet. Det finns ingen lösning på det här felet på administratörsnivå.</span><span class="sxs-lookup"><span data-stu-id="780f3-p109">People who only use the Outlook app won't be forced to reset their Microsoft 365 password until it expires in the cache. This can be several days after the actual expiration date. There's no workaround for this at the admin level.</span></span>

## <a name="prevent-last-password-from-being-used-again"></a><span data-ttu-id="780f3-133">Förhindra att det senaste lösenordet används igen</span><span class="sxs-lookup"><span data-stu-id="780f3-133">Prevent last password from being used again</span></span>

<span data-ttu-id="780f3-134">Om du inte vill att användarna ska kunna återanvända gamla lösenord kan du aktivera lösenordshistorik i lokala Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="780f3-134">If you want to prevent your users from recycling old passwords, you can do so by enforcing password history in on-premises Active Directory (AD).</span></span> <span data-ttu-id="780f3-135">Se [Skapa en anpassad lösenordspolicy](/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).</span><span class="sxs-lookup"><span data-stu-id="780f3-135">See [Create a custom password policy](/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).</span></span>

<span data-ttu-id="780f3-136">Det går inte att använda det senaste lösenordet igen när användaren byter lösenord i Microsoft Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="780f3-136">In Azure AD, The last password can't be used again when the user changes a password.</span></span> <span data-ttu-id="780f3-137">Lösenordsprincipen tillämpas på alla användarkonton som skapas och hanteras direkt i Microsoft Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="780f3-137">The password policy is applied to all user accounts that are created and managed directly in Azure AD.</span></span> <span data-ttu-id="780f3-138">Du kan inte ändra den här lösenordsprincipen.</span><span class="sxs-lookup"><span data-stu-id="780f3-138">This password policy can't be modified.</span></span> <span data-ttu-id="780f3-139">Se [Lösenordsprinciper för Microsoft Azure Active Directory](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).</span><span class="sxs-lookup"><span data-stu-id="780f3-139">See [Azure AD password policies](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).</span></span>

## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a><span data-ttu-id="780f3-140">Synkronisera användares lösenords-hashar från lokal Active Directory till Azure AD (Microsoft 365)</span><span class="sxs-lookup"><span data-stu-id="780f3-140">Synchronize user passwords hashes from an on-premises Active Directory to Azure AD (Microsoft 365)</span></span>

<span data-ttu-id="780f3-141">Den här artikeln handlar om att ange förfalloprincipen för användare som bara använder molnet (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="780f3-141">This article is for setting the expiration policy for cloud-only users (Azure AD).</span></span> <span data-ttu-id="780f3-142">Den gäller inte för hybrididentitetsanvändare som använder synkronisering av lösenords-hashar, direktautentisering och lokal federation som ADFS.</span><span class="sxs-lookup"><span data-stu-id="780f3-142">It doesn't apply to hybrid identity users who use password hash sync, pass-through authentication, or on-premises federation like ADFS.</span></span>
  
<span data-ttu-id="780f3-143">Information om hur du synkroniserar användarlösenordshashar från lokal AD till Azure AD finns i [Implementera synkronisering av lösenordshashar med Azure AD Connect-synkronisering](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span><span class="sxs-lookup"><span data-stu-id="780f3-143">To learn how to synchronize user password hashes from on premises AD to Azure AD, see [Implement password hash synchronization with Azure AD Connect sync](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>

## <a name="password-policies-and-account-restrictions-in-azure-active-directory"></a><span data-ttu-id="780f3-144">Lösenordsprinciper och kontobegränsningar i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="780f3-144">Password policies and account restrictions in Azure Active Directory</span></span>

<span data-ttu-id="780f3-145">Du kan konfigurera fler lösenordsprinciper och begränsningar i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="780f3-145">You can set more password policies and restrictions in Azure active directory.</span></span> <span data-ttu-id="780f3-146">Gå till [Lösenordsprinciper och kontobegränsningar i Azure Active Directory](/azure/active-directory/authentication/concept-sspr-policy) för mer information.</span><span class="sxs-lookup"><span data-stu-id="780f3-146">Check out [Password policies and account restrictions in Azure Active Directory](/azure/active-directory/authentication/concept-sspr-policy) for more info.</span></span>

## <a name="update-password-policy"></a><span data-ttu-id="780f3-147">Uppdatera lösenordspolicy</span><span class="sxs-lookup"><span data-stu-id="780f3-147">Update password Policy</span></span>

<span data-ttu-id="780f3-148">Set-MsolPasswordPolicy cmdlet uppdaterar lösenordspolicyn för en specificerad domän eller hyresgäst.</span><span class="sxs-lookup"><span data-stu-id="780f3-148">The Set-MsolPasswordPolicy cmdlet updates the password policy of a specified domain or tenant.</span></span> <span data-ttu-id="780f3-149">Två inställningar krävs; den första är att ange hur lång tid ett lösenord förblir giltigt innan det måste ändras och det andra är att ange antalet dagar innan lösenordets utgångsdatum som kommer att trigga när användare kommer att få sitt första meddelande om att deras lösenord snart kommer att löpa ut.</span><span class="sxs-lookup"><span data-stu-id="780f3-149">Two settings are required; the first is to indicate the length of time that a password remains valid before it must be changed and the second is to indicate the number of days before the password expiration date that will trigger when users will receive their first notification that their password will soon expire.</span></span>

<span data-ttu-id="780f3-150">Information om hur du uppdaterar lösenordspolicyn för en specifik domän eller hyresgäst finns i [Set-MsolPasswordPolicy](/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="780f3-150">To learn how to update password policy for a specific domain or tenant, see [Set-MsolPasswordPolicy](/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0).</span></span>

## <a name="related-content"></a><span data-ttu-id="780f3-151">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="780f3-151">Related content</span></span>

[<span data-ttu-id="780f3-152">Låt användare återställa sina egna lösenord</span><span class="sxs-lookup"><span data-stu-id="780f3-152">Let users reset their own passwords</span></span>](../add-users/let-users-reset-passwords.md)

[<span data-ttu-id="780f3-153">Återställa lösenord</span><span class="sxs-lookup"><span data-stu-id="780f3-153">Reset passwords</span></span>](../add-users/reset-passwords.md)