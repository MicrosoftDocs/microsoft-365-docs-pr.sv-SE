---
title: Upplev Microsoft Defender ATP genom simulerade attacker
description: Kör de angivna attackscenarion för att uppleva hur Microsoft Defender ATP kan upptäcka, undersöka och hantera överträdelser.
keywords: wdatp, test, scenario, attack, simulering, simulerad, gör-det-själv, Microsoft Defender för slutpunkt
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/20/2018
ms.technology: mde
ms.openlocfilehash: b3fb862ac6e845ed4a3f5b72bae902f00c125b53
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498304"
---
# <a name="experience-microsoft-defender-for-endpoint-through-simulated-attacks"></a><span data-ttu-id="6364f-104">Upplev Microsoft Defender för Endpoint genom simulerade attacker</span><span class="sxs-lookup"><span data-stu-id="6364f-104">Experience Microsoft Defender for Endpoint through simulated attacks</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6364f-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="6364f-105">**Applies to:**</span></span>
- [<span data-ttu-id="6364f-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="6364f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="6364f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6364f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="6364f-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="6364f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6364f-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="6364f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-abovefoldlink)

>[!TIP]
>- <span data-ttu-id="6364f-110">Läs mer om de senaste förbättringarna i Microsoft Defender ATP: [Nyheter i Defender för Slutpunkt.](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/)</span><span class="sxs-lookup"><span data-stu-id="6364f-110">Learn about the latest enhancements in Microsoft Defender ATP: [What's new in Defender for Endpoint?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span></span>
>- <span data-ttu-id="6364f-111">Defender för Endpoint visade branschledandeoptisk och identifieringsfunktioner i den senaste MITRE-utvärderingen.</span><span class="sxs-lookup"><span data-stu-id="6364f-111">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="6364f-112">Läs: [Insikter från MITRE ATT&CK-baserad utvärdering.](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)</span><span class="sxs-lookup"><span data-stu-id="6364f-112">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

<span data-ttu-id="6364f-113">Du kanske vill använda Defender för Slutpunkt innan du inför mer än ett fåtal enheter i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="6364f-113">You might want to experience Defender for Endpoint before you onboard more than a few devices to the service.</span></span> <span data-ttu-id="6364f-114">Det kan du göra genom att köra kontrollerad attack simulering på några testenheter.</span><span class="sxs-lookup"><span data-stu-id="6364f-114">To do this, you can run controlled attack simulations on a few test devices.</span></span> <span data-ttu-id="6364f-115">När du har kört de simulerade attackerna kan du se hur Defender för Endpoint visar skadlig aktivitet och undersöker hur det möjliggör ett effektivt svar.</span><span class="sxs-lookup"><span data-stu-id="6364f-115">After running the simulated attacks, you can review how Defender for Endpoint surfaces malicious activity and explore how it enables an efficient response.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6364f-116">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="6364f-116">Before you begin</span></span>

<span data-ttu-id="6364f-117">Om du vill köra någon av de angivna simuleringarna behöver du minst [en inbyggd enhet](onboard-configure.md).</span><span class="sxs-lookup"><span data-stu-id="6364f-117">To run any of the provided simulations, you need at least [one onboarded device](onboard-configure.md).</span></span> 

<span data-ttu-id="6364f-118">Läs genomgångsdokumentet som tillhandahålls för varje attackscenario.</span><span class="sxs-lookup"><span data-stu-id="6364f-118">Read the walkthrough document provided with each attack scenario.</span></span> <span data-ttu-id="6364f-119">Varje dokument innehåller OS- och programkrav samt detaljerade anvisningar som är specifika för ett attackscenario.</span><span class="sxs-lookup"><span data-stu-id="6364f-119">Each document includes OS and application requirements as well as detailed instructions that are specific to an attack scenario.</span></span>

## <a name="run-a-simulation"></a><span data-ttu-id="6364f-120">Köra en simulering</span><span class="sxs-lookup"><span data-stu-id="6364f-120">Run a simulation</span></span>

1. <span data-ttu-id="6364f-121">I **Hjälp**  >  **simuleringar & självstudiekurser**, välj vilka tillgängliga attackscenarier du vill simulera:</span><span class="sxs-lookup"><span data-stu-id="6364f-121">In **Help** > **Simulations & tutorials**, select which of the available attack scenarios you would like to simulate:</span></span>

   - <span data-ttu-id="6364f-122">**Scenario 1: Dokument tappar backdoor** – simulerar leverans av ett socialt teknikerat lure-dokument.</span><span class="sxs-lookup"><span data-stu-id="6364f-122">**Scenario 1: Document drops backdoor** - simulates delivery of a socially engineered lure document.</span></span> <span data-ttu-id="6364f-123">Dokumentet öppnar en särskilt utformad backdoor som ger attackerare kontroll.</span><span class="sxs-lookup"><span data-stu-id="6364f-123">The document launches a specially crafted backdoor that gives attackers control.</span></span>

   - <span data-ttu-id="6364f-124">**Scenario 2: PowerShell-skript** i fillös attack – simulerar en fillös attack som förlitar sig på PowerShell, visar minskning av attackytan och enhetsinlärning av skadlig minnesaktivitet.</span><span class="sxs-lookup"><span data-stu-id="6364f-124">**Scenario 2: PowerShell script in fileless attack** - simulates a fileless attack that relies on PowerShell, showcasing attack surface reduction and device learning detection of malicious memory activity.</span></span>
    
   - <span data-ttu-id="6364f-125">**Scenario 3: Automatiserat incidentsvar** – utlöser automatiserad undersökning, som automatiskt söker efter och åtgärdar intrångsartefakter för att anpassa svarskapaciteten för incidenter.</span><span class="sxs-lookup"><span data-stu-id="6364f-125">**Scenario 3: Automated incident response** - triggers automated investigation, which automatically hunts for and remediates breach artifacts to scale your incident response capacity.</span></span>

2. <span data-ttu-id="6364f-126">Ladda ned och läs motsvarande genomgångar för ditt valda scenario.</span><span class="sxs-lookup"><span data-stu-id="6364f-126">Download and read the corresponding walkthrough document provided with your selected scenario.</span></span>

3. <span data-ttu-id="6364f-127">Ladda ned simuleringsfilen eller kopiera simuleringsskriptet genom att navigera till **Hjälp**  >  **simuleringar & självstudiekurser.**</span><span class="sxs-lookup"><span data-stu-id="6364f-127">Download the simulation file or copy the simulation script by navigating to **Help** > **Simulations & tutorials**.</span></span> <span data-ttu-id="6364f-128">Du kan välja att ladda ned filen eller skriptet på testenheten men det är inte obligatoriskt.</span><span class="sxs-lookup"><span data-stu-id="6364f-128">You can choose to download the file or script on the test device but it's not mandatory.</span></span>

4. <span data-ttu-id="6364f-129">Kör simuleringsfilen eller skriptet på testenheten enligt anvisningarna i genomgångsdokumentet.</span><span class="sxs-lookup"><span data-stu-id="6364f-129">Run the simulation file or script on the test device as instructed in the walkthrough document.</span></span>

> [!NOTE]
> <span data-ttu-id="6364f-130">Simuleringsfiler eller skript efterliknar attackaktivitet men är faktiskt inte deras skada eller äventyrar testenheten.</span><span class="sxs-lookup"><span data-stu-id="6364f-130">Simulation files or scripts mimic attack activity but are actually benign and will not harm or compromise the test device.</span></span>
> 
> 
> <span data-ttu-id="6364f-131">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="6364f-131">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6364f-132">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="6364f-132">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-belowfoldlink)


## <a name="related-topics"></a><span data-ttu-id="6364f-133">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="6364f-133">Related topics</span></span>

- [<span data-ttu-id="6364f-134">Onboard-enheter</span><span class="sxs-lookup"><span data-stu-id="6364f-134">Onboard devices</span></span>](onboard-configure.md)
- [<span data-ttu-id="6364f-135">Registrera Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="6364f-135">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
