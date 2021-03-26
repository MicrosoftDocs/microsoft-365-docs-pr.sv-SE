---
title: Hämta identifieringar till dina SIEM-verktyg från Microsoft Defender för Slutpunkt
description: Lär dig hur du använder REST API och konfigurerar säkerhetsinformation och verktyg för händelsehantering som stöds för att ta emot och dra identifieringar.
keywords: konfigurera siem, säkerhetsinformation och händelsehanteringsverktyg, splunk, arcsight, anpassade indikatorer, rest api, aviseringsdefinitioner, indikatorer på kompromettering
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 97a64c8537ff2a6f9948ed6ed056b8aa7379ce69
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222341"
---
# <a name="pull-detections-to-your-siem-tools"></a><span data-ttu-id="c2f44-104">Dra identifieringar till dina SIEM-verktyg</span><span class="sxs-lookup"><span data-stu-id="c2f44-104">Pull detections to your SIEM tools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c2f44-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="c2f44-105">**Applies to:**</span></span>
- [<span data-ttu-id="c2f44-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="c2f44-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c2f44-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c2f44-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="c2f44-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="c2f44-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c2f44-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="c2f44-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="pull-detections-using-security-information-and-events-management-siem-tools"></a><span data-ttu-id="c2f44-110">Hämta identifieringar med säkerhetsinformations- och händelsehanteringsverktyg (SIEM)</span><span class="sxs-lookup"><span data-stu-id="c2f44-110">Pull detections using security information and events management (SIEM) tools</span></span>

>[!NOTE]
>- <span data-ttu-id="c2f44-111">[Microsoft Defender för slutpunktsavisering](alerts.md) består av en eller flera identifieringar.</span><span class="sxs-lookup"><span data-stu-id="c2f44-111">[Microsoft Defender for Endpoint Alert](alerts.md) is composed from one or more detections.</span></span>
>- <span data-ttu-id="c2f44-112">[Microsoft Defender för identifiering av slutpunkt](api-portal-mapping.md) består av den misstänkta händelsen som inträffade på enheten och tillhörande aviseringsinformation.</span><span class="sxs-lookup"><span data-stu-id="c2f44-112">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>
><span data-ttu-id="c2f44-113">-Microsoft Defender för slutpunktsaviserings-API är det senaste API:t för aviseringsanvändning och innehåller en detaljerad lista med relaterade bevis för varje avisering.</span><span class="sxs-lookup"><span data-stu-id="c2f44-113">-The Microsoft Defender for Endpoint Alert API is the latest API for alert consumption and contain a detailed list of related evidence for each alert.</span></span> <span data-ttu-id="c2f44-114">Mer information finns i [Aviseringsmetoder och egenskaper](alerts.md) och [Listaviseringar.](get-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="c2f44-114">For more information, see [Alert methods and properties](alerts.md) and [List alerts](get-alerts.md).</span></span>

<span data-ttu-id="c2f44-115">Defender för Endpoint har stöd för säkerhetsinformation och händelsehanteringsverktyg (SIEM) för att hämta identifieringar.</span><span class="sxs-lookup"><span data-stu-id="c2f44-115">Defender for Endpoint supports security information and event management (SIEM) tools to pull detections.</span></span> <span data-ttu-id="c2f44-116">Defender för Endpoint visar aviseringar via en HTTPS-slutpunkt som finns i Azure.</span><span class="sxs-lookup"><span data-stu-id="c2f44-116">Defender for Endpoint exposes alerts through an HTTPS endpoint hosted in Azure.</span></span> <span data-ttu-id="c2f44-117">Slutpunkten kan konfigureras för att hämta identifieringar från företagsklientorganisationen i Azure Active Directory (AAD) med OAuth 2.0-autentiseringsprotokoll för ett AAD-program som representerar den specifika SIEM-anslutaren som är installerad i miljön.</span><span class="sxs-lookup"><span data-stu-id="c2f44-117">The endpoint can be configured to pull detections from your enterprise tenant in Azure Active Directory (AAD) using the OAuth 2.0 authentication protocol for an AAD application that represents the specific SIEM connector installed in your environment.</span></span>

<span data-ttu-id="c2f44-118">Defender för Endpoint stöder för närvarande följande specifika SIEM-lösningsverktyg via en dedikerad SIEM-integrationsmodell:</span><span class="sxs-lookup"><span data-stu-id="c2f44-118">Defender for Endpoint currently supports the following specific SIEM solution tools through a dedicated SIEM integration model:</span></span>

- <span data-ttu-id="c2f44-119">IBM QRadar</span><span class="sxs-lookup"><span data-stu-id="c2f44-119">IBM QRadar</span></span>
- <span data-ttu-id="c2f44-120">Micro Focus ArcSight</span><span class="sxs-lookup"><span data-stu-id="c2f44-120">Micro Focus ArcSight</span></span>

<span data-ttu-id="c2f44-121">Andra SIEM-lösningar (till exempel Splunk, RSA NetWitness) stöds via en annan integrationsmodell som baseras på det nya aviserings-API:t.</span><span class="sxs-lookup"><span data-stu-id="c2f44-121">Other SIEM solutions (such as Splunk, RSA NetWitness) are supported through a different integration model based on the new Alert API.</span></span> <span data-ttu-id="c2f44-122">Mer information finns på sidan [Partnerprogram](https://securitycenter.microsoft.com/interoperability/partners) och väljer avsnittet Säkerhetsinformation och analys för fullständig information.</span><span class="sxs-lookup"><span data-stu-id="c2f44-122">For more information, view the [Partner application](https://securitycenter.microsoft.com/interoperability/partners) page and select the Security Information and Analytics section for full details.</span></span>

<span data-ttu-id="c2f44-123">Om du vill använda något av följande SIEM-verktyg som stöds måste du:</span><span class="sxs-lookup"><span data-stu-id="c2f44-123">To use either of these supported SIEM tools, you'll need to:</span></span>

- [<span data-ttu-id="c2f44-124">Aktivera SIEM-integrering i Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="c2f44-124">Enable SIEM integration in Defender for Endpoint</span></span>](enable-siem-integration.md)
- <span data-ttu-id="c2f44-125">Konfigurera det SIEM-verktyg som stöds:</span><span class="sxs-lookup"><span data-stu-id="c2f44-125">Configure the supported SIEM tool:</span></span>
     - [<span data-ttu-id="c2f44-126">Konfigurera Micro Focus ArcSight för att hämta Defender för slutpunktsidentifiering</span><span class="sxs-lookup"><span data-stu-id="c2f44-126">Configure Micro Focus ArcSight to pull Defender for Endpoint detections</span></span>](configure-arcsight.md)
     - <span data-ttu-id="c2f44-127">Konfigurera IBM QRadar för att hämta Defender för slutpunktsidentifiering Mer information finns [i IBM Knowledge Center.](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/com.ibm.dsm.doc/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1)</span><span class="sxs-lookup"><span data-stu-id="c2f44-127">Configure IBM QRadar to pull Defender for Endpoint detections For more information, see [IBM Knowledge Center](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/com.ibm.dsm.doc/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1).</span></span>

<span data-ttu-id="c2f44-128">Mer information om listan över fält som exponeras i det identifierings-API:et finns [i Defender för fält för slutpunktsidentifiering.](api-portal-mapping.md)</span><span class="sxs-lookup"><span data-stu-id="c2f44-128">For more information on the list of fields exposed in the Detection API, see [Defender for Endpoint Detection fields](api-portal-mapping.md).</span></span>
