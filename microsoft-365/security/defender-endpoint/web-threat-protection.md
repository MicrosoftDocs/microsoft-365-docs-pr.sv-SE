---
title: Skydda din organisation mot webbhot
description: Läs mer om webbskydd i Microsoft Defender ATP och hur du kan skydda din organisation.
keywords: webbskydd, skydd mot webbhot, surfning, säkerhet, nätfiske, skadlig kod, sårbarhet, webbplatser, nätverksskydd, Edge, Internet Explorer, Chrome, Firefox, webbläsare
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3376308988213b84bc7badb96ebacdf706d1ca5f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071673"
---
# <a name="protect-your-organization-against-web-threats"></a><span data-ttu-id="abade-104">Skydda din organisation mot webbhot</span><span class="sxs-lookup"><span data-stu-id="abade-104">Protect your organization against web threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="abade-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="abade-105">**Applies to:**</span></span>
- [<span data-ttu-id="abade-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="abade-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="abade-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="abade-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="abade-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="abade-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="abade-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="abade-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="abade-110">Skydd mot webbhot är en del [av webbskyddet](web-protection-overview.md) i Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="abade-110">Web threat protection is part of [Web protection](web-protection-overview.md) in Defender for Endpoint.</span></span> <span data-ttu-id="abade-111">Den använder [nätverksskydd](network-protection.md) för att skydda dina enheter mot webbhot.</span><span class="sxs-lookup"><span data-stu-id="abade-111">It uses [network protection](network-protection.md) to secure your devices against web threats.</span></span> <span data-ttu-id="abade-112">Genom att integrera med Microsoft Edge och populära webbläsare från tredje part, som Chrome och Firefox, stoppar webbhotskydd webbhot utan webbproxy och kan skydda enheter när de är borta eller lokalt.</span><span class="sxs-lookup"><span data-stu-id="abade-112">By integrating with Microsoft Edge and popular third-party browsers like Chrome and Firefox, web threat protection stops web threats without a web proxy and can protect devices while they are away or on premises.</span></span> <span data-ttu-id="abade-113">Skydd mot webbhot hindrar åtkomst till nätfiskewebbplatser, skadlig programvara, sårbarhetswebbplatser, icke betrodda eller ryktesbaserade webbplatser samt webbplatser som du har blockerat i din anpassade [indikatorlista.](manage-indicators.md)</span><span class="sxs-lookup"><span data-stu-id="abade-113">Web threat protection stops access to phishing sites, malware vectors, exploit sites, untrusted or low-reputation sites, as well as sites that you have blocked in your [custom indicator list](manage-indicators.md).</span></span>

>[!Note]
><span data-ttu-id="abade-114">Det kan ta upp till en timme innan enheter får nya kundindikatorer.</span><span class="sxs-lookup"><span data-stu-id="abade-114">It can take up to an hour for devices to receive new customer indicators.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="abade-115">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="abade-115">Prerequisites</span></span>
<span data-ttu-id="abade-116">Webbskydd använder nätverksskydd för att tillhandahålla surfsäkerhet i Microsoft Edge och webbläsare från tredje part.</span><span class="sxs-lookup"><span data-stu-id="abade-116">Web protection uses network protection to provide web browsing security on Microsoft Edge and third-party web browsers.</span></span>

<span data-ttu-id="abade-117">Så här aktiverar du nätverksskydd på dina enheter:</span><span class="sxs-lookup"><span data-stu-id="abade-117">To turn on network protection on your devices:</span></span>
- <span data-ttu-id="abade-118">Redigera säkerhetsbaslinjen för Defender för slutpunkt under **Web & Network Protection** för att aktivera nätverksskydd innan du distribuerar eller distribuerar om det.</span><span class="sxs-lookup"><span data-stu-id="abade-118">Edit the Defender for Endpoint security baseline under **Web & Network Protection** to enable network protection before deploying or redeploying it.</span></span> [<span data-ttu-id="abade-119">Läs mer om att granska och tilldela Säkerhetsbaslinje för Defender för slutpunkt</span><span class="sxs-lookup"><span data-stu-id="abade-119">Learn about reviewing and assigning the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline)
- <span data-ttu-id="abade-120">Aktivera nätverksskyddet med hjälp av Intune-enhetskonfiguration, SCCM, Grupprincip eller DIN MDM-lösning.</span><span class="sxs-lookup"><span data-stu-id="abade-120">Turn network protection on using Intune device configuration, SCCM, Group Policy, or your MDM solution.</span></span> [<span data-ttu-id="abade-121">Läs mer om hur du aktiverar nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="abade-121">Read more about enabling network protection</span></span>](enable-network-protection.md)  

>[!Note]
><span data-ttu-id="abade-122">Om du anger endast nätverksskydd **som Granskning är** blockeringen otillgänglig.</span><span class="sxs-lookup"><span data-stu-id="abade-122">If you set network protection to **Audit only**, blocking will be unavailable.</span></span> <span data-ttu-id="abade-123">Du kan också identifiera och logga försök att komma åt skadliga och oönskade webbplatser endast på Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="abade-123">Also, you will be able to detect and log attempts to access malicious and unwanted websites on Microsoft Edge only.</span></span>

## <a name="related-topics"></a><span data-ttu-id="abade-124">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="abade-124">Related topics</span></span>

- [<span data-ttu-id="abade-125">Översikt över webbskydd</span><span class="sxs-lookup"><span data-stu-id="abade-125">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="abade-126">Skydd mot webbhot</span><span class="sxs-lookup"><span data-stu-id="abade-126">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="abade-127">Övervaka webbsäkerhet</span><span class="sxs-lookup"><span data-stu-id="abade-127">Monitor web security</span></span>](web-protection-monitoring.md)
- [<span data-ttu-id="abade-128">Svara på webbhot</span><span class="sxs-lookup"><span data-stu-id="abade-128">Respond to web threats</span></span>](web-protection-response.md)
- [<span data-ttu-id="abade-129">Nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="abade-129">Network protection</span></span>](network-protection.md)