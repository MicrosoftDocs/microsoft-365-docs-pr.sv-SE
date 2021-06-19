---
title: Åtgärda falska positiva eller falska negativa tal i Microsoft 365 Defender
description: Har något missats eller identifierats felaktigt av AIR i Microsoft 365 Defender? Lär dig hur du skickar falska positiva eller falska negativa tal till Microsoft för analys.
keywords: automatiserad, undersökning, avisering, åtgärd, falskt positivt, falskt negativt
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: f60208b06e66c1e9803e05ee1fc41376824e9b56
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022540"
---
# <a name="address-false-positives-or-false-negatives-in-microsoft-365-defender"></a><span data-ttu-id="c95b6-105">Åtgärda falska positiva eller falska negativa tal i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c95b6-105">Address false positives or false negatives in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="c95b6-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="c95b6-106">**Applies to:**</span></span>
- <span data-ttu-id="c95b6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c95b6-107">Microsoft 365 Defender</span></span>

<span data-ttu-id="c95b6-108">Falska positiva eller negativa resultat kan ibland uppstå med någon lösning för skydd mot hot.</span><span class="sxs-lookup"><span data-stu-id="c95b6-108">False positives or negatives can occasionally occur with any threat protection solution.</span></span> <span data-ttu-id="c95b6-109">Om [automatisk undersökning och svarsfunktioner i](m365d-autoir.md) Microsoft 365 Defender har missat eller felaktigt identifierat något finns det åtgärder som ditt säkerhetsteam kan vidta:</span><span class="sxs-lookup"><span data-stu-id="c95b6-109">If [automated investigation and response capabilities](m365d-autoir.md) in Microsoft 365 Defender missed or wrongly detected something, there are steps your security operations team can take:</span></span>

- [<span data-ttu-id="c95b6-110">Rapportera ett falskt positivt/negativt resultat till Microsoft</span><span class="sxs-lookup"><span data-stu-id="c95b6-110">Report a false positive/negative to Microsoft</span></span>](#report-a-false-positivenegative-to-microsoft-for-analysis)
- <span data-ttu-id="c95b6-111">[Justera dina aviseringar](#adjust-an-alert-to-prevent-false-positives-from-recurring) (om det behövs)</span><span class="sxs-lookup"><span data-stu-id="c95b6-111">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed)</span></span>
- [<span data-ttu-id="c95b6-112">Ångra åtgärder som har vidtagits på enheter</span><span class="sxs-lookup"><span data-stu-id="c95b6-112">Undo remediation actions that were taken on devices</span></span>](#undo-a-remediation-action-that-was-taken-on-a-device)

<span data-ttu-id="c95b6-113">I följande avsnitt beskrivs hur du utför de här uppgifterna.</span><span class="sxs-lookup"><span data-stu-id="c95b6-113">The following sections describe how to perform these tasks.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="c95b6-114">Rapportera ett falskt positivt/negativt till Microsoft för analys</span><span class="sxs-lookup"><span data-stu-id="c95b6-114">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="c95b6-115">Objekt som har missats eller identifierats felaktigt</span><span class="sxs-lookup"><span data-stu-id="c95b6-115">Item missed or wrongly detected</span></span> |<span data-ttu-id="c95b6-116">Tjänst</span><span class="sxs-lookup"><span data-stu-id="c95b6-116">Service</span></span>  |<span data-ttu-id="c95b6-117">Lämplig åtgärd</span><span class="sxs-lookup"><span data-stu-id="c95b6-117">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="c95b6-118">- E-postmeddelande</span><span class="sxs-lookup"><span data-stu-id="c95b6-118">- Email message</span></span> <br/><span data-ttu-id="c95b6-119">- E-postbilaga</span><span class="sxs-lookup"><span data-stu-id="c95b6-119">- Email attachment</span></span> <br/><span data-ttu-id="c95b6-120">- URL i ett e-postmeddelande</span><span class="sxs-lookup"><span data-stu-id="c95b6-120">- URL in an email message</span></span><br/><span data-ttu-id="c95b6-121">- URL i Office fil</span><span class="sxs-lookup"><span data-stu-id="c95b6-121">- URL in an Office file</span></span>      |[<span data-ttu-id="c95b6-122">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="c95b6-122">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/defender-for-office-365)        |[<span data-ttu-id="c95b6-123">Skicka misstänkt skräppost, nättr ut, URL:er och filer till Microsoft för genomsökning</span><span class="sxs-lookup"><span data-stu-id="c95b6-123">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](../office-365-security/admin-submission.md)         |
|<span data-ttu-id="c95b6-124">Fil eller app på en enhet</span><span class="sxs-lookup"><span data-stu-id="c95b6-124">File or app on a device</span></span>    |[<span data-ttu-id="c95b6-125">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="c95b6-125">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)         |[<span data-ttu-id="c95b6-126">Skicka en fil till Microsoft för analys av skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="c95b6-126">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="c95b6-127">Justera en avisering för att förhindra att falska positiva resultat upprepas</span><span class="sxs-lookup"><span data-stu-id="c95b6-127">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="c95b6-128">Scenario</span><span class="sxs-lookup"><span data-stu-id="c95b6-128">Scenario</span></span> |<span data-ttu-id="c95b6-129">Tjänst</span><span class="sxs-lookup"><span data-stu-id="c95b6-129">Service</span></span> |<span data-ttu-id="c95b6-130">Lämplig åtgärd</span><span class="sxs-lookup"><span data-stu-id="c95b6-130">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="c95b6-131">- En avisering som utlöses av legitimt bruk</span><span class="sxs-lookup"><span data-stu-id="c95b6-131">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="c95b6-132">- En avisering är felaktig</span><span class="sxs-lookup"><span data-stu-id="c95b6-132">- An alert is inaccurate</span></span>    |[<span data-ttu-id="c95b6-133">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c95b6-133">Microsoft Cloud App Security</span></span>](/cloud-app-security)<br/> <span data-ttu-id="c95b6-134">eller</span><span class="sxs-lookup"><span data-stu-id="c95b6-134">or</span></span> <br/>[<span data-ttu-id="c95b6-135">Skydd mot Azure-hot</span><span class="sxs-lookup"><span data-stu-id="c95b6-135">Azure threat protection</span></span>](/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="c95b6-136">Hantera aviseringar i Cloud App Security portalen</span><span class="sxs-lookup"><span data-stu-id="c95b6-136">Manage alerts in the Cloud App Security portal</span></span>](/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="c95b6-137">En fil, IP-adress, URL eller domän behandlas som skadlig kod på en enhet, trots att den är säker</span><span class="sxs-lookup"><span data-stu-id="c95b6-137">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="c95b6-138">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="c95b6-138">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection) |[<span data-ttu-id="c95b6-139">Skapa en anpassad indikator med åtgärden "Tillåt"</span><span class="sxs-lookup"><span data-stu-id="c95b6-139">Create a custom indicator with an "Allow" action</span></span>](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |

## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="c95b6-140">Ångra en åtgärdsåtgärd som har vidtagits på en enhet</span><span class="sxs-lookup"><span data-stu-id="c95b6-140">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="c95b6-141">Om en åtgärdsåtgärd har vidtagits för en entitet (till exempel en enhet eller ett e-postmeddelande) och den berörda enheten faktiskt inte är ett hot, kan ditt säkerhetsåtgärdsteam ångra åtgärden i [Åtgärdscenter.](m365d-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="c95b6-141">If a remediation action was taken on an entity (such as a device or an email message) and the affected entity is not actually a threat, your security operations team can undo the remediation action in the [Action center](m365d-action-center.md).</span></span>

1. <span data-ttu-id="c95b6-142">Gå till [https://security.microsoft.com](https://security.microsoft.com) och logga in.</span><span class="sxs-lookup"><span data-stu-id="c95b6-142">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 
2. <span data-ttu-id="c95b6-143">Välj Åtgärdscenter i **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="c95b6-143">In the navigation pane, choose **Action center**.</span></span> 
3. <span data-ttu-id="c95b6-144">Välj **en åtgärd** som du vill ångra på fliken Historik.</span><span class="sxs-lookup"><span data-stu-id="c95b6-144">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="c95b6-145">Den utfällna rutan öppnas.</span><span class="sxs-lookup"><span data-stu-id="c95b6-145">Its flyout pane opens.</span></span>
4. <span data-ttu-id="c95b6-146">Välj Ångra i den utfällade **rutan.**</span><span class="sxs-lookup"><span data-stu-id="c95b6-146">In the flyout pane, select **Undo**.</span></span>

> [!TIP]
> <span data-ttu-id="c95b6-147">Se [Ångra slutförda åtgärder.](m365d-autoir-actions.md#undo-completed-actions)</span><span class="sxs-lookup"><span data-stu-id="c95b6-147">See [Undo completed actions](m365d-autoir-actions.md#undo-completed-actions).</span></span>

## <a name="see-also"></a><span data-ttu-id="c95b6-148">Se även</span><span class="sxs-lookup"><span data-stu-id="c95b6-148">See also</span></span>

- [<span data-ttu-id="c95b6-149">Visa information och resultat från en automatiserad undersökning</span><span class="sxs-lookup"><span data-stu-id="c95b6-149">View the details and results of an automated investigation</span></span>](m365d-autoir-results.md)
- [<span data-ttu-id="c95b6-150">Proaktivt leta efter hot med avancerad sökning i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c95b6-150">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>](advanced-hunting-overview.md)
