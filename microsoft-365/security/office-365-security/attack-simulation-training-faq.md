---
title: Distributionsöverväganden och vanliga frågor och svar för attacksimulatorträning
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa mer om distributionsöverväganden och vanliga frågor om attack simulering och utbildning i Microsoft 365 E5 eller Microsoft Defender för Office 365 abonnemang 2 organisationer.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f404e2a47756a611135fc70026bf0cce3eec62c4
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207054"
---
# <a name="attack-simulation-training-deployment-considerations-and-faq"></a>Distributionsöverväganden och vanliga frågor och svar för attacksimulatorträning

Utbildning av attack simulering är nu [allmänt tillgänglig.](https://techcommunity.microsoft.com/t5/microsoft-security-and/attack-simulation-training-in-microsoft-defender-for-office-365/ba-p/2037291) Utbildning av attackbedrägerier innebär att Microsoft 365 E5 eller Microsoft Defender för Office 365 plan 2-organisationer kan mäta och hantera social engineering-risker genom att tillåta skapande och hantering av nätfiskebedrägerier som drivs av verkliga, avkodade nätfiske payloads. Hyper riktad utbildning, levererad i samarbete medNova-säkerhet, hjälper till att förbättra kunskaper och ändra beteende för anställda.

Mer information om hur du kommer igång med simulering av attack finns i [Komma igång med att använda simulering av attack](attack-simulation-training-get-started.md).

Hela simuleringen har utformats för att vara fri flöden och friktioner, men det krävs ofta planering för att köra simuleringar på ett företagsnivå. Den här artikeln hjälper till att hantera specifika utmaningar som vi ser när våra kunder kör simuleringar i sina egna miljöer.

## <a name="issues-with-end-user-experiences"></a>Problem med slutanvändarupplevelser

### <a name="phishing-simulation-urls-blocked-by-google-safe-browsing"></a>Url-adresser för nätfiskebedrägerier som blockerats av Google Valv Surfning

Ett rykte för URL-adresser kan identifiera en eller flera URL:er som används av utbildning av attack simulering som osäker. Med Google Valv i Google Chrome blockeras några av de simulerade nätfiske-URL:erna med ett **Deceptive-meddelande i** förväg. Medan vi arbetar med många URL-ryktesleverantörer för att alltid tillåta vår simulerings URL:er, har vi inte alltid fullständig täckning.

![Varning om missfallande webbplats i förväg i Google Chrome](../../media/attack-sim-chrome-deceptive-site-message.png)

Observera att det här problemet inte påverkar Microsoft Edge.

Som en del av planeringsfasen kontrollerar du om URL:en är tillgänglig i de webbläsare som stöds innan du använder URL:en i en nätfiskekampanj. Om URL:erna blockeras av Google [](https://support.google.com/chrome/a/answer/7532419) Valv surfning följer du dessa anvisningar från Google för att tillåta åtkomst till URL:er.

Se Komma [igång med att använda simulering av](attack-simulation-training-get-started.md) attack för listan över URL:er som för närvarande används av simulering av attack.

### <a name="phishing-simulation-and-admin-urls-blocked-by-network-proxy-solutions-and-filter-drivers"></a>Nätfiskebedrägerier och url-adresser för administratörer blockerade av proxylösningar för nätverk och filterdrivrutiner

Både nätfiskebedrägeri-URL:er och administratörs-URL:er kan blockeras eller ignoreras av dina mellanliggande säkerhetsenheter eller filter. Till exempel:

- Brandväggar
- WAF-lösningar (Web Application Firewall)
- Tredjepartsfilterdrivrutiner (till exempel kernellägesfilter)

Även om det är få kunder som blockeras på det här lagret så händer det. Om du stöter på problem kan du konfigurera följande URL:er för att kringgå genomsökning genom dina säkerhetsenheter eller filter efter behov:

- De simulerade url-adresser för nätfiske enligt beskrivningen i Komma igång med [att använda utbildning av attackbedrägerier](attack-simulation-training-get-started.md).
- <https://security.microsoft.com/attacksimulator>
- <https://security.microsoft.com/attacksimulationreport>
- <https://security.microsoft.com/trainingassignments>

### <a name="simulation-messages-not-delivered-to-all-targeted-users"></a>Simuleringsmeddelanden levereras inte till alla riktade användare

Det är möjligt att antalet användare som faktiskt tar emot simuleringsmeddelanden är mindre än antalet användare som skickades av simuleringen. Följande typer av användare utesluts som en del av målverifieringen:

- Ogiltiga mottagares e-postadresser.
- Gästanvändare.
- Användare som inte längre är aktiva i Azure Active Directory (Azure AD).

Endast giltiga användare som inte är gästanvändare med en giltig postlåda inkluderas i simuleringar. Om du använder distributionsgrupper eller e-postaktiverade säkerhetsgrupper för att rikta användare kan du använda cmdlet:en [Get-DistributionGroupMember](/powershell/module/exchange/get-distributiongroupmember) [i Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) för att visa och validera medlemmar i distributionsgrupper.

## <a name="issues-with-attack-simulation-training-reporting"></a>Problem med utbildningsrapportering om attackspel

### <a name="attack-simulation-training-reports-do-not-contain-any-activity-details"></a>Utbildningsrapporter om attack simulering innehåller inte någon aktivitetsinformation

Utbildning av attack simulering kommer med omfattande, handlingsbara insikter som håller dig informerad om hotberedskapsförloppet för dina anställda. Om utbildningsrapporter om attack simulering inte innehåller data kontrollerar du att granskningsloggsökning är aktiverat i din organisation (det är aktiverat som standard).

Granskningsloggsökning krävs av utbildning för attack simulering så att händelser kan registreras, registreras och läsas tillbaka. Att stänga av granskningsloggsökning får följande konsekvenser för utbildning av attack simulering:

- Rapporteringsdata är inte tillgängliga i alla rapporter. Rapporterna visas som tomma.
- Utbildningsuppgifter blockeras eftersom data inte är tillgängliga.

Information om hur du aktiverar granskningsloggsökning finns [i Aktivera eller inaktivera granskningsloggsökning.](../../compliance/turn-audit-log-search-on-or-off.md)

> [!NOTE]
> Information om tom aktivitet kan också orsakas av att inga E5-licenser har tilldelats till användare. Kontrollera att minst en E5-licens är tilldelad till en aktiv användare för att säkerställa att rapporteringshändelser registreras och spelas in.

### <a name="simulation-reports-are-not-updated-immediately"></a>Simuleringsrapporter uppdateras inte omedelbart

Detaljerade simuleringsrapporter uppdateras inte direkt efter att du har lanserat en kampanj. Oroa dig inte. det här beteendet är normalt.

Varje simuleringskampanj har en livscykel. När simuleringen först skapades är den **schemalagda** statusen. När simuleringen startar går den över till läget **Pågår.** När simuleringen är klar går övergången till **läget Slutförd.**

Även om en simulering är i **schemalagd** status är simuleringsrapporterna mest tomma. I det här steget löser simuleringsmotorn målanvändares e-postadresser, expanderar distributionsgrupper, tar bort gästanvändare från listan osv.:

![Rapportering i läget Schemalagt](../../media/attack-sim-empty-reporting.png)

När simuleringen kommer **in i steget Pågår** märker du att information börjar förledas i rapporteringen:

![Rapportering i statusen Pågår](../../media/attack-sim-in-progress.png)

Det kan ta upp till 30 minuter innan de enskilda simuleringsrapporterna uppdateras efter övergången till läget **Pågår.** Rapportdata fortsätter att byggas tills simuleringen når **tillståndet Slutförd.** Rapporteringsuppdateringarna sker med följande intervall:

- Var 10:e minut under de första 60 minuterna.
- Var 15:e minut efter 60 minuter till två dagar.
- Var 30:e minut efter två dagar till sju dagar.
- Var 60:e minut efter sju dagar.

Widgetar på **sidan Översikt** ger en snabb ögonblicksbild av din organisations simuleringsbaserade säkerhetsstatus med tiden. Eftersom dessa widgetar återspeglar din övergripande säkerhet och resa över tid uppdateras de efter att varje simuleringskampanj har slutförts.

> [!NOTE]
> Du kan använda alternativet **Exportera** på olika rapportsidor för att extrahera data.

### <a name="messages-reported-as-phishing-by-users-arent-appearing-in-simulation-reports"></a>Meddelanden som rapporterats som nätfiske av användare visas inte i simuleringsrapporter

Simuleringsrapporter i attackutbildning ger information om användaraktivitet. Till exempel:

- Användare som klickade på länken i meddelandet.
- Användare som har gett upp sina autentiseringsuppgifter.
- Användare som har rapporterat meddelandet som nätfiske.

Om meddelanden som användare rapporterat som nätfiske inte har fångats i simuleringsrapporter om attackattacker kan det finnas en Exchange-e-postflödesregel (kallas även transportregel) som blockerar leveransen av de rapporterade meddelandena till Microsoft. Kontrollera att e-postflödesregler inte blockerar leverans till följande e-postadresser:

- junk@office365.microsoft.com
- abuse@messaging.microsoft.com
- phish@office365.microsoft.com
- inte \_ junk@office365.microsoft.com

## <a name="other-frequently-asked-questions"></a>Andra vanliga frågor och svar

### <a name="q-what-is-the-recommended-method-to-target-users-for-simulation-campaigns"></a>F: Vilken är den rekommenderade metoden för att rikta användare till simuleringskampanjer?

S: Flera alternativ är tillgängliga för målanvändare:

- Inkludera alla användare (för närvarande tillgängligt för organisationer med mindre än 40 000 användare).
- Välj specifika användare.
- Välj användare från en CSV-fil.
- Gruppbaserad azure AD-målanpassning.

Vi har upptäckt att kampanjer där de riktade användarna identifieras av Azure AD-grupper i allmänhet är enklare att hantera.

### <a name="q-are-there-any-limits-in-targeting-users-while-importing-from-a-csv-or-adding-users"></a>F: Finns det några begränsningar för att rikta användare när du importerar från en CSV-fil eller lägger till användare?

S: Gränsen för att importera mottagare från en CSV-fil eller lägga till enskilda mottagare i en simulering är 40 000.

En mottagare kan vara en enskild användare eller grupp. En grupp kan innehålla hundratals eller tusentals mottagare, så det finns ingen faktisk begränsning för antalet enskilda användare.

Det kan vara krångligt att hantera en stor CSV-fil eller lägga till många enskilda mottagare. Med hjälp av Azure AD-grupper förenklas den övergripande hanteringen av simuleringen.

### <a name="q-does-microsoft-provide-payloads-in-other-languages"></a>F: Tillhandahåller Microsoft nyttolaster på andra språk?

S: För närvarande finns det fem lokaliserade nyttolaster tillgängliga. Vi har lagt märke till att eventuella direktöversättningar och maskinöversättningar av befintliga nyttolaster till andra språk leder till felaktigheter och minskad relevans.

Med det sagt kan du skapa en egen nyttolast på det språk du väljer med den anpassade nyttolastförfattaren. Vi rekommenderar även starkt att du inlärer befintliga nyttolaster som har använts för att rikta användare till en viss geografi. Med andra ord, låt attackerarna lokalisera innehållet åt dig.

### <a name="q-how-can-i-switch-to-other-languages-for-my-admin-portal-and-training-experience"></a>F: Hur byter jag till andra språk för administrationsportalen och utbildningsupplevelsen?

S: Microsoft 365 eller Office 365 är språkkonfigurationen specifik och centraliserad för varje användarkonto. Anvisningar om hur du ändrar språkinställningen finns i [Ändra visningsspråk och tidszon i Microsoft 365 för företag.](https://support.microsoft.com/office/6f238bff-5252-441e-b32b-655d5d85d15b)

Observera att konfigurationsändringen kan ta upp till 30 minuter att synkronisera i alla tjänster.

### <a name="q-can-i-trigger-a-test-simulation-to-understand-what-it-looks-like-prior-to-launching-a-full-fledged-campaign"></a>F: Kan jag utlösa en test simulering för att förstå hur den ser ut innan jag startar en fullfjädrad kampanj?

S: Ja, det kan du! På den sista **granska simuleringssidan** i guiden för att skapa en ny simulering finns det ett alternativ för att **Skicka ett test**. Det här alternativet skickar ett exempel på simuleringsmeddelande om nätfiske till den inloggade användaren. När du har validerat nätfiskemeddelandet i inkorgen kan du skicka simuleringen.

![Knappen Skicka ett test på simuleringssidan Granska](../../media/attack-sim-review-simulation-page.png)

### <a name="q-can-i-target-users-that-belong-to-a-different-tenant-as-part-of-the-same-simulation-campaign"></a>F: Kan jag rikta användare som tillhör en annan klientorganisation som en del av samma simuleringskampanj?

S: nej. Simuleringar mellan klientorganisationen stöds för närvarande inte. Kontrollera att alla dina riktade användare finns i samma klientorganisation. Alla användare med flera klientorganisationsanvändare eller gästanvändare undantas från simuleringskampanjen.

### <a name="q-how-does-region-aware-delivery-work"></a>F: Hur fungerar leverans med regioner?

S: Regionmedveten leverans använder attributet TimeZone för den riktade användarens postlåda och logik för att avgöra när meddelandet ska levereras. Tänk dig följande scenario:

- Klockan 07:00 i Stilla havets tidszon (UTC-8) skapar och schemalägger en kampanj så att den börjar kl. 09:00 samma dag.
- UserA är i eastern tidszon (UTC-5).
- AnvändareB är också i Stilla havet.

Klockan 09:00 samma dag skickas simuleringsmeddelandet till AnvändareB. Med leverans med regionmedveten leverans skickas inte meddelandet till AnvändareA samma dag, eftersom 09:00 Stilla havet är 12:00 EASTERN-tid. I stället skickas meddelandet till UserA kl. 09:00 Eastern time följande dag.

Så när en kampanj körts med områdesmedveten leverans aktiverad kan det därför visas att simuleringsmeddelandet endast skickades till användare i en viss tidszon. Men allt eftersom tiden går och fler användare kommer in i omfattningen kommer de riktade användarna att öka.