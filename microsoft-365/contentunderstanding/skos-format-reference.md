---
title: SKOS formatreferens för SharePoint-taxonomi
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: SKOS formatreferens för SharePoint-taxonomi
ms.openlocfilehash: 6a565de9598706e998206304093ed86a1a55704d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911180"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a>SKOS formatreferens för SharePoint-taxonomi

I den här artikeln finns ordlista för RDF som används för att representera [SharePoint-taxonomi](/dotnet/api/microsoft.sharepoint.taxonomy) och som baseras på [SKOS](https://www.w3.org/TR/skos-primer/). Om du vill serialisera RDF använder du RDF [Sköldpadda](https://www.w3.org/TR/turtle/).

I följande tabell visas de [SKOS](https://www.w3.org/TR/skos-primer/) motsvarigheter till vokabulär i [SharePoint-taxonomi](/dotnet/api/microsoft.sharepoint.taxonomy). SharePoint har inte stöd för [SKOS](https://www.w3.org/TR/skos-primer/)-värden som inte har någon motsvarighet i SharePoint-taxonomi.

|SharePoint-taxonomi|Motsvarighet i SKOS|
|:-----------------|:--------------|
|sharepoint-taxonomi:Term|skos:Concept|
|sharepoint-taxonomi:TermSet|skos:ConceptScheme|
|sharepoint-taxonomi:inTermSet|skos:inSchema|
|sharepoint-taxonomi:hasTopLevelTerm|skos:hasTopConcept|
|sharepoint-taxonomi:topLevelTermOf|skos:topConceptOf|
|SharePoint-taxonomi:defaultLabel|skos:prefLabel|
|sharepoint-taxonomi:termSetName|skos:prefLabel|
|sharepoint-taxonomi:propertyName|skos:prefLabel|
|sharepoint-taxonomi:otherLabel|skos:altLabel|
|sharepoint-taxonomi:description|skos:definition|
|sharepoint-taxonomi:parent|skos:broader|
|sharepoint-taxonomi:child|skos:narrower|

I följande tabell visas de enheter i SharePoint-taxonomivokabulär som härleddes från [OWL](https://www.w3.org/TR/owl2-primer/).

|SharePoint-taxonomivokabulär|Härledd från OWL|
|:-----------------------------|:----------------------|
|sharepoint-taxonomi:isAvailableForTagging|owl:datatypeproperty|
|sharepoint-taxonomi:SharedCustomPropertyForTerm|owl:ObjectProperty|
|sharepoint-taxonomi:LocalCustomPropertyForTerm|owl:ObjectProperty|
|sharepoint-taxonomi:CustomPropertyForTermSet|owl:ObjectProperty|

## <a name="sharepoint-taxonomy-vocabulary"></a>SharePoint-taxonomivokabulär

En taxonomi är ett formellt klassificeringssystem. En taxonomi grupperar ord, etiketter och termer som beskriver något och sedan ordnar grupper i en hierarki.

**sharepoint-taxonomi:Term**

Representerar en term eller ett nyckelord i en hierarki med hanterade metadata.

En [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) är den atomiska enheten i en SharePoint [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore). Varje [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) tillhör en [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) som tillhör ett [TermGroup](/dotnet/api/microsoft.sharepoint.taxonomy.group). 

Syntaxen för att definiera en [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) är följande:

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

En [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) existerar obligatoriskt i ett [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset). DefaultLabel är namnet på [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)en som det visas i den visuella presentationen. De obligatoriska fälten för att definiera en [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) inkluderar:

- SharePoint-taxonomi:defaultLabel
- sharepoint-taxonomi:inTermSet

En [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) kan:

- Vara hierarkiskt relaterad till en annan [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) om båda [Termerna](/dotnet/api/microsoft.sharepoint.taxonomy.term) tillhör samma [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).
- Ha flera underordnade [Termer](/dotnet/api/microsoft.sharepoint.taxonomy.term) men bara en överordnad [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).
- Inte har någon överordnad [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) definierad om det är en topLevelTermOf ett [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).
- Ha en defaultLabel, per [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) arbetsspråk.
- Inte finnas om den varken innehåller en överordnad [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) eller är topLevelTermOf ett [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset). 
- Har bara ett unikt defaultLabel på samma hierarkiska nivå.

**sharepoint-taxonomi:TermSet**

Representerar en hierarkisk eller platt uppsättning termobjekt som kallas "TermSet".

Som namnet antyder är TermSet en uppsättning [Termer](/dotnet/api/microsoft.sharepoint.taxonomy.term). En [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) i en [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) måste tillhöra ett [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset). Ingen [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) kan finnas oberoende. 

Syntaxen för att definiera en [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) är:

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

[TermSets](/dotnet/api/microsoft.sharepoint.taxonomy.termset) är logiskt grupperade i [TermGroups](/dotnet/api/microsoft.sharepoint.taxonomy.group). Det obligatoriska fältet för att definiera en [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) är:

- sharepoint-taxonomi:termSetName

Om den termSetName som anges inte är unik i [TermGroup](/dotnet/api/microsoft.sharepoint.taxonomy.group) lägger SharePoint till en siffra i slutet av namnet för att upprätthålla unikheten i termSetName(s).

**sharepoint-taxonomi:hasTopLevelTerm**

I SharePoint används den här egenskapen för att avbilda den översta [Termen](/dotnet/api/microsoft.sharepoint.taxonomy.term) i [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) som är startpunkten i hierarkin för [Termer](/dotnet/api/microsoft.sharepoint.taxonomy.term) i ett [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset). Det här är en inverterad relation till sharepoint-taxonomi:topLevelTermOf. 

Syntaxen för att definiera detta är:

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> Det går inte att definiera [Term på översta nivån](/dotnet/api/microsoft.sharepoint.taxonomy.term) för en överordnad [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).

**sharepoint-taxonomi:topLevelTermOf**

SharePoint-taxonomi:topLevelTermOf är inversen till sharepoint-taxonomi:hasTopLevelTerm

Syntaxen för att definiera detta är:

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

**sharepoint-taxonomi:inTermSet**

Använd det här alternativet om du vill mappen en [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) till ett [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset). En [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) kan bara finnas i en enda [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset). SharePoint kräver den här egenskapen vi [definiering av en term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).

## <a name="required-labels"></a>Obligatoriska etiketter

Din organisation kanske vill göra noggrann planering innan du börjar använda hanterade metadata. Hur mycket planering du måste utföra beror på hur formell din taxonomi är. Det beror även på hur mycket kontroll som du vill använda för metadata. På varje nivå i hierarkin måste du konfigurera obligatoriska etiketter för en Term eller ett TermSet.

En Term kan ha en eller flera etiketter i standardspråket och noll eller fler etiketter på ett annat språk än standardspråket. Om termen har etiketter på ett språk måste en av etiketterna vara standardetiketten.

**sharepoint-taxonomi:defaultLabel**

Använd den här lexikala standardetiketten för en [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) som är en obligatorisk parameter för en [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term). Används för att visuellt representera [Termen](/dotnet/api/microsoft.sharepoint.taxonomy.term).

Syntaxen för att definiera en defaultLabel är:

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

DefaultLabel innehåller två delar – strängen och språktaggen. Språket måste vara något av [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) arbetsspråk. DefaultLabel måste vara unika för alla [Termer](/dotnet/api/microsoft.sharepoint.taxonomy.term) i samma [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset), på samma hierarkiska nivå.

**sharepoint-taxonomi:termSetName**

Hämtar och anger namnet på det aktuella TermSet-objektet.

Det här är en lexikalisk etikett för en [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)i en [termStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) arbetsspråk. Det här är en obligatorisk parameter för ett [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset). Används för att visuellt representera en [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).

Syntaxen för att definiera en termSetName är:

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

**sharepoint-taxonomi:propertyName**

Hämtar och anger namnet på den aktuella TermSet-objektet.

Det här är en lexikalisk etikett för en sharepoint-taxonomi:SharedCustomPropertyForTerm, sharepoint-taxonomi:LocalCustomPropertyForTerm och sharepoint-taxonomi:CustomPropertyForTermSet i en [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) arbetsspråk.

SharePoint-taxonomi:propertyName behandlas som nyckel för CustomProperty.

Syntaxen för att definiera en propetyName är:

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a>Valfria etiketter

Du kan även lägga till valfria etiketter i din taxonomi.

**sharepoint-taxonomi:otherLabel**

Det här är den alternativa lexikala etiketten för en [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term). 

Syntaxen för att definiera en otherLabel är:

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a>Semantiska relationer

Taxonomier har hierarkiska och ibland en enkel "relaterad term" som associerande relation men vissa har "semantiska relationer" eller egendefinierade relationer. 

**sharepoint-taxonomi:parent**

Den här hierarkiska relationen relaterar en [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) till en annan [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term). En [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) kan vara en toppnivå [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) av ett [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset), men om det inte måste det finnas en överordnad [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term). 

Syntaxen för att definiera en parent är:

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

Det innebär att TermA är det överordnade objektet och TermA är det underordnade.

**sharepoint-taxonomi:child**

Objektet innehåller ett eller flera underordnade TermSet-instanser och du kan komma åt dessa via TermSets egenskaper. I den här klassen finns också metoder för att skapa nya underordnade TermSet-objekt. Behörigheter för att redigera underordnad Term och TermSet-instanser anges i gruppen. 

Den här hierarkiska relationen relaterar en [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) till en annan [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).

Syntaxen för att definiera ett child är:

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

Det innebär att TermA är det överordnade objektet och TermA är det underordnade.

## <a name="documentation-notes"></a>Dokumentationskommentarer

I det här avsnittet beskrivs taxonomin detaljerad i Microsoft. SharePoint. taxonomins namnrymd.

**sharepoint-taxonomi:description**

Det här är en detaljerad beskrivning av alla vokabulära enheter i [SharePoint-taxonomi](/dotnet/api/microsoft.sharepoint.taxonomy). 

Syntaxen för att lägga till en beskrivning är:

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a>Anpassade egenskaper

Hämtar en samling egna egenskapsobjekt för det aktuella Termobjektet från den skrivskyddade ordlistan.

Anpassade egenskaper är nyckelvärdespar som kan definieras för en [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) eller [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) för att få en beskrivning av [Termen](/dotnet/api/microsoft.sharepoint.taxonomy.term) eller [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset). I SharePoint anges nyckel för den anpassade egenskapen med hjälp av propertyName.

**sharepoint-taxonomi:CustomPropertyForTermSet**

Syntaxen för att definiera detta är:

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

**sharepoint-taxonomi:SharedCustomPropertyForTerm**

Om den anpassade egenskapen för en [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) måste följa med [Termen](/dotnet/api/microsoft.sharepoint.taxonomy.term) när du återanvänder [Termen](/dotnet/api/microsoft.sharepoint.taxonomy.term) någon annanstans måste du definiera den under SharedCustomPropertyForTerm.

Syntaxen för att definiera detta är:

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
**sharepoint-taxonomi:LocalCustomPropertyForTerm**

Om den anpassade egenskapen för en [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) inte behöver följa med [Termen](/dotnet/api/microsoft.sharepoint.taxonomy.term) när du återanvänder [Termen](/dotnet/api/microsoft.sharepoint.taxonomy.term) någon annanstans, måste du definiera den under LocalCustomPropertyForTerm.

Syntaxen för att definiera detta är:

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a>Dataegenskaper

På varje nivå i hierarkin kan du konfigurera vissa dataegenskaper för en Term eller TermSet.

**sharepoint-taxonomi:isAvailableForTagging**

Använd det här alternativet om du vill ange om en [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) eller [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) tillgänglig i SharePoint-listor och -bibliotek.  

Syntaxen för det här är:

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a>Domän och område

I tabellen nedan beskrivs domänen och intervallet för SharePoint-taxonomivokabulär.

|Predikat/verb|Betydelse|Domän|Område|
|:--------------|:------|:-----|:----|
inTermSet|I termuppsättning|Term|Termuppsättning|
inTermGroup|I termgruppen|TermSet|TermGroup|
topLevelTermOf|Är toppnivåterm för|Term|TermSet|
hasTopLevelTerm|Har en topnivåterm|Termuppsättning|Term|
termSetName|Termuppsättning har namn|Term|Enkel literal|
defaultLabel|Term har standardetikett|Term|Enkel literal|
otherLabel|Term har annan etikett|Term|Enkel literal|
PropertyName|Har egenskapsetikett|SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet |Boolesk, sträng, heltal, decimal, dubbel|
|description|Har beskrivning|Alla|Enkel literal|
|parent|Har överordnad|Term|Term|
|child|Har underordnad|Term|Term|
|isAvailableForTagging|Är tillgängligt för märkning|Term, Termuppsättning|Boolesk|
|SharedCustomPropertyForTerm|Har delad anpassad egenskap|Term|Boolesk, sträng, heltal, decimal, dubbel|
|LocalCustomPropertyForTerm|Har lokal anpassad egenskap|Term|Boolesk, sträng, heltal, decimal, dubbel|
|CustomPropertyForTermSet|Har anpassad egenskap|TermSet|Boolesk, sträng, heltal, decimal, dubbel|

[SKOS](https://www.w3.org/TR/skos-primer/) giltiga scenarier som [SharePoint-taxonomi](/dotnet/api/microsoft.sharepoint.taxonomy) inte tillåter:

- Hierarkisk redundans – ett [SKOS](https://www.w3.org/TR/skos-primer/)-konceptet kan kopplas till flera mer omfattande begrepp samtidigt men en sharepoint-taxonomi:Term kan bara ha en SharePoint-taxonomi:parent och därför är det inte heller tillåtet att använda cykliska beroenden för Termer.
- Du kan inte använda ägarlösa termer i SharePoint-taxonomi. Alla sharepoint-taxonomier:Term ska antingen ha en sharepoint-taxonomi:parent eller så bör den vara sharepoint-taxonomi:topLevelTermOf ett TermSet.
- SharePoint-taxonomi saknar stöd för associeringsrelationer.
- I SharePoint kan du bara använda 2 typer av hierarkiska relationer – sharepoint-taxonomi:parent and sharepoint-taxonomi:child. 
- Till skillnad från [SKOS](https://www.w3.org/TR/skos-primer/) kan den hierarkiska relationen i SharePoint-taxonomivokabulär bara upprättas med Termer i samma TermSet.

## <a name="see-also"></a>Se även

[Importera en termuppsättning med ett SKOS-baserat format](import-term-set-skos.md)