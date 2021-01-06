---
title: Microsoft 365 grupper namn princip
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
description: Lär dig hur du skapar en namn princip för Microsoft 365 Groups.
ms.openlocfilehash: acf660375508760bd2e9874a07454709849929b0
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49759830"
---
# <a name="microsoft-365-groups-naming-policy"></a><span data-ttu-id="7bc5d-103">Microsoft 365 grupper namn princip</span><span class="sxs-lookup"><span data-stu-id="7bc5d-103">Microsoft 365 groups naming policy</span></span>

<span data-ttu-id="7bc5d-104">Du kan använda en princip för att skapa en konsekvent namn strategi för grupper som skapas av användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-104">You can use a group naming policy to enforce a consistent naming strategy for groups created by users in your organization.</span></span> <span data-ttu-id="7bc5d-105">En namn princip hjälper dig och dina användare att identifiera funktionen för gruppen, medlemskap, geografiska områden eller vem som skapat gruppen.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-105">A naming policy can help you and your users identify the function of the group, membership, geographic region, or who created the group.</span></span> <span data-ttu-id="7bc5d-106">Namn princip kan också hjälpa kategorisering av grupper i adress boken.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-106">The naming policy can also help categorize groups in the address book.</span></span> <span data-ttu-id="7bc5d-107">Du kan använda principen för att blockera specifika ord från att användas i grupp namn och alias.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-107">You can use the policy to block specific words from being used in group names and aliases.</span></span>

<span data-ttu-id="7bc5d-108">Namngivnings principen tillämpas på grupper som skapas i alla grupp arbets uppgifter (som Outlook, Microsoft Teams, SharePoint, Planner, Yammer osv.).</span><span class="sxs-lookup"><span data-stu-id="7bc5d-108">The naming policy is applied to groups that are created across all groups workloads (like Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc.).</span></span> <span data-ttu-id="7bc5d-109">Den används för både grupp namn och gruppalias.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-109">It gets applied to both the group name and group alias.</span></span> <span data-ttu-id="7bc5d-110">Den används också när en användare skapar en grupp och när gruppens namn, alias, beskrivning eller avatar redige ras för en befintlig grupp.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-110">It also gets applied when a user creates a group and when the group name, alias, description, or avatar is edited for an existing group.</span></span>

> [!TIP]
> <span data-ttu-id="7bc5d-111">En Microsoft 365-grupp för namngivnings princip gäller endast för Microsoft 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-111">A Microsoft 365 group naming policy only applies to Microsoft 365 groups.</span></span> <span data-ttu-id="7bc5d-112">Det gäller inte distributions grupper som har skapats i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-112">It doesn't apply to distribution groups created in Exchange Online.</span></span> <span data-ttu-id="7bc5d-113">Information om hur du skapar en namngivnings princip för distributions grupper finns i [skapa en namn princip för en distributions grupp](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span><span class="sxs-lookup"><span data-stu-id="7bc5d-113">To create a naming policy for distribution groups, see [Create a distribution group naming policy](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span></span>

<span data-ttu-id="7bc5d-114">Namnprincipen för grupp består av följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="7bc5d-114">The group naming policy consists of the following features:</span></span>

- <span data-ttu-id="7bc5d-115">**Prefix – namngivnings princip för suffix**: du kan ange namn konvention för grupper (till exempel: " \_ min grupp \_ teknik").</span><span class="sxs-lookup"><span data-stu-id="7bc5d-115">**Prefix-Suffix naming policy**: You can use prefixes or suffixes to define the naming convention of groups (for example: "US\_My Group\_Engineering").</span></span> <span data-ttu-id="7bc5d-116">Prefix och suffix kan antingen vara fasta strängar eller användarattribut som [Department], som ersätts utifrån den användare som skapar gruppen.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-116">The prefixes/suffixes can either be fixed strings or user attributes like [Department] that will get substituted based on the user who is creating the group.</span></span>

- <span data-ttu-id="7bc5d-117">**Anpassade blockerade ord**: du kan ladda upp en uppsättning blockerade ord som är specifika för din organisation som blockeras i grupper som skapats av användare.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-117">**Custom Blocked Words**: You can upload a set of blocked words specific to your organization that would be blocked in groups created by users.</span></span> <span data-ttu-id="7bc5d-118">(Till exempel: "VD, lön, HR").</span><span class="sxs-lookup"><span data-stu-id="7bc5d-118">(For example: "CEO, Payroll, HR").</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="7bc5d-119">Licens krav</span><span class="sxs-lookup"><span data-stu-id="7bc5d-119">Licensing requirements</span></span>

<span data-ttu-id="7bc5d-120">För att använda Azure AD-grupprinciper för Microsoft 365-grupper måste du ha, men inte nödvändigt vis, en Azure Active Directory Premium P1-licens eller Azure AD Basic EDU-licens för varje enskild användare (inklusive gäster) som är medlem i en eller flera Microsoft 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-120">Using Azure AD naming policy for Microsoft 365 Groups requires that you possess but not necessarily assign an Azure Active Directory Premium P1 license or Azure AD Basic EDU license for each unique user (including guests) that is a member of one or more Microsoft 365 groups.</span></span>

<span data-ttu-id="7bc5d-121">Det här är också obligatoriskt för administratören som skapar namn princip för grupper.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-121">This is also required for the administrator that creates the groups naming policy.</span></span>

## <a name="prefix-suffix-naming-policy"></a><span data-ttu-id="7bc5d-122">Prefix-Suffix namn princip</span><span class="sxs-lookup"><span data-stu-id="7bc5d-122">Prefix-Suffix naming policy</span></span>

<span data-ttu-id="7bc5d-123">Prefix och suffix kan antingen vara fasta strängar eller användarattribut.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-123">Prefixes and suffixes can either be fixed strings or user attributes.</span></span>

### <a name="fixed-strings"></a><span data-ttu-id="7bc5d-124">Fasta strängar</span><span class="sxs-lookup"><span data-stu-id="7bc5d-124">Fixed strings</span></span>

<span data-ttu-id="7bc5d-125">Du kan använda korta strängar som hjälper dig att skilja grupper i det GAL och vänstra navigerings fältet i gruppens arbets belastning.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-125">You can use short strings that can help you differentiate groups in the GAL and left navigation of the group workloads.</span></span> <span data-ttu-id="7bc5d-126">Vissa vanliga prefix är nyckelord som "GRP \_ Name", " \# namn", " \_ namn"</span><span class="sxs-lookup"><span data-stu-id="7bc5d-126">Some of the common prefixes suffixes are keywords like 'Grp\_Name' , '\#Name', '\_Name'</span></span>

### <a name="attributes"></a><span data-ttu-id="7bc5d-127">Attribut</span><span class="sxs-lookup"><span data-stu-id="7bc5d-127">Attributes</span></span>

<span data-ttu-id="7bc5d-128">Du kan använda attribut som hjälper dig att identifiera vem som skapade gruppen, till exempel [avdelning] och var den skapades från gilla [Country].</span><span class="sxs-lookup"><span data-stu-id="7bc5d-128">You can use attributes that can help identify who created the group like [Department] and where it was created from like [Country].</span></span>

<span data-ttu-id="7bc5d-129">Exempel:</span><span class="sxs-lookup"><span data-stu-id="7bc5d-129">Examples:</span></span>

- <span data-ttu-id="7bc5d-130">Princip = "GRP [GroupName] [Department]"</span><span class="sxs-lookup"><span data-stu-id="7bc5d-130">Policy = "GRP [GroupName] [Department]"</span></span>
- <span data-ttu-id="7bc5d-131">Användarens avdelning = Teknik</span><span class="sxs-lookup"><span data-stu-id="7bc5d-131">User's department = Engineering</span></span>
- <span data-ttu-id="7bc5d-132">Skapat gruppnamn = "GRP Min grupp Teknik"</span><span class="sxs-lookup"><span data-stu-id="7bc5d-132">Created group name = "GRP My Group Engineering"</span></span>

<span data-ttu-id="7bc5d-133">Azure Active Directory (Azure AD)-attribut som stöds är [avdelning], [företag], [Office], [StateOrProvince], [CountryOrRegion] och [title].</span><span class="sxs-lookup"><span data-stu-id="7bc5d-133">Supported Azure Active Directory (Azure AD) attributes are [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], and [Title].</span></span>

- <span data-ttu-id="7bc5d-134">Användarattribut som inte stöds betraktas som fasta strängar, till exempel [post nummer].</span><span class="sxs-lookup"><span data-stu-id="7bc5d-134">Unsupported user attributes are considered as fixed strings, for example [postalCode].</span></span>

- <span data-ttu-id="7bc5d-135">Tilläggsattribut och egna attribut stöds inte.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-135">Extension attributes and custom attributes aren't supported.</span></span>

<span data-ttu-id="7bc5d-136">Vi rekommenderar att du använder attribut som har värden ifyllda för alla användare i organisationen samt att du inte använder attribut som har långa värden.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-136">It's recommended that you use attributes that have values filled in for all users in your organization and don't use attributes that have longer values.</span></span>

### <a name="things-to-look-out-for"></a><span data-ttu-id="7bc5d-137">Saker att se ut för</span><span class="sxs-lookup"><span data-stu-id="7bc5d-137">Things to look out for</span></span>

- <span data-ttu-id="7bc5d-138">När du skapar principen är den totala stränglängden för prefix och suffix begränsad till 53 tecken.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-138">During policy creation, the total prefixes and suffixes string length is restricted to 53 characters.</span></span>

- <span data-ttu-id="7bc5d-139">Prefix och suffix får innehålla specialtecken som stöds i gruppens namn och gruppalias.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-139">Prefixes and suffixes can contain special characters supported in group name and group alias.</span></span> <span data-ttu-id="7bc5d-140">När prefix och suffix innehåller specialtecken som inte är tillåtna i gruppaliaset tillämpas de bara på grupp namnet.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-140">When the prefixes and suffixes contain special characters that are not allowed in the group alias, they are only applied to the group name.</span></span> <span data-ttu-id="7bc5d-141">I det här fallet skiljer sig de prefix och suffix som tillämpas på gruppnamnet från dem som tillämpas på gruppaliaset.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-141">So in this case, the prefixes and suffixes applied to group name would be different from the ones applied to the group alias.</span></span>

  > [!NOTE]
  > <span data-ttu-id="7bc5d-142">En punkt (.) eller ett bindestreck (-) tillåts var som helst i grupp namnet, förutom i början eller slutet av namnet.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-142">A period (.) or a hyphen (-) is permitted anywhere in the group name, except at the beginning or end of the name.</span></span> <span data-ttu-id="7bc5d-143">Ett under streck (_) tillåts var som helst i grupp namnet, inklusive i början eller slutet av namnet.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-143">An underscore (_) is permitted anywhere in the group name, including at the beginning or end of the name.</span></span>

- <span data-ttu-id="7bc5d-144">Om du använder Yammer Office 365-anslutna grupper kan du undvika att använda följande tecken i din namn princip: @, \# , \[ , \] , \<, and \> .</span><span class="sxs-lookup"><span data-stu-id="7bc5d-144">If you are using Yammer Office 365 connected groups, avoid using the following characters in your naming policy: @, \#, \[, \], \<, and \>.</span></span> <span data-ttu-id="7bc5d-145">Om dessa tecken finns i namn principen kan vanliga Yammer-användare inte skapa grupper.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-145">If these characters are in the naming policy, regular Yammer users will not be able to create groups.</span></span>

> [!Tip]
> - <span data-ttu-id="7bc5d-146">Använd korta strängar som suffix.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-146">Use short strings as suffix.</span></span>
> - <span data-ttu-id="7bc5d-147">Använd attribut med värden.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-147">Use attributes with values.</span></span>
> - <span data-ttu-id="7bc5d-148">Är inte för kreativ, total namn längd får högst innehålla 264 tecken.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-148">Don't be too creative, total name length has a maximum of 264 characters.</span></span>
> - <span data-ttu-id="7bc5d-149">Ladda upp dina organisatoriska blockerade ord för att begränsa användningen.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-149">Upload your organization specific blocked words to restrict usage.</span></span>

## <a name="custom-blocked-words"></a><span data-ttu-id="7bc5d-150">Anpassade blockerade ord</span><span class="sxs-lookup"><span data-stu-id="7bc5d-150">Custom blocked words</span></span>

<span data-ttu-id="7bc5d-151">Du kan ange en kommaseparerad lista över blockerade ord som ska blockeras i grupp namn och alias.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-151">You can enter a comma separated list of blocked words that will be blocked in group names and aliases.</span></span>

<span data-ttu-id="7bc5d-152">Inga under Strängs sökningar utförs; specifikt krävs en exakt matchning mellan den användare som angavs och de anpassade blockerade orden för att utlösa ett fel.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-152">No sub-string searches are carried out; specifically, an exact match between the user entered name and the custom blocked words is required to trigger a failure.</span></span>

<span data-ttu-id="7bc5d-153">**Saker att se ut för**:</span><span class="sxs-lookup"><span data-stu-id="7bc5d-153">**Things to look out for**:</span></span>

- <span data-ttu-id="7bc5d-154">Blockerade ord är inte skiftlägeskänsliga.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-154">The blocked words are case-insensitive.</span></span>

- <span data-ttu-id="7bc5d-155">Om en användare anger ett blockerat ord visas ett felmeddelande med det blockerade ordet i gruppklienten.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-155">When a user enters a blocked word, the group client will show an error message with the blocked word.</span></span>

- <span data-ttu-id="7bc5d-156">Det finns inga teckenbegränsningar för de blockerade ord som används.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-156">There are no character restrictions in the blocked words used.</span></span>

- <span data-ttu-id="7bc5d-157">Det finns en begränsning på 5000 ord som kan anges som blockerade ord.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-157">There is a limit of 5000 words that can be set as blocked words.</span></span>

## <a name="admin-override"></a><span data-ttu-id="7bc5d-158">Åsidosättning för administratör</span><span class="sxs-lookup"><span data-stu-id="7bc5d-158">Admin override</span></span>

<span data-ttu-id="7bc5d-159">Vissa administratörer undantas från dessa principer, i alla grupp arbets belastningar och slut punkter, så att de kan skapa grupper med dessa blockerade ord och deras namngivnings regler.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-159">Some administrators are exempted from these policies, across all group workloads and endpoints, so that they can create groups with these blocked words and with their desired naming conventions.</span></span> <span data-ttu-id="7bc5d-160">Nedan följer listan över administratörsroller som är undantagna från namnprincipen för grupp.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-160">The following are the list of administrator roles exempted from the group naming policy.</span></span>

- <span data-ttu-id="7bc5d-161">Global administratör</span><span class="sxs-lookup"><span data-stu-id="7bc5d-161">Global admin</span></span>

- <span data-ttu-id="7bc5d-162">Partner Tier1-support</span><span class="sxs-lookup"><span data-stu-id="7bc5d-162">Partner Tier 1 Support</span></span>

- <span data-ttu-id="7bc5d-163">Partner Tier2-support</span><span class="sxs-lookup"><span data-stu-id="7bc5d-163">Partner Tier 2 Support</span></span>

- <span data-ttu-id="7bc5d-164">Användarkontoadministratör</span><span class="sxs-lookup"><span data-stu-id="7bc5d-164">User account admin</span></span>

## <a name="how-to-set-up-the-naming-policy"></a><span data-ttu-id="7bc5d-165">Så här konfigurerar du namn principen</span><span class="sxs-lookup"><span data-stu-id="7bc5d-165">How to set up the naming policy</span></span>

<span data-ttu-id="7bc5d-166">Så här skapar du en namngivnings princip:</span><span class="sxs-lookup"><span data-stu-id="7bc5d-166">To set up a naming policy:</span></span>

1. <span data-ttu-id="7bc5d-167">Klicka på **grupper** under **Hantera** i [Azure Active Directory](https://aad.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="7bc5d-167">In [Azure Active Directory](https://aad.portal.azure.com), under **Manage**, click **Groups**.</span></span>
2. <span data-ttu-id="7bc5d-168">Klicka på **namn princip** under **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-168">Under **Settings**, click **Naming policy**.</span></span>
3. <span data-ttu-id="7bc5d-169">Välj fliken för att **namnge principer** .</span><span class="sxs-lookup"><span data-stu-id="7bc5d-169">Choose the **Group naming policy** tab.</span></span>
4. <span data-ttu-id="7bc5d-170">Under **aktuell princip** väljer du om du vill kräva ett prefix eller ett suffix eller bådadera och markerar lämpliga kryss rutor.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-170">Under **Current policy**, choose if you want to require a prefix or suffix or both, and select the appropriate check boxes.</span></span>
5. <span data-ttu-id="7bc5d-171">Välj mellan **attribut** och **sträng** för varje rad och ange sedan ett attribut eller en sträng.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-171">Choose between **Attribute** and **String** for each line and then specify the attribute or string.</span></span>
6. <span data-ttu-id="7bc5d-172">När du har lagt till de prefix och suffix du behöver klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="7bc5d-172">When you have added the prefixes and suffixes that you need, click **Save**.</span></span>

![Skärm bild av inställningarna för namngivnings princip för grupper i Azure Active Directory](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a><span data-ttu-id="7bc5d-174">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="7bc5d-174">Related topics</span></span>

[<span data-ttu-id="7bc5d-175">Planerings steg-för-steg-samarbete för samarbets styrning</span><span class="sxs-lookup"><span data-stu-id="7bc5d-175">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="7bc5d-176">Skapa en plan för hantering av samarbete</span><span class="sxs-lookup"><span data-stu-id="7bc5d-176">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="7bc5d-177">Azure Active Directory-cmdlets för konfiguration av grupp inställningar</span><span class="sxs-lookup"><span data-stu-id="7bc5d-177">Azure Active Directory cmdlets for configuring group settings</span></span>](https://go.microsoft.com/fwlink/?linkid=868341)
