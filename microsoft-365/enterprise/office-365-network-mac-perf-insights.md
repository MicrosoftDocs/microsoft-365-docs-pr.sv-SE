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
ms.openlocfilehash: ca665f4e492b071e5a387ffde0efae8336bd96bc
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245786"
---
# <a name="microsoft-365-network-insights-preview"></a>Microsoft 365 Network Insights (förhandsversion)

**Nätverksinsikter** är prestandamätvärden som samlas in från Microsoft 365-klientorganisationen och är tillgängliga för visning endast av administrativa användare i klientorganisationen. Insikter visas i administrationscentret Microsoft 365 i <https://portal.microsoft.com/adminportal/home#/networkperformance> .

Insikter är avsedda att bidra till att utforma nätverks perimeter för dina kontorsplatser. Varje insikt ger detaljerad information om prestandaegenskaper för ett specifikt vanligt problem för varje geografisk plats där användarna har åtkomst till din klientorganisation.

Det finns sex specifika nätverksinsikter som kan visas för varje kontorsplats:

- [Backhauled network egress](#backhauled-network-egress)
- [Nätverkets mellanledde enhet](#network-intermediary-device)
- [Bättre prestanda som upptäckts för kunder nära dig](#better-performance-detected-for-customers-near-you)
- [Användning av en icke-optimal Exchange Online tjänst framifrån](#use-of-a-non-optimal-exchange-online-service-front-door)
- [Användning av en icke-optimal SharePoint för onlinetjänster](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [Låg nedladdningshastighet SharePoint fronten](#low-download-speed-from-sharepoint-front-door)
- [Optimal utgående nätverkstrafik för användare i Kina](#china-user-optimal-network-egress)

Det finns två nätverksinsikter på klientorganisationsnivå som kan visas för klientorganisationen. De visas även på produktivitetsresultatsidorna:

- [Exchange exempel på anslutningar som påverkas av anslutningsproblem](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [SharePoint exempel på anslutningar som påverkas av anslutningsproblem](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
>Nätverksinsikter, prestandarekommendationer och utvärderingar i administrationscentret för Microsoft 365 är för närvarande i förhandsgranskningsstatus och är endast tillgängligt för Microsoft 365-klienter som har registrerats i programmet för förhandsgranskning av funktioner.

## <a name="backhauled-network-egress"></a>Backhauled network egress

Den här insikten visas om tjänsten nätverksinsikter upptäcker att avståndet från en viss användarplats till nätverkets utgående punkt är större än 800 kilometer, vilket indikerar att Microsoft 365-trafik backar till en gemensam Internet edge-enhet eller proxy.

Den här insikten är förkortad som "Egress" i vissa sammanfattningsvyer.

> [!div class="mx-imgBorder"]
> ![Backhauled network egress](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a>Vad betyder det här?

Detta identifierar att avståndet mellan kontorsplatsen och nätverkets utgående punkt är mer än 500 km (800 meter). Kontorsplatsen identifieras med en obfuscerad klientdatorplats och nätverkets utgående plats identifieras med hjälp av omvänd IP-adress till platsdatabaser. Platsen på kontoret kan vara felaktig om Windows platstjänster är inaktiverat på datorer. Nätverkets utgående plats kan vara felaktig om informationen i den omvända IP-adressdatabasen är felaktig.

Information för den här insikten omfattar kontorsplats, uppskattad procentandel av den totala klientorganisationens användare på platsen, den aktuella utgående platsen för nätverket, relevansen för den utgående platsen, avståndet mellan platsen och den aktuella utgående punkten, datumet då villkoret först identifierades och det datum då villkoret löstes.

### <a name="what-should-i-do"></a>Vad ska jag göra?

För den här insikten rekommenderar vi att nätverkets utgående trafik ligger närmare kontorsplatsen så att anslutningen kan dirigeras optimalt till Microsofts globala nätverk och till närmaste Microsoft 365 tjänst front. Att stänga nätverkets utgående trafik till användarnas kontorsplatser gör det också möjligt att förbättra prestanda i framtiden eftersom Microsoft utökar båda nätverkspunkterna av närvaro Microsoft 365 tjänst så att dörrar till fronten i framtiden utökas.

Mer information om hur du löser problemet finns i artikeln [Egress anslutningar lokalt](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) i Office 365 principer för [nätverksanslutning.](microsoft-365-network-connectivity-principles.md)

## <a name="network-intermediary-device"></a>Nätverkets mellanledde enhet

Den här insikten visas om vi har upptäckt enheter mellan dina användare och Microsofts nätverk som kan påverka Office 365 upplevelsen. Vi rekommenderar att dessa kringgås för specifik Microsoft 365 nätverkstrafik som är avsedd för Microsofts datacenter. Denna rekommendation beskrivs Microsoft 365 [principer för nätverksanslutning.](microsoft-365-network-connectivity-principles.md) 

En information som visas för mellanled i nätverket är SSL-avbrott och kontroll när viktiga Office 365-nätverksslutpunkter för Exchange, SharePoint och Teams snappas upp och dekrypteras av nätverkets mellanled.

### <a name="what-does-this-mean"></a>Vad betyder det här?

Nätverkledande enheter som proxyservrar, VPN och enheter för dataförlustskydd kan påverka prestanda och stabilitet Microsoft 365 klienter där trafiken är mellanliggande.

### <a name="what-should-i-do"></a>Vad ska jag göra?

Konfigurera nätverkets mellanledsenhet som har upptäckts att kringgå bearbetning för Microsoft 365 nätverkstrafik.

## <a name="better-performance-detected-for-customers-near-you"></a>Bättre prestanda som upptäckts för kunder nära dig

Den här insikten visas om tjänsten Network Insights upptäcker att ett stort antal kunder i din metroområde har bättre prestanda än användare i organisationen på den här kontorsplatsen.

Den här insikten är förkortad som "Peers" i vissa sammanfattningsvyer.

> [!div class="mx-imgBorder"]
> ![Relativ nätverksprestanda](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a>Vad betyder det här?

Den här insikten undersöker de aggregerade prestanda Microsoft 365 kunder i samma stad som den här kontorsplatsen. Den här insikten visas om den genomsnittliga svarstiden för dina användare är 10 % högre än den genomsnittliga svarstiden för intilliggande klientorganisation.

### <a name="what-should-i-do"></a>Vad ska jag göra?

Det kan finnas många orsaker till det här villkoret, till exempel svarstiden i företagsnätverket eller Internetleverantören, flaskhalsar och designproblem i arkitekturen. Undersök svarstiden mellan varje hopp i vägen mellan ditt kontorsnätverk och den Microsoft 365 fronten. Mer information finns i Microsoft 365 [principer för nätverksanslutning.](microsoft-365-network-connectivity-principles.md)

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a>Användning av en icke-optimal Exchange Online tjänst framifrån

Den här insikten visas om tjänsten nätverksinsikter upptäcker att användare på en viss plats inte ansluter till en optimal Exchange Online tjänst hos alla.

Den här insikten är förkortad som "Dirigering" i vissa sammanfattningsvyer.

> [!div class="mx-imgBorder"]
> ![Icke-optimal EXO-framport](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a>Vad betyder det här?

Vi listar Exchange Online service så att dörrar fram som är lämpliga för användning från kontorsplatsens ort med bra prestanda. Om det aktuella testet visar att en tjänst Exchange Online frontend inte finns med på den här listan kallar vi den här rekommendationen.

### <a name="what-should-i-do"></a>Vad ska jag göra?

Användningen av en icke-optimal Exchange Online tjänst hos fronten kan orsakas av nätverkets backhaul innan företagsnätverkets utgående trafik. I sådana fall rekommenderar vi lokal och direkt utgående nätverkstrafik. Det kan också orsakas av att en fjärr-DNS-rekursiv resolverserver används. I sådana fall rekommenderar vi att du justerar DNS-rekursiv resolverserver med nätverkets utgående linje.

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a>Användning av en icke-optimal SharePoint för onlinetjänster

Den här insikten visas om tjänsten nätverksinsikter upptäcker att användare på en viss plats inte ansluter till den SharePoint onlinetjänsten fronten.

Den här insikten är förkortad som "Afd" i vissa sammanfattningsvyer.

> [!div class="mx-imgBorder"]
> ![Ej optimal SPO-framport](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a>Vad betyder det här?

Vi identifierar SharePoint onlinetjänstens klient som testklienten ansluter till. För kontorsplatsen jämförs det med den förväntade SharePoint för den staden. Om den inte stämmer överens med den här rekommendationen gör vi den här rekommendationen.

### <a name="what-should-i-do"></a>Vad ska jag göra?

Användningen av en icke-optimal SharePoint onlinetjänst front front skulle kunna orsakas av nätverkets backhaul innan företagsnätverkets utgående trafik. I sådana fall rekommenderar vi lokal och direkt utgående nätverkstrafik. Det kan också orsakas av att en fjärr-DNS-rekursiv resolverserver används. I sådana fall rekommenderar vi att du justerar DNS-rekursiv resolverserver med nätverkets utgående linje.

## <a name="low-download-speed-from-sharepoint-front-door"></a>Låg nedladdningshastighet SharePoint fronten

Den här insikten visas om tjänsten för nätverksinsikter upptäcker att bandbredden mellan den specifika kontorsplatsen och den SharePoint Online är mindre än 1 MBP.

Den här insikten är förkortad som "Dataflöde" i vissa sammanfattningsvyer.

### <a name="what-does-this-mean"></a>Vad betyder det här?

Den nedladdningshastighet som en användare kan få från SharePoint Online och OneDrive för företag av dörrar till tjänstens framsida mäts i megabyte per sekund (MBps). Om det här värdet är mindre än 1 MBP ger vi den här insikten.

### <a name="what-should-i-do"></a>Vad ska jag göra?

Bandbredden kan behöva ökas för att förbättra nedladdningshastigheten. Alternativt kan nätverksstockningar vara överbelastade mellan användares datorer på kontoret och SharePoint Online-tjänstens dörr. Det här kallas ibland för grattis till förlust och det begränsar nedladdningshastigheten som är tillgänglig för användarna även om det finns tillräcklig bandbredd.

## <a name="china-user-optimal-network-egress"></a>Optimal utgående nätverkstrafik för användare i Kina

Den här insikten visas om din organisation har användare i Kina som ansluter till Microsoft 365-klientorganisation i andra geografiska platser. 

### <a name="what-does-this-mean"></a>Vad betyder det här?

Om din organisation har privat WAN-anslutning rekommenderar vi att du konfigurerar en WAN-nätverkskrets från dina kontorsplatser i Kina som har utgående nätverk till Internet på någon av följande platser:

- Hongkong
- Japan 
- Taiwan
- Sydkorea
- Singapore
- Malaysia

Internet som går längre bort från användarna än de här platserna kommer att minska prestandan, och utgående trafik i Kina kan orsaka problem med lång fördröjning och anslutning på grund av överbelastning i andra gränser.

### <a name="what-should-i-do"></a>Vad ska jag göra?

Mer information om hur du åtgärdar prestandaproblem relaterade till den här insikten finns i Microsoft 365 den globala [klientorganisationens prestandaoptimering för kinaanvändare.](microsoft-365-networking-china.md)

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a>Exchange exempel på anslutningar som påverkas av anslutningsproblem

Den här insikten visas när 50 % eller fler av de exempelkopplingar som används påverkas. Effekterna definieras av den Exchange under 60 % för varje sampel.

### <a name="what-does-this-mean"></a>Vad betyder det här?

Det är en indikation på att majoriteten av dina användare troligtvis har problem med att använda Outlook ansluter till Exchange Online. Procentandelen exempel motsvarar sannolikt procentandelen användare som visar under 60 punkter.  

### <a name="what-should-i-do"></a>Vad ska jag göra?

Aktivera nätverksanslutning för office-plats om du inte redan har gjort det. Du vill identifiera vilka kontor som påverkas av dålig nätverksanslutning som påverkar Exchange och hitta sätt att förbättra nätverks perimeter på varje som ansluter användarna till Microsofts nätverk.

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a>SharePoint exempel på anslutningar som påverkas av anslutningsproblem

Den här insikten visas när 50 % eller fler av de exempelkopplingar som används påverkas. Effekterna definieras av den SharePoint under 40 % för varje sampel.

### <a name="what-does-this-mean"></a>Vad betyder det här?

Det är en indikation på att majoriteten av dina användare sannolikt har problem med användarupplevelse med SharePoint och OneDrive. Procentandelen exempel motsvarar sannolikt procentandelen användare som visar under 40 punkter.  

### <a name="what-should-i-do"></a>Vad ska jag göra?

Aktivera nätverksanslutning för office-plats om du inte redan har gjort det. Du vill identifiera vilka kontor som påverkas av dålig nätverksanslutning som påverkar SharePoint och hitta sätt att förbättra nätverks perimeter på varje som ansluter användarna till Microsofts nätverk.

## <a name="related-topics"></a>Relaterade ämnen

[Nätverksanslutningen i Microsoft 365 (förhandsversion)](office-365-network-mac-perf-overview.md)

[Microsoft 365 nätverksutvärdering (förhandsversion)](office-365-network-mac-perf-score.md)

[Microsoft 365 testverktyget för nätverksanslutning (förhandsversion)](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 Nätverksplatstjänster (förhandsversion)](office-365-network-mac-location-services.md)
