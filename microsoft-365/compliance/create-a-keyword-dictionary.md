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
ms.openlocfilehash: 8d313650f298f2ab26989bec9df1260918f7dd5c
ms.sourcegitcommit: 17d82e5617f0466eb825e15ab88594afcdaf4437
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "53300117"
---
# <a name="create-a-keyword-dictionary"></a><span data-ttu-id="fc2ff-103">Skapa en nyckelordsordlista</span><span class="sxs-lookup"><span data-stu-id="fc2ff-103">Create a keyword dictionary</span></span>

<span data-ttu-id="fc2ff-104">Dataförlustskyddet (DLP) kan identifiera, övervaka och skydda känsliga objekt.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-104">Data loss prevention (DLP) can identify, monitor, and protect your sensitive items.</span></span> <span data-ttu-id="fc2ff-105">Identifieringen av känsliga objekt måste ibland söka efter nyckelord, särskilt när man identifierar generiskt innehåll (t.ex. sjukvårdsrelaterad kommunikation) eller olämpligt och grovt språk.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-105">Identifying sensitive items sometimes requires looking for keywords, particularly when identifying generic content (such as healthcare-related communication), or inappropriate or explicit language.</span></span> <span data-ttu-id="fc2ff-106">Även om du kan skapa nyckelordslistor för typer av känslig information är de begränsade i storlek och kräver att XML:en ändras för att kunna skapa eller redigera dem.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-106">Although you can create keyword lists in sensitive information types, keyword lists are limited in size and require modifying XML to create or edit them.</span></span> <span data-ttu-id="fc2ff-107">Nyckelordsordlistor ger en enklare hantering av nyckelord och i mycket större skala, med stöd för upp till 1 MB termer (efter komprimering) i ordlistan och med stöd för alla språk.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-107">Keyword dictionaries provide simpler management of keywords and at a much larger scale, supporting up to 1 MB of terms (post compression) in the dictionary and support any language.</span></span> <span data-ttu-id="fc2ff-108">Klientorganisationens gräns är också 1 MB efter komprimering.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-108">The tenant limit is also 1 MB after compression.</span></span> <span data-ttu-id="fc2ff-109">Gränsen på 1 MB efter komprimering innebär att alla kombinerade ordlistor i en klientorganisation kan innehålla nästan 1 miljon tecken.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-109">1 MB of post compression limit means that all dictionaries combined across a tenant can have close to 1 million characters.</span></span>

## <a name="keyword-dictionary-limits"></a><span data-ttu-id="fc2ff-110">Begränsningar av nyckelordsordlistor</span><span class="sxs-lookup"><span data-stu-id="fc2ff-110">Keyword dictionary limits</span></span>

<span data-ttu-id="fc2ff-111">Det finns en gräns på 50 nyckelordsordlistor som är baserade på känsliga informationstyper som kan skapas per klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-111">There is a limit of 50 keyword dictionary based sensitive information types that can be created per tenant.</span></span> <span data-ttu-id="fc2ff-112">Om du vill ta reda på hur många nyckelordsordlistor du har i klientorganisationen kan du ansluta med hjälp av metoderna i [Anslut till Säkerhets- och efterlevnadscenter i PowerShell](/powershell/exchange/connect-to-scc-powershell) för att ansluta till klientorganisationen och köra PowerShell-skriptet.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-112">To find out how many keyword dictionaries you have in your tenant, connect using the procedures in [Connect to the Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) to connect to your tenant and run this PowerShell script.</span></span>

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

## <a name="basic-steps-to-creating-a-keyword-dictionary"></a><span data-ttu-id="fc2ff-113">Grundläggande steg för att skapa en nyckelordsordlista</span><span class="sxs-lookup"><span data-stu-id="fc2ff-113">Basic steps to creating a keyword dictionary</span></span>

<span data-ttu-id="fc2ff-p103">Nyckelorden för ordlistan kan komma från olika källor, oftast från en fil (till exempel en .csv- eller .txt-lista) som importerats i tjänsten eller av en PowerShell-cmdlet, från en lista som du anger direkt i PowerShell-cmdleten eller från en befintlig ordlista. När du skapar en nyckelordsordlista följer du samma huvudsteg:</span><span class="sxs-lookup"><span data-stu-id="fc2ff-p103">The keywords for your dictionary could come from various sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:</span></span>
  
1. <span data-ttu-id="fc2ff-116">Använd **Säkerhets- och efterlevnadscenter** ([https://protection.office.com](https://protection.office.com)) eller anslut till **Säkerhets- &amp; efterlevnadscenter i PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-116">Use the **Security & Compliance Center** ([https://protection.office.com](https://protection.office.com)) or connect to  **Security &amp; Compliance Center PowerShell**.</span></span>
    
2. <span data-ttu-id="fc2ff-117">**Definiera eller läs in dina nyckelord från den avsedda källan**.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-117">**Define or load your keywords from your intended source**.</span></span> <span data-ttu-id="fc2ff-118">Både guiden och cmdleten accepterar en kommaavgränsad lista med nyckelord när en anpassad nyckelordsordlista ska skapas. Det här steget varierar därför något beroende på var dina nyckelord kommer från.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-118">The wizard and the cmdlet both accept a comma-separated list of keywords to create a custom keyword dictionary, so this step will vary slightly depending on where your keywords come from.</span></span> <span data-ttu-id="fc2ff-119">När de har lästs in kodas de och konverteras till en bytematris innan de importeras.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-119">Once loaded, they're encoded and converted to a byte array before they're imported.</span></span>
    
3. <span data-ttu-id="fc2ff-120">**Skapa ordlistan**.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-120">**Create your dictionary**.</span></span> <span data-ttu-id="fc2ff-121">Välj ett namn och en beskrivning och skapa ordlistan.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-121">Choose a name and description and create your dictionary.</span></span>

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a><span data-ttu-id="fc2ff-122">Skapa en nyckelordsordlista i Säkerhets- och efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="fc2ff-122">Create a keyword dictionary using the Security & Compliance Center</span></span>

<span data-ttu-id="fc2ff-123">Använd följande steg för att skapa och importera nyckelord till en egen ordlista:</span><span class="sxs-lookup"><span data-stu-id="fc2ff-123">Use the following steps to create and import keywords for a custom dictionary:</span></span>

1. <span data-ttu-id="fc2ff-124">Ansluta till Säkerhets- och efterlevnadscenter ([https://protection.office.com](https://protection.office.com)).</span><span class="sxs-lookup"><span data-stu-id="fc2ff-124">Connect to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span>

2. <span data-ttu-id="fc2ff-125">Gå till **Klassificeringar > Typer av känslig information**.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-125">Navigate to **Classifications > Sensitive info types**.</span></span>

3. <span data-ttu-id="fc2ff-126">Välj **Skapa** och ange **Namn** och **Beskrivning** för typen av känslig information. Välj sedan **Nästa**</span><span class="sxs-lookup"><span data-stu-id="fc2ff-126">Select **Create** and enter a **Name** and **Description** for your sensitive info type, then select **Next**</span></span>

4. <span data-ttu-id="fc2ff-127">Välj **Lägg till ett element** och välj sedan **Ordlista (stora nyckelord)** i listrutan **Identifiera innehåll som innehåller**.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-127">Select **Add an element**, then select **Dictionary (Large keywords)** in the **Detect content containing** drop-down list.</span></span>

5. <span data-ttu-id="fc2ff-128">Välj **Lägg till en ordlista**</span><span class="sxs-lookup"><span data-stu-id="fc2ff-128">Select **Add a dictionary**</span></span>

6. <span data-ttu-id="fc2ff-129">Under sökkontrollen väljer du **Du kan skapa nya nyckelordsordlistor här**.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-129">Under the Search control, select **You can create new keyword dictionaries here**.</span></span>

7. <span data-ttu-id="fc2ff-130">Ange ett **Namn** på den egna ordlistan.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-130">Enter a **Name** for your custom dictionary.</span></span>

8. <span data-ttu-id="fc2ff-131">Välj **Importera** och välj sedan antingen **Från text** eller **Från CSV** beroende på vilken typ av nyckelordsfil du har.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-131">Select **Import**, and select either **From text** or **From csv** depending on your keyword file type.</span></span>

9. <span data-ttu-id="fc2ff-132">Välj nyckelordsfilen från din lokala dator eller nätverksfilresurs i dialogrutan och välj sedan **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-132">In the file dialog, select the keyword file from your local PC or network file share, then select **Open**.</span></span>

10. <span data-ttu-id="fc2ff-133">Välj **Spara** och välj sedan din egna ordlista i listan **Nyckelordsordlistor**.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-133">Select **Save**, then select your custom dictionary from the **Keyword dictionaries** list.</span></span>

11. <span data-ttu-id="fc2ff-134">Välj **Lägg till** och sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-134">Select **Add**, then select **Next**.</span></span>

12. <span data-ttu-id="fc2ff-135">Granska och slutför dina markeringar för den känsliga informationstypen och välj sedan **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-135">Review and finalize your sensitive info type selections, then select **Finish**.</span></span>
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a><span data-ttu-id="fc2ff-136">Skapa en nyckelordsordlista från en fil med PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc2ff-136">Create a keyword dictionary from a file using PowerShell</span></span>

<span data-ttu-id="fc2ff-137">När du behöver skapa en stor ordlista används ofta nyckelord från en fil eller en lista som har exporterats från en annan källa.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-137">Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source.</span></span> <span data-ttu-id="fc2ff-138">I det här fallet skapar du en nyckelordsordlista med olämpligt språk som ska granskas i extern e-post.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-138">In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email.</span></span> <span data-ttu-id="fc2ff-139">Du måste först [ansluta till Säkerhets- &amp; efterlevnadscenter i PowerShell](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="fc2ff-139">You must first [Connect to Security &amp; Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>
  
1. <span data-ttu-id="fc2ff-140">Kopiera nyckelorden till en textfil och kontrollera att varje nyckelord finns på en separat rad.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-140">Copy the keywords into a text file and make sure that each keyword is on a separate line.</span></span>
    
2. <span data-ttu-id="fc2ff-141">Spara textfilen med Unicode-kodning.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-141">Save the text file with Unicode encoding.</span></span> <span data-ttu-id="fc2ff-142">I Anteckningar \> **Spara som** \> **Kodning** \> **Unicode**.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-142">In Notepad \> **Save As** \> **Encoding** \> **Unicode**.</span></span>
    
3. <span data-ttu-id="fc2ff-143">Läs filen till en variabel genom att köra följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="fc2ff-143">Read the file into a variable by running this cmdlet:</span></span>
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. <span data-ttu-id="fc2ff-144">Skapa ordlistan genom att köra följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="fc2ff-144">Create the dictionary by running this cmdlet:</span></span>
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a><span data-ttu-id="fc2ff-145">Använda nyckelordsordlistor i anpassade typer av känslig information och DLP-principer</span><span class="sxs-lookup"><span data-stu-id="fc2ff-145">Using keyword dictionaries in custom sensitive information types and DLP policies</span></span>

<span data-ttu-id="fc2ff-146">Nyckelordsordlistor kan användas som en del av matchningskraven för en anpassad typ av känslig information eller som en typ av känslig information.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-146">Keyword dictionaries can be used as part of the match requirements for a custom sensitive information type, or as a sensitive information type themselves.</span></span> <span data-ttu-id="fc2ff-147">Båda kräver att du skapar en [anpassad typ av känslig information](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="fc2ff-147">Both require you to create a [custom sensitive information type](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span> <span data-ttu-id="fc2ff-148">Skapa en typ av känslig information genom att följa instruktionerna i den länkade artikeln.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-148">Follow the instructions in the linked article to create a sensitive information type.</span></span> <span data-ttu-id="fc2ff-149">När du har XML-koden behöver du GUID-identifieraren för ordlistan för att kunna använda den.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-149">Once you have the XML, you'll need the GUID identifier for the dictionary to use it.</span></span>
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

<span data-ttu-id="fc2ff-150">Om du vill hämta identiteten för ordlistan kör du det här kommandot och kopierar egenskapsvärdet **Identitet**:</span><span class="sxs-lookup"><span data-stu-id="fc2ff-150">To get the identity of your dictionary, run this command and copy the **Identity** property value:</span></span> 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="fc2ff-151">Kommandots utdata ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="fc2ff-151">The output of the command looks like this:</span></span>
  
<span data-ttu-id="fc2ff-152">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span><span class="sxs-lookup"><span data-stu-id="fc2ff-152">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span></span>
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


<span data-ttu-id="fc2ff-p109">Klistra in identiteten i XML-koden för din anpassade typ av känslig information och ladda upp den. Nu visas ordlistan i listan med typer av känslig information och du kan använda den direkt i principen, samt ange hur många nyckelord som måste matchas.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-p109">Paste the identity into your custom sensitive information type's XML and upload it. Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.</span></span>
  
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
> <span data-ttu-id="fc2ff-155">Microsoft 365 Information Protection har stöd för teckenuppsättningsspråk med dubbla byte i förhandsgranskningen för:</span><span class="sxs-lookup"><span data-stu-id="fc2ff-155">Microsoft 365 Information Protection supports double byte character set languages for:</span></span>
> - <span data-ttu-id="fc2ff-156">Kinesiska (förenklad)</span><span class="sxs-lookup"><span data-stu-id="fc2ff-156">Chinese (simplified)</span></span>
> - <span data-ttu-id="fc2ff-157">Kinesiska (traditionell)</span><span class="sxs-lookup"><span data-stu-id="fc2ff-157">Chinese (traditional)</span></span>
> - <span data-ttu-id="fc2ff-158">Koreanska</span><span class="sxs-lookup"><span data-stu-id="fc2ff-158">Korean</span></span>
> - <span data-ttu-id="fc2ff-159">Japanska</span><span class="sxs-lookup"><span data-stu-id="fc2ff-159">Japanese</span></span>
>
><span data-ttu-id="fc2ff-160">Stödet är tillgängligt för typer av känslig information.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-160">This support is available for sensitive information types.</span></span> <span data-ttu-id="fc2ff-161">Se [Viktig information gällande stöd i Information Protection för teckenuppsättningar med dubbla byte (förhandsversion)](mip-dbcs-relnotes.md) för mer information.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-161">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

> [!TIP]
> <span data-ttu-id="fc2ff-162">Om du vill identifiera mönster som innehåller kinesiska/japanska tecken och en-byte-tecken eller för att identifiera mönster som innehåller kinesiska/japanska och engelska, definierar du två varianter av nyckelordet eller regex.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-162">To detect patterns containing Chinese/Japanese characters and single byte characters or to detect patterns containing Chinese/Japanese and English, define two variants of the keyword or regex.</span></span> 
>
> <span data-ttu-id="fc2ff-163">Om du till exempel vill identifiera ett nyckelord som "机密的dokument" använder du två varianter av nyckelordet. en med ett blanksteg mellan den japanska och den engelska texten och en annan utan blanksteg mellan den japanska och den engelska texten.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-163">For example, to detect a keyword like "机密的document", use two variants of the keyword; one with a space between the Japanese and English text and another without a space between the Japanese and English text.</span></span> <span data-ttu-id="fc2ff-164">Nyckelorden som ska läggas till i SIT ska därför vara "dokumentet "机密的 dokument" och ""机密的dokument".</span><span class="sxs-lookup"><span data-stu-id="fc2ff-164">So, the keywords to be added in the SIT should be "机密的 document" and "机密的document".</span></span> <span data-ttu-id="fc2ff-165">På samma sätt bör två varianter användas för att identifiera frasen "東京オリンピック2020". "東京オリンピック 2020" och "東京オリンピック2020".</span><span class="sxs-lookup"><span data-stu-id="fc2ff-165">Similarly, to detect a phrase "東京オリンピック2020", two variants should be used; "東京オリンピック 2020" and "東京オリンピック2020".</span></span>
>
> <span data-ttu-id="fc2ff-p112">När du skapar ett regex med ett bindestreck med dubbla byte eller en period med dubbla byte ser du till att undanta båda tecknen som ett av bindestreck eller en punkt i ett regex. Här är ett exempel på regex som referens:</span><span class="sxs-lookup"><span data-stu-id="fc2ff-p112">While creating a regex using a double byte hyphen or a double byte period, make sure to escape both the characters like one would escape a hyphen or period in a regex. Here is a sample regex for reference:</span></span>
>
>    - <span data-ttu-id="fc2ff-168">(?<!\d)([４][０-９]{3}[\-?\－\t]\*[０-９]{4}</span><span class="sxs-lookup"><span data-stu-id="fc2ff-168">(?<!\d)([４][０-９]{3}[\-?\－\t]\*[０-９]{4}</span></span>
>
> <span data-ttu-id="fc2ff-169">Vi rekommenderar att du använder en strängmatchning i stället för en ordmatchning i en nyckelordslista.</span><span class="sxs-lookup"><span data-stu-id="fc2ff-169">We recommend using a string match instead of a word match in a keyword list.</span></span>
