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
# <a name="manage-sharepoint-online-users-and-groups-with-powershell"></a><span data-ttu-id="d66a4-103">Hantera SharePoint Online-användare och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="d66a4-103">Manage SharePoint Online users and groups with PowerShell</span></span>

<span data-ttu-id="d66a4-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="d66a4-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d66a4-105">Om du är SharePoint Online-administratör och arbetar med stora listor över användar konton eller grupper och är ett enklare sätt att hantera dem kan du använda PowerShell för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d66a4-105">If you are a SharePoint Online administrator who works with large lists of user accounts or groups and wants an easier way to manage them, you can use PowerShell for Microsoft 365.</span></span> 

<span data-ttu-id="d66a4-106">Innan du börjar måste du ansluta till SharePoint Online med procedurerna i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="d66a4-106">Before you begin, the procedures in this topic require you to connect to SharePoint Online.</span></span> <span data-ttu-id="d66a4-107">Anvisningar finns i [ansluta till SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="d66a4-107">For instructions, see [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span></span>

## <a name="get-a-list-of-sites-groups-and-users"></a><span data-ttu-id="d66a4-108">Få en lista över webbplatser, grupper och användare</span><span class="sxs-lookup"><span data-stu-id="d66a4-108">Get a list of sites, groups, and users</span></span>

<span data-ttu-id="d66a4-109">Innan vi börjar hantera användare och grupper måste du hämta listor över webbplatser, grupper och användare.</span><span class="sxs-lookup"><span data-stu-id="d66a4-109">Before we start to manage users and groups, you need to get lists of your sites, groups, and users.</span></span> <span data-ttu-id="d66a4-110">Du kan sedan använda den här informationen för att arbeta genom exemplet i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="d66a4-110">You can then use this information to work through the example in this article.</span></span>

<span data-ttu-id="d66a4-111">Få en lista över webbplatsernas webbplatser med det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="d66a4-111">Get a list of the sites in your tenant with this command:</span></span>

```powershell
Get-SPOSite
```

<span data-ttu-id="d66a4-112">Få en lista över gruppens grupper med det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="d66a4-112">Get a list of the groups in your tenant with this command:</span></span>

```powershell
Get-SPOSite | ForEach {Get-SPOSiteGroup -Site $_.Url} | Format-Table
```

<span data-ttu-id="d66a4-113">Få en lista över användare i klient organisationen med det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="d66a4-113">Get a list of the users in your tenant with this command:</span></span>

```powershell
Get-SPOSite | ForEach {Get-SPOUser -Site $_.Url}
```

## <a name="add-a-user-to-the-site-collection-administrators-group"></a><span data-ttu-id="d66a4-114">Lägga till en användare i gruppen Administratörer för webbplats samlingar</span><span class="sxs-lookup"><span data-stu-id="d66a4-114">Add a user to the Site Collection Administrators group</span></span>

<span data-ttu-id="d66a4-115">Du använder `Set-SPOUser` cmdleten för att lägga till en användare i listan över administratörer för webbplats samlingar i en webbplats samling.</span><span class="sxs-lookup"><span data-stu-id="d66a4-115">You use the `Set-SPOUser` cmdlet to add a user to the list of Site Collection Administrators on a site collection.</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
 ```

<span data-ttu-id="d66a4-116">Om du vill använda dessa kommandon ersätter du allt inom citat tecknen, inklusive < och > tecken, med rätt namn.</span><span class="sxs-lookup"><span data-stu-id="d66a4-116">To use these commands, replace everything within the quotes, including the < and > characters, with the correct names.</span></span>

<span data-ttu-id="d66a4-117">Denna uppsättning kommandon lägger till exempel till Opal Castillo (användar namn opalc) i listan över administratörer för webbplats samlingar på den ContosoTest webbplats samlingen i Contosos innehavare:</span><span class="sxs-lookup"><span data-stu-id="d66a4-117">For example, this set of commands adds Opal Castillo (user name opalc) to the list of Site Collection Administrators on the ContosoTest site collection in the Contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "opalc"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
```

<span data-ttu-id="d66a4-118">Du kan kopiera och klistra in dessa kommandon i anteckningar, ändra variabel värden för $tenant, $site och $user till faktiska värden från din miljö och sedan klistra in det i ditt SharePoint Online Management Shell-fönster för att köra dem.</span><span class="sxs-lookup"><span data-stu-id="d66a4-118">You can copy and paste these commands into Notepad, change the variable values for $tenant, $site, and $user to actual values from your environment, and then paste this into your SharePoint Online Management Shell window to run them.</span></span>

## <a name="add-a-user-to-other-site-collection-groups"></a><span data-ttu-id="d66a4-119">Lägga till en användare i andra webbplats samlings grupper</span><span class="sxs-lookup"><span data-stu-id="d66a4-119">Add a user to other site collection groups</span></span>

<span data-ttu-id="d66a4-120">I den här uppgiften ska vi använda `Add-SPOUser` cmdlet för att lägga till en användare i en SharePoint-grupp i en webbplats samling.</span><span class="sxs-lookup"><span data-stu-id="d66a4-120">In this task, we'll use the `Add-SPOUser` cmdlet to add a user to a SharePoint group on a site collection.</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site

```

<span data-ttu-id="d66a4-121">Låt oss till exempel lägga till Glen Rife (användar namn glenr) i gruppen granskare på den ContosoTest webbplats samlingen i Contosos innehavare:</span><span class="sxs-lookup"><span data-stu-id="d66a4-121">For example, let's add Glen Rife (user name glenr) to the Auditors group on the ContosoTest site collection in the contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "glenr"
$group = "Auditors"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="create-a-site-collection-group"></a><span data-ttu-id="d66a4-122">Skapa en grupp för webbplats samlingar</span><span class="sxs-lookup"><span data-stu-id="d66a4-122">Create a site collection group</span></span>

<span data-ttu-id="d66a4-123">Du använder `New-SPOSiteGroup` cmdleten för att skapa en ny SharePoint-grupp och lägga till den i en webbplats samling.</span><span class="sxs-lookup"><span data-stu-id="d66a4-123">You use the `New-SPOSiteGroup` cmdlet to create a new SharePoint group and add it to a site collection.</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$group = "<group name name, such as Auditors>"
$level = "<permission level, such as View Only>"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```
<span data-ttu-id="d66a4-124">Grupp egenskaper, till exempel behörighets nivåer, kan uppdateras senare med hjälp av `Set-SPOSiteGroup` cmdleten.</span><span class="sxs-lookup"><span data-stu-id="d66a4-124">Group properties, such as permission levels, can be updated later by using the `Set-SPOSiteGroup` cmdlet.</span></span>

<span data-ttu-id="d66a4-125">Låt oss till exempel lägga till Grans kar gruppen med endast behörighet till contosotest-webbplats samlingen i Contosos innehavare:</span><span class="sxs-lookup"><span data-stu-id="d66a4-125">For example, let's add the Auditors group with View Only permissions to the contosotest site collection in the contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$group = "Auditors"
$level = "View Only"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="remove-users-from-a-group"></a><span data-ttu-id="d66a4-126">Ta bort användare från en grupp</span><span class="sxs-lookup"><span data-stu-id="d66a4-126">Remove users from a group</span></span>

<span data-ttu-id="d66a4-127">Ibland måste du ta bort en användare från en eller flera webbplatser.</span><span class="sxs-lookup"><span data-stu-id="d66a4-127">Sometimes you have to remove a user from a site or even all sites.</span></span> <span data-ttu-id="d66a4-128">Den anställde kan flyttas från en division till en annan eller lämnar företaget.</span><span class="sxs-lookup"><span data-stu-id="d66a4-128">Perhaps the employee moves from one division to another or leaves the company.</span></span> <span data-ttu-id="d66a4-129">Du kan göra detta för en anställd i användar gränssnittet, men det är inte lätt att ringa när du måste flytta en hel division från en webbplats till en annan.</span><span class="sxs-lookup"><span data-stu-id="d66a4-129">You can do this for one employee easily in the UI, but this is not easily done when you have to move a complete division from one site to another.</span></span>

<span data-ttu-id="d66a4-130">Med SharePoint Online Management Shell-och CSV-filerna är detta snabbt och enkelt.</span><span class="sxs-lookup"><span data-stu-id="d66a4-130">However by using the SharePoint Online Management Shell and CSV files, this is fast and easy.</span></span> <span data-ttu-id="d66a4-131">Du använder Windows PowerShell för att ta bort en användare från en säkerhets grupp för en webbplats samling.</span><span class="sxs-lookup"><span data-stu-id="d66a4-131">In this task, you'll use Windows PowerShell to remove a user from a site collection security group.</span></span> <span data-ttu-id="d66a4-132">Då använder du en CSV-fil och tar bort många användare från olika webbplatser.</span><span class="sxs-lookup"><span data-stu-id="d66a4-132">Then you'll use a CSV file and remove lots of users from different sites.</span></span> 

<span data-ttu-id="d66a4-133">Vi kommer att använda cmdleten Remove-makar för att ta bort en enda Microsoft 365-användare från en webbplats samlings grupp så att vi kan se kommandosyntaxen.</span><span class="sxs-lookup"><span data-stu-id="d66a4-133">We'll be using the 'Remove-SPOUser' cmdlet to remove a single Microsoft 365 user from a site collection group just so we can see the command syntax.</span></span> <span data-ttu-id="d66a4-134">Så här ser syntaxen ut:</span><span class="sxs-lookup"><span data-stu-id="d66a4-134">Here is how the syntax looks:</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```
<span data-ttu-id="d66a4-135">Låt oss till exempel ta bort Bobby Overby från gruppen granskare i webbplats samlingen i contosotest-webbplats samlingen i innehavet contoso:</span><span class="sxs-lookup"><span data-stu-id="d66a4-135">For example, let's remove Bobby Overby from the site collection Auditors group in the contosotest site collection in the contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "bobbyo"
$group = "Auditors"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

<span data-ttu-id="d66a4-136">Anta att vi ville ta bort Bobby från alla grupper han för närvarande är i.</span><span class="sxs-lookup"><span data-stu-id="d66a4-136">Suppose we wanted to remove Bobby from all the groups he is currently in.</span></span> <span data-ttu-id="d66a4-137">Så här gör vi det:</span><span class="sxs-lookup"><span data-stu-id="d66a4-137">Here is how we would do that:</span></span>

```powershell
$tenant = "contoso"
$user = "bobbyo"
Get-SPOSite | ForEach {Get-SPOSiteGroup –Site $_.Url} | ForEach {Remove-SPOUser -LoginName $user@$tenant.com -Site &_.Url}
```

> [!WARNING]
> <span data-ttu-id="d66a4-138">Det här är bara ett exempel.</span><span class="sxs-lookup"><span data-stu-id="d66a4-138">This is just an example.</span></span> <span data-ttu-id="d66a4-139">Du bör inte köra det här kommandot om du verkligen måste ta bort en användare från varje grupp, till exempel om användaren lämnar företaget.</span><span class="sxs-lookup"><span data-stu-id="d66a4-139">You should not run this command unless you really have to remove a user from every group, for example if the user leaves the company.</span></span>

## <a name="automate-management-of-large-lists-of-users-and-groups"></a><span data-ttu-id="d66a4-140">Automatisera hanteringen av stora listor med användare och grupper</span><span class="sxs-lookup"><span data-stu-id="d66a4-140">Automate management of large lists of users and groups</span></span>

<span data-ttu-id="d66a4-141">Om du vill lägga till ett stort antal konton på SharePoint-webbplatser och ge dem behörighet kan du använda administrations centret för Microsoft 365, enskilda PowerShell-kommandon eller PowerShell en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="d66a4-141">To add a large number of accounts to SharePoint sites and give them permissions, you can use the Microsoft 365 admin center, individual PowerShell commands, or PowerShell an a CSV file.</span></span> <span data-ttu-id="d66a4-142">De här valen är att CSV-filen är det snabbaste sättet att automatisera den här uppgiften.</span><span class="sxs-lookup"><span data-stu-id="d66a4-142">Of these choices, the CSV file is the fastest way to automate this task.</span></span>

<span data-ttu-id="d66a4-143">Den grundläggande processen är att skapa en CSV-fil som innehåller rubriker (kolumner) som motsvarar de parametrar som Windows PowerShell-skriptet behöver.</span><span class="sxs-lookup"><span data-stu-id="d66a4-143">The basic process is to create a CSV file that has headers (columns) that correspond to the parameters that the Windows PowerShell script needs.</span></span> <span data-ttu-id="d66a4-144">Du kan enkelt skapa en sådan lista i Excel och sedan exportera den som en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="d66a4-144">You can easily create such a list in Excel and then export it as a CSV file.</span></span> <span data-ttu-id="d66a4-145">Sedan använder du ett Windows PowerShell-skript för att iterera genom poster (rader) i CSV-filen och lägger till användare i grupper och grupper på webbplatser.</span><span class="sxs-lookup"><span data-stu-id="d66a4-145">Then, you use a Windows PowerShell script to iterate through records (rows) in the CSV file, adding the users to groups and the groups to sites.</span></span> 

<span data-ttu-id="d66a4-146">Låt oss exempelvis skapa en CSV-fil för att definiera en grupp med webbplats samlingar, grupper och behörigheter.</span><span class="sxs-lookup"><span data-stu-id="d66a4-146">For example, let's create a CSV file to define a group of site collections, groups, and permissions.</span></span> <span data-ttu-id="d66a4-147">Nästa steg är att skapa en CSV-fil för att fylla grupper med användare.</span><span class="sxs-lookup"><span data-stu-id="d66a4-147">Next, we will create a CSV file to populate the groups with users.</span></span> <span data-ttu-id="d66a4-148">Slutligen skapas och körs ett enkelt Windows PowerShell-skript som skapar och fyller i grupper.</span><span class="sxs-lookup"><span data-stu-id="d66a4-148">Finally, we will create and run a simple Windows PowerShell script that creates and populates the groups.</span></span>

<span data-ttu-id="d66a4-149">Den första CSV-filen lägger till en eller flera grupper i en eller flera webbplats samlingar och har den här strukturen:</span><span class="sxs-lookup"><span data-stu-id="d66a4-149">The first CSV file will add one or more groups to one or more site collections and will have this structure:</span></span>

<span data-ttu-id="d66a4-150">Meddelande</span><span class="sxs-lookup"><span data-stu-id="d66a4-150">Header:</span></span>

```powershell
Site,Group,PermissionLevels
```

<span data-ttu-id="d66a4-151">Elementet</span><span class="sxs-lookup"><span data-stu-id="d66a4-151">Item:</span></span>

```powershell
https://tenant.sharepoint.com/sites/site,group,level
```

<span data-ttu-id="d66a4-152">Här är en exempel fil:</span><span class="sxs-lookup"><span data-stu-id="d66a4-152">Here is an example file:</span></span>

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

<span data-ttu-id="d66a4-153">Den andra CSV-filen lägger till en eller flera användare i en eller flera grupper och har den här strukturen:</span><span class="sxs-lookup"><span data-stu-id="d66a4-153">The second CSV file will add one or more users to one or more groups and will have this structure:</span></span>

<span data-ttu-id="d66a4-154">Meddelande</span><span class="sxs-lookup"><span data-stu-id="d66a4-154">Header:</span></span>

```powershell
Group,LoginName,Site
```

<span data-ttu-id="d66a4-155">Elementet</span><span class="sxs-lookup"><span data-stu-id="d66a4-155">Item:</span></span>

```powershell
group,login,https://tenant.sharepoint.com/sites/site
```

<span data-ttu-id="d66a4-156">Här är en exempel fil:</span><span class="sxs-lookup"><span data-stu-id="d66a4-156">Here is an example file:</span></span>

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

<span data-ttu-id="d66a4-157">För nästa steg måste du ha de två CSV-filerna sparade på din enhet.</span><span class="sxs-lookup"><span data-stu-id="d66a4-157">For the next step, you must have the two CSV files saved to your drive.</span></span> <span data-ttu-id="d66a4-158">Här är exempel kommandon som använder båda CSV-filer och för att lägga till behörigheter och grupp medlemskap:</span><span class="sxs-lookup"><span data-stu-id="d66a4-158">Here are example commands that use both CSV files and to add permissions and group membership:</span></span>

```powershell
Import-Csv C:\O365Admin\GroupsAndPermissions.csv | ForEach {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\O365Admin\Users.csv | ForEach {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```

<span data-ttu-id="d66a4-159">Skriptet importerar CSV-filens innehåll och använder värdena i kolumnerna för att fylla i parametrarna för kommandona **New-SPOSiteGroup** och **Add-makeer** .</span><span class="sxs-lookup"><span data-stu-id="d66a4-159">The script imports the CSV file contents and uses the values in the columns to populate the parameters of the **New-SPOSiteGroup** and **Add-SPOUser** commands.</span></span> <span data-ttu-id="d66a4-160">I vårt exempel sparar vi denna till theO365Admin-mappen på enhet C, men du kan spara den var du vill.</span><span class="sxs-lookup"><span data-stu-id="d66a4-160">In our example, we are saving this to theO365Admin folder on drive C, but you can save it wherever you want.</span></span>

<span data-ttu-id="d66a4-161">Låt oss ta bort många personer för flera grupper på olika webbplatser med samma CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="d66a4-161">Now, let's remove a bunch of people for several groups in different sites using the same CSV file.</span></span> <span data-ttu-id="d66a4-162">Här är ett exempel kommando:</span><span class="sxs-lookup"><span data-stu-id="d66a4-162">Here is an example command:</span></span>

```powershell
Import-Csv C:\O365Admin\Users.csv | ForEach {Remove-SPOUser -LoginName $_.LoginName -Site $_.Site -Group $_.Group}
```

## <a name="generate-user-reports"></a><span data-ttu-id="d66a4-163">Skapa användar rapporter</span><span class="sxs-lookup"><span data-stu-id="d66a4-163">Generate user reports</span></span>

<span data-ttu-id="d66a4-164">Du kanske vill få en enkel rapport för några webbplatser och visa användarna för dessa webbplatser, deras behörighets nivå och andra egenskaper.</span><span class="sxs-lookup"><span data-stu-id="d66a4-164">You might want to get a simple report for a few sites and display the users for those sites, their permission level, and other properties.</span></span> <span data-ttu-id="d66a4-165">Så här ser syntaxen ut:</span><span class="sxs-lookup"><span data-stu-id="d66a4-165">This is how the syntax looks:</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | select * | Format-table -Wrap -AutoSize | Out-File c\UsersReport.txt -Force -Width 360 -Append
```

<span data-ttu-id="d66a4-166">Detta hämtar data för dessa tre webbplatser och skriver dem till en textfil på din lokala enhet.</span><span class="sxs-lookup"><span data-stu-id="d66a4-166">This will grab the data for these three sites and write them to a text file on your local drive.</span></span> <span data-ttu-id="d66a4-167">Observera att parametern-append lägger till nytt innehåll i en befintlig fil.</span><span class="sxs-lookup"><span data-stu-id="d66a4-167">Note that the parameter –Append will add new content to an existing file.</span></span>

<span data-ttu-id="d66a4-168">Låt oss till exempel köra en rapport om ContosoTest, TeamSite01 och Project01 för contoso1-klient organisationen:</span><span class="sxs-lookup"><span data-stu-id="d66a4-168">For example, let's run a report on the ContosoTest, TeamSite01, and Project01 sites for the Contoso1 tenant:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "TeamSite01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site |Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "Project01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

<span data-ttu-id="d66a4-169">Observera att vi bara ändra **$Site** variabel.</span><span class="sxs-lookup"><span data-stu-id="d66a4-169">Note that we had to change only the **$site** variable.</span></span> <span data-ttu-id="d66a4-170">Variabeln **$Tenant** behåller sitt värde genom alla tre kommandona för kommandot.</span><span class="sxs-lookup"><span data-stu-id="d66a4-170">The **$tenant** variable keeps its value through all three runs of the command.</span></span>

<span data-ttu-id="d66a4-171">Men vad gör du om du vill göra det för varje webbplats?</span><span class="sxs-lookup"><span data-stu-id="d66a4-171">However, what if you wanted to do this for every site?</span></span> <span data-ttu-id="d66a4-172">Du kan göra detta utan att behöva skriva alla webbplatser med det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="d66a4-172">You can do this without having to type all those websites by using this command:</span></span>

```powershell
Get-SPOSite | ForEach {Get-SPOUser –Site $_.Url} | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

<span data-ttu-id="d66a4-173">Den här rapporten är ganska enkel och du kan lägga till fler koder för att skapa mer specifika rapporter som innehåller mer detaljerad information.</span><span class="sxs-lookup"><span data-stu-id="d66a4-173">This report is fairly simple, and you can add more code to create more specific reports or reports that include more detailed information.</span></span> <span data-ttu-id="d66a4-174">Men det bör ge dig en uppfattning om hur du använder SharePoint Online Management Shell för att hantera användare i SharePoint Online-miljön.</span><span class="sxs-lookup"><span data-stu-id="d66a4-174">But this should give you an idea of how to use the SharePoint Online Management Shell to manage users in the SharePoint Online environment.</span></span>
   
## <a name="see-also"></a><span data-ttu-id="d66a4-175">Se även</span><span class="sxs-lookup"><span data-stu-id="d66a4-175">See also</span></span>

[<span data-ttu-id="d66a4-176">Ansluta till SharePoint Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="d66a4-176">Connect to SharePoint Online PowerShell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[<span data-ttu-id="d66a4-177">Hantera SharePoint Online med PowerShell</span><span class="sxs-lookup"><span data-stu-id="d66a4-177">Manage SharePoint Online with PowerShell</span></span>](create-sharepoint-sites-and-add-users-with-powershell.md)

[<span data-ttu-id="d66a4-178">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="d66a4-178">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="d66a4-179">Komma igång med PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d66a4-179">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
