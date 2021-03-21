---
title: Testverktyg för Microsoft 365-nätverksanslutning (förhandsversion)
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
description: Testverktyg för Microsoft 365-nätverksanslutning (förhandsversion)
ms.openlocfilehash: 3597996a74cccc3a178f7a5a637c956e0393641b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926124"
---
# <a name="microsoft-365-network-connectivity-test-tool-preview"></a>Testverktyg för Microsoft 365-nätverksanslutning (förhandsversion)

Testverktyget för Microsoft 365-nätverksanslutning finns i <https://connectivity.office.com> . Det är ett ad föreläggande till nätverksutvärderingen och informationen om nätverksinsikter som är tillgänglig i administrationscentret för Microsoft 365 under **| Menyn** Anslutning.

> [!IMPORTANT]
> Det är viktigt att logga in på Microsoft 365-klienten eftersom alla testrapporter delas med administratören och laddas upp till klientorganisationen medan du är inloggad.

![Anslutningstestverktyg](../media/m365-mac-perf/m365-mac-perf-test-tool-page.png)

>[!NOTE]
>Testverktyget för nätverksanslutning har stöd för klientorganisation i kommersiella WW och Tyskland, men inte GCC Måttlig, GCC High, DoD eller Kina.

Nätverksinsikterna i Administrationscenter för Microsoft 365 baseras på regelbundna mått i produkten för Microsoft 365-klienten som aggregeras varje dag. Som jämförelse körs nätverksinsikter från Microsoft 365-nätverksanslutningstestet lokalt och en gång i verktyget. Tester som kan utföras i produkten är begränsade och genom att köra tester som är lokala för användaren kan mer data samlas in, vilket resulterar i djupare insikter. Överväg då att nätverksinsikter i Microsoft 365 Admin Center visar att det finns nätverksproblem för användning av Microsoft 365 på en viss kontorsplats. Anslutningstestet för Microsoft 365 kan hjälpa dig att identifiera orsaken till problemet, vilket leder till en rekommenderad åtgärd för prestandaförbättringar.

Vi rekommenderar att dessa används tillsammans där nätverkskvalitetsstatus kan bedömas för varje kontor i administrationscentret för Microsoft 365 och mer information finns efter testning baserad på Microsoft 365-anslutningstestet.

>[!IMPORTANT]
>Nätverksinsikter, prestandarekommendationer och utvärderingar i administrationscentret för Microsoft 365 finns för närvarande i förhandsgranskningsstatus och är endast tillgängligt för Microsoft 365-klienter som har registrerats i programmet för funktionsförhandsgranskning.

## <a name="what-happens-at-each-test-step"></a>Vad händer vid varje teststeg?

### <a name="office-location-identification"></a>Platsidentifiering för kontor

När du klickar på knappen Kör test visar vi sidan med körtest och identifierar platsen för office. Du kan ange din plats efter stad, delstat och land eller så kan du få den upptäckt från webbläsaren. Om du känner igen den begär vi latitud och longitud från webbläsaren och begränsar noggrannheten till 300 m gånger 300 m före användning. Vi gör detta eftersom det inte är nödvändigt att identifiera platsen mer exakt än byggnaden för nätverksprestanda. 

### <a name="javascript-tests"></a>JavaScript-tester

Efter identifiering av kontorsplatsen kör vi ett TCP-svarstidstest i JavaScript och vi begär data från tjänsten om i bruk och rekommenderade Office 365-tjänste front door servers. När dessa är slutförda visar vi dem på kartan och på informationsfliken där de kan visas innan nästa steg.

### <a name="download-the-advanced-tests-client-application"></a>Ladda ned det avancerade testklientprogrammet

Nästa steg är att starta nedladdningen av det avancerade testklientprogrammet. Vi förlitar oss på att användaren startar klientprogrammet och att de också måste ha .NET Core installerat.

Det finns två delar i Microsoft 365-nätverksanslutningstestet: webbplatsen och ett <https://connectivity.office.com> nedladdningsbart Windows-klientprogram som kör avancerade nätverksanslutningstester. De flesta tester kräver att programmet körs. Den fyller i resultat igen på webbsidan medan den körs.

Du uppmanas att ladda ned det avancerade klienttestprogrammet från webbplatsen när webbläsartesterna har slutförts. Öppna och kör filen när du uppmanas att göra det.

![Avancerade tester, klientprogram](../media/m365-mac-perf/m365-mac-perf-open-run-file.png)

### <a name="start-the-advanced-tests-client-application"></a>Starta det avancerade testklientprogrammet

När klientprogrammet startar uppdateras webbsidan för att visa detta och testdata börjar tas emot på webbsidan. Det uppdateras varje gång nya data tas emot och du kan granska data när de kommer in.

### <a name="advanced-tests-completed-and-test-report-upload"></a>Avancerade tester slutförda och uppladdning av testrapport

När testerna är slutförda webbsidan och klienten för avancerade tester anger detta och om användaren är inloggad i testrapporten laddas upp till kundernas klientorganisation.

## <a name="sharing-your-test-report"></a>Dela din testrapport

Testrapporten kräver inloggning till ditt Office 365-konto. Administratören väljer hur testrapporten ska delas.

### <a name="sharing-your-report-with-your-administrator"></a>Dela rapporten med administratören

Alla testrapporter när du är inloggad delas med administratören.

### <a name="sharing-with-your-microsoft-account-team-support-or-other-personnel"></a>Dela med din Microsoft-kontogrupp, support eller annan personal

Testrapporter utom personidentifiering delas med Microsoft-anställda. Det här är aktiverat som standard och kan inaktiveras av administratören **i | Sidan Nätverksanslutning** i administrationscentret för Microsoft 365.

### <a name="sharing-with-other-users-who-sign-in-to-the-same-office-365-tenant"></a>Dela med andra användare som loggar in på samma Office 365-klientorganisation

Du kan välja användare att dela rapporten med och det här är aktiverat som standard. Det kan också inaktiveras av administratören.

![Dela en länk till testresultatet med en användare](../media/m365-mac-perf/m365-mac-perf-share-to-user.png)

### <a name="sharing-with-anyone-using-a-reportid-link"></a>Dela med vem som helst med hjälp av en ReportID-länk

Du kan dela din testrapport med vem som helst genom att ge åtkomst till en ReportID-länk. Då genereras en URL som du kan skicka till någon så att han eller hon kan få fram testrapporten utan att logga in. Det här är inaktiverat som standard och måste aktiveras av administratören.

![Dela en länk till dina testresultat](../media/m365-mac-perf/m365-mac-perf-share-link.png)

## <a name="network-connectivity-test-results"></a>Testresultat för nätverksanslutning

Resultatet visas på flikarna **Sammanfattning** **och** Information. På sammanfattningsfliken visas en karta över den identifierade nätverks perimeter och en jämförelse av nätverksutvärderingen med andra Office 365-kunder i närheten. Det går också att dela testrapporten. Så här ser vyn sammanfattningsresultat ut.

![Sammanfattning av testverktyget för nätverksanslutning](../media/m365-mac-perf/m365-mac-perf-summary-page.png)

Här är ett exempel på informationsflikens utdata som verktyget visar. På fliken Information visas en grön cirkelkontroll om resultatet jämförs med ett tröskelvärde. Vi visar ett rött triangelutropstecken om resultatet överskred ett tröskelvärde som anger en nätverksinsikt. I följande avsnitt beskrivs varje detaljfliksresultatrader och de tröskelvärden som används för nätverksinsikter.

![Exempel på testverktyg för nätverksanslutning](../media/m365-mac-perf/m365-mac-perf-all-details.png)

### <a name="your-location-information"></a>Din platsinformation

I det här avsnittet visas testresultat som är relaterade till din plats.

#### <a name="your-location"></a>Din plats

Användarplatsen identifieras från användarens webbläsare eller så kan den skrivas in efter användarens val. Den används för att identifiera nätverksavstånd till specifika delar av företagsnätverks perimeter. Endast staden från den här platsen och avståndet till andra nätverkspunkter sparas i rapporten.

Användarens kontor visas i kartvyn.

#### <a name="network-egress-location-the-location-where-your-network-connects-to-your-isp"></a>Utgående nätverksplats (den plats där nätverket ansluts till din Internetleverantör)

Vi identifierar den utgående IP-adressen för nätverket på serversidan. Platsdatabaser används för att slå upp ungefärlig plats för nätverkets utgående position. Dessa databaser har vanligtvis noggrannheten omkring 90 % av IP-adresserna. Om platsen som du letade efter från den utgående IP-adressen för nätverket inte är korrekt skulle det leda till ett falskt resultat av det här testet. För att verifiera om det här felet inträffar för en specifik IP-adress kan du använda offentligt tillgängliga nätverks-IP-adressplatser för att jämföra med din faktiska plats.

#### <a name="your-distance-from-the-network-egress-location"></a>Ditt avstånd från nätverkets utgående plats

Vi fastställer avståndet från platsen till platsen där kontoret finns. Det här visas som en nätverksinsikt om avståndet är större än **500** km (800 kvadratkilometer) eftersom det troligen ökar TCP-svarstiden med mer än 25 ms och kan påverka användarupplevelsen.

Den utgående platsen för nätverket visas i kartvyn och ansluts till användarens kontorsplats som anger nätverkets wan-plats.

För Microsoft 365-nätverksanslutning rekommenderas implementering av lokal och direkt nätverkstrafik från användares kontorsplatser till Internet. Förbättringar av lokal och direkt utgående e-post är det bästa sättet att hantera den här nätverksinsikten.

#### <a name="proxy-server-information"></a>Proxyserverinformation

Vi identifierar proxyservrar som konfigurerats på den lokala datorn. Vi identifierar om någon av dessa är konfigurerad i nätverkssökvägen för optimera kategori Microsoft 365-nätverkstrafik. Vi identifierar avståndet från användarens kontorsplats till proxyservrarna. Avståndet testas först av ICMP ping och om det inte fungerar testar vi med TCP ping och slutligen om det misslyckas letar vi upp proxyserverns IP-adress i en IP-adressplatsdatabas. Vi visar en nätverksinsikt om proxyservern är längre än **500** kilometer (800 kilometer) från användarens kontorsplats.

#### <a name="virtual-private-network-vpn-you-use-to-connect-to-your-organization"></a>Virtuellt privat nätverk (VPN) som du använder för att ansluta till din organisation

Detta identifierar om du använder ett VPN för att ansluta till Office 365. Ett passningsresultat visas om du inte har någon VPN, eller om du har en VPN med rekommenderad konfiguration av delade tunnlar för Office 365.

#### <a name="vpn-split-tunnel"></a>VPN-delade tunnel

Varje optimerad kategoriväg för Exchange Online, SharePoint Online och Microsoft Teams testas för att se om den är tunnel på VPN eller inte. Om arbetsbelastningen delas upp undviker du VPN helt och hållet. En tunnelerad arbetsbörda skickas via VPN. En selektiv tunnelarbetsbelastning har vissa vägar att skicka via VPN och en del delas upp. Ett passningsresultat visar om alla arbetsbelastningar är delade eller selektiva tunnlar.

#### <a name="customers-in-your-metropolitan-area-with-better-performance"></a>Kunder i din region med bättre prestanda

Nätverket TCP-svarstiden för användarens kontorsplats till Exchange Online-tjänstens framsida jämförs med andra Microsoft 365-kunder i samma metroområde. En nätverksinsikt visas om 10 % eller fler av kunderna i samma metroområde har bättre prestanda. Det innebär att användarna får bättre prestanda i Microsoft 365-användargränssnittet.

Den här nätverksinsikten genereras utifrån att alla användare i en stad har tillgång till samma telekommunikationsinfrastruktur och samma närhet till internetkretsar och Microsofts nätverk.

#### <a name="time-to-make-a-dns-request-on-your-network"></a>Dags att göra en DNS-begäran i nätverket

Här visas den DNS-server som är konfigurerad på den klientdator som körde testerna. Det kan vara en DNS-rekursiv Resolver-server, men detta är ovanligt. Det är troligare att det är en DNS-vidarebefordrare som cachelagrar DNS-resultat och vidarebefordrar alla okopplade DNS-begäranden till en annan DNS-server.

Detta tillhandahålls endast för information och bidrar inte till någon nätverksinsikt.

#### <a name="your-distance-from-andor-time-to-connect-to-a-dns-recursive-resolver"></a>Ditt avstånd från och/eller tid att ansluta till en DNS-rekursiv resolver

Den aktuella DNS-rekursiva Resolver identifieras genom att göra en specifik DNS-begäran och sedan fråga DNS-namnservern om den IP-adress som den tog emot samma begäran från. Den här IP-adressen är DNS-rekursiv resolver och den letas upp i DATABASER för IP-adressplats för att hitta platsen. Avståndet från användarens kontorsplats till DNS-rekursiv resolverserverplats beräknas sedan. Det här visas som en nätverksinsikt om avståndet är större än **500 kilometer** (800 kvadratkilometer).

Platsen som du letade efter från den utgående IP-adressen för nätverket kanske inte är korrekt, vilket skulle leda till ett falskt resultat av det här testet. För att verifiera om det här felet inträffar för en viss IP-adress kan du använda offentligt tillgängliga nätverks-IP-adressplatswebbplatser.

Den här nätverksinsikten påverkar specifikt valet av Exchange Online-tjänstens dörr. För att hantera den här insikten ska lokal och direkt utgående nätverkstrafik vara en förutsättning och därefter ska DNS-rekursiv resolver finnas nära den utgående nätverksadressen.

### <a name="exchange-online"></a>Exchange Online

I det här avsnittet visas testresultat som är relaterade till Exchange Online.

#### <a name="exchange-service-front-door-location"></a>Exchange-tjänst, frontendplats

Den aktiva Exchange-tjänsten hos användarna identifieras på samma sätt som Outlook gör det och vi mäter tcp-svarstiden i nätverket från användarens plats till den. TCP-svarstiden visas och den i använda Exchange-tjänstens dörr jämförs med listan över bästa service front dörrar för den aktuella platsen. Det här visas som en nätverksinsikt om en av de bästa Exchange-tjänsterna utanför dörren inte används.

Att inte använda en av de bästa Exchange-tjänsternas fronter kan orsakas av nätverkets backhaul innan företagsnätverkets utgående punkt, i vilket fall vi rekommenderar lokal och direkt utgående nätverkstrafik. Det kan också orsakas av användning av en fjärr-DNS-rekursiv resolverserver, och i sådana fall rekommenderar vi att du justerar DNS-rekursiv resolverserver med nätverkets utgående post.

Vi beräknar en möjlig förbättring av TCP-svarstiden (ms) till Exchange-tjänstens dörr. Det gör du genom att titta på den testade nätverksfördröjning för användarplats och subtrahera nätverksfördröjningen från den aktuella platsen till closets Exchange-tjänstens yttersida. Skillnaden representerar en möjlighet till förbättring.

#### <a name="best-exchange-service-front-doors-for-your-location"></a>Bästa Exchange-serviceporten för din plats

Här finns en lista över de bästa Exchange-serviceplatserna före dig, efter stad, för din plats.

#### <a name="service-front-door-recorded-in-the-client-dns"></a>Serviceens klient så att den är registrerad i klient-DNS

Här visas DNS-namn och IP-adress för Exchange-tjänstens dörrserver som du dirigerades till. Den tillhandahålls endast som information och det finns inga associerade nätverksinsikter.

### <a name="sharepoint-online"></a>SharePoint Online

I det här avsnittet visas testresultat som är relaterade till SharePoint Online och OneDrive.

#### <a name="the-service-front-door-location"></a>Platsen där servicen befinner sig

Den aktiva SharePoint-tjänstens klient identifieras på samma sätt som OneDrive-klienten gör och vi mäter TCP-svarstiden i nätverket från användarens kontorsplats till den.

#### <a name="download-speed"></a>Nedladdningshastighet

Vi mäter nedladdningshastigheten för en fil på 15 MB från SharePoint-tjänstens dörr. Resultatet visas i megabyte per sekund för att ange vilken storleksfil i megabyte som kan laddas ned från SharePoint eller OneDrive på **en sekund.** Talet ska vara ungefär en tiondel av den minsta kretsens bandbredd i megabit per sekund. Om du till exempel har en Internetanslutning på 100 Mbit/s kan du förvänta dig 10 MB per sekund (10 MB).

#### <a name="buffer-bloat"></a>Buffertbuffert

Under nedladdningen på 15 MB mäter vi TCP-svarstiden till SharePoint-tjänstens dörr. Det här är svarstiden under belastning och den jämförs med svarstiden när den inte är under belastning. Svarstiden vid inläsning ökar ofta i konsumentnätverksenhetsbuffert som läses in (eller upphöjs). En nätverksinsikt visas för en större mängd 1 000 eller fler.

#### <a name="service-front-door-recorded-in-the-client-dns"></a>Serviceens klient så att den är registrerad i klient-DNS

Här visas DNS-namn och IP-adress för SharePoint-tjänstens dörrserver som du dirigerades till. Den tillhandahålls endast som information och det finns inga associerade nätverksinsikter.

### <a name="microsoft-teams"></a>Microsoft Teams

I det här avsnittet visas testresultat som är relaterade till Microsoft Teams.

#### <a name="media-connectivity-audio-video-and-application-sharing"></a>Medieanslutningar (ljud, video och programdelning)

Detta test för UDP-anslutning till Microsoft Teams-tjänstens dörr. Om detta är blockerat kanske Microsoft Teams fortfarande arbetar med TCP, men ljud och video är nedsatt. Läs mer om UDP-nätverksmått som även gäller för Microsoft Teams vid Mediakvalitet och [Nätverksanslutningsprestanda i Skype för företag – Online](/skypeforbusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)

#### <a name="packet-loss"></a>Paketförlust

Visar UDP-paketförlusten mäts i ett 10 sekunders testljudsamtal från klienten till Microsoft Teams-tjänstens klientport. Den bör vara lägre än **1,00 %** för ett pass.

#### <a name="latency"></a>Svarstid

Visar den mätda UDP-svarstiden, som ska vara lägre än **100 ms.**

#### <a name="jitter"></a>Jitter

Visar mätet UDP-jitter, som ska vara lägre än **30 ms.**

#### <a name="connectivity"></a>Anslutning

Vi testar för HTTP-anslutning från användarens kontorsplats till alla obligatoriska Microsoft 365-nätverksslutpunkter. Dessa publiceras vid [https://aka.ms/o365ip](./urls-and-ip-address-ranges.md) . En nätverksinsikt visas för alla nätverksslutpunkter som inte kan anslutas.

Anslutningen kan blockeras av en proxyserver, en brandvägg eller en annan säkerhetsenhet på företagsnätverkets perimeter. Anslutning till TCP-port 80 testas med en HTTP-begäran och anslutning till TCP-port 443 testas med en HTTPS-begäran. Om det inte finns något svar markeras FQDN som ett fel. Om det finns en HTTP-svarskod 407 markeras FQDN som ett fel. Om det finns en HTTP-svarskod 403 kontrollerar vi serverattributet för svaret och om det verkar vara en proxyserver markerar vi det som ett fel. Du kan simulera de tester vi utför med kommandoradsverktyget i Windows curl.exe.

Vi testar SSL-certifikatet vid varje obligatorisk Microsoft 365-nätverksslutpunkt som finns i optimera- eller tillåt-kategorin enligt definitionen i [https://aka.ms/o365ip](./urls-and-ip-address-ranges.md) . Om några tester inte hittar ett Microsoft SSL-certifikat måste det krypterade nätverket ha snappats upp av en mellanled på nätverket. En nätverksinsikt visas på alla avlyssade krypterade nätverksslutpunkter.

Om ett SSL-certifikat som inte tillhandahålls av Microsoft visas FQDN för testet och SSL-certifikatägaren som används. Den här SSL-certifikatägaren kan vara en proxyserverleverantör eller ett själv signerat företagscertifikat.

#### <a name="network-path"></a>Nätverkssökväg

I det här avsnittet visas resultatet av en ICMP-spårningsroute till Exchange Online-tjänstens yttersida, SharePoint Online-tjänstens frontport och Microsoft Teams-tjänstens frontport. Den tillhandahålls endast som information och det finns inga associerade nätverksinsikter. Det finns tre spårningsroutes. En spårningsroute _till outlook.office365.com_, en spårningsroute till kundernas SharePoint-frontend eller till _microsoft.sharepoint.com_ om det inte fanns en och en spårningsroute _till world.tr.teams.microsoft.com_.

## <a name="connectivity-reports"></a>Anslutningsrapporter

När du är inloggad kan du granska tidigare rapporter som du har kört. Du kan också dela eller ta bort dem från listan.

![Rapporter](../media/m365-mac-perf/m365-mac-perf-reports-list.png)

## <a name="network-health-status"></a>Status för nätverkshälsa

Det visar betydande hälsoproblem med Microsofts globala nätverk som kan påverka Microsoft 365-kunder.

![Status för nätverkshälsa](../media/m365-mac-perf/m365-mac-perf-status-page.png)

## <a name="faq"></a>Vanliga frågor och svar

Här finns svar på några av våra vanliga frågor.

### <a name="is-this-tool-released-and-supported-by-microsoft"></a>Släpps och stöds det här verktyget av Microsoft?

Det är en förhandsversion och vi planerar att tillhandahålla uppdateringar regelbundet tills vi når status för allmänt tillgängliga versioner med support från Microsoft. Lämna gärna feedback som hjälper oss att bli bättre. Vi planerar att publicera en mer detaljerad guide för nätverks onboarding för Office 365 som en del av det här verktyget, som är anpassad för organisationen genom testresultaten.

### <a name="what-is-required-to-run-the-advanced-test-client"></a>Vad krävs för att köra den avancerade testklienten?

För den avancerade testklienten krävs .NET Core 3.1 Desktop Runtime. Om du kör den avancerade testklienten utan det installerade dirigeras du till [installationssidan för .NET Core 3.1.](https://dotnet.microsoft.com/download/dotnet-core/3.1) Se till att installera Desktop Runtime och inte SDK, eller ASP.NET Core Runtime som är högre upp på sidan. Administratörsbehörigheter på datorn krävs för att installera .NET Core.

### <a name="what-is-microsoft-365-service-front-door"></a>Vad är Microsoft 365 service front front door?

Microsoft 365-tjänstens klient är en startpunkt i Microsofts globala nätverk där Office-klienter och -tjänster avslutar nätverksanslutningen. För en optimal nätverksanslutning till Microsoft 365 rekommenderar vi att din nätverksanslutning avslutas till den närmaste Microsoft 365-frontporten i din stad eller metro.

Obs! Microsoft 365-tjänstporter har ingen direkt relation till **Azure Front Door Service-produkten** som är tillgänglig på Azure-marknadsplatsen.

### <a name="what-is-the-best-microsoft-365-service-front-door"></a>Vad är den bästa serviceporten för Microsoft 365?

En bästa Microsoft 365 tjänst front dörr (tidigare kallat en optimal tjänst front dörr) är en som är närmast din nätverks egress, oftast i din stad eller metro område. Använd Microsoft 365-nätverksprestandaverktyget för att avgöra platsen för din användning av Microsoft 365-tjänstens port och den bästa serviceporten. Om verktyget avgör att den som används direkt är en av de bästa kan du förvänta dig en bra anslutning till Microsofts globala nätverk.

### <a name="what-is-an-internet-egress-location"></a>Vad är en utgående Internetplats?

Den utgående Internetplatsen är den plats där din nätverkstrafik går ut ur företagsnätverket och ansluter till Internet. Det här identifieras också som den plats där du har en NAT-enhet (Network Address Translation) och vanligtvis är det där du ansluter med en Internetleverantör (ISP). Om du ser ett långt avstånd mellan din plats och din utgående Internetplats kan detta identifiera ett betydande WAN-konto.

## <a name="related-topics"></a>Relaterade ämnen

[Nätverksanslutning i administrationscentret för Microsoft 365 (förhandsversion)](office-365-network-mac-perf-overview.md)

[Microsoft 365 nätverksprestandainsikter (förhandsversion)](office-365-network-mac-perf-insights.md)

[Microsoft 365-nätverksutvärdering (förhandsversion)](office-365-network-mac-perf-score.md)

[Microsoft 365 Network Connectivity Location Services (förhandsversion)](office-365-network-mac-location-services.md)