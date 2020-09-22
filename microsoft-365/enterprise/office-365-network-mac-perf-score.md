---
title: Microsoft 365 Network Assessment (för hands version)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 Network Assessment (för hands version)
ms.openlocfilehash: 3d80130dbf9ca41342bc1a01fe3ce992303efb48
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200753"
---
# <a name="microsoft-365-network-assessment-preview"></a>Microsoft 365 Network Assessment (för hands version)

I administratörs centret för Microsoft 365 är **nätverks** anslutningar en mängd olika nätverks prestanda mått till en ögonblicks bild av företagets nätverks gräns, representerade av ett Points-värde från 0-100. En nätverks utvärdering visar hur stor del av den fördelade nätverks utformningen som påverkar Office 365-användar upplevelsen. Nätverks utvärderingar bevaras till både hela klient organisationen och för varje geografisk plats där användare ansluter till din klient organisation och ger Microsoft 365-administratörer ett enkelt sätt att omedelbart förstå en gestalt av företagets nätverks tillstånd och snabbt öka detalj nivån till en detaljerad rapport för alla globala Office-platser.

Värdet för nätverks utvärderings punkter är ett medelvärde för TCP-fördröjning, nedladdnings hastighet och UDP-anslutnings kvalitets mått som kompileras en gång om dagen. Prestanda mått för Microsoft-ägda nätverk undantas från dessa mätningar för att säkerställa att bedömnings resultaten är entydiga och specifika för företagets nätverk.

![Nätverkets utvärderings värde](../media/m365-mac-perf/m365-mac-perf-overview-score-top.png)

Ett lågt värde för utvärdering av nätverk ger förslag på att Microsoft 365-klienter har viktiga problem med att ansluta till klient organisationen eller att det finns en fungerande användar upplevelse, medan ett riktigt konfigurerat nätverk med få kontinuerliga prestanda problem uppstår. Ett värde på 80% representerar en felfri original plan där du inte bör förvänta dig regelbundna klagomål om Microsoft 365-anslutning eller svars tid på grund av nätverks prestanda. När du gör en iterativ nätverks förbindelse förbättras det här värdet tillsammans med användar upplevelsen.

| Nätverks utvärdering | Förväntad användar upplevelse |
| :----------------- | :----------------------- |
| 100                | Metod                     |
| 80                 | Möter rekommendationer    |
| 60                 | Tillåtet               |
| 40                 | Användare kan få problem |
| 20.1                 | Användare kan klaga       |
| siffrorna                  | Nätverks problem ett gemensamt ämne i diskussionen |

>[!IMPORTANT]
>Nätverks insikter, prestanda rekommendationer och utvärderingar i administrations centret för Microsoft 365 är för närvarande förhands gransknings status och är bara tillgänglig för Microsoft 365-klient organisationer som har registrerats i funktionen för förhands granskning.

## <a name="network-assessment-panel"></a>Panelen nätverks utvärdering

Varje nätverks utvärdering, oavsett om det gäller innehavaren eller till en viss Office-plats, visar en panel med information om utvärderingen. I den här panelen visas ett stapeldiagram över bedömningen, både som en procents ATS och totalt antal poäng för varje komponent arbets börda, inklusive endast arbets belastningar där mätnings data mottogs. För utvärdering av en Office-plats visar vi också en jämförelse av de procent av Microsoft 365-kunder som har rapporterat data i samma stad som din Office-plats.

![Exempel på nätverkets utvärderings värde](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

**Utvärderings detalj nivån** i panelen visar bedömningen för varje komponent arbets börda.

**Utvärderings historiken** visar de senaste 30 dagarna av utvärderingen och benchmark. Du kan också rapportera till en Office-plats på upp till två år via fliken Historik. På fliken Historik kan du välja vilka attribut du vill rapportera om och genom att välja en rapport tids ram kan du framhäva effekten av ett nätverks uppdaterings projekt och se förbättringen av din nätverks utvärdering.

## <a name="tenant-network-assessments-and-office-location-network-assessments"></a>Bedömningar av klient organisations nätverk och utvärderingar av Office-plats nätverk

En nätverks utvärdering mäter utformningen av nätverks omkretsen för en Office-plats till Microsofts nätverk. Förbättrad nätverks gräns är bäst på varje Office-plats.

Vi visar ett nätverks utvärderings värde för hela Microsoft 365-klienten på sidan för översikt över nätverks prestanda, som är ett vägt medelvärde av nätverks utvärderingarna för alla Office-platser. Det finns också ett specifikt värde för nätverks utvärdering för varje identifierad Office-plats på den platsens sammanfattnings sida.

## <a name="exchange-online"></a>Exchange Online

För Exchange Online mäts TCP-fördröjning från klient datorn till Exchange-tjänstens front dörr. Detta kan påverkas av avståndet mellan nätverket och WAN. Det kan också påverkas av nätverks mellanliggande enheter eller tjänster som fördröjer anslutningen eller orsakar att paket skickas igen. Och det påverkar hur långt bort den närmaste front dörren för Exchange-tjänsten är. Median värdet (kallas även 50 percentil eller P50 mått) tas för alla mätningar under de föregående tre dagarna.

Utvärdering av Exchange Online görs med följande tabell. Alla TCP-latens nummer mellan gränsarna tilldelas punkter linjärt i bandet.

| TCP-fördröjning   | Punkterna |
| :------------ | :----- |
| 10ms eller mindre  | 100    |
| 25ms          | 80     |
| 100ms         | 60     |
| 200ms         | 40     |
| 300ms         | 20.1     |
| 350ms eller mer | siffrorna      |

## <a name="sharepoint-online"></a>SharePoint Online

För SharePoint Online är nedladdnings hastigheten för en användare tillgänglig för åtkomst till ett dokument från SharePoint eller OneDrive. Detta kan påverka bandbredden som är tillgänglig för nätverks kretsar mellan klient datorn och Microsofts nätverk. Det påverkar också ofta nätverks överbelastning som finns i Flask halsar i komplexa nätverks enheter eller i en dåligt räckvidd. Nedladdnings hastigheten mäts i megabyte per sekund som är ungefär en tiondel av ett antal kretsar per sekund. MB per sekund är användbart eftersom du kan se vilken fil storlek som kan laddas ned i 1 sekund. Den 25: e percentilen (kallas även P25-måttet) tas för alla mätningar under de föregående tre dagarna. Denna 25: e percentil minskar effekten av varierande överbelastning över tid.

Utvärdering av SharePoint Online görs med följande tabell. Alla nedladdnings hastighets nummer mellan gräns värdena är tilldelade punkter linjärt inom bandet.

| Nedladdnings hastighet | Punkterna |
| :------------- | :----- |
| 20MBps eller mer | 100    |
| 14MBps         | 80     |
| 8MBps          | 60     |
| 4 Mbit          | 40     |
| 2MBps          | 20.1     |
| 0MBps          | siffrorna      |

## <a name="microsoft-teams"></a>Microsoft Teams

För Microsoft Teams mäts nätverks kvaliteten som UDP-fördröjning, UDP-Darr och förlust av UDP-paket. UDP används för samtal och konferens ljud-och video anslutnings medie anslutningar för Microsoft Teams. Detta kan påverkas av samma faktorer som för fördröjning och nedladdnings hastighet utöver anslutnings luckor i nätverkets UDP-support eftersom UDP är konfigurerat separat för det vanliga TCP-protokollet. Median värdet (kallas även 50 percentil eller P50 mått) tas för alla mätningar under de föregående tre dagarna. 

Vi beräknar ett medelvärde för resultatet från dessa UDP-mått för en skala mellan en och fem. Då kan vi mappa till 0-100-poängen för utvärdering av Microsoft Teams-nätverk.  Det bästa är att det blir över 87,5 Poäng och det totala dåliga är mindre än 50 punkter.

## <a name="related-topics"></a>Relaterade ämnen

[Nätverks anslutning i Microsoft 365 Admin Center (för hands version)](office-365-network-mac-perf-overview.md)

[Microsoft 365 nätverks prestanda (för hands version)](office-365-network-mac-perf-insights.md)

[Microsoft 365-testverktyg (för hands version)](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 nätverks anslutningar (för hands version)](office-365-network-mac-location-services.md)
