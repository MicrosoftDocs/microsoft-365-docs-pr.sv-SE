---
title: Skapa en nyckelordsordlista
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Lär dig de grundläggande stegen för att skapa en nyckelordsordlista i Säkerhets- och efterlevnadscenter för Office 365.
ms.openlocfilehash: 94bacc2a2fe91fdc35aad753cc2e7db80a374e29
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "52162742"
---
# <a name="create-a-keyword-dictionary"></a>Skapa en nyckelordsordlista

Dataförlustskyddet (DLP) kan identifiera, övervaka och skydda känsliga objekt. Identifieringen av känsliga objekt måste ibland söka efter nyckelord, särskilt när man identifierar generiskt innehåll (t.ex. sjukvårdsrelaterad kommunikation) eller olämpligt och grovt språk. Även om du kan skapa nyckelordslistor för typer av känslig information är de begränsade i storlek och kräver att XML:en ändras för att kunna skapa eller redigera dem. Nyckelordsordlistor ger en enklare hantering av nyckelord och i mycket större skala, med stöd för upp till 1 MB termer (efter komprimering) i ordlistan och med stöd för alla språk. Klientorganisationens gräns är också 1 MB efter komprimering. Gränsen på 1 MB efter komprimering innebär att alla kombinerade ordlistor i en klientorganisation kan innehålla nästan 1 miljon tecken.

## <a name="keyword-dictionary-limits"></a>Begränsningar av nyckelordsordlistor

Det finns en gräns på 50 nyckelordsordlistor som är baserade på känsliga informationstyper som kan skapas per klientorganisation. Om du vill ta reda på hur många nyckelordsordlistor du har i klientorganisationen kan du ansluta med hjälp av metoderna i [Anslut till Säkerhets- och efterlevnadscenter i PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) för att ansluta till klientorganisationen och köra PowerShell-skriptet.

```powershell
$rawFile = $env:TEMP + "\rule.xml"

$kd = Get-DlpKeywordDictionary
$ruleCollections = Get-DlpSensitiveInformationTypeRulePackage
Set-Content -path $rawFile -Encoding Byte -Value $ruleCollections.SerializedClassificationRuleCollection
$UnicodeEncoding = New-Object System.Text.UnicodeEncoding
$FileContent = [System.IO.File]::ReadAllText((Resolve-Path $rawFile), $unicodeEncoding)

if($kd.Count -gt 0)
{
$count = 0
$entities = $FileContent -split "Entity id"
for($j=1;$j -lt $entities.Count;$j++)
{
for($i=0;$i -lt $kd.Count;$i++)
{
$Matches = Select-String -InputObject $entities[$j] -Pattern $kd[$i].Identity -AllMatches
$count = $Matches.Matches.Count + $count
if($Matches.Matches.Count -gt 0) {break}
}
}

Write-Output "Total Keyword Dictionary SIT:"
$count
}
else
{
$Matches = Select-String -InputObject $FileContent -Pattern $kd.Identity -AllMatches
Write-Output "Total Keyword Dictionary SIT:"
$Matches.Matches.Count
}

Remove-Item $rawFile
```

## <a name="basic-steps-to-creating-a-keyword-dictionary"></a>Grundläggande steg för att skapa en nyckelordsordlista

Nyckelorden för ordlistan kan komma från olika källor, oftast från en fil (till exempel en .csv- eller .txt-lista) som importerats i tjänsten eller av en PowerShell-cmdlet, från en lista som du anger direkt i PowerShell-cmdleten eller från en befintlig ordlista. När du skapar en nyckelordsordlista följer du samma huvudsteg:
  
1. Använd **Säkerhets- och efterlevnadscenter** ([https://protection.office.com](https://protection.office.com)) eller anslut till **Säkerhets- &amp; efterlevnadscenter i PowerShell**.
    
2. **Definiera eller läs in dina nyckelord från den avsedda källan**. Både guiden och cmdleten accepterar en kommaavgränsad lista med nyckelord när en anpassad nyckelordsordlista ska skapas. Det här steget varierar därför något beroende på var dina nyckelord kommer från. När de har lästs in kodas de och konverteras till en bytematris innan de importeras.
    
3. **Skapa ordlistan**. Välj ett namn och en beskrivning och skapa ordlistan.

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a>Skapa en nyckelordsordlista i Säkerhets- och efterlevnadscenter

Använd följande steg för att skapa och importera nyckelord till en egen ordlista:

1. Ansluta till Säkerhets- och efterlevnadscenter ([https://protection.office.com](https://protection.office.com)).

2. Gå till **Klassificeringar > Typer av känslig information**.

3. Välj **Skapa** och ange **Namn** och **Beskrivning** för typen av känslig information. Välj sedan **Nästa**

4. Välj **Lägg till ett element** och välj sedan **Ordlista (stora nyckelord)** i listrutan **Identifiera innehåll som innehåller**.

5. Välj **Lägg till en ordlista**

6. Under sökkontrollen väljer du **Du kan skapa nya nyckelordsordlistor här**.

7. Ange ett **Namn** på den egna ordlistan.

8. Välj **Importera** och välj sedan antingen **Från text** eller **Från CSV** beroende på vilken typ av nyckelordsfil du har.

9. Välj nyckelordsfilen från din lokala dator eller nätverksfilresurs i dialogrutan och välj sedan **Öppna**.

10. Välj **Spara** och välj sedan din egna ordlista i listan **Nyckelordsordlistor**.

11. Välj **Lägg till** och sedan **Nästa**.

12. Granska och slutför dina markeringar för den känsliga informationstypen och välj sedan **Slutför**.
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a>Skapa en nyckelordsordlista från en fil med PowerShell

När du behöver skapa en stor ordlista används ofta nyckelord från en fil eller en lista som har exporterats från en annan källa. I det här fallet skapar du en nyckelordsordlista med olämpligt språk som ska granskas i extern e-post. Du måste först [ansluta till Säkerhets- &amp; efterlevnadscenter i PowerShell](/powershell/exchange/connect-to-scc-powershell).
  
1. Kopiera nyckelorden till en textfil och kontrollera att varje nyckelord finns på en separat rad.
    
2. Spara textfilen med Unicode-kodning. I Anteckningar \> **Spara som** \> **Kodning** \> **Unicode**.
    
3. Läs filen till en variabel genom att köra följande cmdlet:
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. Skapa ordlistan genom att köra följande cmdlet:
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```

## <a name="modifying-an-existing-keyword-dictionary"></a>Ändra en befintlig nyckelordsordlista

Du kan behöva ändra nyckelord i någon av dina nyckelordsordlistor eller ändra någon av de inbyggda ordlistorna. För närvarande kan du bara uppdatera en egen nyckelordsordlista med PowerShell. 

Vi kommer till exempel att ändra vissa termer i PowerShell, spara termerna lokalt där du kan ändra dem i ett redigeringsprogram och sedan uppdatera de tidigare termerna. 

Hämta först ordlisteobjektet:
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

Om du skriver ut `$dict` visas de olika variablerna. Nyckelorden lagras i ett objekt i serverdelen, men `$dict.KeywordDictionary` innehåller en strängrepresentation av dem som du använder när du ändrar ordlistan. 

Innan du ändrar ordlistan måste du omvandla strängen med termer till en matris med hjälp av `.split(',')`-metoden. Sedan rensar du bort de oönskade blankstegen mellan nyckelorden med `.trim()`-metoden, så att bara nyckelorden finns kvar. 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

Nu kan du ta bort vissa termer från ordlistan. Eftersom exempelordlistan bara innehåller några få nyckelord kan du i stället gå vidare till att exportera ordlistan och redigera den i Anteckningar, men ordlistor innehåller vanligtvis en stor mängd text så du får först lära dig det här sättet att redigera dem enkelt i PowerShell.
  
I det sista steget sparade du nyckelorden i en matris. Det finns flera sätt att [ta bort objekt från en matris](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), men ett enkelt sätt är att skapa en matris med de termer som du vill ta bort från ordlistan och sedan endast kopiera ordlistetermerna som inte finns i listan med termer att ta bort.
  
Kör kommandot `$terms` för att visa den aktuella listan med termer. Kommandots utdata ser ut så här: 
  
`aarskog's syndrome`
`abandonment`
`abasia`
`abderhalden-kaufmann-lignac`
`abdominalgia`
`abduction contracture`
`abetalipoproteinemia`
`abiotrophy`
`ablatio`
`ablation`
`ablepharia`
`abocclusion`
`abolition`
`aborter`
`abortion`
`abortus`
`aboulomania`
`abrami's disease`

Kör kommandot för att ange de termer som du vill ta bort:
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

Kör kommandot för att ta bort termerna från listan:
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

Kör kommandot `$updatedTerms` för att visa den uppdaterade listan med termer. Kommandots utdata ser ut så här (de angivna termerna har tagits bort): 
  
`aarskog's syndrome`
`abasia`
`abderhalden-kaufmann-lignac`
`abdominalgia`
`abduction contracture`
`abetalipo proteinemia`
`abiotrophy`
`ablation`
`ablepharia`
`abocclusion`
`abolition`
`aborter`
`abortion`
`abortus`
`aboulomania`
`abrami's disease`
```

Now save the dictionary locally and add a few more terms. You could add the terms right here in PowerShell, but you'll still need to export the file locally to ensure it's saved with Unicode encoding and contains the BOM.
  
Save the dictionary locally by running the following:
  
```powershell
Set-Content $updatedTerms -Path "C:\myPath\terms.txt"
```

Öppna filen, lägg till dina andra termer och spara med Unicode-kodning (UTF-16). Nu ska du ladda upp de uppdaterade termerna och uppdatera ordlistan på plats.
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

Nu har ordlistan uppdaterats. Fältet `Identity` hämtar namnet på ordlistan. Om du även vill ändra namnet på ordlistan med cmdleten `set-`, behöver du bara lägga till parametern `-Name` i det som visas ovan med det nya ordlistenamnet. 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a>Använda nyckelordsordlistor i anpassade typer av känslig information och DLP-principer

Nyckelordsordlistor kan användas som en del av matchningskraven för en anpassad typ av känslig information eller som en typ av känslig information. Båda kräver att du skapar en [anpassad typ av känslig information](create-a-custom-sensitive-information-type-in-scc-powershell.md). Skapa en typ av känslig information genom att följa instruktionerna i den länkade artikeln. När du har XML-koden behöver du GUID-identifieraren för ordlistan för att kunna använda den.
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

Om du vill hämta identiteten för ordlistan kör du det här kommandot och kopierar egenskapsvärdet **Identitet**: 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

Kommandots utdata ser ut så här:
  
`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


Klistra in identiteten i XML-koden för din anpassade typ av känslig information och ladda upp den. Nu visas ordlistan i listan med typer av känslig information och du kan använda den direkt i principen, samt ange hur många nyckelord som måste matchas.
  
```xml
<Entity id="d333c6c2-5f4c-4131-9433-db3ef72a89e8" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f" />
      </Pattern>
    </Entity>
    <LocalizedStrings>
      <Resource idRef="d333c6c2-5f4c-4131-9433-db3ef72a89e8">
        <Name default="true" langcode="en-us">Diseases</Name>
        <Description default="true" langcode="en-us">Detects various diseases</Description>
      </Resource>
    </LocalizedStrings>
```

> [!NOTE]
> Microsoft 365 Information Protection har stöd för teckenuppsättningsspråk med dubbla byte i förhandsgranskningen för:
> - Kinesiska (förenklad)
> - Kinesiska (traditionell)
> - Koreanska
> - Japanska
>
>Stödet är tillgängligt för typer av känslig information. Se [Viktig information gällande stöd i Information Protection för teckenuppsättningar med dubbla byte (förhandsversion)](mip-dbcs-relnotes.md) för mer information.