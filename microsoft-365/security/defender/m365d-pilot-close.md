---
title: Sammanfattning av dina microsoft 365 Defender-pilotprojektresultat
description: Avsluta microsoft 365 Defender-pilotprojektet genom att slutföra ditt styrkort, analysera resultaten i rapporten och bestämma hur du ska gå framåt.
keywords: Microsoft 365 Defender Pilot, bestäm vad du ska göra härnäst efter pilottestet av Microsoft 365 Defender-projektet, vad du ska göra efter utvärdering av Microsoft 365 Defender i produktionen, övergång från Microsoft 365 Defender pilottest till distribution, cybersäkerhet, avancerade beständiga hot, företagssäkerhet, enheter, enheter, identitet, användare, data, program, incidenter, automatiserad undersökning och åtgärd, avancerad sökning
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 64cdb37b64780a651b2689e68e21c5a385df5ba9
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932875"
---
# <a name="closing-and-summarizing-your-microsoft-365-defender-pilot"></a><span data-ttu-id="9d2ba-104">Stänga och sammanfatta din Microsoft 365 Defender-pilot</span><span class="sxs-lookup"><span data-stu-id="9d2ba-104">Closing and summarizing your Microsoft 365 Defender pilot</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9d2ba-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="9d2ba-105">**Applies to:**</span></span>
- <span data-ttu-id="9d2ba-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9d2ba-106">Microsoft 365 Defender</span></span>



|<span data-ttu-id="9d2ba-107">[![Planering](../../media/phase-diagrams/1-planning.png)](m365d-pilot-plan.md)</span><span class="sxs-lookup"><span data-stu-id="9d2ba-107">[![Planning](../../media/phase-diagrams/1-planning.png)](m365d-pilot-plan.md)</span></span><br/>[<span data-ttu-id="9d2ba-108">Planering</span><span class="sxs-lookup"><span data-stu-id="9d2ba-108">Planning</span></span>](m365d-pilot-plan.md) |<span data-ttu-id="9d2ba-109">[![Förbereda](../../media/phase-diagrams/2-prepare.png)](prepare-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="9d2ba-109">[![Prepare](../../media/phase-diagrams/2-prepare.png)](prepare-m365d-eval.md)</span></span><br/>[<span data-ttu-id="9d2ba-110">Förberedelse</span><span class="sxs-lookup"><span data-stu-id="9d2ba-110">Preparation</span></span>](prepare-m365d-eval.md) | <span data-ttu-id="9d2ba-111">[![Simulera attack](../../media/phase-diagrams/3-simluate.png)](m365d-pilot-simulate.md)</span><span class="sxs-lookup"><span data-stu-id="9d2ba-111">[![Simulate attack](../../media/phase-diagrams/3-simluate.png)](m365d-pilot-simulate.md)</span></span><br/>[<span data-ttu-id="9d2ba-112">Simulera attack</span><span class="sxs-lookup"><span data-stu-id="9d2ba-112">Simulate attack</span></span>](m365d-pilot-simulate.md) | ![Stäng och sammanfatta](../../media/phase-diagrams/4-summary.png)<br/><span data-ttu-id="9d2ba-114">Stäng och sammanfatta</span><span class="sxs-lookup"><span data-stu-id="9d2ba-114">Close and summarize</span></span>|
|--|--|--|--|
|| | |<span data-ttu-id="9d2ba-115">*Du är här!*</span><span class="sxs-lookup"><span data-stu-id="9d2ba-115">*You are here!*</span></span>|


<span data-ttu-id="9d2ba-116">Du befinner dig för närvarande i den sista och sammanfattande fasen.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-116">You're currently in the closing and summarizing phase.</span></span>

<span data-ttu-id="9d2ba-117">Du har precis kört en avancerad simulering av minnes endast minne-attack som körde kod på en domänkontrollant.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-117">You’ve just ran an advanced memory-only attack simulation that executed code remotely on a domain controller.</span></span> <span data-ttu-id="9d2ba-118">Du har sett hur Microsoft Defender för Endpoint och Microsoft Defender för identitet identifierar och skapar aviseringar om skadlig aktivitet.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-118">You’ve seen how Microsoft Defender for Endpoint and Microsoft Defender for Identity detect and create alerts on stealthy malicious activity.</span></span> <span data-ttu-id="9d2ba-119">Du ser också hur aviseringar från olika källor levereras tillsammans med annan sammanhangsberoende information till ett enskilt incident i Microsoft 365 Säkerhetscenter-portalen.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-119">You’ve also seen how alerts from different sources are delivered along with other contextual information into a single incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="9d2ba-120">Då sådan integrering gör det möjligt för SOC-analytiker att undersöka och vidta nödvändiga åtgärder.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-120">Experiencing such integration enables SOC analysts to investigate and take necessary action.</span></span> <span data-ttu-id="9d2ba-121">Du har också skapat en avancerad fråga för sökning som identifierar inkommande e-postmeddelanden där användaren öppnade eller sparade den bifogade filen och skapade identifiering baserat på den frågan.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-121">You’ve also created an advanced hunting query that will identify inbound emails where the user opened or saved the attachment and created detection based on that query.</span></span>

<span data-ttu-id="9d2ba-122">Du har nått slutet av processen när alla tester är slutförda.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-122">You’ve reached the end of the process after all tests have concluded.</span></span>

<span data-ttu-id="9d2ba-123">De slutliga resultaten bör vara:</span><span class="sxs-lookup"><span data-stu-id="9d2ba-123">The final output should be:</span></span>

- <span data-ttu-id="9d2ba-124">Ett slutfört styrkort</span><span class="sxs-lookup"><span data-stu-id="9d2ba-124">A completed scorecard</span></span>
- <span data-ttu-id="9d2ba-125">En detaljerad rapport över pilotens resultat</span><span class="sxs-lookup"><span data-stu-id="9d2ba-125">A detailed report of the findings of the pilot</span></span>
- <span data-ttu-id="9d2ba-126">Ett beslut om hur du ska gå framåt</span><span class="sxs-lookup"><span data-stu-id="9d2ba-126">A decision on how to move forward</span></span>

<span data-ttu-id="9d2ba-127">Presentera rapporter från dina slutliga utdata till interna intressenter (som du har identifierat under [förberedelsefasen)](./prepare-m365d-eval.md) och Microsoft-kontakter.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-127">Present the reports from your final output to internal stakeholders (which you’ve identified during the [preparation](./prepare-m365d-eval.md) phase) and Microsoft contacts.</span></span> <span data-ttu-id="9d2ba-128">Ett sådant arbete säkerställer att all feedback kan användas för att förbättra produkter och dokumentation.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-128">Such an effort ensures that any feedback can be used to improve products and documentation.</span></span>

<span data-ttu-id="9d2ba-129">Vi hoppas att du gillade den här simuleringen.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-129">We hope you enjoyed this simulation.</span></span> <span data-ttu-id="9d2ba-130">Börja implementera det du har lärt dig i större skala i din organisation för att få ut mesta mesta av den integrerade säkerhetslösningen.</span><span class="sxs-lookup"><span data-stu-id="9d2ba-130">Start implementing what you've learned on a larger scale in your organization to get the most out of the integrated security solution.</span></span>

## <a name="next-step"></a><span data-ttu-id="9d2ba-131">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="9d2ba-131">Next step</span></span>
<span data-ttu-id="9d2ba-132">Läs mer om Microsoft 365 Defender-pelarna genom följande interaktiva guider:</span><span class="sxs-lookup"><span data-stu-id="9d2ba-132">Learn more about the Microsoft 365 Defender pillars through the following interactive guides:</span></span>
- [<span data-ttu-id="9d2ba-133">Skydda din organisation med Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="9d2ba-133">Safeguard your organization with Microsoft Defender for Office 365</span></span>](https://aka.ms/O365ATP-Interactive-Guide)
- [<span data-ttu-id="9d2ba-134">Identifiera misstänkta aktiviteter och potentiella attacker med Microsoft Defender för identitet</span><span class="sxs-lookup"><span data-stu-id="9d2ba-134">Detect suspicious activities and potential attacks with Microsoft Defender for Identity</span></span>](https://aka.ms/AATP-Interactive-Guide)
- [<span data-ttu-id="9d2ba-135">Upptäcka hot och hantera aviseringar med Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="9d2ba-135">Detect threats and manage alerts with Microsoft Cloud App Security</span></span>](https://aka.ms/DetectThreatsAndAlertsMCAS-InteractiveGuide)
- [<span data-ttu-id="9d2ba-136">Undersöka och åtgärda hot med Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="9d2ba-136">Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)