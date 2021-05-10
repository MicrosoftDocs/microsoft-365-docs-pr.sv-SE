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
description: Hitta svar på vanliga frågor (vanliga frågor och svar) om att flytta kärndata till ett nytt Office 365 geodatadata.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 46dfdddc50c62970b679a130b3cccf692648cd5c
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52298058"
---
# <a name="data-move-general-faq"></a>Vanliga frågor och svar om dataflytt

Här finns svar på allmänna frågor om att flytta grundläggande kunddata i vila till ett nytt datacenter geo.
  
## <a name="what-customers-are-eligible-to-request-a-move"></a>Vilka kunder är berättigade att begära en flytt?
  
Befintliga Microsoft 365 kommersiella kunder som valde ett land som är berättigat till det nya datacentret geo kommer att kunna begära en flytt. Programmet finns bara för klientorganisationen med en behörig landskod tilldelad till Microsoft 365-klientorganisationen för att migrera grundläggande kunddata i vila för kvalificerade arbetsbelastningar till motsvarande geodatadata Microsoft 365 datacenter. Mer information om hur [du begär dataflyttning finns på](request-your-data-move.md) sidan Så här begär du att få veta om landet är berättigande.   

## <a name="how-do-we-define-core-customer-data"></a>Hur definierar vi basdata?
 
Baskunddata är en term som refererar till en delmängd av kunddata som definierats i villkoren för [Microsoft Online Services:](https://aka.ms/ost) 
- Exchange Online innehållet i postlådan (brödtext, kalenderposter och innehållet i e-postbilagor)
- SharePoint Onlinewebbplatsinnehåll och filer som lagrats på webbplatsen
- Filer som laddats upp till OneDrive för företag 

## <a name="what-is-in-scope-for-teams-migration"></a>Vad är i omfattning för Teams migrering?

Förutom att Exchange Online kan SharePoint Online och OneDrive för företag; Microsoft migrerar Teams data till det lokala datacentret. 
- Teams chattmeddelanden, inklusive privata meddelanden och kanalmeddelanden. 
- Teams bilder som används i chattar. 

Teams lagras på SharePoint Online och Teams lagras i OneDrive för företag. Röstmeddelanden, kalender och kontakter lagras i Exchange Online. I många fall används Exchange Online, SharePoint Online och OneDrive för företag redan av kunden i det lokala datacentret geo och är även en del av migreringsprogrammet för Microsoft 365 för berättigade kundländer.

## <a name="at-what-point-is-my-migration-complete-so-that-my-tenants-core-customer-data-is-being-stored-at-rest-in-my-new-geo"></a>Vid vilken tidpunkt är migreringen klar så att klientorganisationens basdata lagras i vila i min nya geo?

På grund av delade beroenden mellan Exchange Online och SharePoint Online/OneDrive för företag kan inte en migrering anses vara slutförd förrän båda tjänsterna har migrerats. Exchange Online och SharePoint online/OneDrive för företag ofta migreras vid separata tidpunkter och oberoende av varandra. Kundens innehavaradministratörer får en bekräftelse i meddelandecentret när varje tjänstmigrering har slutförts och kan visa dataplatskortet i administrationscentret när som helst för att bekräfta basdata på en vilsplats för varje tjänst.

## <a name="how-do-you-make-sure-my-customer-data-is-safe-during-the-move-and-that-i-wont-experience-downtime"></a>Hur ser du till att mina kunddata är säkra under flytten och att jag inte drabbas av driftstopp?
  
Dataflyttningar är en tjänsteåtgärd i backend med minimal inverkan för slutanvändarna. Funktioner som kan påverkas visas i Under [och efter att dina data har flyttats.](during-and-after-your-data-move.md) Vi följer tjänstnivåavtalet [för Microsoft Online Services (SLA)](https://go.microsoft.com/fwlink/p/?LinkId=523897) för tillgänglighet så att det inte finns något som kunderna behöver förbereda sig för eller övervaka under flytten. 
  
Alla Microsoft 365-tjänster kör samma versioner i datacenter, så att du kan vara säker på enhetliga funktioner. Under hela processen stöds hela tjänsten.
  
## <a name="what-is-the-impact-of-having-different-services-located-in-different-geos"></a>Hur påverkar det olika tjänster på olika platser?

Vissa av Microsoft 365 tjänster kan finnas i olika geos för vissa befintliga kunder och för kunder som befinner sig mitt i flyttprocessen. Våra tjänster körs oberoende av varandra och det påverkar inte användarupplevelsen om så är fallet. Men i syfte att lagra data kan en klientmigrering inte ses som fullständig förrän både Exchange Online och SharePoint Online/OneDrive för företag migreras till samma datacenter geo.

 ## <a name="where-is-my-core-customer-data-located"></a>Var finns mina basdata för kunder?

Administratörer för klientorganisationen kan visa dataplatskortet i administrationscentret när som helst för att bekräfta basdata för varje tjänst, särskilt för klientorganisationen.  Vi publicerar även platsen för geodata från datacenter, datacenter och plats för Office 365-kunddata på de interaktiva datacenterkartorna [i Microsoft 365](https://office.com/datamaps) som en referens för aktuella standardbaskunddata på vilplatser för nya klientorganisationar. Du kan kontrollera platsen för dina kunddata i vila via avsnittet Dataplats under din organisationsprofil i Microsoft 365 administrationscenter.  
 
## <a name="when-will-i-be-able-to-request-a-move"></a>När kommer jag att kunna begära en flytt?
  
Mer information finns på [sidan Begära dataflyttning för](request-your-data-move.md) tidsperioder som stöds för ditt datacenter geo.
  
## <a name="how-can-i-request-to-be-moved"></a>Hur begär jag att få bli flyttad?
  
Berättigade kunder ser en sida i sitt Microsoft 365 [administrationscenter](https://admin.microsoft.com/). Anvisningar om [hur du begär en flytt finns](request-your-data-move.md) i Begära flytt av data. 
  
## <a name="can-i-change-my-selection-after-requesting-a-move"></a>Kan jag ändra min markering efter att ha begärt en flyttning?
  
Vi kan inte ta bort dig från processen efter att du skickat in din begäran.
  
## <a name="what-happens-if-i-do-not-request-a-move-before-the-deadline"></a>Vad händer om jag inte begär en flytt före deadlinen?
  
Vi kan inte acceptera migreringsförfrågningar efter den öppna registreringsperioden.

## <a name="what-if-i-want-to-move-my-data-in-order-to-get-better-network-performance"></a>Vad händer om jag vill flytta mina data för att få bättre nätverksprestanda?
  
Fysisk närhet till ett Microsoft 365 är inte en garanti för bättre nätverksprestanda. Det finns många faktorer och komponenter som påverkar nätverkets prestanda mellan slutanvändaren och Microsoft 365 tjänsten. Mer information om den här inställningen och prestandajustering finns i [Nätverksplanering och prestandajustering för Microsoft 365.](network-planning-and-performance.md)
  
 ## <a name="do-all-the-services-move-their-data-on-the-same-day"></a>Flyttar alla tjänster sina data samma dag?
 
Varje tjänst flyttas oberoende av varandra och flyttar sannolikt sina data vid olika tidpunkter.
  
 ## <a name="can-i-choose-when-i-want-my-data-to-be-moved"></a>Kan jag välja när jag vill att mina data ska flyttas?
 
Kunderna kan inte välja ett visst datum, de kan inte fördröja flytten och vi kan inte dela ett visst datum eller en viss tidsram för flytten.
  
 ## <a name="can-you-share-when-my-data-will-be-moved"></a>Går det att dela när mina data kommer att flyttas?
  
Dataflyttningar är en backend-åtgärd med minimal påverkan för slutanvändarna. Den komplexitet, precision och skala som vi behöver för att utföra dataflyttningar i en globalt drivs och automatiserad miljö hindrar oss från att dela när en dataflyttning förväntas slutföras för din klientorganisation eller någon annan enskild klientorganisation. Kunder får en bekräftelse i meddelandecentret per deltagande tjänst när dataflyttningen är klar. 
  
 ## <a name="what-happens-if-users-access-services-while-the-data-is-being-moved"></a>Vad händer om användare använder tjänster medan data flyttas?

I [Under och efter dataflyttningen](during-and-after-your-data-move.md) finns en fullständig lista över funktioner som kan vara begränsade under vissa delar av dataflyttningen för respektive tjänst. 
  
 ## <a name="how-do-i-know-the-move-is-complete"></a>Hur vet jag att flyttningen är slutförd?
  
Se Microsoft 365 i meddelandecentret för att få en bekräftelse på att flytten av varje tjänsts data har slutförts. När varje tjänsts data flyttas lägger vi upp ett slutförandemeddelande så att du får tre kompletteringsavvarningar: en var för Exchange Online, SharePoint Online och Skype för företag Online. Du kan också verifiera platsen för dina kunddata i vila via avsnittet Dataplats under din organisationsprofil i Microsoft 365 administrationscenter.  
  
## <a name="i-am-a-microsoft-365-customer-in-one-of-the-new-datacenter-geos-but-when-i-signed-up-i-selected-a-different-country-how-can-i-be-moved-to-the-new-datacenter-geo"></a>Jag är Microsoft 365 kund i ett av de nya datacenterna, men när jag registrerade mig valde jag ett annat land. Hur kan jag flyttas till det nya datacentret geo?

Det går inte att ändra det registreringland som är kopplat till din klientorganisation. I stället måste du skapa en Microsoft 365 klientorganisation med en ny prenumeration och manuellt flytta dina användare och data till den nya klientorganisationen.
  
## <a name="what-happens-if-we-are-in-process-of-email-data-migration-to-microsoft-365-during-the-exchange-online-move"></a>Vad händer om vi håller på att migrera e-postdata till Microsoft 365 under Exchange Online flytten?

Det här är ett mycket vanligt scenario och stöds helt.  Molnmigrering mellan geodatadata påverkar inte några migreringar av postlådor lokalt till molnet.
  
 ## <a name="can-i-pilot-some-users"></a>Kan jag pilottesta vissa användare?
  
Du kan skapa en separat utvärderingsklientorganisation för att testa anslutning, men utvärderingsklientorganisationen kan inte kombineras på något sätt med den befintliga klientorganisationen.

## <a name="i-dont-want-to-wait-for-microsoft-to-move-my-data-can-i-just-create-a-new-tenant-and-move-myself"></a>Jag vill inte vänta på att Microsoft ska flytta mina data. Kan jag bara skapa en ny klientorganisation och flytta på mig själv?
  
Ja, men processen blir inte lika smidig som om Microsoft utför dataflyttningen.
  
Om du skapar en ny klientorganisation efter att det nya datacentrets geo är tillgängligt, kommer den nya klientorganisationen att finnas på den nya geo. Den nya klientorganisationen är helt separat från din tidigare klientorganisation och du skulle vara ansvarig för att flytta alla användarpostlådor, webbplatsinnehåll, domännamn och andra data. Observera att du inte kan flytta klientnamnet från en klientorganisation till en annan. Vi rekommenderar att du väntar på det flyttningsprogram som tillhandahålls av Microsoft eftersom vi tar hand om flytten av alla inställningar, data och prenumerationer för användarna.
  
## <a name="my-customer-data-has-already-been-moved-to-a-new-datacenter-geo-can-i-move-back"></a>Mina kunddata har redan flyttats till ett nytt datacenter geo. Kan jag flytta tillbaka?
 
Nej, det går inte. Kunder som har flyttats till nya geodatacenter kan inte flyttas tillbaka. Som kund med alla geotjänster får du samma tjänstekvalitet, prestanda och säkerhetskontroller som du gjorde tidigare. [Microsoft 365 Multi Geo](https://aka.ms/multi-geo) är tillgängligt för vissa kunder som ett tillägg och gör att en enda klientorganisation kan skapa flera satellit geos och flytta användardata till dessa geos med åtaganden om data som lagras.
  
## <a name="will-microsoft-365-tenants-hosted-in-the-new-datacenters-be-available-to-users-outside-of-the-country"></a>Kommer Microsoft 365 klientorganisation i de nya datacenter vara tillgänglig för användare utanför landet?
  
Ja. Microsoft har ett stort globalt nätverk med offentliga Internetanslutningar på fler än 130 platser i 35 länder i världen med peeringavtal med fler än 2 700 Internetleverantörer (ISP). Användarna kommer att kunna komma åt datacenter var de än är på Internet.

## <a name="my-tenant-has-configured-the-multi-geo-add-on-can-i-still-enroll-in-my-tenant-in-the-microsoft-365-move-program-to-change-my-default-geo-and-move-any-user-not-in-a-satellite-region-to-the-new-default-geo"></a>Min klientorganisation har [konfigurerat multi geo-tillägget](https://aka.ms/multi-geo). Kan jag fortfarande registrera mig i min klientorganisation i Microsoft 365 Flytta program för att ändra min standard geo och flytta en användare som inte finns i en satellitområde till den nya standard geo?

Ja, klientorganisationen är berättigad att registrera, men det finns viktiga överväganden eftersom flytt på klientnivå inte stöds fullt ut för kunder som har konfigurerat Multi-Geo.

SharePoint Online- OneDrive för företag kan inte migrera till det nya datacentret geo på klientnivå via det här programmet. Customer Administrator can configure OneDrive för företag shares to move to any available region using Multi-Geo, but the default location for the tenant cannot be changed once Multi-Geo has been configured for a tenant.

För kunder som har valt att migrera – vi flyttar alla Exchange Online-postlådor från din nuvarande geoinställning till det nya lokala datacentret och uppdaterar Exchange Online geoområde. Vi flyttar inte några EXO-postlådor som konfigurerats i flera geo satellitområden för att fortsätta respektera satellitområdesdata som finns kvar som du tänkt dig. 

## <a name="related-topics"></a>Relaterade ämnen

[Flytta basdata till nya Microsoft 365 geodatadata](moving-data-to-new-datacenter-geos.md)

[Hur du begär din dataflytt](request-your-data-move.md)

[Microsoft 365 Multi Geo](https://aka.ms/multi-geo)

[Microsoft 365 en interaktiv datacenterkarta](https://office.com/datamaps)

[Microsoft 365 Support](../business-video/get-help-support.md)

[Nya geodatadatadata för Microsoft Dynamics CRM Online](/power-platform/admin/new-datacenter-regions)
  
[Azure-tjänster efter region](https://azure.microsoft.com/regions/)