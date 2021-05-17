---
title: Ändra Exact Data Match-schemat till att använda konfigurerbar matchning
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
description: Se hur du ändrar ett EDM-schema till att använda konfigurerbar matchning.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7d470b986d4a94206935efb832deec7171f8e404
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52163005"
---
# <a name="modify-exact-data-match-schema-to-use-configurable-match"></a>Ändra Exact Data Match-schemat till att använda konfigurerbar matchning

Med en EDM-baserad (Exact Data Match) klassificering kan du skapa anpassade typer av känslig information som refererar till exakta värden i en databas med känslig information. När du behöver tillåta varianter av den exakta strängen kan du använda *konfigurerbar matchning* som anger att Microsoft 365 ska ignorera skiftläge och vissa avgränsare. 

> [!IMPORTANT]
> Använd den här metoden om du vill ändra ett befintligt EDM-schema och en datafil.

1. Avinstallera **EdmUploadAgent.exe** från den dator som du använder för att ansluta till Microsoft 365, för att EDM-schemat och datafilen ska kunna laddas upp.

2. Ladda ned lämplig **EdmUploadAgent.exe**-fil för din prenumeration med hjälp av länkarna nedan:
    - [Commercial + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) – De flesta kommersiella kunder bör använda denna
    - [GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) – Specifikt för myndighetsmolnprenumeranter som kräver hög säkerhet
    - [DoD](https://go.microsoft.com/fwlink/?linkid=2137807) – Specifikt för USA:s försvarsdepartement (Department of Defense)

3. Godkänn EDM-uppladdningsagenten, öppna kommandotolken (som administratör) och kör följande kommando:

   `EdmUploadAgent.exe /Authorize`

4. Om du inte har en aktuell kopia av det befintliga schemat måste du ladda ned en kopia av det. Kör det följande kommando:

    `EdmUploadAgent.exe /SaveSchema /DataStoreName <dataStoreName> [/OutputDir [Output dir location]]`

5. Anpassa schemat så att varje kolumn använder ”caseInsensitive” och/eller ”ignoredDelimiters”.  Standardvärdet för ”caseInsensitive” är ”false” och ”ignoredDelimiters” är en tom sträng. 

> [!NOTE]
> Den underliggande anpassade typen av känslig information, eller den inbyggda typen av känslig information som används för att identifiera det allmänna Regex-mönstret, måste ha stöd för identifiering av de varianter på indata som finns i listan med ignoredDelimiters. Den inbyggda typen av känslig information för amerikanska socialförsäkringsnummer (SSN) kan till exempel identifiera variationer i datan med streck, blanksteg eller saknade blanksteg mellan de grupperade tal som utgör SSN-numret. Därför är de enda avgränsare som är relevanta att inkludera i EDM:s ignoredDelimiters för SSN-data streck och blanksteg.

Här är ett exempelschema som simulerar skiftlägesokänsliga matchningar genom att skapa de extra kolumner som behövs för att känna igen skiftlägesvariationer i känsliga data.

```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
  <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
           <Field name="PolicyNumber" searchable="true" />
           <Field name="PolicyNumberLowerCase" searchable="true" />
           <Field name="PolicyNumberUpperCase" searchable="true" />
           <Field name="PolicyNumberCapitalLetters" searchable="true" />
  </DataStore>
</EdmSchema>
```

I exemplet ovan behövs inte längre varianterna i den ursprungliga kolumnen `PolicyNumber` om både `caseInsensitive` och `ignoredDelimiters` läggs till.

Om du vill uppdatera schemat så att EDM använder konfigurerbara matchningar, använder du flaggorna `caseInsensitive` och `ignoredDelimiters`.  Det ser ut så här:

```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
  <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
         <Field name="PolicyNumber" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
  </DataStore>
</EdmSchema>
```

Flaggan `ignoredDelimiters` stöder alla icke-alfanumeriska tecken. Här är några exempel:
- \.
- \-
- \/
- \_
- \*
- \^
- \#
- \!
- \?
- \[
- \]
- \{
- \}
- \\
- \~
- \;

Flaggan `ignoredDelimiters` stöder inte:
- tecknen 0–9
- A–Z
- a–z
- \"
- \,

6. Anslut till Säkerhets- och efterlevnadscenter med hjälp av metoderna i [Ansluta till Säkerhets- och efterlevnadscentret i PowerShell](/powershell/exchange/connect-to-scc-powershell).

> [!NOTE]
> Om din organisation har konfigurerat [Kundnyckel för Microsoft 365 på klientorganisationsnivå (allmänt tillgänglig förhandsversion)](customer-key-tenant-level.md#overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview) används Exact Data Match automatiskt för krypteringsfunktionen. Det här är endast tillgängligt för E5-licensierade klientorganisationer i det kommersiella molnet.

7. Uppdatera schemat genom att köra en cmdlet i taget:

`$edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0`

`Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true`

8. Uppdatera datafilen så att den matchar den nya schemaversionen om det behövs

> [!TIP]
> Du kan även köra en validering av CSV-filen innan du laddar upp den genom att köra:
>
>`EdmUploadAgent.exe /ValidateData /DataFile [data file] [schema file]`
>
>Mer information om alla parametrar som stöds av EdmUploadAgent.exe får du genom att köra
>
> `EdmUploadAgent.exe /?`

9. Öppna kommandotolken (som administratör) och kör följande kommando för att skapa en hash och ladda upp känsliga data:

    `EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Salt [custom salt] /Schema [Schema file]`


## <a name="related-articles"></a>Relaterade artiklar

- [Skapa en anpassad typ av känslig information med Exact Data Match-baserad klassificering](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [Entitetsdefinitioner för typer av känslig information](sensitive-information-type-entity-definitions.md)
- [Anpassade typer av känslig information](./sensitive-information-type-learn-about.md)
- [Mer information om dataförlustskydd](dlp-learn-about-dlp.md)
- [Microsoft Cloud App Security](/cloud-app-security)
- [New-DlpEdmSchema](/powershell/module/exchange/new-dlpedmschema)