---
title: Översikt över Microsoft Defender Säkerhetscenter
description: Läs mer om funktionerna i Microsoft Defender Säkerhetscenter, bland annat hur aviseringar fungerar, och förslag på hur du undersöker möjliga överträdelser och attacker.
keywords: instrumentpanel, aviseringar, kö, hantera aviseringar, undersökning, undersöka aviseringar, undersöka enheter, skicka filer, djupanalys, hög, medium, låg, allvarlighetsgrad, ioc, ioa
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
ms.openlocfilehash: ee6fd4bd8d60f828bb474fc80cb987f4f94edcbe
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581100"
---
# <a name="overview-of-microsoft-defender-security-center"></a><span data-ttu-id="6949f-104">Översikt över Microsoft Defender Säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="6949f-104">Overview of Microsoft Defender Security Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6949f-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="6949f-105">**Applies to:**</span></span>
- [<span data-ttu-id="6949f-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="6949f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="6949f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6949f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="6949f-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="6949f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6949f-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="6949f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-usewdatp-abovefoldlink)

<span data-ttu-id="6949f-110">Microsoft Defender Säkerhetscenter är portalen där du kan komma åt Microsoft Defender för slutpunktsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="6949f-110">Microsoft Defender Security Center is the portal where you can access Microsoft Defender for Endpoint capabilities.</span></span>

<span data-ttu-id="6949f-111">Använd **instrumentpanelen för** säkerhetsåtgärder för att få information om de olika aviseringarna på enheter och användare i nätverket.</span><span class="sxs-lookup"><span data-stu-id="6949f-111">Use the **Security operations** dashboard to gain insight on the various alerts on devices and users in your network.</span></span>

<span data-ttu-id="6949f-112">Använd **instrumentpanelen för & Sårbarhetshantering** för att visa den övergripande säkerhetsbristen i din organisation.</span><span class="sxs-lookup"><span data-stu-id="6949f-112">Use the **Threat & Vulnerability Management** dashboard to expand your visibility on the overall security posture of your organization.</span></span> <span data-ttu-id="6949f-113">Du ser enheter som kräver uppmärksamhet och rekommendationer som kan hjälpa dig att minska attackytan i organisationen.</span><span class="sxs-lookup"><span data-stu-id="6949f-113">You'll see devices that require attention and recommendations that can help you reduce the attack surface in your organization.</span></span>

<span data-ttu-id="6949f-114">Använd **instrumentpanelen för hotanalys** för att kontinuerligt bedöma och kontrollera exponering av risker för Kant och härdning.</span><span class="sxs-lookup"><span data-stu-id="6949f-114">Use the **Threat analytics** dashboard to continually assess and control risk exposure to Spectre and Meltdown.</span></span>

## <a name="microsoft-defender-for-endpoint-interactive-guide"></a><span data-ttu-id="6949f-115">Interaktiv guide för Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="6949f-115">Microsoft Defender for Endpoint interactive guide</span></span>
<span data-ttu-id="6949f-116">I den här interaktiva guiden får du lära dig att undersöka hot mot din organisation med Microsoft Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="6949f-116">In this interactive guide, you'll learn how to investigate threats to your organization with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="6949f-117">Du ser hur Microsoft Defender för Endpoint kan hjälpa dig att identifiera misstänkta aktiviteter, undersöka risker för din organisation och åtgärda hot.</span><span class="sxs-lookup"><span data-stu-id="6949f-117">You'll see how Microsoft Defender for Endpoint can help you identify suspicious activities, investigate risks to your organization, and remediate threats.</span></span>

[<span data-ttu-id="6949f-118">Ta en titta på den interaktiva guiden</span><span class="sxs-lookup"><span data-stu-id="6949f-118">Check out the interactive guide</span></span>](https://aka.ms/MSDE-IG)

### <a name="in-this-section"></a><span data-ttu-id="6949f-119">I det här avsnittet</span><span class="sxs-lookup"><span data-stu-id="6949f-119">In this section</span></span>

<span data-ttu-id="6949f-120">Ämne</span><span class="sxs-lookup"><span data-stu-id="6949f-120">Topic</span></span> | <span data-ttu-id="6949f-121">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6949f-121">Description</span></span>
:---|:---
[<span data-ttu-id="6949f-122">Portalöversikt</span><span class="sxs-lookup"><span data-stu-id="6949f-122">Portal overview</span></span>](portal-overview.md) | <span data-ttu-id="6949f-123">Förstå portallayouten och områdesbeskrivningarna.</span><span class="sxs-lookup"><span data-stu-id="6949f-123">Understand the portal layout and area descriptions.</span></span>
[<span data-ttu-id="6949f-124">Visa instrumentpanelen för säkerhetsåtgärder</span><span class="sxs-lookup"><span data-stu-id="6949f-124">View the Security operations dashboard</span></span>](security-operations-dashboard.md) | <span data-ttu-id="6949f-125">Instrumentpanelen för åtgärder för Microsoft Defender  **för slutpunktssäkerhet** ger en ögonblicksbild av nätverket.</span><span class="sxs-lookup"><span data-stu-id="6949f-125">The Microsoft Defender for Endpoint  **Security operations dashboard** provides a snapshot of your network.</span></span> <span data-ttu-id="6949f-126">Du kan visa ggregeringar av aviseringar, den övergripande statusen för tjänsten för enheter i nätverket, undersöka enheter, filer och URL:er och se ögonblicksbilder av hot som visas på enheter.</span><span class="sxs-lookup"><span data-stu-id="6949f-126">You can view aggregates of alerts, the overall status of the service of the devices on your network, investigate devices, files, and URLs, and see snapshots of threats seen on devices.</span></span>
[<span data-ttu-id="6949f-127">Visa instrumentpanelen för & Sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="6949f-127">View the Threat & Vulnerability Management dashboard</span></span>](tvm-dashboard-insights.md) | <span data-ttu-id="6949f-128">Med **instrumentpanelen & Threat Management** kan du se exponering och Microsoft Secure Score för enheter sida vid sida med de viktigaste säkerhetsrekommendationerna, programsäkerhetsproblem, åtgärder och exponerade enheter.</span><span class="sxs-lookup"><span data-stu-id="6949f-128">The **Threat & Vulnerability Management dashboard** lets you view exposure and Microsoft Secure Score for Devices side-by-side with top security recommendations, software vulnerability, remediation activities, and exposed devices.</span></span>
[<span data-ttu-id="6949f-129">Visa instrumentpanelen för hotanalyser och vidta rekommenderade åtgärder</span><span class="sxs-lookup"><span data-stu-id="6949f-129">View the Threat analytics dashboard and take recommended mitigation actions</span></span>](threat-analytics.md) | <span data-ttu-id="6949f-130">På **instrumentpanelen för** hotanalys får du hjälp att kontinuerligt utvärdera och kontrollera exponering av risker för hot.</span><span class="sxs-lookup"><span data-stu-id="6949f-130">The **Threat analytics** dashboard helps you continually assess and control risk exposure to threats.</span></span> <span data-ttu-id="6949f-131">Använd diagrammen för att snabbt identifiera enheter för närvaro eller frånvaro av minskningar.</span><span class="sxs-lookup"><span data-stu-id="6949f-131">Use the charts to quickly identify devices for the presence or absence of mitigations.</span></span>
