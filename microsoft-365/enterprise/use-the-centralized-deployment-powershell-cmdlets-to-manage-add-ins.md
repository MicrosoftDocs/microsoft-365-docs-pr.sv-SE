---
title: Use the Centralized Deployment PowerShell cmdlets to manage add-ins
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 1/24/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
f1.keywords:
- NOCSH
ms.assetid: 94f4e86d-b8e5-42dd-b558-e6092f830ec9
ms.custom:
- seo-marvel-apr2020
description: Använd PowerShell-cmdlets för centraliserad distribution för att hjälpa dig att distribuera och hantera Office-tillägg för din Microsoft 365-organisation.
ms.openlocfilehash: 659f12d2533601c4b2165a95ddbf59ea521945b8
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694807"
---
# <a name="use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins"></a><span data-ttu-id="0b49f-103">Use the Centralized Deployment PowerShell cmdlets to manage add-ins</span><span class="sxs-lookup"><span data-stu-id="0b49f-103">Use the Centralized Deployment PowerShell cmdlets to manage add-ins</span></span>

<span data-ttu-id="0b49f-104">Som en global administratör för Microsoft 365 kan du distribuera Office-tillägg till användare via funktionen centraliserad distribution (se [distribuera Office-tillägg i administrations centret](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)).</span><span class="sxs-lookup"><span data-stu-id="0b49f-104">As a Microsoft 365 global admin, you can deploy Office add-ins to users via the Centralized Deployment feature (see [Deploy Office Add-ins in the admin center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)).</span></span> <span data-ttu-id="0b49f-105">Utöver distribution av Office-tillägg via administrations centret för Microsoft 365 kan du också använda Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0b49f-105">In addition to deploying Office add-ins via the Microsoft 365 admin center, you can also use Microsoft PowerShell.</span></span> <span data-ttu-id="0b49f-106">Installera [modulen för centraliserad O365-distribution för Windows PowerShell](https://www.powershellgallery.com/packages/O365CentralizedAddInDeployment).</span><span class="sxs-lookup"><span data-stu-id="0b49f-106">Install the [O365 Centralized Add-In Deployment Module for Windows PowerShell](https://www.powershellgallery.com/packages/O365CentralizedAddInDeployment).</span></span> 

<span data-ttu-id="0b49f-107">När du har laddat ned modulen öppnar du ett vanligt fönster i Windows PowerShell och kör följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0b49f-107">After you download the module, open a regular Windows PowerShell window and run the following cmdlet:</span></span>

```powershell
 Import-Module -Name O365CentralizedAddInDeployment
```
    
## <a name="connect-using-your-admin-credentials"></a><span data-ttu-id="0b49f-108">Anslut med dina administratörs uppgifter</span><span class="sxs-lookup"><span data-stu-id="0b49f-108">Connect using your admin credentials</span></span>

<span data-ttu-id="0b49f-109">Innan du kan använda cmdlets för centraliserad distribution måste du logga in.</span><span class="sxs-lookup"><span data-stu-id="0b49f-109">Before you can use the Centralized Deployment cmdlets, you need to sign in.</span></span>
  
1. <span data-ttu-id="0b49f-110">Starta PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0b49f-110">Start PowerShell.</span></span>
    
2. <span data-ttu-id="0b49f-111">Anslut till PowerShell med företagets administratörs uppgifter.</span><span class="sxs-lookup"><span data-stu-id="0b49f-111">Connect to PowerShell by using your company admin credentials.</span></span> <span data-ttu-id="0b49f-112">Kör följande cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0b49f-112">Run the following cmdlet.</span></span>
    
  ```powershell
  Connect-OrganizationAddInService
  ```

3. <span data-ttu-id="0b49f-113">På sidan **ange inloggnings uppgifter** anger du dina Microsoft 365-autentiseringsuppgifter för global administratör.</span><span class="sxs-lookup"><span data-stu-id="0b49f-113">In the **Enter Credentials** page, enter your Microsoft 365 global admin credentials.</span></span> <span data-ttu-id="0b49f-114">Du kan också ange dina inloggnings uppgifter direkt i cmdleten.</span><span class="sxs-lookup"><span data-stu-id="0b49f-114">Alternately, you can enter your credentials directly into the cmdlet.</span></span> 
    
    <span data-ttu-id="0b49f-115">Kör följande cmdlet och ange dina autentiseringsuppgifter för företags administratör som ett PSCredential-objekt.</span><span class="sxs-lookup"><span data-stu-id="0b49f-115">Run the following cmdlet specifying your company admin credentials as a PSCredential object.</span></span>
    
  ```powershell
  $secpasswd = ConvertTo-SecureString "MyPassword" -AsPlainText -Force
  $mycredentials = New-Object System.Management.Automation.PSCredential ("serviceaccount@contoso.com", $secpasswd)
  Connect-OrganizationAddInService -Credential $mycredentials
  ```

> [!NOTE]
> <span data-ttu-id="0b49f-116">Mer information om hur du använder PowerShell finns i [ansluta till Microsoft 365 med PowerShell](https://go.microsoft.com/fwlink/p/?linkid=848585).</span><span class="sxs-lookup"><span data-stu-id="0b49f-116">For more information about using PowerShell, see [Connect to Microsoft 365 with PowerShell](https://go.microsoft.com/fwlink/p/?linkid=848585).</span></span> 
  
## <a name="upload-an-add-in-manifest"></a><span data-ttu-id="0b49f-117">Ladda upp ett tilläggs manifest</span><span class="sxs-lookup"><span data-stu-id="0b49f-117">Upload an add-in manifest</span></span>

<span data-ttu-id="0b49f-118">Kör cmdleten **New-OrganizationAdd** för att ladda upp ett tilläggs manifest från en sökväg, som kan vara en fil Sök väg eller URL.</span><span class="sxs-lookup"><span data-stu-id="0b49f-118">Run the **New-OrganizationAdd-In** cmdlet to upload an add-in manifest from a path, which can be either a file location or URL.</span></span> <span data-ttu-id="0b49f-119">I följande exempel visas en fil Sök väg för värdet för parametern  _ManifestPath_ .</span><span class="sxs-lookup"><span data-stu-id="0b49f-119">The following example shows a file location for the value of the  _ManifestPath_ parameter.</span></span> 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

<span data-ttu-id="0b49f-120">Du kan också köra cmdleten **New-OrganizationAdd** för att ladda upp ett tillägg och tilldela det till användare eller grupper direkt genom att använda parametern  _medlemmar_ , enligt följande exempel.</span><span class="sxs-lookup"><span data-stu-id="0b49f-120">You can also run the **New-OrganizationAdd-In** cmdlet to upload an add-in and assign it to users or groups directly by using the  _Members_ parameter, as shown in the following example.</span></span> <span data-ttu-id="0b49f-121">Avgränsa e-postadresserna för medlemmar med ett kommatecken.</span><span class="sxs-lookup"><span data-stu-id="0b49f-121">Separate the email addresses of members with a comma.</span></span> 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US' -Members  'KathyBonner@contoso.com', 'MaxHargrave@contoso.com'
```

## <a name="upload-an-add-in-from-the-office-store"></a><span data-ttu-id="0b49f-122">Ladda upp ett tillägg från Office Store</span><span class="sxs-lookup"><span data-stu-id="0b49f-122">Upload an add-in from the Office Store</span></span>

<span data-ttu-id="0b49f-123">Kör cmdleten **New-OrganizationAddIn** för att ladda upp en manifest fil från Office Store.</span><span class="sxs-lookup"><span data-stu-id="0b49f-123">Run the **New-OrganizationAddIn** cmdlet to upload a manifest from the Office Store.</span></span>
  
<span data-ttu-id="0b49f-124">I följande exempel anger cmdleten **New-OrganizationAddIn** in resursid för ett tillägg för en plats och innehålls marknad för USA.</span><span class="sxs-lookup"><span data-stu-id="0b49f-124">In the following example, the **New-OrganizationAddIn** cmdlet specifies the AssetId for an add-in for a United States location and content market.</span></span>
  
```powershell
New-OrganizationAddIn -AssetId 'WA104099688' -Locale 'en-US' -ContentMarket 'en-US'
```

<span data-ttu-id="0b49f-125">Om du vill veta värdet för  _resursid_ -parametern kan du kopiera den från URL-adressen till Office Store-webbplatsen för tillägget.</span><span class="sxs-lookup"><span data-stu-id="0b49f-125">To determine the value for the  _AssetId_ parameter, you can copy it from the URL of the Office Store webpage for the add-in.</span></span> <span data-ttu-id="0b49f-126">AssetIds börjar alltid med "WA" följt av ett tal.</span><span class="sxs-lookup"><span data-stu-id="0b49f-126">AssetIds always begin with "WA" followed by a number.</span></span> <span data-ttu-id="0b49f-127">I det föregående exemplet är källan för resursid-värdet för WA104099688 till exempel URL-adressen till Office Store för tillägget: [https://store.office.com/en-001/app.aspx?assetid=WA104099688](https://store.office.com/en-001/app.aspx?assetid=WA104099688) .</span><span class="sxs-lookup"><span data-stu-id="0b49f-127">For example, in the previous example, the source for the AssetId value of WA104099688 is the Office Store webpage URL for the add-in: [https://store.office.com/en-001/app.aspx?assetid=WA104099688](https://store.office.com/en-001/app.aspx?assetid=WA104099688).</span></span>
  
<span data-ttu-id="0b49f-128">Värdena för parametern  _locale_ och parametern  _ContentMarket_ är identiska och anger det land/den region som du försöker installera tillägget från.</span><span class="sxs-lookup"><span data-stu-id="0b49f-128">The values for the  _Locale_ parameter and the  _ContentMarket_ parameter are identical and indicate the country/region you're trying to install the add-in from.</span></span> <span data-ttu-id="0b49f-129">Formatet är en-US, fr-FR.</span><span class="sxs-lookup"><span data-stu-id="0b49f-129">The format is en-US, fr-FR.</span></span> <span data-ttu-id="0b49f-130">och så vidare.</span><span class="sxs-lookup"><span data-stu-id="0b49f-130">and so forth.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="0b49f-131">Tillägg som laddas upp från Office Store uppdateras automatiskt inom några dagar efter den senaste uppdateringen som är tillgänglig i Office Store.</span><span class="sxs-lookup"><span data-stu-id="0b49f-131">Add-ins uploaded from the Office Store will update automatically within a few days of the latest update being available on the Office Store.</span></span> 
  
## <a name="get-details-of-an-add-in"></a><span data-ttu-id="0b49f-132">Få information om ett tillägg</span><span class="sxs-lookup"><span data-stu-id="0b49f-132">Get details of an add-in</span></span>

<span data-ttu-id="0b49f-133">Kör cmdleten **Get-OrganizationAddIn** som visas nedan för att få information om alla tillägg som laddas upp till klient organisationen, med ett tilläggs produkt-ID.</span><span class="sxs-lookup"><span data-stu-id="0b49f-133">Run the **Get-OrganizationAddIn** cmdlet as shown below to get details of all add-ins uploaded to the tenant, included an add-in's product ID.</span></span>
  
```powershell
Get-OrganizationAddIn
```

<span data-ttu-id="0b49f-134">Kör cmdleten **Get-OrganizationAddIn** med ett värde för parametern  _ProductID_ för att ange vilket tillägg du vill hämta information om.</span><span class="sxs-lookup"><span data-stu-id="0b49f-134">Run the **Get-OrganizationAddIn** cmdlet with a value for the  _ProductId_ parameter to specify which add-in you want to retrieve details for.</span></span> 
  
```powershell
Get-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

<span data-ttu-id="0b49f-135">För att få fullständig information om alla tillägg plus de tilldelade användarna och grupperna får du till gång till cmdleten **Get-OrganizationAddIn** till format listen, enligt följande exempel.</span><span class="sxs-lookup"><span data-stu-id="0b49f-135">To get full details of all the add-ins plus the assigned users and groups, pipe the output of the **Get-OrganizationAddIn** cmdlet to the Format-List cmdlet, as shown in the following example.</span></span>
  
```powershell
foreach($G in (Get-organizationAddIn)){Get-OrganizationAddIn -ProductId $G.ProductId | Format-List}
```

## <a name="turn-on-or-turn-off-an-add-in"></a><span data-ttu-id="0b49f-136">Aktivera eller inaktivera ett tillägg</span><span class="sxs-lookup"><span data-stu-id="0b49f-136">Turn on or turn off an add-in</span></span>

<span data-ttu-id="0b49f-137">Om du vill inaktivera ett tillägg så att användare och grupper som har tilldelats till det inte längre kommer att ha åtkomst kör du cmdleten **set-OrganizationAddIn** med parametern  _ProductID_ och parametern  _Enabled_  `$false` , enligt följande exempel.</span><span class="sxs-lookup"><span data-stu-id="0b49f-137">To turn off an add-in so users and groups that are assigned to it will no longer have access, run the **Set-OrganizationAddIn** cmdlet with the  _ProductId_ parameter and the  _Enabled_ parameter set to  `$false`, as shown in the following example.</span></span>
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $false
```

<span data-ttu-id="0b49f-138">Om du vill aktivera ett tillägg igen kör du samma cmdlet med parametern  _Enabled_  `$true` .</span><span class="sxs-lookup"><span data-stu-id="0b49f-138">To turn an add-in back on, run the same cmdlet with the  _Enabled_ parameter set to  `$true`.</span></span>
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $true
```

## <a name="add-or-remove-users-from-an-add-in"></a><span data-ttu-id="0b49f-139">Lägga till eller ta bort användare från ett tillägg</span><span class="sxs-lookup"><span data-stu-id="0b49f-139">Add or remove users from an add-in</span></span>

<span data-ttu-id="0b49f-140">Om du vill lägga till användare och grupper i ett specifikt tillägg kör du cmdleten **set-OrganizationAddInAssignments** med parametrarna  _ProductID_,  _Add_och  _members_ .</span><span class="sxs-lookup"><span data-stu-id="0b49f-140">To add users and groups to a specific add-in, run the **Set-OrganizationAddInAssignments** cmdlet with the  _ProductId_,  _Add_, and  _Members_ parameters.</span></span> <span data-ttu-id="0b49f-141">Avgränsa e-postadresserna för medlemmar med ett kommatecken.</span><span class="sxs-lookup"><span data-stu-id="0b49f-141">Separate the email addresses of members with a comma.</span></span> 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Add -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

<span data-ttu-id="0b49f-142">Om du vill ta bort användare och grupper kör du samma cmdlet med parametern  _Remove_ .</span><span class="sxs-lookup"><span data-stu-id="0b49f-142">To remove users and groups, run the same cmdlet using the  _Remove_ parameter.</span></span> 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Remove -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

<span data-ttu-id="0b49f-143">Om du vill tilldela ett tillägg till alla användare i klient organisationen kör du samma cmdlet med parametern  _AssignToEveryone_ och värdet  `$true` .</span><span class="sxs-lookup"><span data-stu-id="0b49f-143">To assign an add-in to all users on the tenant, run the same cmdlet using the  _AssignToEveryone_ parameter with the value set to  `$true`.</span></span>
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $true
```

<span data-ttu-id="0b49f-144">Om du inte vill tilldela ett tillägg till alla och återgå till tidigare tilldelade användare och grupper kan du köra samma cmdlet och inaktivera parametern  _AssignToEveryone_ genom att ange värdet till  `$false` .</span><span class="sxs-lookup"><span data-stu-id="0b49f-144">To not assign an add-in to everyone and revert to the previously assigned users and groups, you can run the same cmdlet and turn off the  _AssignToEveryone_ parameter by setting its value to  `$false`.</span></span>
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $false
```

## <a name="update-an-add-in"></a><span data-ttu-id="0b49f-145">Uppdatera ett tillägg</span><span class="sxs-lookup"><span data-stu-id="0b49f-145">Update an add-in</span></span>

<span data-ttu-id="0b49f-146">Om du vill uppdatera ett tillägg från ett manifest kör du cmdleten **set-OrganizationAddIn** med parametrarna  _ProductID_,  _ManifestPath_och  _locale_ , enligt följande exempel.</span><span class="sxs-lookup"><span data-stu-id="0b49f-146">To update an add-in from a manifest, run the **Set-OrganizationAddIn** cmdlet with the  _ProductId_,  _ManifestPath_, and  _Locale_ parameters, as shown in the following example.</span></span> 
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

> [!NOTE]
> <span data-ttu-id="0b49f-147">Tillägg som laddas upp från Office Store uppdateras automatiskt inom några dagar efter den senaste uppdateringen som är tillgänglig i Office Store.</span><span class="sxs-lookup"><span data-stu-id="0b49f-147">Add-ins uploaded from the Office Store will update automatically within a few days of the latest update being available on the Office Store.</span></span> 
  
## <a name="delete-an-add-in"></a><span data-ttu-id="0b49f-148">Ta bort ett tillägg</span><span class="sxs-lookup"><span data-stu-id="0b49f-148">Delete an add-in</span></span>

<span data-ttu-id="0b49f-149">Om du vill ta bort ett tillägg kör du cmdleten **Remove-OrganizationAddIn** med parametern  _Produktnr_ enligt följande exempel.</span><span class="sxs-lookup"><span data-stu-id="0b49f-149">To delete an add-in, run the **Remove-OrganizationAddIn** cmdlet with the  _ProductId_ parameter, as shown in the following example.</span></span> 
  
```powershell
Remove-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

<!--
## Customize Microsoft Store add-ins for your organization

You must customize the add-in before you deploy it to your organization. Add-ins older than version 1.1 are not supported by this feature. 

We recommend that you deploy a customized add-in  to yourself first to make sure it works as expected before you deploy it to your entire organization.

Note also the following restrictions:
- All URLs must be absolute (include http or https) and valid.
- *DisplayName* must not exceed 125 characters 
- *DisplayName*, *Resources* and *AppDomains* must not include the following characters: 
 
    - \<
    -  \>
    -  ;
    -  =   

If you want to customize an add-in that has been deployed, you have to uninstall it in the admin center, and see [remove an add-in from local cache](#remove-an-add-in-from-local-cache) for steps to remove it from each computer it has been deployed to.

To customize an add-in, run the **Set –OrganizationAddInOverrides** cmdlet with the *ProductId* as a parameter, followed by the tag you want to overwrite and the new value. To find out how to get the *ProductId* see [get details of an add-in](#get-details-of-an-add-in) in this article. For example:

```powershell
 Set-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 -IconUrl "https://site.com/img.jpg" 
```
To customize multiple tags for an add-in, add those tags to the commandline:

```powershell
Set-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 -Hosts h1, 2 -DisplayName "New DocuSign W" -IconUrl "https://site.com/img.jpg" 
```

> [!IMPORTANT]
> You must apply multiple customized tags to one add-in as one command. If you customize tags one by one, only the last customization will be applied. Additionally, if you customize a tag by mistake, you must remove all customizations and start over.

### Tags you can customize

| Tag                  | Description          |
| :------------------- | :------------------- |
| \<IconURL>   </br>| The URL of the image used as the add-in’s icon (in admin center). </br> |
| \<DisplayName>| The title of the add-in  (in admin center).|
| \<Hosts>| List of apps that will support the add-in.|
| \<SourceLocation> | The source URL that the add-in will connect to.| 
| \<AppDomains> | A list of domains that the add-in can connect with. | 
| \<SupportURL>| The URL users can use to access help and support. | 
| \<Resources>  | This tag contains a number of elements including titles, tooltips, and icons of different sizes.| 
|
### Customize Resources tag

Any element in the <Resources> tag of the manifest can be customized dynamically. You first need to check the manifest to find the element id to which you want to assign a new value. The <Resources> tag looks like this:

```
<Resources>  
    <bt:Images> 
          <bt:Image id=”img16icon” DefaultValue=”https://site.com/img.jpg” 
    </bt:Images> 
</Resources> 
``` 
In this case, the element id for the image is “img16icon” and the value associated with it is “http:<i></i>//site.<i></i>com/img.jpg.”

Once you have identified the elements you want to customize, use the following command in Powershell to assign new values to the elements:

```powershell
Set-OrganizationAddInOverrides -Resources @{“ElementID” = “New Value”; “NextElementID” = “Next New Value”} 
```

You can customize as many elements with the command as you need to.

### Remove customization from an add-in

The only option currently available for deleting customizations is to delete all of them at once:

```powershell
Remove-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 
```

### View add-in customizations

To view a list of applied customizations, run the **Get-OrganizationAddInOverrides** cmdlet. If **Get-OrganizationAddInOverrides** is run without a *ProductId* then a list of all add-ins with applied overrides are returned.  

```powershell
Get-OrganizationAddInOverrides 
```
If ProductId is specified, then a list of overrides applied to that add-in is returned. 

```powershell
Get-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 
```

### Remove an add-in from local cache

If an add-in has been deployed, it has to be removed from the cache in each computer before it can be customized. To remive an add-in from cache:

1. Navigate to the “Users” folder in C:\ 
1. Go to your user folder
1. Navigate to AppData\Local\Microsoft\Office and select the folder associated with your version of Office
1. In the *Wef* folder delete the *Manifests* folder.

-->

## <a name="get-detailed-help-for-each-cmdlet"></a><span data-ttu-id="0b49f-150">Få detaljerad hjälp för varje cmdlet</span><span class="sxs-lookup"><span data-stu-id="0b49f-150">Get detailed help for each cmdlet</span></span>

<span data-ttu-id="0b49f-151">Du kan se detaljerad hjälp för varje cmdlet genom att använda cmdleten Get-Help.</span><span class="sxs-lookup"><span data-stu-id="0b49f-151">You can look at detailed help for each cmdlet by using the Get-help cmdlet.</span></span> <span data-ttu-id="0b49f-152">Följande cmdlet innehåller till exempel detaljerad information om cmdlet Remove-OrganizationAddIn.</span><span class="sxs-lookup"><span data-stu-id="0b49f-152">For example, the following cmdlet provides detailed information about the Remove-OrganizationAddIn cmdlet.</span></span>
  
```powershell
Get-help Remove-OrganizationAddIn -Full
```


