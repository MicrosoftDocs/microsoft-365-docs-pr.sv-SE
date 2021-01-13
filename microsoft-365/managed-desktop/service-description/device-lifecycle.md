---
title: Produkt livs cykel för Microsoft Managed Desktop
description: I den här artikeln finns en lista med de specifikationer som används på Microsoft Managed Desktop.
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 75e6c2853a0ff41efdf7d5639f675927f3b95ea4
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841205"
---
# <a name="microsoft-managed-desktop-product-lifecycle"></a>Produkt livs cykel för Microsoft Managed Desktop

Microsoft Managed Station ära datorer gör det möjligt för användare att alltid använda enheter som erbjuder bästa prestanda, tillförlitlighet, design och säkerhets kapacitet (till exempel support för funktioner som Windows Hello). Det här kan du göra genom att Microsoft Managed Desktop hanterar en kort katalog med kontinuerligt uppdaterade [godkända enheter](device-list.md). 
 
I den här artikeln beskrivs enheternas livs cykel när de läggs till och tas bort från den godkända katalogen. 

> [!NOTE]
> I det här avsnittet ska vi skilja mellan en "enhet" och en "produkt". Med "enhet" innebär detta en person, specifik dator. Till exempel "seriellt nummer 1234", "Bill ' s laptop", "Shared VM XYZ" refererar till specifika enheter. En "produkt" refererar emellertid till en samling eller en familj av enheter. Till exempel "Fabrikam laptop", "adatum ZX450 laptop" osv. Det är viktigt eftersom produkter läggs till i vår [godkända lista](device-list.md)eller katalog och enheter är de som finns registrerade på Microsoft Managed Desktop.

## <a name="product-lifecycle"></a>Produktens livscykel

 Vanligt vis rör sig produkterna i dessa livscykler:

- [Produkt lansering och utvärdering](#product-release-and-evaluation)
- [Primär tillgänglighets period för produkten](#product-primary-availability-period)
- [Respittid för produkter](#product-grace-period)
- [Produkt Pension](#product-retirement)


Den här bilden visar hela sekvensen:

![tids linje för livs cykel: att börja med produktens allmänna tillgänglighet, varar i två år. Under den här tiden är certifierings fönstret slut och vid viss tidpunkt är enheten indriven. Vid slutet av primär tillgängligheten arkiveras produkten och "respitperioden" för tre år börjar. Med början när enheten är uppkopplad, har den en 3-års period för användning tills den tas bort från ledningen. I slutet av respitperioden tar vi bort produkten från katalogen.](../../media/non-dark1-edits.PNG)

Produkterna finns kvar i katalogen i upp till 24 månader, men <em>enheter</em> kan fortfarande vara under hantering för tre år baserat på deras enskilda registrerings datum. Varje produkt har dessutom tre viktiga datum men varje enhet har bara en. För produkter beräknas alla tre dessa datum utifrån <em>godkännande datum</em>och därför publicerar vi dessa datum vid godkännandet så att du alltid kan se upp och planera lämpligt för hela livs cykeln.

I den här tabellen visas exempel datum för en teoretisk produkt:


|Produkt  |Godkänt datum  |Slut på primär tillgänglighet  |Slut på berättigande  |
|---------|---------|---------|---------|
|Fabrikam bärbar dator    | 1/1/2017 | 6/1/2019 | 6/1/2022 |
|Adatum bärbar dator   | 1/1/2018 | 6/1/2020 | 6/1/2023  |

I den här tabellen visas exempel datum för teoretiska *enheter*:


|Enhets-ID  |Registrerings datum  |Pensions datum  |
|---------|---------|---------|
|#123412 för bärbara datorer     |  2/3/2018       |  2/3/2021       |
|Skriv bords #321513     | 6/2/2018        |  6/2/2021       |


## <a name="product-release-and-evaluation"></a>Produkt lansering och utvärdering

Produkt livs cykeln startar när en tillverkare släpper produkten allmänt:

![livscykel tids linje som visar släpp-och utvärderings period](../../media/non-dark3-edits.PNG)

Under den här fasen utför Microsoft Managed Desktop Engineering-teamet sin utvärdering och certifiering av en produkt. Teamet utvärderar saker som pålitlighet och prestanda med Windows, uppfyllt med en maskin varu bas, marknads attityd och lager-och kanal beredskap, bland annat. Den här processen tar vanligt vis ungefär sex veckor.
  
Microsoft Managed Desktop utvärderar bara enheter för certifiering inom de sex första månaderna av tillgänglighet. Den här principen ser till att vi alltid fokuserar våra ansträngningar på den senaste generationens maskin vara.
 
I slutet av den här fasen lägger Microsoft hanterat skriv bord med produkten till den [godkända listan](device-list.md)och fri släpp produkten för kund registrering. Oavsett det datum då en enhet **är godkänd, dateras den tillbaka** till produktens eget allmänna tillgänglighets datum. 


## <a name="product-primary-availability-period"></a>Primär tillgänglighets period för produkten

Den här perioden är kärnan till produkt tillgänglighet:

![livs cykel med primär tillgänglighet](../../media/non-dark4-edits.PNG)

Alla enheter som registrerats under den här perioden får de tre bästa supporterna från Microsoft Managed Desktop (som visas i den blå tids linjen). Denna period varar i ett slutdatum som infaller 24 månader efter det allmänna tillgänglighets datumet.

Du kan se den här tiden som effektivt "öppna registrering", så för att maximera värdet på Microsoft Managed Desktop bör du rikta dina inköps modeller och produkter att falla under den här perioden. Som ett litet exempel bör du undvika att kvitta en period på två år med en produkt som finns i dess slutliga månads primära tillgänglighet – de flesta av dessa enheter kommer inte att få de tre åren av Microsoft Managed Desktop Management (se [respitperioden](#product-grace-period) för mer information).  

## <a name="product-grace-period"></a>Respittid för produkter

Respittiden för produkten är en tre års period efter primär tillgänglighet. I den här fasen kan du registrera enheter som kommer från en produkt familj som stöds, men du kan fortfarande hålla fast till löftet av Microsoft Managed Desktop angående modern hård vara och enhets prestanda. Den här fasen är idealisk för kunder som har fattat beslut om offentlig upphandling innan de vet om Microsoft Managed Desktop. 

Om du nyligen har köpt godkända enheter innan du har registrerat dig hos Microsoft Managed Desktop kan du ändå registrera dem, men du får inte ett fullständigt administrations år. I stället kommer de att falla på avtiden, oavsett när de registrerades. Bakom kulisserna behandlas dessa enheter som om de var registrerade på den sista dagen med primär tillgänglighet. I den här bilden kan du se det här scenariot genom att Observera att både den blå och gröna enheten slutar på samma dag, trots en års skillnad i anmälan:


![livs cykel med tids period](../../media/non-dark2-edits.PNG)

I exemplet Fabrikam laptop från föregående tabell visas den här situationen: 

|Produkt  |Godkänt datum  |Slut på primär tillgänglighet  |Slut på berättigande  |
|---------|---------|---------|---------|
|Fabrikam bärbar dator    | 6/1/2017 | 6/1/2019 | 6/1/2022 |

Som kund kan du registrera Fabrikam-datorer på alla sätt tills 6/1/2022 – de kommer att behandlas som om du registrerade dem på 6/1/2019. Om du registrerar en dator med Fabrikam på 6/1/2021 får du bara ett års administration. Med den här principen kan du extrahera delvis livscykler från produkter som tidigare stöddes, i stället för att behöva skaffa nya enheter för tidigt. 

Under den här fasen tas enheten bort från [enhets listan](device-list.md) och flyttas till [listan med arkiverade enheter](archived-device-list.md).


## <a name="product-retirement"></a>Produkt Pension

Produkt Pension är den sista fasen i livs cykeln. I den här fasen kan inga nya enheter med den här produkt typen vara registrerade på Microsoft Managed Desktop och efter definition finns alla befintliga enheter nu utanför deras tillåtna tre års period. Under den här tiden tas enheten bort från den offentliga listan helt och hållet. Det är också under den här fasen, där, om du inte redan har gjort det, kommer du att se mindre tjänster som Microsoft Managed Desktop startar för att öka rampen på de enheter som saknar efterlevnad. 

## <a name="devices-that-are-out-of-compliance"></a>Enheter som inte uppfyller kraven

En enhet har slut på efterlevnad när dess tillåtna fönster för Microsoft Managed Desktop Management har förflutit. Den här situationen uppstår när enheten har nått tre års hantering eller när den produkt typen tas bort från enhets katalogen, beroende på vilket som inträffar först. Du bör alltid vara riktad på dina inköps cyklar, så att nya enheter distribueras före de aktuella enheterna.

Microsoft Managed Desktop-teamet vet att de uppringda serierna är långa och planerade för långsiktiga budgetar. För att se till att du alltid känner till statusen för din enhets population tillhandahåller vi en [webbplats](https://aka.ms/mmdportal) med en lista över alla enheter under hantering, dess ålder och en status som anger hur de efterlevs. Webbplatsen hjälper dig att alltid få den senaste informationen om enhetens ålder och kan använda rapporten i alla planerings planer för inköp. 







