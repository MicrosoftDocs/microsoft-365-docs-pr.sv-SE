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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 7fdb8ef1689c18945352b30b3ebfe6c176c4034e
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772035"
---
# <a name="overview-of-management-and-apis"></a>Översikt över hantering och API:er 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mgt-apis-abovefoldlink)


Defender för Endpoint har stöd för en mängd olika alternativ för att säkerställa att kunderna enkelt kan använda plattformen. 

Eftersom kundmiljöer och kundstrukturer kan variera skapades Defender för Endpoint med flexibilitet och detaljerad kontroll för att passa olika kundkrav. 

## <a name="endpoint-onboarding-and-portal-access"></a>Slutpunkts onboarding och portalåtkomst 

Registrering av enheter är helt integrerat i Microsoft Endpoint Manager och Microsoft Intune för klientenheter och Azure Defender för serverenheter, med fullständig heltäckande upplevelse av konfiguration, distribution och övervakning. Dessutom har Microsoft Defender för Endpoint stöd för grupprinciper och andra verktyg från tredje part som används för hantering av enheter.

Defender för Endpoint ger mer exakt kontroll över vad användare med åtkomst till portalen kan se och göra genom flexibiliteten hos rollbaserad åtkomstkontroll (RBAC). RBAC-modellen har stöd för alla typer av säkerhetsteamsstruktur:
- Globalt fördelade organisationer och säkerhetsteam
- Team för säkerhetsåtgärder på nivåmodell
- Helt avskiljda avdelningar med en enda centraliserad global säkerhetsgrupp 

## <a name="available-apis"></a>Tillgängliga API:er
Microsoft Defender för Slutpunkt-lösningen är uppbyggd på en plattform som är integrationsklar.

Defender för Slutpunkt visar mycket av dess data och åtgärder via en uppsättning programmässiga API:er. De HÄR API:erna gör det möjligt att automatisera arbetsflöden och nya funktioner baserat på Defender för slutpunktsfunktioner.

![Bild av tillgängligt API och integrering i Microsoft Defender för Endpoint](images/mdatp-apis.png)  

Defender för slutpunkts-API:er kan grupperas i tre:
- Microsoft Defender för slutpunkts-API:er 
- API för direktuppspelning av rådata
- SIEM-integrering

## <a name="microsoft-defender-for-endpoint-apis"></a>Microsoft Defender för slutpunkts-API:er

Defender för Endpoint erbjuder en API-modell med lager som visar data och funktioner i en strukturerad, tydlig och lättanvänd modell som exponeras via en Azure AD-baserad standardmodell för autentisering och auktorisering som ger åtkomst i samband med användare eller SaaS-program. API-modellen har utformats för att visa enheter och funktioner i en konsekvent form. 

Titta på den här videon för en snabb överblick över Defender för Endpoints API:er. 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

I  Undersöknings-API:t visas hur rikt Defender för slutpunkten är – det gör att beräknade eller "profilerade" enheter (till exempel enhet, användare och fil) och olika händelser (till exempel processskapande och skapande av filer) visas, vilket normalt beskriver ett beteende som är relaterat till en entitet, vilket gör att åtkomst till data via undersökningsgränssnitt möjliggör en frågebaserad åtkomst till data. Mer information finns i [API:er som stöds.](exposed-apis-list.md)

Med **Response API** kan du vidta åtgärder i tjänsten och på enheter, vilket gör det möjligt för kunder att mata in indikatorer, hantera inställningar, aviseringsstatus och vidta svarsåtgärder på enheter programmässigt, till exempel isolera enheter från nätverket, karantänfiler och andra. 

## <a name="raw-data-streaming-api"></a>API för direktuppspelning av rådata 
Defender för Endpoints strömnings-API för rådata ger kunder möjlighet att skicka händelser och aviseringar i realtid från sina instanser när de inträffar i en enda dataström, vilket ger en leveransmekanism med låg fördröjning och hög genomflödesleveransmekanism.

Defender för slutpunktshändelseinformation skickas direkt till Azure-lagring för lagring av data långsiktigt eller till Azure Event Hubs för förbrukning av visualiseringstjänster eller ytterligare databehandlingsmotorer. 

Mer information finns i [Raw Data Streaming API](raw-data-export.md).

I den nya Microsoft 365 Defender Streaming API ingår e-post och aviseringshändelser utöver enhetshändelser. Mer information finns i Microsoft 365 [Defender Streaming API.](../defender/streaming-api.md)


## <a name="siem-api"></a>SIEM API
När du aktiverar säkerhetsinformation och händelsehanteringsintegrering (SIEM) kan du hämta identifieringar från Microsoft Defender Säkerhetscenter med hjälp av din SIEM-lösning eller genom att ansluta direkt till REST API för identifieringar. Detta aktiverar informationsavsnittet för SIEM-koppling med ifyllda värden och ett program skapas under Azure Active Directory (Azure AD) klientorganisation. Mer information finns i [SIEM-integrering.](enable-siem-integration.md)

## <a name="related-topics"></a>Relaterade ämnen
- [Få åtkomst till API:er för Microsoft Defender för slutpunkt ](apis-intro.md)
- [API:er som stöds](exposed-apis-list.md)
- [Möjligheter för tekniska partner](partner-integration.md)

