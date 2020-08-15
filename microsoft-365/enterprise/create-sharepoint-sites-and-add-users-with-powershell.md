---
title: Skapa SharePoint Online-webbplatser och lägga till användare med PowerShell
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
description: 'Sammanfattning: skapa nya SharePoint Online-webbplatser med hjälp av PowerShell och Lägg sedan till användare och grupper på dessa webbplatser.'
ms.openlocfilehash: 4c4edbd68343f0eaf3a25a8c60a2af1e83b058b6
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694473"
---
# <a name="create-sharepoint-online-sites-and-add-users-with-powershell"></a>Skapa SharePoint Online-webbplatser och lägga till användare med PowerShell

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

När du använder PowerShell för Microsoft 365 för att skapa SharePoint Online-webbplatser och lägga till användare kan du snabbt och enkelt utföra uppgifter snabbare än i administrations centret för Microsoft 365. Du kan också utföra uppgifter som inte kan utföras i administrations centret för Microsoft 365. 

## <a name="connect-to-sharepoint-online"></a>Ansluta till SharePoint Online

Procedurerna i det här avsnittet kräver att du ansluter till SharePoint Online. Anvisningar finns i [ansluta till SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

## <a name="step-1-create-new-site-collections-using-powershell"></a>Steg 1: skapa nya webbplats samlingar med PowerShell

Skapa flera webbplatser med hjälp av PowerShell och en. csv-fil som du skapar med exempel koden som tillhandahålls och anteckningar. För den här proceduren ska du ersätta plats hållaren som visas inom parentes med din egen webbplats-och klient organisations information. Med den här processen kan du skapa en fil och köra ett enda PowerShell-kommando som använder den filen. Detta gör åtgärderna både repeterbara och portabla och eliminerar många, om inte alla, fel som kan komma att skriva långa kommandon till SharePoint Online Management Shell. Det finns två delar till den här proceduren. Först skapar du en CSV-fil och sedan hänvisar du till. csv-filen med PowerShell, som använder dess innehåll för att skapa webbplatserna.

PowerShell-cmdleten importerar. csv-filen och rör den till en loop inuti klammerparenteserna som läser den första raden i filen som kolumn rubriker. PowerShell-cmdleten upprepas sedan genom de återstående posterna, skapar en ny webbplats samling för varje post och tilldelar webbplats Samlingens egenskaper enligt kolumn rubrikerna.

### <a name="create-a-csv-file"></a>Skapa en. csv-fil

1. Öppna Anteckningar och klistra in följande textblock i det:<br/>

```powershell
Owner,StorageQuota,Url,ResourceQuota,Template,TimeZoneID,Name
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/TeamSite01,25,EHS#1,10,Contoso Team Site
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/Blog01,25,BLOG#0,10,Contoso Blog
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Project01,25,PROJECTSITE#0,10,Project Alpha
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Community01,25,COMMUNITY#0,10,Community Site
```
<br/>Här är *klient* organisationens namn och *ägare* är användar namnet på den klient organisation som du vill bevilja rollen som primär administratör för webbplats samlingen.<br/>(Du kan trycka på CTRL + H när du använder anteckningar för att snabbt byta ut.)<br/>

2. Spara filen på Skriv bordet som **SiteCollections.csv**.<br/>

> [!TIP]
> Innan du använder den här eller någon annan. csv-eller Windows PowerShell-skriptfil är det lämpligt att kontrol lera att det inte finns några främmande eller icke utskrivbara tecken. Öppna filen i Word och klicka på stycke ikonen i menyfliksområdet för att visa icke utskrivbara tecken. Det får inte finnas specialtecken som inte skrivs ut. Det får till exempel inte finnas några stycke tecken utöver den sista längst ned i filen.

### <a name="run-the-windows-powershell-command"></a>Köra kommandot Windows PowerShell

1. Skriv eller kopiera och klistra in följande kommando i Windows PowerShell-uppmaningen och tryck på RETUR:<br/>
```powershell
Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -ResourceQuota $_.ResourceQuota -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}
```
<br/>Där *Kantutjämna* är lika med ditt användar namn.<br/>

2. Vänta tills Windows PowerShell-uppmaningen visas igen. Det kan ta ett par minuter.<br/>

3. Skriv eller kopiera och klistra in följande cmdlet vid Windows PowerShell-uppmaningen och tryck på RETUR:<br/>

```powershell
Get-SPOSite -Detailed | Format-Table -AutoSize
```
<br/>

4. Observera de nya webbplats samlingarna i listan. Med exempel filen CSV kan du se följande webbplats samlingar: **TeamSite01**, **Blog01**, **Project01**och **Community01**

Det är det. Du har skapat flera webbplats samlingar med hjälp av CSV-filen som du skapade och ett enda Windows PowerShell-kommando. Nu är du redo att skapa och koppla användare till dessa webbplatser.

## <a name="step-2-add-users-and-groups"></a>Steg 2: Lägg till användare och grupper

Nu ska du skapa användare och lägga till dem i en webbplats samlings grupp. Sedan använder du en CSV-fil för att ladda upp nya grupper och användare.

Följande procedurer fortsätter att använda exemplen TeamSite01, Blog01, Project01 och Community01.

### <a name="create-csv-and-ps1-files"></a>Skapa. csv-och. ps1-filer

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
<br/>Där *klient* organisationen är lika med klient organisationens namn.<br/>

2. Spara filen på Skriv bordet som **GroupsAndPermissions.csv**.<br/>

3. Öppna en ny instans av anteckningar och klistra in följande textblock i det:<br/>

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
<br/>Där *klient* organisationen är lika med klient namnet och *användar* namnet är lika med användarens namn för en befintlig användare.<br/>

4. Spara filen på Skriv bordet som **Users.csv**.<br/>

5. Öppna en ny instans av anteckningar och klistra in följande textblock i det:<br/>

```powershell
Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\users\MyAlias\desktop\Users.csv | where {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```
<br/>Där Kantutjämna är lika med användar namnet på den användare som är inloggad för tillfället.<br/>

6. Spara filen på Skriv bordet som **UsersAndGroups.ps1**. Det här är en enkel Windows PowerShell-skript.

Nu är du redo att köra UsersAndGroup.ps1-skript för att lägga till användare och grupper i flera webbplats samlingar.

### <a name="run-usersandgroupsps1-script"></a>Kör UsersAndGroups.ps1 skript

1. Återvänd till SharePoint Online Management Shell.<br/>
2. Skriv eller kopiera och klistra in följande rad vid Windows PowerShell-uppmaningen och tryck på RETUR:<br/>
```powershell
Set-ExecutionPolicy Bypass
```
<br/>

3. När du uppmanas att bekräfta trycker du på **j**.<br/>

4. Skriv eller kopiera och klistra in följande i Windows PowerShell-uppmaningen och tryck på RETUR:<br/>

```powershell
c:\users\MyAlias\desktop\UsersAndGroups.ps1
```
<br/>Där *Kantutjämna* är lika med ditt användar namn.<br/>

5. Vänta tills uppmaningen återgår innan du fortsätter. Du ser först grupperna när de skapas. Då visas grupp listan upprepade gånger när användarna läggs till.

## <a name="see-also"></a>Se även

[Ansluta till SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[Hantera webbplats grupper för SharePoint Online med PowerShell](manage-sharepoint-site-groups-with-powershell.md)

[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Komma igång med PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)

