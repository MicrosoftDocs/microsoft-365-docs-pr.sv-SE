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
# <a name="use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins"></a>Use the Centralized Deployment PowerShell cmdlets to manage add-ins

Som en global administratör för Microsoft 365 kan du distribuera Office-tillägg till användare via funktionen centraliserad distribution (se [distribuera Office-tillägg i administrations centret](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)). Utöver distribution av Office-tillägg via administrations centret för Microsoft 365 kan du också använda Microsoft PowerShell. Installera [modulen för centraliserad O365-distribution för Windows PowerShell](https://www.powershellgallery.com/packages/O365CentralizedAddInDeployment). 

När du har laddat ned modulen öppnar du ett vanligt fönster i Windows PowerShell och kör följande cmdlet:

```powershell
 Import-Module -Name O365CentralizedAddInDeployment
```
    
## <a name="connect-using-your-admin-credentials"></a>Anslut med dina administratörs uppgifter

Innan du kan använda cmdlets för centraliserad distribution måste du logga in.
  
1. Starta PowerShell.
    
2. Anslut till PowerShell med företagets administratörs uppgifter. Kör följande cmdlet.
    
  ```powershell
  Connect-OrganizationAddInService
  ```

3. På sidan **ange inloggnings uppgifter** anger du dina Microsoft 365-autentiseringsuppgifter för global administratör. Du kan också ange dina inloggnings uppgifter direkt i cmdleten. 
    
    Kör följande cmdlet och ange dina autentiseringsuppgifter för företags administratör som ett PSCredential-objekt.
    
  ```powershell
  $secpasswd = ConvertTo-SecureString "MyPassword" -AsPlainText -Force
  $mycredentials = New-Object System.Management.Automation.PSCredential ("serviceaccount@contoso.com", $secpasswd)
  Connect-OrganizationAddInService -Credential $mycredentials
  ```

> [!NOTE]
> Mer information om hur du använder PowerShell finns i [ansluta till Microsoft 365 med PowerShell](https://go.microsoft.com/fwlink/p/?linkid=848585). 
  
## <a name="upload-an-add-in-manifest"></a>Ladda upp ett tilläggs manifest

Kör cmdleten **New-OrganizationAdd** för att ladda upp ett tilläggs manifest från en sökväg, som kan vara en fil Sök väg eller URL. I följande exempel visas en fil Sök väg för värdet för parametern  _ManifestPath_ . 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

Du kan också köra cmdleten **New-OrganizationAdd** för att ladda upp ett tillägg och tilldela det till användare eller grupper direkt genom att använda parametern  _medlemmar_ , enligt följande exempel. Avgränsa e-postadresserna för medlemmar med ett kommatecken. 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US' -Members  'KathyBonner@contoso.com', 'MaxHargrave@contoso.com'
```

## <a name="upload-an-add-in-from-the-office-store"></a>Ladda upp ett tillägg från Office Store

Kör cmdleten **New-OrganizationAddIn** för att ladda upp en manifest fil från Office Store.
  
I följande exempel anger cmdleten **New-OrganizationAddIn** in resursid för ett tillägg för en plats och innehålls marknad för USA.
  
```powershell
New-OrganizationAddIn -AssetId 'WA104099688' -Locale 'en-US' -ContentMarket 'en-US'
```

Om du vill veta värdet för  _resursid_ -parametern kan du kopiera den från URL-adressen till Office Store-webbplatsen för tillägget. AssetIds börjar alltid med "WA" följt av ett tal. I det föregående exemplet är källan för resursid-värdet för WA104099688 till exempel URL-adressen till Office Store för tillägget: [https://store.office.com/en-001/app.aspx?assetid=WA104099688](https://store.office.com/en-001/app.aspx?assetid=WA104099688) .
  
Värdena för parametern  _locale_ och parametern  _ContentMarket_ är identiska och anger det land/den region som du försöker installera tillägget från. Formatet är en-US, fr-FR. och så vidare. 
  
> [!NOTE]
> Tillägg som laddas upp från Office Store uppdateras automatiskt inom några dagar efter den senaste uppdateringen som är tillgänglig i Office Store. 
  
## <a name="get-details-of-an-add-in"></a>Få information om ett tillägg

Kör cmdleten **Get-OrganizationAddIn** som visas nedan för att få information om alla tillägg som laddas upp till klient organisationen, med ett tilläggs produkt-ID.
  
```powershell
Get-OrganizationAddIn
```

Kör cmdleten **Get-OrganizationAddIn** med ett värde för parametern  _ProductID_ för att ange vilket tillägg du vill hämta information om. 
  
```powershell
Get-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

För att få fullständig information om alla tillägg plus de tilldelade användarna och grupperna får du till gång till cmdleten **Get-OrganizationAddIn** till format listen, enligt följande exempel.
  
```powershell
foreach($G in (Get-organizationAddIn)){Get-OrganizationAddIn -ProductId $G.ProductId | Format-List}
```

## <a name="turn-on-or-turn-off-an-add-in"></a>Aktivera eller inaktivera ett tillägg

Om du vill inaktivera ett tillägg så att användare och grupper som har tilldelats till det inte längre kommer att ha åtkomst kör du cmdleten **set-OrganizationAddIn** med parametern  _ProductID_ och parametern  _Enabled_  `$false` , enligt följande exempel.
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $false
```

Om du vill aktivera ett tillägg igen kör du samma cmdlet med parametern  _Enabled_  `$true` .
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $true
```

## <a name="add-or-remove-users-from-an-add-in"></a>Lägga till eller ta bort användare från ett tillägg

Om du vill lägga till användare och grupper i ett specifikt tillägg kör du cmdleten **set-OrganizationAddInAssignments** med parametrarna  _ProductID_,  _Add_och  _members_ . Avgränsa e-postadresserna för medlemmar med ett kommatecken. 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Add -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

Om du vill ta bort användare och grupper kör du samma cmdlet med parametern  _Remove_ . 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Remove -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

Om du vill tilldela ett tillägg till alla användare i klient organisationen kör du samma cmdlet med parametern  _AssignToEveryone_ och värdet  `$true` .
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $true
```

Om du inte vill tilldela ett tillägg till alla och återgå till tidigare tilldelade användare och grupper kan du köra samma cmdlet och inaktivera parametern  _AssignToEveryone_ genom att ange värdet till  `$false` .
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $false
```

## <a name="update-an-add-in"></a>Uppdatera ett tillägg

Om du vill uppdatera ett tillägg från ett manifest kör du cmdleten **set-OrganizationAddIn** med parametrarna  _ProductID_,  _ManifestPath_och  _locale_ , enligt följande exempel. 
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

> [!NOTE]
> Tillägg som laddas upp från Office Store uppdateras automatiskt inom några dagar efter den senaste uppdateringen som är tillgänglig i Office Store. 
  
## <a name="delete-an-add-in"></a>Ta bort ett tillägg

Om du vill ta bort ett tillägg kör du cmdleten **Remove-OrganizationAddIn** med parametern  _Produktnr_ enligt följande exempel. 
  
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

## <a name="get-detailed-help-for-each-cmdlet"></a>Få detaljerad hjälp för varje cmdlet

Du kan se detaljerad hjälp för varje cmdlet genom att använda cmdleten Get-Help. Följande cmdlet innehåller till exempel detaljerad information om cmdlet Remove-OrganizationAddIn.
  
```powershell
Get-help Remove-OrganizationAddIn -Full
```


