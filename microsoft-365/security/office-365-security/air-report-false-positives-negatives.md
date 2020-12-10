---
title: Rapportera falsk positiv eller falskt negativ efter en automatiserad undersökning i Microsoft Defender för Office 365
description: Har något missats eller felaktigt upptäckts av AIR i Microsoft Defender för Office 365? Lär dig hur du skickar falska positiva eller falska negativa negativ till Microsoft för analys.
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
ms.date: 09/29/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: conceptual
ms.custom:
- autoir
ms.openlocfilehash: 0fe8891f5ea6af215791c5f4321a93667a9d58f0
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616182"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="92bf6-105">Rapportera falskta positiva eller negativa negativ i den automatiska undersökningen och svars funktionerna</span><span class="sxs-lookup"><span data-stu-id="92bf6-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="92bf6-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="92bf6-106">**Applies to:**</span></span>
- <span data-ttu-id="92bf6-107">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="92bf6-107">Microsoft Defender for Office 365</span></span>

<span data-ttu-id="92bf6-108">Har [automatiserade undersökningar och svar (Air) i Office 365](automated-investigation-response-office.md) missats eller inte känner till något?</span><span class="sxs-lookup"><span data-stu-id="92bf6-108">Did [automated investigation and response (AIR) capabilities in Office 365](automated-investigation-response-office.md) miss or wrongly detect something?</span></span> <span data-ttu-id="92bf6-109">Det finns några åtgärder du kan vidta för att åtgärda det.</span><span class="sxs-lookup"><span data-stu-id="92bf6-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="92bf6-110">Du kan:</span><span class="sxs-lookup"><span data-stu-id="92bf6-110">You can:</span></span>

- <span data-ttu-id="92bf6-111">[Rapportera en falsk positiv/negativ till Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="92bf6-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="92bf6-112">[Justera dina meddelanden](#adjust-an-alert-to-prevent-false-positives-from-recurring) (vid behov); och</span><span class="sxs-lookup"><span data-stu-id="92bf6-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span>
- <span data-ttu-id="92bf6-113">[Ångra reparations åtgärder som vidtogs](#undo-a-remediation-action).</span><span class="sxs-lookup"><span data-stu-id="92bf6-113">[Undo remediation actions that were taken](#undo-a-remediation-action).</span></span>

<span data-ttu-id="92bf6-114">Använd den här artikeln som en guide.</span><span class="sxs-lookup"><span data-stu-id="92bf6-114">Use this article as a guide.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="92bf6-115">Rapportera en falsk positiv/negativ till Microsoft för analys</span><span class="sxs-lookup"><span data-stu-id="92bf6-115">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="92bf6-116">Om luften i Microsoft Defender för Office 365 missade ett e-postmeddelande, en e-postbilaga, en URL i ett e-postmeddelande eller en URL i en Office-fil kan du [Skicka misstänkt skräp post, Phish, webb adresser och filer till Microsoft för Office 365-genomsökning](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="92bf6-116">If AIR in Microsoft Defender for Office 365 missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](admin-submission.md).</span></span>

<span data-ttu-id="92bf6-117">Du kan också [skicka en fil till Microsoft för analys av skadlig program vara](https://www.microsoft.com/wdsi/filesubmission).</span><span class="sxs-lookup"><span data-stu-id="92bf6-117">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="92bf6-118">Justera en avisering för att förhindra falsk negativ från återkommande</span><span class="sxs-lookup"><span data-stu-id="92bf6-118">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="92bf6-119">Om en avisering utlöses av en legitim användning eller om aviseringen inte stämmer kan du [Hantera aviseringar i Cloud App Security-portalen](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span><span class="sxs-lookup"><span data-stu-id="92bf6-119">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="92bf6-120">Om din organisation använder [Microsoft Defender för slut punkt](https://docs.microsoft.com/windows/security/threat-protection) utöver Office 365 behandlas en fil, IP-adress, URL eller domän som skadlig program vara på en enhet, trots att det är säkert kan du [skapa en egen indikator med en "Tillåt"-åtgärd för enheten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span><span class="sxs-lookup"><span data-stu-id="92bf6-120">If your organization is using [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="92bf6-121">Ångra en åtgärd för reparation</span><span class="sxs-lookup"><span data-stu-id="92bf6-121">Undo a remediation action</span></span>

<span data-ttu-id="92bf6-122">I de flesta fall kan en reparations åtgärd vidtas i ett e-postmeddelande, en e-postbilaga eller en URL-adress, och objektet är egentligen inte ett hot, men din säkerhets åtgärds grupp återställer åtgärden och vidtar åtgärder för att förhindra att det falska positiva värdet för återkommande.</span><span class="sxs-lookup"><span data-stu-id="92bf6-122">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="92bf6-123">Du kan antingen använda [Threat Explorer](#undo-an-action-using-threat-explorer) eller [fliken åtgärder för att få en undersökning](#undo-an-action-using-the-actions-tab-for-an-investigation) för att ångra en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="92bf6-123">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-using-the-actions-tab-for-an-investigation) to undo an action.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="92bf6-124">Kontrol lera att du har nödvändig behörighet innan du försöker utföra följande uppgifter.</span><span class="sxs-lookup"><span data-stu-id="92bf6-124">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="92bf6-125">Ångra en åtgärd med hjälp av Threat Explorer</span><span class="sxs-lookup"><span data-stu-id="92bf6-125">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="92bf6-126">Med Threat Explorer kan säkerhets åtgärds gruppen Hitta ett e-postmeddelande som påverkas av en åtgärd och eventuellt ångra åtgärden.</span><span class="sxs-lookup"><span data-stu-id="92bf6-126">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

****

|<span data-ttu-id="92bf6-127">Ovanligt</span><span class="sxs-lookup"><span data-stu-id="92bf6-127">Scenario</span></span>|<span data-ttu-id="92bf6-128">Ångra-alternativ</span><span class="sxs-lookup"><span data-stu-id="92bf6-128">Undo Options</span></span>|<span data-ttu-id="92bf6-129">Mer information</span><span class="sxs-lookup"><span data-stu-id="92bf6-129">Learn more</span></span>|
|---|---|---|
|<span data-ttu-id="92bf6-130">Ett e-postmeddelande dirigerades till en användares mapp för skräp post</span><span class="sxs-lookup"><span data-stu-id="92bf6-130">An email message was routed to a user's Junk Email folder</span></span>|<ul><li><span data-ttu-id="92bf6-131">Flytta meddelandet till användarens mapp för borttagna objekt</span><span class="sxs-lookup"><span data-stu-id="92bf6-131">Move the message to the user's Deleted Items folder</span></span></li><li><span data-ttu-id="92bf6-132">Flytta meddelandet till användarens inkorg</span><span class="sxs-lookup"><span data-stu-id="92bf6-132">Move the message to the user's Inbox</span></span></li><li><span data-ttu-id="92bf6-133">Ta bort meddelandet</span><span class="sxs-lookup"><span data-stu-id="92bf6-133">Delete the message</span></span></li></ul>|[<span data-ttu-id="92bf6-134">Hitta och undersöka skadlig e-post som har levererats i Office 365</span><span class="sxs-lookup"><span data-stu-id="92bf6-134">Find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)|
|<span data-ttu-id="92bf6-135">Ett e-postmeddelande eller en fil sattes i karantän</span><span class="sxs-lookup"><span data-stu-id="92bf6-135">An email message or a file was quarantined</span></span>|<ul><li><span data-ttu-id="92bf6-136">Släpp e-postmeddelandet eller filen</span><span class="sxs-lookup"><span data-stu-id="92bf6-136">Release the email or file</span></span></li><li><span data-ttu-id="92bf6-137">Ta bort e-postmeddelandet eller filen</span><span class="sxs-lookup"><span data-stu-id="92bf6-137">Delete the email or file</span></span></li></ul>|[<span data-ttu-id="92bf6-138">Hantera meddelanden i karantän som administratör</span><span class="sxs-lookup"><span data-stu-id="92bf6-138">Manage quarantined messages as an admin</span></span>](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a><span data-ttu-id="92bf6-139">Ångra en åtgärd på fliken åtgärder för en undersökning</span><span class="sxs-lookup"><span data-stu-id="92bf6-139">Undo an action using the Actions tab for an investigation</span></span>

<span data-ttu-id="92bf6-140">I åtgärds Center kan du se åtgärds åtgärder som vidtogs och eventuellt ångra åtgärden.</span><span class="sxs-lookup"><span data-stu-id="92bf6-140">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="92bf6-141">Gå till <https://protection.office.com> och logga in.</span><span class="sxs-lookup"><span data-stu-id="92bf6-141">Go to <https://protection.office.com> and sign in.</span></span> <span data-ttu-id="92bf6-142">Då kommer du till säkerhets & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="92bf6-142">This takes you to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="92bf6-143">Gå till **Threat Management** \> **utredningar**.</span><span class="sxs-lookup"><span data-stu-id="92bf6-143">Go to **Threat management** \> **Investigations**.</span></span>

3. <span data-ttu-id="92bf6-144">I listan över undersökningar väljer du ikonen **Öppna i nytt fönster** bredvid ett objekts ID.</span><span class="sxs-lookup"><span data-stu-id="92bf6-144">In the list of investigations, select the **Open in new window** icon next to an item's ID.</span></span>

4. <span data-ttu-id="92bf6-145">Välj fliken **åtgärder** .</span><span class="sxs-lookup"><span data-stu-id="92bf6-145">Select the **Actions** tab.</span></span>

5. <span data-ttu-id="92bf6-146">Markera ett objekt som har statusen **slutförd** och leta efter en länk, till exempel **godkänd**, i kolumnen **beslut** .</span><span class="sxs-lookup"><span data-stu-id="92bf6-146">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decision** column.</span></span> <span data-ttu-id="92bf6-147">Då öppnas en utfällbar lista med mer information om åtgärden.</span><span class="sxs-lookup"><span data-stu-id="92bf6-147">This opens a flyout with more details about the action.</span></span>

6. <span data-ttu-id="92bf6-148">Om du vill ångra åtgärden väljer du **ta bort reparation**.</span><span class="sxs-lookup"><span data-stu-id="92bf6-148">To undo the action, select **Delete remediation**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="92bf6-149">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="92bf6-149">Related articles</span></span>

[<span data-ttu-id="92bf6-150">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="92bf6-150">Microsoft Defender for Office 365</span></span>](office-365-atp.md)

[<span data-ttu-id="92bf6-151">LUFT i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="92bf6-151">AIR in Microsoft Defender for Office 365</span></span>](office-365-air.md)
