---
title: Konfigurera och hantera Microsoft Defender för slutpunktsfunktioner
ms.reviewer: ''
description: Konfigurera och hantera Microsoft Defender för slutpunktsfunktioner som minskning av attackytan och nästa generations skydd
keywords: konfigurera, hantera, funktioner, minska attackytan, nästa generations skydd, säkerhetskontroller, identifiering och åtgärd på slutpunkt, automatisk undersökning och åtgärd, säkerhetskontroller, kontroller
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c58d7d4192afd0aa13a5ffb0c7f3204b4eaf0315
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844412"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="526bd-104">Konfigurera och hantera Microsoft Defender för slutpunktsfunktioner</span><span class="sxs-lookup"><span data-stu-id="526bd-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="526bd-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="526bd-105">**Applies to:**</span></span>

- [<span data-ttu-id="526bd-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="526bd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="526bd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="526bd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="526bd-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="526bd-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="526bd-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="526bd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="526bd-110">Lär dig hur du konfigurerar och hanterar Defender för slutpunktsfunktioner för att få det bästa säkerhetsskyddet för din organisation.</span><span class="sxs-lookup"><span data-stu-id="526bd-110">Learn how to configure and manage Defender for Endpoint features, to get the best security protection for your organization.</span></span>

<span data-ttu-id="526bd-111">Praktiska råd om hur du ansluter nya enheter i organisationen finns i Artikeln om att [introducera enheter i Microsoft Defender för slutpunktstjänsten.](./onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="526bd-111">For practical advice on connecting new devices in your organization, see [Onboard devices to the Microsoft Defender for Endpoint service](./onboard-configure.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="526bd-112">I det här avsnittet</span><span class="sxs-lookup"><span data-stu-id="526bd-112">In this section</span></span>

<span data-ttu-id="526bd-113">Ämne</span><span class="sxs-lookup"><span data-stu-id="526bd-113">Topic</span></span> | <span data-ttu-id="526bd-114">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="526bd-114">Description</span></span>
:---|:---
[<span data-ttu-id="526bd-115">Konfigurera Microsoft Defender Säkerhetscenter inställningar</span><span class="sxs-lookup"><span data-stu-id="526bd-115">Configure Microsoft Defender Security Center settings</span></span>](preferences-setup.md) | <span data-ttu-id="526bd-116">Konfigurera portalrelaterade inställningar som allmänna inställningar, avancerade funktioner eller aktivera förhandsgranskning.</span><span class="sxs-lookup"><span data-stu-id="526bd-116">Configure portal-related settings such as general settings, advanced features, or enable the preview experience.</span></span>
[<span data-ttu-id="526bd-117">Konfigurera funktioner för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="526bd-117">Configure attack surface reduction capabilities</span></span>](configure-attack-surface-reduction.md) | <span data-ttu-id="526bd-118">Konfigurera funktioner för att minska attackytan för att säkerställa att inställningarna tillämpas på rätt sätt och utnyttja tekniker för minskning av attackytan har ställts in.</span><span class="sxs-lookup"><span data-stu-id="526bd-118">Configure attack surface reduction capabilities, to ensure that settings are properly applied, and exploit mitigation techniques are set.</span></span>
[<span data-ttu-id="526bd-119">Konfigurera nästa generations skydd</span><span class="sxs-lookup"><span data-stu-id="526bd-119">Configure next-generation protection</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) | <span data-ttu-id="526bd-120">Konfigurera nästa generations skydd för att fånga alla typer av nya hot.</span><span class="sxs-lookup"><span data-stu-id="526bd-120">Configure next-generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="526bd-121">Konfigurera Microsoft Hotexperter funktioner</span><span class="sxs-lookup"><span data-stu-id="526bd-121">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md) | <span data-ttu-id="526bd-122">Konfigurera och hantera hotinformation om cybersäkerhet från Microsoft Hotexperter.</span><span class="sxs-lookup"><span data-stu-id="526bd-122">Configure and manage cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="526bd-123">Konfigurera Microsoft 365 Defender-integrering</span><span class="sxs-lookup"><span data-stu-id="526bd-123">Configure Microsoft 365 Defender integration</span></span>](/microsoft-365/security/defender-endpoint/threat-protection-integration) | <span data-ttu-id="526bd-124">Konfigurera andra lösningar som integrerar med Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="526bd-124">Configure other solutions that integrate with Defender for Endpoint.</span></span>
[<span data-ttu-id="526bd-125">Hanterings- och API-support</span><span class="sxs-lookup"><span data-stu-id="526bd-125">Management and API support</span></span>](/microsoft-365/security/defender-endpoint/management-apis) | <span data-ttu-id="526bd-126">Hämta aviseringar till din säkerhetsinformation och händelsehantering (SIEM) eller använd API:er för att skapa anpassade varningar.</span><span class="sxs-lookup"><span data-stu-id="526bd-126">Pull alerts to your Security Information and Event Management (SIEM) or use APIs to create custom alerts.</span></span> <span data-ttu-id="526bd-127">Skapa och Power BI rapporter.</span><span class="sxs-lookup"><span data-stu-id="526bd-127">Create and build Power BI reports.</span></span>
