---
title: Konfigurera undantag för genomsökningar för Microsoft Defender Antivirus
description: Du kan undanta filer (inklusive filer som ändrats av angivna processer) och mappar från att genomsökas av Microsoft Defender AV. Validera dina undantag med PowerShell.
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.technology: mde
ms.audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 08f7f9d4a6e9e70d3ef071f30712b2ae53f4ea52
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764669"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a><span data-ttu-id="b8869-104">Konfigurera och validera undantag för genomsökningar för Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="b8869-104">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b8869-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="b8869-105">**Applies to:**</span></span>

- [<span data-ttu-id="b8869-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="b8869-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="b8869-107">Du kan utesluta vissa filer, mappar, processer och process öppna filer från genomsökningar för Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="b8869-107">You can exclude certain files, folders, processes, and process-opened files from Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="b8869-108">Sådana undantag gäller för [schemalagda genomsökningar](scheduled-catch-up-scans-microsoft-defender-antivirus.md) [,](run-scan-microsoft-defender-antivirus.md)skanningar på begäran och [alltid realtidsskydd och övervakning.](configure-real-time-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="b8869-108">Such exclusions apply to [scheduled scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md), [on-demand scans](run-scan-microsoft-defender-antivirus.md), and [always-on real-time protection and monitoring](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="b8869-109">Undantag för process öppna filer gäller endast realtidsskydd.</span><span class="sxs-lookup"><span data-stu-id="b8869-109">Exclusions for process-opened files only apply to real-time protection.</span></span>

## <a name="configure-and-validate-exclusions"></a><span data-ttu-id="b8869-110">Konfigurera och validera undantag</span><span class="sxs-lookup"><span data-stu-id="b8869-110">Configure and validate exclusions</span></span>

<span data-ttu-id="b8869-111">Information om hur du konfigurerar och validerar undantag finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="b8869-111">To configure and validate exclusions, see the following:</span></span>

- <span data-ttu-id="b8869-112">[Konfigurera och validera undantag baserat på filnamn, filnamnstillägg och mappplats](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="b8869-112">[Configure and validate exclusions based on file name, extension, and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="b8869-113">Det här gör att du kan utesluta filer från genomsökningar från Microsoft Defender Antivirus baserat på deras filtillägg, filnamn eller plats.</span><span class="sxs-lookup"><span data-stu-id="b8869-113">This enables you to exclude files from Microsoft Defender Antivirus scans based on their file extension, file name, or location.</span></span>

- <span data-ttu-id="b8869-114">[Konfigurera och validera undantag för filer som öppnas med processer](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="b8869-114">[Configure and validate exclusions for files opened by processes](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="b8869-115">Det här gör att du kan utesluta filer från genomsökningar som har öppnats av en viss process.</span><span class="sxs-lookup"><span data-stu-id="b8869-115">This enables you to exclude files from scans that have been opened by a specific process.</span></span>

## <a name="recommendations-for-defining-exclusions"></a><span data-ttu-id="b8869-116">Rekommendationer för att definiera undantag</span><span class="sxs-lookup"><span data-stu-id="b8869-116">Recommendations for defining exclusions</span></span>
[!IMPORTANT]
<span data-ttu-id="b8869-117">Microsoft Defender Antivirus innehåller många automatiska undantag baserade på kända operativsystemsbeteenden och vanliga hanteringsfiler, till exempel de som används i företagshantering, databashantering och andra företagsscenarier och situationer.</span><span class="sxs-lookup"><span data-stu-id="b8869-117">Microsoft Defender Antivirus includes many automatic exclusions based on known operating system behaviors and typical management files, such as those used in enterprise management, database management, and other enterprise scenarios and situations.</span></span>  
<span data-ttu-id="b8869-118">Om du definierar undantag sänks skyddet som erbjuds av Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="b8869-118">Defining exclusions lowers the protection offered by Microsoft Defender Antivirus.</span></span> <span data-ttu-id="b8869-119">Du bör alltid utvärdera riskerna som är associerade med att implementera undantag och du bör endast utesluta filer som du är säker på inte är skadliga.</span><span class="sxs-lookup"><span data-stu-id="b8869-119">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

<span data-ttu-id="b8869-120">Följande är en lista med rekommendationer som du bör tänka på när du definierar undantag:</span><span class="sxs-lookup"><span data-stu-id="b8869-120">The following is a list of recommendations that you should keep in mind when defining exclusions:</span></span>  

- <span data-ttu-id="b8869-121">Undantag är tekniskt ett skyddsgap – överväg alltid ytterligare åtgärder när du definierar undantag.</span><span class="sxs-lookup"><span data-stu-id="b8869-121">Exclusions are technically a protection gap—always consider additional mitigations when defining exclusions.</span></span> <span data-ttu-id="b8869-122">Åtgärder kan vara så enkla som att se till att den undantagna platsen har lämpliga åtkomstkontrolllistor, granskningspolicy, bearbetas av en uppdaterad programvara osv.</span><span class="sxs-lookup"><span data-stu-id="b8869-122">Additional mitigations could be as simple as making sure the excluded location has the appropriate access-control lists (ACLs), audit policy, is processed by an up-to-date software, etc.</span></span>

- <span data-ttu-id="b8869-123">Granska undantagen med jämna mellanrum.</span><span class="sxs-lookup"><span data-stu-id="b8869-123">Review the exclusions periodically.</span></span> <span data-ttu-id="b8869-124">Kontrollera om och tillämpa minskningarna som en del av granskningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="b8869-124">Re-check and re-enforce the mitigations as part of the review process.</span></span>

- <span data-ttu-id="b8869-125">Helst bör du undvika att definiera proaktiva undantag.</span><span class="sxs-lookup"><span data-stu-id="b8869-125">Ideally, avoid defining proactive exclusions.</span></span> <span data-ttu-id="b8869-126">Exkludera till exempel inte något bara för att du tror att det kan vara ett problem i framtiden.</span><span class="sxs-lookup"><span data-stu-id="b8869-126">For instance, don't exclude something just because you think it might be a problem in the future.</span></span> <span data-ttu-id="b8869-127">Använd undantag endast för specifika problem – oftast kring prestanda eller ibland kring programkompatibilitet som undantag kan minimera.</span><span class="sxs-lookup"><span data-stu-id="b8869-127">Use exclusions only for specific issues—mostly around performance, or sometimes around application compatibility that exclusions could mitigate.</span></span>

- <span data-ttu-id="b8869-128">Granska ändringarna i undantagslistan.</span><span class="sxs-lookup"><span data-stu-id="b8869-128">Audit the exclusion list changes.</span></span> <span data-ttu-id="b8869-129">Säkerhetsadministratören bör behålla tillräckligt många sammanhang kring varför ett visst undantag har lagts till.</span><span class="sxs-lookup"><span data-stu-id="b8869-129">The security admin should preserve enough context around why a certain exclusion was added.</span></span> <span data-ttu-id="b8869-130">Du bör kunna ge svar med specifika skäl till varför en viss sökväg uteslöts.</span><span class="sxs-lookup"><span data-stu-id="b8869-130">You should be able to provide answer with specific reasoning as to why a certain path was excluded.</span></span>

## <a name="related-articles"></a><span data-ttu-id="b8869-131">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="b8869-131">Related articles</span></span>

- [<span data-ttu-id="b8869-132">Undantag för Microsoft Defender Antivirus i Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="b8869-132">Microsoft Defender Antivirus exclusions on Windows Server 2016</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b8869-133">Vanliga misstag att undvika när du definierar undantag</span><span class="sxs-lookup"><span data-stu-id="b8869-133">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
