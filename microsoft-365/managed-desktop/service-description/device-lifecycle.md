---
title: Microsoft Managed Desktop produktlivscykel
description: I det här avsnittet visas enhetsspecifikationer som används i Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: b65724a1eee35149d473fb69ff646b5ef5751b2c
ms.sourcegitcommit: 1883a103449d7b03d482228bd9ef39a7caf306cf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/10/2020
ms.locfileid: "42805643"
---
# <a name="microsoft-managed-desktop-product-lifecycle"></a>Microsoft Managed Desktop produktlivscykel

Microsoft Managed Desktop gynnar slutanvändare som försäkrar att de alltid använder enheter som erbjuder bästa prestanda, tillförlitlighet, design och säkerhetsfunktioner (till exempel stöd för funktioner som Windows Hello). För att åstadkomma detta upprätthåller Microsoft Managed Desktop en kort katalog med kontinuerligt uppdaterade [godkända enheter](device-list.md). 
 
I det här avsnittet beskrivs livscykeln för enheter när de läggs till och tas bort från den godkända katalogen. 

> [!NOTE]
> I det här avsnittet gör vi en åtskillnad mellan en "enhet" och en "produkt". Med "enhet", menar vi en enskild, specifik dator. "Serienummer 1234", "Bills bärbara dator", "Delad VIRTUELL XYZ" refererar till specifika enheter. En "produkt" avser dock en samling eller en familj av enheter. Till exempel "Fabrikam Laptop", "Adatum ZX450 Laptop", etc. Detta är viktigt eftersom produkter läggs till i vår [godkända lista,](device-list.md)eller katalog, och enheter är det som får registreras i Microsoft Managed Desktop.

## <a name="product-lifecycle"></a>Produktens livscykel

 I allmänhet rör sig produkterna genom dessa livscykelfaser:

- [Produktrelease och utvärdering](#product-release-and-evaluation)
- [Perioden för primär tillgänglighet för produkter](#product-primary-availability-period)
- [Produktrespitperiod](#product-grace-period)
- [Produktpensionering](#product-retirement)


Den här bilden visar hela sekvensen:

![livscykeltidslinje: börjar med produktens allmänna tillgänglighet, "primär tillgänglighet" varar i två år. Under denna tid slutar certifieringsfönstret och någon gång är enheten ombord. I slutet av den primära tillgängligheten arkiveras produkten och "respitperioden" på tre år börjar. Från och med när enheten är ombord har den en 3-årsperiod av användning tills den tas bort från ledningen. I slutet av respitperioden tar vi bort produkten från katalogen.](../../media/non-dark1-edits.PNG)

Produkter finns kvar i katalogen i upp till 24 månader, men <em>enheterna</em> är fortfarande under förvaltning i 3 år baserat på deras individuella registreringsdatum. Effektivt, varje produkt har tre viktiga datum, men varje enhet har bara en. För produkter beräknas alla tre av dessa datum baserat på <em>godkännandedatumet</em>, och därför publicerar vi dessa datum efter godkännande så att du alltid kan se framåt och planera på lämpligt sätt för produktens hela livscykel.

Den här tabellen visar exempeldatum för en teoretisk produkt:


|Produkt  |Godkänt datum  |på primär tillgänglighet  |på stödberättigandet  |
|---------|---------|---------|---------|
|Fabrikam Bärbar dator    | 1/1/2017 | 6/1/2019 | 6/1/2022 |
|Adatum Bärbar dator   | 1/1/2018 | 6/1/2020 | 6/1/2023  |

Den här tabellen visar exempeldatum för teoretiska *enheter:*


|Enhets-ID  |Registreringsdatum  |Datum för pensionering  |
|---------|---------|---------|
|Bärbar dator #123412     |  2/3/2018       |  2/3/2021       |
|Skrivbord #321513     | 6/2/2018        |  6/2/2021       |


## <a name="product-release-and-evaluation"></a>Produktrelease och utvärdering

Produktens livscykel börjar när en tillverkare offentliggör produkten:

![livscykeltidslinje som visar utgivnings- och utvärderingsperiod](../../media/non-dark3-edits.PNG)

Under det här steget gör Microsoft Managed Desktop-teknikteamet sin utvärdering och certifiering av en produkt. Teamet utvärderar saker som tillförlitlighet och prestanda med Windows, överensstämmelse med en maskinvarubaslinje, marknadssentiment och lager- och kanalberedskap, bland annat. Den här processen tar vanligtvis cirka 6 veckor.
  
Microsoft Managed Desktop utvärderar endast enheter för certifiering inom de första 6 månaderna efter tillgänglighet. Detta säkerställer att vi alltid fokuserar våra ansträngningar på den senaste generationen av hårdvara.
 
I slutet av den här fasen lägger Microsoft Managed Desktop till produkten i den [godkända listan](device-list.md)och släpper produkten effektivt för kundregistreringar. Oavsett det datum då en enhet är certifierad är det **godkända datumet** retroaktivt till produktens eget allmänna tillgänglighetsdatum. 


## <a name="product-primary-availability-period"></a>Perioden för primär tillgänglighet för produkter

Denna period är kärnan i produkttillgängligheten:

![livscykeltidslinje som visar primär tillgänglighet](../../media/non-dark4-edits.PNG)

Alla enheter som registrerats under den här perioden får hela tre års support från Microsoft Managed Desktop (som visas av den blå tidslinjen). Den här perioden varar till ett slutdatum satt till 24 månader från det allmänna tillgänglighetsdatumet.

Du kan tänka på denna period så effektivt "öppen registrering", så för att maximera värdet på Microsoft Managed Desktop, bör du rikta dina inköpsmodeller och utvalda produkter att falla inom denna period. Som ett litet exempel bör en kund undvika att lösa en tvåårig utrullningsperiod med hjälp av en produkt som är i sin sista månad med primär tillgänglighet – de flesta av dessa enheter kommer inte att få hela tre år av Microsoft Managed Desktop-hantering (se [respitperiod](#product-grace-period) för mer information).  

## <a name="product-grace-period"></a>Produktrespitperiod

Produktens respitperiod är en treårsperiod efter primär tillgänglighet. Med den här fasen kan du registrera enheter som kommer från en produktfamilj som stöds, men som fortfarande håller fast vid löftena från Microsoft Managed Desktop om modern maskinvara och enhetsprestanda. Den här fasen är idealisk för kunder som har fattat upphandlingsbeslut innan de känner till Microsoft Managed Desktop. 

Om du nyligen har köpt ett antal godkända enheter innan du registrerar dig med Microsoft Managed Desktop kan du fortfarande registrera dem, men du får inte hela tre års hantering. Istället kommer de att falla ur överensstämmelse på pensionsdatum, oavsett när de var inskrivna. Bakom kulisserna behandlar Microsoft Managed Desktop dessa enheter som om de var inskrivna på den sista dagen av primär tillgänglighet. I den här bilden kan du se det här scenariot genom att notera att både den blå och gröna enheten slutar samma dag, trots deras ettårsskillnad i registreringen:


![livscykeltidslinje som visar respitperiod](../../media/non-dark2-edits.PNG)

Exempelpå Fabrikam Laptop från föregående tabell illustrerar den här situationen: 

|Produkt  |Godkänt datum  |på primär tillgänglighet  |på stödberättigandet  |
|---------|---------|---------|---------|
|Fabrikam Bärbar dator    | 6/1/2017 | 6/1/2019 | 6/1/2022 |

Som kund kan du registrera Fabrikam bärbara datorer hela vägen fram till 6/1/2022 – men de kommer alla att behandlas som om du registrerade dem den 6/1/2019. Om du registrerar en Fabrikam Laptop den 6/1/2021 får du bara ett års hantering. Med den här principen kan du extrahera partiella livscykler från produkter som tidigare har stöd, i stället för att behöva skaffa nya enheter i förtid. 

Slutligen, under den här fasen enheten tas bort från [enhetslistan](device-list.md) och flyttas till den [arkiverade enhetslistan](archived-device-list.md).


## <a name="product-retirement"></a>Produktpensionering

Produktpensionering är livscykelns slutfas. I den här fasen kan inga nya enheter av den produkttypen registreras i Microsoft Managed Desktop och per definition ligger alla befintliga enheter nu utanför deras tillåtna treårsperiod. Under den här tiden tar Microsoft Managed Desktop bort enheten från den offentliga listan helt. Det är också under den här fasen där du, om du inte redan har upphandlat ersättare, börjar se minskade tjänster när Microsoft Managed Desktop börjar rampa ner på de enheter som inte uppfyller kraven. 

## <a name="devices-that-are-out-of-compliance"></a>Enheter som inte uppfyller kraven

En enhet är inte i överensstämmelse när det tillåtna fönstret för Microsoft Managed Desktop-hantering har förflutit. Detta inträffar när enheten har nått tre års hantering eller när produkttypen tas bort från enhetskatalogen, beroende på vilket som inträffar först. Du bör alltid inrikta dina anskaffningscykler så att nya enheter distribueras innan aktuella enheter går ut ur efterlevnaden.

Microsoft Managed Desktop-teamet vet att anskaffningscykler na är långa och planerade kring tidskrävande budgetar. För att säkerställa att du alltid är medveten om tillståndet för din enhetspopulation tillhandahåller vi en [webbplats](https://aka.ms/mmdportal) som listar alla enheter under hantering, ålder och status som anger dess efterlevnad. Det innebär att du alltid har den senaste informationen om enhetsålder och kan använda rapporten i alla anskaffningsplaneringscykler. 







