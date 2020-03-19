---
title: Namngivningsprincip för Office 365-grupper
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
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
description: Läs om hur du skapar en namngivningsprincip för Office 365-grupper.
ms.openlocfilehash: 11e2907462d325e4ad421914ae5a0deb5013e695
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42807528"
---
# <a name="office-365-groups-naming-policy"></a><span data-ttu-id="95ef4-103">Namngivningsprincip för Office 365-grupper</span><span class="sxs-lookup"><span data-stu-id="95ef4-103">Office 365 Groups naming policy</span></span>

<span data-ttu-id="95ef4-104">Du använder en princip för gruppnamngivning för att tillämpa en konsekvent namngivningsstrategi för grupper som skapats av användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="95ef4-104">You use a group naming policy to enforce a consistent naming strategy for groups created by users in your organization.</span></span> <span data-ttu-id="95ef4-105">En namngivningsprincip kan hjälpa dig och användarna att identifiera funktionen för gruppen, medlemskap, geografisk region eller vem som skapade gruppen.</span><span class="sxs-lookup"><span data-stu-id="95ef4-105">A naming policy can help you and your users identify the function of the group, membership, geographic region, or who created the group.</span></span> <span data-ttu-id="95ef4-106">Namngivningsprincipen kan också hjälpa till att kategorisera grupper i adressboken.</span><span class="sxs-lookup"><span data-stu-id="95ef4-106">The naming policy can also help categorize groups in the address book.</span></span> <span data-ttu-id="95ef4-107">Du kan använda principen för att blockera specifika ord från att användas i gruppnamn och alias.</span><span class="sxs-lookup"><span data-stu-id="95ef4-107">You can use the policy to block specific words from being used in group names and aliases.</span></span>

<span data-ttu-id="95ef4-108">Namngivningsprincipen tillämpas på grupper som skapas i alla gruppers arbetsbelastningar (som Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc).</span><span class="sxs-lookup"><span data-stu-id="95ef4-108">The naming policy is applied to groups that are created across all groups workloads (like Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc).</span></span> <span data-ttu-id="95ef4-109">Den tillämpas på både gruppnamnet och gruppaliaset.</span><span class="sxs-lookup"><span data-stu-id="95ef4-109">It gets applied to both the group name and group alias.</span></span> <span data-ttu-id="95ef4-110">Den tillämpas när en användare skapar en grupp och när gruppnamn eller alias redigeras för en befintlig grupp.</span><span class="sxs-lookup"><span data-stu-id="95ef4-110">It gets applied when a user creates a group and when group name or alias is edited for an existing group.</span></span>

> [!TIP]
> <span data-ttu-id="95ef4-111">En namngivningsprincip för Office 365-grupp gäller endast för Office 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="95ef4-111">An Office 365 group naming policy only applies to Office 365 Groups.</span></span> <span data-ttu-id="95ef4-112">Det gäller inte distributionsgrupper som skapats i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="95ef4-112">It doesn't apply to distribution groups created in Exchange Online.</span></span> <span data-ttu-id="95ef4-113">Om du vill skapa en namngivningsprincip för distributionsgrupper finns i [Skapa en namngivningsprincip för distributionsgrupper](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span><span class="sxs-lookup"><span data-stu-id="95ef4-113">To create a naming policy for distribution groups, see [Create a distribution group naming policy](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span></span>

<span data-ttu-id="95ef4-114">Namnprincipen för grupp består av följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="95ef4-114">The group naming policy consists of the following features:</span></span>

- <span data-ttu-id="95ef4-115">**Namnprincip för prefixsuffix:** Du kan använda prefix eller suffix för att definiera namngivningskonventionen\_för\_grupper (till exempel GRP\_US My Group Engineering").</span><span class="sxs-lookup"><span data-stu-id="95ef4-115">**Prefix-Suffix naming policy**: You can use prefixes or suffixes to define the naming convention of groups (for example: "GRP\_US\_My Group\_Engineering").</span></span> <span data-ttu-id="95ef4-116">Prefix och suffix kan antingen vara fasta strängar eller användarattribut som [Department], som ersätts utifrån den användare som skapar gruppen.</span><span class="sxs-lookup"><span data-stu-id="95ef4-116">The prefixes/suffixes can either be fixed strings or user attributes like [Department] that will get substituted based on the user who is creating the group.</span></span>

- <span data-ttu-id="95ef4-117">**Anpassade blockerade ord:** Du kan ladda upp en uppsättning blockerade ord som är specifika för deras organisation som skulle blockeras i grupper som skapats av användare.</span><span class="sxs-lookup"><span data-stu-id="95ef4-117">**Custom Blocked Words**: You can upload a set of blocked words specific to their organization that would be blocked in groups created by users.</span></span> <span data-ttu-id="95ef4-118">(Till exempel: "VD, Lön, HR").</span><span class="sxs-lookup"><span data-stu-id="95ef4-118">(For example: "CEO, Payroll, HR").</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="95ef4-119">Licenskrav</span><span class="sxs-lookup"><span data-stu-id="95ef4-119">Licensing requirements</span></span>

<span data-ttu-id="95ef4-120">Om du använder Namnprincip för Azure AD för Office 365-grupper krävs att du har men inte nödvändigtvis tilldela en Azure Active Directory Premium P1-licens eller Azure AD Basic EDU-licens för varje unik användare (inklusive gäster) som är medlem i en eller flera Office 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="95ef4-120">Using Azure AD naming policy for Office 365 groups requires that you possess but not necessarily assign an Azure Active Directory Premium P1 license or Azure AD Basic EDU license for each unique user (including guests) that is a member of one or more Office 365 groups.</span></span>
<span data-ttu-id="95ef4-121">Detta krävs också för administratören som skapar namngivningsprincipen Grupper.</span><span class="sxs-lookup"><span data-stu-id="95ef4-121">This is also required for the administrator that creates the Groups naming policy.</span></span>

## <a name="prefix-suffix-naming-policy"></a><span data-ttu-id="95ef4-122">Namnprinciper för prefixsuffix</span><span class="sxs-lookup"><span data-stu-id="95ef4-122">Prefix-Suffix naming policy</span></span>

<span data-ttu-id="95ef4-123">Prefix och suffix kan antingen vara fasta strängar eller användarattribut.</span><span class="sxs-lookup"><span data-stu-id="95ef4-123">Prefixes and suffixes can either be fixed strings or user attributes.</span></span>

### <a name="fixed-strings"></a><span data-ttu-id="95ef4-124">Fasta strängar</span><span class="sxs-lookup"><span data-stu-id="95ef4-124">Fixed strings</span></span>

<span data-ttu-id="95ef4-125">Du kan använda korta strängar som kan hjälpa dig att skilja grupper i GAL- och vänsternavigatorn för grupparbetsbelastningarna.</span><span class="sxs-lookup"><span data-stu-id="95ef4-125">You can use short strings that can help you differentiate groups in the GAL and Left nav of the group workloads.</span></span> <span data-ttu-id="95ef4-126">Några av de vanliga prefixen är nyckelord som\_Grp-namn ,\#\_"Namn", " Namn"</span><span class="sxs-lookup"><span data-stu-id="95ef4-126">Some of the common prefixes suffixes are Keywords like 'Grp\_Name' , '\#Name', '\_Name'</span></span>

### <a name="attributes"></a><span data-ttu-id="95ef4-127">Attribut</span><span class="sxs-lookup"><span data-stu-id="95ef4-127">Attributes</span></span>

<span data-ttu-id="95ef4-128">Du kan använda attribut som kan identifiera vem som skapade gruppen som [Avdelning] och var den skapades från som [Land].</span><span class="sxs-lookup"><span data-stu-id="95ef4-128">You can use attributes that can help identify who created the group like [Department] and where it was created from like [Country].</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="95ef4-129">**Exempel**</span><span class="sxs-lookup"><span data-stu-id="95ef4-129">**Examples**</span></span>|<span data-ttu-id="95ef4-130">Princip = "GRP [GroupName] [Department]"</span><span class="sxs-lookup"><span data-stu-id="95ef4-130">Policy = "GRP [GroupName] [Department]"</span></span>|
||<span data-ttu-id="95ef4-131">Användarens avdelning = Teknik</span><span class="sxs-lookup"><span data-stu-id="95ef4-131">User's department = Engineering</span></span>|
||<span data-ttu-id="95ef4-132">Skapat gruppnamn = "GRP Min grupp Teknik"</span><span class="sxs-lookup"><span data-stu-id="95ef4-132">Created group name = "GRP My Group Engineering"</span></span>|

<span data-ttu-id="95ef4-133">Azure Active Directory (Azure AD) attribut stöds är [Avdelning], [Företag], [Office], [StateOrProvince], [CountryOrRegion], [Titel]</span><span class="sxs-lookup"><span data-stu-id="95ef4-133">Supported Azure Active Directory (Azure AD) attributes are [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], [Title]</span></span>

- <span data-ttu-id="95ef4-p108">Användarattribut som inte stöds betraktas som fasta strängar, t.ex. "[postalCode]"</span><span class="sxs-lookup"><span data-stu-id="95ef4-p108">Unsupported user attributes are considered as fixed strings. E.g. "[postalCode]"</span></span>

- <span data-ttu-id="95ef4-137">Tilläggsattribut och egna attribut stöds inte.</span><span class="sxs-lookup"><span data-stu-id="95ef4-137">Extension attributes and custom attributes aren't supported.</span></span>

<span data-ttu-id="95ef4-138">Vi rekommenderar att du använder attribut som har värden ifyllda för alla användare i organisationen samt att du inte använder attribut som har långa värden.</span><span class="sxs-lookup"><span data-stu-id="95ef4-138">It's recommended that you use attributes that have values filled in for all users in your organization and don't use attributes that have longer values.</span></span>

### <a name="things-to-look-out-for"></a><span data-ttu-id="95ef4-139">Saker att hålla utkik efter</span><span class="sxs-lookup"><span data-stu-id="95ef4-139">Things to look out for</span></span>

- <span data-ttu-id="95ef4-140">När du skapar principen är den totala stränglängden för prefix och suffix begränsad till 53 tecken.</span><span class="sxs-lookup"><span data-stu-id="95ef4-140">During policy creation, the total prefixes and suffixes string length is restricted to 53 characters.</span></span>

- <span data-ttu-id="95ef4-p109">Prefix och suffix får innehålla specialtecken som stöds i gruppens namn och gruppalias. Om prefix och suffix innehåller specialtecken som inte är tillåtna i gruppaliaset tas de bort och tillämpas på gruppaliaset. I det här fallet skiljer sig de prefix och suffix som tillämpas på gruppnamnet från dem som tillämpas på gruppaliaset.</span><span class="sxs-lookup"><span data-stu-id="95ef4-p109">Prefixes and suffixes can contain special characters supported in group name and group alias. When the prefixes and suffixes contain special characters that are not allowed in the group alias, they are removed and applied to the group alias. So in this case, the prefixes and suffixes applied to group name would be different from the ones applied to the group alias.</span></span>

- <span data-ttu-id="95ef4-144">Om du använder Yammer Office 365-anslutna grupper bör du undvika att \# \[använda \] \<följande \>tecken i namnprincipen: @, , , och .</span><span class="sxs-lookup"><span data-stu-id="95ef4-144">If you are using Yammer Office 365 connected groups, avoid using the following characters in your naming policy: @, \#, \[, \], \<, and \>.</span></span> <span data-ttu-id="95ef4-145">Om dessa tecken finns i namngivningsprincipen kan vanliga Yammer-användare inte skapa grupper.</span><span class="sxs-lookup"><span data-stu-id="95ef4-145">If these characters are in the naming policy, regular Yammer users will not be able to create groups.</span></span>

## <a name="custom-blocked-words"></a><span data-ttu-id="95ef4-146">Anpassade blockerade ord</span><span class="sxs-lookup"><span data-stu-id="95ef4-146">Custom blocked words</span></span>

<span data-ttu-id="95ef4-147">Du kan ange en kommaavgränsad lista med blockerade ord som ska blockeras i gruppnamn och alias.</span><span class="sxs-lookup"><span data-stu-id="95ef4-147">You can enter a comma separated list of blocked words that will be blocked in group names and aliases.</span></span>

<span data-ttu-id="95ef4-148">Den blockerade ordkontrollen görs på det angivna gruppnamnet för användaren.</span><span class="sxs-lookup"><span data-stu-id="95ef4-148">The blocked words check is done on the user entered group name.</span></span> <span data-ttu-id="95ef4-149">Så om användaren anger "darnit" och "Prefix"\_är\_namngivningsprincipen, misslyckas "Prefix darnit".</span><span class="sxs-lookup"><span data-stu-id="95ef4-149">So if user enters 'darnit' and 'Prefix\_' is the naming policy, 'Prefix\_darnit' will fail.</span></span>

<span data-ttu-id="95ef4-150">Inga understrängssökningar görs. Specifikt krävs en exakt matchning mellan det angivna användarnamnet och de anpassade blockerade orden för att utlösa ett fel.</span><span class="sxs-lookup"><span data-stu-id="95ef4-150">No sub-string searches are carried out; specifically, an exact match between the user entered name and the custom blocked words is required to trigger a failure.</span></span> <span data-ttu-id="95ef4-151">Understrängssökning görs inte så att användarna kan använda några av de vanliga orden som "Klass" även om "röv" är ett blockerat ord.</span><span class="sxs-lookup"><span data-stu-id="95ef4-151">Sub-string search isn't done so that users can use some of the common words like 'Class' even if 'ass' is a blocked word.</span></span>

<span data-ttu-id="95ef4-152">**Saker att se upp för:**</span><span class="sxs-lookup"><span data-stu-id="95ef4-152">**Things to look out for**:</span></span>

- <span data-ttu-id="95ef4-153">Blockerade ord är inte skiftlägeskänsliga.</span><span class="sxs-lookup"><span data-stu-id="95ef4-153">The blocked words are case-insensitive.</span></span>

- <span data-ttu-id="95ef4-154">Om en användare anger ett blockerat ord visas ett felmeddelande med det blockerade ordet i gruppklienten.</span><span class="sxs-lookup"><span data-stu-id="95ef4-154">When a user enters a blocked word, the group client will show an error message with the blocked word.</span></span>

- <span data-ttu-id="95ef4-155">Det finns inga teckenbegränsningar för de blockerade ord som används.</span><span class="sxs-lookup"><span data-stu-id="95ef4-155">There are no character restrictions in the blocked words used.</span></span>

- <span data-ttu-id="95ef4-156">Det finns en övre gräns på 5000 ord som kan ställas in som blockerade ord.</span><span class="sxs-lookup"><span data-stu-id="95ef4-156">There is an upper limit of 5000 words that can be set as blocked words.</span></span>

## <a name="admin-override"></a><span data-ttu-id="95ef4-157">Åsidosättning för administratör</span><span class="sxs-lookup"><span data-stu-id="95ef4-157">Admin override</span></span>

<span data-ttu-id="95ef4-p113">Vissa administratörer är undantagna från de här principerna i alla grupparbetslaster och slutpunkter så att de kan skapa grupper med blockerade ord och med de namnkonventioner de önskar. Nedan följer listan över administratörsroller som är undantagna från namnprincipen för grupp.</span><span class="sxs-lookup"><span data-stu-id="95ef4-p113">Selective administrators are exempted from these policies, across all group workloads and endpoints, so that they can create groups with these blocked words and with their desired naming conventions. The following are the list of administrator roles exempted from the group naming policy.</span></span>

- <span data-ttu-id="95ef4-160">Global administratör</span><span class="sxs-lookup"><span data-stu-id="95ef4-160">Global admin</span></span>

- <span data-ttu-id="95ef4-161">Partner Tier1-support</span><span class="sxs-lookup"><span data-stu-id="95ef4-161">Partner Tier 1 Support</span></span>

- <span data-ttu-id="95ef4-162">Partner Tier2-support</span><span class="sxs-lookup"><span data-stu-id="95ef4-162">Partner Tier 2 Support</span></span>

- <span data-ttu-id="95ef4-163">Användarkontoadministratör</span><span class="sxs-lookup"><span data-stu-id="95ef4-163">User account admin</span></span>

- <span data-ttu-id="95ef4-164">Katalogredigerare</span><span class="sxs-lookup"><span data-stu-id="95ef4-164">Directory writers</span></span>

## <a name="how-to-set-up-the-naming-policy"></a><span data-ttu-id="95ef4-165">Så här konfigurerar du namngivningsprincipen</span><span class="sxs-lookup"><span data-stu-id="95ef4-165">How to set up the naming policy</span></span>

<span data-ttu-id="95ef4-166">Så här konfigurerar du en namngivningsprincip:</span><span class="sxs-lookup"><span data-stu-id="95ef4-166">To set up a naming policy:</span></span>

1. <span data-ttu-id="95ef4-167">Klicka på **Grupper**under **Hantera**i [Azure Active Directory](https://aad.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="95ef4-167">In [Azure Active Directory](https://aad.portal.azure.com), under **Manage**, click **Groups**.</span></span>
2. <span data-ttu-id="95ef4-168">Klicka på **Namngivningsprincip**under **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="95ef4-168">Under **Settings**, click **Naming policy**.</span></span>
3. <span data-ttu-id="95ef4-169">Välj fliken **Grupprincip.**</span><span class="sxs-lookup"><span data-stu-id="95ef4-169">Choose the **Group naming policy** tab.</span></span>
4. <span data-ttu-id="95ef4-170">Under **Aktuell princip**väljer du om du vill kräva ett prefix eller ett suffix eller båda, och markerar lämpliga kryssrutor.</span><span class="sxs-lookup"><span data-stu-id="95ef4-170">Under **Current policy**, choose if you want to require a prefix or suffix or both, and select the appropriate check boxes.</span></span>
5. <span data-ttu-id="95ef4-171">Välj mellan **Attribut** och **sträng** för varje rad och ange sedan attributet eller strängen.</span><span class="sxs-lookup"><span data-stu-id="95ef4-171">Choose between **Attribute** and **String** for each line and then specify the attribute or string.</span></span>
6. <span data-ttu-id="95ef4-172">När du har lagt till de prefix och suffix som du behöver klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="95ef4-172">When you have added the prefixes and suffixes that you need, click **Save**.</span></span>

![Skärmbild av de grupper som namnger principinställningar i Azure Active Directory](../../media/groups-naming-policy-azure.png)

## <a name="naming-policy-experiences-across-office-365-apps"></a><span data-ttu-id="95ef4-174">Namnprincipanvändning i alla Office 365-program</span><span class="sxs-lookup"><span data-stu-id="95ef4-174">Naming policy experiences across Office 365 apps</span></span>

<span data-ttu-id="95ef4-p114">Office 365-programmen har uppdaterats så att en förhandsgranskning av namnet på namnprincipen för grupp (med prefix och suffix) visas när användaren skriver in gruppens namn och alias. Om användarna skriver in blockerade ord visas ett felmeddelande så att de kan ta bort de blockerade orden.</span><span class="sxs-lookup"><span data-stu-id="95ef4-p114">The Office 365 apps have been updated to show a preview of the naming policy group name (with prefixes and suffixes) when the user types in the group name and alias. When the user enters blocked words, they'll see an error message so they can remove the blocked words.</span></span>

## <a name="outlook-on-the-web"></a><span data-ttu-id="95ef4-177">Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="95ef4-177">Outlook on the web</span></span>

<span data-ttu-id="95ef4-178">Outlook på webben (tidigare känt som Outlook Web App eller OWA) visar namngivningsprincipen sett när användaren skriver ett gruppnamn eller gruppalias.</span><span class="sxs-lookup"><span data-stu-id="95ef4-178">Outlook on the web (formerly known as Outlook Web App or OWA) shows the naming policy decorated name when the user types a group name or group alias.</span></span> <span data-ttu-id="95ef4-179">Om en användare skriver in ett eget blockerat ord visas ett felmeddelande i användargränssnittet tillsammans med blockerade ordet så att användaren kan ta bort det.</span><span class="sxs-lookup"><span data-stu-id="95ef4-179">When an user enters a custom blocked word, an error message is shown in the UI along with the blocked word so that the user can remove it.</span></span> <span data-ttu-id="95ef4-180">Ögonblicksbilder av webbupplevelsen visas nedan.</span><span class="sxs-lookup"><span data-stu-id="95ef4-180">Outlook on the web experience snapshots are shown below.</span></span>

![Sida vid sida för gruppnamngivningsprincip i Office 365-grupper](../../media/1a21657a-c542-4d9e-ac7d-887ac542a9d9.png)

## <a name="outlook-desktop"></a><span data-ttu-id="95ef4-182">Outlook (skrivbordsversion)</span><span class="sxs-lookup"><span data-stu-id="95ef4-182">Outlook Desktop</span></span>

<span data-ttu-id="95ef4-183">Grupper som har skapats i skrivbordsversionen av Outlook följer namnprincipen.</span><span class="sxs-lookup"><span data-stu-id="95ef4-183">Groups created in Outlook desktop are compliant with naming policy.</span></span> <span data-ttu-id="95ef4-184">I skrivbordsversionen av Outlook visas ännu inte förhandsgranskningen av namnprincipen, och felmeddelanden för egna blockerade ord returneras inte när användaren anger gruppens namn.</span><span class="sxs-lookup"><span data-stu-id="95ef4-184">Outlook desktop app doesn't yet show the preview of the naming policy and doesn't return the custom blocked word errors, when the user enters the group name.</span></span> <span data-ttu-id="95ef4-185">Namngivningsprincipen tillämpas dock automatiskt vid val av skapa/redigera och användarna visas med fel om det finns anpassade blockerade ord i gruppnamnet eller aliaset.</span><span class="sxs-lookup"><span data-stu-id="95ef4-185">However, naming policy will be automatically applied on selecting create/edit and users will be presented with errors if there are custom blocked words in the group name or alias.</span></span>

## <a name="microsoft-teams"></a><span data-ttu-id="95ef4-186">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="95ef4-186">Microsoft Teams</span></span>

<span data-ttu-id="95ef4-187">Microsoft Teams visar namnet på namnet på namngivningsprincipen när användaren skriver ett teamnamn.</span><span class="sxs-lookup"><span data-stu-id="95ef4-187">Microsoft Teams shows the naming policy decorated name when the user types a team name.</span></span> <span data-ttu-id="95ef4-188">När en användare anger ett anpassat blockerat ord visas ett felmeddelande tillsammans med det blockerade ordet så att användaren kan ta bort det.</span><span class="sxs-lookup"><span data-stu-id="95ef4-188">When a user enters a custom blocked word, an error message is shown along with the blocked word so that the user can remove it.</span></span>

![Gruppnamnsprincip i Microsoft Teams blockerade exempel](../../media/7c904546-5853-4642-949a-a55dbb004eca.png)

## <a name="sharepoint"></a><span data-ttu-id="95ef4-190">Sharepoint</span><span class="sxs-lookup"><span data-stu-id="95ef4-190">SharePoint</span></span>

<span data-ttu-id="95ef4-191">SharePoint visar namnprincipnamnet när användaren skriver ett webbplatsnamn eller en grupps e-postadress.</span><span class="sxs-lookup"><span data-stu-id="95ef4-191">SharePoint shows the naming policy name when the user types a site name or group email address.</span></span> <span data-ttu-id="95ef4-192">Om en användare skriver in ett eget blockerat ord visas ett felmeddelande tillsammans med blockerade ordet så att användaren kan ta bort det.</span><span class="sxs-lookup"><span data-stu-id="95ef4-192">When an user enters a custom blocked word, an error message is shown, along with the blocked word so that the user can remove it.</span></span>

![Grornamnprincip - Blockerade SharePoint-webbplatsnamn](../../media/cf0d6158-fd32-4a93-ac24-2e037102c42c.png)

## <a name="microsoft-stream"></a><span data-ttu-id="95ef4-194">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="95ef4-194">Microsoft Stream</span></span>

<span data-ttu-id="95ef4-p119">I Microsoft Stream visas namnprincipens dekorerade namn när användaren skriver in ett gruppnamn eller gruppalias. Om en användare skriver in ett eget blockerat ord visas ett felmeddelande med det blockerade ordet så att användaren kan ta bort det.</span><span class="sxs-lookup"><span data-stu-id="95ef4-p119">Microsoft Stream shows the naming policy decorated name when the user types a group name or group email alias. When an user enters a custom blocked word, an error message is shown with the blocked word so the user can remove it.</span></span>

![Grupprincip blockerad t.ex.](../../media/9748f52a-3814-41a6-9ac1-4e8cd4c91011.png)

## <a name="outlook-ios-and-android-app"></a><span data-ttu-id="95ef4-198">Outlook.app för iOS och Android</span><span class="sxs-lookup"><span data-stu-id="95ef4-198">Outlook iOS and Android App</span></span>

<span data-ttu-id="95ef4-199">Grupper som har skapats i Outlook-appar följer namnprincipen.</span><span class="sxs-lookup"><span data-stu-id="95ef4-199">Groups created in Outlook apps are compliant with naming policy.</span></span> <span data-ttu-id="95ef4-200">I Outlook Mobile visas förhandsgranskningen av namngivningsprincipen när du anger gruppnamnet.</span><span class="sxs-lookup"><span data-stu-id="95ef4-200">Outlook mobile shows the naming policy preview when entering the Group name.</span></span> <span data-ttu-id="95ef4-201">När en användare anger ett anpassat blockerat ord visas ett felmeddelande när gruppen skapas, så att användaren kan ta bort det blockerade ordet.</span><span class="sxs-lookup"><span data-stu-id="95ef4-201">When a user enters a custom blocked word, an error message is shown on creating the group, so the user can remove the blocked word.</span></span>

## <a name="planner"></a><span data-ttu-id="95ef4-202">Planner</span><span class="sxs-lookup"><span data-stu-id="95ef4-202">Planner</span></span>

<span data-ttu-id="95ef4-203">Planner följer namnprincipen.</span><span class="sxs-lookup"><span data-stu-id="95ef4-203">Planner is compliant with naming policy.</span></span> <span data-ttu-id="95ef4-204">Planner visar förhandsgranskningen av namngivningsprincipen när du anger namnet Planera.</span><span class="sxs-lookup"><span data-stu-id="95ef4-204">Planner shows the naming policy preview when entering the Plan name.</span></span> <span data-ttu-id="95ef4-205">När en användare anger ett anpassat blockerat ord visas ett felmeddelande när planen skapas, så att användaren kan ta bort det blockerade ordet.</span><span class="sxs-lookup"><span data-stu-id="95ef4-205">When a user enters a custom blocked word, an error message is shown on creating the plan, so the user can remove the blocked word.</span></span>

![Gruppnamngivningsprincip - skapa nytt blockerat exempel för plan](../../media/ea692b44-3a56-4e6d-bcb8-8444fe5bbc4f.png)

## <a name="dynamics-365-for-customer-engagement"></a><span data-ttu-id="95ef4-207">Dynamics 365 för kundengagemang</span><span class="sxs-lookup"><span data-stu-id="95ef4-207">Dynamics 365 for Customer Engagement</span></span>

<span data-ttu-id="95ef4-208">Dynamics 365 for Customer Engagement är kompatibel med namngivningsprincipen.</span><span class="sxs-lookup"><span data-stu-id="95ef4-208">Dynamics 365 for Customer Engagement is compliant with naming policy.</span></span> <span data-ttu-id="95ef4-209">Dynamics 365 visar namnet på namnet på namngivningsprincipen när användaren skriver ett gruppnamn eller ett e-postalias för grupper.</span><span class="sxs-lookup"><span data-stu-id="95ef4-209">Dynamics 365 shows the naming policy decorated name when the user types a group name or group email alias.</span></span> <span data-ttu-id="95ef4-210">När användaren anger ett anpassat blockerat ord visas ett felmeddelande med det blockerade ordet så att användaren kan ta bort det.</span><span class="sxs-lookup"><span data-stu-id="95ef4-210">When the user enters a custom blocked word, an error message is shown with the blocked word so the user can remove it.</span></span>

![Dynamik 365](../../media/8190331c-6779-42bd-a6b3-f7007428c8ae.png)

## <a name="school-data-sync-sds"></a><span data-ttu-id="95ef4-212">School Data Sync (SDS)</span><span class="sxs-lookup"><span data-stu-id="95ef4-212">School Data Sync (SDS)</span></span>

<span data-ttu-id="95ef4-p123">Grupper som skapats i SDS följer namnprincipen, men namnprincipen används inte automatiskt. SDS-administratörer måste lägga till prefix och suffix till klassnamn. Grupper måste sedan skapas och laddas upp till SDS. Annars går det inte att skapa/redigera grupper.</span><span class="sxs-lookup"><span data-stu-id="95ef4-p123">Groups created through SDS comply with naming policy, but the naming policy isn't applied automatically. SDS administrators have to append the prefixes and suffixes to class names for which groups need to be created and then upload to SDS. Groups creation/edit would fail otherwise.</span></span>

## <a name="outlook-customer-manager-ocm"></a><span data-ttu-id="95ef4-216">Outlook Customer Manager (OCM)</span><span class="sxs-lookup"><span data-stu-id="95ef4-216">Outlook Customer Manager (OCM)</span></span>

<span data-ttu-id="95ef4-217">Outlook Customer Manager är kompatibel med namngivningsprincipen.</span><span class="sxs-lookup"><span data-stu-id="95ef4-217">Outlook Customer Manager is compliant with naming policy.</span></span> <span data-ttu-id="95ef4-218">Namngivningsprincipen tillämpas automatiskt på gruppen som skapats i Outlook Customer Manager.</span><span class="sxs-lookup"><span data-stu-id="95ef4-218">The naming policy gets automatically applied to the group created in Outlook Customer Manager.</span></span> <span data-ttu-id="95ef4-219">Om något av orden i "All Sales Team" definieras som ett anpassat blockerat ord blockeras gruppskapandet i OCM.</span><span class="sxs-lookup"><span data-stu-id="95ef4-219">If any of the words within "All Sales Team" is defined as a custom blocked word, the group creation in OCM will be blocked.</span></span> <span data-ttu-id="95ef4-220">Användaren kommer inte att kunna skapa OCM-gruppen och kommer att blockeras från att använda OCM-appen."</span><span class="sxs-lookup"><span data-stu-id="95ef4-220">The user will not be able to create the OCM group and will be blocked from using the OCM app."</span></span>

## <a name="classroom-app"></a><span data-ttu-id="95ef4-221">Classroom-app</span><span class="sxs-lookup"><span data-stu-id="95ef4-221">Classroom App</span></span>

<span data-ttu-id="95ef4-p125">Grupper som skapas i Classroom-appen följer namnprincipen men namnprincipen används inte automatiskt, och förhandsgranskning av namnprincipen visas inte för användarna när de anger ett klassrumsgruppnamn. Användarna måste alltså ange det dekorerade klassrumsgruppnamnet med prefix och suffix. Annars går det inte att skapa/redigera klassrumsgruppen.</span><span class="sxs-lookup"><span data-stu-id="95ef4-p125">Groups created in classroom app comply with naming policy, but the naming policy isn't applied automatically, and the naming policy preview isn't shown to the users while entering a classroom group name. So users would have to enter the decorated classroom group name with prefixes and suffixes. Otherwise the classroom group create or edit will fail with errors.</span></span>

## <a name="power-bi"></a><span data-ttu-id="95ef4-225">Power BI</span><span class="sxs-lookup"><span data-stu-id="95ef4-225">Power BI</span></span>

<span data-ttu-id="95ef4-226">Grupper som skapas i Power BI-arbetsytor följer namngivningsprincipen, men namngivningsprincipen tillämpas inte automatiskt.</span><span class="sxs-lookup"><span data-stu-id="95ef4-226">Groups created in Power BI workspaces comply with the naming policy, but the naming policy isn't applied automatically.</span></span> <span data-ttu-id="95ef4-227">Och förhandsgranskningen av namngivningsprincipen visas inte för användarna när de anger ett Power BI-arbetsytenamn.</span><span class="sxs-lookup"><span data-stu-id="95ef4-227">And, the naming policy preview isn't shown to users when they enter a Power BI workspace name.</span></span>

<span data-ttu-id="95ef4-228">Det rekommenderade namnet - med den namngivningsprincip som används - visas i felinformationen för att skapa eller redigera arbetsytor.</span><span class="sxs-lookup"><span data-stu-id="95ef4-228">The recommended name - with the naming policy applied - is shown in the error details on create or edit workspaces.</span></span> <span data-ttu-id="95ef4-229">Det innebär att användarna måste ange det dekorerade arbetsytenamnet med prefix och suffix.</span><span class="sxs-lookup"><span data-stu-id="95ef4-229">This means users have to enter the decorated workspace name with prefixes and suffixes.</span></span> <span data-ttu-id="95ef4-230">Annars misslyckas eller misslyckas arbetsytan med fel.</span><span class="sxs-lookup"><span data-stu-id="95ef4-230">Otherwise the workspace create or edit will fail with errors.</span></span>

## <a name="yammer"></a><span data-ttu-id="95ef4-231">Yammer</span><span class="sxs-lookup"><span data-stu-id="95ef4-231">Yammer</span></span>

<span data-ttu-id="95ef4-232">När en användare som är inloggad på Yammer med sitt Azure Active Directory-konto skapar en grupp eller redigerar ett gruppnamn, följer gruppnamnet namngivningsprincipen.</span><span class="sxs-lookup"><span data-stu-id="95ef4-232">When a user signed in to Yammer with their Azure Active Directory account creates a group or edits a group name, the group name will comply with naming policy.</span></span> <span data-ttu-id="95ef4-233">Detta gäller både för Office 365-anslutna grupper och alla andra Yammer-grupper.</span><span class="sxs-lookup"><span data-stu-id="95ef4-233">This applies both to Office 365 connected groups and all other Yammer groups.</span></span>

<span data-ttu-id="95ef4-234">Om en ansluten office 365-grupp skapades innan namngivningsprincipen är på plats följer gruppnamnet inte automatiskt namngivningsprinciperna.</span><span class="sxs-lookup"><span data-stu-id="95ef4-234">If an Office 365 connected group was created before the naming policy is in place, the group name will not automatically follow the naming policies.</span></span> <span data-ttu-id="95ef4-235">När en användare redigerar gruppnamnet uppmanas de att lägga till prefixet och suffixet.</span><span class="sxs-lookup"><span data-stu-id="95ef4-235">When a user edits the group name, they will be prompted to add the prefix and suffix.</span></span>

<span data-ttu-id="95ef4-236">Om namngivningsprincipen innehåller tecken som inte kan finnas i Yammer-gruppnamn kan endast administratörer skapa en ansluten grupp i Yammer.</span><span class="sxs-lookup"><span data-stu-id="95ef4-236">If the naming policy includes characters that can't be in Yammer group names, only admins will be able to create a connected group in Yammer.</span></span>

## <a name="staffhub"></a><span data-ttu-id="95ef4-237">StaffHub (på b80)</span><span class="sxs-lookup"><span data-stu-id="95ef4-237">StaffHub</span></span>

<span data-ttu-id="95ef4-238">StaffHub-team följer inte namngivningsprincipen, men den underliggande Office 365-gruppen gör det.</span><span class="sxs-lookup"><span data-stu-id="95ef4-238">StaffHub teams do not follow the naming policy, but the underlying Office 365 group does.</span></span> <span data-ttu-id="95ef4-239">Prefix och suffix används inte för StaffHub-gruppnamn, och egna blockerade ord kontrolleras inte.</span><span class="sxs-lookup"><span data-stu-id="95ef4-239">StaffHub team name does not apply the prefixes and suffixes and does not check for custom blocked words.</span></span> <span data-ttu-id="95ef4-240">Men StaffHub tillämpar prefixoch suffix och tar bort blockerade ord från den underliggande Office 365-gruppen.</span><span class="sxs-lookup"><span data-stu-id="95ef4-240">But StaffHub does apply the prefixes and suffixes and removes blocked words from the underlying Office 365 group.</span></span>

## <a name="exchange-powershell"></a><span data-ttu-id="95ef4-241">Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="95ef4-241">Exchange PowerShell</span></span>

<span data-ttu-id="95ef4-p131">Exchange PowerShell-cmdlet:ar följer namnprincipen. Användarna får felmeddelanden med förslag på prefix och suffix och även för egna blockerade ord om namnprinciper inte används i gruppnamn och gruppalias.</span><span class="sxs-lookup"><span data-stu-id="95ef4-p131">Exchange PowerShell cmdlets are compliant with naming policy. Users will get appropriate error messages with suggested prefixes and suffixes and for custom blocked words if naming convention isn't used in the group names and group alias.</span></span>

## <a name="azure-active-directory-powershell-cmdlets"></a><span data-ttu-id="95ef4-244">Azure Active Directory PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="95ef4-244">Azure Active Directory PowerShell cmdlets</span></span>

<span data-ttu-id="95ef4-245">Azure Active Directory PowerShell-cmdlets är kompatibla med namngivningsprincipen.</span><span class="sxs-lookup"><span data-stu-id="95ef4-245">Azure Active Directory PowerShell cmdlets are compliant with naming policy.</span></span> <span data-ttu-id="95ef4-246">Användarna får felmeddelanden med förslag på prefix och suffix och även för egna blockerade ord om namnprinciper inte används i gruppnamn och gruppalias.</span><span class="sxs-lookup"><span data-stu-id="95ef4-246">Users will get appropriate error messages with suggested prefixes and suffixes and for custom blocked words if naming convention isn't used in the group names and group alias.</span></span>

## <a name="exchange-admin-center"></a><span data-ttu-id="95ef4-247">Administrationscenter för Exchange</span><span class="sxs-lookup"><span data-stu-id="95ef4-247">Exchange admin center</span></span>

<span data-ttu-id="95ef4-248">Administrationscentret för Exchange (EAC) är kompatibelt med namngivningsprincipen.</span><span class="sxs-lookup"><span data-stu-id="95ef4-248">The Exchange admin center (EAC) is compliant with naming policy.</span></span> <span data-ttu-id="95ef4-249">När användarna skapar eller redigerar grupper får de felmeddelanden med förslag på prefix och suffix och även för egna blockerade ord om namnprinciper inte används i gruppnamn och gruppalias.</span><span class="sxs-lookup"><span data-stu-id="95ef4-249">On create or edit actions, users will get appropriate error messages with suggested prefixes and suffixes and for custom blocked words if naming convention isn't used in the group names and group alias.</span></span>

## <a name="microsoft-365-admin-center"></a><span data-ttu-id="95ef4-250">Administrationscenter för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="95ef4-250">Microsoft 365 admin center</span></span>

<span data-ttu-id="95ef4-251">Administrationscentret för Microsoft 365 är kompatibelt med namngivningsprincipen.</span><span class="sxs-lookup"><span data-stu-id="95ef4-251">The Microsoft 365 admin center is compliant with naming policy.</span></span> <span data-ttu-id="95ef4-252">Namnprincipen används automatiskt när grupper skapas eller redigeras.</span><span class="sxs-lookup"><span data-stu-id="95ef4-252">On create or edit actions, naming policy will automatically get applied.</span></span> <span data-ttu-id="95ef4-253">Felmeddelanden visas om användarna skriver in egna blockerade ord.</span><span class="sxs-lookup"><span data-stu-id="95ef4-253">Users will get appropriate errors when they enter custom blocked words.</span></span> <span data-ttu-id="95ef4-254">Administrationscentret för Microsoft 365 visar ännu inte förhandsgranskningen av namngivningsprincipen och returnerar inte de anpassade blockerade ordfelen när användaren anger gruppnamnet.</span><span class="sxs-lookup"><span data-stu-id="95ef4-254">The Microsoft 365 admin center doesn't yet show the preview of the naming policy and doesn't return the custom blocked word errors, when the user enters the group name.</span></span>

## <a name="azure-active-directory-portal"></a><span data-ttu-id="95ef4-255">Azure Active Directory-portal</span><span class="sxs-lookup"><span data-stu-id="95ef4-255">Azure Active Directory portal</span></span>

<span data-ttu-id="95ef4-256">Azure Active Directory-portalen är kompatibel med namngivningsprincipen.</span><span class="sxs-lookup"><span data-stu-id="95ef4-256">The Azure Active Directory portal is compliant with naming policy.</span></span> <span data-ttu-id="95ef4-257">Azure Active Directory-portalen visar förhandsgranskningen av namngivningsprincipen när gruppens namn matas in.</span><span class="sxs-lookup"><span data-stu-id="95ef4-257">Azure Active Directory portal shows the naming policy preview when entering the Group name.</span></span> <span data-ttu-id="95ef4-258">När en användare anger ett anpassat blockerat ord visas ett felmeddelande när gruppen skapas, så att användaren kan ta bort det blockerade ordet.</span><span class="sxs-lookup"><span data-stu-id="95ef4-258">When a user enters a custom blocked word, an error message is shown on creating the group, so the user can remove the blocked word.</span></span>

## <a name="more-articles-on-naming-policy"></a><span data-ttu-id="95ef4-259">Fler artiklar om namngivningspolicy</span><span class="sxs-lookup"><span data-stu-id="95ef4-259">More articles on naming policy</span></span>

[<span data-ttu-id="95ef4-260">Tillämpa en namngivningsprincip för Office 365-grupper i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="95ef4-260">Enforce a naming policy for Office 365 groups in Azure Active Directory</span></span>](https://go.microsoft.com/fwlink/?linkid=868340)

[<span data-ttu-id="95ef4-261">Azure Active Directory-cmdlets för konfigurera gruppinställningar</span><span class="sxs-lookup"><span data-stu-id="95ef4-261">Azure Active Directory cmdlets for configuring group settings</span></span>](https://go.microsoft.com/fwlink/?linkid=868341)
