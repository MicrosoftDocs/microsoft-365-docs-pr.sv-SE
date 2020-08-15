---
title: Data återhämtning i Microsoft 365
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
description: I den här artikeln lär du dig mer om design och principer för data återhämtning och återställning i Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a0e6ca643fe9842a71102fbabd3c05324ba52b70
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694509"
---
# <a name="data-resiliency-in-microsoft-365"></a>Data återhämtning i Microsoft 365

Med tanke på den komplexa karaktären hos molnbaserade datorer är Microsoft mindful att det inte är ett problem med att det inte går att logga in, men i stället. Vi utformar våra moln tjänster för att maximera tillförlitligheten och minimera de negativa följderna av kunderna när saker gör fel. Vi har flyttat över den traditionella strategin för att lita på komplex fysisk infrastruktur och vi har inbyggd redundans direkt i våra moln tjänster. Vi använder en kombination av mindre komplex fysisk infrastruktur och mer intelligent program vara som skapar data återhämtning till våra tjänster och ger våra kunder hög tillgänglighet. 

## <a name="resiliency-and-recoverability-are-built-in"></a>Återhämtning och återställande är inbyggda 

Att bygga in återhämtning och återhämtning börjar med antagandet att underliggande infrastruktur och processer inte kan genomföras på något ställe: maskin vara (infrastruktur) kommer inte att fungera, och program varan får fel. Det skulle vara fel att säga att program varu utvecklarna inte ville tänka på dessa saker innan molnet, hur dessa problem hanterades i en typisk IT-implementering var väldigt annorlunda före molnet:

- För det första, maskin vara och infrastruktur skydd var signifikant. Det här här är ett Data Center med 99,99% tillförlitlighet som behövs för att få ökad Power-och nätverks redundans och servrar har implementerats med maskinvarubaserad kluster, dubbla nät aggregat, dubbla nätverks gränssnitt och liknande. 
- Den andra, processen var ytterst viktigt. Drifts teamen innehåller rigorösa procedurer, ändra Windows infördes och det fanns ofta betydande projekt hantering. 
- För det tredje, distributionen ägde rum i en takt. Distribuera kod utan att behöva äga källan för att vänta på patch-uppdateringar och viktiga och viktiga outlay. Det enda sättet att åtgärda ett problem var dessutom att återställa. De flesta IT-organisationer distribuerar alltså bara större utgåvor för att undvika att arbetet hålls uppdaterat. 
- Till sist var de distribuerade systemen lika väl lika mycket mindre än nu när du är på gång. 

Idag förväntar sig kunderna fort löp ande innovation från Microsoft utan att kompromissa med kvalitet och det beror på orsaken till att Microsofts tjänster och program vara skapas med återhämtning och återställande i åtanke. 

## <a name="microsoft-365-data-resiliency-principles"></a>Microsoft 365-principer för data återhämtning

Återhämtning syftar på den molnbaserade tjänstens förmåga att tåla vissa typer av fel och som ännu inte är helt funktionell från kundernas perspektiv. Data återhämtning innebär att när det uppstår fel i Microsoft 365 förblir viktig kund information oförändrad och påverkas inte. I detta syfte har Microsoft 365-tjänsterna utformats kring fem särskilda återhämtnings principer:

- Det finns kritiskt och inte kritiskt data. Icke-kritiska data (till exempel om ett meddelande lästes) kan tas bort i sällsynta fel scenarier. Kritiska data (till exempel kunddata som e-postmeddelanden) bör skyddas till extrema priser. Som design mål är de levererade e-postmeddelandena alltid kritiska och saker som om ett meddelande har lästs är inte kritiskt. 
- Kopior av kunddata måste avgränsas med olika fel zoner eller så många fel domäner som möjligt (till exempel data centers, som är tillgängliga för enskilda autentiseringsuppgifter (process, server eller operatör)) för att ge fel isolering. 
- Kritiska kund uppgifter måste övervakas för att ingen del av atomabsorptionsspektrometri, konsistens, isolering, hållbarhet (sur) ska Miss lyckas. 
- Kunddata måste skyddas från skador. Den måste skannas in aktivt eller övervakas, repare ras och återskapas. 
- De flesta data förlust resultat från kund åtgärder så att kunderna kan återfå sina egna med ett GUI som gör att de kan återställa oavsiktligt borttagna objekt. 
 
Genom att utveckla våra moln tjänster till dessa principer, tillsammans med stabil testning och verifiering, kan Microsoft 365 möta och överträffa behoven hos kunder samtidigt som du säkerställer en plattform för fort löp ande innovation och förbättring. 

## <a name="related-links"></a>Relaterade länkar

- [Hantera skadade data](microsoft-365-dealing-with-data-corruption.md)
- [Skydd mot skadlig program vara och utpressnings Jan](microsoft-365-malware-and-ransomware-protection.md)
- [Övervakning och själv återställning](microsoft-365-monitoring-and-self-healing.md)
- [Data återhämtning för Exchange](microsoft-365-exchange-data-resiliency.md)
