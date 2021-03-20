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
description: Sammanfattning Använd PowerShell för att skapa nya SharePoint Online-webbplatser och sedan lägga till användare och grupper på webbplatserna.
ms.openlocfilehash: eb6c2817c8760ca222da8a7c2b14cbfcda4eb4b8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907624"
---
# <a name="create-sharepoint-online-sites-and-add-users-with-powershell"></a><span data-ttu-id="8a3cc-103">Skapa SharePoint Online-webbplatser och lägga till användare med PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a3cc-103">Create SharePoint Online sites and add users with PowerShell</span></span>

<span data-ttu-id="8a3cc-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="8a3cc-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="8a3cc-105">När du använder PowerShell för Microsoft 365 för att skapa SharePoint Online-webbplatser och lägga till användare kan du snabbt och upprepade gånger utföra uppgifter mycket snabbare än vad du kan göra i administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-105">When you use PowerShell for Microsoft 365 to create SharePoint Online sites and add users, you can quickly and repeatedly perform tasks much faster than you can in the Microsoft 365 admin center.</span></span> <span data-ttu-id="8a3cc-106">Du kan också utföra uppgifter som inte är möjliga att utföra i administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-106">You can also perform tasks that are not possible to perform in the Microsoft 365 admin center.</span></span> 

## <a name="connect-to-sharepoint-online"></a><span data-ttu-id="8a3cc-107">Ansluta till SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8a3cc-107">Connect to SharePoint Online</span></span>

<span data-ttu-id="8a3cc-108">För procedurerna i det här avsnittet måste du ansluta till SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-108">The procedures in this topic require you to connect to SharePoint Online.</span></span> <span data-ttu-id="8a3cc-109">Anvisningar finns i [Ansluta till SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="8a3cc-109">For instructions, see [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span></span>

## <a name="step-1-create-new-site-collections-using-powershell"></a><span data-ttu-id="8a3cc-110">Steg 1: Skapa nya webbplatssamlingar med PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a3cc-110">Step 1: Create new site collections using PowerShell</span></span>

<span data-ttu-id="8a3cc-111">Skapa flera webbplatser med PowerShell och en CSV-fil som du skapar med exempelkoden som tillhandahålls och Anteckningar.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-111">Create multiple sites using PowerShell and a .csv file that you create using the example code provided and Notepad.</span></span> <span data-ttu-id="8a3cc-112">För den här proceduren ersätter du platshållarinformationen som visas inom hakparenteser med din egen webbplats- och klientspecifik information.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-112">For this procedure, you’ll be replacing the placeholder information shown in brackets with your own site- and tenant-specific information.</span></span> <span data-ttu-id="8a3cc-113">Med den här processen kan du skapa en enda fil och köra ett enda PowerShell-kommando som använder den filen.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-113">This process lets you create a single file and run a single PowerShell command that uses that file.</span></span> <span data-ttu-id="8a3cc-114">Det här gör att åtgärder som vidtas både går att upprepa och ta bort, och tar bort många, om inte alla, fel som kan komma från att skriva långa kommandon i SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-114">This makes the actions taken both repeatable and portable and eliminates many, if not all, errors that can come from typing long commands into the SharePoint Online Management Shell.</span></span> <span data-ttu-id="8a3cc-115">Den här proceduren har två delar.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-115">There are two parts to this procedure.</span></span> <span data-ttu-id="8a3cc-116">Först skapar du en CSV-fil och sedan refererar du till den CSV-filen med PowerShell som använder innehållet för att skapa webbplatserna.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-116">First you’ll create a .csv file, and then you’ll reference that .csv file using PowerShell, which will use its contents to create the sites.</span></span>

<span data-ttu-id="8a3cc-117">PowerShell-cmdleten importerar CSV-filen och rör den till en slinga inom klammerparenteser som läser den första raden i filen som kolumnrubriker.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-117">The PowerShell cmdlet imports the .csv file and pipes it to a loop inside the curly brackets that reads the first line of the file as column headers.</span></span> <span data-ttu-id="8a3cc-118">PowerShell-cmdleten itereras sedan genom de återstående posterna, skapar en ny webbplatssamling för varje post och tilldelar egenskaper för webbplatssamlingen enligt kolumnrubrikerna.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-118">The PowerShell cmdlet then iterates through the remaining records, creates a new site collection for each record, and assigns properties of the site collection according to the column headers.</span></span>

### <a name="create-a-csv-file"></a><span data-ttu-id="8a3cc-119">Skapa en CSV-fil</span><span class="sxs-lookup"><span data-stu-id="8a3cc-119">Create a .csv file</span></span>

> [!NOTE]
> <span data-ttu-id="8a3cc-120">Resurskvotparametern fungerar bara på klassiska webbplatser.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-120">The resource quota parameter works only on classic sites.</span></span> <span data-ttu-id="8a3cc-121">Om du använder den här parametern på en modern webbplats kan du få ett varningsmeddelande om att den har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-121">If you use this parameter on a modern site, you may receive a warning message that it has been deprecated.</span></span> 

1. <span data-ttu-id="8a3cc-122">Öppna Anteckningar och klistra in följande textblock i det:</span><span class="sxs-lookup"><span data-stu-id="8a3cc-122">Open Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Owner,StorageQuota,Url,ResourceQuota,Template,TimeZoneID,Name
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/TeamSite01,25,EHS#1,10,Contoso Team Site
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/Blog01,25,BLOG#0,10,Contoso Blog
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Project01,25,PROJECTSITE#0,10,Project Alpha
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Community01,25,COMMUNITY#0,10,Community Site
```
<br/><span data-ttu-id="8a3cc-123">Där *klientorganisationen* är namnet på  klientorganisationen och ägare är användarnamnet för den användare i klientorganisationen som du vill tilldela rollen som primär administratör för webbplatssamlingen.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-123">Where *tenant* is the name of your tenant, and *owner* is the user name of the user on your tenant to whom you want to grant the role of primary site collection administrator.</span></span><br/><span data-ttu-id="8a3cc-124">(Du kan trycka på Ctrl+H när du använder Anteckningar för att massutbyt snabbare.)</span><span class="sxs-lookup"><span data-stu-id="8a3cc-124">(You can press Ctrl+H when you use Notepad to bulk replace faster.)</span></span><br/>

2. <span data-ttu-id="8a3cc-125">Spara filen på skrivbordet som **SiteCollections.csv**.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-125">Save the file on your desktop as **SiteCollections.csv**.</span></span><br/>

> [!TIP]
> <span data-ttu-id="8a3cc-126">Innan du använder den här eller någon annan .csv- eller Windows PowerShell-skriptfil är det bra att kontrollera att det inte finns några extra eller icke utskrivbara tecken.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-126">Before you use this or any other .csv or Windows PowerShell script file, it's a good practice to make sure that there are no extraneous or nonprinting characters.</span></span> <span data-ttu-id="8a3cc-127">Öppna filen i Word och klicka på styckeikonen i menyfliksområdet för att visa icke utskrivbara tecken.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-127">Open the file in Word, and in the ribbon, click the paragraph icon to show nonprinting characters.</span></span> <span data-ttu-id="8a3cc-128">Det ska inte finnas några extra icke utskrivbara tecken.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-128">There should be no extraneous nonprinting characters.</span></span> <span data-ttu-id="8a3cc-129">Det ska till exempel inte finnas några stycketecken utöver den sista i slutet av filen.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-129">For example, there should be no paragraph marks beyond the final one at the end of the file.</span></span>

### <a name="run-the-windows-powershell-command"></a><span data-ttu-id="8a3cc-130">Kör Windows PowerShell-kommandot</span><span class="sxs-lookup"><span data-stu-id="8a3cc-130">Run the Windows PowerShell command</span></span>

1. <span data-ttu-id="8a3cc-131">I Windows PowerShell-kommandotolken skriver du eller kopierar och klistrar in följande kommando och trycker på Retur:</span><span class="sxs-lookup"><span data-stu-id="8a3cc-131">At the Windows PowerShell prompt, type or copy and paste the following command, and press Enter:</span></span><br/>
```powershell
Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -ResourceQuota $_.ResourceQuota -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}
```
<br/><span data-ttu-id="8a3cc-132">Där *MyAlias* är lika med ditt användaralias.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-132">Where *MyAlias* equals your user alias.</span></span><br/>

2. <span data-ttu-id="8a3cc-133">Vänta tills Windows PowerShell-kommandot visas igen.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-133">Wait for the Windows PowerShell prompt to reappear.</span></span> <span data-ttu-id="8a3cc-134">Det kan ta några minuter.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-134">It might take a minute or two.</span></span><br/>

3. <span data-ttu-id="8a3cc-135">Skriv eller kopiera och klistra in följande cmdlet i kommandotolken för Windows PowerShell och tryck på Retur:</span><span class="sxs-lookup"><span data-stu-id="8a3cc-135">At the Windows PowerShell prompt, type or copy and paste the following cmdlet, and press Enter:</span></span><br/>

```powershell
Get-SPOSite -Detailed | Format-Table -AutoSize
```
<br/>

4. <span data-ttu-id="8a3cc-136">Observera de nya webbplatssamlingarna i listan.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-136">Note the new site collections in the list.</span></span> <span data-ttu-id="8a3cc-137">Med vår CSV-exempelfil ser du följande webbplatssamlingar: **TeamSite01,** **Blog01,** **Project01** och **Community01**</span><span class="sxs-lookup"><span data-stu-id="8a3cc-137">Using our example CSV file, you would see the following site collections: **TeamSite01**, **Blog01**, **Project01**, and **Community01**</span></span>

<span data-ttu-id="8a3cc-138">Nu är det allt.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-138">That’s it.</span></span> <span data-ttu-id="8a3cc-139">Du har skapat flera webbplatssamlingar med csv-filen du skapade och ett enda Windows PowerShell-kommando.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-139">You’ve created multiple site collections using the .csv file you created and a single Windows PowerShell command.</span></span> <span data-ttu-id="8a3cc-140">Nu är du redo att skapa och tilldela användare till webbplatserna.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-140">You’re now ready to create and assign users to these sites.</span></span>

## <a name="step-2-add-users-and-groups"></a><span data-ttu-id="8a3cc-141">Steg 2: Lägg till användare och grupper</span><span class="sxs-lookup"><span data-stu-id="8a3cc-141">Step 2: Add users and groups</span></span>

<span data-ttu-id="8a3cc-142">Nu ska du skapa användare och lägga till dem i en webbplatssamlingsgrupp.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-142">Now you’re going to create users and add them to a site collection group.</span></span> <span data-ttu-id="8a3cc-143">Sedan använder du en CSV-fil för att massuppladda nya grupper och användare.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-143">You will then use a .csv file to bulk upload new groups and users.</span></span>

<span data-ttu-id="8a3cc-144">Följande procedurer fortsätter att använda exempelwebbplatserna TeamSite01, Blog01, Project01 och Community01.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-144">The following procedures continue using the example sites TeamSite01, Blog01, Project01, and Community01.</span></span>

### <a name="create-csv-and-ps1-files"></a><span data-ttu-id="8a3cc-145">Skapa CSV- och PS1-filer</span><span class="sxs-lookup"><span data-stu-id="8a3cc-145">Create .csv and .ps1 files</span></span>

1. <span data-ttu-id="8a3cc-146">Öppna Anteckningar och klistra in följande textblock i det:</span><span class="sxs-lookup"><span data-stu-id="8a3cc-146">Open Notepad, and paste the following text block into it:</span></span><br/>

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
<br/><span data-ttu-id="8a3cc-147">Där *klientorganisationen* är lika med ditt klientnamn.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-147">Where *tenant* equals your tenant name.</span></span><br/>

2. <span data-ttu-id="8a3cc-148">Spara filen på skrivbordet som **GroupsAndPermissions.csv**.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-148">Save the file to your desktop as **GroupsAndPermissions.csv**.</span></span><br/>

3. <span data-ttu-id="8a3cc-149">Öppna en ny instans av Anteckningar och klistra in följande textblock i den:</span><span class="sxs-lookup"><span data-stu-id="8a3cc-149">Open a new instance of Notepad, and paste the following text block into it:</span></span><br/>

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
<br/><span data-ttu-id="8a3cc-150">Där *klientorganisationen* är lika med ditt *klientnamn och användarnamn* är lika med namnet på en befintlig användare.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-150">Where *tenant* equals your tenant name, and *username* equals the user name of an existing user.</span></span><br/>

4. <span data-ttu-id="8a3cc-151">Spara filen på skrivbordet som **Users.csv**.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-151">Save the file to your desktop as **Users.csv**.</span></span><br/>

5. <span data-ttu-id="8a3cc-152">Öppna en ny instans av Anteckningar och klistra in följande textblock i den:</span><span class="sxs-lookup"><span data-stu-id="8a3cc-152">Open a new instance of Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\users\MyAlias\desktop\Users.csv | where {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```
<br/><span data-ttu-id="8a3cc-153">Där MyAlias är lika med användarnamnet för den användare som är inloggad.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-153">Where MyAlias equals the user name of the user that is currently logged on.</span></span><br/>

6. <span data-ttu-id="8a3cc-154">Spara filen på skrivbordet som **UsersAndGroups.ps1**.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-154">Save the file to your desktop as **UsersAndGroups.ps1**.</span></span> <span data-ttu-id="8a3cc-155">Det här är ett enkelt Windows PowerShell-skript.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-155">This is a simple Windows PowerShell script.</span></span>

<span data-ttu-id="8a3cc-156">Nu kan du köra skriptet UsersAndGroup.ps1 lägga till användare och grupper i flera webbplatssamlingar.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-156">You’re now ready to run the UsersAndGroup.ps1 script to add users and groups to multiple site collections.</span></span>

### <a name="run-usersandgroupsps1-script"></a><span data-ttu-id="8a3cc-157">Kör UsersAndGroups.ps1 skript</span><span class="sxs-lookup"><span data-stu-id="8a3cc-157">Run UsersAndGroups.ps1 script</span></span>

1. <span data-ttu-id="8a3cc-158">Återgå till SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-158">Return to the SharePoint Online Management Shell.</span></span><br/>
2. <span data-ttu-id="8a3cc-159">I windows PowerShell-kommandotolken skriver du eller kopierar och klistrar in följande rad och trycker på Retur:</span><span class="sxs-lookup"><span data-stu-id="8a3cc-159">At the Windows PowerShell prompt, type or copy and paste the following line, and press Enter:</span></span><br/>
```powershell
Set-ExecutionPolicy Bypass
```
<br/>

3. <span data-ttu-id="8a3cc-160">Tryck på Y när du ombeds **bekräfta.**</span><span class="sxs-lookup"><span data-stu-id="8a3cc-160">At the confirmation prompt, press **Y**.</span></span><br/>

4. <span data-ttu-id="8a3cc-161">I windows PowerShell-kommandotolken skriver eller kopierar och klistrar du in följande och trycker på Retur:</span><span class="sxs-lookup"><span data-stu-id="8a3cc-161">At the Windows PowerShell prompt, type or copy and paste the following, and press Enter:</span></span><br/>

```powershell
c:\users\MyAlias\desktop\UsersAndGroups.ps1
```
<br/><span data-ttu-id="8a3cc-162">Där *MyAlias* är lika med ditt användarnamn.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-162">Where *MyAlias* equals your user name.</span></span><br/>

5. <span data-ttu-id="8a3cc-163">Vänta tills du får frågan att återgå innan du fortsätter.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-163">Wait for the prompt to return before moving on.</span></span> <span data-ttu-id="8a3cc-164">Du ser först hur grupperna visas när de skapas.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-164">You will first see the groups appear as they are created.</span></span> <span data-ttu-id="8a3cc-165">Sedan kommer du att se grupplistan upprepad när användare läggs till.</span><span class="sxs-lookup"><span data-stu-id="8a3cc-165">Then you will see the group list repeated as users are added.</span></span>

## <a name="see-also"></a><span data-ttu-id="8a3cc-166">Se även</span><span class="sxs-lookup"><span data-stu-id="8a3cc-166">See also</span></span>

[<span data-ttu-id="8a3cc-167">Ansluta till SharePoint Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a3cc-167">Connect to SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[<span data-ttu-id="8a3cc-168">Hantera SharePoint Online-webbplatsgrupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a3cc-168">Manage SharePoint Online site groups with PowerShell</span></span>](manage-sharepoint-site-groups-with-powershell.md)

[<span data-ttu-id="8a3cc-169">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a3cc-169">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="8a3cc-170">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8a3cc-170">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)