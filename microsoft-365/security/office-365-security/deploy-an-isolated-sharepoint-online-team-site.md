---
title: Distribuera en isolerad SharePoint Online-gruppwebbplats
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: 'Sammanfattning: Distribuera en ny isolerad SharePoint Online-gruppwebbplats med dessa steg-för-steg-instruktioner.'
ms.openlocfilehash: 07867b4646926468f808f8f34086cf9267d7ab7b
ms.sourcegitcommit: 9afcc63b1a7e73f6946f67207337f10b71a5d7f3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/12/2020
ms.locfileid: "42811861"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="99797-103">Distribuera en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="99797-103">Deploy an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="99797-104">**Sammanfattning:** Distribuera en ny isolerad SharePoint Online-gruppwebbplats med dessa steg-för-steg-instruktioner.</span><span class="sxs-lookup"><span data-stu-id="99797-104">**Summary:** Deploy a new isolated SharePoint Online team site with these step-by-step instructions.</span></span>
  
<span data-ttu-id="99797-105">Den här artikeln är en steg-för-steg-distributionsguide för att skapa och konfigurera en isolerad SharePoint Online-gruppwebbplats i Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="99797-105">This article is a step-by-step deployment guide for creating and configuring an isolated SharePoint Online team site in Microsoft Office 365.</span></span> <span data-ttu-id="99797-106">De här stegen förutsätter att de tre standardgrupperna i SharePoint och motsvarande behörighetsnivåer används, med en enda AD-baserad åtkomstgrupp (Azure Active Directory) för varje åtkomstnivå.</span><span class="sxs-lookup"><span data-stu-id="99797-106">These steps assume the use of the three default SharePoint groups and corresponding permission levels, with a single Azure Active Directory (AD)-based access group for each level of access.</span></span>
  
## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a><span data-ttu-id="99797-107">Fas 1: Skapa och fylla i gruppwebbplatsåtkomstgrupperna</span><span class="sxs-lookup"><span data-stu-id="99797-107">Phase 1: Create and populate the team site access groups</span></span>

<span data-ttu-id="99797-108">I den här fasen skapar du de tre Azure AD-baserade åtkomstgrupperna för de tre standardSharePoint-grupperna och fyller i dem med lämpliga användarkonton.</span><span class="sxs-lookup"><span data-stu-id="99797-108">In this phase, you create the three Azure AD-based access groups for the three default SharePoint groups and populate them with the appropriate user accounts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="99797-109">Följande steg förutsätter att alla nödvändiga användarkonton redan finns och tilldelas lämpliga licenser.</span><span class="sxs-lookup"><span data-stu-id="99797-109">The following steps assume that all necessary user accounts already exist and are assigned the appropriate licenses.</span></span> <span data-ttu-id="99797-110">Om inte, lägg till dem och tilldela licenser innan du går vidare till steg 1.</span><span class="sxs-lookup"><span data-stu-id="99797-110">If not, please add them and assign licenses before proceeding to step 1.</span></span> 
  
### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a><span data-ttu-id="99797-111">Steg 1: Lista SharePoint Online-administratörerna för webbplatsen</span><span class="sxs-lookup"><span data-stu-id="99797-111">Step 1: List the SharePoint Online admins for the site</span></span>

<span data-ttu-id="99797-112">Bestäm vilken uppsättning användarkonton som motsvarar SharePoint Online-administratörerna för den isolerade gruppwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="99797-112">Determine the set of user accounts corresponding to the SharePoint Online admins for the isolated team site.</span></span>
  
<span data-ttu-id="99797-113">Om du hanterar användarkonton och grupper via Office 365 och vill använda Windows PowerShell gör du en lista över deras användarnamn (UPN) (t.ex. UPN: belindan@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="99797-113">If you are managing user accounts and groups through Office 365 and want to use Windows PowerShell, make a list of their user principal names (UPNs) (example UPN: belindan@contoso.com).</span></span>
  
### <a name="step-2-list-the-members-for-the-site"></a><span data-ttu-id="99797-114">Steg 2: Lista medlemmarna för webbplatsen</span><span class="sxs-lookup"><span data-stu-id="99797-114">Step 2: List the members for the site</span></span>

<span data-ttu-id="99797-115">Bestäm den uppsättning användarkonton som motsvarar medlemmarna för den isolerade gruppwebbplatsen, de som kommer att samarbeta om resurser som lagras på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="99797-115">Determine the set of user accounts corresponding to the members for the isolated team site, those who will be collaborating on resources stored within the site.</span></span>
  
<span data-ttu-id="99797-116">Om du hanterar användarkonton och grupper via Office 365 och vill använda PowerShell gör du en lista över deras UPN:er.</span><span class="sxs-lookup"><span data-stu-id="99797-116">If you are managing user accounts and groups through Office 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="99797-117">Om det finns många platsmedlemmar kan du lagra listan över UPN:er i en textfil och lägga till dem alla med ett enda PowerShell-kommando.</span><span class="sxs-lookup"><span data-stu-id="99797-117">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>
  
### <a name="step-3-list-the-viewers-for-the-site"></a><span data-ttu-id="99797-118">Steg 3: Lista tittarna för webbplatsen</span><span class="sxs-lookup"><span data-stu-id="99797-118">Step 3: List the viewers for the site</span></span>

<span data-ttu-id="99797-119">Bestäm den uppsättning användarkonton som motsvarar tittarna på den isolerade gruppwebbplatsen, de som kan visa de resurser som lagras på webbplatsen men inte ändra dem eller direkt samarbeta om innehållet.</span><span class="sxs-lookup"><span data-stu-id="99797-119">Determine the set of user accounts corresponding to the viewers of the isolated team site, those who can view the resources stored in the site but not modify them or directly collaborate on their contents.</span></span>
  
<span data-ttu-id="99797-120">Om du hanterar användarkonton och grupper via Office 365 och vill använda PowerShell gör du en lista över deras UPN:er.</span><span class="sxs-lookup"><span data-stu-id="99797-120">If you are managing user accounts and groups through Office 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="99797-121">Om det finns många platsmedlemmar kan du lagra listan över UPN:er i en textfil och lägga till dem alla med ett enda PowerShell-kommando.</span><span class="sxs-lookup"><span data-stu-id="99797-121">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>
  
<span data-ttu-id="99797-122">Tittare på webbplatsen kan inkludera chefsledning, juridisk rådgivning eller intressenter mellan avdelningarna.</span><span class="sxs-lookup"><span data-stu-id="99797-122">Viewers for the site might include executive management, legal counsel, or inter-departmental stakeholders.</span></span>
  
### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a><span data-ttu-id="99797-123">Steg 4: Skapa de tre åtkomstgrupperna för webbplatsen i Azure AD</span><span class="sxs-lookup"><span data-stu-id="99797-123">Step 4: Create the three access groups for the site in Azure AD</span></span>

<span data-ttu-id="99797-124">Du måste skapa följande åtkomstgrupper i Azure AD:</span><span class="sxs-lookup"><span data-stu-id="99797-124">You need to create the following access groups in Azure AD:</span></span>
  
- <span data-ttu-id="99797-125">Webbplatsadministratörer (som innehåller listan från steg 1)</span><span class="sxs-lookup"><span data-stu-id="99797-125">Site admins (which will contain the list from step 1)</span></span>
    
- <span data-ttu-id="99797-126">Webbplatsmedlemmar (som innehåller listan från steg 2)</span><span class="sxs-lookup"><span data-stu-id="99797-126">Site members (which will contain the list from step 2)</span></span>
    
- <span data-ttu-id="99797-127">Webbplatstittare (som innehåller listan från steg 3)</span><span class="sxs-lookup"><span data-stu-id="99797-127">Site viewers (which will contain the list from step 3)</span></span>
    
1. <span data-ttu-id="99797-128">I webbläsaren går du till [https://portal.azure.com](https://portal.azure.com) Azure-portalen och loggar in med autentiseringsuppgifterna för ett konto som har tilldelats rollen Användarhanteringsadministratör eller företagsadministratör.</span><span class="sxs-lookup"><span data-stu-id="99797-128">In your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com) and sign in with the credentials of an account that has been assigned with User Management Admin or Company Administrator role.</span></span>
    
2. <span data-ttu-id="99797-129">Klicka på Azure **Active Directory > grupper**i Azure-portalen .</span><span class="sxs-lookup"><span data-stu-id="99797-129">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>
    
3. <span data-ttu-id="99797-130">Klicka på **+ Ny grupp**på bladet Grupper - Alla **grupper** .</span><span class="sxs-lookup"><span data-stu-id="99797-130">On the **Groups - All groups** blade, click **+ New group**.</span></span>
    
4. <span data-ttu-id="99797-131">På den **nya gruppen** blad:</span><span class="sxs-lookup"><span data-stu-id="99797-131">On the **New Group** blade:</span></span>
    
    - <span data-ttu-id="99797-132">Välj **Säkerhet** **i grupptyp**.</span><span class="sxs-lookup"><span data-stu-id="99797-132">Select **Security** in **Group type**.</span></span>

    - <span data-ttu-id="99797-133">Skriv gruppnamnet i **Namn**.</span><span class="sxs-lookup"><span data-stu-id="99797-133">Type the group name in **Name**.</span></span>

    - <span data-ttu-id="99797-134">Skriv en beskrivning av gruppen i **Gruppbeskrivning**.</span><span class="sxs-lookup"><span data-stu-id="99797-134">Type a description of the group in **Group description**.</span></span>

    - <span data-ttu-id="99797-135">Välj **Tilldelas** i **medlemstyp**.</span><span class="sxs-lookup"><span data-stu-id="99797-135">Select **Assigned** in **Membership type**.</span></span>
    
5. <span data-ttu-id="99797-136">Klicka på **Skapa**och stäng sedan **gruppbladet.**</span><span class="sxs-lookup"><span data-stu-id="99797-136">Click **Create**, and then close the **Group** blade.</span></span>
    
6. <span data-ttu-id="99797-137">Upprepa steg 3-5 för dina ytterligare grupper.</span><span class="sxs-lookup"><span data-stu-id="99797-137">Repeat steps 3-5 for your additional groups.</span></span>
    
> [!NOTE]
> <span data-ttu-id="99797-138">Du måste använda Azure-portalen för att skapa grupperna så att de har Office-funktioner aktiverade.</span><span class="sxs-lookup"><span data-stu-id="99797-138">You need to use the Azure portal to create the groups so that they have Office features enabled.</span></span> <span data-ttu-id="99797-139">Om en SharePoint Online-isolerad webbplats senare konfigureras som en mycket konfidentiell webbplats med en Azure Information Protection-etikett för att kryptera filer och tilldela behörighet till specifika grupper, måste de tillåtna grupperna ha skapats med Office-funktioner aktiverade.</span><span class="sxs-lookup"><span data-stu-id="99797-139">If a SharePoint Online isolated site is later configured as a Highly Confidential site with an Azure Information Protection label to encrypt files and assign permission to specific groups, the permitted groups must have been created with Office features enabled.</span></span> <span data-ttu-id="99797-140">Du kan inte ändra office-inställningen för en Azure AD-grupp när den har skapats.</span><span class="sxs-lookup"><span data-stu-id="99797-140">You cannot change the Office features setting of an Azure AD group after it has been created.</span></span> 
  
<span data-ttu-id="99797-141">Här är din resulterande konfiguration med de tre platsåtkomstgrupperna.</span><span class="sxs-lookup"><span data-stu-id="99797-141">Here is your resulting configuration with the three site access groups.</span></span>
  
![De tre åtkomstgrupperna för distributionen av en isolerad SharePoint Online-webbplats.](../../media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)
  
### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a><span data-ttu-id="99797-143">Steg 5.</span><span class="sxs-lookup"><span data-stu-id="99797-143">Step 5.</span></span> <span data-ttu-id="99797-144">Lägga till användarkontona i åtkomstgrupperna</span><span class="sxs-lookup"><span data-stu-id="99797-144">Add the user accounts to the access groups</span></span>

<span data-ttu-id="99797-145">Gör i det här steget följande:</span><span class="sxs-lookup"><span data-stu-id="99797-145">In this step, do the following:</span></span>
  
1. <span data-ttu-id="99797-146">Lägga till listan över användare från steg 1 i åtkomstgruppen för webbplatsadministratörer</span><span class="sxs-lookup"><span data-stu-id="99797-146">Add the list of users from step 1 to the site admins access group</span></span>
    
2. <span data-ttu-id="99797-147">Lägga till listan över användare från steg 2 i åtkomstgruppen för webbplatsmedlemmar</span><span class="sxs-lookup"><span data-stu-id="99797-147">Add the list of users from step 2 to the site members access group</span></span>
    
3. <span data-ttu-id="99797-148">Lägga till listan över användare från steg 3 i åtkomstgruppen för webbplatstittare</span><span class="sxs-lookup"><span data-stu-id="99797-148">Add the list of users from step 3 to the site viewers access group</span></span>
    
<span data-ttu-id="99797-149">Om du hanterar användarkonton och grupper via AD DS (Active Directory Domain Services) lägger du till användare i lämpliga åtkomstgrupper med dina vanliga AD DS-användar- och grupphanteringsprocedurer och väntar på synkronisering med din Office 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="99797-149">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="99797-150">Om du hanterar användarkonton och grupper via Office 365 kan du använda administrationscentret för Microsoft 365 eller PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99797-150">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell.</span></span> <span data-ttu-id="99797-151">Om du har dubblettgruppnamn för någon av åtkomstgrupperna bör du använda administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="99797-151">If you have duplicate group names for any of the access groups, you should use the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="99797-152">Logga in med ett användarkonto som har tilldelats rollen Användarkontoadministratör eller företagsadministratör i Microsoft 365 och använd grupper för att lägga till lämpliga användarkonton och grupper i lämpliga åtkomstgrupper.</span><span class="sxs-lookup"><span data-stu-id="99797-152">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate user accounts and groups to the appropriate access groups.</span></span>
  
<span data-ttu-id="99797-153">För PowerShell ansluter du först [med Azure Active Directory PowerShell för Graph-modulen](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="99797-153">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="99797-154">Använd sedan följande kommandoblock för att lägga till ett enskilt användarkonto i en åtkomstgrupp:</span><span class="sxs-lookup"><span data-stu-id="99797-154">Next, use the following command block to add an individual user account to an access group:</span></span>
  
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```
<span data-ttu-id="99797-155">Om du har lagrat UPN:erna för användarkonton för någon av åtkomstgrupperna i en textfil kan du använda följande PowerShell-kommandoblock för att lägga till dem alla samtidigt:</span><span class="sxs-lookup"><span data-stu-id="99797-155">If you stored the UPNs of user accounts for any of the access groups in a text file, you can use the following PowerShell command block to add them all at one time:</span></span>
  
```powershell
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

<span data-ttu-id="99797-156">För PowerShell använder du följande kommandoblock för att lägga till en enskild grupp i en åtkomstgrupp:</span><span class="sxs-lookup"><span data-stu-id="99797-156">For PowerShell, use the following command block to add an individual group to an access group:</span></span>
  
```powershell
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID

```

<span data-ttu-id="99797-157">Resultaten bör vara följande:</span><span class="sxs-lookup"><span data-stu-id="99797-157">The results should be the following:</span></span>
  
- <span data-ttu-id="99797-158">Gruppen Azure AD för webbplatsadministratörer innehåller användarkonton eller grupper för webbplatsadministratör</span><span class="sxs-lookup"><span data-stu-id="99797-158">The site admins Azure AD group contains the site admin user accounts or groups</span></span>
    
- <span data-ttu-id="99797-159">Platsmedlemmarnas Azure AD-grupp innehåller användarkonton eller grupper för webbplatsmedlem</span><span class="sxs-lookup"><span data-stu-id="99797-159">The site members Azure AD group contains the site member user accounts or groups</span></span>
    
- <span data-ttu-id="99797-160">WebbplatstittarnaS Azure AD-grupp innehåller användarkonton eller grupper som bara kan visa webbplatsinnehållet</span><span class="sxs-lookup"><span data-stu-id="99797-160">The site viewers Azure AD group contains the user accounts or groups that can only view the site contents</span></span>
    
<span data-ttu-id="99797-161">Validera listan över gruppmedlemmar för varje åtkomstgrupp med administrationscentret för Microsoft 365 eller med följande PowerShell-kommandoblock:</span><span class="sxs-lookup"><span data-stu-id="99797-161">Validate the list of group members for each access group with the Microsoft 365 admin center or with the following PowerShell command block:</span></span>
  
```powershell
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

<span data-ttu-id="99797-162">Här är din resulterande konfiguration med de tre webbplatsåtkomstgrupperna ifyllda med användarkonton eller grupper.</span><span class="sxs-lookup"><span data-stu-id="99797-162">Here is your resulting configuration with the three site access groups populated with user accounts or groups.</span></span>
  
![De tre åtkomstgrupperna som fyllts i med användarkonton.](../../media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)
  
## <a name="phase-2-create-and-configure-the-isolated-team-site"></a><span data-ttu-id="99797-164">Fas 2: Skapa och konfigurera den isolerade gruppplatsen</span><span class="sxs-lookup"><span data-stu-id="99797-164">Phase 2: Create and configure the isolated team site</span></span>

<span data-ttu-id="99797-165">I den här fasen skapar du den isolerade SharePoint Online-webbplatsen och konfigurerar behörigheterna för standardbehörighetsnivåerna för SharePoint Online för att använda dina nya Azure AD-baserade åtkomstgrupper.</span><span class="sxs-lookup"><span data-stu-id="99797-165">In this phase, you create the isolated SharePoint Online site and configure the permissions for the default SharePoint Online permission levels to use your new Azure AD-based access groups.</span></span> <span data-ttu-id="99797-166">Som standard innehåller nya gruppwebbplatser en Office 365-grupp och andra relaterade resurser, men i det här fallet skapar vi en gruppwebbplats utan en Office 365-grupp.</span><span class="sxs-lookup"><span data-stu-id="99797-166">By default, new team sites include an Office 365 group and other related resources, but in this case, we'll create a team site without an Office 365 group.</span></span> <span data-ttu-id="99797-167">Detta gör det möjligt att upprätthålla behörigheter helt via SharePoint.</span><span class="sxs-lookup"><span data-stu-id="99797-167">This allows maintaining permissions entirely through SharePoint.</span></span>
  
<span data-ttu-id="99797-168">Skapa först SharePoint Online-gruppwebbplatsen med de här stegen.</span><span class="sxs-lookup"><span data-stu-id="99797-168">First, create the SharePoint Online team site with these steps.</span></span>
  
1. <span data-ttu-id="99797-169">Logga in på administrationscentret för Microsoft 365 med ett konto som också används för att administrera SharePoint Online-gruppwebbplatsen (en SharePoint Online-administratör).</span><span class="sxs-lookup"><span data-stu-id="99797-169">Sign in to the Microsoft 365 admin center with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator).</span></span> <span data-ttu-id="99797-170">Mer information finns i [Var du kan logga in på Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="99797-170">For help, see [Where to sign in to Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="99797-171">Klicka på **SharePoint**under **Administrationscenter i Administrationscenter**i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="99797-171">In the Microsoft 365 admin center, under **Admin centers**, click **SharePoint**.</span></span>

3. <span data-ttu-id="99797-172">Expandera **Webbplatser** i administrationscentret för SharePoint och klicka på **Aktiva webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="99797-172">In the SharePoint admin center, expand **Sites** and click **Active sites**.</span></span>

4. <span data-ttu-id="99797-173">Klicka på **Skapa**och välj sedan **Andra alternativ**.</span><span class="sxs-lookup"><span data-stu-id="99797-173">Click **Create**, and then choose **Other options**.</span></span>

5. <span data-ttu-id="99797-174">Välj **Gruppwebbplats**i listan **Välj en mall** .</span><span class="sxs-lookup"><span data-stu-id="99797-174">In the **Choose a template** list, choose **Team site**.</span></span>
   
6. <span data-ttu-id="99797-175">Skriv ett namn på gruppwebbplatsen i **Webbplatsnamn.**</span><span class="sxs-lookup"><span data-stu-id="99797-175">In **Site name**, type a name for the team site.</span></span> 
    
7. <span data-ttu-id="99797-176">I **Primär administratör**skriver du kontot som du är inloggad med.</span><span class="sxs-lookup"><span data-stu-id="99797-176">In **Primary administrator**, type the account that you are logged in with.</span></span>
 
8. <span data-ttu-id="99797-177">Klicka på **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="99797-177">Click **Finish**.</span></span>
    
<span data-ttu-id="99797-178">Konfigurera behörigheter sedan från den nya SharePoint Online-gruppwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="99797-178">Next, from the new SharePoint Online team site, configure permissions.</span></span>
  
1. <span data-ttu-id="99797-179">Klicka på inställningsikonen i verktygsfältet och klicka sedan på **Webbplatsbehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="99797-179">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

2. <span data-ttu-id="99797-180">Klicka på **Ändra hur medlemmar kan dela**under **Webbplatsdelning**.</span><span class="sxs-lookup"><span data-stu-id="99797-180">Under **Site sharing**, click **Change how members can share**.</span></span>

3. <span data-ttu-id="99797-181">Välj de **enda webbplatsägarna som kan dela filer, mappar och webbplatsen**.</span><span class="sxs-lookup"><span data-stu-id="99797-181">Choose the **Only site owners can share files, folders, and the site**.</span></span>

4. <span data-ttu-id="99797-182">Ange **tillåt åtkomstbegäranden** till **Av**.</span><span class="sxs-lookup"><span data-stu-id="99797-182">Set **Allow access requests** to **Off**.</span></span>

5. <span data-ttu-id="99797-183">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="99797-183">Click **Save**.</span></span>
    
6. <span data-ttu-id="99797-184">Klicka på Inställningar **för Avancerade behörigheter**i fönstret **Behörigheter** .</span><span class="sxs-lookup"><span data-stu-id="99797-184">In the **Permissions** pane, click **Advanced permissions settings**.</span></span>
    
7. <span data-ttu-id="99797-185">Klicka på \*\* \<webbplatsnamn> medlemmar\*\* i listan på fliken **Behörigheter** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="99797-185">On the **Permissions** tab of your browser, click **\<site name> Members** in the list.</span></span>
    
8. <span data-ttu-id="99797-186">I **Kontakter och Grupper**klickar du på **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="99797-186">In **People and Groups**, click **New**.</span></span>
    
9. <span data-ttu-id="99797-187">Skriv namnet på åtkomstgruppen för webbplatsmedlemmar i dialogrutan **Dela,** markera det och klicka sedan på **Dela**.</span><span class="sxs-lookup"><span data-stu-id="99797-187">In the **Share** dialog box, type the name of the site members access group, select it, and then click **Share**.</span></span>
    
10. <span data-ttu-id="99797-188">Klicka på bakåtknappen i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="99797-188">Click the back button on your browser.</span></span>
    
11. <span data-ttu-id="99797-189">Klicka på \*\* \<webbplatsnamn> ägare\*\* i listan.</span><span class="sxs-lookup"><span data-stu-id="99797-189">Click **\<site name> Owners** in the list.</span></span>
    
12. <span data-ttu-id="99797-190">I **Kontakter och Grupper**klickar du på **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="99797-190">In **People and Groups**, click **New**.</span></span>
    
13. <span data-ttu-id="99797-191">Skriv namnet på åtkomstgruppen för webbplatsadministratörer i dialogrutan **Dela,** markera det och klicka sedan på **Dela**.</span><span class="sxs-lookup"><span data-stu-id="99797-191">In the **Share** dialog box, type the name of the site admins access group, select it, and then click **Share**.</span></span>
    
14. <span data-ttu-id="99797-192">Klicka på bakåtknappen i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="99797-192">Click the back button on your browser.</span></span>
    
15. <span data-ttu-id="99797-193">Klicka på \*\* \<webbplatsnamn> besökare\*\* i listan.</span><span class="sxs-lookup"><span data-stu-id="99797-193">Click **\<site name> Visitors** in the list.</span></span>
    
16. <span data-ttu-id="99797-194">I **Kontakter och Grupper**klickar du på **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="99797-194">In **People and Groups**, click **New**.</span></span>
    
17. <span data-ttu-id="99797-195">Skriv namnet på åtkomstgruppen för webbplatsvisningsprogram i dialogrutan **Dela,** markera det och klicka sedan på **Dela**.</span><span class="sxs-lookup"><span data-stu-id="99797-195">In the **Share** dialog box, type the name of the site viewers access group, select it, and then click **Share**.</span></span>
    
18. <span data-ttu-id="99797-196">Stäng fliken **Behörigheter** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="99797-196">Close the **Permissions** tab of your browser.</span></span>
    
<span data-ttu-id="99797-197">Resultaten av dessa behörighetsinställningarna är:</span><span class="sxs-lookup"><span data-stu-id="99797-197">The results of these permission settings are:</span></span>
  
- <span data-ttu-id="99797-198">\*\* \<Webbplatsnamnet>\*\* SharePoint-gruppen för ägare innehåller åtkomstgruppen för webbplatsadministratörer, där alla medlemmar har **behörighetsnivån fullständig kontroll.**</span><span class="sxs-lookup"><span data-stu-id="99797-198">The **\<site name> Owners** SharePoint group contains the site admins access group, in which all the members have the **Full control** permission level.</span></span>
    
- <span data-ttu-id="99797-199">\*\* \<Webbplatsnamnet>\*\* SharePoint-gruppen för medlemmar innehåller åtkomstgruppen för webbplatsmedlemmar, där alla medlemmar har **behörighetsnivån Redigera.**</span><span class="sxs-lookup"><span data-stu-id="99797-199">The **\<site name> Members** SharePoint group contains the site members access group, in which all the members have the **Edit** permission level.</span></span>
    
- <span data-ttu-id="99797-200">\*\* \<Webbplatsnamnet>\*\* SharePoint-gruppen för besökare innehåller åtkomstgruppen för webbplatsvisningsprogram, där alla medlemmar har **behörighetsnivån Läs.**</span><span class="sxs-lookup"><span data-stu-id="99797-200">The **\<site name> Visitors** SharePoint group contains the site viewers access group, in which all the members have the **Read** permission level.</span></span>
    
- <span data-ttu-id="99797-201">Möjligheten för medlemmar att bjuda in andra medlemmar eller för icke-medlemmar att begära åtkomst är inaktiverad.</span><span class="sxs-lookup"><span data-stu-id="99797-201">The ability for members to invite other members or for non-members to request access is disabled.</span></span>
    
<span data-ttu-id="99797-202">Här är din resulterande konfiguration med de tre SharePoint-grupperna för webbplatsen som konfigurerats för att använda de tre åtkomstgrupperna, som fylls i med användarkonton eller Azure AD-grupper.</span><span class="sxs-lookup"><span data-stu-id="99797-202">Here is your resulting configuration with the three SharePoint groups for the site configured to use the three access groups, which are populated with user accounts or Azure AD groups.</span></span>
  
![Den slutliga konfigurationen av din isolerade SharePoint Online-webbplats med åtkomstgrupper och användarkonton.](../../media/e7618971-06ab-447b-90ff-d8be3790fe63.png)
  
<span data-ttu-id="99797-204">Du och medlemmarna på webbplatsen, genom gruppmedlemskap i en av åtkomstgrupperna, kan nu samarbeta med hjälp av webbplatsens resurser.</span><span class="sxs-lookup"><span data-stu-id="99797-204">You and the members of the site, through group membership in one of the access groups, can now collaborate using the resources of the site.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="99797-205">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="99797-205">Next step</span></span>

<span data-ttu-id="99797-206">När du behöver ändra medlemskap i webbplatsåtkomstgrupp eller skapa en dokumentmapp med anpassade behörigheter läser du [Hantera en isolerad SharePoint Online-gruppwebbplats](manage-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="99797-206">When you need to change site access group membership or create a document folder with custom permissions, see [Manage an isolated SharePoint Online team site](manage-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="99797-207">Se även</span><span class="sxs-lookup"><span data-stu-id="99797-207">See Also</span></span>

[<span data-ttu-id="99797-208">Isolerade SharePoint Online-gruppwebbplatser</span><span class="sxs-lookup"><span data-stu-id="99797-208">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="99797-209">Utforma en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="99797-209">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)
  
[<span data-ttu-id="99797-210">Hantera en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="99797-210">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)
  



