---
title: Använd automatiska undersökningar för att undersöka och åtgärda hot
description: Förstå det automatiska undersökningsflödet i Microsoft Defender för Endpoint.
keywords: automatiserad, undersökning, identifiering, defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.date: 02/02/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.custom: AIR
ms.openlocfilehash: 7143a360fb7093f94c6f66373587e1c895dd3213
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51200311"
---
# <a name="overview-of-automated-investigations"></a><span data-ttu-id="594df-104">Översikt över automatiserade undersökningar</span><span class="sxs-lookup"><span data-stu-id="594df-104">Overview of automated investigations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="594df-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="594df-105">**Applies to:**</span></span>
- [<span data-ttu-id="594df-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="594df-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="594df-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="594df-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="594df-108">Vill du se hur det fungerar?</span><span class="sxs-lookup"><span data-stu-id="594df-108">Want to see how it works?</span></span> <span data-ttu-id="594df-109">Titta på följande video:</span><span class="sxs-lookup"><span data-stu-id="594df-109">Watch the following video:</span></span> <br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bOeh]

<span data-ttu-id="594df-110">Tekniken i automatiserad undersökning använder olika kontrollalgoritmer och baseras på processer som används av säkerhetsanalytiker.</span><span class="sxs-lookup"><span data-stu-id="594df-110">The technology in automated investigation uses various inspection algorithms and is based on processes that are used by security analysts.</span></span> <span data-ttu-id="594df-111">AIR-funktionerna är utformade för att undersöka aviseringar och vidta omedelbar åtgärd för att lösa överträdelser.</span><span class="sxs-lookup"><span data-stu-id="594df-111">AIR capabilities are designed to examine alerts and take immediate action to resolve breaches.</span></span> <span data-ttu-id="594df-112">AIR-funktioner sänker meddelandevolymen avsevärt, vilket gör att säkerhetsåtgärder kan fokusera på mer avancerade hot och andra viktiga initiativ.</span><span class="sxs-lookup"><span data-stu-id="594df-112">AIR capabilities significantly reduce alert volume, allowing security operations to focus on more sophisticated threats and other high-value initiatives.</span></span> <span data-ttu-id="594df-113">Alla åtgärdsåtgärder, oavsett om de är väntande eller slutförda, spåras i [Åtgärdscenter.](auto-investigation-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="594df-113">All remediation actions, whether pending or completed, are tracked in the [Action center](auto-investigation-action-center.md).</span></span> <span data-ttu-id="594df-114">I Åtgärdscenter godkänns väntande åtgärder (eller avvisas) och slutförda åtgärder kan ångras om det behövs.</span><span class="sxs-lookup"><span data-stu-id="594df-114">In the Action center, pending actions are approved (or rejected), and completed actions can be undone if needed.</span></span>

<span data-ttu-id="594df-115">Den här artikeln innehåller en översikt över AIR med länkar till nästa steg och ytterligare resurser.</span><span class="sxs-lookup"><span data-stu-id="594df-115">This article provides an overview of AIR and includes links to next steps and additional resources.</span></span>

> [!TIP]
> <span data-ttu-id="594df-116">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="594df-116">Want to experience Microsoft Defender for Endpoint?</span></span> <span data-ttu-id="594df-117">[Registrera dig för en kostnadsfri utvärderingsversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automated-investigations-abovefoldlink).</span><span class="sxs-lookup"><span data-stu-id="594df-117">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automated-investigations-abovefoldlink).</span></span>

## <a name="how-the-automated-investigation-starts"></a><span data-ttu-id="594df-118">Hur den automatiska undersökningen startar</span><span class="sxs-lookup"><span data-stu-id="594df-118">How the automated investigation starts</span></span>

<span data-ttu-id="594df-119">En automatiserad undersökning kan starta när en avisering utlöses eller när en säkerhetsoperator initierar undersökningen.</span><span class="sxs-lookup"><span data-stu-id="594df-119">An automated investigation can start when an alert is triggered or when a security operator initiates the investigation.</span></span>

|<span data-ttu-id="594df-120">Situation</span><span class="sxs-lookup"><span data-stu-id="594df-120">Situation</span></span>  |<span data-ttu-id="594df-121">Vad som händer</span><span class="sxs-lookup"><span data-stu-id="594df-121">What happens</span></span>  |
|---------|---------|
|<span data-ttu-id="594df-122">En avisering utlöses</span><span class="sxs-lookup"><span data-stu-id="594df-122">An alert is triggered</span></span>     | <span data-ttu-id="594df-123">I allmänhet startar en automatiserad undersökning när [en](review-alerts.md) avisering utlöses och [en incident](view-incidents-queue.md) skapas.</span><span class="sxs-lookup"><span data-stu-id="594df-123">In general, an automated investigation starts when an [alert](review-alerts.md) is triggered, and an [incident](view-incidents-queue.md) is created.</span></span> <span data-ttu-id="594df-124">Anta till exempel att en skadlig fil finns på en enhet.</span><span class="sxs-lookup"><span data-stu-id="594df-124">For example, suppose a malicious file resides on a device.</span></span> <span data-ttu-id="594df-125">När filen identifieras utlöses en avisering och ett incident skapas.</span><span class="sxs-lookup"><span data-stu-id="594df-125">When that file is detected, an alert is triggered, and incident is created.</span></span> <span data-ttu-id="594df-126">En automatiserad undersökningsprocess påbörjas på enheten.</span><span class="sxs-lookup"><span data-stu-id="594df-126">An automated investigation process begins on the device.</span></span> <span data-ttu-id="594df-127">När andra aviseringar genereras på grund av samma fil på andra enheter läggs de till i den associerade incidenten och i den automatiska undersökningen.</span><span class="sxs-lookup"><span data-stu-id="594df-127">As other alerts are generated because of the same file on other devices, they are added to the associated incident and to the automated investigation.</span></span>         |
|<span data-ttu-id="594df-128">En undersökning startas manuellt</span><span class="sxs-lookup"><span data-stu-id="594df-128">An investigation is started manually</span></span>     | <span data-ttu-id="594df-129">En automatiserad undersökning kan startas manuellt av säkerhetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="594df-129">An automated investigation can be started manually by your security operations team.</span></span> <span data-ttu-id="594df-130">Anta till exempel att en säkerhetsoperatör granskar en lista över enheter och märker att en enhet har hög risknivå.</span><span class="sxs-lookup"><span data-stu-id="594df-130">For example, suppose a security operator is reviewing a list of devices and notices that a device has a high risk level.</span></span> <span data-ttu-id="594df-131">Säkerhetsoperatorn kan välja enheten i listan för att öppna dess utfällning och sedan välja **Initiera automatisk undersökning.**</span><span class="sxs-lookup"><span data-stu-id="594df-131">The security operator can select the device in the list to open its flyout, and then select **Initiate Automated Investigation**.</span></span> |

## <a name="how-an-automated-investigation-expands-its-scope"></a><span data-ttu-id="594df-132">Så här utökar en automatiserad undersökning dess omfattning</span><span class="sxs-lookup"><span data-stu-id="594df-132">How an automated investigation expands its scope</span></span>

<span data-ttu-id="594df-133">Medan en undersökning körs läggs alla andra aviseringar som genereras från enheten till i en pågående automatiserad undersökning tills undersökningen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="594df-133">While an investigation is running, any other alerts generated from the device are added to an ongoing automated investigation until that investigation is completed.</span></span> <span data-ttu-id="594df-134">Om samma hot visas på andra enheter läggs dessa enheter dessutom till i undersökningen.</span><span class="sxs-lookup"><span data-stu-id="594df-134">In addition, if the same threat is seen on other devices, those devices are added to the investigation.</span></span>

<span data-ttu-id="594df-135">Om en okritisk enhet visas på en annan enhet utökas processen för automatisk undersökning så att den omfattar den enheten, och en allmän säkerhetsspelbok startar på den enheten.</span><span class="sxs-lookup"><span data-stu-id="594df-135">If an incriminated entity is seen in another device, the automated investigation process expands its scope to include that device, and a general security playbook starts on that device.</span></span> <span data-ttu-id="594df-136">Om 10 eller fler enheter hittas under den här expansionsprocessen från samma entitet kräver den expanderingsåtgärden ett godkännande och visas på fliken **Väntande** åtgärder.</span><span class="sxs-lookup"><span data-stu-id="594df-136">If 10 or more devices are found during this expansion process from the same entity, then that expansion action requires an approval, and is visible on the **Pending actions** tab.</span></span>

## <a name="how-threats-are-remediated"></a><span data-ttu-id="594df-137">Hur hot åtgärdas</span><span class="sxs-lookup"><span data-stu-id="594df-137">How threats are remediated</span></span>

<span data-ttu-id="594df-138">När aviseringar utlöses och en automatiserad undersökning körs genereras en bedömning för varje bevis som undersöks.</span><span class="sxs-lookup"><span data-stu-id="594df-138">As alerts are triggered, and an automated investigation runs, a verdict is generated for each piece of evidence investigated.</span></span> <span data-ttu-id="594df-139">Bedömningarna kan vara</span><span class="sxs-lookup"><span data-stu-id="594df-139">Verdicts can be</span></span> 
- <span data-ttu-id="594df-140">*Skadlig*;</span><span class="sxs-lookup"><span data-stu-id="594df-140">*Malicious*;</span></span>
- <span data-ttu-id="594df-141">*Misstänkt –* om du har en misstänkt e eller</span><span class="sxs-lookup"><span data-stu-id="594df-141">*Suspicious*; or</span></span> 
- <span data-ttu-id="594df-142">*Inga hot hittades*.</span><span class="sxs-lookup"><span data-stu-id="594df-142">*No threats found*.</span></span> 

<span data-ttu-id="594df-143">Eftersom bedömningarna nås kan automatiska undersökningar resultera i en eller flera åtgärder.</span><span class="sxs-lookup"><span data-stu-id="594df-143">As verdicts are reached, automated investigations can result in one or more remediation actions.</span></span> <span data-ttu-id="594df-144">Exempel på åtgärder är att skicka en fil till karantän, stoppa en tjänst, ta bort en schemalagd aktivitet och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="594df-144">Examples of remediation actions include sending a file to quarantine, stopping a service, removing a scheduled task, and more.</span></span> <span data-ttu-id="594df-145">Mer information finns [i Åtgärder .](manage-auto-investigation.md#remediation-actions)</span><span class="sxs-lookup"><span data-stu-id="594df-145">To learn more, see [Remediation actions](manage-auto-investigation.md#remediation-actions).</span></span>  

<span data-ttu-id="594df-146">Beroende på [hur automatiseringsnivån](automation-levels.md) är inställd för organisationen, samt andra säkerhetsinställningar, kan åtgärder vidtas automatiskt eller bara vid godkännande från säkerhetsteamet.</span><span class="sxs-lookup"><span data-stu-id="594df-146">Depending on the [level of automation](automation-levels.md) set for your organization, as well as other security settings, remediation actions can occur automatically or only upon approval by your security operations team.</span></span> <span data-ttu-id="594df-147">Ytterligare säkerhetsinställningar som kan påverka automatisk åtgärd är bland [annat skydd mot potentiellt oönskade program](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) (PUA).</span><span class="sxs-lookup"><span data-stu-id="594df-147">Additional security settings that can affect automatic remediation include [protection from potentially unwanted applications](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) (PUA).</span></span> 

<span data-ttu-id="594df-148">Alla åtgärdsåtgärder, oavsett om de är väntande eller slutförda, spåras i [Åtgärdscenter.](auto-investigation-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="594df-148">All remediation actions, whether pending or completed, are tracked in the [Action center](auto-investigation-action-center.md).</span></span> <span data-ttu-id="594df-149">Om det behövs kan säkerhetsåtgärdsteamet ångra en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="594df-149">If necessary, your security operations team can undo a remediation action.</span></span> <span data-ttu-id="594df-150">Mer information finns i [Granska och godkänna åtgärdsåtgärder efter en automatiserad undersökning.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-auto-investigation)</span><span class="sxs-lookup"><span data-stu-id="594df-150">To learn more, see [Review and approve remediation actions following an automated investigation](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-auto-investigation).</span></span>

> [!TIP]
> <span data-ttu-id="594df-151">Titta på den nya sidan för enhetlig undersökning i Säkerhetscenter för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="594df-151">Check out the new, unified investigation page in the Microsoft 365 security center.</span></span> <span data-ttu-id="594df-152">Mer information finns i [(NYTT!) Sida för enhetlig undersökning](/microsoft-365/security/defender/m365d-autoir-results#new-unified-investigation-page).</span><span class="sxs-lookup"><span data-stu-id="594df-152">To learn more, see [(NEW!) Unified investigation page](/microsoft-365/security/defender/m365d-autoir-results#new-unified-investigation-page).</span></span>


## <a name="requirements-for-air"></a><span data-ttu-id="594df-153">Krav för AIR</span><span class="sxs-lookup"><span data-stu-id="594df-153">Requirements for AIR</span></span>

<span data-ttu-id="594df-154">Din organisation måste ha Defender för Slutpunkt (se [Minimikraven för Microsoft Defender för Slutpunkt](minimum-requirements.md)).</span><span class="sxs-lookup"><span data-stu-id="594df-154">Your organization must have Defender for Endpoint (see [Minimum requirements for Microsoft Defender for Endpoint](minimum-requirements.md)).</span></span>

<span data-ttu-id="594df-155">För närvarande stöder AIR endast följande OS-versioner:</span><span class="sxs-lookup"><span data-stu-id="594df-155">Currently, AIR only supports the following OS versions:</span></span>
- <span data-ttu-id="594df-156">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="594df-156">Windows Server 2019</span></span>
- <span data-ttu-id="594df-157">Windows 10, version 1709 (OS Build 16299.1085 med [KB4493441)](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441)eller senare</span><span class="sxs-lookup"><span data-stu-id="594df-157">Windows 10, version 1709 (OS Build 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441)) or later</span></span>
- <span data-ttu-id="594df-158">Windows 10, version 1803 (OS Build 17134.704 med [KB4493464)](https://support.microsoft.com/help/4493464/windows-10-update-kb4493464)eller senare</span><span class="sxs-lookup"><span data-stu-id="594df-158">Windows 10, version 1803 (OS Build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464/windows-10-update-kb4493464)) or later</span></span>
- <span data-ttu-id="594df-159">Windows 10, version [1803](https://docs.microsoft.com/windows/release-information/status-windows-10-1809-and-windows-server-2019) eller senare</span><span class="sxs-lookup"><span data-stu-id="594df-159">Windows 10, version [1803](https://docs.microsoft.com/windows/release-information/status-windows-10-1809-and-windows-server-2019) or later</span></span>

## <a name="next-steps"></a><span data-ttu-id="594df-160">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="594df-160">Next steps</span></span>

- [<span data-ttu-id="594df-161">Läs mer om automatiseringsnivåer</span><span class="sxs-lookup"><span data-stu-id="594df-161">Learn more about automation levels</span></span>](automation-levels.md)
- [<span data-ttu-id="594df-162">Se den interaktiva guiden: Undersöka och åtgärda hot med Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="594df-162">See the interactive guide: Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
- [<span data-ttu-id="594df-163">Konfigurera funktioner för automatisk undersökning och åtgärder i Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="594df-163">Configure automated investigation and remediation capabilities in Microsoft Defender for Endpoint</span></span>](configure-automated-investigations-remediation.md)

## <a name="see-also"></a><span data-ttu-id="594df-164">Se även</span><span class="sxs-lookup"><span data-stu-id="594df-164">See also</span></span>

- [<span data-ttu-id="594df-165">PUA-skydd</span><span class="sxs-lookup"><span data-stu-id="594df-165">PUA protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [<span data-ttu-id="594df-166">Automatiserad undersökning och svar i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="594df-166">Automated investigation and response in Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
- [<span data-ttu-id="594df-167">Automatiserad undersökning och svar i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="594df-167">Automated investigation and response in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/mtp-autoir)
