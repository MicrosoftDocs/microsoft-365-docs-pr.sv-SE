---
title: Felsöka problem med rapporteringsverktyg för Microsoft Defender AV
description: Identifiera och lösa vanliga problem när du försöker rapportera i Microsoft Defender AV-skyddsstatus i Uppdateringsefterlevnad
keywords: felsökning, fel, korrigering, uppdateringsefterlevnad, oms, bildskärm, rapport, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 405955de63de9f84a783ca1b8c0348c3935440cd
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926181"
---
# <a name="troubleshoot-microsoft-defender-antivirus-reporting-in-update-compliance"></a><span data-ttu-id="e7d40-104">Felsök rapportering för Microsoft Defender Antivirus i Uppdateringsefterlevnad</span><span class="sxs-lookup"><span data-stu-id="e7d40-104">Troubleshoot Microsoft Defender Antivirus reporting in Update Compliance</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e7d40-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="e7d40-105">**Applies to:**</span></span>

- [<span data-ttu-id="e7d40-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="e7d40-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> <span data-ttu-id="e7d40-107">Den 31 mars 2020 Microsoft Defender Antivirus bort rapporteringsfunktionen i Uppdateringsefterlevnad.</span><span class="sxs-lookup"><span data-stu-id="e7d40-107">On March 31, 2020, the Microsoft Defender Antivirus reporting feature of Update Compliance will be removed.</span></span> <span data-ttu-id="e7d40-108">Du kan fortsätta att definiera och granska principer för säkerhetsefterlevnad [med hjälp Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager), vilket ger bättre kontroll över säkerhetsfunktioner och uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="e7d40-108">You can continue to define and review security compliance policies using [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager), which allows finer control over security features and updates.</span></span>

<span data-ttu-id="e7d40-109">Du kan använda Microsoft Defender Antivirus med Uppdateringsefterlevnad.</span><span class="sxs-lookup"><span data-stu-id="e7d40-109">You can use Microsoft Defender Antivirus with Update Compliance.</span></span> <span data-ttu-id="e7d40-110">Status för E3, B, F1, VL och Pro licens.</span><span class="sxs-lookup"><span data-stu-id="e7d40-110">You’ll see status for E3, B, F1, VL, and Pro licenses.</span></span> <span data-ttu-id="e7d40-111">Men för E5-licenser måste du använda [Microsoft Defender för Endpoint-portalen](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="e7d40-111">However, for E5 licenses, you need to use the [Microsoft Defender for Endpoint portal](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="e7d40-112">Mer information om licensalternativ finns i Windows 10 [licensalternativ.](https://www.microsoft.com/licensing/product-licensing/windows10.aspx)</span><span class="sxs-lookup"><span data-stu-id="e7d40-112">To learn more about licensing options, see [Windows 10 product licensing options](https://www.microsoft.com/licensing/product-licensing/windows10.aspx).</span></span>

<span data-ttu-id="e7d40-113">När du använder Windows analysuppdateringsefterlevnad för att få rapporter om [skyddsstatus](/windows/deployment/update/update-compliance-using#wdav-assessment) för enheter eller slutpunkter i ditt nätverk som använder Microsoft Defender Antivirus kan du stöta på problem eller problem.</span><span class="sxs-lookup"><span data-stu-id="e7d40-113">When you use [Windows Analytics Update Compliance to obtain reporting into the protection status of devices or endpoints](/windows/deployment/update/update-compliance-using#wdav-assessment) in your network that are using Microsoft Defender Antivirus, you might encounter problems or issues.</span></span>

<span data-ttu-id="e7d40-114">De vanligaste indikatorerna på ett problem är vanligtvis:</span><span class="sxs-lookup"><span data-stu-id="e7d40-114">Typically, the most common indicators of a problem are:</span></span>
- <span data-ttu-id="e7d40-115">Du ser bara ett litet antal eller delmängd av alla enheter som du förväntade dig att se</span><span class="sxs-lookup"><span data-stu-id="e7d40-115">You only see a small number or subset of all the devices you were expecting to see</span></span>
- <span data-ttu-id="e7d40-116">Du ser inga enheter alls</span><span class="sxs-lookup"><span data-stu-id="e7d40-116">You do not see any devices at all</span></span>
- <span data-ttu-id="e7d40-117">Rapporterna och informationen som visas är inaktuell (äldre än några dagar)</span><span class="sxs-lookup"><span data-stu-id="e7d40-117">The reports and information you do see is outdated (older than a few days)</span></span>

<span data-ttu-id="e7d40-118">Information om vanliga felkoder och händelse-IDt som är Microsoft Defender Antivirus tjänst som inte är relaterad till Uppdateringsefterlevnad finns [i Microsoft Defender Antivirus händelser.](troubleshoot-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="e7d40-118">For common error codes and event IDs related to the Microsoft Defender Antivirus service that are not related to Update Compliance, see [Microsoft Defender Antivirus events](troubleshoot-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="e7d40-119">Det finns tre steg för att felsöka de här problemen:</span><span class="sxs-lookup"><span data-stu-id="e7d40-119">There are three steps to troubleshooting these problems:</span></span>

1. <span data-ttu-id="e7d40-120">Kontrollera att du har uppfyllt alla krav</span><span class="sxs-lookup"><span data-stu-id="e7d40-120">Confirm that you have met all prerequisites</span></span>
2. <span data-ttu-id="e7d40-121">Kontrollera anslutningen till Windows Defender molnbaserad tjänst</span><span class="sxs-lookup"><span data-stu-id="e7d40-121">Check your connectivity to the Windows Defender cloud-based service</span></span>
3. <span data-ttu-id="e7d40-122">Skicka supportloggar</span><span class="sxs-lookup"><span data-stu-id="e7d40-122">Submit support logs</span></span>

>[!IMPORTANT]
><span data-ttu-id="e7d40-123">Det tar normalt 3 dagar för enheter att börja visas i Uppdateringsefterlevnad.</span><span class="sxs-lookup"><span data-stu-id="e7d40-123">It typically takes 3 days for devices to start appearing in Update Compliance.</span></span>


## <a name="confirm-prerequisites"></a><span data-ttu-id="e7d40-124">Bekräfta förutsättningarna</span><span class="sxs-lookup"><span data-stu-id="e7d40-124">Confirm prerequisites</span></span>

<span data-ttu-id="e7d40-125">För att enheter ska visas korrekt i Uppdateringsefterlevnad måste du uppfylla vissa krav för både tjänsten för uppdateringsefterlevnad och för Microsoft Defender Antivirus:</span><span class="sxs-lookup"><span data-stu-id="e7d40-125">In order for devices to properly show up in Update Compliance, you have to meet certain prerequisites for both the Update Compliance service and for Microsoft Defender Antivirus:</span></span>

>[!div class="checklist"]
>- <span data-ttu-id="e7d40-126">Slutpunkter använder Microsoft Defender Antivirus som den enda antivirusskyddsappen.</span><span class="sxs-lookup"><span data-stu-id="e7d40-126">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="e7d40-127">[Om du använder någon annan antivirusapp inaktiveras microsoft Defender AV](microsoft-defender-antivirus-compatibility.md) och slutpunkten rapporteras inte under Uppdateringsefterlevnad.</span><span class="sxs-lookup"><span data-stu-id="e7d40-127">[Using any other antivirus app will cause Microsoft Defender AV to disable itself](microsoft-defender-antivirus-compatibility.md) and the endpoint will not be reported in Update Compliance.</span></span>
> - <span data-ttu-id="e7d40-128">[Moln levererat skydd är aktiverat.](enable-cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="e7d40-128">[Cloud-delivered protection is enabled](enable-cloud-protection-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="e7d40-129">Slutpunkter kan [ansluta till Microsoft Defender AV-molnet](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span><span class="sxs-lookup"><span data-stu-id="e7d40-129">Endpoints can [connect to the Microsoft Defender AV cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span></span>
> - <span data-ttu-id="e7d40-130">Om slutpunkten körs med Windows 10 version 1607 eller tidigare [måste Windows 10 av diagnostikdata](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level)anges till nivån Utökad.</span><span class="sxs-lookup"><span data-stu-id="e7d40-130">If the endpoint is running Windows 10 version 1607 or earlier, [Windows 10 diagnostic data must be set to the Enhanced level](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level).</span></span>
> - <span data-ttu-id="e7d40-131">Det har gått tre dagar sedan alla krav har uppfyllts</span><span class="sxs-lookup"><span data-stu-id="e7d40-131">It has been 3 days since all requirements have been met</span></span>

<span data-ttu-id="e7d40-132">"Du kan använda Microsoft Defender Antivirus med uppdateringsefterlevnad.</span><span class="sxs-lookup"><span data-stu-id="e7d40-132">“You can use Microsoft Defender Antivirus with Update Compliance.</span></span> <span data-ttu-id="e7d40-133">Status för E3, B, F1, VL och Pro licens.</span><span class="sxs-lookup"><span data-stu-id="e7d40-133">You’ll see status for E3, B, F1, VL, and Pro licenses.</span></span> <span data-ttu-id="e7d40-134">Men för E5-licenser måste du använda Microsoft Defender för Slutpunktsportalen (/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="e7d40-134">However, for E5 licenses, you need to use the Microsoft Defender for Endpoint portal (/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="e7d40-135">Mer information om licensalternativ finns i Windows 10 licensalternativ"</span><span class="sxs-lookup"><span data-stu-id="e7d40-135">To learn more about licensing options, see Windows 10 product licensing options"</span></span>

<span data-ttu-id="e7d40-136">Om samtliga krav ovan är uppfyllda kan du behöva gå vidare till nästa steg för att samla in diagnostikinformation och skicka den till oss.</span><span class="sxs-lookup"><span data-stu-id="e7d40-136">If the above prerequisites have all been met, you might need to proceed to the next step to collect diagnostic information and send it to us.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e7d40-137">Samla in diagnostikdata för felsökning av uppdateringsefterlevnad</span><span class="sxs-lookup"><span data-stu-id="e7d40-137">Collect diagnostic data for Update Compliance troubleshooting</span></span>](collect-diagnostic-data.md)  

## <a name="related-topics"></a><span data-ttu-id="e7d40-138">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="e7d40-138">Related topics</span></span>

- [<span data-ttu-id="e7d40-139">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="e7d40-139">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="e7d40-140">Distribuera Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="e7d40-140">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)