---
title: Microsoft Threat Experts
ms.reviewer: ''
description: Microsoft Threat Experts tillhandahåller ytterligare ett expertlager till Microsoft Defender för Endpoint.
keywords: tjänst för hanterad hotsökning, hanterad hotsökning, mdr-tjänst (managed detection and response), MTE, Microsoft Threat Experts, MTE-TAN, riktad attackavisering, riktad attackavisering
search.product: Windows 10
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 466e67bb4649f8cf87e4152a07122d57c5071b79
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185581"
---
# <a name="microsoft-threat-experts"></a><span data-ttu-id="e4f9f-104">Microsoft Threat Experts</span><span class="sxs-lookup"><span data-stu-id="e4f9f-104">Microsoft Threat Experts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e4f9f-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="e4f9f-105">**Applies to:**</span></span>
- [<span data-ttu-id="e4f9f-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="e4f9f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e4f9f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e4f9f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e4f9f-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="e4f9f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e4f9f-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="e4f9f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="e4f9f-110">Microsoft Threat Experts är en hanterad tjänst för hot efter hot som förser ditt säkerhetscenter med övervakning och analys på expertnivå för att hjälpa dem att säkerställa att kritiska hot i dina unika miljöer inte missas.</span><span class="sxs-lookup"><span data-stu-id="e4f9f-110">Microsoft Threat Experts is a managed threat hunting service that provides your Security Operation Centers (SOCs) with expert level monitoring and analysis to help them ensure that critical threats in your unique environments don’t get missed.</span></span>
  
<span data-ttu-id="e4f9f-111">Denna tjänst för hantering av hot efter hot ger expertdrivna insikter och data med dessa två funktioner: riktade attackmeddelanden och tillgång till experter på begäran.</span><span class="sxs-lookup"><span data-stu-id="e4f9f-111">This managed threat hunting service provides expert-driven insights and data through these two capabilities: targeted attack notification and access to experts on demand.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e4f9f-112">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="e4f9f-112">Before you begin</span></span> 
> [!NOTE]
> <span data-ttu-id="e4f9f-113">Diskutera kraven för berättigande med din Microsoft-leverantör och ditt kontoteam innan du använder den hanterade söktjänsten för hot.</span><span class="sxs-lookup"><span data-stu-id="e4f9f-113">Discuss the eligibility requirements with your Microsoft Technical Service provider and account team before you apply to the managed threat hunting service.</span></span>

<span data-ttu-id="e4f9f-114">Om du är Microsoft Defender för slutpunktskund måste du ansöka om **Microsoft Threat Experts – Riktade** attackmeddelanden för att få särskilda insikter och analyser som hjälper dig att identifiera de viktigaste hoten i din miljö så att du snabbt kan svara på dem</span><span class="sxs-lookup"><span data-stu-id="e4f9f-114">If you're a Microsoft Defender for Endpoint customer, you need to apply for **Microsoft Threat Experts - Targeted Attack Notifications** to get special insights and analysis that help identify the most critical threats in your environment so you can respond to them quickly</span></span>

<span data-ttu-id="e4f9f-115">Om du vill registrera dig till Microsoft Threat Experts – fördelar med riktade attackmeddelanden går du till Inställningar Allmänna avancerade funktioner  >    >    >  **Microsoft Threat Experts – Riktade attackmeddelanden** kan användas.</span><span class="sxs-lookup"><span data-stu-id="e4f9f-115">To enroll to Microsoft Threat Experts - Targeted Attack Notifications benefits, go to **Settings** > **General** > **Advanced features** > **Microsoft Threat Experts - Targeted Attack Notifications** to apply.</span></span> <span data-ttu-id="e4f9f-116">När du accepterat det får du fördelarna med riktade attackmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="e4f9f-116">Once accepted, you will get the benefits of Targeted Attack Notifications.</span></span>

<span data-ttu-id="e4f9f-117">Kontakta ditt kontoteam eller din Microsoft-representant för att prenumerera på **Microsoft Threat Experts – Experts on Demand** och rådgör med våra hotexperter om relevanta identifieringar och adversaries som din organisation står inför.</span><span class="sxs-lookup"><span data-stu-id="e4f9f-117">Contact your account team or Microsoft representative to subscribe to **Microsoft Threat Experts - Experts on Demand** to consult with our threat experts on relevant detections and adversaries that your organization is facing.</span></span>

<span data-ttu-id="e4f9f-118">Mer [information finns i Konfigurera Microsoft Threat Experts-funktioner.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#before-you-begin)</span><span class="sxs-lookup"><span data-stu-id="e4f9f-118">See [Configure Microsoft Threat Experts capabilities](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#before-you-begin) for details.</span></span> 

## <a name="microsoft-threat-experts---targeted-attack-notification"></a><span data-ttu-id="e4f9f-119">Microsoft Threat Experts – riktad attackavisering</span><span class="sxs-lookup"><span data-stu-id="e4f9f-119">Microsoft Threat Experts - Targeted attack notification</span></span> 
<span data-ttu-id="e4f9f-120">Microsoft Threat Experts – Riktade attackmeddelanden ger proaktiv sökning efter de viktigaste hoten mot nätverket, bland annat intrång, hand på tangentbordsattacker och avancerade attacker som cyberhot.</span><span class="sxs-lookup"><span data-stu-id="e4f9f-120">Microsoft Threat Experts - Targeted attack notification provides proactive hunting for the most important threats to your network, including human adversary intrusions, hands-on-keyboard attacks, or advanced attacks like cyber-espionage.</span></span> <span data-ttu-id="e4f9f-121">Dessa meddelanden visas som en ny avisering.</span><span class="sxs-lookup"><span data-stu-id="e4f9f-121">These notifications shows up as a new alert.</span></span> <span data-ttu-id="e4f9f-122">Den hanterade servicen för servicen omfattar:</span><span class="sxs-lookup"><span data-stu-id="e4f9f-122">The managed hunting service includes:</span></span>  
- <span data-ttu-id="e4f9f-123">Övervaka och analysera hot, minska invånartid och risker för företaget</span><span class="sxs-lookup"><span data-stu-id="e4f9f-123">Threat monitoring and analysis, reducing dwell time and risk to the business</span></span> 
- <span data-ttu-id="e4f9f-124">Så här upptäcker och prioriterar du både kända och okända attacker</span><span class="sxs-lookup"><span data-stu-id="e4f9f-124">Hunter-trained artificial intelligence to discover and prioritize both known and unknown attacks</span></span>  
- <span data-ttu-id="e4f9f-125">Att identifiera de viktigaste riskerna, hjälpa SOC att maximera tid och energi</span><span class="sxs-lookup"><span data-stu-id="e4f9f-125">Identifying the most important risks, helping SOCs maximize time and energy</span></span> 
- <span data-ttu-id="e4f9f-126">Omfång för kompromettera och så mycket kontext som kan levereras snabbt för att möjliggöra snabbt SOC-svar.</span><span class="sxs-lookup"><span data-stu-id="e4f9f-126">Scope of compromise and as much context as can be quickly delivered to enable fast SOC response.</span></span> 
 
## <a name="microsoft-threat-experts---experts-on-demand"></a><span data-ttu-id="e4f9f-127">Microsoft Threat Experts – experter på begäran</span><span class="sxs-lookup"><span data-stu-id="e4f9f-127">Microsoft Threat Experts - Experts on Demand</span></span>
<span data-ttu-id="e4f9f-128">Kunder kan engagera våra säkerhetsexperter direkt från Microsoft Defender Säkerhetscenter för att få snabba och korrekta svar.</span><span class="sxs-lookup"><span data-stu-id="e4f9f-128">Customers can engage our security experts directly from within Microsoft Defender Security Center for timely and accurate response.</span></span> <span data-ttu-id="e4f9f-129">Experter tillhandahåller insikter som behövs för att bättre förstå komplexa hot som påverkar organisationen, från aviseringar, potentiellt komprometterade enheter, orsaken till en misstänkt nätverksanslutning, till ytterligare hotinformation om pågående avancerade fortlöpande hotkampanjer.</span><span class="sxs-lookup"><span data-stu-id="e4f9f-129">Experts provide insights needed to better understand the complex threats affecting your organization, from alert inquiries, potentially compromised devices, root cause of a suspicious network connection, to additional threat intelligence regarding ongoing advanced persistent threat campaigns.</span></span> <span data-ttu-id="e4f9f-130">Med den här funktionen kan du:</span><span class="sxs-lookup"><span data-stu-id="e4f9f-130">With this capability, you can:</span></span>
- <span data-ttu-id="e4f9f-131">Få ytterligare ett förtydligande av aviseringar, inklusive orsaken till eller omfattningen av händelsen</span><span class="sxs-lookup"><span data-stu-id="e4f9f-131">Get additional clarification on alerts including root cause or scope of the incident</span></span> 
- <span data-ttu-id="e4f9f-132">Öka tydligheten i beteendet på en misstänkt enhet och nästa steg om du står inför en avancerad attack</span><span class="sxs-lookup"><span data-stu-id="e4f9f-132">Gain clarity into suspicious device behavior and next steps if faced with an advanced attacker</span></span>  
- <span data-ttu-id="e4f9f-133">Fastställa risker och skydd för hotfaktorer, kampanjer eller nya attackertekniker</span><span class="sxs-lookup"><span data-stu-id="e4f9f-133">Determine risk and protection regarding threat actors, campaigns, or emerging attacker techniques</span></span> 

<span data-ttu-id="e4f9f-134">Alternativet att Kontakta **en hotexpert finns** på flera platser i portalen så att du kan kommunicera med experter inom ramen för din undersökning:</span><span class="sxs-lookup"><span data-stu-id="e4f9f-134">The option to **Consult a threat expert** is available in several places in the portal so you can engage with experts in the context of your investigation:</span></span>

- <span data-ttu-id="e4f9f-135"><i>**Menyn Hjälp och support**</i></span><span class="sxs-lookup"><span data-stu-id="e4f9f-135"><i>**Help and support menu**</i></span></span><BR>
<span data-ttu-id="e4f9f-136">![Skärmbild av menyalternativet MTE-EOD](images/mte-eod-menu.png)</span><span class="sxs-lookup"><span data-stu-id="e4f9f-136">![Screenshot of MTE-EOD menu option](images/mte-eod-menu.png)</span></span>

- <span data-ttu-id="e4f9f-137"><i>**Menyn Enhet sidåtgärder**</i></span><span class="sxs-lookup"><span data-stu-id="e4f9f-137"><i>**Device page actions menu**</i></span></span><BR>
<span data-ttu-id="e4f9f-138">![Skärmbild av åtgärdsmenyalternativet Sida för MTE-EOD-enhet](images/mte-eod-machines.png)</span><span class="sxs-lookup"><span data-stu-id="e4f9f-138">![Screenshot of MTE-EOD device page action menu option](images/mte-eod-machines.png)</span></span>

- <span data-ttu-id="e4f9f-139"><i>**Menyn Åtgärder på sidan Aviseringar**</i></span><span class="sxs-lookup"><span data-stu-id="e4f9f-139"><i>**Alerts page actions menu**</i></span></span><BR>
<span data-ttu-id="e4f9f-140">![Skärmbild av åtgärdsmenyalternativet MTE-EOD-aviseringssida](images/mte-eod-alerts.png)</span><span class="sxs-lookup"><span data-stu-id="e4f9f-140">![Screenshot of MTE-EOD alert page action menu option](images/mte-eod-alerts.png)</span></span>

- <span data-ttu-id="e4f9f-141"><i>**Menyn Filsidasåtgärder**</i></span><span class="sxs-lookup"><span data-stu-id="e4f9f-141"><i>**File page actions menu**</i></span></span><BR>
<span data-ttu-id="e4f9f-142">![Skärmbild av åtgärdsmenyalternativet Filsida i MTE-EOD](images/mte-eod-file.png)</span><span class="sxs-lookup"><span data-stu-id="e4f9f-142">![Screenshot of MTE-EOD file page action menu option](images/mte-eod-file.png)</span></span>

> [!NOTE]
> <span data-ttu-id="e4f9f-143">Om du vill spåra statusen för ärenden för experter på begäran via Microsoft Services Hub kan du kontakta din Technical Account Manager.</span><span class="sxs-lookup"><span data-stu-id="e4f9f-143">If you would like to track the status of your Experts on Demand cases through Microsoft Services Hub, reach out to your Technical Account Manager.</span></span> 

<span data-ttu-id="e4f9f-144">Titta på den här videon för en snabb överblick över Microsoft Services-hubben.</span><span class="sxs-lookup"><span data-stu-id="e4f9f-144">Watch this video for a quick overview of the Microsoft Services Hub.</span></span>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f] 

   
## <a name="related-topic"></a><span data-ttu-id="e4f9f-145">Relaterat ämne</span><span class="sxs-lookup"><span data-stu-id="e4f9f-145">Related topic</span></span>
- [<span data-ttu-id="e4f9f-146">Konfigurera microsoft Threat Experts-funktioner</span><span class="sxs-lookup"><span data-stu-id="e4f9f-146">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md)
