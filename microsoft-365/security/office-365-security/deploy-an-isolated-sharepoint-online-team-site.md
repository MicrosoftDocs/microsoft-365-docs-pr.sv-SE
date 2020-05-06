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
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: Använd den här steg-för-steg-distributionsguiden för att skapa och konfigurera en isolerad SharePoint Online-gruppwebbplats i Microsoft Office 365.
ms.openlocfilehash: 772a9e5ea08871857a70cc840e377046d459a314
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036457"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="def34-103">Distribuera en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="def34-103">Deploy an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="def34-104">**Sammanfattning:** Distribuera en ny isolerad SharePoint Online-gruppwebbplats med de här steg-för-steg-instruktionerna.</span><span class="sxs-lookup"><span data-stu-id="def34-104">**Summary:** Deploy a new isolated SharePoint Online team site with these step-by-step instructions.</span></span>
  
<span data-ttu-id="def34-105">Den här artikeln är en steg-för-steg-distributionsguide för att skapa och konfigurera en isolerad SharePoint Online-gruppwebbplats i Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="def34-105">This article is a step-by-step deployment guide for creating and configuring an isolated SharePoint Online team site in Microsoft Office 365.</span></span> <span data-ttu-id="def34-106">Dessa steg förutsätter att de tre standard-SharePoint-grupperna och motsvarande behörighetsnivåer används, med en enda AZURE Active Directory-baserad åtkomstgrupp för varje åtkomstnivå.</span><span class="sxs-lookup"><span data-stu-id="def34-106">These steps assume the use of the three default SharePoint groups and corresponding permission levels, with a single Azure Active Directory (AD)-based access group for each level of access.</span></span>
  
## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a><span data-ttu-id="def34-107">Fas 1: Skapa och fylla i åtkomstgrupper för gruppwebbplatser</span><span class="sxs-lookup"><span data-stu-id="def34-107">Phase 1: Create and populate the team site access groups</span></span>

<span data-ttu-id="def34-108">I den här fasen skapar du de tre Azure AD-baserade åtkomstgrupperna för de tre standarddoahPoint-grupperna och fyller dem med lämpliga användarkonton.</span><span class="sxs-lookup"><span data-stu-id="def34-108">In this phase, you create the three Azure AD-based access groups for the three default SharePoint groups and populate them with the appropriate user accounts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="def34-109">Följande steg förutsätter att alla nödvändiga användarkonton redan finns och tilldelas lämpliga licenser.</span><span class="sxs-lookup"><span data-stu-id="def34-109">The following steps assume that all necessary user accounts already exist and are assigned the appropriate licenses.</span></span> <span data-ttu-id="def34-110">Om inte, lägg till dem och tilldela licenser innan du fortsätter till steg 1.</span><span class="sxs-lookup"><span data-stu-id="def34-110">If not, please add them and assign licenses before proceeding to step 1.</span></span> 
  
### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a><span data-ttu-id="def34-111">Steg 1: Lista SharePoint Online-administratörer för webbplatsen</span><span class="sxs-lookup"><span data-stu-id="def34-111">Step 1: List the SharePoint Online admins for the site</span></span>

<span data-ttu-id="def34-112">Bestäm den uppsättning användarkonton som motsvarar SharePoint Online-administratörerna för den isolerade gruppwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="def34-112">Determine the set of user accounts corresponding to the SharePoint Online admins for the isolated team site.</span></span>
  
<span data-ttu-id="def34-113">Om du hanterar användarkonton och grupper via Microsoft 365 och vill använda Windows PowerShell gör du en lista över deras användarnamn (UPN) (t.belindan@contoso.com ex.</span><span class="sxs-lookup"><span data-stu-id="def34-113">If you are managing user accounts and groups through Microsoft 365 and want to use Windows PowerShell, make a list of their user principal names (UPNs) (example UPN: belindan@contoso.com).</span></span>
  
### <a name="step-2-list-the-members-for-the-site"></a><span data-ttu-id="def34-114">Steg 2: Lista medlemmarna för webbplatsen</span><span class="sxs-lookup"><span data-stu-id="def34-114">Step 2: List the members for the site</span></span>

<span data-ttu-id="def34-115">Bestäm den uppsättning användarkonton som motsvarar medlemmarna för den isolerade gruppwebbplatsen, de som ska samarbeta på resurser som lagras på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="def34-115">Determine the set of user accounts corresponding to the members for the isolated team site, those who will be collaborating on resources stored within the site.</span></span>
  
<span data-ttu-id="def34-116">Om du hanterar användarkonton och grupper via Microsoft 365 och vill använda PowerShell gör du en lista över deras UPN-nätverk.</span><span class="sxs-lookup"><span data-stu-id="def34-116">If you are managing user accounts and groups through Microsoft 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="def34-117">Om det finns många webbplatsmedlemmar kan du lagra listan över UPN i en textfil och lägga till dem alla med ett enda PowerShell-kommando.</span><span class="sxs-lookup"><span data-stu-id="def34-117">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>
  
### <a name="step-3-list-the-viewers-for-the-site"></a><span data-ttu-id="def34-118">Steg 3: Lista tittarna för webbplatsen</span><span class="sxs-lookup"><span data-stu-id="def34-118">Step 3: List the viewers for the site</span></span>

<span data-ttu-id="def34-119">Bestäm den uppsättning användarkonton som motsvarar visningssidan på den isolerade gruppwebbplatsen, de som kan visa de resurser som lagras på webbplatsen men inte ändra dem eller direkt samarbeta om innehållet.</span><span class="sxs-lookup"><span data-stu-id="def34-119">Determine the set of user accounts corresponding to the viewers of the isolated team site, those who can view the resources stored in the site but not modify them or directly collaborate on their contents.</span></span>
  
<span data-ttu-id="def34-120">Om du hanterar användarkonton och grupper via Microsoft 365 och vill använda PowerShell gör du en lista över deras UPN-nätverk.</span><span class="sxs-lookup"><span data-stu-id="def34-120">If you are managing user accounts and groups through Microsoft 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="def34-121">Om det finns många webbplatsmedlemmar kan du lagra listan över UPN i en textfil och lägga till dem alla med ett enda PowerShell-kommando.</span><span class="sxs-lookup"><span data-stu-id="def34-121">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>
  
<span data-ttu-id="def34-122">Tittare för webbplatsen kan inkludera chefshantering, juridisk rådgivning eller intressenter mellan avdelningar.</span><span class="sxs-lookup"><span data-stu-id="def34-122">Viewers for the site might include executive management, legal counsel, or inter-departmental stakeholders.</span></span>
  
### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a><span data-ttu-id="def34-123">Steg 4: Skapa de tre åtkomstgrupperna för webbplatsen i Azure AD</span><span class="sxs-lookup"><span data-stu-id="def34-123">Step 4: Create the three access groups for the site in Azure AD</span></span>

<span data-ttu-id="def34-124">Du måste skapa följande åtkomstgrupper i Azure AD:</span><span class="sxs-lookup"><span data-stu-id="def34-124">You need to create the following access groups in Azure AD:</span></span>
  
- <span data-ttu-id="def34-125">Webbplatsadministratörer (som kommer att innehålla listan från steg 1)</span><span class="sxs-lookup"><span data-stu-id="def34-125">Site admins (which will contain the list from step 1)</span></span>
    
- <span data-ttu-id="def34-126">Webbplatsmedlemmar (som kommer att innehålla listan från steg 2)</span><span class="sxs-lookup"><span data-stu-id="def34-126">Site members (which will contain the list from step 2)</span></span>
    
- <span data-ttu-id="def34-127">Webbplatsvisning (som kommer att innehålla listan från steg 3)</span><span class="sxs-lookup"><span data-stu-id="def34-127">Site viewers (which will contain the list from step 3)</span></span>
    
1. <span data-ttu-id="def34-128">I webbläsaren går du till [https://portal.azure.com](https://portal.azure.com) Azure-portalen och loggar in med autentiseringsuppgifterna för ett konto som har tilldelats med användarhanteringsadministratör eller företagsadministratörsroll.</span><span class="sxs-lookup"><span data-stu-id="def34-128">In your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com) and sign in with the credentials of an account that has been assigned with User Management Admin or Company Administrator role.</span></span>
    
2. <span data-ttu-id="def34-129">I Azure-portalen klickar du på **Azure Active Directory > Grupper**.</span><span class="sxs-lookup"><span data-stu-id="def34-129">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>
    
3. <span data-ttu-id="def34-130">Gå till bladet **Grupper – Alla grupper** och klicka på **+ Ny grupp**.</span><span class="sxs-lookup"><span data-stu-id="def34-130">On the **Groups - All groups** blade, click **+ New group**.</span></span>
    
4. <span data-ttu-id="def34-131">På den **nya koncernen** blad:</span><span class="sxs-lookup"><span data-stu-id="def34-131">On the **New Group** blade:</span></span>
    
    - <span data-ttu-id="def34-132">Välj **Säkerhet** i **Grupptyp**.</span><span class="sxs-lookup"><span data-stu-id="def34-132">Select **Security** in **Group type**.</span></span>

    - <span data-ttu-id="def34-133">Skriv gruppnamnet i **Namn**.</span><span class="sxs-lookup"><span data-stu-id="def34-133">Type the group name in **Name**.</span></span>

    - <span data-ttu-id="def34-134">Skriv en beskrivning av gruppen i **Gruppbeskrivning**.</span><span class="sxs-lookup"><span data-stu-id="def34-134">Type a description of the group in **Group description**.</span></span>

    - <span data-ttu-id="def34-135">Välj **Tilldelad** i **Typ av medlemskap**.</span><span class="sxs-lookup"><span data-stu-id="def34-135">Select **Assigned** in **Membership type**.</span></span>
    
5. <span data-ttu-id="def34-136">Klicka på **Skapa** och stäng sedan bladet **Grupp**.</span><span class="sxs-lookup"><span data-stu-id="def34-136">Click **Create**, and then close the **Group** blade.</span></span>
    
6. <span data-ttu-id="def34-137">Upprepa steg 3-5 för dina ytterligare grupper.</span><span class="sxs-lookup"><span data-stu-id="def34-137">Repeat steps 3-5 for your additional groups.</span></span>
    
> [!NOTE]
> <span data-ttu-id="def34-138">Du måste använda Azure-portalen för att skapa grupper så att de har Office-funktioner aktiverade.</span><span class="sxs-lookup"><span data-stu-id="def34-138">You need to use the Azure portal to create the groups so that they have Office features enabled.</span></span> <span data-ttu-id="def34-139">Om en isolerad SharePoint Online-webbplats senare konfigureras som en mycket konfidentiell webbplats med en Azure Information Protection-etikett för att kryptera filer och tilldela behörighet till specifika grupper, måste de tillåtna grupperna ha skapats med Office-funktioner aktiverade.</span><span class="sxs-lookup"><span data-stu-id="def34-139">If a SharePoint Online isolated site is later configured as a Highly Confidential site with an Azure Information Protection label to encrypt files and assign permission to specific groups, the permitted groups must have been created with Office features enabled.</span></span> <span data-ttu-id="def34-140">Du kan inte ändra inställningen för Office-funktioner för en Azure AD-grupp när den har skapats.</span><span class="sxs-lookup"><span data-stu-id="def34-140">You cannot change the Office features setting of an Azure AD group after it has been created.</span></span> 
  
<span data-ttu-id="def34-141">Här är din resulterande konfiguration med de tre platsåtkomstgrupperna.</span><span class="sxs-lookup"><span data-stu-id="def34-141">Here is your resulting configuration with the three site access groups.</span></span>
  
![De tre åtkomstgrupperna för distributionen av en isolerad SharePoint Online-webbplats.](../../media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)
  
### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a><span data-ttu-id="def34-143">Steg 5.</span><span class="sxs-lookup"><span data-stu-id="def34-143">Step 5.</span></span> <span data-ttu-id="def34-144">Lägga till användarkontona i åtkomstgrupperna</span><span class="sxs-lookup"><span data-stu-id="def34-144">Add the user accounts to the access groups</span></span>

<span data-ttu-id="def34-145">Gör så här i det här steget:</span><span class="sxs-lookup"><span data-stu-id="def34-145">In this step, do the following:</span></span>
  
1. <span data-ttu-id="def34-146">Lägga till listan över användare från steg 1 i åtkomstgruppen för webbplatsadministratörer</span><span class="sxs-lookup"><span data-stu-id="def34-146">Add the list of users from step 1 to the site admins access group</span></span>
    
2. <span data-ttu-id="def34-147">Lägga till listan över användare från steg 2 i åtkomstgruppen för webbplatsmedlemmar</span><span class="sxs-lookup"><span data-stu-id="def34-147">Add the list of users from step 2 to the site members access group</span></span>
    
3. <span data-ttu-id="def34-148">Lägga till listan över användare från steg 3 i åtkomstgruppen för webbplatsvisningsprogram</span><span class="sxs-lookup"><span data-stu-id="def34-148">Add the list of users from step 3 to the site viewers access group</span></span>
    
<span data-ttu-id="def34-149">Om du hanterar användarkonton och grupper via AD DS (Active Directory Domain Services) lägger du till användare i lämpliga åtkomstgrupper med hjälp av dina vanliga AD DS-användar- och grupphanteringsprocedurer och väntar på synkronisering med din Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="def34-149">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Microsoft 365 subscription.</span></span>
  
<span data-ttu-id="def34-150">Om du hanterar användarkonton och grupper via Office 365 kan du använda microsoft 365-administrationscentret eller PowerShell.</span><span class="sxs-lookup"><span data-stu-id="def34-150">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell.</span></span> <span data-ttu-id="def34-151">Om du har dubbla gruppnamn för någon av åtkomstgrupperna bör du använda administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="def34-151">If you have duplicate group names for any of the access groups, you should use the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="def34-152">För administrationscentret för Microsoft 365 loggar du in med ett användarkonto som har tilldelats rollen Administratör för användarkonto eller Företagsadministratör och använder grupper för att lägga till lämpliga användarkonton och grupper i lämpliga åtkomstgrupper.</span><span class="sxs-lookup"><span data-stu-id="def34-152">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate user accounts and groups to the appropriate access groups.</span></span>
  
<span data-ttu-id="def34-153">För PowerShell, anslut först [med Azure Active Directory PowerShell för Graph-modulen](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="def34-153">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="def34-154">Använd sedan följande kommandoblock för att lägga till ett enskilt användarkonto i en åtkomstgrupp:</span><span class="sxs-lookup"><span data-stu-id="def34-154">Next, use the following command block to add an individual user account to an access group:</span></span>
  
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```
<span data-ttu-id="def34-155">Om du har lagrat UPN för användarkonton för någon av åtkomstgrupperna i en textfil kan du använda följande PowerShell-kommandoblock för att lägga till dem alla på en gång:</span><span class="sxs-lookup"><span data-stu-id="def34-155">If you stored the UPNs of user accounts for any of the access groups in a text file, you can use the following PowerShell command block to add them all at one time:</span></span>
  
```powershell
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

<span data-ttu-id="def34-156">För PowerShell använder du följande kommandoblock för att lägga till en enskild grupp i en åtkomstgrupp:</span><span class="sxs-lookup"><span data-stu-id="def34-156">For PowerShell, use the following command block to add an individual group to an access group:</span></span>
  
```powershell
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID

```

<span data-ttu-id="def34-157">Resultaten bör vara följande:</span><span class="sxs-lookup"><span data-stu-id="def34-157">The results should be the following:</span></span>
  
- <span data-ttu-id="def34-158">Azure AD-gruppen för webbplatsadministratörer innehåller användarkonton eller grupper för webbplatsadministratörer</span><span class="sxs-lookup"><span data-stu-id="def34-158">The site admins Azure AD group contains the site admin user accounts or groups</span></span>
    
- <span data-ttu-id="def34-159">Webbplatsmedlemmarna Azure AD-gruppen innehåller användarkonton eller grupper för webbplatsmedlemsanvändare</span><span class="sxs-lookup"><span data-stu-id="def34-159">The site members Azure AD group contains the site member user accounts or groups</span></span>
    
- <span data-ttu-id="def34-160">Webbplatsens tittare Azure AD-gruppen innehåller användarkonton eller grupper som bara kan visa webbplatsens innehåll</span><span class="sxs-lookup"><span data-stu-id="def34-160">The site viewers Azure AD group contains the user accounts or groups that can only view the site contents</span></span>
    
<span data-ttu-id="def34-161">Verifiera listan över gruppmedlemmar för varje åtkomstgrupp med Microsoft 365-administrationscentret eller med följande PowerShell-kommandoblock:</span><span class="sxs-lookup"><span data-stu-id="def34-161">Validate the list of group members for each access group with the Microsoft 365 admin center or with the following PowerShell command block:</span></span>
  
```powershell
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

<span data-ttu-id="def34-162">Här är din resulterande konfiguration med de tre platsåtkomstgrupperna som fylls med användarkonton eller grupper.</span><span class="sxs-lookup"><span data-stu-id="def34-162">Here is your resulting configuration with the three site access groups populated with user accounts or groups.</span></span>
  
![De tre åtkomstgrupperna som fylls med användarkonton.](../../media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)
  
## <a name="phase-2-create-and-configure-the-isolated-team-site"></a><span data-ttu-id="def34-164">Fas 2: Skapa och konfigurera den isolerade gruppplatsen</span><span class="sxs-lookup"><span data-stu-id="def34-164">Phase 2: Create and configure the isolated team site</span></span>

<span data-ttu-id="def34-165">I den här fasen skapar du den isolerade SharePoint Online-webbplatsen och konfigurerar behörigheterna för standardbehörighetsnivåerna för SharePoint Online för att använda dina nya Azure AD-baserade åtkomstgrupper.</span><span class="sxs-lookup"><span data-stu-id="def34-165">In this phase, you create the isolated SharePoint Online site and configure the permissions for the default SharePoint Online permission levels to use your new Azure AD-based access groups.</span></span> <span data-ttu-id="def34-166">Som standard innehåller nya gruppwebbplatser en Microsoft 365-grupp och andra relaterade resurser, men i det här fallet skapar vi en gruppwebbplats utan en Microsoft 365-grupp.</span><span class="sxs-lookup"><span data-stu-id="def34-166">By default, new team sites include a Microsoft 365 group and other related resources, but in this case, we'll create a team site without a Microsoft 365 group.</span></span> <span data-ttu-id="def34-167">Detta gör det möjligt att behålla behörigheter helt via SharePoint.</span><span class="sxs-lookup"><span data-stu-id="def34-167">This allows maintaining permissions entirely through SharePoint.</span></span>
  
<span data-ttu-id="def34-168">Skapa först SharePoint Online-gruppwebbplatsen med de här stegen.</span><span class="sxs-lookup"><span data-stu-id="def34-168">First, create the SharePoint Online team site with these steps.</span></span>
  
1. <span data-ttu-id="def34-169">Logga in på Microsoft 365-administrationscentret med ett konto som också används för att administrera SharePoint Online-gruppwebbplatsen (en SharePoint Online-administratör).</span><span class="sxs-lookup"><span data-stu-id="def34-169">Sign in to the Microsoft 365 admin center with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator).</span></span> <span data-ttu-id="def34-170">Mer information finns i [Så här loggar du in i Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="def34-170">For help, see [Where to sign in to Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="def34-171">Klicka på **SharePoint**under **Administrationscenter**i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="def34-171">In the Microsoft 365 admin center, under **Admin centers**, click **SharePoint**.</span></span>

3. <span data-ttu-id="def34-172">Expandera **Webbplatser** i administrationscentret för SharePoint och klicka på **Aktiva webbplatser.**</span><span class="sxs-lookup"><span data-stu-id="def34-172">In the SharePoint admin center, expand **Sites** and click **Active sites**.</span></span>

4. <span data-ttu-id="def34-173">Klicka på **Skapa**och välj sedan **Andra alternativ**.</span><span class="sxs-lookup"><span data-stu-id="def34-173">Click **Create**, and then choose **Other options**.</span></span>

5. <span data-ttu-id="def34-174">Välj **Gruppwebbplats**i listan **Välj en mall** .</span><span class="sxs-lookup"><span data-stu-id="def34-174">In the **Choose a template** list, choose **Team site**.</span></span>
   
6. <span data-ttu-id="def34-175">Skriv ett namn för gruppwebbplatsen i **Platsnamn.**</span><span class="sxs-lookup"><span data-stu-id="def34-175">In **Site name**, type a name for the team site.</span></span> 
    
7. <span data-ttu-id="def34-176">I **Primär administratör**skriver du det konto som du är inloggad med.</span><span class="sxs-lookup"><span data-stu-id="def34-176">In **Primary administrator**, type the account that you are logged in with.</span></span>
 
8. <span data-ttu-id="def34-177">Klicka på **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="def34-177">Click **Finish**.</span></span>
    
<span data-ttu-id="def34-178">Konfigurera sedan behörigheter från den nya SharePoint Online-gruppwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="def34-178">Next, from the new SharePoint Online team site, configure permissions.</span></span>
  
1. <span data-ttu-id="def34-179">Klicka på inställningsikonen i verktygsfältet och klicka sedan på **Webbplatsbehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="def34-179">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

2. <span data-ttu-id="def34-180">Klicka på **Ändra hur medlemmar kan dela**under **Webbplatsdelning.**</span><span class="sxs-lookup"><span data-stu-id="def34-180">Under **Site sharing**, click **Change how members can share**.</span></span>

3. <span data-ttu-id="def34-181">Välj de **enda webbplatsägare som kan dela filer, mappar och webbplatsen**.</span><span class="sxs-lookup"><span data-stu-id="def34-181">Choose the **Only site owners can share files, folders, and the site**.</span></span>

4. <span data-ttu-id="def34-182">Ange **Tillåt åtkomstbegäranden** till **Av**.</span><span class="sxs-lookup"><span data-stu-id="def34-182">Set **Allow access requests** to **Off**.</span></span>

5. <span data-ttu-id="def34-183">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="def34-183">Click **Save**.</span></span>
    
6. <span data-ttu-id="def34-184">Klicka på **Avancerade behörighetsinställningar**i fönstret **Behörigheter.**</span><span class="sxs-lookup"><span data-stu-id="def34-184">In the **Permissions** pane, click **Advanced permissions settings**.</span></span>
    
7. <span data-ttu-id="def34-185">Klicka på \*\* \<webbplatsnamn> medlemmar\*\* i listan på fliken **Behörigheter** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="def34-185">On the **Permissions** tab of your browser, click **\<site name> Members** in the list.</span></span>
    
8. <span data-ttu-id="def34-186">Klicka på **Nytt**i **Personer och grupper.**</span><span class="sxs-lookup"><span data-stu-id="def34-186">In **People and Groups**, click **New**.</span></span>
    
9. <span data-ttu-id="def34-187">Skriv namnet på åtkomstgruppen för webbplatsmedlemmar i dialogrutan **Dela,** markera det och klicka sedan på **Dela**.</span><span class="sxs-lookup"><span data-stu-id="def34-187">In the **Share** dialog box, type the name of the site members access group, select it, and then click **Share**.</span></span>
    
10. <span data-ttu-id="def34-188">Klicka på bakåtknappen i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="def34-188">Click the back button on your browser.</span></span>
    
11. <span data-ttu-id="def34-189">Klicka på \*\* \<webbplatsnamnet> ägare\*\* i listan.</span><span class="sxs-lookup"><span data-stu-id="def34-189">Click **\<site name> Owners** in the list.</span></span>
    
12. <span data-ttu-id="def34-190">Klicka på **Nytt**i **Personer och grupper.**</span><span class="sxs-lookup"><span data-stu-id="def34-190">In **People and Groups**, click **New**.</span></span>
    
13. <span data-ttu-id="def34-191">Skriv namnet på åtkomstgruppen för webbplatsadministratörer i dialogrutan **Dela,** markera det och klicka sedan på **Dela**.</span><span class="sxs-lookup"><span data-stu-id="def34-191">In the **Share** dialog box, type the name of the site admins access group, select it, and then click **Share**.</span></span>
    
14. <span data-ttu-id="def34-192">Klicka på bakåtknappen i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="def34-192">Click the back button on your browser.</span></span>
    
15. <span data-ttu-id="def34-193">Klicka på \*\* \<webbplatsnamnet> besökare\*\* i listan.</span><span class="sxs-lookup"><span data-stu-id="def34-193">Click **\<site name> Visitors** in the list.</span></span>
    
16. <span data-ttu-id="def34-194">Klicka på **Nytt**i **Personer och grupper.**</span><span class="sxs-lookup"><span data-stu-id="def34-194">In **People and Groups**, click **New**.</span></span>
    
17. <span data-ttu-id="def34-195">Skriv namnet på åtkomstgruppen för webbplatsvisning i dialogrutan **Dela,** markera det och klicka sedan på **Dela**.</span><span class="sxs-lookup"><span data-stu-id="def34-195">In the **Share** dialog box, type the name of the site viewers access group, select it, and then click **Share**.</span></span>
    
18. <span data-ttu-id="def34-196">Stäng fliken **Behörigheter** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="def34-196">Close the **Permissions** tab of your browser.</span></span>
    
<span data-ttu-id="def34-197">Resultatet av dessa behörighetsinställningar är:</span><span class="sxs-lookup"><span data-stu-id="def34-197">The results of these permission settings are:</span></span>
  
- <span data-ttu-id="def34-198">\*\* \<Webbplatsnamnet> SharePoint-gruppen ägare\*\* innehåller åtkomstgruppen för webbplatsadministratörer, där alla medlemmar har behörighetsnivån **Fullständig behörighet.**</span><span class="sxs-lookup"><span data-stu-id="def34-198">The **\<site name> Owners** SharePoint group contains the site admins access group, in which all the members have the **Full control** permission level.</span></span>
    
- <span data-ttu-id="def34-199">\*\* \<Webbplatsnamnet> SharePoint-gruppen medlemmar\*\* innehåller åtkomstgruppen för webbplatsmedlemmar, där alla medlemmar har **behörighetsnivån Redigera.**</span><span class="sxs-lookup"><span data-stu-id="def34-199">The **\<site name> Members** SharePoint group contains the site members access group, in which all the members have the **Edit** permission level.</span></span>
    
- <span data-ttu-id="def34-200">\*\* \<Webbplatsnamnet> SharePoint-gruppen för besökare\*\* innehåller åtkomstgruppen för webbplatsvisningsbesökare, där alla medlemmar har **läsbehörighetsnivån.**</span><span class="sxs-lookup"><span data-stu-id="def34-200">The **\<site name> Visitors** SharePoint group contains the site viewers access group, in which all the members have the **Read** permission level.</span></span>
    
- <span data-ttu-id="def34-201">Möjligheten för medlemmar att bjuda in andra medlemmar eller för icke-medlemmar att begära åtkomst är inaktiverad.</span><span class="sxs-lookup"><span data-stu-id="def34-201">The ability for members to invite other members or for non-members to request access is disabled.</span></span>
    
<span data-ttu-id="def34-202">Här är din resulterande konfiguration med de tre SharePoint-grupperna för webbplatsen konfigurerad för att använda de tre åtkomstgrupperna, som fylls i med användarkonton eller Azure AD-grupper.</span><span class="sxs-lookup"><span data-stu-id="def34-202">Here is your resulting configuration with the three SharePoint groups for the site configured to use the three access groups, which are populated with user accounts or Azure AD groups.</span></span>
  
![Den slutliga konfigurationen av din isolerade SharePoint Online-webbplats med åtkomstgrupper och användarkonton.](../../media/e7618971-06ab-447b-90ff-d8be3790fe63.png)
  
<span data-ttu-id="def34-204">Du och medlemmarna på webbplatsen, genom gruppmedlemskap i en av åtkomstgrupperna, kan nu samarbeta med hjälp av webbplatsens resurser.</span><span class="sxs-lookup"><span data-stu-id="def34-204">You and the members of the site, through group membership in one of the access groups, can now collaborate using the resources of the site.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="def34-205">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="def34-205">Next step</span></span>

<span data-ttu-id="def34-206">När du behöver ändra medlemskap i webbplatsåtkomstgrupp eller skapa en dokumentmapp med anpassade behörigheter läser du [Hantera en isolerad SharePoint Online-gruppwebbplats](manage-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="def34-206">When you need to change site access group membership or create a document folder with custom permissions, see [Manage an isolated SharePoint Online team site](manage-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="def34-207">Se även</span><span class="sxs-lookup"><span data-stu-id="def34-207">See Also</span></span>

[<span data-ttu-id="def34-208">Isolerade SharePoint Online-gruppwebbplatser</span><span class="sxs-lookup"><span data-stu-id="def34-208">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="def34-209">Utforma en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="def34-209">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)
  
[<span data-ttu-id="def34-210">Hantera en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="def34-210">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)
  



