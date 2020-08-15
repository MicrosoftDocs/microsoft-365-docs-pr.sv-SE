---
title: Microsoft 365 övervakning och test av klient organisationens gränser
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: I den här artikeln lär du dig hur Microsoft kontinuerligt övervakar och testar klient organisationens gränser för Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cd0aa3f88de3a8e22ef67283b20ecfae9959cb05
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694284"
---
# <a name="monitoring-and-testing-tenant-boundaries"></a>Övervakning och testning av innehavarens gränser

Microsoft kommer kontinuerligt att övervaka och uttryckligen testa svaga sidor och säkerhets problem i innehavarens gränser, inklusive övervakning av intrång, problem med godkännande och Starvation. Vi använder också flera interna system för att kontinuerligt övervaka för olämplig resursutnyttjande, som om det upptäcks, utlöser inbyggd begränsning.

Microsoft 365 har interna övervaknings system som kontinuerligt övervakar för eventuella misslyckanden och automatisk återställning vid fel. Microsoft 365-systemen analyserar avvikelser i tjänst beteende och initierar själv återställnings processer som är inbyggda i systemet. Microsoft 365 använder också övervakning utanför företaget där övervakning utförs från flera platser, både från betrodda tredje part tjänster (för oberoende SLA-verifiering) och våra egna data Center för att öka sina meddelanden. För diagnostik har vi omfattande loggning, granskning och spårning. Med detaljerad spårning och övervakning kan vi isolera problem och utföra snabba och effektiva Rotors Saks analyser.

Medan Microsoft 365 har automatiserade återställnings åtgärder är det möjligt för Microsoft in-Call-tekniker att undersöka alla säkerhets eskaleringer av allvarlighets grad 1 och efter slakten av varje tjänste olycka bidrar till Fort löp ande inlärning och förbättring. Det här teamet innehåller support tekniker, produkt utvecklare, program chefer, produkt chefer och ledarskaps chef. Våra samtals tekniker tillhandahåller tidsbesparande säkerhets kopiering och kan ofta automatisera återställnings åtgärder, så att den nästa gång en händelse inträffar kan den skötas själv.

Microsoft genomför en grundlig granskning efter en olycka varje gång ett säkerhets tillbud i Microsoft 365 inträffar oavsett hur stor inverkan är. En recension efter en olycka består av en analys av vad som hände, hur vi svarade och hur vi förhindrade liknande tillbud i framtiden. I intresse av öppenhet och ansvarighet delar vi efter en granskning efter en olycka med berörda kunder. Mer information finns i [Office 365 security incident management](https://aka.ms/Office365SIM).

## <a name="assume-breach-methodology"></a>Anta brott mot metoderna

Baserat på en detaljerad analys av säkerhets trenderna och Microsoft handlar och fokuserar på behovet av ytterligare investeringar i återaktiva säkerhets processer och-teknologier som fokuserar på identifiering och svar på nya hot, i stället för att förhindra sådana hot. På grund av ändringar i hotets huvud och djupgående analys är Microsoft förfinat sin säkerhets strategi förutom att förhindra säkerhets brott till en bättre utrustning för att hantera överträdelser när de inträffar – en strategi som betraktar viktiga säkerhets händelser, men när.

Trots att Microsoft [har gjort](https://www.microsoft.com/TrustCenter/Security/default.aspx) det gjort för många år är det många kunder som är medvetna om det arbete som utförs bakom kulisserna för att härdning Microsofts moln. Antag att intrång är en Mindset som guidar säkerhets investeringar, design beslut och operativa säkerhets rutiner. Antag att intrång begränsar förtroendet för program, tjänster, identiteter och nätverk genom att behandla allt – internt och externt – som osäkert och säkert. Även om det inte fanns något brott mot en verklig överträdelse av något av Microsofts företags-eller moln tjänster i syfte att undvika intrång var det ett erkännande av att många organisationer, i hela världen, hade brutit sig trots alla försök att förhindra det. När brott mot intrång är en viktig del av organisationens åtgärder måste de vara kontinuerligt testade och utökas till att effektivt adressera moderna adversaries och avancerade hot. För att organisationer ska kunna förbereda sig inför intrång måste de först bygga och underhålla stabila, repeterbara och noggrant testade säkerhets svars rutiner.

Även om säkerhets processer för intrång, till exempel hot modellering, kod granskningar och säkerhets testning är mycket användbara som en del av [livs cykeln för säkerhets utveckling](https://www.microsoft.com/securityengineering/sdl/), får du ett flertal fördelar som hjälper dig att hantera den övergripande säkerheten genom att utöva och mäta återaktiva funktioner i händelse av intrång.

På Microsoft har vi fastställt att du ska göra detta genom fortgående krigs spel-övningar och Live-utträngning av våra säkerhets svars planer med målet att förbättra vår identifierings-och svars kapacitet. Microsoft simulerar regelbundet brott mot hela världen, genomför fort löp ande säkerhets övervakning och praxis för säkerhets tillbuds hantering för att verifiera och förbättra säkerheten för Microsoft 365, Azure och andra Microsofts moln tjänster.

Microsoft genomför säkerhets strategin med två huvud grupper:
- Röda team (angripare)
- Blåa team (försvarare)

Både Microsoft Azure-och Microsoft 365-Personalen är separata, röda och blåa team.

Som "[röda](https://go.microsoft.com/fwlink/?linkid=518599)samarbeten", tillvägagångs sättet är att testa Azure-och Microsoft 365-system och drifts operationer med samma taktiker, tekniker och procedurer som Real adversaries, mot den löpande produktions infrastrukturen, utan foreknowledge av teknik-eller drift team. Detta testar Microsofts funktioner för säkerhets avkänning och svar, och hjälper till att identifiera problem med säkerheten, konfigurations fel, ogiltiga antaganden och andra säkerhets problem på ett kontrollerat sätt. Alla röda grupp överträdelser följs efter fullständig information mellan båda teamerna för att identifiera luckor, undersöknings resultat och förbättra brott mot intrång.

**Obs!** inga kunddata är medvetet riktade mot den röda gruppering-eller Live-webbplatsen. Testerna är mot Microsoft 365 och Azure Infrastructure och plattformar, samt till Microsoft egna klient organisationer, program och data. Kund klienter, program och innehåll som hanteras i Microsoft 365 eller Azure är aldrig riktade mot varandra.

## <a name="red-teams"></a>Röda team

Det röda laget är en grupp heltids anställda i Microsoft som fokuserar på att bryta mot Microsofts infrastruktur, plattform och Microsoft-program. De är de speciella adversary (en grupp etiska hackare) som utför särskilda och permanenta attacker mot online tjänster (Microsoft Infrastructure, plattformar och program, men inte till slut kunders program eller innehåll).

Syftet med den röda gruppen är att attackera och tränga miljöer på samma sätt som en adversary:
 
![Överträdelser](../media/office-365-isolation-breach-stages.png)

Bland andra funktioner försöker röda Teams att bryta mot innehavarens isolerings gränser för att hitta buggar eller luckor i vår isolerings design.

## <a name="blue-teams"></a>Blå Team

Det blå teamet består av antingen en dedikerad uppsättning säkerhets svarare eller medlemmar från säkerhets organisationens svars-, ingenjörs-och verksamhets organisationer. Oavsett hur de blir uppdelade är de oberoende och fungerar åtskilt från den röda gruppen. Det blå teamet följer etablerade säkerhets processer och använder de senaste verktygen och teknikerna för att upptäcka och reagera på attacker och intrång. Precis som i verkliga attacker är det blåa teamet inte att se när eller hur det röda teamets attacker kommer att inträffa eller vilka metoder som kan användas. Deras jobb, vare sig det är ett rött lag eller en verklig Assault, är att upptäcka och reagera på alla säkerhets händelser. Av den anledningen är det blå teamet alltid på-samtal och måste reagera på rött grupp intrång på samma sätt som de skulle ha för övrigt intrång.

När en adversary, till exempel ett rött team, har brutit mot en miljö måste det blå laget:

- Samla in bevis som lämnats av adversary
- Upptäcka beviset som indikation på kompromiss
- Avisera lämpliga tekniska och drifts team (er)
- Postsortering varningarna för att avgöra om de garanterar ytterligare undersökningar
- Samla in kontexten från miljön för att begränsa överträdelsen
- Bilda en reparations plan för att innehålla eller avvisa adversary
- Genomföra reparations planen och återställa mot överträdelse

De här stegen utgör säkerhets tillbuds svaret som körs parallellt med adversary, som visas nedan:
 
![Etapper för brott mot svar](../media/office-365-isolation-breach-response-stages.png)

Tack vare den röda grupp brotten kan du utnyttja den blå gruppens förmåga att upptäcka och reagera på Real-attacker från slut punkt till slut punkt. Viktigast är att det gör det möjligt för säkerhets tillbud att reagera före en verklig överträdelse. Dessutom är det blå teamet bättre på grund av ett rött lag brott som kan vara värdefullt när du hanterar framtida överträdelser (oavsett om det är från det röda teamet eller ett annat adversary). Under hela identifierings-och svars processen ger det blå teamet en åtgärds bara intelligens och får insyn under de faktiska förhållandena i den eller de miljöer som de försöker försvara. Vanligt vis görs detta via data analys och Forensics, som utförs av det blå teamet, när det svarar på röda grupp attacker och genom att skapa hot indikatorer, till exempel indikatorer på intrång. På samma sätt som när det röda teamet identifierar luckor i säkerhets berättelsen identifieras luckor i deras förmåga att upptäcka och svara. Dessutom, eftersom de röda team modellerna i Real världen, kan det blå teamet vara korrekt uppskattat på deras kapacitet eller oförmåga, för att hantera fastställda och bestående adversaries. Slutligen kan röda grupp intrång mäta både beredskap och effekten av vårt svar på intrång.
