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
# <a name="manage-guest-access-in-office-365-groups"></a><span data-ttu-id="5e40d-103">Hantera gäståtkomst i Office 365-grupper</span><span class="sxs-lookup"><span data-stu-id="5e40d-103">Manage guest access in Office 365 Groups</span></span>

<span data-ttu-id="5e40d-104">Som standard är gäståtkomst för Office 365-grupper aktiverat för din organisation.</span><span class="sxs-lookup"><span data-stu-id="5e40d-104">By default, guest access for Office 365 groups is turned on for your organization.</span></span> <span data-ttu-id="5e40d-105">Administratörer kan kontrollera om gäståtkomst till grupper för hela organisationen eller för enskilda grupper ska tillåtas.</span><span class="sxs-lookup"><span data-stu-id="5e40d-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="5e40d-106">När den är aktiverad kan gruppmedlemmar bjuda in gästanvändare till en Office 365-grupp via Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="5e40d-106">When it's turned on, group members can invite guest users to an Office 365 group through Outlook on Web.</span></span> <span data-ttu-id="5e40d-107">Inbjudningar skickas till gruppägaren för godkännande.</span><span class="sxs-lookup"><span data-stu-id="5e40d-107">Invitations are sent to the group owner for approval.</span></span>

> [!Note]
> <span data-ttu-id="5e40d-108">Yammer Enterprise-nätverk som är i inbyggt läge eller [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) stöder inte nätverksgäster.</span><span class="sxs-lookup"><span data-stu-id="5e40d-108">Yammer Enterprise networks that are in Native Mode or the [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) do not support network guests.</span></span>
> <span data-ttu-id="5e40d-109">Office 365 Connected Yammer Groups stöder för närvarande inte gäståtkomst, men du kan skapa icke-anslutna externa grupper i Yammer-nätverket.</span><span class="sxs-lookup"><span data-stu-id="5e40d-109">Office 365 Connected Yammer Groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="5e40d-110">Se [Skapa och hantera externa grupper i Yammer](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a.aspx) för instruktioner.</span><span class="sxs-lookup"><span data-stu-id="5e40d-110">See [Create and manage external groups in Yammer](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a.aspx) for instructions.</span></span>

### <a name="edit-guest-information"></a><span data-ttu-id="5e40d-111">Redigera gästinformation</span><span class="sxs-lookup"><span data-stu-id="5e40d-111">Edit guest information</span></span>

<span data-ttu-id="5e40d-112">När den har godkänts läggs gästanvändaren till i katalogen och gruppen.</span><span class="sxs-lookup"><span data-stu-id="5e40d-112">Once approved, the guest user is added to the directory and the group.</span></span>

<span data-ttu-id="5e40d-113">Gäståtkomst i grupper används ofta som en del av ett bredare scenario som innehåller SharePoint eller Teams.</span><span class="sxs-lookup"><span data-stu-id="5e40d-113">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="5e40d-114">Dessa tjänster har sina egna inställningar för gästdelning.</span><span class="sxs-lookup"><span data-stu-id="5e40d-114">These services have their own guest sharing settings.</span></span> <span data-ttu-id="5e40d-115">Fullständiga instruktioner för hur du konfigurerar gästdelning mellan grupper, SharePoint och Teams finns i:</span><span class="sxs-lookup"><span data-stu-id="5e40d-115">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="5e40d-116">Samarbeta med gäster på en webbplats</span><span class="sxs-lookup"><span data-stu-id="5e40d-116">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="5e40d-117">Samarbeta med gäster i ett team</span><span class="sxs-lookup"><span data-stu-id="5e40d-117">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="5e40d-118">Hantera gruppgäståtkomst</span><span class="sxs-lookup"><span data-stu-id="5e40d-118">Manage groups guest access</span></span>

<span data-ttu-id="5e40d-119">Om du vill aktivera eller inaktivera gäståtkomst i grupper kan du göra det i administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5e40d-119">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="5e40d-120">Gå till sidan **Inställningar** \> & tillägg i <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="5e40d-120">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services & add-ins</a> page.</span></span>

2. <span data-ttu-id="5e40d-121">Välj **Office 365-grupper**.</span><span class="sxs-lookup"><span data-stu-id="5e40d-121">Select **Office 365 Groups**.</span></span>
  
3. <span data-ttu-id="5e40d-122">På sidan **Office 365-grupper** väljer du om du vill låta personer utanför organisationen komma åt gruppresurser eller låta gruppägare lägga till personer utanför organisationen i grupper.</span><span class="sxs-lookup"><span data-stu-id="5e40d-122">On the **Office 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-an-office-365-group-from-the-admin-center"></a><span data-ttu-id="5e40d-123">Lägga till gäster i en Office 365-grupp från administrationscentret</span><span class="sxs-lookup"><span data-stu-id="5e40d-123">Add guests to an Office 365 group from the admin center</span></span>

<span data-ttu-id="5e40d-124">Om gästen redan finns i katalogen kan du lägga till dem i dina grupper från administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5e40d-124">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span>
  
1. <span data-ttu-id="5e40d-125">Gå till sidan **Grupper** > **grupper** i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="5e40d-125">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="5e40d-126">Välj den grupp som du vill lägga till gästen i och välj **Visa alla och hantera medlemmar** på fliken **Medlemmar.**</span><span class="sxs-lookup"><span data-stu-id="5e40d-126">Select the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="5e40d-127">Välj **Lägg till medlemmar**och välj namnet på den gäst som du vill lägga till.</span><span class="sxs-lookup"><span data-stu-id="5e40d-127">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="5e40d-128">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="5e40d-128">Select **Save**.</span></span>

<span data-ttu-id="5e40d-129">Om du vill lägga till en gäst i katalogen direkt kan du [lägga till Azure Active Directory B2B-samarbetsanvändare i Azure-portalen](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span><span class="sxs-lookup"><span data-stu-id="5e40d-129">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="5e40d-130">Om du vill redigera någon av en gästs information kan du [lägga till eller uppdatera en användares profilinformation med Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="5e40d-130">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>
  
## <a name="block-guest-users-from-a-specific-group"></a><span data-ttu-id="5e40d-131">Blockera gästanvändare från en viss grupp</span><span class="sxs-lookup"><span data-stu-id="5e40d-131">Block guest users from a specific group</span></span>

<span data-ttu-id="5e40d-132">Om du vill tillåta gäståtkomst till de flesta grupper, men har några där du vill förhindra gäståtkomst, kan du blockera gäståtkomst för enskilda grupper med hjälp av Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e40d-132">If you want to allow guest access to most groups, but have some where you want to prevent guest access, you can block guest access for individual groups by using Microsoft PowerShell.</span></span>

<span data-ttu-id="5e40d-133">Du måste använda förhandsgranskningsversionen av [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (modulnamnet **AzureADPreview)** för att ändra inställningen för gäståtkomst på gruppnivå:</span><span class="sxs-lookup"><span data-stu-id="5e40d-133">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="5e40d-134">Om du inte har installerat någon version av Azure AD PowerShell-modulen tidigare läser du [Installera Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) och följer instruktionerna för att installera den offentliga förhandsversionen.</span><span class="sxs-lookup"><span data-stu-id="5e40d-134">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="5e40d-135">Om du har den 2.0 allmänna tillgänglighetsversionen av Azure AD PowerShell-modulen (AzureAD) installerad måste du avinstallera den genom att köra `Uninstall-Module AzureAD` i PowerShell-sessionen och sedan installera förhandsgranskningsversionen genom att köra `Install-Module AzureADPreview`.</span><span class="sxs-lookup"><span data-stu-id="5e40d-135">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="5e40d-136">Om du redan har installerat `Install-Module AzureADPreview` förhandsgranskningsversionen kör du för att se till att det är den senaste versionen av den här modulen.</span><span class="sxs-lookup"><span data-stu-id="5e40d-136">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="5e40d-137">Du måste ha globala administratörsrättigheter för att kunna köra dessa kommandon.</span><span class="sxs-lookup"><span data-stu-id="5e40d-137">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="5e40d-138">Kör följande skript \* / \* och ändra till namnet på den grupp där du vill blockera gäståtkomst.</span><span class="sxs-lookup"><span data-stu-id="5e40d-138">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="5e40d-139">Om du vill verifiera inställningarna kör du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="5e40d-139">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="5e40d-140">Verifieringen ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="5e40d-140">The verification looks like this:</span></span>
    
![Skärmbild av PowerShell-fönstret som visar att gästgruppsåtkomst har angetts till false.](../../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="5e40d-142">Tillåt eller blockera gäståtkomst baserat på deras domän</span><span class="sxs-lookup"><span data-stu-id="5e40d-142">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="5e40d-143">Du kan tillåta eller blockera gästanvändare som använder en viss domän.</span><span class="sxs-lookup"><span data-stu-id="5e40d-143">You can allow or block guest users who are using a specific domain.</span></span> <span data-ttu-id="5e40d-144">Om ditt företag (Contoso) till exempel har ett samarbete med ett annat företag (Fabrikam) kan du lägga till Fabrikam i listan Tillåt så att användarna kan lägga till dessa gäster i sina grupper.</span><span class="sxs-lookup"><span data-stu-id="5e40d-144">For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="5e40d-145">Mer information finns i [Tillåt eller blockera inbjudningar till B2B-användare från specifika organisationer](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="5e40d-145">For more information, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="5e40d-146">Lägga till gäster i den globala adresslistan</span><span class="sxs-lookup"><span data-stu-id="5e40d-146">Add guests to the global address list</span></span>

<span data-ttu-id="5e40d-147">Som standard visas inte gäster i Exchange Global-adresslistan.</span><span class="sxs-lookup"><span data-stu-id="5e40d-147">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="5e40d-148">Följ stegen nedan för att göra en gäst synlig i den globala adresslistan.</span><span class="sxs-lookup"><span data-stu-id="5e40d-148">Use the steps listed below to make a guest visible in the global address list.</span></span>

<span data-ttu-id="5e40d-149">Hitta gästanvändarens ObjectID genom att köra:</span><span class="sxs-lookup"><span data-stu-id="5e40d-149">Find the guest user's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="5e40d-150">Kör sedan följande med lämpliga värden för ObjectID, GivenName, Efternamn, DisplayName och Telefonnummer.</span><span class="sxs-lookup"><span data-stu-id="5e40d-150">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-articles"></a><span data-ttu-id="5e40d-151">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="5e40d-151">Related articles</span></span>

[<span data-ttu-id="5e40d-152">Hantera gruppmedlemskap i administrationscentret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5e40d-152">Manage Group membership in the Microsoft 365 admin center</span></span>](add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="5e40d-153">Granskningar av Azure Active Directory-åtkomst</span><span class="sxs-lookup"><span data-stu-id="5e40d-153">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="5e40d-154">Set-AzureAdUser</span><span class="sxs-lookup"><span data-stu-id="5e40d-154">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
