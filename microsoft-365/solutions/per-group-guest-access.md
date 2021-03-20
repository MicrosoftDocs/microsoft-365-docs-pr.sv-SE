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
description: Lär dig hur du förhindrar att gäster läggs till i en viss grupp
ms.openlocfilehash: 572746a666586920ad85dafddbd78997940490d7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907946"
---
# <a name="prevent-guests-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a><span data-ttu-id="6bbd1-103">Förhindra att gäster läggs till i en viss Microsoft 365-grupp eller Microsoft Teams-team</span><span class="sxs-lookup"><span data-stu-id="6bbd1-103">Prevent guests from being added to a specific Microsoft 365 group or Microsoft Teams team</span></span>

<span data-ttu-id="6bbd1-104">Om du vill tillåta gäståtkomst till de flesta grupper och team, men har några där du vill förhindra gäståtkomst, kan du blockera gäståtkomst för enskilda grupper och team.</span><span class="sxs-lookup"><span data-stu-id="6bbd1-104">If you want to allow guest access to most groups and teams, but have some where you want to prevent guest access, you can block guest access for individual groups and teams.</span></span> <span data-ttu-id="6bbd1-105">(Att blockera gäståtkomst till ett team görs genom att blockera gäståtkomst till den associerade gruppen.) Det förhindrar att nya gäster läggs till men tar inte bort gäster som redan finns i gruppen eller teamet.</span><span class="sxs-lookup"><span data-stu-id="6bbd1-105">(Blocking guest access to a team is done by blocking guest access to the associated group.) This prevents new guests from being added but does not remove guests that are already in the group or team.</span></span>

<span data-ttu-id="6bbd1-106">Om du använder känslighetsetiketter i din organisation rekommenderar vi att du använder dem för att styra gäståtkomst per grupp.</span><span class="sxs-lookup"><span data-stu-id="6bbd1-106">If you use sensitivity labels in your organization, we recommend using them to control guest access on a per-group basis.</span></span> <span data-ttu-id="6bbd1-107">Mer information om hur du gör detta finns i Använda känslighetsetiketter för att skydda innehåll i [Microsoft Teams, Microsoft 365-grupper och SharePoint-webbplatser.](../compliance/sensitivity-labels-teams-groups-sites.md)</span><span class="sxs-lookup"><span data-stu-id="6bbd1-107">For information about how to do this, [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span> <span data-ttu-id="6bbd1-108">Det här är den rekommenderade metoden.</span><span class="sxs-lookup"><span data-stu-id="6bbd1-108">This is the recommended approach.</span></span>

## <a name="change-group-settings-using-microsoft-powershell"></a><span data-ttu-id="6bbd1-109">Ändra gruppinställningar med Microsoft PowerShell</span><span class="sxs-lookup"><span data-stu-id="6bbd1-109">Change group settings using Microsoft PowerShell</span></span>

<span data-ttu-id="6bbd1-110">Du kan också förhindra tillägg av nya gäster i enskilda grupper med hjälp av PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6bbd1-110">You can also prevent the addition of new guests to individual groups by using PowerShell.</span></span> <span data-ttu-id="6bbd1-111">(Kom ihåg att teamets associerade SharePoint-webbplats har [separata gästdelningskontroller](/sharepoint/change-external-sharing-site).)</span><span class="sxs-lookup"><span data-stu-id="6bbd1-111">(Remember that the team's associated SharePoint site has [separate guest sharing controls](/sharepoint/change-external-sharing-site).)</span></span>

<span data-ttu-id="6bbd1-112">Du måste använda förhandsversionen av [Azure Active Directory PowerShell för Graph](/powershell/azure/active-directory/install-adv2) (modulnamnet **AzureADPreview**) om du vill ändra inställningen för gäståtkomst på gruppnivå:</span><span class="sxs-lookup"><span data-stu-id="6bbd1-112">You must use the preview version of [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="6bbd1-113">Om du inte har installerat någon version av Azure AD PowerShell-modulen tidigare, se Installera [Azure AD-modulen](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) och följ anvisningarna för att installera den offentliga förhandsversionen.</span><span class="sxs-lookup"><span data-stu-id="6bbd1-113">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="6bbd1-114">Om du har den 2.0 allmänt tillgängliga versionen av Azure AD PowerShell-modulen (AzureAD) installerad måste du avinstallera den genom att köra den i PowerShell-sessionen och sedan installera förhandsversionen genom att köra `Uninstall-Module AzureAD` `Install-Module AzureADPreview` .</span><span class="sxs-lookup"><span data-stu-id="6bbd1-114">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="6bbd1-115">Om du redan har installerat förhandsgranskningsversionen kör `Install-Module AzureADPreview` du för att kontrollera att det är den senaste versionen av den här modulen.</span><span class="sxs-lookup"><span data-stu-id="6bbd1-115">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="6bbd1-116">Du måste ha global administratörsbehörighet för att kunna köra dessa kommandon.</span><span class="sxs-lookup"><span data-stu-id="6bbd1-116">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="6bbd1-117">Kör följande skript och ändra */<GroupName/>* till namnet på den grupp där du vill blockera gäståtkomst.</span><span class="sxs-lookup"><span data-stu-id="6bbd1-117">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="6bbd1-118">Kör det här kommandot för att verifiera dina inställningar:</span><span class="sxs-lookup"><span data-stu-id="6bbd1-118">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="6bbd1-119">Verifieringen ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="6bbd1-119">The verification looks like this:</span></span>
    
![Skärmbild av PowerShell-fönstret som visar att gästgruppsåtkomst har angetts till falskt.](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="6bbd1-121">Tillåta eller blockera gäståtkomst baserat på deras domän</span><span class="sxs-lookup"><span data-stu-id="6bbd1-121">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="6bbd1-122">Du kan tillåta eller blockera gäster som använder en viss domän.</span><span class="sxs-lookup"><span data-stu-id="6bbd1-122">You can allow or block guests who are using a specific domain.</span></span> <span data-ttu-id="6bbd1-123">Om ditt företag (Contoso) till exempel har ett samarbete med ett annat företag (Fabrikam) kan du lägga till Fabrikam i listan över tillåtna företag så att användarna kan lägga till dessa gäster i sina grupper.</span><span class="sxs-lookup"><span data-stu-id="6bbd1-123">For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="6bbd1-124">Mer information finns i Tillåta [eller blockera inbjudningar till B2B-användare från specifika organisationer.](/azure/active-directory/b2b/allow-deny-list)</span><span class="sxs-lookup"><span data-stu-id="6bbd1-124">For more information, see [Allow or block invitations to B2B users from specific organizations](/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="6bbd1-125">Lägga till gäster i den globala adresslistan</span><span class="sxs-lookup"><span data-stu-id="6bbd1-125">Add guests to the global address list</span></span>

<span data-ttu-id="6bbd1-126">Som standard visas inte gäster i den globala adresslistan i Exchange.</span><span class="sxs-lookup"><span data-stu-id="6bbd1-126">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="6bbd1-127">Använd stegen nedan för att göra en gäst synlig i den globala adresslistan.</span><span class="sxs-lookup"><span data-stu-id="6bbd1-127">Use the steps listed below to make a guest visible in the global address list.</span></span>

<span data-ttu-id="6bbd1-128">Hitta gästens ObjectID genom att köra:</span><span class="sxs-lookup"><span data-stu-id="6bbd1-128">Find the guest's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="6bbd1-129">Kör sedan följande med lämpliga värden för ObjectID, GivenName, Efternamn, DisplayName och TelephoneNumber.</span><span class="sxs-lookup"><span data-stu-id="6bbd1-129">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-topics"></a><span data-ttu-id="6bbd1-130">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="6bbd1-130">Related topics</span></span>

[<span data-ttu-id="6bbd1-131">Planering av samarbetsstyrning steg för steg</span><span class="sxs-lookup"><span data-stu-id="6bbd1-131">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="6bbd1-132">Skapa din plan för samarbetesstyrning</span><span class="sxs-lookup"><span data-stu-id="6bbd1-132">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="6bbd1-133">Hantera gruppmedlemskap i administrationscentret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6bbd1-133">Manage Group membership in the Microsoft 365 admin center</span></span>](../admin/create-groups/add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="6bbd1-134">Åtkomstgranskningar i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="6bbd1-134">Azure Active Directory access reviews</span></span>](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="6bbd1-135">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="6bbd1-135">Set-AzureADUser</span></span>](/powershell/module/azuread/set-azureaduser)