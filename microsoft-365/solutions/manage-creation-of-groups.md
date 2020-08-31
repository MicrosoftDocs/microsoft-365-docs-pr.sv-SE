---
title: Hantera vilka som kan skapa Microsoft 365-grupper
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Lär dig hur du styr vilka användare som kan skapa Microsoft 365-grupper.
ms.openlocfilehash: d6e6c6d9caff2ac7c13d03dad97b73906a509f46
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307865"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a><span data-ttu-id="d30a6-103">Hantera vilka som kan skapa Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="d30a6-103">Manage who can create Microsoft 365 Groups</span></span>

<span data-ttu-id="d30a6-104">Som standard kan alla användare skapa Microsoft 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="d30a6-104">By default, all users can create Microsoft 365 groups.</span></span> <span data-ttu-id="d30a6-105">Det här är den rekommenderade metoden eftersom användarna kan börja samar beta utan att behöva använda det.</span><span class="sxs-lookup"><span data-stu-id="d30a6-105">This is the recommended approach because it allows users to start collaborating without requiring assistance from IT.</span></span>

<span data-ttu-id="d30a6-106">Om ditt företag kräver att du begränsar vem som kan skapa grupper kan du göra det genom att följa anvisningarna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="d30a6-106">If your business requires that you restrict who can create groups, you can do so by following the procedures in this article.</span></span> <span data-ttu-id="d30a6-107">När du begränsar vem som kan skapa en grupp påverkas alla tjänster som är beroende av grupper för åtkomst, till exempel:</span><span class="sxs-lookup"><span data-stu-id="d30a6-107">When you limit who can create a group, it affects all services that rely on groups for access, including:</span></span>

- <span data-ttu-id="d30a6-108">Outlook</span><span class="sxs-lookup"><span data-stu-id="d30a6-108">Outlook</span></span>
    
- <span data-ttu-id="d30a6-109">SharePoint</span><span class="sxs-lookup"><span data-stu-id="d30a6-109">SharePoint</span></span>
    
- <span data-ttu-id="d30a6-110">Yammer</span><span class="sxs-lookup"><span data-stu-id="d30a6-110">Yammer</span></span>
    
- <span data-ttu-id="d30a6-111">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d30a6-111">Microsoft Teams</span></span>

- <span data-ttu-id="d30a6-112">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="d30a6-112">Microsoft Stream</span></span>

- <span data-ttu-id="d30a6-113">Planner</span><span class="sxs-lookup"><span data-stu-id="d30a6-113">Planner</span></span>
    
- <span data-ttu-id="d30a6-114">PowerBI (klassisk)</span><span class="sxs-lookup"><span data-stu-id="d30a6-114">PowerBI (classic)</span></span>
    
- <span data-ttu-id="d30a6-115">Projekt för webben/översikt</span><span class="sxs-lookup"><span data-stu-id="d30a6-115">Project for the web / Roadmap</span></span>
    
<span data-ttu-id="d30a6-116">Du kan förhindra att Microsoft 365-grupper skapas för medlemmar i en viss säkerhets grupp.</span><span class="sxs-lookup"><span data-stu-id="d30a6-116">You can restrict Microsoft 365 Group creation to the members of a particular security group.</span></span> <span data-ttu-id="d30a6-117">För att konfigurera det här använder du Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d30a6-117">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="d30a6-118">I den här artikeln får du stegvisa instruktioner.</span><span class="sxs-lookup"><span data-stu-id="d30a6-118">This article walks you through the needed steps.</span></span>
  
<span data-ttu-id="d30a6-119">Åtgärderna i den här artikeln hindrar inte medlemmar från vissa roller från att skapa grupper.</span><span class="sxs-lookup"><span data-stu-id="d30a6-119">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="d30a6-120">Office 365 globala administratörer kan skapa grupper på något sätt, till exempel Microsoft 365 Admin Center, Planner, team, Exchange och SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d30a6-120">Office 365 Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="d30a6-121">Andra roller kan skapa grupper via begränsade sätt, i listan nedan.</span><span class="sxs-lookup"><span data-stu-id="d30a6-121">Other roles can create Groups via limited means, listed below.</span></span>
        
  - <span data-ttu-id="d30a6-122">Exchange-administratör: administrations Center för Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="d30a6-122">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="d30a6-123">Support för partner nivå 1: Microsoft 365 Admin Center, Exchange Admin Center, Azure AD</span><span class="sxs-lookup"><span data-stu-id="d30a6-123">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="d30a6-124">Partner nivå 2: support för Microsoft 365 Admin Center, Exchange Admin Center, Azure AD</span><span class="sxs-lookup"><span data-stu-id="d30a6-124">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="d30a6-125">Katalog författare: Azure AD</span><span class="sxs-lookup"><span data-stu-id="d30a6-125">Directory Writers: Azure AD</span></span>

  - <span data-ttu-id="d30a6-126">SharePoint-administratör: administrations Center för SharePoint, Azure AD</span><span class="sxs-lookup"><span data-stu-id="d30a6-126">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="d30a6-127">Team tjänst administratör: administrations Center för Teams, Azure AD</span><span class="sxs-lookup"><span data-stu-id="d30a6-127">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="d30a6-128">Användar hanterings administratör: Microsoft 365 Admin Center, Yammer, Azure AD</span><span class="sxs-lookup"><span data-stu-id="d30a6-128">User Management Administrator: Microsoft 365 Admin center, Yammer, Azure AD</span></span>
     
<span data-ttu-id="d30a6-129">Om du är medlem i en av de här rollerna kan du skapa Microsoft 365-grupper för användare med begränsad behörighet och sedan koppla användaren till gruppen.</span><span class="sxs-lookup"><span data-stu-id="d30a6-129">If you're a member of one of these roles, you can create Microsoft 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="d30a6-130">Licens krav</span><span class="sxs-lookup"><span data-stu-id="d30a6-130">Licensing requirements</span></span>

<span data-ttu-id="d30a6-131">För att hantera vem som skapar grupper måste följande personer ha Azure AD Premium-licenser eller Azure AD Basic EDU-licenser tilldelade till dem:</span><span class="sxs-lookup"><span data-stu-id="d30a6-131">To manage who creates groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="d30a6-132">Administratören som konfigurerar dessa inställningar för grupp skapande</span><span class="sxs-lookup"><span data-stu-id="d30a6-132">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="d30a6-133">Medlemmar i säkerhets gruppen som får skapa grupper</span><span class="sxs-lookup"><span data-stu-id="d30a6-133">The members of the security group who are allowed to create groups</span></span>
 
> [!NOTE]
> <span data-ttu-id="d30a6-134">Se [tilldela eller ta bort licenser i Azure Active Directory-portalen](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) för mer information om hur du tilldelar Azure-licenser.</span><span class="sxs-lookup"><span data-stu-id="d30a6-134">See [Assign or remove licenses in the Azure Active Directory portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="d30a6-135">Följande personer behöver inte Azure AD Premium-eller Azure AD Basic EDU-licenser tilldelade till dem:</span><span class="sxs-lookup"><span data-stu-id="d30a6-135">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="d30a6-136">Personer som är medlemmar i Microsoft 365-grupper och som inte har möjlighet att skapa andra grupper.</span><span class="sxs-lookup"><span data-stu-id="d30a6-136">People who are members of Microsoft 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-microsoft-365-groups"></a><span data-ttu-id="d30a6-137">Steg 1: skapa en säkerhets grupp för användare som behöver skapa Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="d30a6-137">Step 1: Create a security group for users who need to create Microsoft 365 groups</span></span>

<span data-ttu-id="d30a6-138">Endast en säkerhets grupp i organisationen kan användas för att styra vilka som kan skapa grupper.</span><span class="sxs-lookup"><span data-stu-id="d30a6-138">Only one security group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="d30a6-139">Men du kan kapsla andra säkerhets grupper som medlemmar i den här gruppen.</span><span class="sxs-lookup"><span data-stu-id="d30a6-139">But, you can nest other security groups as members of this group.</span></span>

<span data-ttu-id="d30a6-140">Administratörer i de roller som visas ovan behöver inte vara medlemmar i den här gruppen: de behåller sin möjlighet att skapa grupper.</span><span class="sxs-lookup"><span data-stu-id="d30a6-140">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d30a6-141">Använd en **säkerhets grupp** för att begränsa vem som kan skapa grupper.</span><span class="sxs-lookup"><span data-stu-id="d30a6-141">Be sure to use a **security group** to restrict who can create groups.</span></span> <span data-ttu-id="d30a6-142">Det går inte att använda en Microsoft 365-grupp.</span><span class="sxs-lookup"><span data-stu-id="d30a6-142">Using a Microsoft 365 group is not supported.</span></span> 
    
1. <span data-ttu-id="d30a6-143">Gå till [sidan grupper](https://admin.microsoft.com/adminportal/home#/groups)i administrations centret.</span><span class="sxs-lookup"><span data-stu-id="d30a6-143">In the admin center, go to the [Groups page](https://admin.microsoft.com/adminportal/home#/groups).</span></span>

2. <span data-ttu-id="d30a6-144">Klicka på **Lägg till en grupp**.</span><span class="sxs-lookup"><span data-stu-id="d30a6-144">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="d30a6-145">Välj **säkerhet** som grupptyp.</span><span class="sxs-lookup"><span data-stu-id="d30a6-145">Choose **Security** as the group type.</span></span> <span data-ttu-id="d30a6-146">Kom ihåg namnet på gruppen!</span><span class="sxs-lookup"><span data-stu-id="d30a6-146">Remember the name of the group!</span></span> <span data-ttu-id="d30a6-147">Du behöver det senare.</span><span class="sxs-lookup"><span data-stu-id="d30a6-147">You'll need it later.</span></span>
  
4. <span data-ttu-id="d30a6-148">Slutföra konfigurationen av säkerhets gruppen, lägga till personer eller andra säkerhets grupper som du vill kunna skapa grupper i din organisation.</span><span class="sxs-lookup"><span data-stu-id="d30a6-148">Finish setting up the security group, adding people or other security groups who you want to be able to create groups in your org.</span></span>
    
<span data-ttu-id="d30a6-149">Detaljerade anvisningar finns i [skapa, redigera eller ta bort en säkerhets grupp i administrations centret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group).</span><span class="sxs-lookup"><span data-stu-id="d30a6-149">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group).</span></span>
 
## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="d30a6-150">Steg 2: Kör PowerShell-kommandon</span><span class="sxs-lookup"><span data-stu-id="d30a6-150">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="d30a6-151">Du måste använda för hands versionen av [Azure Active Directory PowerShell för Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (modul name **AzureADPreview**) för att ändra inställningen för gäst åtkomst på grupp nivå:</span><span class="sxs-lookup"><span data-stu-id="d30a6-151">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="d30a6-152">Om du inte har installerat någon version av Azure AD PowerShell-modulen förut läser du [Installera Azure AD-modulen](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) och följa anvisningarna för att installera den offentliga för hands versionen.</span><span class="sxs-lookup"><span data-stu-id="d30a6-152">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="d30a6-153">Om du har 2,0 General Availability-versionen av Azure AD PowerShell-modulen (AzureAD) installerad måste du avinstallera den genom att köra `Uninstall-Module AzureAD` i din PowerShell-session och sedan installera för hands versionen genom att köra `Install-Module AzureADPreview` .</span><span class="sxs-lookup"><span data-stu-id="d30a6-153">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="d30a6-154">Om du redan har installerat för hands versionen måste du `Install-Module AzureADPreview` kontrol lera att den är den senaste versionen av den här modulen.</span><span class="sxs-lookup"><span data-stu-id="d30a6-154">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

<span data-ttu-id="d30a6-155">Kopiera skriptet nedan till en text redigerare, till exempel anteckningar eller [Windows POWERSHELL ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span><span class="sxs-lookup"><span data-stu-id="d30a6-155">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="d30a6-156">Ersätt *\<SecurityGroupName\>* med namnet på den säkerhets grupp som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="d30a6-156">Replace *\<SecurityGroupName\>* with the name of the security group that you created.</span></span> <span data-ttu-id="d30a6-157">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="d30a6-157">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="d30a6-158">Spara filen som GroupCreators.ps1.</span><span class="sxs-lookup"><span data-stu-id="d30a6-158">Save the file as GroupCreators.ps1.</span></span> 

<span data-ttu-id="d30a6-159">Gå till den plats där du sparade filen i PowerShell-fönstret (Skriv "CD <FileLocation> ").</span><span class="sxs-lookup"><span data-stu-id="d30a6-159">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="d30a6-160">Kör skriptet genom att skriva:</span><span class="sxs-lookup"><span data-stu-id="d30a6-160">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="d30a6-161">och [Logga in med ditt administratörs konto](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) när du uppmanas till det.</span><span class="sxs-lookup"><span data-stu-id="d30a6-161">and [sign in with your administrator account](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) when prompted.</span></span>

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
    $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -SearchString $GroupName).objectid
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

<span data-ttu-id="d30a6-162">Den sista raden i skriptet visar de uppdaterade inställningarna:</span><span class="sxs-lookup"><span data-stu-id="d30a6-162">The last line of the script will display the updated settings:</span></span>

![This is what your settings will look like when you're done.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="d30a6-164">Om du i framtiden vill ändra vilken säkerhets grupp som används kan du köra skriptet igen med namnet på den nya säkerhets gruppen.</span><span class="sxs-lookup"><span data-stu-id="d30a6-164">If in the future you want to change which security group is used, you can rerun the script with the name of the new security group.</span></span>

<span data-ttu-id="d30a6-165">Om du vill inaktivera begränsningen för grupp skapande och återigen tillåta alla användare att skapa grupper kan du ange $GroupName till "" och $AllowGroupCreation till "true" och köra skriptet igen.</span><span class="sxs-lookup"><span data-stu-id="d30a6-165">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>
    
## <a name="step-3-verify-that-it-works"></a><span data-ttu-id="d30a6-166">Steg 3: Kontrollera att det fungerar</span><span class="sxs-lookup"><span data-stu-id="d30a6-166">Step 3: Verify that it works</span></span>

<span data-ttu-id="d30a6-167">Det kan ta en halvtimme eller mer att göra ändringar.</span><span class="sxs-lookup"><span data-stu-id="d30a6-167">Changes can take thirty minutes or more to take effect.</span></span> <span data-ttu-id="d30a6-168">Du kan kontrol lera de nya inställningarna genom att göra följande:</span><span class="sxs-lookup"><span data-stu-id="d30a6-168">You can verify the new settings by doing the following:</span></span>

1. <span data-ttu-id="d30a6-169">Logga in på Microsoft 365 med ett användar konto hos någon som inte borde ha möjlighet att skapa grupper.</span><span class="sxs-lookup"><span data-stu-id="d30a6-169">Sign in to Microsoft 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="d30a6-170">De är inte medlemmar i säkerhets gruppen som du skapade eller en administratör.</span><span class="sxs-lookup"><span data-stu-id="d30a6-170">That is, they are not a member of the security group you created or an administrator.</span></span>
    
2. <span data-ttu-id="d30a6-171">Välj panelen **Planner** .</span><span class="sxs-lookup"><span data-stu-id="d30a6-171">Select the **Planner** tile.</span></span> 
    
3. <span data-ttu-id="d30a6-172">I Planner väljer du **nytt abonnemang** i det vänstra navigerings fältet för att skapa en plan.</span><span class="sxs-lookup"><span data-stu-id="d30a6-172">In Planner, select **New Plan** in the left navigation to create a plan.</span></span> 
  
4. <span data-ttu-id="d30a6-173">Du bör få ett meddelande om att planen och skapandet av gruppen är inaktiverat.</span><span class="sxs-lookup"><span data-stu-id="d30a6-173">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="d30a6-174">Prova samma procedur igen med en medlem i säkerhets gruppen.</span><span class="sxs-lookup"><span data-stu-id="d30a6-174">Try the same procedure again with a member of the security group.</span></span>

> [!NOTE]
> <span data-ttu-id="d30a6-175">Om medlemmar i säkerhets gruppen inte kan skapa grupper kontrollerar du att de inte blockeras genom sin princip för [OWA-postlådan](https://go.microsoft.com/fwlink/?linkid=852135).</span><span class="sxs-lookup"><span data-stu-id="d30a6-175">If members of the security group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="d30a6-176">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="d30a6-176">Related articles</span></span>

[<span data-ttu-id="d30a6-177">Komma igång med Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="d30a6-177">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="d30a6-178">Konfigurera hantering av self-service i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d30a6-178">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="d30a6-179">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="d30a6-179">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="d30a6-180">Azure Active Directory-cmdlets för konfiguration av grupp inställningar</span><span class="sxs-lookup"><span data-stu-id="d30a6-180">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
