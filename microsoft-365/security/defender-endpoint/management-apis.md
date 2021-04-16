---
title: Översikt över hantering och API:er
ms.reviewer: ''
description: Läs mer om hanteringsverktyg och API-kategorier i Microsoft Defender för Slutpunkt
keywords: onboarding, api, siem, rbac, access, portal, integrering, undersökning, svar, enheter, entitet, användarkontext, programkontext, direktuppspelning
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
ms.openlocfilehash: 9e54fb5f2105f0a77c4b63e8d880135005c17168
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51862097"
---
# <a name="overview-of-management-and-apis"></a><span data-ttu-id="7faf9-104">Översikt över hantering och API:er</span><span class="sxs-lookup"><span data-stu-id="7faf9-104">Overview of management and APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7faf9-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="7faf9-105">**Applies to:**</span></span>
- [<span data-ttu-id="7faf9-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="7faf9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7faf9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7faf9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7faf9-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="7faf9-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7faf9-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="7faf9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mgt-apis-abovefoldlink)


<span data-ttu-id="7faf9-110">Defender för Endpoint har stöd för en mängd olika alternativ för att säkerställa att kunderna enkelt kan använda plattformen.</span><span class="sxs-lookup"><span data-stu-id="7faf9-110">Defender for Endpoint supports a wide variety of options to ensure that customers can easily adopt the platform.</span></span> 

<span data-ttu-id="7faf9-111">Eftersom kundmiljöer och kundstrukturer kan variera skapades Defender för Endpoint med flexibilitet och detaljerad kontroll för att passa olika kundkrav.</span><span class="sxs-lookup"><span data-stu-id="7faf9-111">Acknowledging that customer environments and structures can vary, Defender for Endpoint was created with flexibility and granular control to fit varying customer requirements.</span></span> 

## <a name="endpoint-onboarding-and-portal-access"></a><span data-ttu-id="7faf9-112">Slutpunkts onboarding och portalåtkomst</span><span class="sxs-lookup"><span data-stu-id="7faf9-112">Endpoint onboarding and portal access</span></span> 

<span data-ttu-id="7faf9-113">Enhets onboarding är helt integrerat i Microsoft Endpoint Manager och Microsoft Intune för klientenheter och Azure Säkerhetscenter för serverenheter, med fullständig heltäckande upplevelse av konfiguration, distribution och övervakning.</span><span class="sxs-lookup"><span data-stu-id="7faf9-113">Device onboarding is fully integrated into Microsoft Endpoint Manager and Microsoft Intune for client devices and Azure Security Center for server devices, providing complete end-to-end experience of configuration, deployment, and monitoring.</span></span> <span data-ttu-id="7faf9-114">Dessutom har Microsoft Defender för Endpoint stöd för grupprinciper och andra verktyg från tredje part som används för hantering av enheter.</span><span class="sxs-lookup"><span data-stu-id="7faf9-114">In addition, Microsoft Defender for Endpoint supports Group Policy and other third-party tools used for devices management.</span></span>

<span data-ttu-id="7faf9-115">Defender för Endpoint ger mer exakt kontroll över vad användare med åtkomst till portalen kan se och göra genom flexibiliteten hos rollbaserad åtkomstkontroll (RBAC).</span><span class="sxs-lookup"><span data-stu-id="7faf9-115">Defender for Endpoint provides fine-grained control over what users with access to the portal can see and do through the flexibility of role-based access control (RBAC).</span></span> <span data-ttu-id="7faf9-116">RBAC-modellen har stöd för alla typer av säkerhetsteamsstruktur:</span><span class="sxs-lookup"><span data-stu-id="7faf9-116">The RBAC model supports all flavors of security teams structure:</span></span>
- <span data-ttu-id="7faf9-117">Globalt fördelade organisationer och säkerhetsteam</span><span class="sxs-lookup"><span data-stu-id="7faf9-117">Globally distributed organizations and security teams</span></span>
- <span data-ttu-id="7faf9-118">Team för säkerhetsåtgärder på nivåmodell</span><span class="sxs-lookup"><span data-stu-id="7faf9-118">Tiered model security operations teams</span></span>
- <span data-ttu-id="7faf9-119">Helt avskiljda avdelningar med en enda centraliserad global säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="7faf9-119">Fully segregated divisions with single centralized global security operations teams</span></span> 

## <a name="available-apis"></a><span data-ttu-id="7faf9-120">Tillgängliga API:er</span><span class="sxs-lookup"><span data-stu-id="7faf9-120">Available APIs</span></span>
<span data-ttu-id="7faf9-121">Microsoft Defender för Slutpunkt-lösningen är uppbyggd på en plattform som är integrationsklar.</span><span class="sxs-lookup"><span data-stu-id="7faf9-121">The Microsoft Defender for Endpoint solution is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="7faf9-122">Defender för Slutpunkt visar mycket av dess data och åtgärder via en uppsättning programmässiga API:er.</span><span class="sxs-lookup"><span data-stu-id="7faf9-122">Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="7faf9-123">De HÄR API:erna gör det möjligt att automatisera arbetsflöden och nya funktioner baserat på Defender för slutpunktsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="7faf9-123">Those APIs will enable you to automate workflows and innovate based on Defender for Endpoint capabilities.</span></span>

![Bild av tillgängligt API och integrering i Microsoft Defender för Endpoint](images/mdatp-apis.png)  

<span data-ttu-id="7faf9-125">Defender för slutpunkts-API:er kan grupperas i tre:</span><span class="sxs-lookup"><span data-stu-id="7faf9-125">The Defender for Endpoint APIs can be grouped into three:</span></span>
- <span data-ttu-id="7faf9-126">Microsoft Defender för slutpunkts-API:er</span><span class="sxs-lookup"><span data-stu-id="7faf9-126">Microsoft Defender for Endpoint APIs</span></span> 
- <span data-ttu-id="7faf9-127">API för direktuppspelning av rådata</span><span class="sxs-lookup"><span data-stu-id="7faf9-127">Raw data streaming API</span></span>
- <span data-ttu-id="7faf9-128">SIEM-integrering</span><span class="sxs-lookup"><span data-stu-id="7faf9-128">SIEM integration</span></span>

## <a name="microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="7faf9-129">Microsoft Defender för slutpunkts-API:er</span><span class="sxs-lookup"><span data-stu-id="7faf9-129">Microsoft Defender for Endpoint APIs</span></span>

<span data-ttu-id="7faf9-130">Defender för Endpoint erbjuder en API-modell med lager som visar data och funktioner i en strukturerad, tydlig och lättanvänd modell som exponeras via en Azure AD-baserad standardmodell för autentisering och auktorisering som ger åtkomst i samband med användare eller SaaS-program.</span><span class="sxs-lookup"><span data-stu-id="7faf9-130">Defender for Endpoint offers a layered API model exposing data and capabilities in a structured, clear, and easy to use model, exposed through a standard Azure  AD-based authentication and authorization model allowing access in context of users or SaaS applications.</span></span> <span data-ttu-id="7faf9-131">API-modellen har utformats för att visa enheter och funktioner i en konsekvent form.</span><span class="sxs-lookup"><span data-stu-id="7faf9-131">The API model was designed to expose entities and capabilities in a consistent form.</span></span> 

<span data-ttu-id="7faf9-132">Titta på den här videon för en snabb överblick över Defender för Endpoints API:er.</span><span class="sxs-lookup"><span data-stu-id="7faf9-132">Watch this video for a quick overview of Defender for Endpoint's APIs.</span></span> 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

<span data-ttu-id="7faf9-133">I  Undersöknings-API:t visas hur rikt Defender för slutpunkten är – det gör att beräknade eller "profilerade" enheter (till exempel enhet, användare och fil) och olika händelser (till exempel processskapande och skapande av filer) visas, vilket normalt beskriver ett beteende som är relaterat till en entitet, vilket gör att åtkomst till data via undersökningsgränssnitt möjliggör en frågebaserad åtkomst till data.</span><span class="sxs-lookup"><span data-stu-id="7faf9-133">The **Investigation API** exposes the richness of Defender for Endpoint - exposing calculated or 'profiled' entities (for example, device, user, and file) and discrete events (for example, process creation and file creation) which typically describes a behavior related to an entity, enabling access to data via investigation interfaces allowing a query-based access to data.</span></span> <span data-ttu-id="7faf9-134">Mer information finns i [API:er som stöds.](exposed-apis-list.md)</span><span class="sxs-lookup"><span data-stu-id="7faf9-134">For more information, see [Supported APIs](exposed-apis-list.md).</span></span>

<span data-ttu-id="7faf9-135">Med **Response API** kan du vidta åtgärder i tjänsten och på enheter, vilket gör det möjligt för kunder att mata in indikatorer, hantera inställningar, aviseringsstatus och vidta svarsåtgärder på enheter programmässigt, till exempel isolera enheter från nätverket, karantänfiler och andra.</span><span class="sxs-lookup"><span data-stu-id="7faf9-135">The **Response API** exposes the ability to take actions in the service and on devices, enabling customers to ingest indicators, manage settings, alert status, as well as take response actions on devices programmatically such as isolate devices from the network, quarantine files, and others.</span></span> 

## <a name="raw-data-streaming-api"></a><span data-ttu-id="7faf9-136">API för direktuppspelning av rådata</span><span class="sxs-lookup"><span data-stu-id="7faf9-136">Raw data streaming API</span></span> 
<span data-ttu-id="7faf9-137">Defender för Endpoints strömnings-API för rådata ger kunder möjlighet att skicka händelser och aviseringar i realtid från sina instanser när de inträffar i en enda dataström, vilket ger en leveransmekanism med låg fördröjning och hög genomflödesleveransmekanism.</span><span class="sxs-lookup"><span data-stu-id="7faf9-137">Defender for Endpoint raw data streaming API provides the ability for customers to ship real-time events and alerts from their instances as they occur within a single data stream, providing a low latency, high throughput delivery mechanism.</span></span>

<span data-ttu-id="7faf9-138">Defender för slutpunktshändelseinformation skickas direkt till Azure-lagring för lagring av data långsiktigt eller till Azure Event Hubs för förbrukning av visualiseringstjänster eller ytterligare databehandlingsmotorer.</span><span class="sxs-lookup"><span data-stu-id="7faf9-138">The Defender for Endpoint event information is pushed directly to Azure storage for long-term data retention, or to Azure Event Hubs for consumption by visualization services or additional data processing engines.</span></span> 

<span data-ttu-id="7faf9-139">Mer information finns i [Raw Data Streaming API](raw-data-export.md).</span><span class="sxs-lookup"><span data-stu-id="7faf9-139">For more information, see [Raw data streaming API](raw-data-export.md).</span></span>


## <a name="siem-api"></a><span data-ttu-id="7faf9-140">SIEM API</span><span class="sxs-lookup"><span data-stu-id="7faf9-140">SIEM API</span></span>
<span data-ttu-id="7faf9-141">När du aktiverar säkerhetsinformation och händelsehanteringsintegrering (SIEM) kan du hämta identifieringar från Microsoft Defender Säkerhetscenter med din SIEM-lösning eller genom att ansluta direkt till REST API för identifieringar.</span><span class="sxs-lookup"><span data-stu-id="7faf9-141">When you enable security information and event management (SIEM) integration, it allows you to pull detections from Microsoft Defender Security Center using your SIEM solution or by connecting directly to the detections REST API.</span></span> <span data-ttu-id="7faf9-142">Då aktiveras åtkomstinformationsavsnittet för SIEM-anslutningen med ifyllda värden och ett program skapas under Azure Active Directory-klienten (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="7faf9-142">This activates the SIEM connector access details section with pre-populated values and an application is created under your Azure Active Directory (Azure AD) tenant.</span></span> <span data-ttu-id="7faf9-143">Mer information finns i [SIEM-integrering.](enable-siem-integration.md)</span><span class="sxs-lookup"><span data-stu-id="7faf9-143">For more information, see [SIEM integration](enable-siem-integration.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="7faf9-144">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="7faf9-144">Related topics</span></span>
- [<span data-ttu-id="7faf9-145">Få åtkomst till API:er för Microsoft Defender för slutpunkt </span><span class="sxs-lookup"><span data-stu-id="7faf9-145">Access the Microsoft Defender for Endpoint APIs </span></span>](apis-intro.md)
- [<span data-ttu-id="7faf9-146">API:er som stöds</span><span class="sxs-lookup"><span data-stu-id="7faf9-146">Supported APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="7faf9-147">Möjligheter för tekniska partner</span><span class="sxs-lookup"><span data-stu-id="7faf9-147">Technical partner opportunities</span></span>](partner-integration.md)

