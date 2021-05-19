---
title: Planera styrning av organisation och livscykel för Microsoft 365 grupper och Microsoft Teams
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
recommendations: false
description: Mer information om alternativ för livscykelstyrning för samarbetsverktyg i Microsoft 365
ms.openlocfilehash: 7d88618b75ef731bf38df029970efdc05f3eea5a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538825"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a><span data-ttu-id="52963-103">Planera styrning av organisation och livscykel för Microsoft 365 grupper och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="52963-103">Plan organization and lifecycle governance for Microsoft 365 groups and Microsoft Teams</span></span>

<span data-ttu-id="52963-104">Microsoft 365 grupper har en omfattande uppsättning verktyg för att implementera de hanteringsfunktioner som din organisation kräver.</span><span class="sxs-lookup"><span data-stu-id="52963-104">Microsoft 365 groups has a rich set of tools to implement the governance capabilities your organization requires.</span></span> 

<span data-ttu-id="52963-105">I följande avsnitt beskrivs funktionerna, rekommendationerna för metodtips och vägledning för att ställa rätt frågor för att avgöra kraven för styrning och hur du uppfyller dem.</span><span class="sxs-lookup"><span data-stu-id="52963-105">The following section describes the capabilities, recommends best practices, and provides guidance to ask the right questions to determine the requirements for governance, and how to meet them.</span></span>

## <a name="control-who-can-create-microsoft-365-groups"></a><span data-ttu-id="52963-106">Styra vem som kan Microsoft 365 grupper</span><span class="sxs-lookup"><span data-stu-id="52963-106">Control who can create Microsoft 365 groups</span></span>

<span data-ttu-id="52963-107">Grupper kan skapas av slutanvändarna från flera ändpunkter, Outlook, SharePoint, Teams och andra miljöer.</span><span class="sxs-lookup"><span data-stu-id="52963-107">Groups can be created by end-users from multiple end-points including Outlook, SharePoint, Teams, and other environments.</span></span>

![image desc](../media/04.png)

<span data-ttu-id="52963-109">Vi rekommenderar självbetjäning för att ge gruppägare möjlighet och hjälpa användarna att få jobbet gjort enklare.</span><span class="sxs-lookup"><span data-stu-id="52963-109">We highly recommend self-service to empower group owners and help users get their work done more easily.</span></span> <span data-ttu-id="52963-110">Att begränsa skapandet av grupper kan leda till långsammare produktivitet för användare Microsoft 365 tjänster kräver att grupper skapas för att tjänsten ska fungera.</span><span class="sxs-lookup"><span data-stu-id="52963-110">Limiting group and team creation can slow users productivity because many Microsoft 365 services require that groups be created for the service to function.</span></span>

<span data-ttu-id="52963-111">Tänk på följande styrningsalternativ för att skapa grupper:</span><span class="sxs-lookup"><span data-stu-id="52963-111">Consider the following governance options for groups creation:</span></span>

- <span data-ttu-id="52963-112">Om du vill begränsa gruppsnålning [använder du förfalloprinciper](microsoft-365-groups-expiration-policy.md) för grupper för att automatiskt ta bort grupper som inte används.</span><span class="sxs-lookup"><span data-stu-id="52963-112">To limit group sprawl, use [groups expiration policies](microsoft-365-groups-expiration-policy.md) to automatically delete groups that are not being used.</span></span>
- <span data-ttu-id="52963-113">Begränsa skapandet av grupper till medlemmar [i en säkerhetsgrupp med dynamiskt](/azure/active-directory/users-groups-roles/groups-create-rule) medlemskap, t.ex. alla heltidsanställda.</span><span class="sxs-lookup"><span data-stu-id="52963-113">Limit group creation to members of a [security groups with dynamic membership](/azure/active-directory/users-groups-roles/groups-create-rule) containing, for example, all full-time employees.</span></span>
- <span data-ttu-id="52963-114">Begränsa skapandet av grupper till en säkerhetsgrupp och kräver att användarna slutför utbildning i organisationens principer för gruppanvändning för att bli medlemmar i säkerhetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="52963-114">Limit group creation to a security group and require users to complete training in your organization's group usage policies in order to become members of the security group.</span></span>

<span data-ttu-id="52963-115">Om du vill begränsa vem som kan skapa grupper kan du gå till Hantera vem [som kan Microsoft 365 grupper](manage-creation-of-groups.md) för information om hur du konfigurerar detta.</span><span class="sxs-lookup"><span data-stu-id="52963-115">If you want to limit who can create groups, see [Manage who can create Microsoft 365 groups](manage-creation-of-groups.md) for information on how to configure this.</span></span>

## <a name="group-delete-restore-and-archiving"></a><span data-ttu-id="52963-116">Gruppera borttagning, återställning och arkivering</span><span class="sxs-lookup"><span data-stu-id="52963-116">Group delete, restore, and archiving</span></span>

<span data-ttu-id="52963-117">När en Microsoft 365 grupp tas bort behålls den som standard i 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="52963-117">When a Microsoft 365 group is deleted, by default it's retained for 30 days.</span></span> <span data-ttu-id="52963-118">Den här 30-dagarsperioden kallas "mjuk borttagning" eftersom du fortfarande kan återställa gruppen.</span><span class="sxs-lookup"><span data-stu-id="52963-118">This 30-day period is called "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="52963-119">Efter 30 dagar tas gruppen och det tillhörande innehållet bort permanent och kan inte återställas.</span><span class="sxs-lookup"><span data-stu-id="52963-119">After 30 days, the group and associated content is permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="52963-120">Om du har kvarhållningsprinciper för att behålla chatt, filer eller e-post, bevaras de objekten när gruppen har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="52963-120">If you have retention policies in place to retain chat, files, or mail, those items will be preserved after the group is deleted.</span></span> <span data-ttu-id="52963-121">Mer [information finns i Läs mer om](../compliance/retention.md) bevarandeprinciper.</span><span class="sxs-lookup"><span data-stu-id="52963-121">See [Learn about retention policies](../compliance/retention.md) for details.</span></span>

<span data-ttu-id="52963-122">Information om hur du tar bort en grupp men bevarar innehållet från en eller flera av de gruppanslutna tjänsterna finns i [Arkivera grupper,](end-life-cycle-groups-teams-sites-yammer.md) grupper och Yammer för information.</span><span class="sxs-lookup"><span data-stu-id="52963-122">If you want to delete a group but preserve the content from one or more of the group-connected services, see [Archive groups, teams, and Yammer](end-life-cycle-groups-teams-sites-yammer.md) for information.</span></span>

## <a name="group-naming-policy"></a><span data-ttu-id="52963-123">Gruppnamnprincip</span><span class="sxs-lookup"><span data-stu-id="52963-123">Group naming policy</span></span>

<span data-ttu-id="52963-124">Med namngivningsprincipen för grupper kan du styra grupperna på två sätt:</span><span class="sxs-lookup"><span data-stu-id="52963-124">A groups naming policy can help you govern groups in two ways:</span></span>

- <span data-ttu-id="52963-125">En prefix-/suffixnamnsprincip kan användas för att framtvinga fasta strängar eller Azure AD-attribut i början eller slutet av ett gruppnamn och dess tillhörande e-postadress.</span><span class="sxs-lookup"><span data-stu-id="52963-125">A prefix/suffix naming policy can be used to enforce fixed strings or Azure AD attributes at the beginning or end of a group name and its associated email address.</span></span> <span data-ttu-id="52963-126">På så sätt kan du säkerställa att exempelvis avdelningsnamn eller regioner i gruppnamn tas med.</span><span class="sxs-lookup"><span data-stu-id="52963-126">By doing this, you can ensure the inclusion of, for example, department names or regions in group names.</span></span>
- <span data-ttu-id="52963-127">En princip för blockerade ord kan säkerställa att vissa ord, till exempel namnen på chefer, inte används i gruppnamn.</span><span class="sxs-lookup"><span data-stu-id="52963-127">A blocked words policy can ensure that certain words, such as the names of executives, are not used in group names.</span></span>

<span data-ttu-id="52963-128">Namnprinciper tillämpas när grupper skapas från någon av de gruppanslutna tjänsterna.</span><span class="sxs-lookup"><span data-stu-id="52963-128">Naming policies are applied when groups are created from any of the group-connected services.</span></span>

<span data-ttu-id="52963-129">Om du bestämmer dig för att använda namnprinciper för grupper kan [du Microsoft 365 Namnprincip för grupper.](groups-naming-policy.md)</span><span class="sxs-lookup"><span data-stu-id="52963-129">If you decide to use naming policies for groups, see [Microsoft 365 Groups naming policy](groups-naming-policy.md).</span></span>

## <a name="group-expiration-policy"></a><span data-ttu-id="52963-130">Förfalloprincip för grupp</span><span class="sxs-lookup"><span data-stu-id="52963-130">Group expiration policy</span></span>

<span data-ttu-id="52963-131">Du kan ange en förfalloperiod så tas alla grupper som når slutet av perioden bort, och som inte förnyas.</span><span class="sxs-lookup"><span data-stu-id="52963-131">You can specify an expiration period and any group that reaches the end of that period, and is not renewed, will be deleted.</span></span> <span data-ttu-id="52963-132">Förfallotiden börjar när gruppen skapas eller det datum då den senast förnyades.</span><span class="sxs-lookup"><span data-stu-id="52963-132">The expiration period begins when the group is created, or on the date it was last renewed.</span></span>

<span data-ttu-id="52963-133">När du ställer in grupper så att de upphör att gälla:</span><span class="sxs-lookup"><span data-stu-id="52963-133">Once you set groups to expire:</span></span>
- <span data-ttu-id="52963-134">Ägare av gruppen meddelas att förnya gruppen när utgångsdatumet närmar sig.</span><span class="sxs-lookup"><span data-stu-id="52963-134">Owners of the group are notified to renew the group as the expiration nears.</span></span>
- <span data-ttu-id="52963-135">Aktiva grupper förnyas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="52963-135">Active groups are renewed automatically.</span></span>
- <span data-ttu-id="52963-136">Alla grupper som inte har förnyats tas bort.</span><span class="sxs-lookup"><span data-stu-id="52963-136">Any group that is not renewed is deleted.</span></span>
- <span data-ttu-id="52963-137">Alla grupper som tas bort kan återställas inom 30 dagar av gruppägarna eller administratören.</span><span class="sxs-lookup"><span data-stu-id="52963-137">Any group that is deleted can be restored within 30 days by the group owners or the admin.</span></span>

<span data-ttu-id="52963-138">Förfalloprinciper är ett bra sätt att begränsa gruppsnålning genom att se till att grupper som inte längre används tas bort.</span><span class="sxs-lookup"><span data-stu-id="52963-138">Expiration policies are a good way to limit group sprawl by ensuring that groups that are no longer in use are deleted.</span></span> <span data-ttu-id="52963-139">Information om hur du skapar en förfalloprincip för grupper finns [Microsoft 365 förfalloprincip för grupper.](microsoft-365-groups-expiration-policy.md)</span><span class="sxs-lookup"><span data-stu-id="52963-139">If you want to create a group expiration policy, see [Microsoft 365 Group Expiration Policy](microsoft-365-groups-expiration-policy.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="52963-140">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="52963-140">Related topics</span></span>

[<span data-ttu-id="52963-141">Planering av samarbetsstyrning steg för steg</span><span class="sxs-lookup"><span data-stu-id="52963-141">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="52963-142">Skapa din plan för samarbetesstyrning</span><span class="sxs-lookup"><span data-stu-id="52963-142">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="52963-143">Ta bort en tidigare anställd och säkra data</span><span class="sxs-lookup"><span data-stu-id="52963-143">Remove a former employee and secure data</span></span>](/microsoft-365/admin/add-users/remove-former-employee)
