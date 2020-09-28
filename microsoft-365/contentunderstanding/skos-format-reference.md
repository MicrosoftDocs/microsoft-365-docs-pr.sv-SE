---
title: SKOS format referens för SharePoint-taxonomi
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
description: SKOS format referens för SharePoint-taxonomi
ms.openlocfilehash: eb228394b06b6e6027937ab105df7c0079875226
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296235"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a>SKOS format referens för SharePoint-taxonomi

Den här artikeln innehåller RDF vokabulär som används för att representera [SharePoint-taxonomi](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) och är baserad på [SKOS](https://www.w3.org/TR/skos-primer/). För serialisering av denna RDF-syntax, Använd RDF [sköldning](https://www.w3.org/TR/turtle/).

I följande tabell visas [SKOS](https://www.w3.org/TR/skos-primer/) motsvarande [SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) -vokabulär. SharePoint har inte stöd för [SKOS](https://www.w3.org/TR/skos-primer/) -värden som inte har någon motsvarande SharePoint-taxonomi.

|SharePoint-taxonomi|SKOS motsvarande|
|:-----------------|:--------------|
|SharePoint-taxonomi: term|skos: begrepp|
|SharePoint-taxonomi: TermSet|skos:ConceptScheme|
|SharePoint-taxonomi: inTermSet|skos: inschema|
|SharePoint-taxonomi: hasTopLevelTerm|skos:hasTopConcept|
|SharePoint-taxonomi: topLevelTermOf|skos:topConceptOf|
|SharePoint-taxonomi: defaultLabel|skos:prefLabel|
|SharePoint-taxonomi: termSetName|skos:prefLabel|
|SharePoint-taxonomi: propertyName|skos:prefLabel|
|SharePoint-taxonomi: otherLabel|skos:altLabel|
|SharePoint-taxonomi: Beskrivning|skos: definition|
|SharePoint-taxonomi: överordnad|skos: bredare|
|SharePoint-taxonomi: underordnad|skos: smalare|

I följande tabell visas de enheter i SharePoint-taxonomin som härleds från [Owl](https://www.w3.org/TR/owl2-primer/).

|SharePoint-vokabulär|Härlett från OWL|
|:-----------------------------|:----------------------|
|SharePoint-taxonomi: isAvailableForTagging|owl:datatypeproperty|
|SharePoint-taxonomi: SharedCustomPropertyForTerm|owl:ObjectProperty|
|SharePoint-taxonomi: LocalCustomPropertyForTerm|owl:ObjectProperty|
|SharePoint-taxonomi: CustomPropertyForTermSet|owl:ObjectProperty|

## <a name="sharepoint-taxonomy-vocabulary"></a>SharePoint-vokabulär

En taxonomi är ett formellt klassificerings system. En taxonomi grupperar orden, etiketterna och termerna som beskriver något och sorterar sedan grupperna i en hierarki.

**SharePoint-taxonomi: term**

Representerar en term eller ett nyckelord i en hierarki med hanterade metadata.

En [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) är en Atomic-enhet i en SharePoint- [postlagring](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore). Varje [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) tillhör en [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) som tillhör en [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group). 

Syntaxen för att definiera en [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) är följande:

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

En [period](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) är obligatorisk i en [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). DefaultLabel är namnet på [termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) som det visas i den visuella presentationen. De obligatoriska fälten för definiering av en [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) är:

- SharePoint-taxonomi: defaultLabel
- SharePoint-taxonomi: inTermSet

En [period](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) kan:

- Vara hierarkiskt relaterad till en annan [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) som tillhandahålls båda [villkoren](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) tillhör samma [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).
- Har flera underordnade [termer](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), men bara en enda överordnad [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).
- Inte en definierad överordnad [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) , om den är en TopLevelTermOf en [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).
- Ha en defaultLabel [, per arbets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) postspråk.
- Inte finnas om den inte innehåller en överordnad [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)och inte heller TopLevelTermOf en [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). 
- Har bara ett unikt defaultLabel på samma hierarkiska nivå.

**SharePoint-taxonomi: TermSet**

Representerar en hierarkisk eller platt uppsättning med term objekt som kallas "TermSet".

När namnet föreslås är TermSet en uppsättning [termer](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). En [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) i en [lagrings](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) tid måste tillhöra en [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Ingen [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) kan existera oberoende. 

Syntaxen för att definiera en [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) är:

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) grupperas logiskt i [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group). Det obligatoriska fältet för att definiera en [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) är:

- SharePoint-taxonomi: termSetName

Om den termSetName som anges inte är unik i [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), lägger SharePoint ett nummer i slutet av namnet så att det är unikt för termSetName.

**SharePoint-taxonomi: hasTopLevelTerm**

SharePoint använder den här egenskapen för att mappa den översta [termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) i [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), vilket är start punkten för [termernas](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) hierarki i ett [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Det här är en inverterad relation till SharePoint-taxonomi: topLevelTermOf. 

Syntaxen för att definiera detta är:

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> Du kan inte ange [termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) på den översta nivån för en överordnad [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).

**SharePoint-taxonomi: topLevelTermOf**

SharePoint-taxonomi: topLevelTermOf är inversen till SharePoint-taxonomi: hasTopLevelTerm

Syntaxen för att definiera detta är:

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

**SharePoint-taxonomi: inTermSet**

Använd den här för att mappa en [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) till en [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). En [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) kan bara finnas i en enda [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). SharePoint kräver den här egenskapen när du [definierar en term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).

## <a name="required-labels"></a>Obligatoriska etiketter

Din organisation kanske vill göra omsorgsfull planering innan du börjar använda hanterade metadata. Hur mycket planering som måste göras beror på hur formell din taxonomi är. Det beror också på hur många kontroller du vill använda för metadata. På varje nivå i hierarkin måste du konfigurera obligatoriska LABLES för en term eller TermSet.

En term kan ha en eller flera etiketter på standard språket och noll eller fler etiketter i ett språk som inte är standard. Om termen har etiketter på ett språk måste en av etiketterna vara standard etiketten.

**SharePoint-taxonomi: defaultLabel**

Använd den här vanliga standard etiketten för en [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) som är en obligatorisk parameter för en [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). Används för att visuellt representera [termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).

Syntaxen för att definiera en defaultLabel är:

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

DefaultLabel innehåller två delar för den – strängen och språkmärkningen. Språket måste vara ett av arbets postspråken för [lagrings platsen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) . DefaultLabel måste vara unikt för alla [termer](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) i samma [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), på samma hierarkiska nivå.

**SharePoint-taxonomi: termSetName**

Hämtar och anger namnet på det aktuella TermSet-objektet.

Den här lexikala etiketten för en [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)på ett språk för [lagrings platsen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) . Det här är en obligatorisk parameter för en [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Används för att visuellt representera en [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).

Syntaxen för att definiera en termSetName är:

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

**SharePoint-taxonomi: propertyName**

Hämtar och anger egenskaps namnet för det aktuella TermSet-objektet.

Det här är lexikalisk etikett för en SharePoint-taxonomi: SharedCustomPropertyForTerm, SharePoint-taxonomi: LocalCustomPropertyForTerm och SharePoint-taxonomi: CustomPropertyForTermSet på ett arbets språk för [lagrings platsen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) .

SharePoint-taxonomin: propertyName behandlas som CustomProperty.

Syntaxen för att definiera en propetyName är:

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a>Valfria etiketter

Du kan också lägga till valfria etiketter i taxonomin.

**SharePoint-taxonomi: otherLabel**

Det här är den alternativa lexikala etiketten för en [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). 

Syntaxen för att definiera en otherLabel är:

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a>Semantiska relationer

Taxonomier har hierarkiskt och ibland en enkel "relaterad termen", men vissa har "semantiska relationer" eller egna relationer. 

**SharePoint-taxonomi: överordnad**

Det här hierarkiskt relaterar en [period](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) till [en annan.](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) En [period](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) kan vara en top level- [period](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) på en [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), men om den inte måste ha en överordnad [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). 

Syntaxen för att definiera en överordnad är:

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

Det innebär att TermA1 har ett överordnat sökord. Det innebär också att TermA1 är underordnat. Relation mellan över-och underordnade objekt är inversible-relationer.

**SharePoint-taxonomi: underordnad**

Objektet innehåller en eller flera underordnade TermSet-instanser och dessa kan nås via egenskapen TermSets. Den här klassen innehåller också metoder för att skapa nya underordnade TermSet-objekt. Behörigheter för redigering av underordnade termer och TermSet-instanser anges i gruppen. 

Det här hierarkiskt relaterar en [period](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) till [en annan.](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)

Syntaxen för att definiera ett barn är:

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

Det innebär att termen bara har underordnade TermA1. Det innebär också att den termen är moder för TermA1 överordnade-underordnad relation är ett inversible-förhållande.

## <a name="documentation-notes"></a>Dokumentations anteckningar

I det här avsnittet beskrivs taxonomin i Microsoft. SharePoint. taxonomi-namnrymd.

**SharePoint-taxonomi: Beskrivning**

Det här är en detaljerad förklaring av en [SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) -vokabulär för ord lista. 

Syntaxen för att lägga till en beskrivning är:

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a>Anpassade egenskaper

Hämtar de egna egenskaps objekten för det aktuella term objekt från den skrivskyddade ord listan.

Anpassade egenskaper är par med nyckelord som du kan definiera för en [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) eller en [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), för att få mer information om [termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) eller en [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). SharePoint anger nyckel för den anpassade egenskapen med hjälp av propertyName.

**SharePoint-taxonomi: CustomPropertyForTermSet**

Syntaxen för att definiera detta är:

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

**SharePoint-taxonomi: SharedCustomPropertyForTerm**

Om den anpassade egenskapen för en [period](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) måste flyttas tillsammans med [termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)när du återanvänder [termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) någon annan, måste du ange den under SharedCustomPropertyForTerm.

Syntaxen för att definiera detta är:

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
**SharePoint-taxonomi: LocalCustomPropertyForTerm**

Om den anpassade egenskapen för en [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) inte behöver transporteras tillsammans med [termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)när du återanvänder [termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) någon annan, måste du definiera den under LocalCustomPropertyForTerm.

Syntaxen för att definiera detta är:

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a>Data egenskaper

På varje nivå i hierarkin kan du konfigurera särskilda data egenskaper för en term eller TermSet.

**SharePoint-taxonomi: isAvailableForTagging**

Använd det här alternativet för att ange om en [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) eller en [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) ska vara tillgänglig i SharePoint-listor och-bibliotek.  

Syntaxen för det här är:

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a>Domän och område

Tabellen nedan beskriver domän och räckvidd för SharePoint-taxonomi.

|Predikat/verb|Särdirektiv|Domän|Område|
|:--------------|:------|:-----|:----|
inTermSet|I term uppsättning|Kortsiktig|Term uppsättning|
inTermGroup|Gruppen term|TermSet|TermGroup|
topLevelTermOf|Är den översta nivån för|Kortsiktig|TermSet|
hasTopLevelTerm|Har den översta nivån|Term uppsättning|Kortsiktig|
termSetName|Term uppsättningen har namn|Kortsiktig|Vanlig literal|
defaultLabel|Termen har standard etikett|Kortsiktig|Vanlig literal|
otherLabel|Termen har en annan etikett|Kortsiktig|Vanlig literal|
propertyName|Har egenskaps etikett|SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet |Boolesk, sträng, heltal, decimal, dubbel|
|beskrivning|Har Beskrivning|Alla|Vanlig literal|
|objektet|Har förälder|Kortsiktig|Kortsiktig|
|element|Har underordnade|Kortsiktig|Kortsiktig|
|isAvailableForTagging|Är tillgängligt för taggning|Period, term uppsättning|Boolesk|
|SharedCustomPropertyForTerm|Har en delad egenskap|Kortsiktig|Boolesk, sträng, heltal, decimal, dubbel|
|LocalCustomPropertyForTerm|Har lokal anpassad egenskap|Kortsiktig|Boolesk, sträng, heltal, decimal, dubbel|
|CustomPropertyForTermSet|Har anpassad egenskap|TermSet|Boolesk, sträng, heltal, decimal, dubbel|

[SKOS](https://www.w3.org/TR/skos-primer/) giltiga scenarier som [SharePoint-taxonomi](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) inte tillåter:

- Hierarkisk redundans-ett [SKOS](https://www.w3.org/TR/skos-primer/) koncept kan kopplas till flera bredare koncept samtidigt, men en SharePoint-taxonomi: termen kan bara innehålla en SharePoint-taxonomi: Parent, och därför är cykliskt beroende av termer inte tillåtet.
- Det går inte att använda ägarlösa termer i SharePoint-taxonomi. Varje SharePoint-taxonomi: termen ska ha en SharePoint-taxonomi: Parent eller så ska den vara SharePoint-taxonomi: topLevelTermOf en TermSet.
- SharePoint-taxonomi stöder inte associerade relationer.
- SharePoint-taxonomi tillåter bara två typer av hierarkiska relationer – SharePoint-taxonomi: Parent och SharePoint-taxonomi: underordnad. 
- Till skillnad från [SKOS](https://www.w3.org/TR/skos-primer/) i hierarkin i SharePoint är det bara möjligt att fastställa villkor i samma termset.

## <a name="see-also"></a>Se även

[Importera en term uppsättning med ett SKOSt format](import-term-set-skos.md)

