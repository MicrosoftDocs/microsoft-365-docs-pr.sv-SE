---
title: 'Översikt: VPN-delade tunnlar med Office 365'
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 9/22/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
- m365initiative-coredeploy
f1.keywords:
- NOCSH
description: Vägledning för att använda VPN-delade tunnlar med Office 365 för att optimera Office 365-anslutningar för fjärranvändare.
ms.openlocfilehash: 9f54d8836105896d8d00afc4a622975c007bda85
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924194"
---
# <a name="optimize-office-365-connectivity-for-remote-users-using-vpn-split-tunneling"></a>Optimera Office 365-anslutningen för fjärranvändare med uppdelad VPN-tunnel
<!---
>[!NOTE]
>This topic is part of a set of topics that address Office 365 optimization for remote users.
>- For VPN split tunnel implementation guidance, see [Implementing VPN split tunneling for Office 365](microsoft-365-vpn-implement-split-tunnel.md).
>- For information about optimizing Office 365 worldwide tenant performance for users in China, see [Office 365 performance optimization for China users](microsoft-365-networking-china.md).
-->

För kunder som ansluter sina fjärranslutna arbetsenheter till företagsnätverket eller molninfrastrukturen via VPN rekommenderar Microsoft att viktiga Office 365-scenarier **Microsoft Teams**, **SharePoint Online** och Exchange **Online** dirigeras via _en VPN-delad tunnelkonfiguration._ Det här blir särskilt viktigt som den första linjestrategin för att underlätta fortsatt produktivitet bland anställda vid storskaliga händelser hemma, till exempel coVID-19-kris.

![VPN-konfiguration för delade tunnlar](../media/vpn-split-tunneling/vpn-model-2.png)

_Bild 1: En VPN-delad tunnellösning med definierade Office 365-undantag som skickas direkt till tjänsten. All annan trafik passerar VPN-tunneln oavsett destination._

Det viktigaste i den här metoden är att tillhandahålla en enkel metod för företag för att minimera risken för VPN-infrastrukturmättnad och avsevärt förbättra Office 365-prestandan inom den kortaste möjliga tidsperioden. Genom att konfigurera VPN-klienter för att tillåta den mest kritiska Office 365-trafiken med hög volym kringgår VPN-tunneln följande fördelar:

- Minimerar omedelbart orsaken till majoriteten av de kundrapporterade prestanda- och nätverkskapacitetsproblemen i VPN-arkitekturer för företag som påverkar användarupplevelsen för Office 365
  
  Den rekommenderade lösningen riktar specifikt in Office 365-tjänstslutpunkter som kategoriserats som Optimera i ämnet [Office 365-URL:er och IP-adressintervall.](./urls-and-ip-address-ranges.md)  Trafik till dessa slutpunkter är mycket känslig för latens och bandbreddsbegränsning, och att göra det möjligt att kringgå VPN-tunneln kan avsevärt förbättra slutanvändarupplevelsen och minska företagets nätverksbelastning. Office 365-anslutningar som inte utgör majoriteten av bandbredden eller användarnas upplevelseavtryck kan fortsätta att dirigeras genom VPN-tunneln tillsammans med resten av Internetbunden trafik. Mer information finns i [VPN-strategi för delade tunnlar.](#the-vpn-split-tunnel-strategy)

- Kan konfigureras, testas och implementeras snabbt av kunder och utan ytterligare krav på infrastruktur eller program

  Implementeringen kan ta så lite som några timmar beroende på VPN-plattformen och nätverksarkitekturen. Mer information finns i Implementera [VPN-delade tunnlar](microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling).

- Bevarar säkerheten hos vpn-implementeringar av kunder genom att inte ändra hur andra anslutningar dirigeras, inklusive trafik till Internet

  Den rekommenderade konfigurationen följer **principen** om minsta behörighet för VPN-trafikundantag och gör det möjligt för kunder att implementera VPN för delade tunnlar utan att utsätta användare eller infrastruktur för ytterligare säkerhetsrisker. Nätverkstrafiken som dirigeras direkt till Office 365-slutpunkter krypteras, valideras för integritet av Office-klientprogramsstackar och är begränsad till IP-adresser som är dedikerade till Office 365-tjänster som är hårdna på både program- och nätverksnivå. Mer information finns i Alternativa sätt för säkerhetsexperter och IT-personal för att uppnå moderna säkerhetskontroller i dagens unika fjärrarbete [(Microsoft Security Team-blogg)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/).

- Stöds inbyggt av de flesta VPN-plattformarna för företag

  Microsoft fortsätter att samarbeta med branschpartners som utvecklar kommersiella VPN-lösningar som hjälper partner att utveckla riktade väglednings- och konfigurationsmallar för sina lösningar i enlighet med rekommendationerna ovan. Mer information finns i [HOWTO-guider för vanliga VPN-plattformar.](microsoft-365-vpn-implement-split-tunnel.md#howto-guides-for-common-vpn-platforms)

>[!TIP]
>Microsoft rekommenderar att man fokuserar på VPN-konfiguration för delade tunnlar på dokumenterade dedikerade IP-intervall för Office 365-tjänster. FQDN- eller AppID-baserade delade tunnelkonfigurationer, även om möjligt på vissa VPN-klientplattformar, kanske inte helt täcker nyckelscenarier i Office 365 och kan vara i konflikt med IP-baserade VPN-routningsregler. Microsoft rekommenderar därför inte att du använder Office 365 FQDN för att konfigurera VPN för delade tunnlar. Användningen av FQDN-konfigurationen kan vara användbar i andra relaterade scenarier, till exempel pac-filanpassningar eller för att implementera förbikoppling av proxy.

Fullständig implementeringsvägledning finns i [Implementera VPN-delade tunnlar för Office 365.](microsoft-365-vpn-implement-split-tunnel.md)

## <a name="the-vpn-split-tunnel-strategy"></a>VPN-strategi för delade tunnlar

Traditionella företagsnätverk är ofta utformade för att fungera säkert för en före molnmoln värld där de viktigaste data, tjänster, program finns lokalt och är direkt anslutna till det interna företagsnätverket, som är majoriteten av användarna. Nätverksinfrastrukturen byggs alltså runt dessa element i att filialkontor är anslutna till huvudkontoren via _MPLS-nätverk (Multiprotocol Label Switching),_ och fjärranslutna användare måste ansluta till företagsnätverket via ett VPN för åtkomst till både lokala slutpunkter och Internet. I den här modellen passerar all trafik från fjärranslutna användare företagsnätverket och dirigeras till molntjänsten via en gemensam utgående punkt.

![Tvingad VPN-konfiguration](../media/vpn-split-tunneling/vpn-model-1.png)

_Bild 2: En vanlig VPN-lösning för fjärranvändare där all trafik tvingas tillbaka till företagsnätverket oavsett destination_

I och med att organisationer flyttar data och program till molnet har den här modellen börjat bli mindre effektiv eftersom den snabbt blir krånglig, dyr och oskadlig, vilket avsevärt påverkar nätverksprestandan och effektiviteten för användarna och begränsar organisationens möjlighet att anpassa sig efter föränderliga behov. Många Microsoft-kunder har rapporterat att för några år sedan gick 80 % av nätverkstrafiken till en intern destination, men 2020 ansluter 80 % plus trafik till en extern molnbaserad resurs.

CoVID-19-krislösningen har löst problemet så att det finns direkta lösningar för majoriteten av alla organisationer. Många kunder har upptäckt att vpn-modellen som tvingades inte är skalbar eller utför tillräckligt för 100 % fjärrarbetesscenarier som den här krissituation medförde. Det krävs snabba lösningar för att organisationen ska fortsätta att fungera effektivt.

För Office 365-tjänsten har Microsoft utformat anslutningskraven för tjänsten med detta problem i åtanke, där en fokuserad, tätt kontrollerad och relativt statisk uppsättning slutpunkter kan optimeras mycket enkelt och snabbt så att användarna får tillgång till tjänsten och därmed minskar kraven på VPN-infrastrukturen så att den kan användas av trafik som fortfarande kräver det.

Office 365 kategoriserar de obligatoriska slutpunkterna för Office 365 i tre kategorier: **Optimera** **,** Tillåt och **Standard**. **Optimera** slutpunkter är vårt fokus här och har följande egenskaper:

- Microsoft ägda och hanterade slutpunkter som finns på Microsofts infrastruktur
- Är dedikerad till grundläggande Office 365-arbetsbelastningar som Exchange Online, SharePoint Online, Skype för företag – Online och Microsoft Teams
- Har IP-adresser tillhandahållit
- Låg förändringshastighet och förväntas vara liten i antal (för närvarande 20 IP-undernät)
- Är känsliga för stora volymer och/eller svarstider
- Kan ha obligatoriska säkerhetselement som tillhandahålls i tjänsten i stället för infogade i nätverket
- Står för cirka 70–80 % av trafiken till Office 365-tjänsten

Denna tätt omfattande uppsättning slutpunkter kan delas upp ur vpn-tunneln och skickas säkert och direkt till Office 365-tjänsten via användarens lokala gränssnitt. Detta kallas delade **tunnlar.**

Säkerhetselement som DLP- och AV-skydd, autentiserings- och åtkomstkontroll kan levereras mycket effektivare mot dessa slutpunkter på olika lager i tjänsten. Eftersom vi även dirigerar om huvuddelen av trafikvolymen från VPN-lösningen frigör vi VPN-kapaciteten för verksamhetskritisk trafik som fortfarande förlitar sig på den. Det bör också i många fall ta bort behovet av att gå igenom ett långt och kostsamt uppgraderingsprogram för att hantera detta nya sätt att hantera.

![Information om split tunnel VPN-konfiguration](../media/vpn-split-tunneling/vpn-split-tunnel-example.png)

_Bild 3: En VPN-delad tunnellösning med definierade Office 365-undantag som skickas direkt till tjänsten. All annan trafik tvingas tillbaka till företagsnätverket oavsett destination._

Ur ett säkerhetsperspektiv har Microsoft en rad säkerhetsfunktioner som kan användas för att ge liknande eller till och med bättre säkerhet än de som levereras genom direktinspektion av lokala säkerhetsstackar. Microsoft Security-teamets blogginlägg Alternativa sätt för säkerhetsexperter och [IT-personal](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/) för att uppnå moderna säkerhetskontroller i dagens unika fjärrarbete scenarier har en tydlig sammanfattning av tillgängliga funktioner och du hittar mer detaljerad vägledning i den här artikeln. Du kan också läsa om Microsofts implementering av VPN-delade tunnlar vid körning av VPN: Hur Microsoft håller [sin fjärranslutna arbetsstyrka ansluten.](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

I många fall kan den här implementeringen uppnås på bara några timmar, vilket ger snabb lösning på ett av de mest tryckande problemen som organisationer ställs inför när de snabbt övergår till fullskalig fjärrarbete. Vägledning för implementering av VPN-delade tunnlar finns [i Implementera VPN-delade tunnlar för Office 365.](microsoft-365-vpn-implement-split-tunnel.md)

## <a name="related-topics"></a>Relaterade ämnen

[Implementera VPN-delade tunnlar för Office 365](microsoft-365-vpn-implement-split-tunnel.md)

[Office 365-prestandaoptimering för kinaanvändare](microsoft-365-networking-china.md)

[Alternativa sätt för säkerhetsexperter och IT-personal för att uppnå moderna säkerhetskontroller i dagens unika fjärrarbete (Microsofts blogg om säkerhetsteam)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[Förbättra VPN-prestanda på Microsoft: använda Windows 10 VPN-profiler för att tillåta automatiska anslutningar](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[Kör på VPN: Så här håller Microsoft sin fjärranslutna arbetsstyrka ansluten](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Office 365 principer för nätverksanslutningar](microsoft-365-network-connectivity-principles.md)

[Utvärdera Nätverksanslutningar för Office 365](assessing-network-connectivity.md)

[Microsoft 365 anslutningstest](https://aka.ms/netonboard)