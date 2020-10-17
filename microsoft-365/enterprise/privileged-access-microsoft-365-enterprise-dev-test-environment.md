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
ms.openlocfilehash: 24ca7a6408a4290c54dd2bcd7c3f6061eb8f6c05
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487594"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="c213b-103">Hantering av privilegie rad åtkomst för din test miljö för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="c213b-103">Privileged access management for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="c213b-104">*Den här test laboratorie guiden kan användas för både Microsoft 365 för företags-och Office 365 företags test miljöer.*</span><span class="sxs-lookup"><span data-stu-id="c213b-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="c213b-105">I den här artikeln beskrivs hur du konfigurerar hanteringen av behörig åtkomst för att öka säkerheten i test miljön för Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="c213b-105">This article describes how to configure privileged access management to increase security in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="c213b-106">Att konfigurera åtkomst hantering med stöd för tre faser:</span><span class="sxs-lookup"><span data-stu-id="c213b-106">Configuring priviledged access management involves three phases:</span></span>
- [<span data-ttu-id="c213b-107">Fas 1: bygga ut test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="c213b-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="c213b-108">Fas 2: Konfigurera hantering av behörig åtkomst</span><span class="sxs-lookup"><span data-stu-id="c213b-108">Phase 2: Configure privileged access management</span></span>](#phase-2-configure-privileged-access-management)
- [<span data-ttu-id="c213b-109">Fas 3: kontrol lera att godkännande krävs för förhöjda och behöriga uppgifter</span><span class="sxs-lookup"><span data-stu-id="c213b-109">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="c213b-111">Om du vill visa en visuell karta till alla artiklar i gruppen Microsoft 365 för Enterprise-testlabbet går du till [Microsoft 365 för Enterprise Test Lab-guide](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="c213b-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="c213b-112">Fas 1: bygga ut test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="c213b-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="c213b-113">Om du vill konfigurera privilegie rad åtkomst hantering på ett enkelt sätt med minimi kraven följer du anvisningarna i [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="c213b-113">If you want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="c213b-114">Om du vill konfigurera privilegie rad åtkomst hantering i ett simulerat företag följer du anvisningarna i [vidarekoppling](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="c213b-114">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
>[!NOTE]
><span data-ttu-id="c213b-115">För att testa hanteringen av privilegierade åtkomst behövs inte den simulerade företags test miljön, som innehåller ett simulerat intranät som är kopplat till Internet och Directory-synkronisering för en Active Directory Domain Services-skog.</span><span class="sxs-lookup"><span data-stu-id="c213b-115">Testing privileged access management doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services forest.</span></span> <span data-ttu-id="c213b-116">Det finns här som ett alternativ så att du kan testa hanteringen av behörig åtkomst och experimentera med den i en miljö som representerar en typisk organisation.</span><span class="sxs-lookup"><span data-stu-id="c213b-116">It's provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="c213b-117">Fas 2: Konfigurera hantering av behörig åtkomst</span><span class="sxs-lookup"><span data-stu-id="c213b-117">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="c213b-118">I den här fasen konfigurerar du en god kännare-grupp och aktiverar hantering av behörig åtkomst till din Microsoft 365 för företags test miljö.</span><span class="sxs-lookup"><span data-stu-id="c213b-118">In this phase, configure an approvers group and enable privileged access management for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="c213b-119">Mer information och en översikt över privilegierade åtkomst hantering finns i [Hantera privilegierad åtkomst](../compliance/privileged-access-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c213b-119">For additional details and an overview of privileged access management, see [Privileged access management](../compliance/privileged-access-management-overview.md).</span></span>

<span data-ttu-id="c213b-120">Utför följande steg för att konfigurera och använda privilegie rad åtkomst i organisationen.</span><span class="sxs-lookup"><span data-stu-id="c213b-120">To set up and use privileged access in your organization, perform the following steps.</span></span>

#### <a name="step-1-create-an-approvers-group"></a>[<span data-ttu-id="c213b-121">Steg 1: skapa en god kännare grupp</span><span class="sxs-lookup"><span data-stu-id="c213b-121">Step 1: Create an approver's group</span></span>](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

<span data-ttu-id="c213b-122">Innan du börjar använda privilegie rad åtkomst kan du bestämma vem som ska ha godkännande auktoritet för inkommande förfrågningar om åtkomst till förhöjda och behöriga uppgifter.</span><span class="sxs-lookup"><span data-stu-id="c213b-122">Before you start using privileged access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="c213b-123">Alla användare som ingår i gruppen god kännare kan godkänna åtkomst förfrågningar.</span><span class="sxs-lookup"><span data-stu-id="c213b-123">All users who are part of the Approvers’ group can approve access requests.</span></span> <span data-ttu-id="c213b-124">För att använda privilegie rad åtkomst måste du skapa en e-postaktive rad säkerhets grupp i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c213b-124">To use privileged access, you must create a mail-enabled security group in Microsoft 365.</span></span> <span data-ttu-id="c213b-125">I test miljön namnger du den nya säkerhets gruppen "behöriga åtkomst Godkännre" och lägger till "användare 3" som tidigare skapades i föregående test labb guide steg.</span><span class="sxs-lookup"><span data-stu-id="c213b-125">In your test environment, name the new security group "Privileged Access Approvers" and add the "User 3" that was previously created in previous test lab guide steps.</span></span>

#### <a name="step-2-enable-privileged-access"></a>[<span data-ttu-id="c213b-126">Steg 2: Aktivera privilegie rad åtkomst</span><span class="sxs-lookup"><span data-stu-id="c213b-126">Step 2: Enable privileged access</span></span>](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

<span data-ttu-id="c213b-127">Privilegie rad åtkomst måste aktive ras explicit i Microsoft 365 med standard gruppen för god kännare, och den måste innehålla en uppsättning system konton som du vill undanta från åtkomst kontrollen privilegie rad åtkomst.</span><span class="sxs-lookup"><span data-stu-id="c213b-127">Privileged access needs to be explicitly turned on in Microsoft 365 with the default approver group, and it must include a set of system accounts that you want excluded from the privileged access management access control.</span></span> <span data-ttu-id="c213b-128">Se till att aktivera privilegie rad åtkomst i organisationen innan du startar fas 3 av den här guiden.</span><span class="sxs-lookup"><span data-stu-id="c213b-128">Be sure to enable privileged access in your organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="c213b-129">Fas 3: kontrol lera att godkännande krävs för förhöjda och behöriga uppgifter</span><span class="sxs-lookup"><span data-stu-id="c213b-129">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="c213b-130">I den här fasen kontrollerar du att principen för privilegie rad åtkomst fungerar och att användarna kräver godkännande för att utföra definierade förhöjda och behöriga uppgifter.</span><span class="sxs-lookup"><span data-stu-id="c213b-130">In this phase, verify that the privileged access policy is working and that users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="c213b-131">Testa möjligheten att köra en uppgift som inte har definierats i en policy för privilegie rad åtkomst</span><span class="sxs-lookup"><span data-stu-id="c213b-131">Test the ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="c213b-132">Först ansluter du till Exchange Management PowerShell med autentiseringsuppgifterna för en användare som har kon figurer ATS som global administratör i test miljön och försöker skapa en ny journal regel.</span><span class="sxs-lookup"><span data-stu-id="c213b-132">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="c213b-133">Den [nya – JournalRule](https://docs.microsoft.com/powershell/module/exchange/new-journalrule) uppgiften är för närvarande inte definierad i en policy för privilegie rad åtkomst för organisationen.</span><span class="sxs-lookup"><span data-stu-id="c213b-133">The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/new-journalrule) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="c213b-134">På din lokala dator öppnar du och loggar in på Exchange Online Remote PowerShell-modulen på **Microsoft Corporation**  >  **Microsoft Exchange Online Remote PowerShell-modul** med det globala administratörs kontot för test miljön.</span><span class="sxs-lookup"><span data-stu-id="c213b-134">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="c213b-135">I Exchange Management PowerShell kan du skapa en ny journal regel för organisationen:</span><span class="sxs-lookup"><span data-stu-id="c213b-135">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="c213b-136">Visa att den nya Journal regeln skapades i Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c213b-136">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="c213b-137">Skapa en ny princip för privilegie rad åtkomst för New-JournalRule aktivitet</span><span class="sxs-lookup"><span data-stu-id="c213b-137">Create a new privileged access policy for the New-JournalRule task</span></span>

>[!NOTE]
><span data-ttu-id="c213b-138">Om du inte redan har slutfört steg 1 och 2 från fas 2 i den här guiden ska du läsa igenom stegen för att skapa en god kännare grupp med namnet "Privilege Access god kännare" för att aktivera privilegie rad åtkomst i test miljön.</span><span class="sxs-lookup"><span data-stu-id="c213b-138">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="c213b-139">Logga in på [administrations centret för Microsoft 365](https://admin.microsoft.com) med autentiseringsuppgifter det globala administratörs kontot för test miljön.</span><span class="sxs-lookup"><span data-stu-id="c213b-139">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="c213b-140">I administrations centret går du till **Inställningar**  >  **säkerhet & integritet**  >  **privilegie rad åtkomst**.</span><span class="sxs-lookup"><span data-stu-id="c213b-140">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="c213b-141">Välj **Hantera åtkomst principer och begär Anden**.</span><span class="sxs-lookup"><span data-stu-id="c213b-141">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="c213b-142">Välj **Konfigurera principer**och välj sedan **Lägg till en princip**.</span><span class="sxs-lookup"><span data-stu-id="c213b-142">Select **Configure policies**, and then select **Add a policy**.</span></span>

5. <span data-ttu-id="c213b-143">Välj eller ange följande värden i list rutan.</span><span class="sxs-lookup"><span data-stu-id="c213b-143">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="c213b-144">**Princip typ**: uppgift</span><span class="sxs-lookup"><span data-stu-id="c213b-144">**Policy type**: Task</span></span>

    <span data-ttu-id="c213b-145">**Princip omfattning**: Exchange</span><span class="sxs-lookup"><span data-stu-id="c213b-145">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="c213b-146">**Princip namn**: ny journal regel</span><span class="sxs-lookup"><span data-stu-id="c213b-146">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="c213b-147">**Godkännande typ**: manuell</span><span class="sxs-lookup"><span data-stu-id="c213b-147">**Approval type**: Manual</span></span>

    <span data-ttu-id="c213b-148">**Godkännande grupp**: god kännare för privilegie rad åtkomst</span><span class="sxs-lookup"><span data-stu-id="c213b-148">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="c213b-149">Välj **skapa**och sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="c213b-149">Select **Create**, and then select **Close**.</span></span> <span data-ttu-id="c213b-150">Det kan ta några minuter innan principen är fullständigt konfigurerad och aktive rad.</span><span class="sxs-lookup"><span data-stu-id="c213b-150">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="c213b-151">Se till att tiden för principen är fullständigt aktive rad innan du testar godkännande kravet i nästa steg.</span><span class="sxs-lookup"><span data-stu-id="c213b-151">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="c213b-152">Testa godkännande kravet för New-JournalRule aktivitet som definierats i en policy för privilegie rad åtkomst</span><span class="sxs-lookup"><span data-stu-id="c213b-152">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="c213b-153">På din lokala dator öppnar du och loggar in på Exchange Online Remote PowerShell-modulen på **Microsoft Corporation**  >  **Microsoft Exchange Online Remote PowerShell-modul** med ett Använd globalt administratörs konto för test miljön.</span><span class="sxs-lookup"><span data-stu-id="c213b-153">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="c213b-154">I Exchange Management PowerShell kan du skapa en ny journal regel för organisationen:</span><span class="sxs-lookup"><span data-stu-id="c213b-154">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. <span data-ttu-id="c213b-155">Se felet "otillräcklig behörighet" i Exchange Management PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c213b-155">View the "Insufficient permissions" error in Exchange Management PowerShell:</span></span>

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="c213b-156">Begära åtkomst för att skapa en ny journal regel med New-JournalRule aktivitet</span><span class="sxs-lookup"><span data-stu-id="c213b-156">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="c213b-157">Logga in på [administrations centret för Microsoft 365](https://admin.microsoft.com) med det globala administratörs kontot för test miljön.</span><span class="sxs-lookup"><span data-stu-id="c213b-157">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="c213b-158">I administrations centret går du till **Inställningar**  >  **säkerhet & integritet**  >  **privilegie rad åtkomst**.</span><span class="sxs-lookup"><span data-stu-id="c213b-158">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="c213b-159">Välj **Hantera åtkomst principer och begär Anden**.</span><span class="sxs-lookup"><span data-stu-id="c213b-159">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="c213b-160">Välj **ny begäran**.</span><span class="sxs-lookup"><span data-stu-id="c213b-160">Select **New request**.</span></span> <span data-ttu-id="c213b-161">Välj lämpliga värden för din organisation i list rutan:</span><span class="sxs-lookup"><span data-stu-id="c213b-161">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="c213b-162">**Begäran**: uppgift</span><span class="sxs-lookup"><span data-stu-id="c213b-162">**Request type**: Task</span></span>

    <span data-ttu-id="c213b-163">**Begärans omfattning**: Exchange</span><span class="sxs-lookup"><span data-stu-id="c213b-163">**Request scope**: Exchange</span></span>

    <span data-ttu-id="c213b-164">**Begäran om**ny journal regel</span><span class="sxs-lookup"><span data-stu-id="c213b-164">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="c213b-165">**Varaktighet (timmar)**: 2</span><span class="sxs-lookup"><span data-stu-id="c213b-165">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="c213b-166">**Kommentar**: begära behörighet att skapa en ny journal regel</span><span class="sxs-lookup"><span data-stu-id="c213b-166">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="c213b-167">Välj **Spara**och sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="c213b-167">Select **Save**, and then select **Close**.</span></span> <span data-ttu-id="c213b-168">Din begäran skickas till gruppen god kännare via e-post.</span><span class="sxs-lookup"><span data-stu-id="c213b-168">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="c213b-169">Godkänn behörig åtkomstbegäran för att skapa en ny journal regel</span><span class="sxs-lookup"><span data-stu-id="c213b-169">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="c213b-170">Logga in på [administrations centret för Microsoft 365](https://admin.microsoft.com) med hjälp av autentiseringsuppgifterna för användare 3 i test miljön (medlem i säkerhets gruppen "behöriga åtkomst god kännare" i test miljön).</span><span class="sxs-lookup"><span data-stu-id="c213b-170">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="c213b-171">I administrations centret går du till **Inställningar**  >  **säkerhet & integritet**  >  **privilegie rad åtkomst**.</span><span class="sxs-lookup"><span data-stu-id="c213b-171">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="c213b-172">Välj **Hantera åtkomst principer och begär Anden**.</span><span class="sxs-lookup"><span data-stu-id="c213b-172">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="c213b-173">Välj den väntande begäran och välj sedan **Godkänn** för att bevilja åtkomst till det globala administratörs kontot för att skapa en ny journal regel.</span><span class="sxs-lookup"><span data-stu-id="c213b-173">Select the pending request, and then select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="c213b-174">Det globala administratörs kontot (den användare som begär det) får ett e-postmeddelande med bekräftelse på att godkännandet har beviljats.</span><span class="sxs-lookup"><span data-stu-id="c213b-174">The Global Admin account (the requesting user) will receive an email confirmation that approval was granted.</span></span>

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="c213b-175">Testa att skapa en ny journal regel med behörig åtkomst godkänd för New-JournalRule aktiviteten</span><span class="sxs-lookup"><span data-stu-id="c213b-175">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="c213b-176">På din lokala dator öppnar du och loggar in på Exchange Online Remote PowerShell-modulen på **Microsoft Corporation**  >  **Microsoft Exchange Online Remote PowerShell-modul** med det globala administratörs kontot för test miljön.</span><span class="sxs-lookup"><span data-stu-id="c213b-176">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="c213b-177">I Exchange Management PowerShell kan du skapa en ny journal regel för organisationen:</span><span class="sxs-lookup"><span data-stu-id="c213b-177">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="c213b-178">Visa att den nya Journal regeln skapades i Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c213b-178">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="c213b-179">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="c213b-179">Next step</span></span>

<span data-ttu-id="c213b-180">Utforska ytterligare funktioner för [informations skydd](m365-enterprise-test-lab-guides.md#information-protection) i test miljön.</span><span class="sxs-lookup"><span data-stu-id="c213b-180">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="c213b-181">Se även</span><span class="sxs-lookup"><span data-stu-id="c213b-181">See also</span></span>

[<span data-ttu-id="c213b-182">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="c213b-182">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="c213b-183">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="c213b-183">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="c213b-184">Microsoft 365 för företags dokumentation</span><span class="sxs-lookup"><span data-stu-id="c213b-184">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
