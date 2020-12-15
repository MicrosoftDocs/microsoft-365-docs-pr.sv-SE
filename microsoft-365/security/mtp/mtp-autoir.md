---
title: Automatisk undersökning och svar i Microsoft 365 Defender
description: Få en översikt över automatiserade undersökningar och svars funktioner, även kallat själv återställning, i Microsoft 365 Defender
keywords: automatiserad, undersökning, avisering, utlösare, åtgärd, reparation, själv återställning
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 7c28b7f3ac797f7402cfdb1f604fcef1e142a31b
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683313"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a><span data-ttu-id="1b288-104">Automatisk undersökning och svar i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1b288-104">Automated investigation and response in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1b288-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="1b288-105">**Applies to:**</span></span>
- <span data-ttu-id="1b288-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1b288-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="1b288-107">Vill du uppleva Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="1b288-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="1b288-108">Du kan [utvärdera det i en labb miljö](https://aka.ms/mtp-trial-lab) eller [köra ett pilot projekt i produktionen](https://aka.ms/m365d-pilotplaybook).</span><span class="sxs-lookup"><span data-stu-id="1b288-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

## <a name="how-automated-investigation-and-self-healing-works"></a><span data-ttu-id="1b288-109">Hur automatisk undersökning och själv återställning fungerar</span><span class="sxs-lookup"><span data-stu-id="1b288-109">How automated investigation and self-healing works</span></span>

<span data-ttu-id="1b288-110">När säkerhets varningar utlöses är det upp till din säkerhets åtgärds grupp för att titta på dessa meddelanden och vidta åtgärder för att skydda din organisation.</span><span class="sxs-lookup"><span data-stu-id="1b288-110">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="1b288-111">Det kan ta väldigt lång tid att prioritera och undersöka aviseringar, särskilt när nya meddelanden fortsätter när en undersökning pågår.</span><span class="sxs-lookup"><span data-stu-id="1b288-111">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="1b288-112">Säkerhets Operations team kan känna av sig som skir volymen av de hot som de måste övervaka och skydda mot.</span><span class="sxs-lookup"><span data-stu-id="1b288-112">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="1b288-113">Automatisk utredning och svars kapacitet, med själv återställning, i Microsoft 365 Defender kan hjälpa dig.</span><span class="sxs-lookup"><span data-stu-id="1b288-113">Automated investigation and response capabilities, with self-healing, in Microsoft 365 Defender can help.</span></span>

<span data-ttu-id="1b288-114">Titta på följande video för att se hur själv återställning fungerar:</span><span class="sxs-lookup"><span data-stu-id="1b288-114">Watch the following video to see how self-healing works:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="1b288-115">I Microsoft 365 Defender går det att automatisera undersökningar och svar med själv lagnings funktion på dina enheter, e-& innehåll och identiteter.</span><span class="sxs-lookup"><span data-stu-id="1b288-115">In Microsoft 365 Defender, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span>
 
> [!TIP]
> <span data-ttu-id="1b288-116">I den här artikeln beskrivs hur automatisk undersökning och svar fungerar.</span><span class="sxs-lookup"><span data-stu-id="1b288-116">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="1b288-117">Information om hur du konfigurerar de här funktionerna finns i [Konfigurera automatiserade undersökningar och svars funktioner i Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span><span class="sxs-lookup"><span data-stu-id="1b288-117">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>

## <a name="your-own-virtual-analyst"></a><span data-ttu-id="1b288-118">Din egen virtuella analytiker</span><span class="sxs-lookup"><span data-stu-id="1b288-118">Your own virtual analyst</span></span>

<span data-ttu-id="1b288-119">Föreställ dig att du har en virtuell analys i ditt team för säkerhets åtgärder för nivå 1/nivå 2.</span><span class="sxs-lookup"><span data-stu-id="1b288-119">Imagine having a virtual analyst in your Tier 1 / Tier 2 security operations team.</span></span> <span data-ttu-id="1b288-120">Den virtuella analytikern imiterar de idealiska stegen som säkerhets åtgärder skulle vidta för att undersöka och åtgärda hot.</span><span class="sxs-lookup"><span data-stu-id="1b288-120">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="1b288-121">Den virtuella assistenten kan arbeta dygnet runt, med obegränsad kapacitet och få en omfattande inläsning av undersökningar och hot.</span><span class="sxs-lookup"><span data-stu-id="1b288-121">The virtual assistant could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="1b288-122">En sådan virtuell assistent kan avsevärt minska tiden för att svara och på så sätt frigöra dina säkerhets åtgärder för andra viktiga strategiska projekt.</span><span class="sxs-lookup"><span data-stu-id="1b288-122">Such a virtual assistant could significantly reduce the time to respond, freeing up your security operations team for other important strategic projects.</span></span> <span data-ttu-id="1b288-123">Om det här scenariot liknar vetenskaps gilla är det inte!</span><span class="sxs-lookup"><span data-stu-id="1b288-123">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="1b288-124">En sådan virtuell analytiker är en del av Microsoft 365 Defender-sviten och dess namn är *automatiserad undersökning och svar*.</span><span class="sxs-lookup"><span data-stu-id="1b288-124">Such a virtual analyst is part of your Microsoft 365 Defender suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="1b288-125">Med den automatiska undersökningen och svaret kan säkerhets åtgärds gruppen markant öka organisationens kapacitet att hantera säkerhets varningar och-händelser.</span><span class="sxs-lookup"><span data-stu-id="1b288-125">Automated investigation and response enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="1b288-126">Genom att automatisera undersökningar och svar kan du minska kostnaderna för att hantera undersökningar och reparations aktiviteter och få ut mesta möjliga av skydds paketet.</span><span class="sxs-lookup"><span data-stu-id="1b288-126">With automated investigation and response, you can reduce the cost of dealing with investigation and remediation activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="1b288-127">automatisk undersökning och svar hjälper din säkerhets åtgärd att:</span><span class="sxs-lookup"><span data-stu-id="1b288-127">automated investigation and response helps your security operations team by:</span></span>

1. <span data-ttu-id="1b288-128">Avgöra om ett hot kräver en åtgärd;</span><span class="sxs-lookup"><span data-stu-id="1b288-128">Determining whether a threat requires action;</span></span>
2. <span data-ttu-id="1b288-129">Utföra (eller rekommendera) alla nödvändiga reparations åtgärder;</span><span class="sxs-lookup"><span data-stu-id="1b288-129">Performing (or recommending) any necessary remediation actions;</span></span>
3. <span data-ttu-id="1b288-130">Avgöra vilka ytterligare undersökningar som bör uppstå; och</span><span class="sxs-lookup"><span data-stu-id="1b288-130">Determining what additional investigations should occur; and</span></span>
4. <span data-ttu-id="1b288-131">Upprepa processen när det behövs för andra aviseringar.</span><span class="sxs-lookup"><span data-stu-id="1b288-131">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="1b288-132">Den automatiserade gransknings processen</span><span class="sxs-lookup"><span data-stu-id="1b288-132">The automated investigation process</span></span>

<span data-ttu-id="1b288-133">**Avisering**  >  **incident**  >  **Automatisk undersökning**  >  **Verdict**  >  **reparations åtgärd**</span><span class="sxs-lookup"><span data-stu-id="1b288-133">**Alert** > **incident** > **automated investigation** > **verdict** > **remediation action**</span></span>

<span data-ttu-id="1b288-134">En utlöst varning skapar en olycka som kan starta en automatiserad undersökning.</span><span class="sxs-lookup"><span data-stu-id="1b288-134">A triggered alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="1b288-135">Denna undersökning kan resultera i en eller flera reparations åtgärder.</span><span class="sxs-lookup"><span data-stu-id="1b288-135">That investigation can result in one or more remediation actions.</span></span> <span data-ttu-id="1b288-136">I Microsoft 365 Defender är varje automatiserad undersökning en översikt över Microsoft Defender för identitet, Microsoft Defender för slut punkt och Defender för Office 365, som sammanfattas i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="1b288-136">In Microsoft 365 Defender, each automated investigation correlates signals across Microsoft Defender for Identity, Microsoft Defender for Endpoint, and Defender for Office 365, as summarized in the following table:</span></span> 

|<span data-ttu-id="1b288-137">Posterna</span><span class="sxs-lookup"><span data-stu-id="1b288-137">Entities</span></span> |<span data-ttu-id="1b288-138">Hot Protection Services</span><span class="sxs-lookup"><span data-stu-id="1b288-138">Threat protection services</span></span>  |
|---------|---------|
|<span data-ttu-id="1b288-139">Enheter (kallas även slut punkter)</span><span class="sxs-lookup"><span data-stu-id="1b288-139">Devices (also referred to as endpoints)</span></span>     |[<span data-ttu-id="1b288-140">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="1b288-140">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[<span data-ttu-id="1b288-141">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="1b288-141">Microsoft Defender for Identity</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="1b288-142">E-postinnehåll (filer och meddelanden i post lådor)</span><span class="sxs-lookup"><span data-stu-id="1b288-142">Email content (files and messages in mailboxes)</span></span>     |[<span data-ttu-id="1b288-143">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="1b288-143">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

<span data-ttu-id="1b288-144">Varje undersökning ger upphov till verdicts (*skadlig*, *misstänkt* eller *Inga hot*) för varje undersöknings bevis.</span><span class="sxs-lookup"><span data-stu-id="1b288-144">Each investigation generates verdicts (*Malicious*, *Suspicious*, or *No threats found*) for each piece of evidence investigated.</span></span> <span data-ttu-id="1b288-145">Beroende på typen av hot och resulterande Verdict inträffar reparations åtgärder automatiskt eller efter godkännande av organisationens säkerhets åtgärds team.</span><span class="sxs-lookup"><span data-stu-id="1b288-145">Depending on the type of threat and resulting verdict, remediation actions occur automatically or upon approval by your organization's security operations team.</span></span> <span data-ttu-id="1b288-146">Pågående och slutförda åtgärder visas i [Åtgärds centret](mtp-action-center.md).</span><span class="sxs-lookup"><span data-stu-id="1b288-146">Pending and completed actions are listed in the [Action center](mtp-action-center.md).</span></span>

<span data-ttu-id="1b288-147">När en undersökning körs läggs eventuella andra relaterade aviseringar till i undersökningen tills den är klar.</span><span class="sxs-lookup"><span data-stu-id="1b288-147">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="1b288-148">Om en incriminated-enhet visas någon annan stans expanderar den automatiserade undersökningen dess omfattning för att inkludera den enheten och en allmän säkerhets Playbook körs.</span><span class="sxs-lookup"><span data-stu-id="1b288-148">If an incriminated entity is seen elsewhere, the automated investigation will expand its scope to include that entity, and a general security playbook will run.</span></span> 

> [!NOTE]
> <span data-ttu-id="1b288-149">Alla notifieringar utlöser en automatiserad undersökning och alla undersöknings resultat leder till automatiska reparations åtgärder; Detta beror på hur automatisk undersökning och svar är konfigurerat för din organisation.</span><span class="sxs-lookup"><span data-stu-id="1b288-149">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions; this all depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="1b288-150">Mer information finns i [Konfigurera automatiserade undersökningar och svars funktioner i Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span><span class="sxs-lookup"><span data-stu-id="1b288-150">See [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="1b288-151">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="1b288-151">Next steps</span></span>

- [<span data-ttu-id="1b288-152">Se förutsättningarna för automatisk undersökning och svar i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1b288-152">See the prerequisites for automated investigation and response in Microsoft 365 Defender</span></span>](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [<span data-ttu-id="1b288-153">Konfigurera automatisk undersökning och svar för organisationen</span><span class="sxs-lookup"><span data-stu-id="1b288-153">Configure automated investigation and response for your organization</span></span>](mtp-configure-auto-investigation-response.md)
- [<span data-ttu-id="1b288-154">Läs mer om åtgärds Center</span><span class="sxs-lookup"><span data-stu-id="1b288-154">Learn more about the Action center</span></span>](mtp-action-center.md)
