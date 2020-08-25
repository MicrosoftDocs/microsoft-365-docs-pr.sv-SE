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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: 'Lär dig hur du anger en förfalloprincip för lösenord i organisationen i administrationscentret för Microsoft 365. '
ms.openlocfilehash: e95184bda631a5efaad0376c766ce5408c0a95e7
ms.sourcegitcommit: 22dab0f7604cc057a062698005ff901d40771692
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/25/2020
ms.locfileid: "46868873"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="55b37-103">Ange förfalloprincip för lösenord i organisationen</span><span class="sxs-lookup"><span data-stu-id="55b37-103">Set the password expiration policy for your organization</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="55b37-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="55b37-104">The admin center is changing.</span></span> <span data-ttu-id="55b37-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="55b37-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="55b37-106">Den här artikeln är avsedd för personer som anger en förfalloprincip för lösenord för ett företag, en skola eller en ideell förening.</span><span class="sxs-lookup"><span data-stu-id="55b37-106">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span>  

<span data-ttu-id="55b37-107">Om du är en användare har du inte behörighet att ange att ditt lösenord aldrig ska upphöra.</span><span class="sxs-lookup"><span data-stu-id="55b37-107">If you're a user, you don't have the permissions to set your password to never expire.</span></span> <span data-ttu-id="55b37-108">Be den tekniska supporten på ditt företag eller din skola att göra stegen i denna artikel åt dig.</span><span class="sxs-lookup"><span data-stu-id="55b37-108">Ask your work or school technical support to do the steps in this article for you.</span></span>

<span data-ttu-id="55b37-109">Som administratör kan du göra så att användarlösenord upphör efter ett visst antal dagar, eller ställa in så att lösenord aldrig upphör.</span><span class="sxs-lookup"><span data-stu-id="55b37-109">As an admin, you can make user passwords expire after a certain number of days, or set passwords to never expire.</span></span> 

> [!Tip]
> <span data-ttu-id="55b37-110">Standard är att lösenord är inställda på att upphöra efter 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="55b37-110">By default, passwords are set to expire in 90 days.</span></span> <span data-ttu-id="55b37-111">Aktuella undersökningar tyder starkt på att tvingande lösenordsändringar gör mer skada än nytta.</span><span class="sxs-lookup"><span data-stu-id="55b37-111">Current research strongly indicates that mandated password changes do more harm than good.</span></span> <span data-ttu-id="55b37-112">Det får användarna att välja svagare lösenord, återanvända lösenord eller uppdatera gamla lösenord på ett sätt som gör det enkelt för hackare att gissa sig till dem.</span><span class="sxs-lookup"><span data-stu-id="55b37-112">They drive users to choose weaker passwords, re-use passwords, or update old passwords in ways that are easily guessed by hackers.</span></span> <span data-ttu-id="55b37-113">Om du ställer in lösenord att aldrig upphöra rekommenderar vi att du aktiverar [multifaktorautentisering](../security-and-compliance/set-up-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="55b37-113">If setting password to never expire, we recommend enabling [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

<span data-ttu-id="55b37-114">Följ anvisningarna nedan om du vill ställa in så att användarlösenorden ska upphöra efter en viss tid.</span><span class="sxs-lookup"><span data-stu-id="55b37-114">Follow the steps below if you want to set user passwords to expire after a specific amount of time.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="55b37-115">Endast [globala administratörer](../add-users/about-admin-roles.md) kan utföra de här stegen.</span><span class="sxs-lookup"><span data-stu-id="55b37-115">Only [global admins](../add-users/about-admin-roles.md) can perform these steps.</span></span>
  
1. <span data-ttu-id="55b37-116">I administrationscentret för går du till fliken **inställningar** \> **organisationsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="55b37-116">In the admin center, go to the **Settings** \> **Org Settings**.</span></span>

2. <span data-ttu-id="55b37-117">Gå till sidan <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Säkerhet och sekretess</a>.</span><span class="sxs-lookup"><span data-stu-id="55b37-117">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
 <span data-ttu-id="55b37-118">Om du inte är global administratör visas inte alternativet Säkerhet och sekretess.</span><span class="sxs-lookup"><span data-stu-id="55b37-118">If you aren't a global admin, you won't see the Security and privacy option.</span></span>
  
3. <span data-ttu-id="55b37-119">Välj **Förfalloprincip för lösenordet**.</span><span class="sxs-lookup"><span data-stu-id="55b37-119">Select **Password expiration policy**.</span></span>
  
4. <span data-ttu-id="55b37-120">Om du inte vill att användarna ska behöva ändra lösenord markerar du kryssrutan bredvid **Ställ in så att användarlösenord upphör att gälla efter ett visst antal dagar**.</span><span class="sxs-lookup"><span data-stu-id="55b37-120">If you don't want users to have to change passwords, select the checkbox next to **Set user passwords to expire after a number of days**.</span></span>
  
5. <span data-ttu-id="55b37-121">Ange hur ofta lösenord ska upphöra.</span><span class="sxs-lookup"><span data-stu-id="55b37-121">Type how often passwords should expire.</span></span> <span data-ttu-id="55b37-122">Välj ett antal dagar mellan 14 och 730.</span><span class="sxs-lookup"><span data-stu-id="55b37-122">Choose a number of days from 14 to 730.</span></span>
  
6. <span data-ttu-id="55b37-123">I den andra rutan anger du när användarna underrättas om att deras lösenord upphör att gälla och väljer sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="55b37-123">In the second box type when users are notified that their password will expire, and then select **Save**.</span></span> <span data-ttu-id="55b37-124">Du kan välja ett antal dagar mellan 1 och 30.</span><span class="sxs-lookup"><span data-stu-id="55b37-124">Choose a number of days from 1 to 30.</span></span>
    
7. <span data-ttu-id="55b37-125">När användarens lösenord slutar gälla, visas ett meddelande om detta i det nedre högra hörnet på skärmen.</span><span class="sxs-lookup"><span data-stu-id="55b37-125">When the user's password expires, they'll get a notification that appears in the lower right corner of their screen.</span></span>
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a><span data-ttu-id="55b37-126">Viktiga saker du behöver veta om funktionen för lösenords giltighetstid</span><span class="sxs-lookup"><span data-stu-id="55b37-126">Important things you need to know about the password expiration feature</span></span>

<span data-ttu-id="55b37-127">Här är några saker som kan vara bra att känna till om hur denna funktion fungerar från och med januari 2018:</span><span class="sxs-lookup"><span data-stu-id="55b37-127">Here are some things to know about how this feature currently works as of January 2018:</span></span>
  
- <span data-ttu-id="55b37-p107">Personer som endast använder Outlook-appen tvingas inte återställa lösenordet för Microsoft 365 förrän det slutar gälla i cachen. Det kan dröja flera dagar från det faktiska utgångsdatumet. Det finns ingen lösning på det här felet på administratörsnivå.</span><span class="sxs-lookup"><span data-stu-id="55b37-p107">People who only use the Outlook app won't be forced to reset their Microsoft 365 password until it expires in the cache. This can be several days after the actual expiration date. There's no workaround for this at the admin level.</span></span>
    
- <span data-ttu-id="55b37-p108">Användarna får inget e-postmeddelande om att lösenordet slutar gälla om X dagar. Vill du ha den här funktionen? **[Rösta här!](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**</span><span class="sxs-lookup"><span data-stu-id="55b37-p108">Users do not get an email notification that their password is going to expire in X number of days. Do you want this feature? **[Vote here!](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**</span></span>
    
## <a name="prevent-last-password-from-being-used-again"></a><span data-ttu-id="55b37-134">Förhindra att det senaste lösenordet används igen</span><span class="sxs-lookup"><span data-stu-id="55b37-134">Prevent last password from being used again</span></span>

<span data-ttu-id="55b37-135">Om du inte vill att användarna ska kunna återanvända gamla lösenord kan du aktivera lösenordshistorik i lokala Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="55b37-135">If you want to prevent your users from recycling old passwords, you can do so by enforcing password history in on-premises Active Directory (AD).</span></span> <span data-ttu-id="55b37-136">Se [Skapa en anpassad lösenordspolicy](https://docs.microsoft.com/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).</span><span class="sxs-lookup"><span data-stu-id="55b37-136">See [Create a custom password policy](https://docs.microsoft.com/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).</span></span>

<span data-ttu-id="55b37-137">Det går inte att använda det senaste lösenordet igen när användaren byter lösenord i Microsoft Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="55b37-137">In Azure AD, The last password can't be used again when the user changes a password.</span></span> <span data-ttu-id="55b37-138">Lösenordsprincipen tillämpas på alla användarkonton som skapas och hanteras direkt i Microsoft Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="55b37-138">The password policy is applied to all user accounts that are created and managed directly in Azure AD.</span></span> <span data-ttu-id="55b37-139">Du kan inte ändra den här lösenordsprincipen.</span><span class="sxs-lookup"><span data-stu-id="55b37-139">This password policy can't be modified.</span></span> <span data-ttu-id="55b37-140">Se [Lösenordsprinciper för Microsoft Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).</span><span class="sxs-lookup"><span data-stu-id="55b37-140">See [Azure AD password policies](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).</span></span>

## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a><span data-ttu-id="55b37-141">Synkronisera användares lösenords-hashar från lokal Active Directory till Azure AD (Microsoft 365)</span><span class="sxs-lookup"><span data-stu-id="55b37-141">Synchronize user passwords hashes from an on-premises Active Directory to Azure AD (Microsoft 365)</span></span>

<span data-ttu-id="55b37-142">Den här artikeln handlar om att ange förfalloprincipen för användare som bara använder molnet (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="55b37-142">This article is for setting the expiration policy for cloud-only users (Azure AD).</span></span> <span data-ttu-id="55b37-143">Den gäller inte för hybrididentitetsanvändare som använder synkronisering av lösenords-hashar, direktautentisering och lokal federation som ADFS.</span><span class="sxs-lookup"><span data-stu-id="55b37-143">It doesn't apply to hybrid identity users who use password hash sync, pass-through authentication, or on-premises federation like ADFS.</span></span>
  
<span data-ttu-id="55b37-144">Information om hur du synkroniserar användarlösenordshashar från lokal AD till Azure AD finns i [Implementera synkronisering av lösenordshashar med Azure AD Connect-synkronisering](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span><span class="sxs-lookup"><span data-stu-id="55b37-144">To learn how to synchronize user password hashes from on premises AD to Azure AD, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>


## <a name="update-password-policy"></a><span data-ttu-id="55b37-145">Uppdatera lösenordspolicy</span><span class="sxs-lookup"><span data-stu-id="55b37-145">Update password Policy</span></span>

<span data-ttu-id="55b37-146">Set-MsolPasswordPolicy cmdlet uppdaterar lösenordspolicyn för en specificerad domän eller hyresgäst.</span><span class="sxs-lookup"><span data-stu-id="55b37-146">The Set-MsolPasswordPolicy cmdlet updates the password policy of a specified domain or tenant.</span></span> <span data-ttu-id="55b37-147">Två inställningar krävs; den första är att ange hur lång tid ett lösenord förblir giltigt innan det måste ändras och det andra är att ange antalet dagar innan lösenordets utgångsdatum som kommer att trigga när användare kommer att få sitt första meddelande om att deras lösenord snart kommer att löpa ut.</span><span class="sxs-lookup"><span data-stu-id="55b37-147">Two settings are required; the first is to indicate the length of time that a password remains valid before it must be changed and the second is to indicate the number of days before the password expiration date that will trigger when users will receive their first notification that their password will soon expire.</span></span>

<span data-ttu-id="55b37-148">Information om hur du uppdaterar lösenordspolicyn för en specifik domän eller hyresgäst finns i [Set-MsolPasswordPolicy](https://docs.microsoft.com/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="55b37-148">To learn how to update password policy for a specific domain or tenant, see [Set-MsolPasswordPolicy](https://docs.microsoft.com/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0).</span></span>
