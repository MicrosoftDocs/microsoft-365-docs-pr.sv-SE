---
title: Rapportera falska positiva eller falska negativa tal efter en automatiserad undersökning i Microsoft Defender för Office 365
description: Har något missats eller identifierats felaktigt av AIR i Microsoft Defender för Office 365? Lär dig hur du skickar falska positiva eller falska negativa tal till Microsoft för analys.
keywords: automatiserad, undersökning, avisering, utlösare, åtgärd, falsk positiv, falsk negativ
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
- m365initiative-defender-office365
ms.topic: how-to
ms.custom:
- autoir
ms.technology: mdo
ms.openlocfilehash: 4ccc023a72ca450b1f0a433410206ccce59cb5f1
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142987"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="d74ce-105">Hur du rapporterar falska positiva/negativa tal i automatiserad undersökning och svarsfunktioner</span><span class="sxs-lookup"><span data-stu-id="d74ce-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="d74ce-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="d74ce-106">**Applies to:**</span></span>
- <span data-ttu-id="d74ce-107">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="d74ce-107">Microsoft Defender for Office 365</span></span>

<span data-ttu-id="d74ce-108">Om automatisk undersökning och svar [(AIR) i Office 365](automated-investigation-response-office.md) missade eller felaktigt identifierat något finns det åtgärder som teamet kan vidta för att åtgärda det.</span><span class="sxs-lookup"><span data-stu-id="d74ce-108">If [automated investigation and response (AIR) capabilities in Office 365](automated-investigation-response-office.md) missed or wrongly detected something, there are steps your security operations team can take to fix it.</span></span> <span data-ttu-id="d74ce-109">Sådana åtgärder omfattar:</span><span class="sxs-lookup"><span data-stu-id="d74ce-109">Such actions include:</span></span>

- <span data-ttu-id="d74ce-110">[Rapportera ett falskt positivt/negativt värde till Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="d74ce-110">[Reporting a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="d74ce-111">[Justera aviseringar](#adjust-an-alert-to-prevent-false-positives-from-recurring) (vid behov). och</span><span class="sxs-lookup"><span data-stu-id="d74ce-111">[Adjusting alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span>
- <span data-ttu-id="d74ce-112">[Ångra åtgärder som har vidtas.](#undo-a-remediation-action)</span><span class="sxs-lookup"><span data-stu-id="d74ce-112">[Undoing remediation actions that were taken](#undo-a-remediation-action).</span></span>

<span data-ttu-id="d74ce-113">Använd den här artikeln som en guide.</span><span class="sxs-lookup"><span data-stu-id="d74ce-113">Use this article as a guide.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="d74ce-114">Rapportera ett falskt positivt/negativt till Microsoft för analys</span><span class="sxs-lookup"><span data-stu-id="d74ce-114">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="d74ce-115">Om AIR i Microsoft Defender för Office 365 missade ett e-postmeddelande, en e-postbilaga, en URL-adress i ett e-postmeddelande eller en URL-adress i en Office-fil kan du skicka misstänkt [skräppost, phish, URL:er](admin-submission.md)och filer till Microsoft för Office 365-skanning.</span><span class="sxs-lookup"><span data-stu-id="d74ce-115">If AIR in Microsoft Defender for Office 365 missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](admin-submission.md).</span></span>

<span data-ttu-id="d74ce-116">Du kan också [skicka en fil till Microsoft för analys av skadlig programvara.](https://www.microsoft.com/wdsi/filesubmission)</span><span class="sxs-lookup"><span data-stu-id="d74ce-116">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="d74ce-117">Justera en avisering för att förhindra att falska positiva resultat upprepas</span><span class="sxs-lookup"><span data-stu-id="d74ce-117">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="d74ce-118">Om en avisering utlöses av legitimt bruk eller om aviseringen är felaktig kan du hantera [aviseringar i Cloud App Security-portalen.](https://docs.microsoft.com/cloud-app-security/managing-alerts)</span><span class="sxs-lookup"><span data-stu-id="d74ce-118">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="d74ce-119">Om din organisation använder [Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection) för Slutpunkt utöver Office 365 och en fil, IP-adress, URL eller domän behandlas som skadlig programvara på en enhet, även om det är säkert, kan du skapa en anpassad indikator med åtgärden ["Tillåt"](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)för din enhet.</span><span class="sxs-lookup"><span data-stu-id="d74ce-119">If your organization is using [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="d74ce-120">Ångra en åtgärdsåtgärd</span><span class="sxs-lookup"><span data-stu-id="d74ce-120">Undo a remediation action</span></span>

<span data-ttu-id="d74ce-121">Om en åtgärdsåtgärd har vidtagits för ett e-postmeddelande, en e-postbilaga eller en URL,och objektet egentligen inte är ett hot, kan säkerhetsåtgärdsteamet i de flesta fall ångra åtgärden och vidta åtgärder för att förhindra att meddelandet felaktigt är återkommande.</span><span class="sxs-lookup"><span data-stu-id="d74ce-121">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="d74ce-122">Du kan använda antingen [Hotutforskaren](#undo-an-action-using-threat-explorer) eller [fliken Åtgärder för en undersökning](#undo-an-action-in-the-action-center) för att ångra en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="d74ce-122">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-in-the-action-center) to undo an action.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d74ce-123">Kontrollera att du har de behörigheter som behövs innan du försöker utföra följande uppgifter.</span><span class="sxs-lookup"><span data-stu-id="d74ce-123">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="d74ce-124">Ångra en åtgärd med Hjälp av Hotutforskaren</span><span class="sxs-lookup"><span data-stu-id="d74ce-124">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="d74ce-125">Med Threat Explorer kan ditt säkerhetsteam hitta ett e-postmeddelande som påverkas av en åtgärd och eventuellt ångra åtgärden.</span><span class="sxs-lookup"><span data-stu-id="d74ce-125">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

|<span data-ttu-id="d74ce-126">Scenario</span><span class="sxs-lookup"><span data-stu-id="d74ce-126">Scenario</span></span>|<span data-ttu-id="d74ce-127">Ångra alternativ</span><span class="sxs-lookup"><span data-stu-id="d74ce-127">Undo Options</span></span>|<span data-ttu-id="d74ce-128">Mer information</span><span class="sxs-lookup"><span data-stu-id="d74ce-128">Learn more</span></span>|
|---|---|---|
|<span data-ttu-id="d74ce-129">Ett e-postmeddelande har dirigerats till en användares skräppostmapp</span><span class="sxs-lookup"><span data-stu-id="d74ce-129">An email message was routed to a user's Junk Email folder</span></span>|<span data-ttu-id="d74ce-130">- Flytta meddelandet till användarens borttagna objekt-mapp</span><span class="sxs-lookup"><span data-stu-id="d74ce-130">- Move the message to the user's Deleted Items folder</span></span><br/><span data-ttu-id="d74ce-131">- Flytta meddelandet till användarens inkorg</span><span class="sxs-lookup"><span data-stu-id="d74ce-131">- Move the message to the user's Inbox</span></span><br/><span data-ttu-id="d74ce-132">- Ta bort meddelandet</span><span class="sxs-lookup"><span data-stu-id="d74ce-132">- Delete the message</span></span>|[<span data-ttu-id="d74ce-133">Hitta och undersöka skadlig e-post som levererats i Office 365</span><span class="sxs-lookup"><span data-stu-id="d74ce-133">Find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)|
|<span data-ttu-id="d74ce-134">Ett e-postmeddelande eller en fil har satts i karantän</span><span class="sxs-lookup"><span data-stu-id="d74ce-134">An email message or a file was quarantined</span></span>|<span data-ttu-id="d74ce-135">- Släpp e-postmeddelandet eller filen</span><span class="sxs-lookup"><span data-stu-id="d74ce-135">- Release the email or file</span></span><br/><span data-ttu-id="d74ce-136">- Ta bort e-postmeddelandet eller filen</span><span class="sxs-lookup"><span data-stu-id="d74ce-136">- Delete the email or file</span></span>|[<span data-ttu-id="d74ce-137">Hantera meddelanden i karantän som administratör</span><span class="sxs-lookup"><span data-stu-id="d74ce-137">Manage quarantined messages as an admin</span></span>](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a><span data-ttu-id="d74ce-138">Ångra en åtgärd i Åtgärdscenter</span><span class="sxs-lookup"><span data-stu-id="d74ce-138">Undo an action in the Action center</span></span>

<span data-ttu-id="d74ce-139">I Åtgärdscenter kan du se åtgärder som har vidtagits och eventuellt ångra åtgärden.</span><span class="sxs-lookup"><span data-stu-id="d74ce-139">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="d74ce-140">Gå till Microsoft 365 säkerhetscenter ( [https://security.microsoft.com](https://security.microsoft.com) ).</span><span class="sxs-lookup"><span data-stu-id="d74ce-140">Go to the Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)).</span></span>
2. <span data-ttu-id="d74ce-141">Välj Åtgärdscenter i **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="d74ce-141">In the navigation pane, select **Action center**.</span></span> 
3. <span data-ttu-id="d74ce-142">Välj fliken **Historik** för att visa listan över slutförda åtgärder.</span><span class="sxs-lookup"><span data-stu-id="d74ce-142">Select the **History** tab to view the list of completed actions.</span></span>
4. <span data-ttu-id="d74ce-143">Markera ett objekt.</span><span class="sxs-lookup"><span data-stu-id="d74ce-143">Select an item.</span></span> <span data-ttu-id="d74ce-144">Det utfällfönster som visas.</span><span class="sxs-lookup"><span data-stu-id="d74ce-144">Its flyout pane opens.</span></span> 
5. <span data-ttu-id="d74ce-145">Välj Ångra i det utfällade **fönstret.**</span><span class="sxs-lookup"><span data-stu-id="d74ce-145">In the flyout pane, select **Undo**.</span></span> <span data-ttu-id="d74ce-146">(Det är bara åtgärder som kan ångras som har **knappen Ångra.)**</span><span class="sxs-lookup"><span data-stu-id="d74ce-146">(Only actions that can be undone will have an **Undo** button.)</span></span>

## <a name="see-also"></a><span data-ttu-id="d74ce-147">Se även</span><span class="sxs-lookup"><span data-stu-id="d74ce-147">See also</span></span>

- [<span data-ttu-id="d74ce-148">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="d74ce-148">Microsoft Defender for Office 365</span></span>](office-365-atp.md)
- [<span data-ttu-id="d74ce-149">Automatiserade undersökningar i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="d74ce-149">Automated investigations in Microsoft Defender for Office 365</span></span>](office-365-air.md)
