---
title: Rapportera falsk positiv eller falskt negativ i Office 365 automatisk undersökning och svar
description: Har något missats eller felaktigt upptäckts av Office 365 Avancerat skydd för hotet? Lär dig hur du skickar falska positiva eller falska negativa negativ till Microsoft för analys.
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
ms.date: 05/15/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 66b81a474ff81df57c0b2a59672b17061f7235cb
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196089"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="2c204-105">Rapportera falskta positiva eller negativa negativ i den automatiska undersökningen och svars funktionerna</span><span class="sxs-lookup"><span data-stu-id="2c204-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="2c204-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="2c204-106">**Applies to:**</span></span>
- <span data-ttu-id="2c204-107">Office 365 Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="2c204-107">Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="2c204-108">Har [automatiserade undersökningar och svar (Air) i Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office) missats eller inte känner till något?</span><span class="sxs-lookup"><span data-stu-id="2c204-108">Did [automated investigation and response (AIR) capabilities in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office) miss or wrongly detect something?</span></span> <span data-ttu-id="2c204-109">Det finns några åtgärder du kan vidta för att åtgärda det.</span><span class="sxs-lookup"><span data-stu-id="2c204-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="2c204-110">Du kan:</span><span class="sxs-lookup"><span data-stu-id="2c204-110">You can:</span></span>
- <span data-ttu-id="2c204-111">[Rapportera en falsk positiv/negativ till Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="2c204-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="2c204-112">[Justera dina meddelanden](#adjust-an-alert-to-prevent-false-positives-from-recurring) (vid behov); och</span><span class="sxs-lookup"><span data-stu-id="2c204-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 
- <span data-ttu-id="2c204-113">[Ångra reparations åtgärder som vidtogs](#undo-a-remediation-action).</span><span class="sxs-lookup"><span data-stu-id="2c204-113">[Undo remediation actions that were taken](#undo-a-remediation-action).</span></span> 

<span data-ttu-id="2c204-114">Använd den här artikeln som en guide.</span><span class="sxs-lookup"><span data-stu-id="2c204-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="2c204-115">Rapportera en falsk positiv/negativ till Microsoft för analys</span><span class="sxs-lookup"><span data-stu-id="2c204-115">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="2c204-116">Om Office 365 AIR missade ett e-postmeddelande, en e-postbilaga, en URL i ett e-postmeddelande eller en URL i en Office-fil kan du [Skicka misstänkt skräp post, Phish, URL: er och filer till Microsoft för Office 365-genomsökning](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).</span><span class="sxs-lookup"><span data-stu-id="2c204-116">If Office 365 AIR missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).</span></span>

<span data-ttu-id="2c204-117">Du kan också [skicka en fil till Microsoft för analys av skadlig program vara](https://www.microsoft.com/wdsi/filesubmission).</span><span class="sxs-lookup"><span data-stu-id="2c204-117">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="2c204-118">Justera en avisering för att förhindra falsk negativ från återkommande</span><span class="sxs-lookup"><span data-stu-id="2c204-118">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="2c204-119">Om en avisering utlöses av en legitim användning eller om aviseringen inte stämmer kan du [Hantera aviseringar i Cloud App Security-portalen](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span><span class="sxs-lookup"><span data-stu-id="2c204-119">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="2c204-120">Om din organisation använder [Microsoft Defender Avancerat skydd](https://docs.microsoft.com/windows/security/threat-protection) utöver Office 365 och en fil, IP-adress, URL eller domän behandlas som skadlig program vara på en enhet, trots att det är säkert, kan du [skapa en egen indikator med en "Tillåt"-åtgärd för enheten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span><span class="sxs-lookup"><span data-stu-id="2c204-120">If your organization is using [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="2c204-121">Ångra en åtgärd för reparation</span><span class="sxs-lookup"><span data-stu-id="2c204-121">Undo a remediation action</span></span>

<span data-ttu-id="2c204-122">I de flesta fall kan en reparations åtgärd vidtas i ett e-postmeddelande, en e-postbilaga eller en URL-adress, och objektet är egentligen inte ett hot, men din säkerhets åtgärds grupp återställer åtgärden och vidtar åtgärder för att förhindra att det falska positiva värdet för återkommande.</span><span class="sxs-lookup"><span data-stu-id="2c204-122">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="2c204-123">Du kan antingen använda [Threat Explorer](#undo-an-action-using-threat-explorer) eller [fliken åtgärder för att få en undersökning](#undo-an-action-using-the-actions-tab-for-an-investigation) för att ångra en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="2c204-123">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-using-the-actions-tab-for-an-investigation) to undo an action.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="2c204-124">Kontrol lera att du har nödvändig behörighet innan du försöker utföra följande uppgifter.</span><span class="sxs-lookup"><span data-stu-id="2c204-124">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="2c204-125">Ångra en åtgärd med hjälp av Threat Explorer</span><span class="sxs-lookup"><span data-stu-id="2c204-125">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="2c204-126">Med Threat Explorer kan säkerhets åtgärds gruppen Hitta ett e-postmeddelande som påverkas av en åtgärd och eventuellt ångra åtgärden.</span><span class="sxs-lookup"><span data-stu-id="2c204-126">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

****

|<span data-ttu-id="2c204-127">Ovanligt</span><span class="sxs-lookup"><span data-stu-id="2c204-127">Scenario</span></span>|<span data-ttu-id="2c204-128">Ångra-alternativ</span><span class="sxs-lookup"><span data-stu-id="2c204-128">Undo Options</span></span>|<span data-ttu-id="2c204-129">Mer information</span><span class="sxs-lookup"><span data-stu-id="2c204-129">Learn more</span></span>|
|---|---|---|
|<span data-ttu-id="2c204-130">Ett e-postmeddelande dirigerades till en användares mapp för skräp post</span><span class="sxs-lookup"><span data-stu-id="2c204-130">An email message was routed to a user's Junk Email folder</span></span>|<span data-ttu-id="2c204-131">-Flytta meddelandet till användarens mapp för borttagna objekt</span><span class="sxs-lookup"><span data-stu-id="2c204-131">- Move the message to the user's Deleted Items folder</span></span><br/><span data-ttu-id="2c204-132">-Flytta meddelandet till användarens inkorg</span><span class="sxs-lookup"><span data-stu-id="2c204-132">- Move the message to the user's Inbox</span></span> <br/><span data-ttu-id="2c204-133">-Ta bort meddelandet</span><span class="sxs-lookup"><span data-stu-id="2c204-133">- Delete the message</span></span>|[<span data-ttu-id="2c204-134">Hitta och undersöka skadlig e-post som har levererats i Office 365</span><span class="sxs-lookup"><span data-stu-id="2c204-134">Find and investigate malicious email that was delivered in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered)|
|<span data-ttu-id="2c204-135">Ett e-postmeddelande eller en fil sattes i karantän</span><span class="sxs-lookup"><span data-stu-id="2c204-135">An email message or a file was quarantined</span></span>|<span data-ttu-id="2c204-136">-Släpp e-postmeddelandet eller filen</span><span class="sxs-lookup"><span data-stu-id="2c204-136">- Release the email or file</span></span> <br/><span data-ttu-id="2c204-137">-Ta bort e-postmeddelandet eller filen</span><span class="sxs-lookup"><span data-stu-id="2c204-137">- Delete the email or file</span></span>|[<span data-ttu-id="2c204-138">Hantera meddelanden och filer i karantän som administratör i Office 365</span><span class="sxs-lookup"><span data-stu-id="2c204-138">Manage quarantined messages and files as an administrator in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/manage-quarantined-messages-and-files)|
|

### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a><span data-ttu-id="2c204-139">Ångra en åtgärd på fliken åtgärder för en undersökning</span><span class="sxs-lookup"><span data-stu-id="2c204-139">Undo an action using the Actions tab for an investigation</span></span>

<span data-ttu-id="2c204-140">I åtgärds Center kan du se åtgärds åtgärder som vidtogs och eventuellt ångra åtgärden.</span><span class="sxs-lookup"><span data-stu-id="2c204-140">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="2c204-141">Gå till [https://protection.office.com](https://protection.office.com) och logga in.</span><span class="sxs-lookup"><span data-stu-id="2c204-141">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="2c204-142">Då kommer du till säkerhets & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="2c204-142">This takes you to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="2c204-143">Gå till **Threat Management**  >  **utredningar**.</span><span class="sxs-lookup"><span data-stu-id="2c204-143">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="2c204-144">I listan över undersökningar väljer du ikonen **Öppna i nytt fönster** bredvid ett objekts ID.</span><span class="sxs-lookup"><span data-stu-id="2c204-144">In the list of investigations, select the **Open in new window** icon next to an item's ID.</span></span>

4. <span data-ttu-id="2c204-145">Välj fliken **åtgärder** .</span><span class="sxs-lookup"><span data-stu-id="2c204-145">Select the **Actions** tab.</span></span>

5. <span data-ttu-id="2c204-146">Markera ett objekt som har statusen **slutförd**och leta efter en länk, till exempel **godkänd**, i kolumnen **beslut** .</span><span class="sxs-lookup"><span data-stu-id="2c204-146">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decision** column.</span></span> <span data-ttu-id="2c204-147">Då öppnas en utfällbar lista med mer information om åtgärden.</span><span class="sxs-lookup"><span data-stu-id="2c204-147">This opens a flyout with more details about the action.</span></span>

6. <span data-ttu-id="2c204-148">Om du vill ångra åtgärden väljer du **ta bort reparation**.</span><span class="sxs-lookup"><span data-stu-id="2c204-148">To undo the action, select **Delete remediation**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="2c204-149">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="2c204-149">Related articles</span></span>

[<span data-ttu-id="2c204-150">Office 365 Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="2c204-150">Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)

[<span data-ttu-id="2c204-151">Komma igång med automatisk undersökning och svar (AIR) i Office 365</span><span class="sxs-lookup"><span data-stu-id="2c204-151">Get started using Automated investigation and response (AIR) in Office 365</span></span>](office-365-air.md)
