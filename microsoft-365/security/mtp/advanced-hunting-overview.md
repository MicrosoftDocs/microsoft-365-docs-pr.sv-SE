---
title: Översikt – avancerad jakt
description: Lär dig mer om de avancerade jakt frågorna i Microsoft 365 och hur du kan använda dem för att proaktivt hitta hot och svaga sidor i ditt nätverk
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, anpassade identifieringar, schema, kusto, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 47035b5c988dba551948334c0c93d08b779c0d38
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950742"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a>Det står proaktivt för problem med avancerad jakt i Microsoft Threat Protection

**Gäller för:**
- Microsoft Hotskydd

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Advanced jakt är ett fråge baserat Threat-verktyg som gör att du kan utforska upp till 30 dagars rå data. Du kan inspektera händelser i ditt nätverk proaktivt för att hitta hot indikatorer och enheter. Den flexibla till gången till data möjliggör obegränsad jakt för både kända och potentiella hot.
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

Du kan använda samma hot-jakt-frågor för att skapa anpassade identifierings regler. Dessa regler körs automatiskt för att söka efter och svara på misstänkt överträdelse aktivitet, felkonfigurerade maskiner och andra undersöknings resultat.

Denna funktion liknar [Avancerad jakt i Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview). Den här funktionen är tillgänglig i Microsoft 365 Security Center och stöder frågor som kontrollerar en bredare data uppsättning från Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security och Azure ATP. [Aktivera skydd mot Microsoft Threat om](mtp-enable.md)du vill använda en avancerad jakt.

## <a name="get-started-with-advanced-hunting"></a>Komma igång med avancerad jakt

Vi rekommenderar att du går igenom flera olika sätt för att snabbt komma igång med avancerad jakt.

| Utbildnings mål | Beskrivning | Resurspool |
|--|--|--|
| **Lär dig språket** | Avancerad jakt är baserat på [Kusto frågespråk](https://docs.microsoft.com/azure/kusto/query/), med stöd för samma syntax och operatorer. Börja lära dig frågespråket genom att köra den första frågan. | [Frågespråk, översikt](advanced-hunting-query-language.md) |
| **Lär dig hur du använder frågeresultat** | Lär dig mer om diagram och olika sätt att visa eller exportera dina resultat. Lär dig hur du snabbt kan justera frågor, öka detalj nivån för att få bättre information och vidta åtgärder. | - [Arbeta med frågeresultat](advanced-hunting-query-results.md)<br>- [Vidta en åtgärd i frågeresultatet](advanced-hunting-take-action.md) |
| **Förstå schemat** | Få en bra, högkvalitativ förståelse av tabellerna i schemat och deras kolumner. Lär dig hur du söker efter data när du skapar dina frågor. | [Schema referens](advanced-hunting-schema-tables.md) |
| **Få expert tips och exempel** | Träna gratis med guider från Microsoft-experter. Lär dig mer om de fördefinierade frågorna | - [Få expert utbildning](advanced-hunting-expert-training.md)<br>- [Använda delade frågor](advanced-hunting-shared-queries.md)<br>- [Gå och leta](advanced-hunting-go-hunt.md)<br>- [Jakt efter hot på enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md) |
| **Optimera frågor och hantera fel** | Förstå hur du skapar effektiva och felfria frågor. | - [Metod tips för frågor](advanced-hunting-best-practices.md)<br>- [Hantera fel](advanced-hunting-errors.md) |
| **Skapa anpassade identifierings regler** | Förstå hur du kan använda avancerade frågor för att utlösa meddelanden och utföra svars åtgärder automatiskt. | - [Anpassade identifierings översikter](custom-detections-overview.md)<br>- [Anpassade identifierings regler](custom-detection-rules.md) |

## <a name="get-access"></a>Få åtkomst
Du behöver en lämplig roll i Azure Active Directory för att kunna använda avancerad jakt eller annan [Microsoft Threat Protection](microsoft-threat-protection.md) -funktion. Din åtkomst till slut punkts data avgörs också av inställningar för en rollbaserad åtkomst kontroll (RBAC) i Microsoft Defender ATP. [Läs om hur du hanterar åtkomst till Microsoft Threat Protection](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a>Data aktualitet och uppdaterings frekvens
Avancerade jakt uppgifter kan kategoriseras i två distinkta typer, som varje konsol IDE rad är annorlunda.

- **Händelse-eller aktivitets data**– fyller i tabeller om aviseringar, säkerhets händelser, system händelser och utvärderings bedömningar. Advanced jakt tar emot dessa data nästan omedelbart efter att de sensorer som samlar in dem lyckades överföra dem till motsvarande moln tjänster. Du kan till exempel läsa händelse data från friska sensorer på arbets stationer eller domänkontrollanter nästan omedelbart efter att de är tillgängliga i Microsoft Defender ATP och Azure ATP.
- **Entitetsinformation**– fyller i tabeller med konsol IDE rad information om användare och enheter. Dessa data kommer från både relativt statiska data källor och dynamiska källor, till exempel Active Directory-poster och händelse loggar. Om du vill lägga till nya data uppdateras tabellerna var 15: e minut och rader som kanske inte är helt ifyllda läggs till. Var 24: e timme konsol IDE ras för att infoga en post som innehåller de senaste, mest omfattande data uppsättningarna för varje enhet.

## <a name="time-zone"></a>Tidszon
Tidsinformation i Advanced jakt är i UTC-zonen.

## <a name="related-topics"></a>Relaterade ämnen
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Få expert utbildning](advanced-hunting-expert-training.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
- [Översikt över anpassade identifieringar](custom-detections-overview.md)

