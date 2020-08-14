---
title: Blockera gäst användare i en viss grupp
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
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Blockera gäst användare i en viss grupp
ms.openlocfilehash: 923a9e5cd09d232f377f55fd6a9f499f8f536a84
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662859"
---
# <a name="block-guest-users-from-a-specific-group"></a><span data-ttu-id="2d820-103">Blockera gäst användare i en viss grupp</span><span class="sxs-lookup"><span data-stu-id="2d820-103">Block guest users from a specific group</span></span>

<span data-ttu-id="2d820-104">Om du vill tillåta gäst åtkomst till de flesta grupperna, men om du vill förhindra gäst åtkomst kan du blockera gäst åtkomst för enskilda grupper.</span><span class="sxs-lookup"><span data-stu-id="2d820-104">If you want to allow guest access to most groups, but have some where you want to prevent guest access, you can block guest access for individual groups.</span></span>

<span data-ttu-id="2d820-105">Om du använder känslighets etiketter i organisationen rekommenderar vi att du använder dem för att kontrol lera gäst åtkomst per grupp.</span><span class="sxs-lookup"><span data-stu-id="2d820-105">If you use sensitivity labels in your organization, we recommend using them to control guest access on a per-group basis.</span></span> <span data-ttu-id="2d820-106">Information om hur du gör detta finns [i känslighets etiketter för att skydda innehåll i Microsoft Teams, microsoft 365-grupper och SharePoint-webbplatser](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="2d820-106">For information about how to do this, [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span> <span data-ttu-id="2d820-107">Det här är den metod som rekommenderas.</span><span class="sxs-lookup"><span data-stu-id="2d820-107">This is the recommended approach.</span></span>

<span data-ttu-id="2d820-108">Du kan också blockera gäst åtkomst till enskilda grupper med hjälp av Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d820-108">You can also block guest access to individual groups by using Microsoft PowerShell.</span></span>

<span data-ttu-id="2d820-109">Du måste använda för hands versionen av [Azure Active Directory PowerShell för graf](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (modul name **AzureADPreview**) för att ändra inställningen för gäst åtkomst på grupp nivå:</span><span class="sxs-lookup"><span data-stu-id="2d820-109">You must use the preview version of [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="2d820-110">Om du inte har installerat någon version av Azure AD PowerShell-modulen förut läser du [Installera Azure AD-modulen](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) och följa anvisningarna för att installera den offentliga för hands versionen.</span><span class="sxs-lookup"><span data-stu-id="2d820-110">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="2d820-111">Om du har 2,0 General Availability-versionen av Azure AD PowerShell-modulen (AzureAD) installerad måste du avinstallera den genom att köra `Uninstall-Module AzureAD` i din PowerShell-session och sedan installera för hands versionen genom att köra `Install-Module AzureADPreview` .</span><span class="sxs-lookup"><span data-stu-id="2d820-111">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="2d820-112">Om du redan har installerat för hands versionen måste du `Install-Module AzureADPreview` kontrol lera att den är den senaste versionen av den här modulen.</span><span class="sxs-lookup"><span data-stu-id="2d820-112">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="2d820-113">Du måste ha global administratörs behörighet för att köra de här kommandona.</span><span class="sxs-lookup"><span data-stu-id="2d820-113">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="2d820-114">Kör följande skript och ändra */<GroupName/>* till namnet på den grupp där du vill blockera gäst åtkomst.</span><span class="sxs-lookup"><span data-stu-id="2d820-114">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="2d820-115">Kör det här kommandot för att bekräfta dina inställningar:</span><span class="sxs-lookup"><span data-stu-id="2d820-115">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="2d820-116">Verifieringen ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="2d820-116">The verification looks like this:</span></span>
    
![Skärm bild av PowerShell-fönstret som visar att åtkomst till gäst gruppen har ställts in på false.](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="2d820-118">Tillåta eller blockera gäst åtkomst baserat på deras domän</span><span class="sxs-lookup"><span data-stu-id="2d820-118">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="2d820-119">Du kan tillåta eller blockera gäst användare som använder en viss domän.</span><span class="sxs-lookup"><span data-stu-id="2d820-119">You can allow or block guest users who are using a specific domain.</span></span> <span data-ttu-id="2d820-120">Om ditt företag till exempel har ett samarbete med ett annat företag (Fabrikam) kan du lägga till Fabrikam i listan Tillåt så att användarna kan lägga till dem i sina grupper.</span><span class="sxs-lookup"><span data-stu-id="2d820-120">For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="2d820-121">Mer information finns i [tillåta eller blockera inbjudningar för B2B-användare från specifika organisationer](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="2d820-121">For more information, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="2d820-122">Lägga till gäster i den globala adress listan</span><span class="sxs-lookup"><span data-stu-id="2d820-122">Add guests to the global address list</span></span>

<span data-ttu-id="2d820-123">Som standard är inte gästerna synliga i den globala adress listan för Exchange.</span><span class="sxs-lookup"><span data-stu-id="2d820-123">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="2d820-124">Följ stegen nedan om du vill göra en gäst synlig i den globala adress listan.</span><span class="sxs-lookup"><span data-stu-id="2d820-124">Use the steps listed below to make a guest visible in the global address list.</span></span>

<span data-ttu-id="2d820-125">Hitta gäst användarens ObjectID genom att köra:</span><span class="sxs-lookup"><span data-stu-id="2d820-125">Find the guest user's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="2d820-126">Kör sedan följande värden för ObjectID, GivenName, efter namn, DisplayName och TelephoneNumber.</span><span class="sxs-lookup"><span data-stu-id="2d820-126">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-articles"></a><span data-ttu-id="2d820-127">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="2d820-127">Related articles</span></span>

[<span data-ttu-id="2d820-128">Hantera grupp medlemskap i administrations centret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2d820-128">Manage Group membership in the Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups)
  
[<span data-ttu-id="2d820-129">Åtkomst granskning för Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="2d820-129">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="2d820-130">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="2d820-130">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)