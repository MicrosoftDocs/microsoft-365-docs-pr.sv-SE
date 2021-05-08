---
title: Microsoft Hanterat skrivbord produktens livscykel
description: I den här artikeln finns en lista över de enhetsspecifikationer som används Microsoft Hanterat skrivbord.
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a8b8abc58b82d08d004d204396cfd8e381c6303a
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245318"
---
# <a name="microsoft-managed-desktop-product-lifecycle"></a>Microsoft Hanterat skrivbord produktens livscykel

Microsoft Hanterat skrivbord att användarna alltid använder enheter som erbjuder bästa möjliga prestanda, tillförlitlighet, design och säkerhetsfunktioner (till exempel stöd för funktioner som Windows Hello). För att uppnå detta Microsoft Hanterat skrivbord en kort katalog över kontinuerligt uppdaterade godkända enheter. Du kan visa godkända enheter genom att filtrera Microsoft Hanterat skrivbord på [webbplatsen för Windows 10 Pro för företagsenheter.](https://www.microsoft.com/windowsforbusiness/view-all-devices)
 
I den här artikeln beskrivs livscykeln för enheter när de läggs till och tas bort från den godkända katalogen. 

> [!NOTE]
> I det här avsnittet görs en skillnad mellan en "enhet" och en "produkt". Med "enhet" menar vi en enskild, specifik dator. Exempelvis avser "Serienummer 1234", "Bills bärbara dator", "Shared VM XYZ" specifika enheter. En "produkt" avser emellertid en samling eller en familj av enheter. Till exempel "Fabrikam Laptop", "Adatum ZX450 Laptop", osv. Detta är viktigt eftersom produkter läggs till i vår godkända lista eller katalog, och enheter är det som registreras i Microsoft Hanterat skrivbord.

## <a name="product-lifecycle"></a>Produktens livscykel

 I allmänhet flyttas produkter genom dessa livscykelfaser:

- [Produktlansning och utvärdering](#product-release-and-evaluation)
- [Period för primär tillgänglighet för produkten](#product-primary-availability-period)
- [Respitperiod för produkt](#product-grace-period)
- [Produkten måste då avsa sig](#product-retirement)


I den här bilden visas hela sekvensen:

![livscykeltidslinje: från och med produktens allmänna tillgänglighet varar "primär tillgänglighet" i två år. Under den här tiden avslutas certifieringsfönstret och vid något tillfälle är enheten onboarded. I slutet av den primära tillgängligheten arkiveras produkten och "respitperioden" på tre år startar. Från och med att enheten är ombord har den en användningsperiod på 3 år tills den tas bort från hanteringen. I slutet av respitperioden tar vi bort produkten från katalogen.](../../media/non-dark1-edits.PNG)

Produkter finns kvar i katalogen i upp till 24 månader, <em>men</em> enheterna är fortfarande under hantering i tre år baserat på deras enskilda registreringsdatum. Varje produkt har tre viktiga datum, men varje enhet har bara ett. För produkter beräknas alla tre av <em></em>dessa datum baserat på godkännandedatumet och därför publicerar vi de här datumen vid godkännande så att du alltid kan titta i förväg och planera utifrån produktens hela livscykel.

I den här tabellen visas exempeldatum för en teoretisk produkt:


|Produkt  |Datum för godkänd  |Slut på primär tillgänglighet  |Berättigandet är slut  |
|---------|---------|---------|---------|
|Fabrikam Laptop    | 1/1/2017 | 6/1/2019 | 6/1/2022 |
|Adatum Laptop   | 1/1/2018 | 6/1/2020 | 6/1/2023  |

I den här tabellen visas exempel på datum för teoretiska *enheter:*


|Enhets-ID  |Registreringsdatum  |Retirement date  |
|---------|---------|---------|
|Bärbar #123412     |  2/3/2018       |  2/3/2021       |
|Skrivbordsversionen #321513     | 6/2/2018        |  6/2/2021       |


## <a name="product-release-and-evaluation"></a>Produktlansning och utvärdering

Produktens livscykel startar när en tillverkare offentligt släpper produkten:

![Livscykeltidslinje som visar utgivnings- och utvärderingsperiod](../../media/non-dark3-edits.PNG)

I det här skedet Microsoft Hanterat skrivbord det tekniska teamet sin utvärdering och certifiering av en produkt. Gruppen utvärderar saker som tillförlitlighet och prestanda med Windows, efterlevnad av en maskinvarubaslinje, marknadskuppen, lager- och kanalberedskap, bland annat. Processen tar normalt ungefär sex veckor.
  
Microsoft Hanterat skrivbord kommer endast att utvärdera enheter för certifiering inom de första sex månaderna av tillgängligheten. Den här principen säkerställer att vi hela tiden fokuserar vårt arbete på den senaste generationens maskinvara.
 
I slutet av den här fasen Microsoft Hanterat skrivbord till produkten i listan över godkända [och](device-list.md)frisläpper i själva verket produkten för kundregistrering. Oavsett vilket datum när en enhet  certifierats är dess godkända datum indaterat till produktens egna datum för allmän tillgänglighet. 


## <a name="product-primary-availability-period"></a>Period för primär tillgänglighet för produkten

Den här perioden är kärnan i produkttillgänglighet:

![Livscykeltidslinje som visar primär tillgänglighet](../../media/non-dark4-edits.PNG)

Alla enheter som registreras under den här perioden får fullständigt stöd under tre års support från Microsoft Hanterat skrivbord (som visas på den blå tidslinjen). Den här perioden varar till ett slutdatum som anges till 24 månader från det allmänna tillgänglighetsdatumet.

Du kan tänka på den här perioden som effektivt "öppen registrering", så att du kan maximera värdet i Microsoft Hanterat skrivbord genom att rikta in dina anskaffningsmodeller och utvalda produkter på att hamna under den här perioden. Som ett litet exempel bör du undvika att sätta in en period på två år med en produkt som är i den sista månaden av primär [](#product-grace-period) tillgänglighet – de flesta av dessa enheter kommer inte att få de tre åren av hantering av Microsoft Hanterat skrivbord (mer information finns i respitperioden).  

## <a name="product-grace-period"></a>Respitperiod för produkt

Respitperioden för produkten är tre år efter den primära tillgängligheten. I den här fasen kan du registrera enheter som kommer från en produktfamilj som stöds, men du kan fortfarande hålla fast vid vad Microsoft Hanterat skrivbord med avseende på modern maskinvara och prestanda på enheter. Den här fasen är perfekt för kunder som har fatta inköpsbeslut innan de vet om Microsoft Hanterat skrivbord. 

Om du nyligen har köpt godkända enheter innan du registrerar dig med Microsoft Hanterat skrivbord kan du fortfarande registrera dem, men du får inte hela tre års hantering. I stället gäller inte efterlevnadsvillkoren på återskrivningsdatumet, oavsett när de registrerades. Bakom kulisserna behandlar Microsoft Hanterat skrivbord dessa enheter som om de registrerades den sista dagen av primär tillgänglighet. I den här bilden kan du se det här scenariot genom att se att både den blå och gröna enheten slutar samma dag, trots en årsskillnad i registrering:


![Livscykeltidslinje som visar respitperiod](../../media/non-dark2-edits.PNG)

Fabrikam Laptop-exemplet från föregående tabell visar den här situationen: 

|Produkt  |Datum för godkänd  |Slut på primär tillgänglighet  |Berättigandet är slut  |
|---------|---------|---------|---------|
|Fabrikam Laptop    | 6/1/2017 | 6/1/2019 | 6/1/2022 |

Som kund kan du registrera Fabrikam Laptops hela vägen fram till 2022-06-01 – men de behandlas som om du registrerade dem 2019-06-01. Om du registrerar en Fabrikam Laptop 2021-06-01 får du bara ett års hantering. Med den här principen kan du extrahera delar av livscykler från produkter som tidigare fanns stöd, i stället för att behöva skaffa nya enheter i tid. 

Under den här fasen tas enheten slutligen bort från [enhetslistan och](device-list.md) flyttas till listan [över arkiverade enheter.](archived-device-list.md)


## <a name="product-retirement"></a>Produkten måste då avsa sig

Produktens avslutande är den sista fasen av livscykeln. I den här fasen kan inga nya enheter av den produkttypen registreras i Microsoft Hanterat skrivbord och som definition är alla befintliga enheter nu utanför deras tillåtna treårs period. Under tiden tas Microsoft Hanterat skrivbord bort enheten från den offentliga listan helt och hållet. Det är också under den här fasen där du, om du inte redan införskaffat ersättning, börjar se försämrade tjänster när Microsoft Hanterat skrivbord börjar komma igång på de enheter som inte uppfyller alla efterlevnadskrav. 

## <a name="devices-that-are-out-of-compliance"></a>Enheter som inte uppfyller efterlevnadsvillkoren

Efterlevnad gäller inte för en enhet när dess tillåtna fönster för Microsoft Hanterat skrivbord hantering har förflutit. Den här situationen inträffar när enheten har uppnått tre års hantering eller när den produkttypen tas bort från enhetskatalogen, beroende på vilket som inträffar först. Du bör alltid rikta cykler mot anskaffning så att nya enheter distribueras innan de aktuella enheterna uppfyller efterlevnadsvillkoren.

Den Microsoft Hanterat skrivbord vet att cykler för anskaffning är långa och planerade kring långvariga budgetar. För att säkerställa att du alltid är medveten om statusen för din enhets population tillhandahåller vi en webbplats som listar alla enheter under hantering, dess ålder och en status som anger dess efterlevnad. [](https://aka.ms/mmdportal) Webbplatsen hjälper dig att alltid ha den senaste informationen om enhetens ålder och kan använda rapporten i alla planeringscykeln för inköp. 







