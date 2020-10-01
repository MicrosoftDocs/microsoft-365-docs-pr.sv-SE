---
title: 'Översikt: dela VPN-tunnlar med Office 365'
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
- M365initiative-CoreDeploy
f1.keywords:
- NOCSH
description: Vägledning för att använda delade VPN-tunnlar med Office 365 för att optimera Office 365-anslutningen för fjärran vändare.
ms.openlocfilehash: fd914a1bb9c5ad905bd94766f3e90d63f7a8bdc3
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327420"
---
# <a name="optimize-office-365-connectivity-for-remote-users-using-vpn-split-tunneling"></a>Optimera Office 365-anslutningen för fjärranvändare med uppdelad VPN-tunnel
<!---
>[!NOTE]
>This topic is part of a set of topics that address Office 365 optimization for remote users.
>- For VPN split tunnel implementation guidance, see [Implementing VPN split tunneling for Office 365](microsoft-365-vpn-implement-split-tunnel.md).
>- For information about optimizing Office 365 worldwide tenant performance for users in China, see [Office 365 performance optimization for China users](microsoft-365-networking-china.md).
-->

För kunder som ansluter sina fjärranslutna enheter till företagets nätverks-eller moln infrastruktur via VPN rekommenderar Microsoft att viktiga Office 365-scenarier **Microsoft Teams**, **SharePoint Online** och **Exchange Online** dirigeras via en konfiguration för _uppdelade VPN-tunnlar_ . Det är särskilt viktigt som den första rad strategin för att under lätta fortsatta arbets uppgifter under arbete – från-hem händelser, till exempel COVID-19 krisen.

![VPN-konfiguration för delad tunnel](../media/vpn-split-tunneling/vpn-model-2.png)

_Bild 1: en lösning för VPN-delning med definierade Office 365-undantag skickade direkt till tjänsten. All annan trafik passerar VPN-tunneln oavsett mål._

Detta tillvägagångs sätt är att tillhandahålla en enkel metod för företag för att minska risken för att en VPN-infrastruktur är mättnad och avsevärt förbättrar Office 365-prestandan i den kortast möjliga tids perioden. Om du konfigurerar VPN-klienter så att de tillåter mest kritiska problem med hög trafik i Office 365 för att kringgå VPN-tunneln uppnår du följande fördelar:

- Omedelbart minskar orsaken till att de flesta kunder rapporterade prestanda-och nätverks kapacitets problem i Enterprise VPN-arkitekturer som påverkar Office 365-användar upplevelsen
  
  Den rekommenderade lösningen riktar sig specifikt till Office 365-tjänste slut punkter kategoriserade som **optimerade** i avsnittet [Office 365 URL: er och IP-adressintervall](https://aka.ms/o365ips). Trafik till dessa slut punkter är mycket känslig för fördröjning och bandbredds begränsning, och att det är möjligt att kringgå VPN-tunneln kan förbättra slutanvändarens upplevelse och minska belastningen på nätverket. Office 365-anslutningar som inte utgör majoriteten av bandbredd eller användar gränssnitt kan fortsätta att dirigeras via VPN-tunneln tillsammans med resten av den Internet bundna trafiken. Mer information finns i [strategin för delad VPN-tunnel](#the-vpn-split-tunnel-strategy).

- Kan konfigureras, testas och implementeras snabbt av kunder och utan ytterligare infrastruktur-eller program krav

  Beroende på VPN-plattform och nätverks arkitektur kan implementeringen ta så lite tid. Mer information finns i [Implementera VPN-delning](microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling).

- Bevarar säkerhets Posture för kundernas VPN-implementeringar genom att inte ändra hur andra anslutningar routas, inklusive trafik till Internet

  Den rekommenderade konfigurationen följer den **minsta behörighets** principen för VPN-trafik undantag och låter kunderna implementera delad tunnel-VPN utan att exponera användare eller infrastruktur för ytterligare säkerhets risker. Nätverks trafik som dirigeras direkt till Office 365-slutpunkter krypteras, verifieras för integritet via Office klient program stackar och omfattning för IP-adresser avsedda för Office 365-tjänster som är härdade både mot program-och nätverks nivå. Mer information finns i [alternativa sätt för säkerhetsadministratörer och för att få moderna säkerhets kontroller i dagens unika scenarier för fjärrarbete (Microsoft Security Team-bloggen)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/).

- Stöds internt av de flesta VPN-plattformarna i Enterprise

  Microsoft fortsätter att samar beta med bransch partners som skapar kommersiella VPN-lösningar för att hjälpa partners att utveckla riktade råd för vägledning och konfiguration för sina lösningar i enlighet med rekommendationerna ovan. Mer information finns i [howto guider för vanliga VPN-plattformar](microsoft-365-vpn-implement-split-tunnel.md#howto-guides-for-common-vpn-platforms).

>[!TIP]
>Microsoft rekommenderar att du fokuserar på delnings-VPN-konfiguration på särskilda IP-adressintervall för Office 365-tjänster. FQDN-eller AppID-baserade delade tunnel-konfigurationer, och möjligt med vissa VPN-klient plattformar, kanske inte helt täcker viktiga Office 365-scenarier och kan krocka med IP-baserade regler för VPN-routning. Av den här anledningen rekommenderar Microsoft inte att använda Office 365 FQDN-namn för att konfigurera delade tunnel-VPN. Användning av FQDN-konfiguration kan vara användbart i andra relaterade scenarier, till exempel filer med fil tillägget PAC eller för att implementera vägar.

Fullständig implementerings vägledning finns i [implementera uppdelade VPN-tunnlar för Office 365](microsoft-365-vpn-implement-split-tunnel.md).

## <a name="the-vpn-split-tunnel-strategy"></a>Den delade tunnel-strategin för VPN

Traditionella företags nätverk är ofta utformade för att fungera säkert för en i förväg moln världen, där de viktigaste data, tjänster, program finns på plats och är direktanslutna till det interna företags nätverket, som är de flesta användare. Nätverks infrastrukturen är alltså inbyggd kring de här elementen på avdelningens kontor är anslutna till huvud kontoret via _MPLS-nätverk (Multiprotocol etikett Switching)_ , och fjärran vändare måste ansluta till företags nätverket via VPN för att få åtkomst till både lokala slut punkter och Internet. I den här modellen passerar all trafik från fjärran vändare företags nätverket och dirigeras till moln tjänsten via en gemensam utförsel plats.

![Tvingande VPN-konfiguration](../media/vpn-split-tunneling/vpn-model-1.png)

_Bild 2: en vanlig VPN-lösning för fjärran vändare där all trafik återförs till företagets nätverk oavsett mål_

Eftersom organisationer flyttar data och program till molnet har den här modellen börjat bli mindre effektiv eftersom den snabbt blir besvärligt, dyrt och inte skalbart, markant påverkar nätverkets prestanda och effektivitet och begränsar organisationens möjligheter att anpassa sig till föränderliga behov. Flera Microsoft-kunder har rapporterat att det är några år sedan 80% av nätverks trafiken var till en intern destination, men i 2020 80% plus för trafik ansluts till en extern molnbaserade resurs.

COVID-19 krisen har förvärrat detta problem för att kräva omedelbara lösningar för de flesta organisationer. Många kunder har upptäckt att den tvingande VPN-modellen inte är skalbar eller utför tillräckligt för 100%-scenarier som denna kris. Snabba lösningar krävs för att dessa organisationer ska fungera effektivt.

För Office 365-tjänsten har Microsoft utformat anslutnings kraven för tjänsten med detta problem på ett fyrkantigt sätt, där en fokuserad, tätt styrd och relativt statisk uppsättning av tjänst slut punkter kan optimeras mycket och snabbt så att den kan användas av den trafik som behövs för att kunna använda tjänsten.

Office 365 kategoriserar de slut punkter som krävs för Office 365 i tre kategorier: **optimera**, **Tillåt**och **standard**. **Optimera** slut punkter här och ha följande egenskaper:

- Är Microsoft-ägda och hanterade slut punkter, som finns på Microsofts infrastruktur
- Är avsedda för viktiga Office 365-arbets belastningar som Exchange Online, SharePoint Online, Skype för företag – Online och Microsoft Teams
- Har IP-adresser tillhandahålls
- Låg pris ändring och förväntas vara små i antal (för närvarande 20 IP-undernät)
- Är hög volym och/eller fördröjnings känslig
- Kan ha nödvändiga säkerhets element i tjänsten i stället för på infogade nätverk
- Konto för omkring 70-80% av volymen för trafik till Office 365-tjänsten

Den här täta uppsättningen slut punkter kan delas ut från den tvingade VPN-tunneln och skickas säkert och direkt till Office 365-tjänsten via användarens lokala gränssnitt. Det kallas **dela tunnlar**.

Säkerhets element som DLP, AV-skydd, inloggningsautentisering och åtkomst kontroll kan skickas mycket mer effektivt mot dessa slut punkter i olika lager i tjänsten. När vi också avlastar trafik volymen från VPN-lösningen, frigör den VPN-kapaciteten för affärs kritisk trafik som fortfarande använder den. Dessutom bör behovet av många fall ta bort så att du kan gå igenom ett tids krävande och dyrt uppgraderings program för att hantera det nya sättet att fungera.

![Information om delade tunnlar för tunnel](../media/vpn-split-tunneling/vpn-split-tunnel-example.png)

_Bild 3: en lösning för VPN-delning med definierade Office 365-undantag direkt till tjänsten. All annan trafik återförs till företagets nätverk oavsett destination._

Från ett säkerhets perspektiv har Microsoft en matris med säkerhetsfunktioner som kan användas för att ge liknande eller ännu bättre säkerhet än den som skickas via den lokala säkerhets stacken. Microsoft Security Teams blogg inlägg [alternativa sätt för säkerhetsexperter och det för att få moderna säkerhets kontroller i dagens unika scenarier för fjärrarbete](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/) har en tydlig översikt över tillgängliga funktioner och du hittar mer detaljerad vägledning i den här artikeln. Du kan också läsa om Microsofts implementering av uppdelad VPN-tunnel vid [körning på VPN: hur Microsoft sköter fjärrpersonalen](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv).

I många fall kan den här implementeringen uppnås på flera timmar, vilket möjliggör en snabb lösning på ett av de mest näraste problemen med organisationer, medan de snabbt kan växla till fjärran sluten fjärråtkomst. Information om hur du skapar delade tunnlar finns i [Implementera VPN dela tunnlar för Office 365](microsoft-365-vpn-implement-split-tunnel.md).

## <a name="related-topics"></a>Relaterade ämnen

[Implementera VPN-fildelning för Office 365](microsoft-365-vpn-implement-split-tunnel.md)

[Office 365 prestanda optimering för Kina-användare](microsoft-365-networking-china.md)

[Alternativa sätt för säkerhetsexperter och för att få moderna säkerhets kontroller i dagens unika scenarier för fjärrarbete (Microsoft Security Team-bloggen)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[Förbättra VPN-prestanda på Microsoft: använda Windows 10-VPN-profiler för att tillåta anslutningar med automatisk anslutning](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[Köra på VPN: hur Microsoft sköter fjärrarbets styrkan](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Office 365 principer för nätverksanslutningar](microsoft-365-network-connectivity-principles.md)

[Utvärdera Nätverksanslutningar för Office 365](assessing-network-connectivity.md)

[Microsoft 365 anslutningstest](https://aka.ms/netonboard)
