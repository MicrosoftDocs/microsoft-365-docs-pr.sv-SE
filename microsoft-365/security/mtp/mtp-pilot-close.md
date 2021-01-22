---
title: Sammanfattning av dina pilotresultat i Microsoft 365 Defender-projektet
description: Avsluta ditt pilotprojekt i Microsoft 365 Defender genom att fylla i ett styrkort, analysera dina rapportresultat och bestämma hur du ska gå framåt.
keywords: Microsoft Threat Protection-piloten, bestäm vad du ska göra härnäst efter att ha pilottestat Microsoft Threat Protection-projektet, vad du ska göra efter utvärdering av Microsoft Threat Protection i produktionen, övergång från Microsoft Threat Protection pilot till distribution, cybersäkerhet, avancerade beständiga hot, företagssäkerhet, enheter, enhet, identitet, användare, data, program, incidenter, automatiserad undersökning och åtgärd, avancerad sökning
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: c8608568301f11a20c940a5ff9f1c205ce6e48f1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930168"
---
# <a name="closing-and-summarizing-your-microsoft-365-defender-pilot"></a><span data-ttu-id="94e35-104">Stänga och sammanfatta din Pilot i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="94e35-104">Closing and summarizing your Microsoft 365 Defender pilot</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="94e35-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="94e35-105">**Applies to:**</span></span>
- <span data-ttu-id="94e35-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="94e35-106">Microsoft 365 Defender</span></span>



|<span data-ttu-id="94e35-107">[![Planering](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span><span class="sxs-lookup"><span data-stu-id="94e35-107">[![Planning](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span></span><br/>[<span data-ttu-id="94e35-108">Planering</span><span class="sxs-lookup"><span data-stu-id="94e35-108">Planning</span></span>](mtp-pilot-plan.md) |<span data-ttu-id="94e35-109">[![Förbereda](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="94e35-109">[![Prepare](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="94e35-110">Förberedelse</span><span class="sxs-lookup"><span data-stu-id="94e35-110">Preparation</span></span>](prepare-mtpeval.md) | <span data-ttu-id="94e35-111">[![Simulera attack](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)</span><span class="sxs-lookup"><span data-stu-id="94e35-111">[![Simulate attack](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)</span></span><br/>[<span data-ttu-id="94e35-112">Simulera attack</span><span class="sxs-lookup"><span data-stu-id="94e35-112">Simulate attack</span></span>](mtp-pilot-simulate.md) | ![Stäng och sammanfatta](../../media/phase-diagrams/4-summary.png)<br/><span data-ttu-id="94e35-114">Stäng och sammanfatta</span><span class="sxs-lookup"><span data-stu-id="94e35-114">Close and summarize</span></span>|
|--|--|--|--|
|| | |<span data-ttu-id="94e35-115">*Du är här!*</span><span class="sxs-lookup"><span data-stu-id="94e35-115">*You are here!*</span></span>|


<span data-ttu-id="94e35-116">Du befinner dig för närvarande i den avslutande och sammanfattande fasen.</span><span class="sxs-lookup"><span data-stu-id="94e35-116">You're currently in the closing and summarizing phase.</span></span>

<span data-ttu-id="94e35-117">Du har precis kört en avancerad minnesstyrd attackattack som körde kod på en domänkontrollant på distans.</span><span class="sxs-lookup"><span data-stu-id="94e35-117">You’ve just ran an advanced memory-only attack simulation that executed code remotely on a domain controller.</span></span> <span data-ttu-id="94e35-118">Du har sett hur Microsoft Defender för Endpoint och Microsoft Defender för identitet identifierar och skapar aviseringar om skadlig aktivitet.</span><span class="sxs-lookup"><span data-stu-id="94e35-118">You’ve seen how Microsoft Defender for Endpoint and Microsoft Defender for Identity detect and create alerts on stealthy malicious activity.</span></span> <span data-ttu-id="94e35-119">Du har också sett hur aviseringar från olika källor levereras tillsammans med annan kontextinformation till en enda incident i Microsoft 365 Säkerhetscenter-portalen.</span><span class="sxs-lookup"><span data-stu-id="94e35-119">You’ve also seen how alerts from different sources are delivered along with other contextual information into a single incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="94e35-120">Genom att uppleva sådan integrering kan SOC-analytiker undersöka och vidta nödvändiga åtgärder.</span><span class="sxs-lookup"><span data-stu-id="94e35-120">Experiencing such integration enables SOC analysts to investigate and take necessary action.</span></span> <span data-ttu-id="94e35-121">Du har också skapat en avancerad fråga för sökning som identifierar inkommande e-postmeddelanden där användaren öppnade eller sparade den bifogade filen och skapade identifieringen baserat på den frågan.</span><span class="sxs-lookup"><span data-stu-id="94e35-121">You’ve also created an advanced hunting query that will identify inbound emails where the user opened or saved the attachment and created detection based on that query.</span></span>

<span data-ttu-id="94e35-122">Du har nått slutet av processen när alla tester är slutförda.</span><span class="sxs-lookup"><span data-stu-id="94e35-122">You’ve reached the end of the process after all tests have concluded.</span></span>

<span data-ttu-id="94e35-123">De slutliga resultaten bör vara:</span><span class="sxs-lookup"><span data-stu-id="94e35-123">The final output should be:</span></span>

- <span data-ttu-id="94e35-124">Ett slutfört styrkort</span><span class="sxs-lookup"><span data-stu-id="94e35-124">A completed scorecard</span></span>
- <span data-ttu-id="94e35-125">En detaljerad rapport över pilotens resultat</span><span class="sxs-lookup"><span data-stu-id="94e35-125">A detailed report of the findings of the pilot</span></span>
- <span data-ttu-id="94e35-126">Ett beslut om hur du ska gå framåt</span><span class="sxs-lookup"><span data-stu-id="94e35-126">A decision on how to move forward</span></span>

<span data-ttu-id="94e35-127">Presentera rapporter från dina slutliga resultat för interna intressenter (som du har identifierat under [förberedelsefasen)](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) och Microsoft-kontakter.</span><span class="sxs-lookup"><span data-stu-id="94e35-127">Present the reports from your final output to internal stakeholders (which you’ve identified during the [preparation](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) phase) and Microsoft contacts.</span></span> <span data-ttu-id="94e35-128">Ett sådant arbete säkerställer att all feedback kan användas för att förbättra produkter och dokumentation.</span><span class="sxs-lookup"><span data-stu-id="94e35-128">Such an effort ensures that any feedback can be used to improve products and documentation.</span></span>

<span data-ttu-id="94e35-129">Vi hoppas att du tyckte om den här simuleringen.</span><span class="sxs-lookup"><span data-stu-id="94e35-129">We hope you enjoyed this simulation.</span></span> <span data-ttu-id="94e35-130">Börja implementera det du har lärt dig i större skala i organisationen för att få ut mesta av den integrerade säkerhetslösningen.</span><span class="sxs-lookup"><span data-stu-id="94e35-130">Start implementing what you've learned on a larger scale in your organization to get the most out of the integrated security solution.</span></span>

## <a name="next-step"></a><span data-ttu-id="94e35-131">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="94e35-131">Next step</span></span>
<span data-ttu-id="94e35-132">Läs mer om Microsoft 365 Defender-pelarna med följande interaktiva guider:</span><span class="sxs-lookup"><span data-stu-id="94e35-132">Learn more about the Microsoft 365 Defender pillars through the following interactive guides:</span></span>
- [<span data-ttu-id="94e35-133">Skydda din organisation med Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="94e35-133">Safeguard your organization with Microsoft Defender for Office 365</span></span>](https://aka.ms/O365ATP-Interactive-Guide)
- [<span data-ttu-id="94e35-134">Identifiera misstänkta aktiviteter och potentiella attacker med Microsoft Defender för identitet</span><span class="sxs-lookup"><span data-stu-id="94e35-134">Detect suspicious activities and potential attacks with Microsoft Defender for Identity</span></span>](https://aka.ms/AATP-Interactive-Guide)
- [<span data-ttu-id="94e35-135">Identifiera hot och hantera aviseringar med Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="94e35-135">Detect threats and manage alerts with Microsoft Cloud App Security</span></span>](https://aka.ms/DetectThreatsAndAlertsMCAS-InteractiveGuide)
- [<span data-ttu-id="94e35-136">Undersöka och åtgärda hot med Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="94e35-136">Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
