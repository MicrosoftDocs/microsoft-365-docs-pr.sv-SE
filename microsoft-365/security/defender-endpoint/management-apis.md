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
ms.openlocfilehash: 78ab364f8a261b1201fad17ebf86adc1a7456a46
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730845"
---
# <a name="overview-of-management-and-apis"></a><span data-ttu-id="a23b8-104">Översikt över hantering och API:er</span><span class="sxs-lookup"><span data-stu-id="a23b8-104">Overview of management and APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a23b8-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="a23b8-105">**Applies to:**</span></span>
- [<span data-ttu-id="a23b8-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="a23b8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a23b8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a23b8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a23b8-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="a23b8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a23b8-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="a23b8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mgt-apis-abovefoldlink)


<span data-ttu-id="a23b8-110">Defender för Endpoint har stöd för en mängd olika alternativ för att säkerställa att kunderna enkelt kan använda plattformen.</span><span class="sxs-lookup"><span data-stu-id="a23b8-110">Defender for Endpoint supports a wide variety of options to ensure that customers can easily adopt the platform.</span></span> 

<span data-ttu-id="a23b8-111">Eftersom kundmiljöer och kundstrukturer kan variera skapades Defender för Endpoint med flexibilitet och detaljerad kontroll för att passa olika kundkrav.</span><span class="sxs-lookup"><span data-stu-id="a23b8-111">Acknowledging that customer environments and structures can vary, Defender for Endpoint was created with flexibility and granular control to fit varying customer requirements.</span></span> 

## <a name="endpoint-onboarding-and-portal-access"></a><span data-ttu-id="a23b8-112">Slutpunkts onboarding och portalåtkomst</span><span class="sxs-lookup"><span data-stu-id="a23b8-112">Endpoint onboarding and portal access</span></span> 

<span data-ttu-id="a23b8-113">Registrering av enheter är helt integrerat i Microsoft Endpoint Manager och Microsoft Intune för klientenheter och Azure Defender för serverenheter, med fullständig heltäckande upplevelse av konfiguration, distribution och övervakning.</span><span class="sxs-lookup"><span data-stu-id="a23b8-113">Device onboarding is fully integrated into Microsoft Endpoint Manager and Microsoft Intune for client devices and Azure Defender for server devices, providing complete end-to-end experience of configuration, deployment, and monitoring.</span></span> <span data-ttu-id="a23b8-114">Dessutom har Microsoft Defender för Endpoint stöd för grupprinciper och andra verktyg från tredje part som används för hantering av enheter.</span><span class="sxs-lookup"><span data-stu-id="a23b8-114">In addition, Microsoft Defender for Endpoint supports Group Policy and other third-party tools used for devices management.</span></span>

<span data-ttu-id="a23b8-115">Defender för Endpoint ger mer exakt kontroll över vad användare med åtkomst till portalen kan se och göra genom flexibiliteten hos rollbaserad åtkomstkontroll (RBAC).</span><span class="sxs-lookup"><span data-stu-id="a23b8-115">Defender for Endpoint provides fine-grained control over what users with access to the portal can see and do through the flexibility of role-based access control (RBAC).</span></span> <span data-ttu-id="a23b8-116">RBAC-modellen har stöd för alla typer av säkerhetsteamsstruktur:</span><span class="sxs-lookup"><span data-stu-id="a23b8-116">The RBAC model supports all flavors of security teams structure:</span></span>
- <span data-ttu-id="a23b8-117">Globalt fördelade organisationer och säkerhetsteam</span><span class="sxs-lookup"><span data-stu-id="a23b8-117">Globally distributed organizations and security teams</span></span>
- <span data-ttu-id="a23b8-118">Team för säkerhetsåtgärder på nivåmodell</span><span class="sxs-lookup"><span data-stu-id="a23b8-118">Tiered model security operations teams</span></span>
- <span data-ttu-id="a23b8-119">Helt avskiljda avdelningar med en enda centraliserad global säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="a23b8-119">Fully segregated divisions with single centralized global security operations teams</span></span> 

## <a name="available-apis"></a><span data-ttu-id="a23b8-120">Tillgängliga API:er</span><span class="sxs-lookup"><span data-stu-id="a23b8-120">Available APIs</span></span>
<span data-ttu-id="a23b8-121">Microsoft Defender för Slutpunkt-lösningen är uppbyggd på en plattform som är integrationsklar.</span><span class="sxs-lookup"><span data-stu-id="a23b8-121">The Microsoft Defender for Endpoint solution is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="a23b8-122">Defender för Slutpunkt visar mycket av dess data och åtgärder via en uppsättning programmässiga API:er.</span><span class="sxs-lookup"><span data-stu-id="a23b8-122">Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="a23b8-123">De HÄR API:erna gör det möjligt att automatisera arbetsflöden och nya funktioner baserat på Defender för slutpunktsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="a23b8-123">Those APIs will enable you to automate workflows and innovate based on Defender for Endpoint capabilities.</span></span>

![Bild av tillgängligt API och integrering i Microsoft Defender för Endpoint](images/mdatp-apis.png)  

<span data-ttu-id="a23b8-125">Defender för slutpunkts-API:er kan grupperas i tre:</span><span class="sxs-lookup"><span data-stu-id="a23b8-125">The Defender for Endpoint APIs can be grouped into three:</span></span>
- <span data-ttu-id="a23b8-126">Microsoft Defender för slutpunkts-API:er</span><span class="sxs-lookup"><span data-stu-id="a23b8-126">Microsoft Defender for Endpoint APIs</span></span> 
- <span data-ttu-id="a23b8-127">API för direktuppspelning av rådata</span><span class="sxs-lookup"><span data-stu-id="a23b8-127">Raw data streaming API</span></span>
- <span data-ttu-id="a23b8-128">SIEM-integrering</span><span class="sxs-lookup"><span data-stu-id="a23b8-128">SIEM integration</span></span>

## <a name="microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="a23b8-129">Microsoft Defender för slutpunkts-API:er</span><span class="sxs-lookup"><span data-stu-id="a23b8-129">Microsoft Defender for Endpoint APIs</span></span>

<span data-ttu-id="a23b8-130">Defender för Endpoint erbjuder en API-modell med lager som visar data och funktioner i en strukturerad, tydlig och lättanvänd modell som exponeras via en Azure AD-baserad standardmodell för autentisering och auktorisering som ger åtkomst i samband med användare eller SaaS-program.</span><span class="sxs-lookup"><span data-stu-id="a23b8-130">Defender for Endpoint offers a layered API model exposing data and capabilities in a structured, clear, and easy to use model, exposed through a standard Azure  AD-based authentication and authorization model allowing access in context of users or SaaS applications.</span></span> <span data-ttu-id="a23b8-131">API-modellen har utformats för att visa enheter och funktioner i en konsekvent form.</span><span class="sxs-lookup"><span data-stu-id="a23b8-131">The API model was designed to expose entities and capabilities in a consistent form.</span></span> 

<span data-ttu-id="a23b8-132">Titta på den här videon för en snabb överblick över Defender för Endpoints API:er.</span><span class="sxs-lookup"><span data-stu-id="a23b8-132">Watch this video for a quick overview of Defender for Endpoint's APIs.</span></span> 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

<span data-ttu-id="a23b8-133">I  Undersöknings-API:t visas hur rikt Defender för slutpunkten är – det gör att beräknade eller "profilerade" enheter (till exempel enhet, användare och fil) och olika händelser (till exempel processskapande och skapande av filer) visas, vilket normalt beskriver ett beteende som är relaterat till en entitet, vilket gör att åtkomst till data via undersökningsgränssnitt möjliggör en frågebaserad åtkomst till data.</span><span class="sxs-lookup"><span data-stu-id="a23b8-133">The **Investigation API** exposes the richness of Defender for Endpoint - exposing calculated or 'profiled' entities (for example, device, user, and file) and discrete events (for example, process creation and file creation) which typically describes a behavior related to an entity, enabling access to data via investigation interfaces allowing a query-based access to data.</span></span> <span data-ttu-id="a23b8-134">Mer information finns i [API:er som stöds.](exposed-apis-list.md)</span><span class="sxs-lookup"><span data-stu-id="a23b8-134">For more information, see [Supported APIs](exposed-apis-list.md).</span></span>

<span data-ttu-id="a23b8-135">Med **Response API** kan du vidta åtgärder i tjänsten och på enheter, vilket gör det möjligt för kunder att mata in indikatorer, hantera inställningar, aviseringsstatus och vidta svarsåtgärder på enheter programmässigt, till exempel isolera enheter från nätverket, karantänfiler och andra.</span><span class="sxs-lookup"><span data-stu-id="a23b8-135">The **Response API** exposes the ability to take actions in the service and on devices, enabling customers to ingest indicators, manage settings, alert status, as well as take response actions on devices programmatically such as isolate devices from the network, quarantine files, and others.</span></span> 

## <a name="streaming-api"></a><span data-ttu-id="a23b8-136">Streaming API</span><span class="sxs-lookup"><span data-stu-id="a23b8-136">Streaming API</span></span> 
<span data-ttu-id="a23b8-137">Direktuppspelnings-API gör det möjligt för kunder att skicka händelser och aviseringar i realtid från sina instanser när de inträffar i en enda dataström, vilket ger en låg latens och hög leveransmekanism för dataflöde.</span><span class="sxs-lookup"><span data-stu-id="a23b8-137">Streaming API provides the ability for customers to ship real-time events and alerts from their instances as they occur within a single data stream, providing a low latency, high throughput delivery mechanism.</span></span>

<span data-ttu-id="a23b8-138">Händelseinformation skickas direkt till Azure-lagring för lagring av data långsiktigt eller till Azure Event Hubs för förbrukning av visualiseringstjänster eller ytterligare databehandlingsmotorer.</span><span class="sxs-lookup"><span data-stu-id="a23b8-138">Event information is pushed directly to Azure storage for long-term data retention, or to Azure Event Hubs for consumption by visualization services or additional data processing engines.</span></span> 

>[!NOTE]
><span data-ttu-id="a23b8-139">Streaming API har nu flyttats till Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="a23b8-139">Streaming API has now moved to Microsoft 365 Defender.</span></span> <span data-ttu-id="a23b8-140">Mer information finns i [Streaming API](raw-data-export.md).</span><span class="sxs-lookup"><span data-stu-id="a23b8-140">For more information, see [Streaming API](raw-data-export.md).</span></span>


## <a name="siem-api"></a><span data-ttu-id="a23b8-141">SIEM API</span><span class="sxs-lookup"><span data-stu-id="a23b8-141">SIEM API</span></span>
<span data-ttu-id="a23b8-142">När du aktiverar säkerhetsinformation och händelsehanteringsintegrering (SIEM) kan du hämta identifieringar från Microsoft Defender Säkerhetscenter med hjälp av din SIEM-lösning eller genom att ansluta direkt till REST API för identifieringar.</span><span class="sxs-lookup"><span data-stu-id="a23b8-142">When you enable security information and event management (SIEM) integration, it allows you to pull detections from Microsoft Defender Security Center using your SIEM solution or by connecting directly to the detections REST API.</span></span> <span data-ttu-id="a23b8-143">Detta aktiverar informationsavsnittet för SIEM-koppling med ifyllda värden och ett program skapas under Azure Active Directory (Azure AD) klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="a23b8-143">This activates the SIEM connector access details section with pre-populated values and an application is created under your Azure Active Directory (Azure AD) tenant.</span></span> <span data-ttu-id="a23b8-144">Mer information finns i [SIEM-integrering.](enable-siem-integration.md)</span><span class="sxs-lookup"><span data-stu-id="a23b8-144">For more information, see [SIEM integration](enable-siem-integration.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="a23b8-145">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="a23b8-145">Related topics</span></span>
- [<span data-ttu-id="a23b8-146">Få åtkomst till API:er för Microsoft Defender för slutpunkt </span><span class="sxs-lookup"><span data-stu-id="a23b8-146">Access the Microsoft Defender for Endpoint APIs </span></span>](apis-intro.md)
- [<span data-ttu-id="a23b8-147">API:er som stöds</span><span class="sxs-lookup"><span data-stu-id="a23b8-147">Supported APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="a23b8-148">Möjligheter för tekniska partner</span><span class="sxs-lookup"><span data-stu-id="a23b8-148">Technical partner opportunities</span></span>](partner-integration.md)

