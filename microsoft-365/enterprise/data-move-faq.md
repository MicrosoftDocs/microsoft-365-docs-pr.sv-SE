---
title: Vanliga frågor och svar om dataflytt
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 1f01bc6f-5d37-4d14-bdd3-9d94a1e23e14
f1.keywords:
- NOCSH
description: Hitta svar på vanliga frågor och svar om att flytta basdata till ett nytt geodatadatacenter i Office 365.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a7e59622e35604ebd9befbbe17a8a125ed15e101
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094661"
---
# <a name="data-move-general-faq"></a>Vanliga frågor och svar om dataflytt

Här finns svar på allmänna frågor om att flytta grundläggande kunddata i vila till ett nytt datacenter.
  
## <a name="what-customers-are-eligible-to-request-a-move"></a>Vilka kunder är berättigade att begära en flytt?
  
Befintliga Microsoft 365-kommersiella kunder som valde ett land som är berättigat till det nya datacentret geo kommer att kunna begära en flytt. Programmet finns bara för klienter med en behörig landkod tilldelad Till Microsoft 365-klientorganisationen för att migrera grundläggande kunddata i vila för berättigade arbetsbelastningar till motsvarande geodata i Microsoft 365-datacentret. Mer information finns på sidan [Hur du begär att data flyttas för](request-your-data-move.md) att bekräfta berättigande till land.   

## <a name="how-do-we-define-core-customer-data"></a>Hur definierar vi basdata för kunddata?
 
Baskunddata är en term som refererar till en delmängd av kunddata som definierats i villkoren för [Microsoft Online-tjänster:](https://aka.ms/ost) 
- Postlådeinnehåll i Exchange Online (e-posttext, kalenderposter och innehållet i e-postbilagor)
- SharePoint Online-webbplatsinnehåll och de filer som lagrats på webbplatsen
- Filer som laddats upp till OneDrive för företag 

## <a name="what-is-in-scope-for-teams-migration"></a>Vad finns i omfattning för Teams-migrering?

Utöver Exchange Online, SharePoint Online och OneDrive för företag: Microsoft migrerar Teams-data till det lokala datacentret. 
- Chattmeddelanden i Teams, inklusive privata meddelanden och kanalmeddelanden. 
- Teams-bilder som används i chattar. 

Teams-filer lagras i SharePoint Online och chattfiler i Teams lagras i OneDrive för företag. Röstmeddelanden, kalender och kontakter lagras i Exchange Online. I många fall används Exchange Online, SharePoint Online och OneDrive för företag redan av kunden i det lokala datacentrets geoområde och är även en del av Microsoft 365-migreringsprogrammet för berättigade kundländer.

## <a name="at-what-point-is-my-migration-complete-so-that-my-tenants-core-customer-data-is-being-stored-at-rest-in-my-new-geo"></a>Vid vilken tidpunkt är min migrering klar så att klientorganisationens baskunddata lagras i vila i min nya geo?

På grund av delade beroenden mellan Exchange Online och SharePoint Online/OneDrive för företag kan en migrering inte anses slutförd förrän båda tjänsterna har migrerats. Exchange Online och SharePoint Online/OneDrive för företag migreras ofta separat och oberoende av varandra. Kundens innehavaradministratörer får en bekräftelse i Meddelandecenter när varje tjänstmigrering är slutförd och kan när som helst visa dataplatskortet i administrationscentret för att bekräfta basdata för kunddata på en vilsplats för varje tjänst.

## <a name="how-do-you-make-sure-my-customer-data-is-safe-during-the-move-and-that-i-wont-experience-downtime"></a>Hur ser du till att mina kunddata är säkra under flytten och att det inte blir några avbrott?
  
Dataflyttningar är en tjänståtgärd i backend med minimal påverkan för slutanvändarna. Funktioner som kan påverkas visas i Under [och efter dataflyttningen.](during-and-after-your-data-move.md) Vi följer Microsofts servicenivåavtal för onlinetjänster [(SLA)](https://go.microsoft.com/fwlink/p/?LinkId=523897) för tillgänglighet så det finns ingenting som kunderna behöver förbereda sig för eller övervaka under flytten. 
  
Alla Microsoft 365-tjänster kör samma versioner i datacenter så att du kan vara säker på enhetliga funktioner. Under hela processen stöds helt och hållet din tjänst.
  
## <a name="what-is-the-impact-of-having-different-services-located-in-different-geos"></a>Hur påverkar det att olika tjänster finns i olika geos?

Vissa Av Microsoft 365-tjänsterna kan finnas i olika geos för vissa befintliga kunder och för kunder som befinner sig mitt i flyttprocessen. Våra tjänster körs oberoende av varandra och det påverkar inte användarupplevelsen om så är fallet. Men i syfte att lagra data kan en klientmigrering inte ses som fullständig förrän både Exchange Online och SharePoint Online/OneDrive för företag migreras till samma datacenter geo.

 ## <a name="where-is-my-core-customer-data-located"></a>Var finns mina kärnkunddata?

Kundens innehavaradministratörer kan visa kortet med dataplats i administrationscentret när som helst för att bekräfta baskunddata på en vilsplats för varje tjänst, speciellt för klientorganisationen.  Vi publicerar även platsen för datacenter geos, datacenter och plats för Office 365-kunddata på de interaktiva [Microsoft 365-datacenterkartorna ](https://office.com/datamaps) som en referens för aktuella standarddata för baskunddata på vilplatser för nya klientorganisationar. Du kan verifiera platsen för dina kunddata vil via avsnittet Dataplats under din organisationsprofil i administrationscentret för Microsoft 365.  
 
## <a name="when-will-i-be-able-to-request-a-move"></a>När kommer jag att kunna begära en flytt?
  
Mer information finns på [sidan För att begära dataflyttning](request-your-data-move.md) för tidsperioder som stöds för ditt datacenter.
  
## <a name="how-can-i-request-to-be-moved"></a>Hur begär jag att få bli flyttad?
  
Berättigade kunder ser en sida i administrationscentret för [Microsoft 365.](https://admin.microsoft.com/) Se hur [du begär dataflyttning för anvisningar](request-your-data-move.md) om hur du begär en flytt. 
  
## <a name="can-i-change-my-selection-after-requesting-a-move"></a>Kan jag ändra mitt val när jag begär en flytt?
  
Vi kan inte ta bort dig från processen efter att du skickat in din begäran.
  
## <a name="what-happens-if-i-do-not-request-a-move-before-the-deadline"></a>Vad händer om jag inte begär en flytt före deadline?
  
Vi kan inte acceptera förfrågningar om migrering efter den öppna registreringsperioden.

## <a name="what-if-i-want-to-move-my-data-in-order-to-get-better-network-performance"></a>Vad gör jag om jag vill flytta mina data för att få bättre nätverksprestanda?
  
Fysisk närhet till ett Microsoft 365-datacenter är ingen garanti för bättre nätverksprestanda. Det finns många faktorer och komponenter som påverkar nätverkets prestanda mellan slutanvändaren och Microsoft 365-tjänsten. Mer information om detta och prestandajustering finns i [Nätverksplanering och prestandajustering för Microsoft 365.](network-planning-and-performance.md)
  
 ## <a name="do-all-the-services-move-their-data-on-the-same-day"></a>Flyttar alla tjänster sina data samma dag?
 
Varje tjänst flyttas oberoende och flyttar sannolikt sina data vid olika tidpunkter.
  
 ## <a name="can-i-choose-when-i-want-my-data-to-be-moved"></a>Kan jag välja när mina data ska flyttas?
 
Kunder kan inte välja ett visst datum, de kan inte fördröja flytten och vi kan inte dela ett visst datum eller en viss tidsperiod för flytten.
  
 ## <a name="can-you-share-when-my-data-will-be-moved"></a>Går det att dela när mina data ska flyttas?
  
Dataflyttningar är en backend-åtgärd med minimal påverkan för slutanvändarna. Den komplexitet, precision och skala som vi behöver för att utföra dataflyttningar i en globalt drivs och automatiserad miljö hindrar oss från att dela när en dataflyttning förväntas slutföras för klientorganisationen eller någon annan enskild klientorganisation. Kunderna får en bekräftelse i Meddelandecenter per deltagande tjänst när dataflyttningen har slutförts. 
  
 ## <a name="what-happens-if-users-access-services-while-the-data-is-being-moved"></a>Vad händer om användare använder tjänster medan data flyttas?

Se [Under och efter dataflyttningen](during-and-after-your-data-move.md) för en fullständig lista över funktioner som kan vara begränsade under vissa delar av dataflyttningen för varje tjänst. 
  
 ## <a name="how-do-i-know-the-move-is-complete"></a>Hur vet jag att flyttningen är slutförd?
  
I Meddelandecenter för Microsoft 365 får du en bekräftelse på att alla tjänstdata har flyttats. När varje tjänsts data flyttas publicerar vi ett kompletteringsmeddelande så att du får tre kompletteringsmeddelanden: en för Exchange Online, SharePoint Online och Skype för företag – Online. Du kan också verifiera platsen för dina kunddata vil via avsnittet Dataplats under din organisationsprofil i administrationscentret för Microsoft 365.  
  
## <a name="i-am-a-microsoft-365-customer-in-one-of-the-new-datacenter-geos-but-when-i-signed-up-i-selected-a-different-country-how-can-i-be-moved-to-the-new-datacenter-geo"></a>Jag är Microsoft 365-kund i något av de nya geodatadatacentret, men när jag registrerade mig valde jag ett annat land. Hur kan jag flyttas till det nya datacentrets geodata?

Det går inte att ändra det registreringland som är kopplat till din klientorganisation. I stället måste du skapa en ny Microsoft 365-klientorganisation med en ny prenumeration och manuellt flytta dina användare och data till den nya klientorganisationen.
  
## <a name="what-happens-if-we-are-in-process-of-email-data-migration-to-microsoft-365-during-the-exchange-online-move"></a>Vad händer om vi håller på att migrera e-postdata till Microsoft 365 under flytten av Exchange Online?

Det här är ett mycket vanligt scenario och stöds fullt ut.  Molnmigrering mellan geodatadatadata påverkar inte några migreringar av postlådor lokalt till molnet.
  
 ## <a name="can-i-pilot-some-users"></a>Kan jag pilottesta vissa användare?
  
Du kan skapa en separat utvärderingsklientorganisation för att testa anslutning, men utvärderingsklientorganisationen kan inte kombineras på något sätt med din befintliga klientorganisation.

## <a name="i-dont-want-to-wait-for-microsoft-to-move-my-data-can-i-just-create-a-new-tenant-and-move-myself"></a>Jag vill inte vänta på att Microsoft flyttar mina data. Kan jag bara skapa en ny klientorganisation och flytta på mig själv?
  
Ja, men processen blir inte lika smidig som om Microsoft utför dataflyttningen.
  
Om du skapar en ny klientorganisation efter att det nya datacentret är tillgängligt ligger den nya klientorganisationen på den nya geoklienten. Den nya klientorganisationen är helt separat från den tidigare klientorganisationen och du skulle ansvara för att flytta alla användarpostlådor, webbplatsinnehåll, domännamn och andra data. Observera att du inte kan flytta klientnamnet från en klientorganisation till en annan. Vi rekommenderar att du väntar på flyttprogrammet som tillhandahålls av Microsoft eftersom vi tar hand om flytten av alla inställningar, data och prenumerationer för användarna.
  
## <a name="my-customer-data-has-already-been-moved-to-a-new-datacenter-geo-can-i-move-back"></a>Mina kunddata har redan flyttats till ett nytt datacenter. Kan jag flytta tillbaka?
 
Nej, det går inte. Kunder som har flyttats till nya geodatacenter kan inte flyttas tillbaka. Som kund i en geo miljö får du samma kvalitet på tjänster, prestanda och säkerhetskontroller som du gjorde tidigare. [Microsoft 365 Multi Geo](https://aka.ms/multi-geo) är tillgängligt för vissa kunder som ett tillägg och gör att en enda klientorganisation kan skapa flera satellitgeoter och flytta användardata till dessa geos med data som lagras tillsammans med uppgifterna.
  
## <a name="will-microsoft-365-tenants-hosted-in-the-new-datacenters-be-available-to-users-outside-of-the-country"></a>Blir Microsoft 365-klientorganisation i de nya datacenteren tillgänglig för användare utanför landet?
  
Ja. Microsoft har ett stort globalt nätverk med offentliga Internetanslutningar på fler än 130 platser i 35 länder runt om i världen med peeringavtal med fler än 2 700 Internetleverantörer (ISP). Användare kommer att kunna komma åt datacenter från var de än är på Internet.

## <a name="my-tenant-has-configured-the-multi-geo-add-on-can-i-still-enroll-in-my-tenant-in-the-microsoft-365-move-program-to-change-my-default-geo-and-move-any-user-not-in-a-satellite-region-to-the-new-default-geo"></a>Min klientorganisation har konfigurerat [multi geo-tillägget.](https://aka.ms/multi-geo) Kan jag fortfarande registrera mig i min klientorganisation i Microsoft 365 Move Program för att ändra min standardgeo och flytta en användare som inte finns i en satellitområde till den nya standard geo?

Ja, klientorganisationen är berättigad att registrera, men det finns viktiga överväganden eftersom flytt på klientnivå inte stöds fullt ut för kunder som har konfigurerat Multi-Geo.

SharePoint Online och OneDrive för företag kan inte migrera till det nya datacentret geo på innehavarnivå genom det här programmet. Customer Administrator can configure OneDrive for Business shares to move to any available region using Multi-Geo, but the default location for the tenant cannot be changed once Multi-Geo has been configured for a tenant.

För kunder som väljer att migrera – vi flyttar alla Exchange Online-postlådor från din nuvarande standardgeo till ditt nya lokala datacenter geo och uppdaterar standardregion för Exchange Online. Vi flyttar inga EXO-postlådor som konfigurerats i flera geo satellitområden för att fortsätta respektera satellitområdesdata som du har tänkt dig. 

## <a name="related-topics"></a>Relaterade ämnen

[Flytta basdata till nya Microsoft 365-datacentergeo](moving-data-to-new-datacenter-geos.md)

[Hur du begär din dataflytt](request-your-data-move.md)

[Microsoft 365 Multi Geo](https://aka.ms/multi-geo)

[Microsoft 365-interaktiv datacenterkarta](https://office.com/datamaps)

[Microsoft 365 Support](https://go.microsoft.com/fwlink/p/?LinkID=522459)

[Nya datacenter geos för Microsoft Dynamics CRM Online](https://go.microsoft.com/fwlink/p/?Linkid=615924)
  
[Azure-tjänster per region](https://azure.microsoft.com/regions/)
