---
title: Microsoft 365 namnprincip för grupper
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
recommendations: false
description: Lär dig hur du skapar en namnprincip för Microsoft 365 grupper.
ms.openlocfilehash: 5ab5f252e2b81470413b4efea17b131613aabc18
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538177"
---
# <a name="microsoft-365-groups-naming-policy"></a><span data-ttu-id="05907-103">Microsoft 365 namnprincip för grupper</span><span class="sxs-lookup"><span data-stu-id="05907-103">Microsoft 365 groups naming policy</span></span>

<span data-ttu-id="05907-104">Du kan använda en gruppnamnprincip för att tillämpa en konsekvent namngivningsstrategi för grupper som skapas av användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="05907-104">You can use a group naming policy to enforce a consistent naming strategy for groups created by users in your organization.</span></span> <span data-ttu-id="05907-105">En namnprincip kan hjälpa dig och dina användare att identifiera funktionen för gruppen, medlemskap, geografiskt område eller vem som skapade gruppen.</span><span class="sxs-lookup"><span data-stu-id="05907-105">A naming policy can help you and your users identify the function of the group, membership, geographic region, or who created the group.</span></span> <span data-ttu-id="05907-106">Namnprincipen kan även hjälpa till att kategorisera grupper i adressboken.</span><span class="sxs-lookup"><span data-stu-id="05907-106">The naming policy can also help categorize groups in the address book.</span></span> <span data-ttu-id="05907-107">Du kan använda principen för att blockera specifika ord från att användas i gruppnamn och gruppalias.</span><span class="sxs-lookup"><span data-stu-id="05907-107">You can use the policy to block specific words from being used in group names and aliases.</span></span>

<span data-ttu-id="05907-108">Namnprincipen tillämpas på grupper som skapas i alla grupparbetsbelastningar (t.ex. Outlook, Microsoft Teams, SharePoint, Planner Yammer osv.).</span><span class="sxs-lookup"><span data-stu-id="05907-108">The naming policy is applied to groups that are created across all groups workloads (like Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc.).</span></span> <span data-ttu-id="05907-109">Det används för både gruppnamn och gruppalias.</span><span class="sxs-lookup"><span data-stu-id="05907-109">It gets applied to both the group name and group alias.</span></span> <span data-ttu-id="05907-110">Det används också när en användare skapar en grupp och när gruppens namn, alias, beskrivning eller avatar redigeras för en befintlig grupp.</span><span class="sxs-lookup"><span data-stu-id="05907-110">It also gets applied when a user creates a group and when the group name, alias, description, or avatar is edited for an existing group.</span></span>

> [!TIP]
> <span data-ttu-id="05907-111">En Microsoft 365 för gruppnamn gäller endast för Microsoft 365 grupper.</span><span class="sxs-lookup"><span data-stu-id="05907-111">A Microsoft 365 group naming policy only applies to Microsoft 365 groups.</span></span> <span data-ttu-id="05907-112">Den gäller inte distributionsgrupper som skapats i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="05907-112">It doesn't apply to distribution groups created in Exchange Online.</span></span> <span data-ttu-id="05907-113">Information om hur du skapar en namnprincip för distributionsgrupper finns [i Skapa en namngivningsprincip för distributionsgrupp.](/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy)</span><span class="sxs-lookup"><span data-stu-id="05907-113">To create a naming policy for distribution groups, see [Create a distribution group naming policy](/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span></span>

<span data-ttu-id="05907-114">Namnprincipen för grupp består av följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="05907-114">The group naming policy consists of the following features:</span></span>

- <span data-ttu-id="05907-115">**Prefix-Suffixnamnprincip:** Du kan använda prefix eller suffix för att definiera namngivningskonventioner för grupper (till exempel "Us \_ My Group \_ Engineering").</span><span class="sxs-lookup"><span data-stu-id="05907-115">**Prefix-Suffix naming policy**: You can use prefixes or suffixes to define the naming convention of groups (for example: "US\_My Group\_Engineering").</span></span> <span data-ttu-id="05907-116">Prefix och suffix kan antingen vara fasta strängar eller användarattribut som [Department], som ersätts utifrån den användare som skapar gruppen.</span><span class="sxs-lookup"><span data-stu-id="05907-116">The prefixes/suffixes can either be fixed strings or user attributes like [Department] that will get substituted based on the user who is creating the group.</span></span>

- <span data-ttu-id="05907-117">**Egna blockerade ord:** Du kan ladda upp en uppsättning blockerade ord som är specifika för din organisation och som blockeras i grupper som skapats av användare.</span><span class="sxs-lookup"><span data-stu-id="05907-117">**Custom Blocked Words**: You can upload a set of blocked words specific to your organization that would be blocked in groups created by users.</span></span> <span data-ttu-id="05907-118">(Till exempel: "VD, Löneavdelningen, HR").</span><span class="sxs-lookup"><span data-stu-id="05907-118">(For example: "CEO, Payroll, HR").</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="05907-119">Licensieringskrav</span><span class="sxs-lookup"><span data-stu-id="05907-119">Licensing requirements</span></span>

<span data-ttu-id="05907-120">Om du använder Azure AD-namnprincip för Microsoft 365 Grupper kräver det att du har, men inte nödvändigtvis tilldelar en Azure Active Directory Premium P1-licens eller Azure AD Basic EDU-licens för varje unik användare (inklusive gäster) som är medlem i en eller flera Microsoft 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="05907-120">Using Azure AD naming policy for Microsoft 365 Groups requires that you possess but not necessarily assign an Azure Active Directory Premium P1 license or Azure AD Basic EDU license for each unique user (including guests) that is a member of one or more Microsoft 365 groups.</span></span>

<span data-ttu-id="05907-121">Det här krävs också för administratören som skapar namnprincipen för grupper.</span><span class="sxs-lookup"><span data-stu-id="05907-121">This is also required for the administrator that creates the groups naming policy.</span></span>

## <a name="prefix-suffix-naming-policy"></a><span data-ttu-id="05907-122">Prefix-Suffix namnprincip</span><span class="sxs-lookup"><span data-stu-id="05907-122">Prefix-Suffix naming policy</span></span>

<span data-ttu-id="05907-123">Prefix och suffix kan antingen vara fasta strängar eller användarattribut.</span><span class="sxs-lookup"><span data-stu-id="05907-123">Prefixes and suffixes can either be fixed strings or user attributes.</span></span>

### <a name="fixed-strings"></a><span data-ttu-id="05907-124">Fasta strängar</span><span class="sxs-lookup"><span data-stu-id="05907-124">Fixed strings</span></span>

<span data-ttu-id="05907-125">Du kan använda korta strängar som hjälper dig att skilja mellan grupper i GAL och vänster navigering i gruppens arbetslaster.</span><span class="sxs-lookup"><span data-stu-id="05907-125">You can use short strings that can help you differentiate groups in the GAL and left navigation of the group workloads.</span></span> <span data-ttu-id="05907-126">Några vanliga prefix/suffix är nyckelord som \_ "Grp-namn", \# "Namn", " \_ Namn"</span><span class="sxs-lookup"><span data-stu-id="05907-126">Some of the common prefixes suffixes are keywords like 'Grp\_Name' , '\#Name', '\_Name'</span></span>

### <a name="attributes"></a><span data-ttu-id="05907-127">Attribut</span><span class="sxs-lookup"><span data-stu-id="05907-127">Attributes</span></span>

<span data-ttu-id="05907-128">Du kan använda attribut som kan hjälpa dig identifiera vem som skapade gruppen, till exempel [Department], och var den skapades, som [Land].</span><span class="sxs-lookup"><span data-stu-id="05907-128">You can use attributes that can help identify who created the group like [Department] and where it was created from like [Country].</span></span>

<span data-ttu-id="05907-129">Exempel:</span><span class="sxs-lookup"><span data-stu-id="05907-129">Examples:</span></span>

- <span data-ttu-id="05907-130">Princip = "GRP [GroupName] [Department]"</span><span class="sxs-lookup"><span data-stu-id="05907-130">Policy = "GRP [GroupName] [Department]"</span></span>
- <span data-ttu-id="05907-131">Användarens avdelning = Teknik</span><span class="sxs-lookup"><span data-stu-id="05907-131">User's department = Engineering</span></span>
- <span data-ttu-id="05907-132">Skapat gruppnamn = "GRP Min grupp Teknik"</span><span class="sxs-lookup"><span data-stu-id="05907-132">Created group name = "GRP My Group Engineering"</span></span>

<span data-ttu-id="05907-133">Azure AD-attribut som stöds Azure Active Directory [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion] och [Title].</span><span class="sxs-lookup"><span data-stu-id="05907-133">Supported Azure Active Directory (Azure AD) attributes are [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], and [Title].</span></span>

- <span data-ttu-id="05907-134">Användarattribut som inte stöds betraktas som fasta strängar, till exempel [postalCode].</span><span class="sxs-lookup"><span data-stu-id="05907-134">Unsupported user attributes are considered as fixed strings, for example [postalCode].</span></span>

- <span data-ttu-id="05907-135">Tilläggsattribut och egna attribut stöds inte.</span><span class="sxs-lookup"><span data-stu-id="05907-135">Extension attributes and custom attributes aren't supported.</span></span>

<span data-ttu-id="05907-136">Vi rekommenderar att du använder attribut som har värden ifyllda för alla användare i organisationen samt att du inte använder attribut som har långa värden.</span><span class="sxs-lookup"><span data-stu-id="05907-136">It's recommended that you use attributes that have values filled in for all users in your organization and don't use attributes that have longer values.</span></span>

### <a name="things-to-look-out-for"></a><span data-ttu-id="05907-137">Saker att vara ute efter</span><span class="sxs-lookup"><span data-stu-id="05907-137">Things to look out for</span></span>

- <span data-ttu-id="05907-138">När du skapar principen är den totala stränglängden för prefix och suffix begränsad till 53 tecken.</span><span class="sxs-lookup"><span data-stu-id="05907-138">During policy creation, the total prefixes and suffixes string length is restricted to 53 characters.</span></span>

- <span data-ttu-id="05907-139">Prefix och suffix får innehålla specialtecken som stöds i gruppens namn och gruppalias.</span><span class="sxs-lookup"><span data-stu-id="05907-139">Prefixes and suffixes can contain special characters supported in group name and group alias.</span></span> <span data-ttu-id="05907-140">Om prefix och suffix innehåller specialtecken som inte är tillåtna i gruppaliaset tillämpas de bara på gruppnamnet.</span><span class="sxs-lookup"><span data-stu-id="05907-140">When the prefixes and suffixes contain special characters that are not allowed in the group alias, they are only applied to the group name.</span></span> <span data-ttu-id="05907-141">I det här fallet skiljer sig de prefix och suffix som tillämpas på gruppnamnet från dem som tillämpas på gruppaliaset.</span><span class="sxs-lookup"><span data-stu-id="05907-141">So in this case, the prefixes and suffixes applied to group name would be different from the ones applied to the group alias.</span></span>

  > [!NOTE]
  > <span data-ttu-id="05907-142">En punkt (.) eller ett bindestreck (-) tillåts någonstans i gruppnamnet, förutom i början eller slutet av namnet.</span><span class="sxs-lookup"><span data-stu-id="05907-142">A period (.) or a hyphen (-) is permitted anywhere in the group name, except at the beginning or end of the name.</span></span> <span data-ttu-id="05907-143">Ett understreck (_) tillåts var som helst i gruppnamnet, även i början eller slutet av namnet.</span><span class="sxs-lookup"><span data-stu-id="05907-143">An underscore (_) is permitted anywhere in the group name, including at the beginning or end of the name.</span></span>

- <span data-ttu-id="05907-144">Om du använder Yammer Office 365 ska du undvika att använda följande tecken i namnprincipen: @, \# , \[ , , \] \<, and \> .</span><span class="sxs-lookup"><span data-stu-id="05907-144">If you are using Yammer Office 365 connected groups, avoid using the following characters in your naming policy: @, \#, \[, \], \<, and \>.</span></span> <span data-ttu-id="05907-145">Om dessa tecken ingår i namnprincipen kan Yammer användare inte skapa grupper.</span><span class="sxs-lookup"><span data-stu-id="05907-145">If these characters are in the naming policy, regular Yammer users will not be able to create groups.</span></span>

> [!Tip]
> - <span data-ttu-id="05907-146">Använd korta strängar som suffix.</span><span class="sxs-lookup"><span data-stu-id="05907-146">Use short strings as suffix.</span></span>
> - <span data-ttu-id="05907-147">Använd attribut med värden.</span><span class="sxs-lookup"><span data-stu-id="05907-147">Use attributes with values.</span></span>
> - <span data-ttu-id="05907-148">Var inte för kreativ, den totala namnlängden får vara högst 264 tecken.</span><span class="sxs-lookup"><span data-stu-id="05907-148">Don't be too creative, total name length has a maximum of 264 characters.</span></span>
> - <span data-ttu-id="05907-149">Upload organisationens specifika blockerade ord för att begränsa användning.</span><span class="sxs-lookup"><span data-stu-id="05907-149">Upload your organization specific blocked words to restrict usage.</span></span>

## <a name="custom-blocked-words"></a><span data-ttu-id="05907-150">Egna blockerade ord</span><span class="sxs-lookup"><span data-stu-id="05907-150">Custom blocked words</span></span>

<span data-ttu-id="05907-151">Du kan ange en kommaavgränsad lista med blockerade ord som ska blockeras i gruppnamn och gruppalias.</span><span class="sxs-lookup"><span data-stu-id="05907-151">You can enter a comma separated list of blocked words that will be blocked in group names and aliases.</span></span>

<span data-ttu-id="05907-152">Ingen sökning utförs i understrängar. mer specifikt krävs en exakt matchning mellan det angivna namnet och de egna blockerade orden för att ett fel ska utlösas.</span><span class="sxs-lookup"><span data-stu-id="05907-152">No sub-string searches are carried out; specifically, an exact match between the user entered name and the custom blocked words is required to trigger a failure.</span></span>

<span data-ttu-id="05907-153">**Saker att hålla reda på:**</span><span class="sxs-lookup"><span data-stu-id="05907-153">**Things to look out for**:</span></span>

- <span data-ttu-id="05907-154">Blockerade ord är inte skiftlägeskänsliga.</span><span class="sxs-lookup"><span data-stu-id="05907-154">The blocked words are case-insensitive.</span></span>

- <span data-ttu-id="05907-155">Om en användare anger ett blockerat ord visas ett felmeddelande med det blockerade ordet i gruppklienten.</span><span class="sxs-lookup"><span data-stu-id="05907-155">When a user enters a blocked word, the group client will show an error message with the blocked word.</span></span>

- <span data-ttu-id="05907-156">Det finns inga teckenbegränsningar för de blockerade ord som används.</span><span class="sxs-lookup"><span data-stu-id="05907-156">There are no character restrictions in the blocked words used.</span></span>

- <span data-ttu-id="05907-157">Det finns en gräns på 5 000 ord som kan anges som blockerade ord.</span><span class="sxs-lookup"><span data-stu-id="05907-157">There is a limit of 5000 words that can be set as blocked words.</span></span>

## <a name="admin-override"></a><span data-ttu-id="05907-158">Åsidosättning för administratör</span><span class="sxs-lookup"><span data-stu-id="05907-158">Admin override</span></span>

<span data-ttu-id="05907-159">Vissa administratörer är undantagna från dessa principer i alla grupparbetsbelastningar och slutpunkter så att de kan skapa grupper med blockerade ord och med de namnkonventioner de önskar.</span><span class="sxs-lookup"><span data-stu-id="05907-159">Some administrators are exempted from these policies, across all group workloads and endpoints, so that they can create groups with these blocked words and with their desired naming conventions.</span></span> <span data-ttu-id="05907-160">Nedan följer listan över administratörsroller som är undantagna från namnprincipen för grupp.</span><span class="sxs-lookup"><span data-stu-id="05907-160">The following are the list of administrator roles exempted from the group naming policy.</span></span>

- <span data-ttu-id="05907-161">Global administratör</span><span class="sxs-lookup"><span data-stu-id="05907-161">Global admin</span></span>

- <span data-ttu-id="05907-162">Partner Tier1-support</span><span class="sxs-lookup"><span data-stu-id="05907-162">Partner Tier 1 Support</span></span>

- <span data-ttu-id="05907-163">Partner Tier2-support</span><span class="sxs-lookup"><span data-stu-id="05907-163">Partner Tier 2 Support</span></span>

- <span data-ttu-id="05907-164">Användarkontoadministratör</span><span class="sxs-lookup"><span data-stu-id="05907-164">User account admin</span></span>

## <a name="how-to-set-up-the-naming-policy"></a><span data-ttu-id="05907-165">Så här ställer du in namnprincipen</span><span class="sxs-lookup"><span data-stu-id="05907-165">How to set up the naming policy</span></span>

<span data-ttu-id="05907-166">Så här ställer du in en namnprincip:</span><span class="sxs-lookup"><span data-stu-id="05907-166">To set up a naming policy:</span></span>

1. <span data-ttu-id="05907-167">I [Azure Active Directory](https://aad.portal.azure.com)under **Hantera klickar** du på **Grupper.**</span><span class="sxs-lookup"><span data-stu-id="05907-167">In [Azure Active Directory](https://aad.portal.azure.com), under **Manage**, click **Groups**.</span></span>
2. <span data-ttu-id="05907-168">Klicka **Inställningar** namnprincip under **Namnprincip.**</span><span class="sxs-lookup"><span data-stu-id="05907-168">Under **Settings**, click **Naming policy**.</span></span>
3. <span data-ttu-id="05907-169">Välj fliken **Gruppnamnprincip.**</span><span class="sxs-lookup"><span data-stu-id="05907-169">Choose the **Group naming policy** tab.</span></span>
4. <span data-ttu-id="05907-170">Under **Aktuell princip** väljer du om du vill kräva prefix eller suffix eller båda. Markera sedan lämpliga kryssrutor.</span><span class="sxs-lookup"><span data-stu-id="05907-170">Under **Current policy**, choose if you want to require a prefix or suffix or both, and select the appropriate check boxes.</span></span>
5. <span data-ttu-id="05907-171">Välj mellan **Attribut** och **Sträng** för varje rad och ange sedan attributet eller strängen.</span><span class="sxs-lookup"><span data-stu-id="05907-171">Choose between **Attribute** and **String** for each line and then specify the attribute or string.</span></span>
6. <span data-ttu-id="05907-172">När du har lagt till de prefix och suffix du behöver klickar du på **Spara.**</span><span class="sxs-lookup"><span data-stu-id="05907-172">When you have added the prefixes and suffixes that you need, click **Save**.</span></span>

![Skärmbild av namnprincipinställningarna för grupper i Azure Active Directory](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a><span data-ttu-id="05907-174">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="05907-174">Related topics</span></span>

[<span data-ttu-id="05907-175">Planering av samarbetsstyrning steg för steg</span><span class="sxs-lookup"><span data-stu-id="05907-175">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="05907-176">Skapa din plan för samarbetesstyrning</span><span class="sxs-lookup"><span data-stu-id="05907-176">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="05907-177">Azure Active Directory cmdlets för att konfigurera gruppinställningar</span><span class="sxs-lookup"><span data-stu-id="05907-177">Azure Active Directory cmdlets for configuring group settings</span></span>](/azure/active-directory/enterprise-users/groups-settings-cmdlets)