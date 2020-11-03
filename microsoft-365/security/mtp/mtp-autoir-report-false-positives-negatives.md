---
title: Hantera falsk positiv eller falskt negativ i luften i Microsoft 365 Defender
description: Har något missats eller felaktigt upptäckts av AIR i Microsoft 365 Defender? Lär dig hur du skickar falska positiva eller falska negativa negativ till Microsoft för analys.
keywords: automatiserad, undersökning, avisering, utlösare, åtgärd, reparation, falskt positivt, falskt negativt
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 92ad4a96665a5355bce7e3546f8c52779f770927
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843738"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="55699-105">Hantera felaktiga positiva/negativa negativ i automatiserade undersökningar och svars funktioner</span><span class="sxs-lookup"><span data-stu-id="55699-105">Handle false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="55699-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="55699-106">**Applies to:**</span></span>
- <span data-ttu-id="55699-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="55699-107">Microsoft 365 Defender</span></span>

<span data-ttu-id="55699-108">Gick det inte att hitta något [automatiskt](mtp-autoir.md) i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="55699-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft 365 Defender miss or wrongly detect something?</span></span> <span data-ttu-id="55699-109">Det finns några åtgärder du kan vidta för att åtgärda det.</span><span class="sxs-lookup"><span data-stu-id="55699-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="55699-110">Du kan:</span><span class="sxs-lookup"><span data-stu-id="55699-110">You can:</span></span>

- <span data-ttu-id="55699-111">[Rapportera en falsk positiv/negativ till Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="55699-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>

- <span data-ttu-id="55699-112">[Justera dina meddelanden](#adjust-an-alert-to-prevent-false-positives-from-recurring) (vid behov); och</span><span class="sxs-lookup"><span data-stu-id="55699-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 

- <span data-ttu-id="55699-113">[Ångra reparations åtgärder som har utförts på enheter](#undo-a-remediation-action-that-was-taken-on-a-device).</span><span class="sxs-lookup"><span data-stu-id="55699-113">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="55699-114">Använd den här artikeln som en guide.</span><span class="sxs-lookup"><span data-stu-id="55699-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="55699-115">Rapportera en falsk positiv/negativ till Microsoft för analys</span><span class="sxs-lookup"><span data-stu-id="55699-115">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="55699-116">Objektet missade eller upptäcktes felaktigt</span><span class="sxs-lookup"><span data-stu-id="55699-116">Item missed or wrongly detected</span></span> |<span data-ttu-id="55699-117">Tjänst</span><span class="sxs-lookup"><span data-stu-id="55699-117">Service</span></span>  |<span data-ttu-id="55699-118">Vad kan jag göra?</span><span class="sxs-lookup"><span data-stu-id="55699-118">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="55699-119">-E-postmeddelande</span><span class="sxs-lookup"><span data-stu-id="55699-119">- Email message</span></span> <br/><span data-ttu-id="55699-120">-E-postbilaga</span><span class="sxs-lookup"><span data-stu-id="55699-120">- Email attachment</span></span> <br/><span data-ttu-id="55699-121">-URL i ett e-postmeddelande</span><span class="sxs-lookup"><span data-stu-id="55699-121">- URL in an email message</span></span><br/><span data-ttu-id="55699-122">-URL i en Office-fil</span><span class="sxs-lookup"><span data-stu-id="55699-122">- URL in an Office file</span></span>      |[<span data-ttu-id="55699-123">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="55699-123">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="55699-124">Skicka misstänkt spam, Phish, webb adresser och filer till Microsoft för genomsökning</span><span class="sxs-lookup"><span data-stu-id="55699-124">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="55699-125">Fil eller app på en enhet</span><span class="sxs-lookup"><span data-stu-id="55699-125">File or app on a device</span></span>    |[<span data-ttu-id="55699-126">Microsoft Defender för slut punkt</span><span class="sxs-lookup"><span data-stu-id="55699-126">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="55699-127">Skicka en fil till Microsoft för analys av skadlig program vara</span><span class="sxs-lookup"><span data-stu-id="55699-127">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="55699-128">Justera en avisering för att förhindra falsk negativ från återkommande</span><span class="sxs-lookup"><span data-stu-id="55699-128">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="55699-129">Ovanligt</span><span class="sxs-lookup"><span data-stu-id="55699-129">Scenario</span></span> |<span data-ttu-id="55699-130">Tjänst</span><span class="sxs-lookup"><span data-stu-id="55699-130">Service</span></span> |<span data-ttu-id="55699-131">Vad kan jag göra?</span><span class="sxs-lookup"><span data-stu-id="55699-131">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="55699-132">-En notifiering utlöses av en legitim användning</span><span class="sxs-lookup"><span data-stu-id="55699-132">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="55699-133">-En avisering är felaktig</span><span class="sxs-lookup"><span data-stu-id="55699-133">- An alert is inaccurate</span></span>    |[<span data-ttu-id="55699-134">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="55699-134">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="55699-135">eller</span><span class="sxs-lookup"><span data-stu-id="55699-135">or</span></span> <br/>[<span data-ttu-id="55699-136">Avancerad hot identifiering för Azure</span><span class="sxs-lookup"><span data-stu-id="55699-136">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="55699-137">Hantera aviseringar i Cloud App Security Portal</span><span class="sxs-lookup"><span data-stu-id="55699-137">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="55699-138">En fil, IP-adress, URL eller domän behandlas som skadlig program vara på en enhet, trots att det är säkert</span><span class="sxs-lookup"><span data-stu-id="55699-138">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="55699-139">Microsoft Defender för slut punkt</span><span class="sxs-lookup"><span data-stu-id="55699-139">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection) |[<span data-ttu-id="55699-140">Skapa en anpassad indikator med åtgärden "Tillåt"</span><span class="sxs-lookup"><span data-stu-id="55699-140">Create a custom indicator with an "Allow" action</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="55699-141">Ångra en reparations åtgärd som har utförts på en enhet</span><span class="sxs-lookup"><span data-stu-id="55699-141">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="55699-142">Om en åtgärd för reparation har utförts på en enhet (till exempel en Windows 10-enhet) och objektet inte är ett hot kan säkerhets åtgärds gruppen ångra reparations åtgärden i [Åtgärds centret](mtp-action-center.md).</span><span class="sxs-lookup"><span data-stu-id="55699-142">If a remediation action was taken on a device (such as a Windows 10 device) and the item is actually not a threat, your security operations team can undo the remediation action in the [Action center](mtp-action-center.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="55699-143">Kontrol lera att du har [nödvändig behörighet](mtp-action-center.md#required-permissions-for-action-center-tasks) innan du försöker utföra följande uppgift.</span><span class="sxs-lookup"><span data-stu-id="55699-143">Make sure you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) before attempting to perform the following task.</span></span>

1. <span data-ttu-id="55699-144">Gå till [https://security.microsoft.com](https://security.microsoft.com) och logga in.</span><span class="sxs-lookup"><span data-stu-id="55699-144">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="55699-145">I navigerings fönstret väljer du **Åtgärds Center**.</span><span class="sxs-lookup"><span data-stu-id="55699-145">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="55699-146">På fliken **Historik** väljer du en åtgärd som du vill ångra.</span><span class="sxs-lookup"><span data-stu-id="55699-146">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="55699-147">Då öppnas en utfällbar meny.</span><span class="sxs-lookup"><span data-stu-id="55699-147">This opens a flyout.</span></span><br/>
    > [!TIP]
    > <span data-ttu-id="55699-148">Använd filter för att begränsa resultat listan.</span><span class="sxs-lookup"><span data-stu-id="55699-148">Use filters to narrow down the list of results.</span></span> 

4. <span data-ttu-id="55699-149">Välj **Öppna undersöknings sida** i utfällning för det markerade objektet.</span><span class="sxs-lookup"><span data-stu-id="55699-149">In the flyout for the selected item, select **Open investigation page**.</span></span>

5. <span data-ttu-id="55699-150">I vyn undersöknings information väljer du fliken **åtgärder** .</span><span class="sxs-lookup"><span data-stu-id="55699-150">In the investigation details view, select the **Actions** tab.</span></span>

6. <span data-ttu-id="55699-151">Markera ett objekt som har statusen **slutförd** och leta efter en länk, till exempel **godkänd** , i kolumnen **beslut** .</span><span class="sxs-lookup"><span data-stu-id="55699-151">Select an item that has status of **Completed** , and look for a link, such as **Approved** , in the **Decisions** column.</span></span> <span data-ttu-id="55699-152">Då öppnas en utfällbar lista med mer information om åtgärden.</span><span class="sxs-lookup"><span data-stu-id="55699-152">This opens a flyout with more details about the action.</span></span>

7. <span data-ttu-id="55699-153">Om du vill ångra åtgärden väljer du **ta bort reparation**.</span><span class="sxs-lookup"><span data-stu-id="55699-153">To undo the action, select **Delete remediation**.</span></span>

## <a name="see-also"></a><span data-ttu-id="55699-154">Se även</span><span class="sxs-lookup"><span data-stu-id="55699-154">See also</span></span>

- [<span data-ttu-id="55699-155">Visa information och resultat från en automatisk undersökning</span><span class="sxs-lookup"><span data-stu-id="55699-155">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="55699-156">Proaktiv för problem med avancerad jakt i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="55699-156">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>](advanced-hunting-overview.md)
