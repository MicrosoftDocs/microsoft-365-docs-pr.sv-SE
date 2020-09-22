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
description: Använd den här stegvisa distributions guiden för att skapa och konfigurera en isolerad SharePoint Online-gruppwebbplats i Microsoft Office 365.
ms.openlocfilehash: f2800e74149e79e5c3f0444799f454ab8b3caf69
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203137"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="c6eb3-103">Distribuera en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="c6eb3-103">Deploy an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 <span data-ttu-id="c6eb3-104">**Sammanfattning:** Distribuera en ny isolerad SharePoint Online-gruppwebbplats med de här stegvisa anvisningarna.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-104">**Summary:** Deploy a new isolated SharePoint Online team site with these step-by-step instructions.</span></span>
  
<span data-ttu-id="c6eb3-105">Den här artikeln är en steg-för-steg-guide för hur du skapar och konfigurerar en isolerad SharePoint Online-gruppwebbplats i Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-105">This article is a step-by-step deployment guide for creating and configuring an isolated SharePoint Online team site in Microsoft Office 365.</span></span> <span data-ttu-id="c6eb3-106">De här stegen förutsätter användning av de tre SharePoint-standardgrupperna och motsvarande behörighets nivåer, med en enda Azure Active Directory (AD)-baserad åtkomst grupp för varje åtkomst nivå.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-106">These steps assume the use of the three default SharePoint groups and corresponding permission levels, with a single Azure Active Directory (AD)-based access group for each level of access.</span></span>
  
## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a><span data-ttu-id="c6eb3-107">Fas 1: skapa och fylla i åtkomst grupperna för grupp webbplatser</span><span class="sxs-lookup"><span data-stu-id="c6eb3-107">Phase 1: Create and populate the team site access groups</span></span>

<span data-ttu-id="c6eb3-108">I den här fasen skapar du de tre Azure AD-baserade åtkomst grupperna för de tre SharePoint-standardgrupperna och fyller dem med rätt användar konton.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-108">In this phase, you create the three Azure AD-based access groups for the three default SharePoint groups and populate them with the appropriate user accounts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c6eb3-109">Följande anvisningar förutsätter att alla nödvändiga användar konton redan finns och har tilldelats rätt licenser.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-109">The following steps assume that all necessary user accounts already exist and are assigned the appropriate licenses.</span></span> <span data-ttu-id="c6eb3-110">Om inte, Lägg till dem och tilldela licenser innan du går vidare till steg 1.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-110">If not, please add them and assign licenses before proceeding to step 1.</span></span> 
  
### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a><span data-ttu-id="c6eb3-111">Steg 1: lista SharePoint Online-administratörer för webbplatsen</span><span class="sxs-lookup"><span data-stu-id="c6eb3-111">Step 1: List the SharePoint Online admins for the site</span></span>

<span data-ttu-id="c6eb3-112">Bestäm vilka användar konton som motsvarar SharePoint Online-administratörer för den isolerade grupp webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-112">Determine the set of user accounts corresponding to the SharePoint Online admins for the isolated team site.</span></span>
  
<span data-ttu-id="c6eb3-113">Om du hanterar användar konton och grupper via Microsoft 365 och vill använda Windows PowerShell kan du skapa en lista över deras UPN-namn (exempel på UPN: belindan@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c6eb3-113">If you are managing user accounts and groups through Microsoft 365 and want to use Windows PowerShell, make a list of their user principal names (UPNs) (example UPN: belindan@contoso.com).</span></span>
  
### <a name="step-2-list-the-members-for-the-site"></a><span data-ttu-id="c6eb3-114">Steg 2: lista medlemmar för webbplatsen</span><span class="sxs-lookup"><span data-stu-id="c6eb3-114">Step 2: List the members for the site</span></span>

<span data-ttu-id="c6eb3-115">Bestäm vilka användar konton som motsvarar medlemmarna för den isolerade grupp webbplatsen, de som samarbetar med resurser som lagras på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-115">Determine the set of user accounts corresponding to the members for the isolated team site, those who will be collaborating on resources stored within the site.</span></span>
  
<span data-ttu-id="c6eb3-116">Om du hanterar användar konton och grupper via Microsoft 365 och vill använda PowerShell kan du skapa en lista över deras UPN-objekt.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-116">If you are managing user accounts and groups through Microsoft 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="c6eb3-117">Om det finns många webbplats medlemmar kan du lagra listan med UPN i en textfil och lägga till alla med ett enda PowerShell-kommando.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-117">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>
  
### <a name="step-3-list-the-viewers-for-the-site"></a><span data-ttu-id="c6eb3-118">Steg 3: Visa webbplatsens visnings program</span><span class="sxs-lookup"><span data-stu-id="c6eb3-118">Step 3: List the viewers for the site</span></span>

<span data-ttu-id="c6eb3-119">Ta reda på vilka användar konton som motsvarar läsarna på den isolerade grupp webbplatsen, de som kan visa resurserna som lagras på webbplatsen, men inte ändra dem eller samar beta direkt i deras innehåll.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-119">Determine the set of user accounts corresponding to the viewers of the isolated team site, those who can view the resources stored in the site but not modify them or directly collaborate on their contents.</span></span>
  
<span data-ttu-id="c6eb3-120">Om du hanterar användar konton och grupper via Microsoft 365 och vill använda PowerShell kan du skapa en lista över deras UPN-objekt.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-120">If you are managing user accounts and groups through Microsoft 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="c6eb3-121">Om det finns många webbplats medlemmar kan du lagra listan med UPN i en textfil och lägga till alla med ett enda PowerShell-kommando.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-121">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>
  
<span data-ttu-id="c6eb3-122">Visnings program för webbplatsen kan omfatta företags ledning, juridisk rådgivning eller intressenter mellan institutioner.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-122">Viewers for the site might include executive management, legal counsel, or inter-departmental stakeholders.</span></span>
  
### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a><span data-ttu-id="c6eb3-123">Steg 4: skapa de tre åtkomst grupperna för webbplatsen i Azure AD</span><span class="sxs-lookup"><span data-stu-id="c6eb3-123">Step 4: Create the three access groups for the site in Azure AD</span></span>

<span data-ttu-id="c6eb3-124">Du måste skapa följande åtkomst grupper i Azure AD:</span><span class="sxs-lookup"><span data-stu-id="c6eb3-124">You need to create the following access groups in Azure AD:</span></span>
  
- <span data-ttu-id="c6eb3-125">Webbplats administratörer (som kommer att innehålla listan från steg 1)</span><span class="sxs-lookup"><span data-stu-id="c6eb3-125">Site admins (which will contain the list from step 1)</span></span>
    
- <span data-ttu-id="c6eb3-126">Webbplats medlemmar (som kommer att innehålla listan från steg 2)</span><span class="sxs-lookup"><span data-stu-id="c6eb3-126">Site members (which will contain the list from step 2)</span></span>
    
- <span data-ttu-id="c6eb3-127">Webbplats visnings program (som kommer att innehålla listan från steg 3)</span><span class="sxs-lookup"><span data-stu-id="c6eb3-127">Site viewers (which will contain the list from step 3)</span></span>
    
1. <span data-ttu-id="c6eb3-128">I din webbläsare går du till Azure-portalen [https://portal.azure.com](https://portal.azure.com) och loggar in med autentiseringsuppgifterna för ett konto som har tilldelats användar hanterings administratören eller administratörs rollen för administratörer.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-128">In your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com) and sign in with the credentials of an account that has been assigned with User Management Admin or Company Administrator role.</span></span>
    
2. <span data-ttu-id="c6eb3-129">I Azure-portalen klickar du på **Azure Active Directory > Grupper**.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-129">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>
    
3. <span data-ttu-id="c6eb3-130">Gå till bladet **Grupper – Alla grupper** och klicka på **+ Ny grupp**.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-130">On the **Groups - All groups** blade, click **+ New group**.</span></span>
    
4. <span data-ttu-id="c6eb3-131">I det **nya grupp** bladet:</span><span class="sxs-lookup"><span data-stu-id="c6eb3-131">On the **New Group** blade:</span></span>
    
    - <span data-ttu-id="c6eb3-132">Välj **Säkerhet** i **Grupptyp**.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-132">Select **Security** in **Group type**.</span></span>

    - <span data-ttu-id="c6eb3-133">Skriv grupp namnet i **namn**.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-133">Type the group name in **Name**.</span></span>

    - <span data-ttu-id="c6eb3-134">Ange en beskrivning av gruppen i **grupp beskrivningen**.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-134">Type a description of the group in **Group description**.</span></span>

    - <span data-ttu-id="c6eb3-135">Välj **Tilldelad** i **Typ av medlemskap**.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-135">Select **Assigned** in **Membership type**.</span></span>
    
5. <span data-ttu-id="c6eb3-136">Klicka på **Skapa** och stäng sedan bladet **Grupp**.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-136">Click **Create**, and then close the **Group** blade.</span></span>
    
6. <span data-ttu-id="c6eb3-137">Upprepa steg 3-5 för dina fler grupper.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-137">Repeat steps 3-5 for your additional groups.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c6eb3-138">Du måste använda Azure-portalen för att skapa grupperna så att de har aktiverade Office-funktioner.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-138">You need to use the Azure portal to create the groups so that they have Office features enabled.</span></span> <span data-ttu-id="c6eb3-139">Om en SharePoint Online-isolerad webbplats senare är konfigurerad som en mycket konfidentiell webbplats med en Azure information Protection-etikett för att kryptera filer och tilldela behörigheter till specifika grupper måste de tillåtna grupperna ha skapats med Office-funktioner aktiverade.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-139">If a SharePoint Online isolated site is later configured as a Highly Confidential site with an Azure Information Protection label to encrypt files and assign permission to specific groups, the permitted groups must have been created with Office features enabled.</span></span> <span data-ttu-id="c6eb3-140">Du kan inte ändra Office-funktioner för en Azure AD-grupp efter att den har skapats.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-140">You cannot change the Office features setting of an Azure AD group after it has been created.</span></span> 
  
<span data-ttu-id="c6eb3-141">Här är din resulterande konfiguration med de tre webbplats åtkomst grupperna.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-141">Here is your resulting configuration with the three site access groups.</span></span>
  
![De tre åtkomst grupperna för en isolerad SharePoint Online-webbplats.](../../media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)
  
### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a><span data-ttu-id="c6eb3-143">Steg 5:</span><span class="sxs-lookup"><span data-stu-id="c6eb3-143">Step 5.</span></span> <span data-ttu-id="c6eb3-144">Lägga till användar konton i åtkomst grupperna</span><span class="sxs-lookup"><span data-stu-id="c6eb3-144">Add the user accounts to the access groups</span></span>

<span data-ttu-id="c6eb3-145">I det här steget gör du följande:</span><span class="sxs-lookup"><span data-stu-id="c6eb3-145">In this step, do the following:</span></span>
  
1. <span data-ttu-id="c6eb3-146">Lägga till listan med användare från steg 1 i gruppen webbplats administratörer</span><span class="sxs-lookup"><span data-stu-id="c6eb3-146">Add the list of users from step 1 to the site admins access group</span></span>
    
2. <span data-ttu-id="c6eb3-147">Lägga till listan med användare från steg 2 till gruppen webbplats medlemmar</span><span class="sxs-lookup"><span data-stu-id="c6eb3-147">Add the list of users from step 2 to the site members access group</span></span>
    
3. <span data-ttu-id="c6eb3-148">Lägga till listan med användare från steg 3 i gruppen webbplats visnings åtkomst</span><span class="sxs-lookup"><span data-stu-id="c6eb3-148">Add the list of users from step 3 to the site viewers access group</span></span>
    
<span data-ttu-id="c6eb3-149">Om du hanterar användar konton och grupper via AD DS (Active Directory Domain Services) lägger du till användare i lämpliga åtkomst grupper med hjälp av din vanliga AD DS-användare och grupp hanterings procedurer och väntar på synkronisering med Microsoft 365-prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-149">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Microsoft 365 subscription.</span></span>
  
<span data-ttu-id="c6eb3-150">Om du hanterar användar konton och grupper via Office 365 kan du använda administrations centret för Microsoft 365 eller PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-150">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell.</span></span> <span data-ttu-id="c6eb3-151">Om du har dubbletter av grupp namn för någon av åtkomst grupperna bör du använda administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-151">If you have duplicate group names for any of the access groups, you should use the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="c6eb3-152">För administrations centret för Microsoft 365 loggar du in med ett användar konto som har tilldelats rollen användar konto administratör eller företags administratör och använder grupper för att lägga till användar konton och grupper i lämpliga åtkomst grupper.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-152">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate user accounts and groups to the appropriate access groups.</span></span>
  
<span data-ttu-id="c6eb3-153">För PowerShell, [Anslut först med Azure Active Directory PowerShell för Graph](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell?view=o365-worldwide#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="c6eb3-153">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell?view=o365-worldwide#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="c6eb3-154">Använd sedan följande kommando block för att lägga till ett enskilt användar konto i en åtkomst grupp:</span><span class="sxs-lookup"><span data-stu-id="c6eb3-154">Next, use the following command block to add an individual user account to an access group:</span></span>
  
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```
<span data-ttu-id="c6eb3-155">Om du har lagrat UPN för användar konton för någon av åtkomst grupperna i en textfil kan du använda följande PowerShell-kommando block för att lägga till dem samtidigt:</span><span class="sxs-lookup"><span data-stu-id="c6eb3-155">If you stored the UPNs of user accounts for any of the access groups in a text file, you can use the following PowerShell command block to add them all at one time:</span></span>
  
```powershell
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

<span data-ttu-id="c6eb3-156">För PowerShell använder du följande kommando block för att lägga till en enskild grupp i en Access-grupp:</span><span class="sxs-lookup"><span data-stu-id="c6eb3-156">For PowerShell, use the following command block to add an individual group to an access group:</span></span>
  
```powershell
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID

```

<span data-ttu-id="c6eb3-157">Resultaten bör vara följande:</span><span class="sxs-lookup"><span data-stu-id="c6eb3-157">The results should be the following:</span></span>
  
- <span data-ttu-id="c6eb3-158">Webbplats administratörer Azure AD-gruppen innehåller användar kontona för webbplats administratören</span><span class="sxs-lookup"><span data-stu-id="c6eb3-158">The site admins Azure AD group contains the site admin user accounts or groups</span></span>
    
- <span data-ttu-id="c6eb3-159">Webbplats medlemmarnas Azure AD-grupp innehåller webbplats medlemmarnas användar konton eller grupper</span><span class="sxs-lookup"><span data-stu-id="c6eb3-159">The site members Azure AD group contains the site member user accounts or groups</span></span>
    
- <span data-ttu-id="c6eb3-160">Webbplats visnings program Azure AD-gruppen innehåller användar konton eller grupper som endast kan visa webbplats innehållet</span><span class="sxs-lookup"><span data-stu-id="c6eb3-160">The site viewers Azure AD group contains the user accounts or groups that can only view the site contents</span></span>
    
<span data-ttu-id="c6eb3-161">Verifiera listan med grupp medlemmar för varje åtkomst grupp med administrations centret för Microsoft 365 eller med följande PowerShell-kommando block:</span><span class="sxs-lookup"><span data-stu-id="c6eb3-161">Validate the list of group members for each access group with the Microsoft 365 admin center or with the following PowerShell command block:</span></span>
  
```powershell
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

<span data-ttu-id="c6eb3-162">Här är din resulterande konfiguration med de tre webbplats åtkomst grupperna som är ifyllda med användar konton eller grupper.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-162">Here is your resulting configuration with the three site access groups populated with user accounts or groups.</span></span>
  
![De tre åtkomst grupperna som är ifyllda med användar konton.](../../media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)
  
## <a name="phase-2-create-and-configure-the-isolated-team-site"></a><span data-ttu-id="c6eb3-164">Fas 2: skapa och konfigurera den isolerade grupp webbplatsen</span><span class="sxs-lookup"><span data-stu-id="c6eb3-164">Phase 2: Create and configure the isolated team site</span></span>

<span data-ttu-id="c6eb3-165">I den här fasen skapar du den isolerade SharePoint Online-webbplatsen och konfigurerar behörigheterna för standard behörighets nivåerna i SharePoint Online för att använda de nya Azure AD-baserade åtkomst grupperna.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-165">In this phase, you create the isolated SharePoint Online site and configure the permissions for the default SharePoint Online permission levels to use your new Azure AD-based access groups.</span></span> <span data-ttu-id="c6eb3-166">Som standard innehåller nya grupp webbplatser en Microsoft 365-grupp och andra relaterade resurser, men i det här fallet skapar vi en grupp webbplats utan en Microsoft 365-grupp.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-166">By default, new team sites include a Microsoft 365 group and other related resources, but in this case, we'll create a team site without a Microsoft 365 group.</span></span> <span data-ttu-id="c6eb3-167">Detta möjliggör underhåll av behörigheter helt och hållet via SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-167">This allows maintaining permissions entirely through SharePoint.</span></span>
  
<span data-ttu-id="c6eb3-168">Börja med att skapa grupp webbplatsen för SharePoint Online med de här stegen.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-168">First, create the SharePoint Online team site with these steps.</span></span>
  
1. <span data-ttu-id="c6eb3-169">Logga in på administrations centret för Microsoft 365 med ett konto som också används för att administrera SharePoint Online-gruppwebbplatsen (en SharePoint Online-administratör).</span><span class="sxs-lookup"><span data-stu-id="c6eb3-169">Sign in to the Microsoft 365 admin center with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator).</span></span> <span data-ttu-id="c6eb3-170">Mer information finns i [Så här loggar du in i Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="c6eb3-170">For help, see [Where to sign in to Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="c6eb3-171">Klicka på **SharePoint** **i administrations**centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-171">In the Microsoft 365 admin center, under **Admin centers**, click **SharePoint**.</span></span>

3. <span data-ttu-id="c6eb3-172">Expandera **webbplatser** och klicka på **aktiva webbplatser**i administrations centret för SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-172">In the SharePoint admin center, expand **Sites** and click **Active sites**.</span></span>

4. <span data-ttu-id="c6eb3-173">Klicka på **skapa**och välj sedan **andra alternativ**.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-173">Click **Create**, and then choose **Other options**.</span></span>

5. <span data-ttu-id="c6eb3-174">Välj **grupp webbplats**i listan **Välj en mall** .</span><span class="sxs-lookup"><span data-stu-id="c6eb3-174">In the **Choose a template** list, choose **Team site**.</span></span>
   
6. <span data-ttu-id="c6eb3-175">Ange ett namn på grupp webbplatsen i **webbplats namn**.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-175">In **Site name**, type a name for the team site.</span></span> 
    
7. <span data-ttu-id="c6eb3-176">I **primär administratör**skriver du det konto som du är inloggad med.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-176">In **Primary administrator**, type the account that you are logged in with.</span></span>
 
8. <span data-ttu-id="c6eb3-177">Klicka på **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-177">Click **Finish**.</span></span>
    
<span data-ttu-id="c6eb3-178">Sedan kan du konfigurera behörigheter från den nya SharePoint Online-gruppwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-178">Next, from the new SharePoint Online team site, configure permissions.</span></span>
  
1. <span data-ttu-id="c6eb3-179">Klicka på inställningsikonen i verktygsfältet och klicka sedan på **Webbplatsbehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-179">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

2. <span data-ttu-id="c6eb3-180">Klicka på **ändra hur medlemmar kan dela**under **webbplats delning**.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-180">Under **Site sharing**, click **Change how members can share**.</span></span>

3. <span data-ttu-id="c6eb3-181">Välj de **enda webbplats ägarna som kan dela filer, mappar och webbplatsen**.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-181">Choose the **Only site owners can share files, folders, and the site**.</span></span>

4. <span data-ttu-id="c6eb3-182">Ange **Tillåt åtkomst förfrågningar** till **av**.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-182">Set **Allow access requests** to **Off**.</span></span>

5. <span data-ttu-id="c6eb3-183">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-183">Click **Save**.</span></span>
    
6. <span data-ttu-id="c6eb3-184">I fönstret **behörigheter** klickar du på **avancerade behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-184">In the **Permissions** pane, click **Advanced permissions settings**.</span></span>
    
7. <span data-ttu-id="c6eb3-185">Klicka på \*\* \<site name> medlemmar\*\* i listan på fliken **behörigheter** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-185">On the **Permissions** tab of your browser, click **\<site name> Members** in the list.</span></span>
    
8. <span data-ttu-id="c6eb3-186">Klicka på **nytt**i **personer och grupper**.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-186">In **People and Groups**, click **New**.</span></span>
    
9. <span data-ttu-id="c6eb3-187">I dialog rutan **dela** skriver du in namnet på gruppen webbplats medlemmar, markerar den och klickar sedan på **dela**.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-187">In the **Share** dialog box, type the name of the site members access group, select it, and then click **Share**.</span></span>
    
10. <span data-ttu-id="c6eb3-188">Klicka på bakåtknappen i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-188">Click the back button on your browser.</span></span>
    
11. <span data-ttu-id="c6eb3-189">Klicka på \*\* \<site name> ägare\*\* i listan.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-189">Click **\<site name> Owners** in the list.</span></span>
    
12. <span data-ttu-id="c6eb3-190">Klicka på **nytt**i **personer och grupper**.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-190">In **People and Groups**, click **New**.</span></span>
    
13. <span data-ttu-id="c6eb3-191">I dialog rutan **dela** skriver du in namnet på gruppen webbplats administratörer, markerar den och klickar sedan på **dela**.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-191">In the **Share** dialog box, type the name of the site admins access group, select it, and then click **Share**.</span></span>
    
14. <span data-ttu-id="c6eb3-192">Klicka på bakåtknappen i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-192">Click the back button on your browser.</span></span>
    
15. <span data-ttu-id="c6eb3-193">Klicka på \*\* \<site name> besökare\*\* i listan.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-193">Click **\<site name> Visitors** in the list.</span></span>
    
16. <span data-ttu-id="c6eb3-194">Klicka på **nytt**i **personer och grupper**.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-194">In **People and Groups**, click **New**.</span></span>
    
17. <span data-ttu-id="c6eb3-195">I dialog rutan **dela** skriver du namnet på gruppen visnings åtkomst för webbplats, markerar den och klickar sedan på **dela**.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-195">In the **Share** dialog box, type the name of the site viewers access group, select it, and then click **Share**.</span></span>
    
18. <span data-ttu-id="c6eb3-196">Stäng fliken **behörigheter** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-196">Close the **Permissions** tab of your browser.</span></span>
    
<span data-ttu-id="c6eb3-197">Resultatet av dessa behörighets inställningar är:</span><span class="sxs-lookup"><span data-stu-id="c6eb3-197">The results of these permission settings are:</span></span>
  
- <span data-ttu-id="c6eb3-198">SharePoint-gruppen \*\* \<site name> ägare\*\* innehåller gruppen webbplats administratörer åtkomst där alla medlemmar har **fullständig** behörighets nivå.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-198">The **\<site name> Owners** SharePoint group contains the site admins access group, in which all the members have the **Full control** permission level.</span></span>
    
- <span data-ttu-id="c6eb3-199">SharePoint-gruppen \*\* \<site name> medlemmar\*\* innehåller gruppen webbplats medlemmar åtkomst där alla medlemmar har behörighets nivån **Redigera** .</span><span class="sxs-lookup"><span data-stu-id="c6eb3-199">The **\<site name> Members** SharePoint group contains the site members access group, in which all the members have the **Edit** permission level.</span></span>
    
- <span data-ttu-id="c6eb3-200">SharePoint-gruppen \*\* \<site name> besökare\*\* innehåller gruppen webbplats visnings åtkomst där alla medlemmar har behörighets nivån **läsa** .</span><span class="sxs-lookup"><span data-stu-id="c6eb3-200">The **\<site name> Visitors** SharePoint group contains the site viewers access group, in which all the members have the **Read** permission level.</span></span>
    
- <span data-ttu-id="c6eb3-201">Möjligheten för medlemmar att bjuda in andra medlemmar eller för icke-medlemmar att begära åtkomst är inaktive rad.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-201">The ability for members to invite other members or for non-members to request access is disabled.</span></span>
    
<span data-ttu-id="c6eb3-202">Här är din resulterande konfiguration med de tre SharePoint-grupperna för webbplatsen konfigurerade för att använda de tre åtkomst grupperna, som är ifyllda med användar konton eller Azure AD-grupper.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-202">Here is your resulting configuration with the three SharePoint groups for the site configured to use the three access groups, which are populated with user accounts or Azure AD groups.</span></span>
  
![Den sista konfigurationen av din isolerade SharePoint Online-webbplats med åtkomst grupper och användar konton.](../../media/e7618971-06ab-447b-90ff-d8be3790fe63.png)
  
<span data-ttu-id="c6eb3-204">Du och medlemmar av webbplatsen, via grupp medlemskap i en av åtkomst grupperna, kan nu samar beta med webbplats resurserna.</span><span class="sxs-lookup"><span data-stu-id="c6eb3-204">You and the members of the site, through group membership in one of the access groups, can now collaborate using the resources of the site.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="c6eb3-205">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="c6eb3-205">Next step</span></span>

<span data-ttu-id="c6eb3-206">Om du behöver ändra grupp medlemskap för webbplats åtkomst eller skapa en dokumentmapp med anpassade behörigheter läser du [hantera en isolerad SharePoint Online-gruppwebbplats](manage-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="c6eb3-206">When you need to change site access group membership or create a document folder with custom permissions, see [Manage an isolated SharePoint Online team site](manage-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c6eb3-207">Se även</span><span class="sxs-lookup"><span data-stu-id="c6eb3-207">See Also</span></span>

[<span data-ttu-id="c6eb3-208">Isolerade SharePoint Online-gruppwebbplatser</span><span class="sxs-lookup"><span data-stu-id="c6eb3-208">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="c6eb3-209">Utforma en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="c6eb3-209">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)
  
[<span data-ttu-id="c6eb3-210">Hantera en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="c6eb3-210">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)
  



