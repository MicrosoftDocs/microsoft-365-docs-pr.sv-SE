---
title: Så här rapporterar du falska positiva eller falska negativa tal efter en automatiserad undersökning i Microsoft Defender för Office 365
description: Har något missats eller identifierats felaktigt av AIR i Microsoft Defender för Office 365? Lär dig hur du skickar falska positiva eller falska negativa tal till Microsoft för analys.
keywords: automatiserad, undersökning, avisering, utlösare, åtgärd, åtgärd, falsk positiv, falsk negativ
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.prod: m365-security
ms.date: 01/29/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: how-to
ms.custom:
- autoir
ms.technology: mdo
ms.openlocfilehash: 4476578939f2ece90c638c919c7e4d134ea2d9ec
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073658"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="1e885-105">Så här rapporterar du falska positiva/negativa tal i automatiska undersöknings- och svarsfunktioner</span><span class="sxs-lookup"><span data-stu-id="1e885-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1e885-106">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="1e885-106">**Applies to**</span></span>
- [<span data-ttu-id="1e885-107">Microsoft Defender för Office 365 abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="1e885-107">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="1e885-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1e885-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="1e885-109">Om funktioner för automatisk undersökning och svar [(AIR) i Office 365](automated-investigation-response-office.md) missade eller felaktigt identifierade något finns det åtgärder som ditt säkerhetsteam kan vidta för att åtgärda det.</span><span class="sxs-lookup"><span data-stu-id="1e885-109">If [automated investigation and response (AIR) capabilities in Office 365](automated-investigation-response-office.md) missed or wrongly detected something, there are steps your security operations team can take to fix it.</span></span> <span data-ttu-id="1e885-110">Sådana åtgärder omfattar:</span><span class="sxs-lookup"><span data-stu-id="1e885-110">Such actions include:</span></span>

- <span data-ttu-id="1e885-111">[Rapportera ett falskt positivt/negativt resultat till Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="1e885-111">[Reporting a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="1e885-112">[Justera aviseringar](#adjust-an-alert-to-prevent-false-positives-from-recurring) (vid behov). och</span><span class="sxs-lookup"><span data-stu-id="1e885-112">[Adjusting alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span>
- <span data-ttu-id="1e885-113">[Ångra åtgärder som har vidtagits](#undo-a-remediation-action).</span><span class="sxs-lookup"><span data-stu-id="1e885-113">[Undoing remediation actions that were taken](#undo-a-remediation-action).</span></span>

<span data-ttu-id="1e885-114">Använd den här artikeln som en guide.</span><span class="sxs-lookup"><span data-stu-id="1e885-114">Use this article as a guide.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="1e885-115">Rapportera ett falskt positivt/negativt till Microsoft för analys</span><span class="sxs-lookup"><span data-stu-id="1e885-115">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="1e885-116">Om AIR i Microsoft Defender för Office 365 missade ett e-postmeddelande, en e-postbilaga, en URL-adress i ett e-postmeddelande eller en URL-adress i en Office-fil kan du skicka misstänkt skräppost, nätt många webbadresser och filer till Microsoft för [Office 365-skanning.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="1e885-116">If AIR in Microsoft Defender for Office 365 missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](admin-submission.md).</span></span>

<span data-ttu-id="1e885-117">Du kan också [skicka en fil till Microsoft för analys av skadlig programvara.](https://www.microsoft.com/wdsi/filesubmission)</span><span class="sxs-lookup"><span data-stu-id="1e885-117">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="1e885-118">Justera en avisering för att förhindra att falska positiva resultat upprepas</span><span class="sxs-lookup"><span data-stu-id="1e885-118">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="1e885-119">Om en avisering utlöses av legitimt bruk eller om aviseringen är felaktig kan du hantera [aviseringar i Cloud App Security-portalen.](/cloud-app-security/managing-alerts)</span><span class="sxs-lookup"><span data-stu-id="1e885-119">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="1e885-120">Om din organisation använder [Microsoft Defender](/windows/security/threat-protection) för Slutpunkt utöver Office 365, och en fil, IP-adress, URL eller domän behandlas som skadlig programvara på en enhet, även om det är säkert, kan du skapa en anpassad indikator med åtgärden ["Tillåt"](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)för din enhet.</span><span class="sxs-lookup"><span data-stu-id="1e885-120">If your organization is using [Microsoft Defender for Endpoint](/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="1e885-121">Ångra en åtgärd</span><span class="sxs-lookup"><span data-stu-id="1e885-121">Undo a remediation action</span></span>

<span data-ttu-id="1e885-122">Om en åtgärd har vidtagits för ett e-postmeddelande, en e-postbilaga eller en URL och objektet egentligen inte är ett hot, kan säkerhetsåtgärdsteamet i de flesta fall ångra åtgärden och vidta åtgärder för att förhindra att meddelandet felaktigt visas som ett hot.</span><span class="sxs-lookup"><span data-stu-id="1e885-122">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="1e885-123">Du kan antingen [använda Hotutforskaren](#undo-an-action-using-threat-explorer) [eller fliken Åtgärder för en undersökning](#undo-an-action-in-the-action-center) för att ångra en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="1e885-123">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-in-the-action-center) to undo an action.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1e885-124">Kontrollera att du har nödvändiga behörigheter innan du försöker utföra följande uppgifter.</span><span class="sxs-lookup"><span data-stu-id="1e885-124">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="1e885-125">Ångra en åtgärd med hjälp av Hotutforskaren</span><span class="sxs-lookup"><span data-stu-id="1e885-125">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="1e885-126">Med Threat Explorer kan ditt säkerhetsåtgärdsteam hitta ett e-postmeddelande som påverkas av en åtgärd och eventuellt ångra åtgärden.</span><span class="sxs-lookup"><span data-stu-id="1e885-126">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

|<span data-ttu-id="1e885-127">Scenario</span><span class="sxs-lookup"><span data-stu-id="1e885-127">Scenario</span></span>|<span data-ttu-id="1e885-128">Ångra-alternativ</span><span class="sxs-lookup"><span data-stu-id="1e885-128">Undo Options</span></span>|<span data-ttu-id="1e885-129">Mer information</span><span class="sxs-lookup"><span data-stu-id="1e885-129">Learn more</span></span>|
|---|---|---|
|<span data-ttu-id="1e885-130">Ett e-postmeddelande har dirigerats till en användares skräppostmapp</span><span class="sxs-lookup"><span data-stu-id="1e885-130">An email message was routed to a user's Junk Email folder</span></span>|<span data-ttu-id="1e885-131">- Flytta meddelandet till användarens Borttaget-mapp</span><span class="sxs-lookup"><span data-stu-id="1e885-131">- Move the message to the user's Deleted Items folder</span></span><br/><span data-ttu-id="1e885-132">– Flytta meddelandet till användarens inkorg</span><span class="sxs-lookup"><span data-stu-id="1e885-132">- Move the message to the user's Inbox</span></span><br/><span data-ttu-id="1e885-133">- Ta bort meddelandet</span><span class="sxs-lookup"><span data-stu-id="1e885-133">- Delete the message</span></span>|[<span data-ttu-id="1e885-134">Hitta och undersöka skadlig e-post som levererats i Office 365</span><span class="sxs-lookup"><span data-stu-id="1e885-134">Find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)|
|<span data-ttu-id="1e885-135">Ett e-postmeddelande eller en fil har satts i karantän</span><span class="sxs-lookup"><span data-stu-id="1e885-135">An email message or a file was quarantined</span></span>|<span data-ttu-id="1e885-136">- Släpp e-postmeddelandet eller filen</span><span class="sxs-lookup"><span data-stu-id="1e885-136">- Release the email or file</span></span><br/><span data-ttu-id="1e885-137">- Ta bort e-postmeddelandet eller filen</span><span class="sxs-lookup"><span data-stu-id="1e885-137">- Delete the email or file</span></span>|[<span data-ttu-id="1e885-138">Hantera meddelanden i karantän som administratör</span><span class="sxs-lookup"><span data-stu-id="1e885-138">Manage quarantined messages as an admin</span></span>](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a><span data-ttu-id="1e885-139">Ångra en åtgärd i Åtgärdscenter</span><span class="sxs-lookup"><span data-stu-id="1e885-139">Undo an action in the Action center</span></span>

<span data-ttu-id="1e885-140">I Åtgärdscenter kan du se åtgärder som har vidtagits och eventuellt ångra åtgärden.</span><span class="sxs-lookup"><span data-stu-id="1e885-140">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="1e885-141">Gå till Säkerhetscenter för Microsoft 365 ( <https://security.microsoft.com> ).</span><span class="sxs-lookup"><span data-stu-id="1e885-141">Go to the Microsoft 365 security center (<https://security.microsoft.com>).</span></span>
2. <span data-ttu-id="1e885-142">Välj Åtgärdscenter i **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="1e885-142">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="1e885-143">Välj fliken **Historik** för att visa listan över slutförda åtgärder.</span><span class="sxs-lookup"><span data-stu-id="1e885-143">Select the **History** tab to view the list of completed actions.</span></span>
4. <span data-ttu-id="1e885-144">Markera ett objekt.</span><span class="sxs-lookup"><span data-stu-id="1e885-144">Select an item.</span></span> <span data-ttu-id="1e885-145">Den utfällna rutan öppnas.</span><span class="sxs-lookup"><span data-stu-id="1e885-145">Its flyout pane opens.</span></span>
5. <span data-ttu-id="1e885-146">Välj Ångra i den utfällade **rutan.**</span><span class="sxs-lookup"><span data-stu-id="1e885-146">In the flyout pane, select **Undo**.</span></span> <span data-ttu-id="1e885-147">(Knappen Ångra finns bara för  åtgärder som kan ångras.)</span><span class="sxs-lookup"><span data-stu-id="1e885-147">(Only actions that can be undone will have an **Undo** button.)</span></span>

## <a name="see-also"></a><span data-ttu-id="1e885-148">Se även</span><span class="sxs-lookup"><span data-stu-id="1e885-148">See also</span></span>

- [<span data-ttu-id="1e885-149">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="1e885-149">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="1e885-150">Automatiserade undersökningar i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="1e885-150">Automated investigations in Microsoft Defender for Office 365</span></span>](office-365-air.md)
