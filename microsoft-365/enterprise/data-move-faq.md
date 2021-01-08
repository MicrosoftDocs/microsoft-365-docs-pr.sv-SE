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
description: Hitta svar på vanliga frågor (FAQ) om att flytta grundläggande data till ett nytt Office 365-datacenter geo.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 49ddcbf3a1aa8d91bd8202894e114fe50624720a
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780266"
---
# <a name="data-move-general-faq"></a>Vanliga frågor och svar om dataflytt

Här är några svar på vanliga frågor om att flytta grundläggande kunddata på andra håll till ett nytt Data Center geo.
  
## <a name="what-customers-are-eligible-to-request-a-move"></a>Vilka kunder är berättigade att begära flytt?
  
Befintliga Microsoft 365-kommersiella kunder som valde ett land som är berättigat till det nya data Center geo kommer att kunna begära en flytt. Programmet finns bara för innehavare med en stödberättigad landskod som tilldelats Microsoft 365-klient organisationen för att migrera grundläggande kunddata på rest för kvalificerade arbets belastningar till motsvarande Microsoft 365 Data Center geo. Se [hur du kan begära att dina data flyttas](request-your-data-move.md) för att bekräfta land.   

## <a name="how-do-we-define-core-customer-data"></a>Hur definierar vi grundläggande kunddata?
 
Grundläggande kund data är en term som refererar till en delmängd kunddata som definierats i [Microsoft Online Services-villkoren](https://aka.ms/ost): 
- Innehåll för Exchange Online-postlådan (e-post, kalender poster och innehållet i e-postbilagor)
- SharePoint Online-webbinnehåll och filer som lagras på webbplatsen
- Filer som laddats upp till OneDrive för företag 

## <a name="what-is-in-scope-for-teams-migration"></a>Vad finns i omfattning för team migrering?

Utöver Exchange Online, SharePoint Online och OneDrive för företag; Microsoft migrerar team data till det lokala data centret. 
- Teams chattar meddelanden, inklusive privata meddelanden och kanal meddelanden. 
- Team-bilder som används i chattar. 

Teams-filer lagras i SharePoint Online-och Teams-chatt-filer lagras i OneDrive för företag. Röst brev låda, kalender och kontakter lagras i Exchange Online. I många fall används Exchange Online, SharePoint Online och OneDrive för företag redan av kunden i det lokala datacentret Geo och är också en del av Microsoft 365 migrations program för godkända kund länder.

## <a name="at-what-point-is-my-migration-complete-so-that-my-tenants-core-customer-data-is-being-stored-at-rest-in-my-new-geo"></a>Vad händer när min migrering är färdig så att min klient organisations viktigaste kund uppgifter lagras på en ny geo?

På grund av delade samarbeten mellan Exchange Online och SharePoint Online/OneDrive för företag kan ingen migrering anses vara slutförd förrän båda tjänsterna migreras. Exchange Online och SharePoint Online/OneDrive för företag migreras ofta vid olika tillfällen och oberoende av varandra. Klient organisations administratörer får bekräftelse i meddelande Center när varje tjänste migrering är färdig och kan visa data plats kortet i administrations centret när som helst för att bekräfta grundläggande kund uppgifter på rest-platsen för varje tjänst.

## <a name="how-do-you-make-sure-my-customer-data-is-safe-during-the-move-and-that-i-wont-experience-downtime"></a>Hur ser jag till att mina kund uppgifter är säkra under flytten och att jag inte upplever nertid?
  
Data flyttas är en server åtgärd som påverkar slutanvändaren minimalt. Funktioner som kan påverkas visas [under och efter att data flyttas](during-and-after-your-data-move.md). Vi följer [service nivå avtalet för Microsoft Online Services (SLA)](https://go.microsoft.com/fwlink/p/?LinkId=523897) för tillgänglighet så det finns inget som kunderna behöver för att förbereda för eller för att övervaka under flytten. 
  
Alla Microsoft 365-tjänster kör samma versioner i Data Center, så att du kan vara säker på konsekvent funktionalitet. Din tjänst stöds helt och hållet.
  
## <a name="what-is-the-impact-of-having-different-services-located-in-different-geos"></a>Vad är effekten av att ha olika tjänster på olika geos?

Vissa av Microsoft 365-tjänsterna kan finnas i olika geos för vissa befintliga kunder och för kunder som är i mitten av flytt processen. Våra tjänster körs oberoende av varandra och det påverkar inte användar upplevelsen om så är fallet. För data de är det dock inte heller att migrera en klient organisation som är fullständig förrän både Exchange Online och SharePoint Online/OneDrive för företag migreras till samma data Center geo.

 ## <a name="where-is-my-core-customer-data-located"></a>Var finns alla grundläggande kund uppgifter?

Kund tjänst administratörer kan när som helst visa data plats kortet i administrations centret för att bekräfta grundläggande kund data på rest-platsen för varje tjänst, särskilt för deras innehavare.  Vi publicerar också platsen för datacenter-geos, data Center och plats för Office 365-kunddata på [Microsoft 365 interaktiva Data Center-kartor ](https://office.com/datamaps) som en referens till de aktuella standard kund uppgifterna på rest-platser för nya klient organisationer. Du kan kontrol lera platsen för dina kunddata på rest via området data plats under din organisations profil i administrations centret för Microsoft 365.  
 
## <a name="when-will-i-be-able-to-request-a-move"></a>När kan jag begära en flytt?
  
Se avsnittet [så här kan du begära data flyttnings](request-your-data-move.md) sidan för stödda tids ramar för ditt data Center geo.
  
## <a name="how-can-i-request-to-be-moved"></a>Hur kan jag begära att få flyttas?
  
Berättigade kunder ser en sida i [Microsoft 365 Admin Center](https://admin.microsoft.com/). Information om hur du gör för att begära ett flytt försök finns i [så här efterfrågar du dina data](request-your-data-move.md) . 
  
## <a name="can-i-change-my-selection-after-requesting-a-move"></a>Kan jag ändra markeringen efter att ha begärt flytt?
  
Vi kan inte ta bort dig från processen när du har skickat in din begäran.
  
## <a name="what-happens-if-i-do-not-request-a-move-before-the-deadline"></a>Vad händer om jag inte gör en flyttning före deadline?
  
Vi kan inte acceptera begäran om migrering efter den öppna registrerings perioden.

## <a name="what-if-i-want-to-move-my-data-in-order-to-get-better-network-performance"></a>Vad gör jag om jag vill flytta mina data för att få bättre nätverks prestanda?
  
Det är inte säkert att det går till ett Microsoft 365-datacenter för bättre nätverks prestanda. Det finns många faktorer och komponenter som påverkar nätverks prestandan mellan slutanvändaren och Microsoft 365-tjänsten. Mer information om den här och prestanda justering finns i [nätverks planering och prestanda justering för Microsoft 365](network-planning-and-performance.md).
  
 ## <a name="do-all-the-services-move-their-data-on-the-same-day"></a>Flyttar alla tjänster sina data samma dag?
 
Varje tjänst flyttas oberoende och kommer troligen att flytta sina data vid olika tillfällen.
  
 ## <a name="can-i-choose-when-i-want-my-data-to-be-moved"></a>Kan jag välja när jag vill att mina data ska flyttas?
 
Kunder kan inte välja ett specifikt datum, de kan inte försena sin flytt och det går inte att dela ett specifikt datum eller en tidsram för flytten.
  
 ## <a name="can-you-share-when-my-data-will-be-moved"></a>Kan du dela när mina data flyttas?
  
Data flyttas är en backend-åtgärd som påverkar slutanvändaren minimalt. Den komplexitet, precision och skala som vi behöver för att utföra data flyttningar inom en global, automatisk, automatiserad miljö hindrar oss från att dela när data flyttas för din klient organisation eller annan klient organisation. Kunderna får en bekräftelse i meddelande Center per deltagande tjänst när dess data flyttas. 
  
 ## <a name="what-happens-if-users-access-services-while-the-data-is-being-moved"></a>Vad händer om användare får åtkomst till tjänster medan data flyttas?

Se [under och efter att data har flyttats](during-and-after-your-data-move.md) för en fullständig lista över funktioner som kan begränsas under delar av data flytten för varje tjänst. 
  
 ## <a name="how-do-i-know-the-move-is-complete"></a>Hur vet jag att flytten är slutförd?
  
Titta på meddelande Center i Microsoft 365 för att bekräfta att det flyttas mellan alla data för varje tjänst. När de enskilda tjänstens data flyttas så skickar vi ett meddelande om att du får tre slut för ande meddelanden: en för Exchange Online, SharePoint Online och Skype för företag – online. Du kan också kontrol lera platsen för dina kunddata på rest via området data plats under din organisations profil i administrations centret för Microsoft 365.  
  
## <a name="i-am-a-microsoft-365-customer-in-one-of-the-new-datacenter-geos-but-when-i-signed-up-i-selected-a-different-country-how-can-i-be-moved-to-the-new-datacenter-geo"></a>Jag är Microsoft 365-kund i ett av de nya data Center-geos, men när jag registrerade dig valde jag ett annat land. Hur kan jag flytta till det nya data Center geo?

Det går inte att ändra det registrerings land som är associerat med din klient organisation. I stället måste du skapa en ny Microsoft 365-klient organisation med en ny prenumeration och manuellt flytta dina användare och data till den nya klient organisationen.
  
## <a name="what-happens-if-we-are-in-process-of-email-data-migration-to-microsoft-365-during-the-exchange-online-move"></a>Vad händer om vi håller på att migrera e-postdata till Microsoft 365 när du flyttar Exchange Online?

Det här är ett ovanligt vanligt scenario och stöds helt. Cloud migration mellan data Center geos stör inte eventuella lokala för migreringar av moln post lådor.
  
 ## <a name="can-i-pilot-some-users"></a>Kan jag piloterar vissa användare?
  
Du kan skapa en separat prov klient för att testa anslutningen, men det går inte att kombinera utvärderings organisationen på något sätt med din befintliga klient organisation.

## <a name="i-dont-want-to-wait-for-microsoft-to-move-my-data-can-i-just-create-a-new-tenant-and-move-myself"></a>Jag vill inte vänta på att Microsoft flyttar mina data. Kan jag skapa en ny klient organisation och flytta mig själv?
  
Ja, men processen kommer inte att vara lika sömlös som om Microsoft gjorde det för att flytta data.
  
Om du skapar en ny klient organisation efter det nya data Center geo är det möjligt att den nya klient organisationen är värd för den nya geoen. Den nya innehavaren är helt separat från din tidigare klient organisation och du ansvarar för att flytta alla användar post lådor, webbplats innehåll, domän namn och andra data. Observera att du inte kan flytta klient organisations namnet från en innehavare till en annan. Vi rekommenderar att du väntar på att det program som tillhandahålls av Microsoft ska flyttas för att du ska kunna flytta alla inställningar, data och abonnemang för dina användare.
  
## <a name="my-customer-data-has-already-been-moved-to-a-new-datacenter-geo-can-i-move-back"></a>Mina kund uppgifter har redan flyttats till ett nytt Data Center geo. Kan jag gå tillbaka?
 
Nej, det är inte möjligt. Kunder som har flyttats till nya geo-datacenter kan inte flyttas tillbaka. Som kund i alla geoprodukter kommer du att uppleva samma QoS-, prestanda-och säkerhets kontroller som du gjorde förut. [Microsoft 365 multi geo](https://aka.ms/multi-geo) är tillgängligt för vissa kunder som ett tillägg och låter en enda klient organisation skapa flera satellit geos och flytta användar data till de geos med data de åtaganden.
  
## <a name="will-microsoft-365-tenants-hosted-in-the-new-datacenters-be-available-to-users-outside-of-the-country"></a>Kommer Microsoft 365-klient organisationer som är värd för nya data Center att vara tillgängliga för användare utanför landet?
  
Ja. Microsoft har ett stort globalt nätverk med offentliga Internet anslutningar på mer än 130 platser i 35-länder i hela världen med olika avtal med fler än 2 700 Internet leverantörer. Användare kommer att kunna komma åt data Center, oavsett var de befinner sig på Internet.

## <a name="my-tenant-has-configured-the-multi-geo-add-on-can-i-still-enroll-in-my-tenant-in-the-microsoft-365-move-program-to-change-my-default-geo-and-move-any-user-not-in-a-satellite-region-to-the-new-default-geo"></a>Klient organisationen har konfigurerat [multi geo-tillägget](https://aka.ms/multi-geo). Kan jag fortfarande registrera sig i min klient organisation i Microsoft 365 flytt program för att ändra standard Geo och flytta användare som inte är i en satellit region till det nya standardvärdet geo?

Ja, din klient organisation är berättigad, men det finns betydande överväganden när flytt av klient nivå inte stöds helt för kunder som har konfigurerat multi-geo.

SharePoint Online och OneDrive för företag kan inte migrera till det nya data Center geo på klient nivå via det här programmet. Kund administratören kan konfigurera OneDrive för företag-resurser för att gå till alla tillgängliga regioner med multi-geo, men standard platsen för klient organisationen kan inte ändras när multi-geo har kon figurer ATS för en klient organisation.

För kunder som väljer att migrera – vi flyttar alla Exchange Online-postlådor från din nuvarande geo till ditt nya lokala data Center och uppdaterar standard området för Exchange Online. Vi kommer inte att flytta EXO-postlådor som kon figurer ATS i flera geo satellit regioner för att fortsätta att respektera data de i satellit området. 

## <a name="related-topics"></a>Relaterade ämnen

[Flytta grundläggande data till nya Microsoft 365 Data Center-geos](moving-data-to-new-datacenter-geos.md)

[Hur du begär din dataflytt](request-your-data-move.md)

[Microsoft 365 multi geo](https://aka.ms/multi-geo)

[Microsoft 365 interaktiv Data Center karta](https://office.com/datamaps)

[Microsoft 365-support](https://go.microsoft.com/fwlink/p/?LinkID=522459)

[Ny datacenter-geos för Microsoft Dynamics CRM Online](https://go.microsoft.com/fwlink/p/?Linkid=615924)
  
[Azure-tjänster efter region](https://azure.microsoft.com/regions/)
