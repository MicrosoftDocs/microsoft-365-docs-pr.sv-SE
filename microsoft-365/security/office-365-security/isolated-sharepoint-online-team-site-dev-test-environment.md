---
title: Utvecklings-/testmiljö för en isolerad resursgrupp online
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
description: 'Sammanfattning: Konfigurera en SharePoint Online-gruppwebbplats som är isolerad från resten av organisationen i microsoft 365-utvecklings-/testmiljön.'
ms.openlocfilehash: 07f3ae349f20fd4498e7809955cf0407d8c31d8c
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588034"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a><span data-ttu-id="033a8-103">Utvecklings-/testmiljö för en isolerad resursgrupp online</span><span class="sxs-lookup"><span data-stu-id="033a8-103">Isolated SharePoint Online team site dev/test environment</span></span>

 <span data-ttu-id="033a8-104">**Sammanfattning:** Konfigurera en SharePoint Online-gruppwebbplats som är isolerad från resten av organisationen i microsoft 365-utvecklings-/testmiljön.</span><span class="sxs-lookup"><span data-stu-id="033a8-104">**Summary:** Configure a SharePoint Online team site that is isolated from the rest of the organization in your Microsoft 365 dev/test environment.</span></span>

<span data-ttu-id="033a8-105">SharePoint Online-gruppwebbplatser i Microsoft 365 är platser för samarbete med hjälp av ett gemensamt dokumentbibliotek, en OneNote-anteckningsbok och andra tjänster.</span><span class="sxs-lookup"><span data-stu-id="033a8-105">SharePoint Online team sites in Microsoft 365 are locations for collaboration using a common document library, a OneNote notebook, and other services.</span></span> <span data-ttu-id="033a8-106">I många fall vill du ha bred åtkomst och samarbete mellan avdelningar eller organisationer.</span><span class="sxs-lookup"><span data-stu-id="033a8-106">In many cases, you want wide access and collaboration across departments or organizations.</span></span> <span data-ttu-id="033a8-107">Men i vissa fall vill du styra åtkomsten och behörigheterna för samarbete mellan en liten grupp personer.</span><span class="sxs-lookup"><span data-stu-id="033a8-107">However, in some cases, you want to tightly control the access and permissions for collaboration among a small group of people.</span></span>

<span data-ttu-id="033a8-108">Åtkomst till SharePoint Online-gruppwebbplatser och vad användarna kan göra styrs av SharePoint-grupper och behörighetsnivåer.</span><span class="sxs-lookup"><span data-stu-id="033a8-108">Access to SharePoint Online team sites and what users can do is controlled by SharePoint groups and permission levels.</span></span> <span data-ttu-id="033a8-109">Som standard har SharePoint Online-webbplatser tre åtkomstnivåer:</span><span class="sxs-lookup"><span data-stu-id="033a8-109">By default, SharePoint Online sites have three levels of access:</span></span>

- <span data-ttu-id="033a8-110">**Medlemmar**, som kan visa, skapa och ändra resurser på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="033a8-110">**Members**, who can view, create, and modify resources on the site.</span></span>

- <span data-ttu-id="033a8-111">**Ägare**, som har fullständig kontroll över webbplatsen, inklusive möjligheten att ändra behörigheter.</span><span class="sxs-lookup"><span data-stu-id="033a8-111">**Owners**, who have complete control of the site, including the ability to change permissions.</span></span>

- <span data-ttu-id="033a8-112">**Besökare**, som bara kan visa resurser på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="033a8-112">**Visitors**, who only can view resources on the site.</span></span>

<span data-ttu-id="033a8-113">I den här artikeln får du hjälp med konfigurationen av en isolerad SharePoint Online-gruppwebbplats för ett hemligt forskningsprojekt med namnet ProjectX.</span><span class="sxs-lookup"><span data-stu-id="033a8-113">This article steps you through the configuration of an isolated SharePoint Online team site for a secret research project named ProjectX.</span></span> <span data-ttu-id="033a8-114">Tillträdeskraven är:</span><span class="sxs-lookup"><span data-stu-id="033a8-114">The access requirements are:</span></span>

- <span data-ttu-id="033a8-115">Endast medlemmar i projektet kan komma åt webbplatsen och dess innehåll (dokument, OneNote Notebook, Pages), med redigerings- och visa SharePoint-behörighetsnivåer som styrs genom gruppmedlemskap.</span><span class="sxs-lookup"><span data-stu-id="033a8-115">Only members of the project can access the site and its contents (documents, OneNote Notebook, Pages), with edit and view SharePoint permission levels controlled through group membership.</span></span>

- <span data-ttu-id="033a8-116">Endast webbplatsskaparen och medlemmarna i en administratörsgrupp för webbplatsen kan utföra webbplatsadministration, vilket inkluderar ändring av behörigheter på webbplatsnivå.</span><span class="sxs-lookup"><span data-stu-id="033a8-116">Only the site creator and members of an Admins group for the site can perform site administration, which includes modifying site-level permissions.</span></span>

<span data-ttu-id="033a8-117">Det finns tre faser för att konfigurera en isolerad SharePoint Online-gruppwebbplats i microsoft 365-utvecklings-/testmiljön:</span><span class="sxs-lookup"><span data-stu-id="033a8-117">There are three phases to setting up an isolated SharePoint Online team site in your Microsoft 365 dev/test environment:</span></span>

1. <span data-ttu-id="033a8-118">Skapa utvecklings-/testmiljön för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="033a8-118">Create the Microsoft 365 dev/test environment.</span></span>

2. <span data-ttu-id="033a8-119">Skapa användare och grupper för ProjectX.</span><span class="sxs-lookup"><span data-stu-id="033a8-119">Create the users and groups for ProjectX.</span></span>

3. <span data-ttu-id="033a8-120">Skapa en ny ProjectX SharePoint Online-gruppwebbplats och isolera den.</span><span class="sxs-lookup"><span data-stu-id="033a8-120">Create a new ProjectX SharePoint Online team site and isolate it.</span></span>

> [!TIP]
> <span data-ttu-id="033a8-121">Klicka [här](https://aka.ms/catlgstack) om du vill ha en visuell karta till alla artiklar i One Microsoft Cloud Test Lab Guide-stacken.</span><span class="sxs-lookup"><span data-stu-id="033a8-121">Click [here](https://aka.ms/catlgstack) for a visual map to all the articles in the One Microsoft Cloud Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-microsoft-365-devtest-environment"></a><span data-ttu-id="033a8-122">Fas 1: Bygg ut din lätta eller simulerade företagsmiljö för Microsoft 365-utveckling/test</span><span class="sxs-lookup"><span data-stu-id="033a8-122">Phase 1: Build out your lightweight or simulated enterprise Microsoft 365 dev/test environment</span></span>

<span data-ttu-id="033a8-123">Om du bara vill skapa en isolerad SharePoint Online-gruppwebbplats på ett lättviktssätt med minimikraven följer du instruktionerna i faserna 2 och 3 i [Den lätta baskonfigurationen](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="033a8-123">If you just want to create an isolated SharePoint Online team site in a lightweight way with the minimum requirements, follow the instructions in phases 2 and 3 of [The lightweight base configuration](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).</span></span>

<span data-ttu-id="033a8-124">Om du vill skapa en isolerad SharePoint Online-gruppwebbplats i en simulerad företagskonfiguration följer du instruktionerna i synkronisering av [lösenordshöte för microsoft 365-testmiljön](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment).</span><span class="sxs-lookup"><span data-stu-id="033a8-124">If you want to create an isolated SharePoint Online team site in a simulated enterprise configuration, follow the instructions in [Password hash synchronization for your Microsoft 365 test environment](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment).</span></span>

> [!NOTE]
> <span data-ttu-id="033a8-125">För att skapa en isolerad SharePoint Online-webbplats krävs inte den simulerade företagsutvecklings-/testmiljön, som innehåller ett simulerat intranät som är anslutet till Internet och katalogsynkronisering för en AD DS-skog (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="033a8-125">Creating an isolated SharePoint Online site does not require the simulated enterprise dev/test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="033a8-126">Det finns här som ett alternativ så att du kan testa en isolerad SharePoint Online-webbplats och experimentera med den i en miljö som representerar en typisk organisation.</span><span class="sxs-lookup"><span data-stu-id="033a8-126">It is provided here as an option so that you can test an isolated SharePoint Online site and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-user-accounts-and-access-groups"></a><span data-ttu-id="033a8-127">Fas 2: Skapa användarkonton och åtkomstgrupper</span><span class="sxs-lookup"><span data-stu-id="033a8-127">Phase 2: Create user accounts and access groups</span></span>

<span data-ttu-id="033a8-128">Använd instruktionerna i [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) för att ansluta till din utvärderingsprenumeration med ditt globala administratörskonto från:</span><span class="sxs-lookup"><span data-stu-id="033a8-128">Use the instructions in [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) to connect to your trial subscription with your global administrator account from:</span></span>

- <span data-ttu-id="033a8-129">Datorn (för den lätta utvecklings-/testmiljön för Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="033a8-129">Your computer (for the lightweight Microsoft 365 dev/test environment).</span></span>

- <span data-ttu-id="033a8-130">Den virtuella klienten1-datorn (för det simulerade företaget Microsoft 365 dev/test-miljö).</span><span class="sxs-lookup"><span data-stu-id="033a8-130">The CLIENT1 virtual machine (for the simulated enterprise Microsoft 365 dev/test environment).</span></span>

<span data-ttu-id="033a8-131">Om du vill skapa de nya åtkomstgrupperna för ProjectX SharePoint Online-gruppwebbplatsen kör du dessa kommandon från Windows Azure Active Directory Module för Windows PowerShell-prompten:</span><span class="sxs-lookup"><span data-stu-id="033a8-131">To create the new access groups for the ProjectX SharePoint Online team site, run these commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

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

<span data-ttu-id="033a8-132">Fyll i organisationsnamnet (t.ex. contosotoycompany), landskoden med två tecken för din plats och kör sedan följande kommandon från Windows Azure Active Directory Module för Windows PowerShell-prompt:</span><span class="sxs-lookup"><span data-stu-id="033a8-132">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, and then run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$licAssignment= $orgName + ":ENTERPRISEPREMIUM"
$userName= "designer@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Designer" -FirstName Lead -LastName Designer -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="033a8-133">Från visningen av kommandot **New-MsolUser** noterar du det genererade lösenordet för Lead Designer-kontot och spelar in det på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="033a8-133">From the display of the **New-MsolUser** command, note the generated password for the Lead Designer account and record it in a safe location.</span></span>

<span data-ttu-id="033a8-134">Kör följande kommandon från Windows Azure Active Directory Module för Windows PowerShell-prompt:</span><span class="sxs-lookup"><span data-stu-id="033a8-134">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="033a8-135">Från visningen av kommandot **New-MsolUser** noterar du det genererade lösenordet för kontot leda forskare och registrera det på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="033a8-135">From the display of the **New-MsolUser** command, note the generated password for the Lead Researcher account and record it in a safe location.</span></span>

<span data-ttu-id="033a8-136">Kör följande kommandon från Windows Azure Active Directory Module för Windows PowerShell-prompt:</span><span class="sxs-lookup"><span data-stu-id="033a8-136">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="033a8-137">Från visningen av kommandot **New-MsolUser** noterar du det genererade lösenordet för utvecklings-VP-kontot och registrerar det på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="033a8-137">From the display of the **New-MsolUser** command, note the generated password for the Development VP account and record it in a safe location.</span></span>

<span data-ttu-id="033a8-138">Om du vill lägga till de nya kontona i de nya åtkomstgrupperna kör du dessa PowerShell-kommandon från Windows Azure Active Directory Module för Windows PowerShell-prompt:</span><span class="sxs-lookup"><span data-stu-id="033a8-138">Next, to add the new accounts to the new access groups, run these PowerShell commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

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

<span data-ttu-id="033a8-139">Resultat:</span><span class="sxs-lookup"><span data-stu-id="033a8-139">Results:</span></span>

- <span data-ttu-id="033a8-140">Åtkomstgruppen ProjectX-medlemmar innehåller användarkontona Lead Designer och Lead Researcher</span><span class="sxs-lookup"><span data-stu-id="033a8-140">The ProjectX-Members access group contains the Lead Designer and Lead Researcher user accounts</span></span>

- <span data-ttu-id="033a8-141">Åtkomstgruppen ProjectX-Admins innehåller det globala administratörskontot för din utvärderingsprenumeration</span><span class="sxs-lookup"><span data-stu-id="033a8-141">The ProjectX-Admins access group contains the global administrator account for your trial subscription</span></span>

- <span data-ttu-id="033a8-142">Åtkomstgruppen ProjectX-Viewers innehåller användarkontot För utvecklingsvp</span><span class="sxs-lookup"><span data-stu-id="033a8-142">The ProjectX-Viewers access group contains the Development VP user account</span></span>

<span data-ttu-id="033a8-143">Figur 1 visar åtkomstgrupperna och deras medlemskap.</span><span class="sxs-lookup"><span data-stu-id="033a8-143">Figure 1 shows the access groups and their membership.</span></span>

<span data-ttu-id="033a8-144">**Bild 1**</span><span class="sxs-lookup"><span data-stu-id="033a8-144">**Figure 1**</span></span>

![Microsoft 365-grupperna och deras medlemskap för en isolerad SharePoint Online Group-webbplats](../../media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)

## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a><span data-ttu-id="033a8-146">Fas 3: Skapa en ny ProjectX SharePoint Online-gruppwebbplats och isolera den</span><span class="sxs-lookup"><span data-stu-id="033a8-146">Phase 3: Create a new ProjectX SharePoint Online team site and isolate it</span></span>

<span data-ttu-id="033a8-147">Så här skapar du en SharePoint Online-gruppwebbplats för ProjectX:</span><span class="sxs-lookup"><span data-stu-id="033a8-147">To create a SharePoint Online team site for ProjectX, do the following:</span></span>

1. <span data-ttu-id="033a8-148">Logga in i Microsoft 365-administrationscentret ( microsoft 365 med hjälp av en webbläsare på din lokala dator (lättkonfiguration) eller på KLIENT1 (simulerad företagskonfiguration) [https://admin.microsoft.com](https://admin.microsoft.com) med hjälp av ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="033a8-148">Using a browser on either your local computer (lightweight configuration) or on CLIENT1 (simulated enterprise configuration), sign in to the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>

2. <span data-ttu-id="033a8-149">Klicka på **SharePoint** i listan med paneler.</span><span class="sxs-lookup"><span data-stu-id="033a8-149">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="033a8-150">På den nya fliken SharePoint i webbläsaren klickar du på **+ Skapa webbplats**.</span><span class="sxs-lookup"><span data-stu-id="033a8-150">On the new SharePoint tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="033a8-151">Skriv **ProjectX** **i Gruppplatsnamn**.</span><span class="sxs-lookup"><span data-stu-id="033a8-151">In **Team site name**, type **ProjectX**.</span></span> <span data-ttu-id="033a8-152">I **Sekretessinställningar**väljer du **Privat - endast medlemmar kan komma åt den här webbplatsen**.</span><span class="sxs-lookup"><span data-stu-id="033a8-152">In **Privacy settings**, select **Private - only members can access this site**.</span></span>

5. <span data-ttu-id="033a8-153">Skriv **SharePoint-webbplats för ProjectX i** **Gruppplatsbeskrivning**och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="033a8-153">In **Team site description**, type **SharePoint site for ProjectX**, and then click **Next**.</span></span>

6. <span data-ttu-id="033a8-154">På vem **vill du lägga till?** klickar du på **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="033a8-154">On the **Who do you want to add**? pane, click **Finish**.</span></span>

7. <span data-ttu-id="033a8-155">Klicka på inställningsikonen i verktygsfältet på den nya fliken **ProjectX-Start** i webbläsaren och klicka sedan på **Webbplatsbehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="033a8-155">On the new **ProjectX-Home** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

8. <span data-ttu-id="033a8-156">I fönstret **Webbplatsbehörigheter** klickar du på **Inställningar för avancerade behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="033a8-156">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

9. <span data-ttu-id="033a8-157">Klicka på **Inställningar för åtkomstbegäran**i den nya **behörigheten: Project X** i webbläsaren .</span><span class="sxs-lookup"><span data-stu-id="033a8-157">In the new **Permissions: Project X** tab in your browser, click **Access Request Settings**.</span></span>

10. <span data-ttu-id="033a8-158">I dialogrutan **Inställningar för åtkomstbegäranden** avmarkerar du **Tillåt medlemmar att dela webbplatsen och enskilda filer och mappar** och tillåt **åtkomstbegäranden** (så att alla tre kryssrutorna är avmarkerade) och klickar sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="033a8-158">In the **Access Requests Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow access requests** (so that all three check boxes are cleared), and then click **OK**.</span></span>

11. <span data-ttu-id="033a8-159">Klicka på **ProjectX-medlemmar** i listan.</span><span class="sxs-lookup"><span data-stu-id="033a8-159">Click **ProjectX Members** in the list.</span></span>

12. <span data-ttu-id="033a8-160">På sidan **Personer och grupper** klickar du på **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="033a8-160">On the **People and Groups** page, click **New**.</span></span>

13. <span data-ttu-id="033a8-161">Skriv **ProjectX-medlemmar**i dialogrutan **Dela** , markera det och klicka sedan på **Dela**.</span><span class="sxs-lookup"><span data-stu-id="033a8-161">In the **Share** dialog box, type **ProjectX-Members**, select it, and then click **Share**.</span></span>

14. <span data-ttu-id="033a8-162">Klicka på bakåtknappen i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="033a8-162">Click the back button on your browser.</span></span>

15. <span data-ttu-id="033a8-163">Klicka på **ProjectX-ägare** i listan.</span><span class="sxs-lookup"><span data-stu-id="033a8-163">Click **ProjectX Owners** in the list.</span></span>

16. <span data-ttu-id="033a8-164">På sidan **Personer och grupper** klickar du på **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="033a8-164">On the **People and Groups** page, click **New**.</span></span>

17. <span data-ttu-id="033a8-165">Skriv **ProjectX-Administratörer**i dialogrutan **Dela** , markera det och klicka sedan på **Dela**.</span><span class="sxs-lookup"><span data-stu-id="033a8-165">In the **Share** dialog box, type **ProjectX-Admins**, select it, and then click **Share**.</span></span>

18. <span data-ttu-id="033a8-166">Klicka på bakåtknappen i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="033a8-166">Click the back button on your browser.</span></span>

19. <span data-ttu-id="033a8-167">Klicka på **ProjectX-besökare** i listan.</span><span class="sxs-lookup"><span data-stu-id="033a8-167">Click **ProjectX Visitors** in the list.</span></span>

20. <span data-ttu-id="033a8-168">På sidan **Personer och grupper** klickar du på **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="033a8-168">On the **People and Groups** page, click **New**.</span></span>

21. <span data-ttu-id="033a8-169">Skriv **ProjectX-Tittare**i dialogrutan **Dela** , markera det och klicka sedan på **Dela**.</span><span class="sxs-lookup"><span data-stu-id="033a8-169">In the **Share** dialog box, type **ProjectX-Viewers**, select it, and then click **Share**.</span></span>

22. <span data-ttu-id="033a8-170">Stäng fliken **Personer och grupper** i webbläsaren, klicka på fliken **ProjectX-Start** i webbläsaren och stäng sedan fönstret **Webbplatsbehörigheter.**</span><span class="sxs-lookup"><span data-stu-id="033a8-170">Close the **People and Groups** tab in your browser, click the **ProjectX-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="033a8-171">Här är resultatet av att konfigurera behörigheter:</span><span class="sxs-lookup"><span data-stu-id="033a8-171">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="033a8-172">Gruppen ProjectX-medlemmars SharePoint innehåller endast åtkomstgruppen ProjectX-medlemmar (som endast innehåller användarkontona lead designer och lead forskare) och ProjectX-gruppen (som endast innehåller det globala administratörsanvändarkontot).</span><span class="sxs-lookup"><span data-stu-id="033a8-172">The ProjectX Members SharePoint group contains only the ProjectX-Members access group (which contains only the Lead Designer and Lead Researcher user accounts) and the ProjectX group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="033a8-173">Gruppen ProjectX-ägares SharePoint innehåller endast åtkomstgruppen ProjectX-Admins (som bara innehåller det globala administratörsanvändarkontot).</span><span class="sxs-lookup"><span data-stu-id="033a8-173">The ProjectX Owners SharePoint group contains only the ProjectX-Admins access group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="033a8-174">Gruppen ProjectX-besökares SharePoint innehåller endast åtkomstgruppen ProjectX-Tittare (som bara innehåller användarkontot För utveckling vp).</span><span class="sxs-lookup"><span data-stu-id="033a8-174">The ProjectX Visitors SharePoint group contains only the ProjectX-Viewers access group (which contains only the Development VP user account).</span></span>

- <span data-ttu-id="033a8-175">Medlemmar kan inte ändra behörigheter på webbplatsnivå (detta kan endast göras av medlemmar i gruppen ProjectX-Administratörer).</span><span class="sxs-lookup"><span data-stu-id="033a8-175">Members cannot modify site-level permissions (this can only be done by members of the ProjectX-Admins group).</span></span>

- <span data-ttu-id="033a8-176">Andra användarkonton kan inte komma åt webbplatsen eller dess resurser. De kan inte heller begära åtkomst till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="033a8-176">Other user accounts cannot access the site or its resources or request access to the site.</span></span>

<span data-ttu-id="033a8-177">Figur 2 visar SharePoint-grupperna och deras medlemskap.</span><span class="sxs-lookup"><span data-stu-id="033a8-177">Figure 2 shows the SharePoint groups and their membership.</span></span>

<span data-ttu-id="033a8-178">**Bild 2**</span><span class="sxs-lookup"><span data-stu-id="033a8-178">**Figure 2**</span></span>

![SharePoint Online-grupperna och deras medlemskap för en isolerad SharePoint Online Group-webbplats](../../media/595abff4-64f9-49de-a37a-c70c6856936b.png)

<span data-ttu-id="033a8-180">Nu ska vi visa åtkomst med hjälp av Lead Designer-användarkontot:</span><span class="sxs-lookup"><span data-stu-id="033a8-180">Now let's demonstrate access using the Lead Designer user account:</span></span>

1. <span data-ttu-id="033a8-181">Stäng fliken **ProjectX-Start** i webbläsaren och klicka sedan på fliken **Start i Microsoft Office** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="033a8-181">Close the **ProjectX-Home** tab in your browser, and then click the **Microsoft Office Home** tab in your browser.</span></span>

2. <span data-ttu-id="033a8-182">Klicka på namnet på den globala administratören och klicka sedan på **Logga ut**.</span><span class="sxs-lookup"><span data-stu-id="033a8-182">Click the name of your global administrator, and then click **Sign out**.</span></span>

3. <span data-ttu-id="033a8-183">Logga in på Microsoft 365 administrationscenter ( [https://admin.microsoft.com](https://admin.microsoft.com) ) med lead designer-kontonamnet och dess lösenord.</span><span class="sxs-lookup"><span data-stu-id="033a8-183">Sign in to the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using the Lead Designer account name and its password.</span></span>

4. <span data-ttu-id="033a8-184">Klicka på **SharePoint** i listan med paneler.</span><span class="sxs-lookup"><span data-stu-id="033a8-184">In the list of tiles, click **SharePoint**.</span></span>

5. <span data-ttu-id="033a8-185">På den nya **fliken SharePoint** i webbläsaren skriver du **ProjectX** i sökrutan, aktiverar sökningen och klickar sedan på ProjectX-gruppwebbplatsen. **ProjectX**</span><span class="sxs-lookup"><span data-stu-id="033a8-185">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site.</span></span> <span data-ttu-id="033a8-186">Du bör se en ny flik i webbläsaren för ProjectX-gruppwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="033a8-186">You should see a new tab in your browser for the ProjectX team site.</span></span>

6. <span data-ttu-id="033a8-187">Klicka på inställningsikonen.</span><span class="sxs-lookup"><span data-stu-id="033a8-187">Click the settings icon.</span></span> <span data-ttu-id="033a8-188">Observera att det inte finns något alternativ för **webbplatsbehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="033a8-188">Notice that there is no option for **Site Permissions**.</span></span> <span data-ttu-id="033a8-189">Detta är korrekt eftersom endast medlemmarna i gruppen ProjectX-administratörer kan ändra behörigheter på webbplatsen</span><span class="sxs-lookup"><span data-stu-id="033a8-189">This is correct because only the members of the ProjectX-Admins group can modify permissions on the site</span></span>

7. <span data-ttu-id="033a8-190">Öppna Anteckningar eller en textredigerare som du väljer.</span><span class="sxs-lookup"><span data-stu-id="033a8-190">Open Notepad or a text editor of your choice.</span></span>

8. <span data-ttu-id="033a8-191">Kopiera URL:en för ProjectX-gruppwebbplatsen och klistra in den på en ny rad i Anteckningar eller textredigeraren.</span><span class="sxs-lookup"><span data-stu-id="033a8-191">Copy the URL of the ProjectX team site and paste it on a new line in Notepad or your text editor.</span></span>

9. <span data-ttu-id="033a8-192">Klicka på **Dokument**på den nya fliken **ProjectX-Start** i webbläsaren .</span><span class="sxs-lookup"><span data-stu-id="033a8-192">On the new **ProjectX-Home** tab in your browser, click **Documents**.</span></span>

10. <span data-ttu-id="033a8-193">Kopiera URL:en för mappen ProjectX-dokument och klistra in den på en ny rad i Anteckningar eller textredigeraren.</span><span class="sxs-lookup"><span data-stu-id="033a8-193">Copy the URL of the ProjectX documents folder and paste it on a new line in Notepad or your text editor.</span></span>

11. <span data-ttu-id="033a8-194">Klicka på **Nytt > Word-dokument**på fliken **Nya ProjektX-dokument** i webbläsaren .</span><span class="sxs-lookup"><span data-stu-id="033a8-194">On the new **ProjectX-Documents** tab in your browser, click **New > Word document**.</span></span>

12. <span data-ttu-id="033a8-195">Skriv text på sidan, vänta tills statusen visas **Sparad,** klicka på bakåtknappen i webbläsaren och uppdatera sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="033a8-195">Type some text on the page, wait for the status to indicate **Saved**, click the back button on your browser, and then refresh the page.</span></span> <span data-ttu-id="033a8-196">Du bör se ett nytt **Document.docx** i mappen **Dokument.**</span><span class="sxs-lookup"><span data-stu-id="033a8-196">You should see a new **Document.docx** in the **Documents** folder.</span></span>

13. <span data-ttu-id="033a8-197">Klicka på ellipsen för **Document.docx-dokumentet** och klicka sedan på **Hämta en länk**.</span><span class="sxs-lookup"><span data-stu-id="033a8-197">Click the ellipsis for the **Document.docx** document, and then click **Get a link**.</span></span>

14. <span data-ttu-id="033a8-198">Kopiera webbadressen i dialogrutan **Dela "Document.docx"** och klistra in den på en ny rad i Anteckningar eller textredigeraren och stäng sedan dialogrutan **Dela "Document.docx".**</span><span class="sxs-lookup"><span data-stu-id="033a8-198">Copy the URL in the **Share 'Document.docx'** dialog box and paste it on a new line in Notepad or your text editor, and then close the **Share 'Document.docx'** dialog box.</span></span>

15. <span data-ttu-id="033a8-199">Stäng **flikarna ProjectX-dokument** och **SharePoint** i webbläsaren och klicka sedan på fliken **Start i Microsoft Office.**</span><span class="sxs-lookup"><span data-stu-id="033a8-199">Close the **ProjectX-Documents** and **SharePoint** tabs in your browser, and then click the **Microsoft Office Home** tab.</span></span>

16. <span data-ttu-id="033a8-200">Klicka på **leaddesignerns** namn och klicka sedan på **Logga ut**.</span><span class="sxs-lookup"><span data-stu-id="033a8-200">Click the **Lead Designer** name, and then click **Sign out**.</span></span>

<span data-ttu-id="033a8-201">Nu ska vi visa åtkomst med hjälp av utvecklings-VP-användarkontot:</span><span class="sxs-lookup"><span data-stu-id="033a8-201">Now let's demonstrate access using the Development VP user account:</span></span>

1. <span data-ttu-id="033a8-202">Logga in på Microsoft 365 administrationscenter ( [https://admin.microsoft.com](https://admin.microsoft.com) ) med hjälp av utvecklings-VP-kontonamnet och dess lösenord.</span><span class="sxs-lookup"><span data-stu-id="033a8-202">Sign in to the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using the Development VP account name and its password.</span></span>

2. <span data-ttu-id="033a8-203">Klicka på **SharePoint** i listan med paneler.</span><span class="sxs-lookup"><span data-stu-id="033a8-203">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="033a8-204">På den nya **fliken SharePoint** i webbläsaren skriver du **ProjectX** i sökrutan, aktiverar sökningen och klickar sedan på ProjectX-gruppwebbplatsen. **ProjectX**</span><span class="sxs-lookup"><span data-stu-id="033a8-204">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site.</span></span> <span data-ttu-id="033a8-205">Du bör se en ny flik i webbläsaren för ProjectX-gruppwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="033a8-205">You should see a new tab in your browser for the ProjectX team site.</span></span>

4. <span data-ttu-id="033a8-206">Klicka på **Dokument**och sedan på **filen Document.docx.**</span><span class="sxs-lookup"><span data-stu-id="033a8-206">Click **Documents**, and then click the **Document.docx** file.</span></span>

5. <span data-ttu-id="033a8-207">Försök att ändra texten på fliken **Document.docx** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="033a8-207">In the **Document.docx** tab in your browser, try to modify the text.</span></span> <span data-ttu-id="033a8-208">Du bör se ett meddelande om att **det här dokumentet är skrivskyddat.**</span><span class="sxs-lookup"><span data-stu-id="033a8-208">You should see a message stating **This document is read-only.**</span></span> <span data-ttu-id="033a8-209">Detta förväntas eftersom användarkontot för utvecklingsvp endast har visningsbehörighet för webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="033a8-209">This is expected because the Development VP user account only has view permissions for the site.</span></span>

6. <span data-ttu-id="033a8-210">Stäng flikarna **Document.docx,** **ProjectX-Documents**och **SharePoint** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="033a8-210">Close the **Document.docx**, **ProjectX-Documents**, and **SharePoint** tabs in your browser.</span></span>

7. <span data-ttu-id="033a8-211">Klicka på fliken **Start i Microsoft Office,** klicka på namnet **utveckling vp** och klicka sedan på **Logga ut**.</span><span class="sxs-lookup"><span data-stu-id="033a8-211">Click the **Microsoft Office Home** tab, click the **Development VP** name, and then click **Sign out**.</span></span>

<span data-ttu-id="033a8-212">Nu ska vi visa åtkomst med ett användarkonto som inte har några behörigheter:</span><span class="sxs-lookup"><span data-stu-id="033a8-212">Now let's demonstrate access with a user account that has no permissions:</span></span>

1. <span data-ttu-id="033a8-213">Logga in på Microsoft 365 administrationscenter ( [https://admin.microsoft.com](https://admin.microsoft.com) ) med användar3-kontonamnet och dess lösenord.</span><span class="sxs-lookup"><span data-stu-id="033a8-213">Sign in to the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) using the User 3 account name and its password.</span></span>

2. <span data-ttu-id="033a8-214">Klicka på **SharePoint** i listan med paneler.</span><span class="sxs-lookup"><span data-stu-id="033a8-214">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="033a8-215">På den nya **fliken SharePoint** i webbläsaren skriver du **ProjectX** i sökrutan och aktiverar sedan sökningen.</span><span class="sxs-lookup"><span data-stu-id="033a8-215">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box and then activate the search.</span></span> <span data-ttu-id="033a8-216">Du bör se meddelandet **Ingenting här matchar din sökning.**</span><span class="sxs-lookup"><span data-stu-id="033a8-216">You should see the message **Nothing here matches your search.**</span></span>

4. <span data-ttu-id="033a8-217">Kopiera URL:en för ProjectX-webbplatsen till webbläsarens adressfält från den öppna förekomsten av Anteckningar eller textredigeraren och tryck på **Retur**.</span><span class="sxs-lookup"><span data-stu-id="033a8-217">From the open instance of Notepad or your text editor, copy the URL for the ProjectX site into the address bar of your browser and press **Enter**.</span></span> <span data-ttu-id="033a8-218">Du bör se en **åtkomst nekad** sida.</span><span class="sxs-lookup"><span data-stu-id="033a8-218">You should see an **Access Denied** page.</span></span>

5. <span data-ttu-id="033a8-219">Kopiera URL:en för mappen ProjectX-dokument i webbläsarens adressfält från Anteckningar eller textredigeraren och tryck på **Retur**.</span><span class="sxs-lookup"><span data-stu-id="033a8-219">From Notepad or your text editor, copy the URL for the ProjectX Documents folder into the address bar of your browser and press **Enter**.</span></span> <span data-ttu-id="033a8-220">Du bör se en **åtkomst nekad** sida.</span><span class="sxs-lookup"><span data-stu-id="033a8-220">You should see an **Access Denied** page.</span></span>

6. <span data-ttu-id="033a8-221">Kopiera URL:en för filen Documents.docx i webbläsarens adressfält från Anteckningar eller textredigeraren och tryck på **Retur**.</span><span class="sxs-lookup"><span data-stu-id="033a8-221">From Notepad or your text editor, copy the URL for the Documents.docx file into the address bar of your browser and press **Enter**.</span></span> <span data-ttu-id="033a8-222">Du bör se en **åtkomst nekad** sida.</span><span class="sxs-lookup"><span data-stu-id="033a8-222">You should see an **Access Denied** page.</span></span>

7. <span data-ttu-id="033a8-223">Stäng **fliken SharePoint** i webbläsaren, klicka på fliken **Start för Microsoft Office,** klicka på **namnet Användare 3** och klicka sedan på **Logga ut**.</span><span class="sxs-lookup"><span data-stu-id="033a8-223">Close the **SharePoint** tab in your browser, click the **Microsoft Office Home** tab, click the **User 3** name, and then click **Sign out**.</span></span>

<span data-ttu-id="033a8-224">Din isolerade SharePoint Online-webbplats är nu klar för ytterligare experiment.</span><span class="sxs-lookup"><span data-stu-id="033a8-224">Your isolated SharePoint Online site is now ready for your additional experimentation.</span></span>

## <a name="next-step"></a><span data-ttu-id="033a8-225">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="033a8-225">Next Step</span></span>

<span data-ttu-id="033a8-226">När du är redo att distribuera en isolerad SharePoint Online-gruppwebbplats i produktion kan du läsa de steg för steg-informationen om utformning i [Utforma en isolerad SharePoint Online-gruppwebbplats](design-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="033a8-226">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="033a8-227">Se även</span><span class="sxs-lookup"><span data-stu-id="033a8-227">See Also</span></span>

[<span data-ttu-id="033a8-228">Isolerade SharePoint Online-gruppwebbplatser</span><span class="sxs-lookup"><span data-stu-id="033a8-228">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="033a8-229">Testlabbguider för integrering med molntjänster</span><span class="sxs-lookup"><span data-stu-id="033a8-229">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)

[<span data-ttu-id="033a8-230">Baskonfiguration för simulerat företag</span><span class="sxs-lookup"><span data-stu-id="033a8-230">The simulated enterprise base configuration</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/simulated-ent-base-configuration-microsoft-365-enterprise)

[<span data-ttu-id="033a8-231">Den enkla baskonfigurationen</span><span class="sxs-lookup"><span data-stu-id="033a8-231">The lightweight base configuration</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise)

[<span data-ttu-id="033a8-232">Integrering av moln- och hybridlösningar</span><span class="sxs-lookup"><span data-stu-id="033a8-232">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
