---
title: Ange en moln levererat skyddsnivå för Microsoft Defender Antivirus
description: Ange din nivå av moln levererat skydd för Microsoft Defender Antivirus.
keywords: Microsoft Defender Antivirus, program mot skadlig programvara, säkerhet, defender, moln, aggressivhet, skyddsnivå
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.date: 10/26/2020
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: a0c73c8dd341c4940e3eddd4ede75240e57502d6
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764127"
---
# <a name="specify-the-cloud-delivered-protection-level"></a><span data-ttu-id="d3874-104">Ange skyddsnivån som levereras i molnet</span><span class="sxs-lookup"><span data-stu-id="d3874-104">Specify the cloud-delivered protection level</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d3874-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="d3874-105">**Applies to:**</span></span>

- [<span data-ttu-id="d3874-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="d3874-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="d3874-107">Du kan ange din nivå av moln levererat skydd som erbjuds av Microsoft Defender Antivirus med hjälp av Microsoft Endpoint Manager (rekommenderas) eller grupprincip.</span><span class="sxs-lookup"><span data-stu-id="d3874-107">You can specify your level of cloud-delivered protection offered by Microsoft Defender Antivirus by using Microsoft Endpoint Manager (recommended) or Group Policy.</span></span>

> [!TIP]
> <span data-ttu-id="d3874-108">Molnskydd är inte bara skydd för filer som lagras i molnet.</span><span class="sxs-lookup"><span data-stu-id="d3874-108">Cloud protection is not simply protection for files that are stored in the cloud.</span></span> <span data-ttu-id="d3874-109">Microsoft Defender Antivirus-molntjänsten är en mekanism för att tillhandahålla uppdaterat skydd till ditt nätverk och dina enheter (kallas även slutpunkter).</span><span class="sxs-lookup"><span data-stu-id="d3874-109">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and devices (also called endpoints).</span></span> <span data-ttu-id="d3874-110">Molnskydd med Microsoft Defender Antivirus använder distribuerade resurser och maskininlärning för att ge skydd till dina slutpunkter i en hastighet som är mycket snabbare än traditionella säkerhetsintelligensuppdateringar.</span><span class="sxs-lookup"><span data-stu-id="d3874-110">Cloud protection with Microsoft Defender Antivirus uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional security intelligence updates.</span></span> <span data-ttu-id="d3874-111">Microsoft Intune och Microsoft Endpoint Manager är nu en del av [Microsoft Endpoint Manager.](/mem/endpoint-manager-overview)</span><span class="sxs-lookup"><span data-stu-id="d3874-111">Microsoft Intune and Microsoft Endpoint Manager are now part of [Microsoft Endpoint Manager](/mem/endpoint-manager-overview).</span></span> 


## <a name="use-microsoft-endpoint-manager-to-specify-the-level-of-cloud-delivered-protection"></a><span data-ttu-id="d3874-112">Använd Microsoft Endpoint Manager för att ange nivån för moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="d3874-112">Use Microsoft Endpoint Manager to specify the level of cloud-delivered protection</span></span>

1. <span data-ttu-id="d3874-113">Gå till administrationscentret för Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) och logga in.</span><span class="sxs-lookup"><span data-stu-id="d3874-113">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="d3874-114">Välj **Endpoint Security**  >  **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="d3874-114">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="d3874-115">Välj en antivirusprofil.</span><span class="sxs-lookup"><span data-stu-id="d3874-115">Select an antivirus profile.</span></span> <span data-ttu-id="d3874-116">(Om du inte redan har en, eller om du vill skapa en ny profil, se Konfigurera inställningar för [enhetsbegränsning i Microsoft Intune.](/intune/device-restrictions-configure)</span><span class="sxs-lookup"><span data-stu-id="d3874-116">(If you don't have one yet, or if you want to create a new profile, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="d3874-117">Välj **Egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="d3874-117">Select **Properties**.</span></span> <span data-ttu-id="d3874-118">Välj sedan Redigera bredvid **Konfigurationsinställningar.** </span><span class="sxs-lookup"><span data-stu-id="d3874-118">Then, next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="d3874-119">Expandera **Molnskydd** och välj sedan **något** av följande i listan Moln levererat skyddsnivå:</span><span class="sxs-lookup"><span data-stu-id="d3874-119">Expand **Cloud protection**, and then in the **Cloud-delivered protection level** list, select one of the following:</span></span>

    1. <span data-ttu-id="d3874-120">**Hög:** Använder en stark identifieringsnivå.</span><span class="sxs-lookup"><span data-stu-id="d3874-120">**High**: Applies a strong level of detection.</span></span>
    2. <span data-ttu-id="d3874-121">**Hög plus:** Använder **högnivån** och tillämpar ytterligare skyddsåtgärder (kan påverka klientprestandan).</span><span class="sxs-lookup"><span data-stu-id="d3874-121">**High plus**: Uses the **High** level and applies additional protection measures (may impact client performance).</span></span>
    3. <span data-ttu-id="d3874-122">**Nollarvering**: Blockerar alla okända körbara filer.</span><span class="sxs-lookup"><span data-stu-id="d3874-122">**Zero tolerance**: Blocks all unknown executables.</span></span>

6. <span data-ttu-id="d3874-123">Välj **Granska + spara** och välj sedan **Spara.**</span><span class="sxs-lookup"><span data-stu-id="d3874-123">Choose **Review + save**, and then choose **Save**.</span></span> 

> [!TIP]
> <span data-ttu-id="d3874-124">Behöver du hjälp?</span><span class="sxs-lookup"><span data-stu-id="d3874-124">Need some help?</span></span> <span data-ttu-id="d3874-125">Se följande resurser:</span><span class="sxs-lookup"><span data-stu-id="d3874-125">See the following resources:</span></span>
> - [<span data-ttu-id="d3874-126">Konfigurera slutpunktsskydd</span><span class="sxs-lookup"><span data-stu-id="d3874-126">Configure Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
> - [<span data-ttu-id="d3874-127">Lägga till inställningar för slutpunktsskydd i Intune</span><span class="sxs-lookup"><span data-stu-id="d3874-127">Add endpoint protection settings in Intune</span></span>](/mem/intune/protect/endpoint-protection-configure)
  

## <a name="use-group-policy-to-specify-the-level-of-cloud-delivered-protection"></a><span data-ttu-id="d3874-128">Använda grupprinciper för att ange nivån för moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="d3874-128">Use Group Policy to specify the level of cloud-delivered protection</span></span>

1.  <span data-ttu-id="d3874-129">Öppna grupprinciphanteringskonsolen på [hanteringsdatorn för grupprinciper.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="d3874-129">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="d3874-130">Högerklicka på det grupprincipobjekt du vill konfigurera och klicka sedan på **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="d3874-130">Right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>

3.  <span data-ttu-id="d3874-131">I **redigeraren för hantering av grupprinciper** går du **till Administrativa mallar för**  >  **datorkonfiguration.**</span><span class="sxs-lookup"><span data-stu-id="d3874-131">In the **Group Policy Management Editor** go to **Computer Configuration** > **Administrative templates**.</span></span>

4.  <span data-ttu-id="d3874-132">Expandera trädet till **Windows-komponenter**  >  **Microsoft Defender Antivirus**  >  **MpEngine.**</span><span class="sxs-lookup"><span data-stu-id="d3874-132">Expand the tree to **Windows Components** > **Microsoft Defender Antivirus** > **MpEngine**.</span></span>

5.  <span data-ttu-id="d3874-133">Dubbelklicka på inställningen Välj **molnskyddsnivå** och ställ in den på **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="d3874-133">Double-click the **Select cloud protection level** setting and set it to **Enabled**.</span></span> <span data-ttu-id="d3874-134">Välj skyddsnivå:</span><span class="sxs-lookup"><span data-stu-id="d3874-134">Select the level of protection:</span></span>
    - <span data-ttu-id="d3874-135">**Standardblockeringsnivån** ger stark identifiering utan att öka risken för att legitima filer identifieras.</span><span class="sxs-lookup"><span data-stu-id="d3874-135">**Default blocking level** provides strong detection without increasing the risk of detecting legitimate files.</span></span>
    - <span data-ttu-id="d3874-136">**Måttlig blockeringsnivå ger** måttlig endast vid identifiering med hög konfidens</span><span class="sxs-lookup"><span data-stu-id="d3874-136">**Moderate blocking level** provides moderate only for high confidence detections</span></span>
    - <span data-ttu-id="d3874-137">**Hög blockeringsnivå** tillämpar en stark identifieringsnivå vid optimering av klientprestanda (men kan också ge dig större risk för falska positiva identifieringar).</span><span class="sxs-lookup"><span data-stu-id="d3874-137">**High blocking level** applies a strong level of detection while optimizing client performance (but can also give you a greater chance of false positives).</span></span>
    - <span data-ttu-id="d3874-138">**Hög + blockeringsnivå** tillämpar ytterligare skyddsåtgärder (kan påverka klientens prestanda och öka risken för falska positiva resultat).</span><span class="sxs-lookup"><span data-stu-id="d3874-138">**High + blocking level** applies additional protection measures (might impact client performance and increase your chance of false positives).</span></span>
    - <span data-ttu-id="d3874-139">**Noll blockering av avvikelser blockerar** alla okända körbara filer.</span><span class="sxs-lookup"><span data-stu-id="d3874-139">**Zero tolerance blocking level** blocks all unknown executables.</span></span>
    
    > [!WARNING]
    > <span data-ttu-id="d3874-140">Det är inte troligt  att om du anger det här alternativet till Hög eller Hög **+** kan vissa legitima filer upptäckas (även om du har möjlighet att häva blockeringen eller tvista vid identifieringen).</span><span class="sxs-lookup"><span data-stu-id="d3874-140">While unlikely, setting this switch to **High** or **High +** may cause some legitimate files to be detected (although you will have the option to unblock or dispute that detection).</span></span>

6. <span data-ttu-id="d3874-141">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3874-141">Click **OK**.</span></span>

7. <span data-ttu-id="d3874-142">Distribuera det uppdaterade grupprincipobjektet.</span><span class="sxs-lookup"><span data-stu-id="d3874-142">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="d3874-143">Se [Konsolen för grupprinciphantering](/windows/win32/srvnodes/group-policy)</span><span class="sxs-lookup"><span data-stu-id="d3874-143">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy)</span></span>

> [!TIP]
> <span data-ttu-id="d3874-144">Använder du grupprincipobjekt lokalt?</span><span class="sxs-lookup"><span data-stu-id="d3874-144">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="d3874-145">Se hur de översätter i molnet.</span><span class="sxs-lookup"><span data-stu-id="d3874-145">See how they translate in the cloud.</span></span> <span data-ttu-id="d3874-146">[Analysera lokala grupprincipobjekt med grupprincipanalyser i Microsoft Endpoint Manager – förhandsversion.](/mem/intune/configuration/group-policy-analytics)</span><span class="sxs-lookup"><span data-stu-id="d3874-146">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="d3874-147">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="d3874-147">Related articles</span></span>

- [<span data-ttu-id="d3874-148">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="d3874-148">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="d3874-149">Aktivera moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="d3874-149">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d3874-150">Så här skapar och distribuerar du skydd mot skadlig programvara: Molnskyddstjänst</span><span class="sxs-lookup"><span data-stu-id="d3874-150">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)