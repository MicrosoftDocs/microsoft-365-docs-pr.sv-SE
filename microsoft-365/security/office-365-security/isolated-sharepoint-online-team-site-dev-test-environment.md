---
title: Isolerad SharePoint Online-grupps dev-och test miljö
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
- TLG
- Ent_TLGs
ms.assetid: d1795031-beef-49ea-a6fc-5da5450d320d
description: 'Sammanfattning: Konfigurera en SharePoint Online-gruppwebbplats som är isolerad från resten av organisationen i din Microsoft 365-miljö.'
ms.openlocfilehash: 6e056cd1d930d13e1ae20f8f8d0cdc9aa886f17e
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616494"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a><span data-ttu-id="e1220-103">Isolerad SharePoint Online-grupps dev-och test miljö</span><span class="sxs-lookup"><span data-stu-id="e1220-103">Isolated SharePoint Online team site dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 <span data-ttu-id="e1220-104">**Sammanfattning:** Konfigurera en SharePoint Online-gruppwebbplats som är isolerad från resten av organisationen i din Microsoft 365-miljö.</span><span class="sxs-lookup"><span data-stu-id="e1220-104">**Summary:** Configure a SharePoint Online team site that is isolated from the rest of the organization in your Microsoft 365 dev/test environment.</span></span>

<span data-ttu-id="e1220-105">SharePoint Online-gruppwebbplatser i Microsoft 365 är platser för samarbete med ett gemensamt dokument bibliotek, en OneNote-anteckningsbok och andra tjänster.</span><span class="sxs-lookup"><span data-stu-id="e1220-105">SharePoint Online team sites in Microsoft 365 are locations for collaboration using a common document library, a OneNote notebook, and other services.</span></span> <span data-ttu-id="e1220-106">I många fall vill du ha bred åtkomst och samarbete mellan avdelningar och organisationer.</span><span class="sxs-lookup"><span data-stu-id="e1220-106">In many cases, you want wide access and collaboration across departments or organizations.</span></span> <span data-ttu-id="e1220-107">I vissa fall vill du dock noggrant kontrol lera åtkomst och behörigheter för samarbete mellan en liten grupp med personer.</span><span class="sxs-lookup"><span data-stu-id="e1220-107">However, in some cases, you want to tightly control the access and permissions for collaboration among a small group of people.</span></span>

<span data-ttu-id="e1220-108">Åtkomst till SharePoint Online-gruppwebbplatser och vilka användare som kan göra styrs av SharePoint-grupper och behörighets nivåer.</span><span class="sxs-lookup"><span data-stu-id="e1220-108">Access to SharePoint Online team sites and what users can do is controlled by SharePoint groups and permission levels.</span></span> <span data-ttu-id="e1220-109">Som standard har SharePoint Online-webbplatser tre åtkomst nivåer:</span><span class="sxs-lookup"><span data-stu-id="e1220-109">By default, SharePoint Online sites have three levels of access:</span></span>

- <span data-ttu-id="e1220-110">**Medlemmar**, som kan visa, skapa och ändra resurser på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="e1220-110">**Members**, who can view, create, and modify resources on the site.</span></span>
- <span data-ttu-id="e1220-111">**Ägare**, som har fullständig kontroll över webbplatsen, inklusive möjligheten att ändra behörigheter.</span><span class="sxs-lookup"><span data-stu-id="e1220-111">**Owners**, who have complete control of the site, including the ability to change permissions.</span></span>
- <span data-ttu-id="e1220-112">**Besökare**, vilka bara kan visa resurser på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="e1220-112">**Visitors**, who only can view resources on the site.</span></span>

<span data-ttu-id="e1220-113">I den här artikeln beskrivs hur du konfigurerar en isolerad SharePoint Online-gruppwebbplats för ett hemligt forsknings projekt med namnet ProjectX.</span><span class="sxs-lookup"><span data-stu-id="e1220-113">This article steps you through the configuration of an isolated SharePoint Online team site for a secret research project named ProjectX.</span></span> <span data-ttu-id="e1220-114">Åtkomst kraven är:</span><span class="sxs-lookup"><span data-stu-id="e1220-114">The access requirements are:</span></span>

- <span data-ttu-id="e1220-115">Endast medlemmar i projektet kan komma åt webbplatsen och dess innehåll (dokument, OneNote-anteckningsbok, sidor) med redigera och visa SharePoint-behörighets nivåer som styrs via grupp medlemskap.</span><span class="sxs-lookup"><span data-stu-id="e1220-115">Only members of the project can access the site and its contents (documents, OneNote Notebook, Pages), with edit and view SharePoint permission levels controlled through group membership.</span></span>

- <span data-ttu-id="e1220-116">Endast webbplats skaparen och medlemmar i en administratörs grupp för webbplatsen kan utföra webbplats administration, vilket inkluderar ändringar på webbplats nivå.</span><span class="sxs-lookup"><span data-stu-id="e1220-116">Only the site creator and members of an Admins group for the site can perform site administration, which includes modifying site-level permissions.</span></span>

<span data-ttu-id="e1220-117">Det finns tre faser för att konfigurera en isolerad SharePoint Online-gruppwebbplats i Microsoft 365 dev/test-miljön:</span><span class="sxs-lookup"><span data-stu-id="e1220-117">There are three phases to setting up an isolated SharePoint Online team site in your Microsoft 365 dev/test environment:</span></span>

1. <span data-ttu-id="e1220-118">Skapa utvecklings-och test miljön för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e1220-118">Create the Microsoft 365 dev/test environment.</span></span>

2. <span data-ttu-id="e1220-119">Skapa användare och grupper för ProjectX.</span><span class="sxs-lookup"><span data-stu-id="e1220-119">Create the users and groups for ProjectX.</span></span>

3. <span data-ttu-id="e1220-120">Skapa en ny ProjectX SharePoint Online-gruppwebbplats och isolera den.</span><span class="sxs-lookup"><span data-stu-id="e1220-120">Create a new ProjectX SharePoint Online team site and isolate it.</span></span>

> [!TIP]
> <span data-ttu-id="e1220-121">Klicka [här](https://aka.ms/catlgstack) för en visuell karta till alla artiklar i den One-guiden för Microsoft Cloud Test Lab.</span><span class="sxs-lookup"><span data-stu-id="e1220-121">Click [here](https://aka.ms/catlgstack) for a visual map to all the articles in the One Microsoft Cloud Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-microsoft-365-devtest-environment"></a><span data-ttu-id="e1220-122">Fas 1: skapa en lätt eller simulerad företags support för Microsoft 365 dev/test</span><span class="sxs-lookup"><span data-stu-id="e1220-122">Phase 1: Build out your lightweight or simulated enterprise Microsoft 365 dev/test environment</span></span>

<span data-ttu-id="e1220-123">Om du bara vill skapa en isolerad SharePoint Online-gruppwebbplats på ett enkelt sätt med minimi kraven följer du instruktionerna i steg 2 och 3 i [Lightweight Base Configuration](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="e1220-123">If you just want to create an isolated SharePoint Online team site in a lightweight way with the minimum requirements, follow the instructions in phases 2 and 3 of [The lightweight base configuration](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).</span></span>

<span data-ttu-id="e1220-124">Om du vill skapa en isolerad SharePoint Online-gruppwebbplats i en simulerad företags konfiguration följer du anvisningarna i [Synkronisera lösen ord för din Microsoft 365 test miljö](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment).</span><span class="sxs-lookup"><span data-stu-id="e1220-124">If you want to create an isolated SharePoint Online team site in a simulated enterprise configuration, follow the instructions in [Password hash synchronization for your Microsoft 365 test environment](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment).</span></span>

> [!NOTE]
> <span data-ttu-id="e1220-125">Att skapa en isolerad SharePoint Online-webbplats kräver inte den simulerade företags dev/test miljön som innehåller ett simulerat intranät som är kopplat till Internet och katalog för en AD DS-skog (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="e1220-125">Creating an isolated SharePoint Online site does not require the simulated enterprise dev/test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="e1220-126">Det finns här som ett alternativ för att testa en isolerad SharePoint Online-webbplats och experimentera med den i en miljö som representerar en typisk organisation.</span><span class="sxs-lookup"><span data-stu-id="e1220-126">It is provided here as an option so that you can test an isolated SharePoint Online site and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-user-accounts-and-access-groups"></a><span data-ttu-id="e1220-127">Fas 2: skapa användar konton och åtkomst grupper</span><span class="sxs-lookup"><span data-stu-id="e1220-127">Phase 2: Create user accounts and access groups</span></span>

<span data-ttu-id="e1220-128">Använd anvisningarna i [Anslut till Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell) för att ansluta till utvärderings prenumerationen med ditt globala administratörs konto från:</span><span class="sxs-lookup"><span data-stu-id="e1220-128">Use the instructions in [Connect to Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell) to connect to your trial subscription with your global administrator account from:</span></span>

- <span data-ttu-id="e1220-129">Din dator (för den lättviktiga Microsoft 365-miljön).</span><span class="sxs-lookup"><span data-stu-id="e1220-129">Your computer (for the lightweight Microsoft 365 dev/test environment).</span></span>

- <span data-ttu-id="e1220-130">Den virtuella KLIENT1-datorn (för den simulerade företags Microsoft 365-miljön).</span><span class="sxs-lookup"><span data-stu-id="e1220-130">The CLIENT1 virtual machine (for the simulated enterprise Microsoft 365 dev/test environment).</span></span>

<span data-ttu-id="e1220-131">Kör de här kommandona från Windows Azure Active Directory-modulen för Windows PowerShell för att skapa nya åtkomst grupper för SharePoint Online-ProjectX:</span><span class="sxs-lookup"><span data-stu-id="e1220-131">To create the new access groups for the ProjectX SharePoint Online team site, run these commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$groupName="ProjectX-Members"
$groupDesc="People allowed to collaborate for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Admins"
$groupDesc="People allowed to administer SharePoint for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Viewers"
$groupDesc="People allowed to view the SharePoint resources for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
```

<span data-ttu-id="e1220-132">Fyll i organisationens namn (till exempel: contosotoycompany), lands koden med två tecken för din plats och kör sedan följande kommandon från Windows Azure Active Directory-modulen för Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e1220-132">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, and then run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$licAssignment= $orgName + ":ENTERPRISEPREMIUM"
$userName= "designer@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Designer" -FirstName Lead -LastName Designer -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="e1220-133">Observera det genererade lösen ordet för det Lead Designer-konto som visas på en säker plats med kommandot **ny-MsolUser** .</span><span class="sxs-lookup"><span data-stu-id="e1220-133">From the display of the **New-MsolUser** command, note the generated password for the Lead Designer account and record it in a safe location.</span></span>

<span data-ttu-id="e1220-134">Kör följande kommandon från Windows Azure Active Directory-modulen för Windows PowerShell-uppmaningen:</span><span class="sxs-lookup"><span data-stu-id="e1220-134">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="e1220-135">Observera det genererade lösen ordet för kontot leads för forskare från visningen av det **nya-MsolUser-** kommandot och registrera det på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="e1220-135">From the display of the **New-MsolUser** command, note the generated password for the Lead Researcher account and record it in a safe location.</span></span>

<span data-ttu-id="e1220-136">Kör följande kommandon från Windows Azure Active Directory-modulen för Windows PowerShell-uppmaningen:</span><span class="sxs-lookup"><span data-stu-id="e1220-136">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="e1220-137">Observera det genererade lösen  ordet för utvecklings direktörs kontot och registrera det på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="e1220-137">From the display of the **New-MsolUser** command, note the generated password for the Development VP account and record it in a safe location.</span></span>

<span data-ttu-id="e1220-138">För att lägga till nya konton i de nya åtkomst grupperna kör du dessa PowerShell-kommandon från Windows Azure Active Directory-modulen för Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e1220-138">Next, to add the new accounts to the new access groups, run these PowerShell commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$grpName="ProjectX-Members"
$userUPN="designer@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$userUPN="researcher@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Admins"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userCredential.UserName }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Viewers"
$userUPN="devvp@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
```

<span data-ttu-id="e1220-139">Resultat</span><span class="sxs-lookup"><span data-stu-id="e1220-139">Results:</span></span>

- <span data-ttu-id="e1220-140">Gruppen ProjectX-Members åtkomst innehåller användar kontona för lead designer och lead-forskare</span><span class="sxs-lookup"><span data-stu-id="e1220-140">The ProjectX-Members access group contains the Lead Designer and Lead Researcher user accounts</span></span>

- <span data-ttu-id="e1220-141">Gruppen ProjectX-Admins åtkomst innehåller det globala administratörs kontot för utvärderings prenumerationen</span><span class="sxs-lookup"><span data-stu-id="e1220-141">The ProjectX-Admins access group contains the global administrator account for your trial subscription</span></span>

- <span data-ttu-id="e1220-142">Gruppen ProjectX-Viewers åtkomst innehåller användar kontot för utvecklings användare</span><span class="sxs-lookup"><span data-stu-id="e1220-142">The ProjectX-Viewers access group contains the Development VP user account</span></span>

<span data-ttu-id="e1220-143">Bild 1 visar åtkomst grupper och deras medlemskap.</span><span class="sxs-lookup"><span data-stu-id="e1220-143">Figure 1 shows the access groups and their membership.</span></span>

<span data-ttu-id="e1220-144">**Bild 1**:</span><span class="sxs-lookup"><span data-stu-id="e1220-144">**Figure 1**:</span></span>

![Microsoft 365-grupperna och deras medlemskap för en isolerad SharePoint Online-gruppwebbplats](../../media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)

## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a><span data-ttu-id="e1220-146">Fas 3: skapa en ny ProjectX för SharePoint Online och isolera den</span><span class="sxs-lookup"><span data-stu-id="e1220-146">Phase 3: Create a new ProjectX SharePoint Online team site and isolate it</span></span>

<span data-ttu-id="e1220-147">Så här skapar du en SharePoint Online-gruppwebbplats för ProjectX:</span><span class="sxs-lookup"><span data-stu-id="e1220-147">To create a SharePoint Online team site for ProjectX, do the following:</span></span>

1. <span data-ttu-id="e1220-148">Med en webbläsare på din lokala dator (Lightweight Configuration) eller på KLIENT1 (simulerad företags konfiguration) loggar du in på Microsoft 365 Admin Center ( <https://admin.microsoft.com> ) med ditt globala administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="e1220-148">Using a browser on either your local computer (lightweight configuration) or on CLIENT1 (simulated enterprise configuration), sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="e1220-149">Klicka på **SharePoint** i listan med paneler.</span><span class="sxs-lookup"><span data-stu-id="e1220-149">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="e1220-150">På den nya fliken SharePoint i webbläsaren klickar du på **+ Skapa webbplats**.</span><span class="sxs-lookup"><span data-stu-id="e1220-150">On the new SharePoint tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="e1220-151">I **grupp webbplatsens namn** skriver du **ProjectX**.</span><span class="sxs-lookup"><span data-stu-id="e1220-151">In **Team site name**, type **ProjectX**.</span></span> <span data-ttu-id="e1220-152">Välj privata medlemmar i **Sekretess inställningar** för **att få åtkomst till webbplatsen**.</span><span class="sxs-lookup"><span data-stu-id="e1220-152">In **Privacy settings**, select **Private - only members can access this site**.</span></span>

5. <span data-ttu-id="e1220-153">I **grupp webbplats Beskrivning** skriver du **SharePoint-webbplats för ProjectX** och klickar sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="e1220-153">In **Team site description**, type **SharePoint site for ProjectX**, and then click **Next**.</span></span>

6. <span data-ttu-id="e1220-154">På sidan **vem vill du lägga till**? klickar du på **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="e1220-154">On the **Who do you want to add**? pane, click **Finish**.</span></span>

7. <span data-ttu-id="e1220-155">På den nya **ProjectX-** fliken i webbläsaren klickar du på ikonen Inställningar och sedan på **webbplats behörigheter** i verktygsfältet.</span><span class="sxs-lookup"><span data-stu-id="e1220-155">On the new **ProjectX-Home** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

8. <span data-ttu-id="e1220-156">I fönstret **Webbplatsbehörigheter** klickar du på **Inställningar för avancerade behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="e1220-156">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

9. <span data-ttu-id="e1220-157">Klicka på **Inställningar** för åtkomstbegäran på fliken ny **behörighet: Project X** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="e1220-157">In the new **Permissions: Project X** tab in your browser, click **Access Request Settings**.</span></span>

10. <span data-ttu-id="e1220-158">I dialog rutan **Inställningar för åtkomst förfrågningar** avmarkerar **du Tillåt medlemmar att dela webbplatsen och enskilda filer och mappar** och **tillåta åtkomst förfrågningar** (så att alla tre kryss rutor är avmarkerade) och klickar sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1220-158">In the **Access Requests Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow access requests** (so that all three check boxes are cleared), and then click **OK**.</span></span>

11. <span data-ttu-id="e1220-159">Klicka på **ProjectX medlemmar** i listan.</span><span class="sxs-lookup"><span data-stu-id="e1220-159">Click **ProjectX Members** in the list.</span></span>

12. <span data-ttu-id="e1220-160">På sidan **Personer och grupper** klickar du på **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="e1220-160">On the **People and Groups** page, click **New**.</span></span>

13. <span data-ttu-id="e1220-161">I dialog rutan **dela** skriver du **ProjectX-members**, markerar den och klickar sedan på **dela**.</span><span class="sxs-lookup"><span data-stu-id="e1220-161">In the **Share** dialog box, type **ProjectX-Members**, select it, and then click **Share**.</span></span>

14. <span data-ttu-id="e1220-162">Klicka på bakåtknappen i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="e1220-162">Click the back button on your browser.</span></span>

15. <span data-ttu-id="e1220-163">Klicka på **ProjectX ägare** i listan.</span><span class="sxs-lookup"><span data-stu-id="e1220-163">Click **ProjectX Owners** in the list.</span></span>

16. <span data-ttu-id="e1220-164">På sidan **Personer och grupper** klickar du på **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="e1220-164">On the **People and Groups** page, click **New**.</span></span>

17. <span data-ttu-id="e1220-165">Skriv **ProjectX – administratörer** i dialog rutan **dela** och klicka sedan på **dela**.</span><span class="sxs-lookup"><span data-stu-id="e1220-165">In the **Share** dialog box, type **ProjectX-Admins**, select it, and then click **Share**.</span></span>

18. <span data-ttu-id="e1220-166">Klicka på bakåtknappen i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="e1220-166">Click the back button on your browser.</span></span>

19. <span data-ttu-id="e1220-167">Klicka på **ProjectX besökare** i listan.</span><span class="sxs-lookup"><span data-stu-id="e1220-167">Click **ProjectX Visitors** in the list.</span></span>

20. <span data-ttu-id="e1220-168">På sidan **Personer och grupper** klickar du på **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="e1220-168">On the **People and Groups** page, click **New**.</span></span>

21. <span data-ttu-id="e1220-169">Skriv **ProjectX-visnings program** i dialog rutan **dela** och klicka på **dela**.</span><span class="sxs-lookup"><span data-stu-id="e1220-169">In the **Share** dialog box, type **ProjectX-Viewers**, select it, and then click **Share**.</span></span>

22. <span data-ttu-id="e1220-170">Stäng fliken **personer och grupper** i webbläsaren, klicka på **ProjectX-** fliken i webbläsaren och stäng sedan fönstret **webbplats behörigheter** .</span><span class="sxs-lookup"><span data-stu-id="e1220-170">Close the **People and Groups** tab in your browser, click the **ProjectX-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="e1220-171">Här är resultatet av att konfigurera behörigheter:</span><span class="sxs-lookup"><span data-stu-id="e1220-171">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="e1220-172">SharePoint-gruppen ProjectX medlemmar innehåller bara gruppen ProjectX-Members åtkomst (som bara innehåller användar kontona Lead Designer och ledar ansvarig) och gruppen ProjectX (som bara innehåller det globala administratörs användar kontot).</span><span class="sxs-lookup"><span data-stu-id="e1220-172">The ProjectX Members SharePoint group contains only the ProjectX-Members access group (which contains only the Lead Designer and Lead Researcher user accounts) and the ProjectX group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="e1220-173">SharePoint-gruppen ProjectX-ägare innehåller bara gruppen ProjectX-Admins åtkomst (som bara innehåller det globala administratörs användar kontot).</span><span class="sxs-lookup"><span data-stu-id="e1220-173">The ProjectX Owners SharePoint group contains only the ProjectX-Admins access group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="e1220-174">SharePoint-gruppen ProjectX besökare innehåller bara gruppen ProjectX-Viewers åtkomst (som bara innehåller användar kontot utvecklings direktör).</span><span class="sxs-lookup"><span data-stu-id="e1220-174">The ProjectX Visitors SharePoint group contains only the ProjectX-Viewers access group (which contains only the Development VP user account).</span></span>

- <span data-ttu-id="e1220-175">Medlemmar kan inte ändra behörigheter på webbplats nivå (detta kan bara utföras av medlemmar i gruppen ProjectX-Admins).</span><span class="sxs-lookup"><span data-stu-id="e1220-175">Members cannot modify site-level permissions (this can only be done by members of the ProjectX-Admins group).</span></span>

- <span data-ttu-id="e1220-176">Andra användarkonton kan inte komma åt webbplatsen eller dess resurser. De kan inte heller begära åtkomst till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="e1220-176">Other user accounts cannot access the site or its resources or request access to the site.</span></span>

<span data-ttu-id="e1220-177">Bild 2 visar SharePoint-grupperna och deras medlemskap.</span><span class="sxs-lookup"><span data-stu-id="e1220-177">Figure 2 shows the SharePoint groups and their membership.</span></span>

<span data-ttu-id="e1220-178">**Bild 2**</span><span class="sxs-lookup"><span data-stu-id="e1220-178">**Figure 2**</span></span>

![SharePoint Online-grupper och deras medlemskap för en isolerad SharePoint Online-gruppwebbplats](../../media/595abff4-64f9-49de-a37a-c70c6856936b.png)

<span data-ttu-id="e1220-180">Nu kan du Visa åtkomst med hjälp av användar kontot för lead designer:</span><span class="sxs-lookup"><span data-stu-id="e1220-180">Now let's demonstrate access using the Lead Designer user account:</span></span>

1. <span data-ttu-id="e1220-181">Stäng **ProjectX-** fliken i webbläsaren och klicka sedan på **Microsoft Office** -fliken Start i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="e1220-181">Close the **ProjectX-Home** tab in your browser, and then click the **Microsoft Office Home** tab in your browser.</span></span>

2. <span data-ttu-id="e1220-182">Klicka på namnet på den globala administratören och klicka sedan på **Logga ut**.</span><span class="sxs-lookup"><span data-stu-id="e1220-182">Click the name of your global administrator, and then click **Sign out**.</span></span>

3. <span data-ttu-id="e1220-183">Logga in på administrations centret för Microsoft 365 ( <https://admin.microsoft.com> ) med namnet Lead Designer och lösen ordet.</span><span class="sxs-lookup"><span data-stu-id="e1220-183">Sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using the Lead Designer account name and its password.</span></span>

4. <span data-ttu-id="e1220-184">Klicka på **SharePoint** i listan med paneler.</span><span class="sxs-lookup"><span data-stu-id="e1220-184">In the list of tiles, click **SharePoint**.</span></span>

5. <span data-ttu-id="e1220-185">På den nya **SharePoint** -fliken i webbläsaren skriver du **ProjectX** i sökrutan, aktiverar sökningen och klickar sedan på **ProjectX** -grupp webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="e1220-185">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site.</span></span> <span data-ttu-id="e1220-186">En ny flik visas i din webbläsare för ProjectX-gruppwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="e1220-186">You should see a new tab in your browser for the ProjectX team site.</span></span>

6. <span data-ttu-id="e1220-187">Klicka på ikonen Inställningar.</span><span class="sxs-lookup"><span data-stu-id="e1220-187">Click the settings icon.</span></span> <span data-ttu-id="e1220-188">Observera att det inte finns något alternativ för **webbplats behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="e1220-188">Notice that there is no option for **Site Permissions**.</span></span> <span data-ttu-id="e1220-189">Det här är korrekt eftersom bara medlemmar i gruppen ProjectX-Admins kan ändra behörigheter på webbplatsen</span><span class="sxs-lookup"><span data-stu-id="e1220-189">This is correct because only the members of the ProjectX-Admins group can modify permissions on the site</span></span>

7. <span data-ttu-id="e1220-190">Öppna Anteckningar eller en text redigerare.</span><span class="sxs-lookup"><span data-stu-id="e1220-190">Open Notepad or a text editor of your choice.</span></span>

8. <span data-ttu-id="e1220-191">Kopiera URL-adressen till ProjectX och klistra in den på en ny rad i anteckningar eller i text redigeraren.</span><span class="sxs-lookup"><span data-stu-id="e1220-191">Copy the URL of the ProjectX team site and paste it on a new line in Notepad or your text editor.</span></span>

9. <span data-ttu-id="e1220-192">Klicka på **dokument** på fliken ny **ProjectX-start** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="e1220-192">On the new **ProjectX-Home** tab in your browser, click **Documents**.</span></span>

10. <span data-ttu-id="e1220-193">Kopiera URL-adressen till ProjectX-mappen och klistra in den på en ny rad i anteckningar eller i text redigeraren.</span><span class="sxs-lookup"><span data-stu-id="e1220-193">Copy the URL of the ProjectX documents folder and paste it on a new line in Notepad or your text editor.</span></span>

11. <span data-ttu-id="e1220-194">På fliken ny **ProjectX-dokument** i webbläsaren klickar du på **nytt > Word-dokument**.</span><span class="sxs-lookup"><span data-stu-id="e1220-194">On the new **ProjectX-Documents** tab in your browser, click **New > Word document**.</span></span>

12. <span data-ttu-id="e1220-195">Skriv lite text på sidan, vänta tills statusen har **sparats**, klicka på knappen tillbaka i webbläsaren och uppdatera sidan.</span><span class="sxs-lookup"><span data-stu-id="e1220-195">Type some text on the page, wait for the status to indicate **Saved**, click the back button on your browser, and then refresh the page.</span></span> <span data-ttu-id="e1220-196">Du bör se en ny **Document.docx** i mappen **dokument** .</span><span class="sxs-lookup"><span data-stu-id="e1220-196">You should see a new **Document.docx** in the **Documents** folder.</span></span>

13. <span data-ttu-id="e1220-197">Klicka på ellipsen för **Document.docx** -dokumentet och klicka sedan på **Hämta en länk**.</span><span class="sxs-lookup"><span data-stu-id="e1220-197">Click the ellipsis for the **Document.docx** document, and then click **Get a link**.</span></span>

14. <span data-ttu-id="e1220-198">Kopiera URL-adressen i dialog rutan **dela Document.docx** och klistra in den på en ny rad i anteckningar eller text redigeraren och stäng sedan dialog rutan **dela Document.docx** .</span><span class="sxs-lookup"><span data-stu-id="e1220-198">Copy the URL in the **Share 'Document.docx'** dialog box and paste it on a new line in Notepad or your text editor, and then close the **Share 'Document.docx'** dialog box.</span></span>

15. <span data-ttu-id="e1220-199">Stäng **ProjectX-dokument** och **SharePoint** -flikar i webbläsaren och klicka sedan på fliken **Microsoft Office hem** .</span><span class="sxs-lookup"><span data-stu-id="e1220-199">Close the **ProjectX-Documents** and **SharePoint** tabs in your browser, and then click the **Microsoft Office Home** tab.</span></span>

16. <span data-ttu-id="e1220-200">Klicka på namnet på **Lead Designer** och sedan på **Logga ut**.</span><span class="sxs-lookup"><span data-stu-id="e1220-200">Click the **Lead Designer** name, and then click **Sign out**.</span></span>

<span data-ttu-id="e1220-201">Nu kan du Visa åtkomst med användar kontot för utvecklings chef:</span><span class="sxs-lookup"><span data-stu-id="e1220-201">Now let's demonstrate access using the Development VP user account:</span></span>

1. <span data-ttu-id="e1220-202">Logga in på administrations centret för Microsoft 365 ( <https://admin.microsoft.com> ) med konto namnet för utvecklings sidan och lösen ordet.</span><span class="sxs-lookup"><span data-stu-id="e1220-202">Sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using the Development VP account name and its password.</span></span>

2. <span data-ttu-id="e1220-203">Klicka på **SharePoint** i listan med paneler.</span><span class="sxs-lookup"><span data-stu-id="e1220-203">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="e1220-204">På den nya **SharePoint** -fliken i webbläsaren skriver du **ProjectX** i sökrutan, aktiverar sökningen och klickar sedan på **ProjectX** -grupp webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="e1220-204">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site.</span></span> <span data-ttu-id="e1220-205">En ny flik visas i din webbläsare för ProjectX-gruppwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="e1220-205">You should see a new tab in your browser for the ProjectX team site.</span></span>

4. <span data-ttu-id="e1220-206">Klicka på **dokument** och sedan på **Document.docx** .</span><span class="sxs-lookup"><span data-stu-id="e1220-206">Click **Documents**, and then click the **Document.docx** file.</span></span>

5. <span data-ttu-id="e1220-207">Prova att ändra texten på fliken **Document.docx** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="e1220-207">In the **Document.docx** tab in your browser, try to modify the text.</span></span> <span data-ttu-id="e1220-208">Du bör se ett meddelande om att **dokumentet är skrivskyddat.**</span><span class="sxs-lookup"><span data-stu-id="e1220-208">You should see a message stating **This document is read-only.**</span></span> <span data-ttu-id="e1220-209">Det förväntas på grund av att användar kontot för utvecklings personen endast har behörigheten Visa för webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="e1220-209">This is expected because the Development VP user account only has view permissions for the site.</span></span>

6. <span data-ttu-id="e1220-210">Stäng flikarna **Document.docx**, **ProjectX** och **SharePoint** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="e1220-210">Close the **Document.docx**, **ProjectX-Documents**, and **SharePoint** tabs in your browser.</span></span>

7. <span data-ttu-id="e1220-211">Klicka på fliken **Microsoft Office-start** , klicka på **utvecklings direktörens** namn och klicka sedan på **Logga ut**.</span><span class="sxs-lookup"><span data-stu-id="e1220-211">Click the **Microsoft Office Home** tab, click the **Development VP** name, and then click **Sign out**.</span></span>

<span data-ttu-id="e1220-212">Nu kan du Visa Access med ett användar konto som inte har behörighet:</span><span class="sxs-lookup"><span data-stu-id="e1220-212">Now let's demonstrate access with a user account that has no permissions:</span></span>

1. <span data-ttu-id="e1220-213">Logga in på administrations centret för Microsoft 365 ( <https://admin.microsoft.com> ) med användare 3-kontonamnet och lösen ordet.</span><span class="sxs-lookup"><span data-stu-id="e1220-213">Sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using the User 3 account name and its password.</span></span>

2. <span data-ttu-id="e1220-214">Klicka på **SharePoint** i listan med paneler.</span><span class="sxs-lookup"><span data-stu-id="e1220-214">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="e1220-215">Skriv **ProjectX** i sökrutan och aktivera sedan sökningen på den nya **SharePoint** -fliken i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="e1220-215">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box and then activate the search.</span></span> <span data-ttu-id="e1220-216">Du bör se meddelandet **ingenting här matchar din sökning.**</span><span class="sxs-lookup"><span data-stu-id="e1220-216">You should see the message **Nothing here matches your search.**</span></span>

4. <span data-ttu-id="e1220-217">Från den öppna instansen av anteckningar eller text redigeraren kopierar du URL-adressen för ProjectX-webbplatsen till adress fältet i webbläsaren och trycker på **RETUR**.</span><span class="sxs-lookup"><span data-stu-id="e1220-217">From the open instance of Notepad or your text editor, copy the URL for the ProjectX site into the address bar of your browser and press **Enter**.</span></span> <span data-ttu-id="e1220-218">Sidan **åtkomst nekad** bör visas.</span><span class="sxs-lookup"><span data-stu-id="e1220-218">You should see an **Access Denied** page.</span></span>

5. <span data-ttu-id="e1220-219">I anteckningar eller text redigeraren kopierar du URL-adressen för ProjectX-dokument till adress fältet i webbläsaren och trycker på **RETUR**.</span><span class="sxs-lookup"><span data-stu-id="e1220-219">From Notepad or your text editor, copy the URL for the ProjectX Documents folder into the address bar of your browser and press **Enter**.</span></span> <span data-ttu-id="e1220-220">Sidan **åtkomst nekad** bör visas.</span><span class="sxs-lookup"><span data-stu-id="e1220-220">You should see an **Access Denied** page.</span></span>

6. <span data-ttu-id="e1220-221">I anteckningar eller text redigeraren kopierar du URL-adressen för Documents.docx filen till webbläsarens Adress fält och trycker på **RETUR**.</span><span class="sxs-lookup"><span data-stu-id="e1220-221">From Notepad or your text editor, copy the URL for the Documents.docx file into the address bar of your browser and press **Enter**.</span></span> <span data-ttu-id="e1220-222">Sidan **åtkomst nekad** bör visas.</span><span class="sxs-lookup"><span data-stu-id="e1220-222">You should see an **Access Denied** page.</span></span>

7. <span data-ttu-id="e1220-223">Stäng **SharePoint** -fliken i webbläsaren, klicka på fliken **Microsoft Office start** , klicka på **användare 3** -namnet och klicka sedan på **Logga ut**.</span><span class="sxs-lookup"><span data-stu-id="e1220-223">Close the **SharePoint** tab in your browser, click the **Microsoft Office Home** tab, click the **User 3** name, and then click **Sign out**.</span></span>

<span data-ttu-id="e1220-224">Din SharePoint Online-webbplats är nu klar för dig.</span><span class="sxs-lookup"><span data-stu-id="e1220-224">Your isolated SharePoint Online site is now ready for your additional experimentation.</span></span>

## <a name="next-step"></a><span data-ttu-id="e1220-225">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="e1220-225">Next Step</span></span>

<span data-ttu-id="e1220-226">När du är redo att distribuera en isolerad SharePoint Online-gruppwebbplats i produktion kan du läsa de steg för steg-informationen om utformning i [Utforma en isolerad SharePoint Online-gruppwebbplats](design-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="e1220-226">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e1220-227">Se även</span><span class="sxs-lookup"><span data-stu-id="e1220-227">See Also</span></span>

[<span data-ttu-id="e1220-228">Isolerade SharePoint Online-gruppwebbplatser</span><span class="sxs-lookup"><span data-stu-id="e1220-228">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="e1220-229">Testlabbguider för integrering med molntjänster</span><span class="sxs-lookup"><span data-stu-id="e1220-229">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/cloud-adoption-test-lab-guides-tlgs)

[<span data-ttu-id="e1220-230">Baskonfiguration för simulerat företag</span><span class="sxs-lookup"><span data-stu-id="e1220-230">The simulated enterprise base configuration</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/simulated-ent-base-configuration-microsoft-365-enterprise)

[<span data-ttu-id="e1220-231">Den enkla baskonfigurationen</span><span class="sxs-lookup"><span data-stu-id="e1220-231">The lightweight base configuration</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise)

[<span data-ttu-id="e1220-232">Integrering av moln- och hybridlösningar</span><span class="sxs-lookup"><span data-stu-id="e1220-232">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
