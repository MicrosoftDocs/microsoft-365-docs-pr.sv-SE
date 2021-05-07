---
title: Skapa, rapportera om och ta bort flera innehållssökningar
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: 1d463dda-a3b5-4675-95d4-83db19c9c4a3
description: Lär dig hur du automatiserar uppgifter för innehållssökning, t.ex. att skapa sökningar och köra rapporter via PowerShell-skript i Säkerhets- & efterlevnadscenter i Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6155a0bf411cc83fd58291efe7797e7f68370708
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/24/2021
ms.locfileid: "52162821"
---
# <a name="create-report-on-and-delete-multiple-content-searches"></a><span data-ttu-id="da60f-103">Skapa, rapportera om och ta bort flera innehållssökningar</span><span class="sxs-lookup"><span data-stu-id="da60f-103">Create, report on, and delete multiple Content Searches</span></span>

 <span data-ttu-id="da60f-104">Att snabbt skapa och rapportera upptäcktssökningar är ofta ett viktigt steg i e-dataidentifiering och undersökningar när du försöker lära dig mer om underliggande data, och dess användbarhet och kvalitet.</span><span class="sxs-lookup"><span data-stu-id="da60f-104">Quickly creating and reporting discovery searches is often an important step in eDiscovery and investigations when you're trying to learn about the underlying data, and the richness and quality of your searches.</span></span> <span data-ttu-id="da60f-105">Som hjälp för det kan du använda Säkerhets- & Compliance Center PowerShell med en uppsättning cmdlets som automatiserar tidskrävande aktiviteter för innehållssökning.</span><span class="sxs-lookup"><span data-stu-id="da60f-105">To help you do this, the Security & Compliance Center PowerShell offers a set of cmdlets to automate time-consuming Content Search tasks.</span></span> <span data-ttu-id="da60f-106">De här skripten är ett snabbt och enkelt sätt att skapa ett antal sökningar och sedan köra rapporter om uppskattade sökresultat som kan hjälpa dig att fastställa det antal data som är i fråga.</span><span class="sxs-lookup"><span data-stu-id="da60f-106">These scripts provide a quick and easy way to create a number of searches, and then run reports of the estimated search results that can help you determine the quantity of data in question.</span></span> <span data-ttu-id="da60f-107">Du kan också använda skripten för att skapa olika versioner av sökningar för att jämföra de resultat som respektive användare får fram.</span><span class="sxs-lookup"><span data-stu-id="da60f-107">You can also use the scripts to create different versions of searches to compare the results each one produces.</span></span> <span data-ttu-id="da60f-108">Med de här skripten kan du snabbt och effektivt identifiera och hantera dina data.</span><span class="sxs-lookup"><span data-stu-id="da60f-108">These scripts can help you to quickly and efficiently identify and cull your data.</span></span>

## <a name="before-you-create-a-content-search"></a><span data-ttu-id="da60f-109">Innan du skapar en innehållssökning</span><span class="sxs-lookup"><span data-stu-id="da60f-109">Before you create a Content Search</span></span>

- <span data-ttu-id="da60f-110">Du måste vara medlem i rollgruppen för eDiscovery Manager i säkerhets- och efterlevnadscentret för & för att kunna köra skripten som beskrivs i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="da60f-110">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the scripts that are described in this topic.</span></span>

- <span data-ttu-id="da60f-111">Om du vill samla in en lista med URL:er för OneDrive för företag-webbplatserna i organisationen som du kan lägga till i CSV-filen i steg 1, se Skapa en lista över alla OneDrive platser i [organisationen.](/onedrive/list-onedrive-urls)</span><span class="sxs-lookup"><span data-stu-id="da60f-111">To collect a list of the URLs for the OneDrive for Business sites in your organization that you can add to the CSV file in Step 1, see [Create a list of all OneDrive locations in your organization](/onedrive/list-onedrive-urls).</span></span>

- <span data-ttu-id="da60f-112">Se till att spara alla filer som du skapar i det här avsnittet i samma mapp.</span><span class="sxs-lookup"><span data-stu-id="da60f-112">Be sure to save all the files that you create in this topic to the same folder.</span></span> <span data-ttu-id="da60f-113">Det gör det enklare att köra skripten.</span><span class="sxs-lookup"><span data-stu-id="da60f-113">That will make it easier to run the scripts.</span></span>

- <span data-ttu-id="da60f-114">Skripten innehåller minimal felhantering.</span><span class="sxs-lookup"><span data-stu-id="da60f-114">The scripts include minimal error handling.</span></span> <span data-ttu-id="da60f-115">Syftet med dem är att snabbt skapa, rapportera om och ta bort flera innehållssökningar.</span><span class="sxs-lookup"><span data-stu-id="da60f-115">Their primary purpose is to quickly create, report on, and delete multiple Content Searches.</span></span>

- <span data-ttu-id="da60f-116">Exempelskripten som tillhandahålls i det här avsnittet stöds inte under något standardsupportprogram eller någon standardsupporttjänst från Microsoft.</span><span class="sxs-lookup"><span data-stu-id="da60f-116">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="da60f-117">Exempelskripten tillhandahålls i SIN FORM UTAN några som helst garantier.</span><span class="sxs-lookup"><span data-stu-id="da60f-117">The sample scripts are provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="da60f-118">Vidare frånsäger sig Microsoft alla underförstådda garantier, inklusive, utan begränsning, alla underförstådda garantier om säljbarhet eller lämplighet för ett visst ändamål.</span><span class="sxs-lookup"><span data-stu-id="da60f-118">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="da60f-119">Hela risken i samband med användningen av eller prestandan hos exempelskripten och dokumentationen ligger kvar hos dig.</span><span class="sxs-lookup"><span data-stu-id="da60f-119">The entire risk arising out of the use or performance of the sample scripts and documentation remains with you.</span></span> <span data-ttu-id="da60f-120">Under inga omständigheter ska Microsoft, dess upphovspersoner eller någon annan som är involverad i skapandet, produktionen eller leveransen av skripten hållas ansvariga för någon som helst skada (inklusive, men inte begränsat till, skador för vinstförlust, driftavbrott, förlust av affärsinformation eller annan ekonomisk skada) som uppstår till följd av användning eller oförmåga att använda exempelskripten eller dokumentationen, även om Microsoft har fått information om att sådana skador kan uppstå.</span><span class="sxs-lookup"><span data-stu-id="da60f-120">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a><span data-ttu-id="da60f-121">Steg 1: Skapa en CSV-fil som innehåller information om de sökningar du vill köra</span><span class="sxs-lookup"><span data-stu-id="da60f-121">Step 1: Create a CSV file that contains information about the searches you want to run</span></span>

<span data-ttu-id="da60f-122">Filen med kommaavgränsade värden (CSV) som du skapar i det här steget innehåller en rad för varje användare som vill söka.</span><span class="sxs-lookup"><span data-stu-id="da60f-122">The comma separated value (CSV) file that you create in this step contains a row for each user that want to search.</span></span> <span data-ttu-id="da60f-123">Du kan söka i användarens e Exchange Online postlåda (som innehåller arkivpostlådan, om den är aktiverad) och deras OneDrive för företag webbplats.</span><span class="sxs-lookup"><span data-stu-id="da60f-123">You can search the user's Exchange Online mailbox (which includes the archive mailbox, if it's enabled) and their OneDrive for Business site.</span></span> <span data-ttu-id="da60f-124">Du kan också söka i bara postlådan eller OneDrive för företag webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="da60f-124">Or you can search just the mailbox or the OneDrive for Business site.</span></span> <span data-ttu-id="da60f-125">Du kan också söka på alla webbplatser i SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="da60f-125">You can also search any site in your SharePoint Online organization.</span></span> <span data-ttu-id="da60f-126">Skriptet som du kör i steg 3 skapar en separat sökning för varje rad i CSV-filen.</span><span class="sxs-lookup"><span data-stu-id="da60f-126">The script that you run in Step 3 will create a separate search for each row in the CSV file.</span></span>

1. <span data-ttu-id="da60f-127">Kopiera och klistra in följande text i en .txt med Anteckningar.</span><span class="sxs-lookup"><span data-stu-id="da60f-127">Copy and paste the following text into a .txt file using NotePad.</span></span> <span data-ttu-id="da60f-128">Spara filen i en mapp på den lokala datorn.</span><span class="sxs-lookup"><span data-stu-id="da60f-128">Save this file to a folder on your local computer.</span></span> <span data-ttu-id="da60f-129">Du sparar även de andra skripten i den här mappen.</span><span class="sxs-lookup"><span data-stu-id="da60f-129">You'll save the other scripts to this folder as well.</span></span>

   ```text
   ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
   ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
   ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
   ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
   ```

   <span data-ttu-id="da60f-130">Filens första rad, eller rubrikraden, innehåller de parametrar som kommer att användas av **New-ComplianceSearch-cmdleten** (i skriptet i steg 3) för att skapa en ny innehållssökning.</span><span class="sxs-lookup"><span data-stu-id="da60f-130">The first row, or header row, of the file lists the parameters that will be used by **New-ComplianceSearch** cmdlet (in the script in Step 3) to create a new Content Searches.</span></span> <span data-ttu-id="da60f-131">Varje parameternamn avgränsas av ett kommatecken.</span><span class="sxs-lookup"><span data-stu-id="da60f-131">Each parameter name is separated by a comma.</span></span> <span data-ttu-id="da60f-132">Kontrollera att det inte finns några blanksteg i rubrikraden.</span><span class="sxs-lookup"><span data-stu-id="da60f-132">Make sure there aren't any spaces in the header row.</span></span> <span data-ttu-id="da60f-133">Varje rad under rubrikraden representerar parametervärdena för varje sökning.</span><span class="sxs-lookup"><span data-stu-id="da60f-133">Each row under the header row represents the parameter values for each search.</span></span> <span data-ttu-id="da60f-134">Se till att ersätta platshållardata i CSV-filen med faktiska data.</span><span class="sxs-lookup"><span data-stu-id="da60f-134">Be sure to replace the placeholder data in the CSV file with your actual data.</span></span>

2. <span data-ttu-id="da60f-135">Öppna .txt filen i Excel och använd sedan informationen i följande tabell för att redigera filen med information för varje sökning.</span><span class="sxs-lookup"><span data-stu-id="da60f-135">Open the .txt file in Excel, and then use the information in the following table to edit the file with information for each search.</span></span>

   ****

   |<span data-ttu-id="da60f-136">Parameter</span><span class="sxs-lookup"><span data-stu-id="da60f-136">Parameter</span></span>|<span data-ttu-id="da60f-137">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="da60f-137">Description</span></span>|
   |---|---|
   |`ExchangeLocation`|<span data-ttu-id="da60f-138">SMTP-adressen för användarens postlåda.</span><span class="sxs-lookup"><span data-stu-id="da60f-138">The SMTP address of the user's mailbox.</span></span>|
   |`SharePointLocation`|<span data-ttu-id="da60f-139">URL-adressen för användarens OneDrive för företag webbplats eller URL för en webbplats i organisationen.</span><span class="sxs-lookup"><span data-stu-id="da60f-139">The URL for the user's OneDrive for Business site or the URL for any site in your organization.</span></span> <span data-ttu-id="da60f-140">För URL-adressen för OneDrive för företag använder du följande format: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com ` .</span><span class="sxs-lookup"><span data-stu-id="da60f-140">For the URL for OneDrive for Business sites, use this format: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `.</span></span> <span data-ttu-id="da60f-141">Till exempel  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com` .</span><span class="sxs-lookup"><span data-stu-id="da60f-141">For example,  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.</span></span>|
   |`ContentMatchQuery`|<span data-ttu-id="da60f-142">Sökfrågan för sökningen.</span><span class="sxs-lookup"><span data-stu-id="da60f-142">The search query for the search.</span></span> <span data-ttu-id="da60f-143">Mer information om hur du skapar en sökfråga finns [i Nyckelordsfrågor och sökvillkor för innehållssökning.](keyword-queries-and-search-conditions.md)</span><span class="sxs-lookup"><span data-stu-id="da60f-143">For more information about creating a search query, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>|
   |`StartDate`|<span data-ttu-id="da60f-144">För e-post: det datum då eller efter det att ett meddelande togs emot av en mottagare eller skickades av avsändaren.</span><span class="sxs-lookup"><span data-stu-id="da60f-144">For email, the date on or after a message was received by a recipient or sent by the sender.</span></span> <span data-ttu-id="da60f-145">För dokument på SharePoint eller OneDrive för företag, datumet då ett dokument senast ändrades.</span><span class="sxs-lookup"><span data-stu-id="da60f-145">For documents on SharePoint or OneDrive for Business sites, the date on or after a document was last modified.</span></span>|
   |`EndDate`|<span data-ttu-id="da60f-146">För e-post: det datum då eller innan ett meddelande skickades av en användare.</span><span class="sxs-lookup"><span data-stu-id="da60f-146">For email, the date on or before a message was sent by a sent by the user.</span></span> <span data-ttu-id="da60f-147">För dokument på SharePoint eller OneDrive för företag webbplatser gäller att det datum då eller innan dokumentet senast ändrades.</span><span class="sxs-lookup"><span data-stu-id="da60f-147">For documents on SharePoint or OneDrive for Business sites, the date on or before a document was last modified.</span></span>|
   |

3. <span data-ttu-id="da60f-148">Spara filen Excel CSV-fil i en mapp på den lokala datorn.</span><span class="sxs-lookup"><span data-stu-id="da60f-148">Save the Excel file as a CSV file to a folder on your local computer.</span></span> <span data-ttu-id="da60f-149">Skriptet som du skapar i steg 3 använder informationen i CSV-filen för att skapa sökningarna.</span><span class="sxs-lookup"><span data-stu-id="da60f-149">The script that you create in Step 3 will use the information in this CSV file to create the searches.</span></span>

## <a name="step-2-connect-to-security--compliance-center-powershell"></a><span data-ttu-id="da60f-150">Steg 2: Anslut säkerhets- & Säkerhets- och efterlevnadscenter PowerShell</span><span class="sxs-lookup"><span data-stu-id="da60f-150">Step 2: Connect to Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="da60f-151">Nästa steg är att ansluta till Security & Compliance Center, PowerShell för din organisation.</span><span class="sxs-lookup"><span data-stu-id="da60f-151">The next step is to connect to Security & Compliance Center PowerShell for your organization.</span></span> <span data-ttu-id="da60f-152">Stegvisa instruktioner finns i Skapa säkerhets- [Anslut Säkerhets- & Compliance Center PowerShell.](/powershell/exchange/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="da60f-152">For step-by-step instructions, see [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a><span data-ttu-id="da60f-153">Steg 3: Kör skriptet för att skapa och starta sökningarna</span><span class="sxs-lookup"><span data-stu-id="da60f-153">Step 3: Run the script to create and start the searches</span></span>

<span data-ttu-id="da60f-154">Skriptet i det här steget skapar en separat innehållssökning för varje rad i CSV-filen som du skapade i steg 1.</span><span class="sxs-lookup"><span data-stu-id="da60f-154">The script in this step will create a separate Content Search for each row in the CSV file that you created in Step 1.</span></span> <span data-ttu-id="da60f-155">När du kör det här skriptet uppmanas du att ange två värden:</span><span class="sxs-lookup"><span data-stu-id="da60f-155">When you run this script, you'll be prompted for two values:</span></span>

- <span data-ttu-id="da60f-156">**Sökgrupp-ID** – Det här namnet är ett enkelt sätt att ordna sökningar som skapas från CSV-filen.</span><span class="sxs-lookup"><span data-stu-id="da60f-156">**Search Group ID** - This name provides an easy way to organize the searches that are created from the CSV file.</span></span> <span data-ttu-id="da60f-157">Varje sökning som skapas namnges med sökgrupp-ID och sedan läggs ett nummer till i söknamnet.</span><span class="sxs-lookup"><span data-stu-id="da60f-157">Each search that's created is named with the Search Group ID, and then a number is appended to the search name.</span></span> <span data-ttu-id="da60f-158">Om du till exempel anger **ContosoCase** för sökgrupp-ID:t heter **sökningarna ContosoCase_1**, **ContosoCase_2**, **ContosoCase_3** och så vidare.</span><span class="sxs-lookup"><span data-stu-id="da60f-158">For example, if you enter **ContosoCase** for the Search Group ID, then the searches are named **ContosoCase_1**, **ContosoCase_2**, **ContosoCase_3**, and so on.</span></span> <span data-ttu-id="da60f-159">Observera att namnet du skriver är det ärendekänsliga.</span><span class="sxs-lookup"><span data-stu-id="da60f-159">Note that the name you type is case sensitive.</span></span> <span data-ttu-id="da60f-160">När du använder sökgrupp-ID i steg 4 och steg 5 måste du använda samma ärende som du gjorde när du skapade det.</span><span class="sxs-lookup"><span data-stu-id="da60f-160">When you use the Search Group ID in Step 4 and Step 5, you have to use the same case as you did when you created it.</span></span>

- <span data-ttu-id="da60f-161">**CSV-fil** – namnet på CSV-filen som du skapade i steg 1.</span><span class="sxs-lookup"><span data-stu-id="da60f-161">**CSV file** - The name of the CSV file that you created in Step 1.</span></span> <span data-ttu-id="da60f-162">Se till att använda det fullständiga filnamnet, inklusive filnamnstillägget .csv filnamnstillägget. till exempel  `ContosoCase.csv` .</span><span class="sxs-lookup"><span data-stu-id="da60f-162">Be sure to include the use the full filename, include the .csv file extension; for example,  `ContosoCase.csv`.</span></span>

<span data-ttu-id="da60f-163">Så här kör du skriptet:</span><span class="sxs-lookup"><span data-stu-id="da60f-163">To run the script:</span></span>

1. <span data-ttu-id="da60f-164">Spara följande text i en Windows PowerShell skriptfil med hjälp av ett filnamnssuffix .ps1; till exempel `CreateSearches.ps1` .</span><span class="sxs-lookup"><span data-stu-id="da60f-164">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CreateSearches.ps1`.</span></span> <span data-ttu-id="da60f-165">Spara filen i samma mapp där du sparade de andra filerna.</span><span class="sxs-lookup"><span data-stu-id="da60f-165">Save the file to the same folder where you saved the other files.</span></span>

   ```Powershell
   # Get the Search Group ID and the location of the CSV input file
   $searchGroup = Read-Host 'Search Group ID'
   $csvFile = Read-Host 'Source CSV file'

   # Do a quick check to make sure our group name will not collide with other searches
   $searchCounter = 1
   import-csv $csvFile |
     ForEach-Object{

    $searchName = $searchGroup +'_' + $searchCounter
    $search = Get-ComplianceSearch $searchName -EA SilentlyContinue
    if ($search)
    {
       Write-Error "The Search Group ID conflicts with existing searches.  Please choose a search group name and restart the script."
       return
    }
    $searchCounter++
   }

   $searchCounter = 1
   import-csv $csvFile |
     ForEach-Object{

    # Create the query
    $query = $_.ContentMatchQuery
    if(($_.StartDate -or $_.EndDate))
    {
          # Add the appropriate date restrictions.  NOTE: Using the Date condition property here because it works across Exchange, SharePoint, and OneDrive for Business.
          # For Exchange, the Date condition property maps to the Sent and Received dates; for SharePoint and OneDrive for Business, it maps to Created and Modified dates.
          if($query)
          {
              $query += " AND"
          }
          $query += " ("
          if($_.StartDate)
          {
              $query += "Date >= " + $_.StartDate
          }
          if($_.EndDate)
          {
              if($_.StartDate)
              {
                  $query += " AND "
              }
              $query += "Date <= " + $_.EndDate
          }
          $query += ")"
    }

     # -ExchangeLocation can't be set to an empty string, set to null if there's no location.
     $exchangeLocation = $null
     if ( $_.ExchangeLocation)
     {
           $exchangeLocation = $_.ExchangeLocation
     }

    # Create and run the search
    $searchName = $searchGroup +'_' + $searchCounter
    Write-Host "Creating and running search: " $searchName -NoNewline
    $search = New-ComplianceSearch -Name $searchName -ExchangeLocation $exchangeLocation -SharePointLocation $_.SharePointLocation -ContentMatchQuery $query

    # Start and wait for each search to complete
    Start-ComplianceSearch $search.Name
    while ((Get-ComplianceSearch $search.Name).Status -ne "Completed")
    {
       Write-Host " ." -NoNewline
       Start-Sleep -s 3
    }
    Write-Host ""

    $searchCounter++
   }
   ```

2. <span data-ttu-id="da60f-166">I Windows PowerShell du till den mapp där du sparade skriptet i föregående steg och kör sedan skriptet. till exempel:</span><span class="sxs-lookup"><span data-stu-id="da60f-166">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>

   ```Powershell
   .\CreateSearches.ps1
   ```

3. <span data-ttu-id="da60f-167">Skriv ett **namn för sökgruppen** i frågan Sök efter grupp-ID och tryck sedan på **Retur**. till exempel  `ContosoCase` .</span><span class="sxs-lookup"><span data-stu-id="da60f-167">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example,  `ContosoCase`.</span></span> <span data-ttu-id="da60f-168">Kom ihåg att namnet är ärendekänsligt, så du måste skriva det på samma sätt i de efterföljande stegen.</span><span class="sxs-lookup"><span data-stu-id="da60f-168">Remember that this name is case sensitive, so you'll have to type it the same way in the subsequent steps.</span></span>

4. <span data-ttu-id="da60f-169">I frågan **Käll-CSV-fil** skriver du namnet på CSV-filen, inklusive namnet .csv filnamnstillägget. till exempel  `ContosoCase.csv` .</span><span class="sxs-lookup"><span data-stu-id="da60f-169">At the **Source CSV file** prompt, type the name of the CSV file, including the .csv file extension; for example,  `ContosoCase.csv`.</span></span>

5. <span data-ttu-id="da60f-170">Tryck **på Retur** för att fortsätta köra skriptet.</span><span class="sxs-lookup"><span data-stu-id="da60f-170">Press **Enter** to continue running the script.</span></span>

   <span data-ttu-id="da60f-171">Skriptet visar förloppet för att skapa och köra sökningarna.</span><span class="sxs-lookup"><span data-stu-id="da60f-171">The script displays the progress of creating and running the searches.</span></span> <span data-ttu-id="da60f-172">När skriptet är klart återgår det till uppmaningen.</span><span class="sxs-lookup"><span data-stu-id="da60f-172">When the script is complete, it returns to the prompt.</span></span>

   ![Exempelresultat från körning av skriptet för att skapa flera efterlevnadssökningar](../media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)

## <a name="step-4-run-the-script-to-report-the-search-estimates"></a><span data-ttu-id="da60f-174">Steg 4: Kör skriptet för att rapportera sökuppskattningarna</span><span class="sxs-lookup"><span data-stu-id="da60f-174">Step 4: Run the script to report the search estimates</span></span>

<span data-ttu-id="da60f-175">När du har skapat sökningarna är nästa steg att köra ett skript som visar en enkel rapport med antalet sökträffar för varje sökning som skapades i steg 3.</span><span class="sxs-lookup"><span data-stu-id="da60f-175">After you create the searches, the next step is to run a script that displays a simple report of the number of search hits for each search that was created in Step 3.</span></span> <span data-ttu-id="da60f-176">Rapporten innehåller även storleken på resultatet för varje sökning och det totala antalet träffar och den totala storleken för alla sökningar.</span><span class="sxs-lookup"><span data-stu-id="da60f-176">The report also includes the size of results for each search, and the total number of hits and total size of all searches.</span></span> <span data-ttu-id="da60f-177">När du kör rapporteringsskriptet uppmanas du att ange grupp-ID och ett CSV-filnamn om du vill spara rapporten i en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="da60f-177">When you run the reporting script, you'll be prompted for the Search Group ID, and a CSV filename if you want to save the report to a CSV file.</span></span>

1. <span data-ttu-id="da60f-178">Spara följande text i en Windows PowerShell skriptfil med hjälp av ett filnamnssuffix .ps1; till exempel `SearchReport.ps1` .</span><span class="sxs-lookup"><span data-stu-id="da60f-178">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchReport.ps1`.</span></span> <span data-ttu-id="da60f-179">Spara filen i samma mapp där du sparade de andra filerna.</span><span class="sxs-lookup"><span data-stu-id="da60f-179">Save the file to the same folder where you saved the other files.</span></span>

   ```Powershell
   $searchGroup = Read-Host 'Search Group ID'
   $outputFile = Read-Host 'Enter a file name or file path to save the report to a .csv file. Leave blank to only display the report'
   $searches = Get-ComplianceSearch | ?{$_.Name -clike $searchGroup + "_*"}
   $allSearchStats = @()
   foreach ($partialObj in $searches)
   {
      $search = Get-ComplianceSearch $partialObj.Name
      $sizeMB = [System.Math]::Round($search.Size / 1MB, 2)
      $searchStatus = $search.Status
      if($search.Errors)
      {
          $searchStatus = "Failed"
      }elseif($search.NumFailedSources -gt 0)
      {
          $searchStatus = "Failed Sources"
      }
      $searchStats = New-Object PSObject
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Name -Value $search.Name
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name ContentMatchQuery -Value $search.ContentMatchQuery
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Status -Value $searchStatus
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Items -Value $search.Items
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name "Size" -Value $search.Size
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name "Size(MB)" -Value $sizeMB
      $allSearchStats += $searchStats
   }
   # Calculate the totals
   $allItems = ($allSearchStats | Measure-Object Items -Sum).Sum
   # Convert the total size to MB and round to the nearst 100th
   $allSize = ($allSearchStats | Measure-Object 'Size' -Sum).Sum
   $allSizeMB = [System.Math]::Round($allSize  / 1MB, 2)
   # Get the total successful searches and total of all searches
   $allSuccessCount = ($allSearchStats |?{$_.Status -eq "Completed"}).Count
   $allCount = $allSearchStats.Count
   $allStatus = [string]$allSuccessCount + " of " + [string]$allCount
   # Totals Row
   $totalSearchStats = New-Object PSObject
   Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Name -Value "Total"
   Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Status -Value $allStatus
   Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Items -Value $allItems
   Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name "Size(MB)" -Value $allSizeMB
   $allSearchStats += $totalSearchStats
   # Just get the columns we're interested in showing
   $allSearchStatsPrime = $allSearchStats | Select-Object Name, Status, Items, "Size(MB)", ContentMatchQuery
   # Print the results to the screen
   $allSearchStatsPrime |ft -AutoSize -Wrap
   # Save the results to a CSV file
   if ($outputFile)
   {
      $allSearchStatsPrime | Export-Csv -Path $outputFile -NoTypeInformation
   }
   ```

2. <span data-ttu-id="da60f-180">I Windows PowerShell du till den mapp där du sparade skriptet i föregående steg och kör sedan skriptet. till exempel:</span><span class="sxs-lookup"><span data-stu-id="da60f-180">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>

   ```Powershell
   .\SearchReport.ps1
   ```

3. <span data-ttu-id="da60f-181">Skriv ett **namn för sökgruppen** i frågan Sök efter grupp-ID och tryck sedan på **Retur**. till exempel  `ContosoCase` .</span><span class="sxs-lookup"><span data-stu-id="da60f-181">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example  `ContosoCase`.</span></span> <span data-ttu-id="da60f-182">Kom ihåg att det här namnet är case sensitive så du måste skriva det på samma sätt som du gjorde när du körde skriptet i steg 3.</span><span class="sxs-lookup"><span data-stu-id="da60f-182">Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>

4. <span data-ttu-id="da60f-183">Skriv ett filnamn på den fullständiga filnamnssökvägen (inklusive filnamnstillägget .csv) vid sökvägen till en **CSV-fil (lämna** tomt för att bara visa rapporten) om du vill spara rapporten i en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="da60f-183">At the **File path to save the report to a CSV file (leave blank to just display the report)** prompt, type a file name of complete filename path (including the .csv file extension) if you want to save the report to a CSV file.</span></span> <span data-ttu-id="da60f-184">namnet på CSV-filen, inklusive .csv filnamnstillägget.</span><span class="sxs-lookup"><span data-stu-id="da60f-184">name of the CSV file, including the .csv file extension.</span></span> <span data-ttu-id="da60f-185">Du kan till exempel skriva om du vill spara den i den aktuella katalogen eller skriva  `ContosoCaseReport.csv` för att spara den i en annan  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` mapp.</span><span class="sxs-lookup"><span data-stu-id="da60f-185">For example, you could type  `ContosoCaseReport.csv` to save it to the current directory or you could type  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` to save it to a different folder.</span></span> <span data-ttu-id="da60f-186">Du kan också lämna uppmaningen tom om du vill visa rapporten men inte spara den i en fil.</span><span class="sxs-lookup"><span data-stu-id="da60f-186">You can also leave the prompt blank to display the report but not save it to a file.</span></span>

5. <span data-ttu-id="da60f-187">Tryck **på Retur.**</span><span class="sxs-lookup"><span data-stu-id="da60f-187">Press **Enter**.</span></span>

   <span data-ttu-id="da60f-188">Skriptet visar förloppet för att skapa och köra sökningarna.</span><span class="sxs-lookup"><span data-stu-id="da60f-188">The script displays the progress of creating and running the searches.</span></span> <span data-ttu-id="da60f-189">När skriptet är klart visas rapporten.</span><span class="sxs-lookup"><span data-stu-id="da60f-189">When the script is complete, the report is displayed.</span></span>

   ![Kör sökrapporten för att visa uppskattningar för sökgruppen](../media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)

> [!NOTE]
> <span data-ttu-id="da60f-191">Om samma postlåda eller webbplats anges som en innehållsplats i mer än en sökning i en sökgrupp kan den totala resultatberäkningen i rapporten (för både antal objekt och den totala storleken) innehålla resultat för samma objekt.</span><span class="sxs-lookup"><span data-stu-id="da60f-191">If the same mailbox or site is specified as a content location in more than one search in a search group, the total results estimate in the report (for both the number of items and the total size) might include results for the same items.</span></span> <span data-ttu-id="da60f-192">Det beror på att samma e-postmeddelande eller dokument räknas mer än en gång om det matchar frågan för olika sökningar i sökgruppen.</span><span class="sxs-lookup"><span data-stu-id="da60f-192">That's because the same email message or document will be counted more than once if it matches the query for different searches in the search group.</span></span>

## <a name="step-5-run-the-script-to-delete-the-searches"></a><span data-ttu-id="da60f-193">Steg 5: Kör skriptet för att ta bort sökningarna</span><span class="sxs-lookup"><span data-stu-id="da60f-193">Step 5: Run the script to delete the searches</span></span>

<span data-ttu-id="da60f-194">Eftersom du kanske skapar många sökningar gör det här sista skriptet det enkelt att snabbt ta bort de sökningar du skapade i steg 3.</span><span class="sxs-lookup"><span data-stu-id="da60f-194">Because you might be creating a lot of searches, this last script just makes it easy to quickly delete the searches you created in Step 3.</span></span> <span data-ttu-id="da60f-195">Precis som de andra skripten uppmanas du även att ange sökgrupps-ID.</span><span class="sxs-lookup"><span data-stu-id="da60f-195">Like the other scripts, this one also prompts you for the Search Group ID.</span></span> <span data-ttu-id="da60f-196">Alla sökningar med sökgrupp-ID i söknamnet tas bort när du kör skriptet.</span><span class="sxs-lookup"><span data-stu-id="da60f-196">All searches with the Search Group ID in the search name will be deleted when you run this script.</span></span>

1. <span data-ttu-id="da60f-197">Spara följande text i en Windows PowerShell skriptfil med hjälp av ett filnamnssuffix .ps1; till exempel `DeleteSearches.ps1` .</span><span class="sxs-lookup"><span data-stu-id="da60f-197">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `DeleteSearches.ps1`.</span></span> <span data-ttu-id="da60f-198">Spara filen i samma mapp där du sparade de andra filerna.</span><span class="sxs-lookup"><span data-stu-id="da60f-198">Save the file to the same folder where you saved the other files.</span></span>

   ```Powershell
   # Delete all searches in a search group
   $searchGroup = Read-Host 'Search Group ID'
   Get-ComplianceSearch |
      ForEach-Object{
      # If the name matches the search group name pattern (case sensitive), delete the search
      if ($_.Name -cmatch $searchGroup + "_\d+")
      {
          Write-Host "Deleting search: " $_.Name
          Remove-ComplianceSearch $_.Name -Confirm:$false
      }
   }
   ```

2. <span data-ttu-id="da60f-199">I Windows PowerShell du till den mapp där du sparade skriptet i föregående steg och kör sedan skriptet. till exempel:</span><span class="sxs-lookup"><span data-stu-id="da60f-199">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>

   ```Powershell
   .\DeleteSearches.ps1
   ```

3. <span data-ttu-id="da60f-200">Skriv ett **namn på sökgruppen** för de sökningar du vill ta bort i uppmaningen Sök efter grupp-ID och tryck sedan på **Retur**. till exempel  `ContosoCase` .</span><span class="sxs-lookup"><span data-stu-id="da60f-200">At the **Search Group ID** prompt, type a search group name for the searches that you want to delete, and then press **Enter**; for example,  `ContosoCase`.</span></span> <span data-ttu-id="da60f-201">Kom ihåg att det här namnet är case sensitive så du måste skriva det på samma sätt som du gjorde när du körde skriptet i steg 3.</span><span class="sxs-lookup"><span data-stu-id="da60f-201">Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>

   <span data-ttu-id="da60f-202">Skriptet visar namnet på varje sökning som tas bort.</span><span class="sxs-lookup"><span data-stu-id="da60f-202">The script displays the name of each search that's deleted.</span></span>

   ![Kör skriptet för att ta bort sökningarna i sökgruppen](../media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
