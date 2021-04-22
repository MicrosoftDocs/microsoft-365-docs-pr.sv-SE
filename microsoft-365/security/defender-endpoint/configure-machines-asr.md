---
title: Optimera ASR-regeldistribution och identifiering
description: Optimera ASR-reglerna (attack surface reduction) för att identifiera och förhindra vanliga sårbarheter för skadlig programvara.
keywords: onboard, Intune-hantering, Microsoft Defender för slutpunkt, Microsoft Defender, Windows Defender, minskning av attackytan, ASR, säkerhetsbaslinje
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 91295135c833c6b403078bdfd517c7b84ec7d630
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932853"
---
# <a name="optimize-asr-rule-deployment-and-detections"></a><span data-ttu-id="239cd-104">Optimera ASR-regeldistribution och identifiering</span><span class="sxs-lookup"><span data-stu-id="239cd-104">Optimize ASR rule deployment and detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="239cd-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="239cd-105">**Applies to:**</span></span>
- [<span data-ttu-id="239cd-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="239cd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="239cd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="239cd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="239cd-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="239cd-108">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="239cd-109">[Registrera dig för en kostnadsfri utvärderingsversion](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink).</span><span class="sxs-lookup"><span data-stu-id="239cd-109">[Sign up for a free trial](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink).</span></span>

<span data-ttu-id="239cd-110">[ASR-regler (Attack Surface Reduction) identifierar](./attack-surface-reduction.md) och förhindrar vanliga sårbarheter från skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="239cd-110">[Attack surface reduction (ASR) rules](./attack-surface-reduction.md) identify and prevent typical malware exploits.</span></span> <span data-ttu-id="239cd-111">De styr när och hur potentiellt skadlig kod kan köras.</span><span class="sxs-lookup"><span data-stu-id="239cd-111">They control when and how potentially malicious code can run.</span></span> <span data-ttu-id="239cd-112">De kan till exempel förhindra att JavaScript eller VBScript startar en nedladdad körbar fil, blockera Win32 API-anrop från Office-makron och blockera processer som körs från USB-enheter.</span><span class="sxs-lookup"><span data-stu-id="239cd-112">For example, they can prevent JavaScript or VBScript from launching a downloaded executable, block Win32 API calls from Office macros, and block processes that run from USB drives.</span></span>

<span data-ttu-id="239cd-113">![Kortet Attackyta](images/secconmgmt_asr_card.png)</span><span class="sxs-lookup"><span data-stu-id="239cd-113">![Attack surface management card](images/secconmgmt_asr_card.png)</span></span><br>
<span data-ttu-id="239cd-114">*Kortet Attackyta*</span><span class="sxs-lookup"><span data-stu-id="239cd-114">*Attack surface management card*</span></span>

<span data-ttu-id="239cd-115">Kortet *för hantering av attackytor* är en startpunkt för verktyg i Microsoft 365 säkerhetscenter som du kan använda för att:</span><span class="sxs-lookup"><span data-stu-id="239cd-115">The *Attack surface management card* is an entry point to tools in Microsoft 365 security center that you can use to:</span></span>

* <span data-ttu-id="239cd-116">Förstå hur ASR-regler för närvarande distribueras i organisationen.</span><span class="sxs-lookup"><span data-stu-id="239cd-116">Understand how ASR rules are currently deployed in your organization.</span></span>
* <span data-ttu-id="239cd-117">Granska ASR-identifieringar och identifiera möjliga felaktiga identifieringar.</span><span class="sxs-lookup"><span data-stu-id="239cd-117">Review ASR detections and identify possible incorrect detections.</span></span>
* <span data-ttu-id="239cd-118">Analysera effekterna av undantag och generera listan med filsökvägar som ska undantas.</span><span class="sxs-lookup"><span data-stu-id="239cd-118">Analyze the impact of exclusions and generate the list of file paths to exclude.</span></span>

<span data-ttu-id="239cd-119">Välj **Gå till regler för övervakning av attackytor**& i > för minskning av  >  **attackytor > Lägg till undantag**.</span><span class="sxs-lookup"><span data-stu-id="239cd-119">Select **Go to attack surface management** > **Monitoring & reports > Attack surface reduction rules > Add exclusions**.</span></span> <span data-ttu-id="239cd-120">Därifrån kan du gå till andra avsnitt i Säkerhetscenter för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="239cd-120">From there, you can navigate to other sections of Microsoft 365 security center.</span></span>

<span data-ttu-id="239cd-121">![Fliken Lägg till undantag på sidan För att minska attackytan i Microsoft 365 Säkerhetscenter](images/secconmgmt_asr_m365exlusions.png)</span><span class="sxs-lookup"><span data-stu-id="239cd-121">![Add exclusions tab in the Attack surface reduction rules page in Microsoft 365 security center](images/secconmgmt_asr_m365exlusions.png)</span></span><br>
<span data-ttu-id="239cd-122">Fliken ***Lägg till undantag** på sidan För att minska attackytan i Microsoft 365 Säkerhetscenter*</span><span class="sxs-lookup"><span data-stu-id="239cd-122">The ***Add exclusions** tab in the Attack surface reduction rules page in Microsoft 365 security center*</span></span>

> [!NOTE]
> <span data-ttu-id="239cd-123">För att komma åt Microsoft 365 säkerhetscenter behöver du en Microsoft 365 E3- eller E5-licens och ett konto som har vissa roller i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="239cd-123">To access Microsoft 365 security center, you need a Microsoft 365 E3 or E5 license and an account that has certain roles on Azure Active Directory.</span></span> <span data-ttu-id="239cd-124">[Läs om licenser och behörigheter som krävs.](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="239cd-124">[Read about required licenses and permissions](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).</span></span>

<span data-ttu-id="239cd-125">Mer information om distribution av ASR-regler i Säkerhetscenter för Microsoft 365 finns i Övervaka och hantera distribution och identifiering av [ASR-regler.](https://docs.microsoft.com/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections)</span><span class="sxs-lookup"><span data-stu-id="239cd-125">For more information about ASR rule deployment in Microsoft 365 security center, see [Monitor and manage ASR rule deployment and detections](https://docs.microsoft.com/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections).</span></span>

<span data-ttu-id="239cd-126">**Närliggande ämnen**</span><span class="sxs-lookup"><span data-stu-id="239cd-126">**Related topics**</span></span>

* [<span data-ttu-id="239cd-127">Se till att dina enheter är korrekt konfigurerade</span><span class="sxs-lookup"><span data-stu-id="239cd-127">Ensure your devices are configured properly</span></span>](configure-machines.md)
* [<span data-ttu-id="239cd-128">Få enheter skickade till Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="239cd-128">Get devices onboarded to Microsoft Defender for Endpoint</span></span>](configure-machines-onboarding.md)
* [<span data-ttu-id="239cd-129">Övervaka efterlevnad av Microsoft Defender för slutpunktens säkerhetsbaslinje</span><span class="sxs-lookup"><span data-stu-id="239cd-129">Monitor compliance to the Microsoft Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md)
