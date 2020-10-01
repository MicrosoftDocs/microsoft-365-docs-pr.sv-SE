---
title: Hantera Microsoft 365-grupper
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Lär dig mer om hur du hanterar Microsoft 365-grupper.
ms.openlocfilehash: a01bf5dcc0b87cbdce8d7044b666cfb3a16a5aa9
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328552"
---
# <a name="manage-microsoft-365-groups"></a><span data-ttu-id="c5c4f-103">Hantera Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="c5c4f-103">Manage Microsoft 365 groups</span></span>

<span data-ttu-id="c5c4f-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="c5c4f-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c5c4f-105">Du kan hantera Microsoft 365-grupper på flera olika sätt, beroende på konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-105">You can manage Microsoft 365 groups in several different ways, depending on your configuration.</span></span> <span data-ttu-id="c5c4f-106">Du kan hantera användar konton i [administrations centret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/), PowerShell, i AD DS (Active Directory Domain Services) eller i [administrations centret för Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="c5c4f-106">You can manage user accounts in the [Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/add-users/), PowerShell, in Active Directory Domain Services (AD DS), or in the [Azure Active Directory (Azure AD) admin center](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal).</span></span> 

## <a name="plan-for-where-and-how-you-will-manage-your-groups"></a><span data-ttu-id="c5c4f-107">Planera var och hur du ska hantera dina grupper</span><span class="sxs-lookup"><span data-stu-id="c5c4f-107">Plan for where and how you will manage your groups</span></span>

<span data-ttu-id="c5c4f-108">Var och hur du kan hantera dina användar konton beror på vilken identitets modell du vill använda för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-108">Where and how you can manage your user accounts depends on the identity model you want to use for your Microsoft 365.</span></span> <span data-ttu-id="c5c4f-109">De två övergripande modellerna är endast molnbaserade och hybrid.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-109">The two overall models are cloud-only and hybrid.</span></span>
  
### <a name="cloud-only"></a><span data-ttu-id="c5c4f-110">Endast molnet</span><span class="sxs-lookup"><span data-stu-id="c5c4f-110">Cloud-only</span></span>

<span data-ttu-id="c5c4f-111">Du skapar och hanterar grupper med:</span><span class="sxs-lookup"><span data-stu-id="c5c4f-111">You create and manage groups with:</span></span>

- [<span data-ttu-id="c5c4f-112">Administrationscentret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c5c4f-112">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- [<span data-ttu-id="c5c4f-113">PowerShell</span><span class="sxs-lookup"><span data-stu-id="c5c4f-113">PowerShell</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="c5c4f-114">Administrations Center för Azure AD</span><span class="sxs-lookup"><span data-stu-id="c5c4f-114">Azure AD admin center</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    
### <a name="hybrid"></a><span data-ttu-id="c5c4f-115">Hybrid</span><span class="sxs-lookup"><span data-stu-id="c5c4f-115">Hybrid</span></span>

<span data-ttu-id="c5c4f-116">AD DS-grupper synkroniseras med Microsoft 365 från AD DS, så du måste använda lokala AD DS-verktyg för att hantera dessa grupper.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-116">AD DS groups are synchronized with Microsoft 365 from AD DS, so you must use on-premises AD DS tools to manage these groups.</span></span>

<span data-ttu-id="c5c4f-117">Du kan också skapa och hantera Azure AD-grupper som är åtskilda från AD DS-grupper men som kan innehålla användare och grupper från AD DS.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-117">You can also create and manage Azure AD groups that are separate from AD DS groups but can contain users and groups from AD DS.</span></span> <span data-ttu-id="c5c4f-118">I det här fallet kan du använda:</span><span class="sxs-lookup"><span data-stu-id="c5c4f-118">In this case, you can use:</span></span>

- [<span data-ttu-id="c5c4f-119">Administrationscentret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c5c4f-119">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- [<span data-ttu-id="c5c4f-120">PowerShell</span><span class="sxs-lookup"><span data-stu-id="c5c4f-120">PowerShell</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="c5c4f-121">Administrations Center för Azure AD</span><span class="sxs-lookup"><span data-stu-id="c5c4f-121">Azure AD admin center</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

## <a name="allow-users-to-create-and-manage-their-own-groups"></a><span data-ttu-id="c5c4f-122">Användare kan skapa och hantera sina egna grupper</span><span class="sxs-lookup"><span data-stu-id="c5c4f-122">Allow users to create and manage their own groups</span></span>

<span data-ttu-id="c5c4f-123">Azure AD tillåter grupper som kan hanteras av grupp ägare i stället för IT-administratörer.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-123">Azure AD allows groups that can be managed by group owners instead of IT administrators.</span></span> <span data-ttu-id="c5c4f-124">Funktionen kallas för *grupphantering via självbetjäning* där gruppägare som inte har tilldelats någon administratörsroll kan skapa och hantera säkerhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-124">Known as *self-service group management*, this feature allows group owners who are not assigned an administrative role to create and manage security groups.</span></span> 

<span data-ttu-id="c5c4f-125">Användarna kan begära medlemskap i en säkerhetsgrupp och begäran skickas till gruppens ägare, i stället för IT-administratören.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-125">Users can request membership in a security group and that request goes to the group owner, rather than an IT administrator.</span></span> <span data-ttu-id="c5c4f-126">Det innebär att den dagliga kontrollen av gruppmedlemskap blir delegerad till team-, projekt- eller företagsägare som förstår gruppens användningsområden och kan hantera medlemskapen.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-126">This allows the day-to-day control of group membership to be delegated to team, project, or business owners who understand the business use for the group and can manage its membership.</span></span>

>[!Note]
><span data-ttu-id="c5c4f-127">Grupphantering via självbetjäning finns endast för Azure AD-säkerhetsgrupper och Microsoft 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-127">Self-service group management is available only for Azure AD security and Microsoft 365 groups.</span></span> <span data-ttu-id="c5c4f-128">Det är inte tillgängligt för e-postaktiverade grupper, distributions listor eller någon grupp som har synkroniserats från AD DS.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-128">It is not available for mail-enabled groups, distribution lists, or any group that has been synchronized from AD DS.</span></span>
>

<span data-ttu-id="c5c4f-129">Mer information finns i [anvisningarna om att konfigurera en Azure AD-grupp för självbetjäningshantering](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span><span class="sxs-lookup"><span data-stu-id="c5c4f-129">For more information, see the [instructions to configure an Azure AD group for self-service management](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span></span>

## <a name="set-up-dynamic-group-membership"></a><span data-ttu-id="c5c4f-130">Konfigurera dynamiskt gruppmedlemskap</span><span class="sxs-lookup"><span data-stu-id="c5c4f-130">Set up dynamic group membership</span></span>

<span data-ttu-id="c5c4f-131">Azure AD har stöd för att konfigurera en serie regler som automatiskt lägger till eller tar bort användar konton som medlemmar i en Azure AD-grupp.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-131">Azure AD supports configuring a series of rules that automatically add or remove user accounts as members of an Azure AD group.</span></span> <span data-ttu-id="c5c4f-132">Detta kallas för ett *dynamiskt gruppmedlemskap*.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-132">This is known as *dynamic group membership*.</span></span> <span data-ttu-id="c5c4f-133">Reglerna baseras på användarkontonas attribut, till exempel Avdelning eller Land.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-133">The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="c5c4f-134">Så här tillämpas reglerna:</span><span class="sxs-lookup"><span data-stu-id="c5c4f-134">Here's how the rules are applied:</span></span>

- <span data-ttu-id="c5c4f-135">Om ett nytt användarkonto matchar alla regler för gruppen, blir det en medlem.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-135">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="c5c4f-136">Om ett användarkonto inte är medlem i gruppen, men dess attribut ändras så att det matchar alla regler för gruppen, blir det medlem i gruppen.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-136">If a user account isn't a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="c5c4f-137">Om ett användarkonto inte matchar alla regler för gruppen, läggs det inte till i gruppen.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-137">If a user account doesn't match all the rules for the group, it isn't added to the group.</span></span>
- <span data-ttu-id="c5c4f-138">Om ett användarkonto är medlem i gruppen, men dess attribut ändras så att det inte längre matchar alla regler för gruppen, tas det bort som medlem i gruppen.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-138">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="c5c4f-139">Om du vill använda dynamiskt medlemskap, måste du först bestämma vilka grupper som ska ha en gemensam uppsättning av användarkontoattribut.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-139">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes.</span></span> <span data-ttu-id="c5c4f-140">Alla medlemmar på säljavdelningen kan t.ex. ingå i gruppen Azure AD-försäljning, baserat på användarkontoattributet Avdelning som är inställd på ”Försäljning”.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-140">For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to "Sales".</span></span>

<span data-ttu-id="c5c4f-141">I [anvisningarna finns information om hur du skapar och konfigurerar reglerna för en dynamisk Azure AD-grupp](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="c5c4f-141">See the [instructions to create and configure the rules for a dynamic Azure AD group](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

## <a name="set-up-automatic-licensing"></a><span data-ttu-id="c5c4f-142">Konfigurera automatisk licensiering</span><span class="sxs-lookup"><span data-stu-id="c5c4f-142">Set up automatic licensing</span></span>

<span data-ttu-id="c5c4f-143">Du kan konfigurera säkerhets grupper i Azure AD så att de automatiskt tilldelar licenser från en uppsättning prenumerationer till alla medlemmar i gruppen.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-143">You can configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="c5c4f-144">Det här kallas för *gruppbaserad licensiering*.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-144">This is known as *group-based licensing*.</span></span> <span data-ttu-id="c5c4f-145">Om du lägger till eller tar bort ett användarkonto från gruppen, kommer licenserna för gruppens prenumerationer att tilldelas eller tas bort automatiskt från användarkontot.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-145">If a user account is added to or removed from the group, the licenses for the group's subscriptions will be automatically assigned or unassigned from the user account.</span></span>

<span data-ttu-id="c5c4f-146">För Microsoft 365 Enterprise konfigurerar du att Azure AD-säkerhetsgrupperna tilldelar en lämplig Microsoft 365 Enterprise-licens.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-146">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign the appropriate Microsoft 365 Enterprise license.</span></span>

<span data-ttu-id="c5c4f-147">Kontrollera att du har tillräckligt med licenser för alla gruppmedlemmar.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-147">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="c5c4f-148">Om licenserna tar slut kommer nya användare inte att tilldelas några licenser förrän licenserna blir tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-148">If you run out of licenses, new users won't be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="c5c4f-149">Du bör inte konfigurera gruppbaserad licensiering för grupper som innehåller konton för Azure B2B.</span><span class="sxs-lookup"><span data-stu-id="c5c4f-149">You should not configure group-based licensing for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="c5c4f-150">Mer information finns i avsnittet [om grundläggande licenser i Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="c5c4f-150">For more information, see [Group-based licensing basics in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="c5c4f-151">Se [anvisningarna för att konfigurera gruppbaserad licensiering för en Azure-säkerhetsgrupp](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="c5c4f-151">See the [instructions to configure group-based licensing for an Azure security group](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>
