---
title: Hantera SharePoint Online-användare och grupper med PowerShell
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
description: I den här artikeln får du lära dig hur du använder PowerShell för Microsoft 365 för att hantera användare, grupper och webbplatser i SharePoint Online.
ms.openlocfilehash: cc977355f1182b18d2f2e90b573683ed69299c1c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916732"
---
# <a name="manage-sharepoint-online-users-and-groups-with-powershell"></a>Hantera SharePoint Online-användare och grupper med PowerShell

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Om du är SharePoint Online-administratör och arbetar med stora listor med användarkonton eller grupper och vill ha ett enklare sätt att hantera dem kan du använda PowerShell för Microsoft 365. 

Innan du börjar måste du ansluta till SharePoint Online för procedurerna i det här avsnittet. Anvisningar finns i [Ansluta till SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

## <a name="get-a-list-of-sites-groups-and-users"></a>Få en lista över webbplatser, grupper och användare

Innan vi börjar hantera användare och grupper behöver du listor över dina webbplatser, grupper och användare. Du kan sedan använda den här informationen för att gå igenom exemplet i den här artikeln.

Hämta en lista över webbplatserna i klientorganisationen med det här kommandot:

```powershell
Get-SPOSite
```

Hämta en lista över grupperna i klientorganisationen med det här kommandot:

```powershell
Get-SPOSite | ForEach {Get-SPOSiteGroup -Site $_.Url} | Format-Table
```

Hämta en lista över användarna i klientorganisationen med det här kommandot:

```powershell
Get-SPOSite | ForEach {Get-SPOUser -Site $_.Url}
```

## <a name="add-a-user-to-the-site-collection-administrators-group"></a>Lägga till en användare i gruppen Administratörer för webbplatssamlingar

Du använder `Set-SPOUser` cmdleten för att lägga till en användare i listan med administratörer för webbplatssamlingar på en webbplatssamling.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
 ```

Om du vill använda dessa kommandon ersätter du allt inom citattecken, < och >, med rätt namn.

I den här uppsättningen kommandon läggs till till Till Exempel Castkommando (användarnamn och c) i listan över administratörer för webbplatssamlingar på ContosoTest-webbplatssamlingen i Contoso-innehavare:

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "opalc"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
```

Du kan kopiera och klistra in kommandona i Anteckningar, ändra variabelvärdena för $tenant, $site och $user till faktiska värden från din miljö och sedan klistra in dem i fönstret SharePoint Online Management Shell för att köra dem.

## <a name="add-a-user-to-other-site-collection-groups"></a>Lägga till en användare i andra webbplatssamlingsgrupper

I den här uppgiften använder vi `Add-SPOUser` cmdleten för att lägga till en användare i en SharePoint-grupp i en webbplatssamling.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site

```

Vi kan till exempel lägga till Mikael Berg (användarnamnsr) i gruppen Granskare på ContosoTest-webbplatssamlingen i contoso-innehavare:

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "glenr"
$group = "Auditors"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="create-a-site-collection-group"></a>Skapa en webbplatssamlingsgrupp

Du använder `New-SPOSiteGroup` cmdleten för att skapa en ny SharePoint-grupp och lägga till den i en webbplatssamling.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$group = "<group name name, such as Auditors>"
$level = "<permission level, such as View Only>"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```
Gruppegenskaper, till exempel behörighetsnivåer, kan uppdateras senare med hjälp av `Set-SPOSiteGroup` cmdleten.

Vi lägger till exempel till gruppen Granskare med behörigheten Endast visa för den contosotesta webbplatssamlingen i contoso-innehavare:

```powershell
$tenant = "contoso"
$site = "contosotest"
$group = "Auditors"
$level = "View Only"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="remove-users-from-a-group"></a>Ta bort användare från en grupp

Ibland behöver du ta bort en användare från en webbplats eller till och med alla webbplatser. Den anställda kanske flyttar från en avdelning till en annan eller lämnar företaget. Det kan du göra enkelt för en anställd i användargränssnittet, men detta görs inte enkelt när du behöver flytta en fullständig avdelning från en webbplats till en annan.

Men med hjälp av SharePoint Online Management Shell och CSV-filer går det snabbt och enkelt. I den här uppgiften använder du Windows PowerShell för att ta bort en användare från en säkerhetsgrupp för en webbplatssamling. Sedan använder du en CSV-fil och tar bort många användare från olika webbplatser. 

Vi använder cmdleten Remove-SPOUser för att ta bort en enskild Microsoft 365-användare från en webbplatssamlingsgrupp så att vi kan se kommandosyntaxen. Så här ser syntaxen ut:

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```
Vi kan till exempel ta bort Johan Överby från webbplatssamlingen Granskare-gruppen i den contosotesta webbplatssamlingen i contoso-innehavare:

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "bobbyo"
$group = "Auditors"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

Anta att vi vill ta bort Johan från alla grupper han finns i för närvarande. Så här skulle vi göra:

```powershell
$tenant = "contoso"
$user = "bobbyo"
Get-SPOSite | ForEach {Get-SPOSiteGroup –Site $_.Url} | ForEach {Remove-SPOUser -LoginName $user@$tenant.com -Site &_.Url}
```

> [!WARNING]
> Det här är bara ett exempel. Du bör inte köra det här kommandot såvida du inte verkligen måste ta bort en användare från varje grupp, till exempel om användaren lämnar företaget.

## <a name="automate-management-of-large-lists-of-users-and-groups"></a>Automatisera hanteringen av stora listor med användare och grupper

Om du vill lägga till ett stort antal konton till SharePoint-webbplatser och ge dem behörigheter kan du använda administrationscentret för Microsoft 365, enskilda PowerShell-kommandon eller PowerShell en CSV-fil. Av de här alternativen är CSV-filen det snabbaste sättet att automatisera den här uppgiften.

Den grundläggande processen är att skapa en CSV-fil med rubriker (kolumner) som motsvarar de parametrar som Windows PowerShell-skriptet behöver. Du kan enkelt skapa en sådan lista i Excel och sedan exportera den som en CSV-fil. Sedan använder du ett Windows PowerShell-skript för att iterera genom poster (rader) i CSV-filen och lägga till användare i grupper och grupper på webbplatserna. 

Låt oss till exempel skapa en CSV-fil för att definiera en grupp med webbplatssamlingar, grupper och behörigheter. Sedan skapar vi en CSV-fil för att fylla grupperna med användare. Slutligen skapar och kör vi ett enkelt Windows PowerShell-skript som skapar och fyller i grupperna.

Den första CSV-filen lägger till en eller flera grupper i en eller flera webbplatssamlingar och har följande struktur:

Sidhuvud:

```powershell
Site,Group,PermissionLevels
```

Artikel:

```powershell
https://tenant.sharepoint.com/sites/site,group,level
```

Här är en exempelfil:

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

Den andra CSV-filen lägger till en eller flera användare i en eller flera grupper och kommer att ha följande struktur:

Sidhuvud:

```powershell
Group,LoginName,Site
```

Artikel:

```powershell
group,login,https://tenant.sharepoint.com/sites/site
```

Här är en exempelfil:

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

I nästa steg måste du ha de två CSV-filerna sparade på enheten. Här är exempelkommandon som använder både CSV-filer och för att lägga till behörigheter och gruppmedlemskap:

```powershell
Import-Csv C:\O365Admin\GroupsAndPermissions.csv | ForEach {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\O365Admin\Users.csv | ForEach {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```

Skriptet importerar CSV-filens innehåll och använder värdena i kolumnerna för att fylla i parametrarna för **kommandona New-SPOSiteGroup** och **Add-SPOUser.** I vårt exempel sparar vi den i mappenO365Admin på enhet C, men du kan spara den var du vill.

Nu tar vi bort flera personer för flera grupper på olika webbplatser med hjälp av samma CSV-fil. Här är ett exempelkommando:

```powershell
Import-Csv C:\O365Admin\Users.csv | ForEach {Remove-SPOUser -LoginName $_.LoginName -Site $_.Site -Group $_.Group}
```

## <a name="generate-user-reports"></a>Skapa användarrapporter

Du kanske vill få en enkel rapport för några webbplatser och visa användarna för dessa webbplatser, deras behörighetsnivå och andra egenskaper. Så här ser syntaxen ut:

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | select * | Format-table -Wrap -AutoSize | Out-File c\UsersReport.txt -Force -Width 360 -Append
```

Då hämtar du data för dessa tre webbplatser och skriver dem till en textfil på din lokala enhet. Observera att parametern Lägg till lägger till nytt innehåll i en befintlig fil.

Låt oss till exempel köra en rapport på webbplatserna ContosoTest, TeamSite01 och Project01 för Contoso1-klientorganisationen:

```powershell
$tenant = "contoso"
$site = "contosotest"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "TeamSite01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site |Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "Project01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

Observera att vi var tvungna att endast ändra **$site** variabeln. Variabel$ **$tenant** behåller sitt värde genom alla tre körningarna av kommandot.

Men hur gör du om du vill göra det här för varje webbplats? Du kan göra det här utan att behöva skriva alla dessa webbplatser med hjälp av det här kommandot:

```powershell
Get-SPOSite | ForEach {Get-SPOUser –Site $_.Url} | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

Den här rapporten är ganska enkel och du kan lägga till mer kod för att skapa mer specifika rapporter eller rapporter som innehåller mer detaljerad information. Men det bör ge dig en uppfattning om hur Du använder SharePoint Online Management Shell för att hantera användare i SharePoint Online-miljön.
   
## <a name="see-also"></a>Se även

[Ansluta till SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[Hantera SharePoint Online med PowerShell](create-sharepoint-sites-and-add-users-with-powershell.md)

[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Börja använda PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)