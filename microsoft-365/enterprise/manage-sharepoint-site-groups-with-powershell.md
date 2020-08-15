---
title: Hantera webbplats grupper för SharePoint Online med PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/17/2019
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
description: I den här artikeln hittar du anvisningar för hur du använder PowerShell för Microsoft 365 för att hantera webbplats grupper för SharePoint Online.
ms.openlocfilehash: fa9aff769ff84f8567c45b20c7b6c8a078b4a70c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694778"
---
# <a name="manage-sharepoint-online-site-groups-with-powershell"></a>Hantera webbplats grupper för SharePoint Online med PowerShell

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

Även om du kan använda administrations centret för Microsoft 365 kan du även använda PowerShell för Microsoft 365 för att hantera webbplats grupper för SharePoint Online.

## <a name="before-you-begin"></a>Innan du börjar

Procedurerna i den här artikeln kräver att du ansluter till SharePoint Online. Anvisningar finns i [ansluta till SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

## <a name="view-sharepoint-online-with-powershell-for-microsoft-365"></a>Visa SharePoint Online med PowerShell för Microsoft 365

Administrations centret för SharePoint Online har några lättanvända metoder för att hantera webbplats grupper. Anta till exempel att du vill titta på grupperna och grupp medlemmarna för `https://litwareinc.sharepoint.com/sites/finance` webbplatsen. Det här kan du göra:

1. I administrations centret för SharePoint klickar du på **aktiva webbplatser**och sedan på webbplatsen.
2. Klicka på ikonen **Inställningar** (i det övre högra hörnet på sidan) på webbplats sidan och klicka sedan på **webbplats behörigheter**.

Och upprepar sedan processen för nästa webbplats du vill titta på.

Om du vill ha en lista över grupperna med PowerShell för Microsoft 365 kan du använda följande kommandon:

```powershell
$siteURL = "https://litwareinc.sharepoint.com/sites/finance"
$x = Get-SPOSiteGroup -Site $siteURL
foreach ($y in $x)
    {
        Write-Host $y.Title -ForegroundColor "Yellow"
        Get-SPOSiteGroup -Site $siteURL -Group $y.Title | Select-Object -ExpandProperty Users
        Write-Host
    }
```

Det finns två sätt att köra den här kommando uppsättningen i kommando tolken i SharePoint Online Management Shell:

- Kopiera kommandona till anteckningar (eller en annan text redigerare), ändra värdet för **$siteURL** variabel, Välj kommandon och klistra sedan in dem i kommando tolken i SharePoint Online Management Shell. När du gör det stannar PowerShell vid en **>>** uppmaning. Kör kommandot genom att trycka på RETUR `foreach` .<br/>
- Kopiera kommandona till anteckningar (eller en annan text redigerare), ändra värdet för variabeln **$siteURL** och spara sedan den här text filen med ett namn och fil namns tillägget. ps1 i en lämplig mapp. Kör sedan skriptet från kommando tolken för SharePoint Online Management Shell genom att ange sökvägen och fil namnet. Här är ett exempel kommando:

```powershell
C:\Scripts\SiteGroupsAndUsers.ps1
```

I båda fallen ser du något som liknar det här:

![Webbplats grupper för SharePoint Online](../media/SPO-site-groups.png)

Det här är alla grupper som har skapats för webbplatsen `https://litwareinc.sharepoint.com/sites/finance` och alla användare som har tilldelats till gruppen. Grupp namnen är i gult för att hjälpa dig att dela upp grupp namn från deras medlemmar.

Det här är en kommando uppsättning som visar grupperna och alla grupp medlemskap för alla SharePoint Online-webbplatser.

```powershell
$x = Get-SPOSite
foreach ($y in $x)
    {
        Write-Host $y.Url -ForegroundColor "Yellow"
        $z = Get-SPOSiteGroup -Site $y.Url
        foreach ($a in $z)
            {
                 $b = Get-SPOSiteGroup -Site $y.Url -Group $a.Title 
                 Write-Host $b.Title -ForegroundColor "Cyan"
                 $b | Select-Object -ExpandProperty Users
                 Write-Host
            }
    }
```
    
## <a name="see-also"></a>Se även

[Ansluta till SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[Skapa SharePoint Online-webbplatser och lägga till användare med PowerShell](create-sharepoint-sites-and-add-users-with-powershell.md)

[Hantera SharePoint Online-användare och-grupper med PowerShell](manage-sharepoint-users-and-groups-with-powershell.md)

[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Komma igång med PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)

