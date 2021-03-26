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
# <a name="pull-detections-to-your-siem-tools"></a>Dra identifieringar till dina SIEM-verktyg

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="pull-detections-using-security-information-and-events-management-siem-tools"></a>Hämta identifieringar med säkerhetsinformations- och händelsehanteringsverktyg (SIEM)

>[!NOTE]
>- [Microsoft Defender för slutpunktsavisering](alerts.md) består av en eller flera identifieringar.
>- [Microsoft Defender för identifiering av slutpunkt](api-portal-mapping.md) består av den misstänkta händelsen som inträffade på enheten och tillhörande aviseringsinformation.
>-Microsoft Defender för slutpunktsaviserings-API är det senaste API:t för aviseringsanvändning och innehåller en detaljerad lista med relaterade bevis för varje avisering. Mer information finns i [Aviseringsmetoder och egenskaper](alerts.md) och [Listaviseringar.](get-alerts.md)

Defender för Endpoint har stöd för säkerhetsinformation och händelsehanteringsverktyg (SIEM) för att hämta identifieringar. Defender för Endpoint visar aviseringar via en HTTPS-slutpunkt som finns i Azure. Slutpunkten kan konfigureras för att hämta identifieringar från företagsklientorganisationen i Azure Active Directory (AAD) med OAuth 2.0-autentiseringsprotokoll för ett AAD-program som representerar den specifika SIEM-anslutaren som är installerad i miljön.

Defender för Endpoint stöder för närvarande följande specifika SIEM-lösningsverktyg via en dedikerad SIEM-integrationsmodell:

- IBM QRadar
- Micro Focus ArcSight

Andra SIEM-lösningar (till exempel Splunk, RSA NetWitness) stöds via en annan integrationsmodell som baseras på det nya aviserings-API:t. Mer information finns på sidan [Partnerprogram](https://securitycenter.microsoft.com/interoperability/partners) och väljer avsnittet Säkerhetsinformation och analys för fullständig information.

Om du vill använda något av följande SIEM-verktyg som stöds måste du:

- [Aktivera SIEM-integrering i Defender för Slutpunkt](enable-siem-integration.md)
- Konfigurera det SIEM-verktyg som stöds:
     - [Konfigurera Micro Focus ArcSight för att hämta Defender för slutpunktsidentifiering](configure-arcsight.md)
     - Konfigurera IBM QRadar för att hämta Defender för slutpunktsidentifiering Mer information finns [i IBM Knowledge Center.](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/com.ibm.dsm.doc/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1)

Mer information om listan över fält som exponeras i det identifierings-API:et finns [i Defender för fält för slutpunktsidentifiering.](api-portal-mapping.md)
