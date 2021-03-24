---
title: Microsoft Defender Säkerhetscenter
description: Microsoft Defender Säkerhetscenter är portalen där du kan komma åt Microsoft Defender för Endpoint.
keywords: windows, defender, säkerhet, center, defender, avancerat, hot, skydd
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
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 521c24c24ecc46c81f74e0bab28642aaf581274d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069610"
---
# <a name="microsoft-defender-security-center"></a><span data-ttu-id="d922a-104">Microsoft Defender Säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="d922a-104">Microsoft Defender Security Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d922a-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="d922a-105">**Applies to:**</span></span>
- [<span data-ttu-id="d922a-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="d922a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="d922a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d922a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d922a-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="d922a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d922a-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="d922a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="d922a-110">Microsoft Defender Säkerhetscenter är portalen där du kan komma åt Microsoft Defender för slutpunktsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="d922a-110">Microsoft Defender Security Center is the portal where you can access Microsoft Defender for Endpoint capabilities.</span></span> <span data-ttu-id="d922a-111">Det ger företagssäkerhetsgrupper ett enda fönster med glas för att skydda nätverk.</span><span class="sxs-lookup"><span data-stu-id="d922a-111">It gives enterprise security operations teams a single pane of glass experience to help secure networks.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d922a-112">I det här avsnittet</span><span class="sxs-lookup"><span data-stu-id="d922a-112">In this section</span></span>

<span data-ttu-id="d922a-113">Ämne</span><span class="sxs-lookup"><span data-stu-id="d922a-113">Topic</span></span> | <span data-ttu-id="d922a-114">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="d922a-114">Description</span></span>
:---|:---
<span data-ttu-id="d922a-115">Komma igång</span><span class="sxs-lookup"><span data-stu-id="d922a-115">Get started</span></span>  |  <span data-ttu-id="d922a-116">Läs mer om minimikraven, validera licensiering och fullständig konfiguration, få information om förhandsgranskningsfunktioner, förstå datalagring och sekretess och hur du tilldelar användaråtkomst till portalen.</span><span class="sxs-lookup"><span data-stu-id="d922a-116">Learn about the minimum requirements, validate licensing and complete setup, know about preview features, understand data storage and privacy, and how to assign user access to the portal.</span></span>
[<span data-ttu-id="d922a-117">Onboard-enheter</span><span class="sxs-lookup"><span data-stu-id="d922a-117">Onboard devices</span></span>](onboard-configure.md) | <span data-ttu-id="d922a-118">Läs mer om onboarding-klient-, server- och icke-Windows-enheter.</span><span class="sxs-lookup"><span data-stu-id="d922a-118">Learn about onboarding client, server, and non-Windows devices.</span></span> <span data-ttu-id="d922a-119">Lär dig hur du kör ett identifieringstest, konfigurerar proxy och Internetanslutningsinställningar och hur du felsöker möjliga onboarding-problem.</span><span class="sxs-lookup"><span data-stu-id="d922a-119">Learn how to run a detection test, configure proxy and Internet connectivity settings, and how to troubleshoot potential onboarding issues.</span></span>
[<span data-ttu-id="d922a-120">Förstå portalen</span><span class="sxs-lookup"><span data-stu-id="d922a-120">Understand the portal</span></span>](use.md) | <span data-ttu-id="d922a-121">Förstå säkerhetsåtgärder, Secure Score- och instrumentpaneler för hotanalys samt hur du navigerar i portalen.</span><span class="sxs-lookup"><span data-stu-id="d922a-121">Understand the Security operations, Secure Score, and Threat analytics dashboards as well as how to navigate the portal.</span></span>
<span data-ttu-id="d922a-122">Undersöka och åtgärda hot</span><span class="sxs-lookup"><span data-stu-id="d922a-122">Investigate and remediate threats</span></span> | <span data-ttu-id="d922a-123">Undersök aviseringar, enheter och vidta åtgärder för att åtgärda hot.</span><span class="sxs-lookup"><span data-stu-id="d922a-123">Investigate alerts, devices, and take response actions to remediate threats.</span></span>
<span data-ttu-id="d922a-124">Stöd för API och SIEM</span><span class="sxs-lookup"><span data-stu-id="d922a-124">API and SIEM support</span></span> | <span data-ttu-id="d922a-125">Använd API:er som stöds för att hämta och skapa anpassade aviseringar eller automatisera arbetsflöden.</span><span class="sxs-lookup"><span data-stu-id="d922a-125">Use the supported APIs to pull and create custom alerts, or automate workflows.</span></span> <span data-ttu-id="d922a-126">Använd de SIEM-verktyg som stöds för att hämta aviseringar från Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="d922a-126">Use the supported SIEM tools to pull alerts from Microsoft Defender Security Center.</span></span>
<span data-ttu-id="d922a-127">Rapportering</span><span class="sxs-lookup"><span data-stu-id="d922a-127">Reporting</span></span> | <span data-ttu-id="d922a-128">Skapa och skapa Power BI-rapporter med Microsoft Defender för Endpoint-data.</span><span class="sxs-lookup"><span data-stu-id="d922a-128">Create and build Power BI reports using Microsoft Defender for Endpoint data.</span></span>
<span data-ttu-id="d922a-129">Kontrollera tjänstens hälsa och sensortillståndet</span><span class="sxs-lookup"><span data-stu-id="d922a-129">Check service health and sensor state</span></span> | <span data-ttu-id="d922a-130">Kontrollera att tjänsten körs och kontrollera sensortillståndet på enheter.</span><span class="sxs-lookup"><span data-stu-id="d922a-130">Verify that the service is running and check the sensor state on devices.</span></span>
[<span data-ttu-id="d922a-131">Konfigurera inställningar för Microsoft Defender Säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="d922a-131">Configure Microsoft Defender Security Center settings</span></span>](preferences-setup.md) | <span data-ttu-id="d922a-132">Konfigurera allmänna inställningar, aktivera förhandsgranskning, meddelanden och aktivera andra funktioner.</span><span class="sxs-lookup"><span data-stu-id="d922a-132">Configure general settings, turn on the preview experience, notifications, and enable other features.</span></span>
[<span data-ttu-id="d922a-133">Få åtkomst till Microsoft Defender för Endpoint Community Center</span><span class="sxs-lookup"><span data-stu-id="d922a-133">Access the Microsoft Defender for Endpoint Community Center</span></span>](community.md) | <span data-ttu-id="d922a-134">Få åtkomst till Microsoft Defender för Endpoint Community Center om du vill lära dig, samarbeta och dela upplevelser om produkten.</span><span class="sxs-lookup"><span data-stu-id="d922a-134">Access the Microsoft Defender for Endpoint Community Center to learn, collaborate, and share experiences about the product.</span></span>
[<span data-ttu-id="d922a-135">Felsöka tjänstproblem</span><span class="sxs-lookup"><span data-stu-id="d922a-135">Troubleshoot service issues</span></span>](troubleshoot-mdatp.md) | <span data-ttu-id="d922a-136">I det här avsnittet behandlas problem som kan uppstå när du använder Tjänsten Microsoft Defender för slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="d922a-136">This section addresses issues that might arise as you use the Microsoft Defender for Endpoint service.</span></span>