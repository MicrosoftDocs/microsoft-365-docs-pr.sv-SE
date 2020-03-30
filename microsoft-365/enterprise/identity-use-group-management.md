---
title: 'Steg 5: Använda grupper för hantering'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Du kan använda grupper för att automatisera hanteringen av vissa administrativa uppgifter.
ms.openlocfilehash: 215bb84cbb0cedc2f1320372ba8239cd51d07c98
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42810397"
---
# <a name="step-5-use-groups-for-management"></a><span data-ttu-id="2f0e9-103">Steg 5: Använda grupper för hantering</span><span class="sxs-lookup"><span data-stu-id="2f0e9-103">Step 5: Use groups for management</span></span>

![Fas 2 – Identitet ](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-self-service-groups"></a>
## <a name="allow-users-to-create-and-manage-their-own-groups"></a><span data-ttu-id="2f0e9-105">Användare kan skapa och hantera sina egna grupper</span><span class="sxs-lookup"><span data-stu-id="2f0e9-105">Allow users to create and manage their own groups</span></span>

<span data-ttu-id="2f0e9-106">*Det här är valfritt och gäller både E3- och E5-versionerna av Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="2f0e9-106">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="2f0e9-107">I avsnittet identifierar du de Azure Active Directory-grupper som kan hanteras av gruppägare i stället för IT-administratörer.</span><span class="sxs-lookup"><span data-stu-id="2f0e9-107">In this section, you'll identify Azure Active Directory (Azure AD) groups that can be managed by group owners instead of IT administrators.</span></span> <span data-ttu-id="2f0e9-108">Funktionen kallas för *grupphantering via självbetjäning* där gruppägare som inte har tilldelats någon administratörsroll kan skapa och hantera säkerhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="2f0e9-108">Known as *self-service group management*, this feature allows group owners who are not assigned an administrative role to create and manage security groups.</span></span> 

<span data-ttu-id="2f0e9-109">Användarna kan begära medlemskap i en säkerhetsgrupp och begäran skickas till gruppens ägare, i stället för IT-administratören.</span><span class="sxs-lookup"><span data-stu-id="2f0e9-109">Users can request membership in a security group and that request goes to the group owner, rather than an IT administrator.</span></span> <span data-ttu-id="2f0e9-110">Det innebär att den dagliga kontrollen av gruppmedlemskap blir delegerad till team-, projekt- eller företagsägare som förstår gruppens användningsområden och kan hantera medlemskapen.</span><span class="sxs-lookup"><span data-stu-id="2f0e9-110">This allows the day-to-day control of group membership to be delegated to team, project, or business owners who understand the business use for the group and can manage its membership.</span></span>

>[!Note]
><span data-ttu-id="2f0e9-111">Grupphantering via självbetjäning finns endast för vissa Azure AD-säkerhetsgrupper och Office 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="2f0e9-111">Self-service group management is available only for Azure AD security and Office 365 groups.</span></span> <span data-ttu-id="2f0e9-112">Den är inte tillgänglig för e-postaktiverade grupper, distributionslistor eller grupper som har synkroniserats från lokala Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="2f0e9-112">It is not available for mail-enabled groups, distribution lists, or any group that has been synchronized from your on-premises Active Directory Domain Services (AD DS).</span></span>
>

<span data-ttu-id="2f0e9-113">Mer information finns i [anvisningarna om att konfigurera en Azure AD-grupp för självbetjäningshantering](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span><span class="sxs-lookup"><span data-stu-id="2f0e9-113">For more information, see the [instructions to configure an Azure AD group for self-service management](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span></span>

<span data-ttu-id="2f0e9-114">Som en mellanliggande kontrollpunkt kan du läsa [avslutsvillkoren](identity-exit-criteria.md#crit-identity-self-service-groups) för det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="2f0e9-114">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-self-service-groups) for this section.</span></span>

<a name="identity-dyn-groups"></a>
## <a name="set-up-dynamic-group-membership"></a><span data-ttu-id="2f0e9-115">Konfigurera dynamiskt gruppmedlemskap</span><span class="sxs-lookup"><span data-stu-id="2f0e9-115">Set up dynamic group membership</span></span>

<span data-ttu-id="2f0e9-116">*Det här är valfritt och gäller både E3- och E5-versionerna av Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="2f0e9-116">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="2f0e9-117">I avsnittet kan du skapa en serie regler som automatiskt lägger till eller tar bort användarkonton som är medlemmar i en Azure AD-grupp.</span><span class="sxs-lookup"><span data-stu-id="2f0e9-117">In this section, you'll create a series of rules that automatically add or remove user accounts as members of an Azure AD group.</span></span> <span data-ttu-id="2f0e9-118">Detta kallas för ett *dynamiskt gruppmedlemskap*.</span><span class="sxs-lookup"><span data-stu-id="2f0e9-118">This is known as *dynamic group membership*.</span></span> <span data-ttu-id="2f0e9-119">Reglerna baseras på användarkontonas attribut, till exempel Avdelning eller Land.</span><span class="sxs-lookup"><span data-stu-id="2f0e9-119">The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="2f0e9-120">Så här tillämpas reglerna:</span><span class="sxs-lookup"><span data-stu-id="2f0e9-120">Here’s how the rules are applied:</span></span>

- <span data-ttu-id="2f0e9-121">Om ett nytt användarkonto matchar alla regler för gruppen, blir det en medlem.</span><span class="sxs-lookup"><span data-stu-id="2f0e9-121">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="2f0e9-122">Om ett användarkonto inte är medlem i gruppen, men dess attribut ändras så att det matchar alla regler för gruppen, blir det medlem i gruppen.</span><span class="sxs-lookup"><span data-stu-id="2f0e9-122">If a user account isn’t a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="2f0e9-123">Om ett användarkonto inte matchar alla regler för gruppen, läggs det inte till i gruppen.</span><span class="sxs-lookup"><span data-stu-id="2f0e9-123">If a user account doesn’t match all the rules for the group, it isn’t added to the group.</span></span>
- <span data-ttu-id="2f0e9-124">Om ett användarkonto är medlem i gruppen, men dess attribut ändras så att det inte längre matchar alla regler för gruppen, tas det bort som medlem i gruppen.</span><span class="sxs-lookup"><span data-stu-id="2f0e9-124">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="2f0e9-125">Om du vill använda dynamiskt medlemskap, måste du först bestämma vilka grupper som ska ha en gemensam uppsättning av användarkontoattribut.</span><span class="sxs-lookup"><span data-stu-id="2f0e9-125">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes.</span></span> <span data-ttu-id="2f0e9-126">Alla medlemmar på säljavdelningen kan t.ex. ingå i gruppen Azure AD-försäljning, baserat på användarkontoattributet Avdelning som är inställd på ”Försäljning”.</span><span class="sxs-lookup"><span data-stu-id="2f0e9-126">For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to “Sales”.</span></span>

<span data-ttu-id="2f0e9-127">I [anvisningarna finns information om hur du skapar och konfigurerar reglerna för en dynamisk Azure AD-grupp](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="2f0e9-127">See the [instructions to create and configure the rules for a dynamic Azure AD group](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

<span data-ttu-id="2f0e9-128">Resultatet från det här avsnittet är:</span><span class="sxs-lookup"><span data-stu-id="2f0e9-128">The results of this section are:</span></span>

- <span data-ttu-id="2f0e9-129">En uppsättning Azure AD-grupper som kan konfigureras för dynamiskt medlemskap</span><span class="sxs-lookup"><span data-stu-id="2f0e9-129">A set of Azure AD groups that can be configured for dynamic membership</span></span>
- <span data-ttu-id="2f0e9-130">En uppsättning regler för varje dynamisk grupp</span><span class="sxs-lookup"><span data-stu-id="2f0e9-130">A set of rules on each dynamic group</span></span>

|||
|:-------|:-----|
|![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="2f0e9-132">Testlabbguide: Automatisera licenser och gruppmedlemskap</span><span class="sxs-lookup"><span data-stu-id="2f0e9-132">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="2f0e9-133">Som en mellanliggande kontrollpunkt kan du läsa [avslutsvillkoren](identity-exit-criteria.md#crit-identity-dyn-groups) för det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="2f0e9-133">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-dyn-groups) for this section.</span></span>

<a name="identity-group-license"></a>
## <a name="set-up-automatic-licensing"></a><span data-ttu-id="2f0e9-134">Konfigurera automatisk licensiering</span><span class="sxs-lookup"><span data-stu-id="2f0e9-134">Set up automatic licensing</span></span>

<span data-ttu-id="2f0e9-135">*Det här är valfritt och gäller både E3- och E5-versionerna av Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="2f0e9-135">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="2f0e9-136">I avsnittet konfigurerar du att säkerhetsgrupper i Azure AD automatiskt tilldelar licenser från en uppsättning prenumerationer till alla medlemmar i gruppen.</span><span class="sxs-lookup"><span data-stu-id="2f0e9-136">In this section, you'll configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="2f0e9-137">Det här kallas för *gruppbaserad licensiering*.</span><span class="sxs-lookup"><span data-stu-id="2f0e9-137">This is known as *group-based licensing*.</span></span> <span data-ttu-id="2f0e9-138">Om du lägger till eller tar bort ett användarkonto från gruppen, kommer licenserna för gruppens prenumerationer att tilldelas eller tas bort automatiskt från användarkontot.</span><span class="sxs-lookup"><span data-stu-id="2f0e9-138">If a user account is added to or removed from the group, the licenses for the group’s subscriptions will be automatically assigned or unassigned from the user account.</span></span>

<span data-ttu-id="2f0e9-139">För Microsoft 365 Enterprise konfigurerar du att Azure AD-säkerhetsgrupperna tilldelar en lämplig Microsoft 365 Enterprise-licens.</span><span class="sxs-lookup"><span data-stu-id="2f0e9-139">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign the appropriate Microsoft 365 Enterprise license.</span></span>

<span data-ttu-id="2f0e9-140">Kontrollera att du har tillräckligt med licenser för alla gruppmedlemmar.</span><span class="sxs-lookup"><span data-stu-id="2f0e9-140">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="2f0e9-141">Om licenserna tar slut kommer nya användare inte att tilldelas några licenser förrän licenserna blir tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="2f0e9-141">If you run out of licenses, new users won’t be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="2f0e9-142">Du bör inte konfigurera *gruppbaserad licensiering* för grupper som innehåller konton för Azure B2B.</span><span class="sxs-lookup"><span data-stu-id="2f0e9-142">You should not configure *group-based licensing* for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="2f0e9-143">Se mer information om [Grunderna i gruppbaserad licensiering i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="2f0e9-143">See additional information on [Group-based licensing basics in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="2f0e9-144">Se [stegen för att konfigurera gruppbaserad licensiering för en Azure-säkerhetsgrupp](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="2f0e9-144">See the [steps to configure group-based licensing for an Azure security group](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>

<span data-ttu-id="2f0e9-145">Resultatet från det här avsnittet är:</span><span class="sxs-lookup"><span data-stu-id="2f0e9-145">The results of this section are:</span></span>

- <span data-ttu-id="2f0e9-146">Du har identifierat vilka säkerhetsgrupper som är lämpliga för gruppbaserad licensiering.</span><span class="sxs-lookup"><span data-stu-id="2f0e9-146">You've identified which security groups are appropriate for group-based licensing.</span></span>
- <span data-ttu-id="2f0e9-147">Du har konfigurerat dessa grupper för gruppbaserad licensiering.</span><span class="sxs-lookup"><span data-stu-id="2f0e9-147">You've configured these groups for group-based licensing.</span></span>

|||
|:-------|:-----|
|![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="2f0e9-149">Testlabbguide: Automatisera licenser och gruppmedlemskap</span><span class="sxs-lookup"><span data-stu-id="2f0e9-149">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="2f0e9-150">Som en mellanliggande kontrollpunkt kan du läsa [avslutsvillkoren](identity-exit-criteria.md#crit-identity-group-license) för det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="2f0e9-150">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-group-license) for this section.</span></span>

|||
|:-------|:-----|
|![Steg 6](../media/stepnumbers/Step6.png)| [<span data-ttu-id="2f0e9-152">Konfigurera Identity Governance</span><span class="sxs-lookup"><span data-stu-id="2f0e9-152">Configure identity governance</span></span>](identity-configure-identity-governance.md) |
