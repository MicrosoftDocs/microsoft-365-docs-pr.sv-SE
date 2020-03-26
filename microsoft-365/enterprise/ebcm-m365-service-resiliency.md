---
title: Microsoft 365-tjänstens återhämtning
author: chrfox
f1.keywords:
- NOCSH
ms.author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Beskrivning av återhämtningsämne
ms.openlocfilehash: 8cda7a861b6ea646ed9606674e26aaca551d1024
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42808124"
---
# <a name="built-in-resiliency"></a>Inbyggd återhämtning

Som molnsamarbetsleverantör känner Microsoft till behovet av att ständigt vinna ditt förtroende genom att erbjuda lösningar som fungerar konsekvent och som användarna tycker om. När en viss tjänst inte är tillgänglig kallas detta för driftsavbrott. Definitionen av driftsavbrott varierar beroende på var och en av tjänsterna Microsoft 365, men de har vanligtvis fokus på vilken tidsperiod som helst när användare inte kan använda tjänstens väsentliga funktioner. Här är till exempel definitionen av driftsavbrott för SharePoint Online från Microsoft 365-tjänstenivåavtalet:

**”SharePoint Online-driftsavbrott**: valfri tidsperiod när användare inte kan läsa eller skriva någon del av en SharePoint Online-webbplatssamling som de har tillräcklig behörighet för.”

Du hittar definitioner av driftsavbrott för varje tjänst i [tjänstenivåavtalen](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=37).

För att minimera driftsavbrott, antingen planerat eller oväntat, blir Microsoft 365-tjänsterna utformade och drivna för att ha hög tillgänglighet och vara motståndskraftiga mot fel genom att fokusera på fyra områden:

## <a name="activeactive-design"></a>Aktiv/aktiv-struktur

I Microsoft 365 strävar vi efter att ha alla tjänster konstruerade och drivna i en aktiv/aktiv design vilket ökar återhämtningen. Det innebär att alltid ha flera instanser av en tjänst som körs och som kan svara på användarförfrågningar och som finns i geografiskt spridda datacenter. All användartrafik kommer via tjänsten Microsoft Front Door och dirigeras automatiskt till den instans av tjänsten som är bäst och kommer att ligga nära alla misslyckade försök att förhindra eller minska påverkan på våra kunder.

## <a name="reduce-incident-scope"></a>Minska händelsens omfattning

Omfattningen av en tjänsthändelse mäts genom hur allvarligt det är, hur lång tid det varar och hur många kunder som påverkas. Vi strävar efter att begränsa omfattningarna för alla händelser genom att:

- ha flera instanser av varje tjänst partitionerade från varandra
- distribution av uppdateringar på ett kontrollerat sätt med hjälp av verifieringsringar, så att problem som kan uppstå från uppdateringen kan upptäckas och minskas tidigt i distributionsprocessen. Med det här alternativet kan du använda regressionen av uppdateringen om det behövs för första gången sker i en liten grupp inom Microsoft (den inre ringen) innan den distribueras till större grupper, t. ex. alla 140 000 Microsoft-anställda globalt (ring 2), därefter till grupper med tidiga användare (grupp 3) och i slutändan till alla kunder globalt (ring 4).
- genomför förbättringar av övervakning via automatisering. Microsoft 365 är mycket stort och drifttiden för SLA-målet är hög. I början av en tjänstehändelse skulle det inte gå att svara tillräckligt snabbt för att uppfylla tjänstenivåavtalet om människor var inblandande. Automation är nyckeln till att snabbt och effektivt upptäcka identifiering och svar för tjänstproblem. Ju tidigare vet vi om något, desto snabbare kan det åtgärdas.

Tillsammans med de aktiva/aktiva funktionerna som är inbyggda i Microsoft 365-tjänstens arkitektur minskar de här åtgärderna allvarlighetsgraden, varaktigheten och antalet påverkade kunder under en tjänstehändelse.  

## <a name="fault-isolation"></a>Felisolering

I likhet med att tjänsterna är utformade och körs på ett aktivt/aktivt sätt och är partitionerade från varandra för att förhindra att fel påverkar en tjänst, utvecklas kodbasen för tjänsten med liknande partitioneringsprinciper som kallas för felisolering. Åtgärder för felisolering är stegvisa skydd i själva kodbasen. De här åtgärderna bidrar till att förhindra att ett problem i ett område överförs till andra arbetsområden.
Felisoleringsåtgärder tillämpas i flera steg under utvecklingen och leveransen av en tjänst, inklusive kodutveckling, tjänstdistribution, belastningsutjämning och databasreplikering.

Microsoft Security Development Lifecycle (SDL) främjar också återhämtning och består av en uppsättning metoder som stöder säkerhets- och efterlevnadskrav. SDL vägleder våra utvecklare när de skapar elastiska, säkra, kompatibla tjänster. Viktiga element i SDL är kodgranskningar, hotmodellering, intrångstestning och standardiserade svarsprocesser för incidenter i Microsoft Cloud.

M365-tjänsterna är mycket sammankopplade, men systemen och tekniken som ligger bakom dem är utformade på ett sätt som begränsar konsekvenserna om en tjänstehändelse går över till andra tjänster. Exempelvis påverkar inte ett problem som påverkar Exchange Online inte huvudfunktionerna i Teams, och ett problem med sökfunktionen i SharePoint Online påverkar inte användarens möjlighet att ladda upp eller ladda ned filer.

## <a name="continuous-service-improvement"></a>Löpande tjänstförbättringar

Vi tar en incident på allvar. Med vår redundanta molnarkitektur och rigorösa interna processer kan våra tjänster vara lättillgängliga. Under en incident identifierar vår övervakning snabbt de berörda tjänsterna och om din klientorganisation påverkas kommer du att bli informerad omedelbart via en mängd olika kanaler. Samtidigt följer teknikerna väldefinierade processer för att prioritera problemet och vidta nödvändiga åtgärder för att återställa normala åtgärder så snabbt som möjligt. När tjänsten fungerar som vanligt igen gör vi granskningar efteråt som en del av vår löpande tjänstförbättring. Under granskningen efter händelsen identifierar vi orsaken till incidenten och vad som krävdes för att åtgärda problemen. Vi tar sedan det vi har lärt oss av situationen och tillämpar det på designen och driften i alla våra erbjudanden. Genom att göra det kan vi förhindra att samma rotorsak påverkar andra tjänster och fler kunder.
