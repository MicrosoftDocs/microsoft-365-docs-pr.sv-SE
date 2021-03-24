---
title: Konfigurera och hantera Microsoft Defender ATP-funktioner
ms.reviewer: ''
description: Konfigurera och hantera Microsoft Defender ATP-funktioner, till exempel minskning av attackytan och nästa generations skydd
keywords: konfigurera, hantera, funktioner, minska attackytan, nästa generations skydd, säkerhetskontroller, identifiering och svar av slutpunkter, automatisk undersökning och åtgärd, säkerhetskontroller, kontroller
search.product: eADQiWindows 10XVcnh
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e2082929cf1fb7f4b55331cf62adcd9b936168d0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069156"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="8e20c-104">Konfigurera och hantera Microsoft Defender för slutpunktsfunktioner</span><span class="sxs-lookup"><span data-stu-id="8e20c-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8e20c-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="8e20c-105">**Applies to:**</span></span>
- [<span data-ttu-id="8e20c-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="8e20c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="8e20c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8e20c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8e20c-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="8e20c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8e20c-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="8e20c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="8e20c-110">Konfigurera och hantera alla Defender för Slutpunkt-funktioner för att få det bästa säkerhetsskyddet för din organisation.</span><span class="sxs-lookup"><span data-stu-id="8e20c-110">Configure and manage all the Defender for Endpoint capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="8e20c-111">I det här avsnittet</span><span class="sxs-lookup"><span data-stu-id="8e20c-111">In this section</span></span> 
<span data-ttu-id="8e20c-112">Ämne</span><span class="sxs-lookup"><span data-stu-id="8e20c-112">Topic</span></span> | <span data-ttu-id="8e20c-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8e20c-113">Description</span></span> 
:---|:---
[<span data-ttu-id="8e20c-114">Konfigurera funktioner för att minska attackytan</span><span class="sxs-lookup"><span data-stu-id="8e20c-114">Configure attack surface reduction capabilities</span></span>](configure-attack-surface-reduction.md) |  <span data-ttu-id="8e20c-115">Genom att säkerställa att konfigurationsinställningarna är korrekt inställda och utnyttja tekniker för minskningar tillämpas, kommer dessa uppsättning funktioner att motarbeta attacker och användning.</span><span class="sxs-lookup"><span data-stu-id="8e20c-115">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span> 
[<span data-ttu-id="8e20c-116">Konfigurera nästa generations skydd</span><span class="sxs-lookup"><span data-stu-id="8e20c-116">Configure next-generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) | <span data-ttu-id="8e20c-117">Konfigurera nästa generations skydd för att fånga alla typer av nya hot.</span><span class="sxs-lookup"><span data-stu-id="8e20c-117">Configure next-generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="8e20c-118">Konfigurera microsoft Threat Experts-funktioner</span><span class="sxs-lookup"><span data-stu-id="8e20c-118">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md) | <span data-ttu-id="8e20c-119">Konfigurera och hantera hur du vill få information om hot mot cyberhot från Microsoft Threat Experts.</span><span class="sxs-lookup"><span data-stu-id="8e20c-119">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="8e20c-120">Konfigurera Microsoft Threat Protection-integrering</span><span class="sxs-lookup"><span data-stu-id="8e20c-120">Configure Microsoft Threat Protection integration</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/threat-protection-integration)| <span data-ttu-id="8e20c-121">Konfigurera andra lösningar som integrerar med Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="8e20c-121">Configure other solutions that integrate with Defender for Endpoint.</span></span>
[<span data-ttu-id="8e20c-122">Hanterings- och API-support</span><span class="sxs-lookup"><span data-stu-id="8e20c-122">Management and API support</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/management-apis)| <span data-ttu-id="8e20c-123">Hämta aviseringar till ditt SIEM eller använd API:er för att skapa anpassade aviseringar.</span><span class="sxs-lookup"><span data-stu-id="8e20c-123">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="8e20c-124">Skapa och skapa Power BI-rapporter.</span><span class="sxs-lookup"><span data-stu-id="8e20c-124">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="8e20c-125">Konfigurera inställningar för Microsoft Defender Säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="8e20c-125">Configure Microsoft Defender Security Center settings</span></span>](preferences-setup.md) |  <span data-ttu-id="8e20c-126">Konfigurera portalrelaterade inställningar, till exempel allmänna inställningar, avancerade funktioner, aktivera förhandsgranskning och andra.</span><span class="sxs-lookup"><span data-stu-id="8e20c-126">Configure portal-related settings such as general settings, advanced features, enable the preview experience and others.</span></span>



