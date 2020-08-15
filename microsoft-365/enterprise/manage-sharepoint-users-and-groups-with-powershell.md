---
title: Hantera SharePoint Online-användare och-grupper med PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
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
description: I den här artikeln lär du dig hur du använder PowerShell för Microsoft 365 för att hantera SharePoint Online-användare,-grupper och-webbplatser.
ms.openlocfilehash: 5252ecc950e5f26d6ad60cd871910a67bf50f187
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694775"
---
# <a name="manage-sharepoint-online-users-and-groups-with-powershell"></a>Hantera SharePoint Online-användare och-grupper med PowerShell

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

Om du är SharePoint Online-administratör och arbetar med stora listor över användar konton eller grupper och är ett enklare sätt att hantera dem kan du använda PowerShell för Microsoft 365. 

Innan du börjar måste du ansluta till SharePoint Online med procedurerna i det här avsnittet. Anvisningar finns i [ansluta till SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

## <a name="get-a-list-of-sites-groups-and-users"></a>Få en lista över webbplatser, grupper och användare

Innan vi börjar hantera användare och grupper måste du hämta listor över webbplatser, grupper och användare. Du kan sedan använda den här informationen för att arbeta genom exemplet i den här artikeln.

Få en lista över webbplatsernas webbplatser med det här kommandot:

```powershell
Get-SPOSite
```

Få en lista över gruppens grupper med det här kommandot:

```powershell
Get-SPOSite | ForEach {Get-SPOSiteGroup -Site $_.Url} | Format-Table
```

Få en lista över användare i klient organisationen med det här kommandot:

```powershell
Get-SPOSite | ForEach {Get-SPOUser -Site $_.Url}
```

## <a name="add-a-user-to-the-site-collection-administrators-group"></a>Lägga till en användare i gruppen Administratörer för webbplats samlingar

Du använder `Set-SPOUser` cmdleten för att lägga till en användare i listan över administratörer för webbplats samlingar i en webbplats samling.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
 ```

Om du vill använda dessa kommandon ersätter du allt inom citat tecknen, inklusive < och > tecken, med rätt namn.

Denna uppsättning kommandon lägger till exempel till Opal Castillo (användar namn opalc) i listan över administratörer för webbplats samlingar på den ContosoTest webbplats samlingen i Contosos innehavare:

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "opalc"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
```

Du kan kopiera och klistra in dessa kommandon i anteckningar, ändra variabel värden för $tenant, $site och $user till faktiska värden från din miljö och sedan klistra in det i ditt SharePoint Online Management Shell-fönster för att köra dem.

## <a name="add-a-user-to-other-site-collection-groups"></a>Lägga till en användare i andra webbplats samlings grupper

I den här uppgiften ska vi använda `Add-SPOUser` cmdlet för att lägga till en användare i en SharePoint-grupp i en webbplats samling.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site

```

Låt oss till exempel lägga till Glen Rife (användar namn glenr) i gruppen granskare på den ContosoTest webbplats samlingen i Contosos innehavare:

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "glenr"
$group = "Auditors"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="create-a-site-collection-group"></a>Skapa en grupp för webbplats samlingar

Du använder `New-SPOSiteGroup` cmdleten för att skapa en ny SharePoint-grupp och lägga till den i en webbplats samling.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$group = "<group name name, such as Auditors>"
$level = "<permission level, such as View Only>"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```
Grupp egenskaper, till exempel behörighets nivåer, kan uppdateras senare med hjälp av `Set-SPOSiteGroup` cmdleten.

Låt oss till exempel lägga till Grans kar gruppen med endast behörighet till contosotest-webbplats samlingen i Contosos innehavare:

```powershell
$tenant = "contoso"
$site = "contosotest"
$group = "Auditors"
$level = "View Only"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="remove-users-from-a-group"></a>Ta bort användare från en grupp

Ibland måste du ta bort en användare från en eller flera webbplatser. Den anställde kan flyttas från en division till en annan eller lämnar företaget. Du kan göra detta för en anställd i användar gränssnittet, men det är inte lätt att ringa när du måste flytta en hel division från en webbplats till en annan.

Med SharePoint Online Management Shell-och CSV-filerna är detta snabbt och enkelt. Du använder Windows PowerShell för att ta bort en användare från en säkerhets grupp för en webbplats samling. Då använder du en CSV-fil och tar bort många användare från olika webbplatser. 

Vi kommer att använda cmdleten Remove-makar för att ta bort en enda Microsoft 365-användare från en webbplats samlings grupp så att vi kan se kommandosyntaxen. Så här ser syntaxen ut:

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```
Låt oss till exempel ta bort Bobby Overby från gruppen granskare i webbplats samlingen i contosotest-webbplats samlingen i innehavet contoso:

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "bobbyo"
$group = "Auditors"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

Anta att vi ville ta bort Bobby från alla grupper han för närvarande är i. Så här gör vi det:

```powershell
$tenant = "contoso"
$user = "bobbyo"
Get-SPOSite | ForEach {Get-SPOSiteGroup –Site $_.Url} | ForEach {Remove-SPOUser -LoginName $user@$tenant.com -Site &_.Url}
```

> [!WARNING]
> Det här är bara ett exempel. Du bör inte köra det här kommandot om du verkligen måste ta bort en användare från varje grupp, till exempel om användaren lämnar företaget.

## <a name="automate-management-of-large-lists-of-users-and-groups"></a>Automatisera hanteringen av stora listor med användare och grupper

Om du vill lägga till ett stort antal konton på SharePoint-webbplatser och ge dem behörighet kan du använda administrations centret för Microsoft 365, enskilda PowerShell-kommandon eller PowerShell en CSV-fil. De här valen är att CSV-filen är det snabbaste sättet att automatisera den här uppgiften.

Den grundläggande processen är att skapa en CSV-fil som innehåller rubriker (kolumner) som motsvarar de parametrar som Windows PowerShell-skriptet behöver. Du kan enkelt skapa en sådan lista i Excel och sedan exportera den som en CSV-fil. Sedan använder du ett Windows PowerShell-skript för att iterera genom poster (rader) i CSV-filen och lägger till användare i grupper och grupper på webbplatser. 

Låt oss exempelvis skapa en CSV-fil för att definiera en grupp med webbplats samlingar, grupper och behörigheter. Nästa steg är att skapa en CSV-fil för att fylla grupper med användare. Slutligen skapas och körs ett enkelt Windows PowerShell-skript som skapar och fyller i grupper.

Den första CSV-filen lägger till en eller flera grupper i en eller flera webbplats samlingar och har den här strukturen:

Meddelande

```powershell
Site,Group,PermissionLevels
```

Elementet

```powershell
https://tenant.sharepoint.com/sites/site,group,level
```

Här är en exempel fil:

```powershell
Site,Group,PermissionLevels
https://contoso.sharepoint.com/sites/contosotest,Contoso Project Leads,Full Control
https://contoso.sharepoint.com/sites/contosotest,Contoso Auditors,View Only
https://contoso.sharepoint.com/sites/contosotest,Contoso Designers,Design
https://contoso.sharepoint.com/sites/TeamSite01,XT1000 Team Leads,Full Control
https://contoso.sharepoint.com/sites/TeamSite01,XT1000 Advisors,Edit
https://contoso.sharepoint.com/sites/Blog01,Contoso Blog Designers,Design
https://contoso.sharepoint.com/sites/Blog01,Contoso Blog Editors,Edit
https://contoso.sharepoint.com/sites/Project01,Project Alpha Approvers,Full Control
```

Den andra CSV-filen lägger till en eller flera användare i en eller flera grupper och har den här strukturen:

Meddelande

```powershell
Group,LoginName,Site
```

Elementet

```powershell
group,login,https://tenant.sharepoint.com/sites/site
```

Här är en exempel fil:

```powershell
Group,LoginName,Site
Contoso Project Leads,bobbyo@contoso.com,https://contoso.sharepoint.com/sites/contosotest
Contoso Auditors,allieb@contoso.com,https://contoso.sharepoint.com/sites/contosotest
Contoso Designers,bonniek@contoso.com,https://contoso.sharepoint.com/sites/contosotest
XT1000 Team Leads,dorenap@contoso.com,https://contoso.sharepoint.com/sites/TeamSite01
XT1000 Advisors,garthf@contoso.com,https://contoso.sharepoint.com/sites/TeamSite01
Contoso Blog Designers,janets@contoso.com,https://contoso.sharepoint.com/sites/Blog01
Contoso Blog Editors,opalc@contoso.com,https://contoso.sharepoint.com/sites/Blog01
Project Alpha Approvers,robinc@contoso.com,https://contoso.sharepoint.com/sites/Project01
```

För nästa steg måste du ha de två CSV-filerna sparade på din enhet. Här är exempel kommandon som använder båda CSV-filer och för att lägga till behörigheter och grupp medlemskap:

```powershell
Import-Csv C:\O365Admin\GroupsAndPermissions.csv | ForEach {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\O365Admin\Users.csv | ForEach {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```

Skriptet importerar CSV-filens innehåll och använder värdena i kolumnerna för att fylla i parametrarna för kommandona **New-SPOSiteGroup** och **Add-makeer** . I vårt exempel sparar vi denna till theO365Admin-mappen på enhet C, men du kan spara den var du vill.

Låt oss ta bort många personer för flera grupper på olika webbplatser med samma CSV-fil. Här är ett exempel kommando:

```powershell
Import-Csv C:\O365Admin\Users.csv | ForEach {Remove-SPOUser -LoginName $_.LoginName -Site $_.Site -Group $_.Group}
```

## <a name="generate-user-reports"></a>Skapa användar rapporter

Du kanske vill få en enkel rapport för några webbplatser och visa användarna för dessa webbplatser, deras behörighets nivå och andra egenskaper. Så här ser syntaxen ut:

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | select * | Format-table -Wrap -AutoSize | Out-File c\UsersReport.txt -Force -Width 360 -Append
```

Detta hämtar data för dessa tre webbplatser och skriver dem till en textfil på din lokala enhet. Observera att parametern-append lägger till nytt innehåll i en befintlig fil.

Låt oss till exempel köra en rapport om ContosoTest, TeamSite01 och Project01 för contoso1-klient organisationen:

```powershell
$tenant = "contoso"
$site = "contosotest"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "TeamSite01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site |Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "Project01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

Observera att vi bara ändra **$Site** variabel. Variabeln **$Tenant** behåller sitt värde genom alla tre kommandona för kommandot.

Men vad gör du om du vill göra det för varje webbplats? Du kan göra detta utan att behöva skriva alla webbplatser med det här kommandot:

```powershell
Get-SPOSite | ForEach {Get-SPOUser –Site $_.Url} | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

Den här rapporten är ganska enkel och du kan lägga till fler koder för att skapa mer specifika rapporter som innehåller mer detaljerad information. Men det bör ge dig en uppfattning om hur du använder SharePoint Online Management Shell för att hantera användare i SharePoint Online-miljön.
   
## <a name="see-also"></a>Se även

[Ansluta till SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[Hantera SharePoint Online med PowerShell](create-sharepoint-sites-and-add-users-with-powershell.md)

[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Komma igång med PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)
