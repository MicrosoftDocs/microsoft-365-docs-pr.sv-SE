---
title: Skydda filer i Teams i en utvecklings-/testmiljö
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 06af70f3-e7dc-4ee2-a385-fb4d61a5e93b
description: 'Sammanfattning: Skapa grupper som är känsliga och strikt konfidentiella i Microsoft Teams för filer i en utvecklings-/testmiljö.'
ms.openlocfilehash: 5b3f5c74ac484eb00852d5756b3269fb7c8c6a5b
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637974"
---
# <a name="secure-teams-for-files-in-a-devtest-environment"></a><span data-ttu-id="be24f-103">Skydda filer i Teams i en utvecklings-/testmiljö</span><span class="sxs-lookup"><span data-stu-id="be24f-103">Secure Teams for files in a dev/test environment</span></span>

<span data-ttu-id="be24f-104">I den här artikeln får du stegvisa instruktioner för hur du skapar en utvecklings-/testmiljö som innehåller känsliga och strikt konfidentiella grupper för lösningen [Skydda filer i Microsoft Teams](secure-files-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="be24f-104">This article provides step-by-step instructions to create a dev/test environment that includes the sensitive and highly confidential teams for the [Secure files in Microsoft Teams](secure-files-in-teams.md) solution.</span></span>
  
![Känsliga och strikt konfidentiella grupper för filer i Microsoft Teams.](../../media/sensitive-highly-confidential-teams-dev-test.png)
  
<span data-ttu-id="be24f-106">Använd utvecklings-/testmiljön för att experimentera och finjustera inställningarna efter dina behov innan du distribuerar grupptyperna i produktion.</span><span class="sxs-lookup"><span data-stu-id="be24f-106">Use this dev/test environment to experiment and fine-tune settings for your specific needs before deploying these types of teams in production.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="be24f-107">Fas 1: Bygga ut testmiljön i Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="be24f-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="be24f-108">Om du bara vill testa känsliga och strikt konfidentiella grupper på ett enkelt sätt med lägsta möjliga krav, följer du anvisningarna i [Enkel baskonfiguration](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="be24f-108">If you just want to test sensitive and highly confidential teams in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).</span></span>

<span data-ttu-id="be24f-109">Om du vill testa känsliga och strikt konfidentiella grupper i ett simulerat företag, följer du anvisningarna i [Synkronisering av lösenordshash](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment).</span><span class="sxs-lookup"><span data-stu-id="be24f-109">If you want to test sensitive and highly confidential teams in a simulated enterprise, follow the instructions in [Password hash synchronization](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment).</span></span>

>[!Note]
><span data-ttu-id="be24f-110">Att testa känsliga och strikt konfidentiella grupper kräver inte någon simulerad företagstestmiljö, som innehåller ett simulerat intranät som är kopplat till Internet och katalogsynkronisering för en AD DS-skog (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="be24f-110">Testing sensitive and highly confidential teams does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="be24f-111">Det här är ett alternativ där du kan testa känsliga och strikt konfidentiella grupper, samt experimentera i en miljö som motsvarar en vanlig organisation.</span><span class="sxs-lookup"><span data-stu-id="be24f-111">It is provided here as an option so that you can test sensitive and highly confidential teams and experiment with it in an environment that represents a typical organization.</span></span>
>
    
## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups-and-users"></a><span data-ttu-id="be24f-112">Fas 2: Skapa och konfigurera grupper och användare i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="be24f-112">Phase 2: Create and configure your Azure Active Directory (AD) groups and users</span></span>

<span data-ttu-id="be24f-113">I den här fasen skapar och konfigurerar du Azure AD-grupper och användare för din fiktiva organisation.</span><span class="sxs-lookup"><span data-stu-id="be24f-113">In this phase, you create and configure the Azure AD groups and users for your fictional organization.</span></span>
  
<span data-ttu-id="be24f-114">Börja med att skapa två grupper för en vanlig organisation med Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="be24f-114">First, create two groups for a typical organization with the Azure portal.</span></span>
  
1. <span data-ttu-id="be24f-115">Gå till Azure-portalen på [https://portal.azure.com](https://portal.azure.com) från en separat flik i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="be24f-115">Create a separate tab in your browser, and then go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span> <span data-ttu-id="be24f-116">Om det behövs loggar du in med autentiseringsuppgifterna för det globala administratörskontot för din utvärderingsprenumeration eller betalda prenumeration för Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="be24f-116">If needed, sign in with the credentials of the global administrator account for your Microsoft 365 E5 trial or paid subscription.</span></span>
    
2. <span data-ttu-id="be24f-117">I Azure-portalen klickar du på **Azure Active Directory > Grupper**.</span><span class="sxs-lookup"><span data-stu-id="be24f-117">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>
    
3. <span data-ttu-id="be24f-118">Gå till bladet **Grupper – Alla grupper** och klicka på **+ Ny grupp**.</span><span class="sxs-lookup"><span data-stu-id="be24f-118">On the **Groups - All groups** blade, click **+ New group**.</span></span>
    
4. <span data-ttu-id="be24f-119">På bladet **Grupp**:</span><span class="sxs-lookup"><span data-stu-id="be24f-119">On the **Group** blade:</span></span>
    
  - <span data-ttu-id="be24f-120">Välj **Säkerhet** i **Grupptyp**.</span><span class="sxs-lookup"><span data-stu-id="be24f-120">Select **Security** in **Group type**.</span></span>
    
  - <span data-ttu-id="be24f-121">Skriv **C-Suite** i **Namn**.</span><span class="sxs-lookup"><span data-stu-id="be24f-121">Type **C-Suite** in **Name**.</span></span>
    
  - <span data-ttu-id="be24f-122">Välj **Tilldelad** i **Typ av medlemskap**.</span><span class="sxs-lookup"><span data-stu-id="be24f-122">Select **Assigned** in **Membership type**.</span></span>
      
5. <span data-ttu-id="be24f-123">Klicka på **Skapa** och stäng sedan bladet **Grupp**.</span><span class="sxs-lookup"><span data-stu-id="be24f-123">Click **Create**, and then close the **Group** blade.</span></span>
    
6.    <span data-ttu-id="be24f-124">Upprepa steg 3–5 för en ny grupp med namnet **Marknadspersonal**.</span><span class="sxs-lookup"><span data-stu-id="be24f-124">Repeat steps 3-5 for a new group named **Marketing staff**.</span></span>
    
<span data-ttu-id="be24f-125">Nästa steg är att konfigurera automatisk licensiering så att medlemmarna i dina grupper automatiskt tilldelas licenser för dina Microsoft 365- och EMS-prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="be24f-125">Next, you configure automatic licensing so that members of your groups are automatically assigned licenses for your Microsoft 365 and EMS subscriptions.</span></span>
  
1. <span data-ttu-id="be24f-126">Klicka på **Azure Active Directory > Licenser > Alla produkter** i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="be24f-126">In the Azure portal, click **Azure Active Directory > Licenses > All products**.</span></span>
    
2. <span data-ttu-id="be24f-127">Välj **Microsoft 365 Enterprise E5** i listan och klicka sedan på **Tilldela**.</span><span class="sxs-lookup"><span data-stu-id="be24f-127">In the list, select **Microsoft 365 Enterprise E5**, and then click **Assign**.</span></span>
    
3. <span data-ttu-id="be24f-128">På bladet **Tilldela licens** klickar du på **Användare och grupper**.</span><span class="sxs-lookup"><span data-stu-id="be24f-128">In the **Assign license** blade, click **Users and groups**.</span></span>
    
4. <span data-ttu-id="be24f-129">I listan med grupper väljer du följande:</span><span class="sxs-lookup"><span data-stu-id="be24f-129">In the list of groups, select the following:</span></span>
    
  - <span data-ttu-id="be24f-130">C-Suite</span><span class="sxs-lookup"><span data-stu-id="be24f-130">C-Suite</span></span>
    
  - <span data-ttu-id="be24f-131">Marknadspersonal</span><span class="sxs-lookup"><span data-stu-id="be24f-131">Marketing staff</span></span>
    
5. <span data-ttu-id="be24f-132">Klicka på **Välj** och sedan på **Tilldela**.</span><span class="sxs-lookup"><span data-stu-id="be24f-132">Click **Select**, and then click **Assign**.</span></span>
    
6. <span data-ttu-id="be24f-133">Stäng fliken för Azure-portalen i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="be24f-133">Close the Azure portal tab in your browser.</span></span>
    
<span data-ttu-id="be24f-134">Därefter [ansluter du med Azure Active Directory PowerShell för Graph-modulen](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="be24f-134">Next, you [Connect with the Azure Active Directory PowerShell for Graph module ](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="be24f-135">Fyll i organisationsnamn, plats och lösenord samt kör dessa kommandon från PowerShell-kommandotolken eller en ISE (Integrated Script Environment) för att skapa användarkonton och lägga till dem i grupper:</span><span class="sxs-lookup"><span data-stu-id="be24f-135">Fill in your organization name, your location, and a common password, and then run these commands from the PowerShell command prompt or Integrated Script Environment (ISE) to create user accounts and add them to their groups:</span></span>
  
```powershell
$orgName="<organization name, such as contoso for the contoso.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$groupName="C-Suite"
$userNames=@("CEO","CFO","CIO") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Marketing staff"
$userNames=@("Marketing1", "Marketing2") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
```

> [!NOTE]
> <span data-ttu-id="be24f-136">Ett gemensamt lösenord används för automatisering och enklare konfiguration i utvecklings-/testmiljön.</span><span class="sxs-lookup"><span data-stu-id="be24f-136">The use of a common password here is for automation and ease of configuration for a dev/test environment.</span></span> <span data-ttu-id="be24f-137">Självklart rekommenderas detta inte för produktionsprenumerationer.</span><span class="sxs-lookup"><span data-stu-id="be24f-137">Obviously, this is highly discouraged for production subscriptions.</span></span> 
  
<span data-ttu-id="be24f-138">Använd stegen för att kontrollera att gruppbaserad licensiering fungerar som den ska.</span><span class="sxs-lookup"><span data-stu-id="be24f-138">Use these steps to verify that group-based licensing is working correctly.</span></span>
  
1. <span data-ttu-id="be24f-139">På fliken **Microsoft Office Home** i webbläsaren klickar du på fliken **Administratör**.</span><span class="sxs-lookup"><span data-stu-id="be24f-139">From the **Microsoft Office Home** tab of your browser, click the **Admin** tile.</span></span>
    
2. <span data-ttu-id="be24f-140">Klicka på **Användare**under den nya fliken **Administrationscenter för Microsoft 365** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="be24f-140">From the new **Microsoft 365 admin center** tab of your browser, click **Users**.</span></span>
    
3. <span data-ttu-id="be24f-141">I listan med användare klickar du på **CEO**.</span><span class="sxs-lookup"><span data-stu-id="be24f-141">In the list of users, click **CEO**.</span></span>
    
4. <span data-ttu-id="be24f-142">I fönstret med egenskaperna för **CEO**-användarkontot, kontrollerar du att det har tilldelats till **Microsoft 365 Enterprise E5**-licensen (i **Produktlicenser**).</span><span class="sxs-lookup"><span data-stu-id="be24f-142">In the pane that lists the properties of the **CEO** user account, verify that it has been assigned the **Microsoft 365 Enterprise E5** license (in **Product licenses**).</span></span>
    
## <a name="phase-3-create-retention-labels"></a><span data-ttu-id="be24f-143">Fas 3: Skapa kvarhållningsetiketter</span><span class="sxs-lookup"><span data-stu-id="be24f-143">Phase 3: Create retention labels</span></span>

<span data-ttu-id="be24f-144">I den här fasen skapar du kvarhållningsetiketter till de olika säkerhetsnivåerna för dokumentmapparna på underliggande SharePoint-webbplats.</span><span class="sxs-lookup"><span data-stu-id="be24f-144">In this phase, you create the retention labels for the different levels of security for underlying SharePoint site documents folders.</span></span>

1. <span data-ttu-id="be24f-145">Logga in på [efterlevnadsportalen i Microsoft 365](https://compliance.microsoft.com) med ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="be24f-145">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with your global admin account.</span></span>
    
2. <span data-ttu-id="be24f-146">På fliken **Start – Efterlevnad i Microsoft 365** i webbläsaren klickar du på **Klassifikationer > Etiketter**.</span><span class="sxs-lookup"><span data-stu-id="be24f-146">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="be24f-147">Klicka på **Kvarhållningsetiketter > Skapa en etikett**.</span><span class="sxs-lookup"><span data-stu-id="be24f-147">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="be24f-148">I fönstret **Namnge din etikett** skriver du **Känslig** i **Namnge din etikett**. Klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="be24f-148">On the **Name your label** pane, type **Sensitive** in **Name your label**, and then click **Next**.</span></span>

5. <span data-ttu-id="be24f-149">Klicka på **Nästa** i fönstret **Filplansbeskrivningar**.</span><span class="sxs-lookup"><span data-stu-id="be24f-149">On the **File plan descriptors** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="be24f-150">I fönstret **Etikettinställningar** anger du vid behov **Kvarhållning** till **På** och klickar sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="be24f-150">On the **Label settings** pane, if needed, set **Retention** to **On**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="be24f-151">I fönstret **Granska inställningarna** klickar du på **Skapa etiketten**.</span><span class="sxs-lookup"><span data-stu-id="be24f-151">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="be24f-152">Upprepa steg 3–7 för ytterligare en kvarhållningsetikett med namnet **Strikt konfidentiell**.</span><span class="sxs-lookup"><span data-stu-id="be24f-152">Repeat steps 3-7 for an additional retention label named **Highly Confidential**.</span></span>
    
9. <span data-ttu-id="be24f-153">I fönstret **Start > Etiketter** klickar du på **Publicera etiketter**.</span><span class="sxs-lookup"><span data-stu-id="be24f-153">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
10. <span data-ttu-id="be24f-154">Klicka på **Välj etiketter att publicera** i fönstret **Välj etiketter att publicera**.</span><span class="sxs-lookup"><span data-stu-id="be24f-154">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
11. <span data-ttu-id="be24f-155">I fönstret **Välj etiketter** klickar du på **Lägg till** och markerar alla fyra etiketterna.</span><span class="sxs-lookup"><span data-stu-id="be24f-155">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
12. <span data-ttu-id="be24f-156">Klicka på **Klar**.</span><span class="sxs-lookup"><span data-stu-id="be24f-156">Click **Done**.</span></span>
    
13. <span data-ttu-id="be24f-157">I fönstret **Välj etiketter att publicera** klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="be24f-157">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="be24f-158">Klicka på **Nästa** i fönstret **Välj platser**.</span><span class="sxs-lookup"><span data-stu-id="be24f-158">On the **Choose locations** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="be24f-159">I fönstret **Namnge principen** skriver du **Organisationsexempel** i **Namn** och klickar sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="be24f-159">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
16. <span data-ttu-id="be24f-160">I fönstret **Granska inställningarna** klickar du på **Publicera etiketter** och sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="be24f-160">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>
    
## <a name="phase-4-create-your-teams"></a><span data-ttu-id="be24f-161">Fas 4: Skapa dina grupper</span><span class="sxs-lookup"><span data-stu-id="be24f-161">Phase 4: Create your teams</span></span>

<span data-ttu-id="be24f-162">I den här fasen skapar och konfigurerar du känsliga och strikt konfidentiella grupper i ditt organisationsexempel.</span><span class="sxs-lookup"><span data-stu-id="be24f-162">In this phase, you create and configure sensitive and highly confidential teams for your example organization.</span></span>

### <a name="sensitive-team-for-marketing-campaigns"></a><span data-ttu-id="be24f-163">Känslig grupp för marknadsföringskampanjer</span><span class="sxs-lookup"><span data-stu-id="be24f-163">Sensitive team for marketing campaigns</span></span>

<span data-ttu-id="be24f-164">Skapa en grupp på den känsliga nivån för medlemmarna i marknadsföringsgruppen som ska samarbeta i pågående marknadsföringskampanjer:</span><span class="sxs-lookup"><span data-stu-id="be24f-164">To create a sensitive-level team for members of the marketing group to collaborate on ongoing marketing campaigns:</span></span>

1. <span data-ttu-id="be24f-165">[Skapa en ny privat grupp](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) med namnet **Marknadsföringskampanjer**.</span><span class="sxs-lookup"><span data-stu-id="be24f-165">[Create a new private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) with the name **Marketing Campaigns**.</span></span>
2. <span data-ttu-id="be24f-166">Öppna gruppen **Marknadsföringskampanjer**.</span><span class="sxs-lookup"><span data-stu-id="be24f-166">Open the **Marketing Campaigns** team.</span></span>
3.    <span data-ttu-id="be24f-167">I verktygsfältet för gruppen klickar du på **Filer**.</span><span class="sxs-lookup"><span data-stu-id="be24f-167">In the tool bar for the team, click **Files**.</span></span>
4.    <span data-ttu-id="be24f-168">Klicka på ellipsen och sedan på **Öppna i SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="be24f-168">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
5.    <span data-ttu-id="be24f-169">Klicka på inställningsikonen i verktygsfältet på den underliggande SharePoint-webbplatsen och klicka sedan på **Webbplatsbehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="be24f-169">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
6.    <span data-ttu-id="be24f-170">I fönstret **Webbplatsbehörigheter** under **Delningsinställningar** klickar du på **Ändra delningsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="be24f-170">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
7.    <span data-ttu-id="be24f-171">Under **Delningsbehörigheter** väljer du **Endast webbplatsens ägare kan dela filer, mappar och webbplatsen**. Klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="be24f-171">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>

<span data-ttu-id="be24f-172">Därefter konfigurerar du dokumentmappen för den underliggande SharePoint-webbplatsen för marknadsföringskampanjer med etiketten Känslig.</span><span class="sxs-lookup"><span data-stu-id="be24f-172">Next, configure the documents folder of the underlying Marketing Campaigns SharePoint site for the Sensitive label.</span></span>

1.    <span data-ttu-id="be24f-173">På fliken **Marknadsföringskampanjer-Start** i webbläsaren klickar du på **Dokument**.</span><span class="sxs-lookup"><span data-stu-id="be24f-173">In the **Marketing Campaigns-Home** tab of your browser, click **Documents**.</span></span>
2.    <span data-ttu-id="be24f-174">Klicka på inställningsikonen och sedan på **Inställningar för bibliotek**. </span><span class="sxs-lookup"><span data-stu-id="be24f-174">Click the settings icon, and then click **Library settings**.</span></span>
3.    <span data-ttu-id="be24f-175">Under **Behörigheter och hantering** klickar du på **Använd etikett för objekt i det här biblioteket**. </span><span class="sxs-lookup"><span data-stu-id="be24f-175">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
4.    <span data-ttu-id="be24f-176">I **Inställningar-Använd etikett** väljer du **Känslig** och klickar sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="be24f-176">In **Settings-Apply Label**, select **Sensitive**, and then click **Save**.</span></span> 

<span data-ttu-id="be24f-177">Därefter konfigurerar du en princip för dataförlustskydd (DLP) som meddelar användarna när de delar ett dokument med etiketten Känslig på en underliggande SharePoint-webbplats (som inkluderar marknadsföringskampanjplatsen) och som finns utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="be24f-177">Next, configure a data loss prevention (DLP) policy that notifies users when they share a document on the underlying SharePoint site with the Sensitive label, which includes the Marketing Campaigns site, outside the organization.</span></span>

1. <span data-ttu-id="be24f-178">Logga in på [efterlevnadsportalen i Microsoft 365](https://compliance.microsoft.com/) med ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="be24f-178">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with your global admin account.</span></span>
    
2. <span data-ttu-id="be24f-179">På den nya fliken **Efterlevnad i Microsoft 365** i webbläsaren klickar du på **Principer > Dataförlustskydd**.</span><span class="sxs-lookup"><span data-stu-id="be24f-179">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="be24f-180">I fönstret **Start > Dataförlustskydd** klickar du på **Skapa en princip**.</span><span class="sxs-lookup"><span data-stu-id="be24f-180">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="be24f-181">I fönstret **Börja med en mall eller skapa en anpassad princip** klickar du på **Anpassa** och sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="be24f-181">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="be24f-182">I fönstret **Namnge principen** skriver du **Etiketten Känslig, SharePoint-webbplatser** i **Namn**. Klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="be24f-182">In the **Name your policy** pane, type **Sensitive label SharePoint sites** in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="be24f-183">I fönstret **Välj platser** klickar du på **Låt mig välja specifika platser**. Klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="be24f-183">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="be24f-184">Inaktivera platserna **Exchange-e-post**, **OneDrive-konton** och **Chatt- och kanalmeddelanden i Teams** i listan med platser och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="be24f-184">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="be24f-185">I fönstret **Anpassa typen av innehåll som du vill skydda** klickar du på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="be24f-185">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="be24f-186">I fönstret **Välj de typer av innehåll som ska skyddas** klickar du på **Lägg till** i listrutan och klickar sedan på **Kvarhållningsetiketter**.</span><span class="sxs-lookup"><span data-stu-id="be24f-186">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="be24f-187">I fönstret **Kvarhållningsetiketter** klickar du på **Lägg till**, väljer etiketten **Känslig**, klickar på **Lägg till** och sedan på **Klar**.</span><span class="sxs-lookup"><span data-stu-id="be24f-187">In the **Retention labels** pane, click **Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="be24f-188">I fönstret **Välj de typer av innehåll som ska skyddas** klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="be24f-188">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="be24f-189">I fönstret **Anpassa typen av innehåll som du vill skydda** klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="be24f-189">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="be24f-190">I fönstret **Vad vill du göra om vi identifierar känslig information?** klickar du på **Anpassa tips och e-post**.</span><span class="sxs-lookup"><span data-stu-id="be24f-190">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="be24f-191">I fönstret **Anpassa principtips och e-postmeddelanden** klickar du på **Anpassa principtipsets text**.</span><span class="sxs-lookup"><span data-stu-id="be24f-191">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="be24f-192">I textrutan skriver du eller klistrar in följande:</span><span class="sxs-lookup"><span data-stu-id="be24f-192">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="be24f-193">Om du vill dela med en användare utanför organisationen, laddar du ned filen och öppnar den.</span><span class="sxs-lookup"><span data-stu-id="be24f-193">To share with a user outside the organization, download the file and then open it.</span></span> <span data-ttu-id="be24f-194">Klicka på Arkiv, Skydda dokument och Kryptera med lösenord och ange sedan ett starkt lösenord.</span><span class="sxs-lookup"><span data-stu-id="be24f-194">Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password.</span></span> <span data-ttu-id="be24f-195">Skicka lösenordet i ett separat e-postmeddelande eller med annat kommunikationssätt.</span><span class="sxs-lookup"><span data-stu-id="be24f-195">Send the password in a separate email or other means of communication.</span></span>
    
16. <span data-ttu-id="be24f-196">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="be24f-196">Click **OK**.</span></span>
    
17. <span data-ttu-id="be24f-197">I fönstret **Vad vill du göra om vi identifierar känslig information?** klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="be24f-197">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="be24f-198">I fönstret **Vill du aktivera principen eller testa saker först?** klickar du på **Ja, aktivera direkt** och sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="be24f-198">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="be24f-199">I fönstret **Granska inställningarna** klickar du på **Skapa** och sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="be24f-199">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

<span data-ttu-id="be24f-200">Här är den resulterande konfigurationen för marknadsföringskampanjens grupp.</span><span class="sxs-lookup"><span data-stu-id="be24f-200">Here is the resulting configuration for the Marketing Campaigns team.</span></span>

![Konfiguration av gruppen Marknadsföringskampanjer.](../../media/sensitive-team-config-dev-test.png)
  
### <a name="company-strategy-team-site"></a><span data-ttu-id="be24f-202">Gruppwebbplats för företagsstrategi</span><span class="sxs-lookup"><span data-stu-id="be24f-202">Company strategy team site</span></span>

<span data-ttu-id="be24f-203">Skapa en strikt konfidentiell grupp för medlemmar i ledningsgruppen som ska samarbeta om företagsstrategin:</span><span class="sxs-lookup"><span data-stu-id="be24f-203">To create a highly confidential-level team for members of the senior leadership team to collaborate on company strategy:</span></span>

1. <span data-ttu-id="be24f-204">[Skapa en ny privat grupp](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) med namnet **Företagsstrategi**.</span><span class="sxs-lookup"><span data-stu-id="be24f-204">[Create a new private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) with the name **Company Strategy**.</span></span>
2. <span data-ttu-id="be24f-205">Öppna gruppen **Företagsstrategi**.</span><span class="sxs-lookup"><span data-stu-id="be24f-205">Open the **Company Strategy** team.</span></span>
3.    <span data-ttu-id="be24f-206">I verktygsfältet för gruppen klickar du på **Filer**.</span><span class="sxs-lookup"><span data-stu-id="be24f-206">In the tool bar for the team, click **Files**.</span></span>
4.    <span data-ttu-id="be24f-207">Klicka på ellipsen och sedan på **Öppna i SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="be24f-207">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
5.    <span data-ttu-id="be24f-208">Klicka på inställningsikonen i verktygsfältet på den underliggande SharePoint-webbplatsen och klicka sedan på **Webbplatsbehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="be24f-208">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
6.    <span data-ttu-id="be24f-209">I fönstret **Webbplatsbehörigheter** under **Delningsinställningar** klickar du på **Ändra delningsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="be24f-209">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
7.    <span data-ttu-id="be24f-210">Under **Delningsbehörigheter** väljer du **Endast webbplatsägare kan dela filer, mappar och webbplats**.</span><span class="sxs-lookup"><span data-stu-id="be24f-210">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
8.    <span data-ttu-id="be24f-211">Inaktivera **Tillåt åtkomstbegäranden** och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="be24f-211">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="be24f-212">Därefter konfigurerar du dokumentmappen för företagsstrategins underliggande SharePoint-webbplats med etiketten Strikt konfidentiellt.</span><span class="sxs-lookup"><span data-stu-id="be24f-212">Next, configure the documents folder of the underlying Company Strategy SharePoint site for the Highly Confidential label.</span></span>

1.    <span data-ttu-id="be24f-213">På fliken **Företagsstrategi-Start** i webbläsaren klickar du på **Dokument**.</span><span class="sxs-lookup"><span data-stu-id="be24f-213">In the **Company Strategy-Home** tab of your browser, click **Documents**.</span></span>
2.    <span data-ttu-id="be24f-214">Klicka på inställningsikonen och sedan på **Inställningar för bibliotek**. </span><span class="sxs-lookup"><span data-stu-id="be24f-214">Click the settings icon, and then click **Library settings**.</span></span>
3.    <span data-ttu-id="be24f-215">Under **Behörigheter och hantering** klickar du på **Använd etikett för objekt i det här biblioteket**. </span><span class="sxs-lookup"><span data-stu-id="be24f-215">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
4.    <span data-ttu-id="be24f-216">I **Inställningar-Använd etikett** väljer du **Strikt konfidentiellt** och klickar sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="be24f-216">In **Settings-Apply Label**, select **Highly Confidential**, and then click **Save**.</span></span> 

<span data-ttu-id="be24f-217">Därefter konfigurerar du en DLP-princip som blockerar användare när de delar ett dokument med etiketten Strikt konfidentiellt på en underliggande SharePoint-webbplats (som inkluderar företagsstrategiplatsen) som finns utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="be24f-217">Next, configure a DLP policy that blocks users when they share a document on an underlying SharePoint site with the Highly Confidential label, which includes the Company Strategy site, outside the organization.</span></span>
  
1. <span data-ttu-id="be24f-218">Logga in på [efterlevnadsportalen i Microsoft 365](https://compliance.microsoft.com/) som global administratör.</span><span class="sxs-lookup"><span data-stu-id="be24f-218">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with your global admin.</span></span>
    
2. <span data-ttu-id="be24f-219">På den nya fliken **Efterlevnad i Microsoft 365** i webbläsaren klickar du på **Principer > Dataförlustskydd**.</span><span class="sxs-lookup"><span data-stu-id="be24f-219">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="be24f-220">I fönstret **Start > Dataförlustskydd** klickar du på **Skapa en princip**.</span><span class="sxs-lookup"><span data-stu-id="be24f-220">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="be24f-221">I fönstret **Börja med en mall eller skapa en anpassad princip** klickar du på **Anpassa** och sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="be24f-221">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="be24f-222">I fönstret **Namnge principen** skriver du **Etiketten Strikt konfidentiellt, SharePoint-webbplatser** i **Namn**. Klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="be24f-222">In the **Name your policy** pane, type **Highly Confidential label SharePoint sites** in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="be24f-223">I fönstret **Välj platser** klickar du på **Låt mig välja specifika platser**. Klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="be24f-223">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="be24f-224">Inaktivera platserna **Exchange-e-post**, **OneDrive-konton** och **Chatt- och kanalmeddelanden i Teams** i listan med platser och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="be24f-224">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="be24f-225">I fönstret **Anpassa typen av innehåll som du vill skydda** klickar du på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="be24f-225">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="be24f-226">I fönstret **Välj de typer av innehåll som ska skyddas** klickar du på **Lägg till** i listrutan och klickar sedan på **Kvarhållningsetiketter**.</span><span class="sxs-lookup"><span data-stu-id="be24f-226">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="be24f-227">I fönstret **Kvarhållningsetiketter** klickar du på **Lägg till**, väljer **Strikt konfidentiellt**, klickar på **Lägg till** och sedan på **Klar**.</span><span class="sxs-lookup"><span data-stu-id="be24f-227">In the **Retention labels** pane, click **Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="be24f-228">I fönstret **Välj de typer av innehåll som ska skyddas** klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="be24f-228">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="be24f-229">I fönstret **Anpassa typen av innehåll som du vill skydda** klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="be24f-229">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="be24f-230">I fönstret **Vad vill du göra om vi identifierar känslig information?** klickar du på **Anpassa tips och e-post**.</span><span class="sxs-lookup"><span data-stu-id="be24f-230">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="be24f-231">I fönstret **Anpassa principtips och e-postmeddelanden** klickar du på **Anpassa principtipsets text**.</span><span class="sxs-lookup"><span data-stu-id="be24f-231">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="be24f-232">I textrutan skriver du eller klistrar in följande:</span><span class="sxs-lookup"><span data-stu-id="be24f-232">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="be24f-233">Om du vill dela med en användare utanför organisationen, laddar du ned filen och öppnar den.</span><span class="sxs-lookup"><span data-stu-id="be24f-233">To share with a user outside the organization, download the file and then open it.</span></span> <span data-ttu-id="be24f-234">Klicka på Arkiv, Skydda dokument och Kryptera med lösenord och ange sedan ett starkt lösenord.</span><span class="sxs-lookup"><span data-stu-id="be24f-234">Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password.</span></span> <span data-ttu-id="be24f-235">Skicka lösenordet i ett separat e-postmeddelande eller med annat kommunikationssätt.</span><span class="sxs-lookup"><span data-stu-id="be24f-235">Send the password in a separate email or other means of communication.</span></span>
    
16. <span data-ttu-id="be24f-236">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="be24f-236">Click **OK**.</span></span>
    
17. <span data-ttu-id="be24f-237">I fönstret **Vill du aktivera principen eller testa saker först?** klickar du på **Ja, aktivera direkt** och sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="be24f-237">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

18. <span data-ttu-id="be24f-238">I fönstret **Vill du aktivera principen eller testa saker först?** klickar du på **Ja, aktivera direkt** och sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="be24f-238">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="be24f-239">I fönstret **Granska inställningarna** klickar du på **Skapa** och sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="be24f-239">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

<span data-ttu-id="be24f-240">Använd [anvisningarna](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) till att konfigurera en känslighetsetikett med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="be24f-240">Use [these instructions](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a sensitivity label with the following settings:</span></span>

- <span data-ttu-id="be24f-241">Etikettnamnet är Företagsstrategi</span><span class="sxs-lookup"><span data-stu-id="be24f-241">The name of the label is Company Strategy</span></span>
- <span data-ttu-id="be24f-242">Kryptering är aktiverat</span><span class="sxs-lookup"><span data-stu-id="be24f-242">Encryption is enabled</span></span>
- <span data-ttu-id="be24f-243">Gruppen Företagsstrategi har samredigeringsbehörighet</span><span class="sxs-lookup"><span data-stu-id="be24f-243">The Company Strategy group has Co-Author permissions</span></span>

<span data-ttu-id="be24f-244">Publicera den nya etiketten när du har skapat den.</span><span class="sxs-lookup"><span data-stu-id="be24f-244">After creating, publish the new label.</span></span> <span data-ttu-id="be24f-245">Om du loggar in som medlem i gruppen Företagsstrategi, kommer du att se den nya etiketten i alternativet Känslighet i verktygsfältet Start i Word, Excel och PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="be24f-245">If you sign in as a member of the Company Strategy group, you will see the new label in the Sensitivity option in the Home toolbar of Word, Excel, and PowerPoint.</span></span> <span data-ttu-id="be24f-246">Välj etiketten Företagsstrategi från alternativet Känslighet om du vill tilldela etiketten till en fil.</span><span class="sxs-lookup"><span data-stu-id="be24f-246">Select the Company Strategy label from the Sensitivity option to assign the label to a file.</span></span>

<span data-ttu-id="be24f-247">Här är den resulterande konfigurationen för gruppen Företagsstrategi.</span><span class="sxs-lookup"><span data-stu-id="be24f-247">Here is the resulting configuration for the Company Strategy team.</span></span>

![Konfiguration av gruppen Företagsstrategi.](../../media/highlyconfidential-team-config-dev-test.png) 

<span data-ttu-id="be24f-249">Filer som finns i dokumentavsnittet på företagsstrategins underliggande SharePoint-webbplats, tilldelas kvarhållningsetiketten Strikt konfidentiellt och omfattas av den konfigurerade DLP-principen.</span><span class="sxs-lookup"><span data-stu-id="be24f-249">Files in the documents section of the underlying Company Strategy SharePoint site are assigned the Highly confidential retention label and are subject to the configured DLP policy.</span></span> <span data-ttu-id="be24f-250">Filer kan också ha tilldelats känslighetsetiketten för företagsstrategin.</span><span class="sxs-lookup"><span data-stu-id="be24f-250">Files can also have the Company Strategy sensitivity label assigned.</span></span>    
  
## <a name="next-step"></a><span data-ttu-id="be24f-251">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="be24f-251">Next step</span></span>

<span data-ttu-id="be24f-252">När du är redo för produktionsdistribution kan du läsa mer i [Skydda filer i Microsoft Teams](secure-files-in-teams.md) för detaljerad information och länkar till steg för steg-distributionsartiklar.</span><span class="sxs-lookup"><span data-stu-id="be24f-252">When you are ready for production deployment, see [Secure files in Microsoft Teams](secure-files-in-teams.md) for detailed information and links to step-by-step deployment articles.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="be24f-253">Se även</span><span class="sxs-lookup"><span data-stu-id="be24f-253">See Also</span></span>

[<span data-ttu-id="be24f-254">Integrering av moln- och hybridlösningar</span><span class="sxs-lookup"><span data-stu-id="be24f-254">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
