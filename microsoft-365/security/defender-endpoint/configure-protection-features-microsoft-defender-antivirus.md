---
title: Aktivera och konfigurera Microsoft Defender Antivirus skyddsfunktioner
description: Aktivera beteendebaserad, heuristisk och realtidsskydd i Microsoft Defender AV.
keywords: heuristisk, maskininlärning, beteendeövervakare, realtidsskydd, alltid på, Microsoft Defender Antivirus, program mot skadlig programvara, säkerhet, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: d8ce2ded8fd3270bcb095022c714f07d8030e1f7
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925569"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a><span data-ttu-id="47c86-104">Konfigurera skydd för beteende, heuristisk och realtid</span><span class="sxs-lookup"><span data-stu-id="47c86-104">Configure behavioral, heuristic, and real-time protection</span></span>


<span data-ttu-id="47c86-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="47c86-105">**Applies to:**</span></span>

- [<span data-ttu-id="47c86-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="47c86-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="47c86-107">Microsoft Defender Antivirus flera metoder för att skydda hot:</span><span class="sxs-lookup"><span data-stu-id="47c86-107">Microsoft Defender Antivirus uses several methods to provide threat protection:</span></span>

- <span data-ttu-id="47c86-108">Molnskydd för omedelbar identifiering och blockering av nya och nya hot</span><span class="sxs-lookup"><span data-stu-id="47c86-108">Cloud-delivered protection for near-instant detection and blocking of new and emerging threats</span></span>
- <span data-ttu-id="47c86-109">Ständigt skanna, med övervakning av fil- och processbeteenden och annan heuristik (kallas även "realtidsskydd")</span><span class="sxs-lookup"><span data-stu-id="47c86-109">Always-on scanning, using file and process behavior monitoring and other heuristics (also known as "real-time protection")</span></span>
- <span data-ttu-id="47c86-110">Särskilda skyddsuppdateringar baserade på maskininlärning, mänsklig och automatiserad analys av stora data samt ingående forskning om hotresistens</span><span class="sxs-lookup"><span data-stu-id="47c86-110">Dedicated protection updates based on machine-learning, human and automated big-data analysis, and in-depth threat resistance research</span></span>

<span data-ttu-id="47c86-111">Du kan konfigurera Microsoft Defender Antivirus hur de här metoderna används med Grupprincip, System Center Configuration Manage, PowerShell-cmdlets och Windows Management Instrumentation (WMI).</span><span class="sxs-lookup"><span data-stu-id="47c86-111">You can configure how Microsoft Defender Antivirus uses these methods with Group Policy, System Center Configuration Manage, PowerShell cmdlets, and Windows Management Instrumentation (WMI).</span></span>

<span data-ttu-id="47c86-112">Det här avsnittet beskriver konfiguration för alltid-on-skanning, inklusive hur du identifierar och blockerar appar som anses osäkra, men inte kan identifieras som skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="47c86-112">This section covers configuration for always-on scanning, including how to detect and block apps that are deemed unsafe, but may not be detected as malware.</span></span>

<span data-ttu-id="47c86-113">Se [Använda nästa generationens Microsoft Defender Antivirus-teknik via](cloud-protection-microsoft-defender-antivirus.md) moln levererat skydd för att aktivera och konfigurera Microsoft Defender Antivirus moln levererat skydd.</span><span class="sxs-lookup"><span data-stu-id="47c86-113">See [Use next-gen Microsoft Defender Antivirus technologies through cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for how to enable and configure Microsoft Defender Antivirus cloud-delivered protection.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="47c86-114">I det här avsnittet</span><span class="sxs-lookup"><span data-stu-id="47c86-114">In this section</span></span>

 <span data-ttu-id="47c86-115">Ämne</span><span class="sxs-lookup"><span data-stu-id="47c86-115">Topic</span></span> | <span data-ttu-id="47c86-116">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="47c86-116">Description</span></span>
---|---
[<span data-ttu-id="47c86-117">Identifiera och blockera potentiellt oönskade program</span><span class="sxs-lookup"><span data-stu-id="47c86-117">Detect and block potentially unwanted applications</span></span>](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | <span data-ttu-id="47c86-118">Identifiera och blockera appar som kan vara oönskade i nätverket, till exempel reklamprogram, webbläsarrektatörer och verktygsfält och falska eller falska antivirusprogram</span><span class="sxs-lookup"><span data-stu-id="47c86-118">Detect and block apps that may be unwanted in your network, such as adware, browser modifiers and toolbars, and rogue or fake antivirus apps</span></span>
[<span data-ttu-id="47c86-119">Aktivera och Microsoft Defender Antivirus funktioner för skydd</span><span class="sxs-lookup"><span data-stu-id="47c86-119">Enable and configure Microsoft Defender Antivirus protection capabilities</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md) | <span data-ttu-id="47c86-120">Aktivera och konfigurera realtidsskydd, heuristics och andra funktioner för Microsoft Defender Antivirus övervakning</span><span class="sxs-lookup"><span data-stu-id="47c86-120">Enable and configure real-time protection, heuristics, and other always-on Microsoft Defender Antivirus monitoring features</span></span>
