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
# <a name="create-sharepoint-online-sites-and-add-users-with-powershell"></a><span data-ttu-id="2c49b-103">Skapa SharePoint Online-webbplatser och lägga till användare med PowerShell</span><span class="sxs-lookup"><span data-stu-id="2c49b-103">Create SharePoint Online sites and add users with PowerShell</span></span>

<span data-ttu-id="2c49b-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="2c49b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="2c49b-105">När du använder PowerShell för Microsoft 365 för att skapa SharePoint Online-webbplatser och lägga till användare kan du snabbt och enkelt utföra uppgifter snabbare än i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2c49b-105">When you use PowerShell for Microsoft 365 to create SharePoint Online sites and add users, you can quickly and repeatedly perform tasks much faster than you can in the Microsoft 365 admin center.</span></span> <span data-ttu-id="2c49b-106">Du kan också utföra uppgifter som inte kan utföras i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2c49b-106">You can also perform tasks that are not possible to perform in the Microsoft 365 admin center.</span></span> 

## <a name="connect-to-sharepoint-online"></a><span data-ttu-id="2c49b-107">Ansluta till SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2c49b-107">Connect to SharePoint Online</span></span>

<span data-ttu-id="2c49b-108">Procedurerna i det här avsnittet kräver att du ansluter till SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="2c49b-108">The procedures in this topic require you to connect to SharePoint Online.</span></span> <span data-ttu-id="2c49b-109">Anvisningar finns i [ansluta till SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="2c49b-109">For instructions, see [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span></span>

## <a name="step-1-create-new-site-collections-using-powershell"></a><span data-ttu-id="2c49b-110">Steg 1: skapa nya webbplats samlingar med PowerShell</span><span class="sxs-lookup"><span data-stu-id="2c49b-110">Step 1: Create new site collections using PowerShell</span></span>

<span data-ttu-id="2c49b-111">Skapa flera webbplatser med hjälp av PowerShell och en. csv-fil som du skapar med exempel koden som tillhandahålls och anteckningar.</span><span class="sxs-lookup"><span data-stu-id="2c49b-111">Create multiple sites using PowerShell and a .csv file that you create using the example code provided and Notepad.</span></span> <span data-ttu-id="2c49b-112">För den här proceduren ska du ersätta plats hållaren som visas inom parentes med din egen webbplats-och klient organisations information.</span><span class="sxs-lookup"><span data-stu-id="2c49b-112">For this procedure, you’ll be replacing the placeholder information shown in brackets with your own site- and tenant-specific information.</span></span> <span data-ttu-id="2c49b-113">Med den här processen kan du skapa en fil och köra ett enda PowerShell-kommando som använder den filen.</span><span class="sxs-lookup"><span data-stu-id="2c49b-113">This process lets you create a single file and run a single PowerShell command that uses that file.</span></span> <span data-ttu-id="2c49b-114">Detta gör åtgärderna både repeterbara och portabla och eliminerar många, om inte alla, fel som kan komma att skriva långa kommandon till SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="2c49b-114">This makes the actions taken both repeatable and portable and eliminates many, if not all, errors that can come from typing long commands into the SharePoint Online Management Shell.</span></span> <span data-ttu-id="2c49b-115">Det finns två delar till den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="2c49b-115">There are two parts to this procedure.</span></span> <span data-ttu-id="2c49b-116">Först skapar du en CSV-fil och sedan hänvisar du till. csv-filen med PowerShell, som använder dess innehåll för att skapa webbplatserna.</span><span class="sxs-lookup"><span data-stu-id="2c49b-116">First you’ll create a .csv file, and then you’ll reference that .csv file using PowerShell, which will use its contents to create the sites.</span></span>

<span data-ttu-id="2c49b-117">PowerShell-cmdleten importerar. csv-filen och rör den till en loop inuti klammerparenteserna som läser den första raden i filen som kolumn rubriker.</span><span class="sxs-lookup"><span data-stu-id="2c49b-117">The PowerShell cmdlet imports the .csv file and pipes it to a loop inside the curly brackets that reads the first line of the file as column headers.</span></span> <span data-ttu-id="2c49b-118">PowerShell-cmdleten upprepas sedan genom de återstående posterna, skapar en ny webbplats samling för varje post och tilldelar webbplats Samlingens egenskaper enligt kolumn rubrikerna.</span><span class="sxs-lookup"><span data-stu-id="2c49b-118">The PowerShell cmdlet then iterates through the remaining records, creates a new site collection for each record, and assigns properties of the site collection according to the column headers.</span></span>

### <a name="create-a-csv-file"></a><span data-ttu-id="2c49b-119">Skapa en. csv-fil</span><span class="sxs-lookup"><span data-stu-id="2c49b-119">Create a .csv file</span></span>

1. <span data-ttu-id="2c49b-120">Öppna Anteckningar och klistra in följande textblock i det:</span><span class="sxs-lookup"><span data-stu-id="2c49b-120">Open Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Owner,StorageQuota,Url,ResourceQuota,Template,TimeZoneID,Name
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/TeamSite01,25,EHS#1,10,Contoso Team Site
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/Blog01,25,BLOG#0,10,Contoso Blog
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Project01,25,PROJECTSITE#0,10,Project Alpha
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Community01,25,COMMUNITY#0,10,Community Site
```
<br/><span data-ttu-id="2c49b-121">Här är *klient* organisationens namn och *ägare* är användar namnet på den klient organisation som du vill bevilja rollen som primär administratör för webbplats samlingen.</span><span class="sxs-lookup"><span data-stu-id="2c49b-121">Where *tenant* is the name of your tenant, and *owner* is the user name of the user on your tenant to whom you want to grant the role of primary site collection administrator.</span></span><br/><span data-ttu-id="2c49b-122">(Du kan trycka på CTRL + H när du använder anteckningar för att snabbt byta ut.)</span><span class="sxs-lookup"><span data-stu-id="2c49b-122">(You can press Ctrl+H when you use Notepad to bulk replace faster.)</span></span><br/>

2. <span data-ttu-id="2c49b-123">Spara filen på Skriv bordet som **SiteCollections.csv**.</span><span class="sxs-lookup"><span data-stu-id="2c49b-123">Save the file on your desktop as **SiteCollections.csv**.</span></span><br/>

> [!TIP]
> <span data-ttu-id="2c49b-124">Innan du använder den här eller någon annan. csv-eller Windows PowerShell-skriptfil är det lämpligt att kontrol lera att det inte finns några främmande eller icke utskrivbara tecken.</span><span class="sxs-lookup"><span data-stu-id="2c49b-124">Before you use this or any other .csv or Windows PowerShell script file, it's a good practice to make sure that there are no extraneous or nonprinting characters.</span></span> <span data-ttu-id="2c49b-125">Öppna filen i Word och klicka på stycke ikonen i menyfliksområdet för att visa icke utskrivbara tecken.</span><span class="sxs-lookup"><span data-stu-id="2c49b-125">Open the file in Word, and in the ribbon, click the paragraph icon to show nonprinting characters.</span></span> <span data-ttu-id="2c49b-126">Det får inte finnas specialtecken som inte skrivs ut.</span><span class="sxs-lookup"><span data-stu-id="2c49b-126">There should be no extraneous nonprinting characters.</span></span> <span data-ttu-id="2c49b-127">Det får till exempel inte finnas några stycke tecken utöver den sista längst ned i filen.</span><span class="sxs-lookup"><span data-stu-id="2c49b-127">For example, there should be no paragraph marks beyond the final one at the end of the file.</span></span>

### <a name="run-the-windows-powershell-command"></a><span data-ttu-id="2c49b-128">Köra kommandot Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2c49b-128">Run the Windows PowerShell command</span></span>

1. <span data-ttu-id="2c49b-129">Skriv eller kopiera och klistra in följande kommando i Windows PowerShell-uppmaningen och tryck på RETUR:</span><span class="sxs-lookup"><span data-stu-id="2c49b-129">At the Windows PowerShell prompt, type or copy and paste the following command, and press Enter:</span></span><br/>
```powershell
Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -ResourceQuota $_.ResourceQuota -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}
```
<br/><span data-ttu-id="2c49b-130">Där *Kantutjämna* är lika med ditt användar namn.</span><span class="sxs-lookup"><span data-stu-id="2c49b-130">Where *MyAlias* equals your user alias.</span></span><br/>

2. <span data-ttu-id="2c49b-131">Vänta tills Windows PowerShell-uppmaningen visas igen.</span><span class="sxs-lookup"><span data-stu-id="2c49b-131">Wait for the Windows PowerShell prompt to reappear.</span></span> <span data-ttu-id="2c49b-132">Det kan ta ett par minuter.</span><span class="sxs-lookup"><span data-stu-id="2c49b-132">It might take a minute or two.</span></span><br/>

3. <span data-ttu-id="2c49b-133">Skriv eller kopiera och klistra in följande cmdlet vid Windows PowerShell-uppmaningen och tryck på RETUR:</span><span class="sxs-lookup"><span data-stu-id="2c49b-133">At the Windows PowerShell prompt, type or copy and paste the following cmdlet, and press Enter:</span></span><br/>

```powershell
Get-SPOSite -Detailed | Format-Table -AutoSize
```
<br/>

4. <span data-ttu-id="2c49b-134">Observera de nya webbplats samlingarna i listan.</span><span class="sxs-lookup"><span data-stu-id="2c49b-134">Note the new site collections in the list.</span></span> <span data-ttu-id="2c49b-135">Med exempel filen CSV kan du se följande webbplats samlingar: **TeamSite01**, **Blog01**, **Project01**och **Community01**</span><span class="sxs-lookup"><span data-stu-id="2c49b-135">Using our example CSV file, you would see the following site collections: **TeamSite01**, **Blog01**, **Project01**, and **Community01**</span></span>

<span data-ttu-id="2c49b-136">Det är det.</span><span class="sxs-lookup"><span data-stu-id="2c49b-136">That’s it.</span></span> <span data-ttu-id="2c49b-137">Du har skapat flera webbplats samlingar med hjälp av CSV-filen som du skapade och ett enda Windows PowerShell-kommando.</span><span class="sxs-lookup"><span data-stu-id="2c49b-137">You’ve created multiple site collections using the .csv file you created and a single Windows PowerShell command.</span></span> <span data-ttu-id="2c49b-138">Nu är du redo att skapa och koppla användare till dessa webbplatser.</span><span class="sxs-lookup"><span data-stu-id="2c49b-138">You’re now ready to create and assign users to these sites.</span></span>

## <a name="step-2-add-users-and-groups"></a><span data-ttu-id="2c49b-139">Steg 2: Lägg till användare och grupper</span><span class="sxs-lookup"><span data-stu-id="2c49b-139">Step 2: Add users and groups</span></span>

<span data-ttu-id="2c49b-140">Nu ska du skapa användare och lägga till dem i en webbplats samlings grupp.</span><span class="sxs-lookup"><span data-stu-id="2c49b-140">Now you’re going to create users and add them to a site collection group.</span></span> <span data-ttu-id="2c49b-141">Sedan använder du en CSV-fil för att ladda upp nya grupper och användare.</span><span class="sxs-lookup"><span data-stu-id="2c49b-141">You will then use a .csv file to bulk upload new groups and users.</span></span>

<span data-ttu-id="2c49b-142">Följande procedurer fortsätter att använda exemplen TeamSite01, Blog01, Project01 och Community01.</span><span class="sxs-lookup"><span data-stu-id="2c49b-142">The following procedures continue using the example sites TeamSite01, Blog01, Project01, and Community01.</span></span>

### <a name="create-csv-and-ps1-files"></a><span data-ttu-id="2c49b-143">Skapa. csv-och. ps1-filer</span><span class="sxs-lookup"><span data-stu-id="2c49b-143">Create .csv and .ps1 files</span></span>

1. <span data-ttu-id="2c49b-144">Öppna Anteckningar och klistra in följande textblock i det:</span><span class="sxs-lookup"><span data-stu-id="2c49b-144">Open Notepad, and paste the following text block into it:</span></span><br/>

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
<br/><span data-ttu-id="2c49b-145">Där *klient* organisationen är lika med klient organisationens namn.</span><span class="sxs-lookup"><span data-stu-id="2c49b-145">Where *tenant* equals your tenant name.</span></span><br/>

2. <span data-ttu-id="2c49b-146">Spara filen på Skriv bordet som **GroupsAndPermissions.csv**.</span><span class="sxs-lookup"><span data-stu-id="2c49b-146">Save the file to your desktop as **GroupsAndPermissions.csv**.</span></span><br/>

3. <span data-ttu-id="2c49b-147">Öppna en ny instans av anteckningar och klistra in följande textblock i det:</span><span class="sxs-lookup"><span data-stu-id="2c49b-147">Open a new instance of Notepad, and paste the following text block into it:</span></span><br/>

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
<br/><span data-ttu-id="2c49b-148">Där *klient* organisationen är lika med klient namnet och *användar* namnet är lika med användarens namn för en befintlig användare.</span><span class="sxs-lookup"><span data-stu-id="2c49b-148">Where *tenant* equals your tenant name, and *username* equals the user name of an existing user.</span></span><br/>

4. <span data-ttu-id="2c49b-149">Spara filen på Skriv bordet som **Users.csv**.</span><span class="sxs-lookup"><span data-stu-id="2c49b-149">Save the file to your desktop as **Users.csv**.</span></span><br/>

5. <span data-ttu-id="2c49b-150">Öppna en ny instans av anteckningar och klistra in följande textblock i det:</span><span class="sxs-lookup"><span data-stu-id="2c49b-150">Open a new instance of Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\users\MyAlias\desktop\Users.csv | where {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```
<br/><span data-ttu-id="2c49b-151">Där Kantutjämna är lika med användar namnet på den användare som är inloggad för tillfället.</span><span class="sxs-lookup"><span data-stu-id="2c49b-151">Where MyAlias equals the user name of the user that is currently logged on.</span></span><br/>

6. <span data-ttu-id="2c49b-152">Spara filen på Skriv bordet som **UsersAndGroups.ps1**.</span><span class="sxs-lookup"><span data-stu-id="2c49b-152">Save the file to your desktop as **UsersAndGroups.ps1**.</span></span> <span data-ttu-id="2c49b-153">Det här är en enkel Windows PowerShell-skript.</span><span class="sxs-lookup"><span data-stu-id="2c49b-153">This is a simple Windows PowerShell script.</span></span>

<span data-ttu-id="2c49b-154">Nu är du redo att köra UsersAndGroup.ps1-skript för att lägga till användare och grupper i flera webbplats samlingar.</span><span class="sxs-lookup"><span data-stu-id="2c49b-154">You’re now ready to run the UsersAndGroup.ps1 script to add users and groups to multiple site collections.</span></span>

### <a name="run-usersandgroupsps1-script"></a><span data-ttu-id="2c49b-155">Kör UsersAndGroups.ps1 skript</span><span class="sxs-lookup"><span data-stu-id="2c49b-155">Run UsersAndGroups.ps1 script</span></span>

1. <span data-ttu-id="2c49b-156">Återvänd till SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="2c49b-156">Return to the SharePoint Online Management Shell.</span></span><br/>
2. <span data-ttu-id="2c49b-157">Skriv eller kopiera och klistra in följande rad vid Windows PowerShell-uppmaningen och tryck på RETUR:</span><span class="sxs-lookup"><span data-stu-id="2c49b-157">At the Windows PowerShell prompt, type or copy and paste the following line, and press Enter:</span></span><br/>
```powershell
Set-ExecutionPolicy Bypass
```
<br/>

3. <span data-ttu-id="2c49b-158">När du uppmanas att bekräfta trycker du på **j**.</span><span class="sxs-lookup"><span data-stu-id="2c49b-158">At the confirmation prompt, press **Y**.</span></span><br/>

4. <span data-ttu-id="2c49b-159">Skriv eller kopiera och klistra in följande i Windows PowerShell-uppmaningen och tryck på RETUR:</span><span class="sxs-lookup"><span data-stu-id="2c49b-159">At the Windows PowerShell prompt, type or copy and paste the following, and press Enter:</span></span><br/>

```powershell
c:\users\MyAlias\desktop\UsersAndGroups.ps1
```
<br/><span data-ttu-id="2c49b-160">Där *Kantutjämna* är lika med ditt användar namn.</span><span class="sxs-lookup"><span data-stu-id="2c49b-160">Where *MyAlias* equals your user name.</span></span><br/>

5. <span data-ttu-id="2c49b-161">Vänta tills uppmaningen återgår innan du fortsätter.</span><span class="sxs-lookup"><span data-stu-id="2c49b-161">Wait for the prompt to return before moving on.</span></span> <span data-ttu-id="2c49b-162">Du ser först grupperna när de skapas.</span><span class="sxs-lookup"><span data-stu-id="2c49b-162">You will first see the groups appear as they are created.</span></span> <span data-ttu-id="2c49b-163">Då visas grupp listan upprepade gånger när användarna läggs till.</span><span class="sxs-lookup"><span data-stu-id="2c49b-163">Then you will see the group list repeated as users are added.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c49b-164">Se även</span><span class="sxs-lookup"><span data-stu-id="2c49b-164">See also</span></span>

[<span data-ttu-id="2c49b-165">Ansluta till SharePoint Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="2c49b-165">Connect to SharePoint Online PowerShell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[<span data-ttu-id="2c49b-166">Hantera webbplats grupper för SharePoint Online med PowerShell</span><span class="sxs-lookup"><span data-stu-id="2c49b-166">Manage SharePoint Online site groups with PowerShell</span></span>](manage-sharepoint-site-groups-with-powershell.md)

[<span data-ttu-id="2c49b-167">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="2c49b-167">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="2c49b-168">Komma igång med PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2c49b-168">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

