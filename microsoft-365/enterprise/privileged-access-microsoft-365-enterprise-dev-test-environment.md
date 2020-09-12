---
title: Hantering av privilegie rad åtkomst för din test miljö för Microsoft 365 för företag
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: Ent_TLGs
description: Använd den här test laboratorie guiden för att aktivera hantering av privilegierad åtkomst för Microsoft 365 för företags test miljö.
ms.openlocfilehash: d8d92aa86076e323e4b5bb5c8eb1385edcac420c
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545948"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="379ee-103">Hantering av privilegie rad åtkomst för din test miljö för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="379ee-103">Privileged access management for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="379ee-104">*Den här test laboratorie guiden kan användas för både Microsoft 365 för företags-och Office 365 företags test miljöer.*</span><span class="sxs-lookup"><span data-stu-id="379ee-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="379ee-105">Genom att följa anvisningarna i den här artikeln kan du konfigurera hanteringen av behörig åtkomst för att öka säkerheten i test miljön av Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="379ee-105">With the instructions in this article, you configure privileged access management to increase security in your Microsoft 365 for enterprise test environment.</span></span>

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

>[!TIP]
><span data-ttu-id="379ee-107">Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med testlabbguider för Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="379ee-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="379ee-108">Fas 1: bygga ut test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="379ee-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="379ee-109">Om du bara vill konfigurera privilegie rad åtkomst hantering på ett enkelt sätt med de minsta kraven följer du anvisningarna i [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="379ee-109">If you just want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="379ee-110">Om du vill konfigurera privilegie rad åtkomst hantering i ett simulerat företag följer du anvisningarna i [vidarekoppling](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="379ee-110">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
>[!NOTE]
><span data-ttu-id="379ee-111">För att testa hanteringen av privilegierade åtkomst krävs inte den simulerade företags test miljön, som innehåller ett simulerat intranät som är kopplat till Internet och Directory-synkronisering för en AD DS-skog.</span><span class="sxs-lookup"><span data-stu-id="379ee-111">Testing privileged access management does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an AD DS forest.</span></span> <span data-ttu-id="379ee-112">Det finns ett alternativ som gör att du kan testa hanteringen av behörig åtkomst och experimentera med den i en miljö som representerar en typisk organisation.</span><span class="sxs-lookup"><span data-stu-id="379ee-112">It is provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="379ee-113">Fas 2: Konfigurera hantering av behörig åtkomst</span><span class="sxs-lookup"><span data-stu-id="379ee-113">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="379ee-114">I den här fasen konfigurerar du en god kännare grupp och aktiverar hantering av privilegierade åtkomst för din Microsoft 365 för företags test miljö.</span><span class="sxs-lookup"><span data-stu-id="379ee-114">In this phase, you configure an approvers group and enable privileged access management for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="379ee-115">Mer information och en översikt över privilegierade åtkomst hantering finns i [Hantera privilegierad åtkomst](../compliance/privileged-access-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="379ee-115">For additional details and an overview of privileged access management, see [Privileged access management](../compliance/privileged-access-management-overview.md).</span></span>

<span data-ttu-id="379ee-116">Följ de här stegen för att konfigurera och använda privilegie rad åtkomst i organisationen:</span><span class="sxs-lookup"><span data-stu-id="379ee-116">Follow these steps to set up and use privileged access in your organization:</span></span>

- [<span data-ttu-id="379ee-117">Steg 1: skapa en god kännare grupp</span><span class="sxs-lookup"><span data-stu-id="379ee-117">Step 1: Create an approver's group</span></span>](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

    <span data-ttu-id="379ee-118">Innan du börjar använda privilegie rad åtkomst kan du bestämma vem som ska ha godkännande auktoritet för inkommande förfrågningar om åtkomst till förhöjda och behöriga uppgifter.</span><span class="sxs-lookup"><span data-stu-id="379ee-118">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="379ee-119">Alla användare som är medlemmar i gruppen god kännare kan godkänna åtkomst förfrågningar.</span><span class="sxs-lookup"><span data-stu-id="379ee-119">Any user who is part of the Approvers’ group will be able to approve access requests.</span></span> <span data-ttu-id="379ee-120">Det här är aktiverat genom att skapa en e-postaktive rad säkerhets grupp i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="379ee-120">This is enabled by creating a mail-enabled security group in Microsoft 365.</span></span> <span data-ttu-id="379ee-121">Skapa en ny säkerhets grupp med namnet "behöriga åtkomst god kännare" i test miljön och Lägg till "användare 3" tidigare skapad i den föregående test laboratorie guiden.</span><span class="sxs-lookup"><span data-stu-id="379ee-121">Create a new security group named "Privileged Access Approvers" in your test environment and add the "User 3" previously created in prior test lab guide steps.</span></span>

- [<span data-ttu-id="379ee-122">Steg 2: Aktivera privilegie rad åtkomst</span><span class="sxs-lookup"><span data-stu-id="379ee-122">Step 2: Enable privileged access</span></span>](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

    <span data-ttu-id="379ee-123">Privilegie rad åtkomst måste aktive ras explicit i Microsoft 365 med standard gruppen för godkännande och inklusive en uppsättning system konton som du vill ska undantas från åtkomst kontroll för privilegie rad åtkomst.</span><span class="sxs-lookup"><span data-stu-id="379ee-123">Privileged access needs to be explicitly turned on in Microsoft 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control.</span></span> <span data-ttu-id="379ee-124">Se till att aktivera privilegie rad åtkomst i organisationen innan du startar fas 3 av den här guiden.</span><span class="sxs-lookup"><span data-stu-id="379ee-124">Be sure to enable privileged access in your organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="379ee-125">Fas 3: kontrol lera att godkännande krävs för förhöjda och behöriga uppgifter</span><span class="sxs-lookup"><span data-stu-id="379ee-125">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="379ee-126">I den här fasen kontrollerar du att principen för privilegie rad åtkomst fungerar och att användarna kräver godkännande för att utföra definierade förhöjda och behöriga uppgifter.</span><span class="sxs-lookup"><span data-stu-id="379ee-126">In this phase, you verify that the privileged access policy is working and users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="379ee-127">Testa möjligheten att utföra en uppgift som inte har definierats i en policy för privilegie rad åtkomst</span><span class="sxs-lookup"><span data-stu-id="379ee-127">Test ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="379ee-128">Först ansluter du till Exchange Management PowerShell med autentiseringsuppgifterna för en användare som har kon figurer ATS som global administratör i test miljön och försöker skapa en ny journal regel.</span><span class="sxs-lookup"><span data-stu-id="379ee-128">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="379ee-129">Den [nya – JournalRule](https://docs.microsoft.com/powershell/module/exchange/new-journalrule) uppgiften är för närvarande inte definierad i en policy för privilegie rad åtkomst för organisationen.</span><span class="sxs-lookup"><span data-stu-id="379ee-129">The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/new-journalrule) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="379ee-130">På din lokala dator öppnar du och loggar in på Exchange Online Remote PowerShell-modulen på **Microsoft Corporation**  >  **Microsoft Exchange Online Remote PowerShell module** med det globala administratörs kontot för test miljön.</span><span class="sxs-lookup"><span data-stu-id="379ee-130">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="379ee-131">I Exchange Management PowerShell kan du skapa en ny journal regel för organisationen:</span><span class="sxs-lookup"><span data-stu-id="379ee-131">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```

4. <span data-ttu-id="379ee-132">Visa att den nya Journal regeln skapades i Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="379ee-132">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="379ee-133">Skapa en ny privilegierad åtkomst policy för den nya-JournalRule-aktiviteten</span><span class="sxs-lookup"><span data-stu-id="379ee-133">Create a new privileged access policy for the New-JournalRule task</span></span>

>[!NOTE]
><span data-ttu-id="379ee-134">Om du inte redan har slutfört steg 1 och 2 från fas 2 i den här guiden ska du läsa igenom stegen för att skapa en god kännare grupp med namnet "behörighets godkännanden" och aktivera privilegie rad åtkomst i test miljön.</span><span class="sxs-lookup"><span data-stu-id="379ee-134">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" and to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="379ee-135">Logga in i [administrations centret för Microsoft 365](https://admin.microsoft.com) med autentiseringsuppgifter det globala administratörs kontot för test miljön.</span><span class="sxs-lookup"><span data-stu-id="379ee-135">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="379ee-136">I administrations centret går du till **Inställningar**  >  **säkerhet & integritet**  >  **privilegie rad åtkomst**.</span><span class="sxs-lookup"><span data-stu-id="379ee-136">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="379ee-137">Välj **Hantera åtkomst principer och begär Anden**.</span><span class="sxs-lookup"><span data-stu-id="379ee-137">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="379ee-138">Välj **Konfigurera principer** och välj sedan **Lägg till en princip**.</span><span class="sxs-lookup"><span data-stu-id="379ee-138">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="379ee-139">Välj eller ange följande värden i list rutan.</span><span class="sxs-lookup"><span data-stu-id="379ee-139">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="379ee-140">**Princip typ**: uppgift</span><span class="sxs-lookup"><span data-stu-id="379ee-140">**Policy type**: Task</span></span>

    <span data-ttu-id="379ee-141">**Princip omfattning**: Exchange</span><span class="sxs-lookup"><span data-stu-id="379ee-141">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="379ee-142">**Princip namn**: ny journal regel</span><span class="sxs-lookup"><span data-stu-id="379ee-142">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="379ee-143">**Godkännande typ**: manuell</span><span class="sxs-lookup"><span data-stu-id="379ee-143">**Approval type**: Manual</span></span>

    <span data-ttu-id="379ee-144">**Godkännande grupp**: god kännare för privilegie rad åtkomst</span><span class="sxs-lookup"><span data-stu-id="379ee-144">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="379ee-145">Välj **skapa** och sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="379ee-145">Select **Create** and then **Close**.</span></span> <span data-ttu-id="379ee-146">Det kan ta några minuter innan principen är fullständigt konfigurerad och aktive rad.</span><span class="sxs-lookup"><span data-stu-id="379ee-146">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="379ee-147">Se till att tiden för principen är fullständigt aktive rad innan du testar godkännande kravet i nästa steg.</span><span class="sxs-lookup"><span data-stu-id="379ee-147">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="379ee-148">Test godkännande krav för den nya-JournalRule-aktiviteten definierad i en policy för privilegie rad åtkomst</span><span class="sxs-lookup"><span data-stu-id="379ee-148">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="379ee-149">På din lokala dator öppnar du och loggar in på Exchange Online Remote PowerShell-modulen på **Microsoft Corporation**  >  **Microsoft Exchange Online Remote PowerShell-modul** med ett Använd globalt administratörs konto för test miljön.</span><span class="sxs-lookup"><span data-stu-id="379ee-149">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="379ee-150">I Exchange Management PowerShell kan du skapa en ny journal regel för organisationen:</span><span class="sxs-lookup"><span data-stu-id="379ee-150">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. <span data-ttu-id="379ee-151">Visa fel meddelandet "otillräcklig behörighet" i Exchange Management PowerShell:</span><span class="sxs-lookup"><span data-stu-id="379ee-151">View "Insufficient permissions" error in Exchange Management PowerShell:</span></span>

```ExchangeManagementPowerShell
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="379ee-152">Begära åtkomst för att skapa en ny journal regel med den nya-JournalRule-uppgiften</span><span class="sxs-lookup"><span data-stu-id="379ee-152">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="379ee-153">Logga in i [administrations centret för Microsoft 365](https://admin.microsoft.com) med det globala administratörs kontot för test miljön.</span><span class="sxs-lookup"><span data-stu-id="379ee-153">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="379ee-154">I administrations centret går du till **Inställningar**  >  **säkerhet & integritet**  >  **privilegie rad åtkomst**.</span><span class="sxs-lookup"><span data-stu-id="379ee-154">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="379ee-155">Välj **Hantera åtkomst principer och begär Anden**.</span><span class="sxs-lookup"><span data-stu-id="379ee-155">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="379ee-156">Välj **ny begäran**.</span><span class="sxs-lookup"><span data-stu-id="379ee-156">Select **New request**.</span></span> <span data-ttu-id="379ee-157">Välj lämpliga värden för din organisation i list rutan:</span><span class="sxs-lookup"><span data-stu-id="379ee-157">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="379ee-158">**Begäran**: uppgift</span><span class="sxs-lookup"><span data-stu-id="379ee-158">**Request type**: Task</span></span>

    <span data-ttu-id="379ee-159">**Begärans omfattning**: Exchange</span><span class="sxs-lookup"><span data-stu-id="379ee-159">**Request scope**: Exchange</span></span>

    <span data-ttu-id="379ee-160">**Begäran om**ny journal regel</span><span class="sxs-lookup"><span data-stu-id="379ee-160">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="379ee-161">**Varaktighet (timmar)**: 2</span><span class="sxs-lookup"><span data-stu-id="379ee-161">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="379ee-162">**Kommentar**: begära behörighet att skapa en ny journal regel</span><span class="sxs-lookup"><span data-stu-id="379ee-162">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="379ee-163">Välj **Spara** och sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="379ee-163">Select **Save** and then **Close**.</span></span> <span data-ttu-id="379ee-164">Din begäran skickas till gruppen god kännare via e-post.</span><span class="sxs-lookup"><span data-stu-id="379ee-164">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="379ee-165">Godkänn behörig åtkomstbegäran för att skapa en ny journal regel</span><span class="sxs-lookup"><span data-stu-id="379ee-165">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="379ee-166">Logga in i [administrations centret för Microsoft 365](https://admin.microsoft.com) med hjälp av autentiseringsuppgifterna för användare 3 i test miljön (medlem i säkerhets gruppen "privilegie rad god kännare" i test miljön).</span><span class="sxs-lookup"><span data-stu-id="379ee-166">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="379ee-167">I administrations centret går du till **Inställningar**  >  **säkerhet & integritet**  >  **privilegie rad åtkomst**.</span><span class="sxs-lookup"><span data-stu-id="379ee-167">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="379ee-168">Välj **Hantera åtkomst principer och begär Anden**.</span><span class="sxs-lookup"><span data-stu-id="379ee-168">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="379ee-169">Välj den väntande begäran och välj **Godkänn** för att bevilja åtkomst till det globala administratörs kontot för att skapa en ny journal regel.</span><span class="sxs-lookup"><span data-stu-id="379ee-169">Select the pending request and select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="379ee-170">Ett e-postmeddelande som bekräftar att godkännandet kommer att skickas till det globala administratörs kontot (den användare som begär detta).</span><span class="sxs-lookup"><span data-stu-id="379ee-170">A notification email confirming that approval has been granted will be sent to the Global Admin account (the requesting user).</span></span>  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="379ee-171">Testa att skapa en ny journal regel med behörig åtkomst godkänd för den nya-JournalRule-aktiviteten</span><span class="sxs-lookup"><span data-stu-id="379ee-171">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="379ee-172">På din lokala dator öppnar du och loggar in på Exchange Online Remote PowerShell-modulen på **Microsoft Corporation**  >  **Microsoft Exchange Online Remote PowerShell module** med det globala administratörs kontot för test miljön.</span><span class="sxs-lookup"><span data-stu-id="379ee-172">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="379ee-173">I Exchange Management PowerShell kan du skapa en ny journal regel för organisationen:</span><span class="sxs-lookup"><span data-stu-id="379ee-173">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. <span data-ttu-id="379ee-174">Visa att den nya Journal regeln skapades i Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="379ee-174">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="379ee-175">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="379ee-175">Next step</span></span>

<span data-ttu-id="379ee-176">Utforska ytterligare funktioner för [informations skydd](m365-enterprise-test-lab-guides.md#information-protection) i test miljön.</span><span class="sxs-lookup"><span data-stu-id="379ee-176">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="379ee-177">Se även</span><span class="sxs-lookup"><span data-stu-id="379ee-177">See also</span></span>

[<span data-ttu-id="379ee-178">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="379ee-178">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="379ee-179">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="379ee-179">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="379ee-180">Microsoft 365 för företags dokumentation</span><span class="sxs-lookup"><span data-stu-id="379ee-180">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
