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
ms.openlocfilehash: fb87f36c5289d622df2615046c5bb2fd8fad9543
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842248"
---
# <a name="create-indicators"></a><span data-ttu-id="bbd26-104">Skapa indikatorer</span><span class="sxs-lookup"><span data-stu-id="bbd26-104">Create indicators</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bbd26-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="bbd26-105">**Applies to:**</span></span>
- [<span data-ttu-id="bbd26-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="bbd26-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bbd26-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bbd26-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> [!TIP]
> <span data-ttu-id="bbd26-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="bbd26-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bbd26-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="bbd26-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="bbd26-110">Indikator på kompromettering (IoCs) är en viktig funktion i varje lösning för slutpunktsskydd.</span><span class="sxs-lookup"><span data-stu-id="bbd26-110">Indicator of compromise (IoCs) matching is an essential feature in every endpoint protection solution.</span></span> <span data-ttu-id="bbd26-111">Den här funktionen ger SekOps möjlighet att ange en lista över indikatorer för identifiering och blockering (skydd och svar).</span><span class="sxs-lookup"><span data-stu-id="bbd26-111">This capability gives SecOps the ability to set a list of indicators for detection and for blocking (prevention and response).</span></span>

<span data-ttu-id="bbd26-112">Skapa indikatorer som definierar identifiering, skydd och undantag för enheter.</span><span class="sxs-lookup"><span data-stu-id="bbd26-112">Create indicators that define the detection, prevention, and exclusion of entities.</span></span> <span data-ttu-id="bbd26-113">Du kan definiera vilken åtgärd som ska vidtas samt varaktigheten för när åtgärden ska tillämpas samt omfattningen av enhetsgruppen som den ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="bbd26-113">You can define the action to be taken as well as the duration for when to apply the action as well as the scope of the device group to apply it to.</span></span>

<span data-ttu-id="bbd26-114">Källor som stöds för närvarande är molnidentifieringsmotorn i Defender för Endpoint, den automatiska undersöknings- och åtgärdsmotorn och slutpunktsskyddsmotorn (Microsoft Defender Antivirus).</span><span class="sxs-lookup"><span data-stu-id="bbd26-114">Currently supported sources are the cloud detection engine of Defender for Endpoint, the automated investigation and remediation engine, and the endpoint prevention engine (Microsoft Defender Antivirus).</span></span>

<span data-ttu-id="bbd26-115">**Motor för molnidentifiering**</span><span class="sxs-lookup"><span data-stu-id="bbd26-115">**Cloud detection engine**</span></span><br>
<span data-ttu-id="bbd26-116">Molnidentifieringsmotorn i Defender för Endpoint söker regelbundet igenom insamlade data och försöker matcha de indikatorer du anger.</span><span class="sxs-lookup"><span data-stu-id="bbd26-116">The cloud detection engine of Defender for Endpoint regularly scans collected data and tries to match the indicators you set.</span></span> <span data-ttu-id="bbd26-117">När det finns en matchning vidtas åtgärden enligt de inställningar du har angett för IoC.</span><span class="sxs-lookup"><span data-stu-id="bbd26-117">When there is a match, action will be taken according to the settings you specified for the IoC.</span></span>

<span data-ttu-id="bbd26-118">**Slutpunktsskyddsmotor**</span><span class="sxs-lookup"><span data-stu-id="bbd26-118">**Endpoint prevention engine**</span></span><br>
<span data-ttu-id="bbd26-119">Samma lista över indikatorer används av agenten för förebyggande åtgärder.</span><span class="sxs-lookup"><span data-stu-id="bbd26-119">The same list of indicators is honored by the prevention agent.</span></span> <span data-ttu-id="bbd26-120">Om Microsoft Defender AV är den primära av-konfigurerade av-appen kommer de matchade indikatorerna att hanteras i enlighet med inställningarna.</span><span class="sxs-lookup"><span data-stu-id="bbd26-120">Meaning, if Microsoft Defender AV is the primary AV configured, the matched indicators will be treated according to the settings.</span></span> <span data-ttu-id="bbd26-121">Om åtgärden till exempel är "Avisering och Blockera" förhindras filkörningar (blockering och åtgärd) av Microsoft Defender AV, och en motsvarande avisering höjs.</span><span class="sxs-lookup"><span data-stu-id="bbd26-121">For example, if the action is "Alert and Block", Microsoft Defender AV will prevent file executions (block and remediate) and a corresponding alert will be raised.</span></span> <span data-ttu-id="bbd26-122">Å andra sidan, om åtgärden är inställd på "Tillåt" kommer Microsoft Defender AV inte att identifiera eller blockera filen från att köras.</span><span class="sxs-lookup"><span data-stu-id="bbd26-122">On the other hand, if the Action is set to "Allow", Microsoft Defender AV will not detect nor block the file from being run.</span></span>

<span data-ttu-id="bbd26-123">**Motor för automatisk undersökning och åtgärder**</span><span class="sxs-lookup"><span data-stu-id="bbd26-123">**Automated investigation and remediation engine**</span></span><BR>
<span data-ttu-id="bbd26-124">Automatisk undersökning och åtgärd fungerar på samma sätt.</span><span class="sxs-lookup"><span data-stu-id="bbd26-124">The automated investigation and remediation behave the same.</span></span> <span data-ttu-id="bbd26-125">Om en indikator är inställd på "Tillåt" ignorerar automatiserad undersökning och åtgärd en "dålig" bedömning för den.</span><span class="sxs-lookup"><span data-stu-id="bbd26-125">If an indicator is set to "Allow", Automated investigation and remediation will ignore a "bad" verdict for it.</span></span> <span data-ttu-id="bbd26-126">Om denna anges till "Block" behandlas automatisk undersökning och åtgärd som "dåligt".</span><span class="sxs-lookup"><span data-stu-id="bbd26-126">If set to "Block", Automated investigation and remediation will treat it as "bad".</span></span>

> [!NOTE]
> <span data-ttu-id="bbd26-127">Inställningen EnableFileHashComputation beräknar filhash för certifikatet och fil-IoC vid filsökningar.</span><span class="sxs-lookup"><span data-stu-id="bbd26-127">The EnableFileHashComputation setting computes the file hash for the cert and file IoC during file scans.</span></span> <span data-ttu-id="bbd26-128">Den stöder IoC-tillämpning av hashtaggar och certifikat tillhör betrodda program.</span><span class="sxs-lookup"><span data-stu-id="bbd26-128">It supports IoC enforcement of hashes and certs belong to trusted applications.</span></span> <span data-ttu-id="bbd26-129">Den aktiveras samtidigt som den inaktiveras med inställningen tillåts eller blockeras.</span><span class="sxs-lookup"><span data-stu-id="bbd26-129">It will be concurrently enabled and disabled with the allow or block file setting.</span></span> <span data-ttu-id="bbd26-130">EnableFileHashComputation aktiveras manuellt via grupprincip och är inaktiverat som standard.</span><span class="sxs-lookup"><span data-stu-id="bbd26-130">EnableFileHashComputation is enabled manually through Group Policy, and is disabled by default.</span></span>


<span data-ttu-id="bbd26-131">De aktuella åtgärderna som stöds är:</span><span class="sxs-lookup"><span data-stu-id="bbd26-131">The current supported actions are:</span></span>
- <span data-ttu-id="bbd26-132">Tillåt</span><span class="sxs-lookup"><span data-stu-id="bbd26-132">Allow</span></span>
- <span data-ttu-id="bbd26-133">Endast avisering</span><span class="sxs-lookup"><span data-stu-id="bbd26-133">Alert only</span></span>
- <span data-ttu-id="bbd26-134">Avisering och blockering</span><span class="sxs-lookup"><span data-stu-id="bbd26-134">Alert and block</span></span>


<span data-ttu-id="bbd26-135">Du kan skapa en indikator för:</span><span class="sxs-lookup"><span data-stu-id="bbd26-135">You can create an indicator for:</span></span>
- [<span data-ttu-id="bbd26-136">Filer</span><span class="sxs-lookup"><span data-stu-id="bbd26-136">Files</span></span>](indicator-file.md)
- [<span data-ttu-id="bbd26-137">IP-adresser, URL:er/domäner</span><span class="sxs-lookup"><span data-stu-id="bbd26-137">IP addresses, URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="bbd26-138">Certifikat</span><span class="sxs-lookup"><span data-stu-id="bbd26-138">Certificates</span></span>](indicator-certificates.md)


> [!NOTE]
> <span data-ttu-id="bbd26-139">Det finns en gräns på 15 000 indikatorer per klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="bbd26-139">There is a limit of 15,000 indicators per tenant.</span></span> <span data-ttu-id="bbd26-140">Arkiv- och certifikatindikatorer blockerar inte [undantag som definierats för Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="bbd26-140">File and certificate indicators do not block [exclusions defined for Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus).</span></span> <span data-ttu-id="bbd26-141">Indikatorer stöds inte i Microsoft Defender Antivirus när det är i passivt läge.</span><span class="sxs-lookup"><span data-stu-id="bbd26-141">Indicators are not supported in Microsoft Defender Antivirus when it is in passive mode.</span></span> 


## <a name="related-topics"></a><span data-ttu-id="bbd26-142">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="bbd26-142">Related topics</span></span>

- [<span data-ttu-id="bbd26-143">Skapa sammanhangsberoende IoC</span><span class="sxs-lookup"><span data-stu-id="bbd26-143">Create contextual IoC</span></span>](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
- [<span data-ttu-id="bbd26-144">Använda API:t För slutpunktsindikatorer i Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="bbd26-144">Use the Microsoft Defender for Endpoint indicators API</span></span>](ti-indicator.md)
- [<span data-ttu-id="bbd26-145">Använda partnerintegrerade lösningar</span><span class="sxs-lookup"><span data-stu-id="bbd26-145">Use partner integrated solutions</span></span>](partner-applications.md)
