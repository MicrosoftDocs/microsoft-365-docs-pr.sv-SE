---
title: Hantera falska positiva eller falska negativa tal i AIR i Microsoft 365 Defender
description: Har något missats eller identifierats felaktigt av AIR i Microsoft 365 Defender? Lär dig hur du skickar falska positiva eller falska negativa tal till Microsoft för analys.
keywords: automatiserad, undersökning, avisering, utlösare, åtgärd, falsk positiv eller falsk negativ
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 09/16/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: dbef240e28258d1ac4000c05538d0ce073a9d910
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930360"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="5f490-105">Hantera falska positiva/negativa tal i automatisk undersökning och svarsfunktioner</span><span class="sxs-lookup"><span data-stu-id="5f490-105">Handle false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5f490-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="5f490-106">**Applies to:**</span></span>
- <span data-ttu-id="5f490-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5f490-107">Microsoft 365 Defender</span></span>

<span data-ttu-id="5f490-108">Har [automatisk undersökning och svar i](mtp-autoir.md) Microsoft 365 Defender missat eller felaktigt upptäckt något?</span><span class="sxs-lookup"><span data-stu-id="5f490-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft 365 Defender miss or wrongly detect something?</span></span> <span data-ttu-id="5f490-109">Det finns åtgärder du kan vidta för att åtgärda det.</span><span class="sxs-lookup"><span data-stu-id="5f490-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="5f490-110">Du kan:</span><span class="sxs-lookup"><span data-stu-id="5f490-110">You can:</span></span>

- <span data-ttu-id="5f490-111">[Rapportera ett falskt positivt/negativt värde till Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="5f490-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>

- <span data-ttu-id="5f490-112">[Justera dina aviseringar](#adjust-an-alert-to-prevent-false-positives-from-recurring) (om det behövs). och</span><span class="sxs-lookup"><span data-stu-id="5f490-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 

- <span data-ttu-id="5f490-113">[Ångra åtgärder som har vidtagits på enheter.](#undo-a-remediation-action-that-was-taken-on-a-device)</span><span class="sxs-lookup"><span data-stu-id="5f490-113">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="5f490-114">Använd den här artikeln som en guide.</span><span class="sxs-lookup"><span data-stu-id="5f490-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="5f490-115">Rapportera ett falskt positivt/negativt till Microsoft för analys</span><span class="sxs-lookup"><span data-stu-id="5f490-115">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="5f490-116">Objekt som har missats eller identifierats fel</span><span class="sxs-lookup"><span data-stu-id="5f490-116">Item missed or wrongly detected</span></span> |<span data-ttu-id="5f490-117">Tjänst</span><span class="sxs-lookup"><span data-stu-id="5f490-117">Service</span></span>  |<span data-ttu-id="5f490-118">Vad kan jag göra?</span><span class="sxs-lookup"><span data-stu-id="5f490-118">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="5f490-119">- E-postmeddelande</span><span class="sxs-lookup"><span data-stu-id="5f490-119">- Email message</span></span> <br/><span data-ttu-id="5f490-120">- E-postbilaga</span><span class="sxs-lookup"><span data-stu-id="5f490-120">- Email attachment</span></span> <br/><span data-ttu-id="5f490-121">- URL i ett e-postmeddelande</span><span class="sxs-lookup"><span data-stu-id="5f490-121">- URL in an email message</span></span><br/><span data-ttu-id="5f490-122">- URL i en Office-fil</span><span class="sxs-lookup"><span data-stu-id="5f490-122">- URL in an Office file</span></span>      |[<span data-ttu-id="5f490-123">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="5f490-123">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="5f490-124">Skicka misstänkt skräppost, phish, URL:er och filer till Microsoft för genomsökning</span><span class="sxs-lookup"><span data-stu-id="5f490-124">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="5f490-125">Fil eller app på en enhet</span><span class="sxs-lookup"><span data-stu-id="5f490-125">File or app on a device</span></span>    |[<span data-ttu-id="5f490-126">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="5f490-126">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="5f490-127">Skicka en fil till Microsoft för analys av skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="5f490-127">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="5f490-128">Justera en avisering för att förhindra att falska positiva resultat upprepas</span><span class="sxs-lookup"><span data-stu-id="5f490-128">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="5f490-129">Scenario</span><span class="sxs-lookup"><span data-stu-id="5f490-129">Scenario</span></span> |<span data-ttu-id="5f490-130">Tjänst</span><span class="sxs-lookup"><span data-stu-id="5f490-130">Service</span></span> |<span data-ttu-id="5f490-131">Vad kan jag göra?</span><span class="sxs-lookup"><span data-stu-id="5f490-131">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="5f490-132">- En avisering utlöses av legitimt bruk</span><span class="sxs-lookup"><span data-stu-id="5f490-132">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="5f490-133">- En avisering är felaktig</span><span class="sxs-lookup"><span data-stu-id="5f490-133">- An alert is inaccurate</span></span>    |[<span data-ttu-id="5f490-134">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="5f490-134">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="5f490-135">eller</span><span class="sxs-lookup"><span data-stu-id="5f490-135">or</span></span> <br/>[<span data-ttu-id="5f490-136">Avancerad identifiering av Azure-hot</span><span class="sxs-lookup"><span data-stu-id="5f490-136">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="5f490-137">Hantera aviseringar i Cloud App Security-portalen</span><span class="sxs-lookup"><span data-stu-id="5f490-137">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="5f490-138">En fil, IP-adress, URL eller domän behandlas som skadlig programvara på en enhet, trots att den är säker</span><span class="sxs-lookup"><span data-stu-id="5f490-138">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="5f490-139">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="5f490-139">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection) |[<span data-ttu-id="5f490-140">Skapa en anpassad indikator med åtgärden "Tillåt"</span><span class="sxs-lookup"><span data-stu-id="5f490-140">Create a custom indicator with an "Allow" action</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="5f490-141">Ångra en åtgärdsåtgärd som har vidtagits på en enhet</span><span class="sxs-lookup"><span data-stu-id="5f490-141">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="5f490-142">Om en åtgärdsåtgärd har vidtagits på en enhet (till exempel en Windows 10-enhet) och objektet egentligen inte är ett hot kan säkerhetsåtgärdsteamet ångra åtgärden i [Åtgärdscenter.](mtp-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="5f490-142">If a remediation action was taken on a device (such as a Windows 10 device) and the item is actually not a threat, your security operations team can undo the remediation action in the [Action center](mtp-action-center.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5f490-143">Kontrollera att du har [de behörigheter som](mtp-action-center.md#required-permissions-for-action-center-tasks) behövs innan du försöker utföra följande uppgift.</span><span class="sxs-lookup"><span data-stu-id="5f490-143">Make sure you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) before attempting to perform the following task.</span></span>

1. <span data-ttu-id="5f490-144">Gå till [https://security.microsoft.com](https://security.microsoft.com) och logga in.</span><span class="sxs-lookup"><span data-stu-id="5f490-144">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="5f490-145">Välj Åtgärdscenter i **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="5f490-145">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="5f490-146">Välj en **åtgärd** som du vill ångra på fliken Historik.</span><span class="sxs-lookup"><span data-stu-id="5f490-146">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="5f490-147">Då öppnas en utfällblad.</span><span class="sxs-lookup"><span data-stu-id="5f490-147">This opens a flyout.</span></span><br/>
    > [!TIP]
    > <span data-ttu-id="5f490-148">Använd filter för att begränsa resultatlistan.</span><span class="sxs-lookup"><span data-stu-id="5f490-148">Use filters to narrow down the list of results.</span></span> 

4. <span data-ttu-id="5f490-149">Välj sidan Öppna undersökning i den utfäll plats som är markerad för **det markerade objektet.**</span><span class="sxs-lookup"><span data-stu-id="5f490-149">In the flyout for the selected item, select **Open investigation page**.</span></span>

5. <span data-ttu-id="5f490-150">Välj fliken Åtgärder i vyn **undersökningsinformation.**</span><span class="sxs-lookup"><span data-stu-id="5f490-150">In the investigation details view, select the **Actions** tab.</span></span>

6. <span data-ttu-id="5f490-151">Markera ett objekt som har **statusen Slutförd** och leta efter en länk, till exempel **Godkänd,** i **kolumnen** Beslut.</span><span class="sxs-lookup"><span data-stu-id="5f490-151">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decisions** column.</span></span> <span data-ttu-id="5f490-152">Då öppnas en utfällblad med mer information om åtgärden.</span><span class="sxs-lookup"><span data-stu-id="5f490-152">This opens a flyout with more details about the action.</span></span>

7. <span data-ttu-id="5f490-153">Om du vill ångra åtgärden väljer **du Ta bort åtgärd.**</span><span class="sxs-lookup"><span data-stu-id="5f490-153">To undo the action, select **Delete remediation**.</span></span>

## <a name="see-also"></a><span data-ttu-id="5f490-154">Se även</span><span class="sxs-lookup"><span data-stu-id="5f490-154">See also</span></span>

- [<span data-ttu-id="5f490-155">Visa information och resultat från en automatiserad undersökning</span><span class="sxs-lookup"><span data-stu-id="5f490-155">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="5f490-156">Proaktiv sökning efter hot med avancerad sökning i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5f490-156">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>](advanced-hunting-overview.md)
