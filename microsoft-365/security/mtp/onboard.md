---
title: Konfigurera och hantera Microsoft Defender ATP-funktioner
ms.reviewer: ''
description: Konfigurera och hantera Microsoft Defender ATP-funktioner som reducering av attack ytan, nästa generationens skydd och säkerhets kontroller
keywords: Konfigurera, hantera, funktioner, reducering av attack yta, nästa generationens skydd, säkerhets kontroller, slut punkts avkänning och svar, automatisk undersökning och reparation, säkerhets kontroller, kontroller
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 0bc7ada54c0ce67ccbe1fded5970853672e08c1b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201042"
---
# <a name="configure-and-manage-microsoft-defender-atp-capabilities"></a><span data-ttu-id="04fcb-104">Konfigurera och hantera Microsoft Defender ATP-funktioner</span><span class="sxs-lookup"><span data-stu-id="04fcb-104">Configure and manage Microsoft Defender ATP capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="04fcb-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="04fcb-105">**Applies to:**</span></span>

- [<span data-ttu-id="04fcb-106">Microsoft Defender Avancerat skydd (Microsoft Defender ATP)</span><span class="sxs-lookup"><span data-stu-id="04fcb-106">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2069559)

<span data-ttu-id="04fcb-107">Konfigurera och hantera alla Microsoft Defender ATP-funktioner för att få bästa möjliga säkerhet för din organisation.</span><span class="sxs-lookup"><span data-stu-id="04fcb-107">Configure and manage all the Microsoft Defender ATP capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="04fcb-108">I det här avsnittet</span><span class="sxs-lookup"><span data-stu-id="04fcb-108">In this section</span></span> 
<span data-ttu-id="04fcb-109">Ämnes</span><span class="sxs-lookup"><span data-stu-id="04fcb-109">Topic</span></span> | <span data-ttu-id="04fcb-110">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="04fcb-110">Description</span></span> 
:---|:---
[<span data-ttu-id="04fcb-111">Konfigurera funktioner för reducering av attack ytan</span><span class="sxs-lookup"><span data-stu-id="04fcb-111">Configure attack surface reduction capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-attack-surface-reduction) |  <span data-ttu-id="04fcb-112">Genom att kontrol lera att konfigurations inställningarna är korrekt inställda och utnyttjande av utnyttjande av skadlighet tillämpas, kan dessa möjligheter motstå attacker och utnyttjandet.</span><span class="sxs-lookup"><span data-stu-id="04fcb-112">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitations.</span></span> 
[<span data-ttu-id="04fcb-113">Konfigurera nästa generations skydd</span><span class="sxs-lookup"><span data-stu-id="04fcb-113">Configure next generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) | <span data-ttu-id="04fcb-114">Konfigurera nästa generations skydd för att fånga alla typer av framväxande hot.</span><span class="sxs-lookup"><span data-stu-id="04fcb-114">Configure next generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="04fcb-115">Konfigurera funktioner i Microsoft Threat experter</span><span class="sxs-lookup"><span data-stu-id="04fcb-115">Configure Microsoft Threat Experts capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-microsoft-threat-experts) | <span data-ttu-id="04fcb-116">Konfigurera och hantera hur du vill få Cybersecurity Threat Intelligence från Microsoft Threat experter.</span><span class="sxs-lookup"><span data-stu-id="04fcb-116">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="04fcb-117">Konfigurera Microsoft Threat Protection-integrering</span><span class="sxs-lookup"><span data-stu-id="04fcb-117">Configure Microsoft Threat Protection integration</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-protection-integration)| <span data-ttu-id="04fcb-118">Konfigurera andra lösningar som integreras med Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="04fcb-118">Configure other solutions that integrate with Microsoft Defender ATP.</span></span>
[<span data-ttu-id="04fcb-119">Stöd för hantering och API</span><span class="sxs-lookup"><span data-stu-id="04fcb-119">Management and API support</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis)| <span data-ttu-id="04fcb-120">Dra aviseringar till din SIEM eller Använd API: er för att skapa anpassade aviseringar.</span><span class="sxs-lookup"><span data-stu-id="04fcb-120">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="04fcb-121">Skapa och skapa Power BI-rapporter.</span><span class="sxs-lookup"><span data-stu-id="04fcb-121">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="04fcb-122">Konfigurera inställningar för säkerhets Center i Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="04fcb-122">Configure Microsoft Defender Security Center settings</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/preferences-setup) |  <span data-ttu-id="04fcb-123">Konfigurera Portal inställningar, till exempel allmänna inställningar, avancerade funktioner, aktivera för hands versionen och andra.</span><span class="sxs-lookup"><span data-stu-id="04fcb-123">Configure portal related settings such as general settings, advanced features, enable the preview experience and others.</span></span>



