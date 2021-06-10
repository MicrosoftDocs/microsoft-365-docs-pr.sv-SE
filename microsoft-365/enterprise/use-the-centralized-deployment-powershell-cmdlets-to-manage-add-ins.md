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
description: Använd PowerShell-cmdlets för centraliserad distribution för att distribuera och Office tillägg för din Microsoft 365 organisation.
ms.openlocfilehash: 7872deedfcfe058f0a4ac63c489bbed139699d18
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924678"
---
# <a name="use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins"></a>Use the Centralized Deployment PowerShell cmdlets to manage add-ins

Som Microsoft 365 global administratör kan du distribuera Office-tillägg till användare via funktionen för centraliserad distribution (se Distribuera [Office-tillägg](../admin/manage/manage-deployment-of-add-ins.md)i administrationscentret ). Förutom att distribuera Office tillägg via administrationscentret för Microsoft 365 kan du också använda Microsoft PowerShell. Installera [O365 Centralized Add-In Deployment Module för Windows PowerShell.](https://www.powershellgallery.com/packages/O365CentralizedAddInDeployment) 

När du har laddat ned modulen öppnar du ett Windows PowerShell fönster och kör följande cmdlet:

```powershell
 Import-Module -Name O365CentralizedAddInDeployment
```
    
## <a name="connect-using-your-admin-credentials"></a>Anslut dina administratörsuppgifter

Innan du kan använda cmdlets för centraliserad distribution måste du logga in.
  
1. Starta PowerShell.
    
2. Anslut till PowerShell med dina autentiseringsuppgifter som företagsadministratör. Kör följande cmdlet.
    
  ```powershell
  Connect-OrganizationAddInService
  ```

3. På sidan **Ange autentiseringsuppgifter** anger du dina Microsoft 365 som global administratör. Alternativt kan du ange dina autentiseringsuppgifter direkt i cmdleten. 
    
    Kör följande cmdlet med dina autentiseringsuppgifter som företagsadministratör som ett PSCredential-objekt.
    
  ```powershell
  $secpasswd = ConvertTo-SecureString "MyPassword" -AsPlainText -Force
  $mycredentials = New-Object System.Management.Automation.PSCredential ("serviceaccount@contoso.com", $secpasswd)
  Connect-OrganizationAddInService -Credential $mycredentials
  ```

> [!NOTE]
> Mer information om hur du använder PowerShell finns i [Anslut att Microsoft 365 med PowerShell.](./connect-to-microsoft-365-powershell.md) 
  
## <a name="upload-an-add-in-manifest"></a>Upload ett tilläggsmanifest

Kör **cmdleten New-OrganizationAdd-In** för att ladda upp ett tilläggsmanifest från en sökväg, som antingen kan vara en filsökväg eller en URL. I följande exempel visas en filplats för parametervärdet för _ManifestPath._ 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

Du kan också köra cmdleten **New-OrganizationAdd-In** för att ladda upp ett tillägg och tilldela det till användare eller grupper direkt med hjälp av parametern  _Members,_ enligt exemplet nedan. Avgränsa e-postadresserna till medlemmarna med kommatecken. 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US' -Members  'KathyBonner@contoso.com', 'MaxHargrave@contoso.com'
```

## <a name="upload-an-add-in-from-the-office-store"></a>Upload ett tillägg från Office Store

Kör **cmdleten New-OrganizationAddIn** för att ladda upp ett manifest från Office Store.
  
I följande exempel anger **cmdleten New-OrganizationAddIn** TillgångsID för ett tillägg för en plats och en innehållsmarknad i USA.
  
```powershell
New-OrganizationAddIn -AssetId 'WA104099688' -Locale 'en-US' -ContentMarket 'en-US'
```

Om du vill avgöra värdet för parametern _AssetId_ kan du kopiera det från URL:en för Office Store-webbsidan för tillägget. Tillgångsid:er börjar alltid med "WA" följt av ett tal. I föregående exempel är källan för AssetId-värdet WA104099688 webbside-URL för Office Store för tillägget: [https://store.office.com/en-001/app.aspx?assetid=WA104099688](https://store.office.com/en-001/app.aspx?assetid=WA104099688) .
  
Värdena för parametern  _Locale_ och  _parametern ContentMarket_ är identiska och anger landet/regionen som du försöker installera tillägget från. Formatet är en-US, fr-FR. och så vidare. 
  
> [!NOTE]
> Tillägg som laddats upp från Office Store uppdateras automatiskt inom några dagar efter det att den senaste uppdateringen är tillgänglig på Office Store. 
  
## <a name="get-details-of-an-add-in"></a>Få information om ett tillägg

Kör cmdleten **Get-OrganizationAddIn** enligt nedan för att få information om alla tillägg som laddats upp till klientorganisationen, inklusive tilläggets produkt-ID.
  
```powershell
Get-OrganizationAddIn
```

Kör **cmdleten Get-OrganizationAddIn** med ett värde för parametern  _ProductId_ för att ange vilket tillägg du vill hämta information för. 
  
```powershell
Get-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

För att få fullständig information om alla tillägg plus tilldelade användare och grupper ska du pipa utdata från cmdlet:en **Get-OrganizationAddIn** till cmdleten Format-List, som du ser i följande exempel.
  
```powershell
foreach($G in (Get-organizationAddIn)){Get-OrganizationAddIn -ProductId $G.ProductId | Format-List}
```

## <a name="turn-on-or-turn-off-an-add-in"></a>Aktivera eller inaktivera ett tillägg

Om du vill inaktivera ett tillägg så att användare och grupper som har tilldelats det inte längre har åtkomst kör du cmdleten **Set-OrganizationAddIn** med parametern  _ProductId_ och parametern  _Enabled_ inställda på , som i följande  `$false` exempel.
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $false
```

Om du vill aktivera tillägget igen kör du samma cmdlet med  _parametern Enabled_ inställd på  `$true` .
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $true
```

## <a name="add-or-remove-users-from-an-add-in"></a>Lägga till eller ta bort användare från ett tillägg

Om du vill lägga till användare och grupper i ett specifikt tillägg kör du cmdleten **Set-OrganizationAddInAssignments** med parametrarna _ProductId,_ _Add_ _och Members._ Avgränsa e-postadresserna till medlemmarna med kommatecken. 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Add -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

Om du vill ta bort användare och grupper kör du samma cmdlet med _parametern Remove._ 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Remove -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

Om du vill tilldela ett tillägg till alla användare i klientorganisationen kör du samma cmdlet med parametern  _AssignToEveryone_ med värdet inställt på  `$true` .
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $true
```

Om du inte vill tilldela ett tillägg till alla och återgå till de tidigare tilldelade användarna och grupperna, kan du köra samma cmdlet och inaktivera parametern  _AssignToEveryone_ genom att ange dess värde till  `$false` .
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $false
```

## <a name="update-an-add-in"></a>Uppdatera ett tillägg

Om du vill uppdatera ett tillägg från ett manifest kör du **cmdleten Set-OrganizationAddIn** med parametrarna  _ProductId,_  _ManifestPath_ och  _Locale,_ enligt följande exempel. 
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

> [!NOTE]
> Tillägg som laddats upp från Office Store uppdateras automatiskt inom några dagar efter det att den senaste uppdateringen är tillgänglig på Office Store. 
  
## <a name="delete-an-add-in"></a>Ta bort ett tillägg

Om du vill ta bort ett tillägg kör du **cmdleten Remove-OrganizationAddIn** med  _parametern ProductId,_ enligt följande exempel. 
  
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

Du kan se detaljerad hjälp för varje cmdlet med hjälp av cmdleten Get-help. Följande cmdlet ger till exempel detaljerad information om Remove-OrganizationAddIn cmdlet.
  
```powershell
Get-help Remove-OrganizationAddIn -Full
```