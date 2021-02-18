---
title: Isolerad utvecklings-/testmiljö för SharePoint Online-gruppwebbplats
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
- TLG
- Ent_TLGs
ms.assetid: d1795031-beef-49ea-a6fc-5da5450d320d
description: 'Sammanfattning: Konfigurera en SharePoint Online-gruppwebbplats som isoleras från resten av organisationen i utvecklings-/testmiljön för Microsoft 365.'
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 103ba1ddb2b5123db80be91f40c4fce8c6e2eb3d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286615"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a><span data-ttu-id="8af53-103">Isolerad utvecklings-/testmiljö för SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="8af53-103">Isolated SharePoint Online team site dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8af53-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="8af53-104">**Applies to**</span></span>
- [<span data-ttu-id="8af53-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8af53-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="8af53-106">Microsoft Defender för Office 365 abonnemang 1</span><span class="sxs-lookup"><span data-stu-id="8af53-106">Microsoft Defender for Office 365 plan 1</span></span>](office-365-atp.md)
- <span data-ttu-id="8af53-107">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8af53-107">SharePoint Online</span></span> 


 <span data-ttu-id="8af53-108">**Sammanfattning:** Konfigurera en SharePoint Online-gruppwebbplats som isoleras från resten av organisationen i utvecklings-/testmiljön för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8af53-108">**Summary:** Configure a SharePoint Online team site that is isolated from the rest of the organization in your Microsoft 365 dev/test environment.</span></span>

<span data-ttu-id="8af53-109">SharePoint Online-gruppwebbplatser i Microsoft 365 är platser för samarbete med hjälp av ett gemensamt dokumentbibliotek, en OneNote-anteckningsbok och andra tjänster.</span><span class="sxs-lookup"><span data-stu-id="8af53-109">SharePoint Online team sites in Microsoft 365 are locations for collaboration using a common document library, a OneNote notebook, and other services.</span></span> <span data-ttu-id="8af53-110">I många fall vill du ha bred åtkomst och samarbete mellan avdelningar eller organisationer.</span><span class="sxs-lookup"><span data-stu-id="8af53-110">In many cases, you want wide access and collaboration across departments or organizations.</span></span> <span data-ttu-id="8af53-111">Men i vissa fall vill du ha nära kontroll över åtkomst och behörighet för samarbete mellan en liten grupp personer.</span><span class="sxs-lookup"><span data-stu-id="8af53-111">However, in some cases, you want to tightly control the access and permissions for collaboration among a small group of people.</span></span>

<span data-ttu-id="8af53-112">Åtkomsten till SharePoint Online-gruppwebbplatser och vad användarna kan göra styrs av SharePoint-grupper och behörighetsnivåer.</span><span class="sxs-lookup"><span data-stu-id="8af53-112">Access to SharePoint Online team sites and what users can do is controlled by SharePoint groups and permission levels.</span></span> <span data-ttu-id="8af53-113">Som standard har SharePoint Online-webbplatser tre åtkomstnivåer:</span><span class="sxs-lookup"><span data-stu-id="8af53-113">By default, SharePoint Online sites have three levels of access:</span></span>

- <span data-ttu-id="8af53-114">**Medlemmar,** som kan visa, skapa och ändra resurser på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="8af53-114">**Members**, who can view, create, and modify resources on the site.</span></span>
- <span data-ttu-id="8af53-115">**Ägare,** som har fullständig kontroll över webbplatsen, inklusive möjligheten att ändra behörigheter.</span><span class="sxs-lookup"><span data-stu-id="8af53-115">**Owners**, who have complete control of the site, including the ability to change permissions.</span></span>
- <span data-ttu-id="8af53-116">**Besökare,** som bara kan visa resurser på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="8af53-116">**Visitors**, who only can view resources on the site.</span></span>

<span data-ttu-id="8af53-117">Den här artikeln beskriver hur du kan konfigurera en isolerad SharePoint Online-gruppwebbplats för ett hemligt forskningsprojekt med namnet ProjectX.</span><span class="sxs-lookup"><span data-stu-id="8af53-117">This article steps you through the configuration of an isolated SharePoint Online team site for a secret research project named ProjectX.</span></span> <span data-ttu-id="8af53-118">Åtkomstkraven är:</span><span class="sxs-lookup"><span data-stu-id="8af53-118">The access requirements are:</span></span>

- <span data-ttu-id="8af53-119">Endast medlemmar i projektet kan komma åt webbplatsen och dess innehåll (dokument, OneNote-anteckningsbok, sidor), med behörighetsnivåer för redigering och visning av SharePoint som styrs av gruppmedlemskap.</span><span class="sxs-lookup"><span data-stu-id="8af53-119">Only members of the project can access the site and its contents (documents, OneNote Notebook, Pages), with edit and view SharePoint permission levels controlled through group membership.</span></span>

- <span data-ttu-id="8af53-120">Endast webbplatsskaparen och medlemmar i en administratörsgrupp för webbplatsen kan utföra webbplatsadministration, vilket omfattar att ändra behörigheter på webbplatsnivå.</span><span class="sxs-lookup"><span data-stu-id="8af53-120">Only the site creator and members of an Admins group for the site can perform site administration, which includes modifying site-level permissions.</span></span>

<span data-ttu-id="8af53-121">Det finns tre faser för att konfigurera en isolerad SharePoint Online-gruppwebbplats i utvecklings-/testmiljön för Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="8af53-121">There are three phases to setting up an isolated SharePoint Online team site in your Microsoft 365 dev/test environment:</span></span>

1. <span data-ttu-id="8af53-122">Skapa utvecklings-/testmiljön för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8af53-122">Create the Microsoft 365 dev/test environment.</span></span>

2. <span data-ttu-id="8af53-123">Skapa användare och grupper för ProjectX.</span><span class="sxs-lookup"><span data-stu-id="8af53-123">Create the users and groups for ProjectX.</span></span>

3. <span data-ttu-id="8af53-124">Skapa en ny ProjectX SharePoint Online-gruppwebbplats och isolera den.</span><span class="sxs-lookup"><span data-stu-id="8af53-124">Create a new ProjectX SharePoint Online team site and isolate it.</span></span>

> [!TIP]
> <span data-ttu-id="8af53-125">Klicka [här](https://aka.ms/catlgstack) för en visuell karta till alla artiklar i en Microsoft Cloud Test Lab Guide-stack.</span><span class="sxs-lookup"><span data-stu-id="8af53-125">Click [here](https://aka.ms/catlgstack) for a visual map to all the articles in the One Microsoft Cloud Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-microsoft-365-devtest-environment"></a><span data-ttu-id="8af53-126">Fas 1: Bygg ut din lättaste eller simulerade utvecklings-/testmiljö för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8af53-126">Phase 1: Build out your lightweight or simulated enterprise Microsoft 365 dev/test environment</span></span>

<span data-ttu-id="8af53-127">Om du bara vill skapa en isolerad SharePoint Online-gruppwebbplats på ett lätt sätt med minimikraven följer du anvisningarna i fas 2 och 3 i den lätta [grundkonfigurationen.](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="8af53-127">If you just want to create an isolated SharePoint Online team site in a lightweight way with the minimum requirements, follow the instructions in phases 2 and 3 of [The lightweight base configuration](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>

<span data-ttu-id="8af53-128">Om du vill skapa en isolerad SharePoint Online-gruppwebbplats i en simulerad företagskonfiguration följer du anvisningarna i synkronisering av lösenordshashar för [Microsoft 365-testmiljön.](../../enterprise/password-hash-sync-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="8af53-128">If you want to create an isolated SharePoint Online team site in a simulated enterprise configuration, follow the instructions in [Password hash synchronization for your Microsoft 365 test environment](../../enterprise/password-hash-sync-m365-ent-test-environment.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8af53-129">Om du skapar en isolerad SharePoint Online-webbplats krävs inte den simulerade utvecklings-/testmiljön för företag, vilket omfattar en simulerad intranätanslutning till Internet och katalogsynkronisering för en Active Directory DS-skog (AD DS).</span><span class="sxs-lookup"><span data-stu-id="8af53-129">Creating an isolated SharePoint Online site does not require the simulated enterprise dev/test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="8af53-130">Här finns ett alternativ för att testa en isolerad SharePoint Online-webbplats och experimentera med den i en miljö som representerar en vanlig organisation.</span><span class="sxs-lookup"><span data-stu-id="8af53-130">It is provided here as an option so that you can test an isolated SharePoint Online site and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-user-accounts-and-access-groups"></a><span data-ttu-id="8af53-131">Steg 2: Skapa användarkonton och komma åt grupper</span><span class="sxs-lookup"><span data-stu-id="8af53-131">Phase 2: Create user accounts and access groups</span></span>

<span data-ttu-id="8af53-132">Följ anvisningarna i [Ansluta till Office 365 PowerShell för](../../enterprise/connect-to-microsoft-365-powershell.md) att ansluta till utvärderingsprenumerationen med ditt globala administratörskonto från:</span><span class="sxs-lookup"><span data-stu-id="8af53-132">Use the instructions in [Connect to Office 365 PowerShell](../../enterprise/connect-to-microsoft-365-powershell.md) to connect to your trial subscription with your global administrator account from:</span></span>

- <span data-ttu-id="8af53-133">Din dator (för den lätta utvecklings-/testmiljön för Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="8af53-133">Your computer (for the lightweight Microsoft 365 dev/test environment).</span></span>

- <span data-ttu-id="8af53-134">Den virtuella KLIENT1-datorn (för det simulerade företagets utvecklings-/testmiljö för Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="8af53-134">The CLIENT1 virtual machine (for the simulated enterprise Microsoft 365 dev/test environment).</span></span>

<span data-ttu-id="8af53-135">Skapa de nya åtkomstgrupperna för ProjectX SharePoint Online-gruppwebbplatsen genom att köra följande kommandon från kommandotolken för Windows Azure Active Directory-modulen för Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8af53-135">To create the new access groups for the ProjectX SharePoint Online team site, run these commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

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

<span data-ttu-id="8af53-136">Fyll i ditt organisationsnamn (exempel: contosotoycompany), landskoden för de två tecken som finns på din plats och kör sedan följande kommandon från kommandotolken för Windows Azure Active Directory-modulen för Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8af53-136">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, and then run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$licAssignment= $orgName + ":ENTERPRISEPREMIUM"
$userName= "designer@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Designer" -FirstName Lead -LastName Designer -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="8af53-137">Notera det genererade lösenordet för Lead Designer-kontot från visningen av kommandot **New-MsolUser** och registrera det på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="8af53-137">From the display of the **New-MsolUser** command, note the generated password for the Lead Designer account and record it in a safe location.</span></span>

<span data-ttu-id="8af53-138">Kör följande kommandon från uppmaningen Windows Azure Active Directory-modul för Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8af53-138">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="8af53-139">Notera det genererade lösenordet för lead researcher-kontot från visningen av kommandot **New-MsolUser** och registrera det på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="8af53-139">From the display of the **New-MsolUser** command, note the generated password for the Lead Researcher account and record it in a safe location.</span></span>

<span data-ttu-id="8af53-140">Kör följande kommandon från uppmaningen Windows Azure Active Directory-modul för Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8af53-140">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="8af53-141">Notera det genererade lösenordet för Development VP-kontot från visningen av **kommandot New-MsolUser** och registrera det på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="8af53-141">From the display of the **New-MsolUser** command, note the generated password for the Development VP account and record it in a safe location.</span></span>

<span data-ttu-id="8af53-142">Om du vill lägga till nya konton i de nya åtkomstgrupperna kör du följande PowerShell-kommandon från uppmaningen Windows Azure Active Directory-modul för Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8af53-142">Next, to add the new accounts to the new access groups, run these PowerShell commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

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

<span data-ttu-id="8af53-143">Resultat:</span><span class="sxs-lookup"><span data-stu-id="8af53-143">Results:</span></span>

- <span data-ttu-id="8af53-144">Gruppen ProjectX-Members innehåller användarkontona Lead Designer och Lead Researcher</span><span class="sxs-lookup"><span data-stu-id="8af53-144">The ProjectX-Members access group contains the Lead Designer and Lead Researcher user accounts</span></span>

- <span data-ttu-id="8af53-145">Gruppen ProjectX-Admins innehåller det globala administratörskontot för utvärderingsprenumerationen</span><span class="sxs-lookup"><span data-stu-id="8af53-145">The ProjectX-Admins access group contains the global administrator account for your trial subscription</span></span>

- <span data-ttu-id="8af53-146">Gruppen ProjectX-Viewers innehåller användarkontot Development VP</span><span class="sxs-lookup"><span data-stu-id="8af53-146">The ProjectX-Viewers access group contains the Development VP user account</span></span>

<span data-ttu-id="8af53-147">I bild 1 visas åtkomstgrupperna och deras medlemskap.</span><span class="sxs-lookup"><span data-stu-id="8af53-147">Figure 1 shows the access groups and their membership.</span></span>

<span data-ttu-id="8af53-148">**Bild 1:**</span><span class="sxs-lookup"><span data-stu-id="8af53-148">**Figure 1**:</span></span>

![Microsoft 365-grupperna och deras medlemskap för en isolerad SharePoint Online-gruppwebbplats](../../media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)

## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a><span data-ttu-id="8af53-150">Fas 3: Skapa en ny ProjectX SharePoint Online-gruppwebbplats och isolera den</span><span class="sxs-lookup"><span data-stu-id="8af53-150">Phase 3: Create a new ProjectX SharePoint Online team site and isolate it</span></span>

<span data-ttu-id="8af53-151">Så här skapar du en SharePoint Online-gruppwebbplats för ProjectX:</span><span class="sxs-lookup"><span data-stu-id="8af53-151">To create a SharePoint Online team site for ProjectX, do the following:</span></span>

1. <span data-ttu-id="8af53-152">Med hjälp av en webbläsare på din lokala dator (enkel konfiguration) eller på CLIENT1 (simulerad företagskonfiguration) loggar du in på administrationscentret för Microsoft 365 () med ditt <https://admin.microsoft.com> globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="8af53-152">Using a browser on either your local computer (lightweight configuration) or on CLIENT1 (simulated enterprise configuration), sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="8af53-153">Klicka på **SharePoint** i listan med paneler.</span><span class="sxs-lookup"><span data-stu-id="8af53-153">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="8af53-154">På den nya fliken SharePoint i webbläsaren klickar du på **+ Skapa webbplats**.</span><span class="sxs-lookup"><span data-stu-id="8af53-154">On the new SharePoint tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="8af53-155">Skriv ProjectX **i** **gruppwebbplatsens namn.**</span><span class="sxs-lookup"><span data-stu-id="8af53-155">In **Team site name**, type **ProjectX**.</span></span> <span data-ttu-id="8af53-156">Välj **Privat i Sekretessinställningar** **– endast medlemmar kan komma åt den här webbplatsen.**</span><span class="sxs-lookup"><span data-stu-id="8af53-156">In **Privacy settings**, select **Private - only members can access this site**.</span></span>

5. <span data-ttu-id="8af53-157">Skriv **SharePoint-webbplats** för **ProjectX i beskrivningen av gruppwebbplatsen** och klicka sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="8af53-157">In **Team site description**, type **SharePoint site for ProjectX**, and then click **Next**.</span></span>

6. <span data-ttu-id="8af53-158">På knappen **Vem vill du lägga till?** klickar du på **Slutför.**</span><span class="sxs-lookup"><span data-stu-id="8af53-158">On the **Who do you want to add**? pane, click **Finish**.</span></span>

7. <span data-ttu-id="8af53-159">Klicka på ikonen för inställningar i verktygsfältet på den nya **fliken ProjectX-Start** i webbläsaren och klicka sedan på **Webbplatsbehörigheter.**</span><span class="sxs-lookup"><span data-stu-id="8af53-159">On the new **ProjectX-Home** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

8. <span data-ttu-id="8af53-160">I fönstret **Webbplatsbehörigheter** klickar du på **Inställningar för avancerade behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="8af53-160">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

9. <span data-ttu-id="8af53-161">I den nya **behörighetsfliken: Project X** i webbläsaren klickar du på **Inställningar för åtkomstbegäran.**</span><span class="sxs-lookup"><span data-stu-id="8af53-161">In the new **Permissions: Project X** tab in your browser, click **Access Request Settings**.</span></span>

10. <span data-ttu-id="8af53-162">Avmarkera **Tillåt** medlemmar att dela  webbplatsen och enskilda filer och mappar och Tillåt åtkomstbegäranden **(så** att alla tre kryssrutorna avmarkeras) i dialogrutan Inställningar för åtkomstbegäranden och klicka sedan på **OK.**</span><span class="sxs-lookup"><span data-stu-id="8af53-162">In the **Access Requests Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow access requests** (so that all three check boxes are cleared), and then click **OK**.</span></span>

11. <span data-ttu-id="8af53-163">Klicka **på ProjectX-medlemmar** i listan.</span><span class="sxs-lookup"><span data-stu-id="8af53-163">Click **ProjectX Members** in the list.</span></span>

12. <span data-ttu-id="8af53-164">På sidan **Personer och grupper** klickar du på **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="8af53-164">On the **People and Groups** page, click **New**.</span></span>

13. <span data-ttu-id="8af53-165">Skriv  **ProjectX-Members** i dialogrutan Dela, markera den och klicka sedan på **Dela.**</span><span class="sxs-lookup"><span data-stu-id="8af53-165">In the **Share** dialog box, type **ProjectX-Members**, select it, and then click **Share**.</span></span>

14. <span data-ttu-id="8af53-166">Klicka på bakåtknappen i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="8af53-166">Click the back button on your browser.</span></span>

15. <span data-ttu-id="8af53-167">Klicka **på ProjectX-ägare** i listan.</span><span class="sxs-lookup"><span data-stu-id="8af53-167">Click **ProjectX Owners** in the list.</span></span>

16. <span data-ttu-id="8af53-168">På sidan **Personer och grupper** klickar du på **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="8af53-168">On the **People and Groups** page, click **New**.</span></span>

17. <span data-ttu-id="8af53-169">Skriv  **ProjectX-administratörer** i dialogrutan Dela, markera det och klicka sedan på **Dela.**</span><span class="sxs-lookup"><span data-stu-id="8af53-169">In the **Share** dialog box, type **ProjectX-Admins**, select it, and then click **Share**.</span></span>

18. <span data-ttu-id="8af53-170">Klicka på bakåtknappen i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="8af53-170">Click the back button on your browser.</span></span>

19. <span data-ttu-id="8af53-171">Klicka **på ProjectX-besökare** i listan.</span><span class="sxs-lookup"><span data-stu-id="8af53-171">Click **ProjectX Visitors** in the list.</span></span>

20. <span data-ttu-id="8af53-172">På sidan **Personer och grupper** klickar du på **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="8af53-172">On the **People and Groups** page, click **New**.</span></span>

21. <span data-ttu-id="8af53-173">Skriv  **ProjectX-Viewers** i dialogrutan Dela, markera det och klicka sedan på **Dela.**</span><span class="sxs-lookup"><span data-stu-id="8af53-173">In the **Share** dialog box, type **ProjectX-Viewers**, select it, and then click **Share**.</span></span>

22. <span data-ttu-id="8af53-174">Stäng fliken **Personer och** grupper i webbläsaren, klicka på fliken **ProjectX-Start** i webbläsaren och stäng sedan fönstret **Webbplatsbehörigheter.**</span><span class="sxs-lookup"><span data-stu-id="8af53-174">Close the **People and Groups** tab in your browser, click the **ProjectX-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="8af53-175">Här är resultatet av att konfigurera behörigheter:</span><span class="sxs-lookup"><span data-stu-id="8af53-175">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="8af53-176">SharePoint-gruppen ProjectX-medlemmar innehåller endast åtkomstgruppen ProjectX-Members (som endast innehåller användarkontona Lead Designer och Lead Researcher) och ProjectX-gruppen (som endast innehåller användarkontot för global administratör).</span><span class="sxs-lookup"><span data-stu-id="8af53-176">The ProjectX Members SharePoint group contains only the ProjectX-Members access group (which contains only the Lead Designer and Lead Researcher user accounts) and the ProjectX group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="8af53-177">SharePoint-gruppen ProjectX-ägare innehåller ProjectX-Admins gruppen (som endast innehåller användarkontot för global administratör).</span><span class="sxs-lookup"><span data-stu-id="8af53-177">The ProjectX Owners SharePoint group contains only the ProjectX-Admins access group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="8af53-178">SharePoint-gruppen ProjectX Visitors innehåller endast ProjectX-Viewers åtkomstgrupp (som endast innehåller development VP-användarkontot).</span><span class="sxs-lookup"><span data-stu-id="8af53-178">The ProjectX Visitors SharePoint group contains only the ProjectX-Viewers access group (which contains only the Development VP user account).</span></span>

- <span data-ttu-id="8af53-179">Medlemmar kan inte ändra behörigheter på webbplatsnivå (detta kan endast utföras av medlemmar i ProjectX-Admins gruppen).</span><span class="sxs-lookup"><span data-stu-id="8af53-179">Members cannot modify site-level permissions (this can only be done by members of the ProjectX-Admins group).</span></span>

- <span data-ttu-id="8af53-180">Andra användarkonton kan inte komma åt webbplatsen eller dess resurser. De kan inte heller begära åtkomst till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="8af53-180">Other user accounts cannot access the site or its resources or request access to the site.</span></span>

<span data-ttu-id="8af53-181">Bild 2 visar SharePoint-grupperna och deras medlemskap.</span><span class="sxs-lookup"><span data-stu-id="8af53-181">Figure 2 shows the SharePoint groups and their membership.</span></span>

<span data-ttu-id="8af53-182">**Bild 2**</span><span class="sxs-lookup"><span data-stu-id="8af53-182">**Figure 2**</span></span>

![SharePoint Online-grupperna och deras medlemskap för en isolerad SharePoint Online-gruppwebbplats](../../media/595abff4-64f9-49de-a37a-c70c6856936b.png)

<span data-ttu-id="8af53-184">Nu visar vi åtkomst med hjälp av leaddesignerns användarkonto:</span><span class="sxs-lookup"><span data-stu-id="8af53-184">Now let's demonstrate access using the Lead Designer user account:</span></span>

1. <span data-ttu-id="8af53-185">Stäng fliken **ProjectX-Home** i webbläsaren och klicka sedan på fliken **Microsoft Office Start** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="8af53-185">Close the **ProjectX-Home** tab in your browser, and then click the **Microsoft Office Home** tab in your browser.</span></span>

2. <span data-ttu-id="8af53-186">Klicka på den globala administratörens namn och klicka sedan på **Logga ut.**</span><span class="sxs-lookup"><span data-stu-id="8af53-186">Click the name of your global administrator, and then click **Sign out**.</span></span>

3. <span data-ttu-id="8af53-187">Logga in på administrationscentret för Microsoft 365 <https://admin.microsoft.com> () med hjälp av leaddesignerns kontonamn och lösenord.</span><span class="sxs-lookup"><span data-stu-id="8af53-187">Sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using the Lead Designer account name and its password.</span></span>

4. <span data-ttu-id="8af53-188">Klicka på **SharePoint** i listan med paneler.</span><span class="sxs-lookup"><span data-stu-id="8af53-188">In the list of tiles, click **SharePoint**.</span></span>

5. <span data-ttu-id="8af53-189">På den nya **SharePoint-fliken** i webbläsaren skriver du **ProjectX** i sökrutan, aktiverar sökningen och klickar sedan på ProjectX-gruppwebbplatsen. </span><span class="sxs-lookup"><span data-stu-id="8af53-189">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site.</span></span> <span data-ttu-id="8af53-190">Du bör se en ny flik i webbläsaren för ProjectX-gruppwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="8af53-190">You should see a new tab in your browser for the ProjectX team site.</span></span>

6. <span data-ttu-id="8af53-191">Klicka på inställningsikonen.</span><span class="sxs-lookup"><span data-stu-id="8af53-191">Click the settings icon.</span></span> <span data-ttu-id="8af53-192">Observera att det inte finns något alternativ för **webbplatsbehörigheter.**</span><span class="sxs-lookup"><span data-stu-id="8af53-192">Notice that there is no option for **Site Permissions**.</span></span> <span data-ttu-id="8af53-193">Det här är rätt eftersom endast medlemmar i ProjectX-Admins kan ändra behörigheter på webbplatsen</span><span class="sxs-lookup"><span data-stu-id="8af53-193">This is correct because only the members of the ProjectX-Admins group can modify permissions on the site</span></span>

7. <span data-ttu-id="8af53-194">Öppna Anteckningar eller en valfri textredigerare.</span><span class="sxs-lookup"><span data-stu-id="8af53-194">Open Notepad or a text editor of your choice.</span></span>

8. <span data-ttu-id="8af53-195">Kopiera WEBBADRESSen till ProjectX-gruppwebbplatsen och klistra in den på en ny rad i Anteckningar eller i textredigeraren.</span><span class="sxs-lookup"><span data-stu-id="8af53-195">Copy the URL of the ProjectX team site and paste it on a new line in Notepad or your text editor.</span></span>

9. <span data-ttu-id="8af53-196">Klicka på **Dokument på den nya fliken ProjectX-Start** i **webbläsaren.**</span><span class="sxs-lookup"><span data-stu-id="8af53-196">On the new **ProjectX-Home** tab in your browser, click **Documents**.</span></span>

10. <span data-ttu-id="8af53-197">Kopiera WEBBADRESSen till mappen ProjectX-dokument och klistra in den på en ny rad i Anteckningar eller i textredigeraren.</span><span class="sxs-lookup"><span data-stu-id="8af53-197">Copy the URL of the ProjectX documents folder and paste it on a new line in Notepad or your text editor.</span></span>

11. <span data-ttu-id="8af53-198">På den nya **fliken ProjectX-Dokument** i webbläsaren klickar du på **Nytt > Word-dokument.**</span><span class="sxs-lookup"><span data-stu-id="8af53-198">On the new **ProjectX-Documents** tab in your browser, click **New > Word document**.</span></span>

12. <span data-ttu-id="8af53-199">Skriv lite text på sidan, vänta tills statusen visar Sparad, klicka på tillbaka-knappen i webbläsaren och uppdatera sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="8af53-199">Type some text on the page, wait for the status to indicate **Saved**, click the back button on your browser, and then refresh the page.</span></span> <span data-ttu-id="8af53-200">Du bör se en **Document.docx** objekt i **mappen** Dokument.</span><span class="sxs-lookup"><span data-stu-id="8af53-200">You should see a new **Document.docx** in the **Documents** folder.</span></span>

13. <span data-ttu-id="8af53-201">Klicka på ellipsen för **Document.docx** och klicka sedan **på Hämta en länk.**</span><span class="sxs-lookup"><span data-stu-id="8af53-201">Click the ellipsis for the **Document.docx** document, and then click **Get a link**.</span></span>

14. <span data-ttu-id="8af53-202">Kopiera WEBBADRESSen i dialogrutan Dela **Document.docx** och klistra in den på en ny rad i Anteckningar  eller textredigeraren och stäng sedan dialogrutan Dela Document.docx.</span><span class="sxs-lookup"><span data-stu-id="8af53-202">Copy the URL in the **Share 'Document.docx'** dialog box and paste it on a new line in Notepad or your text editor, and then close the **Share 'Document.docx'** dialog box.</span></span>

15. <span data-ttu-id="8af53-203">Stäng **flikarna ProjectX-Dokument** **och SharePoint** i webbläsaren och klicka sedan på fliken **Start i Microsoft Office.**</span><span class="sxs-lookup"><span data-stu-id="8af53-203">Close the **ProjectX-Documents** and **SharePoint** tabs in your browser, and then click the **Microsoft Office Home** tab.</span></span>

16. <span data-ttu-id="8af53-204">Klicka på **leaddesignerns** namn och klicka sedan **på Logga ut.**</span><span class="sxs-lookup"><span data-stu-id="8af53-204">Click the **Lead Designer** name, and then click **Sign out**.</span></span>

<span data-ttu-id="8af53-205">Nu visar vi åtkomst med hjälp av development VP-användarkontot:</span><span class="sxs-lookup"><span data-stu-id="8af53-205">Now let's demonstrate access using the Development VP user account:</span></span>

1. <span data-ttu-id="8af53-206">Logga in på Administrationscenter för Microsoft 365 () med <https://admin.microsoft.com> hjälp av development VP-kontonamnet och dess lösenord.</span><span class="sxs-lookup"><span data-stu-id="8af53-206">Sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using the Development VP account name and its password.</span></span>

2. <span data-ttu-id="8af53-207">Klicka på **SharePoint** i listan med paneler.</span><span class="sxs-lookup"><span data-stu-id="8af53-207">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="8af53-208">På den nya **SharePoint-fliken** i webbläsaren skriver du **ProjectX** i sökrutan, aktiverar sökningen och klickar sedan på ProjectX-gruppwebbplatsen. </span><span class="sxs-lookup"><span data-stu-id="8af53-208">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site.</span></span> <span data-ttu-id="8af53-209">Du bör se en ny flik i webbläsaren för ProjectX-gruppwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="8af53-209">You should see a new tab in your browser for the ProjectX team site.</span></span>

4. <span data-ttu-id="8af53-210">Klicka **på** Dokument och sedan på **Document.docx** dokumentfilen.</span><span class="sxs-lookup"><span data-stu-id="8af53-210">Click **Documents**, and then click the **Document.docx** file.</span></span>

5. <span data-ttu-id="8af53-211">I **Document.docx** i webbläsaren kan du försöka ändra texten.</span><span class="sxs-lookup"><span data-stu-id="8af53-211">In the **Document.docx** tab in your browser, try to modify the text.</span></span> <span data-ttu-id="8af53-212">Du bör se ett meddelande som **säger att det här dokumentet är skrivskyddade.**</span><span class="sxs-lookup"><span data-stu-id="8af53-212">You should see a message stating **This document is read-only.**</span></span> <span data-ttu-id="8af53-213">Detta förväntas eftersom development VP-användarkontot bara har visningsbehörigheter för webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="8af53-213">This is expected because the Development VP user account only has view permissions for the site.</span></span>

6. <span data-ttu-id="8af53-214">Stäng **flikarnaDocument.docx,** **ProjectX-Dokument** och **SharePoint** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="8af53-214">Close the **Document.docx**, **ProjectX-Documents**, and **SharePoint** tabs in your browser.</span></span>

7. <span data-ttu-id="8af53-215">Klicka på **fliken Microsoft Office Home,** klicka på **development VP-namnet** och klicka sedan på **Logga ut.**</span><span class="sxs-lookup"><span data-stu-id="8af53-215">Click the **Microsoft Office Home** tab, click the **Development VP** name, and then click **Sign out**.</span></span>

<span data-ttu-id="8af53-216">Nu ska vi visa åtkomst med ett användarkonto som inte har någon behörighet:</span><span class="sxs-lookup"><span data-stu-id="8af53-216">Now let's demonstrate access with a user account that has no permissions:</span></span>

1. <span data-ttu-id="8af53-217">Logga in på administrationscentret för Microsoft 365 <https://admin.microsoft.com> () med användarnamnet och lösenordet för User 3-kontot.</span><span class="sxs-lookup"><span data-stu-id="8af53-217">Sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using the User 3 account name and its password.</span></span>

2. <span data-ttu-id="8af53-218">Klicka på **SharePoint** i listan med paneler.</span><span class="sxs-lookup"><span data-stu-id="8af53-218">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="8af53-219">På den nya **SharePoint-fliken** i webbläsaren skriver du **ProjectX** i sökrutan och aktiverar sökningen.</span><span class="sxs-lookup"><span data-stu-id="8af53-219">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box and then activate the search.</span></span> <span data-ttu-id="8af53-220">Du bör se meddelandet **Inget här matchar din sökning.**</span><span class="sxs-lookup"><span data-stu-id="8af53-220">You should see the message **Nothing here matches your search.**</span></span>

4. <span data-ttu-id="8af53-221">I den öppna instansen av Anteckningar eller textredigeraren kopierar du URL-adressen för ProjectX-webbplatsen till adressfältet i webbläsaren och trycker på **Retur.**</span><span class="sxs-lookup"><span data-stu-id="8af53-221">From the open instance of Notepad or your text editor, copy the URL for the ProjectX site into the address bar of your browser and press **Enter**.</span></span> <span data-ttu-id="8af53-222">Du bör se en sida **om nekad** åtkomst.</span><span class="sxs-lookup"><span data-stu-id="8af53-222">You should see an **Access Denied** page.</span></span>

5. <span data-ttu-id="8af53-223">Kopiera WEBBADRESSen för mappen ProjectX-dokument från Anteckningar eller textredigeraren till adressfältet i webbläsaren och tryck på **Retur.**</span><span class="sxs-lookup"><span data-stu-id="8af53-223">From Notepad or your text editor, copy the URL for the ProjectX Documents folder into the address bar of your browser and press **Enter**.</span></span> <span data-ttu-id="8af53-224">Du bör se en sida **om nekad** åtkomst.</span><span class="sxs-lookup"><span data-stu-id="8af53-224">You should see an **Access Denied** page.</span></span>

6. <span data-ttu-id="8af53-225">I Anteckningar eller i textredigeraren kopierar du URL:en för Documents.docx filen i adressfältet i webbläsaren och trycker på **Retur.**</span><span class="sxs-lookup"><span data-stu-id="8af53-225">From Notepad or your text editor, copy the URL for the Documents.docx file into the address bar of your browser and press **Enter**.</span></span> <span data-ttu-id="8af53-226">Du bör se en sida **om nekad** åtkomst.</span><span class="sxs-lookup"><span data-stu-id="8af53-226">You should see an **Access Denied** page.</span></span>

7. <span data-ttu-id="8af53-227">Stäng **fliken SharePoint** i webbläsaren, klicka på fliken Start i **Microsoft Office,** klicka på namnet Användare **3** och klicka sedan **på Logga ut.**</span><span class="sxs-lookup"><span data-stu-id="8af53-227">Close the **SharePoint** tab in your browser, click the **Microsoft Office Home** tab, click the **User 3** name, and then click **Sign out**.</span></span>

<span data-ttu-id="8af53-228">Din isolerade SharePoint Online-webbplats är nu redo att experimentera ytterligare.</span><span class="sxs-lookup"><span data-stu-id="8af53-228">Your isolated SharePoint Online site is now ready for your additional experimentation.</span></span>

## <a name="next-step"></a><span data-ttu-id="8af53-229">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="8af53-229">Next Step</span></span>

<span data-ttu-id="8af53-230">När du är redo att distribuera en isolerad SharePoint Online-gruppwebbplats i produktion kan du läsa de steg för steg-informationen om utformning i [Utforma en isolerad SharePoint Online-gruppwebbplats](design-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="8af53-230">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8af53-231">Se även</span><span class="sxs-lookup"><span data-stu-id="8af53-231">See Also</span></span>

[<span data-ttu-id="8af53-232">Isolerade SharePoint Online-gruppwebbplatser</span><span class="sxs-lookup"><span data-stu-id="8af53-232">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="8af53-233">Testlabbguider för integrering med molntjänster</span><span class="sxs-lookup"><span data-stu-id="8af53-233">Cloud adoption Test Lab Guides (TLGs)</span></span>](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[<span data-ttu-id="8af53-234">Baskonfiguration för simulerat företag</span><span class="sxs-lookup"><span data-stu-id="8af53-234">The simulated enterprise base configuration</span></span>](../../enterprise/simulated-ent-base-configuration-microsoft-365-enterprise.md)

[<span data-ttu-id="8af53-235">Den enkla baskonfigurationen</span><span class="sxs-lookup"><span data-stu-id="8af53-235">The lightweight base configuration</span></span>](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md)

[<span data-ttu-id="8af53-236">Microsoft 365-center för lösningar och arkitektur</span><span class="sxs-lookup"><span data-stu-id="8af53-236">Microsoft 365 solution and architecture center</span></span>](../../solutions/index.yml)