---
title: Instrumentpanelinsikter – Hantering av hot och säkerhetsrisker
description: Den Hantering av hot och säkerhetsrisker kan hjälpa SecOps och säkerhetsadministratörer att hantera hot mot cybersäkerhet och bygga upp organisationens säkerhetsåterresiliens.
keywords: Microsoft Defender för Endpoint-tvm, Microsoft Defender för Endpoint-tvm-instrumentpanel, & hantering av säkerhetsrisker, Hantering av hot och säkerhetsrisker, riskbaserade hot & hantering av säkerhetsrisker, säkerhetskonfiguration, Microsoft Secure Score för enheter, exponeringsresultat
search.appverid: met150
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 82b6123a99eb406918708c6bf23b870ef3bc3d79
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934147"
---
# <a name="dashboard-insights---threat-and-vulnerability-management"></a>Instrumentpanelinsikter – Hantering av hot och säkerhetsrisker

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Hot och hantering av säkerhetsrisker](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Hot och hantering av säkerhetsrisker är en komponent i Defender för Endpoint och ger både säkerhetsadministratörer och säkerhetsoperationsteam ett unikt värde, inklusive:


- Realtids-identifiering och åtgärd på slutpunkt (Identifiering och åtgärd på slutpunkt) korrelerade med svagheter i slutpunkten
- Ovärderliga enhetssäkerhetsproblem under incidentundersökningar
- Inbyggda åtgärdsprocesser genom Microsoft Intune och Microsoft Endpoint Configuration Manager  
  
Du kan använda Hantering av hot och säkerhetsrisker [i](https://securitycenter.windows.com/) Microsoft Defender Säkerhetscenter:

- Visa exponeringsresultat och Microsoft Secure Score för enheter, tillsammans med de viktigaste säkerhetsrekommendationerna, programbrister, åtgärder och exponerade enheter
- Korrelera Identifiering och åtgärd på slutpunkt med slutpunktsbrister och bearbeta dem
- Välj alternativ för åtgärder för att åtgärda och spåra åtgärder
- Välja undantagsalternativ och spåra aktiva undantag

> [!NOTE]
> Enheter som inte är aktiva under de senaste 30 dagarna indelade inte i de data som återspeglar din organisations Hantering av hot och säkerhetsrisker exponeringsresultat och Microsoft Secure Score för enheter.

Titta på den här videon för en snabb överblick över vad som finns på Hantering av hot och säkerhetsrisker instrumentpanel.

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r1nv]

## <a name="threat-and-vulnerability-management-dashboard"></a>Hot och hantering av säkerhetsrisker instrumentpanel

 ![Microsoft Defender för Slutpunktsportalen](images/tvm-dashboard-devices.png)

Område | Beskrivning
:---|:---
**Valda enhetsgrupper (#/#)**   | Filtrera de Hantering av hot och säkerhetsrisker data du vill se på instrumentpanelen och korten efter enhetsgrupper. Det du väljer i filtret gäller i Hantering av hot och säkerhetsrisker sidor.
[**Exponeringsvärde**](tvm-exposure-score.md)   | Se den aktuella statusen för organisationens exponering av enheter för hot och säkerhetsproblem. Flera faktorer påverkar organisationens exponeringsresultat: identifierad av dina enheter, hur sannolikt det är att dina enheter bryter sig, enheternas värde i organisationen och relevanta aviseringar som upptäcks med dina enheter. Målet är att minska exponeringsresultatet för organisationen för att vara säkrare. För att minska poäng måste du åtgärda relaterade problem med säkerhetskonfigurationen som anges i säkerhetsrekommendationerna.
[**Microsoft Secure Score för enheter**](tvm-microsoft-secure-score-devices.md) | Se säkerheten för operativsystemet, programmen, nätverket, kontona och säkerhetskontrollerna för din organisation. Målet är att åtgärda relaterade problem med säkerhetskonfigurationen för att öka poäng för enheter. Om du markerar staplarna kommer du till sidan **Med säkerhetsrekommendationer.**
**Exponeringsfördelning för enhet** | Se hur många enheter som är exponerade baserat på deras exponeringsnivå. Välj ett avsnitt i ringdiagrammet för  att gå till listsidan Enheter och visa namn på enheter, exponeringsnivå, risknivå och annan information som domän, operativsystemplattform, status, när den senast sågs och dess taggar.
**De viktigaste säkerhetsrekommendationerna** | Se de sorteringsbaserade säkerhetsrekommendationer som sorteras och prioriteras utifrån organisationens risk exponering och hur brådskande det är. Välj **Visa mer** om du vill se resten av säkerhetsrekommendationerna i listan. Välj **Visa undantag** för listan med rekommendationer som har ett undantag.
**Mest sårbar programvara** | Få insyn i din organisations programvaruinventering i realtid med en staplad lista över sårbar programvara installerad på nätverkets enheter och hur de påverkar organisationens exponeringsresultat. Välj ett objekt om du vill **ha mer information eller** Visa mer om du vill se resten av listan över sårbara program på sidan för lager **av** programvara.
**De viktigaste åtgärdsaktiviteterna** | Spåra de åtgärdsaktiviteter som genereras från säkerhetsrekommendationerna. Du kan markera varje objekt i listan  om du vill  se information på sidan Åtgärd eller välja Visa mer för att visa resten av åtgärdsaktiviteterna och aktiva undantag.
**De mest exponerade enheterna** | Visa namn på exponerade enheter och deras exponeringsnivå. Välj ett enhetsnamn i listan för att gå till sidan för enheten där du kan visa varningar, risker, incidenter, säkerhetsrekommendationer, installerad programvara och identifierade säkerhetsproblem kopplade till de exponerade enheterna. Välj **Visa mer** om du vill se resten av listan över exponerade enheter. I enhetslistan kan du hantera taggar, initiera automatiska undersökningar, starta en svarssession, samla in ett undersökningspaket, köra antivirussökning, begränsa appkörning och isolera enhet.

Mer information om ikoner som används i portalen finns i [Microsoft Defender för Slutpunktsikoner](portal-overview.md#microsoft-defender-for-endpoint-icons).


## <a name="related-topics"></a>Relaterade ämnen

- [Översikt över hantering av säkerhetsrisker hot och hot](next-gen-threat-and-vuln-mgt.md)
- [Exponeringsvärde](tvm-exposure-score.md)
- [Microsoft Secure Score för enheter](tvm-microsoft-secure-score-devices.md)
- [Säkerhetsrekommendationer](tvm-security-recommendation.md)
- [Programvaruinventering](tvm-software-inventory.md)
- [Tidlinje för händelse](threat-and-vuln-mgt-event-timeline.md)

