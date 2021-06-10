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
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a>Använda innehållssökning för att söka i postlådan OneDrive för företag efter en lista med användare

Säkerhets- & efterlevnadscenter innehåller ett antal Windows PowerShell cmdlets som du kan använda för att automatisera tidskrävande eDiscovery-relaterade uppgifter. För närvarande kan du skapa en innehållssökning i Säkerhets- & efterlevnadscenter för att söka efter ett stort antal plats för det skyddande innehållet tar tid och förberedelser. Innan du skapar en sökning måste du samla in URL-adressen för OneDrive för företag-webbplats och sedan lägga till varje postlåda OneDrive för företag webbplats i sökningen. I kommande versioner blir det enklare att göra detta i Säkerhets- & Efterlevnadscenter. Tills dess kan du använda skriptet i den här artikeln för att automatisera processen. Det här skriptet uppmanar dig att ange namnet på din organisations Min webbplats-domän (till exempel **contoso** i URL:en), en lista med användarnas e-postadresser, namnet på den nya innehållssökningen och den sökfråga som ska `https://contoso-my.sharepoint.com` användas. Skriptet får URL-OneDrive för företag för varje användare i listan och skapar och startar en innehållssökning som söker i postlådan och OneDrive för företag-webbplatsen för varje användare i listan, med hjälp av sökfrågan som du anger.
  
## <a name="permissions-and-script-information"></a>Behörigheter och skriptinformation

- Du måste vara medlem i rollgruppen för eDiscovery Manager i säkerhets- och efterlevnadscentret för & och en global SharePoint Online-administratör för att kunna köra skriptet i steg 3.

- Se till att spara listan med användare som du skapar i steg 2 och skriptet i steg 3 i samma mapp. Det gör det enklare att köra skriptet.

- Skriptet innehåller minimal felhantering. Dess huvudsakliga syfte är att snabbt och enkelt söka i postlådan och OneDrive för företag webbplatsen för varje användare.

- Exempelskripten som tillhandahålls i det här avsnittet stöds inte under något standardsupportprogram eller någon standardsupporttjänst från Microsoft. Exempelskripten ges i befintligt skick utan garantier av något slag. Vidare frånsäger sig Microsoft alla underförstådda garantier, inklusive, utan begränsning, underförstådda garantier om säljbarhet eller lämplighet för ett visst ändamål. Hela risken i samband med användningen av eller prestandan hos exempelskripten och dokumentationen vilar på dig. Under inga omständigheter ska Microsoft, dess upphovspersoner eller någon annan som är involverad i skapandet, produktionen eller leveransen av skripten hållas ansvariga för någon som helst skada (inklusive, men inte begränsat till, skador avseende utebliven vinst, driftavbrott, förlust av affärsinformation eller annan ekonomisk skada) som uppstår till följd av användning eller svårighet eller omöjlighet att använda exempelskripten eller dokumentationen, även om Microsoft har fått information om att sådana skador kan uppstå.

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>Steg 1: Installera SharePoint Online Management Shell

Det första steget är att installera SharePoint Online Management Shell. Du behöver inte använda gränssnittet i den här proceduren, men du måste installera det eftersom det innehåller förutsättningar som krävs av skriptet som du kör i steg 3. Dessa krav gör att skriptet kan kommunicera med SharePoint Online för att få URL:er för OneDrive för företag webbplatser.
  
Gå till [Konfigurera SharePoint Online Management Shell Windows PowerShell och](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) utför steg 1 och steg 2 för att installera SharePoint Online Management Shell.
  
## <a name="step-2-generate-a-list-of-users"></a>Steg 2: Skapa en lista över användare

Skriptet i steg 3 skapar en innehållssökning för att söka i postlådorna och OneDrive efter en lista med användare. Du kan skriva e-postadresserna i en textfil eller köra ett kommando i Windows PowerShell för att visa en lista med e-postadresser och spara dem i en fil (som finns i samma mapp som skriptet ska sparas i steg 3).
  
Här är ett [Exchange Online PowerShell-kommando](/powershell/exchange/connect-to-exchange-online-powershell) som du kan använda för att få en lista över e-postadresser för alla användare i organisationen och spara den i en textfil med namnet `Users.txt` . 
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

När du har kört kommandot måste du öppna filen och ta bort rubriken som innehåller  `PrimarySmtpAddress` egenskapsnamnet. Textfilen ska bara innehålla en lista med e-postadresser och ingenting annat. Kontrollera att det inte finns tomma rader före eller efter listan med e-postadresser.
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a>Steg 3: Kör skriptet för att skapa och starta sökningen

När du kör skriptet i det här steget uppmanas du att ange följande information. Se till att ha den här informationen redo innan du kör skriptet.
  
- **Dina användarautentiseringsuppgifter** – Skriptet använder dina autentiseringsuppgifter för att komma åt SharePoint Online för att få URL-adresser för OneDrive för företag och ansluta till & Säkerhets- och efterlevnadscenter med fjärr-PowerShell. 
    
- **Namn på Min webbplats-domänen** – Domänen Min webbplats är den domän som innehåller alla OneDrive för företag i organisationen. Om URL:en för din Min webbplats-domän till exempel är anger du när du uppmanas att ange namnet på **https://contoso-my.sharepoint.com**  `contoso` din Min webbplats-domän. 
    
- **Sökväg till textfilen från steg 2** – sökvägen till textfilen som du skapade i steg 2. Om textfilen och skriptet finns i samma mapp anger du namnet på textfilen. Annars anger du hela sökvägen för textfilen. 
    
- **Namn på innehållssökningen** – namnet på den innehållssökning som skapas av skriptet. 
    
- **Sökfråga** – Sökfrågan som ska användas med Innehållssökning skapas och körs. Mer information om sökfrågor finns i [Nyckelordsfrågor och sökvillkor för Innehållssökning.](keyword-queries-and-search-conditions.md)


**Så här kör du skriptet:**
    
1. Spara följande text i en Windows PowerShell skriptfil med hjälp av ett filnamnssuffix .ps1; till exempel `SearchEXOOD4B.ps1` . Spara filen i samma mapp där du sparade listan med användare i steg 2.
    
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

2. Öppna Windows PowerShell och gå till mappen där du sparade skriptet och listan med användare från steg 2.
    
3. Starta skriptet. till exempel:
    
    ```powershell
    .\SearchEXOOD4B.ps1
    ```

4. När du uppmanas att ange dina autentiseringsuppgifter anger du din e-postadress och ditt lösenord och klickar sedan på **OK.** 
    
5. Ange följande information när du uppmanas att göra det i skriptet. Skriv in varje informationsbit och tryck sedan på **Retur.**
    
    - Namnet på din MySite-domän. 
    
    - Sökvägen till textfilen som innehåller listan över användare.
    
    - Ett namn på Innehållssökning.
    
    - Sökfrågan (lämna det här tomt om du vill returnera alla objekt på innehållsplatserna).
    
    Skriptet hämtar webbadresserna för varje OneDrive för företag och skapar sedan sökningen och startar sökningen. Du kan antingen köra cmdleten **Get-ComplianceSearch** i PowerShell för säkerhets- och efterlevnadscenter för  & för att visa sökstatistik och resultat, eller så kan du gå till sidan Innehållssökning i Säkerhets- och efterlevnadscenter för & och visa information om sökningen.