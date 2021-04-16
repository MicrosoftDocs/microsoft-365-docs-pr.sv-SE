---
title: Microsoft Defender för slutpunkt partner affärsmöjligheter och scenarier
ms.reviewer: ''
description: Lär dig hur du kan utöka befintliga säkerhetserbjudanden ovanpå det öppna ramverket och en omfattande uppsättning API:er för att skapa tillägg och integreringar med Microsoft Defender för Slutpunkt
keywords: API, partner, utöka, öppna ramverket, api:er, tillägg, integreringar, identifiering, hantering, svar, svagheter, information
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
ms.openlocfilehash: be2f33514a568f290a3fc5cf0adc62db72243a6f
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861115"
---
# <a name="microsoft-defender-for-endpoint-partner-opportunities-and-scenarios"></a><span data-ttu-id="61cc7-104">Microsoft Defender för slutpunkt partner affärsmöjligheter och scenarier</span><span class="sxs-lookup"><span data-stu-id="61cc7-104">Microsoft Defender for Endpoint partner opportunities and scenarios</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="61cc7-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="61cc7-105">**Applies to:**</span></span>
- [<span data-ttu-id="61cc7-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="61cc7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="61cc7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="61cc7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="61cc7-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="61cc7-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="61cc7-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="61cc7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="61cc7-110">Partner kan enkelt utöka sina befintliga säkerhetserbjudanden ovanpå det öppna ramverket och en omfattande och fullständig uppsättning API:er för att skapa tillägg och integreringar med Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="61cc7-110">Partners can easily extend their existing security offerings on top of the open framework and a rich and complete set of APIs to build extensions and integrations with Defender for Endpoint.</span></span> 

<span data-ttu-id="61cc7-111">API:erna omfattar funktionella områden, inklusive identifiering, hantering, svar, säkerhetsproblem och användningsfall som omfattar information.</span><span class="sxs-lookup"><span data-stu-id="61cc7-111">The APIs span functional areas including detection, management, response, vulnerabilities, and intelligence-wide range of use cases.</span></span> <span data-ttu-id="61cc7-112">Baserat på användningsfall och behov kan partner antingen strömma eller fråga data från Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="61cc7-112">Based on the use case and need, partners can either stream or query data from Defender for Endpoint.</span></span> 


## <a name="scenario-1-external-alert-correlation-and-automated-investigation-and-remediation"></a><span data-ttu-id="61cc7-113">Scenario 1: Extern aviseringskorrelation och automatiserad undersökning och åtgärd</span><span class="sxs-lookup"><span data-stu-id="61cc7-113">Scenario 1: External alert correlation and Automated investigation and remediation</span></span>
<span data-ttu-id="61cc7-114">Defender för Endpoint erbjuder unika automatiska undersöknings- och åtgärdsfunktioner för att köra incidentåtgärder med en skala.</span><span class="sxs-lookup"><span data-stu-id="61cc7-114">Defender for Endpoint offers unique automated investigation and remediation capabilities to drive incident response at scale.</span></span> 

<span data-ttu-id="61cc7-115">Genom att integrera automatisk undersökning och svarsfunktioner med andra lösningar, till exempel produkter för nätverkssäkerhet eller andra slutpunktssäkerhetsprodukter, blir det bättre att hantera aviseringar.</span><span class="sxs-lookup"><span data-stu-id="61cc7-115">Integrating the automated investigation and response capability with other solutions such as network security products or other endpoint security products will help to address alerts.</span></span> <span data-ttu-id="61cc7-116">Integreringen minimerar också komplexiteten kring nätverks- och enhets signalkorrelation, vilket effektiviserar undersöknings- och hotåtgärder på enheter.</span><span class="sxs-lookup"><span data-stu-id="61cc7-116">The integration also minimizes the complexities surrounding network and device signal correlation, effectively streamlining the investigation and threat remediation actions on devices.</span></span>

<span data-ttu-id="61cc7-117">Defender för Endpoint lägger till stöd för det här scenariot i följande formulär:</span><span class="sxs-lookup"><span data-stu-id="61cc7-117">Defender for Endpoint adds support for this scenario in the following forms:</span></span>

- <span data-ttu-id="61cc7-118">Externa aviseringar kan skickas till Defender för Slutpunkt och presenteras sida vid sida med ytterligare enhetsbaserade aviseringar från Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="61cc7-118">External alerts can be pushed into Defender for Endpoint and presented side by side with additional device-based alerts from Defender for Endpoint.</span></span> <span data-ttu-id="61cc7-119">Den här vyn ger en fullständig kontext av varningen – med den faktiska processen och hela attackprocessen.</span><span class="sxs-lookup"><span data-stu-id="61cc7-119">This view provides the full context of the alert - with the real process and the full story of attack.</span></span>

- <span data-ttu-id="61cc7-120">När en avisering skapas delas signalen mellan alla Defender för slutpunktsskyddade slutpunkter i företaget.</span><span class="sxs-lookup"><span data-stu-id="61cc7-120">Once an alert is generated, the signal is shared across all Defender for Endpoint protected endpoints in the enterprise.</span></span> <span data-ttu-id="61cc7-121">Defender för Endpoint tar omedelbart automatiserat eller operatörs assisterat svar för att åtgärda aviseringen.</span><span class="sxs-lookup"><span data-stu-id="61cc7-121">Defender for Endpoint takes immediate automated or operator-assisted response to address the alert.</span></span>

## <a name="scenario-2-security-orchestration-and-automation-response-soar-integration"></a><span data-ttu-id="61cc7-122">Scenario 2: Säkerhetshantering och automationssvarsintegrering (SOAR)</span><span class="sxs-lookup"><span data-stu-id="61cc7-122">Scenario 2: Security orchestration and automation response (SOAR) integration</span></span>
<span data-ttu-id="61cc7-123">Om du tar bort olika lösningar kan du skapa spelböcker och integrera den omfattande datamodellen och åtgärderna som Defender för slutpunkts-API:er exponerar för att få svar, till exempel fråga om enhetsdata, utlösa enhetsisolering, blockera/tillåta, åtgärda aviseringar och andra.</span><span class="sxs-lookup"><span data-stu-id="61cc7-123">Orchestration solutions can help build playbooks and integrate the rich data model and actions that Defender for Endpoint APIs expose to orchestrate responses, such as query for device data, trigger device isolation, block/allow, resolve alert and others.</span></span>

## <a name="scenario-3-indicators-matching"></a><span data-ttu-id="61cc7-124">Scenario 3: Indikatormatchning</span><span class="sxs-lookup"><span data-stu-id="61cc7-124">Scenario 3: Indicators matching</span></span> 
<span data-ttu-id="61cc7-125">Indikator på kompromettering (IoCs) är en viktig funktion i varje lösning för slutpunktsskydd.</span><span class="sxs-lookup"><span data-stu-id="61cc7-125">Indicator of compromise (IoCs) matching is an essential feature in every endpoint protection solution.</span></span> <span data-ttu-id="61cc7-126">Den här funktionen är tillgänglig i Defender för Endpoint och ger möjlighet att ange en lista över indikatorer för skydd, identifiering och exkludering av enheter.</span><span class="sxs-lookup"><span data-stu-id="61cc7-126">This capability is available in Defender for Endpoint and gives the ability to set a list of indicators for prevention, detection, and exclusion of entities.</span></span> <span data-ttu-id="61cc7-127">En kan definiera vilken åtgärd som ska vidtas samt varaktigheten för när åtgärden ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="61cc7-127">One can define the action to be taken as well as the duration for when to apply the action.</span></span>

<span data-ttu-id="61cc7-128">Ovanstående scenarier fungerar som exempel på plattformens utökningsbarhet.</span><span class="sxs-lookup"><span data-stu-id="61cc7-128">The above scenarios serve as examples of the extensibility of the platform.</span></span> <span data-ttu-id="61cc7-129">Du är inte begränsad till exemplen och vi uppmuntrar dig verkligen att använda det öppna ramverket för att upptäcka och utforska andra scenarier.</span><span class="sxs-lookup"><span data-stu-id="61cc7-129">You are not limited to the examples and we certainly encourage you to leverage the open framework to discover and explore other scenarios.</span></span>

<span data-ttu-id="61cc7-130">Följ stegen i Bli [en Microsoft Defender för Slutpunkt-partner för](get-started-partner-integration.md) att integrera din lösning i Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="61cc7-130">Follow the steps in [Become a Microsoft Defender for Endpoint partner](get-started-partner-integration.md) to integrate your solution in Defender for Endpoint.</span></span>

## <a name="related-topic"></a><span data-ttu-id="61cc7-131">Relaterat ämne</span><span class="sxs-lookup"><span data-stu-id="61cc7-131">Related topic</span></span>
- [<span data-ttu-id="61cc7-132">Översikt över hantering och API:er</span><span class="sxs-lookup"><span data-stu-id="61cc7-132">Overview of management and APIs</span></span>](management-apis.md)
