---
title: Beteendeblockering av klientdator
description: Klientbeteendeblockering är en del av funktioner för blockering och inneslutning i Microsoft Defender för slutpunkt
keywords: blockering av beteende, snabbt skydd, klientbeteende, Microsoft Defender för Slutpunkt
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 4e416aa9484f251280649035247a59dcc82ce750
ms.sourcegitcommit: bce733c1152dfbca782e716579074261e3c2ef65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/07/2021
ms.locfileid: "52795964"
---
# <a name="client-behavioral-blocking"></a><span data-ttu-id="be04a-104">Beteendeblockering av klientdator</span><span class="sxs-lookup"><span data-stu-id="be04a-104">Client behavioral blocking</span></span>

<span data-ttu-id="be04a-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="be04a-105">**Applies to:**</span></span>
- [<span data-ttu-id="be04a-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="be04a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="be04a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="be04a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="be04a-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="be04a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="be04a-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="be04a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a><span data-ttu-id="be04a-110">Översikt</span><span class="sxs-lookup"><span data-stu-id="be04a-110">Overview</span></span>

<span data-ttu-id="be04a-111">Klientbeteendeblockering är en komponent i funktioner [för beteendeblockering](behavioral-blocking-containment.md) och inneslutning i Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="be04a-111">Client behavioral blocking is a component of [behavioral blocking and containment capabilities](behavioral-blocking-containment.md) in Defender for Endpoint.</span></span> <span data-ttu-id="be04a-112">När misstänkta beteenden identifieras på enheter (kallas även klienter eller slutpunkter) blockeras, kontrolleras och åtgärdas artefakter (till exempel filer eller program) automatiskt.</span><span class="sxs-lookup"><span data-stu-id="be04a-112">As suspicious behaviors are detected on devices (also referred to as clients or endpoints), artifacts (such as files or applications) are blocked, checked, and remediated automatically.</span></span> 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="Moln- och klientskydd":::

<span data-ttu-id="be04a-114">Antivirusskyddet fungerar bäst när det paras ihop med molnskydd.</span><span class="sxs-lookup"><span data-stu-id="be04a-114">Antivirus protection works best when paired with cloud protection.</span></span>

## <a name="how-client-behavioral-blocking-works"></a><span data-ttu-id="be04a-115">Så här fungerar klientbeteendeblockering</span><span class="sxs-lookup"><span data-stu-id="be04a-115">How client behavioral blocking works</span></span>

<span data-ttu-id="be04a-116">[Microsoft Defender Antivirus](microsoft-defender-antivirus-in-windows-10.md) kan identifiera misstänkt beteende, skadlig kod, fillös och minnesintrång och mycket mer på en enhet.</span><span class="sxs-lookup"><span data-stu-id="be04a-116">[Microsoft Defender Antivirus](microsoft-defender-antivirus-in-windows-10.md) can detect suspicious behavior, malicious code, fileless and in-memory attacks, and more on a device.</span></span> <span data-ttu-id="be04a-117">När misstänkta beteenden identifieras Microsoft Defender Antivirus och skickar de misstänkta beteendena och deras processträd till molnskyddstjänsten.</span><span class="sxs-lookup"><span data-stu-id="be04a-117">When suspicious behaviors are detected, Microsoft Defender Antivirus monitors and sends those suspicious behaviors and their process trees to the cloud protection service.</span></span> <span data-ttu-id="be04a-118">Maskininlärning skiljer mellan skadliga program och bra beteenden inom millisekunder och klassificerar varje artefakt.</span><span class="sxs-lookup"><span data-stu-id="be04a-118">Machine learning differentiates between malicious applications and good behaviors within milliseconds, and classifies each artifact.</span></span> <span data-ttu-id="be04a-119">I nästan realtid blockeras en artefakt på enheten när den visar sig vara skadlig.</span><span class="sxs-lookup"><span data-stu-id="be04a-119">In almost real time, as soon as an artifact is found to be malicious, it's blocked on the device.</span></span> 

<span data-ttu-id="be04a-120">När ett misstänkt beteende identifieras genereras [en avisering](alerts-queue.md) och visas i Microsoft Defender Säkerhetscenter ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="be04a-120">Whenever a suspicious behavior is detected, an [alert](alerts-queue.md) is generated, and is visible in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

<span data-ttu-id="be04a-121">Klientbeteendeblockering är effektivt eftersom det inte bara hjälper till att förhindra att en attack startar, den kan också stoppa en attack som har börjat köras.</span><span class="sxs-lookup"><span data-stu-id="be04a-121">Client behavioral blocking is effective because it not only helps prevent an attack from starting, it can help stop an attack that has begun executing.</span></span> <span data-ttu-id="be04a-122">Och med [blockering av feedbackslingan](feedback-loop-blocking.md) (en annan funktion för blockering och inneslutning) förhindras attacker på andra enheter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="be04a-122">And, with [feedback-loop blocking](feedback-loop-blocking.md) (another capability of behavioral blocking and containment), attacks are prevented on other devices in your organization.</span></span>

## <a name="behavior-based-detections"></a><span data-ttu-id="be04a-123">Funktionsbaserade identifieringar</span><span class="sxs-lookup"><span data-stu-id="be04a-123">Behavior-based detections</span></span>

<span data-ttu-id="be04a-124">Beteendebaserade identifieringar namnges enligt [MITRE ATT-&CK-matrisen för företag.](https://attack.mitre.org/matrices/enterprise)</span><span class="sxs-lookup"><span data-stu-id="be04a-124">Behavior-based detections are named according to the [MITRE ATT&CK Matrix for Enterprise](https://attack.mitre.org/matrices/enterprise).</span></span> <span data-ttu-id="be04a-125">Namngivningskonventionerna hjälper till att identifiera attackfasen där det skadliga beteendet har observerats:</span><span class="sxs-lookup"><span data-stu-id="be04a-125">The naming convention helps identify the attack stage where the malicious behavior was observed:</span></span>


|<span data-ttu-id="be04a-126">Taktik</span><span class="sxs-lookup"><span data-stu-id="be04a-126">Tactic</span></span> |   <span data-ttu-id="be04a-127">Namn på identifiering av hot</span><span class="sxs-lookup"><span data-stu-id="be04a-127">Detection threat name</span></span> |
|----|----|
|<span data-ttu-id="be04a-128">Inledande åtkomst</span><span class="sxs-lookup"><span data-stu-id="be04a-128">Initial Access</span></span> | `Behavior:Win32/InitialAccess.*!ml` |
|<span data-ttu-id="be04a-129">Körning</span><span class="sxs-lookup"><span data-stu-id="be04a-129">Execution</span></span>  | `Behavior:Win32/Execution.*!ml` |
|<span data-ttu-id="be04a-130">Beständighet</span><span class="sxs-lookup"><span data-stu-id="be04a-130">Persistence</span></span>    | `Behavior:Win32/Persistence.*!ml` |
|<span data-ttu-id="be04a-131">Eskalering av behörighet</span><span class="sxs-lookup"><span data-stu-id="be04a-131">Privilege Escalation</span></span>   | `Behavior:Win32/PrivilegeEscalation.*!ml` |
|<span data-ttu-id="be04a-132">Defense Evasion</span><span class="sxs-lookup"><span data-stu-id="be04a-132">Defense Evasion</span></span>    | `Behavior:Win32/DefenseEvasion.*!ml` |
|<span data-ttu-id="be04a-133">Åtkomst till autentiseringsuppgifter</span><span class="sxs-lookup"><span data-stu-id="be04a-133">Credential Access</span></span>  | `Behavior:Win32/CredentialAccess.*!ml` |
|<span data-ttu-id="be04a-134">Upptäckt</span><span class="sxs-lookup"><span data-stu-id="be04a-134">Discovery</span></span>  | `Behavior:Win32/Discovery.*!ml` |
|<span data-ttu-id="be04a-135">Lateral Movement</span><span class="sxs-lookup"><span data-stu-id="be04a-135">Lateral Movement</span></span> | `Behavior:Win32/LateralMovement.*!ml` |
|<span data-ttu-id="be04a-136">Samling</span><span class="sxs-lookup"><span data-stu-id="be04a-136">Collection</span></span> |   `Behavior:Win32/Collection.*!ml` |
|<span data-ttu-id="be04a-137">Kommando och kontroll</span><span class="sxs-lookup"><span data-stu-id="be04a-137">Command and Control</span></span> | `Behavior:Win32/CommandAndControl.*!ml` |
|<span data-ttu-id="be04a-138">Exfiltration</span><span class="sxs-lookup"><span data-stu-id="be04a-138">Exfiltration</span></span>   | `Behavior:Win32/Exfiltration.*!ml` |
|<span data-ttu-id="be04a-139">Påverkan</span><span class="sxs-lookup"><span data-stu-id="be04a-139">Impact</span></span> | `Behavior:Win32/Impact.*!ml` |
|<span data-ttu-id="be04a-140">Ej kategoriserat</span><span class="sxs-lookup"><span data-stu-id="be04a-140">Uncategorized</span></span>  | `Behavior:Win32/Generic.*!ml` |

> [!TIP]
> <span data-ttu-id="be04a-141">Mer information om specifika hot finns i den senaste **[globala hotaktiviteten.](https://www.microsoft.com/wdsi/threats)**</span><span class="sxs-lookup"><span data-stu-id="be04a-141">To learn more about specific threats, see **[recent global threat activity](https://www.microsoft.com/wdsi/threats)**.</span></span>


## <a name="configuring-client-behavioral-blocking"></a><span data-ttu-id="be04a-142">Konfigurera klientbeteendeblockering</span><span class="sxs-lookup"><span data-stu-id="be04a-142">Configuring client behavioral blocking</span></span>

<span data-ttu-id="be04a-143">Om din organisation använder Defender för Slutpunkt är klientbeteendeblockering aktiverat som standard.</span><span class="sxs-lookup"><span data-stu-id="be04a-143">If your organization is using Defender for Endpoint, client behavioral blocking is enabled by default.</span></span> <span data-ttu-id="be04a-144">Om du däremot vill dra nytta av [](behavioral-blocking-containment.md)alla Defender för Slutpunkt-funktioner, inklusive blockering och inneslutning, ska du se till att följande funktioner i Defender för slutpunkt är aktiverade och konfigurerade:</span><span class="sxs-lookup"><span data-stu-id="be04a-144">However, to benefit from all Defender for Endpoint capabilities, including [behavioral blocking and containment](behavioral-blocking-containment.md), make sure the following features and capabilities of Defender for Endpoint are enabled and configured:</span></span>

- [<span data-ttu-id="be04a-145">Defender för slutpunktsbaslinjer</span><span class="sxs-lookup"><span data-stu-id="be04a-145">Defender for Endpoint baselines</span></span>](configure-machines-security-baseline.md)

- [<span data-ttu-id="be04a-146">Enheter som finns i Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="be04a-146">Devices onboarded to Defender for Endpoint</span></span>](onboard-configure.md)

- [<span data-ttu-id="be04a-147">EDR i blockläge</span><span class="sxs-lookup"><span data-stu-id="be04a-147">EDR in block mode</span></span>](edr-in-block-mode.md)

- [<span data-ttu-id="be04a-148">Minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="be04a-148">Attack surface reduction</span></span>](attack-surface-reduction.md)

- <span data-ttu-id="be04a-149">[Nästa generations skydd](configure-microsoft-defender-antivirus-features.md) (antivirus, program mot skadlig programvara och andra skyddsfunktioner för hot)</span><span class="sxs-lookup"><span data-stu-id="be04a-149">[Next-generation protection](configure-microsoft-defender-antivirus-features.md) (antivirus, antimalware, and other threat protection capabilities)</span></span>

