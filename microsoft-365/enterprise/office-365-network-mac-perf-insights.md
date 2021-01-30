---
title: Microsoft 365 Network Insights (förhandsversion)
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
description: Microsoft 365 Network Insights (förhandsversion)
ms.openlocfilehash: d6786ce6cd58ce6f350804fbbacd272b8c077dc0
ms.sourcegitcommit: 1ac884d8470b2f2a58b6f79e324fd91e4d11dceb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055479"
---
# <a name="microsoft-365-network-insights-preview"></a>Microsoft 365 Network Insights (förhandsversion)

**Nätverksinsikter** är prestandamätvärden som samlas in från Microsoft 365-klienten och är tillgängliga för visning endast av administrativa användare i klientorganisationen. Insikter visas i administrationscentret för Microsoft 365 i <https://portal.microsoft.com/adminportal/home#/networkperformance> .

Insikter är avsedda att hjälpa dig att utforma nätverks perimeter för dina kontorsplatser. Varje insikt ger direktinformation om prestandaegenskaper för ett specifikt gemensamt problem för varje geografisk plats där användarna har åtkomst till din klientorganisation.

Det finns sex specifika nätverksinsikter som kan visas för varje kontorsplats:

- [Utgående nätverksback](#backhauled-network-egress)
- [Nätverkets mellanliggande enhet](#network-intermediary-device)
- [Bättre prestanda upptäckt för kunder nära dig](#better-performance-detected-for-customers-near-you)
- [Användning av en icke-optimal Exchange Online-tjänsts framsida](#use-of-a-non-optimal-exchange-online-service-front-door)
- [Användning av en icke-optimal SharePoint Online-tjänsts framsida](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [Låg nedladdningshastighet från SharePoints dörr](#low-download-speed-from-sharepoint-front-door)
- [Optimal utgående nätverkstrafik för användare i Kina](#china-user-optimal-network-egress)

Det finns två nätverksinsikter på klientorganisationsnivå som kan visas för klientorganisationen. De visas även på resultatsidorna:

- [Exempel på Exchange-anslutningar som påverkas av anslutningsproblem](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [SharePoint-exempelanslutningar som påverkas av anslutningsproblem](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
>Nätverksinsikter, prestandarekommendationer och utvärderingar i Administrationscenter för Microsoft 365 är för närvarande i förhandsgranskningsstatus och är endast tillgängligt för Microsoft 365-innehavare som har registrerats i programmet för funktionsförhandsgranskning.

## <a name="backhauled-network-egress"></a>Utgående nätverksback

Den här insikten visas om tjänsten nätverksinsikter identifierar att avståndet från en viss användarplats till nätverkets utgång är större än 800 km (800 km), vilket anger att Microsoft 365-trafik backar till en vanlig Internet-edge-enhet eller -proxy.

Den här insikten är förkortad som "Egress" i vissa sammanfattningsvyer.

![Utgående nätverksback](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a>Vad betyder det här?

Detta identifierar att avståndet mellan kontorsplatsen och nätverkets utgående punkt är mer än 500 miles (800 miles). Kontorsplatsen identifieras av en obfyllande klientdatorplats och den utgående platsen för nätverket identifieras genom att använda omvänd IP-adress till platsdatabaser. Platsen på kontoret kan vara felaktig om Windows Platstjänster är inaktiverat på datorer. Nätverkets utgående plats kan vara felaktig om den omvända IP-adressdatabasinformationen är felaktig.

Information för den här insikten omfattar kontorsplatsen, uppskattad procentandel av den totala användaren för klientorganisationen på platsen, den aktuella utgående platsen för nätverket, relevans för den utgående platsen, avståndet mellan platsen och den aktuella utgående punkten, datumet då villkoret först identifierades och det datum då villkoret löstes.

### <a name="what-should-i-do"></a>Vad ska jag göra?

För den här insikten rekommenderar vi att nätverket går närmare kontorsplatsen så att anslutningen kan dirigeras optimalt till Microsofts globala nätverk och till närmaste Microsoft 365-tjänstport. Att stänga nätverkets utgång till användarnas kontorsplatser gör det också möjligt att förbättra prestanda i framtiden eftersom Microsoft utökar båda nätverkspunkternas närvaro och Microsoft 365-tjänstens fram dörrar i framtiden.

Mer information om hur du löser problemet finns i utgående [nätverksanslutningar lokalt i](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) principer för [Office 365-nätverksanslutning.](microsoft-365-network-connectivity-principles.md)

## <a name="network-intermediary-device"></a>Nätverkets mellanliggande enhet

Den här insikten visas om vi har upptäckt enheter mellan dina användare och Microsofts nätverk som kan påverka användarupplevelsen för Office 365. Vi rekommenderar att dessa kringgås för specifik Microsoft 365-nätverkstrafik som är avsedd för Microsoft-datacenter. Den här rekommendationen beskrivs dessutom i [Microsoft 365-principer för nätverksanslutning](microsoft-365-network-connectivity-principles.md)

### <a name="what-does-this-mean"></a>Vad betyder det här?

Nätverkets mellanledande enheter som proxyservrar, VPN och enheter för dataförlustskydd kan påverka prestanda och stabilitet för Microsoft 365-klienter där trafiken mellanliggandes.

### <a name="what-should-i-do"></a>Vad ska jag göra?

Konfigurera den nätverksledande enhet som upptäckts att kringgå bearbetning för Microsoft 365-nätverkstrafik.

## <a name="better-performance-detected-for-customers-near-you"></a>Bättre prestanda upptäckt för kunder nära dig

Den här insikten visas om tjänsten Network Insights identifierar att ett stort antal kunder i metroområdet har bättre prestanda än användare i organisationen på den här kontorsplatsen.

Den här insikten är förkortad som "Peers" i vissa sammanfattningsvyer.

![Relativ nätverksprestanda](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a>Vad betyder det här?

Den här insikten undersöker de aggregerade prestandan för Microsoft 365-kunder i samma stad som den här kontorsplatsen. Den här insikten visas om den genomsnittliga svarstiden för dina användare är 10 % större än den genomsnittliga svarstiden för intilliggande klientorganisation.

### <a name="what-should-i-do"></a>Vad ska jag göra?

Det kan finnas många orsaker till det här villkoret, till exempel svarstiden i företagsnätverket eller Internetleverantör, problem med flaskhalsar eller arkitekturdesign. Undersök svarstiden mellan varje hopp i vägen mellan ditt office-nätverk och den aktuella Front Door i Microsoft 365. Mer information finns i [Microsoft 365-principer för nätverksanslutning.](microsoft-365-network-connectivity-principles.md)

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a>Användning av en icke-optimal Exchange Online-tjänsts framsida

Den här insikten visas om tjänsten nätverksinsikter identifierar att användare på en viss plats inte ansluter till en optimal Exchange Online-tjänst så att säga.

Den här insikten är förkortad som "Routing" i vissa sammanfattningsvyer.

![Ej optimal EXO-dörr](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a>Vad betyder det här?

Vi listar Exchange Online-tjänstens fram dörrar som är lämpliga för användning från kontorsplatsens ort med bra prestanda. Om det i det aktuella testet visas att en Exchange Online-tjänst används utanför den här listan rekommenderar vi den här rekommendationen.

### <a name="what-should-i-do"></a>Vad ska jag göra?

Användningen av en icke-optimal Exchange Online-tjänsts framsida kan orsakas av nätverkets backhaul innan företagsnätverket går ut. I sådana fall rekommenderar vi lokal och direkt utgående nätverkstrafik. Det kan också bero på att en DNS-rekursiv rekursiv resolverserver används, och då rekommenderar vi att du justerar DNS Rekursiv resolver-servern med nätverkets utgående post.

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a>Användning av en icke-optimal SharePoint Online-tjänsts framsida

Den här insikten visas om tjänsten nätverksinsikter identifierar att användare på en viss plats inte ansluter till den närmaste SharePoint Online-tjänstens yttersida.

Den här insikten är förkortad som "Afd" i vissa sammanfattningsvyer.

![Ej optimal SPO-dörr](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a>Vad betyder det här?

Vi identifierar SharePoint Online-tjänstens yttersida som testklienten ansluter till. För kontorsplatsen jämför vi den med den förväntade SharePoint Online-tjänstens framsida för den staden. Om den inte stämmer överens med den här rekommendationen.

### <a name="what-should-i-do"></a>Vad ska jag göra?

Användningen av en icke-optimal SharePoint Online-tjänsts framsida skulle kunna orsakas av ett nätverksnätverk före företagsnätverkets utgång. I sådana fall rekommenderar vi lokal och direkt utgående nätverkstrafik. Det kan också bero på att en DNS-rekursiv rekursiv resolverserver används, och då rekommenderar vi att du justerar DNS Rekursiv resolver-servern med nätverkets utgående post.

## <a name="low-download-speed-from-sharepoint-front-door"></a>Låg nedladdningshastighet från SharePoints dörr

Den här insikten visas om tjänsten nätverksinsikter identifierar den bandbredden mellan den specifika kontorsplatsen och SharePoint Online är mindre än 1 MBp.

Den här insikten är förkortad som "Dataflöde" i vissa sammanfattningsvyer.

### <a name="what-does-this-mean"></a>Vad betyder det här?

Den nedladdningshastighet som en användare kan få från SharePoint Online och OneDrive för företag-tjänstens dörrar fram mäts i megabyte per sekund (MBps). Om det här värdet är mindre än 1 MBp ger vi den här insikten.

### <a name="what-should-i-do"></a>Vad ska jag göra?

För att förbättra nedladdningshastigheter kan bandbredden behöva ökas. Alternativt kan nätverksstockningar vara överbelastade mellan användares datorer på kontoret och SharePoint Online-tjänstens framsida. Det här kallas ibland för en överbelastande förlust och det begränsar nedladdningshastigheten som är tillgänglig för användarna även om tillräcklig bandbredd finns tillgänglig.

## <a name="china-user-optimal-network-egress"></a>Optimal utgående nätverkstrafik för användare i Kina

Den här insikten visas om din organisation har användare i Kina som ansluter till din Microsoft 365-klientorganisation på andra geografiska platser. 

### <a name="what-does-this-mean"></a>Vad betyder det här?

Om din organisation har privat WAN-anslutning rekommenderar vi att du konfigurerar en WAN-krets för nätverket från dina kontorsplatser i Kina som har utgående nätverk till Internet på någon av följande platser:

- Hongkong
- Japan 
- Taiwan
- Sydkorea
- Singapore
- Malaysia

Internet som går ut längre bort från användarna än dessa platser kommer att minska prestandan, och utgående trafik i Kina kan orsaka problem med lång fördröjning och anslutning på grund av överbelastning över gränsen.

### <a name="what-should-i-do"></a>Vad ska jag göra?

Mer information om hur du åtgärdar prestandaproblem relaterade till den här insikten finns i den globala klientorganisationens prestandaoptimering [för Microsoft 365 för kinaanvändare.](microsoft-365-networking-china.md)

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a>Exempel på Exchange-anslutningar som påverkas av anslutningsproblem

Den här insikten visas när 50 % eller fler av de exempelade anslutningarna påverkas. Effekterna definieras av Exchange-utvärderingen som understiger 60 % för varje stickprov.

### <a name="what-does-this-mean"></a>Vad betyder det här?

Det är en indikation på att majoriteten av användarna troligtvis har problem med användarupplevelse med Outlook som ansluter till Exchange Online. Procentandelen exempel motsvarar sannolikt procentandelen användare som visar under 60 punkter.  

### <a name="what-should-i-do"></a>Vad ska jag göra?

Aktivera synligheten för nätverksanslutningen för kontorsplatser om du inte redan har gjort det. Du vill identifiera vilka kontor som påverkas av dålig nätverksanslutning som påverkar Exchange och hitta sätt att förbättra nätverks perimeter vid varje kontor som ansluter användarna till Microsofts nätverk.

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a>SharePoint-exempelanslutningar som påverkas av anslutningsproblem

Den här insikten visas när 50 % eller fler av de exempelade anslutningarna påverkas. Effekterna definieras av SharePoint-utvärderingen som understiger 40 % för varje stickprov.

### <a name="what-does-this-mean"></a>Vad betyder det här?

Det är en indikation på att majoriteten av användarna troligtvis har problem med användarupplevelse med SharePoint och OneDrive. Procentandelen exempel motsvarar sannolikt procentandelen användare som visar under 40 punkter.  

### <a name="what-should-i-do"></a>Vad ska jag göra?

Aktivera synligheten för nätverksanslutningen för kontorsplatser om du inte redan har gjort det. Du vill identifiera vilka kontor som påverkas av dåliga nätverksanslutningar som påverkar SharePoint och hitta sätt att förbättra nätverks perimeter vid varje kontor som ansluter användarna till Microsofts nätverk.

## <a name="related-topics"></a>Relaterade ämnen

[Nätverksanslutning i administrationscentret för Microsoft 365 (förhandsversion)](office-365-network-mac-perf-overview.md)

[Microsoft 365-nätverksutvärdering (förhandsversion)](office-365-network-mac-perf-score.md)

[Testverktyg för Microsoft 365-nätverksanslutning (förhandsversion)](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 Network Connectivity Location Services (förhandsversion)](office-365-network-mac-location-services.md)
