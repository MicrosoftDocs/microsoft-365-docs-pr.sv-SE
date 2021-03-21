---
title: Konfigurera och hantera Microsoft Defender för slutpunktsfunktioner
ms.reviewer: ''
description: Konfigurera och hantera Microsoft Defender för slutpunktsfunktioner som minskning av attackytan och nästa generations skydd
keywords: konfigurera, hantera, funktioner, minska attackytan, nästa generations skydd, säkerhetskontroller, identifiering och svar av slutpunkter, automatisk undersökning och åtgärd, säkerhetskontroller, kontroller
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: c3bb09820f4a22c8ecb1e49c699db5b6f4cabc68
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928622"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="74991-104">Konfigurera och hantera Microsoft Defender för slutpunktsfunktioner</span><span class="sxs-lookup"><span data-stu-id="74991-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="74991-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="74991-105">**Applies to:**</span></span>

- [<span data-ttu-id="74991-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="74991-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2069559)

<span data-ttu-id="74991-107">Konfigurera och hantera alla Microsoft Defender för Slutpunkt-funktioner för att få det bästa säkerhetsskyddet för din organisation.</span><span class="sxs-lookup"><span data-stu-id="74991-107">Configure and manage all the Microsoft Defender for Endpoint capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="74991-108">I det här avsnittet</span><span class="sxs-lookup"><span data-stu-id="74991-108">In this section</span></span> 
<span data-ttu-id="74991-109">Ämne</span><span class="sxs-lookup"><span data-stu-id="74991-109">Topic</span></span> | <span data-ttu-id="74991-110">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="74991-110">Description</span></span> 
:---|:---
[<span data-ttu-id="74991-111">Konfigurera funktioner för att minska attackytan</span><span class="sxs-lookup"><span data-stu-id="74991-111">Configure attack surface reduction capabilities</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-attack-surface-reduction) |  <span data-ttu-id="74991-112">Genom att säkerställa att konfigurationsinställningarna är korrekt inställda och utnyttja tekniker för minskningar tillämpas, kommer dessa uppsättning funktioner att motarbeta attacker och användning.</span><span class="sxs-lookup"><span data-stu-id="74991-112">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span> 
[<span data-ttu-id="74991-113">Konfigurera nästa generations skydd</span><span class="sxs-lookup"><span data-stu-id="74991-113">Configure next generation protection</span></span>](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) | <span data-ttu-id="74991-114">Konfigurera nästa generations skydd för att fånga alla typer av nya hot.</span><span class="sxs-lookup"><span data-stu-id="74991-114">Configure next generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="74991-115">Konfigurera microsoft Threat Experts-funktioner</span><span class="sxs-lookup"><span data-stu-id="74991-115">Configure Microsoft Threat Experts capabilities</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-microsoft-threat-experts) | <span data-ttu-id="74991-116">Konfigurera och hantera hur du vill få information om hot mot cyberhot från Microsoft Threat Experts.</span><span class="sxs-lookup"><span data-stu-id="74991-116">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="74991-117">Konfigurera Microsoft 365 Defender-integrering</span><span class="sxs-lookup"><span data-stu-id="74991-117">Configure Microsoft 365 Defender integration</span></span>](/windows/security/threat-protection/microsoft-defender-atp/threat-protection-integration)| <span data-ttu-id="74991-118">Konfigurera andra lösningar som kan integreras med Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="74991-118">Configure other solutions that integrate with Microsoft Defender for Endpoint.</span></span>
[<span data-ttu-id="74991-119">Hanterings- och API-support</span><span class="sxs-lookup"><span data-stu-id="74991-119">Management and API support</span></span>](/windows/security/threat-protection/microsoft-defender-atp/management-apis)| <span data-ttu-id="74991-120">Hämta aviseringar till ditt SIEM eller använd API:er för att skapa anpassade aviseringar.</span><span class="sxs-lookup"><span data-stu-id="74991-120">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="74991-121">Skapa och skapa Power BI-rapporter.</span><span class="sxs-lookup"><span data-stu-id="74991-121">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="74991-122">Konfigurera inställningar för Microsoft Defender Säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="74991-122">Configure Microsoft Defender Security Center settings</span></span>](/windows/security/threat-protection/microsoft-defender-atp/preferences-setup) |  <span data-ttu-id="74991-123">Konfigurera portalrelaterade inställningar, till exempel allmänna inställningar, avancerade funktioner, aktivera förhandsgranskning och andra.</span><span class="sxs-lookup"><span data-stu-id="74991-123">Configure portal-related settings such as general settings, advanced features, enable the preview experience and others.</span></span>