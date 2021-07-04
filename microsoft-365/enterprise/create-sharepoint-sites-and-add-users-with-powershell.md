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
ms.openlocfilehash: 0c363df3edd40d810a0d8ca63090c0fec4c1c155
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288665"
---
# <a name="create-sharepoint-online-sites-and-add-users-with-powershell"></a><span data-ttu-id="9c246-103">Skapa SharePoint onlinewebbplatser och lägga till användare med PowerShell</span><span class="sxs-lookup"><span data-stu-id="9c246-103">Create SharePoint Online sites and add users with PowerShell</span></span>

<span data-ttu-id="9c246-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="9c246-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="9c246-105">När du använder PowerShell för Microsoft 365 för att skapa SharePoint Online-webbplatser och lägga till användare kan du snabbt och upprepade gånger utföra uppgifter mycket snabbare än du kan i Administrationscenter för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9c246-105">When you use PowerShell for Microsoft 365 to create SharePoint Online sites and add users, you can quickly and repeatedly perform tasks much faster than you can in the Microsoft 365 admin center.</span></span> <span data-ttu-id="9c246-106">Du kan också utföra uppgifter som inte går att utföra i Administrationscenter för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9c246-106">You can also perform tasks that are not possible to perform in the Microsoft 365 admin center.</span></span>

## <a name="connect-to-sharepoint-online"></a><span data-ttu-id="9c246-107">Anslut till SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9c246-107">Connect to SharePoint Online</span></span>

<span data-ttu-id="9c246-108">Procedurerna i det här avsnittet kräver att du ansluter till SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9c246-108">The procedures in this topic require you to connect to SharePoint Online.</span></span> <span data-ttu-id="9c246-109">Instruktioner finns i [Anslut för SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)</span><span class="sxs-lookup"><span data-stu-id="9c246-109">For instructions, see [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)</span></span>

## <a name="step-1-create-new-site-collections-using-powershell"></a><span data-ttu-id="9c246-110">Steg 1: Skapa nya webbplatssamlingar med PowerShell</span><span class="sxs-lookup"><span data-stu-id="9c246-110">Step 1: Create new site collections using PowerShell</span></span>

<span data-ttu-id="9c246-111">Skapa flera webbplatser med PowerShell och en .csv fil som du skapar med den exempelkod som tillhandahålls och Anteckningar.</span><span class="sxs-lookup"><span data-stu-id="9c246-111">Create multiple sites using PowerShell and a .csv file that you create using the example code provided and Notepad.</span></span> <span data-ttu-id="9c246-112">För den här proceduren ersätter du platshållarinformationen som visas inom hakparenteser med din egen webbplats- och klientspecifik information.</span><span class="sxs-lookup"><span data-stu-id="9c246-112">For this procedure, you’ll be replacing the placeholder information shown in brackets with your own site- and tenant-specific information.</span></span> <span data-ttu-id="9c246-113">Med den här processen kan du skapa en enda fil och köra ett enda PowerShell-kommando som använder den filen.</span><span class="sxs-lookup"><span data-stu-id="9c246-113">This process lets you create a single file and run a single PowerShell command that uses that file.</span></span> <span data-ttu-id="9c246-114">Det här gör att åtgärder som vidtas både går att upprepa och ta bort många, om inte alla, fel som kan komma från att skriva långa kommandon i SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9c246-114">This makes the actions taken both repeatable and portable and eliminates many, if not all, errors that can come from typing long commands into the SharePoint Online Management Shell.</span></span> <span data-ttu-id="9c246-115">Den här proceduren har två delar.</span><span class="sxs-lookup"><span data-stu-id="9c246-115">There are two parts to this procedure.</span></span> <span data-ttu-id="9c246-116">Först skapar du en .csv-fil och sedan refererar du till den .csv filen med PowerShell som använder innehållet för att skapa webbplatserna.</span><span class="sxs-lookup"><span data-stu-id="9c246-116">First you’ll create a .csv file, and then you’ll reference that .csv file using PowerShell, which will use its contents to create the sites.</span></span>

<span data-ttu-id="9c246-117">PowerShell-cmdleten importerar .csv-filen och rör den till en slinga inom klammerparenteser som läser den första raden i filen som kolumnrubriker.</span><span class="sxs-lookup"><span data-stu-id="9c246-117">The PowerShell cmdlet imports the .csv file and pipes it to a loop inside the curly brackets that reads the first line of the file as column headers.</span></span> <span data-ttu-id="9c246-118">PowerShell-cmdleten itereras sedan genom de återstående posterna, skapar en ny webbplatssamling för varje post och tilldelar egenskaper för webbplatssamlingen enligt kolumnrubrikerna.</span><span class="sxs-lookup"><span data-stu-id="9c246-118">The PowerShell cmdlet then iterates through the remaining records, creates a new site collection for each record, and assigns properties of the site collection according to the column headers.</span></span>

### <a name="create-a-csv-file"></a><span data-ttu-id="9c246-119">Skapa en .csv fil</span><span class="sxs-lookup"><span data-stu-id="9c246-119">Create a .csv file</span></span>

> [!NOTE]
> <span data-ttu-id="9c246-120">Resurskvotparametern fungerar bara på klassiska webbplatser.</span><span class="sxs-lookup"><span data-stu-id="9c246-120">The resource quota parameter works only on classic sites.</span></span> <span data-ttu-id="9c246-121">Om du använder den här parametern på en modern webbplats kan du få ett varningsmeddelande om att den har tagits bort.</span><span class="sxs-lookup"><span data-stu-id="9c246-121">If you use this parameter on a modern site, you may receive a warning message that it has been deprecated.</span></span>

1. <span data-ttu-id="9c246-122">Öppna Anteckningar och klistra in följande textblock i det:</span><span class="sxs-lookup"><span data-stu-id="9c246-122">Open Notepad, and paste the following text block into it:</span></span>

   ```powershell
   Owner,StorageQuota,Url,ResourceQuota,Template,TimeZoneID,Name
   owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/TeamSite01,25,EHS#1,10,Contoso Team Site
   owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/Blog01,25,BLOG#0,10,Contoso Blog
   owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Project01,25,PROJECTSITE#0,10,Project Alpha
   owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Community01,25,COMMUNITY#0,10,Community Site
   ```

   <span data-ttu-id="9c246-123">Där *klientorganisationen* är namnet på  klientorganisationen och ägare är användarnamnet för den användare i klientorganisationen som du vill tilldela rollen som primär administratör för webbplatssamlingen.</span><span class="sxs-lookup"><span data-stu-id="9c246-123">Where *tenant* is the name of your tenant, and *owner* is the user name of the user on your tenant to whom you want to grant the role of primary site collection administrator.</span></span>

   <span data-ttu-id="9c246-124">(Du kan trycka på Ctrl+H när du Anteckningar massutfyllnad snabbare.)</span><span class="sxs-lookup"><span data-stu-id="9c246-124">(You can press Ctrl+H when you use Notepad to bulk replace faster.)</span></span>

2. <span data-ttu-id="9c246-125">Spara filen på skrivbordet som **SiteCollections.csv**.</span><span class="sxs-lookup"><span data-stu-id="9c246-125">Save the file on your desktop as **SiteCollections.csv**.</span></span>

> [!TIP]
> <span data-ttu-id="9c246-126">Innan du använder den här .csv- eller Windows PowerShell-skriptfilen är det bra att kontrollera att det inte finns några extra eller icke utskrivbara tecken.</span><span class="sxs-lookup"><span data-stu-id="9c246-126">Before you use this or any other .csv or Windows PowerShell script file, it's a good practice to make sure that there are no extraneous or nonprinting characters.</span></span> <span data-ttu-id="9c246-127">Öppna filen i Word och klicka på styckeikonen i menyfliksområdet för att visa icke utskrivbara tecken.</span><span class="sxs-lookup"><span data-stu-id="9c246-127">Open the file in Word, and in the ribbon, click the paragraph icon to show nonprinting characters.</span></span> <span data-ttu-id="9c246-128">Det ska inte finnas några extra icke utskrivbara tecken.</span><span class="sxs-lookup"><span data-stu-id="9c246-128">There should be no extraneous nonprinting characters.</span></span> <span data-ttu-id="9c246-129">Det ska till exempel inte finnas några stycketecken utöver den sista i slutet av filen.</span><span class="sxs-lookup"><span data-stu-id="9c246-129">For example, there should be no paragraph marks beyond the final one at the end of the file.</span></span>

### <a name="run-the-windows-powershell-command"></a><span data-ttu-id="9c246-130">Kör kommandot Windows PowerShell kommando</span><span class="sxs-lookup"><span data-stu-id="9c246-130">Run the Windows PowerShell command</span></span>

1. <span data-ttu-id="9c246-131">Skriv eller kopiera Windows PowerShell klistra in följande kommando i kommandotolken och tryck på Retur:</span><span class="sxs-lookup"><span data-stu-id="9c246-131">At the Windows PowerShell prompt, type or copy and paste the following command, and press Enter:</span></span>

   ```powershell
   Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -ResourceQuota $_.ResourceQuota -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}
   ```

   <span data-ttu-id="9c246-132">Där *MyAlias* är lika med ditt användaralias.</span><span class="sxs-lookup"><span data-stu-id="9c246-132">Where *MyAlias* equals your user alias.</span></span>

2. <span data-ttu-id="9c246-133">Vänta tills Windows PowerShell visas igen.</span><span class="sxs-lookup"><span data-stu-id="9c246-133">Wait for the Windows PowerShell prompt to reappear.</span></span> <span data-ttu-id="9c246-134">Det kan ta några minuter.</span><span class="sxs-lookup"><span data-stu-id="9c246-134">It might take a minute or two.</span></span>

3. <span data-ttu-id="9c246-135">Skriv eller Windows PowerShell och klistra in följande cmdlet i kommandotolken och tryck på Retur:</span><span class="sxs-lookup"><span data-stu-id="9c246-135">At the Windows PowerShell prompt, type or copy and paste the following cmdlet, and press Enter:</span></span>

   ```powershell
   Get-SPOSite -Detailed | Format-Table -AutoSize
   ```

4. <span data-ttu-id="9c246-136">Observera de nya webbplatssamlingarna i listan.</span><span class="sxs-lookup"><span data-stu-id="9c246-136">Note the new site collections in the list.</span></span> <span data-ttu-id="9c246-137">Med vår CSV-exempelfil ser du följande webbplatssamlingar: **TeamSite01,** **Blog01,** **Project01** och **Community01**</span><span class="sxs-lookup"><span data-stu-id="9c246-137">Using our example CSV file, you would see the following site collections: **TeamSite01**, **Blog01**, **Project01**, and **Community01**</span></span>

<span data-ttu-id="9c246-138">Nu är det allt.</span><span class="sxs-lookup"><span data-stu-id="9c246-138">That’s it.</span></span> <span data-ttu-id="9c246-139">Du har skapat flera webbplatssamlingar med hjälp av .csv fil som du skapat och ett enda Windows PowerShell kommando.</span><span class="sxs-lookup"><span data-stu-id="9c246-139">You’ve created multiple site collections using the .csv file you created and a single Windows PowerShell command.</span></span> <span data-ttu-id="9c246-140">Nu är du redo att skapa och tilldela användare till webbplatserna.</span><span class="sxs-lookup"><span data-stu-id="9c246-140">You’re now ready to create and assign users to these sites.</span></span>

## <a name="step-2-add-users-and-groups"></a><span data-ttu-id="9c246-141">Steg 2: Lägg till användare och grupper</span><span class="sxs-lookup"><span data-stu-id="9c246-141">Step 2: Add users and groups</span></span>

<span data-ttu-id="9c246-142">Nu ska du skapa användare och lägga till dem i en webbplatssamlingsgrupp.</span><span class="sxs-lookup"><span data-stu-id="9c246-142">Now you’re going to create users and add them to a site collection group.</span></span> <span data-ttu-id="9c246-143">Sedan använder du en .csv för att massuppladda nya grupper och användare.</span><span class="sxs-lookup"><span data-stu-id="9c246-143">You will then use a .csv file to bulk upload new groups and users.</span></span>

<span data-ttu-id="9c246-144">Följande procedurer fortsätter att använda exempelwebbplatserna TeamSite01, Blog01, Project01 och Community01.</span><span class="sxs-lookup"><span data-stu-id="9c246-144">The following procedures continue using the example sites TeamSite01, Blog01, Project01, and Community01.</span></span>

### <a name="create-csv-and-ps1-files"></a><span data-ttu-id="9c246-145">Skapa .csv och .ps1 filer</span><span class="sxs-lookup"><span data-stu-id="9c246-145">Create .csv and .ps1 files</span></span>

1. <span data-ttu-id="9c246-146">Öppna Anteckningar och klistra in följande textblock i det:</span><span class="sxs-lookup"><span data-stu-id="9c246-146">Open Notepad, and paste the following text block into it:</span></span>

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

   <span data-ttu-id="9c246-147">Där *klientorganisationen* är lika med ditt klientnamn.</span><span class="sxs-lookup"><span data-stu-id="9c246-147">Where *tenant* equals your tenant name.</span></span>

2. <span data-ttu-id="9c246-148">Spara filen på skrivbordet som **GroupsAndPermissions.csv**.</span><span class="sxs-lookup"><span data-stu-id="9c246-148">Save the file to your desktop as **GroupsAndPermissions.csv**.</span></span>

3. <span data-ttu-id="9c246-149">Öppna en ny instans Anteckningar och klistra in följande textblock i den:</span><span class="sxs-lookup"><span data-stu-id="9c246-149">Open a new instance of Notepad, and paste the following text block into it:</span></span>

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

   <span data-ttu-id="9c246-150">Där *klientorganisationen* är lika med ditt *klientnamn och användarnamn* är lika med namnet på en befintlig användare.</span><span class="sxs-lookup"><span data-stu-id="9c246-150">Where *tenant* equals your tenant name, and *username* equals the user name of an existing user.</span></span>

4. <span data-ttu-id="9c246-151">Spara filen på skrivbordet som **Users.csv**.</span><span class="sxs-lookup"><span data-stu-id="9c246-151">Save the file to your desktop as **Users.csv**.</span></span>

5. <span data-ttu-id="9c246-152">Öppna en ny instans Anteckningar och klistra in följande textblock i den:</span><span class="sxs-lookup"><span data-stu-id="9c246-152">Open a new instance of Notepad, and paste the following text block into it:</span></span>

   ```powershell
   Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
   Import-Csv C:\users\MyAlias\desktop\Users.csv | where {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
   ```

   <span data-ttu-id="9c246-153">Där MyAlias är lika med användarnamnet för den användare som är inloggad.</span><span class="sxs-lookup"><span data-stu-id="9c246-153">Where MyAlias equals the user name of the user that is currently logged on.</span></span>

6. <span data-ttu-id="9c246-154">Spara filen på skrivbordet som **UsersAndGroups.ps1**.</span><span class="sxs-lookup"><span data-stu-id="9c246-154">Save the file to your desktop as **UsersAndGroups.ps1**.</span></span> <span data-ttu-id="9c246-155">Det här är ett enkelt Windows PowerShell skript.</span><span class="sxs-lookup"><span data-stu-id="9c246-155">This is a simple Windows PowerShell script.</span></span>

<span data-ttu-id="9c246-156">Nu kan du köra skriptet UsersAndGroup.ps1 lägga till användare och grupper i flera webbplatssamlingar.</span><span class="sxs-lookup"><span data-stu-id="9c246-156">You’re now ready to run the UsersAndGroup.ps1 script to add users and groups to multiple site collections.</span></span>

### <a name="run-usersandgroupsps1-script"></a><span data-ttu-id="9c246-157">Kör UsersAndGroups.ps1 skript</span><span class="sxs-lookup"><span data-stu-id="9c246-157">Run UsersAndGroups.ps1 script</span></span>

1. <span data-ttu-id="9c246-158">Gå tillbaka till SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9c246-158">Return to the SharePoint Online Management Shell.</span></span>

2. <span data-ttu-id="9c246-159">Skriv eller Windows PowerShell klistra in följande rad i rutan och tryck på Retur:</span><span class="sxs-lookup"><span data-stu-id="9c246-159">At the Windows PowerShell prompt, type or copy and paste the following line, and press Enter:</span></span>

   ```powershell
   Set-ExecutionPolicy Bypass
   ```

3. <span data-ttu-id="9c246-160">Tryck på Y när du ombeds **bekräfta.**</span><span class="sxs-lookup"><span data-stu-id="9c246-160">At the confirmation prompt, press **Y**.</span></span>

4. <span data-ttu-id="9c246-161">Skriv eller kopiera Windows PowerShell klistra in följande i kommandotolken och tryck på Retur:</span><span class="sxs-lookup"><span data-stu-id="9c246-161">At the Windows PowerShell prompt, type or copy and paste the following, and press Enter:</span></span>

   ```powershell
   c:\users\MyAlias\desktop\UsersAndGroups.ps1
   ```

   <span data-ttu-id="9c246-162">Där *MyAlias* är lika med ditt användarnamn.</span><span class="sxs-lookup"><span data-stu-id="9c246-162">Where *MyAlias* equals your user name.</span></span>

5. <span data-ttu-id="9c246-163">Vänta tills du får frågan att återgå innan du fortsätter.</span><span class="sxs-lookup"><span data-stu-id="9c246-163">Wait for the prompt to return before moving on.</span></span> <span data-ttu-id="9c246-164">Du ser först hur grupperna visas när de skapas.</span><span class="sxs-lookup"><span data-stu-id="9c246-164">You will first see the groups appear as they are created.</span></span> <span data-ttu-id="9c246-165">Sedan kommer du att se grupplistan upprepad när användare läggs till.</span><span class="sxs-lookup"><span data-stu-id="9c246-165">Then you will see the group list repeated as users are added.</span></span>

## <a name="see-also"></a><span data-ttu-id="9c246-166">Se även</span><span class="sxs-lookup"><span data-stu-id="9c246-166">See also</span></span>

[<span data-ttu-id="9c246-167">Anslut till SharePoint Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="9c246-167">Connect to SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

[<span data-ttu-id="9c246-168">Hantera SharePoint onlinewebbplatsgrupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="9c246-168">Manage SharePoint Online site groups with PowerShell</span></span>](manage-sharepoint-site-groups-with-powershell.md)

[<span data-ttu-id="9c246-169">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="9c246-169">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)

[<span data-ttu-id="9c246-170">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9c246-170">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
