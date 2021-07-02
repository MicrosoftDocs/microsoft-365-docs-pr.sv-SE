---
title: Anpassa en inbyggd typ av känslig information
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Lär dig hur du skapar en anpassad typ av känslig information som tillåter dig att använda regler som uppfyller organisationens behov.
ms.openlocfilehash: da79c525a268ff686c2edaf777cedf447335ed27
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227037"
---
# <a name="customize-a-built-in-sensitive-information-type"></a>Anpassa en inbyggd typ av känslig information

När du söker efter känslig information i innehåll måste du beskriva den informationen i en så kallad  *regel*  . I dataförlustskydd (DLP) ingår regler för de vanligaste typerna av känslig information som du kan använda direkt. Om du vill använda de här reglerna måste du inkludera dem i en princip. Du kanske vill justera de inbyggda reglerna efter organisationens specifika behov, och det kan du göra genom att skapa en anpassad typ av känslig information. Det här avsnittet visar hur du anpassar XML-filen som innehåller den befintliga regelsamlingen för att identifiera ett större urval möjliga kreditkortsuppgifter.

Du kan använda det här exemplet och tillämpa det på andra inbyggda typer av känslig information. Du hittar en lista med vanliga typer av känslig information och XML-definitioner under [Entitetsdefinitioner för typer av känslig information](sensitive-information-type-entity-definitions.md).

## <a name="export-the-xml-file-of-the-current-rules"></a>Exportera XML-filen för de aktuella reglerna

Om du vill exportera XML-koden måste du [ansluta till Säkerhets- och efterlevnadscenter via PowerShell-fjärranvändning.](/powershell/exchange/connect-to-scc-powershell).

1. I PowerShell anger du följande för att visa organisationens regler på skärmen. Om du inte har skapat egna regler visas bara de inbyggda standardreglerna som kallas för Regelpaket för Microsoft.

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

2. Lagra organisationens regler i en variabel genom att skriva följande. Om du lagrar något i en variabel blir det lätt tillgängligt senare i ett format som fungerar med fjärrkommandon i PowerShell.

   ```powershell
   $ruleCollections = Get-DlpSensitiveInformationTypeRulePackage
   ```

3. Gör en formaterad XML-fil med alla dessa data genom att skriva följande. ( `Set-content` är den del av cmdleten som skriver XML till filen.)

   ```powershell
   Set-Content -path C:\custompath\exportedRules.xml -Encoding Byte -Value $ruleCollections.SerializedClassificationRuleCollection
   ```

   > [!IMPORTANT]
   > Kontrollera att du använder den filplats där regelpaketet faktiskt lagras. `C:\custompath\` är en platshållare.

## <a name="find-the-rule-that-you-want-to-modify-in-the-xml"></a>Hitta den regel som du vill ändra i XML-filen

Ovanstående cmdletar exporterade hela *regelsamlingen*, som innehåller de standardregler vi tillhandahåller. Därefter måste du söka specifikt efter den regeln för kreditkortsnummer som du vill ändra.

1. Använd en textredigerare för att öppna XML-filen som du exporterade i föregående avsnitt.

2. Rulla ned till `<Rules>`-taggen, som är början på avsnittet som innehåller DLP-reglerna. Eftersom den här XML-filen innehåller informationen för hela regelsamlingen innehåller den annan information längst upp som du behöver bläddra förbi för att komma till reglerna.

3. Leta efter *Func_credit_card* för att hitta regeldefinitionen för kreditkortsnummer. I XML kan regelnamn inte innehålla blanksteg, så blankstegen ersätts vanligtvis med understreck och regelnamn förkortas ibland. Ett exempel på detta är regeln för amerikanska socialförsäkringsnummer som förkortas till _SSN_. XML-koden för regeln för kreditkortsnummer bör se ut som i följande kodexempel.

   ```xml
   <Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085"
          patternsProximity="300" recommendedConfidence="85">
         <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_credit_card" />
           <Any minMatches="1">
             <Match idRef="Keyword_cc_verification" />
             <Match idRef="Keyword_cc_name" />
             <Match idRef="Func_expiration_date" />
           </Any>
         </Pattern>
       </Entity>
   ```

Nu när du har hittat regeldefinitionen för kreditkortsnummer i XML kan du anpassa regelns XML-kod så att den uppfyller dina behov. En uppdatering av XML-definitioner finns i [Termordlistan](#term-glossary) i slutet av det här avsnittet.

## <a name="modify-the-xml-and-create-a-new-sensitive-information-type"></a>Ändra XML-koden och skapa en ny typ av känslig information

Först måste du skapa en ny typ av känslig information eftersom du inte kan ändra själva standardreglerna. Du kan göra en mängd olika saker med anpassade typer av känslig information, vilket beskrivs i [Skapa en anpassad typ av känslig information i Säkerhets- och efterlevnadscenter PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md). I det här exemplet kommer vi att hålla det enkelt och bara ta bort samarbetsbevis och lägga till nyckelord till regeln för kreditkortsnummer.

Alla XML-regeldefinitioner bygger på följande allmänna mall. Du måste kopiera och klistra in XML-definitionen för kreditkortsnummer i mallen, ändra vissa värden (observera “. . ." platshållarna i följande exempel) och överför sedan den ändrade XML-koden som en ny regel som kan användas i principer.

```xml
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce">
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
   <!-- Paste the Credit Card Number rule definition here.-->
      <LocalizedStrings>
         <Resource idRef=". . .">
           <Name default="true" langcode=" . . . ">. . .</Name>
           <Description default="true" langcode=". . ."> . . .</Description>
         </Resource>
      </LocalizedStrings>
   </Rules>
</RulePackage>
```

Nu har du något som liknar följande XML-kod. Eftersom regelpaket och regler identifieras via sina unika GUID:er behöver du skapa två GUID:er, en för regelpaketet och en för att ersätta GUID:en för regeln för kreditkortsnummer. GUID:en för entitets-ID i följande kodexempel är GUID:en för vår inbyggda regeldefinition, som du måste ersätta med en ny. Det finns flera sätt att generera GUID:er, men det kan du enkelt göra i PowerShell genom att skriva **[guid]::NewGuid()**.

```xml
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce">
  <RulePack id="8aac8390-e99f-4487-8d16-7f0cdee8defc">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id="8d34806e-cd65-4178-ba0e-5d7d712e5b66" />
    <Details defaultLangCode="en">
      <LocalizedDetails langcode="en">
        <PublisherName>Contoso Ltd.</PublisherName>
        <Name>Financial Information</Name>
        <Description>Modified versions of the Microsoft rule package</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>

 <Rules>
    <Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f"
       patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
      <LocalizedStrings>
         <Resource idRef="db80b3da-0056-436e-b0ca-1f4cf7080d1f">
<!-- This is the GUID for the preceding Credit Card Number entity because the following text is for that Entity. -->
           <Name default="true" langcode="en-us">Modified Credit Card Number</Name>
           <Description default="true" langcode="en-us">Credit Card Number that looks for additional keywords, and another version of Credit Card Number that doesn't require keywords (but has a lower confidence level)</Description>
         </Resource>
      </LocalizedStrings>
   </Rules>
</RulePackage>
```

## <a name="remove-the-corroborative-evidence-requirement-from-a-sensitive-information-type"></a>Ta bort kravet på samarbetsbevis från en typ av känslig information

Nu när du har en ny typ av känslig information som du kan ladda upp till Säkerhets- &amp; och efterlevnadscenter är nästa steg att göra regeln mer specifik. Ändra regeln så att den bara söker ett 16-siffrigt tal som passerar kontrollsumman men inte kräver ytterligare (samarbets)bevis, till exempel nyckelord. För att göra detta måste du ta bort den del av XML-datan som söker efter ett samarbetsbevis. Samarbetsbevis är mycket användbart för att minska falska positiva identifieringar. I det här fallet finns det vanligtvis vissa nyckelord eller ett utgångsdatum i närheten av kreditkortsnumret. Om du tar bort dessa bevis bör du också justera hur säker du är på att du har hittat ett kreditkortsnummer genom att sänka `confidenceLevel`, vilket är 85 i exemplet.

```xml
<Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="300"
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
      </Pattern>
    </Entity>
```

## <a name="look-for-keywords-that-are-specific-to-your-organization"></a>Söka efter nyckelord som är specifika för din organisation

Du kanske vill att ett samarbetsbevis krävs men vill ha olika eller ytterligare nyckelord, och du kanske vill ändra var du söker efter dessa bevis. Du kan justera  `patternsProximity` för att expandera eller förminska fönstret för att få samarbetsbevis kring det 16-siffriga talet. Om du vill lägga till egna nyckelord måste du definiera en nyckelordslista och referera till den i regeln. I följande XML-data läggs nyckelorden “företagskort” och “Contoso-kort” till så att alla meddelanden som innehåller dessa fraser inom 150 tecken från ett kreditkortsnummer identifieras som kreditkortsnummer.

```xml
<Rules>
<! -- Modify the patternsProximity to be "150" rather than "300." -->
    <Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="150" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
<!-- Add the following XML, which references the keywords at the end of the XML sample. -->
          <Match idRef="My_Additional_Keywords" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
<!-- Add the following XML, and update the information inside the <Term> tags with the keywords that you want to detect. -->
    <Keyword id="My_Additional_Keywords">
      <Group matchStyle="word">
        <Term caseSensitive="false">company card</Term>
        <Term caseSensitive="false">Contoso card</Term>
      </Group>
    </Keyword>
```

## <a name="upload-your-rule"></a>Ladda upp regeln

Gör följande om du vill ladda upp regeln.

1. Spara den som en .xml-fil med Unicode-kodning. Det här är viktigt eftersom regeln inte fungerar om filen sparas med en annan kodning.

2. [Ansluta till Säkerhets- och efterlevnadscenter via PowerShell-fjärranvändning.](/powershell/exchange/connect-to-scc-powershell)

3. Skriv följande i PowerShell.

   ```powershell
   New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\custompath\MyNewRulePack.xml" -Encoding Byte)
   ```

   > [!IMPORTANT]
   > Kontrollera att du använder den filplats där regelpaketet faktiskt lagras.  `C:\custompath\` är en platshållare.

4. Bekräfta genom att skriva Y och sedan trycka på **Retur**.

5. Kontrollera att den nya regeln har laddats upp och dess visningsnamn genom att skriva:

   ```powershell
   Get-DlpSensitiveInformationType
   ```

Om du vill börja använda den nya regeln för att identifiera känslig information måste du lägga till regeln i en DLP-princip. Mer information om hur du lägger till regeln i en princip finns i [Skapa en DLP-princip från en mall](create-a-dlp-policy-from-a-template.md).

## <a name="term-glossary"></a>Termordlista

Det här är definitionerna av de termer som du stötte på under denna procedur.

|**Villkor**|**Definition**|
|:-----|:-----|
|Entitet|Entiteter är det som vi kallar typer av känslig information, till exempel kreditkortsnummer. Varje entitet har en unik GUID som ID. Om du kopierar en GUID och söker efter den i XML-koden hittar du XML-regeldefinitionen och alla lokaliserade översättningar av den XML-regeln. Du kan också hitta den här definitionen genom att hitta GUID:en för översättningen och sedan söka efter denna GUID.|
|Funktioner|XML-filen refererar till  `Func_credit_card`, som är en funktion i kompilerad kod. Funktioner används för att köra komplexa reguljära uttryck och verifiera att kontrollsummorna matchar för våra inbyggda regler.) Eftersom det här händer i koden visas inte vissa av variablerna i XML-filen.|
|IdMatch|Det här är identifieraren som mönstret försöker matcha – till exempel ett kreditkortsnummer.|
|Nyckelordslistor|XML-filen refererar även till  `keyword_cc_verification` och  `keyword_cc_name`, som är listor med nyckelord, från vilka vi letar efter matchningar inom  `patternsProximity` för entiteten. Dessa visas för närvarande inte i XML-koden.|
|Mönster|Mönstret innehåller en lista över vad typen av känslig information söker efter. Det omfattar nyckelord, reguljära uttryck och interna funktioner som utför uppgifter som att verifiera kontrollsummor. Typer av känslig information kan ha flera mönster med unik konfidens. Det här är användbart när du skapar en typ av känslig information som ger hög konfidens om ett samarbetsbevis påträffas och lägre eller ingen konfidens om inget samarbetsbevis påträffas.|
|Mönstret confidenceLevel|Det här är konfidensnivån som DLP-motorn hittade en matchning för. Den här konfidensnivån associeras med en matchning för mönstret om kraven för mönstret uppfylls. Det här är det konfidensmått som du bör välja när du använder e-postflödesregler för Exchange (även kallade transportregler).|
|patternsProximity|När vi hittar det som liknar ett mönster för kreditkortsnummer är  `patternsProximity` den närhet till det talet där vi söker efter samarbetsbevis.|
|recommendedConfidence|Det här är den konfidensnivå som vi rekommenderar för den här regeln. Den rekommenderade konfidensen gäller för entiteter och tillhörigheter. För entiteter utvärderas aldrig det här talet mot  `confidenceLevel` för mönstret. Det är bara ett förslag som hjälper dig att välja en konfidensnivå om du vill tillämpa en. För tillhörigheter måste  `confidenceLevel` för mönstret vara högre än  `recommendedConfidence` för att en åtgärd för ett e-postflöde ska anropas. `recommendedConfidence` är standardkonfidensnivån som används i e-postflödesregler som anropar en åtgärd. Om du vill kan du manuellt ändra e-postflödesregeln så att den anropas baserat på mönstrets konfidensnivå i stället.|

## <a name="for-more-information"></a>Mer information

- [Entitetsdefinitioner för typer av känslig information](sensitive-information-type-entity-definitions.md)
- [Skapa en anpassad känslig informationstyp](create-a-custom-sensitive-information-type.md)
- [Mer information om dataförlustskydd](dlp-learn-about-dlp.md)