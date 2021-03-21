---
title: Nätverksanslutning i administrationscentret för Microsoft 365 (förhandsversion)
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
- m365initiative-coredeploy
description: Översikt över nätverksanslutningen i administrationscentret för Microsoft 365 (förhandsversion)
ms.openlocfilehash: 0bfcebff4ebbefdb77049119fef2402af1ca8f90
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926102"
---
# <a name="network-connectivity-in-the-microsoft-365-admin-center-preview"></a>Nätverksanslutning i administrationscentret för Microsoft 365 (förhandsversion)

Administrationscentret för Microsoft 365 innehåller nu aggregerade mått för nätverksanslutning som samlats från Microsoft 365-klienten och är tillgängliga för visning endast av administrativa användare i klientorganisationen.

> [!div class="mx-imgBorder"]
> ![Testverktyg för nätverksanslutning](../media/m365-mac-perf/m365-mac-perf-admin-center.png)

**Nätverksutvärderingar** **och nätverksinsikter** visas i Administrationscenter för Microsoft 365 under **| Anslutningar**.

> [!div class="mx-imgBorder"]
> ![Sidan Nätverksprestanda](../media/m365-mac-perf/m365-mac-perf-page-nav.png)

>[!NOTE]
>Testverktyget för nätverksanslutning har stöd för klientorganisation i kommersiella WW och Tyskland, men inte GCC Måttlig, GCC High, DoD eller Kina.

Första gången du navigerar till sidan nätverksprestanda visas ett översiktsfönster med en karta över globala nätverksprestanda, en nätverksutvärdering begränsad till hela klientorganisationen och en lista över aktuella problem. Från översikten kan du öka detalj detaljvyn för att visa specifika nätverksprestandamätvärden och -problem efter plats. Mer information finns i Översikt [av nätverksprestanda i Administrationscenter för Microsoft 365.](#network-connectivity-overview-in-the-microsoft-365-admin-center)

Du kan bli ombedd att ansluta till den offentliga förhandsversionen för den här funktionen för din organisations räkning. Accepterande sker vanligtvis direkt och sedan visas sidan nätverksanslutning. 

När du navigerar till sidan nätverksanslutning visas ett översiktsfönster med en karta över globala nätverksprestanda, en nätverksutvärdering begränsad till hela klientorganisationen och en lista över aktuella problem. För att komma åt den här sidan måste du vara administratör för organisationen i Microsoft 365. Den administrativa rollen Rapportläsare har läsbehörighet till den här informationen. För att konfigurera platser och andra element i nätverksanslutningen måste en administratör vara en del av serveradministratörsrollen, till exempel rollen Tjänstsupportadministratör. Från översikten kan du öka detalj detaljvyn för att visa specifika nätverksprestandamätvärden och -problem efter plats. Mer information finns i Översikt [över nätverksanslutning i Administrationscenter för Microsoft 365.](#network-connectivity-overview-in-the-microsoft-365-admin-center)

## <a name="pre-requisites-for-network-connectivity-assessments-to-appear"></a>Förutsättningar för att en utvärdering av nätverksanslutningen ska visas

För att komma igång aktiverar du din inställning för platsanmälning för att automatiskt samla in data från enheter som använder Windows Location Services, går till listan Platser och lägger till eller laddar upp platsdata eller kör Microsoft 365-nätverksanslutningstestet från dina kontorsplatser. Nätverksanslutningen kan dock utvärderas i hela organisationen, men alla förbättringar av nätverksdesignen måste göras för specifika kontor. Information om nätverksanslutningen tillhandahålls för varje kontor när dessa platser kan fastställas. Det finns tre alternativ för att hämta nätverksutvärderingar från kontorsplatser:

### <a name="1-enable-windows-location-services"></a>1. Aktivera Windows Platstjänster

För det här alternativet måste du ha minst två datorer på varje kontorsplats som har stöd för förutsättningarna. OneDrive för Windows-versionen måste vara uppdaterad och installerad på varje dator. Mer information om OneDrive-versioner finns i Viktig information [för OneDrive.](https://support.office.com/article/onedrive-release-notes-845dcf18-f921-435e-bf28-4e24b95e5fc0) Nätverksmått planeras att läggas till i andra Office 365-klientprogram inom kort.

Windows platstjänst måste godkännas på maskinerna. Du kan testa det genom att **köra appen** Kartor och hitta dig själv. Den kan aktiveras på en enda dator med **| Sekretess | Plats** där inställningen Tillåt _appar att komma åt din plats_ måste vara aktiverad. Windows Platstjänster medgivande kan distribueras till datorer som använder MDM eller grupprincip med inställningen _LetAppsAccessLocation._

Du behöver inte lägga till platser i administrationscentret med den här metoden eftersom de automatiskt identifieras i stadsupplösningen. Du kan inte visa flera kontorsplatser på en stad med Windows Platstjänster. Platsinformation avrundas också till närmaste 300 meter och 300 meter innan den laddas upp så att det inte går att komma åt mer exakt platsinformation.

Datorer bör ha tillgång till Wi-Fi-nätverk i stället för en Ethernet-kabel. Datorer med en Ethernet-kabel har inte rätt platsinformation.

Måttprov och kontorsplatser bör börja visas 24 timmar efter att dessa förutsättningar har uppfyllts.

### <a name="2-add-locations-and-provide-lan-subnet-information"></a>2. Lägga till platser och ange lan-undernätsinformation

För det här alternativet krävs varken Windows Wi-Fi eller windows Wi-Fi plats. Din Version av OneDrive för Windows måste vara uppdaterad och installerad på varje dator på platsen.

Du måste också lägga till platser i sidan Admin Center-nätverksanslutning eller importera dem från en CSV-fil. Platserna som läggs till måste innehålla informationen om office LAN-undernätet.

Eftersom du lägger till platser kan du ha flera kontor definierade på en stad.

Alla testmått från klientdatorer innehåller LAN-undernätsinformationen, som är korrelerad med den platsinformation om kontoret som du har angett. Måttprov och kontorsplatser bör börja visas 24 timmar efter att dessa förutsättningar har uppfyllts.

### <a name="3-manually-gather-test-reports-with-the-microsoft-365-network-connectivity-test-tool"></a>3. Samla in testrapporter manuellt med testverktyget för Microsoft 365-nätverksanslutning

För det här alternativet måste du identifiera en person på varje plats. Be dem bläddra till [Microsoft 365-nätverksanslutningstest](https://connectivity.office.com) på en Windows-dator där de har administratörsbehörighet. På webbplatsen måste de logga in på sitt Office 365-konto för samma organisation som du vill se resultaten för. Sedan ska de klicka på **Kör test**. Under testet finns det ett nedladdat anslutningstest MED EXE. De måste öppna och köra det också. När testerna har slutförts laddas testresultatet upp till Office 365.

Testrapporter länkas till en plats om den har lagts till med information om LAN-undernätet, annars visas de endast på platsen för staden.

Måttprov och kontorsplatser bör börja visas 2–3 minuter efter att en testrapport har slutförts. Mer information finns i [Microsoft 365-nätverksanslutningstest (förhandsversion).](office-365-network-mac-perf-onboarding-tool.md)

## <a name="how-do-i-use-this-information"></a>Hur använder jag den här informationen?

**Nätverksinsikter**, deras relaterade prestandarekommendationer och nätverksutvärderingar är avsedda att bidra till att utforma nätverks perimeter för kontorsplatser. Varje insikt ger information om prestandaegenskaper för ett specifikt vanligt problem för varje geografisk plats där användarna har åtkomst till din klientorganisation. **Prestandarekommendationer** för varje nätverksinsikt ger specifika ändringar i nätverksarkitekturdesignen som du kan göra för att förbättra användarupplevelsen relaterad till Microsoft 365-nätverksanslutning. Nätverksutvärderingen visar hur nätverksanslutningen påverkar användarupplevelsen, vilket gör det möjligt att jämföra olika nätverksanslutningar för användarplatser.

**Nätverksutvärderingar** sammanfattar en mängd nätverksprestandamätvärden till en ögonblicksbild av företagets nätverkshälsa, som representeras av ett poängvärde mellan 0 och 100. Nätverksutvärderingar är begränsade till både hela klientorganisationen och för varje geografisk plats som användarna ansluter till klientorganisationen från, vilket ger Microsoft 365-administratörer ett enkelt sätt att snabbt förstå ett av företagets nätverkshälsa och snabbt öka detaljgranskningen i en detaljerad rapport för alla globala kontor.

Komplexa företag med flera kontorsplatser och perimeterarkitekturer utanför nätverket kan dra nytta av den här informationen antingen under den första introduktionen till Microsoft 365 eller för att åtgärda prestandaproblem i nätverket som upptäcks med användningstillväxt. Detta är vanligtvis inte nödvändigt för småföretag som använder Microsoft 365 eller för företag som redan har enkel och direkt nätverksanslutning. Företag med fler än 500 användare och flera kontor förväntas ha störst nytta.

>[!IMPORTANT]
>Nätverksinsikter, prestandarekommendationer och utvärderingar i administrationscentret för Microsoft 365 finns för närvarande i förhandsgranskningsstatus och är endast tillgängligt för Microsoft 365-klienter som har registrerats i programmet för funktionsförhandsgranskning.

## <a name="enterprise-network-connectivity-challenges"></a>Utmaningar vid företagsnätverksanslutningar

> [!div class="mx-imgBorder"]
> ![Kundnätverk till molnet](../media/m365-mac-perf/m365-mac-perf-first-last-mile.png)

Många företag har nätverks perimeterkonfigurationer som har vuxit över tid och främst utformats för att ge de anställda tillgång till Internetwebbplatser där de flesta webbplatser inte är kända i förväg och inte är betrodda. Det nödvändiga fokuset är att undvika attacker mot skadlig programvara och fiske från dessa okända webbplatser. Den här nätverkskonfigurationsstrategin kan, även användbar för säkerhetsändamål, leda till försämring av Microsoft 365-användarprestanda och användarupplevelse.

## <a name="how-we-can-solve-these-challenges"></a>Hur vi kan lösa de här problemen

Företag kan förbättra den allmänna användarupplevelsen och skydda miljön genom att följa [Office 365-anslutningsprinciperna](./microsoft-365-network-connectivity-principles.md) och genom att använda nätverksanslutningsfunktionen i administrationscentret för Microsoft 365. I de flesta fall har följande allmänna principer betydande inverkan på slutanvändarens svarstid, tjänsttillförlitlighet och övergripande prestanda i Microsoft 365.

Microsoft uppmanas ibland att undersöka problem med nätverksprestanda med Microsoft 365 för stora företagskunder, och dessa har ofta en orsak relaterad till kundernas perimeterinfrastruktur i nätverket. När en vanlig orsak till ett perimeterproblem i kundens nätverk påträffas försöker vi identifiera enkla testmått som identifierar det. Ett test med ett mättröskelvärde som identifierar ett specifikt problem är värdefullt eftersom vi kan testa samma mått på valfri plats, avgöra om orsaken finns där och dela den som en nätverksinsikt med administratören.

Vissa nätverksinsikter anger bara ett problem som behöver undersökas ytterligare. En nätverksinsikt där vi har tillräckligt många tester för att visa en viss åtgärd för att korrigera orsaken visas som en **rekommenderad åtgärd.** De här rekommendationerna, baserat på livevärden som visar värden som faller utanför ett förutbestämt tröskelvärde, är mycket mer värdefulla än allmänna råd om metodtips eftersom de är specifika för din miljö och visar den faktiska förbättringen när de rekommenderade ändringarna har gjorts.

## <a name="network-connectivity-overview-in-the-microsoft-365-admin-center"></a>Översikt över nätverksanslutningen i administrationscentret för Microsoft 365

Microsoft har befintliga nätverksmått från flera Office-skrivbords- och webbklienter som har stöd för Microsoft 365. Dessa mått används nu för att ge insikter om nätverksarkitekturdesign  och en nätverksutvärdering som visas på sidan Nätverksanslutning i Administrationscenter för Microsoft 365.

Som standard identifierar ungefärlig platsinformation som associeras med nätverksmått staden där klientenheterna finns. Nätverksutvärderingen på varje plats visas med färg och det relativa antalet användare på varje plats representeras av storleken på cirkeln.

> [!div class="mx-imgBorder"]
> ![Översiktskarta för nätverksinsikter](../media/m365-mac-perf/m365-mac-perf-overview-map.png)

På översiktssidan visas även nätverksutvärderingen för kunden som ett viktat medelvärde för alla kontorsplatser.

> [!div class="mx-imgBorder"]
> ![Nätverksutvärdering](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

Du kan visa en tabellvy över de platser där de kan filtreras, sorteras och redigeras på fliken Platser. Platser med specifika rekommendationer kan också innehålla en uppskattad potentiell förbättring av svarstiden. Beräkningen beräknas genom att ta mediansvarstid för organisationens användare på platsen och subtrahera mediansvarsfördröjningen för alla organisationer på samma ort.

> [!div class="mx-imgBorder"]
> ![Platser med nätverksinsikter](../media/m365-mac-perf/m365-mac-perf-locations.png)

## <a name="specific-office-location-network-performance-summary-and-insights"></a>Nätverksprestandasammanfattning och information för specifik kontorsplats

Om du väljer en kontorsplats öppnas en platsspecifik sammanfattningssida med information om den utgående nätverkstrafik som har identifierats från måtten för den kontorsplatsen.

> [!div class="mx-imgBorder"]
> ![Information om nätverksinsikter efter plats](../media/m365-mac-perf/m365-mac-perf-locations-plan-overview.png)

En karta över perimeternätverket för organisationens användare på platsen visas med några av eller alla följande element:

- **Plats för** Office – platsen för det kontor du tittar på
- **Nätverks perimeter** – Platsen för käll-IP-adressen för anslutningar från kontorsplatsen. Det beror på noggrannheten i geo-IP-platsdatabaser
- **Exchange optimal service front dörr** - En av de rekommenderade Exchange-tjänste front dörrar som användare på den här kontorsplatsen ska ansluta till
- **Exchange sub-optimal front door** - En Exchange-tjänst front dörr som användarna är anslutna till, men rekommenderas inte
- **Optimal serviceport i SharePoint** – En av de rekommenderade Dörrar till SharePoint-tjänsten som användare på den här kontorsplatsen ska ansluta till
- **Deloptimal tjänst i SharePoint –** en dörr mellan SharePoint-tjänsten och som användarna är anslutna till, men rekommenderas inte
- **DNS-rekursiv resolverserver** – Platsen från en geo IP-databas hos den identifierade DNS-rekursiva resolveren som används för Exchange Online (om tillgänglig)
- **Din proxyserver** – Platsen från en geo IP-databas för den identifierade proxyservern (om tillgänglig) 

På sidan För kontorsplatser visas dessutom platsens nätverksutvärdering, nätverksutvärderingshistorik, en jämförelse av den här platsens utvärdering med andra kunder i samma stad och en lista med specifika insikter och rekommendationer som du kan utföra för att förbättra nätverksprestanda och tillförlitlighet.

Jämförelser mellan kunder i samma stad baseras på förväntningarna att alla kunder har samma tillgång till nätverkstjänstleverantörer, telekommunikationsinfrastruktur och närliggande Microsoft-nätverkspunkter för närvaro.

På fliken Information på kontorets platssida visas de specifika måttresultat som användes för att få med insikter, rekommendationer och nätverksutvärderingen. Detta tillhandahålls så att nätverkstekniker kan validera rekommendationerna och faktorn för alla begränsningar eller specifika frågor i miljön.

> [!div class="mx-imgBorder"]
> ![Platsspecifik information](../media/m365-mac-perf/m365-mac-perf-locations-plan-details-all.png)

## <a name="csv-import-for-lan-subnet-office-locations"></a>CSV-import för LAN-undernätsplatser

För LAN-undernäts-office-ID måste du lägga till varje plats i förväg. I stället för att lägga till enskilda kontorsplatser **på fliken Platser** kan du importera dem från en CSV-fil. Du kan eventuellt hämta dessa data från andra platser som du har lagrat den, till exempel instrumentpanelen för samtalskvalitet eller Active Directory-webbplatser och -tjänster

I CSV-filen visas en upptäckt ortplats som tom i kolumnen användareAnvändarkolumnen och en manuellt tillagd kontorsplats visas som 1.

1. Klicka på fliken Platser i huvudfönstret Anslutning  till _Microsoft 365._

1. Klicka **på** knappen Importera precis ovanför platslistan. Den **utfäll plats för** Importera kontor visas.

   > [!div class="mx-imgBorder"]
   > ![CSV-importmeddelande](../media/m365-mac-perf/m365-mac-perf-import.png)

1. Klicka på **länken Hämta aktuella kontorsplatser (.csv)** för att exportera den aktuella platslistan till en CSV-fil och spara den på den lokala hårddisken. Det ger dig en korrekt formaterad CSV-fil med kolumnrubriker som du kan lägga till platser i. Du kan lämna de befintliga exporterade platserna som de är. De dupliceras inte när du importerar den uppdaterade CSV-filen. Om du vill ändra adressen till en befintlig plats uppdateras den när du importerar CSV-filen. Du kan inte ändra adressen till en upptäckt stad.

1. Öppna CSV-filen och lägg till dina platser genom att fylla i följande fält på en ny rad för varje plats du vill lägga till. Lämna alla andra fält tomma. värden som du anger i andra fält ignoreras.

   1. **userEntered** (obligatoriskt): Måste vara 1 för en ny LAN-undernätsplats för kontor
   1. **Adress** (obligatoriskt): Kontorets fysiska adress
   1. **Latitud** (valfritt): Ifylld från Bing-kartor uppslag av adressen om den är tom
   1. **Longitud** (valfritt): Ifylld från Bing-kartor uppslag av adressen om den är tom
   1. **EGRESS IP Address ranges 1-5** (optional): For each range, enter the circuit name followed by a space separated list of valid IPv4 or IPv6 CIDR addresses. Dessa värden används för att särskilja flera kontorsplatser där du använder samma LAN-undernäts-IP-adresser. IP-adressintervall för utgående adresser måste alla vara /24 nätverk och /24 tas inte med i indata.
   1. **LanIps** (obligatoriskt): Lista de LAN-undernätsintervall som används på den här kontorsplatsen. LAN-undernäts-ID måste ha en CIDR-nätverksstorlek där nätverksstorleken kan vara mellan /8 och /29. Flera LAN-undernätsområden kan avgränsas med komma eller semikolon.
   
1. När du har lagt till dina kontorsplatser  och sparat filen  klickar du på knappen Bläddra bredvid fältet Ladda upp slutförda och väljer den sparade CSV-filen.

1. Filen verifieras automatiskt. Om det finns verifieringsfel visas felmeddelandet _Det finns några fel i importfilen. Granska felen, korrigera importfilen och försök sedan igen._ Klicka på länken **Öppna felinformation för** en lista med specifika fältverifieringsfel.

   > [!div class="mx-imgBorder"]
   > ![Csv-importfelmeddelande](../media/m365-mac-perf/m365-mac-perf-import-error.png)

1. Om det inte finns några fel i filen visas meddelandet Rapporten _är klar. Hittade x platser att lägga till och x platser att uppdatera._ Ladda upp **CSV-filen** genom att klicka på knappen Importera.

   > [!div class="mx-imgBorder"]
   > ![CSV-importklara meddelanden](../media/m365-mac-perf/m365-mac-perf-import-ready.png)

## <a name="faq"></a>Vanliga frågor och svar

### <a name="what-is-a-microsoft-365-service-front-door"></a>Vad är en Microsoft 365-tjänst hos alla?

Microsoft 365-tjänstens klient är en startpunkt i Microsofts globala nätverk där Office-klienter och -tjänster avslutar nätverksanslutningen. För en optimal nätverksanslutning till Microsoft 365 rekommenderar vi att din nätverksanslutning avslutas till den närmaste Microsoft 365-fronten.

>[!NOTE]
>Microsoft 365-tjänsterna hos fronten har inga direkta relationer med Azure Front Door Service-produkten som finns tillgänglig på Azure-marknadsplatsen.

### <a name="what-is-an-optimal-microsoft-365-service-front-door"></a>Vad är en optimal Microsoft 365 tjänst front dörr?

En optimal Microsoft 365 tjänst front dörr är den som är närmast din nätverks utgång, oftast i din stad eller metro område. Använd [Microsoft 365-anslutningstestverktyget (förhandsversion)](office-365-network-mac-perf-onboarding-tool.md) för att avgöra var den Microsoft 365-tjänst som används är nära och optimal service så att den finns nära tillhands. Om verktyget avgör att den lokala dörren används optimalt ska du ha optimal anslutning till Microsofts globala nätverk.

### <a name="what-is-an-internet-egress-location"></a>Vad är en utgående Internetplats?

Den utgående internetplatsen är den plats där din nätverkstrafik går ut ur företagsnätverket och ansluter till Internet. Det här identifieras också som den plats där du har en NAT-enhet (Network Address Translation) och vanligtvis är det där du ansluter med en Internetleverantör (ISP). Om du ser ett långt avstånd mellan din plats och din utgående Internetplats kan detta indikera ett betydande WAN-backhaul.

## <a name="related-topics"></a>Relaterade ämnen

[Microsoft 365-nätverksinsikter (förhandsversion)](office-365-network-mac-perf-insights.md)

[Microsoft 365-nätverksutvärdering (förhandsversion)](office-365-network-mac-perf-score.md)

[Microsoft 365 anslutningstestverktyg (förhandsversion)](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 Network Connectivity Location Services (förhandsversion)](office-365-network-mac-location-services.md)