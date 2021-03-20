---
title: Hantera falska positiva resultat eller falska negativa resultat i AIR i Microsoft 365 Defender
description: Har något missats eller identifierats felaktigt av AIR i Microsoft 365 Defender? Lär dig hur du skickar falska positiva eller falska negativa tal till Microsoft för analys.
keywords: automatiserad, undersökning, avisering, åtgärd, falskt positivt, falskt negativt
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 01/29/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: ccfb2c8d9395d3f64b20980b156ed51545967101
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917076"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="7ab10-105">Hantera falska positiva/negativa i automatiska undersöknings- och svarsfunktioner</span><span class="sxs-lookup"><span data-stu-id="7ab10-105">Handle false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="7ab10-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="7ab10-106">**Applies to:**</span></span>
- <span data-ttu-id="7ab10-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7ab10-107">Microsoft 365 Defender</span></span>

<span data-ttu-id="7ab10-108">Falska positiva/negativa kan ibland uppstå med någon lösning för skydd mot hot.</span><span class="sxs-lookup"><span data-stu-id="7ab10-108">False positives/negatives can occasionally occur with any threat protection solution.</span></span> <span data-ttu-id="7ab10-109">Om [automatisk undersökning och svarsfunktioner](mtp-autoir.md) i Microsoft 365 Defender missade eller felaktigt identifierade något finns det åtgärder som ditt säkerhetsteam kan vidta:</span><span class="sxs-lookup"><span data-stu-id="7ab10-109">If [automated investigation and response capabilities](mtp-autoir.md) in Microsoft 365 Defender missed or wrongly detected something, there are steps your security operations team can take:</span></span>

- <span data-ttu-id="7ab10-110">[Rapportera falskt positivt/negativt till Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="7ab10-110">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="7ab10-111">[Justera dina aviseringar](#adjust-an-alert-to-prevent-false-positives-from-recurring) (om det behövs). och</span><span class="sxs-lookup"><span data-stu-id="7ab10-111">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 
- <span data-ttu-id="7ab10-112">[Ångra åtgärder som har vidtagits på enheter](#undo-a-remediation-action-that-was-taken-on-a-device).</span><span class="sxs-lookup"><span data-stu-id="7ab10-112">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="7ab10-113">I följande avsnitt beskrivs hur du utför de här uppgifterna.</span><span class="sxs-lookup"><span data-stu-id="7ab10-113">The following sections describe how to perform these tasks.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="7ab10-114">Rapportera ett falskt positivt/negativt till Microsoft för analys</span><span class="sxs-lookup"><span data-stu-id="7ab10-114">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="7ab10-115">Objekt som har missats eller identifierats felaktigt</span><span class="sxs-lookup"><span data-stu-id="7ab10-115">Item missed or wrongly detected</span></span> |<span data-ttu-id="7ab10-116">Tjänst</span><span class="sxs-lookup"><span data-stu-id="7ab10-116">Service</span></span>  |<span data-ttu-id="7ab10-117">Vad kan jag göra?</span><span class="sxs-lookup"><span data-stu-id="7ab10-117">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="7ab10-118">- E-postmeddelande</span><span class="sxs-lookup"><span data-stu-id="7ab10-118">- Email message</span></span> <br/><span data-ttu-id="7ab10-119">- E-postbilaga</span><span class="sxs-lookup"><span data-stu-id="7ab10-119">- Email attachment</span></span> <br/><span data-ttu-id="7ab10-120">- URL i ett e-postmeddelande</span><span class="sxs-lookup"><span data-stu-id="7ab10-120">- URL in an email message</span></span><br/><span data-ttu-id="7ab10-121">- URL i en Office-fil</span><span class="sxs-lookup"><span data-stu-id="7ab10-121">- URL in an Office file</span></span>      |[<span data-ttu-id="7ab10-122">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="7ab10-122">Microsoft Defender for Office 365</span></span>](../office-365-security/office-365-atp.md)        |[<span data-ttu-id="7ab10-123">Skicka misstänkt skräppost, nättr ut, URL:er och filer till Microsoft för genomsökning</span><span class="sxs-lookup"><span data-stu-id="7ab10-123">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](../office-365-security/admin-submission.md)         |
|<span data-ttu-id="7ab10-124">Fil eller app på en enhet</span><span class="sxs-lookup"><span data-stu-id="7ab10-124">File or app on a device</span></span>    |[<span data-ttu-id="7ab10-125">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="7ab10-125">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)         |[<span data-ttu-id="7ab10-126">Skicka en fil till Microsoft för analys av skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="7ab10-126">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="7ab10-127">Justera en avisering för att förhindra att falska positiva resultat upprepas</span><span class="sxs-lookup"><span data-stu-id="7ab10-127">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="7ab10-128">Scenario</span><span class="sxs-lookup"><span data-stu-id="7ab10-128">Scenario</span></span> |<span data-ttu-id="7ab10-129">Tjänst</span><span class="sxs-lookup"><span data-stu-id="7ab10-129">Service</span></span> |<span data-ttu-id="7ab10-130">Vad kan jag göra?</span><span class="sxs-lookup"><span data-stu-id="7ab10-130">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="7ab10-131">- En avisering som utlöses av legitimt bruk</span><span class="sxs-lookup"><span data-stu-id="7ab10-131">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="7ab10-132">- En avisering är felaktig</span><span class="sxs-lookup"><span data-stu-id="7ab10-132">- An alert is inaccurate</span></span>    |[<span data-ttu-id="7ab10-133">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="7ab10-133">Microsoft Cloud App Security</span></span>](/cloud-app-security)<br/> <span data-ttu-id="7ab10-134">eller</span><span class="sxs-lookup"><span data-stu-id="7ab10-134">or</span></span> <br/>[<span data-ttu-id="7ab10-135">Avancerad identifiering av hot i Azure</span><span class="sxs-lookup"><span data-stu-id="7ab10-135">Azure Advanced Threat Detection</span></span>](/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="7ab10-136">Hantera aviseringar i Cloud App Security-portalen</span><span class="sxs-lookup"><span data-stu-id="7ab10-136">Manage alerts in the Cloud App Security portal</span></span>](/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="7ab10-137">En fil, IP-adress, URL eller domän behandlas som skadlig kod på en enhet, trots att den är säker</span><span class="sxs-lookup"><span data-stu-id="7ab10-137">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="7ab10-138">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="7ab10-138">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection) |[<span data-ttu-id="7ab10-139">Skapa en anpassad indikator med åtgärden "Tillåt"</span><span class="sxs-lookup"><span data-stu-id="7ab10-139">Create a custom indicator with an "Allow" action</span></span>](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |

## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="7ab10-140">Ångra en åtgärdsåtgärd som har vidtagits på en enhet</span><span class="sxs-lookup"><span data-stu-id="7ab10-140">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="7ab10-141">Om en åtgärdsåtgärd har vidtagits för en entitet (till exempel en enhet eller ett e-postmeddelande) och den berörda enheten faktiskt inte är ett hot, kan ditt säkerhetsåtgärdsteam ångra åtgärden i [Åtgärdscenter.](mtp-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="7ab10-141">If a remediation action was taken on an entity (such as a device or an email message) and the affected entity is not actually a threat, your security operations team can undo the remediation action in the [Action center](mtp-action-center.md).</span></span>

1. <span data-ttu-id="7ab10-142">Gå till [https://security.microsoft.com](https://security.microsoft.com) och logga in.</span><span class="sxs-lookup"><span data-stu-id="7ab10-142">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 
2. <span data-ttu-id="7ab10-143">Välj Åtgärdscenter i **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="7ab10-143">In the navigation pane, choose **Action center**.</span></span> 
3. <span data-ttu-id="7ab10-144">Välj **en åtgärd** som du vill ångra på fliken Historik.</span><span class="sxs-lookup"><span data-stu-id="7ab10-144">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="7ab10-145">Den utfällna rutan öppnas.</span><span class="sxs-lookup"><span data-stu-id="7ab10-145">Its flyout pane opens.</span></span>
4. <span data-ttu-id="7ab10-146">Välj Ångra i den utfällade **rutan.**</span><span class="sxs-lookup"><span data-stu-id="7ab10-146">In the flyout pane, select **Undo**.</span></span>

> [!TIP]
> <span data-ttu-id="7ab10-147">Se [Ångra slutförda åtgärder.](mtp-autoir-actions.md#undo-completed-actions)</span><span class="sxs-lookup"><span data-stu-id="7ab10-147">See [Undo completed actions](mtp-autoir-actions.md#undo-completed-actions).</span></span>

## <a name="see-also"></a><span data-ttu-id="7ab10-148">Se även</span><span class="sxs-lookup"><span data-stu-id="7ab10-148">See also</span></span>

- [<span data-ttu-id="7ab10-149">Visa information och resultat från en automatiserad undersökning</span><span class="sxs-lookup"><span data-stu-id="7ab10-149">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="7ab10-150">Proaktiv sökning efter hot med avancerad sökning i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7ab10-150">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7ab10-151">Adressera falska positiva/negativa tal i Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="7ab10-151">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/defender-endpoint-false-positives-negatives)