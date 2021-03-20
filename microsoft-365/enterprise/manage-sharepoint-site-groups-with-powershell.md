---
title: Hantera SharePoint Online-webbplatsgrupper med PowerShell
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
description: I den här artikeln hittar du procedurer för att använda PowerShell för Microsoft 365 för att hantera SharePoint Online-webbplatsgrupper.
ms.openlocfilehash: bcc7a00a6114a6fa2ba8aa02520267bd03a0abf5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909544"
---
# <a name="manage-sharepoint-online-site-groups-with-powershell"></a>Hantera SharePoint Online-webbplatsgrupper med PowerShell

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Även om du kan använda administrationscentret för Microsoft 365 kan du också använda PowerShell för Microsoft 365 för att hantera dina SharePoint Online-webbplatsgrupper.

## <a name="before-you-begin"></a>Innan du börjar

Procedurerna i den här artikeln kräver att du ansluter till SharePoint Online. Instruktioner finns i [Ansluta till SharePoint Online PowerShell.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

## <a name="view-sharepoint-online-with-powershell-for-microsoft-365"></a>Visa SharePoint Online med PowerShell för Microsoft 365

I administrationscentret för SharePoint Online finns det några lättanvända metoder för att hantera webbplatsgrupper. Anta till exempel att du vill titta på grupperna och gruppmedlemmarna för `https://litwareinc.sharepoint.com/sites/finance` webbplatsen. Det här måste du göra:

1. I administrationscentret för SharePoint klickar du **på Aktiva** webbplatser och sedan på webbplatsens URL.
2. Klicka på ikonen Inställningar (längst **upp** till höger på sidan) och klicka sedan på **Webbplatsbehörigheter.**

Upprepa sedan processen för nästa webbplats som du vill titta på.

För att få en lista över grupper med PowerShell för Microsoft 365 kan du använda följande kommandon:

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

Det finns två sätt att köra den här kommandouppsättningen i kommandotolken för SharePoint Online Management Shell:

- Kopiera kommandona till Anteckningar (eller någon annan textredigerare), ändra värdet för $siteURL-variabeln, markera kommandona och klistra in dem i kommandotolken i SharePoint Online Management Shell.  När du gör det slutar PowerShell när du uppmanas att **>>** göra det. Tryck på Retur för att köra `foreach` kommandot.<br/>
- Kopiera kommandona till Anteckningar (eller någon annan textredigerare), ändra värdet för **$siteURL-variabeln** och spara sedan textfilen med ett namn och filnamnstillägget .ps1 i en lämplig mapp. Kör sedan skriptet från kommandotolken i SharePoint Online Management Shell genom att ange dess sökväg och filnamn. Här är ett exempelkommando:

```powershell
C:\Scripts\SiteGroupsAndUsers.ps1
```

I båda fallen bör du se något som liknar det här:

![SharePoint Online-webbplatsgrupper](../media/SPO-site-groups.png)

Det här är alla grupper som har skapats för webbplatsen `https://litwareinc.sharepoint.com/sites/finance` och alla användare som tilldelats grupperna. Gruppnamnen är i gult så att du kan skilja gruppnamnen från medlemmarna.

Ett annat exempel är här en kommandouppsättning som listar grupperna och alla gruppmedlemskap för alla dina SharePoint Online-webbplatser.

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

[Ansluta till SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[Skapa SharePoint Online-webbplatser och lägga till användare med PowerShell](create-sharepoint-sites-and-add-users-with-powershell.md)

[Hantera SharePoint Online-användare och grupper med PowerShell](manage-sharepoint-users-and-groups-with-powershell.md)

[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Börja använda PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)