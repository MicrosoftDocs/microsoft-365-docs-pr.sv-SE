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
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 2b8872288291adc0b9fc5e1c1541f885711df230
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356709"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a><span data-ttu-id="746b4-104">Automatisk undersökning och svar i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="746b4-104">Automated investigation and response in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="746b4-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="746b4-105">**Applies to:**</span></span>
- <span data-ttu-id="746b4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="746b4-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="746b4-107">Vill du uppleva Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="746b4-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="746b4-108">Du kan [utvärdera det i en labb miljö](https://aka.ms/mtp-trial-lab) eller [köra ett pilot projekt i produktionen](https://aka.ms/m365d-pilotplaybook).</span><span class="sxs-lookup"><span data-stu-id="746b4-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

<span data-ttu-id="746b4-109">När säkerhets varningar utlöses är det upp till din säkerhets åtgärds grupp för att titta på dessa meddelanden och vidta åtgärder för att skydda din organisation.</span><span class="sxs-lookup"><span data-stu-id="746b4-109">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="746b4-110">Det kan ta väldigt lång tid att prioritera och undersöka aviseringar, särskilt när nya meddelanden fortsätter när en undersökning pågår.</span><span class="sxs-lookup"><span data-stu-id="746b4-110">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="746b4-111">Säkerhets Operations team kan känna av sig som skir volymen av de hot som de måste övervaka och skydda mot.</span><span class="sxs-lookup"><span data-stu-id="746b4-111">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="746b4-112">Automatisk utredning och svars kapacitet, med själv återställning, i Microsoft 365 Defender kan hjälpa dig.</span><span class="sxs-lookup"><span data-stu-id="746b4-112">Automated investigation and response capabilities, with self-healing, in Microsoft 365 Defender can help.</span></span>

<span data-ttu-id="746b4-113">Titta på följande video för att se hur själv återställning fungerar:</span><span class="sxs-lookup"><span data-stu-id="746b4-113">Watch the following video to see how self-healing works:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="746b4-114">I Microsoft 365 Defender går det att automatisera undersökningar och svar med själv lagnings funktion på dina enheter, e-& innehåll och identiteter.</span><span class="sxs-lookup"><span data-stu-id="746b4-114">In Microsoft 365 Defender, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span> <span data-ttu-id="746b4-115">I Microsoft 365 Defender samlas funktioner från:</span><span class="sxs-lookup"><span data-stu-id="746b4-115">Microsoft 365 Defender brings together capabilities from:</span></span> 
- [<span data-ttu-id="746b4-116">Automatisk undersökning och reparation i Microsoft Defender för slut punkt</span><span class="sxs-lookup"><span data-stu-id="746b4-116">Automated investigation and remediation in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [<span data-ttu-id="746b4-117">Automatisk undersökning och svar i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="746b4-117">Automated investigation and response in Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
- [<span data-ttu-id="746b4-118">Avancerad hot identifiering för Azure</span><span class="sxs-lookup"><span data-stu-id="746b4-118">Azure advanced threat detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)
- [<span data-ttu-id="746b4-119">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="746b4-119">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
 
<span data-ttu-id="746b4-120">I den här artikeln beskrivs hur automatisk undersökning och svar fungerar.</span><span class="sxs-lookup"><span data-stu-id="746b4-120">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="746b4-121">Information om hur du konfigurerar de här funktionerna finns i [Konfigurera automatiserade undersökningar och svars funktioner i Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span><span class="sxs-lookup"><span data-stu-id="746b4-121">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>

## <a name="your-virtual-analyst"></a><span data-ttu-id="746b4-122">Din virtuella analytiker</span><span class="sxs-lookup"><span data-stu-id="746b4-122">Your virtual analyst</span></span>

<span data-ttu-id="746b4-123">Föreställ dig att du har en virtuell analys i ditt team för säkerhets åtgärder för nivå 1/nivå 2.</span><span class="sxs-lookup"><span data-stu-id="746b4-123">Imagine having a virtual analyst in your Tier 1 / Tier 2 security operations team.</span></span> <span data-ttu-id="746b4-124">Den virtuella analytikern imiterar de idealiska stegen som säkerhets åtgärder skulle vidta för att undersöka och åtgärda hot.</span><span class="sxs-lookup"><span data-stu-id="746b4-124">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="746b4-125">Den virtuella assistenten kan arbeta dygnet runt, med obegränsad kapacitet och få en omfattande inläsning av undersökningar och hot.</span><span class="sxs-lookup"><span data-stu-id="746b4-125">The virtual assistant could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="746b4-126">En sådan virtuell assistent kan avsevärt minska tiden för att svara och på så sätt frigöra dina säkerhets åtgärder för andra viktiga strategiska projekt.</span><span class="sxs-lookup"><span data-stu-id="746b4-126">Such a virtual assistant could significantly reduce the time to respond, freeing up your security operations team for other important strategic projects.</span></span> <span data-ttu-id="746b4-127">Om det här scenariot liknar vetenskaps gilla är det inte!</span><span class="sxs-lookup"><span data-stu-id="746b4-127">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="746b4-128">En sådan virtuell analytiker är en del av Microsoft 365 Defender-sviten och dess namn är *automatiserad undersökning och svar*.</span><span class="sxs-lookup"><span data-stu-id="746b4-128">Such a virtual analyst is part of your Microsoft 365 Defender suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="746b4-129">Med den automatiska undersökningen och svaret kan säkerhets åtgärds gruppen markant öka organisationens kapacitet att hantera säkerhets varningar och-händelser.</span><span class="sxs-lookup"><span data-stu-id="746b4-129">Automated investigation and response enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="746b4-130">Genom att automatisera undersökningar och svar kan du minska kostnaderna för att hantera undersökningar och reparations aktiviteter och få ut mesta möjliga av skydds paketet.</span><span class="sxs-lookup"><span data-stu-id="746b4-130">With automated investigation and response, you can reduce the cost of dealing with investigation and remediation activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="746b4-131">automatisk undersökning och svar hjälper din säkerhets åtgärd att:</span><span class="sxs-lookup"><span data-stu-id="746b4-131">automated investigation and response helps your security operations team by:</span></span>

1. <span data-ttu-id="746b4-132">Avgöra om ett hot kräver en åtgärd;</span><span class="sxs-lookup"><span data-stu-id="746b4-132">Determining whether a threat requires action;</span></span>
2. <span data-ttu-id="746b4-133">Utföra (eller rekommendera) alla nödvändiga reparations åtgärder;</span><span class="sxs-lookup"><span data-stu-id="746b4-133">Performing (or recommending) any necessary remediation actions;</span></span>
3. <span data-ttu-id="746b4-134">Avgöra vilka ytterligare undersökningar som bör uppstå; och</span><span class="sxs-lookup"><span data-stu-id="746b4-134">Determining what additional investigations should occur; and</span></span>
4. <span data-ttu-id="746b4-135">Upprepa processen när det behövs för andra aviseringar.</span><span class="sxs-lookup"><span data-stu-id="746b4-135">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="746b4-136">Den automatiserade gransknings processen</span><span class="sxs-lookup"><span data-stu-id="746b4-136">The automated investigation process</span></span>

<span data-ttu-id="746b4-137">**Avisering**  >  **incident**  >  **Automatisk undersökning**  >  **Verdict**  >  **reparations åtgärd**</span><span class="sxs-lookup"><span data-stu-id="746b4-137">**Alert** > **incident** > **automated investigation** > **verdict** > **remediation action**</span></span>

<span data-ttu-id="746b4-138">En utlöst varning skapar en olycka som kan starta en automatiserad undersökning.</span><span class="sxs-lookup"><span data-stu-id="746b4-138">A triggered alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="746b4-139">Denna undersökning kan resultera i en eller flera reparations åtgärder.</span><span class="sxs-lookup"><span data-stu-id="746b4-139">That investigation can result in one or more remediation actions.</span></span> <span data-ttu-id="746b4-140">I Microsoft 365 Defender är varje automatiserad undersökning en översikt över Microsoft Defender för identitet, Microsoft Defender för slut punkt och Defender för Office 365, som sammanfattas i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="746b4-140">In Microsoft 365 Defender, each automated investigation correlates signals across Microsoft Defender for Identity, Microsoft Defender for Endpoint, and Defender for Office 365, as summarized in the following table:</span></span> 

|<span data-ttu-id="746b4-141">Posterna</span><span class="sxs-lookup"><span data-stu-id="746b4-141">Entities</span></span> |<span data-ttu-id="746b4-142">Hot Protection Services</span><span class="sxs-lookup"><span data-stu-id="746b4-142">Threat protection services</span></span>  |
|---------|---------|
|<span data-ttu-id="746b4-143">Enheter (kallas även slut punkter)</span><span class="sxs-lookup"><span data-stu-id="746b4-143">Devices (also referred to as endpoints)</span></span>     |[<span data-ttu-id="746b4-144">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="746b4-144">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[<span data-ttu-id="746b4-145">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="746b4-145">Microsoft Defender for Identity</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="746b4-146">E-postinnehåll (filer och meddelanden i post lådor)</span><span class="sxs-lookup"><span data-stu-id="746b4-146">Email content (files and messages in mailboxes)</span></span>     |[<span data-ttu-id="746b4-147">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="746b4-147">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

<span data-ttu-id="746b4-148">Varje undersökning ger upphov till verdicts (*skadlig*, *misstänkt* eller *Inga hot*) för varje undersöknings bevis.</span><span class="sxs-lookup"><span data-stu-id="746b4-148">Each investigation generates verdicts (*Malicious*, *Suspicious*, or *No threats found*) for each piece of evidence investigated.</span></span> <span data-ttu-id="746b4-149">Beroende på typen av hot och resulterande Verdict inträffar reparations åtgärder automatiskt eller efter godkännande av organisationens säkerhets åtgärds team.</span><span class="sxs-lookup"><span data-stu-id="746b4-149">Depending on the type of threat and resulting verdict, remediation actions occur automatically or upon approval by your organization's security operations team.</span></span> <span data-ttu-id="746b4-150">Pågående och slutförda åtgärder visas i [Åtgärds centret](mtp-action-center.md).</span><span class="sxs-lookup"><span data-stu-id="746b4-150">Pending and completed actions are listed in the [Action center](mtp-action-center.md).</span></span>

<span data-ttu-id="746b4-151">När en undersökning körs läggs eventuella andra relaterade aviseringar till i undersökningen tills den är klar.</span><span class="sxs-lookup"><span data-stu-id="746b4-151">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="746b4-152">Om en incriminated-enhet visas någon annan stans expanderar den automatiserade undersökningen dess omfattning för att inkludera den enheten och en allmän säkerhets Playbook körs.</span><span class="sxs-lookup"><span data-stu-id="746b4-152">If an incriminated entity is seen elsewhere, the automated investigation will expand its scope to include that entity, and a general security playbook will run.</span></span> 

> [!NOTE]
> <span data-ttu-id="746b4-153">Alla notifieringar utlöser en automatiserad undersökning och alla undersöknings resultat leder till automatiska reparations åtgärder; Detta beror på hur automatisk undersökning och svar är konfigurerat för din organisation.</span><span class="sxs-lookup"><span data-stu-id="746b4-153">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions; this all depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="746b4-154">Mer information finns i [Konfigurera automatiserade undersökningar och svars funktioner i Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span><span class="sxs-lookup"><span data-stu-id="746b4-154">See [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="746b4-155">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="746b4-155">Next steps</span></span>

- [<span data-ttu-id="746b4-156">Se förutsättningarna för automatisk undersökning och svar i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="746b4-156">See the prerequisites for automated investigation and response in Microsoft 365 Defender</span></span>](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [<span data-ttu-id="746b4-157">Konfigurera automatisk undersökning och svar för organisationen</span><span class="sxs-lookup"><span data-stu-id="746b4-157">Configure automated investigation and response for your organization</span></span>](mtp-configure-auto-investigation-response.md)
- [<span data-ttu-id="746b4-158">Läs mer om åtgärds Center</span><span class="sxs-lookup"><span data-stu-id="746b4-158">Learn more about the Action center</span></span>](mtp-action-center.md)
