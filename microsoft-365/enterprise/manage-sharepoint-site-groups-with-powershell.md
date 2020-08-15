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
# <a name="manage-sharepoint-online-site-groups-with-powershell"></a><span data-ttu-id="3009b-103">Hantera webbplats grupper för SharePoint Online med PowerShell</span><span class="sxs-lookup"><span data-stu-id="3009b-103">Manage SharePoint Online site groups with PowerShell</span></span>

<span data-ttu-id="3009b-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="3009b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="3009b-105">Även om du kan använda administrations centret för Microsoft 365 kan du även använda PowerShell för Microsoft 365 för att hantera webbplats grupper för SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="3009b-105">Although you can use the Microsoft 365 admin center, you can also use PowerShell for Microsoft 365 to manage your SharePoint Online site groups.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="3009b-106">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="3009b-106">Before you begin</span></span>

<span data-ttu-id="3009b-107">Procedurerna i den här artikeln kräver att du ansluter till SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="3009b-107">The procedures in this article require you to connect to SharePoint Online.</span></span> <span data-ttu-id="3009b-108">Anvisningar finns i [ansluta till SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="3009b-108">For instructions, see [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

## <a name="view-sharepoint-online-with-powershell-for-microsoft-365"></a><span data-ttu-id="3009b-109">Visa SharePoint Online med PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3009b-109">View SharePoint Online with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="3009b-110">Administrations centret för SharePoint Online har några lättanvända metoder för att hantera webbplats grupper.</span><span class="sxs-lookup"><span data-stu-id="3009b-110">The SharePoint Online admin center has some easy-to-use methods for managing site groups.</span></span> <span data-ttu-id="3009b-111">Anta till exempel att du vill titta på grupperna och grupp medlemmarna för `https://litwareinc.sharepoint.com/sites/finance` webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="3009b-111">For example, suppose you want to look at the groups, and the group members, for the `https://litwareinc.sharepoint.com/sites/finance` site.</span></span> <span data-ttu-id="3009b-112">Det här kan du göra:</span><span class="sxs-lookup"><span data-stu-id="3009b-112">Here's what you have to do to:</span></span>

1. <span data-ttu-id="3009b-113">I administrations centret för SharePoint klickar du på **aktiva webbplatser**och sedan på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="3009b-113">From the SharePoint admin center, click **Active sites**, and then click the URL of the site.</span></span>
2. <span data-ttu-id="3009b-114">Klicka på ikonen **Inställningar** (i det övre högra hörnet på sidan) på webbplats sidan och klicka sedan på **webbplats behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="3009b-114">On the site page, click the **Settings** icon (located in the upper right-hand corner of the page), and then click **Site permissions**.</span></span>

<span data-ttu-id="3009b-115">Och upprepar sedan processen för nästa webbplats du vill titta på.</span><span class="sxs-lookup"><span data-stu-id="3009b-115">And then repeat the process for the next site you want to look at.</span></span>

<span data-ttu-id="3009b-116">Om du vill ha en lista över grupperna med PowerShell för Microsoft 365 kan du använda följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="3009b-116">To get a list of the groups with PowerShell for Microsoft 365, you can use the following commands:</span></span>

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

<span data-ttu-id="3009b-117">Det finns två sätt att köra den här kommando uppsättningen i kommando tolken i SharePoint Online Management Shell:</span><span class="sxs-lookup"><span data-stu-id="3009b-117">There are two ways to run this command set in the SharePoint Online Management Shell command prompt:</span></span>

- <span data-ttu-id="3009b-118">Kopiera kommandona till anteckningar (eller en annan text redigerare), ändra värdet för **$siteURL** variabel, Välj kommandon och klistra sedan in dem i kommando tolken i SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="3009b-118">Copy the commands into Notepad (or another text editor), modify the value of the **$siteURL** variable, select the commands, and then paste them into the SharePoint Online Management Shell command prompt.</span></span> <span data-ttu-id="3009b-119">När du gör det stannar PowerShell vid en **>>** uppmaning.</span><span class="sxs-lookup"><span data-stu-id="3009b-119">When you do, PowerShell will stop at a **>>** prompt.</span></span> <span data-ttu-id="3009b-120">Kör kommandot genom att trycka på RETUR `foreach` .</span><span class="sxs-lookup"><span data-stu-id="3009b-120">Press Enter to execute the `foreach` command.</span></span><br/>
- <span data-ttu-id="3009b-121">Kopiera kommandona till anteckningar (eller en annan text redigerare), ändra värdet för variabeln **$siteURL** och spara sedan den här text filen med ett namn och fil namns tillägget. ps1 i en lämplig mapp.</span><span class="sxs-lookup"><span data-stu-id="3009b-121">Copy the commands into Notepad (or another text editor), modify the value of the **$siteURL** variable, and then save this text file with a name and the .ps1 extension in a suitable folder.</span></span> <span data-ttu-id="3009b-122">Kör sedan skriptet från kommando tolken för SharePoint Online Management Shell genom att ange sökvägen och fil namnet.</span><span class="sxs-lookup"><span data-stu-id="3009b-122">Next, run the script from the SharePoint Online Management Shell command prompt by specifying its path and file name.</span></span> <span data-ttu-id="3009b-123">Här är ett exempel kommando:</span><span class="sxs-lookup"><span data-stu-id="3009b-123">Here is an example command:</span></span>

```powershell
C:\Scripts\SiteGroupsAndUsers.ps1
```

<span data-ttu-id="3009b-124">I båda fallen ser du något som liknar det här:</span><span class="sxs-lookup"><span data-stu-id="3009b-124">In both cases, you should see something similar to this:</span></span>

![Webbplats grupper för SharePoint Online](../media/SPO-site-groups.png)

<span data-ttu-id="3009b-126">Det här är alla grupper som har skapats för webbplatsen `https://litwareinc.sharepoint.com/sites/finance` och alla användare som har tilldelats till gruppen.</span><span class="sxs-lookup"><span data-stu-id="3009b-126">These are all the groups that have been created for the site `https://litwareinc.sharepoint.com/sites/finance`, and all the users assigned to those groups.</span></span> <span data-ttu-id="3009b-127">Grupp namnen är i gult för att hjälpa dig att dela upp grupp namn från deras medlemmar.</span><span class="sxs-lookup"><span data-stu-id="3009b-127">The group names are in yellow to help you separate group names from their members.</span></span>

<span data-ttu-id="3009b-128">Det här är en kommando uppsättning som visar grupperna och alla grupp medlemskap för alla SharePoint Online-webbplatser.</span><span class="sxs-lookup"><span data-stu-id="3009b-128">As another example, here is a command set that lists the groups, and all the group memberships, for all of your SharePoint Online sites.</span></span>

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
    
## <a name="see-also"></a><span data-ttu-id="3009b-129">Se även</span><span class="sxs-lookup"><span data-stu-id="3009b-129">See also</span></span>

[<span data-ttu-id="3009b-130">Ansluta till SharePoint Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="3009b-130">Connect to SharePoint Online PowerShell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[<span data-ttu-id="3009b-131">Skapa SharePoint Online-webbplatser och lägga till användare med PowerShell</span><span class="sxs-lookup"><span data-stu-id="3009b-131">Create SharePoint Online sites and add users with PowerShell</span></span>](create-sharepoint-sites-and-add-users-with-powershell.md)

[<span data-ttu-id="3009b-132">Hantera SharePoint Online-användare och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="3009b-132">Manage SharePoint Online users and groups with PowerShell</span></span>](manage-sharepoint-users-and-groups-with-powershell.md)

[<span data-ttu-id="3009b-133">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="3009b-133">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="3009b-134">Komma igång med PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3009b-134">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

