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
# <a name="create-a-keyword-dictionary"></a><span data-ttu-id="b0498-103">Skapa en nyckelordsordlista</span><span class="sxs-lookup"><span data-stu-id="b0498-103">Create a keyword dictionary</span></span>

<span data-ttu-id="b0498-104">Dataförlustskyddet (DLP) kan identifiera, övervaka och skydda känsliga objekt.</span><span class="sxs-lookup"><span data-stu-id="b0498-104">Data loss prevention (DLP) can identify, monitor, and protect your sensitive items.</span></span> <span data-ttu-id="b0498-105">Identifieringen av känsliga objekt måste ibland söka efter nyckelord, särskilt när man identifierar generiskt innehåll (t.ex. sjukvårdsrelaterad kommunikation) eller olämpligt och grovt språk.</span><span class="sxs-lookup"><span data-stu-id="b0498-105">Identifying sensitive items sometimes requires looking for keywords, particularly when identifying generic content (such as healthcare-related communication), or inappropriate or explicit language.</span></span> <span data-ttu-id="b0498-106">Även om du kan skapa nyckelordslistor för typer av känslig information är de begränsade i storlek och kräver att XML:en ändras för att kunna skapa eller redigera dem.</span><span class="sxs-lookup"><span data-stu-id="b0498-106">Although you can create keyword lists in sensitive information types, keyword lists are limited in size and require modifying XML to create or edit them.</span></span> <span data-ttu-id="b0498-107">Nyckelordsordlistor ger en enklare hantering av nyckelord och i mycket större skala, med stöd för upp till 1 MB termer (efter komprimering) i ordlistan och med stöd för alla språk.</span><span class="sxs-lookup"><span data-stu-id="b0498-107">Keyword dictionaries provide simpler management of keywords and at a much larger scale, supporting up to 1 MB of terms (post compression) in the dictionary and support any language.</span></span> <span data-ttu-id="b0498-108">Klientorganisationens gräns är också 1 MB efter komprimering.</span><span class="sxs-lookup"><span data-stu-id="b0498-108">The tenant limit is also 1 MB after compression.</span></span> <span data-ttu-id="b0498-109">Gränsen på 1 MB efter komprimering innebär att alla kombinerade ordlistor i en klientorganisation kan innehålla nästan 1 miljon tecken.</span><span class="sxs-lookup"><span data-stu-id="b0498-109">1 MB of post compression limit means that all dictionaries combined across a tenant can have close to 1 million characters.</span></span>

## <a name="keyword-dictionary-limits"></a><span data-ttu-id="b0498-110">Begränsningar av nyckelordsordlistor</span><span class="sxs-lookup"><span data-stu-id="b0498-110">Keyword dictionary limits</span></span>

<span data-ttu-id="b0498-111">Det finns en gräns på 50 nyckelordsordlistor som är baserade på känsliga informationstyper som kan skapas per klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="b0498-111">There is a limit of 50 keyword dictionary based sensitive information types that can be created per tenant.</span></span> <span data-ttu-id="b0498-112">Om du vill ta reda på hur många nyckelordsordlistor du har i klientorganisationen kan du ansluta med hjälp av metoderna i [Anslut till Säkerhets- och efterlevnadscenter i PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) för att ansluta till klientorganisationen och köra PowerShell-skriptet.</span><span class="sxs-lookup"><span data-stu-id="b0498-112">To find out how many keyword dictionaries you have in your tenant, connect using the procedures in [Connect to the Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) to connect to your tenant and run this PowerShell script.</span></span>

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

## <a name="basic-steps-to-creating-a-keyword-dictionary"></a><span data-ttu-id="b0498-113">Grundläggande steg för att skapa en nyckelordsordlista</span><span class="sxs-lookup"><span data-stu-id="b0498-113">Basic steps to creating a keyword dictionary</span></span>

<span data-ttu-id="b0498-114">Nyckelorden för ordlistan kan komma från olika källor, oftast från en fil (till exempel en .csv- eller .txt-lista) som importerats i tjänsten eller av en PowerShell-cmdlet, från en lista som du anger direkt i PowerShell-cmdleten eller från en befintlig ordlista.</span><span class="sxs-lookup"><span data-stu-id="b0498-114">The keywords for your dictionary could come from various sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary.</span></span> <span data-ttu-id="b0498-115">När du skapar en nyckelordsordlista följer du samma huvudsteg:</span><span class="sxs-lookup"><span data-stu-id="b0498-115">When you create a keyword dictionary, you follow the same core steps:</span></span>
  
1. <span data-ttu-id="b0498-116">Använd **Säkerhets- och efterlevnadscenter** ([https://protection.office.com](https://protection.office.com)) eller anslut till **Säkerhets- &amp; efterlevnadscenter i PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="b0498-116">Use the **Security & Compliance Center** ([https://protection.office.com](https://protection.office.com)) or connect to  **Security &amp; Compliance Center PowerShell**.</span></span>
    
2. <span data-ttu-id="b0498-117">**Definiera eller läs in dina nyckelord från den avsedda källan**.</span><span class="sxs-lookup"><span data-stu-id="b0498-117">**Define or load your keywords from your intended source**.</span></span> <span data-ttu-id="b0498-118">Både guiden och cmdleten accepterar en kommaavgränsad lista med nyckelord när en anpassad nyckelordsordlista ska skapas. Det här steget varierar därför något beroende på var dina nyckelord kommer från.</span><span class="sxs-lookup"><span data-stu-id="b0498-118">The wizard and the cmdlet both accept a comma-separated list of keywords to create a custom keyword dictionary, so this step will vary slightly depending on where your keywords come from.</span></span> <span data-ttu-id="b0498-119">När de har lästs in kodas de och konverteras till en bytematris innan de importeras.</span><span class="sxs-lookup"><span data-stu-id="b0498-119">Once loaded, they're encoded and converted to a byte array before they're imported.</span></span>
    
3. <span data-ttu-id="b0498-120">**Skapa ordlistan**.</span><span class="sxs-lookup"><span data-stu-id="b0498-120">**Create your dictionary**.</span></span> <span data-ttu-id="b0498-121">Välj ett namn och en beskrivning och skapa ordlistan.</span><span class="sxs-lookup"><span data-stu-id="b0498-121">Choose a name and description and create your dictionary.</span></span>

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a><span data-ttu-id="b0498-122">Skapa en nyckelordsordlista i Säkerhets- och efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="b0498-122">Create a keyword dictionary using the Security & Compliance Center</span></span>

<span data-ttu-id="b0498-123">Använd följande steg för att skapa och importera nyckelord till en egen ordlista:</span><span class="sxs-lookup"><span data-stu-id="b0498-123">Use the following steps to create and import keywords for a custom dictionary:</span></span>

1. <span data-ttu-id="b0498-124">Ansluta till Säkerhets- och efterlevnadscenter ([https://protection.office.com](https://protection.office.com)).</span><span class="sxs-lookup"><span data-stu-id="b0498-124">Connect to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span>

2. <span data-ttu-id="b0498-125">Gå till **Klassificeringar > Typer av känslig information**.</span><span class="sxs-lookup"><span data-stu-id="b0498-125">Navigate to **Classifications > Sensitive info types**.</span></span>

3. <span data-ttu-id="b0498-126">Välj **Skapa** och ange **Namn** och **Beskrivning** för typen av känslig information. Välj sedan **Nästa**</span><span class="sxs-lookup"><span data-stu-id="b0498-126">Select **Create** and enter a **Name** and **Description** for your sensitive info type, then select **Next**</span></span>

4. <span data-ttu-id="b0498-127">Välj **Lägg till ett element** och välj sedan **Ordlista (stora nyckelord)** i listrutan **Identifiera innehåll som innehåller**.</span><span class="sxs-lookup"><span data-stu-id="b0498-127">Select **Add an element**, then select **Dictionary (Large keywords)** in the **Detect content containing** drop-down list.</span></span>

5. <span data-ttu-id="b0498-128">Välj **Lägg till en ordlista**</span><span class="sxs-lookup"><span data-stu-id="b0498-128">Select **Add a dictionary**</span></span>

6. <span data-ttu-id="b0498-129">Under sökkontrollen väljer du **Du kan skapa nya nyckelordsordlistor här**.</span><span class="sxs-lookup"><span data-stu-id="b0498-129">Under the Search control, select **You can create new keyword dictionaries here**.</span></span>

7. <span data-ttu-id="b0498-130">Ange ett **Namn** på den egna ordlistan.</span><span class="sxs-lookup"><span data-stu-id="b0498-130">Enter a **Name** for your custom dictionary.</span></span>

8. <span data-ttu-id="b0498-131">Välj **Importera** och välj sedan antingen **Från text** eller **Från CSV** beroende på vilken typ av nyckelordsfil du har.</span><span class="sxs-lookup"><span data-stu-id="b0498-131">Select **Import**, and select either **From text** or **From csv** depending on your keyword file type.</span></span>

9. <span data-ttu-id="b0498-132">Välj nyckelordsfilen från din lokala dator eller nätverksfilresurs i dialogrutan och välj sedan **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="b0498-132">In the file dialog, select the keyword file from your local PC or network file share, then select **Open**.</span></span>

10. <span data-ttu-id="b0498-133">Välj **Spara** och välj sedan din egna ordlista i listan **Nyckelordsordlistor**.</span><span class="sxs-lookup"><span data-stu-id="b0498-133">Select **Save**, then select your custom dictionary from the **Keyword dictionaries** list.</span></span>

11. <span data-ttu-id="b0498-134">Välj **Lägg till** och sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="b0498-134">Select **Add**, then select **Next**.</span></span>

12. <span data-ttu-id="b0498-135">Granska och slutför dina markeringar för den känsliga informationstypen och välj sedan **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="b0498-135">Review and finalize your sensitive info type selections, then select **Finish**.</span></span>
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a><span data-ttu-id="b0498-136">Skapa en nyckelordsordlista från en fil med PowerShell</span><span class="sxs-lookup"><span data-stu-id="b0498-136">Create a keyword dictionary from a file using PowerShell</span></span>

<span data-ttu-id="b0498-137">När du behöver skapa en stor ordlista används ofta nyckelord från en fil eller en lista som har exporterats från en annan källa.</span><span class="sxs-lookup"><span data-stu-id="b0498-137">Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source.</span></span> <span data-ttu-id="b0498-138">I det här fallet skapar du en nyckelordsordlista med olämpligt språk som ska granskas i extern e-post.</span><span class="sxs-lookup"><span data-stu-id="b0498-138">In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email.</span></span> <span data-ttu-id="b0498-139">Du måste först [ansluta till Säkerhets- &amp; efterlevnadscenter i PowerShell](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="b0498-139">You must first [Connect to Security &amp; Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>
  
1. <span data-ttu-id="b0498-140">Kopiera nyckelorden till en textfil och kontrollera att varje nyckelord finns på en separat rad.</span><span class="sxs-lookup"><span data-stu-id="b0498-140">Copy the keywords into a text file and make sure that each keyword is on a separate line.</span></span>
    
2. <span data-ttu-id="b0498-141">Spara textfilen med Unicode-kodning.</span><span class="sxs-lookup"><span data-stu-id="b0498-141">Save the text file with Unicode encoding.</span></span> <span data-ttu-id="b0498-142">I Anteckningar \> **Spara som** \> **Kodning** \> **Unicode**.</span><span class="sxs-lookup"><span data-stu-id="b0498-142">In Notepad \> **Save As** \> **Encoding** \> **Unicode**.</span></span>
    
3. <span data-ttu-id="b0498-143">Läs filen till en variabel genom att köra följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b0498-143">Read the file into a variable by running this cmdlet:</span></span>
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. <span data-ttu-id="b0498-144">Skapa ordlistan genom att köra följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b0498-144">Create the dictionary by running this cmdlet:</span></span>
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```

## <a name="modifying-an-existing-keyword-dictionary"></a><span data-ttu-id="b0498-145">Ändra en befintlig nyckelordsordlista</span><span class="sxs-lookup"><span data-stu-id="b0498-145">Modifying an existing keyword dictionary</span></span>

<span data-ttu-id="b0498-146">Du kan behöva ändra nyckelord i någon av dina nyckelordsordlistor eller ändra någon av de inbyggda ordlistorna.</span><span class="sxs-lookup"><span data-stu-id="b0498-146">You might need to modify keywords in one of your keyword dictionaries, or modify one of the built-in dictionaries.</span></span> <span data-ttu-id="b0498-147">För närvarande kan du bara uppdatera en egen nyckelordsordlista med PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0498-147">Currently, your can only update a custom keyword dictionary using PowerShell.</span></span> 

<span data-ttu-id="b0498-148">Vi kommer till exempel att ändra vissa termer i PowerShell, spara termerna lokalt där du kan ändra dem i ett redigeringsprogram och sedan uppdatera de tidigare termerna.</span><span class="sxs-lookup"><span data-stu-id="b0498-148">For example, we'll modify some terms in PowerShell, save the terms locally where you can modify them in an editor, and then update the previous terms in place.</span></span> 

<span data-ttu-id="b0498-149">Hämta först ordlisteobjektet:</span><span class="sxs-lookup"><span data-stu-id="b0498-149">First, retrieve the dictionary object:</span></span>
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="b0498-150">Om du skriver ut `$dict` visas de olika variablerna.</span><span class="sxs-lookup"><span data-stu-id="b0498-150">Printing  `$dict` will show the various variables.</span></span> <span data-ttu-id="b0498-151">Nyckelorden lagras i ett objekt i serverdelen, men `$dict.KeywordDictionary` innehåller en strängrepresentation av dem som du använder när du ändrar ordlistan.</span><span class="sxs-lookup"><span data-stu-id="b0498-151">The keywords themselves are stored in an object on the backend, but  `$dict.KeywordDictionary` contains a string representation of them, which you'll use to modify the dictionary.</span></span> 

<span data-ttu-id="b0498-152">Innan du ändrar ordlistan måste du omvandla strängen med termer till en matris med hjälp av `.split(',')`-metoden.</span><span class="sxs-lookup"><span data-stu-id="b0498-152">Before you modify the dictionary, you need to turn the string of terms back into an array using the  `.split(',')` method.</span></span> <span data-ttu-id="b0498-153">Sedan rensar du bort de oönskade blankstegen mellan nyckelorden med `.trim()`-metoden, så att bara nyckelorden finns kvar.</span><span class="sxs-lookup"><span data-stu-id="b0498-153">Then you'll clean up the unwanted spaces between the keywords with the  `.trim()` method, leaving just the keywords to work with.</span></span> 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

<span data-ttu-id="b0498-154">Nu kan du ta bort vissa termer från ordlistan.</span><span class="sxs-lookup"><span data-stu-id="b0498-154">Now you'll remove some terms from the dictionary.</span></span> <span data-ttu-id="b0498-155">Eftersom exempelordlistan bara innehåller några få nyckelord kan du i stället gå vidare till att exportera ordlistan och redigera den i Anteckningar, men ordlistor innehåller vanligtvis en stor mängd text så du får först lära dig det här sättet att redigera dem enkelt i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0498-155">Because the example dictionary has only a few keywords, you could as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span></span>
  
<span data-ttu-id="b0498-156">I det sista steget sparade du nyckelorden i en matris.</span><span class="sxs-lookup"><span data-stu-id="b0498-156">In the last step, you saved the keywords to an array.</span></span> <span data-ttu-id="b0498-157">Det finns flera sätt att [ta bort objekt från en matris](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), men ett enkelt sätt är att skapa en matris med de termer som du vill ta bort från ordlistan och sedan endast kopiera ordlistetermerna som inte finns i listan med termer att ta bort.</span><span class="sxs-lookup"><span data-stu-id="b0498-157">There are several ways to [remove items from an array](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span></span>
  
<span data-ttu-id="b0498-158">Kör kommandot `$terms` för att visa den aktuella listan med termer.</span><span class="sxs-lookup"><span data-stu-id="b0498-158">Run the command  `$terms` to show the current list of terms.</span></span> <span data-ttu-id="b0498-159">Kommandots utdata ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="b0498-159">The output of the command looks like this:</span></span> 
  
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

<span data-ttu-id="b0498-160">Kör kommandot för att ange de termer som du vill ta bort:</span><span class="sxs-lookup"><span data-stu-id="b0498-160">Run this command to specify the terms that you want to remove:</span></span>
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

<span data-ttu-id="b0498-161">Kör kommandot för att ta bort termerna från listan:</span><span class="sxs-lookup"><span data-stu-id="b0498-161">Run this command to actually remove the terms from the list:</span></span>
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

<span data-ttu-id="b0498-162">Kör kommandot `$updatedTerms` för att visa den uppdaterade listan med termer.</span><span class="sxs-lookup"><span data-stu-id="b0498-162">Run the command  `$updatedTerms` to show the updated list of terms.</span></span> <span data-ttu-id="b0498-163">Kommandots utdata ser ut så här (de angivna termerna har tagits bort):</span><span class="sxs-lookup"><span data-stu-id="b0498-163">The output of the command looks like this (the specified terms have been removed):</span></span> 
  
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

<span data-ttu-id="b0498-164">Öppna filen, lägg till dina andra termer och spara med Unicode-kodning (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="b0498-164">Now open the file, add your other terms, and save with Unicode encoding (UTF-16).</span></span> <span data-ttu-id="b0498-165">Nu ska du ladda upp de uppdaterade termerna och uppdatera ordlistan på plats.</span><span class="sxs-lookup"><span data-stu-id="b0498-165">Now you'll upload the updated terms and update the dictionary in place.</span></span>
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

<span data-ttu-id="b0498-166">Nu har ordlistan uppdaterats.</span><span class="sxs-lookup"><span data-stu-id="b0498-166">Now the dictionary has been updated in place.</span></span> <span data-ttu-id="b0498-167">Fältet `Identity` hämtar namnet på ordlistan.</span><span class="sxs-lookup"><span data-stu-id="b0498-167">The  `Identity` field takes the name of the dictionary.</span></span> <span data-ttu-id="b0498-168">Om du även vill ändra namnet på ordlistan med cmdleten `set-`, behöver du bara lägga till parametern `-Name` i det som visas ovan med det nya ordlistenamnet.</span><span class="sxs-lookup"><span data-stu-id="b0498-168">If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span></span> 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a><span data-ttu-id="b0498-169">Använda nyckelordsordlistor i anpassade typer av känslig information och DLP-principer</span><span class="sxs-lookup"><span data-stu-id="b0498-169">Using keyword dictionaries in custom sensitive information types and DLP policies</span></span>

<span data-ttu-id="b0498-170">Nyckelordsordlistor kan användas som en del av matchningskraven för en anpassad typ av känslig information eller som en typ av känslig information.</span><span class="sxs-lookup"><span data-stu-id="b0498-170">Keyword dictionaries can be used as part of the match requirements for a custom sensitive information type, or as a sensitive information type themselves.</span></span> <span data-ttu-id="b0498-171">Båda kräver att du skapar en [anpassad typ av känslig information](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="b0498-171">Both require you to create a [custom sensitive information type](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span> <span data-ttu-id="b0498-172">Skapa en typ av känslig information genom att följa instruktionerna i den länkade artikeln.</span><span class="sxs-lookup"><span data-stu-id="b0498-172">Follow the instructions in the linked article to create a sensitive information type.</span></span> <span data-ttu-id="b0498-173">När du har XML-koden behöver du GUID-identifieraren för ordlistan för att kunna använda den.</span><span class="sxs-lookup"><span data-stu-id="b0498-173">Once you have the XML, you'll need the GUID identifier for the dictionary to use it.</span></span>
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

<span data-ttu-id="b0498-174">Om du vill hämta identiteten för ordlistan kör du det här kommandot och kopierar egenskapsvärdet **Identitet**:</span><span class="sxs-lookup"><span data-stu-id="b0498-174">To get the identity of your dictionary, run this command and copy the **Identity** property value:</span></span> 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="b0498-175">Kommandots utdata ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="b0498-175">The output of the command looks like this:</span></span>
  
<span data-ttu-id="b0498-176">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span><span class="sxs-lookup"><span data-stu-id="b0498-176">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span></span>
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


<span data-ttu-id="b0498-177">Klistra in identiteten i XML-koden för din anpassade typ av känslig information och ladda upp den.</span><span class="sxs-lookup"><span data-stu-id="b0498-177">Paste the identity into your custom sensitive information type's XML and upload it.</span></span> <span data-ttu-id="b0498-178">Nu visas ordlistan i listan med typer av känslig information och du kan använda den direkt i principen, samt ange hur många nyckelord som måste matchas.</span><span class="sxs-lookup"><span data-stu-id="b0498-178">Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.</span></span>
  
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
> <span data-ttu-id="b0498-179">Microsoft 365 Information Protection har stöd för teckenuppsättningsspråk med dubbla byte i förhandsgranskningen för:</span><span class="sxs-lookup"><span data-stu-id="b0498-179">Microsoft 365 Information Protection supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="b0498-180">Kinesiska (förenklad)</span><span class="sxs-lookup"><span data-stu-id="b0498-180">Chinese (simplified)</span></span>
> - <span data-ttu-id="b0498-181">Kinesiska (traditionell)</span><span class="sxs-lookup"><span data-stu-id="b0498-181">Chinese (traditional)</span></span>
> - <span data-ttu-id="b0498-182">Koreanska</span><span class="sxs-lookup"><span data-stu-id="b0498-182">Korean</span></span>
> - <span data-ttu-id="b0498-183">Japanska</span><span class="sxs-lookup"><span data-stu-id="b0498-183">Japanese</span></span>
>
><span data-ttu-id="b0498-184">Stödet är tillgängligt för typer av känslig information.</span><span class="sxs-lookup"><span data-stu-id="b0498-184">This support is available for sensitive information types.</span></span> <span data-ttu-id="b0498-185">Se [Viktig information gällande stöd i Information Protection för teckenuppsättningar med dubbla byte (förhandsversion)](mip-dbcs-relnotes.md) för mer information.</span><span class="sxs-lookup"><span data-stu-id="b0498-185">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>
