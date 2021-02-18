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
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: Hantera en isolerad SharePoint Online-gruppwebbplats, lägg till nya användare och grupper, ta bort användare och grupper och skapa en dokumentundermapp med anpassade behörigheter.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 20e354de77b70ea69d69e201bd3b1d40ea32cc5b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289527"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="ddc08-103">Hantera en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="ddc08-103">Manage an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ddc08-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="ddc08-104">**Applies to**</span></span>
- [<span data-ttu-id="ddc08-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ddc08-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ddc08-106">Microsoft Defender för Office 365 abonnemang 1</span><span class="sxs-lookup"><span data-stu-id="ddc08-106">Microsoft Defender for Office 365 plan 1</span></span>](office-365-atp.md)
- <span data-ttu-id="ddc08-107">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ddc08-107">SharePoint Online</span></span> 

 <span data-ttu-id="ddc08-108">**Sammanfattning:** Hantera din isolerade SharePoint Online-gruppwebbplats med de här procedurerna.</span><span class="sxs-lookup"><span data-stu-id="ddc08-108">**Summary:** Manage your isolated SharePoint Online team site with these procedures.</span></span>

<span data-ttu-id="ddc08-109">I den här artikeln beskrivs vanliga hanteringsåtgärder för en isolerad SharePoint Online-gruppwebbplats.</span><span class="sxs-lookup"><span data-stu-id="ddc08-109">This article describes common management operations for an isolated SharePoint Online team site.</span></span>

## <a name="add-a-new-user"></a><span data-ttu-id="ddc08-110">Lägga till en ny användare</span><span class="sxs-lookup"><span data-stu-id="ddc08-110">Add a new user</span></span>

<span data-ttu-id="ddc08-111">När någon ny ansluter till webbplatsen måste du bestämma i vilken grad de vill delta på webbplatsen:</span><span class="sxs-lookup"><span data-stu-id="ddc08-111">When someone new joins the site, you must decide their level of participation in the site:</span></span>

- <span data-ttu-id="ddc08-112">Administration: Lägg till det nya användarkontot i åtkomstgruppen för webbplatsadministratörer</span><span class="sxs-lookup"><span data-stu-id="ddc08-112">Administration: Add the new user account to the site admins access group</span></span>

- <span data-ttu-id="ddc08-113">Aktivt samarbete: Lägg till användarkontot i åtkomstgruppen för webbplatsmedlemmar</span><span class="sxs-lookup"><span data-stu-id="ddc08-113">Active collaboration: Add the user account to the site members access group</span></span>

- <span data-ttu-id="ddc08-114">Visa: Lägga till användarkontot i åtkomstgruppen för webbplatsvisningsprogram</span><span class="sxs-lookup"><span data-stu-id="ddc08-114">Viewing: Add the user account to the site viewers access group</span></span>

<span data-ttu-id="ddc08-115">Om du hanterar användarkonton och grupper via Active Directory DS (AD DS) lägger du till rätt användare i lämpliga åtkomstgrupper med dina vanliga procedurer för hantering av AD DS och grupper och väntar på synkronisering med din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="ddc08-115">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add the appropriate users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="ddc08-116">Om du hanterar användarkonton och grupper via Microsoft 365 kan du använda administrationscentret för Microsoft 365 eller Microsoft PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ddc08-116">If you are managing user accounts and groups through Microsoft 365, you can use the Microsoft 365 admin center or Microsoft PowerShell:</span></span>

- <span data-ttu-id="ddc08-117">I administrationscentret för Microsoft 365 loggar du in med ett användarkonto som har tilldelats rollen Som administratör för användarkonto eller Företagsadministratör, och använder Grupper för att lägga till rätt användare i lämpliga åtkomstgrupper.</span><span class="sxs-lookup"><span data-stu-id="ddc08-117">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate users to the appropriate access groups.</span></span>

- <span data-ttu-id="ddc08-118">För PowerShell ska du [först ansluta till Azure Active Directory PowerShell för Graph-modulen.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="ddc08-118">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span> <span data-ttu-id="ddc08-119">Om du vill lägga till ett användarkonto i en åtkomstgrupp med dess huvudnamn (UPN) använder du följande PowerShell-kommandoblock:</span><span class="sxs-lookup"><span data-stu-id="ddc08-119">To add a user account to an access group with its user principal name (UPN), use the following PowerShell command block:</span></span>

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="ddc08-120">Om du vill lägga till ett användarkonto i en åtkomstgrupp med dess visningsnamn använder du följande PowerShell-kommandoblock:</span><span class="sxs-lookup"><span data-stu-id="ddc08-120">To add a user account to an access group with its display name, use the following PowerShell command block:</span></span>

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a><span data-ttu-id="ddc08-121">Lägga till en ny grupp</span><span class="sxs-lookup"><span data-stu-id="ddc08-121">Add a new group</span></span>

<span data-ttu-id="ddc08-122">Om du vill lägga till åtkomst till en hel grupp måste du bestämma i vilken grad alla medlemmar i gruppen ska delta på webbplatsen:</span><span class="sxs-lookup"><span data-stu-id="ddc08-122">To add access to an entire group, you must decide the level of participation of all the members of the group in the site:</span></span>

- <span data-ttu-id="ddc08-123">Administration: Lägg till gruppen i åtkomstgruppen för webbplatsadministratörer</span><span class="sxs-lookup"><span data-stu-id="ddc08-123">Administration: Add the group to the site admins access group</span></span>

- <span data-ttu-id="ddc08-124">Aktivt samarbete: Lägg till gruppen i åtkomstgruppen för webbplatsmedlemmar</span><span class="sxs-lookup"><span data-stu-id="ddc08-124">Active collaboration: Add the group to the site members access group</span></span>

- <span data-ttu-id="ddc08-125">Visa: Lägga till gruppen i åtkomstgruppen för webbplatsvisningsprogram</span><span class="sxs-lookup"><span data-stu-id="ddc08-125">Viewing: Add the group to the site viewers access group</span></span>

<span data-ttu-id="ddc08-126">Om du hanterar användarkonton och grupper via AD DS kan du lägga till lämpliga grupper i lämpliga grupper med dina vanliga användar- och grupphanteringsprocedurer AD DS och vänta på synkronisering med din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="ddc08-126">If you are managing user accounts and groups through AD DS, add the appropriate groups to the appropriate groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="ddc08-127">Om du hanterar användarkonton och grupper via Office 365 kan du använda administrationscentret för Microsoft 365 eller PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ddc08-127">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="ddc08-128">I administrationscentret för Microsoft 365 loggar du in med ett användarkonto som har tilldelats rollen Som administratör för användarkonto eller Företagsadministratör, och använder Grupper för att lägga till lämpliga grupper i lämpliga åtkomstgrupper.</span><span class="sxs-lookup"><span data-stu-id="ddc08-128">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate groups to the appropriate access groups.</span></span>

- <span data-ttu-id="ddc08-129">För PowerShell ska du [först ansluta till Azure Active Directory PowerShell för Graph-modulen.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="ddc08-129">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 <span data-ttu-id="ddc08-130">Använd sedan följande PowerShell-kommandon:</span><span class="sxs-lookup"><span data-stu-id="ddc08-130">Then, use the following PowerShell commands:</span></span>

```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a><span data-ttu-id="ddc08-131">Ta bort en användare</span><span class="sxs-lookup"><span data-stu-id="ddc08-131">Remove a user</span></span>

<span data-ttu-id="ddc08-132">När någons åtkomst måste tas bort från webbplatsen tar du bort dem från åtkomstgruppen för vilken de för närvarande är medlemmar baserat på deras deltagande på webbplatsen:</span><span class="sxs-lookup"><span data-stu-id="ddc08-132">When someone's access must be removed from the site, you remove them from the access group for which they are currently a member based on their participation in the site:</span></span>

- <span data-ttu-id="ddc08-133">Administration: Ta bort användarkontot från åtkomstgruppen för webbplatsadministratörer</span><span class="sxs-lookup"><span data-stu-id="ddc08-133">Administration: Remove the user account from the site admins access group</span></span>

- <span data-ttu-id="ddc08-134">Aktivt samarbete: Ta bort användarkontot från åtkomstgruppen för webbplatsmedlemmar</span><span class="sxs-lookup"><span data-stu-id="ddc08-134">Active collaboration: Remove the user account from the site members access group</span></span>

- <span data-ttu-id="ddc08-135">Visa: Ta bort användarkontot från åtkomstgruppen för webbplatsvisningsprogram</span><span class="sxs-lookup"><span data-stu-id="ddc08-135">Viewing: Remove the user account from the site viewers access group</span></span>

<span data-ttu-id="ddc08-136">Om du hanterar användarkonton och grupper via AD DS kan du ta bort lämpliga användare från lämpliga åtkomstgrupper med dina vanliga procedurer AD DS för användar- och grupphantering och vänta på synkronisering med din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="ddc08-136">If you are managing user accounts and groups through AD DS, remove the appropriate users from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="ddc08-137">Om du hanterar användarkonton och grupper via Office 365 kan du använda administrationscentret för Microsoft 365 eller PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ddc08-137">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="ddc08-138">I administrationscentret för Microsoft 365 loggar du in med ett användarkonto som har tilldelats rollen Som administratör för användarkonto eller Företagsadministratör, och använder Grupper för att ta bort rätt användare från lämpliga åtkomstgrupper.</span><span class="sxs-lookup"><span data-stu-id="ddc08-138">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate users from the appropriate access groups.</span></span>

- <span data-ttu-id="ddc08-139">För PowerShell ska du [först ansluta till Azure Active Directory PowerShell för Graph-modulen.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="ddc08-139">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="ddc08-140">Om du vill ta bort ett användarkonto från en åtkomstgrupp med dess UPN använder du följande PowerShell-kommandoblock:</span><span class="sxs-lookup"><span data-stu-id="ddc08-140">To remove a user account from an access group with its UPN, use the following PowerShell command block:</span></span>

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="ddc08-141">Om du vill ta bort ett användarkonto från en åtkomstgrupp med dess visningsnamn använder du följande PowerShell-kommandoblock:</span><span class="sxs-lookup"><span data-stu-id="ddc08-141">To remove a user account from an access group with its display name, use the following PowerShell command block:</span></span>

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a><span data-ttu-id="ddc08-142">Ta bort en grupp</span><span class="sxs-lookup"><span data-stu-id="ddc08-142">Remove a group</span></span>

<span data-ttu-id="ddc08-143">Om du vill ta bort åtkomst för en hel grupp tar du bort gruppen från den åtkomstgrupp där de för närvarande är medlemmar baserat på deras deltagande på webbplatsen:</span><span class="sxs-lookup"><span data-stu-id="ddc08-143">To remove access for an entire group, you remove the group from the access group for which they are currently a member based on their participation in the site:</span></span>

- <span data-ttu-id="ddc08-144">Administration: Ta bort gruppen från åtkomstgruppen för webbplatsadministratörer</span><span class="sxs-lookup"><span data-stu-id="ddc08-144">Administration: Remove the group from the site admins access group</span></span>

- <span data-ttu-id="ddc08-145">Aktivt samarbete: Ta bort gruppen från åtkomstgruppen för webbplatsmedlemmar</span><span class="sxs-lookup"><span data-stu-id="ddc08-145">Active collaboration: Remove the group from the site members access group</span></span>

- <span data-ttu-id="ddc08-146">Visa: Ta bort gruppen från åtkomstgruppen för webbplatsvisningsprogram</span><span class="sxs-lookup"><span data-stu-id="ddc08-146">Viewing: Remove the group from the site viewers access group</span></span>

<span data-ttu-id="ddc08-147">Om du hanterar användarkonton och grupper via Windows Server Active Directory kan du ta bort lämpliga grupper från lämpliga åtkomstgrupper med dina vanliga procedurer för användar- och grupphantering i AD DS och vänta på synkronisering med din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="ddc08-147">If you are managing user accounts and groups through Windows Server Active Directory, remove the appropriate groups from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="ddc08-148">Om du hanterar användarkonton och grupper via Office 365 kan du använda administrationscentret för Microsoft 365 eller PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ddc08-148">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="ddc08-149">I administrationscentret för Microsoft 365 loggar du in med ett användarkonto som har tilldelats rollen Som administratör för användarkonto eller Företagsadministratör, och använder Grupper för att ta bort lämpliga grupper från lämpliga åtkomstgrupper.</span><span class="sxs-lookup"><span data-stu-id="ddc08-149">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate groups from the appropriate access groups.</span></span>

- <span data-ttu-id="ddc08-150">För PowerShell ska du [först ansluta till Azure Active Directory PowerShell för Graph-modulen.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="ddc08-150">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="ddc08-151">Om du vill ta bort en grupp från en åtkomstgrupp med hjälp av deras visningsnamn använder du följande PowerShell-kommandoblock:</span><span class="sxs-lookup"><span data-stu-id="ddc08-151">To remove a group from an access group using their display names, use the following PowerShell command block:</span></span>

```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a><span data-ttu-id="ddc08-152">Skapa en dokumentundermapp med anpassade behörigheter</span><span class="sxs-lookup"><span data-stu-id="ddc08-152">Create a documents subfolder with custom permissions</span></span>

<span data-ttu-id="ddc08-153">I vissa fall behöver en del av de personer som arbetar på den isolerade webbplatsen en mer privat plats för samarbete.</span><span class="sxs-lookup"><span data-stu-id="ddc08-153">In some cases, a subset of the people working within the isolated site need a more private place to collaborate.</span></span> <span data-ttu-id="ddc08-154">För SharePoint Online-webbplatser kan du skapa en undermapp i mappen Dokument på webbplatsen och tilldela anpassade behörigheter.</span><span class="sxs-lookup"><span data-stu-id="ddc08-154">For SharePoint Online sites, you can create a subfolder in the Documents folder of the site and assign custom permissions.</span></span> <span data-ttu-id="ddc08-155">De som inte har behörighet kan inte se undermappen.</span><span class="sxs-lookup"><span data-stu-id="ddc08-155">Those without permissions will not see the subfolder.</span></span>

<span data-ttu-id="ddc08-156">Så här skapar du en dokumentundermapp med anpassad behörighet:</span><span class="sxs-lookup"><span data-stu-id="ddc08-156">To create a documents subfolder with custom permissions, do the following:</span></span>

1. <span data-ttu-id="ddc08-157">Logga in på ett konto som är medlem i administratörsåtkomstgruppen för webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="ddc08-157">Sign in to an account that is a member of the admins access group for the site.</span></span> <span data-ttu-id="ddc08-158">Mer information finns i [Så här loggar du in i Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="ddc08-158">For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="ddc08-159">Gå till den isolerade gruppwebbplatsen och klicka på **Dokument.**</span><span class="sxs-lookup"><span data-stu-id="ddc08-159">Go to the isolated team site and click **Documents**.</span></span>

3. <span data-ttu-id="ddc08-160">Bläddra till mappen i dokumentmappen som innehåller undermappen med anpassade behörigheter, skapa mappen och öppna den sedan.</span><span class="sxs-lookup"><span data-stu-id="ddc08-160">Browse to the folder in the documents folder that will contain the subfolder with custom permissions, create the folder, and then open it.</span></span>

4. <span data-ttu-id="ddc08-161">Klicka **på Dela.**</span><span class="sxs-lookup"><span data-stu-id="ddc08-161">Click **Share**.</span></span>

5. <span data-ttu-id="ddc08-162">Klicka **på Delas > Avancerat.**</span><span class="sxs-lookup"><span data-stu-id="ddc08-162">Click **Shared with > Advanced**.</span></span>

6. <span data-ttu-id="ddc08-163">Klicka **på Sluta ärva behörigheter** och klicka sedan på **OK.**</span><span class="sxs-lookup"><span data-stu-id="ddc08-163">Click **Stop inheriting permissions**, and then click **OK**.</span></span>

7. <span data-ttu-id="ddc08-164">Klicka **på Dela.**</span><span class="sxs-lookup"><span data-stu-id="ddc08-164">Click **Share**.</span></span>

8. <span data-ttu-id="ddc08-165">Klicka **på Delas > Avancerat.**</span><span class="sxs-lookup"><span data-stu-id="ddc08-165">Click **Shared with > Advanced**.</span></span>

9. <span data-ttu-id="ddc08-166">Klicka **på Bevilja behörigheter > Delas med > Avancerat.**</span><span class="sxs-lookup"><span data-stu-id="ddc08-166">Click **Grant Permissions > Shared with > Advanced**.</span></span>

10. <span data-ttu-id="ddc08-167">Klicka på Medlemmar i **\<site name> listan på behörighetssidan.**</span><span class="sxs-lookup"><span data-stu-id="ddc08-167">On the permissions page, click **\<site name> Members in the list**.</span></span>

11. <span data-ttu-id="ddc08-168">På sidan **\<site name> Medlemmar** markerar du kryssrutan bredvid åtkomstgruppen Webbplatsmedlemmar, klickar på **Åtgärder,** klickar på Ta bort användare från grupp och klickar sedan på **OK.**</span><span class="sxs-lookup"><span data-stu-id="ddc08-168">On the **\<site name> Members** page, select the checkmark next to the site members access group, click **Actions**, click **Remove users from group**, and then click **OK**.</span></span>

12. <span data-ttu-id="ddc08-169">Om du vill lägga till specifika medlemmar i den här undermappen **klickar du på > Lägg till användare.**</span><span class="sxs-lookup"><span data-stu-id="ddc08-169">To add specific members to this subfolder, click **New > Add users**.</span></span>

13. <span data-ttu-id="ddc08-170">I dialogrutan **Dela** skriver du namnen på användarkontona som kan samarbeta med filer i undermappen och klickar sedan på **Dela.**</span><span class="sxs-lookup"><span data-stu-id="ddc08-170">In the **Share** dialog box, type the names of the user accounts that can collaborate on files in the subfolder, and then click **Share**.</span></span>

14. <span data-ttu-id="ddc08-171">Uppdatera webbsidan för att se de nya resultaten.</span><span class="sxs-lookup"><span data-stu-id="ddc08-171">Refresh the web page to see the new results.</span></span>

15. <span data-ttu-id="ddc08-172">Under **Grupper** i det vänstra **\<site name>** navigeringsfältet klickar du på gruppen Besökare och använder steg 11–14 för att ange vilken uppsättning användarkonton som kan visa filerna i undermappen (vid behov).</span><span class="sxs-lookup"><span data-stu-id="ddc08-172">Under **Groups** in the left navigation, click the **\<site name> Visitors** group and use steps 11-14 to specify the set of user accounts that can view the files in the subfolder (as needed).</span></span>

16. <span data-ttu-id="ddc08-173">Under **Grupper i** det vänstra **\<site name>** navigeringsfältet klickar du på gruppen Ägare och använder steg 11–14 för att ange den uppsättning användarkonton som kan administrera behörigheterna i undermappen (vid behov).</span><span class="sxs-lookup"><span data-stu-id="ddc08-173">Under **Groups** in the left navigation, click the **\<site name> Owners** group and use steps 11-14 to specify the set of user accounts that can administer the permissions in the subfolder (as needed).</span></span>

17. <span data-ttu-id="ddc08-174">Stäng fliken **Personer och** grupper i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="ddc08-174">Close the **People and Groups** tab in your browser.</span></span>

## <a name="see-also"></a><span data-ttu-id="ddc08-175">Se även</span><span class="sxs-lookup"><span data-stu-id="ddc08-175">See Also</span></span>

[<span data-ttu-id="ddc08-176">Isolerade SharePoint Online-gruppwebbplatser</span><span class="sxs-lookup"><span data-stu-id="ddc08-176">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="ddc08-177">Utforma en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="ddc08-177">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="ddc08-178">Distribuera en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="ddc08-178">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)
