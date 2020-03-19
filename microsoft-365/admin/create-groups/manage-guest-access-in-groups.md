---
title: Hantera gäståtkomst i Office 365-grupper
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.date: 12/18/2019
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
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Lär dig hur du lägger till gäster i en Office 365-grupp, visar gästanvändare och använder PowerShell för att styra gäståtkomst.
ms.openlocfilehash: 3314746e4d12c318eaae8fbfa34c2ed0b4d31aed
ms.sourcegitcommit: dcea75af89f5f80ec6670346ee176407e043de54
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/12/2020
ms.locfileid: "42807702"
---
# <a name="manage-guest-access-in-office-365-groups"></a>Hantera gäståtkomst i Office 365-grupper

Som standard är gäståtkomst för Office 365-grupper aktiverat för din organisation. Administratörer kan kontrollera om gäståtkomst till grupper för hela organisationen eller för enskilda grupper ska tillåtas.

När den är aktiverad kan gruppmedlemmar bjuda in gästanvändare till en Office 365-grupp via Outlook på webben. Inbjudningar skickas till gruppägaren för godkännande.

> [!Note]
> Yammer Enterprise-nätverk som är i inbyggt läge eller [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) stöder inte nätverksgäster.
> Office 365 Connected Yammer Groups stöder för närvarande inte gäståtkomst, men du kan skapa icke-anslutna externa grupper i Yammer-nätverket. Se [Skapa och hantera externa grupper i Yammer](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a.aspx) för instruktioner.

### <a name="edit-guest-information"></a>Redigera gästinformation

När den har godkänts läggs gästanvändaren till i katalogen och gruppen.

Gäståtkomst i grupper används ofta som en del av ett bredare scenario som innehåller SharePoint eller Teams. Dessa tjänster har sina egna inställningar för gästdelning. Fullständiga instruktioner för hur du konfigurerar gästdelning mellan grupper, SharePoint och Teams finns i:

- [Samarbeta med gäster på en webbplats](../../solutions/collaborate-in-site.md)
- [Samarbeta med gäster i ett team](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Hantera gruppgäståtkomst

Om du vill aktivera eller inaktivera gäståtkomst i grupper kan du göra det i administrationscentret för Microsoft 365.

1. Gå till sidan **Inställningar** \> & tillägg i <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">administrationscentret.</a>

2. Välj **Office 365-grupper**.
  
3. På sidan **Office 365-grupper** väljer du om du vill låta personer utanför organisationen komma åt gruppresurser eller låta gruppägare lägga till personer utanför organisationen i grupper.

## <a name="add-guests-to-an-office-365-group-from-the-admin-center"></a>Lägga till gäster i en Office 365-grupp från administrationscentret

Om gästen redan finns i katalogen kan du lägga till dem i dina grupper från administrationscentret för Microsoft 365.
  
1. Gå till sidan **Grupper** > **grupper** i administrationscentret.
  
2. Välj den grupp som du vill lägga till gästen i och välj **Visa alla och hantera medlemmar** på fliken **Medlemmar.** 
  
4. Välj **Lägg till medlemmar**och välj namnet på den gäst som du vill lägga till.
    
5. Välj **Spara**.

Om du vill lägga till en gäst i katalogen direkt kan du [lägga till Azure Active Directory B2B-samarbetsanvändare i Azure-portalen](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).

Om du vill redigera någon av en gästs information kan du [lägga till eller uppdatera en användares profilinformation med Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).
  
## <a name="block-guest-users-from-a-specific-group"></a>Blockera gästanvändare från en viss grupp

Om du vill tillåta gäståtkomst till de flesta grupper, men har några där du vill förhindra gäståtkomst, kan du blockera gäståtkomst för enskilda grupper med hjälp av Microsoft PowerShell.

Du måste använda förhandsgranskningsversionen av [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (modulnamnet **AzureADPreview)** för att ändra inställningen för gäståtkomst på gruppnivå:

- Om du inte har installerat någon version av Azure AD PowerShell-modulen tidigare läser du [Installera Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) och följer instruktionerna för att installera den offentliga förhandsversionen.

- Om du har den 2.0 allmänna tillgänglighetsversionen av Azure AD PowerShell-modulen (AzureAD) installerad måste du avinstallera den genom att köra `Uninstall-Module AzureAD` i PowerShell-sessionen och sedan installera förhandsgranskningsversionen genom att köra `Install-Module AzureADPreview`.

- Om du redan har installerat `Install-Module AzureADPreview` förhandsgranskningsversionen kör du för att se till att det är den senaste versionen av den här modulen.

> [!NOTE]
> Du måste ha globala administratörsrättigheter för att kunna köra dessa kommandon. 

Kör följande skript * / * och ändra till namnet på den grupp där du vill blockera gäståtkomst.

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

Om du vill verifiera inställningarna kör du det här kommandot:

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

Verifieringen ser ut så här:
    
![Skärmbild av PowerShell-fönstret som visar att gästgruppsåtkomst har angetts till false.](../../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a>Tillåt eller blockera gäståtkomst baserat på deras domän

Du kan tillåta eller blockera gästanvändare som använder en viss domän. Om ditt företag (Contoso) till exempel har ett samarbete med ett annat företag (Fabrikam) kan du lägga till Fabrikam i listan Tillåt så att användarna kan lägga till dessa gäster i sina grupper.

Mer information finns i [Tillåt eller blockera inbjudningar till B2B-användare från specifika organisationer](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).

## <a name="add-guests-to-the-global-address-list"></a>Lägga till gäster i den globala adresslistan

Som standard visas inte gäster i Exchange Global-adresslistan. Följ stegen nedan för att göra en gäst synlig i den globala adresslistan.

Hitta gästanvändarens ObjectID genom att köra:

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

Kör sedan följande med lämpliga värden för ObjectID, GivenName, Efternamn, DisplayName och Telefonnummer.

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-articles"></a>Relaterade artiklar

[Hantera gruppmedlemskap i administrationscentret för Microsoft 365](add-or-remove-members-from-groups.md)
  
[Granskningar av Azure Active Directory-åtkomst](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureAdUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
