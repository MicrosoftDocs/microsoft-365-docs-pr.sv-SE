---
title: Översikt – Avancerad sökning
description: Läs mer om avancerade sökfrågor i Microsoft 365 och hur du använder dem för att proaktivt hitta hot och svagheter i nätverket
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, custom detections, schema, kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: df48ec921dee7d8f3b441ed3f68ed148c5c6c857
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932983"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a>Proaktiv sökning efter hot med avancerad sökning i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

> Vill du uppleva Microsoft 365 Defender? Du kan [utvärdera det i en laboratoriemiljö](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) eller [köra ett pilotprojekt i produktionen](m365d-pilot.md?ocid=cx-evalpilot).
>

Avancerad sökning är ett frågebaserat verktyg för hothot där du kan utforska upp till 30 dagars rådata. Du kan proaktivt kontrollera händelser i nätverket för att hitta hotindikatorer och enheter. Den flexibla åtkomsten till data gör att du inte behöver hålla efter både kända och potentiella hot.
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

Du kan använda samma hotsökningsfrågor för att skapa anpassade identifieringsregler. Dessa regler körs automatiskt för att kontrollera och sedan svara på misstänkt intrång, felkonfigurerade datorer och andra resultat.

Den här funktionen liknar avancerad sökning [i Microsoft Defender för Slutpunkt.](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) Den här funktionen finns tillgänglig i Microsoft 365 Säkerhetscenter och stöder frågor som kontrollerar en bredare datauppsättning från:

- Microsoft Defender för Endpoint
- Microsoft Defender för Office 365
- Microsoft Cloud App Security
- Microsoft Defender for Identity

Om du vill använda avancerad sökning [aktiverar du Microsoft 365 Defender.](m365d-enable.md)

### <a name="before-you-begin"></a>Innan du börjar

Användarna behöver någon av följande behörighetsnivåer för att få åtkomst till Microsoft Defender:

- Fullständig åtkomst (läsning och skrivning)
- Skrivskyddade åtkomst

**Fullständig åtkomst:** Användare med fullständig åtkomst kan spara, ändra och dela en fråga. Om du vill tilldela fullständiga åtkomstbehörigheter måste du lägga till användarna i de inbyggda rollerna "säkerhetsadministratör" eller "global administratör" i Azure Active Directory (AAD).

**Skrivskyddsåtkomst:** Användare med skrivskydd kan logga in och visa alla aviseringar och relaterad information. De kommer inte att kunna spara, ändra eller dela en fråga. Om du vill tilldela skrivskyddad åtkomstbehörighet måste användarna läggs till i den inbyggda rollen "Säkerhetsläsare" i AAD.

## <a name="get-started-with-advanced-hunting"></a>Komma igång med avancerad sökning

Vi rekommenderar att du går igenom flera steg för att snabbt komma igång med avancerad sökning.

| Utbildningsmål | Beskrivning | Resurs |
|--|--|--|
| **Lär dig språket** | Avancerad sökning baseras på [Kusto-frågespråk som](/azure/kusto/query/)har stöd för samma syntax och operatorer. Börja lära dig frågespråket genom att köra den första frågan. | [Översikt över frågespråk](advanced-hunting-query-language.md) |
| **Lär dig hur du använder frågeresultatet** | Läs mer om diagram och olika sätt att visa eller exportera resultaten. Se hur du snabbt kan justera frågorna, öka detaljinformationen och vidta svarsåtgärder. | - [Arbeta med frågeresultat](advanced-hunting-query-results.md)<br>- [Vidta åtgärder för frågeresultat](advanced-hunting-take-action.md) |
| **Förstå schemat** | Få en bra förståelse på hög nivå för tabellerna i schemat och deras kolumner. Lär dig var du letar efter data när du skapar dina frågor. | - [Schemareferens](advanced-hunting-schema-tables.md)<br>- [Övergång från Microsoft Defender för Slutpunkt](advanced-hunting-migrate-from-mde.md) |
| **Få experttips och exempel** | Utbilda dig kostnadsfritt med guider från Microsofts experter. Utforska samlingar av fördefinierade frågor som täcker olika scenarier för hot efter hot. | - [Få expertutbildning](advanced-hunting-expert-training.md)<br>- [Använda delade frågor](advanced-hunting-shared-queries.md)<br>- [Gå och leta](advanced-hunting-go-hunt.md)<br>- [Jaga hot på enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md) |
| **Optimera frågor och hantera fel** | Förstå hur du skapar effektiva och felfria frågor. | - [Metodtips för frågor](advanced-hunting-best-practices.md)<br>- [Hantera fel](advanced-hunting-errors.md) |
| **Skapa anpassade identifieringsregler** | Förstå hur du kan använda avancerade sökfrågor för att utlösa aviseringar och vidta svarsåtgärder automatiskt. | - [Översikt över anpassade identifieringar](custom-detections-overview.md)<br>- [Anpassade identifieringsregler](custom-detection-rules.md) |

## <a name="get-access"></a>Få åtkomst
Om du vill använda avancerad sökning [eller andra Microsoft 365 Defender-funktioner](microsoft-365-defender.md) måste du ha rätt roll i Azure Active Directory. Åtkomsten till slutpunktsdata avgörs också av rollbaserad åtkomstkontroll (RBAC) i Microsoft Defender för Slutpunkt. [Läs om hur du hanterar åtkomst till Microsoft 365 Defender](m365d-permissions.md)

## <a name="data-freshness-and-update-frequency"></a>Datauppdatering och uppdateringsfrekvens
Avancerade sökdata kan kategoriseras i två distinkta typer, som var och en konsolideras på olika sätt.

- **Händelse- eller aktivitetsdata**– fyller i tabeller om aviseringar, säkerhetshändelser, systemhändelser och rutinmässiga utvärderingar. Avancerad sökning tar emot dessa data nästan omedelbart efter att de signaler som samlar in dem överför dem till motsvarande molntjänster. Du kan till exempel fråga händelsedata från hälsosamma sensorer på arbetsstationer eller domänkontrollanter nästan omedelbart efter att de är tillgängliga på Microsoft Defender för Endpoint och Microsoft Defender för identitet.
- **Entitetsdata**– fyller i tabeller med information om användare och enheter. Dessa data kommer från både relativt statiska datakällor och dynamiska källor, till exempel Active Directory-poster och händelseloggar. För att ge nya data uppdateras tabeller med ny information var 15:e minut, vilket innebär att rader som kanske inte är helt ifyllda läggs till. Varje dygn konsolideras data för att infoga en post som innehåller den senaste och mest omfattande datauppsättningen om varje entitet.

## <a name="time-zone"></a>Tidszon
Tidsinformation för avancerad sökning finns i UTC-tidszonen.

## <a name="related-topics"></a>Relaterade ämnen
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Få expertutbildning](advanced-hunting-expert-training.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
- [Översikt över anpassade identifieringar](custom-detections-overview.md)
