---
title: Översikt över avancerad sökning i Microsoft Defender ATP
description: Använda sökfunktioner för hot i Microsoft Defender ATP för att skapa frågor som hittar hot och svagheter i ditt nätverk
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp, search, query, telemetry, custom detections, schema, kusto, time zone, UTC
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4883a4f04f06774d02aa0d942edc841867eb36b6
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499513"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting"></a>Proaktiv sökning efter hot med avancerad sökning

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

Avancerad sökning är ett frågebaserat verktyg för hothot där du kan utforska upp till 30 dagars rådata. Du kan proaktivt kontrollera händelser i nätverket för att hitta hotindikatorer och enheter. Den flexibla åtkomsten till data gör att du inte behöver hålla efter både kända och potentiella hot.

I den här videon får du en snabb överblick över avancerad sökning och en kort självstudiekurs som hjälper dig att komma igång snabbt.
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqo]

Du kan använda samma hotsökningsfrågor för att skapa anpassade identifieringsregler. Dessa regler körs automatiskt för att kontrollera och sedan svara på misstänkt intrång, felkonfigurerade datorer och andra resultat.

>[!TIP]
>Använd [avancerad sökning i Microsoft Threat Protection för](https://docs.microsoft.com/microsoft-365/security/defender/advanced-hunting-overview) att leta efter hot med hjälp av data från Defender för Slutpunkt, Microsoft Defender för Office 365, Microsoft Cloud App Security och Microsoft Defender för identitet. [Aktivera Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/mtp-enable)

## <a name="get-started-with-advanced-hunting"></a>Komma igång med avancerad sökning

Gå igenom följande steg för att öka din avancerade kunskaper om sökning.

Vi rekommenderar att du går igenom flera olika steg för att snabbt komma igång med avancerad sökning.

| Utbildningsmål | Beskrivning | Resurs |
|--|--|--|
| **Lär dig språket** | Avancerad sökning baseras på [Kusto-frågespråk som](https://docs.microsoft.com/azure/kusto/query/)har stöd för samma syntax och operatorer. Börja lära dig frågespråket genom att köra den första frågan. | [Översikt över frågespråk](advanced-hunting-query-language.md) |
| **Lär dig hur du använder frågeresultatet** | Läs mer om diagram och olika sätt att visa eller exportera resultaten. Se hur du snabbt kan justera frågorna och öka detaljinformationen. | [Arbeta med frågeresultat](advanced-hunting-query-results.md) |
| **Förstå schemat** | Få en bra förståelse på hög nivå för tabellerna i schemat och deras kolumner. Lär dig var du letar efter data när du skapar dina frågor. | [Schemareferens](advanced-hunting-schema-reference.md) |
| **Använda fördefinierade frågor** | Utforska samlingar av fördefinierade frågor som täcker olika scenarier för hot efter hot. | [Delade frågor](advanced-hunting-shared-queries.md) |
| **Optimera frågor och hantera fel** | Förstå hur du skapar effektiva och felfria frågor. | - [Metodtips för frågor](advanced-hunting-best-practices.md)<br>- [Hantera fel](advanced-hunting-errors.md) |
| **Få fullständig täckning** | Använd granskningsinställningarna för att ge din organisation bättre datatäckning. | - [Utöka den avancerade söktäckningen](advanced-hunting-extend-data.md) |
| **Gör en snabb undersökning** | Kör snabbt en avancerad fråga för sökning för att undersöka misstänkt aktivitet. | - [Snabbt jaga efter entitets- eller händelseinformation med *go-hunt*](advanced-hunting-go-hunt.md) |
| **Innehåller hot och adresskomprometter** | Svara på attacker genom att kvartilering av filer, begränsa körning av appar och andra åtgärder | - [Vidta åtgärder för avancerade frågeresultat för sökning](advanced-hunting-take-action.md) |
| **Skapa anpassade identifieringsregler** | Förstå hur du kan använda avancerade sökfrågor för att utlösa aviseringar och vidta svarsåtgärder automatiskt. | - [Översikt över anpassade identifieringar](overview-custom-detections.md)<br>- [Anpassade identifieringsregler](custom-detection-rules.md) |

## <a name="data-freshness-and-update-frequency"></a>Datauppdatering och uppdateringsfrekvens

Avancerade sökdata kan kategoriseras i två distinkta typer, som var och en konsolideras på olika sätt.

- **Händelse- eller aktivitetsdata**– fyller i tabeller om aviseringar, säkerhetshändelser, systemhändelser och rutinmässiga utvärderingar. Avancerad sökning tar emot dessa data nästan omedelbart efter att de signaler som samlar in dem överför dem till Defender för Endpoint.
- **Entitetsdata**– fyller i tabeller med konsoliderad information om användare och enheter. Dessa data kommer från både relativt statiska datakällor och dynamiska källor, till exempel Active Directory-poster och händelseloggar. För att ge nya data uppdateras tabeller med ny information var 15:e minut, vilket innebär att rader som kanske inte är helt ifyllda läggs till. Varje dygn konsolideras data för att infoga en post som innehåller den senaste och mest omfattande datauppsättningen om varje entitet.

## <a name="time-zone"></a>Tidszon

Tidsinformation för avancerad sökning finns för närvarande i UTC-tidszonen.

## <a name="related-topics"></a>Relaterade ämnen

- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Arbeta med frågeresultat](advanced-hunting-query-results.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Förstå schemat](advanced-hunting-schema-reference.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
- [Översikt över anpassade identifieringar](overview-custom-detections.md)