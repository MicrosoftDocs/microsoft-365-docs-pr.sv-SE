---
title: Översikt – Avancerad sökning
description: Läs mer om avancerade sökfrågor i Microsoft 365 och hur du använder dem för att proaktivt hitta hot och svagheter i nätverket
keywords: avancerad sökning, hotsökning, cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, anpassade identifieringar, schema, kusto, microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 8fbf9c3d93434ec2dbc3f069bc0fbd3fe03fc260
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932280"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a>Proaktiv sökning efter hot med avancerad sökning i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

> Vill du uppleva Microsoft 365 Defender? Du kan [utvärdera det i en labbmiljö](https://aka.ms/mtp-trial-lab) eller köra [pilotprojektet i produktion.](https://aka.ms/m365d-pilotplaybook)
>

Avancerad sökning är ett frågebaserat verktyg för hothot där du kan utforska upp till 30 dagars rådata. Du kan proaktivt kontrollera händelser i nätverket för att hitta hotindikatorer och -enheter. Den flexibla åtkomsten till data gör att du inte behöver hitta kända och potentiella hot.
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

Du kan använda samma hotsökningsfrågor för att skapa anpassade identifieringsregler. Dessa regler körs automatiskt för att söka efter och sedan svara på misstänkt intrång, felkonfigurerade datorer och andra resultat.

Den här funktionen liknar avancerad sökning [i Microsoft Defender för Slutpunkt.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) Den här funktionen finns tillgänglig i Microsoft 365 Säkerhetscenter och stöder frågor som kontrollerar en bredare datauppsättning från:

- Microsoft Defender för Endpoint
- Microsoft Defender för Office 365
- Microsoft Cloud App Security
- Microsoft Defender for Identity

Om du vill använda avancerad sökning [aktiverar du Microsoft 365 Defender.](mtp-enable.md)

## <a name="get-started-with-advanced-hunting"></a>Komma igång med avancerad sökning

Vi rekommenderar att du går igenom flera steg för att snabbt komma igång med avancerad sökning.

| Utbildningsmål | Beskrivning | Resurs |
|--|--|--|
| **Lär dig språket** | Avancerad sökning baseras på [Kusto-frågespråk](https://docs.microsoft.com/azure/kusto/query/)som har stöd för samma syntax och operatorer. Börja lära dig frågespråket genom att köra din första fråga. | [Översikt över frågespråk](advanced-hunting-query-language.md) |
| **Lär dig hur du använder frågeresultatet** | Läs mer om diagram och olika sätt att visa eller exportera resultaten. Utforska hur du snabbt kan modifiera frågorna, öka detaljinformationen och vidta svarsåtgärder. | - [Arbeta med frågeresultat](advanced-hunting-query-results.md)<br>- [Vidta åtgärder på frågeresultat](advanced-hunting-take-action.md) |
| **Förstå schemat** | Få en bra, bra förståelse av tabellerna i schemat och deras kolumner. Lär dig var du kan leta efter data när du skapar dina frågor. | - [Schemareferens](advanced-hunting-schema-tables.md)<br>- [Övergång från Microsoft Defender för Slutpunkt](advanced-hunting-migrate-from-mdatp.md) |
| **Få experttips och exempel** | Utbilda dig kostnadsfritt med guider från Microsoft-experter. Utforska samlingar av fördefinierade frågor som täcker olika hotens sökscenarier. | - [Få expertutbildning](advanced-hunting-expert-training.md)<br>- [Använda delade frågor](advanced-hunting-shared-queries.md)<br>- [Gå och leta](advanced-hunting-go-hunt.md)<br>- [Leta efter hot på olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md) |
| **Optimera frågor och hantera fel** | Förstå hur du skapar effektiva och felfria frågor. | - [Metodtips för frågor](advanced-hunting-best-practices.md)<br>- [Hantera fel](advanced-hunting-errors.md) |
| **Skapa anpassade identifieringsregler** | Förstå hur du kan använda avancerade sökfrågor för att utlösa aviseringar och vidta svarsåtgärder automatiskt. | - [Översikt över anpassade identifieringar](custom-detections-overview.md)<br>- [Anpassade identifieringsregler](custom-detection-rules.md) |

## <a name="get-access"></a>Få åtkomst
Om du vill använda avancerad sökning [eller andra Microsoft 365 Defender-funktioner](microsoft-threat-protection.md) behöver du en lämplig roll i Azure Active Directory. Åtkomsten till slutpunktsdata bestäms också av rollbaserad åtkomstkontroll (RBAC) i Microsoft Defender för Slutpunkt. [Läs om hur du hanterar åtkomst till Microsoft 365 Defender](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a>Datauppdatering och uppdateringsfrekvens
Avancerade sökdata kan kategoriseras i två distinkta typer, som var och en konsolideras olika.

- **Händelse- eller aktivitetsdata**– fyller i tabeller om aviseringar, säkerhetshändelser, systemhändelser och rutinutvärderingar. Avancerad sökning tar emot dessa data nästan omedelbart efter att sensorn som samlar in dem har överfört dem till motsvarande molntjänster. Du kan till exempel fråga händelsedata från hälsosamma sensorer på arbetsstationer eller domänkontrollanter nästan omedelbart efter att de är tillgängliga på Microsoft Defender för Slutpunkt och Microsoft Defender för identitet.
- **Entitetsdata**– fyller i tabeller med information om användare och enheter. Dessa data kommer från både relativt statiska datakällor och dynamiska källor, till exempel Active Directory-poster och händelseloggar. För att ge nya data uppdateras tabellerna med ny information var 15:e minut och rader som eventuellt inte är helt ifyllda läggs till. Varje dygn konsolideras data för att infoga en post som innehåller den senaste och mest omfattande datauppsättningen för varje entitet.

## <a name="time-zone"></a>Tidszon
Tidsinformation för avancerad sökning finns i UTC-tidszonen.

## <a name="related-topics"></a>Relaterade ämnen
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Få expertutbildning](advanced-hunting-expert-training.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
- [Översikt över anpassade identifieringar](custom-detections-overview.md)

