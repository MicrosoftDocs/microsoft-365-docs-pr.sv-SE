---
title: Aktivera och konfigurera Microsoft Defender Antivirus skyddsfunktioner
description: Aktivera beteendebaserad, heuristisk och realtidsskydd i Microsoft Defender AV.
keywords: heuristisk, maskininlärning, beteendeövervakare, realtidsskydd, alltid på, Microsoft Defender Antivirus, program mot skadlig programvara, säkerhet, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 53b1e1474e0870388ec1cfaf214190eb0bdf7beb
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274616"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a><span data-ttu-id="80091-104">Konfigurera skydd för beteende, heuristisk och realtid</span><span class="sxs-lookup"><span data-stu-id="80091-104">Configure behavioral, heuristic, and real-time protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="80091-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="80091-105">**Applies to:**</span></span>

- [<span data-ttu-id="80091-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="80091-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="80091-107">Microsoft Defender Antivirus flera metoder för att skydda hot:</span><span class="sxs-lookup"><span data-stu-id="80091-107">Microsoft Defender Antivirus uses several methods to provide threat protection:</span></span>

- <span data-ttu-id="80091-108">Molnskydd för omedelbar identifiering och blockering av nya och nya hot</span><span class="sxs-lookup"><span data-stu-id="80091-108">Cloud-delivered protection for near-instant detection and blocking of new and emerging threats</span></span>
- <span data-ttu-id="80091-109">Ständigt skanna, med övervakning av fil- och processbeteenden och annan heuristik (kallas även "realtidsskydd")</span><span class="sxs-lookup"><span data-stu-id="80091-109">Always-on scanning, using file and process behavior monitoring and other heuristics (also known as "real-time protection")</span></span>
- <span data-ttu-id="80091-110">Särskilda skyddsuppdateringar baserade på maskininlärning, mänsklig och automatiserad analys av stora data samt ingående forskning om hotresistens</span><span class="sxs-lookup"><span data-stu-id="80091-110">Dedicated protection updates based on machine-learning, human and automated big-data analysis, and in-depth threat resistance research</span></span>

<span data-ttu-id="80091-111">Du kan konfigurera Microsoft Defender Antivirus hur de här metoderna används med Grupprincip, System Center Configuration Manage, PowerShell-cmdlets och Windows Management Instrumentation (WMI).</span><span class="sxs-lookup"><span data-stu-id="80091-111">You can configure how Microsoft Defender Antivirus uses these methods with Group Policy, System Center Configuration Manage, PowerShell cmdlets, and Windows Management Instrumentation (WMI).</span></span>

<span data-ttu-id="80091-112">Det här avsnittet beskriver konfiguration för alltid-on-skanning, inklusive hur du identifierar och blockerar appar som anses osäkra, men inte kan identifieras som skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="80091-112">This section covers configuration for always-on scanning, including how to detect and block apps that are deemed unsafe, but may not be detected as malware.</span></span>

<span data-ttu-id="80091-113">Se [Använda nästa generationens Microsoft Defender Antivirus-teknik via](cloud-protection-microsoft-defender-antivirus.md) moln levererat skydd för att aktivera och konfigurera Microsoft Defender Antivirus moln levererat skydd.</span><span class="sxs-lookup"><span data-stu-id="80091-113">See [Use next-gen Microsoft Defender Antivirus technologies through cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for how to enable and configure Microsoft Defender Antivirus cloud-delivered protection.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="80091-114">I det här avsnittet</span><span class="sxs-lookup"><span data-stu-id="80091-114">In this section</span></span>

 <span data-ttu-id="80091-115">Ämne</span><span class="sxs-lookup"><span data-stu-id="80091-115">Topic</span></span> | <span data-ttu-id="80091-116">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="80091-116">Description</span></span>
---|---
[<span data-ttu-id="80091-117">Identifiera och blockera potentiellt oönskade program</span><span class="sxs-lookup"><span data-stu-id="80091-117">Detect and block potentially unwanted applications</span></span>](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | <span data-ttu-id="80091-118">Identifiera och blockera appar som kan vara oönskade i nätverket, till exempel reklamprogram, webbläsarrektatörer och verktygsfält och falska eller falska antivirusprogram</span><span class="sxs-lookup"><span data-stu-id="80091-118">Detect and block apps that may be unwanted in your network, such as adware, browser modifiers and toolbars, and rogue or fake antivirus apps</span></span>
[<span data-ttu-id="80091-119">Aktivera och Microsoft Defender Antivirus funktioner för skydd</span><span class="sxs-lookup"><span data-stu-id="80091-119">Enable and configure Microsoft Defender Antivirus protection capabilities</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md) | <span data-ttu-id="80091-120">Aktivera och konfigurera realtidsskydd, heuristics och andra funktioner för Microsoft Defender Antivirus övervakning</span><span class="sxs-lookup"><span data-stu-id="80091-120">Enable and configure real-time protection, heuristics, and other always-on Microsoft Defender Antivirus monitoring features</span></span>