---
title: Kapacitetsplanering och belastningstestning av SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/10/2019
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
ms.assetid: c932bd9b-fb9a-47ab-a330-6979d03688c0
description: I den här artikeln beskrivs hur du kan distribuera till SharePoint Online utan att utföra traditionella belastningstester eftersom det inte är tillåtet.
ms.openlocfilehash: fb54864168b35fed290ccb1139cb6c607969820d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905230"
---
# <a name="capacity-planning-and-load-testing-sharepoint-online"></a>Kapacitetsplanering och belastningstestning av SharePoint Online
I den här artikeln beskrivs hur du kan distribuera till SharePoint Online utan traditionella belastningstester, eftersom belastningstester inte är tillåtna i SharePoint Online. SharePoint Online är en molntjänst och belastningsfunktionerna, hälsotillståndet och den övergripande belastningen i tjänsten hanteras av Microsoft.
  
Det bästa sättet att säkerställa att webbplatsen lanseras väl är att följa grundläggande principer, metoder och rekommendationer som markeras i planen för lanseringen [av din portal.](planportallaunchroll-out.md)

## <a name="overview-of-how-sharepoint-online-performs-capacity-planning"></a>Översikt över hur SharePoint Online utför kapacitetsplanering 
En av fördelarna med SharePoint Online i en lokal distribution är flexibiliteten i molnet samt optimeringar för användare i distribuerade regioner. Våra storskaliga miljö är konfigurerad för miljontals användare varje dag, så det är viktigt att vi hanterar kapaciteten effektivt genom att balansera och utöka kapaciteten.
  
Även om tillväxten ofta är svår att förutse för en klientorganisation i en servergrupp går det att förutspå den samlade summan av förfrågningar med tiden. Genom att identifiera tillväxttrender i SharePoint Online kan vi planera för framtida expansion.
  
För att kunna använda vår kapacitet effektivt och hantera oväntad tillväxt i olika serverfarmer använder vi automation som spårar och övervakar olika delar av tjänsten. Flera mätvärden används, med en av de viktigaste värdena vid processorbelastning, som används som en signal för att skala upp frontend-servrar. Dessutom rekommenderar vi en [](planportallaunchroll-out.md)fasad /våg-metod eftersom SQL-miljöer skalar efter belastning och tillväxt över tid och genom att följa faserna och vågorna möjliggör rätt fördelning av belastningen och tillväxten. 

Kapacitet handlar mer än bara om att kontinuerligt lägga till mer maskinvara, men den handlar även om att hantera och kontrollera denna kapacitet för att säkerställa att den underhålls av giltiga belastningsförfrågningar. Vi rekommenderar att kunderna följer de rekommenderade rekommendationer för att säkerställa att de får den bästa upplevelsen. Det innebär också att vi har begränsningsmönster och kontroller för att säkerställa att vi inte tillåter "olämpligt" beteende i tjänsten. Det är inte alltid "dåligt" beteende som är avsiktligt, vi måste säkerställa att vi begränsar effekten av beteendet. Mer information om begränsning och hur du undviker den finns i artikeln om [hur du undviker begränsningar i vägledningen.](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online)

## <a name="why-you-cannot-load-test-sharepoint-online"></a>Varför kan du inte läsa in testa SharePoint Online
I lokala miljöer används belastningstester till att kontrollera antaganden om skalning och få reda på servergruppens brytningspunkt. genom att mätta det med belastning. 

Med SharePoint Online behöver vi göra saker på ett annat sätt eftersom skalan är relativt flytande och justerar, begränsar och styr belastningen, baserat på viss heuristisk. Eftersom miljön har så stor storlek för flera innehavare måste vi skydda alla innehavare i samma servergrupp, så vi kommer automatiskt att begränsa eventuella belastningstester. Om du däremot försöker läsa in test, förutom att begränsas, kommer du att få ett eventuellt missvisande resultat eftersom den servergrupp som du testat idag troligtvis har haft skaländringar under testfönstret eller inom några timmar efter testning, allt eftersom åtgärder för skalning och servergruppsutjämning utförs i farten.

I stället för att försöka läsa in testa SharePoint som en tjänst bör du hellre fokusera på att följa de rekommenderade metoderna och följa rekommendationer för att skapa, starta och underhålla en [felfri](/sharepoint/portal-health) portalvägledning.