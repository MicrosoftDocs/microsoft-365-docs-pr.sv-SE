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
ms.custom: Ent_Solutions
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: 'Sammanfattning: Hantera din isolerade SharePoint Online-gruppwebbplats med dessa procedurer.'
ms.openlocfilehash: 59c86c869ed38c3e64ff19974660cf96ec4c715e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42810399"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="52dd7-103">Hantera en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="52dd7-103">Manage an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="52dd7-104">**Sammanfattning:** Hantera din isolerade SharePoint Online-gruppwebbplats med dessa procedurer.</span><span class="sxs-lookup"><span data-stu-id="52dd7-104">**Summary:** Manage your isolated SharePoint Online team site with these procedures.</span></span>
  
<span data-ttu-id="52dd7-105">I den här artikeln beskrivs vanliga hanteringsåtgärder för en isolerad SharePoint Online-gruppwebbplats.</span><span class="sxs-lookup"><span data-stu-id="52dd7-105">This article describes common management operations for an isolated SharePoint Online team site.</span></span>
  
## <a name="add-a-new-user"></a><span data-ttu-id="52dd7-106">Lägga till en ny användare</span><span class="sxs-lookup"><span data-stu-id="52dd7-106">Add a new user</span></span>

<span data-ttu-id="52dd7-107">När någon ny ansluter till webbplatsen måste du bestämma deras deltagande nivå på webbplatsen:</span><span class="sxs-lookup"><span data-stu-id="52dd7-107">When someone new joins the site, you must decide their level of participation in the site:</span></span>
  
- <span data-ttu-id="52dd7-108">Administration: Lägga till det nya användarkontot i åtkomstgruppen för webbplatsadministratörer</span><span class="sxs-lookup"><span data-stu-id="52dd7-108">Administration: Add the new user account to the site admins access group</span></span>
    
- <span data-ttu-id="52dd7-109">Aktivt samarbete: Lägga till användarkontot i åtkomstgruppen för webbplatsmedlemmar</span><span class="sxs-lookup"><span data-stu-id="52dd7-109">Active collaboration: Add the user account to the site members access group</span></span>
    
- <span data-ttu-id="52dd7-110">Visa: Lägga till användarkontot i åtkomstgruppen för webbplatstittare</span><span class="sxs-lookup"><span data-stu-id="52dd7-110">Viewing: Add the user account to the site viewers access group</span></span>
    
<span data-ttu-id="52dd7-111">Om du hanterar användarkonton och grupper via AD DS (Active Directory Domain Services) lägger du till lämpliga användare i lämpliga åtkomstgrupper med hjälp av dina normala AD DS-användar- och grupphanteringsprocedurer och väntar på synkronisering med Office 365 Prenumeration.</span><span class="sxs-lookup"><span data-stu-id="52dd7-111">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add the appropriate users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="52dd7-112">Om du hanterar användarkonton och grupper via Office 365 kan du använda administrationscentret för Microsoft 365 eller Microsoft PowerShell:</span><span class="sxs-lookup"><span data-stu-id="52dd7-112">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or Microsoft PowerShell:</span></span>
  
- <span data-ttu-id="52dd7-113">Logga in med ett användarkonto som har tilldelats rollen Användarkontoadministratör eller företagsadministratör i Microsoft 365 och använd grupper för att lägga till lämpliga användare i lämpliga åtkomstgrupper.</span><span class="sxs-lookup"><span data-stu-id="52dd7-113">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate users to the appropriate access groups.</span></span>
    
- <span data-ttu-id="52dd7-114">För PowerShell ansluter du först [med Azure Active Directory PowerShell för Graph-modulen](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="52dd7-114">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span> <span data-ttu-id="52dd7-115">Om du vill lägga till ett användarkonto i en åtkomstgrupp med dess användarnamn (UPN) använder du följande PowerShell-kommandoblock:</span><span class="sxs-lookup"><span data-stu-id="52dd7-115">To add a user account to an access group with its user principal name (UPN), use the following PowerShell command block:</span></span>
    
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="52dd7-116">Om du vill lägga till ett användarkonto i en åtkomstgrupp med visningsnamnet använder du följande PowerShell-kommandoblock:</span><span class="sxs-lookup"><span data-stu-id="52dd7-116">To add a user account to an access group with its display name, use the following PowerShell command block:</span></span>

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a><span data-ttu-id="52dd7-117">Lägga till en ny grupp</span><span class="sxs-lookup"><span data-stu-id="52dd7-117">Add a new group</span></span>

<span data-ttu-id="52dd7-118">Om du vill lägga till åtkomst till en hel grupp måste du bestämma hur många medlemmar i gruppen på webbplatsen ska delta:</span><span class="sxs-lookup"><span data-stu-id="52dd7-118">To add access to an entire group, you must decide the level of participation of all the members of the group in the site:</span></span>
  
- <span data-ttu-id="52dd7-119">Administration: Lägga till gruppen i åtkomstgruppen för webbplatsadministratörer</span><span class="sxs-lookup"><span data-stu-id="52dd7-119">Administration: Add the group to the site admins access group</span></span>
    
- <span data-ttu-id="52dd7-120">Aktivt samarbete: Lägga till gruppen i åtkomstgruppen för webbplatsmedlemmar</span><span class="sxs-lookup"><span data-stu-id="52dd7-120">Active collaboration: Add the group to the site members access group</span></span>
    
- <span data-ttu-id="52dd7-121">Visa: Lägga till gruppen i åtkomstgruppen för webbplatstittare</span><span class="sxs-lookup"><span data-stu-id="52dd7-121">Viewing: Add the group to the site viewers access group</span></span>
    
<span data-ttu-id="52dd7-122">Om du hanterar användarkonton och grupper via AD DS lägger du till lämpliga grupper i lämpliga grupper med hjälp av dina normala AD DS-användar- och grupphanteringsprocedurer och väntar på synkronisering med din Office 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="52dd7-122">If you are managing user accounts and groups through AD DS, add the appropriate groups to the appropriate groups using your normal AD DS user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="52dd7-123">Om du hanterar användarkonton och grupper via Office 365 kan du använda administrationscentret för Microsoft 365 eller PowerShell:</span><span class="sxs-lookup"><span data-stu-id="52dd7-123">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="52dd7-124">Logga in med ett användarkonto som har tilldelats rollen Användarkontoadministratör eller företagsadministratör i Microsoft 365 och använd grupper för att lägga till lämpliga grupper i lämpliga åtkomstgrupper.</span><span class="sxs-lookup"><span data-stu-id="52dd7-124">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate groups to the appropriate access groups.</span></span>
    
- <span data-ttu-id="52dd7-125">För PowerShell ansluter du först [med Azure Active Directory PowerShell för Graph-modulen](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="52dd7-125">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 <span data-ttu-id="52dd7-126">Använd sedan följande PowerShell-kommandon:</span><span class="sxs-lookup"><span data-stu-id="52dd7-126">Then, use the following PowerShell commands:</span></span>
 
```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a><span data-ttu-id="52dd7-127">Ta bort en användare</span><span class="sxs-lookup"><span data-stu-id="52dd7-127">Remove a user</span></span>

<span data-ttu-id="52dd7-128">När någons åtkomst måste tas bort från webbplatsen tar du bort dem från den åtkomstgrupp som de för närvarande är medlemmar för baserat på deras deltagande på webbplatsen:</span><span class="sxs-lookup"><span data-stu-id="52dd7-128">When someone's access must be removed from the site, you remove them from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="52dd7-129">Administration: Ta bort användarkontot från åtkomstgruppen för webbplatsadministratörer</span><span class="sxs-lookup"><span data-stu-id="52dd7-129">Administration: Remove the user account from the site admins access group</span></span>
    
- <span data-ttu-id="52dd7-130">Aktivt samarbete: Ta bort användarkontot från åtkomstgruppen för webbplatsmedlemmar</span><span class="sxs-lookup"><span data-stu-id="52dd7-130">Active collaboration: Remove the user account from the site members access group</span></span>
    
- <span data-ttu-id="52dd7-131">Visa: Ta bort användarkontot från åtkomstgruppen för webbplatstittare</span><span class="sxs-lookup"><span data-stu-id="52dd7-131">Viewing: Remove the user account from the site viewers access group</span></span>
    
<span data-ttu-id="52dd7-132">Om du hanterar användarkonton och grupper via AD DS tar du bort lämpliga användare från lämpliga åtkomstgrupper med hjälp av dina normala AD DS-användar- och grupphanteringsprocedurer och väntar på synkronisering med din Office 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="52dd7-132">If you are managing user accounts and groups through AD DS, remove the appropriate users from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="52dd7-133">Om du hanterar användarkonton och grupper via Office 365 kan du använda administrationscentret för Microsoft 365 eller PowerShell:</span><span class="sxs-lookup"><span data-stu-id="52dd7-133">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="52dd7-134">Logga in med ett användarkonto som har tilldelats rollen Användarkontoadministratör eller företagsadministratör i Microsoft 365 och använd grupper för att ta bort lämpliga användare från lämpliga åtkomstgrupper.</span><span class="sxs-lookup"><span data-stu-id="52dd7-134">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate users from the appropriate access groups.</span></span>
    
- <span data-ttu-id="52dd7-135">För PowerShell ansluter du först [med Azure Active Directory PowerShell för Graph-modulen](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="52dd7-135">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="52dd7-136">Om du vill ta bort ett användarkonto från en åtkomstgrupp med UPN använder du följande PowerShell-kommandoblock:</span><span class="sxs-lookup"><span data-stu-id="52dd7-136">To remove a user account from an access group with its UPN, use the following PowerShell command block:</span></span>
    
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="52dd7-137">Om du vill ta bort ett användarkonto från en åtkomstgrupp med visningsnamnet använder du följande PowerShell-kommandoblock:</span><span class="sxs-lookup"><span data-stu-id="52dd7-137">To remove a user account from an access group with its display name, use the following PowerShell command block:</span></span>
    
```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a><span data-ttu-id="52dd7-138">Ta bort en grupp</span><span class="sxs-lookup"><span data-stu-id="52dd7-138">Remove a group</span></span>

<span data-ttu-id="52dd7-139">Om du vill ta bort åtkomsten för en hel grupp tar du bort gruppen från åtkomstgruppen som de för närvarande är medlemmar för baserat på deras deltagande på webbplatsen:</span><span class="sxs-lookup"><span data-stu-id="52dd7-139">To remove access for an entire group, you remove the group from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="52dd7-140">Administration: Ta bort gruppen från åtkomstgruppen för webbplatsadministratörer</span><span class="sxs-lookup"><span data-stu-id="52dd7-140">Administration: Remove the group from the site admins access group</span></span>
    
- <span data-ttu-id="52dd7-141">Aktivt samarbete: Ta bort gruppen från åtkomstgruppen för webbplatsmedlemmar</span><span class="sxs-lookup"><span data-stu-id="52dd7-141">Active collaboration: Remove the group from the site members access group</span></span>
    
- <span data-ttu-id="52dd7-142">Visa: Ta bort gruppen från åtkomstgruppen för webbplatstittare</span><span class="sxs-lookup"><span data-stu-id="52dd7-142">Viewing: Remove the group from the site viewers access group</span></span>
    
<span data-ttu-id="52dd7-143">Om du hanterar användarkonton och grupper via Windows Server Active Directory tar du bort lämpliga grupper från lämpliga åtkomstgrupper med hjälp av dina normala AD DS-användar- och grupphanteringsprocedurer och väntar på synkronisering med Office 365 Prenumeration.</span><span class="sxs-lookup"><span data-stu-id="52dd7-143">If you are managing user accounts and groups through Windows Server Active Directory, remove the appropriate groups from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="52dd7-144">Om du hanterar användarkonton och grupper via Office 365 kan du använda administrationscentret för Microsoft 365 eller PowerShell:</span><span class="sxs-lookup"><span data-stu-id="52dd7-144">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="52dd7-145">Logga in med ett användarkonto som har tilldelats rollen Användarkontoadministratör eller företagsadministratör i Microsoft 365 och använd grupper för att ta bort lämpliga grupper från lämpliga åtkomstgrupper.</span><span class="sxs-lookup"><span data-stu-id="52dd7-145">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate groups from the appropriate access groups.</span></span>
    
- <span data-ttu-id="52dd7-146">För PowerShell ansluter du först [med Azure Active Directory PowerShell för Graph-modulen](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="52dd7-146">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>    
<span data-ttu-id="52dd7-147">Om du vill ta bort en grupp från en åtkomstgrupp med hjälp av deras visningsnamn använder du följande PowerShell-kommandoblock:</span><span class="sxs-lookup"><span data-stu-id="52dd7-147">To remove a group from an access group using their display names, use the following PowerShell command block:</span></span>
    
```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a><span data-ttu-id="52dd7-148">Skapa en undermapp för dokument med anpassade behörigheter</span><span class="sxs-lookup"><span data-stu-id="52dd7-148">Create a documents subfolder with custom permissions</span></span>

<span data-ttu-id="52dd7-149">I vissa fall behöver en delmängd av de personer som arbetar på den isolerade webbplatsen en mer privat plats för att samarbeta.</span><span class="sxs-lookup"><span data-stu-id="52dd7-149">In some cases, a subset of the people working within the isolated site need a more private place to collaborate.</span></span> <span data-ttu-id="52dd7-150">För SharePoint Online-webbplatser kan du skapa en undermapp i mappen Dokument på webbplatsen och tilldela anpassade behörigheter.</span><span class="sxs-lookup"><span data-stu-id="52dd7-150">For SharePoint Online sites, you can create a subfolder in the Documents folder of the site and assign custom permissions.</span></span> <span data-ttu-id="52dd7-151">De utan behörighet ser inte undermappen.</span><span class="sxs-lookup"><span data-stu-id="52dd7-151">Those without permissions will not see the subfolder.</span></span>
  
<span data-ttu-id="52dd7-152">Så här skapar du en undermapp för dokument med anpassade behörigheter:</span><span class="sxs-lookup"><span data-stu-id="52dd7-152">To create a documents subfolder with custom permissions, do the following:</span></span>
  
1. <span data-ttu-id="52dd7-153">Logga in på Office 365 med ett konto som är medlem i administratörsåtkomstgruppen för webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="52dd7-153">Sign in to Office 365 with an account that is a member of the admins access group for the site.</span></span> <span data-ttu-id="52dd7-154">Mer information finns i [Var du kan logga in på Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="52dd7-154">For help, see [Where to sign in to Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="52dd7-155">Gå till den isolerade gruppwebbplatsen och klicka på **Dokument**.</span><span class="sxs-lookup"><span data-stu-id="52dd7-155">Go to the isolated team site and click **Documents**.</span></span>
    
3. <span data-ttu-id="52dd7-156">Bläddra till mappen i dokumentmappen som ska innehålla undermappen med anpassade behörigheter, skapa mappen och öppna den sedan.</span><span class="sxs-lookup"><span data-stu-id="52dd7-156">Browse to the folder in the documents folder that will contain the subfolder with custom permissions, create the folder, and then open it.</span></span>
    
4. <span data-ttu-id="52dd7-157">Klicka på **Dela**.</span><span class="sxs-lookup"><span data-stu-id="52dd7-157">Click **Share**.</span></span>
    
5. <span data-ttu-id="52dd7-158">Klicka på **Delas med > Avancerat**.</span><span class="sxs-lookup"><span data-stu-id="52dd7-158">Click **Shared with > Advanced**.</span></span>
    
6. <span data-ttu-id="52dd7-159">Klicka på **Sluta ärva behörigheter**och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="52dd7-159">Click **Stop inheriting permissions**, and then click **OK**.</span></span>
    
7. <span data-ttu-id="52dd7-160">Klicka på **Dela**.</span><span class="sxs-lookup"><span data-stu-id="52dd7-160">Click **Share**.</span></span>
    
8. <span data-ttu-id="52dd7-161">Klicka på **Delas med > Avancerat**.</span><span class="sxs-lookup"><span data-stu-id="52dd7-161">Click **Shared with > Advanced**.</span></span>
    
9. <span data-ttu-id="52dd7-162">Klicka på **Bevilja behörigheter > delas med > Avancerat**.</span><span class="sxs-lookup"><span data-stu-id="52dd7-162">Click **Grant Permissions > Shared with > Advanced**.</span></span>
    
10. <span data-ttu-id="52dd7-163">Klicka på \*\* \<webbplatsnamn> medlemmar i listan\*\*på behörighetssidan.</span><span class="sxs-lookup"><span data-stu-id="52dd7-163">On the permissions page, click **\<site name> Members in the list**.</span></span>
    
11. <span data-ttu-id="52dd7-164">Markera kryssrutan bredvid åtkomstgruppen för webbplatsmedlemmar på sidan \*\* \<Webbplatsnamn> medlemmar,\*\* klicka på **Åtgärder,** klicka på **Ta bort användare från gruppen**och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="52dd7-164">On the **\<site name> Members** page, select the checkmark next to the site members access group, click **Actions**, click **Remove users from group**, and then click **OK**.</span></span>
    
12. <span data-ttu-id="52dd7-165">Om du vill lägga till specifika medlemmar i den här undermappen klickar du på **Ny > Lägg till användare**.</span><span class="sxs-lookup"><span data-stu-id="52dd7-165">To add specific members to this subfolder, click **New > Add users**.</span></span>
    
13. <span data-ttu-id="52dd7-166">I dialogrutan **Dela** skriver du namnen på de användarkonton som kan samarbeta om filer i undermappen och klickar sedan på **Dela**.</span><span class="sxs-lookup"><span data-stu-id="52dd7-166">In the **Share** dialog box, type the names of the user accounts that can collaborate on files in the subfolder, and then click **Share**.</span></span>
    
14. <span data-ttu-id="52dd7-167">Uppdatera webbsidan för att se de nya resultaten.</span><span class="sxs-lookup"><span data-stu-id="52dd7-167">Refresh the web page to see the new results.</span></span>
    
15. <span data-ttu-id="52dd7-168">Under **Grupper** i den vänstra navigeringen klickar du på \*\* \<webbplatsnamnet> besöksgruppen\*\* och använder steg 11-14 för att ange den uppsättning användarkonton som kan visa filerna i undermappen (efter behov).</span><span class="sxs-lookup"><span data-stu-id="52dd7-168">Under **Groups** in the left navigation, click the **\<site name> Visitors** group and use steps 11-14 to specify the set of user accounts that can view the files in the subfolder (as needed).</span></span>
    
16. <span data-ttu-id="52dd7-169">Under **Grupper** i den vänstra navigeringen klickar du på \*\* \<webbplatsnamnet> ägargruppen\*\* och använder steg 11-14 för att ange den uppsättning användarkonton som kan administrera behörigheterna i undermappen (efter behov).</span><span class="sxs-lookup"><span data-stu-id="52dd7-169">Under **Groups** in the left navigation, click the **\<site name> Owners** group and use steps 11-14 to specify the set of user accounts that can administer the permissions in the subfolder (as needed).</span></span>
    
17. <span data-ttu-id="52dd7-170">Stäng fliken **Kontakter och grupper** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="52dd7-170">Close the **People and Groups** tab in your browser.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="52dd7-171">Se även</span><span class="sxs-lookup"><span data-stu-id="52dd7-171">See Also</span></span>

[<span data-ttu-id="52dd7-172">Isolerade SharePoint Online-gruppwebbplatser</span><span class="sxs-lookup"><span data-stu-id="52dd7-172">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="52dd7-173">Utforma en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="52dd7-173">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="52dd7-174">Distribuera en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="52dd7-174">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)



