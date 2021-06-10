---
title: Granska aviseringar i Microsoft Defender för Slutpunkt
description: Granska aviseringsinformation, inklusive en visualiserad aviseringsartikel och information för varje steg i kedjan.
keywords: incidenter, incidenter, datorer, enheter, användare, aviseringar, avisering, undersökning, diagram, bevis
ms.prod: m365-security
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: daniha
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.date: 5/1/2020
ms.technology: mde
ms.openlocfilehash: b17af7931b181a5fa30271a3eee07c7abf10a010
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844028"
---
# <a name="review-alerts-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="5779d-104">Granska aviseringar i Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="5779d-104">Review alerts in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5779d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="5779d-105">**Applies to:**</span></span>
- [<span data-ttu-id="5779d-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="5779d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="5779d-107">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="5779d-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5779d-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="5779d-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-managealerts-abovefoldlink)

<span data-ttu-id="5779d-109">Aviseringssidan i Microsoft Defender för Slutpunkt ger full kontext för aviseringen genom att kombinera attacksignaler och aviseringar relaterade till den valda aviseringen för att skapa en detaljerad aviseringsartikel.</span><span class="sxs-lookup"><span data-stu-id="5779d-109">The alert page in Microsoft Defender for Endpoint provides full context to the alert, by combining attack signals and alerts related to the selected alert, to construct a detailed alert story.</span></span>

<span data-ttu-id="5779d-110">Du kan snabbt organisera, undersöka och vidta effektiva åtgärder på aviseringar som påverkar organisationen.</span><span class="sxs-lookup"><span data-stu-id="5779d-110">Quickly triage, investigate, and take effective action on alerts that affect your organization.</span></span> <span data-ttu-id="5779d-111">Förstå varför de utlöstes och deras påverkan från en plats.</span><span class="sxs-lookup"><span data-stu-id="5779d-111">Understand why they were triggered, and their impact from one location.</span></span> <span data-ttu-id="5779d-112">Läs mer i den här översikten.</span><span class="sxs-lookup"><span data-stu-id="5779d-112">Learn more in this overview.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4yiO5]

## <a name="getting-started-with-an-alert"></a><span data-ttu-id="5779d-113">Komma igång med en avisering</span><span class="sxs-lookup"><span data-stu-id="5779d-113">Getting started with an alert</span></span>

<span data-ttu-id="5779d-114">Om du väljer namnet på en avisering i Defender för Endpoint hamnar du på aviseringssidan.</span><span class="sxs-lookup"><span data-stu-id="5779d-114">Selecting an alert's name in Defender for Endpoint will land you on its alert page.</span></span> <span data-ttu-id="5779d-115">På aviseringssidan visas all information i samband med den valda aviseringen.</span><span class="sxs-lookup"><span data-stu-id="5779d-115">On the alert page, all the information will be shown in context of the selected alert.</span></span> <span data-ttu-id="5779d-116">Varje aviseringssida består av 4 avsnitt:</span><span class="sxs-lookup"><span data-stu-id="5779d-116">Each alert page consists of 4 sections:</span></span>

1. <span data-ttu-id="5779d-117">**Aviseringsrubriken** visar aviseringens namn och finns där för att påminna dig om vilken avisering som startade den aktuella undersökningen oavsett vad du valde på sidan.</span><span class="sxs-lookup"><span data-stu-id="5779d-117">**The alert title** shows the alert's name and is there to remind you which alert started your current investigation regardless of what you have selected on the page.</span></span>
2. <span data-ttu-id="5779d-118">[**Berörda tillgångar**](#review-affected-assets) visar korten för enheter och användare som påverkas av den här aviseringen som kan klickas för ytterligare information och åtgärder.</span><span class="sxs-lookup"><span data-stu-id="5779d-118">[**Affected assets**](#review-affected-assets) lists cards of devices and users affected by this alert that are clickable for further information and actions.</span></span>
3. <span data-ttu-id="5779d-119">I **aviseringsartikeln** visas alla enheter som är relaterade till aviseringen, sammankopplade med en trädvy.</span><span class="sxs-lookup"><span data-stu-id="5779d-119">The **alert story** displays all entities related to the alert, interconnected by a tree view.</span></span> <span data-ttu-id="5779d-120">Aviseringen i rubriken kommer att vara den som är i fokus när du först kommer till den valda aviseringens sida.</span><span class="sxs-lookup"><span data-stu-id="5779d-120">The alert in the title will be the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="5779d-121">Enheter i aviseringsinformationen är expanderbara och klickbara, för att ge ytterligare information och underlätta svar genom att göra det möjligt att vidta åtgärder direkt i kontexten för aviseringssidan.</span><span class="sxs-lookup"><span data-stu-id="5779d-121">Entities in the alert story are expandable and clickable, to provide additional information and expedite response by allowing you to take actions right in the context of the alert page.</span></span> <span data-ttu-id="5779d-122">Använd aviseringsartikeln för att starta din undersökning.</span><span class="sxs-lookup"><span data-stu-id="5779d-122">Use the alert story to start your investigation.</span></span> <span data-ttu-id="5779d-123">Läs mer i [Undersöka aviseringar i Microsoft Defender för Slutpunkt.](/microsoft-365/security/defender-endpoint/investigate-alerts)</span><span class="sxs-lookup"><span data-stu-id="5779d-123">Learn how in [Investigate alerts in Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/investigate-alerts).</span></span>
4. <span data-ttu-id="5779d-124">I **informationsfönstret** visas först information om den valda aviseringen med information och åtgärder relaterade till den här aviseringen.</span><span class="sxs-lookup"><span data-stu-id="5779d-124">The **details pane** will show the details of the selected alert at first, with details and actions related to this alert.</span></span> <span data-ttu-id="5779d-125">Om du väljer någon av de berörda tillgångarna eller enheterna i aviseringsinformationen ändras informationsfönstret för att ge sammanhangsberoende information och åtgärder för det valda objektet.</span><span class="sxs-lookup"><span data-stu-id="5779d-125">If you select any of the affected assets or entities in the alert story, the details pane will change to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="5779d-126">Observera identifieringsstatus för din avisering.</span><span class="sxs-lookup"><span data-stu-id="5779d-126">Note the detection status for your alert.</span></span> 
- <span data-ttu-id="5779d-127">Förhindrades – Den misstänkta åtgärden som du försökte undvika.</span><span class="sxs-lookup"><span data-stu-id="5779d-127">Prevented – The attempted suspicious action was avoided.</span></span> <span data-ttu-id="5779d-128">Till exempel har en fil antingen inte skrivits på disken eller körts.</span><span class="sxs-lookup"><span data-stu-id="5779d-128">For example, a file either wasn’t written to disk or executed.</span></span>
<span data-ttu-id="5779d-129">![En aviseringssida som visar att hot har förhindrats](images/detstat-prevented.png)</span><span class="sxs-lookup"><span data-stu-id="5779d-129">![An alert page showing threat was prevented](images/detstat-prevented.png)</span></span>
- <span data-ttu-id="5779d-130">Blockerad – Misstänkt beteende utfördes och blockerades sedan.</span><span class="sxs-lookup"><span data-stu-id="5779d-130">Blocked – Suspicious behavior was executed and then blocked.</span></span> <span data-ttu-id="5779d-131">En process utfördes till exempel, men eftersom misstänkt beteende därefter visades i den, avslutas processen.</span><span class="sxs-lookup"><span data-stu-id="5779d-131">For example, a process was executed but because it subsequently exhibited suspicious behaviors, the process was terminated.</span></span>
<span data-ttu-id="5779d-132">![En aviseringssida som visar att hot blockerades](images/detstat-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="5779d-132">![An alert page showing threat was blocked](images/detstat-blocked.png)</span></span>
- <span data-ttu-id="5779d-133">Upptäckt – En attack identifierades och är eventuellt fortfarande aktiv.</span><span class="sxs-lookup"><span data-stu-id="5779d-133">Detected – An attack was detected and is possibly still active.</span></span>
<span data-ttu-id="5779d-134">![En aviseringssida som visar att hot har upptäckts](images/detstat-detected.png)</span><span class="sxs-lookup"><span data-stu-id="5779d-134">![An alert page showing threat was detected](images/detstat-detected.png)</span></span>




<span data-ttu-id="5779d-135">Du kan sedan  också granska automatisk undersökningsinformation i aviseringens informationsfönster för att se vilka åtgärder som redan har vidtagits samt läsa beskrivningen av aviseringen för rekommenderade åtgärder.</span><span class="sxs-lookup"><span data-stu-id="5779d-135">You can then also review the *automated investigation details* in your alert's details pane, to see which actions were already taken, as well as reading the alert's description for recommended actions.</span></span>

![Ett avsnitt av informationsfönstret med aviseringsbeskrivningen och avsnitten för automatisk undersökning markerade](images/alert-air-and-alert-description.png)

<span data-ttu-id="5779d-137">Annan information som är tillgänglig i informationsfönstret när aviseringen öppnas innehåller MITRE-tekniker, källa och ytterligare kontextinformation.</span><span class="sxs-lookup"><span data-stu-id="5779d-137">Other information available in the details pane when the alert opens includes MITRE techniques, source, and additional contextual details.</span></span>




## <a name="review-affected-assets"></a><span data-ttu-id="5779d-138">Granska påverkade tillgångar</span><span class="sxs-lookup"><span data-stu-id="5779d-138">Review affected assets</span></span>

<span data-ttu-id="5779d-139">Om du väljer en enhet eller ett användarkort i avsnitten för de berörda tillgångarna växlas du till informationen om enheten eller användaren i informationsfönstret.</span><span class="sxs-lookup"><span data-stu-id="5779d-139">Selecting a device or a user card in the affected assets sections will switch to the details of the device or user in the details pane.</span></span>

- <span data-ttu-id="5779d-140">**För enheter** visar informationsfönstret information om själva enheten, som Domän, Operativsystem och IP.</span><span class="sxs-lookup"><span data-stu-id="5779d-140">**For devices**, the details pane will display information about the device itself, like Domain, Operating System, and IP.</span></span> <span data-ttu-id="5779d-141">Aktiva aviseringar och inloggade användare på enheten är också tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="5779d-141">Active alerts and the logged on users on that device are also available.</span></span> <span data-ttu-id="5779d-142">Du kan vidta åtgärder omedelbart genom att isolera enheten, begränsa appkörningen eller köra en antivirussökning.</span><span class="sxs-lookup"><span data-stu-id="5779d-142">You can take immediate action by isolating the device, restricting app execution, or running an antivirus scan.</span></span> <span data-ttu-id="5779d-143">Alternativt kan du samla in ett undersökningspaket, initiera en automatisk undersökning eller gå till enhetssidan för att undersöka ur enhetens perspektiv.</span><span class="sxs-lookup"><span data-stu-id="5779d-143">Alternatively, you could collect an investigation package, initiate an automated investigation, or go to the device page to investigate from the device's point of view.</span></span>

   ![Ett avsnitt av informationsfönstret när en enhet väljs](images/device-page-details.png)

- <span data-ttu-id="5779d-145">**För användare** visar informationsfönstret detaljerad användarinformation, till exempel användarens SAM-namn och SID, samt inloggningstyper som utförs av användaren och eventuella aviseringar och incidenter relaterade till den.</span><span class="sxs-lookup"><span data-stu-id="5779d-145">**For users**, the details pane will display detailed user information, such as the user's SAM name and SID, as well as logon types performed by this user and any alerts and incidents related to it.</span></span> <span data-ttu-id="5779d-146">Du kan välja *Öppna användarsida* för att fortsätta undersökningen från användarens perspektiv.</span><span class="sxs-lookup"><span data-stu-id="5779d-146">You can select *Open user page* to continue the investigation from that user's point of view.</span></span>

   ![Ett avsnitt av informationsfönstret när en användare väljs](images/user-page-details.png)


## <a name="related-topics"></a><span data-ttu-id="5779d-148">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="5779d-148">Related topics</span></span>

- [<span data-ttu-id="5779d-149">Visa och ordna incidentkön</span><span class="sxs-lookup"><span data-stu-id="5779d-149">View and organize the incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="5779d-150">Undersöka incidenter</span><span class="sxs-lookup"><span data-stu-id="5779d-150">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="5779d-151">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="5779d-151">Manage incidents</span></span>](manage-incidents.md)
