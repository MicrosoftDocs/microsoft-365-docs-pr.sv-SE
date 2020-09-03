---
title: 'Microsoft 365 grundläggande principer för skydd mot dos: denial-of-service'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Hur Microsoft utnyttjar de grundläggande principerna för absorption, identifiering och skydd mot DoS-attacker (Denial-of-Service).
ms.openlocfilehash: fb3446570dd8e99ccdb3005a6a7c90ca90a81aee
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47331914"
---
# <a name="core-principles-of-defense-against-denial-of-service-attacks"></a><span data-ttu-id="9fbc6-103">Grundläggande principer för skydd mot överbelastningsattacker</span><span class="sxs-lookup"><span data-stu-id="9fbc6-103">Core principles of defense against denial-of-service attacks</span></span>

<span data-ttu-id="9fbc6-104">De tre grundläggande principerna när skydd mot nätbaserade DoS-attacker är absorption, identifiering och minskning.</span><span class="sxs-lookup"><span data-stu-id="9fbc6-104">The three core principles when defending against network-based DoS attacks are Absorption, Detection, and Mitigation.</span></span> <span data-ttu-id="9fbc6-105">Absorption sker före identifiering och identifiering sker innan den begränsas.</span><span class="sxs-lookup"><span data-stu-id="9fbc6-105">Absorption happens before detection, and detection happens before mitigation.</span></span> <span data-ttu-id="9fbc6-106">Absorption är det bästa försvaret mot en DoS-attack.</span><span class="sxs-lookup"><span data-stu-id="9fbc6-106">Absorption is the best defense against a DoS attack.</span></span> <span data-ttu-id="9fbc6-107">Om det inte går att hitta angreppet kan det inte begränsas.</span><span class="sxs-lookup"><span data-stu-id="9fbc6-107">If the attack can't be detected, it can't be mitigated.</span></span> <span data-ttu-id="9fbc6-108">Men om ännu den minsta DoS-attacken inte kan absorberas kommer inte tjänsterna att överleva tillräckligt länge för att angreppet ska kunna identifieras.</span><span class="sxs-lookup"><span data-stu-id="9fbc6-108">But if even the smallest DoS attack can't be absorbed, then services aren't going to survive long enough for the attack to be detected.</span></span>

<span data-ttu-id="9fbc6-109">Det är inte ekonomiskt genomförbart för de flesta organisationer att köpa överskotts kapacitet till att absorbera DoS-attacker, eftersom detta kräver avsevärda investeringar i teknologi och tekniska färdigheter.</span><span class="sxs-lookup"><span data-stu-id="9fbc6-109">It is not economically feasible for most organizations to purchase excess capacity to absorb DoS attacks, as this requires a considerable investment in technology and technical skills.</span></span> <span data-ttu-id="9fbc6-110">Detta markerar en av säkerhets fördelarna med att använda Microsofts moln tjänster.</span><span class="sxs-lookup"><span data-stu-id="9fbc6-110">This highlights one of the security benefits of using Microsoft cloud services.</span></span> <span data-ttu-id="9fbc6-111">Skir skala för Microsoft Services ger starkt nätverks skydd till moln kunder på ett kostnads effektivt sätt.</span><span class="sxs-lookup"><span data-stu-id="9fbc6-111">The sheer scale of Microsoft services provides strong network protection to cloud customers in a cost-effective manner.</span></span> <span data-ttu-id="9fbc6-112">Men till och med för stor skala måste det finnas en avvägning mellan absorption, identifiering och minskning.</span><span class="sxs-lookup"><span data-stu-id="9fbc6-112">But even at a large scale, there must be a balance between absorption, detection, and mitigation.</span></span> <span data-ttu-id="9fbc6-113">För att hitta saldot kan Microsoft utsätta tillväxt priser för att uppskatta hur många Microsoft behöver absorbera.</span><span class="sxs-lookup"><span data-stu-id="9fbc6-113">To find that balance, Microsoft studies attack growth rates to estimate how much Microsoft needs to absorb.</span></span>

<span data-ttu-id="9fbc6-114">Identifiering är ett Cat-och-Mouse-spel.</span><span class="sxs-lookup"><span data-stu-id="9fbc6-114">Detection is a cat-and-mouse game.</span></span> <span data-ttu-id="9fbc6-115">Du måste ständigt leta efter nya sätt som andra är attackerade och prova på att gå ur dina system.</span><span class="sxs-lookup"><span data-stu-id="9fbc6-115">You must constantly look for new ways people are attack and try to defeat your systems.</span></span> <span data-ttu-id="9fbc6-116">Identifiera-> minska-> identifiering-> minskas, etc., är ett permanent, beständigt tillstånd som fortsätter i oändlighet.</span><span class="sxs-lookup"><span data-stu-id="9fbc6-116">Detect -> Mitigate -> Detect -> Mitigate, etc., is a perpetual, persistent state that continues indefinitely.</span></span>

## <a name="defending-against-dos-attacks"></a><span data-ttu-id="9fbc6-117">Försvara mot DoS-attacker</span><span class="sxs-lookup"><span data-stu-id="9fbc6-117">Defending Against DoS Attacks</span></span>

<span data-ttu-id="9fbc6-118">För att det ska kunna försvara sig mot en DoS-attack är det viktigt att upptäcka tidigt.</span><span class="sxs-lookup"><span data-stu-id="9fbc6-118">To successfully defend against a DoS attack, early detection is essential.</span></span> <span data-ttu-id="9fbc6-119">Genom att upptäcka en attack innan systemet är på ett trångt sätt kan försvarare genomföra en svars plan.</span><span class="sxs-lookup"><span data-stu-id="9fbc6-119">By detecting an attack before the system is overwhelmed, defenders can execute a response plan.</span></span>

<span data-ttu-id="9fbc6-120">Följande formel bidrar till att approximera tiden för en DoS-attack:</span><span class="sxs-lookup"><span data-stu-id="9fbc6-120">The following formula helps approximate the time to impact of a DoS attack:</span></span>

   <span data-ttu-id="9fbc6-121">**Maximal kapacitet (i byte/SEK)/tillväxt hastighet (i byte/SEK) = tid att påverka (i SEK)**</span><span class="sxs-lookup"><span data-stu-id="9fbc6-121">**Maximum Capacity (in bytes/sec) / Growth Rate (in bytes/sec) = Time to Impact (in sec)**</span></span>

<span data-ttu-id="9fbc6-122">Om tids-till-identifiering sker efter en tids fördröjning är det troligt vis att DoS-attacken lyckas.</span><span class="sxs-lookup"><span data-stu-id="9fbc6-122">If the time-to-detection occurs after time-to-impact, it is likely the DoS attack will be successful.</span></span> <span data-ttu-id="9fbc6-123">Om tids-till-identifiering sker innan det är dags att påverka bör de attackerade tjänsterna vara online och tillgängliga om det finns begränsningar.</span><span class="sxs-lookup"><span data-stu-id="9fbc6-123">If the time-to-detection occurs before time-to-impact, the attacked services should remain online and accessible if mitigation strategies are used.</span></span> <span data-ttu-id="9fbc6-124">Därför finns det bara två saker som kan utföras för att skydda mot DoS-attacker:</span><span class="sxs-lookup"><span data-stu-id="9fbc6-124">Thus, there are only two things that can be done to defend against DoS attacks:</span></span>

- <span data-ttu-id="9fbc6-125">Öka kapaciteten för att öka taket för maximal kapacitet (vilket i sin tur ger mer tid för att upptäcka ett angrepp); respektive</span><span class="sxs-lookup"><span data-stu-id="9fbc6-125">Increase capacity to raise the ceiling of maximum capacity (which in turn provides more time to detect an attack); or</span></span>
- <span data-ttu-id="9fbc6-126">Förkorta tiden för att upptäcka.</span><span class="sxs-lookup"><span data-stu-id="9fbc6-126">Decrease the time to detect.</span></span>

<span data-ttu-id="9fbc6-127">Ökad kapacitet har en direkt beskattnings effekt.</span><span class="sxs-lookup"><span data-stu-id="9fbc6-127">Increasing capacity has a direct fiscal impact.</span></span> <span data-ttu-id="9fbc6-128">Microsoft rekommenderar att kunderna utvecklar minst grundläggande absorptions kapacitet för att säkerställa att de kan klara av viss DoS-attack.</span><span class="sxs-lookup"><span data-stu-id="9fbc6-128">Microsoft recommends that customers develop at least basic absorption capacity to ensure that they can survive some level of DoS attack.</span></span> <span data-ttu-id="9fbc6-129">Den faktiska absorptions kapaciteten varierar från kund till kund, eftersom varje kund har sina egna tröskelvärden för exponering, risk och ekonomisk outlay.</span><span class="sxs-lookup"><span data-stu-id="9fbc6-129">The actual absorption capacity varies from customer to customer, as each customer has their own thresholds for exposure, risk, and financial outlay.</span></span> <span data-ttu-id="9fbc6-130">Av ekonomiska skäl är det vanligt vis bara det mest kostnads effektiva försvars sättet att minska tiden mot identifieringen.</span><span class="sxs-lookup"><span data-stu-id="9fbc6-130">For economic reasons, investments in research and time for ways to decrease time-to-detection are usually the most cost-effective defense.</span></span>
