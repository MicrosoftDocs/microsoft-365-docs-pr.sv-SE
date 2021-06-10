---
title: Söka i postlådan & OneDrive för företag webbplats efter en lista över användare med innehållssökning
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/3/2017
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 5f4f8206-2d6a-4cb2-bbc6-7a0698703cc0
description: Använd innehållssökning och skriptet i den här artikeln för att söka i postlådorna OneDrive för företag webbplatser efter en grupp användare.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 51e668438c6016a0c5f2c914dc2b2e86cc56f49e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162140"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a><span data-ttu-id="6a13f-103">Använda innehållssökning för att söka i postlådan OneDrive för företag efter en lista med användare</span><span class="sxs-lookup"><span data-stu-id="6a13f-103">Use Content Search to search the mailbox and OneDrive for Business site for a list of users</span></span>

<span data-ttu-id="6a13f-104">Säkerhets- & efterlevnadscenter innehåller ett antal Windows PowerShell cmdlets som du kan använda för att automatisera tidskrävande eDiscovery-relaterade uppgifter.</span><span class="sxs-lookup"><span data-stu-id="6a13f-104">The Security & Compliance Center provides a number of Windows PowerShell cmdlets that let you automate time-consuming eDiscovery-related tasks.</span></span> <span data-ttu-id="6a13f-105">För närvarande kan du skapa en innehållssökning i Säkerhets- & efterlevnadscenter för att söka efter ett stort antal plats för det skyddande innehållet tar tid och förberedelser.</span><span class="sxs-lookup"><span data-stu-id="6a13f-105">Currently, creating a Content Search in the Security & Compliance Center to search a large number of custodian content locations takes time and preparation.</span></span> <span data-ttu-id="6a13f-106">Innan du skapar en sökning måste du samla in URL-adressen för OneDrive för företag-webbplats och sedan lägga till varje postlåda OneDrive för företag webbplats i sökningen.</span><span class="sxs-lookup"><span data-stu-id="6a13f-106">Before you create a search, you have to collect the URL for each OneDrive for Business site and then add each mailbox and OneDrive for Business site to the search.</span></span> <span data-ttu-id="6a13f-107">I kommande versioner blir det enklare att göra detta i Säkerhets- & Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="6a13f-107">In future releases, this will be easier to do in the Security & Compliance Center.</span></span> <span data-ttu-id="6a13f-108">Tills dess kan du använda skriptet i den här artikeln för att automatisera processen.</span><span class="sxs-lookup"><span data-stu-id="6a13f-108">Until then, you can use the script in this article to automate this process.</span></span> <span data-ttu-id="6a13f-109">Det här skriptet uppmanar dig att ange namnet på din organisations Min webbplats-domän (till exempel **contoso** i URL:en), en lista med användarnas e-postadresser, namnet på den nya innehållssökningen och den sökfråga som ska `https://contoso-my.sharepoint.com` användas.</span><span class="sxs-lookup"><span data-stu-id="6a13f-109">This script prompts you for the name of your organization's MySite domain (for example, **contoso** in the URL `https://contoso-my.sharepoint.com`), a list of user email addresses, the name of the new Content Search, and the search query to use.</span></span> <span data-ttu-id="6a13f-110">Skriptet får URL-OneDrive för företag för varje användare i listan och skapar och startar en innehållssökning som söker i postlådan och OneDrive för företag-webbplatsen för varje användare i listan, med hjälp av sökfrågan som du anger.</span><span class="sxs-lookup"><span data-stu-id="6a13f-110">The script gets the OneDrive for Business URL for each user in the list, and then it creates and starts a Content Search that searches the mailbox and OneDrive for Business site for each user in the list, using the search query that you provide.</span></span>
  
## <a name="permissions-and-script-information"></a><span data-ttu-id="6a13f-111">Behörigheter och skriptinformation</span><span class="sxs-lookup"><span data-stu-id="6a13f-111">Permissions and script information</span></span>

- <span data-ttu-id="6a13f-112">Du måste vara medlem i rollgruppen för eDiscovery Manager i säkerhets- och efterlevnadscentret för & och en global SharePoint Online-administratör för att kunna köra skriptet i steg 3.</span><span class="sxs-lookup"><span data-stu-id="6a13f-112">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center and a SharePoint Online global administrator to run the script in Step 3.</span></span>

- <span data-ttu-id="6a13f-113">Se till att spara listan med användare som du skapar i steg 2 och skriptet i steg 3 i samma mapp.</span><span class="sxs-lookup"><span data-stu-id="6a13f-113">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder.</span></span> <span data-ttu-id="6a13f-114">Det gör det enklare att köra skriptet.</span><span class="sxs-lookup"><span data-stu-id="6a13f-114">That will make it easier to run the script.</span></span>

- <span data-ttu-id="6a13f-115">Skriptet innehåller minimal felhantering.</span><span class="sxs-lookup"><span data-stu-id="6a13f-115">The script includes minimal error handling.</span></span> <span data-ttu-id="6a13f-116">Dess huvudsakliga syfte är att snabbt och enkelt söka i postlådan och OneDrive för företag webbplatsen för varje användare.</span><span class="sxs-lookup"><span data-stu-id="6a13f-116">Its primary purpose is to quickly and easily search the mailbox and OneDrive for Business site of each user.</span></span>

- <span data-ttu-id="6a13f-117">Exempelskripten som tillhandahålls i det här avsnittet stöds inte under något standardsupportprogram eller någon standardsupporttjänst från Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6a13f-117">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="6a13f-118">Exempelskripten ges i befintligt skick utan garantier av något slag.</span><span class="sxs-lookup"><span data-stu-id="6a13f-118">The sample scripts are provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="6a13f-119">Vidare frånsäger sig Microsoft alla underförstådda garantier, inklusive, utan begränsning, underförstådda garantier om säljbarhet eller lämplighet för ett visst ändamål.</span><span class="sxs-lookup"><span data-stu-id="6a13f-119">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="6a13f-120">Hela risken i samband med användningen av eller prestandan hos exempelskripten och dokumentationen vilar på dig.</span><span class="sxs-lookup"><span data-stu-id="6a13f-120">The entire risk arising out of the use or performance of the sample scripts and documentation remains with you.</span></span> <span data-ttu-id="6a13f-121">Under inga omständigheter ska Microsoft, dess upphovspersoner eller någon annan som är involverad i skapandet, produktionen eller leveransen av skripten hållas ansvariga för någon som helst skada (inklusive, men inte begränsat till, skador avseende utebliven vinst, driftavbrott, förlust av affärsinformation eller annan ekonomisk skada) som uppstår till följd av användning eller svårighet eller omöjlighet att använda exempelskripten eller dokumentationen, även om Microsoft har fått information om att sådana skador kan uppstå.</span><span class="sxs-lookup"><span data-stu-id="6a13f-121">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="6a13f-122">Steg 1: Installera SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="6a13f-122">Step 1: Install the SharePoint Online Management Shell</span></span>

<span data-ttu-id="6a13f-123">Det första steget är att installera SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="6a13f-123">The first step is to install the SharePoint Online Management Shell.</span></span> <span data-ttu-id="6a13f-124">Du behöver inte använda gränssnittet i den här proceduren, men du måste installera det eftersom det innehåller förutsättningar som krävs av skriptet som du kör i steg 3.</span><span class="sxs-lookup"><span data-stu-id="6a13f-124">You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3.</span></span> <span data-ttu-id="6a13f-125">Dessa krav gör att skriptet kan kommunicera med SharePoint Online för att få URL:er för OneDrive för företag webbplatser.</span><span class="sxs-lookup"><span data-stu-id="6a13f-125">These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="6a13f-126">Gå till [Konfigurera SharePoint Online Management Shell Windows PowerShell och](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) utför steg 1 och steg 2 för att installera SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="6a13f-126">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell.</span></span>
  
## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="6a13f-127">Steg 2: Skapa en lista över användare</span><span class="sxs-lookup"><span data-stu-id="6a13f-127">Step 2: Generate a list of users</span></span>

<span data-ttu-id="6a13f-128">Skriptet i steg 3 skapar en innehållssökning för att söka i postlådorna och OneDrive efter en lista med användare.</span><span class="sxs-lookup"><span data-stu-id="6a13f-128">The script in Step 3 will create a Content Search to search the mailboxes and OneDrive accounts for a list of users.</span></span> <span data-ttu-id="6a13f-129">Du kan skriva e-postadresserna i en textfil eller köra ett kommando i Windows PowerShell för att visa en lista med e-postadresser och spara dem i en fil (som finns i samma mapp som skriptet ska sparas i steg 3).</span><span class="sxs-lookup"><span data-stu-id="6a13f-129">You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="6a13f-130">Här är ett [Exchange Online PowerShell-kommando](/powershell/exchange/connect-to-exchange-online-powershell) som du kan använda för att få en lista över e-postadresser för alla användare i organisationen och spara den i en textfil med namnet `Users.txt` .</span><span class="sxs-lookup"><span data-stu-id="6a13f-130">Here's an [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) command that you can runt to get a list of email addresses for all users in your organization and save it to a text file named `Users.txt`.</span></span> 
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

<span data-ttu-id="6a13f-131">När du har kört kommandot måste du öppna filen och ta bort rubriken som innehåller  `PrimarySmtpAddress` egenskapsnamnet.</span><span class="sxs-lookup"><span data-stu-id="6a13f-131">After you run this command, be sure to open the file and remove the header that contains the property name,  `PrimarySmtpAddress`.</span></span> <span data-ttu-id="6a13f-132">Textfilen ska bara innehålla en lista med e-postadresser och ingenting annat.</span><span class="sxs-lookup"><span data-stu-id="6a13f-132">The text file should just contain a list of email addresses, and nothing else.</span></span> <span data-ttu-id="6a13f-133">Kontrollera att det inte finns tomma rader före eller efter listan med e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="6a13f-133">Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a><span data-ttu-id="6a13f-134">Steg 3: Kör skriptet för att skapa och starta sökningen</span><span class="sxs-lookup"><span data-stu-id="6a13f-134">Step 3: Run the script to create and start the search</span></span>

<span data-ttu-id="6a13f-135">När du kör skriptet i det här steget uppmanas du att ange följande information.</span><span class="sxs-lookup"><span data-stu-id="6a13f-135">When you run the script in this step, it will prompt you for the following information.</span></span> <span data-ttu-id="6a13f-136">Se till att ha den här informationen redo innan du kör skriptet.</span><span class="sxs-lookup"><span data-stu-id="6a13f-136">Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="6a13f-137">**Dina användarautentiseringsuppgifter** – Skriptet använder dina autentiseringsuppgifter för att komma åt SharePoint Online för att få URL-adresser för OneDrive för företag och ansluta till & Säkerhets- och efterlevnadscenter med fjärr-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6a13f-137">**Your user credentials** - The script will use your credentials to access SharePoint Online to get the OneDrive for Business URLs and to connect to the Security & Compliance Center with remote PowerShell.</span></span> 
    
- <span data-ttu-id="6a13f-138">**Namn på Min webbplats-domänen** – Domänen Min webbplats är den domän som innehåller alla OneDrive för företag i organisationen.</span><span class="sxs-lookup"><span data-stu-id="6a13f-138">**Name of your MySite domain** - The MySite domain is the domain that contains all the OneDrive for Business sites in your organization.</span></span> <span data-ttu-id="6a13f-139">Om URL:en för din Min webbplats-domän till exempel är anger du när du uppmanas att ange namnet på **https://contoso-my.sharepoint.com**  `contoso` din Min webbplats-domän.</span><span class="sxs-lookup"><span data-stu-id="6a13f-139">For example, if the URL for your MySite domain is **https://contoso-my.sharepoint.com**, then you would enter  `contoso` when the script prompts you for the name of your MySite domain.</span></span> 
    
- <span data-ttu-id="6a13f-140">**Sökväg till textfilen från steg 2** – sökvägen till textfilen som du skapade i steg 2.</span><span class="sxs-lookup"><span data-stu-id="6a13f-140">**Pathname of the text file from Step 2** - The pathname of the text file that you created in Step 2.</span></span> <span data-ttu-id="6a13f-141">Om textfilen och skriptet finns i samma mapp anger du namnet på textfilen.</span><span class="sxs-lookup"><span data-stu-id="6a13f-141">If the text file and the script are located in the same folder, then enter the name of the text file.</span></span> <span data-ttu-id="6a13f-142">Annars anger du hela sökvägen för textfilen.</span><span class="sxs-lookup"><span data-stu-id="6a13f-142">Otherwise, enter the complete pathname for the text file.</span></span> 
    
- <span data-ttu-id="6a13f-143">**Namn på innehållssökningen** – namnet på den innehållssökning som skapas av skriptet.</span><span class="sxs-lookup"><span data-stu-id="6a13f-143">**Name of the Content Search** - The name of the Content Search that will be created by the script.</span></span> 
    
- <span data-ttu-id="6a13f-144">**Sökfråga** – Sökfrågan som ska användas med Innehållssökning skapas och körs.</span><span class="sxs-lookup"><span data-stu-id="6a13f-144">**Search query** - The search query that will be used with the Content Search is created and run.</span></span> <span data-ttu-id="6a13f-145">Mer information om sökfrågor finns i [Nyckelordsfrågor och sökvillkor för Innehållssökning.](keyword-queries-and-search-conditions.md)</span><span class="sxs-lookup"><span data-stu-id="6a13f-145">For more information about search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>


<span data-ttu-id="6a13f-146">**Så här kör du skriptet:**</span><span class="sxs-lookup"><span data-stu-id="6a13f-146">**To run the script:**</span></span>
    
1. <span data-ttu-id="6a13f-147">Spara följande text i en Windows PowerShell skriptfil med hjälp av ett filnamnssuffix .ps1; till exempel `SearchEXOOD4B.ps1` .</span><span class="sxs-lookup"><span data-stu-id="6a13f-147">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchEXOOD4B.ps1`.</span></span> <span data-ttu-id="6a13f-148">Spara filen i samma mapp där du sparade listan med användare i steg 2.</span><span class="sxs-lookup"><span data-stu-id="6a13f-148">Save the file to the same folder where you saved the list of users in Step 2.</span></span>
    
  ```powershell
  # This PowerShell script will prompt you for the following information:
  #    * Your user credentials 
  #    * The name of your organization's MySite domain                                              
  #    * The pathname for the text file that contains a list of user email addresses
  #    * The name of the Content Search that will be created
  #    * The search query string
  # The script will then:
  #    * Find the OneDrive for Business site for each user in the text file
  #    * Create and start a Content Search using the above information
  # Get user credentials
  if (!$credentials)
  {
      $credentials = Get-Credential
  }
  # Get the user's MySite domain name.  We use this to create the admin URL and root URL for OneDrive for Business
  $mySiteDomain = Read-Host "What is your organization's MySite domain?  For example,  'contoso' for 'https://contoso-my.sharepoint.com'"
  $AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
  $mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
  # Get other required information
  $inputfile = read-host "Enter the file name of the text file that contains the email addresses for the users you want to search"
  $searchName = Read-Host "Enter the name for the new search"
  $searchQuery = Read-Host "Enter the search query you want to use"
  $emailAddresses = Get-Content $inputfile | where {$_ -ne ""}  | foreach{ $_.Trim() }
  # Connect to Office 365
  if (!$s -or !$a)
  {
      $s = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://ps.compliance.protection.outlook.com/powershell-liveid" -Credential $credentials -Authentication Basic -AllowRedirection -SessionOption (New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck)
      $a = Import-PSSession $s -AllowClobber
      if (!$s)
      {
          Write-Error "Could not create PowerShell session."
          return;
      }
  }
  # Load the SharePoint assemblies from the SharePoint Online Management Shell
  # To install, go to https://go.microsoft.com/fwlink/p/?LinkId=255251
  if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
  {
      $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
      $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
      $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
      if (!$SharePointClient)
      {
          Write-Error "SharePoint Online Management Shell isn't installed, please install from: https://go.microsoft.com/fwlink/p/?LinkId=255251 and then run this script again"
          return;
      }
  }
  if (!$spCreds)
  {
      $spCreds = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($credentials.UserName, $credentials.Password)
  }
  # Add the path of the User Profile Service to the SPO admin URL, then create a new webservice proxy to access it
  $proxyaddr = "$AdminUrl/_vti_bin/UserProfileService.asmx?wsdl"
  $UserProfileService= New-WebServiceProxy -Uri $proxyaddr -UseDefaultCredential False
  $UserProfileService.Credentials = $credentials
  # Take care of auth cookies
  $strAuthCookie = $spCreds.GetAuthenticationCookie($AdminUrl)
  $uri = New-Object System.Uri($AdminUrl)
  $container = New-Object System.Net.CookieContainer
  $container.SetCookies($uri, $strAuthCookie)
  $UserProfileService.CookieContainer = $container
  Write-Host "Getting each user's OneDrive for Business URL"
  $urls = @()
  foreach($emailAddress in $emailAddresses)
  {
      try
      {
          $prop = $UserProfileService.GetUserProfileByName("i:0#.f|membership|$emailAddress") | Where-Object { $_.Name -eq "PersonalSpace" } 
          $url = $prop.values[0].value
          $furl = $mySiteUrlRoot + $url
          $urls += $furl
          Write-Host "-$emailAddress => $furl"
      }
      catch
      {
          Write-Warning "Could not locate OneDrive for $emailAddress"
      }
  }
  Write-Host "Creating and starting the search"
  $search = New-ComplianceSearch -Name $searchName -ExchangeLocation $emailAddresses -SharePointLocation $urls -ContentMatchQuery $searchQuery
  # Finally, start the search and then display the status
  if($search)
  {
      Start-ComplianceSearch $search.Name
      Get-ComplianceSearch $search.Name
  }
  
  ```

2. <span data-ttu-id="6a13f-149">Öppna Windows PowerShell och gå till mappen där du sparade skriptet och listan med användare från steg 2.</span><span class="sxs-lookup"><span data-stu-id="6a13f-149">Open Windows PowerShell and go to the folder where you saved the script and the list of users from Step 2.</span></span>
    
3. <span data-ttu-id="6a13f-150">Starta skriptet. till exempel:</span><span class="sxs-lookup"><span data-stu-id="6a13f-150">Start the script; for example:</span></span>
    
    ```powershell
    .\SearchEXOOD4B.ps1
    ```

4. <span data-ttu-id="6a13f-151">När du uppmanas att ange dina autentiseringsuppgifter anger du din e-postadress och ditt lösenord och klickar sedan på **OK.**</span><span class="sxs-lookup"><span data-stu-id="6a13f-151">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span> 
    
5. <span data-ttu-id="6a13f-152">Ange följande information när du uppmanas att göra det i skriptet.</span><span class="sxs-lookup"><span data-stu-id="6a13f-152">Enter following information when prompted by the script.</span></span> <span data-ttu-id="6a13f-153">Skriv in varje informationsbit och tryck sedan på **Retur.**</span><span class="sxs-lookup"><span data-stu-id="6a13f-153">Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="6a13f-154">Namnet på din MySite-domän.</span><span class="sxs-lookup"><span data-stu-id="6a13f-154">The name of your MySite domain.</span></span> 
    
    - <span data-ttu-id="6a13f-155">Sökvägen till textfilen som innehåller listan över användare.</span><span class="sxs-lookup"><span data-stu-id="6a13f-155">The pathname of the text file that contains the list of users.</span></span>
    
    - <span data-ttu-id="6a13f-156">Ett namn på Innehållssökning.</span><span class="sxs-lookup"><span data-stu-id="6a13f-156">A name for the Content Search.</span></span>
    
    - <span data-ttu-id="6a13f-157">Sökfrågan (lämna det här tomt om du vill returnera alla objekt på innehållsplatserna).</span><span class="sxs-lookup"><span data-stu-id="6a13f-157">The search query (leave this blank to return all items in the content locations).</span></span>
    
    <span data-ttu-id="6a13f-158">Skriptet hämtar webbadresserna för varje OneDrive för företag och skapar sedan sökningen och startar sökningen.</span><span class="sxs-lookup"><span data-stu-id="6a13f-158">The script gets the URLs for each OneDrive for Business site and then creates and starts the search.</span></span> <span data-ttu-id="6a13f-159">Du kan antingen köra cmdleten **Get-ComplianceSearch** i PowerShell för säkerhets- och efterlevnadscenter för  & för att visa sökstatistik och resultat, eller så kan du gå till sidan Innehållssökning i Säkerhets- och efterlevnadscenter för & och visa information om sökningen.</span><span class="sxs-lookup"><span data-stu-id="6a13f-159">You can either run the **Get-ComplianceSearch** cmdlet in Security & Compliance Center PowerShell to display the search statistics and results, or you can go to the **Content search** page in the Security & Compliance Center to view information about the search.</span></span>