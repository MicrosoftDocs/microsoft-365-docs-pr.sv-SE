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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: 'Lär dig hur du anger en förfalloprincip för lösenord i organisationen i administrationscentret för Microsoft 365. '
ms.openlocfilehash: bcea72dadb6f10ac4ef80677f3def57eca2724cd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628058"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="208c2-103">Ange förfalloprincip för lösenord i organisationen</span><span class="sxs-lookup"><span data-stu-id="208c2-103">Set the password expiration policy for your organization</span></span>

<span data-ttu-id="208c2-104">Den här artikeln är avsedd för personer som anger en förfalloprincip för lösenord för ett företag, en skola eller en ideell förening.</span><span class="sxs-lookup"><span data-stu-id="208c2-104">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span>  

<span data-ttu-id="208c2-105">Om du är en användare har du inte behörighet att ange att ditt lösenord aldrig ska upphöra.</span><span class="sxs-lookup"><span data-stu-id="208c2-105">If you're a user, you don't have the permissions to set your password to never expire.</span></span> <span data-ttu-id="208c2-106">Be den tekniska supporten på ditt företag eller din skola att göra stegen i denna artikel åt dig.</span><span class="sxs-lookup"><span data-stu-id="208c2-106">Ask your work or school technical support to do the steps in this article for you.</span></span>

<span data-ttu-id="208c2-107">Som administratör kan du göra så att användarlösenord upphör efter ett visst antal dagar, eller ställa in så att lösenord aldrig upphör.</span><span class="sxs-lookup"><span data-stu-id="208c2-107">As an admin, you can make user passwords expire after a certain number of days, or set passwords to never expire.</span></span> 

> [!Tip]
> <span data-ttu-id="208c2-108">Standard är att lösenord är inställda på att upphöra efter 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="208c2-108">By default, passwords are set to expire in 90 days.</span></span> <span data-ttu-id="208c2-109">Aktuella undersökningar tyder starkt på att tvingande lösenordsändringar gör mer skada än nytta.</span><span class="sxs-lookup"><span data-stu-id="208c2-109">Current research strongly indicates that mandated password changes do more harm than good.</span></span> <span data-ttu-id="208c2-110">Det får användarna att välja svagare lösenord, återanvända lösenord eller uppdatera gamla lösenord på ett sätt som gör det enkelt för hackare att gissa sig till dem.</span><span class="sxs-lookup"><span data-stu-id="208c2-110">They drive users to choose weaker passwords, re-use passwords, or update old passwords in ways that are easily guessed by hackers.</span></span> <span data-ttu-id="208c2-111">Om du ställer in lösenord att aldrig upphöra rekommenderar vi att du aktiverar [multifaktorautentisering](../security-and-compliance/set-up-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="208c2-111">If setting password to never expire, we recommend enabling [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

<span data-ttu-id="208c2-112">Följ anvisningarna nedan om du vill ställa in så att användarlösenorden ska upphöra efter en viss tid.</span><span class="sxs-lookup"><span data-stu-id="208c2-112">Follow the steps below if you want to set user passwords to expire after a specific amount of time.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="208c2-113">Endast [globala administratörer](../add-users/about-admin-roles.md) kan utföra de här stegen.</span><span class="sxs-lookup"><span data-stu-id="208c2-113">Only [global admins](../add-users/about-admin-roles.md) can perform these steps.</span></span>
  
1. <span data-ttu-id="208c2-114">I administrationscentret går du till **Inställningar** \> **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="208c2-114">In the admin center, go to the **Settings** \> **Settings**.</span></span>

2. <span data-ttu-id="208c2-115">Gå till sidan <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Säkerhet och sekretess</a>.</span><span class="sxs-lookup"><span data-stu-id="208c2-115">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
 <span data-ttu-id="208c2-116">Om du inte är global administratör visas inte alternativet Säkerhet och sekretess.</span><span class="sxs-lookup"><span data-stu-id="208c2-116">If you aren't a global admin, you won't see the Security and privacy option.</span></span>
  
3. <span data-ttu-id="208c2-117">Välj **Förfalloprincip för lösenordet**.</span><span class="sxs-lookup"><span data-stu-id="208c2-117">Select **Password expiration policy**.</span></span>
  
4. <span data-ttu-id="208c2-118">Om du inte vill att användarna ska behöva ändra lösenord markerar du kryssrutan bredvid **Ställ in så att användarlösenord upphör att gälla efter ett visst antal dagar**.</span><span class="sxs-lookup"><span data-stu-id="208c2-118">If you don't want users to have to change passwords, select the checkbox next to **Set user passwords to expire after a number of days**.</span></span>
  
5. <span data-ttu-id="208c2-119">Ange hur ofta lösenord ska upphöra.</span><span class="sxs-lookup"><span data-stu-id="208c2-119">Type how often passwords should expire.</span></span> <span data-ttu-id="208c2-120">Välj ett antal dagar mellan 14 och 730.</span><span class="sxs-lookup"><span data-stu-id="208c2-120">Choose a number of days from 14 to 730.</span></span>
  
6. <span data-ttu-id="208c2-121">I den andra rutan anger du när användarna underrättas om att deras lösenord upphör att gälla och väljer sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="208c2-121">In the second box type when users are notified that their password will expire, and then select **Save**.</span></span> <span data-ttu-id="208c2-122">Du kan välja ett antal dagar mellan 1 och 30.</span><span class="sxs-lookup"><span data-stu-id="208c2-122">Choose a number of days from 1 to 30.</span></span>
    
7. <span data-ttu-id="208c2-123">När användarens lösenord slutar gälla, visas ett meddelande om detta i det nedre högra hörnet på skärmen.</span><span class="sxs-lookup"><span data-stu-id="208c2-123">When the user's password expires, they'll get a notification that appears in the lower right corner of their screen.</span></span>
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a><span data-ttu-id="208c2-124">Viktiga saker du behöver veta om funktionen för lösenords giltighetstid</span><span class="sxs-lookup"><span data-stu-id="208c2-124">Important things you need to know about the password expiration feature</span></span>

<span data-ttu-id="208c2-125">Här är några saker som kan vara bra att känna till om hur denna funktion fungerar från och med januari 2018:</span><span class="sxs-lookup"><span data-stu-id="208c2-125">Here are some things to know about how this feature currently works as of January 2018:</span></span>
  
- <span data-ttu-id="208c2-p106">Personer som endast använder Outlook-appen tvingas inte återställa lösenordet för Microsoft 365 förrän det slutar gälla i cachen. Det kan dröja flera dagar från det faktiska utgångsdatumet. Det finns ingen lösning på det här felet på administratörsnivå.</span><span class="sxs-lookup"><span data-stu-id="208c2-p106">People who only use the Outlook app won't be forced to reset their Microsoft 365 password until it expires in the cache. This can be several days after the actual expiration date. There's no workaround for this at the admin level.</span></span>
    
- <span data-ttu-id="208c2-p107">Användarna får inget e-postmeddelande om att lösenordet slutar gälla om X dagar. Vill du ha den här funktionen? **[Rösta här!](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**</span><span class="sxs-lookup"><span data-stu-id="208c2-p107">Users do not get an email notification that their password is going to expire in X number of days. Do you want this feature? **[Vote here!](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**</span></span>
    
## <a name="prevent-last-password-from-being-used-again"></a><span data-ttu-id="208c2-132">Förhindra att det senaste lösenordet används igen</span><span class="sxs-lookup"><span data-stu-id="208c2-132">Prevent last password from being used again</span></span>

<span data-ttu-id="208c2-133">Om du vill förhindra återanvändning av gamla lösenord kan du göra det i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="208c2-133">If you want to prevent your users from recycling old passwords, you can do so in Azure AD.</span></span> <span data-ttu-id="208c2-134">Se [Ange förfalloprincip för lösenord i organisationen](https://docs.microsoft.com/office365/admin/manage/set-password-expiration-policy?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="208c2-134">See [Set the password expiration policy for your organization](https://docs.microsoft.com/office365/admin/manage/set-password-expiration-policy?view=o365-worldwide).</span></span>

<span data-ttu-id="208c2-135">Om en medarbetare använder en mobil enhet för att komma åt Microsoft 365 kan du också rensa den för att säkerställa att lösenordet inte längre lagras och återanvänds därifrån.</span><span class="sxs-lookup"><span data-stu-id="208c2-135">In addition, if an employee used a mobile device to access Microsoft 365, you can wipe it to ensure the password is no longer stored and recycled from there.</span></span> <span data-ttu-id="208c2-136">Mer information finns i [Rensa och blockera en tidigare anställds mobila enhet](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee?view=o365-worldwide#wipe-and-block-a-former-employees-mobile-device).</span><span class="sxs-lookup"><span data-stu-id="208c2-136">To learn more, see [Wipe and block a former employee's mobile device](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee?view=o365-worldwide#wipe-and-block-a-former-employees-mobile-device).</span></span>


## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a><span data-ttu-id="208c2-137">Synkronisera användares lösenords-hashar från lokal Active Directory till Azure AD (Microsoft 365)</span><span class="sxs-lookup"><span data-stu-id="208c2-137">Synchronize user passwords hashes from an on-premises Active Directory to Azure AD (Microsoft 365)</span></span>

<span data-ttu-id="208c2-p110">Den här artikeln handlar om att ange förfalloprincipen för användare som bara använder molnet (Azure AD). Den gäller inte för hybrididentitetsanvändare som använder synkronisering av lösenordshashar, direktautentisering och lokal federation som ADFS.</span><span class="sxs-lookup"><span data-stu-id="208c2-p110">This article is for setting the expiration policy for cloud-only users (Azure AD). It doesn't apply to hybrid identity users who use password hash sync, pass-through authentication or on-premises federation like ADFS.</span></span>
  
<span data-ttu-id="208c2-140">Information om hur du synkroniserar användarlösenordshashar från lokal AD till Azure AD finns i [Implementera synkronisering av lösenordshashar med Azure AD Connect-synkronisering](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span><span class="sxs-lookup"><span data-stu-id="208c2-140">To learn how to synchronize user password hashes from on premises AD to Azure AD, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>
