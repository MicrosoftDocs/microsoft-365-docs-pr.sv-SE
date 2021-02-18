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
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: Använd den här stegvisa distributionsguiden för att skapa och konfigurera en isolerad SharePoint Online-gruppwebbplats i Microsoft Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d226a545c3f8dc274f02e5d54d39739fe5d981ea
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288353"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="523eb-103">Distribuera en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="523eb-103">Deploy an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="523eb-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="523eb-104">**Applies to**</span></span>
- [<span data-ttu-id="523eb-105">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="523eb-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="523eb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="523eb-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

 <span data-ttu-id="523eb-107">**Sammanfattning:** Distribuera en ny isolerad SharePoint Online-gruppwebbplats med de här stegvisa instruktionerna.</span><span class="sxs-lookup"><span data-stu-id="523eb-107">**Summary:** Deploy a new isolated SharePoint Online team site with these step-by-step instructions.</span></span>

<span data-ttu-id="523eb-108">Den här artikeln är en stegvis distributionsguide för hur du skapar och konfigurerar en isolerad SharePoint Online-gruppwebbplats i Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="523eb-108">This article is a step-by-step deployment guide for creating and configuring an isolated SharePoint Online team site in Microsoft Office 365.</span></span> <span data-ttu-id="523eb-109">I de här stegen förutsätts det att de tre standardgrupperna i SharePoint och motsvarande behörighetsnivåer används, med en enda Azure Active Directory-baserad åtkomstgrupp (AD) för varje åtkomstnivå.</span><span class="sxs-lookup"><span data-stu-id="523eb-109">These steps assume the use of the three default SharePoint groups and corresponding permission levels, with a single Azure Active Directory (AD)-based access group for each level of access.</span></span>

## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a><span data-ttu-id="523eb-110">Fas 1: Skapa och fylla i åtkomstgrupper för gruppwebbplatser</span><span class="sxs-lookup"><span data-stu-id="523eb-110">Phase 1: Create and populate the team site access groups</span></span>

<span data-ttu-id="523eb-111">I den här fasen skapar du de tre Azure AD-baserade åtkomstgrupperna för de tre standardgrupperna i SharePoint och fyller dem med lämpliga användarkonton.</span><span class="sxs-lookup"><span data-stu-id="523eb-111">In this phase, you create the three Azure AD-based access groups for the three default SharePoint groups and populate them with the appropriate user accounts.</span></span>

> [!NOTE]
> <span data-ttu-id="523eb-112">Följande steg förutsätter att alla nödvändiga användarkonton redan finns och har tilldelats lämpliga licenser.</span><span class="sxs-lookup"><span data-stu-id="523eb-112">The following steps assume that all necessary user accounts already exist and are assigned the appropriate licenses.</span></span> <span data-ttu-id="523eb-113">Annars kan du lägga till dem och tilldela licenser innan du fortsätter med steg 1.</span><span class="sxs-lookup"><span data-stu-id="523eb-113">If not, please add them and assign licenses before proceeding to step 1.</span></span>

### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a><span data-ttu-id="523eb-114">Steg 1: Lista SharePoint Online-administratörerna för webbplatsen</span><span class="sxs-lookup"><span data-stu-id="523eb-114">Step 1: List the SharePoint Online admins for the site</span></span>

<span data-ttu-id="523eb-115">Fastställ den uppsättning användarkonton som motsvarar SharePoint Online-administratörerna för den isolerade gruppwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="523eb-115">Determine the set of user accounts corresponding to the SharePoint Online admins for the isolated team site.</span></span>

<span data-ttu-id="523eb-116">Om du hanterar användarkonton och grupper via Microsoft 365 och vill använda Windows PowerShell gör du en lista över deras användarhuvudnamn (UPN) (exempel UPN: belindan@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="523eb-116">If you are managing user accounts and groups through Microsoft 365 and want to use Windows PowerShell, make a list of their user principal names (UPNs) (example UPN: belindan@contoso.com).</span></span>

### <a name="step-2-list-the-members-for-the-site"></a><span data-ttu-id="523eb-117">Steg 2: Lista medlemmar för webbplatsen</span><span class="sxs-lookup"><span data-stu-id="523eb-117">Step 2: List the members for the site</span></span>

<span data-ttu-id="523eb-118">Fastställ vilken uppsättning användarkonton som motsvarar medlemmarna för den isolerade gruppwebbplatsen, de som ska samarbeta med resurser som lagras på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="523eb-118">Determine the set of user accounts corresponding to the members for the isolated team site, those who will be collaborating on resources stored within the site.</span></span>

<span data-ttu-id="523eb-119">Om du hanterar användarkonton och grupper via Microsoft 365 och vill använda PowerShell gör du en lista med deras UPN-namn.</span><span class="sxs-lookup"><span data-stu-id="523eb-119">If you are managing user accounts and groups through Microsoft 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="523eb-120">Om det finns många medlemmar på webbplatsen kan du lagra listan med UPN-namn i en textfil och lägga till dem alla med ett enda PowerShell-kommando.</span><span class="sxs-lookup"><span data-stu-id="523eb-120">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>

### <a name="step-3-list-the-viewers-for-the-site"></a><span data-ttu-id="523eb-121">Steg 3: Lista användarna för webbplatsen</span><span class="sxs-lookup"><span data-stu-id="523eb-121">Step 3: List the viewers for the site</span></span>

<span data-ttu-id="523eb-122">Bestäm vilken uppsättning användarkonton som motsvarar de som visar den isolerade gruppwebbplatsen, de som kan visa de resurser som finns lagrade på webbplatsen men inte ändra dem eller samarbeta direkt med innehållet.</span><span class="sxs-lookup"><span data-stu-id="523eb-122">Determine the set of user accounts corresponding to the viewers of the isolated team site, those who can view the resources stored in the site but not modify them or directly collaborate on their contents.</span></span>

<span data-ttu-id="523eb-123">Om du hanterar användarkonton och grupper via Microsoft 365 och vill använda PowerShell gör du en lista med deras UPN-namn.</span><span class="sxs-lookup"><span data-stu-id="523eb-123">If you are managing user accounts and groups through Microsoft 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="523eb-124">Om det finns många medlemmar på webbplatsen kan du lagra listan med UPN-namn i en textfil och lägga till dem alla med ett enda PowerShell-kommando.</span><span class="sxs-lookup"><span data-stu-id="523eb-124">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>

<span data-ttu-id="523eb-125">Användare för webbplatsen kan omfatta ledning, juridisk rådgivning eller mellan avdelningars intressenter.</span><span class="sxs-lookup"><span data-stu-id="523eb-125">Viewers for the site might include executive management, legal counsel, or inter-departmental stakeholders.</span></span>

### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a><span data-ttu-id="523eb-126">Steg 4: Skapa de tre åtkomstgrupperna för webbplatsen i Azure AD</span><span class="sxs-lookup"><span data-stu-id="523eb-126">Step 4: Create the three access groups for the site in Azure AD</span></span>

<span data-ttu-id="523eb-127">Du måste skapa följande åtkomstgrupper i Azure AD:</span><span class="sxs-lookup"><span data-stu-id="523eb-127">You need to create the following access groups in Azure AD:</span></span>

- <span data-ttu-id="523eb-128">Webbplatsadministratörer (som kommer att innehålla listan från steg 1)</span><span class="sxs-lookup"><span data-stu-id="523eb-128">Site admins (which will contain the list from step 1)</span></span>
- <span data-ttu-id="523eb-129">Webbplatsmedlemmar (som kommer att innehålla listan från steg 2)</span><span class="sxs-lookup"><span data-stu-id="523eb-129">Site members (which will contain the list from step 2)</span></span>
- <span data-ttu-id="523eb-130">Webbplatsvisare (som kommer att innehålla listan från steg 3)</span><span class="sxs-lookup"><span data-stu-id="523eb-130">Site viewers (which will contain the list from step 3)</span></span>

1. <span data-ttu-id="523eb-131">Gå till Azure-portalen i webbläsaren och logga in med autentiseringsuppgifterna för ett konto som har tilldelats rollen Användarhanteringsadministratör eller <https://portal.azure.com> Företagsadministratör.</span><span class="sxs-lookup"><span data-stu-id="523eb-131">In your browser, go to the Azure portal at <https://portal.azure.com> and sign in with the credentials of an account that has been assigned with User Management Admin or Company Administrator role.</span></span>

2. <span data-ttu-id="523eb-132">I Azure-portalen klickar du på **Azure Active Directory > Grupper**.</span><span class="sxs-lookup"><span data-stu-id="523eb-132">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>

3. <span data-ttu-id="523eb-133">Gå till bladet **Grupper – Alla grupper** och klicka på **+ Ny grupp**.</span><span class="sxs-lookup"><span data-stu-id="523eb-133">On the **Groups - All groups** blade, click **+ New group**.</span></span>

4. <span data-ttu-id="523eb-134">I **bladet Ny** grupp:</span><span class="sxs-lookup"><span data-stu-id="523eb-134">On the **New Group** blade:</span></span>

   - <span data-ttu-id="523eb-135">Välj **Säkerhet** i **Grupptyp**.</span><span class="sxs-lookup"><span data-stu-id="523eb-135">Select **Security** in **Group type**.</span></span>

   - <span data-ttu-id="523eb-136">Skriv gruppnamnet i **Namn.**</span><span class="sxs-lookup"><span data-stu-id="523eb-136">Type the group name in **Name**.</span></span>

   - <span data-ttu-id="523eb-137">Skriv en beskrivning av gruppen i **gruppbeskrivningen.**</span><span class="sxs-lookup"><span data-stu-id="523eb-137">Type a description of the group in **Group description**.</span></span>

   - <span data-ttu-id="523eb-138">Välj **Tilldelad** i **Typ av medlemskap**.</span><span class="sxs-lookup"><span data-stu-id="523eb-138">Select **Assigned** in **Membership type**.</span></span>

5. <span data-ttu-id="523eb-139">Klicka på **Skapa** och stäng sedan bladet **Grupp**.</span><span class="sxs-lookup"><span data-stu-id="523eb-139">Click **Create**, and then close the **Group** blade.</span></span>

6. <span data-ttu-id="523eb-140">Upprepa steg 3–5 för de övriga grupperna.</span><span class="sxs-lookup"><span data-stu-id="523eb-140">Repeat steps 3-5 for your additional groups.</span></span>

> [!NOTE]
> <span data-ttu-id="523eb-141">Du måste använda Azure Portal för att skapa grupperna så att de har Office-funktioner aktiverade.</span><span class="sxs-lookup"><span data-stu-id="523eb-141">You need to use the Azure portal to create the groups so that they have Office features enabled.</span></span> <span data-ttu-id="523eb-142">Om en sharePoint Online-isolerad webbplats senare konfigureras som en webbplats med mycket konfidentiell information med azure informationsskydd-etiketten för att kryptera filer och tilldela behörighet till specifika grupper, måste de tillåtna grupperna ha skapats med Office-funktioner aktiverade.</span><span class="sxs-lookup"><span data-stu-id="523eb-142">If a SharePoint Online isolated site is later configured as a Highly Confidential site with an Azure Information Protection label to encrypt files and assign permission to specific groups, the permitted groups must have been created with Office features enabled.</span></span> <span data-ttu-id="523eb-143">Du kan inte ändra Office-funktioner för en Azure AD-grupp när den har skapats.</span><span class="sxs-lookup"><span data-stu-id="523eb-143">You cannot change the Office features setting of an Azure AD group after it has been created.</span></span>

<span data-ttu-id="523eb-144">Här är den resulterande konfigurationen med de tre grupperna för webbplatsåtkomst.</span><span class="sxs-lookup"><span data-stu-id="523eb-144">Here is your resulting configuration with the three site access groups.</span></span>

![De tre åtkomstgrupperna för din distribution av en isolerad SharePoint Online-webbplats.](../../media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)

### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a><span data-ttu-id="523eb-146">Steg 5:</span><span class="sxs-lookup"><span data-stu-id="523eb-146">Step 5.</span></span> <span data-ttu-id="523eb-147">Lägga till användarkontona i åtkomstgrupper</span><span class="sxs-lookup"><span data-stu-id="523eb-147">Add the user accounts to the access groups</span></span>

<span data-ttu-id="523eb-148">I det här steget gör du följande:</span><span class="sxs-lookup"><span data-stu-id="523eb-148">In this step, do the following:</span></span>

1. <span data-ttu-id="523eb-149">Lägg till listan med användare från steg 1 i åtkomstgruppen för webbplatsadministratörer.</span><span class="sxs-lookup"><span data-stu-id="523eb-149">Add the list of users from step 1 to the site admins access group.</span></span>
2. <span data-ttu-id="523eb-150">Lägg till listan med användare från steg 2 i åtkomstgruppen för webbplatsmedlemmar.</span><span class="sxs-lookup"><span data-stu-id="523eb-150">Add the list of users from step 2 to the site members access group.</span></span>
3. <span data-ttu-id="523eb-151">Lägg till listan med användare från steg 3 i åtkomstgruppen för webbplatsvisare.</span><span class="sxs-lookup"><span data-stu-id="523eb-151">Add the list of users from step 3 to the site viewers access group.</span></span>

<span data-ttu-id="523eb-152">Om du hanterar användarkonton och grupper via Active Directory DS (AD DS) kan du lägga till användare i lämpliga åtkomstgrupper med dina vanliga procedurer för användar- och grupphantering i AD DS och vänta på synkronisering med Microsoft 365-prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="523eb-152">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Microsoft 365 subscription.</span></span>

<span data-ttu-id="523eb-153">Om du hanterar användarkonton och grupper via Office 365 kan du använda administrationscentret för Microsoft 365 eller PowerShell.</span><span class="sxs-lookup"><span data-stu-id="523eb-153">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell.</span></span> <span data-ttu-id="523eb-154">Om du har dubbletter av gruppnamn för någon av åtkomstgrupperna bör du använda administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="523eb-154">If you have duplicate group names for any of the access groups, you should use the Microsoft 365 admin center.</span></span>

<span data-ttu-id="523eb-155">I administrationscentret för Microsoft 365 loggar du in med ett användarkonto som har tilldelats rollen Som administratör för användarkonto eller Företagsadministratör, och använder Grupper för att lägga till användarkonton och grupper i lämpliga åtkomstgrupper.</span><span class="sxs-lookup"><span data-stu-id="523eb-155">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate user accounts and groups to the appropriate access groups.</span></span>

<span data-ttu-id="523eb-156">För PowerShell ska du [först ansluta till Azure Active Directory PowerShell för Graph-modulen.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="523eb-156">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="523eb-157">Använd sedan följande kommandoblock för att lägga till ett enskilt användarkonto i en åtkomstgrupp:</span><span class="sxs-lookup"><span data-stu-id="523eb-157">Next, use the following command block to add an individual user account to an access group:</span></span>

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="523eb-158">Om du har lagrat UPN-namn för användarkonton för någon av åtkomstgrupperna i en textfil kan du använda följande PowerShell-kommandoblock för att lägga till dem alla samtidigt:</span><span class="sxs-lookup"><span data-stu-id="523eb-158">If you stored the UPNs of user accounts for any of the access groups in a text file, you can use the following PowerShell command block to add them all at one time:</span></span>

```powershell
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

<span data-ttu-id="523eb-159">För PowerShell använder du följande kommandoblock för att lägga till en enskild grupp i en åtkomstgrupp:</span><span class="sxs-lookup"><span data-stu-id="523eb-159">For PowerShell, use the following command block to add an individual group to an access group:</span></span>

```powershell
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="523eb-160">Resultatet bör vara följande:</span><span class="sxs-lookup"><span data-stu-id="523eb-160">The results should be the following:</span></span>

- <span data-ttu-id="523eb-161">Webbplatsadministratörerna för Azure AD-gruppen innehåller användarkonton eller grupper för webbplatsadministratörer</span><span class="sxs-lookup"><span data-stu-id="523eb-161">The site admins Azure AD group contains the site admin user accounts or groups</span></span>
- <span data-ttu-id="523eb-162">Azure AD-gruppen för webbplatsmedlemmar innehåller användarkonton eller grupper för webbplatsmedlemmar</span><span class="sxs-lookup"><span data-stu-id="523eb-162">The site members Azure AD group contains the site member user accounts or groups</span></span>
- <span data-ttu-id="523eb-163">Azure AD-gruppen för webbplatsvisningsprogram innehåller användarkonton eller grupper som bara kan visa webbplatsinnehållet</span><span class="sxs-lookup"><span data-stu-id="523eb-163">The site viewers Azure AD group contains the user accounts or groups that can only view the site contents</span></span>

<span data-ttu-id="523eb-164">Validera listan över gruppmedlemmar för varje åtkomstgrupp med administrationscentret för Microsoft 365 eller med följande PowerShell-kommandoblock:</span><span class="sxs-lookup"><span data-stu-id="523eb-164">Validate the list of group members for each access group with the Microsoft 365 admin center or with the following PowerShell command block:</span></span>

```powershell
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

<span data-ttu-id="523eb-165">Här är den resulterande konfigurationen med de tre grupperna för webbplatsåtkomst som är ifyllda med användarkonton eller grupper.</span><span class="sxs-lookup"><span data-stu-id="523eb-165">Here is your resulting configuration with the three site access groups populated with user accounts or groups.</span></span>

![De tre åtkomstgrupperna som är ifyllda med användarkonton.](../../media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)

## <a name="phase-2-create-and-configure-the-isolated-team-site"></a><span data-ttu-id="523eb-167">Fas 2: Skapa och konfigurera den isolerade gruppwebbplatsen</span><span class="sxs-lookup"><span data-stu-id="523eb-167">Phase 2: Create and configure the isolated team site</span></span>

<span data-ttu-id="523eb-168">I den här fasen skapar du den isolerade SharePoint Online-webbplatsen och konfigurerar behörigheterna för standardbehörighetsnivåerna i SharePoint Online till att använda de nya Azure AD-baserade åtkomstgrupperna.</span><span class="sxs-lookup"><span data-stu-id="523eb-168">In this phase, you create the isolated SharePoint Online site and configure the permissions for the default SharePoint Online permission levels to use your new Azure AD-based access groups.</span></span> <span data-ttu-id="523eb-169">Som standard innehåller nya gruppwebbplatser en Microsoft 365-grupp och andra relaterade resurser, men i det här fallet skapar vi en gruppwebbplats utan en Microsoft 365-grupp.</span><span class="sxs-lookup"><span data-stu-id="523eb-169">By default, new team sites include a Microsoft 365 group and other related resources, but in this case, we'll create a team site without a Microsoft 365 group.</span></span> <span data-ttu-id="523eb-170">På så sätt kan du underhålla behörigheter helt och hållet via SharePoint.</span><span class="sxs-lookup"><span data-stu-id="523eb-170">This allows maintaining permissions entirely through SharePoint.</span></span>

<span data-ttu-id="523eb-171">Börja med att skapa SharePoint Online-gruppwebbplatsen med de här stegen.</span><span class="sxs-lookup"><span data-stu-id="523eb-171">First, create the SharePoint Online team site with these steps.</span></span>

1. <span data-ttu-id="523eb-172">Logga in på administrationscentret för Microsoft 365 med ett konto som också kommer att användas för att administrera SharePoint Online-gruppwebbplatsen (en SharePoint Online-administratör).</span><span class="sxs-lookup"><span data-stu-id="523eb-172">Sign in to the Microsoft 365 admin center with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator).</span></span> <span data-ttu-id="523eb-173">Mer information finns i [Så här loggar du in i Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="523eb-173">For help, see [Where to sign in to Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="523eb-174">Klicka på SharePoint i administrationscentret för Microsoft 365, under **Administrationscenter.**</span><span class="sxs-lookup"><span data-stu-id="523eb-174">In the Microsoft 365 admin center, under **Admin centers**, click **SharePoint**.</span></span>

3. <span data-ttu-id="523eb-175">I administrationscentret för SharePoint expanderar **du Webbplatser** och klickar **på Aktiva webbplatser.**</span><span class="sxs-lookup"><span data-stu-id="523eb-175">In the SharePoint admin center, expand **Sites** and click **Active sites**.</span></span>

4. <span data-ttu-id="523eb-176">Klicka **på Skapa** och välj sedan Andra **alternativ.**</span><span class="sxs-lookup"><span data-stu-id="523eb-176">Click **Create**, and then choose **Other options**.</span></span>

5. <span data-ttu-id="523eb-177">Välj **Gruppwebbplats i** listan Välj **en mall.**</span><span class="sxs-lookup"><span data-stu-id="523eb-177">In the **Choose a template** list, choose **Team site**.</span></span>

6. <span data-ttu-id="523eb-178">Ange **ett namn** på gruppwebbplatsen i Webbplatsnamn.</span><span class="sxs-lookup"><span data-stu-id="523eb-178">In **Site name**, type a name for the team site.</span></span>

7. <span data-ttu-id="523eb-179">I **Primär administratör** anger du det konto som du är inloggad med.</span><span class="sxs-lookup"><span data-stu-id="523eb-179">In **Primary administrator**, type the account that you are logged in with.</span></span>

8. <span data-ttu-id="523eb-180">Klicka på **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="523eb-180">Click **Finish**.</span></span>

<span data-ttu-id="523eb-181">Konfigurera sedan behörigheter från den nya SharePoint Online-gruppwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="523eb-181">Next, from the new SharePoint Online team site, configure permissions.</span></span>

1. <span data-ttu-id="523eb-182">Klicka på inställningsikonen i verktygsfältet och klicka sedan på **Webbplatsbehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="523eb-182">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

2. <span data-ttu-id="523eb-183">Klicka **på Ändra hur** medlemmar kan dela under **Webbplatsdelning.**</span><span class="sxs-lookup"><span data-stu-id="523eb-183">Under **Site sharing**, click **Change how members can share**.</span></span>

3. <span data-ttu-id="523eb-184">Välj endast **webbplatsägare som kan dela filer, mappar och webbplatsen.**</span><span class="sxs-lookup"><span data-stu-id="523eb-184">Choose the **Only site owners can share files, folders, and the site**.</span></span>

4. <span data-ttu-id="523eb-185">Ställ **in Tillåt åtkomstförfrågningar** på **Av.**</span><span class="sxs-lookup"><span data-stu-id="523eb-185">Set **Allow access requests** to **Off**.</span></span>

5. <span data-ttu-id="523eb-186">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="523eb-186">Click **Save**.</span></span>

6. <span data-ttu-id="523eb-187">Klicka på **Avancerade** behörighetsinställningar i **fönstret Behörigheter.**</span><span class="sxs-lookup"><span data-stu-id="523eb-187">In the **Permissions** pane, click **Advanced permissions settings**.</span></span>

7. <span data-ttu-id="523eb-188">Klicka **på Medlemmar** i listan på fliken **\<site name> Behörigheter** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="523eb-188">On the **Permissions** tab of your browser, click **\<site name> Members** in the list.</span></span>

8. <span data-ttu-id="523eb-189">Klicka **på Nytt i** Personer och **grupper.**</span><span class="sxs-lookup"><span data-stu-id="523eb-189">In **People and Groups**, click **New**.</span></span>

9. <span data-ttu-id="523eb-190">Skriv namnet **på** åtkomstgruppen webbplatsmedlemmar i dialogrutan Dela, markera den och klicka sedan på **Dela.**</span><span class="sxs-lookup"><span data-stu-id="523eb-190">In the **Share** dialog box, type the name of the site members access group, select it, and then click **Share**.</span></span>

10. <span data-ttu-id="523eb-191">Klicka på bakåtknappen i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="523eb-191">Click the back button on your browser.</span></span>

11. <span data-ttu-id="523eb-192">Klicka **\<site name> på** Ägare i listan.</span><span class="sxs-lookup"><span data-stu-id="523eb-192">Click **\<site name> Owners** in the list.</span></span>

12. <span data-ttu-id="523eb-193">Klicka **på Nytt i Personer** och **grupper.**</span><span class="sxs-lookup"><span data-stu-id="523eb-193">In **People and Groups**, click **New**.</span></span>

13. <span data-ttu-id="523eb-194">Skriv namnet **på** åtkomstgruppen webbplatsadministratörer i dialogrutan Dela, markera den och klicka sedan på **Dela.**</span><span class="sxs-lookup"><span data-stu-id="523eb-194">In the **Share** dialog box, type the name of the site admins access group, select it, and then click **Share**.</span></span>

14. <span data-ttu-id="523eb-195">Klicka på bakåtknappen i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="523eb-195">Click the back button on your browser.</span></span>

15. <span data-ttu-id="523eb-196">Klicka **\<site name> på** Besökare i listan.</span><span class="sxs-lookup"><span data-stu-id="523eb-196">Click **\<site name> Visitors** in the list.</span></span>

16. <span data-ttu-id="523eb-197">Klicka **på Nytt i Personer** och **grupper.**</span><span class="sxs-lookup"><span data-stu-id="523eb-197">In **People and Groups**, click **New**.</span></span>

17. <span data-ttu-id="523eb-198">I dialogrutan **Dela** skriver du namnet på gruppen webbplatsvisare, markerar den och klickar sedan på **Dela.**</span><span class="sxs-lookup"><span data-stu-id="523eb-198">In the **Share** dialog box, type the name of the site viewers access group, select it, and then click **Share**.</span></span>

18. <span data-ttu-id="523eb-199">Stäng **fliken Behörigheter** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="523eb-199">Close the **Permissions** tab of your browser.</span></span>

<span data-ttu-id="523eb-200">Resultatet av de här behörighetsinställningarna är:</span><span class="sxs-lookup"><span data-stu-id="523eb-200">The results of these permission settings are:</span></span>

- <span data-ttu-id="523eb-201">SharePoint-gruppen Ägare innehåller webbplatsadministratörsåtkomstgruppen, där alla medlemmar har **behörighetsnivån Fullständig** behörighet. **\<site name>**</span><span class="sxs-lookup"><span data-stu-id="523eb-201">The **\<site name> Owners** SharePoint group contains the site admins access group, in which all the members have the **Full control** permission level.</span></span>
- <span data-ttu-id="523eb-202">**\<site name> SharePoint-gruppen** Medlemmar innehåller gruppen webbplatsmedlemmar, där alla medlemmar har **behörighetsnivån** Redigera.</span><span class="sxs-lookup"><span data-stu-id="523eb-202">The **\<site name> Members** SharePoint group contains the site members access group, in which all the members have the **Edit** permission level.</span></span>
- <span data-ttu-id="523eb-203">**\<site name> SharePoint-gruppen** Besökare innehåller gruppen Webbplatsläsaråtkomst, där alla medlemmar har **behörighetsnivån** Läsa.</span><span class="sxs-lookup"><span data-stu-id="523eb-203">The **\<site name> Visitors** SharePoint group contains the site viewers access group, in which all the members have the **Read** permission level.</span></span>
- <span data-ttu-id="523eb-204">Möjligheten för medlemmar att bjuda in andra medlemmar eller för icke-medlemmar att begära åtkomst inaktiveras.</span><span class="sxs-lookup"><span data-stu-id="523eb-204">The ability for members to invite other members or for non-members to request access is disabled.</span></span>

<span data-ttu-id="523eb-205">Här är den resulterande konfigurationen med de tre SharePoint-grupperna för webbplatsen som konfigurerats för att använda de tre åtkomstgrupperna, som är ifyllda med användarkonton eller Azure AD-grupper.</span><span class="sxs-lookup"><span data-stu-id="523eb-205">Here is your resulting configuration with the three SharePoint groups for the site configured to use the three access groups, which are populated with user accounts or Azure AD groups.</span></span>

![Den slutliga konfigurationen av din isolerade SharePoint Online-webbplats med åtkomstgrupper och användarkonton.](../../media/e7618971-06ab-447b-90ff-d8be3790fe63.png)

<span data-ttu-id="523eb-207">Du och webbplatsens medlemmar, via gruppmedlemskap i någon av åtkomstgrupperna, kan nu samarbeta med hjälp av webbplatsens resurser.</span><span class="sxs-lookup"><span data-stu-id="523eb-207">You and the members of the site, through group membership in one of the access groups, can now collaborate using the resources of the site.</span></span>

## <a name="next-step"></a><span data-ttu-id="523eb-208">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="523eb-208">Next step</span></span>

<span data-ttu-id="523eb-209">Om du behöver ändra medlemskap i en webbplatsåtkomstgrupp eller skapa en dokumentmapp med anpassad behörighet kan du läsa Hantera [en isolerad SharePoint Online-gruppwebbplats.](manage-an-isolated-sharepoint-online-team-site.md)</span><span class="sxs-lookup"><span data-stu-id="523eb-209">When you need to change site access group membership or create a document folder with custom permissions, see [Manage an isolated SharePoint Online team site](manage-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="523eb-210">Se även</span><span class="sxs-lookup"><span data-stu-id="523eb-210">See Also</span></span>

[<span data-ttu-id="523eb-211">Isolerade SharePoint Online-gruppwebbplatser</span><span class="sxs-lookup"><span data-stu-id="523eb-211">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="523eb-212">Utforma en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="523eb-212">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="523eb-213">Hantera en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="523eb-213">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)
