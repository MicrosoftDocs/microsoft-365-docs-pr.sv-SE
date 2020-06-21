---
title: Hantera vem som kan skapa grupper
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MSP160
- MST160
- MET150
- MOE150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Lär dig hur du styr vilka användare som kan skapa Microsoft 365-grupper.
ms.openlocfilehash: b64e7ac96c5a0e38583d00f8a61bd47c5304cf45
ms.sourcegitcommit: 589f78fc0f39aff9109959ded48d146cc32fc3c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44761680"
---
# <a name="manage-who-can-create-groups"></a><span data-ttu-id="cc011-103">Hantera vem som kan skapa grupper</span><span class="sxs-lookup"><span data-stu-id="cc011-103">Manage who can create Groups</span></span>

  
<span data-ttu-id="cc011-104">Eftersom det är så enkelt för användare att skapa Microsoft 365-grupper översvämmas du inte av begäranden om att skapa dem för andra personers räkning.</span><span class="sxs-lookup"><span data-stu-id="cc011-104">Because it's so easy for users to create Microsoft 365 groups, you aren't inundated with requests to create them on behalf of other people.</span></span> <span data-ttu-id="cc011-105">Beroende på vilken verksamhet du har kanske du ändå vill styra vilka som har möjlighet att skapa grupper.</span><span class="sxs-lookup"><span data-stu-id="cc011-105">Depending on your business, however, you might want to control who has the ability to create groups.</span></span>
  
<span data-ttu-id="cc011-106">I den hÃ¤r artikeln beskrivs hur du inaktiverar möjligheten att skapa grupper i alla Microsoft 365-tjänster som anvÃ¤nder grupper, inklusive:</span><span class="sxs-lookup"><span data-stu-id="cc011-106">This article explains how to disable the ability to create groups in all Microsoft 365 services that use groups, including:</span></span>
  
- <span data-ttu-id="cc011-107">Outlook</span><span class="sxs-lookup"><span data-stu-id="cc011-107">Outlook</span></span>
    
- <span data-ttu-id="cc011-108">SharePoint</span><span class="sxs-lookup"><span data-stu-id="cc011-108">SharePoint</span></span>
    
- <span data-ttu-id="cc011-109">Yammer</span><span class="sxs-lookup"><span data-stu-id="cc011-109">Yammer</span></span>
    
- <span data-ttu-id="cc011-110">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cc011-110">Microsoft Teams</span></span>

- <span data-ttu-id="cc011-111">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="cc011-111">Microsoft Stream</span></span>

- <span data-ttu-id="cc011-112">Planner</span><span class="sxs-lookup"><span data-stu-id="cc011-112">Planner</span></span>
    
- <span data-ttu-id="cc011-113">PowerBI (på andra)</span><span class="sxs-lookup"><span data-stu-id="cc011-113">PowerBI</span></span>

- <span data-ttu-id="cc011-114">Projekt för webben och färdplanen</span><span class="sxs-lookup"><span data-stu-id="cc011-114">Project for the web and Roadmap</span></span>
    
<span data-ttu-id="cc011-115">Du kan begränsa skapandet av Microsoft 365-grupper till medlemmarna i en viss säkerhetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="cc011-115">You can restrict Microsoft 365 group creation to the members of a particular security group.</span></span> <span data-ttu-id="cc011-116">Om du vill konfigurera detta använder du Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc011-116">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="cc011-117">Den här artikeln går igenom de nödvändiga stegen.</span><span class="sxs-lookup"><span data-stu-id="cc011-117">This article walks you through the needed steps.</span></span>
  
<span data-ttu-id="cc011-118">Stegen i den här artikeln hindrar inte medlemmar i vissa roller från att skapa grupper.</span><span class="sxs-lookup"><span data-stu-id="cc011-118">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="cc011-119">Globala administratörer kan skapa grupper på alla sätt, till exempel Microsoft 365-administrationscentret, Planner, Teams, Exchange och SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="cc011-119">Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="cc011-120">Andra roller kan skapa grupper med begränsade medel, listade nedan.</span><span class="sxs-lookup"><span data-stu-id="cc011-120">Other roles can create Groups via limited means, listed below.</span></span>
        
  - <span data-ttu-id="cc011-121">Exchange-administratör: Administrationscenter för Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="cc011-121">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="cc011-122">Support för partnernivå 1: Administrationscenter för Microsoft 365, Administrationscenter för Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="cc011-122">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="cc011-123">Support för partnernivå 2: Administrationscenter för Microsoft 365, Administrationscenter för Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="cc011-123">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="cc011-124">Katalogförfattare: Azure AD</span><span class="sxs-lookup"><span data-stu-id="cc011-124">Directory Writers: Azure AD</span></span>

  - <span data-ttu-id="cc011-125">SharePoint-administratör: Administrationscenter för SharePoint, Azure AD</span><span class="sxs-lookup"><span data-stu-id="cc011-125">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="cc011-126">Teams Service Administrator: Teams Admin center, Azure AD</span><span class="sxs-lookup"><span data-stu-id="cc011-126">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="cc011-127">Administratör för användarhantering: Microsoft 365 Admin center, Yammer, Azure AD</span><span class="sxs-lookup"><span data-stu-id="cc011-127">User Management Administrator: Microsoft 365 Admin center, Yammer, Azure AD</span></span>
     
<span data-ttu-id="cc011-128">Om du är medlem i en av dessa roller kan du skapa Microsoft 365-grupper för begränsade användare och sedan tilldela användaren som ägare till gruppen.</span><span class="sxs-lookup"><span data-stu-id="cc011-128">If you're a member of one of these roles, you can create Microsoft 365 groups for restricted users, and then assign the user as the owner of the group.</span></span> <span data-ttu-id="cc011-129">Användare som har den här rollen kan skapa anslutna grupper i Yammer, oavsett eventuella PowerShell-inställningar som kan förhindra skapande.</span><span class="sxs-lookup"><span data-stu-id="cc011-129">Users that have this role are able to create connected groups in Yammer, regardless of any PowerShell settings that might prevent creation.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="cc011-130">Licenskrav</span><span class="sxs-lookup"><span data-stu-id="cc011-130">Licensing requirements</span></span>

<span data-ttu-id="cc011-131">För att hantera vem som skapar grupper behöver följande personer Azure AD Premium-licenser eller Azure AD Basic EDU-licenser som tilldelats dem:</span><span class="sxs-lookup"><span data-stu-id="cc011-131">To manage who creates Groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="cc011-132">Administratören som konfigurerar inställningarna för gruppskapande</span><span class="sxs-lookup"><span data-stu-id="cc011-132">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="cc011-133">Medlemmarna i säkerhetsgruppen som får skapa grupper</span><span class="sxs-lookup"><span data-stu-id="cc011-133">The members of the security group who are allowed to create groups</span></span>

> [!NOTE]
> <span data-ttu-id="cc011-134">Mer information om hur du tilldelar Azure-licenser finns [i Tilldela eller ta bort licenser i Azure Active Directory-portalen.](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups)</span><span class="sxs-lookup"><span data-stu-id="cc011-134">See [Assign or remove licenses in the Azure Active Directory portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="cc011-135">Följande personer behöver inte Azure AD Premium- eller Azure AD Basic EDU-licenser som tilldelats dem:</span><span class="sxs-lookup"><span data-stu-id="cc011-135">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="cc011-136">Personer som är medlemmar i Microsoft 365-grupper och som inte har möjlighet att skapa andra grupper.</span><span class="sxs-lookup"><span data-stu-id="cc011-136">People who are members of Microsoft 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-microsoft-365-groups"></a><span data-ttu-id="cc011-137">Steg 1: Skapa en säkerhetsgrupp för användare som behöver skapa Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="cc011-137">Step 1: Create a security group for users who need to create Microsoft 365 groups</span></span>

<span data-ttu-id="cc011-138">Endast en säkerhetsgrupp i organisationen kan användas för att styra vem som kan skapa grupper.</span><span class="sxs-lookup"><span data-stu-id="cc011-138">Only one security group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="cc011-139">Men du kan kapsla andra säkerhetsgrupper som medlemmar i den här gruppen.</span><span class="sxs-lookup"><span data-stu-id="cc011-139">But, you can nest other security groups as members of this group.</span></span> <span data-ttu-id="cc011-140">Gruppen Tillåt gruppskapande är till exempel den angivna säkerhetsgruppen och grupperna Microsoft Planner Users och Exchange Online Users är medlemmar i den gruppen.</span><span class="sxs-lookup"><span data-stu-id="cc011-140">For example, the group named Allow Group Creation is the designated security group, and the groups named Microsoft Planner Users and Exchange Online Users are members of that group.</span></span>

<span data-ttu-id="cc011-141">Administratörer i de roller som anges ovan behöver inte vara medlemmar i den här gruppen: de behåller sin förmåga att skapa grupper.</span><span class="sxs-lookup"><span data-stu-id="cc011-141">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc011-142">Var noga med att använda en **säkerhetsgrupp** för att begränsa vem som kan skapa grupper.</span><span class="sxs-lookup"><span data-stu-id="cc011-142">Be sure to use a **security group** to restrict who can create groups.</span></span> <span data-ttu-id="cc011-143">Om du försöker använda en Microsoft 365-grupp kan medlemmarna inte skapa en grupp från SharePoint eftersom den söker efter en säkerhetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="cc011-143">If you try to use a Microsoft 365 group, members won't be able to create a group from SharePoint because it checks for a security group.</span></span> 
    
1. <span data-ttu-id="cc011-144">Gå till sidan **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppergrupper i</a> administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="cc011-144">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>

2. <span data-ttu-id="cc011-145">Klicka på **Lägg till en grupp**.</span><span class="sxs-lookup"><span data-stu-id="cc011-145">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="cc011-146">Välj **Säkerhet** som grupptyp.</span><span class="sxs-lookup"><span data-stu-id="cc011-146">Choose **Security** as the group type.</span></span> <span data-ttu-id="cc011-147">Kom ihåg namnet på gruppen!</span><span class="sxs-lookup"><span data-stu-id="cc011-147">Remember the name of the group!</span></span> <span data-ttu-id="cc011-148">Du behöver det senare.</span><span class="sxs-lookup"><span data-stu-id="cc011-148">You'll need it later.</span></span>
  
4. <span data-ttu-id="cc011-149">Slutför inrättandet av säkerhetsgruppen och lägg till personer eller andra säkerhetsgrupper som du vill ska kunna skapa grupper i organisationen.</span><span class="sxs-lookup"><span data-stu-id="cc011-149">Finish setting up the security group, adding people or other security groups who you want to be able to create groups in your org.</span></span>
    
<span data-ttu-id="cc011-150">Detaljerade instruktioner finns i [Skapa, redigera eller ta bort en säkerhetsgrupp i administrationscentret för Microsoft 365](../email/create-edit-or-delete-a-security-group.md).</span><span class="sxs-lookup"><span data-stu-id="cc011-150">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](../email/create-edit-or-delete-a-security-group.md).</span></span>
 
## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="cc011-151">Steg 2: Kör PowerShell-kommandon</span><span class="sxs-lookup"><span data-stu-id="cc011-151">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="cc011-152">Du måste använda förhandsversionen av [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (modulnamnet **AzureADPreview)** för att ändra inställningen för gäståtkomst på gruppnivå:</span><span class="sxs-lookup"><span data-stu-id="cc011-152">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="cc011-153">Om du inte har installerat någon version av Azure AD PowerShell-modulen tidigare läser [du Installera Azure AD-modulen](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) och följer instruktionerna för att installera den offentliga förhandsversionen.</span><span class="sxs-lookup"><span data-stu-id="cc011-153">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="cc011-154">Om du har installerat 2.0-versionen för allmän tillgänglighet av Azure AD PowerShell-modulen (AzureAD) måste du avinstallera den genom att `Uninstall-Module AzureAD` köras i PowerShell-sessionen och sedan installera förhandsversionen genom att köra `Install-Module AzureADPreview` .</span><span class="sxs-lookup"><span data-stu-id="cc011-154">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="cc011-155">Om du redan har installerat förhandsversionen kör du `Install-Module AzureADPreview` för att kontrollera att den är den senaste versionen av den här modulen.</span><span class="sxs-lookup"><span data-stu-id="cc011-155">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>



<span data-ttu-id="cc011-156">Kopiera skriptet nedan till en textredigerare, till exempel Anteckningar, eller [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span><span class="sxs-lookup"><span data-stu-id="cc011-156">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="cc011-157">Ersätt *\<SecurityGroupName\>* med namnet på den säkerhetsgrupp som du skapade.</span><span class="sxs-lookup"><span data-stu-id="cc011-157">Replace *\<SecurityGroupName\>* with the name of the security group that you created.</span></span> <span data-ttu-id="cc011-158">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="cc011-158">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="cc011-159">Spara filen som GroupCreators.ps1.</span><span class="sxs-lookup"><span data-stu-id="cc011-159">Save the file as GroupCreators.ps1.</span></span> 

<span data-ttu-id="cc011-160">I PowerShell-fönstret navigerar du till den plats där du sparade filen (skriv "CD <FileLocation> ").</span><span class="sxs-lookup"><span data-stu-id="cc011-160">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="cc011-161">Kör skriptet genom att skriva:</span><span class="sxs-lookup"><span data-stu-id="cc011-161">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="cc011-162">och [logga in med ditt administratörskonto](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) när du uppmanas att göra det.</span><span class="sxs-lookup"><span data-stu-id="cc011-162">and [sign in with your administrator account](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) when prompted.</span></span>

```PowerShell
$GroupName = "<SecurityGroupName>"
$AllowGroupCreation = "False"

Connect-AzureAD

$settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
if(!$settingsObjectID)
{
      $template = Get-AzureADDirectorySettingTemplate | Where-object {$_.displayname -eq "group.unified"}
    $settingsCopy = $template.CreateDirectorySetting()
    New-AzureADDirectorySetting -DirectorySetting $settingsCopy
    $settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
}

$settingsCopy = Get-AzureADDirectorySetting -Id $settingsObjectID
$settingsCopy["EnableGroupCreation"] = $AllowGroupCreation

if($GroupName)
{
    $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -Filter "DisplayName eq '$GroupName'").objectId
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

<span data-ttu-id="cc011-163">Den sista raden i skriptet visar de uppdaterade inställningarna:</span><span class="sxs-lookup"><span data-stu-id="cc011-163">The last line of the script will display the updated settings:</span></span>

![This is what your settings will look like when you're done.](../../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="cc011-165">Om du i framtiden vill ändra vilken säkerhetsgrupp som används kan du köra skriptet igen med namnet på den nya säkerhetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="cc011-165">If in the future you want to change which security group is used, you can rerun the script with the name of the new security group.</span></span>

<span data-ttu-id="cc011-166">Om du vill inaktivera begränsningen för gruppskapande och återigen tillåta alla användare att skapa grupper, ställer du in $GroupName till "" och $AllowGroupCreation till "True" och kör skriptet igen.</span><span class="sxs-lookup"><span data-stu-id="cc011-166">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>
    
## <a name="step-3-verify-that-it-works"></a><span data-ttu-id="cc011-167">Steg 3: Kontrollera att det fungerar</span><span class="sxs-lookup"><span data-stu-id="cc011-167">Step 3: Verify that it works</span></span>

<span data-ttu-id="cc011-168">Det kan ta trettio minuter eller mer att träda i kraft.</span><span class="sxs-lookup"><span data-stu-id="cc011-168">Changes can take thirty minutes or more to take effect.</span></span> <span data-ttu-id="cc011-169">Du kan verifiera de nya inställningarna genom att göra följande:</span><span class="sxs-lookup"><span data-stu-id="cc011-169">You can verify the new settings by doing the following:</span></span>

1. <span data-ttu-id="cc011-170">Logga in med ett användarkonto för någon som INTE ska ha möjlighet att skapa grupper.</span><span class="sxs-lookup"><span data-stu-id="cc011-170">Sign in with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="cc011-171">Det vill säga, de är inte medlemmar i den säkerhetsgrupp du skapade eller en administratör.</span><span class="sxs-lookup"><span data-stu-id="cc011-171">That is, they are not a member of the security group you created or an administrator.</span></span>
    
2. <span data-ttu-id="cc011-172">Välj panelen **Planerare.**</span><span class="sxs-lookup"><span data-stu-id="cc011-172">Select the **Planner** tile.</span></span> 
    
3. <span data-ttu-id="cc011-173">Välj Ny **plan** i den vänstra navigeringen i Planner för att skapa en plan.</span><span class="sxs-lookup"><span data-stu-id="cc011-173">In Planner, select **New Plan** in the left navigation to create a plan.</span></span> 
  
4. <span data-ttu-id="cc011-174">Du bör få ett meddelande om att planen och gruppskapandet är inaktiverat.</span><span class="sxs-lookup"><span data-stu-id="cc011-174">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="cc011-175">Försök med samma procedur igen med en medlem i säkerhetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="cc011-175">Try the same procedure again with a member of the security group.</span></span>

> [!NOTE]
> <span data-ttu-id="cc011-176">Om medlemmar i säkerhetsgruppen inte kan skapa grupper kontrollerar du att de inte blockeras via principen [för OWA-postlådeprincipen](https://go.microsoft.com/fwlink/?linkid=852135).</span><span class="sxs-lookup"><span data-stu-id="cc011-176">If members of the security group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="cc011-177">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="cc011-177">Related articles</span></span>

[<span data-ttu-id="cc011-178">Komma igång med Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc011-178">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="cc011-179">Konfigurera grupphantering med självbetjäning i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="cc011-179">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="cc011-180">Set-executionPolicy</span><span class="sxs-lookup"><span data-stu-id="cc011-180">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="cc011-181">Azure Active Directory-cmdletar för att konfigurera gruppinställningar</span><span class="sxs-lookup"><span data-stu-id="cc011-181">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
