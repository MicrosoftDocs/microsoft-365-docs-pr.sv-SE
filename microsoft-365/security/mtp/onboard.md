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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.openlocfilehash: 64c6e5f7eefad50aa59301de3fd46cae60d6876f
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429437"
---
# <a name="configure-and-manage-microsoft-defender-atp-capabilities"></a><span data-ttu-id="22ba9-104">Konfigurera och hantera Microsoft Defender ATP-funktioner</span><span class="sxs-lookup"><span data-stu-id="22ba9-104">Configure and manage Microsoft Defender ATP capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="22ba9-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="22ba9-105">**Applies to:**</span></span>

- [<span data-ttu-id="22ba9-106">Microsoft Defender Avancerat skydd (Microsoft Defender ATP)</span><span class="sxs-lookup"><span data-stu-id="22ba9-106">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2069559)

<span data-ttu-id="22ba9-107">Konfigurera och hantera alla Microsoft Defender ATP-funktioner för att få bästa möjliga säkerhet för din organisation.</span><span class="sxs-lookup"><span data-stu-id="22ba9-107">Configure and manage all the Microsoft Defender ATP capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="22ba9-108">I det här avsnittet</span><span class="sxs-lookup"><span data-stu-id="22ba9-108">In this section</span></span> 
<span data-ttu-id="22ba9-109">Ämnes</span><span class="sxs-lookup"><span data-stu-id="22ba9-109">Topic</span></span> | <span data-ttu-id="22ba9-110">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="22ba9-110">Description</span></span> 
:---|:---
[<span data-ttu-id="22ba9-111">Konfigurera funktioner för reducering av attack ytan</span><span class="sxs-lookup"><span data-stu-id="22ba9-111">Configure attack surface reduction capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-attack-surface-reduction) |  <span data-ttu-id="22ba9-112">Genom att kontrol lera att konfigurations inställningarna är korrekt inställda och utnyttjande av utnyttjande av skadlighet tillämpas, kan dessa möjligheter motstå attacker och utnyttjandet.</span><span class="sxs-lookup"><span data-stu-id="22ba9-112">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitations.</span></span> 
[<span data-ttu-id="22ba9-113">Konfigurera nästa generations skydd</span><span class="sxs-lookup"><span data-stu-id="22ba9-113">Configure next generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) | <span data-ttu-id="22ba9-114">Konfigurera nästa generations skydd för att fånga alla typer av framväxande hot.</span><span class="sxs-lookup"><span data-stu-id="22ba9-114">Configure next generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="22ba9-115">Konfigurera funktioner i Microsoft Threat experter</span><span class="sxs-lookup"><span data-stu-id="22ba9-115">Configure Microsoft Threat Experts capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-microsoft-threat-experts) | <span data-ttu-id="22ba9-116">Konfigurera och hantera hur du vill få Cybersecurity Threat Intelligence från Microsoft Threat experter.</span><span class="sxs-lookup"><span data-stu-id="22ba9-116">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="22ba9-117">Konfigurera Microsoft Threat Protection-integrering</span><span class="sxs-lookup"><span data-stu-id="22ba9-117">Configure Microsoft Threat Protection integration</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-protection-integration)| <span data-ttu-id="22ba9-118">Konfigurera andra lösningar som integreras med Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="22ba9-118">Configure other solutions that integrate with Microsoft Defender ATP.</span></span>
[<span data-ttu-id="22ba9-119">Stöd för hantering och API</span><span class="sxs-lookup"><span data-stu-id="22ba9-119">Management and API support</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis)| <span data-ttu-id="22ba9-120">Dra aviseringar till din SIEM eller Använd API: er för att skapa anpassade aviseringar.</span><span class="sxs-lookup"><span data-stu-id="22ba9-120">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="22ba9-121">Skapa och skapa Power BI-rapporter.</span><span class="sxs-lookup"><span data-stu-id="22ba9-121">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="22ba9-122">Konfigurera inställningar för säkerhets Center i Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="22ba9-122">Configure Microsoft Defender Security Center settings</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/preferences-setup) |  <span data-ttu-id="22ba9-123">Konfigurera Portal inställningar, till exempel allmänna inställningar, avancerade funktioner, aktivera för hands versionen och andra.</span><span class="sxs-lookup"><span data-stu-id="22ba9-123">Configure portal related settings such as general settings, advanced features, enable the preview experience and others.</span></span>



