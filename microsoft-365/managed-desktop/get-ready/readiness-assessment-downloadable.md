---
title: Nedladdningsbar beredskapsbedömning
description: Kontrollerar enhets- och nätverksinställningar, inklusive obligatoriska slutpunkter
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2080b2fc924320f38d9972c82c0425fa1d8026e7
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/21/2021
ms.locfileid: "49922026"
---
# <a name="downloadable-readiness-assessment-checker"></a><span data-ttu-id="faf1f-104">Nedladdningsbar beredskapsbedömning</span><span class="sxs-lookup"><span data-stu-id="faf1f-104">Downloadable readiness assessment checker</span></span>

<span data-ttu-id="faf1f-105">För att fungera bra med Microsoft Managed Desktop måste enheter uppfylla vissa krav för maskinvara och inställningar.</span><span class="sxs-lookup"><span data-stu-id="faf1f-105">To work well with Microsoft Managed Desktop, devices must meet certain requirements for hardware and settings.</span></span> <span data-ttu-id="faf1f-106">Varje enhet måste också kunna nå viktiga slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="faf1f-106">Also, each device must be able to reach key endpoints.</span></span> <span data-ttu-id="faf1f-107">Ladda ned och kör det här verktyget för att hämta en HTML-rapport, visa resultat och sedan vidta åtgärder.</span><span class="sxs-lookup"><span data-stu-id="faf1f-107">Download and run this tool to obtain an HTML report, view results, and then take action.</span></span> <span data-ttu-id="faf1f-108">Du måste ladda ned verktyget och stödfilerna och sedan köra det manuellt på varje enhet som du vill registrera i Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="faf1f-108">You will need to download the tool and supporting files, and then run it manually on each device you want to enroll in Microsoft Managed Desktop.</span></span>

<span data-ttu-id="faf1f-109">För varje kontroll rapporterar verktyget ett av tre möjliga resultat:</span><span class="sxs-lookup"><span data-stu-id="faf1f-109">For each check, the tool will report one of three possible results:</span></span>


|<span data-ttu-id="faf1f-110">Resultat</span><span class="sxs-lookup"><span data-stu-id="faf1f-110">Result</span></span>  |<span data-ttu-id="faf1f-111">Betydelse</span><span class="sxs-lookup"><span data-stu-id="faf1f-111">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="faf1f-112">Klar</span><span class="sxs-lookup"><span data-stu-id="faf1f-112">Ready</span></span>     | <span data-ttu-id="faf1f-113">Ingen åtgärd krävs innan du slutför registreringen.</span><span class="sxs-lookup"><span data-stu-id="faf1f-113">No action is required before you complete enrollment.</span></span>        |
|<span data-ttu-id="faf1f-114">Rådgivning</span><span class="sxs-lookup"><span data-stu-id="faf1f-114">Advisory</span></span>    | <span data-ttu-id="faf1f-115">Följ stegen i verktyget för att få den bästa upplevelsen med registrering och för användare.</span><span class="sxs-lookup"><span data-stu-id="faf1f-115">Follow the steps in the tool for the best experience with enrollment and for users.</span></span> <span data-ttu-id="faf1f-116">Du *kan* slutföra registreringen, men du måste åtgärda problemen innan du distribuerar din första enhet.</span><span class="sxs-lookup"><span data-stu-id="faf1f-116">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="faf1f-117">Inte klar</span><span class="sxs-lookup"><span data-stu-id="faf1f-117">Not ready</span></span> | <span data-ttu-id="faf1f-118">*Registrering misslyckas om* du inte åtgärdar dessa problem.</span><span class="sxs-lookup"><span data-stu-id="faf1f-118">*Enrollment will fail* if you don't fix these issues.</span></span> <span data-ttu-id="faf1f-119">Följ stegen i verktyget för att lösa dem.</span><span class="sxs-lookup"><span data-stu-id="faf1f-119">Follow the steps in the tool to resolve them.</span></span>        |

## <a name="obtain-the-checker"></a><span data-ttu-id="faf1f-120">Hämta kontrollen</span><span class="sxs-lookup"><span data-stu-id="faf1f-120">Obtain the checker</span></span>

<span data-ttu-id="faf1f-121">Hämta ZIP-filen https://aka.ms/mmddratoolv0 från.</span><span class="sxs-lookup"><span data-stu-id="faf1f-121">Download the .zip file from https://aka.ms/mmddratoolv0.</span></span>

> [!NOTE]
> <span data-ttu-id="faf1f-122">Den användare som kör verktyget måste ha lokala administratörsrättigheter på den enhet där den körs.</span><span class="sxs-lookup"><span data-stu-id="faf1f-122">The user running the tool must have local Administrator rights on the device where they're running it.</span></span>

 <span data-ttu-id="faf1f-123">Kör sedan verktyget så här:</span><span class="sxs-lookup"><span data-stu-id="faf1f-123">Then run the tool by following these steps:</span></span>

1. <span data-ttu-id="faf1f-124">Kopiera den nedladdade ZIP-filen till varje enhet som du vill kontrollera.</span><span class="sxs-lookup"><span data-stu-id="faf1f-124">Copy the downloaded .zip file to each device you want to check.</span></span>
2. <span data-ttu-id="faf1f-125">Extrahera alla filer i den komprimerade nedladdningen.</span><span class="sxs-lookup"><span data-stu-id="faf1f-125">Extract all files in the compressed download.</span></span>
3. <span data-ttu-id="faf1f-126">Kör **Microsoft.MMD.DeviceReadinessAssessmentTool.exe.**</span><span class="sxs-lookup"><span data-stu-id="faf1f-126">Run **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**.</span></span>
4. <span data-ttu-id="faf1f-127">Välj Ja när frågan om användaråtkomstkontroll **visas.**</span><span class="sxs-lookup"><span data-stu-id="faf1f-127">When the User Access Control prompt appears, select **Yes**.</span></span> <span data-ttu-id="faf1f-128">Verktyget körs och öppnar en rapport i standardwebbläsaren.</span><span class="sxs-lookup"><span data-stu-id="faf1f-128">The tool runs and opens a report in your default browser.</span></span>

<span data-ttu-id="faf1f-129">Du kan också ladda ned och extrahera ZIP-arkivet till en delad plats, komma **Microsoft.MMD.DeviceReadinessAssessmentTool.exe** från varje enhet och sedan köra det lokalt.</span><span class="sxs-lookup"><span data-stu-id="faf1f-129">You could also download and extract the .zip archive to a shared location, access **Microsoft.MMD.DeviceReadinessAssessmentTool.exe** from each device, and then run it locally.</span></span>


## <a name="checks"></a><span data-ttu-id="faf1f-130">Kontroller</span><span class="sxs-lookup"><span data-stu-id="faf1f-130">Checks</span></span>

<span data-ttu-id="faf1f-131">Det nedladdningsbara verktyget kontrollerar dessa enhets- och nätverksrelaterade objekt:</span><span class="sxs-lookup"><span data-stu-id="faf1f-131">The downloadable tool checks these device- and network-related items:</span></span>

### <a name="hardware"></a><span data-ttu-id="faf1f-132">Maskinvara</span><span class="sxs-lookup"><span data-stu-id="faf1f-132">Hardware</span></span>

<span data-ttu-id="faf1f-133">Enheter måste uppfylla specifika maskinvarukrav för att fungera med Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="faf1f-133">Devices must meet specific hardware requirements to work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="faf1f-134">För närvarande [tillåts endast vissa](../service-description/device-list.md) godkända enheter att registrera.</span><span class="sxs-lookup"><span data-stu-id="faf1f-134">Currently, only specific [approved devices](../service-description/device-list.md) are allowed to enroll.</span></span> 

<span data-ttu-id="faf1f-135">Om någon av kontrollerna misslyckas på enheten är den inte kompatibel med Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="faf1f-135">If your device fails any of the checks, it's not compatible with Microsoft Managed Desktop.</span></span>

### <a name="network-endpoints"></a><span data-ttu-id="faf1f-136">Nätverksslutpunkter</span><span class="sxs-lookup"><span data-stu-id="faf1f-136">Network endpoints</span></span>

<span data-ttu-id="faf1f-137">Enheter kan nå flera viktiga [slutpunkter för att arbeta](network.md) med Microsoft Hanterat skrivbord.</span><span class="sxs-lookup"><span data-stu-id="faf1f-137">Devices much be able to reach several [key endpoints](network.md) to work with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="faf1f-138">Om verktyget rapporterar ett resultat **som inte** är klart kan du i den detaljerade rapporten ta reda på vilka slutpunkter som inte kunde nås.</span><span class="sxs-lookup"><span data-stu-id="faf1f-138">If the tool reports a **Not ready** result, see the detailed report to find out which endpoints weren't reachable.</span></span> <span data-ttu-id="faf1f-139">Justera sedan brandväggen eller andra nätverksinställningar för att säkerställa att slutpunkterna kan nås.</span><span class="sxs-lookup"><span data-stu-id="faf1f-139">Then adjust your firewall or other network settings to ensure those endpoints can be reached.</span></span>

### <a name="other-settings"></a><span data-ttu-id="faf1f-140">Andra inställningar</span><span class="sxs-lookup"><span data-stu-id="faf1f-140">Other settings</span></span>

#### <a name="enterprise-wi-fi-profiles"></a><span data-ttu-id="faf1f-141">Wi-Fi-profiler för Enterprise</span><span class="sxs-lookup"><span data-stu-id="faf1f-141">Enterprise wi-fi profiles</span></span>

<span data-ttu-id="faf1f-142">Ett **rådgivningsresultat** innebär att du använder vissa Wi-Fi-profiler som behöver certifikat och profiler för att fungera korrekt.</span><span class="sxs-lookup"><span data-stu-id="faf1f-142">An **Advisory** result means that you are using some wi-fi profiles that need certificates and profiles to work properly.</span></span> <span data-ttu-id="faf1f-143">Mer information finns i Distribuera [certifikat och profilen Wi-Fi/VPN.](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile)</span><span class="sxs-lookup"><span data-stu-id="faf1f-143">For more information, see [Deploy certificates and Wi-Fi/VPN profile](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile).</span></span>

#### <a name="lan-profiles"></a><span data-ttu-id="faf1f-144">LAN-profiler</span><span class="sxs-lookup"><span data-stu-id="faf1f-144">LAN profiles</span></span>

<span data-ttu-id="faf1f-145">Ett **rådgivningsresultat** innebär att du har LAN som behöver certifikat och profiler för att fungera korrekt.</span><span class="sxs-lookup"><span data-stu-id="faf1f-145">An **Advisory** result means that you have LANs that need certificates and profiles to work properly.</span></span> <span data-ttu-id="faf1f-146">Mer information finns i Förbereda [certifikat och nätverksprofiler för Microsoft Managed Desktop.](certs-wifi-lan.md)</span><span class="sxs-lookup"><span data-stu-id="faf1f-146">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="vpn-profiles"></a><span data-ttu-id="faf1f-147">VPN-profiler</span><span class="sxs-lookup"><span data-stu-id="faf1f-147">VPN profiles</span></span>

<span data-ttu-id="faf1f-148">Ett **rådgivningsresultat** innebär att du använder ett virtuellt privat nätverk (VPN).</span><span class="sxs-lookup"><span data-stu-id="faf1f-148">An **Advisory** result means that you're using a virtual private network (VPN).</span></span> <span data-ttu-id="faf1f-149">Skapa en VPN-profil som distribuerar certifikat integrerat med Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="faf1f-149">Create a VPN profile that deploys certificates integrated with Microsoft Intune.</span></span> <span data-ttu-id="faf1f-150">Mer information finns i Förbereda [certifikat och nätverksprofiler för Microsoft Managed Desktop.](certs-wifi-lan.md)</span><span class="sxs-lookup"><span data-stu-id="faf1f-150">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="mapped-drives"></a><span data-ttu-id="faf1f-151">Mappade enheter</span><span class="sxs-lookup"><span data-stu-id="faf1f-151">Mapped drives</span></span>

<span data-ttu-id="faf1f-152">Ett **rådgivningsresultat** innebär att du har vissa mappade enheter, vilket inte rekommenderas.</span><span class="sxs-lookup"><span data-stu-id="faf1f-152">An **Advisory** result means that you have some mapped drives, which aren't recommended.</span></span> <span data-ttu-id="faf1f-153">Mer information finns i Förbereda [mappade enheter för Microsoft Managed Desktop.](mapped-drives.md)</span><span class="sxs-lookup"><span data-stu-id="faf1f-153">For more information, see [Prepare mapped drives for Microsoft Managed Desktop](mapped-drives.md).</span></span>

#### <a name="print-queues"></a><span data-ttu-id="faf1f-154">Skriva ut köer</span><span class="sxs-lookup"><span data-stu-id="faf1f-154">Print queues</span></span>

<span data-ttu-id="faf1f-155">Ett **rådgivningsresultat** innebär att du har några utestående utskriftsköer, vilket inte rekommenderas.</span><span class="sxs-lookup"><span data-stu-id="faf1f-155">An **Advisory** result means that you have some outstanding print queues, which aren't recommended.</span></span> <span data-ttu-id="faf1f-156">En lösning är att skriva ut i molnet.</span><span class="sxs-lookup"><span data-stu-id="faf1f-156">One solution is to use cloud printing.</span></span> <span data-ttu-id="faf1f-157">Mer information finns i Förbereda [utskriftsresurser för Microsoft Managed Desktop.](printing.md)</span><span class="sxs-lookup"><span data-stu-id="faf1f-157">For more information, see [Prepare printing resources for Microsoft Managed Desktop](printing.md).</span></span>

#### <a name="proxies"></a><span data-ttu-id="faf1f-158">Proxy</span><span class="sxs-lookup"><span data-stu-id="faf1f-158">Proxies</span></span>

<span data-ttu-id="faf1f-159">Ett **rådgivningsresultat** innebär att du har en proxyserver som används.</span><span class="sxs-lookup"><span data-stu-id="faf1f-159">An **Advisory** result means that you have a proxy server in use.</span></span> <span data-ttu-id="faf1f-160">Mer information finns i [Nätverkskonfiguration för Microsoft Managed Desktop.](network.md)</span><span class="sxs-lookup"><span data-stu-id="faf1f-160">For more information, see [Network configuration for Microsoft Managed Desktop](network.md).</span></span>

