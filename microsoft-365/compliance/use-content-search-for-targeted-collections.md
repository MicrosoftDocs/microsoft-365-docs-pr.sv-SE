---
title: Använda innehållssökning för riktade samlingar
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
- M365-security-compliance
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
ms.custom: seo-marvel-apr2020
description: Använd Innehållssökning i kompatibilitetscentret för Microsoft 365 för att utföra en riktad samling som söker efter objekt i en viss postlåda eller webbplatsmapp.
ms.openlocfilehash: cf0364d39a78e1bbbc062d85ce750d190fbbda5a
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311904"
---
# <a name="use-content-search-for-targeted-collections"></a>Använda innehållssökning för riktade samlingar

Verktyget för innehållssökning i efterlevnadscentret för Microsoft 365 tillhandahåller inte något direkt sätt i användargränssnittet för att söka i specifika mappar i Exchange-postlådor eller på SharePoint- och OneDrive för företag-webbplatser. Du kan emellertid söka i specifika mappar (kallas för riktad *samling)* genom att ange egenskapen mapp-ID för e-post eller sökväg (DocumentLink) för webbplatser i den faktiska sökfrågesyntaxen. Det kan vara användbart att använda innehållssökning för att utföra en riktad samling när du är säker på att objekt som svarar på ett ärende eller objekt med privilegierad åtkomst finns i en viss postlåda eller webbplatsmapp. Du kan använda skriptet i den här artikeln för att hämta mapp-ID för postlådemappar eller sökvägen (DocumentLink) för mappar på en SharePoint och OneDrive för företag webbplats. Sedan kan du använda mapp-ID:t eller sökvägen i en sökfråga för att returnera objekt som finns i mappen.

> [!NOTE]
> För att returnera innehåll som finns i en mapp på en SharePoint- eller OneDrive för företag-webbplats använder skriptet i det här avsnittet den hanterade DocumentLink-egenskapen i stället för egenskapen Path. Egenskapen DocumentLink är mer robust än egenskapen Path eftersom den returnerar allt innehåll i en mapp, medan egenskapen Path inte returnerar vissa mediefiler.

## <a name="before-you-run-a-targeted-collection"></a>Innan du kör en riktad samling

- Du måste vara medlem i rollgruppen för eDiscovery Manager i Säkerhets- & kompatibilitetscenter för att kunna köra skriptet i steg 1. Mer information finns i [Tilldela eDiscovery-behörigheter](assign-ediscovery-permissions.md).

- Du måste också ha tilldelats rollen E-postmottagare i Exchange Online organisation. Detta krävs för att köra cmdleten **Get-MailboxFolderStatistics,** som ingår i skriptet. Som standard tilldelas rollen E-postmottagare rollgrupperna Organisationshantering och Mottagarhantering i Exchange Online. Mer information om hur du tilldelar behörigheter Exchange Online i Hantera [rollgruppsmedlemmar.](/exchange/manage-role-group-members-exchange-2013-help) Du kan också skapa en anpassad rollgrupp, tilldela rollen E-postmottagare till den och sedan lägga till de medlemmar som behöver köra skriptet i steg 1. Mer information finns i [Hantera rollgrupper.](/Exchange/permissions-exo/role-groups)

- Skriptet i den här artikeln har stöd för modern autentisering. Du kan använda skriptet som det är om du är en Microsoft 365 eller en Microsoft 365 GCC organisation. Om du är en Office 365 Germany-organisation, Microsoft 365 GCC High-organisation eller en Microsoft 365 DoD-organisation måste du redigera skriptet för att kunna köra det. Du måste specifikt redigera linjen och använda `Connect-ExchangeOnline` *ExchangeEnvironmentName-parametern* (och rätt värde för organisationstypen) för att ansluta till Exchange Online PowerShell.  Du måste också redigera linjen och använda parametrarna `Connect-IPPSSession` *ConnectionUri* och *AzureADAuthorizationEndpointUri* (och lämpliga värden för organisationstypen) för att ansluta till Security & Compliance Center PowerShell. Mer information finns i exemplen i [PowerShell Anslut](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-without-using-mfa) Exchange Online och Anslut till PowerShell för [& Compliance Center.](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)

- Varje gång du kör skriptet skapas en ny fjärrsession för PowerShell. Det innebär att du kan använda alla tillgängliga PowerShell-fjärrsessioner. Om du vill förhindra att det händer kör du följande kommando för att koppla bort de aktiva fjärrsessionerna i PowerShell.

  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    Mer information finns i Anslut [till Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

- Skriptet innehåller minimal felhantering. Det primära syftet med skriptet är att snabbt visa en lista med mapp-ID:er för postlådor eller webbplatssökvägar som kan användas i sökfrågesyntaxen för en innehållssökning för att utföra en riktad samling.

- Exempelskriptet som tillhandahålls i det här avsnittet stöds inte under något standardsupportprogram eller någon standardsupporttjänst från Microsoft. Exempelskriptet tillhandahålls i SIN FORM utan några som helst garantier. Vidare frånsäger sig Microsoft alla underförstådda garantier, inklusive, utan begränsning, alla underförstådda garantier om säljbarhet eller lämplighet för ett visst ändamål. Hela risken i samband med användningen av eller prestandan hos exempelskriptet och dokumentationen ligger kvar hos dig. Under inga omständigheter ska Microsoft, dess upphovspersoner eller någon annan som är involverad i skapandet, produktionen eller leveransen av skripten hållas ansvariga för någon som helst skada (inklusive, men inte begränsat till, skador för vinstförlust, driftavbrott, förlust av affärsinformation eller annan ekonomisk skada) som uppstår till följd av användning eller oförmåga att använda exempelskripten eller dokumentationen, även om Microsoft har fått information om att sådana skador kan uppstå.

## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a>Steg 1: Kör skriptet för att få en lista med mappar för en postlåda eller webbplats

Skriptet som du kör i det här första steget returnerar en lista över postlådemappar eller e SharePoint- OneDrive för företag postmappar och motsvarande mapp-ID eller mappsökväg för varje mapp. När du kör det här skriptet uppmanas du att ange följande information.

- **E-postadress eller webbplats-URL:** Skriv en e-postadress till den som är dokumenterade för att returnera en lista Exchange postlådemappar och mapp-ID. Eller skriv URL:en för en SharePoint webbplats eller en OneDrive för företag för att returnera en lista med sökvägar för den angivna webbplatsen. Här är några exempel:

  - **Exchange**: stacig@contoso.onmicrosoft <spam> <spam> .com

  - **SharePoint:** https <span>://</span>contoso.sharepoint.com/sites/marketing

  - **OneDrive för företag**: https <span>://</span>contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com

- **Dina användarautentiseringsuppgifter:** Skriptet använder dina autentiseringsuppgifter för att ansluta till Exchange Online PowerShell eller Säkerhets- & PowerShell med modern autentisering. Som tidigare förklarats måste du ha rätt behörighet för att kunna köra det här skriptet.

Så här visar du en lista över postlådemappar eller webbplatsdokumentlänknamn (sökväg):

1. Spara följande text i en Windows PowerShell skriptfil med hjälp av ett filnamnssuffix .ps1; till exempel `GetFolderSearchParameters.ps1` .

   ```powershell
   #########################################################################################################
   # This PowerShell script will prompt you for:                                #
   #    * Admin credentials for a user who can run the Get-MailboxFolderStatistics cmdlet in Exchange    #
   #      Online and who is an eDiscovery Manager in the Security & Compliance Center.            #
   # The script will then:                                            #
   #    * If an email address is supplied: list the folders for the target mailbox.            #
   #    * If a SharePoint or OneDrive for Business site is supplied: list the documentlinks (folder paths) #
   #    * for the site.                                                                                    #
   #    * In both cases, the script supplies the correct search properties (folderid: or documentlink:)    #
   #      appended to the folder ID or documentlink to use in a Content Search.                #
   # Notes:                                                #
   #    * For SharePoint and OneDrive for Business, the paths are searched recursively; this means the     #
   #      the current folder and all sub-folders are searched.                        #
   #    * For Exchange, only the specified folder will be searched; this means sub-folders in the folder    #
   #      will not be searched.  To search sub-folders, you need to use the specify the folder ID for    #
   #      each sub-folder that you want to search.                                #
   #    * For Exchange, only folders in the user's primary mailbox will be returned by the script.        #
   #########################################################################################################
   # Collect the target email address or SharePoint Url
   $addressOrSite = Read-Host "Enter an email address or a URL for a SharePoint or OneDrive for Business site"
   # Authenticate with Exchange Online and the Security & Compliance Center (Exchange Online Protection - EOP)
   if ($addressOrSite.IndexOf("@") -ige 0)
   {
      # List the folder Ids for the target mailbox
      $emailAddress = $addressOrSite
      # Connect to Exchange Online PowerShell
      if (!$ExoSession)
      {
          Import-Module ExchangeOnlineManagement
          Connect-ExchangeOnline
      }
      $folderQueries = @()
      $folderStatistics = Get-MailboxFolderStatistics $emailAddress
      foreach ($folderStatistic in $folderStatistics)
      {
          $folderId = $folderStatistic.FolderId;
          $folderPath = $folderStatistic.FolderPath;
          $encoding= [System.Text.Encoding]::GetEncoding("us-ascii")
          $nibbler= $encoding.GetBytes("0123456789ABCDEF");
          $folderIdBytes = [Convert]::FromBase64String($folderId);
          $indexIdBytes = New-Object byte[] 48;
          $indexIdIdx=0;
          $folderIdBytes | select -skip 23 -First 24 | %{$indexIdBytes[$indexIdIdx++]=$nibbler[$_ -shr 4];$indexIdBytes[$indexIdIdx++]=$nibbler[$_ -band 0xF]}
          $folderQuery = "folderid:$($encoding.GetString($indexIdBytes))";
          $folderStat = New-Object PSObject
          Add-Member -InputObject $folderStat -MemberType NoteProperty -Name FolderPath -Value $folderPath
          Add-Member -InputObject $folderStat -MemberType NoteProperty -Name FolderQuery -Value $folderQuery
          $folderQueries += $folderStat
      }
      Write-Host "-----Exchange Folders-----"
      $folderQueries |ft
   }
   elseif ($addressOrSite.IndexOf("http") -ige 0)
   {
      $searchName = "SPFoldersSearch"
      $searchActionName = "SPFoldersSearch_Preview"
      # List the folders for the SharePoint or OneDrive for Business Site
      $siteUrl = $addressOrSite
      # Connect to Security & Compliance Center PowerShell
      if (!$SccSession)
      {
          Import-Module ExchangeOnlineManagement
          Connect-IPPSSession
      }
      # Clean-up, if the script was aborted, the search we created might not have been deleted.  Try to do so now.
      Remove-ComplianceSearch $searchName -Confirm:$false -ErrorAction 'SilentlyContinue'
      # Create a Content Search against the SharePoint Site or OneDrive for Business site and only search for folders; wait for the search to complete
      $complianceSearch = New-ComplianceSearch -Name $searchName -ContentMatchQuery "contenttype:folder" -SharePointLocation $siteUrl
      Start-ComplianceSearch $searchName
      do{
          Write-host "Waiting for search to complete..."
          Start-Sleep -s 5
          $complianceSearch = Get-ComplianceSearch $searchName
      }while ($complianceSearch.Status -ne 'Completed')
      if ($complianceSearch.Items -gt 0)
      {
          # Create a Compliance Search Action and wait for it to complete. The folders will be listed in the .Results parameter
          $complianceSearchAction = New-ComplianceSearchAction -SearchName $searchName -Preview
          do
          {
              Write-host "Waiting for search action to complete..."
              Start-Sleep -s 5
              $complianceSearchAction = Get-ComplianceSearchAction $searchActionName
          }while ($complianceSearchAction.Status -ne 'Completed')
          # Get the results and print out the folders
          $results = $complianceSearchAction.Results
          $matches = Select-String "Data Link:.+[,}]" -Input $results -AllMatches
          foreach ($match in $matches.Matches)
          {
              $rawUrl = $match.Value
              $rawUrl = $rawUrl -replace "Data Link: " -replace "," -replace "}"
              Write-Host "DocumentLink:""$rawUrl"""
          }
      }
      else
      {
          Write-Host "No folders were found for $siteUrl"
      }
      Remove-ComplianceSearch $searchName -Confirm:$false -ErrorAction 'SilentlyContinue'
   }
   else
   {
      Write-Error "Couldn't recognize $addressOrSite as an email address or a site URL"
   }
   ```

2. Öppna den lokala datorn Windows PowerShell gå till mappen där du sparade skriptet.

3. Kör skriptet. till exempel:

   ```powershell
   .\GetFolderSearchParameters.ps1
   ```

4. Ange den information som skriptet uppmanar dig att ange.

    Skriptet visar en lista över postlådemappar eller webbplatsmappar för den angivna användaren. Lämna det här fönstret öppet så att du kan kopiera ett mapp-ID eller ett namn på dokumentlänken och klistra in det i en sökfråga i steg 2.

    > [!TIP]
    > I stället för att visa en lista med mappar på datorskärmen kan du dirigera skriptets utdata till en textfil igen. Den här filen sparas i mappen där skriptet finns. Om du till exempel vill omdirigera skriptutdata till en textfil kör du följande kommando i steg 3: Sedan kan du kopiera ett mapp-ID eller en dokumentlänk från filen för användning i en  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` sökfråga.

### <a name="script-output-for-mailbox-folders"></a>Skriptresultat för postlådemappar

Om du får mapp-ID:n för postlådor ansluter skriptet till Exchange Online PowerShell, kör cmdleten **Get-MailboxFolderStatisics** och visar sedan listan med mappar från den angivna postlådan. För varje mapp i postlådan visar skriptet namnet på mappen i kolumnen **FolderPath** och mapp-ID:t i **kolumnen Mappfråga.** Skriptet lägger dessutom till prefixet **folderId** (som är namnet på postlådeeegenskapen) i mapp-ID: t. Eftersom **egenskapen folderid** är en sökbar egenskap använder du i en sökfråga i  `folderid:<folderid>` steg 2 för att söka i mappen. Skriptet visar högst 100 postlådemappar.

> [!IMPORTANT]
> Skriptet i den här artikeln innehåller kodningslogik som konverterar mapp-ID-värdena med 64 tecken som returneras av **Get-MailboxFolderStatistics** till samma format på 48 tecken som indexeras för sökning. Om du bara kör cmdleten **Get-MailboxFolderStatistics** i PowerShell för att hämta ett mapp-ID (i stället för att köra skriptet i den här artikeln), misslyckas en sökfråga som använder det mapp-ID-värdet. Du måste köra skriptet för att få korrekt formaterade mapp-ID:n som kan användas i en innehållssökning.

Här är ett exempel på resultatet som returneras av skriptet för postlådemappar.

![Exempel på listan över postlådemappar och mapp-ID:er som returneras av skriptet](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)

I exemplet i steg 2 visas den fråga som används för att söka i undermappen Rensningar i användarens Återställningsbara objekt-mapp.

### <a name="script-output-for-site-folders"></a>Skriptresultat för webbplatsmappar

Om du får sökvägen  till dokumentlänkegenskapen från SharePoint- eller OneDrive för företag-webbplatser ansluter skriptet till Security & Compliance PowerShell, skapar en ny innehållssökning som söker efter mappar på webbplatsen och visar sedan en lista över de mappar som finns på den angivna webbplatsen. Skriptet visar namnet på varje mapp och lägger till prefixet för **dokumentlänken till** mappens URL. Eftersom egenskapen **documentlink** är en sökbar egenskap använder du property:value pair i en sökfråga i `documentlink:<path>` steg 2 för att söka i mappen. Skriptet visar högst 200 webbplatsmappar. Om det finns fler än 200 webbplatsmappar visas de senaste.

Här är ett exempel på resultatet som returneras av skriptet för webbplatsmappar.

![Exempel på listan med dokumentlänknamn för webbplatsmappar som returneras av skriptet](../media/519e8347-7365-4067-af78-96c465dc3d15.png)

## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a>Steg 2: Använd ett mapp-ID eller en dokumentlänk för att utföra en riktad samling

När du har kört skriptet för att samla in en lista med mapp-ID eller dokumentlänkar för en viss användare går du till efterlevnadscentret för Microsoft 365 och skapar en ny innehållssökning för att söka efter en särskild mapp. Du använder värdeparet eller i sökfrågan som du konfigurerar i rutan Nyckelord för innehållssökning (eller som värde för parametern ContentMatchQuery om du använder `folderid:<folderid>` `documentlink:<path>` cmdleten **New-ComplianceSearch).**  Du kan kombinera egenskapen  `folderid`  `documentlink` eller med andra sökparametrar eller sökvillkor. Om du bara tar med egenskapen eller i frågan returneras alla objekt i den  `folderid`  `documentlink` angivna mappen.

1. Gå till <https://compliance.microsoft.com> och logga in med det konto och de autentiseringsuppgifter som du använde för att köra skriptet i steg 1.

2. I det vänstra fönstret i efterlevnadscentret klickar du på **Visa all**  >  **innehållssökning** och sedan på **Ny sökning.**

3. I rutan **Nyckelord** klistrar du in `folderid:<folderid>` det eller det värde som  `documentlink:<path>` returnerades av skriptet i steg 1.

    Frågan på följande skärmbild söker till exempel efter alla objekt i undermappen Rensningar i användarens Återställningsbara objekt-mapp (egenskapens värde för undermappen Rensningar visas på skärmbilden i `folderid` steg 1):

    ![Klistra in mappid eller dokumentlänk i nyckelordsrutan för sökfrågan](../media/FolderIDSearchQuery.png)

4. Under **Platser väljer** du Specifika platser **och** klickar sedan på **Ändra**.

5. Gör något av följande, beroende på om du söker i en postlådemapp eller i en webbplatsmapp:

    - Bredvid **e Exchange klickar** du på Välj **användare,** grupper eller team och lägger sedan till samma postlåda som du angav när du körde skriptet i steg 1.

      Eller

    - Bredvid SharePoint **klickar du**  på Välj webbplatser och lägger sedan till samma webbadress som du angav när du körde skriptet i steg 1.

6. När du har sparat innehållsplatsen som ska sökas klickar du på **Spara**&  kör , anger ett namn på Innehållssökning och klickar sedan på Spara för att starta sökningen i den riktade samlingen.

### <a name="examples-of-search-queries-for-targeted-collections"></a>Exempel på sökfrågor för riktade samlingar

Här är några exempel på hur du kan  `folderid` använda egenskaperna och i en  `documentlink` sökfråga för att utföra en riktad samling. Platshållare används för och  `folderid:<folderid>` för  `documentlink:<path>` att spara utrymme.

- I det här exemplet genomsöks tre olika postlådemappar. Du kan använda liknande frågesyntax för att söka i de dolda mapparna i en användares Återställningsbara objekt-mapp.

  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- I det här exemplet genomsöks en postlådemapp efter objekt som innehåller en exakt fras.

  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- I det här exemplet genomsöks en webbplatsmapp (och eventuella undermappar) efter dokument som innehåller bokstäverna "SEKRETESS" i rubriken.

  ```powershell
  documentlink:<path> AND filename:nda
  ```

- I det här exemplet genomsöks en webbplatsmapp (och eventuella undermappar) efter dokument som har ändrats inom ett datumintervall.

  ```powershell
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a>Mer information

Tänk på följande när du använder skriptet i den här artikeln för att utföra riktade samlingar.

- Skriptet tar inte bort några mappar från resultatet. Vissa mappar som visas i resultatet kanske inte går att söka efter (eller returnera noll objekt) eftersom de innehåller systemgenererat innehåll eller eftersom de bara innehåller undermappar och inte postlådeobjekt.

- Det här skriptet returnerar bara mappinformation för användarens primära postlåda. Den returnerar inte information om mappar i användarens arkivpostlåda. Om du vill returnera information om mappar i användarens arkivpostlåda kan du redigera skriptet. Det gör du genom att ändra raden `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` till, spara och köra det redigerade skriptet. Den här ändringen returnerar mapp-ID:erna för mappar och undermappar i användarens arkivpostlåda. Om du vill söka i hela arkivpostlådan kan du ansluta alla egenskapsnamn för mapp-ID:värdepar med `OR` en operator i en sökfråga.

- När du söker i postlådemappar genomsöks endast den angivna mappen (identifieras med dess egenskap), undermappar `folderid` genomsöks inte. Om du vill söka i undermappar måste du använda mapp-ID:t för den undermapp som du vill söka i.

- När du söker i webbplatsmappar genomsöks mappen (identifieras med `documentlink` egenskapen) och alla undermappar.

- När du exporterar resultatet av en sökning där du endast angav egenskapen i sökfrågan kan du välja det första exportalternativet, "Alla objekt, utom sådana som har ett okänt format, krypteras eller inte indexeras av andra `folderid` orsaker". Alla objekt i mappen exporteras alltid oavsett indexeringsstatus eftersom mapp-ID:t alltid indexeras.
