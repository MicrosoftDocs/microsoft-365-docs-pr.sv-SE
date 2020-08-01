---
title: Microsoft Managed Desktop-produktlivscykel
description: I det här avsnittet visas enhetsspecifikationerna som används i Microsoft Managed Desktop.
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 0dee95743e0a504330ebbcc69749e41cdc96da39
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529953"
---
# <a name="microsoft-managed-desktop-product-lifecycle"></a>Microsoft Managed Desktop-produktlivscykel

Microsoft Managed Desktop gynnar slutanvändare som försäkrar att de alltid använder enheter som erbjuder bästa prestanda, tillförlitlighet, design och säkerhetsfunktioner (till exempel stöd för funktioner som Windows Hello). För att åstadkomma detta har Microsoft Managed Desktop en kort katalog med kontinuerligt uppdaterade [godkända enheter](device-list.md). 
 
I det här avsnittet beskrivs enheternas livscykel när de läggs till och tas bort från den godkända katalogen. 

> [!NOTE]
> I det här avsnittet kommer vi att göra en åtskillnad mellan en "enhet" och en "produkt". Med "enhet" menar vi en enskild, specifik dator. Till exempel "Serienummer 1234", "Bill's laptop", "Delad VM XYZ" hänvisar till specifika enheter. En "produkt" avser dock en samling eller en familj av enheter. Till exempel "Fabrikam Laptop", "Adatum ZX450 Laptop", etc. Detta är viktigt eftersom produkter läggs till i vår [godkända lista](device-list.md)eller katalog, och enheter är det som registreras på Microsoft Managed Desktop.

## <a name="product-lifecycle"></a>Produktens livscykel

 I allmänhet rör sig produkterna genom dessa livscykelfaser:

- [Produktrelease och utvärdering](#product-release-and-evaluation)
- [Produktens primära tillgänglighetsperiod](#product-primary-availability-period)
- [Produktens respitperiod](#product-grace-period)
- [Pensionering av produkter](#product-retirement)


Den här bilden visar hela sekvensen:

![livscykeltidslinje: från och med produktens allmänna tillgänglighet varar "primär tillgänglighet" i två år. Under denna tid slutar certifieringsfönstret och någon gång enheten är ombord. I slutet av den primära tillgängligheten arkiveras produkten och "respitperioden" på tre år börjar. Från och med enheten är ombord, den har en 3-års användningsperiod tills den tas bort från ledningen. I slutet av respitperioden tar vi bort produkten från katalogen.](../../media/non-dark1-edits.PNG)

Produkterna finns kvar i katalogen i upp till 24 månader, men <em>enheterna</em> är fortfarande under hantering i 3 år baserat på deras individuella registreringsdatum. Effektivt, varje produkt har tre viktiga datum, men varje enhet har bara en. För produkter beräknas alla tre dessa datum baserat på <em>godkännandedatumet,</em>och därför publicerar vi dessa datum efter godkännande så att du alltid kan se framåt och planera på lämpligt sätt för produktens hela livscykel.

I den här tabellen visas exempeldatum för en teoretisk produkt:


|Produkt  |Godkänt datum  |på primär tillgänglighet  |på behörigheten  |
|---------|---------|---------|---------|
|Fabrikam Bärbar dator    | 1/1/2017 | 6/1/2019 | 6/1/2022 |
|Adatum Bärbar dator   | 1/1/2018 | 6/1/2020 | 6/1/2023  |

I den här tabellen visas exempeldatum för teoretiska *enheter:*


|Enhets-ID  |Datum för registrering  |Pensioneringsdatum  |
|---------|---------|---------|
|Laptop #123412     |  2/3/2018       |  2/3/2021       |
|Stationär #321513     | 6/2/2018        |  6/2/2021       |


## <a name="product-release-and-evaluation"></a>Produktrelease och utvärdering

Produktens livscykel startar när en tillverkare offentliggör produkten:

![livscykeltidslinje som visar utgivnings- och utvärderingsperioden](../../media/non-dark3-edits.PNG)

Under det här skedet gör Microsoft Managed Desktop-teknikteamet utvärdering och certifiering av en produkt. Teamet utvärderar saker som tillförlitlighet och prestanda med Windows, efterlevnad av en maskinvarubaslinje, marknadssentiment och lager- och kanalberedskap, bland annat. Denna process tar vanligtvis cirka 6 veckor.
  
Microsoft Managed Desktop utvärderar endast enheter för certifiering inom de första 6 månadernas tillgänglighet. Detta säkerställer att vi alltid fokuserar våra ansträngningar på den senaste generationens hårdvara.
 
I slutet av den här fasen lägger Microsoft Managed Desktop till produkten i den [godkända listan](device-list.md)och släpper produkten effektivt för kundregistreringar. Oavsett vilket datum en enhet är certifierad är dess **godkända datum** back-daterat till produktens eget allmänna tillgänglighetsdatum. 


## <a name="product-primary-availability-period"></a>Produktens primära tillgänglighetsperiod

Denna period är kärnan i produkttillgängligheten:

![livscykeltidstidslinje som visar primär tillgänglighet](../../media/non-dark4-edits.PNG)

Alla enheter som registreras under den här perioden får hela tre års support från Microsoft Managed Desktop (vilket visas av den blå tidslinjen). Den här perioden varar till ett slutdatum som är satt till 24 månader från det allmänna tillgänglighetsdatumet.

Du kan se den här perioden som en effektiv "öppen registrering", så för att maximera värdet på Microsoft Managed Desktop bör du inrikta dina anskaffningsmodeller och utvalda produkter att omfattas av den här perioden. Som ett litet exempel bör en kund undvika att lösa en tvåårig utrullningsperiod med hjälp av en produkt som är i sin sista månad med primär tillgänglighet – de flesta av dessa enheter kommer inte att få hela tre år av Microsoft Managed Desktop-hantering (se [respitperiod](#product-grace-period) för mer information).  

## <a name="product-grace-period"></a>Produktens respitperiod

Produktens respitperiod är en treårsperiod efter primär tillgänglighet. Med den här fasen kan du registrera enheter som kommer från en produktfamilj som stöds, men ändå hålla fast vid löftena från Microsoft Managed Desktop om modern maskinvara och enhetsprestanda. Den här fasen är idealisk för kunder som har fattat upphandlingsbeslut innan de vet om Microsoft Managed Desktop. 

Om du nyligen har köpt ett antal godkända enheter innan du registrerar dig på Microsoft Managed Desktop kan du fortfarande registrera dem, men du får inte hela tre års hantering. Istället kommer de att falla ur överensstämmelse på pensionering datum, oavsett när de var inskrivna. Bakom kulisserna behandlar Microsoft Managed Desktop dessa enheter som om de registrerades den sista dagen av primär tillgänglighet. I den här bilden kan du se det här scenariot genom att notera att både den blå och den gröna enheten slutar på samma dag, trots deras ett års skillnad i registrering:


![livscykeltidslinje som visar respitperiod](../../media/non-dark2-edits.PNG)

Exemplet Fabrikam Laptop från föregående tabell illustrerar den här situationen: 

|Produkt  |Godkänt datum  |på primär tillgänglighet  |på behörigheten  |
|---------|---------|---------|---------|
|Fabrikam Bärbar dator    | 6/1/2017 | 6/1/2019 | 6/1/2022 |

Som kund kan du registrera Fabrikam-bärbara datorer hela vägen fram till 2022-06-01 – men de kommer alla att behandlas som om du registrerade dem den 6/1/2019. Om du registrerar en fabrikam-bärbar dator den 2021-06-1 får du bara ett års hantering. Med den här principen kan du extrahera partiella livscykler från produkter som tidigare stöddes, i stället för att behöva skaffa nya enheter i förtid. 

Slutligen tas enheten bort från [enhetslistan](device-list.md) under den här fasen och flyttas till listan [över arkiverade enheter](archived-device-list.md).


## <a name="product-retirement"></a>Pensionering av produkter

Produktpensionering är livscykelns slutfas. I den här fasen kan inga nya enheter av den produkttypen registreras i Microsoft Managed Desktop och per definition ligger alla befintliga enheter nu utanför den tillåtna treårsperioden. Under den här tiden tar Microsoft Managed Desktop bort enheten helt och hållet. Det är också under denna fas där du, om du inte redan har skaffat ersättningar, börjar se minskade tjänster när Microsoft Managed Desktop börjar rampa ner på de enheter som inte uppfyller kraven. 

## <a name="devices-that-are-out-of-compliance"></a>Enheter som inte uppfyller kraven

En enhet är inte förenligt när det tillåtna fönstret för Hantering av Microsoft Managed Desktop har förflutit. Detta inträffar när enheten har uppnått tre års hantering eller när den produkttypen tas bort från enhetskatalogen, beroende på vilket som inträffar först. Du bör alltid inrikta dig på dina anskaffningscykler så att nya enheter distribueras innan aktuella enheter inte uppfyller kraven.

Microsoft Managed Desktop-teamet vet att anskaffningscyklerna är långa och planerade kring tidskrävande budgetar. För att säkerställa att du alltid är medveten om tillståndet för din enhetspopulation tillhandahåller vi en [webbplats](https://aka.ms/mmdportal) som listar varje enhet som är under hantering, dess ålder och en status som anger att den uppfyller kraven. Det innebär att du alltid har den senaste informationen om enhetens ålder och kan använda rapporten i alla planeringscykler för upphandlingar. 







