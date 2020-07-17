---
title: Hantera gäståtkomst i Microsoft 365-grupper
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
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
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Lär dig hur du lägger till gäster i en Microsoft 365-grupp, visar gästanvändare och använder PowerShell för att styra gäståtkomsten.
ms.openlocfilehash: 0322bd269f1c5637627461d136b40f6af4fc9540
ms.sourcegitcommit: 4512f54ba80d869d4c04e8f9bd897d1878280852
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "44854252"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="9d491-103">Hantera gäståtkomst i Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="9d491-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="9d491-104">Som standard är gäståtkomst för Microsoft 365-grupper aktiverat för din organisation.</span><span class="sxs-lookup"><span data-stu-id="9d491-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="9d491-105">Administratörer kan styra om gäståtkomst till grupper ska tillåtas för hela organisationen eller enskilda grupper.</span><span class="sxs-lookup"><span data-stu-id="9d491-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="9d491-106">När gruppmedlemmarna är aktiverade kan de bjuda in gästanvändare till en Microsoft 365-grupp via Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="9d491-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="9d491-107">Inbjudningar skickas till gruppägaren för godkännande.</span><span class="sxs-lookup"><span data-stu-id="9d491-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="9d491-108">När gästanvändaren har godkänts läggs den till i katalogen och gruppen.</span><span class="sxs-lookup"><span data-stu-id="9d491-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="9d491-109">Yammer Enterprise-nätverk som är i inbyggt läge eller [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) stöder inte nätverksgäster.</span><span class="sxs-lookup"><span data-stu-id="9d491-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) do not support network guests.</span></span>
> <span data-ttu-id="9d491-110">Microsoft 365 Connected Yammer-grupper stöder för närvarande inte gäståtkomst, men du kan skapa icke-anslutna externa grupper i Yammer-nätverket.</span><span class="sxs-lookup"><span data-stu-id="9d491-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="9d491-111">Instruktioner [finns i Skapa och hantera externa grupper i Yammer.](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups)</span><span class="sxs-lookup"><span data-stu-id="9d491-111">See [Create and manage external groups in Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="9d491-112">Gäståtkomst i grupper används ofta som en del av ett bredare scenario som innehåller SharePoint eller Teams.</span><span class="sxs-lookup"><span data-stu-id="9d491-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="9d491-113">Dessa tjänster har sina egna inställningar för gästdelning.</span><span class="sxs-lookup"><span data-stu-id="9d491-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="9d491-114">Fullständiga instruktioner för hur du konfigurerar gästdelning mellan grupper, SharePoint och Teams finns i:</span><span class="sxs-lookup"><span data-stu-id="9d491-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="9d491-115">Samarbeta med gäster på en webbplats</span><span class="sxs-lookup"><span data-stu-id="9d491-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="9d491-116">Samarbeta med gäster i ett team</span><span class="sxs-lookup"><span data-stu-id="9d491-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="9d491-117">Hantera gäståtkomst för grupper</span><span class="sxs-lookup"><span data-stu-id="9d491-117">Manage groups guest access</span></span>

<span data-ttu-id="9d491-118">Om du vill aktivera eller inaktivera gäståtkomst i grupper kan du göra det i administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9d491-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="9d491-119">I administrationscentret går du till **Visa alla** inställningar \> **Settings** \> **Org inställningar** och välj **Microsoft 365-grupper**på fliken **Tjänster** .</span><span class="sxs-lookup"><span data-stu-id="9d491-119">In the admin center, go to **Show all** \> **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="9d491-120">På sidan **Microsoft 365 Grupper** väljer du om du vill låta personer utanför organisationen komma åt gruppresurser eller låta gruppägare lägga till personer utanför organisationen i grupper.</span><span class="sxs-lookup"><span data-stu-id="9d491-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="9d491-121">Lägga till gäster i en Microsoft 365-grupp från administrationscentret</span><span class="sxs-lookup"><span data-stu-id="9d491-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="9d491-122">Om gästen redan finns i katalogen kan du lägga till dem i dina grupper från administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9d491-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span>
  
1. <span data-ttu-id="9d491-123">Gå till sidan **Groups**  >  **Gruppergrupper i** administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="9d491-123">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="9d491-124">Klicka på den grupp som du vill lägga till gästen i och välj **Visa alla och hantera medlemmar** på fliken **Medlemmar.**</span><span class="sxs-lookup"><span data-stu-id="9d491-124">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="9d491-125">Välj **Lägg till medlemmar**och välj namnet på den gäst som du vill lägga till.</span><span class="sxs-lookup"><span data-stu-id="9d491-125">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="9d491-126">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="9d491-126">Select **Save**.</span></span>

<span data-ttu-id="9d491-127">Om du vill lägga till en gäst i katalogen direkt kan du [lägga till Azure Active Directory B2B-samarbetsanvändare i Azure-portalen](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span><span class="sxs-lookup"><span data-stu-id="9d491-127">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="9d491-128">Om du vill redigera någon av en gästs information kan du [lägga till eller uppdatera en användares profilinformation med Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="9d491-128">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>
  
## <a name="block-guest-users-from-a-specific-group"></a><span data-ttu-id="9d491-129">Blockera gästanvändare från en viss grupp</span><span class="sxs-lookup"><span data-stu-id="9d491-129">Block guest users from a specific group</span></span>

<span data-ttu-id="9d491-130">Om du vill ge gäståtkomst till de flesta grupper, men har några där du vill förhindra gäståtkomst, kan du blockera gäståtkomst för enskilda grupper med hjälp av Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9d491-130">If you want to allow guest access to most groups, but have some where you want to prevent guest access, you can block guest access for individual groups by using Microsoft PowerShell.</span></span>

<span data-ttu-id="9d491-131">Du måste använda förhandsversionen av [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (modulnamnet **AzureADPreview)** för att ändra inställningen för gäståtkomst på gruppnivå:</span><span class="sxs-lookup"><span data-stu-id="9d491-131">You must use the preview version of [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="9d491-132">Om du inte har installerat någon version av Azure AD PowerShell-modulen tidigare läser [du Installera Azure AD-modulen](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) och följer instruktionerna för att installera den offentliga förhandsversionen.</span><span class="sxs-lookup"><span data-stu-id="9d491-132">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="9d491-133">Om du har installerat 2.0-versionen för allmän tillgänglighet av Azure AD PowerShell-modulen (AzureAD) måste du avinstallera den genom att `Uninstall-Module AzureAD` köras i PowerShell-sessionen och sedan installera förhandsversionen genom att köra `Install-Module AzureADPreview` .</span><span class="sxs-lookup"><span data-stu-id="9d491-133">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="9d491-134">Om du redan har installerat förhandsversionen kör du `Install-Module AzureADPreview` för att kontrollera att den är den senaste versionen av den här modulen.</span><span class="sxs-lookup"><span data-stu-id="9d491-134">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="9d491-135">Du måste ha globala administratörsrättigheter för att kunna köra dessa kommandon.</span><span class="sxs-lookup"><span data-stu-id="9d491-135">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="9d491-136">Kör följande skript och ändra */<GroupName/>* till namnet på den grupp där du vill blockera gäståtkomst.</span><span class="sxs-lookup"><span data-stu-id="9d491-136">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="9d491-137">Om du vill verifiera inställningarna kör du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="9d491-137">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="9d491-138">Verifieringen ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="9d491-138">The verification looks like this:</span></span>
    
![Skärmbild av PowerShell-fönstret som visar att gästgruppsåtkomsten har angetts till false.](../../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="9d491-140">Tillåt eller blockera gäståtkomst baserat på deras domän</span><span class="sxs-lookup"><span data-stu-id="9d491-140">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="9d491-141">Du kan tillåta eller blockera gästanvändare som använder en viss domän.</span><span class="sxs-lookup"><span data-stu-id="9d491-141">You can allow or block guest users who are using a specific domain.</span></span> <span data-ttu-id="9d491-142">Om ditt företag (Contoso) till exempel har ett partnerskap med ett annat företag (Fabrikam) kan du lägga till Fabrikam i listan Tillåt så att användarna kan lägga till dessa gäster i sina grupper.</span><span class="sxs-lookup"><span data-stu-id="9d491-142">For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="9d491-143">Mer information finns i [Tillåt eller blockera inbjudningar till B2B-användare från specifika organisationer](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="9d491-143">For more information, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="9d491-144">Lägga till gäster i den globala adresslistan</span><span class="sxs-lookup"><span data-stu-id="9d491-144">Add guests to the global address list</span></span>

<span data-ttu-id="9d491-145">Som standard visas inte gäster i exchange-listan över globala adresser.</span><span class="sxs-lookup"><span data-stu-id="9d491-145">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="9d491-146">Följ stegen nedan för att göra en gäst synlig i den globala adresslistan.</span><span class="sxs-lookup"><span data-stu-id="9d491-146">Use the steps listed below to make a guest visible in the global address list.</span></span>

<span data-ttu-id="9d491-147">Hitta gästanvändarens ObjectID genom att köra:</span><span class="sxs-lookup"><span data-stu-id="9d491-147">Find the guest user's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="9d491-148">Kör sedan följande med lämpliga värden för ObjectID, GivenName, Surname, DisplayName och TelephoneNumber.</span><span class="sxs-lookup"><span data-stu-id="9d491-148">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-articles"></a><span data-ttu-id="9d491-149">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="9d491-149">Related articles</span></span>

[<span data-ttu-id="9d491-150">Hantera gruppmedlemskap i administrationscentret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9d491-150">Manage group membership in the Microsoft 365 admin center</span></span>](add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="9d491-151">Azure Active Directory-åtkomstgranskningar</span><span class="sxs-lookup"><span data-stu-id="9d491-151">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="9d491-152">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="9d491-152">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
