---
title: Mer information om kvarhållning för Yammer
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Mer information om de kvarhållningsprinciper som gäller för Yammer.
ms.openlocfilehash: d4988eee419a38497d4fa35cdb3e2f7fec103688
ms.sourcegitcommit: 4d26a57c37ff7efbb8d235452c78498b06a59714
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53052933"
---
# <a name="learn-about-retention-for-yammer"></a><span data-ttu-id="492cd-103">Mer information om kvarhållning för Yammer</span><span class="sxs-lookup"><span data-stu-id="492cd-103">Learn about retention for Yammer</span></span>

><span data-ttu-id="492cd-104">*[Vägledning för säkerhet och efterlevnad med licensiering i Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="492cd-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

> [!NOTE]
> <span data-ttu-id="492cd-105">Den här funktionen är i förhandsversion och kan komma att ändras.</span><span class="sxs-lookup"><span data-stu-id="492cd-105">This feature is in preview and subject to change.</span></span>

<span data-ttu-id="492cd-106">Informationen i den här artikeln kompletterar [Mer information om kvarhållning](retention.md) eftersom den innehåller specifik information för Yammer.</span><span class="sxs-lookup"><span data-stu-id="492cd-106">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Yammer.</span></span>

<span data-ttu-id="492cd-107">För andra arbetsbelastningar, se:</span><span class="sxs-lookup"><span data-stu-id="492cd-107">For other workloads, see:</span></span>

- [<span data-ttu-id="492cd-108">Mer information om kvarhållning för SharePoint och OneDrive</span><span class="sxs-lookup"><span data-stu-id="492cd-108">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="492cd-109">Mer information om kvarhållning för Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="492cd-109">Learn about retention for Microsoft Teams</span></span>](retention-policies-teams.md)
- [<span data-ttu-id="492cd-110">Lär dig mer om kvarhållning för Exchange</span><span class="sxs-lookup"><span data-stu-id="492cd-110">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a><span data-ttu-id="492cd-111">Vad ingår för kvarhållning och borttagning</span><span class="sxs-lookup"><span data-stu-id="492cd-111">What's included for retention and deletion</span></span>

<span data-ttu-id="492cd-112">Följande Yammer-objekt kan behållas och tas bort med kvarhållningsprinciper för Yammer: Communitymeddelanden och privata meddelanden.</span><span class="sxs-lookup"><span data-stu-id="492cd-112">The following Yammer items can be retained and deleted by using retention policies for Yammer: Community messages and private messages.</span></span>

<span data-ttu-id="492cd-113">Reaktioner från andra i form av uttryckssymboler tas inte med i dessa meddelanden.</span><span class="sxs-lookup"><span data-stu-id="492cd-113">Reactions from others in the form of emoticons are not included in these messages.</span></span>

## <a name="how-retention-works-with-yammer"></a><span data-ttu-id="492cd-114">Så fungerar kvarhållning för Yammer</span><span class="sxs-lookup"><span data-stu-id="492cd-114">How retention works with Yammer</span></span>

<span data-ttu-id="492cd-115">Du kan använda en kvarhållningsprincip för att behålla och ta bort communitymeddelanden och privata meddelanden i Yammer.</span><span class="sxs-lookup"><span data-stu-id="492cd-115">You can use a retention policy to retain and delete community messages and private messages in Yammer.</span></span> <span data-ttu-id="492cd-116">Privata meddelanden lagras i en dold mapp i postlådan för varje användare som ingår i meddelandet och communitymeddelanden lagras i en liknande dold mapp i gruppostlådan för communityn.</span><span class="sxs-lookup"><span data-stu-id="492cd-116">Private messages are stored in a hidden folder in the mailbox of each user included in the message, and community messages are stored in a similar hidden folder in the group mailbox for the community.</span></span>

<span data-ttu-id="492cd-117">Yammer-meddelanden påverkas inte av kvarhållningsprinciper som har konfigurerats för användar- eller gruppostlådor.</span><span class="sxs-lookup"><span data-stu-id="492cd-117">Yammer messages are not affected by retention policies that are configured for user or group mailboxes.</span></span> <span data-ttu-id="492cd-118">Även om Yammer-meddelanden lagras i Exchange omfattas dessa Yammer-data endast av en kvarhållningsprincip som är konfigurerad för platserna **Community-meddelanden i Yammer** och **Användarmeddelanden i Yammer**.</span><span class="sxs-lookup"><span data-stu-id="492cd-118">Even though Yammer messages are stored in Exchange, this Yammer data is included only by a retention policy that's configured for the **Yammer community messages** and **Yammer user messages** locations.</span></span>

> [!NOTE]
> <span data-ttu-id="492cd-119">Om en användare ingår i en aktiv kvarhållningsprincip som behåller Yammer-data och du tar bort postlådan för en användare som ingår i den principen, konverteras postlådan till en [inaktiv postlåda](inactive-mailboxes-in-office-365.md) för att Yammer-datan ska behållas.</span><span class="sxs-lookup"><span data-stu-id="492cd-119">If a user is included in an active retention policy that retains Yammer data and you a delete a mailbox of a user who is included in this policy, to retain the Yammer data, the mailbox is converted into an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="492cd-120">Om du inte behöver behålla Yammer-datan för användaren exkluderar du användarkontot från kvarhållningsprincipen innan du tar bort postlådan.</span><span class="sxs-lookup"><span data-stu-id="492cd-120">If you don't need to retain this Yammer data for the user, exclude the user account from the retention policy before you delete their mailbox.</span></span>

<span data-ttu-id="492cd-121">När en kvarhållningsprincip har konfigurerats för Yammer-meddelanden, utvärderar ett tidsinställt jobb från Exchange-tjänsten regelbundet objekt i den dolda mappen där dessa Yammer-meddelanden lagras.</span><span class="sxs-lookup"><span data-stu-id="492cd-121">After a retention policy is configured for Yammer messages, a timer job from the Exchange service periodically evaluates items in the hidden folder where these Yammer messages are stored.</span></span> <span data-ttu-id="492cd-122">Det tidsinställda jobbet tar upp till sju dagar att köra.</span><span class="sxs-lookup"><span data-stu-id="492cd-122">The timer job takes up to seven days to run.</span></span> <span data-ttu-id="492cd-123">När kvarhållningsperioden för objekten har upphört flyttas de till mappen SubstrateHolds. Det är en dold mapp som finns i varje användar- eller gruppostlåda där ej permanent borttagna objekt lagras innan de tas bort permanent.</span><span class="sxs-lookup"><span data-stu-id="492cd-123">When these items have expired their retention period, they are moved to the SubstrateHolds folder—a hidden folder that's in every user or group mailbox to store "soft-deleted" items before they are permanently deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="492cd-124">På grund av [första principen om kvarhållning](retention.md#the-principles-of-retention-or-what-takes-precedence)inaktiveras permanent borttagning alltid om samma objekt måste behållas på grund av en annan kvarhållningsprincip, eller om det finns eDiscovery som gäller för juridiska skäl eller av juridiska skäl.</span><span class="sxs-lookup"><span data-stu-id="492cd-124">Because of the [first principle of retention](retention.md#the-principles-of-retention-or-what-takes-precedence), permanent deletion is always suspended if the same item must be retained because of another retention policy, or it is under eDiscovery holds for legal or investigative reasons.</span></span>

<span data-ttu-id="492cd-125">När en kvarhållningsprincip har konfigurerats för Yammer-meddelanden beror sökvägarna till innehållet på om kvarhållningsprincipen ska behålla och sedan ta bort, endast behålla eller endast ta bort.</span><span class="sxs-lookup"><span data-stu-id="492cd-125">After a retention policy is configured for Yammer messages, the paths the content takes depend on whether the retention policy is to retain and then delete, to retain only, or delete only.</span></span>

<span data-ttu-id="492cd-126">När kvarhållningsprincipen ska behålla och sedan ta bort:</span><span class="sxs-lookup"><span data-stu-id="492cd-126">When the retention policy is to retain and then delete:</span></span>

![Diagram med kvarhållningsflöde för Yammer-meddelanden](../media/yammerretentionlifecycle.png)

<span data-ttu-id="492cd-128">För de två sökvägarna i diagrammet:</span><span class="sxs-lookup"><span data-stu-id="492cd-128">For the two paths in the diagram:</span></span>

1. <span data-ttu-id="492cd-129">**Om ett Yammer-meddelande redigeras eller tas bort** av användaren under kvarhållningsperioden, kopieras det ursprungliga meddelandet omedelbart (om det redigeras) eller flyttas (om det tas bort) till mappen SubstrateHolds.</span><span class="sxs-lookup"><span data-stu-id="492cd-129">**If a Yammer message is edited or deleted** by the user during the retention period, the original message is immediately copied (if edited) or moved (if deleted) to the SubstrateHolds folder.</span></span> <span data-ttu-id="492cd-130">Meddelandet lagras där tills kvarhållningsperioden upphör och meddelandet tas bort permanent.</span><span class="sxs-lookup"><span data-stu-id="492cd-130">The message is stored there until the retention period expires and then the message is immediately permanently deleted.</span></span>

2. <span data-ttu-id="492cd-131">**Om ett Yammer-meddelande inte tas bort** och för aktuella meddelanden efter redigering, flyttas meddelandet till mappen SubstrateHolds efter att kvarhållningsperioden har upphört.</span><span class="sxs-lookup"><span data-stu-id="492cd-131">**If a Yammer message is not deleted** and for current messages after editing, the message is moved to the SubstrateHolds folder after the retention period expires.</span></span> <span data-ttu-id="492cd-132">Den här åtgärden tar upp till sju dagar från utgångsdatumet.</span><span class="sxs-lookup"><span data-stu-id="492cd-132">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="492cd-133">När meddelandet finns i mappen SubstrateHolds tas det omedelbart bort permanent.</span><span class="sxs-lookup"><span data-stu-id="492cd-133">When the message is in the SubstrateHolds folder, it is then immediately permanently deleted.</span></span> 

> [!NOTE]
> <span data-ttu-id="492cd-134">Meddelanden i mappen SubstrateHolds är sökbara med eDiscovery-verktyg.</span><span class="sxs-lookup"><span data-stu-id="492cd-134">Messages in the SubstrateHolds folder are searchable by eDiscovery tools.</span></span> <span data-ttu-id="492cd-135">Tills meddelandena tas bort permanent (i mappen SubstrateHolds) förblir de sökbara med eDiscovery-verktyg.</span><span class="sxs-lookup"><span data-stu-id="492cd-135">Until messages are permanently deleted (in the SubstrateHolds folder), they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="492cd-136">När kvarhållningsprincipen endast ska behålla eller endast ta bort, är innehållssökvägarna varianter av att behålla eller ta bort.</span><span class="sxs-lookup"><span data-stu-id="492cd-136">When the retention policy is retain-only, or delete-only, the content's paths are variations of retain and delete.</span></span>

### <a name="content-paths-for-retain-only-retention-policy"></a><span data-ttu-id="492cd-137">Innehållssökvägar för kvarhållningsprincip som endast behåller</span><span class="sxs-lookup"><span data-stu-id="492cd-137">Content paths for retain-only retention policy</span></span>

1. <span data-ttu-id="492cd-138">**Om ett Yammer-meddelande redigeras eller tas bort**: En kopia av det ursprungliga meddelandet skapas omedelbart i mappen SubstrateHolds och behålls där tills kvarhållningsperioden upphör.</span><span class="sxs-lookup"><span data-stu-id="492cd-138">**If a Yammer message is edited or deleted**: A copy of the original message is immediately created in the SubstrateHolds folder and retained there until the retention period expires.</span></span> <span data-ttu-id="492cd-139">Meddelandet tas sedan bort permanent från mappen SubstrateHolds omedelbart.</span><span class="sxs-lookup"><span data-stu-id="492cd-139">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="492cd-140">**Om Yammer-meddelandet inte ändras eller tas bort** och för aktuella meddelanden efter redigering under kvarhållningsperioden: Ingenting händer före och efter kvarhållningsperioden, meddelandet finns kvar på sin ursprungliga plats.</span><span class="sxs-lookup"><span data-stu-id="492cd-140">**If the Yammer message is not modified or deleted** and for current messages after editing during the retention period: Nothing happens before and after the retention period; the message remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-policy"></a><span data-ttu-id="492cd-141">Innehållssökvägar för kvarhållningsprincip som endast tar bort</span><span class="sxs-lookup"><span data-stu-id="492cd-141">Content paths for delete-only retention policy</span></span>

1. <span data-ttu-id="492cd-142">**Om Yammer-meddelandet inte tas bort** under kvarhållningsperioden: Meddelandet flyttas till mappen SubstrateHolds efter kvarhållningsperioden.</span><span class="sxs-lookup"><span data-stu-id="492cd-142">**If the Yammer message is not deleted** during the retention period: At the end of the retention period, the message is moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="492cd-143">Den här åtgärden tar upp till sju dagar från utgångsdatumet.</span><span class="sxs-lookup"><span data-stu-id="492cd-143">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="492cd-144">Meddelandet tas sedan bort permanent från mappen SubstrateHolds omedelbart.</span><span class="sxs-lookup"><span data-stu-id="492cd-144">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="492cd-145">**Om Yammer-meddelandet tas bort av användaren** under perioden flyttas objektet omedelbart till mappen SubstrateHolds där det tas bort omedelbart och permanent.</span><span class="sxs-lookup"><span data-stu-id="492cd-145">**If the Yammer message is deleted by the user** during the period, the item is immediately moved to the SubstrateHolds folder where it is immediately permanently deleted.</span></span>


## <a name="messages-and-external-users"></a><span data-ttu-id="492cd-146">Meddelanden och externa användare</span><span class="sxs-lookup"><span data-stu-id="492cd-146">Messages and external users</span></span>

<span data-ttu-id="492cd-147">Som standard gäller en kvarhållningsprincip för användarmeddelanden i Yammer alla användare i organisationen, men inte för externa användare.</span><span class="sxs-lookup"><span data-stu-id="492cd-147">By default, a retention policy for Yammer user messages applies to all users in your organization, but not external users.</span></span> <span data-ttu-id="492cd-148">Du kan tillämpa en kvarhållningsprincip på externa användare om du använder **Välj användare** och anger deras konto.</span><span class="sxs-lookup"><span data-stu-id="492cd-148">You can apply a retention policy to external users if you use the **Choose user** and specify their account.</span></span> 

<span data-ttu-id="492cd-149">För närvarande stöds inte Azure B2B-gästanvändare.</span><span class="sxs-lookup"><span data-stu-id="492cd-149">At this time, Azure B2B guest users are not supported.</span></span>

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="492cd-150">När en användare lämnar organisationen</span><span class="sxs-lookup"><span data-stu-id="492cd-150">When a user leaves the organization</span></span> 

<span data-ttu-id="492cd-151">Om användare lämnar organisationen och deras Microsoft 365-konto tas bort, lagras deras Yammer-användarmeddelanden som ska behållas i en inaktiv postlåda.</span><span class="sxs-lookup"><span data-stu-id="492cd-151">If a user leaves your organization and their Microsoft 365 account is deleted, their Yammer user messages that are subject to retention are stored in an inactive mailbox.</span></span> <span data-ttu-id="492cd-152">Meddelandena finns kvar enligt kvarhållningsprincipen för användaren innan postlådan inaktiverades och innehållet är tillgängligt för eDiscovery-sökningar.</span><span class="sxs-lookup"><span data-stu-id="492cd-152">These messages remain subject to any retention policy that was placed on the user before their mailbox was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="492cd-153">Mer information finns i [Inaktiva postlådor i Exchange Online](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="492cd-153">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

<span data-ttu-id="492cd-154">Om användaren har lagrat några filer i Yammer kan du se [motsvarande avsnitt](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) för SharePoint och OneDrive.</span><span class="sxs-lookup"><span data-stu-id="492cd-154">If the user stored any files in Yammer, see the [equivalent section](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) for SharePoint and OneDrive.</span></span>

## <a name="limitations"></a><span data-ttu-id="492cd-155">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="492cd-155">Limitations</span></span>

<span data-ttu-id="492cd-156">För närvarande finns det en förhandsversion av Yammers kvarhållningsprinciper och vi arbetar kontinuerligt med att optimera kvarhållningsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="492cd-156">Yammer retention policies are currently in preview and we're continuously working on optimizing retention functionality.</span></span> <span data-ttu-id="492cd-157">Under tiden bör du vara medveten om följande begränsning när du använder kvarhållning för Yammers communitymeddelanden och privata meddelanden:</span><span class="sxs-lookup"><span data-stu-id="492cd-157">In the meantime, be aware of the following limitation when you use retention for Yammer community messages and private messages:</span></span>

- <span data-ttu-id="492cd-158">När du väljer **Välj användare** för platsen **Användarmeddelanden i Yammer** kan du se gäster och användare utan postlåda.</span><span class="sxs-lookup"><span data-stu-id="492cd-158">When you select **Choose users** for the **Yammer user messages** location, you might see guests and non-mailbox users.</span></span> <span data-ttu-id="492cd-159">Kvarhållningsprinciperna är inte avsedda för de här användarna, så välj dem inte.</span><span class="sxs-lookup"><span data-stu-id="492cd-159">Retention policies aren't designed for these users, so don't select them.</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="492cd-160">Konfigurationsvägledning</span><span class="sxs-lookup"><span data-stu-id="492cd-160">Configuration guidance</span></span>

<span data-ttu-id="492cd-161">Om du inte är bekant med att konfigurera kvarhållning i Microsoft 365 kan du läsa mer i [Komma igång med kvarhållningsprinciper och kvarhållningsetiketter](get-started-with-retention.md).</span><span class="sxs-lookup"><span data-stu-id="492cd-161">If you're new to configuring retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="492cd-162">Om du är redo att konfigurera en kvarhållningsprincip för Yammer kan du läsa [Skapa och konfigurera kvarhållningsprinciper](create-retention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="492cd-162">If you're ready to configure a retention policy for Yammer, see [Create and configure retention policies](create-retention-policies.md).</span></span>