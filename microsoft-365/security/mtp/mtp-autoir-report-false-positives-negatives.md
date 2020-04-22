---
title: Hantera falska positiva eller falska negativ i AIR i Microsoft Threat Protection
description: Har något missats eller felaktigt upptäckts av AIR i Microsoft Threat Protection? Lär dig hur du skickar falska positiva eller falska negativ till Microsoft för analys.
keywords: automatiserad, utredning, alert, utlösa, åtgärd, sanering, falskt positivt, falskt negativt
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 01/29/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 4030469b54d9a3a9c6f2eaceae384d39ea7f3e20
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637086"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="9a329-105">Hantera falska positiva identifieringar/negativ i automatiserade undersöknings- och svarsfunktioner</span><span class="sxs-lookup"><span data-stu-id="9a329-105">Handle false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="9a329-106">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="9a329-106">**Applies to:**</span></span>
- <span data-ttu-id="9a329-107">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="9a329-107">Microsoft Threat Protection</span></span>

<span data-ttu-id="9a329-108">Har [automatiserade undersöknings- och svarsfunktioner](mtp-autoir.md) i Microsoft Threat Protection missat eller felaktigt upptäckt något?</span><span class="sxs-lookup"><span data-stu-id="9a329-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft Threat Protection miss or wrongly detect something?</span></span> <span data-ttu-id="9a329-109">Det finns åtgärder du kan vidta för att åtgärda det.</span><span class="sxs-lookup"><span data-stu-id="9a329-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="9a329-110">Du kan:</span><span class="sxs-lookup"><span data-stu-id="9a329-110">You can:</span></span>

- <span data-ttu-id="9a329-111">[Rapportera ett falskt positivt/negativt till Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="9a329-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>

- <span data-ttu-id="9a329-112">[Justera dina aviseringar](#adjust-an-alert-to-prevent-false-positives-from-recurring) (om det behövs); Och</span><span class="sxs-lookup"><span data-stu-id="9a329-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 

- <span data-ttu-id="9a329-113">[Ångra åtgärder för reparation som har vidtagits på enheter](#undo-a-remediation-action-that-was-taken-on-a-device).</span><span class="sxs-lookup"><span data-stu-id="9a329-113">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="9a329-114">Använd den här artikeln som vägledning.</span><span class="sxs-lookup"><span data-stu-id="9a329-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="9a329-115">Rapportera ett falskt positivt/negativt till Microsoft för analys</span><span class="sxs-lookup"><span data-stu-id="9a329-115">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="9a329-116">Objektet har missats eller upptäckts felaktigt</span><span class="sxs-lookup"><span data-stu-id="9a329-116">Item missed or wrongly detected</span></span> |<span data-ttu-id="9a329-117">Tjänst</span><span class="sxs-lookup"><span data-stu-id="9a329-117">Service</span></span>  |<span data-ttu-id="9a329-118">Vad du ska göra</span><span class="sxs-lookup"><span data-stu-id="9a329-118">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="9a329-119">- E-postmeddelande</span><span class="sxs-lookup"><span data-stu-id="9a329-119">- Email message</span></span> <br/><span data-ttu-id="9a329-120">- Bifogad fil i e-post</span><span class="sxs-lookup"><span data-stu-id="9a329-120">- Email attachment</span></span> <br/><span data-ttu-id="9a329-121">- URL i ett e-postmeddelande</span><span class="sxs-lookup"><span data-stu-id="9a329-121">- URL in an email message</span></span><br/><span data-ttu-id="9a329-122">- URL i en Office-fil</span><span class="sxs-lookup"><span data-stu-id="9a329-122">- URL in an Office file</span></span>      |[<span data-ttu-id="9a329-123">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="9a329-123">Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="9a329-124">Skicka misstänkt skräppost, phish, webbadresser och filer till Microsoft för skanning</span><span class="sxs-lookup"><span data-stu-id="9a329-124">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="9a329-125">Fil eller app på en enhet</span><span class="sxs-lookup"><span data-stu-id="9a329-125">File or app on a device</span></span>    |[<span data-ttu-id="9a329-126">Microsoft Defender Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="9a329-126">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="9a329-127">Skicka en fil till Microsoft för analys av skadlig kod</span><span class="sxs-lookup"><span data-stu-id="9a329-127">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="9a329-128">Justera en avisering för att förhindra att falska positiva identifieringar upprepas</span><span class="sxs-lookup"><span data-stu-id="9a329-128">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="9a329-129">Scenario</span><span class="sxs-lookup"><span data-stu-id="9a329-129">Scenario</span></span> |<span data-ttu-id="9a329-130">Tjänst</span><span class="sxs-lookup"><span data-stu-id="9a329-130">Service</span></span> |<span data-ttu-id="9a329-131">Vad du ska göra</span><span class="sxs-lookup"><span data-stu-id="9a329-131">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="9a329-132">- En avisering utlöses av legitim användning</span><span class="sxs-lookup"><span data-stu-id="9a329-132">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="9a329-133">- En varning är felaktig</span><span class="sxs-lookup"><span data-stu-id="9a329-133">- An alert is inaccurate</span></span>    |[<span data-ttu-id="9a329-134">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="9a329-134">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="9a329-135">eller</span><span class="sxs-lookup"><span data-stu-id="9a329-135">or</span></span> <br/>[<span data-ttu-id="9a329-136">Azure avancerad hotidentifiering</span><span class="sxs-lookup"><span data-stu-id="9a329-136">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="9a329-137">Hantera aviseringar i Cloud App Security-portalen</span><span class="sxs-lookup"><span data-stu-id="9a329-137">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="9a329-138">En fil, IP-adress, URL eller domän behandlas som skadlig kod på en enhet, även om den är säker</span><span class="sxs-lookup"><span data-stu-id="9a329-138">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="9a329-139">Microsoft Defender Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="9a329-139">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection) |[<span data-ttu-id="9a329-140">Skapa en anpassad indikator med åtgärden Tillåt</span><span class="sxs-lookup"><span data-stu-id="9a329-140">Create a custom indicator with an "Allow" action</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="9a329-141">Ångra en åtgärd som har vidtagits på en enhet</span><span class="sxs-lookup"><span data-stu-id="9a329-141">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="9a329-142">Om en reparationsåtgärd har vidtagits på en enhet (till exempel en Windows 10-enhet) och objektet faktiskt inte är ett hot, kan säkerhetsoperationsgruppen ångra reparationsåtgärden i [Åtgärdscenter](mtp-action-center.md).</span><span class="sxs-lookup"><span data-stu-id="9a329-142">If a remediation action was taken on a device (such as a Windows 10 device) and the item is actually not a threat, your security operations team can undo the remediation action in the [Action center](mtp-action-center.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9a329-143">Kontrollera att du har de [behörigheter som krävs](mtp-action-center.md#required-permissions-for-action-center-tasks) innan du försöker utföra följande uppgift.</span><span class="sxs-lookup"><span data-stu-id="9a329-143">Make sure you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) before attempting to perform the following task.</span></span>

1. <span data-ttu-id="9a329-144">Gå [https://security.microsoft.com](https://security.microsoft.com) till och logga in.</span><span class="sxs-lookup"><span data-stu-id="9a329-144">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="9a329-145">Välj **Åtgärdscenter**i navigeringsfönstret .</span><span class="sxs-lookup"><span data-stu-id="9a329-145">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="9a329-146">Välj en åtgärd som du vill ångra på fliken **Historik.**</span><span class="sxs-lookup"><span data-stu-id="9a329-146">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="9a329-147">Detta öppnar ett utfällbart.</span><span class="sxs-lookup"><span data-stu-id="9a329-147">This opens a flyout.</span></span><br/>
    > [!TIP]
    > <span data-ttu-id="9a329-148">Använd filter för att begränsa resultatlistan.</span><span class="sxs-lookup"><span data-stu-id="9a329-148">Use filters to narrow down the list of results.</span></span> 

4. <span data-ttu-id="9a329-149">I utfällbara objekt för det markerade objektet väljer du **Öppna undersökningssida**.</span><span class="sxs-lookup"><span data-stu-id="9a329-149">In the flyout for the selected item, select **Open investigation page**.</span></span>

5. <span data-ttu-id="9a329-150">Välj fliken **Åtgärder** i vyn Undersökningsinformation.</span><span class="sxs-lookup"><span data-stu-id="9a329-150">In the investigation details view, select the **Actions** tab.</span></span>

6. <span data-ttu-id="9a329-151">Markera ett objekt som har **statusen Slutförd**och leta efter en länk, till exempel **Godkänd**, i kolumnen **Beslut.**</span><span class="sxs-lookup"><span data-stu-id="9a329-151">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decisions** column.</span></span> <span data-ttu-id="9a329-152">Detta öppnar ett utfällbart överläge med mer information om åtgärden.</span><span class="sxs-lookup"><span data-stu-id="9a329-152">This opens a flyout with more details about the action.</span></span>

7. <span data-ttu-id="9a329-153">Om du vill ångra åtgärden väljer du **Ta bort reparation**.</span><span class="sxs-lookup"><span data-stu-id="9a329-153">To undo the action, select **Delete remediation**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="9a329-154">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="9a329-154">Related articles</span></span>

- [<span data-ttu-id="9a329-155">Godkänna eller avvisa åtgärder relaterade till automatisk undersökning och svar</span><span class="sxs-lookup"><span data-stu-id="9a329-155">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)

- [<span data-ttu-id="9a329-156">Läs mer om Åtgärdscentret</span><span class="sxs-lookup"><span data-stu-id="9a329-156">Learn more about the Action center</span></span>](mtp-action-center.md)

- [<span data-ttu-id="9a329-157">Proaktivt jakt efter hot med avancerad jakt i Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="9a329-157">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>](advanced-hunting-overview.md)
