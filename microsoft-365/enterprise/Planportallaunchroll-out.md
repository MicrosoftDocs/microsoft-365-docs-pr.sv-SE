---
title: Planera lanseringsplanen för portalen i SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: I den här artikeln beskrivs hur du planerar lanseringen av portalen i SharePoint Online och vilka åtgärder du kan vidta för att lanseringen ska lyckas
ms.openlocfilehash: d77baac6209a4002bb1c27513d5ccfdf5c4ac28a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905698"
---
# <a name="planning-your-portal-launch-roll-out-plan-in-sharepoint-online"></a>Planera lanseringsplanen för portalen i SharePoint Online

En portal är en SharePoint-webbplats i ditt intranät som har många användare som använder innehåll på webbplatsen. I stora organisationer kan det finnas flera av dessa: till exempel en företagsportal och en personalportal. Vanligtvis har portaler relativt få personer som skapar och skapar webbplatsen och dess innehåll. De flesta besökare på portalen läser bara och använder innehållet.

I den här artikeln beskrivs hur du planerar distribution och distribution till SharePoint Online. Det ger även metoder att följa eftersom traditionella belastningstester inte är tillåtna i SharePoint Online. SharePoint Online är en molntjänst och belastningsfunktionerna, hälsotillståndet och den övergripande belastningen i tjänsten hanteras av Microsoft.

För att skapa en lyckad portal följer du de grundläggande principerna, metoderna och rekommendationerna i skapa, starta och [underhålla en felfri portal](/sharepoint/portal-health) 

Distributionsmetod markeras nedan.

## <a name="overview-of-capacity-planning-in-sharepoint-online"></a>Översikt över kapacitetsplanering i SharePoint Online
För att kunna använda vår kapacitet effektivt och hantera oväntad tillväxt i olika servergruppar använder vi automation som spårar vissa användningsscenarier. Även om exakt tillväxt är svår att förutse för en klientorganisation i en servergrupp går det att förutspå den samlade summan av förfrågningar med tiden. Genom att identifiera tillväxttrender i SharePoint Online kan vi planera för framtida expansion. Mer information om [kapacitetsplanering och belastningstester av SharePoint Online.](capacity-planning-and-load-testing-sharepoint-online.md)

En viktig del i en lyckad lansering är metoden med "våg" eller "fasad utrullning" som beskrivs nedan. 

## <a name="can-i-load-test-sharepoint-online"></a>Kan jag läsa in test i SharePoint Online?
SharePoint Online är en delad miljö med flera klientgrupper som är balanserad över alla grupper och skala justeras i det löpande. Om du läser in en miljö, till exempel SharePoint Online, vars skala ändras kontinuerligt får du inte bara oväntade resultat utan det är inte tillåtet. 

Läs mer:  [Kapacitetsplanering och belastningstestning av SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md)

## <a name="optimize-pages-by-following-recommended-guidelines"></a>Optimera sidor genom att följa rekommenderade riktlinjer
Sidor från en lokal distribution bör inte bara flyttas när de kommer till SharePoint Online utan att de granskas mot rekommenderade riktlinjer för SharePoint Online. Det bästa sättet är att alltid optimera en startsida för en webbplats eller portal i SharePoint, eftersom det är här de flesta användare i organisationen kommer åt den som startpunkt för dina webbplatser.

Några grundläggande faktorer bör beaktas:
- Lokala distributioner kan utnyttja traditionella serverbaserade cacheminnen som objektcache, utdatacache och blob-cache. Eftersom det finns skillnader i topologi i molnet är de här alternativen inte nödvändigtvis tillgängliga eftersom de viktigaste skillnaderna gör dem mindre gångbara metoder.
- Alla sidor/funktioner/anpassningar som används för molnanvändning bör vara optimerade för högre latens och distribuerade platser för användare, så att användare i olika områden eller regioner får en mer enhetlig upplevelse. Molnet erbjuder optimeringar som Content Delivery Networks (CDN) för att optimera för en distribuerad användarbas och för moderna SharePoint, och den senaste kända (LKG) används av våra oanvända webbdelar (OOTB).

### <a name="what-to-do"></a>Vad kan jag göra?
 - För alla webbsidor i SharePoint [](./page-diagnostics-for-spo.md)Online använder du verktyget Siddiagnostik, som är ett Chromium-tillägg som hjälper dig analysera och ge vägledning. Det kan användas av webbplatsägare, redigerare, administratörer och utvecklare eftersom det är utformat för att vara en utgångspunkt för analys och optimering.
 - Utvecklare bör också använda utvecklingsverktyg som F12-webbläsarutvecklingsverktyg och CTRL-F12 i webbläsaren på moderna sidor. Du kan även använda [Fiddler](https://www.telerik.com/download/fiddler) för att granska storleken (hur stor sidan är i megabyte) och antalet samtal och element som påverkar den totala sidinläsningen. 

Det här avsnittet var en kort sammanfattning för hur du optimerar sidor.  Mer information finns i [Skapa, starta och underhålla en felfri portal.](/sharepoint/portal-health)

## <a name="follow-a-wave--phased-roll-out-approach"></a>Följ en omgång/fasningsmetod för utrullning
Den traditionella metoden med jättearg för webbplatslanseringar tillåter inte verifiering av att anpassningar, externa källor, tjänster eller processer har testats på rätt skala. Det innebär inte att det tar månader att starta, men vi rekommenderar det över minst flera dagar beroende på organisationens storlek. Efter en plan för att genomföra en omgång får du därför möjlighet att pausa och lösa problem innan du fortsätter med nästa fas, och därmed minskar antalet användare som påverkas av eventuella problem. SharePoint som en tjänst skalar din kapacitet baserat på användning och prognostbaserad användning och vi behöver inte dig att meddela oss om lanseringen, bör du följa riktlinjerna för att säkerställa framgång.
  
Så som visas i följande bild är antalet inbjudna användare ofta betydligt högre än antalet som faktiskt använder webbplatsen. Den här bilden visar en strategi för en ny version. Med den här metoden kan du identifiera olika sätt att förbättra SharePoint-webbplatsen innan majoriteten av användarna ser den.
  
![Diagram som visar inbjudna och aktiva användare](../media/0bc14a20-9420-4986-b9b9-fbcd2c6e0fb9.png)
  
Under pilotfasen är det bra att få feedback från engagerade användare som organisationen har förtroende för. På så sätt går det att avgöra hur systemet används och vilken prestanda det har.
  
Under var och en av vågorna samlar du in feedback om användarnas funktioner och prestanda under varje distributionsomgång. Fördelen är att systemet införs långsamt och att du kan förbättra det i takt med att användningen ökar. Det här gör också att vi kan reagera på ökade arbetsbelastningar när webbplatsen distribueras till fler och fler användare och i kombination med att följa riktlinjerna för sidoptimering säkerställer en positiv upplevelse för dina användare.

### <a name="what-to-do"></a>Vad kan jag göra?
- Bestäm tidsinställningar för varje fas och kontrollera att du har en möjlighet till reserv/paus om du skulle behöva justera innan du fortsätter
- Planera den första gruppen av användare som du vill aktivera, så att du får den feedback du behöver. Det innebär att där det är möjligt bör du välja en aktiv grupp användare som kommer att ge feedback i tid
- När du planerar varje omgång kan du försöka börja med en liten användarbas (mindre än 5 000 användare) och sedan öka gruppstorleken när du fortsätter med varje omgång. Det här hjälper till att skapa en spridd metod och gör det enklare att pausa möjligheter som kan behövas.