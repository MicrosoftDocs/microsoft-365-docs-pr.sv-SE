---
title: Kom igång med aktivitetsutforskaren
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Aktivitetsutforskaren avrundar funktionaliteten i dataklassificeringsfunktionen genom att du kan se och filtrera på de åtgärder som användarna gör på det etiketterade innehållet.
ms.openlocfilehash: 414ef4e5d9f6472180a5eaef391d3eba33463b02
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52162945"
---
# <a name="get-started-with-activity-explorer"></a><span data-ttu-id="cbd8a-103">Kom igång med aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="cbd8a-103">Get started with activity explorer</span></span>

<span data-ttu-id="cbd8a-104">Med [flikarna Översikt över](data-classification-overview.md) [dataklassificering och](data-classification-content-explorer.md) Innehållsutforskaren får du insyn i vilket innehåll som har identifierats och etiketterats och var innehållet finns.</span><span class="sxs-lookup"><span data-stu-id="cbd8a-104">The [data classification overview](data-classification-overview.md) and [content explorer](data-classification-content-explorer.md) tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="cbd8a-105">Aktivitetsutforskaren avrundar den här funktionssviten genom att låta dig övervaka vad som görs med det etiketterade innehållet.</span><span class="sxs-lookup"><span data-stu-id="cbd8a-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="cbd8a-106">Aktivitetsutforskaren ger en historisk vy av aktiviteter på ditt etiketterade innehåll.</span><span class="sxs-lookup"><span data-stu-id="cbd8a-106">Activity explorer provides a historical view of activities on your labeled content.</span></span> <span data-ttu-id="cbd8a-107">Aktivitetsinformation samlas in från Microsoft 365 enhetliga granskningsloggar, transformerade och tillgängliga i användargränssnittet för Aktivitetsutforskaren.</span><span class="sxs-lookup"><span data-stu-id="cbd8a-107">The activity information is collected from the Microsoft 365 unified audit logs, transformed and made available in the Activity explorer UI.</span></span> 

![Översikt över aktivitetsutforskaren för platshållare](../media/data-classification-activity-explorer-1.png)

<span data-ttu-id="cbd8a-109">Det finns över 30 olika filter att använda och några är:</span><span class="sxs-lookup"><span data-stu-id="cbd8a-109">There are over 30 different filters available for use, some are:</span></span>

- <span data-ttu-id="cbd8a-110">datumintervall</span><span class="sxs-lookup"><span data-stu-id="cbd8a-110">date range</span></span>
- <span data-ttu-id="cbd8a-111">aktivitetstyp</span><span class="sxs-lookup"><span data-stu-id="cbd8a-111">activity type</span></span>
- <span data-ttu-id="cbd8a-112">plats</span><span class="sxs-lookup"><span data-stu-id="cbd8a-112">location</span></span>
- <span data-ttu-id="cbd8a-113">användare</span><span class="sxs-lookup"><span data-stu-id="cbd8a-113">user</span></span>
- <span data-ttu-id="cbd8a-114">känslighetsetikett</span><span class="sxs-lookup"><span data-stu-id="cbd8a-114">sensitivity label</span></span>
- <span data-ttu-id="cbd8a-115">bevarandeetikett</span><span class="sxs-lookup"><span data-stu-id="cbd8a-115">retention label</span></span>
- <span data-ttu-id="cbd8a-116">filsökväg</span><span class="sxs-lookup"><span data-stu-id="cbd8a-116">file path</span></span>
- <span data-ttu-id="cbd8a-117">DLP-princip</span><span class="sxs-lookup"><span data-stu-id="cbd8a-117">DLP policy</span></span>



## <a name="prerequisites"></a><span data-ttu-id="cbd8a-118">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="cbd8a-118">Prerequisites</span></span>

<span data-ttu-id="cbd8a-119">Varje konto som har åtkomst till och använder dataklassificering, måste ha en tilldelad licens från någon av dessa prenumerationer:</span><span class="sxs-lookup"><span data-stu-id="cbd8a-119">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="cbd8a-120">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="cbd8a-120">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="cbd8a-121">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="cbd8a-121">Office 365 (E5)</span></span>
- <span data-ttu-id="cbd8a-122">Tillägget Advanced Compliance (E5)</span><span class="sxs-lookup"><span data-stu-id="cbd8a-122">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="cbd8a-123">Tillägget Advanced Threat Intelligence (E5)</span><span class="sxs-lookup"><span data-stu-id="cbd8a-123">Advanced Threat Intelligence (E5) add-on</span></span>
- <span data-ttu-id="cbd8a-124">Microsoft 365 E5/A5 – Informationsskydd och styrning</span><span class="sxs-lookup"><span data-stu-id="cbd8a-124">Microsoft 365 E5/A5 Info Protection & Governance</span></span>
- <span data-ttu-id="cbd8a-125">Microsoft 365 E5/A5 – Efterlevnad</span><span class="sxs-lookup"><span data-stu-id="cbd8a-125">Microsoft 365 E5/A5 Compliance</span></span>

### <a name="permissions"></a><span data-ttu-id="cbd8a-126">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="cbd8a-126">Permissions</span></span>

 <span data-ttu-id="cbd8a-127">För att få åtkomst till fliken aktivitetsutforskaren måste ett konto uttryckligen tilldelas medlemskap i någon av rollgrupperna eller uttryckligen beviljas rollen.</span><span class="sxs-lookup"><span data-stu-id="cbd8a-127">In order to get access to the activity explorer tab, an account must be explicitly assigned membership in any one of these role groups or explicitly granted the role.</span></span>

<!--
> [!IMPORTANT]
> Access to Activity explorer via the Security reader or Device Management role groups or other has been removed-->

<span data-ttu-id="cbd8a-128">**Microsoft 365-rollgrupper**</span><span class="sxs-lookup"><span data-stu-id="cbd8a-128">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="cbd8a-129">Global administratör</span><span class="sxs-lookup"><span data-stu-id="cbd8a-129">Global administrator</span></span>
- <span data-ttu-id="cbd8a-130">Efterlevnadsadministratör</span><span class="sxs-lookup"><span data-stu-id="cbd8a-130">Compliance administrator</span></span>
- <span data-ttu-id="cbd8a-131">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="cbd8a-131">Security administrator</span></span>
- <span data-ttu-id="cbd8a-132">Administratör för efterlevnadsdata</span><span class="sxs-lookup"><span data-stu-id="cbd8a-132">Compliance data administrator</span></span>

<span data-ttu-id="cbd8a-133">**Microsoft 365 roller**</span><span class="sxs-lookup"><span data-stu-id="cbd8a-133">**Microsoft 365 roles**</span></span>

- <span data-ttu-id="cbd8a-134">Efterlevnadsadministratör</span><span class="sxs-lookup"><span data-stu-id="cbd8a-134">Compliance administrator</span></span>
- <span data-ttu-id="cbd8a-135">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="cbd8a-135">Security administrator</span></span>

## <a name="activity-types"></a><span data-ttu-id="cbd8a-136">Aktivitetstyper</span><span class="sxs-lookup"><span data-stu-id="cbd8a-136">Activity types</span></span>

<span data-ttu-id="cbd8a-137">Aktivitetsutforskaren samlar in aktivitetsinformation från granskningsloggar på flera aktivitetskällor.</span><span class="sxs-lookup"><span data-stu-id="cbd8a-137">Activity explorer gathers activity information from the audit logs on multiple sources of activities.</span></span> <span data-ttu-id="cbd8a-138">Mer detaljerad information om vad aktivitetsetiketter gör det till Aktivitetsutforskaren finns i [Märka händelser som är tillgängliga i Aktivitetsutforskaren.](data-classification-activity-explorer-available-events.md)</span><span class="sxs-lookup"><span data-stu-id="cbd8a-138">For more detailed information on what labeling activity makes it to Activity explorer, see [Labeling events available in Activity explorer](data-classification-activity-explorer-available-events.md).</span></span>

<span data-ttu-id="cbd8a-139">**Aktiviteter för känslighetsetiketter** och aktiviteter med bevarandeetiketter från Office inbyggda program, tillägg för Azure Information Protection, SharePoint Online, Exchange Online (endast känslighetsetiketter) och OneDrive. </span><span class="sxs-lookup"><span data-stu-id="cbd8a-139">**Sensitivity label activities** and **Retention labeling activities** from Office native applications, Azure Information Protection add-in, SharePoint Online, Exchange Online (sensitivity labels only) and OneDrive.</span></span> <span data-ttu-id="cbd8a-140">Några exempel är:</span><span class="sxs-lookup"><span data-stu-id="cbd8a-140">Some examples are:</span></span>

- <span data-ttu-id="cbd8a-141">etikett används</span><span class="sxs-lookup"><span data-stu-id="cbd8a-141">label applied</span></span>
- <span data-ttu-id="cbd8a-142">etikett har ändrats (uppgraderats, nedgraderats eller tagits bort)</span><span class="sxs-lookup"><span data-stu-id="cbd8a-142">label changed (upgraded, downgraded, or removed)</span></span>
- <span data-ttu-id="cbd8a-143">automatisk märkning av simulering</span><span class="sxs-lookup"><span data-stu-id="cbd8a-143">auto-labeling simulation</span></span>
- <span data-ttu-id="cbd8a-144">fil som lästs</span><span class="sxs-lookup"><span data-stu-id="cbd8a-144">file read</span></span> 

<span data-ttu-id="cbd8a-145">**AIP-skanner (Azure Information Protection) och AIP-klienter**</span><span class="sxs-lookup"><span data-stu-id="cbd8a-145">**Azure Information Protection (AIP) scanner and AIP clients**</span></span>

- <span data-ttu-id="cbd8a-146">skydd tillämpat</span><span class="sxs-lookup"><span data-stu-id="cbd8a-146">protection applied</span></span>
- <span data-ttu-id="cbd8a-147">skydd har ändrats</span><span class="sxs-lookup"><span data-stu-id="cbd8a-147">protection changed</span></span>
- <span data-ttu-id="cbd8a-148">skydd har tagits bort</span><span class="sxs-lookup"><span data-stu-id="cbd8a-148">protection removed</span></span>
- <span data-ttu-id="cbd8a-149">upptäckta filer</span><span class="sxs-lookup"><span data-stu-id="cbd8a-149">files discovered</span></span> 

<span data-ttu-id="cbd8a-150">Aktivitetsutforskaren  samlar även in DLP-principmatchningar från Exchange Online, SharePoint Online, OneDrive, Teams Chatt och kanal (förhandsversion), lokala SharePoint-mappar och bibliotek och lokala filresurser och Windows 10-enheter via slutpunktens skydd mot **dataförlust (DLP).**</span><span class="sxs-lookup"><span data-stu-id="cbd8a-150">Activity explorer also gathers **DLP policy matches** events from Exchange Online, SharePoint Online, OneDrive, Teams Chat and Channel (preview), on-premises SharePoint folders and libraries, and on-premises file shares, and Windows 10 devices via **Endpoint data loss prevention (DLP)**.</span></span> <span data-ttu-id="cbd8a-151">Några exempelhändelser från Windows 10 enheter är filer:</span><span class="sxs-lookup"><span data-stu-id="cbd8a-151">Some examples events from Windows 10 devices are file:</span></span>

- <span data-ttu-id="cbd8a-152">borttagningar</span><span class="sxs-lookup"><span data-stu-id="cbd8a-152">deletions</span></span>
- <span data-ttu-id="cbd8a-153">skapelser</span><span class="sxs-lookup"><span data-stu-id="cbd8a-153">creations</span></span>
- <span data-ttu-id="cbd8a-154">har kopierats till Urklipp</span><span class="sxs-lookup"><span data-stu-id="cbd8a-154">copied to clipboard</span></span>
- <span data-ttu-id="cbd8a-155">ändrad</span><span class="sxs-lookup"><span data-stu-id="cbd8a-155">modified</span></span>
- <span data-ttu-id="cbd8a-156">läsa</span><span class="sxs-lookup"><span data-stu-id="cbd8a-156">read</span></span>
- <span data-ttu-id="cbd8a-157">utskriven</span><span class="sxs-lookup"><span data-stu-id="cbd8a-157">printed</span></span>
- <span data-ttu-id="cbd8a-158">bytt namn</span><span class="sxs-lookup"><span data-stu-id="cbd8a-158">renamed</span></span>
- <span data-ttu-id="cbd8a-159">kopieras till nätverksresurs</span><span class="sxs-lookup"><span data-stu-id="cbd8a-159">copied to network share</span></span>
- <span data-ttu-id="cbd8a-160">åtkomst av ej tillkomlig app</span><span class="sxs-lookup"><span data-stu-id="cbd8a-160">accessed by unallowed app</span></span> 

<span data-ttu-id="cbd8a-161">Värdet av att förstå vilka åtgärder som vidtas med känsligt etikettinnehåll är att du kan se om de kontroller som du redan har vidtagit, t.ex. skydd mot [dataförlust,](dlp-learn-about-dlp.md) är effektiva eller inte.</span><span class="sxs-lookup"><span data-stu-id="cbd8a-161">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention](dlp-learn-about-dlp.md) are effective or not.</span></span> <span data-ttu-id="cbd8a-162">Om det inte fungerar, eller om du upptäcker något oväntat, t.ex. ett stort antal objekt som är märkta och nedgraderade, kan du hantera dina olika principer och vidta nya åtgärder för att begränsa det oönskade `highly confidential` `general` beteendet.</span><span class="sxs-lookup"><span data-stu-id="cbd8a-162">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="cbd8a-163">Aktivitetsutforskaren övervakar för närvarande inte kvarhållningsaktiviteter för Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="cbd8a-163">Activity explorer doesn't currently monitor retention activities for Exchange Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="cbd8a-164">Se även</span><span class="sxs-lookup"><span data-stu-id="cbd8a-164">See also</span></span>

- [<span data-ttu-id="cbd8a-165">Mer information om känslighetsetiketter</span><span class="sxs-lookup"><span data-stu-id="cbd8a-165">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="cbd8a-166">Mer information om kvarhållningsprinciper och kvarhållningsetiketter</span><span class="sxs-lookup"><span data-stu-id="cbd8a-166">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="cbd8a-167">Mer information om typer av känslig information</span><span class="sxs-lookup"><span data-stu-id="cbd8a-167">Learn about sensitive information types</span></span>](sensitive-information-type-learn-about.md)
- [<span data-ttu-id="cbd8a-168">Mer information om dataklassificering</span><span class="sxs-lookup"><span data-stu-id="cbd8a-168">Learn about data classification</span></span>](data-classification-overview.md)
