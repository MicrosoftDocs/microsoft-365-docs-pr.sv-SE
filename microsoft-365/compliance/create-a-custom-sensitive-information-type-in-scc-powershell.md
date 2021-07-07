---
title: Skapa en anpassad typ av känslig information med PowerShell
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Lär dig hur du skapar och importerar en anpassad typ av känslig information för principer i efterlevnadscentret.
ms.openlocfilehash: ab89104804fd1af781ca30ed8893bed60cd29e47
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322263"
---
# <a name="create-a-custom-sensitive-information-type-using-powershell"></a>Skapa en anpassad typ av känslig information med PowerShell

I det här avsnittet beskrivs hur du använder PowerShell för att skapa en XML-fil för *regelpaket* som definierar dina egna [typer av känslig information](sensitive-information-type-entity-definitions.md). Du behöver veta hur du skapar ett reguljärt uttryck. I det här avsnittet skapas exempelvis en anpassad typ av känslig information som identifierar ett medarbetar-ID. Du kan använda det här XML-exemplet som utgångspunkt för din egen XML-fil. Se [Läs mer om typer av känslig information](sensitive-information-type-learn-about.md) om du inte har använt typer av känslig information tidigare.

När du har skapat en korrekt formaterad XML-fil kan du ladda upp den till Microsoft 365 med hjälp av Microsoft 365 PowerShell. Sedan är du redo att använda din anpassade typ av känslig information i dina principer och testa att den identifierar denna känsliga information på det sätt som du tänkt dig.

> [!NOTE]
> Om du inte behöver den detaljerade kontroll som du får med PowerShell kan du skapa anpassade typer av känslig information i efterlevnadscentret. Mer information finns i [Skapa en anpassad typ av känslig information](create-a-custom-sensitive-information-type.md).

## <a name="important-disclaimer"></a>Viktig ansvarsfriskrivning

På grund av skillnaderna mellan olika kundmiljöer och innehållsmatchningskrav kan Microsoft Support inte hjälpa till med att ge anpassade definitioner för innehållsmatchning, till exempel definiera anpassade klassificeringar eller mönster för reguljära uttryck (även kallade RegEx). För utveckling, testning och felsökning av anpassad innehållsmatchning måste Microsoft 365-kunder förlita sig på interna IT-resurser, eller använda en extern konsultresurs som Microsoft Consulting Services (MCS). Supporttekniker kan ge begränsad support för funktionen, men kan inte garantera att utvecklingen av anpassad innehållsmatchning uppfyller kundens krav eller skyldigheter.  En typ av support som kan tillhandahållas är exempelmönster för reguljära uttryck för testningsändamål. Eller så kan supporten hjälpa till att felsöka ett befintligt RegEx-mönster som inte utlöses som förväntat med ett enskilt specifikt innehållsexempel.

Se [Möjliga verifieringsproblem som du bör känna till ](#potential-validation-issues-to-be-aware-of) i det här avsnittet.

Mer information om Boost.RegEx-motorn (tidigare kallad RegEx++) som används för att bearbeta texten finns i [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).

> [!NOTE]
> Om du använder ett et-tecken (&) som en del av ett nyckelord i din anpassade typ av känslig information, observera att det finns ett känt problem. Du bör lägga till ytterligare en term med blanksteg runt tecknet för att se till att tecknet identifieras korrekt, till exempel L & P _inte_ L&P.

## <a name="sample-xml-of-a-rule-package"></a>XML-exempel för regelpaket

Här är XML-exempelkoden för det regelpaketet som vi skapar i det här avsnittet. Element och attribut förklaras i avsnitten nedan.
  
```xml
<?xml version="1.0" encoding="UTF-16"?>
<RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce">
<RulePack id="DAD86A92-AB18-43BB-AB35-96F7C594ADAA">
  <Version build="0" major="1" minor="0" revision="0"/>
  <Publisher id="619DD8C3-7B80-4998-A312-4DF0402BAC04"/>
  <Details defaultLangCode="en-us">
    <LocalizedDetails langcode="en-us">
      <PublisherName>Contoso</PublisherName>
      <Name>Employee ID Custom Rule Pack</Name>
      <Description>
      This rule package contains the custom Employee ID entity.
      </Description>
    </LocalizedDetails>
  </Details>
</RulePack>
<Rules>
<!-- Employee ID -->
  <Entity id="E1CC861E-3FE9-4A58-82DF-4BD259EAB378" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="65">
      <IdMatch idRef="Regex_employee_id"/>
    </Pattern>
    <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_employee_id"/>
      <Match idRef="Func_us_date"/>
    </Pattern>
    <Pattern confidenceLevel="85">
      <IdMatch idRef="Regex_employee_id"/>
      <Match idRef="Func_us_date"/>
      <Any minMatches="1">
        <Match idRef="Keyword_badge" minCount="2"/>
        <Match idRef="Keyword_employee"/>
      </Any>
      <Any minMatches="0" maxMatches="0">
        <Match idRef="Keyword_false_positives_local"/>
        <Match idRef="Keyword_false_positives_intl"/>
      </Any>
    </Pattern>
  </Entity>
  <Regex id="Regex_employee_id">(\s)(\d{9})(\s)</Regex>
  <Keyword id="Keyword_employee">
    <Group matchStyle="word">
      <Term>Identification</Term>
      <Term>Contoso Employee</Term>
    </Group>
  </Keyword>
  <Keyword id="Keyword_badge">
    <Group matchStyle="string">
      <Term>card</Term>
      <Term>badge</Term>
      <Term caseSensitive="true">ID</Term>
    </Group>
  </Keyword>
  <Keyword id="Keyword_false_positives_local">
    <Group matchStyle="word">
      <Term>credit card</Term>
      <Term>national ID</Term>
    </Group>
  </Keyword>
  <Keyword id="Keyword_false_positives_intl">
    <Group matchStyle="word">
      <Term>identity card</Term>
      <Term>national ID</Term>
      <Term>EU debit card</Term>
    </Group>
  </Keyword>
  <LocalizedStrings>
    <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB378">
      <Name default="true" langcode="en-us">Employee ID</Name>
      <Description default="true" langcode="en-us">
      A custom classification for detecting Employee IDs.
      </Description>
      <Description default="false" langcode="de-de">
      Description for German locale.
      </Description>
    </Resource>
  </LocalizedStrings>
</Rules>
</RulePackage>
```

## <a name="what-are-your-key-requirements-rule-entity-pattern-elements"></a>Vilka är dina viktigaste krav? [elementen Rule, Entity, Pattern]

Innan du börjar är det bra om du förstår den grundläggande strukturen i XML-schemat för en regel och hur du kan använda den här strukturen för att definiera en anpassad typ av känslig information så att rätt innehåll identifieras.
  
En regel definierar en eller flera entiteter (typer av känslig information) och varje entitet definierar ett eller flera mönster. En princip söker efter mönster när den utvärderar innehåll som e-post och dokument.

I det här avsnittet med XML-kod avser regel de mönster som definierar en entitet, även kallad typ av känslig information. När du ser en regel i det här avsnittet motsvarar den alltså entitet eller typ av känslig information, inte villkor och åtgärder.
  
### <a name="simplest-scenario-entity-with-one-pattern"></a>Enklaste scenariot: entitet med ett mönster

Här är det enklaste scenariot. Du vill att principen ska identifiera innehåll som innehåller organisationens medarbetar-ID, som är formaterat som ett niosiffrigt nummer. Mönstret refererar därför till ett reguljärt uttryck som finns i en regel som identifierar niosiffriga nummer. Allt innehåll som innehåller ett niosiffrigt nummer uppfyller mönstret.
  
![Diagram av entitet med ett mönster](../media/4cc82dcf-068f-43ff-99b2-bac3892e9819.png)
  
Det här är ett enkelt mönster som riskerar att identifiera många falska positiva identifieringar eftersom det matchar alla niosiffriga nummer, inte bara medarbetar-ID:n.
  
### <a name="more-common-scenario-entity-with-multiple-patterns"></a>Ett vanligare scenario: entitet med flera mönster

Därför är det vanligare att definiera en entitet med hjälp av flera mönster, där mönster identifierar bevis (till exempel ett nyckelord eller datum) utöver enheten (till exempel ett niosiffrigt nummer).
  
Om du vill öka sannolikheten att exempelvis identifiera ett faktiskt medarbetar-ID i ett visst innehåll kan du definiera ett annat mönster som även identifierar anställningsdatum, och definiera ytterligare ett mönster som identifierar både ett anställningsdatum och ett nyckelord (till exempel ”medarbetar-ID”), utöver det niosiffriga numret.
  
![Diagram över en entitet med flera mönster](../media/c8dc2c9d-00c6-4ebc-889a-53b41a90024a.png)
  
Observera några viktiga aspekter av den här strukturen:
  
- Mönster som kräver fler bevis har högre konfidensnivå. Du kan ha nytta av detta senare när du använder den här typen av känslig information i en princip då du kan använda mer begränsande åtgärder (till exempel blockera innehåll) med endast matchningar med högre säkerhet och du kan använda mindre begränsande åtgärder (till exempel skicka meddelande) med matchningar med lägre säkerhet.

- Stödelementen IdMatch och Match refererar till regex och nyckelord som är underordnade Rules-elementet, inte Pattern-elementet. De här stödelementen refereras till av Pattern-elementet men tas med i Rules-elementet. Det innebär att en enda definition av ett stödelement, till exempel ett reguljärt uttryck eller en nyckelordslista, kan refereras till av flera entiteter och mönster.

## <a name="what-entity-do-you-need-to-identify-entity-element-id-attribute"></a>Vilken entitet behöver du identifiera? [elementet Entity, attributet id]

En entitet är en typ av känslig information, till exempel kreditkortsnummer, som har ett väldefinierat mönster. Varje entitet har ett unikt GUID som ID.
  
### <a name="name-the-entity-and-generate-its-guid"></a>Namnge entiteten och generera dess GUID

1. Lägg till elementen Rules och Entity i valfri XML-redigerare.
2. Lägg till en kommentar som innehåller namnet på ditt anpassade entitet – i det här exemplet Employee ID (medarbetar-ID). Senare lägger du till entitetsnamnet i avsnittet för lokaliserade strängar. Det namnet visas i användargränssnittet när du skapar en princip.
3. Generera ett GUID för entiteten. Det finns flera sätt att generera GUID. Ett enkelt sätt är att skriva **[guid]::NewGuid()** i PowerShell. Senare lägger du även till GUID för entiteten i avsnittet för lokaliserade strängar.
  
![XML-kod som visar elementen Rules och Entity](../media/c46c0209-0947-44e0-ac3a-8fd5209a81aa.png)
  
## <a name="what-pattern-do-you-want-to-match-pattern-element-idmatch-element-regex-element"></a>Vilket mönster vill du matcha? [elementet Pattern, elementet IdMatch, elementet Regex]

Mönstret innehåller en lista över vad typen av känslig information söker efter. Det kan vara regex, nyckelord och inbyggda funktioner (som utför uppgifter som att köra regex för att hitta datum eller adresser). Typer av känslig information kan ha flera mönster med unika konfidenser.
  
Gemensamt för alla mönster nedan är att de refererar till samma reguljära uttryck, som söker efter ett niosiffrigt nummer (\d{9}) omgivet av tomt utrymme (\s) … (\s). Det här reguljära uttrycket refereras av IdMatch-elementet och är det vanliga kravet för alla mönster som letar efter entiteten Employee ID (medarbetar-ID). IdMatch är identifieraren som mönstret försöker matcha, till exempel medarbetar-ID, kreditkortsnummer eller personnummer. Ett Pattern-element måste ha exakt ett IdMatch-element.
  
![XML-kod med flera Pattern-element som refererar till ett Regex-element](../media/8f3f497b-3b8b-4bad-9c6a-d9abf0520854.png)
  
Om mönstret uppfylls returneras ett antal och konfidensnivån, som du kan använda i villkoren i din princip. När du lägger till ett villkor för att identifiera en typ av känslig information i en princip kan du redigera antalet och konfidensnivån på det sätt som visas här. Konfidensnivån (kallas även matchningsnoggrannhet) förklaras senare i det här avsnittet.
  
![Alternativ för antal instanser och matchningsnoggrannhet](../media/sit-confidence-level.png)
  
När du skapar ett reguljärt uttryck finns det möjliga problem som du bör känna till. Om du till exempel skriver och laddar upp en regex som identifierar för mycket innehåll kan det påverka prestanda. Mer information om möjliga problem finns i avsnittet [Möjliga verifieringsproblem som du bör känna till](#potential-validation-issues-to-be-aware-of).
  
## <a name="do-you-want-to-require-additional-evidence-match-element-mincount-attribute"></a>Vill du kräva ytterligare bevis? [elementet Match, attributet minCount]

Förutom IdMatch kan ett mönster använda elementet Match för att kräva ytterligare bevis, till exempel nyckelord, regex, datum eller adress.
  
Ett mönster kan innehålla flera Match-element. De kan tas med direkt i Pattern-elementet eller kombineras med hjälp av elementet Any. Match-element sammanfogas av en implicit OCH-operator. Alla Match-element måste vara uppfyllda för att mönstret ska matchas. Du kan använda elementet Any till att introducera OCH- eller ELLER-operatorer (mer om det i ett senare avsnitt).
  
Du kan använda det valfria attributet minCount till att ange hur många instanser av en matchning som behöver hittas för varje Match-element. Du kan till exempel ange att ett mönster bara är uppfyllt när minst två nyckelord från en nyckelordslista hittas.
  
![XML-kod som visar Match-element med attribut för minOccurs](../media/607f6b5e-2c7d-43a5-a131-a649f122e15a.png)
  
### <a name="keywords-keyword-group-and-term-elements-matchstyle-and-casesensitive-attributes"></a>Nyckelord [elementen Keyword, Group och Term elements, attributen matchStyle och caseSensitive]

När du identifierar känslig information, t.ex. medarbetar-ID, är det vanligt att kräva nyckelord som samarbetsbevis. Förutom att matcha ett niosiffrigt nummer kanske du vill söka efter ord som ”kort”, ”bricka” eller ”ID”. Det gör du med hjälp av elementet Keyword. Keyword-elementet har ett ID-attribut som kan refereras av flera Match-element i flera mönster eller entiteter.
  
Keyword-element ingår som en lista över Term-element i ett Group-element. Group-elementet har ett matchStyle-attribut med två möjliga värden:
  
- **matchStyle="word"** Word-matchningen identifierar hela ord omgivna av tomt utrymme eller andra avgränsare. Du bör alltid använda ”word” om du inte behöver matcha delar av ord eller matcha ord på asiatiska språk. 
    
- **matchStyle="string"** identifierar strängar oavsett vad de omges av. "id" matchar till exempel "sida" och "idé". Använd ”string” endast när du behöver matcha asiatiska ord eller om ditt nyckelord kan ingå som en del av andra strängar. 
    
Slutligen kan du använda attributet CaseSensitive för Term-elementet för att ange att innehållet måste matcha nyckelordet exakt, inklusive gemener och versaler.
  
![XML-kod som visar Match-element som refererar till nyckelord](../media/e729ba27-dec6-46f4-9242-584c6c12fd85.png)
  
### <a name="regular-expressions-regex-element"></a>Reguljära uttryck [elementet Regex]

I det här exemplet använder employee ID-entiteten redan elementet IdMatch för att referera till ett regex för mönstret, dvs. ett niosiffrigt nummer omgivet av tomt utrymme. Ett mönster kan dessutom använda ett Match-element för att referera till ett ytterligare Regex-element för att identifiera samarbetsbevis, till exempel ett fem- eller niosiffrigt nummer i ett amerikanskt postnummerformat.
  
### <a name="additional-patterns-such-as-dates-or-addresses-built-in-functions"></a>Ytterligare mönster, till exempel datum eller adresser [inbyggda funktioner]

Utöver de inbyggda typerna av känslig information, kan typer av känslig information även använda inbyggda funktioner som kan identifiera samarbetsbevis, till exempel ett amerikanskt datum, ett utgångsdatum eller en adress i USA. Microsoft 365 stöder inte uppladdning av egna anpassade funktioner, men när du skapar en anpassad typ av känslig information kan entiteten referera till de inbyggda funktionerna.
  
På ett id-kort för personal (”employee ID badge”) finns ett anställningsdatum, så den anpassade entiteten kan använda den inbyggda funktionen `Func_us_date` för att identifiera ett datum i det format som vanligtvis används i USA. 
  
Mer information finns i [Vad DLP-funktionerna letar efter](what-the-dlp-functions-look-for.md).
  
![XML-kod som visar Match-element som refererar till en inbyggd funktion](../media/dac6eae3-9c52-4537-b984-f9f127cc9c33.png)
  
## <a name="different-combinations-of-evidence-any-element-minmatches-and-maxmatches-attributes"></a>Olika kombinationer av bevis [elementet Any, attributen minMatches och maxMatches]

I ett Pattern-element är alla IdMatch- och Match-element sammanfogade av en implicit AND-operator och alla matchningar måste uppfyllas innan mönstret kan uppfyllas. Men du kan skapa en mer flexibel matchningslogik genom att gruppera Match-element med elementet Any. Med elementet Any kan du till exempel matcha alla, inga eller en exakt delmängd av dess underordnade Match-element.
  
Elementet Any har valfria minMatches- och maxMatches-attribut som du kan använda till att definiera hur många av de underordnade Match-elementen som behöver uppfyllas innan mönstret matchas. Observera att dessa attribut definierar antalet Match-element som måste uppfyllas, inte antalet instanser av bevis som hittas för matchningarna. Om du vill definiera ett minsta antal instanser för en viss matchning, till exempel två nyckelord från en lista använder du attributet minCount för ett Match-element (se ovan).
  
### <a name="match-at-least-one-child-match-element"></a>Matcha minst ett underordnat Match-element

Om du vill kräva att ett minsta antal Match-element måste uppfyllas kan du använda attributet minMatches. I praktiken är dessa Match-element sammanfogade av en implicit ELLER-operator. Ett Any-element uppfylls om ett datum i amerikanskt format eller ett nyckelord i någon av listorna hittas.

```xml
<Any minMatches="1" >
     <Match idRef="Func_us_date" />
     <Match idRef="Keyword_employee" />
     <Match idRef="Keyword_badge" />
</Any>
```
    
### <a name="match-an-exact-subset-of-any-children-match-elements"></a>Matcha en exakt delmängd av underordnade Match-element

Om du vill kräva att ett exakt antal Match-element måste uppfyllas kan du ange samma värde för minMatches och maxMatches. Det här Any-elementet uppfylls bara om exakt ett datum eller nyckelord hittas – om fler hittas matchas inte mönstret.

```xml
<Any minMatches="1" maxMatches="1" >
     <Match idRef="Func_us_date" />
     <Match idRef="Keyword_employee" />
     <Match idRef="Keyword_badge" />
</Any>
```
  
### <a name="match-none-of-children-match-elements"></a>Matcha inget av underordnade Match-element

Om du vill kräva att specifika bevis inte får finnas för att ett mönster ska uppfyllas kan du ange värdet 0 för både minMatches och maxMatches. Det kan vara användbart om du har en nyckelordslista eller andra bevis som troligen ger en falsk positiv identifiering.
  
Entiteten employee ID (medarbetar-ID) letar till exempel efter nyckelordet ”card” (kort) eftersom det kan referera till ett ”ID card” (ID-kort). Men om ”card” endast förekommer i frasen ”credit card” (kreditkort) är det inte sannolikt att “card” i det här innehållet betyder “ID card”. Du kan alltså lägga till ”credit card” som ett nyckelord i en lista med termer som inte får finnas för att mönstret ska uppfyllas.
  
```xml
<Any minMatches="0" maxMatches="0" >
    <Match idRef="Keyword_false_positives_local" />
    <Match idRef="Keyword_false_positives_intl" />
</Any>
```

### <a name="match-a-number-of-unique-terms"></a>Matcha ett antal unika termer

Om du vill matcha ett antal unika termer använder du parametern *uniqueResults* inställd på *true*, som i följande exempel:

```xml
<Pattern confidenceLevel="75">
    <IdMatch idRef="Salary_Revision_terms" />
    <Match idRef=" Salary_Revision_ID " minCount="3" uniqueResults="true" />
</Pattern>
```

I det här exemplet definieras ett mönster för lönerevision med minst tre unika matchningar. 
  
## <a name="how-close-to-the-entity-must-the-other-evidence-be-patternsproximity-attribute"></a>Hur nära entiteten måste det andra beviset vara? [attributet patternsProximity]

Din typ av känslig information letar efter ett mönster som representerar ett medarbetar-ID, och som en del i mönstret letar den även efter samarbetsbevis, till exempel ett nyckelord som ”ID”. Det är logiskt att ju närmare detta bevis är, desto troligare är det att mönstret är ett faktiskt medarbetar-ID. Du kan ange hur nära andra bevis i mönstret måste vara i förhållande till entiteten med hjälp av det obligatoriska attributet patternsProximity i elementet Entity.
  
![XML-kod med attributet patternsProximity](../media/e97eb7dc-b897-4e11-9325-91c742d9839b.png)
  
För varje mönster i entiteten definierar värdet för attributet patternsProximity avståndet (i Unicode-tecken) från platsen för IdMatch för alla andra Match-element som angetts för mönstret. Närhetsfönstret är förankrat vid IdMatch-platsen, och fortsätter till vänster och höger om IdMatch.
  
![Diagram över närhetsfönster](../media/b593dfd1-5eef-4d79-8726-a28923f7c31e.png)
  
Exemplet nedan visar hur närhetsfönstret påverkar mönstermatchningen där elementet IdMatch för den anpassade entiteten medarbetar-ID kräver minst en samarbetsmatchning av nyckelord eller datum. Endast ID1 matchar eftersom inget eller bara delvisa samarbetsbevis hittas för ID2 och ID3 inom närhetsfönstret.
  
![Diagram över samarbetsbevis och närhetsfönster](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)
  
Observera att för e-post behandlas meddelandetexten och varje bifogad fil som separata objekt. Det innebär att närhetsfönstret inte fortsätter utanför slutet av de här objekten. Både idMatch och samarbetsbevis måste finnas i varje objekt (bifogad fil eller brödtext).
  
## <a name="what-are-the-right-confidence-levels-for-different-patterns-confidencelevel-attribute-recommendedconfidence-attribute"></a>Vad är rätt konfidensnivåer för olika mönster? [attributet confidenceLevel, attributet recommendedConfidence]

Ju mer bevis ett mönster kräver, desto större blir konfidensen att en faktisk entitet (till exempel ett medarbetar-ID) har identifierats när mönstret matchas. Du har till exempel mer konfidens i ett mönster som kräver ett niosiffrigt ID-nummer, anställningsdatum och nyckelord i närheten än i ett mönster som endast kräver ett niosiffrigt ID-nummer.
  
Pattern-elementet har ett obligatoriskt confidenceLevel-attribut. Du kan tänka på värdet för confidenceLevel (ett heltal mellan 1 och 100) som ett unikt ID för varje mönster i en entitet – mönster i en entitet måste ha olika konfidensnivåer, som du tilldelar. Det exakta värdet för heltalet spelar ingen roll. Välj bara ett värde som är logiskt för ditt efterlevnadsteam. När du har laddat upp din anpassade typ av känslig information och sedan skapar en princip kan du referera till dessa konfidensnivåer i villkoren i den regel som du skapar.
  
![XML-kod som visar Pattern-element med olika värden för attributet confidenceLevel](../media/sit-xml-markedup-2.png)
  
Utöver confidenceLevel för varje mönster har entiteten också ett recommendedConfidence-attribut. Det rekommenderade konfidensattributet kan ses som standardkonfidensnivå för regeln. Om du inte anger en konfidensnivå för en regel när du skapar regeln i en princip utförs matchningen av regeln baserat på den rekommenderade konfidensnivån för entiteten. Observera att attributet recommendedConfidence är obligatoriskt för varje entitets-ID i regelpaketet. Om det saknas kan du inte spara principer som använder typen av känslig information. 
  
## <a name="do-you-want-to-support-other-languages-in-the-ui-of-the-compliance-center-localizedstrings-element"></a>Vill du använda andra språk i användargränssnittet i efterlevnadscentret? [elementet LocalizedStrings]

Om ditt efterlevnadsteam använder Microsoft 365 Efterlevnadscenter för att skapa principer på olika språk kan du tillhandahålla lokaliserade versioner av namnet och beskrivningen av din anpassade typ av känslig information. När efterlevnadsteamet använder Microsoft 365 på ett språk som du stöder ser de det lokaliserade namnet i användargränssnittet.
  
![Alternativ för antal instanser och matchningsnoggrannhet](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)
  
Elementet Rules måste innehålla ett localizedStrings-element som innehåller ett Resource-element som refererar till GUID för din anpassade entitet. I sin tur innehåller varje Resource-element ett eller flera namn- och beskrivningselement som vart och ett använder attributet langcode för att tillhandahålla en lokaliserad sträng för ett visst språk.
  
![XML-kod som visar innehållet i elementet LocalizedStrings](../media/a96fc34a-b93d-498f-8b92-285b16a7bbe6.png)
  
Observera att de lokaliserade strängarna endast påverkar hur din anpassade typ av känslig information visas i användargränssnittet i efterlevnadscentret. Du kan inte använda lokaliserade strängar för att tillhandahålla olika lokaliserade versioner av en nyckelordslista eller ett reguljärt uttryck.
  
## <a name="other-rule-package-markup-rulepack-guid"></a>Annan regelpaketkod [RulePack GUID]

I början av varje RulePackage finns viss allmän information som du behöver fylla i. Du kan använda följande kod som mall och ersätta platshållarna ". . ." med egen information.
  
Det viktigaste är att du skapar ett GUID för RulePack. Ovan genererade du ett GUID för entiteten. Detta är ett andra GUID för RulePack. Det finns flera sätt att generera GUID. Ett enkelt sätt är att skriva [guid]::NewGuid() i PowerShell.
  
Versionselementet är också viktigt. När du laddar upp regelpaketet för första gången registrerar Microsoft 365 versionsnumret. Om du uppdaterar regelpaketet senare och laddar upp en ny version måste du uppdatera versionsnumret, annars distribuerar Microsoft 365 inte regelpaketet.
  
```xml
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce">
  <RulePack id=". . .">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id=". . ." /> 
    <Details defaultLangCode=". . .">
      <LocalizedDetails langcode=" . . . ">
         <PublisherName>. . .</PublisherName>
         <Name>. . .</Name>
         <Description>. . .</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>
  
 <Rules>
  . . .
 </Rules>
</RulePackage>

```

När allt är klart bör ditt RulePack-element se ut så här.
  
![XML-kod som visar RulePack-elementet](../media/fd0f31a7-c3ee-43cd-a71b-6a3813b21155.png)

## <a name="validators"></a>Validerare

Microsoft 365 kan använda funktionsprocessorer för vanliga SITs som validatorer. Här är en lista över dem. 

### <a name="list-of-validators-currently-available"></a>Lista över tillgängliga validerare

- Func_credit_card
- Func_ssn
- Func_unformatted_ssn
- Func_randomized_formatted_ssn
- Func_randomized_unformatted_ssn
- Func_aba_routing
- Func_south_africa_identification_number
- Func_brazil_cpf
- Func_iban
- Func_brazil_cnpj
- Func_swedish_national_identifier
- Func_india_aadhaar
- Func_uk_nhs_number
- Func_Turkish_National_Id
- Func_australian_tax_file_number
- Func_usa_uk_passport
- Func_canadian_sin
- Func_formatted_itin
- Func_unformatted_itin
- Func_dea_number_v2
- Func_dea_number
- Func_japanese_my_number_personal
- Func_japanese_my_number_corporate

På så sätt kan du definiera en egen regex och verifiera dem. Om du vill använda verifierare definierar du egna regex och när du definierar regex använder du egenskapen validator för att lägga till valfri funktionsbehandlare. När den är definierad kan du använda denna regex i en SIT. 

I exemplet nedan har ett vanligt uttryck - Regex_credit_card_AdditionalDelimiters definierats för kreditkort som sedan valideras med funktionen checksumma för kreditkort genom att använda Func_credit_card som validerare.

```xml
<Regex id="Regex_credit_card_AdditionalDelimiters" validators="Func_credit_card"> (?:^|[\s,;\:\(\)\[\]"'])([0-9]{4}[ -_][0-9]{4}[ -_][0-9]{4}[ -_][0-9]{4})(?:$|[\s,;\:\(\)\[\]"'])</Regex>
<Entity id="675634eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
<Pattern confidenceLevel="85">
<IdMatch idRef="Regex_credit_card_AdditionalDelimiters" />
<Any minMatches="1">
<Match idRef="Keyword_cc_verification" />
<Match idRef="Keyword_cc_name" />
<Match idRef="Func_expiration_date" />
</Any>
</Pattern>
</Entity>
```

Microsoft 365 finns två allmänna validerare

### <a name="checksum-validator"></a>Kontrollerasummator

I det här exemplet har en kontrollsumma för anställnings-ID definierats för att verifiera regex för EmployeeID.

```xml
<Validators id="EmployeeIDChecksumValidator">
<Validator type="Checksum">
<Param name="Weights">2, 2, 2, 2, 2, 1</Param>
<Param name="Mod">28</Param>
<Param name="CheckDigit">2</Param> <!-- Check 2nd digit -->
<Param name="AllowAlphabets">1</Param> <!— 0 if no Alphabets -->
</Validator>
</Validators>
<Regex id="Regex_EmployeeID" validators="ChecksumValidator">(\d{5}[A-Z])</Regex>
<Entity id="675634eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
<Pattern confidenceLevel="85">
<IdMatch idRef="Regex_EmployeeID"/>
</Pattern>
</Entity>
```

### <a name="date-validator"></a>Datum giltiga

I det här exemplet definieras ett datum validator för en regex-del som är datum.

```xml
<Validators id="date_validator_1"> <Validator type="DateSimple"> <Param name="Pattern">DDMMYYYY</Param> <!—supported patterns DDMMYYYY, MMDDYYYY, YYYYDDMM, YYYYMMDD, DDMMYYYY, DDMMYY, MMDDYY, YYDDMM, YYMMDD --> </Validator> </Validators>
<Regex id="date_regex_1" validators="date_validator_1">\d{8}</Regex>
```
  
## <a name="changes-for-exchange-online"></a>Ändringar för Exchange Online

Tidigare kanske du använde Exchange Online PowerShell för att importera anpassade typer av känslig information för DLP. Nu kan dina anpassade typer av känslig information användas i både administrationscentret för Exchange och i efterlevnadscentret. Som en del av den här förbättringen bör du använda Compliance Center PowerShell för att importera anpassade typer av känslig information – du kan inte importera dem från Exchange PowerShell längre. Dina anpassade typer av känslig information fortsätter att fungera som vanligt, men det kan ta upp till en timme innan ändringar av anpassade typer av känslig information som gjorts i efterlevnadscentret visas i administrationscentret för Exchange. 
  
Observera att du kan ladda upp ett regelpaket med cmdleten **[New-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage)** i efterlevnadscentret. (Tidigare kunde du använda cmdleten **ClassificationRuleCollection** i administrationscentret för Exchange.) 
  
## <a name="upload-your-rule-package"></a>Ladda upp regelpaketet

Gör så här om du vill ladda upp regelpaketet:
  
1. Spara det som en XML-fil med Unicode-kodning.
    
2. [Ansluta till Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell)
    
3. Använd följande syntax:

   ```powershell
   New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "PathToUnicodeXMLFile" -Encoding Byte -ReadCount 0)
   ```

   I det här exemplet överförs Unicode XML-filen med namnet MyNewRulePack.xml från C:\My Documents.

   ```powershell
   New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\My Documents\MyNewRulePack.xml" -Encoding Byte -ReadCount 0)
   ```

   Se [New-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/new-dlpsensitiveinformationtyperulepackage) för detaljerad information om syntax och parametrar.

   > [!NOTE]
   > Det maximala antalet regelpaket som stöds är tio, men varje paket kan innehålla en definition för flera typer av känslig information.

4. Gör något av följande för att kontrollera att du har skapat en ny typ av känslig information:

   - Kör cmdleten [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) och kontrollera att det nya regelpaketet visas:

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ``` 

   - Kör cmdleten [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) och kontrollera att typen av känslig information visas:

     ```powershell
     Get-DlpSensitiveInformationType
     ``` 

     För anpassade typer av känslig information är egenskapsvärdet för utgivare något annat än Microsoft Corporation.

   - Ersätt \<Name\> med namnvärdet för typen av känslig information (till exempel: medarbetar-ID) och kör cmdleten [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype):

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```
    
## <a name="potential-validation-issues-to-be-aware-of"></a>Möjliga verifieringsproblem som du bör känna till

När du laddar upp din XML-fil för regelpaket verifierar systemet XML-koden och söker efter kända felaktiga mönster och tydliga prestandaproblem. Här är några kända problem som verifieringen söker efter – ett reguljärt uttryck:
  
- Kan inte börja eller sluta med ”|”, som matchar allt eftersom den betraktas som en tom matchning.
    
  Till exempel godkänns inte ”|a” eller ”b|”.
    
- Kan inte börja eller sluta med ett ”.{0,m}”-mönster, som inte har något funktionssyfte utan bara försämrar prestanda.
    
  Till exempel godkänns inte ”.{0,50}ASDF” eller ”ASDF.{0,50}”.
    
- Kan inte ha ”.{0,m}” eller ”.{1,m}” i grupper, och kan inte ha ”.\*” eller ”.+” i grupper.
    
  Till exempel godkänns inte ”(.{0,50000})”.
    
- Kan inte ha något tecken med ”{0,m}”- eller ”{1,m}”-repeaters i grupper.
    
  Till exempel godkänns inte ” (a\*)”.
    
- Kan inte börja eller sluta med ”. {1,m}”. I stället använder du bara ”.”.
    
  Till exempel godkänns inte ”.{1,m}asdf”. I stället använder du bara ”.asdf”.
    
- Kan inte ha en obunden repeater (till exempel ”\*” eller ”+”) i en grupp.
    
  Till exempel godkänns inte ”(xx)\*” och ”(xx)+”.
  
- Nyckelorden får vara högst 50 tecken långa.  Om du ett nyckelord i en grupp som överskrider den här gränsen föreslår vi att du skapar en grupp med termer, till exempel en [nyckelordsordlista](./create-a-keyword-dictionary.md) och refererar till GUID för nyckelordsordlistan i XML-strukturen som en del i entiteten för Match eller idMatch i filen.

- Varje anpassad typ av känslig information kan innehålla maximalt 2 048 nyckelord.

- Den maximala storleken på nyckelordsordlistor i en enskild klientorganisation är 1 MB komprimerad. Du kan referera till samma ordlista så många gånger som behövs när du skapar anpassade typer av känslig information. Börja med att skapa anpassade nyckelordslistor i typen av känslig information och använd nyckelordsordlistor om du har fler än 2 048 nyckelord i en nyckelordslista eller om ett nyckelord är längre än 50 tecken.

- Högst 50 nyckelordsordlistebaserade typer av känslig information tillåts i en klientorganisation.

- Kontrollera att varje Entity-element innehåller ett recommendedConfidence-attribut.

- När du använder PowerShell-cmdleten finns en maximal returstorlek för deserialiserade data på ungefär 1 MB.   Det här påverkar storleken på XML-filen för regelpaketet. Vi föreslår att du begränsar den uppladdade filen till högst 770 kB så att du får konsekventa resultat utan fel vid bearbetningen.

- XML-strukturen kräver inte formateringstecken som blanksteg, tabbar eller poster för vagnretur/radmatning.  Tänk på det när du optimerar utrymme för uppladdningar. Verktyg som Microsoft Visual Code tillhandahåller kopplingslinjefunktioner för att komprimera XML-filen.
    
Om en anpassad typ av känslig information innehåller ett problem som kan påverka prestanda laddas den inte upp och något av följande felmeddelanden visas:
  
- **Allmänna kvantifierare som matchar mer innehåll än förväntat (t.ex. ”+”, ”\*”)**
    
- **Påståenden för sökning**
    
- **Komplex gruppering tillsammans med allmänna kvantifierare**
    
## <a name="recrawl-your-content-to-identify-the-sensitive-information"></a>Du måste crawla innehållet igen för att identifiera känslig information

I Microsoft 365 används Search Crawler för att identifiera och klassificera känslig information i webbplatsinnehåll. Innehållet i SharePoint Online- och OneDrive för företag-webbplatserna crawlas igen automatiskt när det uppdateras. Men för att identifiera den nya anpassade typen av känslig information i allt befintligt innehåll måste innehållet crawlas på nytt.
  
I Microsoft 365 kan du inte begära en ny crawlning av en hel klientorganisation manuellt, men du kan göra det för en webbplatssamling, en lista eller ett bibliotek. Se [Manuellt begära crawlning och omindexering av en webbplats, ett bibliotek eller en lista](/sharepoint/crawl-site-content).
  
## <a name="reference-rule-package-xml-schema-definition"></a>Referens: XML-schemadefinition för regelpaket

Du kan kopiera den här koden, spara den som en XSD-fil och använda den för att verifiera XML-filen för regelpaketet.
  
```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema xmlns:mce="http://schemas.microsoft.com/office/2011/mce"
           targetNamespace="http://schemas.microsoft.com/office/2011/mce"
           xmlns:xs="https://www.w3.org/2001/XMLSchema"
           elementFormDefault="qualified"
           attributeFormDefault="unqualified"
           id="RulePackageSchema">
  <!-- Use include if this schema has the same target namespace as the schema being referenced, otherwise use import -->
  <xs:element name="RulePackage" type="mce:RulePackageType"/>
  <xs:simpleType name="LangType">
    <xs:union memberTypes="xs:language">
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:enumeration value=""/>
        </xs:restriction>
      </xs:simpleType>
    </xs:union>
  </xs:simpleType>
  <xs:simpleType name="GuidType" final="#all">
    <xs:restriction base="xs:token">
      <xs:pattern value="[0-9a-fA-F]{8}\-([0-9a-fA-F]{4}\-){3}[0-9a-fA-F]{12}"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="RulePackageType">
    <xs:sequence>
      <xs:element name="RulePack" type="mce:RulePackType"/>
      <xs:element name="Rules" type="mce:RulesType">
        <xs:key name="UniqueRuleId">
          <xs:selector xpath="mce:Entity|mce:Affinity|mce:Version/mce:Entity|mce:Version/mce:Affinity"/>
          <xs:field xpath="@id"/>
        </xs:key>
        <xs:key name="UniqueProcessorId">
          <xs:selector xpath="mce:Regex|mce:Keyword|mce:Fingerprint"></xs:selector>
          <xs:field xpath="@id"/>
        </xs:key>
        <xs:key name="UniqueResourceIdRef">
          <xs:selector xpath="mce:LocalizedStrings/mce:Resource"/>
          <xs:field xpath="@idRef"/>
        </xs:key>
        <xs:keyref name="ReferencedRuleMustExist" refer="mce:UniqueRuleId">
          <xs:selector xpath="mce:LocalizedStrings/mce:Resource"/>
          <xs:field xpath="@idRef"/>
        </xs:keyref>
        <xs:keyref name="RuleMustHaveResource" refer="mce:UniqueResourceIdRef">
          <xs:selector xpath="mce:Entity|mce:Affinity|mce:Version/mce:Entity|mce:Version/mce:Affinity"/>
          <xs:field xpath="@id"/>
        </xs:keyref>
      </xs:element>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="RulePackType">
    <xs:sequence>
      <xs:element name="Version" type="mce:VersionType"/>
      <xs:element name="Publisher" type="mce:PublisherType"/>
      <xs:element name="Details" type="mce:DetailsType">
        <xs:key name="UniqueLangCodeInLocalizedDetails">
          <xs:selector xpath="mce:LocalizedDetails"/>
          <xs:field xpath="@langcode"/>
        </xs:key>
        <xs:keyref name="DefaultLangCodeMustExist" refer="mce:UniqueLangCodeInLocalizedDetails">
          <xs:selector xpath="."/>
          <xs:field xpath="@defaultLangCode"/>
        </xs:keyref>
      </xs:element>
      <xs:element name="Encryption" type="mce:EncryptionType" minOccurs="0" maxOccurs="1"/>
    </xs:sequence>
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
  </xs:complexType>
  <xs:complexType name="VersionType">
    <xs:attribute name="major" type="xs:unsignedShort" use="required"/>
    <xs:attribute name="minor" type="xs:unsignedShort" use="required"/>
    <xs:attribute name="build" type="xs:unsignedShort" use="required"/>
    <xs:attribute name="revision" type="xs:unsignedShort" use="required"/>
  </xs:complexType>
  <xs:complexType name="PublisherType">
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
  </xs:complexType>
  <xs:complexType name="LocalizedDetailsType">
    <xs:sequence>
      <xs:element name="PublisherName" type="mce:NameType"/>
      <xs:element name="Name" type="mce:RulePackNameType"/>
      <xs:element name="Description" type="mce:OptionalNameType"/>
    </xs:sequence>
    <xs:attribute name="langcode" type="mce:LangType" use="required"/>
  </xs:complexType>
  <xs:complexType name="DetailsType">
    <xs:sequence>
      <xs:element name="LocalizedDetails" type="mce:LocalizedDetailsType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="defaultLangCode" type="mce:LangType" use="required"/>
  </xs:complexType>
  <xs:complexType name="EncryptionType">
    <xs:sequence>
      <xs:element name="Key" type="xs:normalizedString"/>
      <xs:element name="IV" type="xs:normalizedString"/>
    </xs:sequence>
  </xs:complexType>
  <xs:simpleType name="RulePackNameType">
    <xs:restriction base="xs:token">
      <xs:minLength value="1"/>
      <xs:maxLength value="64"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="NameType">
    <xs:restriction base="xs:normalizedString">
      <xs:minLength value="1"/>
      <xs:maxLength value="256"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="OptionalNameType">
    <xs:restriction base="xs:normalizedString">
      <xs:minLength value="0"/>
      <xs:maxLength value="256"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="RestrictedTermType">
    <xs:restriction base="xs:string">
      <xs:minLength value="1"/>
      <xs:maxLength value="100"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="RulesType">
    <xs:sequence>
      <xs:choice maxOccurs="unbounded">
        <xs:element name="Entity" type="mce:EntityType"/>
        <xs:element name="Affinity" type="mce:AffinityType"/>
        <xs:element name="Version" type="mce:VersionedRuleType"/>
      </xs:choice>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element name="Regex" type="mce:RegexType"/>
        <xs:element name="Keyword" type="mce:KeywordType"/>
        <xs:element name="Fingerprint" type="mce:FingerprintType"/>
        <xs:element name="ExtendedKeyword" type="mce:ExtendedKeywordType"/>
      </xs:choice>
      <xs:element name="LocalizedStrings" type="mce:LocalizedStringsType"/>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="EntityType">
    <xs:sequence>
      <xs:element name="Pattern" type="mce:PatternType" maxOccurs="unbounded"/>
      <xs:element name="Version" type="mce:VersionedPatternType" minOccurs="0" maxOccurs="unbounded" />
    </xs:sequence>
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
    <xs:attribute name="patternsProximity" type="mce:ProximityType" use="required"/>
    <xs:attribute name="recommendedConfidence" type="mce:ProbabilityType"/>
    <xs:attribute name="workload" type="mce:WorkloadType"/>
  </xs:complexType>
  <xs:complexType name="PatternType">
    <xs:sequence>
      <xs:element name="IdMatch" type="mce:IdMatchType"/>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element name="Match" type="mce:MatchType"/>
        <xs:element name="Any" type="mce:AnyType"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="confidenceLevel" type="mce:ProbabilityType" use="required"/>
  </xs:complexType>
  <xs:complexType name="AffinityType">
    <xs:sequence>
      <xs:element name="Evidence" type="mce:EvidenceType" maxOccurs="unbounded"/>
      <xs:element name="Version" type="mce:VersionedEvidenceType" minOccurs="0" maxOccurs="unbounded" />
    </xs:sequence>
    <xs:attribute name="id" type="mce:GuidType" use="required"/>
    <xs:attribute name="evidencesProximity" type="mce:ProximityType" use="required"/>
    <xs:attribute name="thresholdConfidenceLevel" type="mce:ProbabilityType" use="required"/>
    <xs:attribute name="workload" type="mce:WorkloadType"/>
  </xs:complexType>
  <xs:complexType name="EvidenceType">
    <xs:sequence>
      <xs:choice maxOccurs="unbounded">
        <xs:element name="Match" type="mce:MatchType"/>
        <xs:element name="Any" type="mce:AnyType"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="confidenceLevel" type="mce:ProbabilityType" use="required"/>
  </xs:complexType>
  <xs:complexType name="IdMatchType">
    <xs:attribute name="idRef" type="xs:string" use="required"/>
  </xs:complexType>
  <xs:complexType name="MatchType">
    <xs:attribute name="idRef" type="xs:string" use="required"/>
    <xs:attribute name="minCount" type="xs:positiveInteger" use="optional"/>
    <xs:attribute name="uniqueResults" type="xs:boolean" use="optional"/>
  </xs:complexType>
  <xs:complexType name="AnyType">
    <xs:sequence>
      <xs:choice maxOccurs="unbounded">
        <xs:element name="Match" type="mce:MatchType"/>
        <xs:element name="Any" type="mce:AnyType"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="minMatches" type="xs:nonNegativeInteger" default="1"/>
    <xs:attribute name="maxMatches" type="xs:nonNegativeInteger" use="optional"/>
  </xs:complexType>
  <xs:simpleType name="ProximityType">
    <xs:union>
      <xs:simpleType>
        <xs:restriction base='xs:string'>
          <xs:enumeration value="unlimited"/>
        </xs:restriction>
      </xs:simpleType>
      <xs:simpleType>
        <xs:restriction base="xs:positiveInteger">
          <xs:minInclusive value="1"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:union>
  </xs:simpleType>
  <xs:simpleType name="ProbabilityType">
    <xs:restriction base="xs:integer">
      <xs:minInclusive value="1"/>
      <xs:maxInclusive value="100"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="WorkloadType">
    <xs:restriction base="xs:string">
      <xs:enumeration value="Exchange"/>
      <xs:enumeration value="Outlook"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:simpleType name="EngineVersionType">
    <xs:restriction base="xs:token">
      <xs:pattern value="^\d{2}\.01?\.\d{3,4}\.\d{1,3}$"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="VersionedRuleType">
    <xs:choice maxOccurs="unbounded">
      <xs:element name="Entity" type="mce:EntityType"/>
      <xs:element name="Affinity" type="mce:AffinityType"/>
    </xs:choice>
    <xs:attribute name="minEngineVersion" type="mce:EngineVersionType" use="required" />
  </xs:complexType>
  <xs:complexType name="VersionedPatternType">
    <xs:sequence>
      <xs:element name="Pattern" type="mce:PatternType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="minEngineVersion" type="mce:EngineVersionType" use="required" />
  </xs:complexType>
  <xs:complexType name="VersionedEvidenceType">
    <xs:sequence>
      <xs:element name="Evidence" type="mce:EvidenceType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="minEngineVersion" type="mce:EngineVersionType" use="required" />
  </xs:complexType>
  <xs:simpleType name="FingerprintValueType">
    <xs:restriction base="xs:string">
      <xs:minLength value="2732"/>
      <xs:maxLength value="2732"/>
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="FingerprintType">
    <xs:simpleContent>
      <xs:extension base="mce:FingerprintValueType">
        <xs:attribute name="id" type="xs:token" use="required"/>
        <xs:attribute name="threshold" type="mce:ProbabilityType" use="required"/>
        <xs:attribute name="shingleCount" type="xs:positiveInteger" use="required"/>
        <xs:attribute name="description" type="xs:string" use="optional"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="RegexType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="id" type="xs:token" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="KeywordType">
    <xs:sequence>
      <xs:element name="Group" type="mce:GroupType" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="id" type="xs:token" use="required"/>
  </xs:complexType>
  <xs:complexType name="GroupType">
    <xs:sequence>
      <xs:choice>
        <xs:element name="Term" type="mce:TermType" maxOccurs="unbounded"/>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="matchStyle" default="word">
      <xs:simpleType>
        <xs:restriction base="xs:NMTOKEN">
          <xs:enumeration value="word"/>
          <xs:enumeration value="string"/>
        </xs:restriction>
      </xs:simpleType>
    </xs:attribute>
  </xs:complexType>
  <xs:complexType name="TermType">
    <xs:simpleContent>
      <xs:extension base="mce:RestrictedTermType">
        <xs:attribute name="caseSensitive" type="xs:boolean" default="false"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="ExtendedKeywordType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="id" type="xs:token" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="LocalizedStringsType">
    <xs:sequence>
      <xs:element name="Resource" type="mce:ResourceType" maxOccurs="unbounded">
      <xs:key name="UniqueLangCodeUsedInNamePerResource">
        <xs:selector xpath="mce:Name"/>
        <xs:field xpath="@langcode"/>
      </xs:key>
      <xs:key name="UniqueLangCodeUsedInDescriptionPerResource">
        <xs:selector xpath="mce:Description"/>
        <xs:field xpath="@langcode"/>
      </xs:key>
    </xs:element>
    </xs:sequence>
  </xs:complexType>
  <xs:complexType name="ResourceType">
    <xs:sequence>
      <xs:element name="Name" type="mce:ResourceNameType" maxOccurs="unbounded"/>
      <xs:element name="Description" type="mce:DescriptionType" minOccurs="0" maxOccurs="unbounded"/>
    </xs:sequence>
    <xs:attribute name="idRef" type="mce:GuidType" use="required"/>
  </xs:complexType>
  <xs:complexType name="ResourceNameType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="default" type="xs:boolean" default="false"/>
        <xs:attribute name="langcode" type="mce:LangType" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
  <xs:complexType name="DescriptionType">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="default" type="xs:boolean" default="false"/>
        <xs:attribute name="langcode" type="mce:LangType" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>
</xs:schema>
```

## <a name="more-information"></a>Mer information

- [Mer information om skydd mot dataförlust](dlp-learn-about-dlp.md)

- [Entitetsdefinitioner för typer av känslig information](sensitive-information-type-entity-definitions.md)

- [Vad DLP-funktionerna letar efter](what-the-dlp-functions-look-for.md)
