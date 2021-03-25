---
title: Skapa indikatorer
ms.reviewer: ''
description: Skapa indikatorer för en filhash, IP-adress, URL:er eller domäner som definierar identifiering, skydd och undantag för enheter.
keywords: hantera, tillåtna, blockerade, blockera, rensa, skadliga, filshashar, ip-adress, url:er, domän
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a04f3be1f13fb57cd76cda7115d014f2ba3aa8d6
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198843"
---
# <a name="create-indicators"></a><span data-ttu-id="a5ccd-104">Skapa indikatorer</span><span class="sxs-lookup"><span data-stu-id="a5ccd-104">Create indicators</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a5ccd-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="a5ccd-105">**Applies to:**</span></span>
- [<span data-ttu-id="a5ccd-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="a5ccd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a5ccd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a5ccd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> [!TIP]
> <span data-ttu-id="a5ccd-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="a5ccd-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a5ccd-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="a5ccd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="a5ccd-110">Indikator på kompromettering (IoCs) är en viktig funktion i varje lösning för slutpunktsskydd.</span><span class="sxs-lookup"><span data-stu-id="a5ccd-110">Indicator of compromise (IoCs) matching is an essential feature in every endpoint protection solution.</span></span> <span data-ttu-id="a5ccd-111">Den här funktionen ger SekOps möjlighet att ange en lista över indikatorer för identifiering och blockering (skydd och svar).</span><span class="sxs-lookup"><span data-stu-id="a5ccd-111">This capability gives SecOps the ability to set a list of indicators for detection and for blocking (prevention and response).</span></span>

<span data-ttu-id="a5ccd-112">Skapa indikatorer som definierar identifiering, skydd och undantag för enheter.</span><span class="sxs-lookup"><span data-stu-id="a5ccd-112">Create indicators that define the detection, prevention, and exclusion of entities.</span></span> <span data-ttu-id="a5ccd-113">Du kan definiera vilken åtgärd som ska vidtas samt varaktigheten för när åtgärden ska tillämpas samt omfattningen av enhetsgruppen som den ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="a5ccd-113">You can define the action to be taken as well as the duration for when to apply the action as well as the scope of the device group to apply it to.</span></span>

<span data-ttu-id="a5ccd-114">Källor som stöds för närvarande är molnidentifieringsmotorn i Defender för Endpoint, den automatiska undersöknings- och åtgärdsmotorn och slutpunktsskyddsmotorn (Microsoft Defender Antivirus).</span><span class="sxs-lookup"><span data-stu-id="a5ccd-114">Currently supported sources are the cloud detection engine of Defender for Endpoint, the automated investigation and remediation engine, and the endpoint prevention engine (Microsoft Defender Antivirus).</span></span>

<span data-ttu-id="a5ccd-115">**Motor för molnidentifiering**</span><span class="sxs-lookup"><span data-stu-id="a5ccd-115">**Cloud detection engine**</span></span><br>
<span data-ttu-id="a5ccd-116">Molnidentifieringsmotorn i Defender för Endpoint söker regelbundet igenom insamlade data och försöker matcha de indikatorer du anger.</span><span class="sxs-lookup"><span data-stu-id="a5ccd-116">The cloud detection engine of Defender for Endpoint regularly scans collected data and tries to match the indicators you set.</span></span> <span data-ttu-id="a5ccd-117">När det finns en matchning vidtas åtgärden enligt de inställningar du har angett för IoC.</span><span class="sxs-lookup"><span data-stu-id="a5ccd-117">When there is a match, action will be taken according to the settings you specified for the IoC.</span></span>

<span data-ttu-id="a5ccd-118">**Slutpunktsskyddsmotor**</span><span class="sxs-lookup"><span data-stu-id="a5ccd-118">**Endpoint prevention engine**</span></span><br>
<span data-ttu-id="a5ccd-119">Samma lista över indikatorer används av agenten för förebyggande åtgärder.</span><span class="sxs-lookup"><span data-stu-id="a5ccd-119">The same list of indicators is honored by the prevention agent.</span></span> <span data-ttu-id="a5ccd-120">Om Microsoft Defender AV är den primära av-konfigurerade av-appen kommer de matchade indikatorerna att hanteras i enlighet med inställningarna.</span><span class="sxs-lookup"><span data-stu-id="a5ccd-120">Meaning, if Microsoft Defender AV is the primary AV configured, the matched indicators will be treated according to the settings.</span></span> <span data-ttu-id="a5ccd-121">Om åtgärden till exempel är "Avisering och Blockera" förhindras filkörningar (blockering och åtgärd) av Microsoft Defender AV, och en motsvarande avisering höjs.</span><span class="sxs-lookup"><span data-stu-id="a5ccd-121">For example, if the action is "Alert and Block", Microsoft Defender AV will prevent file executions (block and remediate) and a corresponding alert will be raised.</span></span> <span data-ttu-id="a5ccd-122">Å andra sidan, om åtgärden är inställd på "Tillåt" kommer Microsoft Defender AV inte att identifiera eller blockera filen från att köras.</span><span class="sxs-lookup"><span data-stu-id="a5ccd-122">On the other hand, if the Action is set to "Allow", Microsoft Defender AV will not detect nor block the file from being run.</span></span>

<span data-ttu-id="a5ccd-123">**Motor för automatisk undersökning och åtgärder**</span><span class="sxs-lookup"><span data-stu-id="a5ccd-123">**Automated investigation and remediation engine**</span></span><BR>
<span data-ttu-id="a5ccd-124">Automatisk undersökning och åtgärd fungerar på samma sätt.</span><span class="sxs-lookup"><span data-stu-id="a5ccd-124">The automated investigation and remediation behave the same.</span></span> <span data-ttu-id="a5ccd-125">Om en indikator är inställd på "Tillåt" ignorerar automatiserad undersökning och åtgärd en "dålig" bedömning för den.</span><span class="sxs-lookup"><span data-stu-id="a5ccd-125">If an indicator is set to "Allow", Automated investigation and remediation will ignore a "bad" verdict for it.</span></span> <span data-ttu-id="a5ccd-126">Om denna anges till "Block" behandlas automatisk undersökning och åtgärd som "dåligt".</span><span class="sxs-lookup"><span data-stu-id="a5ccd-126">If set to "Block", Automated investigation and remediation will treat it as "bad".</span></span>


<span data-ttu-id="a5ccd-127">De aktuella åtgärderna som stöds är:</span><span class="sxs-lookup"><span data-stu-id="a5ccd-127">The current supported actions are:</span></span>
- <span data-ttu-id="a5ccd-128">Tillåt</span><span class="sxs-lookup"><span data-stu-id="a5ccd-128">Allow</span></span>
- <span data-ttu-id="a5ccd-129">Endast avisering</span><span class="sxs-lookup"><span data-stu-id="a5ccd-129">Alert only</span></span>
- <span data-ttu-id="a5ccd-130">Avisering och blockering</span><span class="sxs-lookup"><span data-stu-id="a5ccd-130">Alert and block</span></span>


<span data-ttu-id="a5ccd-131">Du kan skapa en indikator för:</span><span class="sxs-lookup"><span data-stu-id="a5ccd-131">You can create an indicator for:</span></span>
- [<span data-ttu-id="a5ccd-132">Filer</span><span class="sxs-lookup"><span data-stu-id="a5ccd-132">Files</span></span>](indicator-file.md)
- [<span data-ttu-id="a5ccd-133">IP-adresser, URL:er/domäner</span><span class="sxs-lookup"><span data-stu-id="a5ccd-133">IP addresses, URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="a5ccd-134">Certifikat</span><span class="sxs-lookup"><span data-stu-id="a5ccd-134">Certificates</span></span>](indicator-certificates.md)


> [!NOTE]
> <span data-ttu-id="a5ccd-135">Det finns en gräns på 15 000 indikatorer per klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="a5ccd-135">There is a limit of 15,000 indicators per tenant.</span></span> <span data-ttu-id="a5ccd-136">Fil- och certifikatindikatorer blockerar inte [undantag som definierats för Microsoft Defender Antivirus.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="a5ccd-136">File and certificate indicators do not block [exclusions defined for Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus).</span></span> <span data-ttu-id="a5ccd-137">Indikatorer stöds inte i Microsoft Defender Antivirus är i passiv form.</span><span class="sxs-lookup"><span data-stu-id="a5ccd-137">Indicators are not supported in Microsoft Defender Antivirus is in passive mode.</span></span> 


## <a name="related-topics"></a><span data-ttu-id="a5ccd-138">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="a5ccd-138">Related topics</span></span>

- [<span data-ttu-id="a5ccd-139">Skapa sammanhangsberoende IoC</span><span class="sxs-lookup"><span data-stu-id="a5ccd-139">Create contextual IoC</span></span>](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
- [<span data-ttu-id="a5ccd-140">Använda API:t För slutpunktsindikatorer i Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a5ccd-140">Use the Microsoft Defender for Endpoint indicators API</span></span>](ti-indicator.md)
- [<span data-ttu-id="a5ccd-141">Använda partnerintegrerade lösningar</span><span class="sxs-lookup"><span data-stu-id="a5ccd-141">Use partner integrated solutions</span></span>](partner-applications.md)
