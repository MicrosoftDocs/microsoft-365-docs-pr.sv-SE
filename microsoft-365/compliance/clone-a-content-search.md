---
title: Klona en innehållssökning
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/26/2017
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
ms.custom:
- seo-marvel-apr2020
description: Använd PowerShell-skriptet i den här artikeln för att snabbt klona en befintlig innehållssökning i efterlevnadscentret i Office 365 eller Microsoft 365.
ms.openlocfilehash: c64cec2415819dc53f30c303c241e3902f34017d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162012"
---
# <a name="clone-a-content-search"></a><span data-ttu-id="35980-103">Klona en innehållssökning</span><span class="sxs-lookup"><span data-stu-id="35980-103">Clone a Content Search</span></span>

<span data-ttu-id="35980-104">Det kan ta en stund att skapa en innehållssökning i efterlevnadscentret i Office 365 eller Microsoft 365 som genomsöker många postlådor SharePoint-OneDrive för företag-webbplatser.</span><span class="sxs-lookup"><span data-stu-id="35980-104">Creating a Content Search in the compliance center in Office 365 or Microsoft 365 that searches many mailboxes or SharePoint and OneDrive for Business sites can take a while.</span></span> <span data-ttu-id="35980-105">Att ange webbplatser att söka på kan också lätt bli fel om du skriver en URL-adress fel.</span><span class="sxs-lookup"><span data-stu-id="35980-105">Specifying the sites to search can also be prone to errors if you mistype a URL.</span></span> <span data-ttu-id="35980-106">För att undvika dessa problem kan du använda skriptet Windows PowerShell den här artikeln för att snabbt klona en befintlig innehållssökning.</span><span class="sxs-lookup"><span data-stu-id="35980-106">To avoid these issues, you can use the Windows PowerShell script in this article to quickly clone an existing Content Search.</span></span> <span data-ttu-id="35980-107">När du klonar en sökning skapas en ny sökning (med ett annat namn) som innehåller samma egenskaper (till exempel innehållsplatserna och sökfrågan) som den ursprungliga sökningen.</span><span class="sxs-lookup"><span data-stu-id="35980-107">When you clone a search, a new search (with a different name) is created that contains the same properties (such as the content locations and the search query) as the original search.</span></span> <span data-ttu-id="35980-108">Sedan kan du redigera den nya sökningen genom att ändra nyckelordsfrågan eller datumintervallet och köra den.</span><span class="sxs-lookup"><span data-stu-id="35980-108">Then you can edit the new search by changing the keyword query or the date range, and run it.</span></span>
  
<span data-ttu-id="35980-109">Varför klona innehållssökningar?</span><span class="sxs-lookup"><span data-stu-id="35980-109">Why clone Content Searches?</span></span>
  
- <span data-ttu-id="35980-110">Om du vill jämföra resultat från olika sökordsökfrågor körs på samma innehållsplatser.</span><span class="sxs-lookup"><span data-stu-id="35980-110">To compare the results of different keyword search queries run on the same content locations.</span></span>
    
- <span data-ttu-id="35980-111">För att spara dig från att behöva gå tillbaka till ett stort antal innehållsplatser när du skapar en ny sökning.</span><span class="sxs-lookup"><span data-stu-id="35980-111">To save you from having to reenter a large number of content locations when you create a new search.</span></span>
    
- <span data-ttu-id="35980-112">Om du vill minska storleken på sökresultatet.</span><span class="sxs-lookup"><span data-stu-id="35980-112">To decrease the size of the search results.</span></span> <span data-ttu-id="35980-113">Om du till exempel har en sökning som returnerar för många resultat att exportera kan du klona sökningen och sedan lägga till ett sökvillkor baserat på ett datumintervall för att minska antalet sökresultat.</span><span class="sxs-lookup"><span data-stu-id="35980-113">For example, if you have a search that returns too many results to export, you can clone the search and then add a search condition based on a date range to reduce the number of search results.</span></span>
  
## <a name="script-information"></a><span data-ttu-id="35980-114">Skriptinformation</span><span class="sxs-lookup"><span data-stu-id="35980-114">Script information</span></span>

- <span data-ttu-id="35980-115">Du måste vara medlem i rollgruppen för eDiscovery Manager i Säkerhets- och & för att köra skriptet som beskrivs i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="35980-115">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the script described in this topic.</span></span>
    
- <span data-ttu-id="35980-116">Skriptet innehåller minimal felhantering.</span><span class="sxs-lookup"><span data-stu-id="35980-116">The script includes minimal error handling.</span></span> <span data-ttu-id="35980-117">Det primära syftet med skriptet är att snabbt klona en innehållssökning.</span><span class="sxs-lookup"><span data-stu-id="35980-117">The primary purpose of the script is to quickly clone a content search.</span></span>
    
- <span data-ttu-id="35980-118">Skriptet skapar en ny innehållssökning, men startar den inte.</span><span class="sxs-lookup"><span data-stu-id="35980-118">The script creates a new Content Search, but doesn't start it.</span></span>
    
- <span data-ttu-id="35980-119">Det här skriptet tar hänsyn till om den innehållssökning som du håller på att undersöka är kopplad till ett eDiscovery-fall.</span><span class="sxs-lookup"><span data-stu-id="35980-119">This script takes into account whether the Content Search that you're cloning is associated with an eDiscovery case.</span></span> <span data-ttu-id="35980-120">Om sökningen är kopplad till ett ärende associeras den nya sökningen också med samma ärende.</span><span class="sxs-lookup"><span data-stu-id="35980-120">If the search is associated with a case, the new search will also be associated with the same case.</span></span> <span data-ttu-id="35980-121">Om den befintliga sökningen inte är kopplad till ett ärende visas den nya sökningen på sidan **Innehållssökning** i efterlevnadscentret.</span><span class="sxs-lookup"><span data-stu-id="35980-121">If the existing search isn't associated with a case, the new search will be listed on the **Content search** page in the compliance center.</span></span> 
    
- <span data-ttu-id="35980-122">Exempelskriptet som tillhandahålls i det här avsnittet stöds inte under något standardsupportprogram eller någon standardsupporttjänst från Microsoft.</span><span class="sxs-lookup"><span data-stu-id="35980-122">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="35980-123">Exempelskriptet tillhandahålls i SIN FORM utan några som helst garantier.</span><span class="sxs-lookup"><span data-stu-id="35980-123">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="35980-124">Vidare frånsäger sig Microsoft alla underförstådda garantier, inklusive, utan begränsning, alla underförstådda garantier om säljbarhet eller lämplighet för ett visst ändamål.</span><span class="sxs-lookup"><span data-stu-id="35980-124">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="35980-125">Hela risken i samband med användningen av eller prestandan hos exempelskriptet och dokumentationen ligger kvar hos dig.</span><span class="sxs-lookup"><span data-stu-id="35980-125">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="35980-126">Under inga omständigheter ska Microsoft, dess upphovspersoner eller någon annan som är involverad i skapandet, produktionen eller leveransen av skripten hållas ansvariga för någon som helst skada (inklusive, men inte begränsat till, skador för vinstförlust, driftavbrott, förlust av affärsinformation eller annan ekonomisk skada) som uppstår till följd av användning eller oförmåga att använda exempelskripten eller dokumentationen, även om Microsoft har fått information om att sådana skador kan uppstå.</span><span class="sxs-lookup"><span data-stu-id="35980-126">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-clone-a-search"></a><span data-ttu-id="35980-127">Steg 1: Kör skriptet för att klona en sökning</span><span class="sxs-lookup"><span data-stu-id="35980-127">Step 1: Run the script to clone a search</span></span>

<span data-ttu-id="35980-128">Skriptet i det här steget skapar en ny innehållssökning genom att klona en befintlig.</span><span class="sxs-lookup"><span data-stu-id="35980-128">The script in this step will create a new Content Search by cloning an existing one.</span></span> <span data-ttu-id="35980-129">När du kör det här skriptet uppmanas du att ange följande information:</span><span class="sxs-lookup"><span data-stu-id="35980-129">When you run this script, you'll be prompted for the following information:</span></span>
  
- <span data-ttu-id="35980-130">**Dina användarautentiseringsuppgifter** – Skriptet använder dina autentiseringsuppgifter för att ansluta till säkerhets- & kompatibilitetscentret för din organisation med Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="35980-130">**Your user credentials** - The script will use your credentials to connect to the Security & Compliance Center for your organization with Windows PowerShell.</span></span> <span data-ttu-id="35980-131">Som tidigare nämnts måste du vara medlem i rollgruppen för eDiscovery Manager i Säkerhets- & CompCompliance Center för att köra skriptet.</span><span class="sxs-lookup"><span data-stu-id="35980-131">As previously stated, you have to be a member of the eDiscovery Manager role group in the Security & compCompliance Center to run the script.</span></span> 
    
- <span data-ttu-id="35980-132">**Namnet på den befintliga sökningen –** Det här är den innehållssökning som du vill klona.</span><span class="sxs-lookup"><span data-stu-id="35980-132">**The name of the existing search** - This is the Content Search that you want to clone.</span></span> 
    
- <span data-ttu-id="35980-133">**Namnet på den nya** sökning som kommer att skapas – Om du låter det här värdet vara tomt skapar skriptet ett namn för den nya sökningen som baseras på namnet på den sökning som du är klonad.</span><span class="sxs-lookup"><span data-stu-id="35980-133">**The name of the new search that will be created** - If you leave this value blank, the script will create a name for the new search that is based on the name of the search that you're cloning.</span></span> 
    
<span data-ttu-id="35980-134">Så här klonar du en sökning:</span><span class="sxs-lookup"><span data-stu-id="35980-134">To clone a search:</span></span>
  
1. <span data-ttu-id="35980-135">Spara följande text i en Windows PowerShell skriptfil med hjälp av ett filnamnssuffix .ps1; till exempel `CloneSearch.ps1` .</span><span class="sxs-lookup"><span data-stu-id="35980-135">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CloneSearch.ps1`.</span></span>
    
  ```powershell
  # This PowerShell script clones an existing content search in the Security &amp; Compliance Center.
  # Get login credentials from the user
  if(!$UserCredential)
  {
      $UserCredential = Get-Credential
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
      if (!$Session)
      {
          Write-Error "Couldn't create a remote PowerShell session."
          return
      }
      Import-PSSession $Session -AllowClobber -DisableNameChecking
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)"
  }
  # Ask for the name of the search you want to clone
  $searchName = Read-Host 'Enter the name of the search that you want to clone'
  # Ask for the name of the new search
  $newSearchName = Read-Host 'Enter a name for the new search [leave blank to automatically generate a name]'
  $originalSearch = Get-ComplianceSearch $searchName -EA SilentlyContinue
  # Make sure we have a valid search before continuing
  if(!$originalSearch)
  {
      Write-Error "Couldn't find search: $searchName"
      return
  }
  $searchNameCounter = 1
  # Find a suitable name for the new search
  while(!$newSearchName)
  {
      $newSearchName = $originalSearch.Name + "_" + $searchNameCounter
      $tempSearch = Get-ComplianceSearch $newSearchName -EA SilentlyContinue
      if ($tempSearch)
      {
          $newSearchName = $null
          $searchNameCounter++
      }
  }
  $caseName
  # Determine if the search is part of a case; if so get the case name
  if ($originalSearch.CaseId)
  {
      $searchCase = Get-ComplianceCase $originalSearch.CaseId
      $caseName = $searchCase.Name
  }
  # Need to cast this value as a Boolean the old fashion way
  $allowNotFoundExchangeLocationsEnabled = $false
  if ($originalSearch.AllowNotFoundExchangeLocationsEnabled)
  {
      $allowNotFoundExchangeLocationsEnabled = $true
  }
  $newSearch = New-ComplianceSearch -Name $newSearchName -AllowNotFoundExchangeLocationsEnabled $allowNotFoundExchangeLocationsEnabled -Case $caseName -ContentMatchQuery $originalSearch.ContentMatchQuery -Description $originalSearch.Description -ExchangeLocation $originalSearch.ExchangeLocation -ExchangeLocationExclusion $originalSearch.ExchangeLocationExclusion -Language $originalSearch.Language -SharePointLocation $originalSearch.SharePointLocation -SharePointLocationExclusion $originalSearch.SharePointLocationExclusion -PublicFolderLocation $originalSearch.PublicFolderLocation
  if ($newSearch)
  {
      Write-Host $newSearch.Name "was successfully created" -ForegroundColor Yellow
  }
  ```

2. <span data-ttu-id="35980-136">Öppna Windows PowerShell och gå till mappen där du sparade skriptet.</span><span class="sxs-lookup"><span data-stu-id="35980-136">Open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="35980-137">Kör skriptet. till exempel:</span><span class="sxs-lookup"><span data-stu-id="35980-137">Run the script; for example:</span></span>
    
    ```powershell
    .\CloneSearch.ps1
    ```

4. <span data-ttu-id="35980-138">När du uppmanas att ange dina autentiseringsuppgifter anger du din e-postadress och ditt lösenord och klickar sedan på **OK.**</span><span class="sxs-lookup"><span data-stu-id="35980-138">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span>
    
5. <span data-ttu-id="35980-139">Ange följande information när du uppmanas att göra det i skriptet.</span><span class="sxs-lookup"><span data-stu-id="35980-139">Enter following information when prompted by the script.</span></span> <span data-ttu-id="35980-140">Skriv in varje informationsbit och tryck sedan på **Retur.**</span><span class="sxs-lookup"><span data-stu-id="35980-140">Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="35980-141">Namnet på den befintliga sökningen.</span><span class="sxs-lookup"><span data-stu-id="35980-141">The name of the existing search.</span></span>
    
    - <span data-ttu-id="35980-142">Namnet på den nya sökningen.</span><span class="sxs-lookup"><span data-stu-id="35980-142">The name of the new search.</span></span>
    
    <span data-ttu-id="35980-143">Skriptet skapar den nya innehållssökningen, men startar den inte.</span><span class="sxs-lookup"><span data-stu-id="35980-143">The script creates the new Content Search, but doesn't start it.</span></span> <span data-ttu-id="35980-144">Då kan du redigera och köra sökningen i nästa steg.</span><span class="sxs-lookup"><span data-stu-id="35980-144">This gives you a chance to edit and run the search in the next step.</span></span> <span data-ttu-id="35980-145">Du kan visa egenskaperna för den nya sökningen genom att köra cmdleten **Get-ComplianceSearch** eller genom att gå till sidan Innehållssökning eller **eDiscovery** i efterlevnadscentret, beroende på om den nya sökningen är kopplad till ett ärende. </span><span class="sxs-lookup"><span data-stu-id="35980-145">You can view the properties of the new search by running the **Get-ComplianceSearch** cmdlet or by going to the **Content search** or **eDiscovery** page in the compliance center, depending on whether the new search is associated with a case.</span></span> 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a><span data-ttu-id="35980-146">Steg 2: Redigera och kör den klonade sökningen i efterlevnadscentret</span><span class="sxs-lookup"><span data-stu-id="35980-146">Step 2: Edit and run the cloned search in the compliance center</span></span>

<span data-ttu-id="35980-147">När du har kört skriptet för att klona en befintlig innehållssökning är nästa steg att gå till efterlevnadscentret och redigera och köra den nya sökningen.</span><span class="sxs-lookup"><span data-stu-id="35980-147">After you run the script to clone an existing Content Search, the next step is to go to the compliance center to edit and run the new search.</span></span> <span data-ttu-id="35980-148">Som tidigare nämnts kan du redigera en sökning genom att ändra sökordets sökfråga och lägga till eller ta bort sökvillkor.</span><span class="sxs-lookup"><span data-stu-id="35980-148">As previously stated, you can edit a search by changing the keyword search query and adding or removing search conditions.</span></span> <span data-ttu-id="35980-149">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="35980-149">For more information, see:</span></span>
  
- [<span data-ttu-id="35980-150">Innehållssökning i Office 365</span><span class="sxs-lookup"><span data-stu-id="35980-150">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="35980-151">Nyckelordsfrågor och sökvillkor för innehållssökning</span><span class="sxs-lookup"><span data-stu-id="35980-151">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
    
- [<span data-ttu-id="35980-152">eDiscovery-fall</span><span class="sxs-lookup"><span data-stu-id="35980-152">eDiscovery cases</span></span>](./get-started-core-ediscovery.md)