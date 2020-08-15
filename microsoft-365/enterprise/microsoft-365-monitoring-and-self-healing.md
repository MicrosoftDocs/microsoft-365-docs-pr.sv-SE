---
title: Microsoft 365-övervakning och själv återställning
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
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln lär du dig mer om övervakning och själv återställning i Microsoft 365.
ms.openlocfilehash: 459fdb50577c255d3cf27a31dbbbdd5768392c44
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694887"
---
# <a name="microsoft-365-monitoring-and-self-healing"></a>Microsoft 365-övervakning och själv återställning

Med hänsyn till omfattningen av Microsoft 365 skulle det vara omöjligt att skydda kund data på ett säkert sätt från skadlig program vara utan inbyggd övervakning som är omfattande, aviseringar som är intelligenta och själv återställning och som är snabbt och tillförlitligt. Det är mycket utmanande att övervaka en uppsättning tjänster på skalan från Microsoft 365. Nya mindsets och metoder som behövs för att introduceras och helt nya uppsättningar teknik som behövs för att skapa och hantera tjänsten i en ansluten global miljö. Vi har flyttat från den traditionella övervakningen av data insamling och filtrering för att skapa aviseringar till en metod som baseras på data analys. ta fram signaler och skapa förtroende för dessa data och Använd sedan Automation för att återställa eller lösa problemet. Den här metoden hjälper till att ta bort återställnings ekvationen, som i sin tur gör att det blir billigare, snabbare och mindre fel. 

Grunderna till Microsoft 365 Monitoring är en samling tekniker som omfattar vår data Insights-motor, som bygger på Azure-, SQL Azure-och [Open-source-databas teknologi](https://cassandra.apache.org/). Det är utformat för att samla in och sammanställa data och nå slut satser. För närvarande bearbetar den fler än 500 000 000 händelser per timme från fler än 100 000 servrar (~ 15 TB per dag) indelat på dussin tals Data Center i många regioner och dessa nummer växer. 

Microsoft 365 använder *övervakning utanför*programmet, som innebär att du kan skapa syntetiska transaktioner för att testa allting som är viktigt. I till exempel Exchange Online testar varje databas var som helst i världen var som helst i alla fem minuter, vilket ger nära kontinuerlig täckning av allt som finns i systemet. Från flera 250 000 000 platser utförs test transaktioner per dag för att skapa en robust original plan eller pulsslag för tjänsten. 

I Microsoft 365 används dessutom begreppet *röd varning*som förminskar alla övervaknings signaler från alla datorer i våra data Center till något som kan hanteras av människa. Konceptet är ganska enkelt: om något händer på flera signaler måste det finnas något att vänta. Den är inte till för att kunna skapa förtroendet för en signal, den är på att ha rimlig åter givning för varje signal så att du får större precision. Det här övervaknings systemet är så kraftfullt att vi inte har personal för att titta på våra skärmar; allt vi har är de maskiner som vaknar sig om ett problem upptäcks, då kommer den att placera den lämplige samtals personalen, eller oftare, så att du kan lösa problemet. När vi börjar samla in signaler och bygga ut röda aviseringar kan vi starta triangulating på alla våra tjänst-partitioner. 

Den här aviseringen anger exakt vilka komponenter som kan ha ett problem och att systemet ska försöka åtgärda problemet genom att starta om en server för post lådor, baserat på kombinationen av varningen och de röda varningarna. 

Förutom själv återställnings funktioner som återställning med en enda sida inkluderar Exchange Online flera funktioner som gör det enkelt att övervaka och sköta den själv återställning som fokuserar på att bevara slut användar upplevelsen. De här funktionerna inkluderar *hanterad tillgänglighet*, som innehåller inbyggda övervaknings-och återställnings åtgärder och AutoReseed, som automatiskt återställer databasens redundans efter ett diskfel. 

## <a name="managed-availability"></a>Hanterad tillgänglighet 

Hanterad tillgänglighet tillhandahåller en ursprunglig hälso kontroll och återställning som övervakar och skyddar slutanvändarens upplevelse genom återställnings åtgärder. Hanterad tillgänglighet är integrationen av inbyggda kontroll-och återställnings åtgärder med plattformen för Exchange med hög tillgänglighet. Det är utformat för att upptäcka och återställa problem så fort de inträffar och upptäcks av systemet. Till skillnad från tidigare externa övervaknings lösningar och teknik för Exchange försöker inte hanterad tillgänglighet att identifiera eller förmedla orsaken till ett problem. I stället är det fokuserat på återställnings aspekter som riktar sig till tre viktiga delar av slut användar upplevelsen:

- **Availability** -kan användare komma åt tjänsten? 
- **Fördröjning** – hur är upplevelsen för användarna? 
- **Fel** – kan användarna få veta vad de vill ha? 

Hanterad tillgänglighet är en intern funktion som körs på alla Microsoft 365-servrar med Exchange Online. Den avsöker och analyserar hundratals hälso mått varje sekund. Om något är fel, så är det mesta möjliga att åtgärda det. Men det kommer alltid att finnas problem som hanterad tillgänglighet inte kommer att kunna åtgärda just nu. I de fallen eskalerar Managed Availability problemet till en support grupp för Microsoft 365 via händelse loggning.

## <a name="autoreseed"></a>AutoReseed

Exchange Online-servrar distribueras i en konfiguration som lagrar flera databaser och deras logg strömmar på samma icke-RAID-disk. Denna konfiguration kallas ofta *bara för en mängd olika diskar* (JBOD) eftersom inga mekanismer för redundans, till exempel RAID, används för att duplicera data på disken. När en disk havererar i en JBOD-miljö förloras data på disken. 

Med hänsyn till storleken på Exchange Online och det faktum att det är miljon tals hård diskar är det vanligt att disk enheter havererar i Exchange Online. I verkligheten är mer än 100 fel varje dag. När en disk slutar fungera i en lokal företags distribution måste en administratör manuellt ersätta den felaktiga disken och återställa de data som påverkas. I en distribution med moln är det varken praktiskt eller ekonomiskt genomförbart 365 att ersätta diskar med operatörer (moln administratörer) manuellt. 

Automatisk omdirigering, eller *AutoReseed*, är en funktion som ersätter vad som normalt är en nödvändig operator som svar på ett diskfel, databas skador eller andra problem som kräver omdirigering av en databas kopia. AutoReseed är utformat för att automatiskt återställa databasens redundans efter ett diskfel med reserv diskar som har etablerats på systemet. Om en disk havererar kommer de databas kopior som lagras på den disken automatiskt att dirigeras om till en förkonfigurerad reserv disk på servern och därmed återställa redundans. 