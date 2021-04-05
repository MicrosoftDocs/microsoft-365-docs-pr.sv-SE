---
title: Beteendeblockering av klientdator
description: Klientbeteendeblockering är en del av funktioner för blockering och inneslutning i Microsoft Defender för slutpunkt
keywords: blockering av beteende, snabbt skydd, klientbeteende, Microsoft Defender ATP
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
ms.openlocfilehash: 9fcff96b2583c6ef6bec05429ec50a71f3872e43
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587113"
---
# <a name="client-behavioral-blocking"></a><span data-ttu-id="5fdeb-104">Beteendeblockering av klientdator</span><span class="sxs-lookup"><span data-stu-id="5fdeb-104">Client behavioral blocking</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5fdeb-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="5fdeb-105">**Applies to:**</span></span>
- [<span data-ttu-id="5fdeb-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="5fdeb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5fdeb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5fdeb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="5fdeb-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="5fdeb-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5fdeb-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="5fdeb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a><span data-ttu-id="5fdeb-110">Översikt</span><span class="sxs-lookup"><span data-stu-id="5fdeb-110">Overview</span></span>

<span data-ttu-id="5fdeb-111">Klientbeteendeblockering är en komponent i funktioner [för beteendeblockering](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) och inneslutning i Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="5fdeb-111">Client behavioral blocking is a component of [behavioral blocking and containment capabilities](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) in Defender for Endpoint.</span></span> <span data-ttu-id="5fdeb-112">När misstänkta beteenden identifieras på enheter (kallas även klienter eller slutpunkter) blockeras, kontrolleras och åtgärdas artefakter (till exempel filer eller program) automatiskt.</span><span class="sxs-lookup"><span data-stu-id="5fdeb-112">As suspicious behaviors are detected on devices (also referred to as clients or endpoints), artifacts (such as files or applications) are blocked, checked, and remediated automatically.</span></span> 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="Moln- och klientskydd":::

<span data-ttu-id="5fdeb-114">Antivirusskyddet fungerar bäst när det paras ihop med molnskydd.</span><span class="sxs-lookup"><span data-stu-id="5fdeb-114">Antivirus protection works best when paired with cloud protection.</span></span>

## <a name="how-client-behavioral-blocking-works"></a><span data-ttu-id="5fdeb-115">Så här fungerar klientbeteendeblockering</span><span class="sxs-lookup"><span data-stu-id="5fdeb-115">How client behavioral blocking works</span></span>

<span data-ttu-id="5fdeb-116">[Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) kan identifiera misstänkt beteende, skadlig kod, fillösa och minnesattacker och mycket mer på en enhet.</span><span class="sxs-lookup"><span data-stu-id="5fdeb-116">[Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) can detect suspicious behavior, malicious code, fileless and in-memory attacks, and more on a device.</span></span> <span data-ttu-id="5fdeb-117">När misstänkta beteenden upptäcks övervakar Microsoft Defender Antivirus och skickar de misstänkta beteendena och deras processträd till molnskyddstjänsten.</span><span class="sxs-lookup"><span data-stu-id="5fdeb-117">When suspicious behaviors are detected, Microsoft Defender Antivirus monitors and sends those suspicious behaviors and their process trees to the cloud protection service.</span></span> <span data-ttu-id="5fdeb-118">Maskininlärning skiljer mellan skadliga program och bra beteenden inom millisekunder och klassificerar varje artefakt.</span><span class="sxs-lookup"><span data-stu-id="5fdeb-118">Machine learning differentiates between malicious applications and good behaviors within milliseconds, and classifies each artifact.</span></span> <span data-ttu-id="5fdeb-119">I nästan realtid blockeras en artefakt på enheten när den visar sig vara skadlig.</span><span class="sxs-lookup"><span data-stu-id="5fdeb-119">In almost real time, as soon as an artifact is found to be malicious, it's blocked on the device.</span></span> 

<span data-ttu-id="5fdeb-120">När ett misstänkt beteende identifieras genereras [en avisering](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/alerts-queue) och visas i Microsoft Defender Säkerhetscenter ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="5fdeb-120">Whenever a suspicious behavior is detected, an [alert](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/alerts-queue) is generated, and is visible in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

<span data-ttu-id="5fdeb-121">Klientbeteendeblockering är effektivt eftersom det inte bara hjälper till att förhindra att en attack startar, den kan också stoppa en attack som har börjat köras.</span><span class="sxs-lookup"><span data-stu-id="5fdeb-121">Client behavioral blocking is effective because it not only helps prevent an attack from starting, it can help stop an attack that has begun executing.</span></span> <span data-ttu-id="5fdeb-122">Och med [blockering av feedbackslingan](feedback-loop-blocking.md) (en annan funktion för blockering och inneslutning) förhindras attacker på andra enheter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="5fdeb-122">And, with [feedback-loop blocking](feedback-loop-blocking.md) (another capability of behavioral blocking and containment), attacks are prevented on other devices in your organization.</span></span>

## <a name="behavior-based-detections"></a><span data-ttu-id="5fdeb-123">Funktionsbaserade identifieringar</span><span class="sxs-lookup"><span data-stu-id="5fdeb-123">Behavior-based detections</span></span>

<span data-ttu-id="5fdeb-124">Beteendebaserade identifieringar namnges enligt [MITRE ATT-&CK-matrisen för företag.](https://attack.mitre.org/matrices/enterprise)</span><span class="sxs-lookup"><span data-stu-id="5fdeb-124">Behavior-based detections are named according to the [MITRE ATT&CK Matrix for Enterprise](https://attack.mitre.org/matrices/enterprise).</span></span> <span data-ttu-id="5fdeb-125">Namngivningskonventionerna hjälper till att identifiera attackfasen där det skadliga beteendet har observerats:</span><span class="sxs-lookup"><span data-stu-id="5fdeb-125">The naming convention helps identify the attack stage where the malicious behavior was observed:</span></span>


|<span data-ttu-id="5fdeb-126">Taktik</span><span class="sxs-lookup"><span data-stu-id="5fdeb-126">Tactic</span></span> |   <span data-ttu-id="5fdeb-127">Namn på identifiering av hot</span><span class="sxs-lookup"><span data-stu-id="5fdeb-127">Detection threat name</span></span> |
|----|----|
|<span data-ttu-id="5fdeb-128">Inledande åtkomst</span><span class="sxs-lookup"><span data-stu-id="5fdeb-128">Initial Access</span></span> | <span data-ttu-id="5fdeb-129">Beteende:Win32/InitialAccess.\*!ml</span><span class="sxs-lookup"><span data-stu-id="5fdeb-129">Behavior:Win32/InitialAccess.\*!ml</span></span> |
|<span data-ttu-id="5fdeb-130">Körning</span><span class="sxs-lookup"><span data-stu-id="5fdeb-130">Execution</span></span>  | <span data-ttu-id="5fdeb-131">Beteende:Win32/Execution.\*!ml</span><span class="sxs-lookup"><span data-stu-id="5fdeb-131">Behavior:Win32/Execution.\*!ml</span></span> |
|<span data-ttu-id="5fdeb-132">Beständighet</span><span class="sxs-lookup"><span data-stu-id="5fdeb-132">Persistence</span></span>    | <span data-ttu-id="5fdeb-133">Beteende:Win32/Persistence.\*!ml</span><span class="sxs-lookup"><span data-stu-id="5fdeb-133">Behavior:Win32/Persistence.\*!ml</span></span> |
|<span data-ttu-id="5fdeb-134">Eskalering av behörighet</span><span class="sxs-lookup"><span data-stu-id="5fdeb-134">Privilege Escalation</span></span>   | <span data-ttu-id="5fdeb-135">Beteende:Win32/PrivilegeEscalation.\*!ml</span><span class="sxs-lookup"><span data-stu-id="5fdeb-135">Behavior:Win32/PrivilegeEscalation.\*!ml</span></span> |
|<span data-ttu-id="5fdeb-136">Defense Evasion</span><span class="sxs-lookup"><span data-stu-id="5fdeb-136">Defense Evasion</span></span>    | <span data-ttu-id="5fdeb-137">Beteende:Win32/DefenseEvasion.\*!ml</span><span class="sxs-lookup"><span data-stu-id="5fdeb-137">Behavior:Win32/DefenseEvasion.\*!ml</span></span> |
|<span data-ttu-id="5fdeb-138">Åtkomst till autentiseringsuppgifter</span><span class="sxs-lookup"><span data-stu-id="5fdeb-138">Credential Access</span></span>  | <span data-ttu-id="5fdeb-139">Beteende:Win32/CredentialAccess.\*!ml</span><span class="sxs-lookup"><span data-stu-id="5fdeb-139">Behavior:Win32/CredentialAccess.\*!ml</span></span> |
|<span data-ttu-id="5fdeb-140">Upptäckt</span><span class="sxs-lookup"><span data-stu-id="5fdeb-140">Discovery</span></span>  | <span data-ttu-id="5fdeb-141">Beteende:Win32/Discovery.\*!ml</span><span class="sxs-lookup"><span data-stu-id="5fdeb-141">Behavior:Win32/Discovery.\*!ml</span></span> |
|<span data-ttu-id="5fdeb-142">Lateral Movement</span><span class="sxs-lookup"><span data-stu-id="5fdeb-142">Lateral Movement</span></span> | <span data-ttu-id="5fdeb-143">Beteende:Win32/Movement.\*!ml</span><span class="sxs-lookup"><span data-stu-id="5fdeb-143">Behavior:Win32/LateralMovement.\*!ml</span></span> |
|<span data-ttu-id="5fdeb-144">Samling</span><span class="sxs-lookup"><span data-stu-id="5fdeb-144">Collection</span></span> |   <span data-ttu-id="5fdeb-145">Beteende:Win32/Collection.\*!ml</span><span class="sxs-lookup"><span data-stu-id="5fdeb-145">Behavior:Win32/Collection.\*!ml</span></span> |
|<span data-ttu-id="5fdeb-146">Kommando och kontroll</span><span class="sxs-lookup"><span data-stu-id="5fdeb-146">Command and Control</span></span> | <span data-ttu-id="5fdeb-147">Beteende:Win32/CommandAndControl.\*!ml</span><span class="sxs-lookup"><span data-stu-id="5fdeb-147">Behavior:Win32/CommandAndControl.\*!ml</span></span> |
|<span data-ttu-id="5fdeb-148">Exfiltration</span><span class="sxs-lookup"><span data-stu-id="5fdeb-148">Exfiltration</span></span>   | <span data-ttu-id="5fdeb-149">Beteende:Win32/Exfiltration.\*!ml</span><span class="sxs-lookup"><span data-stu-id="5fdeb-149">Behavior:Win32/Exfiltration.\*!ml</span></span> |
|<span data-ttu-id="5fdeb-150">Påverkan</span><span class="sxs-lookup"><span data-stu-id="5fdeb-150">Impact</span></span> | <span data-ttu-id="5fdeb-151">Beteende:Win32/Impact.\*!ml</span><span class="sxs-lookup"><span data-stu-id="5fdeb-151">Behavior:Win32/Impact.\*!ml</span></span> |
|<span data-ttu-id="5fdeb-152">Ej kategoriserat</span><span class="sxs-lookup"><span data-stu-id="5fdeb-152">Uncategorized</span></span>  | <span data-ttu-id="5fdeb-153">Beteende:Win32/Generic.\*!ml</span><span class="sxs-lookup"><span data-stu-id="5fdeb-153">Behavior:Win32/Generic.\*!ml</span></span> |

> [!TIP]
> <span data-ttu-id="5fdeb-154">Mer information om specifika hot finns i den senaste **[globala hotaktiviteten.](https://www.microsoft.com/wdsi/threats)**</span><span class="sxs-lookup"><span data-stu-id="5fdeb-154">To learn more about specific threats, see **[recent global threat activity](https://www.microsoft.com/wdsi/threats)**.</span></span>


## <a name="configuring-client-behavioral-blocking"></a><span data-ttu-id="5fdeb-155">Konfigurera klientbeteendeblockering</span><span class="sxs-lookup"><span data-stu-id="5fdeb-155">Configuring client behavioral blocking</span></span>

<span data-ttu-id="5fdeb-156">Om din organisation använder Defender för Slutpunkt är klientbeteendeblockering aktiverat som standard.</span><span class="sxs-lookup"><span data-stu-id="5fdeb-156">If your organization is using Defender for Endpoint, client behavioral blocking is enabled by default.</span></span> <span data-ttu-id="5fdeb-157">Om du däremot vill dra nytta av [](behavioral-blocking-containment.md)alla Defender för Slutpunkt-funktioner, inklusive blockering och inneslutning, ska du se till att följande funktioner i Defender för slutpunkt är aktiverade och konfigurerade:</span><span class="sxs-lookup"><span data-stu-id="5fdeb-157">However, to benefit from all Defender for Endpoint capabilities, including [behavioral blocking and containment](behavioral-blocking-containment.md), make sure the following features and capabilities of Defender for Endpoint are enabled and configured:</span></span>

- [<span data-ttu-id="5fdeb-158">Defender för slutpunktsbaslinjer</span><span class="sxs-lookup"><span data-stu-id="5fdeb-158">Defender for Endpoint baselines</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [<span data-ttu-id="5fdeb-159">Enheter som finns i Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="5fdeb-159">Devices onboarded to Defender for Endpoint</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-configure)

- [<span data-ttu-id="5fdeb-160">EDR i blockläge</span><span class="sxs-lookup"><span data-stu-id="5fdeb-160">EDR in block mode</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [<span data-ttu-id="5fdeb-161">Minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="5fdeb-161">Attack surface reduction</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- <span data-ttu-id="5fdeb-162">[Nästa generations skydd](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)</span><span class="sxs-lookup"><span data-stu-id="5fdeb-162">[Next-generation protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)</span></span>

## <a name="related-articles"></a><span data-ttu-id="5fdeb-163">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="5fdeb-163">Related articles</span></span>

- [<span data-ttu-id="5fdeb-164">Beteendeblockering och inneslutning</span><span class="sxs-lookup"><span data-stu-id="5fdeb-164">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md)

- [<span data-ttu-id="5fdeb-165">Blockering av feedbackslinga</span><span class="sxs-lookup"><span data-stu-id="5fdeb-165">Feedback-loop blocking</span></span>](feedback-loop-blocking.md)

- [<span data-ttu-id="5fdeb-166">(Blogg) Beteendeblockering och inneslutning: Omvandla fiberoptisk till skydd</span><span class="sxs-lookup"><span data-stu-id="5fdeb-166">(Blog) Behavioral blocking and containment: Transforming optics into protection</span></span>](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [<span data-ttu-id="5fdeb-167">Användbara Defender för Slutpunkt-resurser</span><span class="sxs-lookup"><span data-stu-id="5fdeb-167">Helpful Defender for Endpoint resources</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/helpful-resources)
