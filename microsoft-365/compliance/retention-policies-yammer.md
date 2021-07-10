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
ms.openlocfilehash: 1398bf385631967d92de760924ef94e2b3c16441
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362300"
---
# <a name="learn-about-retention-for-yammer"></a><span data-ttu-id="560bf-103">Mer information om kvarhållning för Yammer</span><span class="sxs-lookup"><span data-stu-id="560bf-103">Learn about retention for Yammer</span></span>

><span data-ttu-id="560bf-104">*[Vägledning för säkerhet och efterlevnad med licensiering i Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="560bf-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

> [!NOTE]
> <span data-ttu-id="560bf-105">Den här funktionen är i förhandsversion och kan komma att ändras.</span><span class="sxs-lookup"><span data-stu-id="560bf-105">This feature is in preview and subject to change.</span></span>

<span data-ttu-id="560bf-106">Informationen i den här artikeln kompletterar [Mer information om kvarhållning](retention.md) eftersom den innehåller specifik information för Yammer.</span><span class="sxs-lookup"><span data-stu-id="560bf-106">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Yammer.</span></span>

<span data-ttu-id="560bf-107">För andra arbetsbelastningar, se:</span><span class="sxs-lookup"><span data-stu-id="560bf-107">For other workloads, see:</span></span>

- [<span data-ttu-id="560bf-108">Mer information om kvarhållning för SharePoint och OneDrive</span><span class="sxs-lookup"><span data-stu-id="560bf-108">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="560bf-109">Mer information om kvarhållning för Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="560bf-109">Learn about retention for Microsoft Teams</span></span>](retention-policies-teams.md)
- [<span data-ttu-id="560bf-110">Lär dig mer om kvarhållning för Exchange</span><span class="sxs-lookup"><span data-stu-id="560bf-110">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a><span data-ttu-id="560bf-111">Vad omfattas för kvarhållning och borttagning</span><span class="sxs-lookup"><span data-stu-id="560bf-111">What's included for retention and deletion</span></span>

<span data-ttu-id="560bf-112">Följande Yammer-objekt kan behållas och tas bort med kvarhållningsprinciper för Yammer: Communitymeddelanden och användarmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="560bf-112">The following Yammer items can be retained and deleted by using retention policies for Yammer: Community messages and user messages.</span></span>

<span data-ttu-id="560bf-113">Reaktioner från andra i form av uttryckssymboler tas inte med i dessa meddelanden.</span><span class="sxs-lookup"><span data-stu-id="560bf-113">Reactions from others in the form of emoticons are not included in these messages.</span></span>

## <a name="how-retention-works-with-yammer"></a><span data-ttu-id="560bf-114">Så fungerar kvarhållning för Yammer</span><span class="sxs-lookup"><span data-stu-id="560bf-114">How retention works with Yammer</span></span>

<span data-ttu-id="560bf-115">I det här avsnittet beskrivs hur lagringen och processerna på serverdelen uppfyller dina efterlevnadskrav, och varför de bör verifieras med eDiscovery-verktyg i stället för med de meddelanden som för närvarande visas i Yammer-appen.</span><span class="sxs-lookup"><span data-stu-id="560bf-115">Use this section to understand how your compliance requirements are met by backend storage and processes, and should be verified by eDiscovery tools rather than by messages that are currently visible in the Yammer app.</span></span>

<span data-ttu-id="560bf-116">Du kan använda en kvarhållningsprincip för att behålla data från community-meddelanden och användarmeddelanden i Yammer samt ta bort dessa meddelanden.</span><span class="sxs-lookup"><span data-stu-id="560bf-116">You can use a retention policy to retain data from community messages and user messages in Yammer, and delete these messages.</span></span> <span data-ttu-id="560bf-117">Bakom kulisserna används Exchange-postlådor för att lagra data som kopieras från dessa meddelanden.</span><span class="sxs-lookup"><span data-stu-id="560bf-117">Behind the scenes, Exchange mailboxes are used to store data copied from these messages.</span></span> <span data-ttu-id="560bf-118">Data från Yammer-användarmeddelanden lagras i en dold mapp i postlådan för varje användare som ingår i användarmeddelandet, och en liknande dold mapp i en gruppostlåda används för community-meddelanden.</span><span class="sxs-lookup"><span data-stu-id="560bf-118">Data from Yammer user messages is stored in a hidden folder in the mailbox of each user included in the user message, and a similar hidden folder in a group mailbox is used for community messages.</span></span>

<span data-ttu-id="560bf-119">Kopior av community-meddelanden kan också lagras i den dolda mappen med användarpostlådor när de @omnämner användare eller meddelar användaren om ett svar.</span><span class="sxs-lookup"><span data-stu-id="560bf-119">Copies of community messages can also be stored in the hidden folder of user mailboxes when they @ mention users or notify the user of a reply.</span></span> <span data-ttu-id="560bf-120">Även om dessa meddelanden kommer från ett community-meddelande innehåller en kvarhållningsprincip för Yammer-användarmeddelanden ofta kopior av community-meddelanden.</span><span class="sxs-lookup"><span data-stu-id="560bf-120">Although these messages originate as a community message, a retention policy for Yammer user messages will often include copies of community messages.</span></span>

<span data-ttu-id="560bf-121">De dolda mapparna är inte avsedda att vara direkt tillgängliga för användare eller administratörer, utan för att lagra data som efterlevnadsadministratörer kan söka i med eDiscovery-verktyg.</span><span class="sxs-lookup"><span data-stu-id="560bf-121">These hidden folders are not designed to be directly accessible to users or administrators, but instead, store data that compliance administrators can search with eDiscovery tools.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="560bf-122">Eftersom kopior av community-meddelanden också kan lagras i användarpostlådor kan en kvarhållningsprincip med en borttagningsåtgärd för Yammer-användarmeddelanden resultera i att det ursprungliga communitymeddelandet inte längre visas för användare i Yammer-appen.</span><span class="sxs-lookup"><span data-stu-id="560bf-122">Because copies of community messages can also be stored in user mailboxes, a retention policy with a delete action for Yammer user messages can result in the original community message no longer visible to users in the Yammer app.</span></span>
> 
> <span data-ttu-id="560bf-123">En kopia av det ursprungliga meddelandet är dock fortfarande tillgänglig i den dolda mappen i gruppostlådan för communityn och är tillgänglig med eDiscovery-sökningar i efterlevnadssyfte.</span><span class="sxs-lookup"><span data-stu-id="560bf-123">However, a copy of the original message is still available in the hidden folder of the community group mailbox, and accessible with eDiscovery searches for compliance purposes.</span></span>

<span data-ttu-id="560bf-124">Yammer-meddelanden påverkas inte av kvarhållningsprinciper som har konfigurerats för Exchange-postlådor.</span><span class="sxs-lookup"><span data-stu-id="560bf-124">Yammer messages are not affected by retention policies that are configured for Exchange mailboxes.</span></span> <span data-ttu-id="560bf-125">Även om Yammer-meddelanden lagras i Exchange omfattas dessa Yammer-data endast av en kvarhållningsprincip som är konfigurerad för platserna **Community-meddelanden i Yammer** och **Användarmeddelanden i Yammer**.</span><span class="sxs-lookup"><span data-stu-id="560bf-125">Even though Yammer messages are stored in Exchange, this Yammer data is included only by a retention policy that's configured for the **Yammer community messages** and **Yammer user messages** locations.</span></span>

> [!NOTE]
> <span data-ttu-id="560bf-126">Om en användare ingår i en aktiv kvarhållningsprincip som behåller Yammer-data och du tar bort postlådan för en användare som ingår i den principen, konverteras postlådan till en [inaktiv postlåda](inactive-mailboxes-in-office-365.md) för att Yammer-datan ska behållas.</span><span class="sxs-lookup"><span data-stu-id="560bf-126">If a user is included in an active retention policy that retains Yammer data and you a delete a mailbox of a user who is included in this policy, to retain the Yammer data, the mailbox is converted into an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="560bf-127">Om du inte behöver behålla Yammer-datan för användaren exkluderar du användarkontot från kvarhållningsprincipen innan du tar bort postlådan.</span><span class="sxs-lookup"><span data-stu-id="560bf-127">If you don't need to retain this Yammer data for the user, exclude the user account from the retention policy before you delete their mailbox.</span></span>

<span data-ttu-id="560bf-128">När en kvarhållningsprincip har konfigurerats för Yammer-meddelanden, utvärderar ett tidsinställt jobb från Exchange-tjänsten regelbundet objekt i den dolda mappen där dessa Yammer-meddelanden lagras.</span><span class="sxs-lookup"><span data-stu-id="560bf-128">After a retention policy is configured for Yammer messages, a timer job from the Exchange service periodically evaluates items in the hidden folder where these Yammer messages are stored.</span></span> <span data-ttu-id="560bf-129">Det tidsinställda jobbet tar upp till sju dagar att köra.</span><span class="sxs-lookup"><span data-stu-id="560bf-129">The timer job takes up to seven days to run.</span></span> <span data-ttu-id="560bf-130">När kvarhållningsperioden för objekten har upphört flyttas de till mappen SubstrateHolds. Det är en dold mapp som finns i varje användar- eller gruppostlåda där ej permanent borttagna objekt lagras innan de tas bort permanent.</span><span class="sxs-lookup"><span data-stu-id="560bf-130">When these items have expired their retention period, they are moved to the SubstrateHolds folder—a hidden folder that's in every user or group mailbox to store "soft-deleted" items before they are permanently deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="560bf-131">På grund av [första principen om kvarhållning](retention.md#the-principles-of-retention-or-what-takes-precedence)inaktiveras permanent borttagning alltid om samma objekt måste behållas på grund av en annan kvarhållningsprincip, eller om det finns eDiscovery som gäller för juridiska skäl eller av juridiska skäl.</span><span class="sxs-lookup"><span data-stu-id="560bf-131">Because of the [first principle of retention](retention.md#the-principles-of-retention-or-what-takes-precedence), permanent deletion is always suspended if the same item must be retained because of another retention policy, or it is under eDiscovery holds for legal or investigative reasons.</span></span>

<span data-ttu-id="560bf-132">När en kvarhållningsprincip har konfigurerats för Yammer-meddelanden beror sökvägarna till innehållet på om kvarhållningsprincipen ska behålla och sedan ta bort, endast behålla eller endast ta bort.</span><span class="sxs-lookup"><span data-stu-id="560bf-132">After a retention policy is configured for Yammer messages, the paths the content takes depend on whether the retention policy is to retain and then delete, to retain only, or delete only.</span></span>

<span data-ttu-id="560bf-133">När kvarhållningsprincipen ska behålla och sedan ta bort:</span><span class="sxs-lookup"><span data-stu-id="560bf-133">When the retention policy is to retain and then delete:</span></span>

![Diagram med kvarhållningsflöde för Yammer-meddelanden](../media/yammerretentionlifecycle.png)

<span data-ttu-id="560bf-135">För de två sökvägarna i diagrammet:</span><span class="sxs-lookup"><span data-stu-id="560bf-135">For the two paths in the diagram:</span></span>

1. <span data-ttu-id="560bf-136">**Om ett Yammer-meddelande redigeras eller tas bort** av användaren under kvarhållningsperioden, kopieras det ursprungliga meddelandet omedelbart (om det redigeras) eller flyttas (om det tas bort) till mappen SubstrateHolds.</span><span class="sxs-lookup"><span data-stu-id="560bf-136">**If a Yammer message is edited or deleted** by the user during the retention period, the original message is immediately copied (if edited) or moved (if deleted) to the SubstrateHolds folder.</span></span> <span data-ttu-id="560bf-137">Meddelandet lagras där tills kvarhållningsperioden upphör och meddelandet tas bort permanent.</span><span class="sxs-lookup"><span data-stu-id="560bf-137">The message is stored there until the retention period expires and then the message is immediately permanently deleted.</span></span>

2. <span data-ttu-id="560bf-138">**Om ett Yammer-meddelande inte tas bort** och för aktuella meddelanden efter redigering, flyttas meddelandet till mappen SubstrateHolds efter att kvarhållningsperioden har upphört.</span><span class="sxs-lookup"><span data-stu-id="560bf-138">**If a Yammer message is not deleted** and for current messages after editing, the message is moved to the SubstrateHolds folder after the retention period expires.</span></span> <span data-ttu-id="560bf-139">Den här åtgärden tar upp till sju dagar från utgångsdatumet.</span><span class="sxs-lookup"><span data-stu-id="560bf-139">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="560bf-140">När meddelandet finns i mappen SubstrateHolds tas det omedelbart bort permanent.</span><span class="sxs-lookup"><span data-stu-id="560bf-140">When the message is in the SubstrateHolds folder, it is then immediately permanently deleted.</span></span> 

> [!NOTE]
> <span data-ttu-id="560bf-141">Meddelanden i mappen SubstrateHolds är sökbara med eDiscovery-verktyg.</span><span class="sxs-lookup"><span data-stu-id="560bf-141">Messages in the SubstrateHolds folder are searchable by eDiscovery tools.</span></span> <span data-ttu-id="560bf-142">Tills meddelandena tas bort permanent (i mappen SubstrateHolds) förblir de sökbara med eDiscovery-verktyg.</span><span class="sxs-lookup"><span data-stu-id="560bf-142">Until messages are permanently deleted (in the SubstrateHolds folder), they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="560bf-143">När kvarhållningsprincipen endast ska behålla eller endast ta bort, är innehållssökvägarna varianter av att behålla eller ta bort.</span><span class="sxs-lookup"><span data-stu-id="560bf-143">When the retention policy is retain-only, or delete-only, the content's paths are variations of retain and delete.</span></span>

### <a name="content-paths-for-retain-only-retention-policy"></a><span data-ttu-id="560bf-144">Innehållssökvägar för kvarhållningsprincip som endast behåller</span><span class="sxs-lookup"><span data-stu-id="560bf-144">Content paths for retain-only retention policy</span></span>

1. <span data-ttu-id="560bf-145">**Om ett Yammer-meddelande redigeras eller tas bort**: En kopia av det ursprungliga meddelandet skapas omedelbart i mappen SubstrateHolds och behålls där tills kvarhållningsperioden upphör.</span><span class="sxs-lookup"><span data-stu-id="560bf-145">**If a Yammer message is edited or deleted**: A copy of the original message is immediately created in the SubstrateHolds folder and retained there until the retention period expires.</span></span> <span data-ttu-id="560bf-146">Meddelandet tas sedan bort permanent från mappen SubstrateHolds omedelbart.</span><span class="sxs-lookup"><span data-stu-id="560bf-146">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="560bf-147">**Om Yammer-meddelandet inte ändras eller tas bort** och för aktuella meddelanden efter redigering under kvarhållningsperioden: Ingenting händer före och efter kvarhållningsperioden, meddelandet finns kvar på sin ursprungliga plats.</span><span class="sxs-lookup"><span data-stu-id="560bf-147">**If the Yammer message is not modified or deleted** and for current messages after editing during the retention period: Nothing happens before and after the retention period; the message remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-policy"></a><span data-ttu-id="560bf-148">Innehållssökvägar för kvarhållningsprincip som endast tar bort</span><span class="sxs-lookup"><span data-stu-id="560bf-148">Content paths for delete-only retention policy</span></span>

1. <span data-ttu-id="560bf-149">**Om Yammer-meddelandet inte tas bort** under kvarhållningsperioden: Meddelandet flyttas till mappen SubstrateHolds efter kvarhållningsperioden.</span><span class="sxs-lookup"><span data-stu-id="560bf-149">**If the Yammer message is not deleted** during the retention period: At the end of the retention period, the message is moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="560bf-150">Den här åtgärden tar upp till sju dagar från utgångsdatumet.</span><span class="sxs-lookup"><span data-stu-id="560bf-150">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="560bf-151">Meddelandet tas sedan bort permanent från mappen SubstrateHolds omedelbart.</span><span class="sxs-lookup"><span data-stu-id="560bf-151">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="560bf-152">**Om Yammer-meddelandet tas bort av användaren** under perioden flyttas objektet omedelbart till mappen SubstrateHolds där det tas bort omedelbart och permanent.</span><span class="sxs-lookup"><span data-stu-id="560bf-152">**If the Yammer message is deleted by the user** during the period, the item is immediately moved to the SubstrateHolds folder where it is immediately permanently deleted.</span></span>


## <a name="messages-and-external-users"></a><span data-ttu-id="560bf-153">Meddelanden och externa användare</span><span class="sxs-lookup"><span data-stu-id="560bf-153">Messages and external users</span></span>

<span data-ttu-id="560bf-154">Som standard gäller en kvarhållningsprincip för användarmeddelanden i Yammer alla användare i organisationen, men inte för externa användare.</span><span class="sxs-lookup"><span data-stu-id="560bf-154">By default, a retention policy for Yammer user messages applies to all users in your organization, but not external users.</span></span> <span data-ttu-id="560bf-155">Du kan använda en kvarhållningsprincip för externa användare om du använder alternativet **Redigera** för användare som ingår och ange deras konto.</span><span class="sxs-lookup"><span data-stu-id="560bf-155">You can apply a retention policy to external users if you use the **Edit** option for users included, and specify their account.</span></span>

<span data-ttu-id="560bf-156">För närvarande stöds inte Azure B2B-gästanvändare.</span><span class="sxs-lookup"><span data-stu-id="560bf-156">At this time, Azure B2B guest users are not supported.</span></span>

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="560bf-157">När en användare lämnar organisationen</span><span class="sxs-lookup"><span data-stu-id="560bf-157">When a user leaves the organization</span></span> 

<span data-ttu-id="560bf-158">Om användare lämnar organisationen och deras Microsoft 365-konto tas bort, lagras deras Yammer-användarmeddelanden som ska behållas i en inaktiv postlåda.</span><span class="sxs-lookup"><span data-stu-id="560bf-158">If a user leaves your organization and their Microsoft 365 account is deleted, their Yammer user messages that are subject to retention are stored in an inactive mailbox.</span></span> <span data-ttu-id="560bf-159">Meddelandena finns kvar enligt kvarhållningsprincipen för användaren innan postlådan inaktiverades och innehållet är tillgängligt för eDiscovery-sökningar.</span><span class="sxs-lookup"><span data-stu-id="560bf-159">These messages remain subject to any retention policy that was placed on the user before their mailbox was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="560bf-160">Mer information finns i [Inaktiva postlådor i Exchange Online](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="560bf-160">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

<span data-ttu-id="560bf-161">Om användaren har lagrat några filer i Yammer kan du se [motsvarande avsnitt](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) för SharePoint och OneDrive.</span><span class="sxs-lookup"><span data-stu-id="560bf-161">If the user stored any files in Yammer, see the [equivalent section](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) for SharePoint and OneDrive.</span></span>

## <a name="limitations"></a><span data-ttu-id="560bf-162">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="560bf-162">Limitations</span></span>

<span data-ttu-id="560bf-163">För närvarande finns det en förhandsversion av Yammers kvarhållningsprinciper och vi arbetar kontinuerligt med att optimera kvarhållningsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="560bf-163">Yammer retention policies are currently in preview and we're continuously working on optimizing retention functionality.</span></span> <span data-ttu-id="560bf-164">Under tiden bör du vara medveten om följande begränsning när du använder kvarhållning för Yammer community-meddelanden och användarmeddelanden:</span><span class="sxs-lookup"><span data-stu-id="560bf-164">In the meantime, be aware of the following limitation when you use retention for Yammer community messages and user messages:</span></span>

- <span data-ttu-id="560bf-165">När du väljer **Redigera** för platsen **Användarmeddelanden i Yammer** kan du se gäster och användare utan postlåda.</span><span class="sxs-lookup"><span data-stu-id="560bf-165">When you select **Edit** for the **Yammer user messages** location, you might see guests and non-mailbox users.</span></span> <span data-ttu-id="560bf-166">Kvarhållningsprinciperna är inte avsedda för de här användarna, så välj dem inte.</span><span class="sxs-lookup"><span data-stu-id="560bf-166">Retention policies aren't designed for these users, so don't select them.</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="560bf-167">Konfigurationsvägledning</span><span class="sxs-lookup"><span data-stu-id="560bf-167">Configuration guidance</span></span>

<span data-ttu-id="560bf-168">Om du inte är bekant med att konfigurera kvarhållning i Microsoft 365 kan du läsa mer i [Komma igång med kvarhållningsprinciper och kvarhållningsetiketter](get-started-with-retention.md).</span><span class="sxs-lookup"><span data-stu-id="560bf-168">If you're new to configuring retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="560bf-169">Om du är redo att konfigurera en kvarhållningsprincip för Yammer kan du läsa [Skapa och konfigurera kvarhållningsprinciper](create-retention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="560bf-169">If you're ready to configure a retention policy for Yammer, see [Create and configure retention policies](create-retention-policies.md).</span></span>