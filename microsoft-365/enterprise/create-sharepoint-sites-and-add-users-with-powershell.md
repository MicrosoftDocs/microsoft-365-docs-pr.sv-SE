---
title: Skapa SharePoint onlinewebbplatser och lägga till användare med PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- SPO_Content
- seo-marvel-apr2020
ms.assetid: d0d3877a-831f-4744-96b0-d8167f06cca2
description: Sammanfattning Använd PowerShell för att skapa nya SharePoint Online-webbplatser och sedan lägga till användare och grupper på de webbplatserna.
ms.openlocfilehash: eb6c2817c8760ca222da8a7c2b14cbfcda4eb4b8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907624"
---
# <a name="create-sharepoint-online-sites-and-add-users-with-powershell"></a>Skapa SharePoint onlinewebbplatser och lägga till användare med PowerShell

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

När du använder PowerShell för Microsoft 365 för att skapa SharePoint Online-webbplatser och lägga till användare kan du snabbt och upprepade gånger utföra uppgifter mycket snabbare än vad du kan Microsoft 365 administrationscentret. Du kan också utföra uppgifter som inte går att utföra Microsoft 365 administrationscentret. 

## <a name="connect-to-sharepoint-online"></a>Anslut till SharePoint Online

Procedurerna i det här avsnittet kräver att du ansluter till SharePoint Online. Instruktioner finns i [Anslut för SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

## <a name="step-1-create-new-site-collections-using-powershell"></a>Steg 1: Skapa nya webbplatssamlingar med PowerShell

Skapa flera webbplatser med PowerShell och en .csv fil som du skapar med den exempelkod som tillhandahålls och Anteckningar. För den här proceduren ersätter du platshållarinformationen som visas inom hakparenteser med din egen webbplats- och klientspecifik information. Med den här processen kan du skapa en enda fil och köra ett enda PowerShell-kommando som använder den filen. Det här gör att åtgärder som vidtas både går att upprepa och ta bort många, om inte alla, fel som kan komma från att skriva långa kommandon i SharePoint Online Management Shell. Den här proceduren har två delar. Först skapar du en .csv-fil och sedan refererar du till den .csv filen med PowerShell som använder innehållet för att skapa webbplatserna.

PowerShell-cmdleten importerar .csv-filen och rör den till en slinga inom klammerparenteser som läser den första raden i filen som kolumnrubriker. PowerShell-cmdleten itereras sedan genom de återstående posterna, skapar en ny webbplatssamling för varje post och tilldelar egenskaper för webbplatssamlingen enligt kolumnrubrikerna.

### <a name="create-a-csv-file"></a>Skapa en .csv fil

> [!NOTE]
> Resurskvotparametern fungerar bara på klassiska webbplatser. Om du använder den här parametern på en modern webbplats kan du få ett varningsmeddelande om att den har tagits bort. 

1. Öppna Anteckningar och klistra in följande textblock i det:<br/>

```powershell
Owner,StorageQuota,Url,ResourceQuota,Template,TimeZoneID,Name
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/TeamSite01,25,EHS#1,10,Contoso Team Site
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/Blog01,25,BLOG#0,10,Contoso Blog
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Project01,25,PROJECTSITE#0,10,Project Alpha
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Community01,25,COMMUNITY#0,10,Community Site
```
<br/>Där *klientorganisationen* är namnet på  klientorganisationen och ägare är användarnamnet för den användare i klientorganisationen som du vill tilldela rollen som primär administratör för webbplatssamlingen.<br/>(Du kan trycka på Ctrl+H när du Anteckningar massutfyllnad snabbare.)<br/>

2. Spara filen på skrivbordet som **SiteCollections.csv**.<br/>

> [!TIP]
> Innan du använder den här .csv- eller Windows PowerShell-skriptfilen är det bra att kontrollera att det inte finns några extra eller icke utskrivbara tecken. Öppna filen i Word och klicka på styckeikonen i menyfliksområdet för att visa icke utskrivbara tecken. Det ska inte finnas några extra icke utskrivbara tecken. Det ska till exempel inte finnas några stycketecken utöver den sista i slutet av filen.

### <a name="run-the-windows-powershell-command"></a>Kör kommandot Windows PowerShell kommando

1. Skriv eller kopiera Windows PowerShell klistra in följande kommando i kommandotolken och tryck på Retur:<br/>
```powershell
Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -ResourceQuota $_.ResourceQuota -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}
```
<br/>Där *MyAlias* är lika med ditt användaralias.<br/>

2. Vänta tills Windows PowerShell visas igen. Det kan ta några minuter.<br/>

3. Skriv eller Windows PowerShell och klistra in följande cmdlet i kommandotolken och tryck på Retur:<br/>

```powershell
Get-SPOSite -Detailed | Format-Table -AutoSize
```
<br/>

4. Observera de nya webbplatssamlingarna i listan. Med vår CSV-exempelfil ser du följande webbplatssamlingar: **TeamSite01,** **Blog01,** **Project01** och **Community01**

Nu är det allt. Du har skapat flera webbplatssamlingar med hjälp av .csv fil som du skapat och ett enda Windows PowerShell kommando. Nu är du redo att skapa och tilldela användare till webbplatserna.

## <a name="step-2-add-users-and-groups"></a>Steg 2: Lägg till användare och grupper

Nu ska du skapa användare och lägga till dem i en webbplatssamlingsgrupp. Sedan använder du en .csv för att massuppladda nya grupper och användare.

Följande procedurer fortsätter att använda exempelwebbplatserna TeamSite01, Blog01, Project01 och Community01.

### <a name="create-csv-and-ps1-files"></a>Skapa .csv och .ps1 filer

1. Öppna Anteckningar och klistra in följande textblock i det:<br/>

```powershell
Site,Group,PermissionLevels
https://tenant.sharepoint.com/sites/Community01,Contoso Project Leads,Full Control
https://tenant.sharepoint.com/sites/Community01,Contoso Auditors,View Only
https://tenant.sharepoint.com/sites/Community01,Contoso Designers,Design
https://tenant.sharepoint.com/sites/TeamSite01,XT1000 Team Leads,Full Control
https://tenant.sharepoint.com/sites/TeamSite01,XT1000 Advisors,Edit
https://tenant.sharepoint.com/sites/Blog01,Contoso Blog Designers,Design
https://tenant.sharepoint.com/sites/Blog01,Contoso Blog Editors,Edit
https://tenant.sharepoint.com/sites/Project01,Project Alpha Approvers,Full Control
```
<br/>Där *klientorganisationen* är lika med ditt klientnamn.<br/>

2. Spara filen på skrivbordet som **GroupsAndPermissions.csv**.<br/>

3. Öppna en ny instans Anteckningar och klistra in följande textblock i den:<br/>

```powershell
Group,LoginName,Site
Contoso Project Leads,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
Contoso Auditors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
Contoso Designers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
XT1000 Team Leads,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/TeamSite01
XT1000 Advisors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/TeamSite01
Contoso Blog Designers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Blog01
Contoso Blog Editors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Blog01
Project Alpha Approvers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Project01
```
<br/>Där *klientorganisationen* är lika med ditt *klientnamn och användarnamn* är lika med namnet på en befintlig användare.<br/>

4. Spara filen på skrivbordet som **Users.csv**.<br/>

5. Öppna en ny instans Anteckningar och klistra in följande textblock i den:<br/>

```powershell
Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\users\MyAlias\desktop\Users.csv | where {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```
<br/>Där MyAlias är lika med användarnamnet för den användare som är inloggad.<br/>

6. Spara filen på skrivbordet som **UsersAndGroups.ps1**. Det här är ett enkelt Windows PowerShell skript.

Nu kan du köra skriptet UsersAndGroup.ps1 lägga till användare och grupper i flera webbplatssamlingar.

### <a name="run-usersandgroupsps1-script"></a>Kör UsersAndGroups.ps1 skript

1. Gå tillbaka till SharePoint Online Management Shell.<br/>
2. Skriv eller Windows PowerShell klistra in följande rad i rutan och tryck på Retur:<br/>
```powershell
Set-ExecutionPolicy Bypass
```
<br/>

3. Tryck på Y när du ombeds **bekräfta.**<br/>

4. Skriv eller kopiera Windows PowerShell klistra in följande i kommandotolken och tryck på Retur:<br/>

```powershell
c:\users\MyAlias\desktop\UsersAndGroups.ps1
```
<br/>Där *MyAlias* är lika med ditt användarnamn.<br/>

5. Vänta tills du får frågan att återgå innan du fortsätter. Du ser först hur grupperna visas när de skapas. Sedan kommer du att se grupplistan upprepad när användare läggs till.

## <a name="see-also"></a>Se även

[Anslut till SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[Hantera SharePoint onlinewebbplatsgrupper med PowerShell](manage-sharepoint-site-groups-with-powershell.md)

[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Börja använda PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)