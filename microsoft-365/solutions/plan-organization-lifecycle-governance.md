---
title: Planera organisation och livscykler för Microsoft 365-grupper och Microsoft Teams
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Lean-alternativ för hantering av livs cykeln för samarbets verktyg i Microsoft 365
ms.openlocfilehash: 4d779701d241fc7178ab759063be1b8cdf2e960c
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613026"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a><span data-ttu-id="01502-103">Planera organisation och livscykler för Microsoft 365-grupper och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="01502-103">Plan organization and lifecycle governance for Microsoft 365 groups and Microsoft Teams</span></span>

<span data-ttu-id="01502-104">Microsoft 365-grupper har många verktyg för att implementera de styrnings funktioner som din organisation behöver.</span><span class="sxs-lookup"><span data-stu-id="01502-104">Microsoft 365 groups has a rich set of tools to implement the governance capabilities your organization requires.</span></span> 

<span data-ttu-id="01502-105">I följande avsnitt beskrivs funktionerna, rekommenderar de bästa metoderna och ger vägledning för att ställa rätt frågor för att fastställa kraven för styrning och hur de ska mötas.</span><span class="sxs-lookup"><span data-stu-id="01502-105">The following section describes the capabilities, recommends best practices, and provides guidance to ask the right questions to determine the requirements for governance, and how to meet them.</span></span>

## <a name="control-who-can-create-microsoft-365-groups"></a><span data-ttu-id="01502-106">Kontrol lera vilka som kan skapa Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="01502-106">Control who can create Microsoft 365 groups</span></span>

<span data-ttu-id="01502-107">Grupper kan skapas av slutanvändare från flera slut punkter inklusive Outlook, SharePoint, team och andra miljöer.</span><span class="sxs-lookup"><span data-stu-id="01502-107">Groups can be created by end-users from multiple end-points including Outlook, SharePoint, Teams, and other environments.</span></span>

![bild DESC](../media/04.png)

<span data-ttu-id="01502-109">Vi rekommenderar starkt att du använder sig själv för att stärka grupp ägarna och hjälpa användare att få jobbet gjort lättare.</span><span class="sxs-lookup"><span data-stu-id="01502-109">We highly recommend self-service to empower group owners and help users get their work done more easily.</span></span> <span data-ttu-id="01502-110">Om du begränsar grupp-och grupp skapande kan användarna bli långsamma eftersom många Microsoft 365-tjänster kräver att grupper skapas för att tjänsten ska fungera.</span><span class="sxs-lookup"><span data-stu-id="01502-110">Limiting group and team creation can slow users productivity because many Microsoft 365 services require that groups be created for the service to function.</span></span>

<span data-ttu-id="01502-111">Överväg följande styr alternativ för att skapa grupper:</span><span class="sxs-lookup"><span data-stu-id="01502-111">Consider the following governance options for groups creation:</span></span>

- <span data-ttu-id="01502-112">Om du vill begränsa grupp sprawl kan du använda [grupper för förfallo principer](microsoft-365-groups-expiration-policy.md) för att automatiskt ta bort grupper som inte används.</span><span class="sxs-lookup"><span data-stu-id="01502-112">To limit group sprawl, use [groups expiration policies](microsoft-365-groups-expiration-policy.md) to automatically delete groups that are not being used.</span></span>
- <span data-ttu-id="01502-113">Begränsa grupp skapande till medlemmar i en [säkerhets grupp med dynamiskt medlemskap](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) som innehåller, till exempel, alla heltids anställda.</span><span class="sxs-lookup"><span data-stu-id="01502-113">Limit group creation to members of a [security groups with dynamic membership](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) containing, for example, all full-time employees.</span></span>
- <span data-ttu-id="01502-114">Begränsa grupp skapande till en säkerhets grupp och Kräv att användare ska kunna slutföra utbildning i organisationens principer för grup användning för att bli medlemmar i säkerhets gruppen.</span><span class="sxs-lookup"><span data-stu-id="01502-114">Limit group creation to a security group and require users to complete training in your organization's group usage policies in order to become members of the security group.</span></span>

<span data-ttu-id="01502-115">Om du vill begränsa vem som kan skapa grupper läser du [Hantera vilka som kan skapa Microsoft 365-grupper](manage-creation-of-groups.md) för information om hur du konfigurerar detta.</span><span class="sxs-lookup"><span data-stu-id="01502-115">If you want to limit who can create groups, see [Manage who can create Microsoft 365 groups](manage-creation-of-groups.md) for information on how to configure this.</span></span>

## <a name="group-delete-restore-and-archiving"></a><span data-ttu-id="01502-116">Grupp borttagning, återställning och arkivering</span><span class="sxs-lookup"><span data-stu-id="01502-116">Group delete, restore, and archiving</span></span>

<span data-ttu-id="01502-117">När en Microsoft 365-grupp tas bort sparas den som standard i 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="01502-117">When a Microsoft 365 group is deleted, by default it's retained for 30 days.</span></span> <span data-ttu-id="01502-118">Den här 30-dagarsperioden kallas "mjuk borttagning" eftersom du fortfarande kan återställa gruppen.</span><span class="sxs-lookup"><span data-stu-id="01502-118">This 30-day period is called "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="01502-119">Efter 30 dagar tas gruppen och det tillhörande innehållet bort permanent och kan inte återställas.</span><span class="sxs-lookup"><span data-stu-id="01502-119">After 30 days, the group and associated content is permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="01502-120">Om du har bevarande principer för att behålla chatt, filer eller e-post bevaras dessa objekt efter att gruppen har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="01502-120">If you have retention policies in place to retain chat, files, or mail, those items will be preserved after the group is deleted.</span></span> <span data-ttu-id="01502-121">Läs [mer om bevarande principer](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) .</span><span class="sxs-lookup"><span data-stu-id="01502-121">See [Learn about retention policies](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) for details.</span></span>

<span data-ttu-id="01502-122">Om du vill ta bort en grupp men behålla innehållet från en eller flera av de gruppanslutna tjänsterna läser du [arkivera grupper, team och Yammer](end-life-cycle-groups-teams-sites-yammer.md) efter information.</span><span class="sxs-lookup"><span data-stu-id="01502-122">If you want to delete a group but preserve the content from one or more of the group-connected services, see [Archive groups, teams, and Yammer](end-life-cycle-groups-teams-sites-yammer.md) for information.</span></span>

## <a name="group-naming-policy"></a><span data-ttu-id="01502-123">Namn princip för grupper</span><span class="sxs-lookup"><span data-stu-id="01502-123">Group naming policy</span></span>

<span data-ttu-id="01502-124">En namn princip för grupper kan hjälpa dig att styra grupper på två sätt:</span><span class="sxs-lookup"><span data-stu-id="01502-124">A groups naming policy can help you govern groups in two ways:</span></span>

- <span data-ttu-id="01502-125">En princip för prefix/namnsuffix kan användas för att tvinga fasta strängar eller Azure AD-attribut i början eller slutet av ett grupp namn och dess associerade e-postadress.</span><span class="sxs-lookup"><span data-stu-id="01502-125">A prefix/suffix naming policy can be used to enforce fixed strings or Azure AD attributes at the beginning or end of a group name and its associated email address.</span></span> <span data-ttu-id="01502-126">Genom att göra detta kan du se till exempel avdelnings namn eller områden i grupp namn.</span><span class="sxs-lookup"><span data-stu-id="01502-126">By doing this, you can ensure the inclusion of, for example, department names or regions in group names.</span></span>
- <span data-ttu-id="01502-127">En princip för blockerade ord kan säkerställa att vissa ord, till exempel namn på chefer, inte används i grupp namn.</span><span class="sxs-lookup"><span data-stu-id="01502-127">A blocked words policy can ensure that certain words, such as the names of executives, are not used in group names.</span></span>

<span data-ttu-id="01502-128">Namngivnings principer tillämpas när grupper skapas från någon av de gruppanslutna tjänsterna.</span><span class="sxs-lookup"><span data-stu-id="01502-128">Naming policies are applied when groups are created from any of the group-connected services.</span></span>

<span data-ttu-id="01502-129">Om du bestämmer dig för att använda namngivnings principer för grupper kan du läsa mer i [Microsoft 365 grupper för namngivnings principer](groups-naming-policy.md).</span><span class="sxs-lookup"><span data-stu-id="01502-129">If you decide to use naming policies for groups, see [Microsoft 365 Groups naming policy](groups-naming-policy.md).</span></span>

## <a name="group-expiration-policy"></a><span data-ttu-id="01502-130">Policy för giltighets tid för grupp</span><span class="sxs-lookup"><span data-stu-id="01502-130">Group expiration policy</span></span>

<span data-ttu-id="01502-131">Du kan ange en förfallo period och alla grupper som når slutet av perioden och som inte förnyas, tas bort.</span><span class="sxs-lookup"><span data-stu-id="01502-131">You can specify an expiration period and any group that reaches the end of that period, and is not renewed, will be deleted.</span></span> <span data-ttu-id="01502-132">Utgångs perioden börjar när gruppen skapas, eller vid det datum då den senast förnyades.</span><span class="sxs-lookup"><span data-stu-id="01502-132">The expiration period begins when the group is created, or on the date it was last renewed.</span></span>

<span data-ttu-id="01502-133">När du har ställt in grupper som förfaller:</span><span class="sxs-lookup"><span data-stu-id="01502-133">Once you set groups to expire:</span></span>
- <span data-ttu-id="01502-134">Ägarna till gruppen meddelas om att förnya gruppen efter att ha gått ut nära.</span><span class="sxs-lookup"><span data-stu-id="01502-134">Owners of the group are notified to renew the group as the expiration nears.</span></span>
- <span data-ttu-id="01502-135">Aktiva grupper förnyas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="01502-135">Active groups are renewed automatically.</span></span>
- <span data-ttu-id="01502-136">Alla grupper som inte är förnyade raderas.</span><span class="sxs-lookup"><span data-stu-id="01502-136">Any group that is not renewed is deleted.</span></span>
- <span data-ttu-id="01502-137">Alla grupper som tas bort kan återställas inom 30 dagar av grupp ägarna eller administratören.</span><span class="sxs-lookup"><span data-stu-id="01502-137">Any group that is deleted can be restored within 30 days by the group owners or the admin.</span></span>

<span data-ttu-id="01502-138">Principer för förfallo dag är ett bra sätt att begränsa gruppens sprawl genom att se till att grupper som inte längre används tas bort.</span><span class="sxs-lookup"><span data-stu-id="01502-138">Expiration policies are a good way to limit group sprawl by ensuring that groups that are no longer in use are deleted.</span></span> <span data-ttu-id="01502-139">Om du vill skapa en giltighets princip för en grupp kan du läsa [Microsoft 365-gruppens förfallo princip](microsoft-365-groups-expiration-policy.md).</span><span class="sxs-lookup"><span data-stu-id="01502-139">If you want to create a group expiration policy, see [Microsoft 365 Group Expiration Policy](microsoft-365-groups-expiration-policy.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="01502-140">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="01502-140">Related topics</span></span>

[<span data-ttu-id="01502-141">Planerings steg-för-steg-samarbete för samarbets styrning</span><span class="sxs-lookup"><span data-stu-id="01502-141">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="01502-142">Skapa en plan för hantering av samarbete</span><span class="sxs-lookup"><span data-stu-id="01502-142">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)
