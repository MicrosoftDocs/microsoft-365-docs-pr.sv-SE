---
title: Namngivningsprincipen för Office 365-grupper
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: Lär dig hur du skapar en namngivningsprincip för Office 365-grupper.
ms.openlocfilehash: 4325a5e0a1de0c3a83be71220abd256c204ec07d
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42894629"
---
# <a name="office-365-groups-naming-policy"></a><span data-ttu-id="53c6b-103">Namngivningsprincipen för Office 365-grupper</span><span class="sxs-lookup"><span data-stu-id="53c6b-103">Office 365 Groups naming policy</span></span>

<span data-ttu-id="53c6b-104">Du använder en gruppnamngivningsprincip för att tillämpa en konsekvent namngivningsstrategi för grupper som skapats av användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="53c6b-104">You use a group naming policy to enforce a consistent naming strategy for groups created by users in your organization.</span></span> <span data-ttu-id="53c6b-105">En namngivningsprincip kan hjälpa dig och dina användare att identifiera funktionen för gruppen, medlemskap, geografisk region eller vem som skapade gruppen.</span><span class="sxs-lookup"><span data-stu-id="53c6b-105">A naming policy can help you and your users identify the function of the group, membership, geographic region, or who created the group.</span></span> <span data-ttu-id="53c6b-106">Namngivningsprincipen kan också hjälpa till att kategorisera grupper i adressboken.</span><span class="sxs-lookup"><span data-stu-id="53c6b-106">The naming policy can also help categorize groups in the address book.</span></span> <span data-ttu-id="53c6b-107">Du kan använda principen för att blockera specifika ord från att användas i gruppnamn och alias.</span><span class="sxs-lookup"><span data-stu-id="53c6b-107">You can use the policy to block specific words from being used in group names and aliases.</span></span>

<span data-ttu-id="53c6b-108">Namngivningsprincipen tillämpas på grupper som skapas i alla grupparbetsbelastningar (som Outlook, Microsoft Teams, SharePoint, Planner, Yammer osv.).</span><span class="sxs-lookup"><span data-stu-id="53c6b-108">The naming policy is applied to groups that are created across all groups workloads (like Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc.).</span></span> <span data-ttu-id="53c6b-109">Den tillämpas på både gruppnamnet och gruppaliaset.</span><span class="sxs-lookup"><span data-stu-id="53c6b-109">It gets applied to both the group name and group alias.</span></span> <span data-ttu-id="53c6b-110">Den tillämpas när en användare skapar en grupp och när gruppnamn eller alias redigeras för en befintlig grupp.</span><span class="sxs-lookup"><span data-stu-id="53c6b-110">It gets applied when a user creates a group and when group name or alias is edited for an existing group.</span></span>

> [!TIP]
> <span data-ttu-id="53c6b-111">En namngivningsprincip för Office 365-grupper gäller endast för Office 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="53c6b-111">An Office 365 group naming policy only applies to Office 365 groups.</span></span> <span data-ttu-id="53c6b-112">Det gäller inte distributionsgrupper som skapats i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="53c6b-112">It doesn't apply to distribution groups created in Exchange Online.</span></span> <span data-ttu-id="53c6b-113">Om du vill skapa en namngivningsprincip för distributionsgrupper finns i [Skapa en namngivningsprincip för distributionsgrupper](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span><span class="sxs-lookup"><span data-stu-id="53c6b-113">To create a naming policy for distribution groups, see [Create a distribution group naming policy](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span></span>

<span data-ttu-id="53c6b-114">Namnprincipen för grupp består av följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="53c6b-114">The group naming policy consists of the following features:</span></span>

- <span data-ttu-id="53c6b-115">**Namngivningsprincipen prefix-Suffix**: Du kan använda prefix eller suffix för att definiera namngivningskonventionen för grupper (till exempel:"US\_My Group\_Engineering").</span><span class="sxs-lookup"><span data-stu-id="53c6b-115">**Prefix-Suffix naming policy**: You can use prefixes or suffixes to define the naming convention of groups (for example: "US\_My Group\_Engineering").</span></span> <span data-ttu-id="53c6b-116">Prefix och suffix kan antingen vara fasta strängar eller användarattribut som [Department], som ersätts utifrån den användare som skapar gruppen.</span><span class="sxs-lookup"><span data-stu-id="53c6b-116">The prefixes/suffixes can either be fixed strings or user attributes like [Department] that will get substituted based on the user who is creating the group.</span></span>

- <span data-ttu-id="53c6b-117">**Anpassade blockerade ord:** Du kan ladda upp en uppsättning blockerade ord som är specifika för din organisation och som skulle blockeras i grupper som skapats av användare.</span><span class="sxs-lookup"><span data-stu-id="53c6b-117">**Custom Blocked Words**: You can upload a set of blocked words specific to your organization that would be blocked in groups created by users.</span></span> <span data-ttu-id="53c6b-118">(Till exempel: "VD, Lön, HR").</span><span class="sxs-lookup"><span data-stu-id="53c6b-118">(For example: "CEO, Payroll, HR").</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="53c6b-119">Licenskrav</span><span class="sxs-lookup"><span data-stu-id="53c6b-119">Licensing requirements</span></span>

<span data-ttu-id="53c6b-120">Om du använder Azure AD-namngivningsprincipen för Office 365-grupper krävs att du har men inte nödvändigtvis tilldela en Azure Active Directory Premium P1-licens eller Azure AD Basic EDU-licens för varje unik användare (inklusive gäster) som är medlem i en eller flera Office 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="53c6b-120">Using Azure AD naming policy for Office 365 groups requires that you possess but not necessarily assign an Azure Active Directory Premium P1 license or Azure AD Basic EDU license for each unique user (including guests) that is a member of one or more Office 365 groups.</span></span>

<span data-ttu-id="53c6b-121">Detta krävs också för administratören som skapar namngivningsprincipen Grupper.</span><span class="sxs-lookup"><span data-stu-id="53c6b-121">This is also required for the administrator that creates the Groups naming policy.</span></span>

## <a name="prefix-suffix-naming-policy"></a><span data-ttu-id="53c6b-122">Namngivningsprincip för Prefix-Suffix</span><span class="sxs-lookup"><span data-stu-id="53c6b-122">Prefix-Suffix naming policy</span></span>

<span data-ttu-id="53c6b-123">Prefix och suffix kan antingen vara fasta strängar eller användarattribut.</span><span class="sxs-lookup"><span data-stu-id="53c6b-123">Prefixes and suffixes can either be fixed strings or user attributes.</span></span>

### <a name="fixed-strings"></a><span data-ttu-id="53c6b-124">Fasta strängar</span><span class="sxs-lookup"><span data-stu-id="53c6b-124">Fixed strings</span></span>

<span data-ttu-id="53c6b-125">Du kan använda korta strängar som kan hjälpa dig att skilja grupper i GAL och vänster navigering av grupparbetsbelastningar.</span><span class="sxs-lookup"><span data-stu-id="53c6b-125">You can use short strings that can help you differentiate groups in the GAL and left navigation of the group workloads.</span></span> <span data-ttu-id="53c6b-126">Några av de vanliga suffixen prefix är\_nyckelord som\#"Grp\_Name", ' Name', ' Name'</span><span class="sxs-lookup"><span data-stu-id="53c6b-126">Some of the common prefixes suffixes are keywords like 'Grp\_Name' , '\#Name', '\_Name'</span></span>

### <a name="attributes"></a><span data-ttu-id="53c6b-127">Attribut</span><span class="sxs-lookup"><span data-stu-id="53c6b-127">Attributes</span></span>

<span data-ttu-id="53c6b-128">Du kan använda attribut som kan hjälpa till att identifiera vem som skapade gruppen som [Avdelning] och var den skapades från som [Land].</span><span class="sxs-lookup"><span data-stu-id="53c6b-128">You can use attributes that can help identify who created the group like [Department] and where it was created from like [Country].</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="53c6b-129">**Exempel**</span><span class="sxs-lookup"><span data-stu-id="53c6b-129">**Examples**</span></span>|<span data-ttu-id="53c6b-130">Princip = "GRP [GroupName] [Department]"</span><span class="sxs-lookup"><span data-stu-id="53c6b-130">Policy = "GRP [GroupName] [Department]"</span></span>|
||<span data-ttu-id="53c6b-131">Användarens avdelning = Teknik</span><span class="sxs-lookup"><span data-stu-id="53c6b-131">User's department = Engineering</span></span>|
||<span data-ttu-id="53c6b-132">Skapat gruppnamn = "GRP Min grupp Teknik"</span><span class="sxs-lookup"><span data-stu-id="53c6b-132">Created group name = "GRP My Group Engineering"</span></span>|

<span data-ttu-id="53c6b-133">Azure Active Directory-attribut (Azure AD) stöds är [Avdelning], [Företag], [Office], [StateOrProvince], [CountryOrRegion] och [Titel].</span><span class="sxs-lookup"><span data-stu-id="53c6b-133">Supported Azure Active Directory (Azure AD) attributes are [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], and [Title].</span></span>

- <span data-ttu-id="53c6b-p107">Användarattribut som inte stöds betraktas som fasta strängar, t.ex. "[postalCode]"</span><span class="sxs-lookup"><span data-stu-id="53c6b-p107">Unsupported user attributes are considered as fixed strings. E.g. "[postalCode]"</span></span>

- <span data-ttu-id="53c6b-137">Tilläggsattribut och egna attribut stöds inte.</span><span class="sxs-lookup"><span data-stu-id="53c6b-137">Extension attributes and custom attributes aren't supported.</span></span>

<span data-ttu-id="53c6b-138">Vi rekommenderar att du använder attribut som har värden ifyllda för alla användare i organisationen samt att du inte använder attribut som har långa värden.</span><span class="sxs-lookup"><span data-stu-id="53c6b-138">It's recommended that you use attributes that have values filled in for all users in your organization and don't use attributes that have longer values.</span></span>

### <a name="things-to-look-out-for"></a><span data-ttu-id="53c6b-139">Saker att hålla utkik efter</span><span class="sxs-lookup"><span data-stu-id="53c6b-139">Things to look out for</span></span>

- <span data-ttu-id="53c6b-140">När du skapar principen är den totala stränglängden för prefix och suffix begränsad till 53 tecken.</span><span class="sxs-lookup"><span data-stu-id="53c6b-140">During policy creation, the total prefixes and suffixes string length is restricted to 53 characters.</span></span>

- <span data-ttu-id="53c6b-141">Prefix och suffix får innehålla specialtecken som stöds i gruppens namn och gruppalias.</span><span class="sxs-lookup"><span data-stu-id="53c6b-141">Prefixes and suffixes can contain special characters supported in group name and group alias.</span></span> <span data-ttu-id="53c6b-142">När prefixen och suffixen innehåller specialtecken som inte är tillåtna i gruppaliaset, tillämpas de bara på gruppnamnet.</span><span class="sxs-lookup"><span data-stu-id="53c6b-142">When the prefixes and suffixes contain special characters that are not allowed in the group alias, they are only applied to the group name.</span></span> <span data-ttu-id="53c6b-143">I det här fallet skiljer sig de prefix och suffix som tillämpas på gruppnamnet från dem som tillämpas på gruppaliaset.</span><span class="sxs-lookup"><span data-stu-id="53c6b-143">So in this case, the prefixes and suffixes applied to group name would be different from the ones applied to the group alias.</span></span>

- <span data-ttu-id="53c6b-144">Om du använder Yammer Office 365-anslutna grupper undviker du att \#använda \[ \]följande \<tecken \>i namnprincipen: @, , , och .</span><span class="sxs-lookup"><span data-stu-id="53c6b-144">If you are using Yammer Office 365 connected groups, avoid using the following characters in your naming policy: @, \#, \[, \], \<, and \>.</span></span> <span data-ttu-id="53c6b-145">Om dessa tecken finns i namngivningsprincipen kan vanliga Yammer-användare inte skapa grupper.</span><span class="sxs-lookup"><span data-stu-id="53c6b-145">If these characters are in the naming policy, regular Yammer users will not be able to create groups.</span></span>

## <a name="custom-blocked-words"></a><span data-ttu-id="53c6b-146">Anpassade blockerade ord</span><span class="sxs-lookup"><span data-stu-id="53c6b-146">Custom blocked words</span></span>

<span data-ttu-id="53c6b-147">Du kan ange en kommaavgränsad lista med blockerade ord som ska blockeras i gruppnamn och alias.</span><span class="sxs-lookup"><span data-stu-id="53c6b-147">You can enter a comma separated list of blocked words that will be blocked in group names and aliases.</span></span>

<span data-ttu-id="53c6b-148">Inga substrängsökningar utförs. Närmare bestämt krävs en exakt matchning mellan användarens angivna namn och de anpassade blockerade orden för att utlösa ett fel.</span><span class="sxs-lookup"><span data-stu-id="53c6b-148">No sub-string searches are carried out; specifically, an exact match between the user entered name and the custom blocked words is required to trigger a failure.</span></span> <span data-ttu-id="53c6b-149">Sub-string sökning görs inte så att användarna kan använda några av de vanliga orden som Klass även om är ett blockerat ord.</span><span class="sxs-lookup"><span data-stu-id="53c6b-149">Sub-string search isn't done so that users can use some of the common words like 'Class' even if 'ass' is a blocked word.</span></span>

<span data-ttu-id="53c6b-150">**Saker att hålla utkik efter:**</span><span class="sxs-lookup"><span data-stu-id="53c6b-150">**Things to look out for**:</span></span>

- <span data-ttu-id="53c6b-151">Blockerade ord är inte skiftlägeskänsliga.</span><span class="sxs-lookup"><span data-stu-id="53c6b-151">The blocked words are case-insensitive.</span></span>

- <span data-ttu-id="53c6b-152">Om en användare anger ett blockerat ord visas ett felmeddelande med det blockerade ordet i gruppklienten.</span><span class="sxs-lookup"><span data-stu-id="53c6b-152">When a user enters a blocked word, the group client will show an error message with the blocked word.</span></span>

- <span data-ttu-id="53c6b-153">Det finns inga teckenbegränsningar för de blockerade ord som används.</span><span class="sxs-lookup"><span data-stu-id="53c6b-153">There are no character restrictions in the blocked words used.</span></span>

- <span data-ttu-id="53c6b-154">Det finns en gräns på 5000 ord som kan ställas in som blockerade ord.</span><span class="sxs-lookup"><span data-stu-id="53c6b-154">There is a limit of 5000 words that can be set as blocked words.</span></span>

## <a name="admin-override"></a><span data-ttu-id="53c6b-155">Åsidosättning för administratör</span><span class="sxs-lookup"><span data-stu-id="53c6b-155">Admin override</span></span>

<span data-ttu-id="53c6b-p111">Vissa administratörer är undantagna från de här principerna i alla grupparbetslaster och slutpunkter så att de kan skapa grupper med blockerade ord och med de namnkonventioner de önskar. Nedan följer listan över administratörsroller som är undantagna från namnprincipen för grupp.</span><span class="sxs-lookup"><span data-stu-id="53c6b-p111">Selective administrators are exempted from these policies, across all group workloads and endpoints, so that they can create groups with these blocked words and with their desired naming conventions. The following are the list of administrator roles exempted from the group naming policy.</span></span>

- <span data-ttu-id="53c6b-158">Global administratör</span><span class="sxs-lookup"><span data-stu-id="53c6b-158">Global admin</span></span>

- <span data-ttu-id="53c6b-159">Partner Tier1-support</span><span class="sxs-lookup"><span data-stu-id="53c6b-159">Partner Tier 1 Support</span></span>

- <span data-ttu-id="53c6b-160">Partner Tier2-support</span><span class="sxs-lookup"><span data-stu-id="53c6b-160">Partner Tier 2 Support</span></span>

- <span data-ttu-id="53c6b-161">Användarkontoadministratör</span><span class="sxs-lookup"><span data-stu-id="53c6b-161">User account admin</span></span>

- <span data-ttu-id="53c6b-162">Katalogredigerare</span><span class="sxs-lookup"><span data-stu-id="53c6b-162">Directory writers</span></span>

## <a name="how-to-set-up-the-naming-policy"></a><span data-ttu-id="53c6b-163">Så här ställer du in namngivningsprincipen</span><span class="sxs-lookup"><span data-stu-id="53c6b-163">How to set up the naming policy</span></span>

<span data-ttu-id="53c6b-164">Så här ställer du in en namngivningsprincip:</span><span class="sxs-lookup"><span data-stu-id="53c6b-164">To set up a naming policy:</span></span>

1. <span data-ttu-id="53c6b-165">Klicka på **Grupper**under **Hantera**i [Azure Active Directory](https://aad.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="53c6b-165">In [Azure Active Directory](https://aad.portal.azure.com), under **Manage**, click **Groups**.</span></span>
2. <span data-ttu-id="53c6b-166">Klicka på **Namngivningsprincip**under **Inställningar.**</span><span class="sxs-lookup"><span data-stu-id="53c6b-166">Under **Settings**, click **Naming policy**.</span></span>
3. <span data-ttu-id="53c6b-167">Välj fliken **Gruppnamnprincip.**</span><span class="sxs-lookup"><span data-stu-id="53c6b-167">Choose the **Group naming policy** tab.</span></span>
4. <span data-ttu-id="53c6b-168">Under **Aktuell princip**väljer du om du vill kräva ett prefix eller suffix eller båda och markerar lämpliga kryssrutor.</span><span class="sxs-lookup"><span data-stu-id="53c6b-168">Under **Current policy**, choose if you want to require a prefix or suffix or both, and select the appropriate check boxes.</span></span>
5. <span data-ttu-id="53c6b-169">Välj mellan **Attribut** och **Sträng** för varje rad och ange sedan attributet eller strängen.</span><span class="sxs-lookup"><span data-stu-id="53c6b-169">Choose between **Attribute** and **String** for each line and then specify the attribute or string.</span></span>
6. <span data-ttu-id="53c6b-170">När du har lagt till de prefix och suffix som du behöver klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="53c6b-170">When you have added the prefixes and suffixes that you need, click **Save**.</span></span>

![Skärmbild av principinställningarna för grupper i Azure Active Directory](../../media/groups-naming-policy-azure.png)

> [!NOTE]
> <span data-ttu-id="53c6b-172">StaffHub-team följer inte namngivningsprincipen, men den underliggande Office 365-gruppen gör det.</span><span class="sxs-lookup"><span data-stu-id="53c6b-172">StaffHub teams do not follow the naming policy, but the underlying Office 365 group does.</span></span> <span data-ttu-id="53c6b-173">Prefix och suffix används inte för StaffHub-gruppnamn, och egna blockerade ord kontrolleras inte.</span><span class="sxs-lookup"><span data-stu-id="53c6b-173">StaffHub team name does not apply the prefixes and suffixes and does not check for custom blocked words.</span></span> <span data-ttu-id="53c6b-174">Men StaffHub tillämpar prefix och suffix och tar bort blockerade ord från den underliggande Office 365-gruppen.</span><span class="sxs-lookup"><span data-stu-id="53c6b-174">But StaffHub does apply the prefixes and suffixes and removes blocked words from the underlying Office 365 group.</span></span>

## <a name="more-articles-on-naming-policy"></a><span data-ttu-id="53c6b-175">Fler artiklar om namngivningsprincip</span><span class="sxs-lookup"><span data-stu-id="53c6b-175">More articles on naming policy</span></span>

[<span data-ttu-id="53c6b-176">Framtvinga en namngivningsprincip för Office 365-grupper i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="53c6b-176">Enforce a naming policy for Office 365 groups in Azure Active Directory</span></span>](https://go.microsoft.com/fwlink/?linkid=868340)

[<span data-ttu-id="53c6b-177">Azure Active Directory-cmdletar för att konfigurera gruppinställningar</span><span class="sxs-lookup"><span data-stu-id="53c6b-177">Azure Active Directory cmdlets for configuring group settings</span></span>](https://go.microsoft.com/fwlink/?linkid=868341)
