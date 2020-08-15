---
title: Microsoft 365 anslutnings test (för hands version) i administrations centret för Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 anslutnings test i M365 administrations Center (för hands version)
ms.openlocfilehash: 421df459e2a8a1c1c62680b2d3658f5bdd297b25
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694602"
---
# <a name="microsoft-365-connectivity-test-in-the-microsoft-365-admin-center-preview"></a>Microsoft 365-anslutnings test i administrations centret för Microsoft 365 (för hands version)

Microsoft 365-anslutnings testet finns på <https://connectivity.office.com> . Det är ett Adjunct verktyg för nätverks insikter och nätverks Poäng information som är tillgänglig i administrations centret för Microsoft 365 under **tillståndet |. Menyn nätverks prestanda** .

>[!NOTE]
>Det inbyggda verktyget har stöd för klient organisationer i WW kommersiell och GCC måttlig men inte GCC hög, DoD, Tyskland och Kina.

Nätverks insikter i administrations centret för Microsoft 365 är baserade på produkt mått för din Microsoft 365-klient organisation. Nätverks insikter från Microsoft 365-anslutnings testet körs lokalt i verktyget. Testning som kan utföras med produkten är begränsad och genom att köra test som är lokala för användaren fler data kan samlas in i större insikter. Tänk på att nätverks insikter i administrations centret för Microsoft 365 visar att det finns ett nätverks problem för användning av Microsoft 365 på en viss Office-plats. Med testet Microsoft 365 Connectivity kan du identifiera rotor Saks orsaken till det problem som ledde till en Rekommenderad åtgärd för förbättring av nätverks prestanda.

Vi rekommenderar att dessa används tillsammans där statusen för nätverks kvalitet kan bedömas för varje Office-plats i administrations centret för Microsoft 365 och mer information finns efter distribution av test baserat på Microsoft 365-anslutnings testet.

>[!IMPORTANT]
>Nätverks insikter, prestanda rekommendationer och utvärderingar i administrations centret för Microsoft 365 är för närvarande förhands gransknings status och är bara tillgänglig för Microsoft 365-klient organisationer som har registrerats i funktionen för förhands granskning.

## <a name="the-advanced-tests-client-application"></a>Klient programmet avancerad test

Det finns två delar till Microsoft 365-anslutnings testet. Det finns <https://connectivity.office.com> en webbplats som är en nedladdnings bar Windows-klient. Den nedladdnings bara klienten kör avancerade test för nätverks anslutning och de flesta testerna kräver att detta kan köras.

Du kan köra det avancerade klient testet från webbplatsen, och resultatet återställs till webb sidan när det körs.

![Exempel test resultat för O365-nätverkskort](../media/m365-mac-perf/m365-mac-perf-onboarding-tool-tests.png)

## <a name="user-office-location"></a>Användarens Office-plats

Användarens Office-plats identifieras från användarens webbläsare. Den används för att identifiera nätverks avstånd till specifika delar av företagets nätverks gräns.

Användarens Office-plats visas i vyn karta.

## <a name="distance-to-the-network-egress-location"></a>Avstånd till nätverks utgångs platsen

Vi hittar en IP-adress på Server sidan. Plats databaser används för att slå upp den ungefärliga placeringen av nätverket och bestämma avståndet från platsen till Office-platsen. Detta visas som en nätverks insikt om avståndet är större än 500 mil (800 kilo meter).

Utgångs platsen för nätverket visas i vyn karta och är ansluten till den användare som har ett nätverks bakpositions drag i företags WANet.

Den plats som hämtas från nätverks utgångs-IP-adressen kanske inte stämmer och det skulle leda till ett falskt resultat från det här testet. Om du vill kontrol lera om det här felet uppstår för en viss IP-adress kan du använda allmänt tillgänglig nätverks-webbplatser för IP-adress för nätverk.

Att implementera lokala och direkta nätverks utgångar från användarens Office-platser till Internet rekommenderas för anslutning till Microsoft 365-nätverk. Förbättringar av lokala och direkta utgångar är det bästa sättet att adressera insikt i det här nätverket.

## <a name="exchange-online-service-front-door"></a>Exchange Online-tjänstens främre dörr

Start dörren för Exchange Online-tjänsten används på samma sätt som i Outlook och vi mäter nätverkets TCP-fördröjning från användarens Office-plats. Dessa båda visas och den som använder Exchange Online-tjänsten är jämförd med listan med rekommenderade optimala front dörrar för den aktuella platsen. Det här visas som en nätverks insikt om ett icke optimalt Exchange Online-tjänstens front dörr används.

Användning av en icke optimal Exchange Online-tjänst front dörren kan orsakas av nätverks belastningar innan företags nätverket avsluts, vilket innebär att det lokala och dirigerade nätverks uttaget rekommenderas. Det kan också orsakas av användning av en fjärran sluten DNS-server för rekursiva lösningar, vilket innebär att vi rekommenderar att du justerar den rekursiva servern för DNS-resolver med nätverks utgången.

Vi beräknar en möjlig förbättring i TCP-fördröjningen till Exchange Online-tjänstens front dörr. Detta görs genom att titta på den testade användarens nätverks svars tid och minska nätverks tiden från den aktuella platsen till tjänsten för Exchange Online service. Skillnaden är den potentiella möjligheten för förbättring.

## <a name="comparison-of-performance-of-customers-in-the-area"></a>Jämförelse av kund prestationer i området

Nätverkets TCP-fördröjning för användarens Office-plats till Exchange Online-tjänstens front dörr jämförs med andra Microsoft 365-kunder i samma tunnelbane område. En inblick i nätverket visas om 10% eller fler kunder i samma tunnelbane område har bättre prestanda.

Detta nät inblick skapas på grund av att alla användare i en stad har till gång till samma infrastruktur för kommunikation och att du har samma närhet av Internet kretsar och Microsofts nätverk.

## <a name="in-use-default-gateway"></a>Använd standard-gateway

Använd standard-gateway är den router som test klienten har konfigurerat för TCP/IP-nätverksanslutningar.

Detta tillhandahålls endast för information och bidrar inte till någon inblick i nätverket.

## <a name="in-use-dns-servers"></a>Används DNS-servrar

Här visas DNS-servern som är konfigurerad på klient datorn där testerna kördes. Det kan vara en DNS-gruppserver för rekursiva lösningar, men detta är ovanligt. Det är troligt att det är en server för DNS-vidarebefordrare som cachelagrar DNS-resultat och vidarebefordrar eventuella icke cachelagrade DNS-begäranden till en annan DNS-server.

Detta tillhandahålls endast för information och bidrar inte till någon inblick i nätverket.

## <a name="identified-dns-recursive-resolver-server"></a>Identifierad DNS-rekursiv Server

Den inaktuella DNS-relösaren för in-use identifieras genom att göra en specifik DNS-begäran och sedan fråga DNS-namnservern efter den IP-adress som den fått från. Denna IP-adress är den rekursiva DNS-lösaren och den kommer att letas upp i databaser med IP-plats för att hitta platsen. Avståndet från användarens Office-plats till platsen för den rekursiva servern för DNS beräknas. Detta visas som en nätverks insikt om avståndet är större än 500 mil (800 kilo meter).

Den plats som hämtas från nätverks utgångs-IP-adressen kanske inte stämmer och det skulle leda till ett falskt resultat från det här testet. Om du vill kontrol lera om det här felet uppstår för en viss IP-adress kan du använda allmänt tillgänglig nätverks-webbplatser för IP-adress för nätverk.

Det här nätverks inblicken påverkar bara valet av Exchange Online-tjänstens främre dörr. För att adressera denna insyn i det lokala nätverket och det direkta nätverks utlandet bör den vara förnödvändig och sedan måste DNS-rekursiva lösa punkter ligga nära detta nät tillkommer.

## <a name="dns-lookup-of-exchange-online-front-end-server-and-sharepoint-online-front-end-server"></a>DNS-sökning av Exchange Online-frontend-Server och front server i SharePoint Online

Dessa visar DNS-posten för tjänstens främre dörr för de här två Microsoft 365-arbetsbelastningarna. De tillhandahålls endast för information och det finns ingen inblick i nätverket.

## <a name="proxy-server-identification"></a>Proxyserver-identifiering

Vi identifierar att proxyservern är konfigurerad på den lokala datorn. Vi tar reda på om någon av dessa är konfigurerade i nätverks Sök vägen för optimering av kategori Microsoft 365-nätverks trafik. Vi identifierar avståndet från användarens Office-plats till proxyservern. Avståndet testas först av ICMP-Ping och om det inte fungerar kan vi testa med TCP-ping och slutligen om det inte går att hitta IP-adressen till proxyservern i en IP-adress plats databas. Vi visar en inblick i nätverket om proxyservern är mer än 500 miles (800 kilo meter) borta från användarens Office-plats.

## <a name="media-quality-checks"></a>Kontroller för medie kvalitet

Det här testet installerar och använder verktyget för nätverks utvärdering i Skype för företag och tolkar resultaten. Verktyget finns på [https://www.microsoft.com/download/details.aspx?id=53885](https://www.microsoft.com/download/details.aspx?id=53885) .

Det här är UDP-protokoll-test som används av Microsoft Teams ljud-och video samtal och konferens funktioner. Vi testar för UDP-paket förlust, UDP-nätverks fördröjning, UDP-Darr och omordning för UDP-paket. En inblick i nätverket visas om någon av dessa är över det tillåtna intervallet.

## <a name="tcp-connectivity-tests"></a>Test av TCP-anslutning

Vi testar för HTTP-anslutning från användar kontoret till alla obligatoriska Microsoft 365-nätverks slut punkter. Dessa publiceras hos [https://aka.ms/o365ip](https://aka.ms/o365ip) . Ett nätverks inblick visas för eventuella nätverks slut punkter som eventuellt inte kan anslutas till.

Anslutningen i rad blockeras av en proxyserver, en brand vägg eller en annan nätverks säkerhets enhet i företags nätverkets perimeter eller används som en molnbaserad proxyserver.

## <a name="ssl-interception-tests"></a>Test av SSL-spärr

Vi testar SSL-certifikatet hos alla obligatoriska Microsoft 365-nätverks slut punkter i kategorin optimera eller Tillåt enligt definitionen i [https://aka.ms/o365ip](https://aka.ms/o365ip) . Om en test inte hittar ett Microsoft SSL-certifikat måste det krypterade nätverket vara anslutet till en mellanliggande nätverks enhet. Ett nätverks inblick visas på alla spärrade krypterade nätverks slut punkter.

När ett SSL-certifikat hittas som inte tillhandahålls av Microsoft visar vi FQDN för testet och ägaren till SSL-certifikatet. Det här SSL-certifikatets ägare kan vara en proxyserver eller det kan vara ett självsignerat företags certifikat.

## <a name="network-path-diagnostics"></a>Nätverksdiagnostik för nätverks Sök väg

I det här avsnittet visas resultatet av en ICMP-traceroute till Exchange Online-tjänstens front dörr, SharePoint Online-tjänstens front dörr och Microsoft Teams-tjänsten. Den är endast avsedd för information och det finns ingen överblick för nätverket.

## <a name="faq"></a>Vanliga frågor och svar

Här är några svar på vanliga frågor.

### <a name="is-this-tool-released-and-supported-by-microsoft"></a>Släpps det här verktyget och stöds av Microsoft?

Det är för närvarande ett bevis på konceptet och vi planerar att tillhandahålla uppdateringar regelbundet tills vi har nått den allmänna statusen för utgivning av tillgänglighet med support från Microsoft. Ge feedback för att hjälpa oss att förbättra. Vi planerar att publicera en mer detaljerad Office 365-guide för nätverks registrering som en del av det här verktyget som är anpassat för organisationen genom dess test resultat.

### <a name="what-is-microsoft-365-service-front-door"></a>Vad är Microsoft 365-tjänstens front dörr?

Microsoft 365-tjänstens front dörr är en start adress i Microsofts globala nätverk där Office-klienter och-tjänster avslutar nätverks anslutningen. För att du ska få en optimal nätverks anslutning till Microsoft 365 rekommenderar vi att nätverks anslutningen avbryts till närmaste Microsoft 365-frontend i staden eller i din tunnelbane linje.

Obs! Microsoft 365 service front dörren har ingen direkt relation till "Azure främre dörren"-produkten som är tillgänglig i Azure Marketplace.

### <a name="what-is-an-optimal-microsoft-365-service-front-door"></a>Vad är en optimal tjänst i Microsoft 365-tjänsten?

En optimal Microsoft 365-tjänst front dörr är en som ligger närmast ditt nätverks uttag, vanligt vis i staden eller i Metro-området. Använd Microsoft 365 Network Performance Tool för att bestämma platsen för din användning av Microsoft 365-tjänsten och optimal tjänstens främre dörr. Om det är optimalt att använda verktyget kan du ansluta till Microsofts globala nätverk.

### <a name="what-is-an-internet-egress-location"></a>Vad är ett avgångs läge för Internet?

Avsluts platsen för Internet är den plats där nätverks trafiken avslutar ditt företags nätverk och ansluter till Internet. Detta identifieras också som den plats där du har en NAT-enhet (Network Address Translation) och oftast vart du ansluter hos en Internet leverantör. Om du ser ett långt avstånd mellan platsen och avgångs platsen för Internet kan detta identifiera ett viktigt WAN-bakposition.

## <a name="related-topics"></a>Relaterade ämnen

[Rekommendationer för nätverks prestanda i Microsoft 365 Admin Center (för hands version)](office-365-network-mac-perf-overview.md)

[Microsoft 365 nätverks prestanda (för hands version)](office-365-network-mac-perf-insights.md)

[Microsoft 365 Network Assessment (för hands version)](office-365-network-mac-perf-score.md)

[Microsoft 365 nätverks anslutningar (för hands version)](office-365-network-mac-location-services.md)
