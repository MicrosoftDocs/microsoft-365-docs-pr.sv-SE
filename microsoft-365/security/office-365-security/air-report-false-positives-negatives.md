---
title: Så här rapporterar du falska positiva eller falska negativ i automatisk undersökning och svar i Office 365
description: Har något missats eller upptäckts felaktigt av Office 365 Advanced Threat Protection? Lär dig hur du skickar falska positiva eller falska negativ till Microsoft för analys.
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
ms.date: 05/15/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 837232550ca392a364b9842f64a1c3f0d790a502
ms.sourcegitcommit: 33be6075fcc89d4c0a48fa7e59f3b3ebc605d9f3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2020
ms.locfileid: "44520164"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="4fbf6-105">Så här rapporterar du falska positiva identifieringar/negativ i automatiserade undersöknings- och svarsfunktioner</span><span class="sxs-lookup"><span data-stu-id="4fbf6-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="4fbf6-106">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="4fbf6-106">**Applies to:**</span></span>
- <span data-ttu-id="4fbf6-107">Office 365 Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="4fbf6-107">Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="4fbf6-108">Har funktioner för [automatisk undersökning och respons (AIR) i Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office) missat eller felidentifierade något?</span><span class="sxs-lookup"><span data-stu-id="4fbf6-108">Did [automated investigation and response (AIR) capabilities in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office) miss or wrongly detect something?</span></span> <span data-ttu-id="4fbf6-109">Det finns åtgärder du kan vidta för att åtgärda det.</span><span class="sxs-lookup"><span data-stu-id="4fbf6-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="4fbf6-110">Du kan:</span><span class="sxs-lookup"><span data-stu-id="4fbf6-110">You can:</span></span>
- <span data-ttu-id="4fbf6-111">[Rapportera ett falskt positivt/negativt till Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="4fbf6-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="4fbf6-112">[Justera dina aviseringar](#adjust-an-alert-to-prevent-false-positives-from-recurring) (om det behövs); Och</span><span class="sxs-lookup"><span data-stu-id="4fbf6-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 
- <span data-ttu-id="4fbf6-113">[Ångra åtgärder för reparation som har vidtagits](#undo-a-remediation-action).</span><span class="sxs-lookup"><span data-stu-id="4fbf6-113">[Undo remediation actions that were taken](#undo-a-remediation-action).</span></span> 

<span data-ttu-id="4fbf6-114">Använd den här artikeln som vägledning.</span><span class="sxs-lookup"><span data-stu-id="4fbf6-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="4fbf6-115">Rapportera ett falskt positivt/negativt till Microsoft för analys</span><span class="sxs-lookup"><span data-stu-id="4fbf6-115">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="4fbf6-116">Om Office 365 AIR missade ett e-postmeddelande, en e-postbilaga, en URL i ett e-postmeddelande eller en URL i en Office-fil kan du [skicka misstänkt skräppost, phish, URL:er och filer till Microsoft för Office 365-skanning](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).</span><span class="sxs-lookup"><span data-stu-id="4fbf6-116">If Office 365 AIR missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).</span></span>

<span data-ttu-id="4fbf6-117">Du kan också [skicka en fil till Microsoft för analys av skadlig kod](https://www.microsoft.com/wdsi/filesubmission).</span><span class="sxs-lookup"><span data-stu-id="4fbf6-117">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="4fbf6-118">Justera en avisering för att förhindra att falska positiva identifieringar upprepas</span><span class="sxs-lookup"><span data-stu-id="4fbf6-118">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="4fbf6-119">Om en avisering utlöses av legitim användning eller aviseringen är felaktig kan du [hantera aviseringar i Cloud App Security-portalen](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span><span class="sxs-lookup"><span data-stu-id="4fbf6-119">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="4fbf6-120">Om din organisation använder [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) utöver Office 365 och en fil, IP-adress, URL eller domän behandlas som skadlig kod på en enhet, även om det är säkert, kan du skapa en anpassad indikator med åtgärden Tillåt för din [enhet](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span><span class="sxs-lookup"><span data-stu-id="4fbf6-120">If your organization is using [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="4fbf6-121">Ångra en åtgärd</span><span class="sxs-lookup"><span data-stu-id="4fbf6-121">Undo a remediation action</span></span>

<span data-ttu-id="4fbf6-122">I de flesta fall, om en reparationsåtgärd har vidtagits på ett e-postmeddelande, en e-postbilaga eller webbadress, och objektet faktiskt inte är ett hot, kan säkerhetsoperationsteamet ångra reparationsåtgärden och vidta åtgärder för att förhindra att det falska positiva upprepas.</span><span class="sxs-lookup"><span data-stu-id="4fbf6-122">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="4fbf6-123">Du kan antingen använda [Threat Explorer](#undo-an-action-using-threat-explorer) eller fliken Åtgärder för att en [undersökning ska](#undo-an-action-using-the-actions-tab-for-an-investigation) ångra en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="4fbf6-123">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-using-the-actions-tab-for-an-investigation) to undo an action.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="4fbf6-124">Kontrollera att du har de behörigheter som krävs innan du försöker utföra följande uppgifter.</span><span class="sxs-lookup"><span data-stu-id="4fbf6-124">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="4fbf6-125">Ångra en åtgärd med Hjälp av Threat Explorer</span><span class="sxs-lookup"><span data-stu-id="4fbf6-125">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="4fbf6-126">Med Threat Explorer kan säkerhetsoperationsteamet hitta ett e-postmeddelande som påverkas av en åtgärd och eventuellt ångra åtgärden.</span><span class="sxs-lookup"><span data-stu-id="4fbf6-126">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

|<span data-ttu-id="4fbf6-127">Scenario</span><span class="sxs-lookup"><span data-stu-id="4fbf6-127">Scenario</span></span>  |<span data-ttu-id="4fbf6-128">Ångra alternativ</span><span class="sxs-lookup"><span data-stu-id="4fbf6-128">Undo Options</span></span>  |<span data-ttu-id="4fbf6-129">Mer information</span><span class="sxs-lookup"><span data-stu-id="4fbf6-129">Learn more</span></span> |
|---------|---------|---------|
|<span data-ttu-id="4fbf6-130">Ett e-postmeddelande dirigerades till en användares skräppostmapp</span><span class="sxs-lookup"><span data-stu-id="4fbf6-130">An email message was routed to a user's Junk Email folder</span></span>     |<span data-ttu-id="4fbf6-131">- Flytta meddelandet till användarens mapp Borttaget</span><span class="sxs-lookup"><span data-stu-id="4fbf6-131">- Move the message to the user's Deleted Items folder</span></span><br/><span data-ttu-id="4fbf6-132">- Flytta meddelandet till användarens inkorg</span><span class="sxs-lookup"><span data-stu-id="4fbf6-132">- Move the message to the user's Inbox</span></span> <br/><span data-ttu-id="4fbf6-133">- Ta bort meddelandet</span><span class="sxs-lookup"><span data-stu-id="4fbf6-133">- Delete the message</span></span>          |[<span data-ttu-id="4fbf6-134">Hitta och undersöka skadlig e-post som levererades i Office 365</span><span class="sxs-lookup"><span data-stu-id="4fbf6-134">Find and investigate malicious email that was delivered in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered) |
|<span data-ttu-id="4fbf6-135">Ett e-postmeddelande eller en fil har satts i karantän</span><span class="sxs-lookup"><span data-stu-id="4fbf6-135">An email message or a file was quarantined</span></span>     |<span data-ttu-id="4fbf6-136">- Släpp e-post eller fil</span><span class="sxs-lookup"><span data-stu-id="4fbf6-136">- Release the email or file</span></span> <br/><span data-ttu-id="4fbf6-137">- Ta bort e-post eller fil</span><span class="sxs-lookup"><span data-stu-id="4fbf6-137">- Delete the email or file</span></span>         |[<span data-ttu-id="4fbf6-138">Hantera meddelanden och filer i karantän som administratör i Office 365</span><span class="sxs-lookup"><span data-stu-id="4fbf6-138">Manage quarantined messages and files as an administrator in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/manage-quarantined-messages-and-files) |


### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a><span data-ttu-id="4fbf6-139">Ångra en åtgärd med hjälp av fliken Åtgärder för en undersökning</span><span class="sxs-lookup"><span data-stu-id="4fbf6-139">Undo an action using the Actions tab for an investigation</span></span>

<span data-ttu-id="4fbf6-140">I åtgärdscentret kan du se åtgärder för reparation som har vidtagits och eventuellt ångra åtgärden.</span><span class="sxs-lookup"><span data-stu-id="4fbf6-140">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="4fbf6-141">Gå till [https://protection.office.com](https://protection.office.com) och logga in.</span><span class="sxs-lookup"><span data-stu-id="4fbf6-141">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="4fbf6-142">Detta tar dig till Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="4fbf6-142">This takes you to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="4fbf6-143">Gå till **Hot management**  >  **Undersökningar**.</span><span class="sxs-lookup"><span data-stu-id="4fbf6-143">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="4fbf6-144">I listan över undersökningar väljer du ikonen **Öppna i nytt fönster** bredvid ett objekts ID.</span><span class="sxs-lookup"><span data-stu-id="4fbf6-144">In the list of investigations, select the **Open in new window** icon next to an item's ID.</span></span>

4. <span data-ttu-id="4fbf6-145">Välj fliken **Åtgärder.**</span><span class="sxs-lookup"><span data-stu-id="4fbf6-145">Select the **Actions** tab.</span></span>

5. <span data-ttu-id="4fbf6-146">Markera ett objekt som har **statusen Slutförd**och leta efter en länk, till exempel **Godkänd**, i kolumnen **Beslut.**</span><span class="sxs-lookup"><span data-stu-id="4fbf6-146">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decision** column.</span></span> <span data-ttu-id="4fbf6-147">Detta öppnar ett utfällbart överläge med mer information om åtgärden.</span><span class="sxs-lookup"><span data-stu-id="4fbf6-147">This opens a flyout with more details about the action.</span></span>

6. <span data-ttu-id="4fbf6-148">Om du vill ångra åtgärden väljer du **Ta bort reparation**.</span><span class="sxs-lookup"><span data-stu-id="4fbf6-148">To undo the action, select **Delete remediation**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="4fbf6-149">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="4fbf6-149">Related articles</span></span>

[<span data-ttu-id="4fbf6-150">Office 365 Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="4fbf6-150">Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)

[<span data-ttu-id="4fbf6-151">Komma igång med automatisk undersökning och svar (AIR) i Office 365</span><span class="sxs-lookup"><span data-stu-id="4fbf6-151">Get started using Automated investigation and response (AIR) in Office 365</span></span>](office-365-air.md)
