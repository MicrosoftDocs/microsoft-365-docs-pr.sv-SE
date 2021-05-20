---
title: Använd Microsoft 365 lokal skanner för dataförlustskydd (förhandsversion)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Lär dig hur du använder Microsoft 365 lokal skanner för dataförlustskydd för att skanna igenom vilande data och implementera skyddsåtgärder för lokala filresurser och lokala SharePoint-mappar och dokumentbibliotek.
ms.openlocfilehash: e81b48560a8011e955e6508daf27e96f9fdb70fa
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538093"
---
# <a name="use-the-microsoft-365-data-loss-prevention-on-premises-scanner-preview"></a><span data-ttu-id="f95df-103">Använd Microsoft 365 lokal skanner för dataförlustskydd (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="f95df-103">Use the Microsoft 365 data loss prevention on-premises scanner (preview)</span></span>

<span data-ttu-id="f95df-104">För att bekanta dig med lokala DLP-funktioner, och hur de visar sig i DLP-principer, har vi skapat scenarier som du kan följa.</span><span class="sxs-lookup"><span data-stu-id="f95df-104">To help familiarize you with DLP on-premises features and how they surface in DLP policies, we've put together some scenarios for you to follow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f95df-105">De här lokala DLP-scenarierna är inte officiella procedurer för att skapa och justera DLP-principer.</span><span class="sxs-lookup"><span data-stu-id="f95df-105">These DLP on-premises scenarios are not the official procedures for creating and tuning DLP policies.</span></span> <span data-ttu-id="f95df-106">Läs följande avsnitt om du behöver arbeta med DLP-principer i allmänna situationer:</span><span class="sxs-lookup"><span data-stu-id="f95df-106">Refer to the below topics when you need to work with DLP policies in general situations:</span></span>
>- [<span data-ttu-id="f95df-107">Mer information om dataförlustskydd</span><span class="sxs-lookup"><span data-stu-id="f95df-107">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
>- [<span data-ttu-id="f95df-108">Kom igång med DLP-standardprincipen</span><span class="sxs-lookup"><span data-stu-id="f95df-108">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
>- [<span data-ttu-id="f95df-109">Skapa en DLP-princip från en mall</span><span class="sxs-lookup"><span data-stu-id="f95df-109">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
>- [<span data-ttu-id="f95df-110">Skapa, testa och justera en DLP-princip</span><span class="sxs-lookup"><span data-stu-id="f95df-110">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

### <a name="scenario-discover-files-matching-dlp-rules"></a><span data-ttu-id="f95df-111">Scenario: Upptäck filer som matchar DLP-regler</span><span class="sxs-lookup"><span data-stu-id="f95df-111">Scenario: Discover files matching DLP rules</span></span>

<span data-ttu-id="f95df-112">Data från lokala DLP-skanner visar sig i flera områden</span><span class="sxs-lookup"><span data-stu-id="f95df-112">Data from DLP on-premises scanner surfaces in several areas</span></span>

#### <a name="activity-explorer"></a><span data-ttu-id="f95df-113">Aktivitetsutforskare</span><span class="sxs-lookup"><span data-stu-id="f95df-113">Activity explorer</span></span>

 <span data-ttu-id="f95df-114">Lokal Microsoft DLP identifierar DLP-regelmatchningar och rapporterar dem till [Aktivitetsutforskaren](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer).</span><span class="sxs-lookup"><span data-stu-id="f95df-114">Microsoft DLP for on-premises detects DLP rule matches and reports them to [Activity Explorer](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer).</span></span> 
 
#### <a name="microsoft-365-audit-log"></a><span data-ttu-id="f95df-115">Microsoft 365-granskningslogg</span><span class="sxs-lookup"><span data-stu-id="f95df-115">Microsoft 365 Audit log</span></span>

<span data-ttu-id="f95df-116">Under den offentliga förhandsversionen är DLP-regelmatchningar tillgängliga i användargränssnittet för granskningsloggen. Läs mer i [Söka i granskningsloggen i efterlevnadscentret](search-the-audit-log-in-security-and-compliance.md)  eller komma åt den med[Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f95df-116">During the public preview the DLP rule matches are available in Audit log UI, see [Search the audit log in the compliance center](search-the-audit-log-in-security-and-compliance.md)  or accessible by [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) PowerShell.</span></span>

#### <a name="aip"></a><span data-ttu-id="f95df-117">AIP</span><span class="sxs-lookup"><span data-stu-id="f95df-117">AIP</span></span>

<span data-ttu-id="f95df-118">Identifieringsdata är tillgänglig i en lokal rapport i CSV-format som lagras i:</span><span class="sxs-lookup"><span data-stu-id="f95df-118">Discovery data is available in a local report in csv format which is stored under:</span></span>

<span data-ttu-id="f95df-119">**%localappdata%\Microsoft\MSIP\Scanner\Reports\DetailedReport_%timestamp%.csv report**.</span><span class="sxs-lookup"><span data-stu-id="f95df-119">**%localappdata%\Microsoft\MSIP\Scanner\Reports\DetailedReport_%timestamp%.csv report**.</span></span>

 <span data-ttu-id="f95df-120">Leta efter följande kolumner:</span><span class="sxs-lookup"><span data-stu-id="f95df-120">Look for the following columns:</span></span>
- <span data-ttu-id="f95df-121">DLP-läge</span><span class="sxs-lookup"><span data-stu-id="f95df-121">DLP Mode</span></span>
- <span data-ttu-id="f95df-122">DLP-status</span><span class="sxs-lookup"><span data-stu-id="f95df-122">DLP Status</span></span>
- <span data-ttu-id="f95df-123">DLP-kommentar</span><span class="sxs-lookup"><span data-stu-id="f95df-123">DLP Comment</span></span>
- <span data-ttu-id="f95df-124">DLP-regelnamn DLP-åtgärder</span><span class="sxs-lookup"><span data-stu-id="f95df-124">DLP Rule Name DLP Actions</span></span>
- <span data-ttu-id="f95df-125">Ägare</span><span class="sxs-lookup"><span data-stu-id="f95df-125">Owner</span></span>
- <span data-ttu-id="f95df-126">Aktuella NTFS-behörigheter (SDDL)</span><span class="sxs-lookup"><span data-stu-id="f95df-126">Current NTFS Permissions (SDDL)</span></span>
- <span data-ttu-id="f95df-127">Tillämpade NTFS-behörigheter (SDDL)</span><span class="sxs-lookup"><span data-stu-id="f95df-127">Applied NTFS Permissions (SDDL)</span></span>
- <span data-ttu-id="f95df-128">NTFS-behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="f95df-128">NTFS permissions type</span></span>
 
### <a name="scenario-enforce-dlp-rule"></a><span data-ttu-id="f95df-129">Scenario: Tillämpad DLP-regel</span><span class="sxs-lookup"><span data-stu-id="f95df-129">Scenario: Enforce DLP rule</span></span> 

<span data-ttu-id="f95df-130">Om du vill tillämpa DLP-regler för de skannade filerna måste tillämpning vara aktiverat för både innehållssökningsjobbet i AIP och på principnivån i DLP.</span><span class="sxs-lookup"><span data-stu-id="f95df-130">If you want to enforce DLP rules on the scanned files, enforcement must be enabled on both the content scan job in AIP and at the policy level in DLP.</span></span>


#### <a name="configure-dlp-to-enforce-policy-actions"></a><span data-ttu-id="f95df-131">Konfigurera DLP för att tillämpa principåtgärder</span><span class="sxs-lookup"><span data-stu-id="f95df-131">Configure DLP to enforce policy actions</span></span>

1. <span data-ttu-id="f95df-132">Öppna [sidan Dataförlustskydd](https://compliance.microsoft.com/datalossprevention?viewid=policies) och välj den DLP-princip som är avsedd för de lokala platsdatabaser som du har konfigurerat i AIP.</span><span class="sxs-lookup"><span data-stu-id="f95df-132">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies) and select the DLP policy that is targeted to the on-premises location repositories you have configured in AIP.</span></span> 
2. <span data-ttu-id="f95df-133">Redigera principen.</span><span class="sxs-lookup"><span data-stu-id="f95df-133">Edit the policy.</span></span>
3. <span data-ttu-id="f95df-134">På sidan **Testa eller aktivera principen** väljer du **Ja, aktivera det direkt**.</span><span class="sxs-lookup"><span data-stu-id="f95df-134">On the **Test or turn on the policy** page, select **Yes, turn it on right away**.</span></span> 

## <a name="see-also"></a><span data-ttu-id="f95df-135">Se även</span><span class="sxs-lookup"><span data-stu-id="f95df-135">See also</span></span>

- [<span data-ttu-id="f95df-136">Läs mer om DLP-lokal skanner (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="f95df-136">Learn about DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-learn.md)
- [<span data-ttu-id="f95df-137">Komma igång med DLP-lokal skanner (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="f95df-137">Get started with  DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-get-started.md)
- [<span data-ttu-id="f95df-138">Mer information om dataförlustskydd</span><span class="sxs-lookup"><span data-stu-id="f95df-138">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="f95df-139">Skapa, testa och justera en DLP-princip</span><span class="sxs-lookup"><span data-stu-id="f95df-139">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="f95df-140">Kom igång med Aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="f95df-140">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)