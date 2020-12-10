---
title: Hantera en isolerad SharePoint Online-gruppwebbplats
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: Hantera en isolerad SharePoint Online-gruppwebbplats, lägga till nya användare och grupper, ta bort användare och grupper och skapa en undermapp med anpassade behörigheter.
ms.openlocfilehash: 1e244738071b434efd09e8fd700462bbef7e116a
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616770"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="d516b-103">Hantera en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="d516b-103">Manage an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 <span data-ttu-id="d516b-104">**Sammanfattning:** Hantera din isolerade SharePoint Online-gruppwebbplats med de här procedurerna.</span><span class="sxs-lookup"><span data-stu-id="d516b-104">**Summary:** Manage your isolated SharePoint Online team site with these procedures.</span></span>

<span data-ttu-id="d516b-105">I den här artikeln beskrivs vanliga hanterings åtgärder för en isolerad SharePoint Online-gruppwebbplats.</span><span class="sxs-lookup"><span data-stu-id="d516b-105">This article describes common management operations for an isolated SharePoint Online team site.</span></span>

## <a name="add-a-new-user"></a><span data-ttu-id="d516b-106">Lägga till en ny användare</span><span class="sxs-lookup"><span data-stu-id="d516b-106">Add a new user</span></span>

<span data-ttu-id="d516b-107">När någon ny ansluter till webbplatsen måste du bestämma deras deltagande på webbplatsen:</span><span class="sxs-lookup"><span data-stu-id="d516b-107">When someone new joins the site, you must decide their level of participation in the site:</span></span>

- <span data-ttu-id="d516b-108">Administration: lägga till det nya användar kontot i gruppen webbplats administratörs åtkomst</span><span class="sxs-lookup"><span data-stu-id="d516b-108">Administration: Add the new user account to the site admins access group</span></span>

- <span data-ttu-id="d516b-109">Aktivt samarbete: lägga till användar kontot i gruppen webbplats medlemmar</span><span class="sxs-lookup"><span data-stu-id="d516b-109">Active collaboration: Add the user account to the site members access group</span></span>

- <span data-ttu-id="d516b-110">Visa: lägga till användar kontot i gruppen webbplats visnings åtkomst</span><span class="sxs-lookup"><span data-stu-id="d516b-110">Viewing: Add the user account to the site viewers access group</span></span>

<span data-ttu-id="d516b-111">Om du hanterar användar konton och grupper via AD DS (Active Directory Domain Services) lägger du till de användare du vill använda i de lämpliga åtkomst grupperna med din vanliga AD DS-användare och grupp hanterings procedurer och väntar på synkronisering med ditt abonnemang.</span><span class="sxs-lookup"><span data-stu-id="d516b-111">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add the appropriate users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="d516b-112">Om du hanterar användar konton och grupper via Microsoft 365 kan du använda Microsoft 365 Admin Center eller Microsoft PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d516b-112">If you are managing user accounts and groups through Microsoft 365, you can use the Microsoft 365 admin center or Microsoft PowerShell:</span></span>

- <span data-ttu-id="d516b-113">För administrations centret för Microsoft 365 loggar du in med ett användar konto som har tilldelats rollen användar konto administratör eller företags administratör och använder grupper för att lägga till rätt användare i lämpliga åtkomst grupper.</span><span class="sxs-lookup"><span data-stu-id="d516b-113">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate users to the appropriate access groups.</span></span>

- <span data-ttu-id="d516b-114">För PowerShell, [Anslut först med Azure Active Directory PowerShell för Graph](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="d516b-114">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span> <span data-ttu-id="d516b-115">Om du vill lägga till ett användar konto i en åtkomst grupp med dess huvud namn (UPN) använder du följande PowerShell-kommando block:</span><span class="sxs-lookup"><span data-stu-id="d516b-115">To add a user account to an access group with its user principal name (UPN), use the following PowerShell command block:</span></span>

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="d516b-116">Om du vill lägga till ett användar konto i en åtkomst grupp med dess visnings namn använder du följande PowerShell-kommando block:</span><span class="sxs-lookup"><span data-stu-id="d516b-116">To add a user account to an access group with its display name, use the following PowerShell command block:</span></span>

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a><span data-ttu-id="d516b-117">Lägga till en ny grupp</span><span class="sxs-lookup"><span data-stu-id="d516b-117">Add a new group</span></span>

<span data-ttu-id="d516b-118">Om du vill lägga till åtkomst till en hel grupp måste du bestämma hur många medlemmar i gruppen som ska delta på webbplatsen:</span><span class="sxs-lookup"><span data-stu-id="d516b-118">To add access to an entire group, you must decide the level of participation of all the members of the group in the site:</span></span>

- <span data-ttu-id="d516b-119">Administration: lägga till gruppen i gruppen webbplats administratörer</span><span class="sxs-lookup"><span data-stu-id="d516b-119">Administration: Add the group to the site admins access group</span></span>

- <span data-ttu-id="d516b-120">Aktivt samarbete: lägga till gruppen i gruppen webbplats medlemmar</span><span class="sxs-lookup"><span data-stu-id="d516b-120">Active collaboration: Add the group to the site members access group</span></span>

- <span data-ttu-id="d516b-121">Visa: lägga till gruppen i gruppen webbplats visnings program</span><span class="sxs-lookup"><span data-stu-id="d516b-121">Viewing: Add the group to the site viewers access group</span></span>

<span data-ttu-id="d516b-122">Om du använder AD DS för att hantera användar konton och grupper kan du lägga till lämpliga grupper i lämpliga grupper med hjälp av dina vanliga procedurer för AD DS-användare och-grupper och vänta på synkronisering med ditt abonnemang.</span><span class="sxs-lookup"><span data-stu-id="d516b-122">If you are managing user accounts and groups through AD DS, add the appropriate groups to the appropriate groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="d516b-123">Om du hanterar användar konton och grupper via Office 365 kan du använda Microsoft 365 Admin Center eller PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d516b-123">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="d516b-124">För administrations centret för Microsoft 365 loggar du in med ett användar konto som har tilldelats rollen användar konto administratör eller företags administratör och använder grupper för att lägga till lämpliga grupper i lämpliga åtkomst grupper.</span><span class="sxs-lookup"><span data-stu-id="d516b-124">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate groups to the appropriate access groups.</span></span>

- <span data-ttu-id="d516b-125">För PowerShell, [Anslut först med Azure Active Directory PowerShell för Graph](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="d516b-125">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 <span data-ttu-id="d516b-126">Använd sedan följande PowerShell-kommandon:</span><span class="sxs-lookup"><span data-stu-id="d516b-126">Then, use the following PowerShell commands:</span></span>

```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a><span data-ttu-id="d516b-127">Ta bort en användare</span><span class="sxs-lookup"><span data-stu-id="d516b-127">Remove a user</span></span>

<span data-ttu-id="d516b-128">När någons åtkomst måste tas bort från webbplatsen tar du bort dem från den åtkomst grupp för vilken de för närvarande är medlemmar baserat på deras deltagande på webbplatsen:</span><span class="sxs-lookup"><span data-stu-id="d516b-128">When someone's access must be removed from the site, you remove them from the access group for which they are currently a member based on their participation in the site:</span></span>

- <span data-ttu-id="d516b-129">Administration: ta bort användar kontot från gruppen webbplats administratörs åtkomst</span><span class="sxs-lookup"><span data-stu-id="d516b-129">Administration: Remove the user account from the site admins access group</span></span>

- <span data-ttu-id="d516b-130">Aktivt samarbete: ta bort användar kontot från gruppen webbplats medlemmar</span><span class="sxs-lookup"><span data-stu-id="d516b-130">Active collaboration: Remove the user account from the site members access group</span></span>

- <span data-ttu-id="d516b-131">Visa: ta bort användar kontot från gruppen webbplats visnings åtkomst</span><span class="sxs-lookup"><span data-stu-id="d516b-131">Viewing: Remove the user account from the site viewers access group</span></span>

<span data-ttu-id="d516b-132">Om du hanterar användar konton och grupper via AD DS tar du bort de lämpliga användarna från lämpliga åtkomst grupper med hjälp av dina vanliga procedurer för AD DS-användare och-grupper och väntar på synkronisering med ditt abonnemang.</span><span class="sxs-lookup"><span data-stu-id="d516b-132">If you are managing user accounts and groups through AD DS, remove the appropriate users from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="d516b-133">Om du hanterar användar konton och grupper via Office 365 kan du använda Microsoft 365 Admin Center eller PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d516b-133">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="d516b-134">För administrations centret för Microsoft 365 loggar du in med ett användar konto som har tilldelats rollen användar konto administratör eller företags administratör och använder grupper för att ta bort lämpliga användare från lämpliga åtkomst grupper.</span><span class="sxs-lookup"><span data-stu-id="d516b-134">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate users from the appropriate access groups.</span></span>

- <span data-ttu-id="d516b-135">För PowerShell, [Anslut först med Azure Active Directory PowerShell för Graph](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="d516b-135">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="d516b-136">Om du vill ta bort ett användar konto från en åtkomst grupp med dess UPN kan du använda följande PowerShell-kommando block:</span><span class="sxs-lookup"><span data-stu-id="d516b-136">To remove a user account from an access group with its UPN, use the following PowerShell command block:</span></span>

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="d516b-137">Om du vill ta bort ett användar konto från en åtkomst grupp med dess visnings namn kan du använda följande PowerShell-kommando block:</span><span class="sxs-lookup"><span data-stu-id="d516b-137">To remove a user account from an access group with its display name, use the following PowerShell command block:</span></span>

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a><span data-ttu-id="d516b-138">Ta bort en grupp</span><span class="sxs-lookup"><span data-stu-id="d516b-138">Remove a group</span></span>

<span data-ttu-id="d516b-139">Om du vill ta bort åtkomst för en hel grupp tar du bort gruppen från den åtkomst grupp för vilken de för närvarande är medlemmar baserat på deras deltagande på webbplatsen:</span><span class="sxs-lookup"><span data-stu-id="d516b-139">To remove access for an entire group, you remove the group from the access group for which they are currently a member based on their participation in the site:</span></span>

- <span data-ttu-id="d516b-140">Administration: ta bort gruppen från gruppen webbplats administratörer</span><span class="sxs-lookup"><span data-stu-id="d516b-140">Administration: Remove the group from the site admins access group</span></span>

- <span data-ttu-id="d516b-141">Aktivt samarbete: ta bort gruppen från gruppen webbplats medlemmar</span><span class="sxs-lookup"><span data-stu-id="d516b-141">Active collaboration: Remove the group from the site members access group</span></span>

- <span data-ttu-id="d516b-142">Visa: ta bort gruppen från gruppen webbplats visnings åtkomst</span><span class="sxs-lookup"><span data-stu-id="d516b-142">Viewing: Remove the group from the site viewers access group</span></span>

<span data-ttu-id="d516b-143">Om du hanterar användar konton och grupper via Windows Server Active Directory tar du bort lämpliga grupper från lämpliga åtkomst grupper med hjälp av dina vanliga procedurer för AD DS-användare och grupp hantering och väntar på synkronisering med ditt abonnemang.</span><span class="sxs-lookup"><span data-stu-id="d516b-143">If you are managing user accounts and groups through Windows Server Active Directory, remove the appropriate groups from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="d516b-144">Om du hanterar användar konton och grupper via Office 365 kan du använda Microsoft 365 Admin Center eller PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d516b-144">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="d516b-145">För administrations centret för Microsoft 365 loggar du in med ett användar konto som har tilldelats rollen användar konto administratör eller företags administratör och använder grupper för att ta bort lämpliga grupper från lämpliga åtkomst grupper.</span><span class="sxs-lookup"><span data-stu-id="d516b-145">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate groups from the appropriate access groups.</span></span>

- <span data-ttu-id="d516b-146">För PowerShell, [Anslut först med Azure Active Directory PowerShell för Graph](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="d516b-146">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="d516b-147">Om du vill ta bort en grupp från en åtkomst grupp med deras visnings namn kan du använda följande PowerShell-kommando block:</span><span class="sxs-lookup"><span data-stu-id="d516b-147">To remove a group from an access group using their display names, use the following PowerShell command block:</span></span>

```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a><span data-ttu-id="d516b-148">Skapa en undermapp för dokument med anpassade behörigheter</span><span class="sxs-lookup"><span data-stu-id="d516b-148">Create a documents subfolder with custom permissions</span></span>

<span data-ttu-id="d516b-149">I vissa fall måste en delmängd av de personer som arbetar inom den isolerade webbplatsen vara en privat plats för att samar beta.</span><span class="sxs-lookup"><span data-stu-id="d516b-149">In some cases, a subset of the people working within the isolated site need a more private place to collaborate.</span></span> <span data-ttu-id="d516b-150">För SharePoint Online-webbplatser kan du skapa en undermapp i mappen dokument på webbplatsen och tilldela anpassade behörigheter.</span><span class="sxs-lookup"><span data-stu-id="d516b-150">For SharePoint Online sites, you can create a subfolder in the Documents folder of the site and assign custom permissions.</span></span> <span data-ttu-id="d516b-151">Dessa utan behörigheter visas inte i undermappen.</span><span class="sxs-lookup"><span data-stu-id="d516b-151">Those without permissions will not see the subfolder.</span></span>

<span data-ttu-id="d516b-152">Gör så här om du vill skapa en undermapp för dokument med anpassade behörigheter:</span><span class="sxs-lookup"><span data-stu-id="d516b-152">To create a documents subfolder with custom permissions, do the following:</span></span>

1. <span data-ttu-id="d516b-153">Logga in på ett konto som är medlem i gruppen Administratörer för webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="d516b-153">Sign in to an account that is a member of the admins access group for the site.</span></span> <span data-ttu-id="d516b-154">Mer information finns i [Så här loggar du in i Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="d516b-154">For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="d516b-155">Gå till den isolerade grupp webbplatsen och klicka på **dokument**.</span><span class="sxs-lookup"><span data-stu-id="d516b-155">Go to the isolated team site and click **Documents**.</span></span>

3. <span data-ttu-id="d516b-156">Bläddra till mappen i mappen dokument som ska innehålla undermappen med anpassade behörigheter, skapa mappen och öppna den.</span><span class="sxs-lookup"><span data-stu-id="d516b-156">Browse to the folder in the documents folder that will contain the subfolder with custom permissions, create the folder, and then open it.</span></span>

4. <span data-ttu-id="d516b-157">Klicka på **dela**.</span><span class="sxs-lookup"><span data-stu-id="d516b-157">Click **Share**.</span></span>

5. <span data-ttu-id="d516b-158">Klicka på **delas med > Avancerat**.</span><span class="sxs-lookup"><span data-stu-id="d516b-158">Click **Shared with > Advanced**.</span></span>

6. <span data-ttu-id="d516b-159">Klicka på **sluta ärva behörigheter** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="d516b-159">Click **Stop inheriting permissions**, and then click **OK**.</span></span>

7. <span data-ttu-id="d516b-160">Klicka på **dela**.</span><span class="sxs-lookup"><span data-stu-id="d516b-160">Click **Share**.</span></span>

8. <span data-ttu-id="d516b-161">Klicka på **delas med > Avancerat**.</span><span class="sxs-lookup"><span data-stu-id="d516b-161">Click **Shared with > Advanced**.</span></span>

9. <span data-ttu-id="d516b-162">Klicka på **bevilja behörigheter > delas med > Avancerat**.</span><span class="sxs-lookup"><span data-stu-id="d516b-162">Click **Grant Permissions > Shared with > Advanced**.</span></span>

10. <span data-ttu-id="d516b-163">Klicka på **\<site name> medlemmar i listan** på sidan behörigheter.</span><span class="sxs-lookup"><span data-stu-id="d516b-163">On the permissions page, click **\<site name> Members in the list**.</span></span>

11. <span data-ttu-id="d516b-164">På sidan **\<site name> medlemmar** markerar du kryss rutan bredvid gruppen webbplats medlemmar, klickar på **åtgärder**, klickar på **ta bort användare från grupp** och klickar sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="d516b-164">On the **\<site name> Members** page, select the checkmark next to the site members access group, click **Actions**, click **Remove users from group**, and then click **OK**.</span></span>

12. <span data-ttu-id="d516b-165">Om du vill lägga till specifika medlemmar i den här undermappen klickar du på **ny > lägga till användare**.</span><span class="sxs-lookup"><span data-stu-id="d516b-165">To add specific members to this subfolder, click **New > Add users**.</span></span>

13. <span data-ttu-id="d516b-166">I dialog rutan **dela** skriver du namnen på de användar konton som kan samar beta med filer i undermappen och klickar sedan på **dela**.</span><span class="sxs-lookup"><span data-stu-id="d516b-166">In the **Share** dialog box, type the names of the user accounts that can collaborate on files in the subfolder, and then click **Share**.</span></span>

14. <span data-ttu-id="d516b-167">Uppdatera webb sidan för att se de nya resultaten.</span><span class="sxs-lookup"><span data-stu-id="d516b-167">Refresh the web page to see the new results.</span></span>

15. <span data-ttu-id="d516b-168">Klicka på gruppen **\<site name> besökare** under **grupper** i det vänstra navigerings fältet och Använd stegen 11-14 för att ange den uppsättning användar konton som kan visa filerna i undermappen (efter behov).</span><span class="sxs-lookup"><span data-stu-id="d516b-168">Under **Groups** in the left navigation, click the **\<site name> Visitors** group and use steps 11-14 to specify the set of user accounts that can view the files in the subfolder (as needed).</span></span>

16. <span data-ttu-id="d516b-169">Under **grupper** i det vänstra navigerings fältet klickar du på gruppen **\<site name> ägare** och använder steg 11-14 för att ange den uppsättning användar konton som kan hantera behörigheterna i undermappen (efter behov).</span><span class="sxs-lookup"><span data-stu-id="d516b-169">Under **Groups** in the left navigation, click the **\<site name> Owners** group and use steps 11-14 to specify the set of user accounts that can administer the permissions in the subfolder (as needed).</span></span>

17. <span data-ttu-id="d516b-170">Stäng fliken **personer och grupper** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="d516b-170">Close the **People and Groups** tab in your browser.</span></span>

## <a name="see-also"></a><span data-ttu-id="d516b-171">Se även</span><span class="sxs-lookup"><span data-stu-id="d516b-171">See Also</span></span>

[<span data-ttu-id="d516b-172">Isolerade SharePoint Online-gruppwebbplatser</span><span class="sxs-lookup"><span data-stu-id="d516b-172">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="d516b-173">Utforma en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="d516b-173">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="d516b-174">Distribuera en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="d516b-174">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)
