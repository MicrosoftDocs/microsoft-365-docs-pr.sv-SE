---
title: Använda ett skript för att lägga till användare i ett ärende för bas-eDiscovery
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
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
ms.custom: seo-marvel-apr2020
description: Lär dig hur du kör ett skript för att lägga & OneDrive för företag postlådor på en ny plats som är kopplad till ett eDiscovery-ärende Microsoft 365 efterlevnadscenter.
ms.openlocfilehash: d6e6ff1ca053fd8c729054490e78ef42dc64e829
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161989"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-a-core-ediscovery-case"></a>Använda ett skript för att lägga till användare i ett ärende för bas-eDiscovery

Säkerhets& Compliance Center PowerShell innehåller cmdlets som gör att du kan automatisera tidskrävande uppgifter när du skapar och hanterar eDiscovery-ärenden. För närvarande tar det tid och förberedelse att använda grundärende för eDiscovery-ärendet i säkerhets- och efterlevnadscentret för säkerhet i & för att skapa ett stort antal platser för innehåll som är beroende av senare användning. Innan du skapar ett område måste du till exempel samla in WEBBADRESSen för OneDrive för företag webbplats som du vill skapa ett område för. För varje användare som du vill använda som väntande måste du sedan lägga till deras postlåda och deras OneDrive för företag-webbplats i holden. Du kan använda skriptet i den här artikeln för att automatisera processen.
  
Skriptet uppmanar dig att ange namnet på organisationens domän Min webbplats (till exempel i URL-adressen, namnet på ett befintligt `contoso` eDiscovery-ärende, namnet på det nya håll som är kopplat till ärendet, en lista med e-postadresser till de användare som du vill sätta på plats och en sökfråga som ska användas om du vill skapa ett frågebaserat https://contoso-my.sharepoint.com) ärende. Skriptet hämtar sedan URL-adressen för OneDrive för företag-webbplatsen för varje användare i listan, skapar det nya antalet och lägger sedan till postlådan och OneDrive för företag-webbplatsen för varje användare i listan i listan. Skriptet genererar även loggfiler som innehåller information om det nya arkivet.
  
Här är stegen för att göra detta:
  
[Steg 1: Installera SharePoint Online Management Shell](#step-1-install-the-sharepoint-online-management-shell)
  
[Steg 2: Skapa en lista över användare](#step-2-generate-a-list-of-users)
  
[Steg 3: Kör skriptet för att skapa ett väntande och lägga till användare](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-add-users-to-a-hold"></a>Innan du lägger till användare i en holden

- Du måste vara medlem i rollgruppen för eDiscovery Manager i säkerhets- och efterlevnadscentret för & och en SharePoint Online-administratör för att kunna köra skriptet i steg 3. Mer information finns i [Tilldela eDiscovery-behörigheter i säkerhets- Office 365 & efterlevnadscenter.](assign-ediscovery-permissions.md)

- Maximalt 1 000 postlådor och 100 webbplatser kan läggas till i ett hold som är kopplat till ett eDiscovery-ärende i Säkerhets- och & efterlevnadscenter. Anta att alla användare som du vill skapa en webbplats för OneDrive för företag har möjlighet att lägga till högst 100 användare i ett område med hjälp av skriptet i den här artikeln.

- Se till att spara listan med användare som du skapar i steg 2 och skriptet i steg 3 i samma mapp. Det gör det enklare att köra skriptet.

- Skriptet lägger till listan med användare i ett nytt ärende som är kopplat till ett befintligt ärende. Se till att det ärende som du vill koppla behåll till skapas innan du kör skriptet.

- Skriptet i den här artikeln stöder modern autentisering när du ansluter till Security & Compliance Center PowerShell och SharePoint Online Management Shell. Du kan använda skriptet som det är om du är en Microsoft 365 eller en Microsoft 365 GCC organisation. Om du är en Office 365 Germany-organisation, Microsoft 365 GCC High-organisation eller en Microsoft 365 DoD-organisation måste du redigera skriptet för att kunna köra det. Specifikt måste du redigera linjen och använda parametrarna ConnectionUri och `Connect-IPPSSession` *AzureADAuthorizationEndpointUri* (och lämpliga värden för din organisationstyp) för att ansluta till *Säkerhets-* och efterlevnadscenter för & PowerShell. Mer information finns i exemplen i [Anslut Security & Compliance Center PowerShell.](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)

- Skriptet kopplar automatiskt bort från Security & Compliance Center PowerShell och SharePoint Online Management Shell.

- Skriptet innehåller minimal felhantering. Det primära syftet är att snabbt och enkelt placera postlådan och OneDrive för företag-webbplatsen för varje användare i holden.

- Exempelskripten som tillhandahålls i det här avsnittet stöds inte under något standardsupportprogram eller någon standardsupporttjänst från Microsoft. Exempelskripten ges i befintligt skick utan garantier av något slag. Vidare frånsäger sig Microsoft alla underförstådda garantier, inklusive, utan begränsning, underförstådda garantier om säljbarhet eller lämplighet för ett visst ändamål. Hela risken i samband med användningen av eller prestandan hos exempelskripten och dokumentationen vilar på dig. Under inga omständigheter ska Microsoft, dess upphovspersoner eller någon annan som är involverad i skapandet, produktionen eller leveransen av skripten hållas ansvariga för någon som helst skada (inklusive, men inte begränsat till, skador avseende utebliven vinst, driftavbrott, förlust av affärsinformation eller annan ekonomisk skada) som uppstår till följd av användning eller svårighet eller omöjlighet att använda exempelskripten eller dokumentationen, även om Microsoft har fått information om att sådana skador kan uppstå.

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>Steg 1: Installera SharePoint Online Management Shell

Det första steget är att installera SharePoint Online Management Shell om det inte redan är installerat på den lokala datorn. Du behöver inte använda gränssnittet i den här proceduren, men du måste installera det eftersom det innehåller förutsättningar som krävs av skriptet som du kör i steg 3. Dessa krav gör att skriptet kan kommunicera med SharePoint Online för att få URL:er för OneDrive för företag webbplatser.
  
Gå till [Konfigurera SharePoint Online Management Shell Windows PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) och utför steg 1 och steg 2 för att installera SharePoint Online Management Shell på den lokala datorn.

## <a name="step-2-generate-a-list-of-users"></a>Steg 2: Skapa en lista över användare

Skriptet i steg 3 skapar ett ärende som är kopplat till ett eDiscovery-ärende och lägger till postlådorna och OneDrive för företag av en lista över användare i servern. Du kan skriva e-postadresserna i en textfil eller köra ett kommando i Windows PowerShell för att visa en lista med e-postadresser och spara dem i en fil (som finns i samma mapp som skriptet ska sparas i steg 3).
  
Här är ett PowerShell-kommando (som du kör med fjärr-PowerShell som är anslutet till din Exchange Online-organisation) för att få en lista med e-postadresser för alla användare i organisationen och spara den i en textfil som heter HoldUsers.txt.
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

När du har kört kommandot öppnar du textfilen och tar bort rubriken som innehåller  `PrimarySmtpAddress` egenskapsnamnet. Ta sedan bort alla e-postadresser utom de för de användare som du vill lägga till i undantagssteget som du skapar i steg 3. Kontrollera att det inte finns tomma rader före eller efter listan med e-postadresser.
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a>Steg 3: Kör skriptet för att skapa ett väntande och lägga till användare

När du kör skriptet i det här steget uppmanas du att ange följande information. Se till att ha den här informationen redo innan du kör skriptet.
  
- **Dina användarautentiseringsuppgifter:** Skriptet använder dina autentiseringsuppgifter för att ansluta till Säkerhets- & med PowerShell. De här autentiseringsuppgifterna används också för att komma SharePoint Online för att hämta e OneDrive för företag adresser för listan med användare.

- **Namnet på din SharePoint domän:** Skriptet uppmanar dig att ange det här namnet så att det kan ansluta SharePoint administrationscentret. Den använder också domännamnet för OneDrive i organisationen. Om URL:en för administrationscentret till exempel är och URL:en för OneDrive är anger du när skriptet uppmanar dig att `https://contoso-admin.sharepoint.com` `https://contoso-my.sharepoint.com` ange `contoso` domännamnet.

- **Namnet på ärendet:** Namnet på ett befintligt ärende. Skriptet skapar ett nytt ärende som är associerat med det här fallet.

- **Namn på det hållna:** Namnet på det hållna skriptet skapar och associerar med det angivna ärendet.

- **Sökfråga för ett frågebaserat rymmer:** Du kan skapa ett frågebaserat hold-baserat så att endast det innehåll som uppfyller de angivna sökvillkoren får plats. Om du vill placera allt innehåll i meddelandefältet **trycker** du på Retur när du uppmanas att ange en sökfråga.

- **Aktivera eller inte aktivera det:** Du kan aktivera skriptets aktivering när det har skapats, eller så kan du låta skriptet skapa ett väntande skript utan att aktivera det. Om du inte har skriptet som aktiverar körningen kan du aktivera det senare i Security & Compliance Center eller genom att köra följande PowerShell-kommandon:

  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- **Namnet på textfilen med** listan över användare – namnet på textfilen från steg 2 som innehåller listan över användare som ska läggas till i fältet. Om filen finns i samma mapp som skriptet skriver du namnet på filen (till exempel skriv HoldUsers.txt). Om textfilen finns i en annan mapp skriver du den fullständiga sökvägen till filen.

När du har samlat in den information som skriptet kommer att be dig om är det sista steget att köra skriptet för att skapa det nya tillägget och lägga till användare i det.
  
1. Spara följande text i Windows PowerShell skriptfil med ett filnamnssuffix på `.ps1` . Till exempel `AddUsersToHold.ps1`.

```powershell
#script begin
" "
write-host "***********************************************"
write-host "   Security & Compliance Center PowerShell  " -foregroundColor yellow -backgroundcolor darkgreen
write-host "   Core eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
write-host "***********************************************"
" "
# Connect to SCC PowerShell using modern authentication
if (!$SccSession)
{
  Import-Module ExchangeOnlineManagement
  Connect-IPPSSession
}

# Get the organization's domain name. We use this to create the SharePoint admin URL and root URL for OneDrive for Business.
""
$mySiteDomain = Read-Host "Enter the domain name for your SharePoint organization. We use this name to connect to SharePoint admin center and for the OneDrive URLs in your organization. For example, 'contoso' in 'https://contoso-admin.sharepoint.com' and 'https://contoso-my.sharepoint.com'"
""

# Connect to PnP Online using modern authentication
Import-Module PnP.PowerShell
Connect-PnPOnline -Url https://$mySiteDomain-admin.sharepoint.com -UseWebLogin

# Load the SharePoint assemblies from the SharePoint Online Management Shell
# To install, go to https://go.microsoft.com/fwlink/p/?LinkId=255251
if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
{
    $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
    $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
    $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
    if (!$SharePointClient)
    {
        Write-Error "The SharePoint Online Management Shell isn't installed. Please install it from: https://go.microsoft.com/fwlink/p/?LinkId=255251 and then re-run this script."
        return;
    }
}

# Get other required information
do{
$casename = Read-Host "Enter the name of the case"
$caseexists = (get-compliancecase -identity "$casename" -erroraction SilentlyContinue).isvalid
if($caseexists -ne 'True')
{""
write-host "A case named '$casename' doesn't exist. Please specify the name of an existing case, or create a new case and then re-run the script." -foregroundColor Yellow
""}
}While($caseexists -ne 'True')
""
do{
$holdName = Read-Host "Enter the name of the new hold"
$holdexists=(get-caseholdpolicy -identity "$holdname" -case "$casename" -erroraction SilentlyContinue).isvalid
if($holdexists -eq 'True')
{""
write-host "A hold named '$holdname' already exists. Please specify a new hold name." -foregroundColor Yellow
""}
}While($holdexists -eq 'True')
""
$holdQuery = Read-Host "Enter a search query to create a query-based hold, or press Enter to hold all content"
""
$holdstatus = read-host "Do you want the hold enabled after it's created? (Yes/No)"
do{
""
$inputfile = read-host "Enter the name of the text file that contains the email addresses of the users to add to the hold"
""
$fileexists = test-path -path $inputfile
if($fileexists -ne 'True'){write-host "$inputfile doesn't exist. Please enter a valid file name." -foregroundcolor Yellow}
}while($fileexists -ne 'True')
#Import the list of addresses from the txt file.  Trim any excess spaces and make sure all addresses 
    #in the list are unique.
  [array]$emailAddresses = Get-Content $inputfile -ErrorAction SilentlyContinue | where {$_.trim() -ne ""}  | foreach{ $_.Trim() }
  [int]$dupl = $emailAddresses.count
  [array]$emailAddresses = $emailAddresses | select-object -unique
  $dupl -= $emailAddresses.count
#Validate email addresses so the hold creation does not run in to an error.
if($emailaddresses.count -gt 0){
write-host ($emailAddresses).count "addresses were found in the text file. There were $dupl duplicate entries in the file." -foregroundColor Yellow
""
Write-host "Validating the email addresses. Please wait..." -foregroundColor Yellow
""
$finallist =@()
foreach($emailAddress in $emailAddresses)
{
if((get-recipient $emailaddress -erroraction SilentlyContinue).isvalid -eq 'True')
{$finallist += $emailaddress}
else {"Unable to find the user $emailaddress"
[array]$excludedlist += $emailaddress}
}
""
#Find user's OneDrive account URL using email address
Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow 
""
$AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
$mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
$urls = @()
foreach($emailAddress in $emailAddresses)
{
try
{
$url=Get-PnPUserProfileProperty -Account $emailAddress | Select PersonalUrl
$urls += $url.PersonalUrl
       Write-Host "- $emailAddress => $url"
       [array]$ODadded += $url.PersonalUrl
       }catch { 
 Write-Warning "Could not locate OneDrive for $emailAddress"
 [array]$ODExluded += $emailAddress
 Continue }
}
$urls | FL
if(($finallist.count -gt 0) -or ($urls.count -gt 0)){
""
Write-Host "Creating the hold named $holdname. Please wait..." -foregroundColor Yellow
if(($holdstatus -eq "Y") -or ($holdstatus -eq  "y") -or ($holdstatus -eq "yes") -or ($holdstatus -eq "YES")){
New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $True | out-null
New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery | out-null
}
else{
New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $false | out-null
New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery -disabled $true | out-null
}
""
}
else {"No valid locations were identified. Therefore, the hold wasn't created."}
#write log files (if needed)
$newhold=Get-CaseHoldPolicy -Identity "$holdname" -Case "$casename" -erroraction SilentlyContinue
$newholdrule=Get-CaseHoldRule -Identity "$holdName" -erroraction SilentlyContinue
if(($ODAdded.count -gt 0) -or ($ODExluded.count -gt 0) -or ($finallist.count -gt 0) -or ($excludedlist.count -gt 0) -or ($newhold.isvalid -eq 'True') -or ($newholdrule.isvalid -eq 'True'))
{
Write-Host "Generating output files..." -foregroundColor Yellow
if($ODAdded.count -gt 0){
"OneDrive Locations" | add-content .\LocationsOnHold.txt
"==================" | add-content .\LocationsOnHold.txt 
$newhold.SharePointLocation.name | add-content .\LocationsOnHold.txt}
if($ODExluded.count -gt 0){ 
"Users without OneDrive locations" | add-content .\LocationsNotOnHold.txt
"================================" | add-content .\LocationsNotOnHold.txt
$ODExluded | add-content .\LocationsNotOnHold.txt}
if($finallist.count -gt 0){
" " | add-content .\LocationsOnHold.txt
"Exchange Locations" | add-content .\LocationsOnHold.txt
"==================" | add-content .\LocationsOnHold.txt 
$newhold.ExchangeLocation.name | add-content .\LocationsOnHold.txt}
if($excludedlist.count -gt 0){
" "| add-content .\LocationsNotOnHold.txt
"Mailboxes not added to the hold" | add-content .\LocationsNotOnHold.txt
"===============================" | add-content .\LocationsNotOnHold.txt
$excludedlist | add-content .\LocationsNotOnHold.txt}
$FormatEnumerationLimit=-1
if($newhold.isvalid -eq 'True'){$newhold|fl >.\GetCaseHoldPolicy.txt}
if($newholdrule.isvalid -eq 'True'){$newholdrule|Fl >.\GetCaseHoldRule.txt}
}
}
else {"The hold wasn't created because no valid entries were found in the text file."}
""
#Disconnect from SCC PowerShell and PnPOnline

Write-host "Disconnecting from SCC PowerShell and PnP Online" -foregroundColor Yellow
Get-PSSession | Remove-PSSession
Disconnect-PnPOnline

Write-host "Script complete!" -foregroundColor Yellow
""
#script end
```

2. Öppna den lokala datorn Windows PowerShell gå till mappen där du sparade skriptet.

3. Kör skriptet. till exempel:

   ```powershell
   .\AddUsersToHold.ps1
   ```

4. Ange den information som skriptet uppmanar dig att ange.

   Skriptet ansluter till Säkerhets- & Efterlevnadscenter PowerShell, och skapar sedan det nya antalet i eDiscovery-ärendet och lägger till postlådorna och OneDrive för företag för användarna i listan. Du kan gå till ärendet på sidan **eDiscovery** i säkerhets- & kompatibilitetscentret för att visa det nya antalet.

När skriptet har körts klart skapas följande loggfiler och sparas i den mapp där skriptet finns.
  
- **LocationsOnHold.txt:** Innehåller en lista över postlådor och OneDrive för företag webbplatser som skriptet har satts i servern.

- **LocationsNotOnHold.txt:** Innehåller en lista över postlådor OneDrive för företag webbplatser som skriptet inte har plats för. Om en användare har en postlåda, men inte en OneDrive för företag-webbplats, skulle användaren ingå i listan med OneDrive för företag-webbplatser som inte har satts på en plats.

- **GetCaseHoldPolicy.txt:** Innehåller resultatet från cmdleten **Get-CaseHoldPolicy** för det nya holden som skriptet körde när det nya fältet hade skapats. Informationen som returneras av den här cmdleten innehåller en lista över användare vars postlådor och OneDrive för företag platser har aktiverats och om det är aktiverat eller inaktiverat. 

- **GetCaseHoldRule.txt:** Innehåller resultatet från cmdleten **Get-CaseHoldRule** för det nya holden, som skriptet kördes efter att det nya fältet hade skapats. Den information som returneras av den här cmdleten innehåller sökfrågan om du använde skriptet för att skapa ett frågebaserat håll.