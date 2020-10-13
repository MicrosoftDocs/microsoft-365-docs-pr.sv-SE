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
ms.openlocfilehash: 101747fa1121c675938610b9681f98c6e39b7d75
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446621"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="4dc19-105">Rapportera falskta positiva eller negativa negativ i den automatiska undersökningen och svars funktionerna</span><span class="sxs-lookup"><span data-stu-id="4dc19-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="4dc19-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="4dc19-106">**Applies to:**</span></span>
- <span data-ttu-id="4dc19-107">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="4dc19-107">Microsoft Defender for Office 365</span></span>

<span data-ttu-id="4dc19-108">Har [automatiserade undersökningar och svar (Air) i Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office) missats eller inte känner till något?</span><span class="sxs-lookup"><span data-stu-id="4dc19-108">Did [automated investigation and response (AIR) capabilities in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office) miss or wrongly detect something?</span></span> <span data-ttu-id="4dc19-109">Det finns några åtgärder du kan vidta för att åtgärda det.</span><span class="sxs-lookup"><span data-stu-id="4dc19-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="4dc19-110">Du kan:</span><span class="sxs-lookup"><span data-stu-id="4dc19-110">You can:</span></span>
- <span data-ttu-id="4dc19-111">[Rapportera en falsk positiv/negativ till Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="4dc19-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="4dc19-112">[Justera dina meddelanden](#adjust-an-alert-to-prevent-false-positives-from-recurring) (vid behov); och</span><span class="sxs-lookup"><span data-stu-id="4dc19-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 
- <span data-ttu-id="4dc19-113">[Ångra reparations åtgärder som vidtogs](#undo-a-remediation-action).</span><span class="sxs-lookup"><span data-stu-id="4dc19-113">[Undo remediation actions that were taken](#undo-a-remediation-action).</span></span> 

<span data-ttu-id="4dc19-114">Använd den här artikeln som en guide.</span><span class="sxs-lookup"><span data-stu-id="4dc19-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="4dc19-115">Rapportera en falsk positiv/negativ till Microsoft för analys</span><span class="sxs-lookup"><span data-stu-id="4dc19-115">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="4dc19-116">Om luften i Microsoft Defender för Office 365 missade ett e-postmeddelande, en e-postbilaga, en URL i ett e-postmeddelande eller en URL i en Office-fil kan du [Skicka misstänkt skräp post, Phish, webb adresser och filer till Microsoft för Office 365-genomsökning](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).</span><span class="sxs-lookup"><span data-stu-id="4dc19-116">If AIR in Microsoft Defender for Office 365 missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).</span></span>

<span data-ttu-id="4dc19-117">Du kan också [skicka en fil till Microsoft för analys av skadlig program vara](https://www.microsoft.com/wdsi/filesubmission).</span><span class="sxs-lookup"><span data-stu-id="4dc19-117">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="4dc19-118">Justera en avisering för att förhindra falsk negativ från återkommande</span><span class="sxs-lookup"><span data-stu-id="4dc19-118">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="4dc19-119">Om en avisering utlöses av en legitim användning eller om aviseringen inte stämmer kan du [Hantera aviseringar i Cloud App Security-portalen](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span><span class="sxs-lookup"><span data-stu-id="4dc19-119">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="4dc19-120">Om din organisation använder [Microsoft Defender för slut punkt](https://docs.microsoft.com/windows/security/threat-protection) utöver Office 365 behandlas en fil, IP-adress, URL eller domän som skadlig program vara på en enhet, trots att det är säkert kan du [skapa en egen indikator med en "Tillåt"-åtgärd för enheten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span><span class="sxs-lookup"><span data-stu-id="4dc19-120">If your organization is using [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="4dc19-121">Ångra en åtgärd för reparation</span><span class="sxs-lookup"><span data-stu-id="4dc19-121">Undo a remediation action</span></span>

<span data-ttu-id="4dc19-122">I de flesta fall kan en reparations åtgärd vidtas i ett e-postmeddelande, en e-postbilaga eller en URL-adress, och objektet är egentligen inte ett hot, men din säkerhets åtgärds grupp återställer åtgärden och vidtar åtgärder för att förhindra att det falska positiva värdet för återkommande.</span><span class="sxs-lookup"><span data-stu-id="4dc19-122">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="4dc19-123">Du kan antingen använda [Threat Explorer](#undo-an-action-using-threat-explorer) eller [fliken åtgärder för att få en undersökning](#undo-an-action-using-the-actions-tab-for-an-investigation) för att ångra en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="4dc19-123">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-using-the-actions-tab-for-an-investigation) to undo an action.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="4dc19-124">Kontrol lera att du har nödvändig behörighet innan du försöker utföra följande uppgifter.</span><span class="sxs-lookup"><span data-stu-id="4dc19-124">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="4dc19-125">Ångra en åtgärd med hjälp av Threat Explorer</span><span class="sxs-lookup"><span data-stu-id="4dc19-125">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="4dc19-126">Med Threat Explorer kan säkerhets åtgärds gruppen Hitta ett e-postmeddelande som påverkas av en åtgärd och eventuellt ångra åtgärden.</span><span class="sxs-lookup"><span data-stu-id="4dc19-126">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

****

|<span data-ttu-id="4dc19-127">Ovanligt</span><span class="sxs-lookup"><span data-stu-id="4dc19-127">Scenario</span></span>|<span data-ttu-id="4dc19-128">Ångra-alternativ</span><span class="sxs-lookup"><span data-stu-id="4dc19-128">Undo Options</span></span>|<span data-ttu-id="4dc19-129">Mer information</span><span class="sxs-lookup"><span data-stu-id="4dc19-129">Learn more</span></span>|
|---|---|---|
|<span data-ttu-id="4dc19-130">Ett e-postmeddelande dirigerades till en användares mapp för skräp post</span><span class="sxs-lookup"><span data-stu-id="4dc19-130">An email message was routed to a user's Junk Email folder</span></span>|<span data-ttu-id="4dc19-131">-Flytta meddelandet till användarens mapp för borttagna objekt</span><span class="sxs-lookup"><span data-stu-id="4dc19-131">- Move the message to the user's Deleted Items folder</span></span><br/><span data-ttu-id="4dc19-132">-Flytta meddelandet till användarens inkorg</span><span class="sxs-lookup"><span data-stu-id="4dc19-132">- Move the message to the user's Inbox</span></span> <br/><span data-ttu-id="4dc19-133">-Ta bort meddelandet</span><span class="sxs-lookup"><span data-stu-id="4dc19-133">- Delete the message</span></span>|[<span data-ttu-id="4dc19-134">Hitta och undersöka skadlig e-post som har levererats i Office 365</span><span class="sxs-lookup"><span data-stu-id="4dc19-134">Find and investigate malicious email that was delivered in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered)|
|<span data-ttu-id="4dc19-135">Ett e-postmeddelande eller en fil sattes i karantän</span><span class="sxs-lookup"><span data-stu-id="4dc19-135">An email message or a file was quarantined</span></span>|<span data-ttu-id="4dc19-136">-Släpp e-postmeddelandet eller filen</span><span class="sxs-lookup"><span data-stu-id="4dc19-136">- Release the email or file</span></span> <br/><span data-ttu-id="4dc19-137">-Ta bort e-postmeddelandet eller filen</span><span class="sxs-lookup"><span data-stu-id="4dc19-137">- Delete the email or file</span></span>|[<span data-ttu-id="4dc19-138">Hantera meddelanden och filer i karantän som administratör i Office 365</span><span class="sxs-lookup"><span data-stu-id="4dc19-138">Manage quarantined messages and files as an administrator in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/manage-quarantined-messages-and-files)|
|

### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a><span data-ttu-id="4dc19-139">Ångra en åtgärd på fliken åtgärder för en undersökning</span><span class="sxs-lookup"><span data-stu-id="4dc19-139">Undo an action using the Actions tab for an investigation</span></span>

<span data-ttu-id="4dc19-140">I åtgärds Center kan du se åtgärds åtgärder som vidtogs och eventuellt ångra åtgärden.</span><span class="sxs-lookup"><span data-stu-id="4dc19-140">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="4dc19-141">Gå till [https://protection.office.com](https://protection.office.com) och logga in.</span><span class="sxs-lookup"><span data-stu-id="4dc19-141">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="4dc19-142">Då kommer du till säkerhets & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="4dc19-142">This takes you to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="4dc19-143">Gå till **Threat Management**  >  **utredningar**.</span><span class="sxs-lookup"><span data-stu-id="4dc19-143">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="4dc19-144">I listan över undersökningar väljer du ikonen **Öppna i nytt fönster** bredvid ett objekts ID.</span><span class="sxs-lookup"><span data-stu-id="4dc19-144">In the list of investigations, select the **Open in new window** icon next to an item's ID.</span></span>

4. <span data-ttu-id="4dc19-145">Välj fliken **åtgärder** .</span><span class="sxs-lookup"><span data-stu-id="4dc19-145">Select the **Actions** tab.</span></span>

5. <span data-ttu-id="4dc19-146">Markera ett objekt som har statusen **slutförd**och leta efter en länk, till exempel **godkänd**, i kolumnen **beslut** .</span><span class="sxs-lookup"><span data-stu-id="4dc19-146">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decision** column.</span></span> <span data-ttu-id="4dc19-147">Då öppnas en utfällbar lista med mer information om åtgärden.</span><span class="sxs-lookup"><span data-stu-id="4dc19-147">This opens a flyout with more details about the action.</span></span>

6. <span data-ttu-id="4dc19-148">Om du vill ångra åtgärden väljer du **ta bort reparation**.</span><span class="sxs-lookup"><span data-stu-id="4dc19-148">To undo the action, select **Delete remediation**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="4dc19-149">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="4dc19-149">Related articles</span></span>

[<span data-ttu-id="4dc19-150">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="4dc19-150">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)

[<span data-ttu-id="4dc19-151">LUFT i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="4dc19-151">AIR in Microsoft Defender for Office 365</span></span>](office-365-air.md)
