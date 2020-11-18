---
title: Sammanfatta resultatet från piloten Microsoft 365 Defender Project
description: Avsluta ditt pilot Microsoft 365 Defender-projekt genom att fylla på ditt styrkort, analysera rapportens resultat och bestämma hur du ska gå vidare.
keywords: Microsoft Threat Protection pilot, Välj vad du vill göra härnäst efter pilot Microsoft Threat Protection Project, vad kan jag göra efter utvärdering av Microsoft Threat Protection in Production, över gång från Microsoft Threat Protection pilot till distribution, cyberterrorism Security, Avancerat, säkerhets-och skydds system
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: 3fe5bfdec566b0988d9f565595624fc8dd597788
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130963"
---
# <a name="closing-and-summarizing-your-microsoft-365-defender-pilot"></a><span data-ttu-id="2c60f-104">Stänga och sammanfatta din Microsoft 365 Defender pilot</span><span class="sxs-lookup"><span data-stu-id="2c60f-104">Closing and summarizing your Microsoft 365 Defender pilot</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2c60f-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="2c60f-105">**Applies to:**</span></span>
- <span data-ttu-id="2c60f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2c60f-106">Microsoft 365 Defender</span></span>



|<span data-ttu-id="2c60f-107">[![Planering](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span><span class="sxs-lookup"><span data-stu-id="2c60f-107">[![Planning](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span></span><br/>[<span data-ttu-id="2c60f-108">Planering</span><span class="sxs-lookup"><span data-stu-id="2c60f-108">Planning</span></span>](mtp-pilot-plan.md) |<span data-ttu-id="2c60f-109">[![Förbereda](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="2c60f-109">[![Prepare](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="2c60f-110">Förberedelse</span><span class="sxs-lookup"><span data-stu-id="2c60f-110">Preparation</span></span>](prepare-mtpeval.md) | <span data-ttu-id="2c60f-111">[![Simulera attack](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)</span><span class="sxs-lookup"><span data-stu-id="2c60f-111">[![Simulate attack](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)</span></span><br/>[<span data-ttu-id="2c60f-112">Simulera attack</span><span class="sxs-lookup"><span data-stu-id="2c60f-112">Simulate attack</span></span>](mtp-pilot-simulate.md) | ![Stäng och sammanfatta](../../media/phase-diagrams/4-summary.png)<br/><span data-ttu-id="2c60f-114">Stäng och sammanfatta</span><span class="sxs-lookup"><span data-stu-id="2c60f-114">Close and summarize</span></span>|
|--|--|--|--|
|| | |<span data-ttu-id="2c60f-115">*Nu är det här!*</span><span class="sxs-lookup"><span data-stu-id="2c60f-115">*You are here!*</span></span>|


<span data-ttu-id="2c60f-116">Du befinner dig i steget avsluta och summera.</span><span class="sxs-lookup"><span data-stu-id="2c60f-116">You're currently in the closing and summarizing phase.</span></span>

<span data-ttu-id="2c60f-117">Du har precis kört en avancerad simulering av minnes attacker som kördes på en fjärrdator på en domänkontrollant.</span><span class="sxs-lookup"><span data-stu-id="2c60f-117">You’ve just ran an advanced memory-only attack simulation that executed code remotely on a domain controller.</span></span> <span data-ttu-id="2c60f-118">Du har sett hur Microsoft Defender för slut punkten och Microsoft Defender för att identifiera och skapa aviseringar för stealthy uppsåtlig aktivitet.</span><span class="sxs-lookup"><span data-stu-id="2c60f-118">You’ve seen how Microsoft Defender for Endpoint and Microsoft Defender for Identity detect and create alerts on stealthy malicious activity.</span></span> <span data-ttu-id="2c60f-119">Du har också sett hur aviseringar från olika källor levereras tillsammans med annan kontextuell information till en enda olycka i Microsoft 365 Security Center-portalen.</span><span class="sxs-lookup"><span data-stu-id="2c60f-119">You’ve also seen how alerts from different sources are delivered along with other contextual information into a single incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="2c60f-120">Tack vare denna integrering kan SOC analytiker undersöka och vidta nödvändiga åtgärder.</span><span class="sxs-lookup"><span data-stu-id="2c60f-120">Experiencing such integration enables SOC analysts to investigate and take necessary action.</span></span> <span data-ttu-id="2c60f-121">Du har också skapat en avancerad jakt fråga som identifierar inkommande e-postmeddelanden där användaren öppnade eller sparade den bifogade filen och skapade identifiering som baseras på den frågan.</span><span class="sxs-lookup"><span data-stu-id="2c60f-121">You’ve also created an advanced hunting query that will identify inbound emails where the user opened or saved the attachment and created detection based on that query.</span></span>

<span data-ttu-id="2c60f-122">Du har nått slutet av processen efter att alla tester har genomförts.</span><span class="sxs-lookup"><span data-stu-id="2c60f-122">You’ve reached the end of the process after all tests have concluded.</span></span>

<span data-ttu-id="2c60f-123">De slutliga resultaten ska vara:</span><span class="sxs-lookup"><span data-stu-id="2c60f-123">The final output should be:</span></span>

- <span data-ttu-id="2c60f-124">Ett slutfört styrkort</span><span class="sxs-lookup"><span data-stu-id="2c60f-124">A completed scorecard</span></span>
- <span data-ttu-id="2c60f-125">En detaljerad rapport om resultatet av piloten</span><span class="sxs-lookup"><span data-stu-id="2c60f-125">A detailed report of the findings of the pilot</span></span>
- <span data-ttu-id="2c60f-126">Ett beslut om hur du flyttar framåt</span><span class="sxs-lookup"><span data-stu-id="2c60f-126">A decision on how to move forward</span></span>

<span data-ttu-id="2c60f-127">Presentera rapporterna från dina slutliga utdata till interna intressenter (som du har identifierat under [förberedelse](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) fasen) och Microsoft-kontakter.</span><span class="sxs-lookup"><span data-stu-id="2c60f-127">Present the reports from your final output to internal stakeholders (which you’ve identified during the [preparation](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) phase) and Microsoft contacts.</span></span> <span data-ttu-id="2c60f-128">Sådant arbete garanterar att all feedback kan användas för att förbättra produkter och dokumentation.</span><span class="sxs-lookup"><span data-stu-id="2c60f-128">Such an effort ensures that any feedback can be used to improve products and documentation.</span></span>

<span data-ttu-id="2c60f-129">Vi hoppas du gillade den här simuleringen.</span><span class="sxs-lookup"><span data-stu-id="2c60f-129">We hope you enjoyed this simulation.</span></span> <span data-ttu-id="2c60f-130">Börja implementera det du har lärt dig på en större skala för att få ut mesta möjliga av den integrerade säkerhets lösningen.</span><span class="sxs-lookup"><span data-stu-id="2c60f-130">Start implementing what you've learned on a larger scale in your organization to get the most out of the integrated security solution.</span></span>

## <a name="next-step"></a><span data-ttu-id="2c60f-131">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="2c60f-131">Next step</span></span>
<span data-ttu-id="2c60f-132">Läs mer om Microsoft 365 Defender-pelaren genom följande interaktiva stöd linjer:</span><span class="sxs-lookup"><span data-stu-id="2c60f-132">Learn more about the Microsoft 365 Defender pillars through the following interactive guides:</span></span>
- [<span data-ttu-id="2c60f-133">Skydda din organisation med Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="2c60f-133">Safeguard your organization with Microsoft Defender for Office 365</span></span>](https://aka.ms/O365ATP-Interactive-Guide)
- [<span data-ttu-id="2c60f-134">Upptäck misstänkta aktiviteter och potentiella attacker med Microsoft Defender för identitet</span><span class="sxs-lookup"><span data-stu-id="2c60f-134">Detect suspicious activities and potential attacks with Microsoft Defender for Identity</span></span>](https://aka.ms/AATP-Interactive-Guide)
- [<span data-ttu-id="2c60f-135">Upptäcka hot och hantera aviseringar med säkerhet för Microsoft Cloud App</span><span class="sxs-lookup"><span data-stu-id="2c60f-135">Detect threats and manage alerts with Microsoft Cloud App Security</span></span>](https://aka.ms/DetectThreatsAndAlertsMCAS-InteractiveGuide)
- [<span data-ttu-id="2c60f-136">Undersöka och åtgärda hot med Microsoft Defender för slut punkten</span><span class="sxs-lookup"><span data-stu-id="2c60f-136">Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
