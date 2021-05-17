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
# <a name="modify-exact-data-match-schema-to-use-configurable-match"></a><span data-ttu-id="19d50-103">Ändra Exact Data Match-schemat till att använda konfigurerbar matchning</span><span class="sxs-lookup"><span data-stu-id="19d50-103">Modify Exact Data Match schema to use configurable match</span></span>

<span data-ttu-id="19d50-104">Med en EDM-baserad (Exact Data Match) klassificering kan du skapa anpassade typer av känslig information som refererar till exakta värden i en databas med känslig information.</span><span class="sxs-lookup"><span data-stu-id="19d50-104">Exact Data Match (EDM) based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="19d50-105">När du behöver tillåta varianter av den exakta strängen kan du använda *konfigurerbar matchning* som anger att Microsoft 365 ska ignorera skiftläge och vissa avgränsare.</span><span class="sxs-lookup"><span data-stu-id="19d50-105">When you need to allow for variants of a exact string, you can use *configurable match* to tell Microsoft 365 to ignore case and some delimiters.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="19d50-106">Använd den här metoden om du vill ändra ett befintligt EDM-schema och en datafil.</span><span class="sxs-lookup"><span data-stu-id="19d50-106">Use this procedure to modify an existing EDM schema and data file.</span></span>

1. <span data-ttu-id="19d50-107">Avinstallera **EdmUploadAgent.exe** från den dator som du använder för att ansluta till Microsoft 365, för att EDM-schemat och datafilen ska kunna laddas upp.</span><span class="sxs-lookup"><span data-stu-id="19d50-107">Uninstall the **EdmUploadAgent.exe** from the computer that you use to connect to Microsoft 365 for EDM schema and data file upload purposes.</span></span>

2. <span data-ttu-id="19d50-108">Ladda ned lämplig **EdmUploadAgent.exe**-fil för din prenumeration med hjälp av länkarna nedan:</span><span class="sxs-lookup"><span data-stu-id="19d50-108">Download the appropriate **EdmUploadAgent.exe** file for your subscription using the links below:</span></span>
    - <span data-ttu-id="19d50-109">[Commercial + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) – De flesta kommersiella kunder bör använda denna</span><span class="sxs-lookup"><span data-stu-id="19d50-109">[Commercial + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - most commercial customers should use this</span></span>
    - <span data-ttu-id="19d50-110">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) – Specifikt för myndighetsmolnprenumeranter som kräver hög säkerhet</span><span class="sxs-lookup"><span data-stu-id="19d50-110">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - This is specifically for high security government cloud subscribers</span></span>
    - <span data-ttu-id="19d50-111">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) – Specifikt för USA:s försvarsdepartement (Department of Defense)</span><span class="sxs-lookup"><span data-stu-id="19d50-111">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - this is specifically for United States Department of Defense cloud customers</span></span>

3. <span data-ttu-id="19d50-112">Godkänn EDM-uppladdningsagenten, öppna kommandotolken (som administratör) och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="19d50-112">Authorize the EDM Upload Agent, open Command Prompt window (as an administrator) and run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

4. <span data-ttu-id="19d50-113">Om du inte har en aktuell kopia av det befintliga schemat måste du ladda ned en kopia av det. Kör det följande kommando:</span><span class="sxs-lookup"><span data-stu-id="19d50-113">If you don't have a current copy of the existing schema, you'll need to download a copy of the existing schema, run this command:</span></span>

    `EdmUploadAgent.exe /SaveSchema /DataStoreName <dataStoreName> [/OutputDir [Output dir location]]`

5. <span data-ttu-id="19d50-114">Anpassa schemat så att varje kolumn använder ”caseInsensitive” och/eller ”ignoredDelimiters”.</span><span class="sxs-lookup"><span data-stu-id="19d50-114">Customize the schema so each column utilizes “caseInsensitive” and / or “ignoredDelimiters”.</span></span>  <span data-ttu-id="19d50-115">Standardvärdet för ”caseInsensitive” är ”false” och ”ignoredDelimiters” är en tom sträng.</span><span class="sxs-lookup"><span data-stu-id="19d50-115">The default value for “caseInsensitive” is “false” and for “ignoredDelimiters”, it is an empty string.</span></span> 

> [!NOTE]
> <span data-ttu-id="19d50-116">Den underliggande anpassade typen av känslig information, eller den inbyggda typen av känslig information som används för att identifiera det allmänna Regex-mönstret, måste ha stöd för identifiering av de varianter på indata som finns i listan med ignoredDelimiters.</span><span class="sxs-lookup"><span data-stu-id="19d50-116">The underlying custom sensitive information type or built in sensitive information type used to detect the general regex pattern must support detection of the variations inputs listed with ignoredDelimiters.</span></span> <span data-ttu-id="19d50-117">Den inbyggda typen av känslig information för amerikanska socialförsäkringsnummer (SSN) kan till exempel identifiera variationer i datan med streck, blanksteg eller saknade blanksteg mellan de grupperade tal som utgör SSN-numret.</span><span class="sxs-lookup"><span data-stu-id="19d50-117">For example, the built in U.S. social security number (SSN) sensitive information type can detect variations in the data that include dashes, spaces, or lack of spaces between the grouped numbers that make up the SSN.</span></span> <span data-ttu-id="19d50-118">Därför är de enda avgränsare som är relevanta att inkludera i EDM:s ignoredDelimiters för SSN-data streck och blanksteg.</span><span class="sxs-lookup"><span data-stu-id="19d50-118">As a result, the only delimiters that are relevant to include in EDM’s ignoredDelimiters for SSN data are: dash and space.</span></span>

<span data-ttu-id="19d50-119">Här är ett exempelschema som simulerar skiftlägesokänsliga matchningar genom att skapa de extra kolumner som behövs för att känna igen skiftlägesvariationer i känsliga data.</span><span class="sxs-lookup"><span data-stu-id="19d50-119">Here is a sample schema that simulates case insensitive match by creating the extra columns needed to recognize case variations in the sensitive data.</span></span>

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

<span data-ttu-id="19d50-120">I exemplet ovan behövs inte längre varianterna i den ursprungliga kolumnen `PolicyNumber` om både `caseInsensitive` och `ignoredDelimiters` läggs till.</span><span class="sxs-lookup"><span data-stu-id="19d50-120">In the above example, the variations of the original `PolicyNumber` column will no longer be needed if both `caseInsensitive` and `ignoredDelimiters` are added.</span></span>

<span data-ttu-id="19d50-121">Om du vill uppdatera schemat så att EDM använder konfigurerbara matchningar, använder du flaggorna `caseInsensitive` och `ignoredDelimiters`.</span><span class="sxs-lookup"><span data-stu-id="19d50-121">To update this schema so that EDM uses configurable match use the `caseInsensitive` and `ignoredDelimiters` flags.</span></span>  <span data-ttu-id="19d50-122">Det ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="19d50-122">Here's how that looks:</span></span>

```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
  <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
         <Field name="PolicyNumber" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
  </DataStore>
</EdmSchema>
```

<span data-ttu-id="19d50-123">Flaggan `ignoredDelimiters` stöder alla icke-alfanumeriska tecken. Här är några exempel:</span><span class="sxs-lookup"><span data-stu-id="19d50-123">The `ignoredDelimiters` flag supports any non-alphanumeric character, here are some examples:</span></span>
- <span data-ttu-id="19d50-124">\.</span><span class="sxs-lookup"><span data-stu-id="19d50-124">\.</span></span>
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

<span data-ttu-id="19d50-125">Flaggan `ignoredDelimiters` stöder inte:</span><span class="sxs-lookup"><span data-stu-id="19d50-125">The `ignoredDelimiters` flag doesn't support:</span></span>
- <span data-ttu-id="19d50-126">tecknen 0–9</span><span class="sxs-lookup"><span data-stu-id="19d50-126">characters 0-9</span></span>
- <span data-ttu-id="19d50-127">A–Z</span><span class="sxs-lookup"><span data-stu-id="19d50-127">A-Z</span></span>
- <span data-ttu-id="19d50-128">a–z</span><span class="sxs-lookup"><span data-stu-id="19d50-128">a-z</span></span>
- \"
- \,

6. <span data-ttu-id="19d50-129">Anslut till Säkerhets- och efterlevnadscenter med hjälp av metoderna i [Ansluta till Säkerhets- och efterlevnadscentret i PowerShell](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="19d50-129">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

> [!NOTE]
> <span data-ttu-id="19d50-130">Om din organisation har konfigurerat [Kundnyckel för Microsoft 365 på klientorganisationsnivå (allmänt tillgänglig förhandsversion)](customer-key-tenant-level.md#overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview) används Exact Data Match automatiskt för krypteringsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="19d50-130">If your organization has set up [Customer Key for Microsoft 365 at the tenant level (public preview)](customer-key-tenant-level.md#overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview), Exact data match will make use of its encryption functionality automatically.</span></span> <span data-ttu-id="19d50-131">Det här är endast tillgängligt för E5-licensierade klientorganisationer i det kommersiella molnet.</span><span class="sxs-lookup"><span data-stu-id="19d50-131">This is available only to E5 licensed tenants in the Commercial cloud.</span></span>

7. <span data-ttu-id="19d50-132">Uppdatera schemat genom att köra en cmdlet i taget:</span><span class="sxs-lookup"><span data-stu-id="19d50-132">Update your schema by running these cmdlets one at a time:</span></span>

`$edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0`

`Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true`

8. <span data-ttu-id="19d50-133">Uppdatera datafilen så att den matchar den nya schemaversionen om det behövs</span><span class="sxs-lookup"><span data-stu-id="19d50-133">If necessary, update the data file to match the new schema version</span></span>

> [!TIP]
> <span data-ttu-id="19d50-134">Du kan även köra en validering av CSV-filen innan du laddar upp den genom att köra:</span><span class="sxs-lookup"><span data-stu-id="19d50-134">Optionally, you can run a validation against your csv file before uploading by running:</span></span>
>
>`EdmUploadAgent.exe /ValidateData /DataFile [data file] [schema file]`
>
><span data-ttu-id="19d50-135">Mer information om alla parametrar som stöds av EdmUploadAgent.exe får du genom att köra</span><span class="sxs-lookup"><span data-stu-id="19d50-135">For more information on all the EdmUploadAgent.exe >supported parameters run</span></span>
>
> `EdmUploadAgent.exe /?`

9. <span data-ttu-id="19d50-136">Öppna kommandotolken (som administratör) och kör följande kommando för att skapa en hash och ladda upp känsliga data:</span><span class="sxs-lookup"><span data-stu-id="19d50-136">Open Command Prompt window (as an administrator) and run the following command to hash and upload your sensitive data:</span></span>

    `EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Salt [custom salt] /Schema [Schema file]`


## <a name="related-articles"></a><span data-ttu-id="19d50-137">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="19d50-137">Related articles</span></span>

- [<span data-ttu-id="19d50-138">Skapa en anpassad typ av känslig information med Exact Data Match-baserad klassificering</span><span class="sxs-lookup"><span data-stu-id="19d50-138">Create a custom sensitive information type with Exact Data Match based classification</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [<span data-ttu-id="19d50-139">Entitetsdefinitioner för typer av känslig information</span><span class="sxs-lookup"><span data-stu-id="19d50-139">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="19d50-140">Anpassade typer av känslig information</span><span class="sxs-lookup"><span data-stu-id="19d50-140">Custom sensitive information types</span></span>](./sensitive-information-type-learn-about.md)
- [<span data-ttu-id="19d50-141">Mer information om dataförlustskydd</span><span class="sxs-lookup"><span data-stu-id="19d50-141">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="19d50-142">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="19d50-142">Microsoft Cloud App Security</span></span>](/cloud-app-security)
- [<span data-ttu-id="19d50-143">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="19d50-143">New-DlpEdmSchema</span></span>](/powershell/module/exchange/new-dlpedmschema)