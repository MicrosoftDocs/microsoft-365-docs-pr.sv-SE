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
# <a name="clone-a-content-search"></a>Klona en innehållssökning

Det kan ta en stund att skapa en innehållssökning i efterlevnadscentret i Office 365 eller Microsoft 365 som genomsöker många postlådor SharePoint-OneDrive för företag-webbplatser. Att ange webbplatser att söka på kan också lätt bli fel om du skriver en URL-adress fel. För att undvika dessa problem kan du använda skriptet Windows PowerShell den här artikeln för att snabbt klona en befintlig innehållssökning. När du klonar en sökning skapas en ny sökning (med ett annat namn) som innehåller samma egenskaper (till exempel innehållsplatserna och sökfrågan) som den ursprungliga sökningen. Sedan kan du redigera den nya sökningen genom att ändra nyckelordsfrågan eller datumintervallet och köra den.
  
Varför klona innehållssökningar?
  
- Om du vill jämföra resultat från olika sökordsökfrågor körs på samma innehållsplatser.
    
- För att spara dig från att behöva gå tillbaka till ett stort antal innehållsplatser när du skapar en ny sökning.
    
- Om du vill minska storleken på sökresultatet. Om du till exempel har en sökning som returnerar för många resultat att exportera kan du klona sökningen och sedan lägga till ett sökvillkor baserat på ett datumintervall för att minska antalet sökresultat.
  
## <a name="script-information"></a>Skriptinformation

- Du måste vara medlem i rollgruppen för eDiscovery Manager i Säkerhets- och & för att köra skriptet som beskrivs i det här avsnittet.
    
- Skriptet innehåller minimal felhantering. Det primära syftet med skriptet är att snabbt klona en innehållssökning.
    
- Skriptet skapar en ny innehållssökning, men startar den inte.
    
- Det här skriptet tar hänsyn till om den innehållssökning som du håller på att undersöka är kopplad till ett eDiscovery-fall. Om sökningen är kopplad till ett ärende associeras den nya sökningen också med samma ärende. Om den befintliga sökningen inte är kopplad till ett ärende visas den nya sökningen på sidan **Innehållssökning** i efterlevnadscentret. 
    
- Exempelskriptet som tillhandahålls i det här avsnittet stöds inte under något standardsupportprogram eller någon standardsupporttjänst från Microsoft. Exempelskriptet tillhandahålls i SIN FORM utan några som helst garantier. Vidare frånsäger sig Microsoft alla underförstådda garantier, inklusive, utan begränsning, alla underförstådda garantier om säljbarhet eller lämplighet för ett visst ändamål. Hela risken i samband med användningen av eller prestandan hos exempelskriptet och dokumentationen ligger kvar hos dig. Under inga omständigheter ska Microsoft, dess upphovspersoner eller någon annan som är involverad i skapandet, produktionen eller leveransen av skripten hållas ansvariga för någon som helst skada (inklusive, men inte begränsat till, skador för vinstförlust, driftavbrott, förlust av affärsinformation eller annan ekonomisk skada) som uppstår till följd av användning eller oförmåga att använda exempelskripten eller dokumentationen, även om Microsoft har fått information om att sådana skador kan uppstå.
  
## <a name="step-1-run-the-script-to-clone-a-search"></a>Steg 1: Kör skriptet för att klona en sökning

Skriptet i det här steget skapar en ny innehållssökning genom att klona en befintlig. När du kör det här skriptet uppmanas du att ange följande information:
  
- **Dina användarautentiseringsuppgifter** – Skriptet använder dina autentiseringsuppgifter för att ansluta till säkerhets- & kompatibilitetscentret för din organisation med Windows PowerShell. Som tidigare nämnts måste du vara medlem i rollgruppen för eDiscovery Manager i Säkerhets- & CompCompliance Center för att köra skriptet. 
    
- **Namnet på den befintliga sökningen –** Det här är den innehållssökning som du vill klona. 
    
- **Namnet på den nya** sökning som kommer att skapas – Om du låter det här värdet vara tomt skapar skriptet ett namn för den nya sökningen som baseras på namnet på den sökning som du är klonad. 
    
Så här klonar du en sökning:
  
1. Spara följande text i en Windows PowerShell skriptfil med hjälp av ett filnamnssuffix .ps1; till exempel `CloneSearch.ps1` .
    
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

2. Öppna Windows PowerShell och gå till mappen där du sparade skriptet.
    
3. Kör skriptet. till exempel:
    
    ```powershell
    .\CloneSearch.ps1
    ```

4. När du uppmanas att ange dina autentiseringsuppgifter anger du din e-postadress och ditt lösenord och klickar sedan på **OK.**
    
5. Ange följande information när du uppmanas att göra det i skriptet. Skriv in varje informationsbit och tryck sedan på **Retur.**
    
    - Namnet på den befintliga sökningen.
    
    - Namnet på den nya sökningen.
    
    Skriptet skapar den nya innehållssökningen, men startar den inte. Då kan du redigera och köra sökningen i nästa steg. Du kan visa egenskaperna för den nya sökningen genom att köra cmdleten **Get-ComplianceSearch** eller genom att gå till sidan Innehållssökning eller **eDiscovery** i efterlevnadscentret, beroende på om den nya sökningen är kopplad till ett ärende.  
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a>Steg 2: Redigera och kör den klonade sökningen i efterlevnadscentret

När du har kört skriptet för att klona en befintlig innehållssökning är nästa steg att gå till efterlevnadscentret och redigera och köra den nya sökningen. Som tidigare nämnts kan du redigera en sökning genom att ändra sökordets sökfråga och lägga till eller ta bort sökvillkor. Mer information finns i:
  
- [Innehållssökning i Office 365](content-search.md)
    
- [Nyckelordsfrågor och sökvillkor för innehållssökning](keyword-queries-and-search-conditions.md)
    
- [eDiscovery-fall](./get-started-core-ediscovery.md)