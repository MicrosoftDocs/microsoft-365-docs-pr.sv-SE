---
title: Rapport om sårbara enheter – Hantering av hot och säkerhetsrisker
description: En rapport som visar sårbar enhetstrender och aktuell statistik. Målet är att du förstår andan och omfattningen av din enhets exponering.
keywords: Microsoft Defender för slutpunkts-TVm-sårbara enheter, Microsoft Defender för slutpunkt, tvm, minska risken & exponering för sårbarhet, minska risken och risken, övervaka säkerhetskonfiguration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 355561936642b1fa38228bfa07ad59269c48d817
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245486"
---
# <a name="vulnerable-devices-report---threat-and-vulnerability-management"></a><span data-ttu-id="7c567-105">Rapport om sårbara enheter – Hantering av hot och säkerhetsrisker</span><span class="sxs-lookup"><span data-stu-id="7c567-105">Vulnerable devices report - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7c567-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="7c567-106">**Applies to:**</span></span>

- [<span data-ttu-id="7c567-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="7c567-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="7c567-108">Hot och hantering av säkerhetsrisker</span><span class="sxs-lookup"><span data-stu-id="7c567-108">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="7c567-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7c567-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="7c567-110">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="7c567-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7c567-111">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="7c567-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="7c567-112">Rapporten visar diagram och stapeldiagram med sårbar enhetstrender och aktuell statistik.</span><span class="sxs-lookup"><span data-stu-id="7c567-112">The report shows graphs and bar charts with vulnerable device trends and current statistics.</span></span> <span data-ttu-id="7c567-113">Målet är att du förstår andan och omfattningen av din enhets exponering.</span><span class="sxs-lookup"><span data-stu-id="7c567-113">The goal is for you to understand the breath and scope of your device exposure.</span></span>

<span data-ttu-id="7c567-114">Få tillgång till rapporten i Microsoft Defender Säkerhetscenter genom att **gå till Rapporter > sårbara enheter**</span><span class="sxs-lookup"><span data-stu-id="7c567-114">Access the report in the Microsoft Defender Security Center by going to **Reports > Vulnerable devices**</span></span>

<span data-ttu-id="7c567-115">Det finns två kolumner:</span><span class="sxs-lookup"><span data-stu-id="7c567-115">There are two columns:</span></span>

- <span data-ttu-id="7c567-116">Trender (över tid).</span><span class="sxs-lookup"><span data-stu-id="7c567-116">Trends (over time).</span></span> <span data-ttu-id="7c567-117">Kan visa de senaste 30 dagarna, 3 månader, 6 månader eller ett anpassat datumintervall.</span><span class="sxs-lookup"><span data-stu-id="7c567-117">Can show the past 30 days, 3 months, 6 months, or a custom date range.</span></span>
- <span data-ttu-id="7c567-118">I dag (aktuell information)</span><span class="sxs-lookup"><span data-stu-id="7c567-118">Today (current information)</span></span>

<span data-ttu-id="7c567-119">**Filter:** Du kan filtrera data efter allvarlighetsnivåer, sårbarhet, sårbarhet, ålder, operativsystemsplattform, Windows 10 version eller enhetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="7c567-119">**Filter**: You can filter the data by vulnerability severity levels, exploit availability, vulnerability age, operating system platform, Windows 10 version, or device group.</span></span>

<span data-ttu-id="7c567-120">**Öka detaljnivån**: Om det finns en insikt som du vill utforska ytterligare väljer du relevant stapeldiagram för att visa en filtrerad lista med enheter på sidan Enhetslager.</span><span class="sxs-lookup"><span data-stu-id="7c567-120">**Drill down**: If there is an insight you want to explore further, select the relevant bar chart to view a filtered list of devices in the Device inventory page.</span></span> <span data-ttu-id="7c567-121">Därifrån kan du exportera listan.</span><span class="sxs-lookup"><span data-stu-id="7c567-121">From there, you can export the list.</span></span>

## <a name="severity-level-graphs"></a><span data-ttu-id="7c567-122">Diagram för allvarlighetsnivå</span><span class="sxs-lookup"><span data-stu-id="7c567-122">Severity level graphs</span></span>

<span data-ttu-id="7c567-123">Varje enhet räknas bara en gång enligt det mest allvarliga problemet på enheten.</span><span class="sxs-lookup"><span data-stu-id="7c567-123">Each device is counted only once according to the most severe vulnerability found on that device.</span></span>

![Ett diagram över olika allvarlighetsnivåer för enheter och ett diagram som visar nivåer över tid.](images/tvm-report-severity.png)

## <a name="exploit-availability-graphs"></a><span data-ttu-id="7c567-125">Utnyttja tillgänglighetsdiagram</span><span class="sxs-lookup"><span data-stu-id="7c567-125">Exploit availability graphs</span></span>

<span data-ttu-id="7c567-126">Varje enhet räknas bara en gång baserat på den högsta nivån av känd sårbarhet.</span><span class="sxs-lookup"><span data-stu-id="7c567-126">Each device is counted only once based on the highest level of known exploit.</span></span>

![Ett diagram över aktuell enhets sårbarhetstillgänglighet och ett diagram som visar tillgänglighet över tid.](images/tvm-report-exploit-availability.png)

## <a name="vulnerability-age-graphs"></a><span data-ttu-id="7c567-128">Diagram över sårbarhetsåldern</span><span class="sxs-lookup"><span data-stu-id="7c567-128">Vulnerability age graphs</span></span>

<span data-ttu-id="7c567-129">Varje enhet räknas bara en gång under datumet för den äldsta sårbarhetspublikationen.</span><span class="sxs-lookup"><span data-stu-id="7c567-129">Each device is counted only once under the oldest vulnerability publication date.</span></span> <span data-ttu-id="7c567-130">Äldre säkerhetsproblem har större risk att utnyttjas.</span><span class="sxs-lookup"><span data-stu-id="7c567-130">Older vulnerabilities have a higher chance of being exploited.</span></span>

![Ett diagram över den aktuella enhetens sårbarhets ålder och ett diagram som visar ålder över tid.](images/tvm-report-age.png)

## <a name="vulnerable-devices-by-operating-system-platform-graphs"></a><span data-ttu-id="7c567-132">Sårbara enheter efter operativsystemsplattformsgrafer</span><span class="sxs-lookup"><span data-stu-id="7c567-132">Vulnerable devices by operating system platform graphs</span></span>

<span data-ttu-id="7c567-133">Antalet enheter i varje operativsystem som exponeras på grund av säkerhetsproblem med programvara.</span><span class="sxs-lookup"><span data-stu-id="7c567-133">The number of devices on each operating system that are exposed due to software vulnerabilities.</span></span>

![Ett diagram över aktuella sårbara enheter efter operativsystemplattform och ett diagram som visar sårbara enheter för os-plattformar över tid.](images/tvm-report-os.png)

## <a name="vulnerable-devices-by-windows-10-version-graphs"></a><span data-ttu-id="7c567-135">Sårbara enheter som kan Windows 10 av versionsdiagram</span><span class="sxs-lookup"><span data-stu-id="7c567-135">Vulnerable devices by Windows 10 version graphs</span></span>

<span data-ttu-id="7c567-136">Antalet enheter på varje version Windows 10 exponeras på grund av sårbara program eller operativsystem.</span><span class="sxs-lookup"><span data-stu-id="7c567-136">The number of devices on each Windows 10 version that are exposed due to vulnerable applications or OS.</span></span>

![Ett diagram över aktuella sårbara enheter i Windows 10 version, och ett diagram som visar sårbara enheter Windows 10 version över tid.](images/tvm-report-version.png)

## <a name="related-topics"></a><span data-ttu-id="7c567-138">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="7c567-138">Related topics</span></span>

- [<span data-ttu-id="7c567-139">Översikt över hantering av säkerhetsrisker hot och hot</span><span class="sxs-lookup"><span data-stu-id="7c567-139">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="7c567-140">Säkerhetsrekommendationer</span><span class="sxs-lookup"><span data-stu-id="7c567-140">Security recommendations</span></span>](tvm-security-recommendation.md)
