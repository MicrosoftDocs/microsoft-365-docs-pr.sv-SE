---
title: Ställ in undantag för Microsoft Defender Antivirus genomsökningar
description: Du kan undanta filer (inklusive filer som ändrats av angivna processer) och mappar från att genomsökas Microsoft Defender Antivirus. Validera dina undantag med PowerShell.
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.technology: mde
ms.audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 7065aa7cd1975b2f5a38e79da8618ba3efdcdac5
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275126"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a><span data-ttu-id="a4b0d-104">Konfigurera och validera undantag för Microsoft Defender Antivirus genomsökningar</span><span class="sxs-lookup"><span data-stu-id="a4b0d-104">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a4b0d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="a4b0d-105">**Applies to:**</span></span>

- [<span data-ttu-id="a4b0d-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="a4b0d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="a4b0d-107">Du kan utesluta vissa filer, mappar, processer och process öppna filer Microsoft Defender Antivirus genomsökningar.</span><span class="sxs-lookup"><span data-stu-id="a4b0d-107">You can exclude certain files, folders, processes, and process-opened files from Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="a4b0d-108">Sådana undantag gäller för [schemalagda genomsökningar](scheduled-catch-up-scans-microsoft-defender-antivirus.md) [,](run-scan-microsoft-defender-antivirus.md)skanningar på begäran och [alltid realtidsskydd och övervakning.](configure-real-time-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="a4b0d-108">Such exclusions apply to [scheduled scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md), [on-demand scans](run-scan-microsoft-defender-antivirus.md), and [always-on real-time protection and monitoring](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="a4b0d-109">Undantag för process öppna filer gäller endast realtidsskydd.</span><span class="sxs-lookup"><span data-stu-id="a4b0d-109">Exclusions for process-opened files only apply to real-time protection.</span></span>

## <a name="configure-and-validate-exclusions"></a><span data-ttu-id="a4b0d-110">Konfigurera och validera undantag</span><span class="sxs-lookup"><span data-stu-id="a4b0d-110">Configure and validate exclusions</span></span>

<span data-ttu-id="a4b0d-111">Information om hur du konfigurerar och validerar undantag finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="a4b0d-111">To configure and validate exclusions, see the following:</span></span>

- <span data-ttu-id="a4b0d-112">[Konfigurera och validera undantag baserat på filnamn, filnamnstillägg och mappplats](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="a4b0d-112">[Configure and validate exclusions based on file name, extension, and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="a4b0d-113">Du kan utesluta filer Microsoft Defender Antivirus genomsökningar baserat på deras filnamnstillägg, filnamn eller plats.</span><span class="sxs-lookup"><span data-stu-id="a4b0d-113">You can exclude files from Microsoft Defender Antivirus scans based on their file extension, file name, or location.</span></span>

- <span data-ttu-id="a4b0d-114">[Konfigurera och validera undantag för filer som öppnas med processer](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="a4b0d-114">[Configure and validate exclusions for files opened by processes](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="a4b0d-115">Du kan utesluta filer från genomsökningar som har öppnats genom en viss process.</span><span class="sxs-lookup"><span data-stu-id="a4b0d-115">You can exclude files from scans that have been opened by a specific process.</span></span>

## <a name="recommendations-for-defining-exclusions"></a><span data-ttu-id="a4b0d-116">Rekommendationer för att definiera undantag</span><span class="sxs-lookup"><span data-stu-id="a4b0d-116">Recommendations for defining exclusions</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4b0d-117">Microsoft Defender Antivirus omfattar många automatiska undantag baserade på kända operativsystemsbeteenden och vanliga hanteringsfiler, till exempel de som används i företagshantering, databashantering och andra företagsscenarier och situationer.</span><span class="sxs-lookup"><span data-stu-id="a4b0d-117">Microsoft Defender Antivirus includes many automatic exclusions based on known operating system behaviors and typical management files, such as those used in enterprise management, database management, and other enterprise scenarios and situations.</span></span>  
> 
> <span data-ttu-id="a4b0d-118">Om du definierar undantag sänks det skydd som Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="a4b0d-118">Defining exclusions lowers the protection offered by Microsoft Defender Antivirus.</span></span> <span data-ttu-id="a4b0d-119">Du bör alltid utvärdera riskerna som är associerade med att implementera undantag och du bör endast utesluta filer som du är säker på inte är skadliga.</span><span class="sxs-lookup"><span data-stu-id="a4b0d-119">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

<span data-ttu-id="a4b0d-120">Tänk på följande när du definierar undantag:</span><span class="sxs-lookup"><span data-stu-id="a4b0d-120">Keep the following points in mind when you are defining exclusions:</span></span>  

- <span data-ttu-id="a4b0d-121">Undantag är tekniskt sett ett skyddsgap.</span><span class="sxs-lookup"><span data-stu-id="a4b0d-121">Exclusions are technically a protection gap.</span></span> <span data-ttu-id="a4b0d-122">Överväg alltid åtgärder när du definierar undantag.</span><span class="sxs-lookup"><span data-stu-id="a4b0d-122">Always consider mitigations when defining exclusions.</span></span> <span data-ttu-id="a4b0d-123">Andra åtgärder kan vara så enkla som att se till att den undantagna platsen har lämpliga åtkomstkontrolllistor, granskningspolicy, bearbetas av en uppdaterad programvara osv.</span><span class="sxs-lookup"><span data-stu-id="a4b0d-123">Other mitigations could be as simple as making sure the excluded location has the appropriate access-control lists (ACLs), audit policy, is processed by an up-to-date software, etc.</span></span>

- <span data-ttu-id="a4b0d-124">Granska undantagen med jämna mellanrum.</span><span class="sxs-lookup"><span data-stu-id="a4b0d-124">Review the exclusions periodically.</span></span> <span data-ttu-id="a4b0d-125">Kontrollera och tillämpa minskningarna på nytt under granskningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="a4b0d-125">Recheck and re-enforce the mitigations as part of the review process.</span></span>

- <span data-ttu-id="a4b0d-126">Undvik helst att definiera undantag som avser att vara proaktiva.</span><span class="sxs-lookup"><span data-stu-id="a4b0d-126">Ideally, avoid defining exclusions intending to be proactive.</span></span> <span data-ttu-id="a4b0d-127">Exkludera till exempel inte något bara för att du tror att det kan vara ett problem i framtiden.</span><span class="sxs-lookup"><span data-stu-id="a4b0d-127">For instance, don't exclude something just because you think it might be a problem in the future.</span></span> <span data-ttu-id="a4b0d-128">Använd undantag endast för specifika problem, till exempel de som rör prestanda eller programkompatibilitet som undantag kan minimera.</span><span class="sxs-lookup"><span data-stu-id="a4b0d-128">Use exclusions only for specific issues, such as those pertaining to performance or application compatibility that exclusions could mitigate.</span></span>

- <span data-ttu-id="a4b0d-129">Granska ändringarna i undantagslistan.</span><span class="sxs-lookup"><span data-stu-id="a4b0d-129">Audit the exclusion list changes.</span></span> <span data-ttu-id="a4b0d-130">Säkerhetsadministratören bör behålla tillräckligt många sammanhang kring varför ett visst undantag har lagts till.</span><span class="sxs-lookup"><span data-stu-id="a4b0d-130">The security admin should preserve enough context around why a certain exclusion was added.</span></span> <span data-ttu-id="a4b0d-131">Du bör kunna ge svar med specifika skäl till varför en viss sökväg uteslöts.</span><span class="sxs-lookup"><span data-stu-id="a4b0d-131">You should be able to provide answer with specific reasoning as to why a certain path was excluded.</span></span>

## <a name="related-articles"></a><span data-ttu-id="a4b0d-132">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="a4b0d-132">Related articles</span></span>

- [<span data-ttu-id="a4b0d-133">Microsoft Defender Antivirus undantag i Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="a4b0d-133">Microsoft Defender Antivirus exclusions on Windows Server 2016</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a4b0d-134">Vanliga misstag att undvika när man definierar undantag</span><span class="sxs-lookup"><span data-stu-id="a4b0d-134">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
