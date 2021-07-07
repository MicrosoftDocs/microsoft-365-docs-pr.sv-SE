---
title: Referens för anpassade typer av känslig information
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: I den här artikeln visas en lista med filter som kan kodas i anpassade typer av känslig information.
ms.openlocfilehash: 6dfa562d581f14c0b1ac41c4ce803e2367a94636
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322967"
---
# <a name="custom-sensitive-information-type-filters-reference"></a>Referens för anpassade typer av känslig information

I Microsoft kan du definiera filter eller ytterligare kontroller när du skapar anpassade typer av känslig information (SIT).

## <a name="list-of-supported-filters-and-use-cases"></a>Lista över filter som stöds och användningsfall

### <a name="alldigitssame-exclude"></a>AllDigitsSame Exclude

Beskrivning: Tillåter dig att utesluta matchningar som har alla siffror som dubblettsiffror, t.ex. 111111111 eller 111-111-111-111

Definiera filter
```xml
<Filters id="ssn_filters">
    <Filter type="AllDigitsSameFilter"></Filter>
</Filters>
```

Använda det i regelpaket på entitetsnivån
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85"  filters="ssn_filters">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

Använda det i regelpaket på mönsternivån
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="ssn_filters">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

### <a name="textmatchfilter-startswith"></a>TextMatchFilter StartsWith 

Beskrivning: Med den här funktionen kan du definiera starttecken för entiteten. Den har två varianter, inkluderar och exkluderar.

Om du till exempel vill utesluta tal som börjar med 0500, 91, 091, 010 i en lista som den här:

- 0500-4500-027
- 91564721450
- 91-8523697410
- 700-8956-7844
- 1000-3265-9874
- 0100-7892-3012

kan du använda den här xml-koden

```xml
<Filters id="phone_number_filters_exc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Exclude" textProcessorId="Keyword_false_positives_sw">
</Filter>
</Filters>

  <Keyword id="Keyword_false_positives_sw">
    <Group matchStyle="string">
      <Term>0500</Term>
      <Term>91</Term>
      <Term>091</Term>
      <Term>0100</Term>
    </Group>
  </Keyword>
```
Om du till exempel vill ta med tal som börjar med 0500, 91, 091, 0100 i en lista så här: 

- 0500-4500-027
- 91564721450
- 91-8523697410
- 700-8956-7844
- 1000-3265-9874
- 0100-7892-3012

kan du använda den här xml-koden

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-endswith"></a>TextMatchFilter EndsWith 

Beskrivning: Med den här funktionen kan du definiera sluttecken för entiteten. 

Om du till exempel vill utesluta tal som slutar med 0500 91 091, 0100 i en lista som den här:

- 1234567891
- 1234-5678-0091
- 1234.4567.7091
- 1234-8091-4564

kan du använda den här xml-koden

```xml
<Filters id="phone_number_filters_exc">
    <Filter type="TextMatchFilter" direction="EndsWith" logic="Exclude" textProcessorId="Keyword_false_positives_sw">
</Filter>

  <Keyword id="Keyword_false_positives_sw">
    <Group matchStyle="string">
      <Term>0500</Term>
      <Term>91</Term>
      <Term>091</Term>
      <Term>0100</Term>
    </Group>
  </Keyword>
```

Om du till exempel vill ta med tal som slutar med 0500, 91, 091, 0100 i en lista som den här:

- 1234567891
- 1234-5678-0091
- 1234.4567.7091
- 1234-8091-4564

kan du använda den här xml-koden

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction=" EndsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-full"></a>TextMatchFilter Full

Beskrivning: Tillåter att du förhindrar vissa matchningar för att förhindra att de utlöser regeln. Exempel: exkludera 41111111111111111 i listan med giltiga kreditkortsmatcher.

Om du till exempel vill utesluta kreditkortsnummer som 411111111111111 och 3241891031113111 i en lista så här:

- 4485 3647 3952 7352
- 4111111111111111
- 3241891031113111

kan du använda den här xml-koden

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Full" logic="Exclude" textProcessorId="Keyword_false_positives_full">
</Filter>

  <Keyword id="Keyword_false_positives_full">
    <Group matchStyle="string">
      <Term>4111111111111111</Term>
      <Term>3241891031113111</Term>
    </Group>
  </Keyword>
```

Om du till exempel vill ta med kreditkortsnummer som 411111111111111 och 3241891031113111 i en lista så här:

- 4485 3647 3952 7352
- 4111111111111111
- 3241891031113111

kan du använda den här xml-koden

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_false_positives_full">
</Filter>
```

### <a name="textmatchfilter-prefix"></a>TextMatchfilter-prefix

Beskrivning: Med den här funktionen kan du definiera de föregående tecknen som alltid ska tas med eller utelämnas. Om kreditkortsnummer föregås av Order-ID tar du bort matchningen från de giltiga matchningarna.

Om du till exempel vill utesluta förekomster av telefonnummer  som har **Telefon och** ringer mig på strängar före telefonnumret, i en lista som den här:

- telefonnummer 091-8974-653278
- Telefon 45 124576532-123
- 45-124576532-123

kan du använda den här xml-koden

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_prefix">
</Filter>
  <Keyword id="Keyword_false_positives_prefix">
    <Group matchStyle="string">
      <Term>phone number</Term>
      <Term>call me at</Term>
    </Group>
  </Keyword>
```

Om du till exempel vill ta med **förekomster** som har kreditkorts- och **kortnummersträngar** före kreditkortsnumret, i en lista som den här:

- Kreditkort 45-124576532-123 
- 45-124576532-123 (vilket kan vara telefonnummer)

kan du använda den här xml-koden

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_true_positives_prefix">
</Filter>

  <Keyword id="Keyword_true_positives_prefix">
    <Group matchStyle="string">
      <Term>credit card</Term>
      <Term>card #</Term>
    </Group>
  </Keyword
```

### <a name="textmatchfilter-suffix"></a>TextMatchFilter-suffix

Beskrivning: Med den här beskrivningen kan du definiera följande tecken som alltid ska inkluderas eller undantas. Om kreditkortsnummer följs av "/xuid" tar du bort matchningen från de giltiga matchningarna.

Till exempel översta exkludera förekomster om det finns ytterligare 5 förekomster av fyra siffror som suffix i en lista som den här:

- 1234-5678-9321 4500 9870 6321 48925566
- 1234-5678-9321

kan du använda den här xml-koden

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Regex_false_positives_suffix">
</Filter>

  <Regexid="Regex_false_positives_suffix">(\d{4}){5,}</Regex>
```
Om du till exempel vill utesluta förekomster om de följs av **/xuidsuffix**, som ett i den här listan:

- 1234-5678-9321 /xuid
- 1234-5678-9321

kan du använda den här xml-koden

''xml <Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_suffix">
</Filter>

  <Keyword id="Keyword_false_positives_suffix"> <Group matchStyle="string">
      <Term>/xuid</Term>
    </Group> </Keyword>
```

For example, to include an occurrence only if it is followed by **cvv** or **expires**, like two in this list:

- 45-124576532-123 
- 45-124576532-123  cvv 966
- 45-124576532-123  expires 03/23

you can use this xml

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_true_positives_suffix">
</Filter>

  <Keyword id="Keyword_true_positives_suffix">
    <Group matchStyle="string">
      <Term>cvv</Term>
      <Term>expires</Term>
    </Group>
  </Keyword>
```

## <a name="using-filters-in-rule-packages"></a>Använda filter i regelpaket

Filter kan definieras på hela SIT eller på ett mönster. Här är några exempel på kodavsnitt. 

### <a name="at-sensitive-information-type-level"></a>På nivå med känslig information

Filter hos Entitet – täcker alla underordnade mönster

Filtren används på alla **instanser** som klassificeras av något av mönster i den enheten/den känsliga typen

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
```

### <a name="at-the-individual-pattern-of-the-sensitive-information-type-level"></a>På det enskilda mönstret i typnivån för känslig information

Filtrerar bara på mönsternivån.

Filtret används för de instanser som matchas av mönstret.

```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Keyword_cc_verification" />
      </Pattern>
</Entity>
```


### <a name="at-sensitive-information-type-level-and-an-additional-filter-on-some-of-the-patterns-of-that-entity"></a>På typsnivå för känslig information och ett ytterligare filter på vissa av mönster i entiteten

Filter för Entitet + mönster

Filtren används på alla **instanser** som klassificeras av något av mönster i den enheten/den känsliga typen. Filtret på mönsternivån filtrerar de instanser som matchas av det mönstret.

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85" filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
``` 

 

## <a name="more-information"></a>Mer information

- [Mer information om skydd mot dataförlust](dlp-learn-about-dlp.md)

- [Entitetsdefinitioner för typer av känslig information](sensitive-information-type-entity-definitions.md)

- [Vad DLP-funktionerna letar efter](what-the-dlp-functions-look-for.md)
