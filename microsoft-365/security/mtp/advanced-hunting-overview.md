---
title: Översikt över avancerad jakt i Microsoft Threat Protection
description: Lär dig mer om avancerade jaktfrågor i Microsoft 365 och hur du använder dem för att proaktivt hitta hot och svagheter i nätverket
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetri, custom detections, schema, kusto, microsoft 365, Microsoft Threat Protection
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
ms.openlocfilehash: 598ef669e95081ef098dfa9cfdb5473b21b28306
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42806063"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a>Proaktivt jaga hot med avancerad jakt i Microsoft Threat Protection

**Gäller:**
- Skydd av Hot mot Microsoft



Avancerad jakt är ett frågebaserat hotjaktsverktyg som låter dig utforska upp till 30 dagars rådata. Du kan proaktivt granska händelser i nätverket för att hitta intressanta indikatorer och entiteter. Den flexibla tillgången till data underlättar obegränsad jakt efter både kända och potentiella hot.

I Microsoft 365 security center stöder avancerad jakt frågor som undersöker data från både Microsoft Defender ATP, som täcker data från inbyggda enheter och Office 365 ATP, som tillhandahåller data från e-postmeddelanden. Om du vill använda avancerad jakt [aktiverar du Microsoft Threat Protection](mtp-enable.md).

## <a name="get-started-with-advanced-hunting"></a>Kom igång med avancerad jakt

Vi rekommenderar att du går igenom flera steg för att snabbt komma igång med avancerad jakt.

| Lärande mål | Beskrivning | Resurs |
|--|--|--|
| **Få en känsla för språket** | Avancerad jakt baseras på [Kusto-frågespråket](https://docs.microsoft.com/azure/kusto/query/), som stöder samma syntax och operatorer. Börja lära dig frågespråket genom att köra den första frågan. | [Översikt över frågespråk](advanced-hunting-query-language.md) |
| **Förstå schemat** | Få en bra förståelse på hög nivå av tabellerna i schemat och deras kolumner. Detta hjälper dig att avgöra var du ska leta efter data och hur du konstruerar dina frågor. | [Schemareferens](advanced-hunting-schema-tables.md) |
| **Använda fördefinierade frågor** | Utforska samlingar av fördefinierade frågor som täcker olika hotjaktsscenarier. | [Använda delade frågor](advanced-hunting-shared-queries.md)
| **Optimera frågor** | Förstå hur du skapar effektiva frågor och frågor som kombinerar data från e-postmeddelanden och enheter. | [Fråga metodtips](advanced-hunting-shared-queries.md), [Jaga över enheter och e-postmeddelanden](advanced-hunting-best-practices.md)

## <a name="get-help-as-you-write-queries"></a>Få hjälp när du skriver frågor
Dra nytta av följande funktioner för att skriva frågor snabbare:
- **Autosuggest** - när du skriver frågor, avancerad jakt ger förslag. 
- **Schemareferens** – en schemareferens som innehåller listan med tabeller och deras kolumner anges bredvid arbetsområdet. Om du vill ha mer information håller du muspekaren över ett objekt. Dubbelklicka på ett objekt för att infoga det i frågeredigeraren.

## <a name="drilldown-from-query-results"></a>Detaljerad granskning från frågeresultat
Om du vill visa mer information om entiteter, till exempel datorer, filer, användare, IP-adresser och webbadresser, klickar du bara på entitetsidentifieraren i frågeresultaten. Då öppnas en detaljerad profilsida för den valda entiteten i Microsoft Defender Security Center.

## <a name="tweak-your-queries-from-the-results"></a>Justera dina frågor från resultaten
Högerklicka på ett värde i resultatuppsättningen för att snabbt förbättra frågan. Du kan använda alternativen för att:

- Leta uttryckligen efter det`==`valda värdet ( )
- Exkludera det markerade`!=`värdet från frågan ( )
- Få fler avancerade operatorer för att lägga `contains`till `starts with` värdet i frågan, till exempel, och`ends with` 

![Bild på Microsoft Defender ATP avancerade jaktresultat set](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a>Filtrera frågeresultaten
Filtren som visas till höger ger en sammanfattning av resultatuppsättningen. Varje kolumn har ett eget avsnitt som visar de distinkta värden som finns för den kolumnen och antalet instanser.

Förfina frågan genom att välja knapparna "+" eller "-" på de värden som du vill inkludera eller utesluta och sedan välja **Kör fråga**.

![Bild av avancerat jaktfilter](../../media/advanced-hunting-filter.png)

När du har tillämpat filtret för att ändra frågan och sedan köra frågan uppdateras resultaten i enlighet med detta.

## <a name="related-topics"></a>Relaterade ämnen
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga hot mellan enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
