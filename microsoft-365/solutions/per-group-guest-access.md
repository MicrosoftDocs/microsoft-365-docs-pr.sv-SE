---
title: Förhindra att gäster läggs till i en viss grupp
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: Lär dig hur du förhindrar att gäster läggs till i en viss grupp
ms.openlocfilehash: 1db2055f3e546c05905dbf4c854333387112f06e
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538933"
---
# <a name="prevent-guests-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a>Förhindra att gäster läggs till i en viss Microsoft 365 grupp eller Microsoft Teams grupp

Om du vill tillåta gäståtkomst till de flesta grupper och team, men har några där du vill förhindra gäståtkomst, kan du blockera gäståtkomst för enskilda grupper och team. (Att blockera gäståtkomst till ett team görs genom att blockera gäståtkomst till den associerade gruppen.) Det förhindrar att nya gäster läggs till men tar inte bort gäster som redan finns i gruppen eller teamet.

Om du använder känslighetsetiketter i din organisation rekommenderar vi att du använder dem för att styra gäståtkomst per grupp. Mer information om hur du gör detta finns i Använda känslighetsetiketter för att skydda innehåll i [Microsoft Teams, Microsoft 365 grupper och SharePoint webbplatser.](../compliance/sensitivity-labels-teams-groups-sites.md) Det här är den rekommenderade metoden.

## <a name="change-group-settings-using-microsoft-powershell"></a>Ändra gruppinställningar med Microsoft PowerShell

Du kan också förhindra tillägg av nya gäster i enskilda grupper med hjälp av PowerShell. (Kom ihåg att teamets associerade SharePoint har [separata gästdelningskontroller](/sharepoint/change-external-sharing-site).)

Du måste använda förhandsversionen av Azure Active Directory PowerShell för [Graph (modulnamn](/powershell/azure/active-directory/install-adv2) **AzureADPreview**) om du vill ändra inställningen för gäståtkomst på gruppnivå:

- Om du inte har installerat någon version av Azure AD PowerShell-modulen tidigare, se Installera [Azure AD-modulen](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) och följ anvisningarna för att installera den offentliga förhandsversionen.

- Om du har den 2.0 allmänt tillgängliga versionen av Azure AD PowerShell-modulen (AzureAD) installerad måste du avinstallera den genom att köra den i PowerShell-sessionen och sedan installera förhandsversionen genom att köra `Uninstall-Module AzureAD` `Install-Module AzureADPreview` .

- Om du redan har installerat förhandsgranskningsversionen kör `Install-Module AzureADPreview` du för att kontrollera att det är den senaste versionen av den här modulen.

> [!NOTE]
> Du måste ha global administratörsbehörighet för att kunna köra dessa kommandon. 

Kör följande skript och ändra */<GroupName/>* till namnet på den grupp där du vill blockera gäståtkomst.

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

Kör det här kommandot för att verifiera dina inställningar:

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

Verifieringen ser ut så här:
    
![Skärmbild av PowerShell-fönstret som visar att gästgruppsåtkomst har angetts till falskt.](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a>Tillåta eller blockera gäståtkomst baserat på deras domän

Du kan tillåta eller blockera gäster som använder en viss domän. Om ditt företag (Contoso) till exempel har ett samarbete med ett annat företag (Fabrikam) kan du lägga till Fabrikam i listan över tillåtna företag så att användarna kan lägga till dessa gäster i sina grupper.

Mer information finns i Tillåta [eller blockera inbjudningar till B2B-användare från specifika organisationer.](/azure/active-directory/b2b/allow-deny-list)

## <a name="add-guests-to-the-global-address-list"></a>Lägga till gäster i den globala adresslistan

Som standard visas inte gäster i den globala Exchange adresslistan. Använd stegen nedan för att göra en gäst synlig i den globala adresslistan.

Hitta gästens ObjectID genom att köra:

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

Kör sedan följande med lämpliga värden för ObjectID, GivenName, Efternamn, DisplayName och TelephoneNumber.

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-topics"></a>Relaterade ämnen

[Planering av samarbetsstyrning steg för steg](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Skapa din plan för samarbetesstyrning](collaboration-governance-first.md)

[Hantera gruppmedlemskap i Microsoft 365 administrationscentret](../admin/create-groups/add-or-remove-members-from-groups.md)
  
[Azure Active Directory granskningar av åtkomst](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](/powershell/module/azuread/set-azureaduser)