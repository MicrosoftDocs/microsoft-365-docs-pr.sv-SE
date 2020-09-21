---
title: Microsoft 365 nätverks insikter (för hands version)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/17/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 nätverks insikter (för hands version)
ms.openlocfilehash: e3730704b6672c931b7538659a38f218e769dd0a
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962377"
---
# <a name="microsoft-365-network-insights-preview"></a>Microsoft 365 nätverks insikter (för hands version)

**Nätverks insikter** är prestanda värden som samlas från din Microsoft 365-klient organisation och kan bara visas av administrativa användare i din klient organisation. Insikter visas i administrations centret för Microsoft 365 på <https://portal.microsoft.com/adminportal/home#/networkperformance> .

Insikter är avsedda att hjälpa dig att utforma nätverks gränser för dina Office-platser. Varje Insight ger direkt information om prestanda egenskaper för ett specifikt gemensamt problem för varje geografisk plats där användare kan komma åt din klient organisation.

Det finns sex specifika nätverks insikter som kan visas för varje Office-plats:

- [Utgående nätverks utgångar](#backhauled-network-egress)
- [Bättre prestanda upptäckt för kunder nära dig](#better-performance-detected-for-customers-near-you)
- [Användning av en icke optimal Exchange Online-onlinetjänst](#use-of-a-non-optimal-exchange-online-service-front-door)
- [Användning av en icke-optimal SharePoint Online-onlinetjänst](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [Liten nedladdnings hastighet från SharePoint-startdörren](#low-download-speed-from-sharepoint-front-door)
- [Kina-användarens optimala nätverks utgång](#china-user-optimal-network-egress)

Det finns två nätverks insikter för klient organisations nivå som kan visas för klient organisationen. Dessa visas också på producvitivy resultat sidor:

- [Exchange-sampel som påverkas av anslutnings problem](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [SharePoint-sampel som påverkas av anslutnings problem](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
>Nätverks insikter, prestanda rekommendationer och utvärderingar i administrations centret för Microsoft 365 är för närvarande förhands gransknings status och är bara tillgänglig för Microsoft 365-klient organisationer som har registrerats i funktionen för förhands granskning.

## <a name="backhauled-network-egress"></a>Utgående nätverks utgångar

Denna inblick visas om tjänsten nätverks insikter upptäcker att avståndet från en viss användares plats till nätverket utfaller över 500 mil (800 kilo meter), vilket betyder att Microsoft 365-trafik behålls till en gemensam Internet kant linje eller proxyserver.

Denna inblick är för kortas som "ut" i vissa sammanfattningsvyn.

![Utgående nätverks utgångar](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a>Vad innebär detta?

Detta anger att avståndet mellan arbets platsen och nätverket tar mer än 500 miles (800 kilo meter). Office-platsen identifieras av en Obfuscated och nätverks platsen identifieras med omvänd IP-adress till plats databaser. Office-platsen kanske inte stämmer om Windows Location Services är inaktiverat på datorer. Nätverks utgångs platsen kan vara felaktig om den återförda IP Address-databas informationen är felaktig.

Information om den här inblicken inkluderar arbets platsen, den uppskattade procent andelen av klient organisationen på platsen, den aktuella nätverks utgångs platsen, relevansen för den utgående platsen, avståndet mellan platsen och den aktuella avsluts punkten, det datum då villkoret först identifierades och det datum då villkoret löstes.

### <a name="what-should-i-do"></a>Vad ska jag göra?

För den här inblicken rekommenderar vi att nätverks utfallet närmar sig till Office-platsen så att anslutningen kan leda optimalt till Microsofts globala nätverk och till närmaste Microsoft 365-tjänst. Om du har ett nära nätverks utleverans till användarnas Office-platser kan du också få bättre prestanda i framtiden allteftersom Microsoft expanderar både nätverks punkter och Microsoft 365-tjänstens front dörrar.

Mer information om hur du löser det här problemet finns i [utgående nätverks anslutningar lokalt](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) i [principer för Office 365-nätverks anslutningar](microsoft-365-network-connectivity-principles.md).

## <a name="better-performance-detected-for-customers-near-you"></a>Bättre prestanda upptäckt för kunder nära dig

Denna inblick visas om tjänsten nätverks insikter upptäcker att ett stort antal kunder i din tunnelbane linje har bättre prestanda än användare i organisationen på den här platsen.

Denna inblick är uppkopplad som "peers" i vissa sammanfattningsvyn.

![Relativ nätverks prestanda](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a>Vad innebär detta?

Den här inblicken undersöker den sammanlagda prestandan hos Microsoft 365-kunder i samma stad som den här kontoret. Denna inblick visas om medelvärdet för användarna är 10% högre än genomsnittlig fördröjning för närliggande klient organisationer.

### <a name="what-should-i-do"></a>Vad ska jag göra?

Det kan finnas många orsaker till det här problemet, inklusive svars tid i företagets nätverks-eller Internet leverantör, Flask halsar eller arkitektur design. Undersök fördröjningen mellan varje hopp i vägen mellan ditt kontors nät verk och den aktuella Microsoft 365-dörren. Mer information finns i [principer för Office 365-nätverks anslutningar](microsoft-365-network-connectivity-principles.md).

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a>Användning av en icke optimal Exchange Online-onlinetjänst

Denna inblick visas om tjänsten nätverks insikter upptäcker att användare på en viss plats inte ansluter till en optimal Exchange Online-tjänst.

Denna inblick är för kortas som "routing" i vissa sammanfattningsvyn.

![Icke-optimal EXO främre dörr](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a>Vad innebär detta?

Vi visar Exchange Online Service front dörrar som är lämpliga för användning från Office-platsen med bra prestanda. Om det aktuella testet visar användning av en Exchange Online-onlinetjänst som inte finns med i listan, ringer vi den här rekommendationen.

### <a name="what-should-i-do"></a>Vad ska jag göra?

Användning av en icke optimal Exchange Online-tjänst front dörren kan orsakas av nätverks belastningar innan företags nätverket avsluts, vilket innebär att det lokala och dirigerade nätverks uttaget rekommenderas. Det kan också orsakas av användning av en fjärran sluten DNS-server för rekursiva lösningar, vilket innebär att vi rekommenderar att du justerar den rekursiva servern för DNS-resolver med nätverks utgången.

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a>Användning av en icke-optimal SharePoint Online-onlinetjänst

Denna inblick visas om tjänsten nätverks insikter upptäcker att användare på en viss plats inte ansluter till närmaste SharePoint Online-tjänst.

Denna inblick är för kortas med "AFD" i vissa sammanfattningsvyn.

![Icke-optimal SPO främre dörr](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a>Vad innebär detta?

Vi identifierar SharePoint Online-tjänsten som test klienten ansluter till. För platsen för Office-plats jämför vi nu att du har den förväntade SharePoint Online-tjänstens främre dörr. Om den inte matchar gör vi den här rekommendationen.

### <a name="what-should-i-do"></a>Vad ska jag göra?

Användning av en icke-optimal SharePoint Online-tjänst front dörren kan orsakas av nätverks belastningar innan företags nätverket avslut ATS, vilket innebär att det lokala och direkta nätverks utgången. Det kan också orsakas av användning av en fjärran sluten DNS-server för rekursiva lösningar, vilket innebär att vi rekommenderar att du justerar den rekursiva servern för DNS-resolver med nätverks utgången.

## <a name="low-download-speed-from-sharepoint-front-door"></a>Liten nedladdnings hastighet från SharePoint-startdörren

Denna inblick visas om tjänsten nätverks insikter upptäcker att bandbredden mellan den specifika Office-platsen och SharePoint Online är mindre än 1 MBps.

Denna inblick är för kortas som "genomflöde" i vissa sammanfattningsvyn.

### <a name="what-does-this-mean"></a>Vad innebär detta?

Nedladdnings hastigheten som en användare kan få från SharePoint Online och tjänsten OneDrive för företag-tjänst mäts i megabyte per sekund (MBps). Om det här värdet är mindre än 1 MBps ger vi denna insikt.

### <a name="what-should-i-do"></a>Vad ska jag göra?

För att förbättra nedladdnings hastigheten kan bandbredden behöva ökas. Det kan också hända att nätverks belastningen är överbelastade på Office-platsen och front dörren för SharePoint Online. Det här kallas ibland för congestive förlust och begränsar nedladdnings hastigheten till användarna även om det finns tillräckligt med bandbredd.

## <a name="china-user-optimal-network-egress"></a>Kina-användarens optimala nätverks utgång

Denna inblick visas om din organisation har användare i Kina som ansluter till din Microsoft 365-klient organisation på andra geografiska platser. 

### <a name="what-does-this-mean"></a>Vad innebär detta?

Om din organisation har en privat WAN-anslutning rekommenderar vi att du konfigurerar nätverks WAN-kretsen från din Office-plats i Kina som har nätverks täckning på Internet på någon av följande platser:

- Hongkong
- Japan 
- Taiwan
- Sydkorea
- Singapore
- Malaysia

Internet upphör längre bort från användare än de här platserna minskar prestanda och utgångs i Kina kan orsaka hög latens och anslutnings problem på grund av gränsöverskridande överbelastning.

### <a name="what-should-i-do"></a>Vad ska jag göra?

Mer information om hur du minskar prestanda problem som är relaterade till den här inblicken finns i [Office 365 global Performance Optimization för användare i Kina](microsoft-365-networking-china.md).

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a>Exchange-sampel som påverkas av anslutnings problem

Denna inblick visar när 50% eller fler av de uppkopplings bara förbindelserna påverkas. Effekten definieras av Exchange utvärdering som unders tiger 60% för varje prov.

### <a name="what-does-this-mean"></a>Vad innebär detta?

Det är en indikation på att de flesta av användarna troligt vis drabbas av problem med att Outlook ansluter till Exchange Online. Procent andelen av proverna representerar procent av användare som visar under 60 punkter.  

### <a name="what-should-i-do"></a>Vad ska jag göra?

Aktivera synligheten för nätverks anslutningar för Office om du inte redan har gjort det. Du vill identifiera vilka kontor som är impactred av dåligt ansluten till nätverket som påverkar Exchange och hitta olika sätt att förbättra nätverks behållning hos alla som ansluter användarna till Microsofts nätverk.

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a>SharePoint-sampel som påverkas av anslutnings problem

Denna inblick visar när 50% eller fler av de uppkopplings bara förbindelserna påverkas. Effekten definieras av SharePoint-utvärderingen under 40% för varje prov.

### <a name="what-does-this-mean"></a>Vad innebär detta?

Det är en indikation på att de flesta av användarna sannolikt har problem med användar miljön med SharePoint och OneDrive. Procent andelen av proverna representerar procent av användare som visar under 40 punkter.  

### <a name="what-should-i-do"></a>Vad ska jag göra?

Aktivera synligheten för nätverks anslutningar för Office om du inte redan har gjort det. Du vill identifiera vilka kontor som är impactred av dåligt nätverksanslutna anslutningar som påverkar SharePoint och hittar olika sätt att förbättra nätverks behållning hos alla som ansluter användarna till Microsofts nätverk.

## <a name="related-topics"></a>Relaterade ämnen

[Nätverks anslutning i Microsoft 365 Admin Center (för hands version)](office-365-network-mac-perf-overview.md)

[Microsoft 365 Network Assessment (för hands version)](office-365-network-mac-perf-score.md)

[Microsoft 365 anslutnings test i M365 administrations Center (för hands version)](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 nätverks anslutningar (för hands version)](office-365-network-mac-location-services.md)
