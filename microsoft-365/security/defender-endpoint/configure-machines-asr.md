---
title: Optimera ASR-regeldistribution och identifiering
description: Optimera ASR-reglerna (attack surface reduction) för att identifiera och förhindra vanliga sårbarheter för skadlig programvara.
keywords: onboard, Intune-hantering, Microsoft Defender för Slutpunkt, Microsoft Defender, Windows Defender, minskning av attackytan, ASR, säkerhetsbaslinje
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
ms.openlocfilehash: a5590e62e7838bb9f611320b6d0e5c573b2be084
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841566"
---
# <a name="optimize-asr-rule-deployment-and-detections"></a><span data-ttu-id="1f0e3-104">Optimera ASR-regeldistribution och identifiering</span><span class="sxs-lookup"><span data-stu-id="1f0e3-104">Optimize ASR rule deployment and detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1f0e3-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="1f0e3-105">**Applies to:**</span></span>
- [<span data-ttu-id="1f0e3-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="1f0e3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1f0e3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1f0e3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1f0e3-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="1f0e3-108">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="1f0e3-109">[Registrera dig för en kostnadsfri utvärderingsversion](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink).</span><span class="sxs-lookup"><span data-stu-id="1f0e3-109">[Sign up for a free trial](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink).</span></span>

<span data-ttu-id="1f0e3-110">[ASR-regler (Attack Surface Reduction) identifierar](./attack-surface-reduction.md) och förhindrar vanliga sårbarheter från skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="1f0e3-110">[Attack surface reduction (ASR) rules](./attack-surface-reduction.md) identify and prevent typical malware exploits.</span></span> <span data-ttu-id="1f0e3-111">De styr när och hur potentiellt skadlig kod kan köras.</span><span class="sxs-lookup"><span data-stu-id="1f0e3-111">They control when and how potentially malicious code can run.</span></span> <span data-ttu-id="1f0e3-112">De kan till exempel förhindra att JavaScript eller VBScript startar en nedladdad körbar fil, blockera Win32 API-anrop från Office-makron och blockera processer som körs från USB-enheter.</span><span class="sxs-lookup"><span data-stu-id="1f0e3-112">For example, they can prevent JavaScript or VBScript from launching a downloaded executable, block Win32 API calls from Office macros, and block processes that run from USB drives.</span></span>

<span data-ttu-id="1f0e3-113">![Kortet Attackyta](images/secconmgmt_asr_card.png)</span><span class="sxs-lookup"><span data-stu-id="1f0e3-113">![Attack surface management card](images/secconmgmt_asr_card.png)</span></span><br>
<span data-ttu-id="1f0e3-114">*Kortet Attackyta*</span><span class="sxs-lookup"><span data-stu-id="1f0e3-114">*Attack surface management card*</span></span>

<span data-ttu-id="1f0e3-115">Kortet *för hantering av attackytor* är en startpunkt för verktyg Microsoft 365 säkerhetscenter som du kan använda för att:</span><span class="sxs-lookup"><span data-stu-id="1f0e3-115">The *Attack surface management card* is an entry point to tools in Microsoft 365 security center that you can use to:</span></span>

* <span data-ttu-id="1f0e3-116">Förstå hur ASR-regler för närvarande distribueras i organisationen.</span><span class="sxs-lookup"><span data-stu-id="1f0e3-116">Understand how ASR rules are currently deployed in your organization.</span></span>
* <span data-ttu-id="1f0e3-117">Granska ASR-identifieringar och identifiera möjliga felaktiga identifieringar.</span><span class="sxs-lookup"><span data-stu-id="1f0e3-117">Review ASR detections and identify possible incorrect detections.</span></span>
* <span data-ttu-id="1f0e3-118">Analysera effekterna av undantag och generera listan med filsökvägar som ska undantas.</span><span class="sxs-lookup"><span data-stu-id="1f0e3-118">Analyze the impact of exclusions and generate the list of file paths to exclude.</span></span>

<span data-ttu-id="1f0e3-119">Välj **Gå till regler för övervakning av attackytor**& i > för minskning av  >  **attackytor > Lägg till undantag**.</span><span class="sxs-lookup"><span data-stu-id="1f0e3-119">Select **Go to attack surface management** > **Monitoring & reports > Attack surface reduction rules > Add exclusions**.</span></span> <span data-ttu-id="1f0e3-120">Därifrån kan du navigera till andra avsnitt i Microsoft 365 Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="1f0e3-120">From there, you can navigate to other sections of Microsoft 365 security center.</span></span>

<span data-ttu-id="1f0e3-121">![Fliken Lägg till undantag på sidan För att minska attackytan i Microsoft 365 säkerhetscenter](images/secconmgmt_asr_m365exlusions.png)</span><span class="sxs-lookup"><span data-stu-id="1f0e3-121">![Add exclusions tab in the Attack surface reduction rules page in Microsoft 365 security center](images/secconmgmt_asr_m365exlusions.png)</span></span><br>
<span data-ttu-id="1f0e3-122">Fliken ***Lägg till undantag** på sidan För att minska attackytan i Microsoft 365 säkerhetscenter*</span><span class="sxs-lookup"><span data-stu-id="1f0e3-122">The ***Add exclusions** tab in the Attack surface reduction rules page in Microsoft 365 security center*</span></span>

> [!NOTE]
> <span data-ttu-id="1f0e3-123">För att Microsoft 365 åtkomst till säkerhetscentret behöver du en licens Microsoft 365 E3 eller E5 och ett konto som har vissa roller på Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1f0e3-123">To access Microsoft 365 security center, you need a Microsoft 365 E3 or E5 license and an account that has certain roles on Azure Active Directory.</span></span> <span data-ttu-id="1f0e3-124">[Läs om licenser och behörigheter som krävs.](/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="1f0e3-124">[Read about required licenses and permissions](/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).</span></span>

<span data-ttu-id="1f0e3-125">Mer information om distribution av ASR-regler Microsoft 365 säkerhetscenter finns i Övervaka och hantera DISTRIBUTION och identifiering av [ASR-regler.](/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections)</span><span class="sxs-lookup"><span data-stu-id="1f0e3-125">For more information about ASR rule deployment in Microsoft 365 security center, see [Monitor and manage ASR rule deployment and detections](/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections).</span></span>

<span data-ttu-id="1f0e3-126">**Närliggande ämnen**</span><span class="sxs-lookup"><span data-stu-id="1f0e3-126">**Related topics**</span></span>

* [<span data-ttu-id="1f0e3-127">Se till att dina enheter är korrekt konfigurerade</span><span class="sxs-lookup"><span data-stu-id="1f0e3-127">Ensure your devices are configured properly</span></span>](configure-machines.md)
* [<span data-ttu-id="1f0e3-128">Få enheter skickade till Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="1f0e3-128">Get devices onboarded to Microsoft Defender for Endpoint</span></span>](configure-machines-onboarding.md)
* [<span data-ttu-id="1f0e3-129">Övervaka efterlevnad av Microsoft Defender för slutpunktens säkerhetsbaslinje</span><span class="sxs-lookup"><span data-stu-id="1f0e3-129">Monitor compliance to the Microsoft Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md)
