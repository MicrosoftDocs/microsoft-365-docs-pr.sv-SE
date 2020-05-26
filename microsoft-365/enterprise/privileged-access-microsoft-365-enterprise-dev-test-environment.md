---
title: Hantering av privilegierad åtkomst för microsoft 365 Enterprise-testmiljön
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
description: Använd den här testlabbet-guiden om du vill aktivera hantering av privilegierad åtkomst din Microsoft 365 Enterprise-testmiljö.
ms.openlocfilehash: 1a81c62124177a328209f175262ac13455ca0899
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352528"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="4fbbb-103">Hantering av privilegierad åtkomst för microsoft 365 Enterprise-testmiljön</span><span class="sxs-lookup"><span data-stu-id="4fbbb-103">Privileged access management for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="4fbbb-104">*Den här testlabbguiden kan användas i både Microsoft 365 Enterprise- och Office 365 Enterprise-testmiljöer.*</span><span class="sxs-lookup"><span data-stu-id="4fbbb-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="4fbbb-105">Med instruktionerna i den här artikeln konfigurerar du hantering av privilegierad åtkomst för att öka säkerheten i microsoft 365 Enterprise-testmiljön.</span><span class="sxs-lookup"><span data-stu-id="4fbbb-105">With the instructions in this article, you configure privileged access management to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

>[!TIP]
><span data-ttu-id="4fbbb-107">Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med Microsoft 365 Enterprise-testlabbguider.</span><span class="sxs-lookup"><span data-stu-id="4fbbb-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="4fbbb-108">Fas 1: Bygga ut testmiljön i Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4fbbb-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="4fbbb-109">Om du bara vill konfigurera hantering av privilegierad åtkomst på ett lättviktssätt med minimikraven följer du instruktionerna i [Lightweight base-konfigurationen](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="4fbbb-109">If you just want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="4fbbb-110">Om du vill konfigurera hantering av privilegierad åtkomst i ett simulerat företag följer du instruktionerna i [Direktautentisering](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="4fbbb-110">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
>[!NOTE]
><span data-ttu-id="4fbbb-111">Testning av privilegierad åtkomsthantering kräver inte den simulerade företagstestmiljön, som innehåller ett simulerat intranät som är anslutet till Internet och katalogsynkronisering för en AD DS-skog.</span><span class="sxs-lookup"><span data-stu-id="4fbbb-111">Testing privileged access management does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an AD DS forest.</span></span> <span data-ttu-id="4fbbb-112">Det finns här som ett alternativ så att du kan testa privilegierad åtkomsthantering och experimentera med den i en miljö som representerar en typisk organisation.</span><span class="sxs-lookup"><span data-stu-id="4fbbb-112">It is provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="4fbbb-113">Fas 2: Konfigurera hantering av privilegierad åtkomst</span><span class="sxs-lookup"><span data-stu-id="4fbbb-113">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="4fbbb-114">I den här fasen konfigurerar du en godkännaregrupp och aktiverar hantering av privilegierad åtkomst för microsoft 365 Enterprise-testmiljön.</span><span class="sxs-lookup"><span data-stu-id="4fbbb-114">In this phase, you configure an approvers group and enable privileged access management for your Microsoft 365 Enterprise test environment.</span></span> <span data-ttu-id="4fbbb-115">Mer information och en översikt över hantering av privilegierad åtkomst finns i Hantering av [privilegierad åtkomst i Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span><span class="sxs-lookup"><span data-stu-id="4fbbb-115">For additional details and an overview of privileged access management, see [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span></span>

<span data-ttu-id="4fbbb-116">Så här konfigurerar och använder du privilegierad åtkomst i organisationen:</span><span class="sxs-lookup"><span data-stu-id="4fbbb-116">Follow these steps to set up and use privileged access in your organization:</span></span>

- [<span data-ttu-id="4fbbb-117">Steg 1: Skapa en godkännargrupp</span><span class="sxs-lookup"><span data-stu-id="4fbbb-117">Step 1: Create an approver's group</span></span>](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-1-create-an-approvers-group)

    <span data-ttu-id="4fbbb-118">Innan du börjar använda behörighetsåtkomst bör du bestämma vem som har godkännandebehörighet för inkommande begäranden om åtkomst till förhöjda och privilegierade uppgifter.</span><span class="sxs-lookup"><span data-stu-id="4fbbb-118">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="4fbbb-119">Alla användare som ingår i gruppen Godkännare kan godkänna åtkomstbegäranden.</span><span class="sxs-lookup"><span data-stu-id="4fbbb-119">Any user who is part of the Approvers’ group will be able to approve access requests.</span></span> <span data-ttu-id="4fbbb-120">Detta aktiveras genom att skapa en e-postaktiverad säkerhetsgrupp i Office 365.</span><span class="sxs-lookup"><span data-stu-id="4fbbb-120">This is enabled by creating a mail-enabled security group in Office 365.</span></span> <span data-ttu-id="4fbbb-121">Skapa en ny säkerhetsgrupp med namnet "Privileged Access Approvers" i testmiljön och lägg till "Användare 3" som tidigare skapats i tidigare testlabbguidesteg.</span><span class="sxs-lookup"><span data-stu-id="4fbbb-121">Create a new security group named "Privileged Access Approvers" in your test environment and add the "User 3" previously created in prior test lab guide steps.</span></span>

- [<span data-ttu-id="4fbbb-122">Steg 2: Aktivera privilegierad åtkomst</span><span class="sxs-lookup"><span data-stu-id="4fbbb-122">Step 2: Enable privileged access</span></span>](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-2-enable-privileged-access)

    <span data-ttu-id="4fbbb-123">Privilegierad åtkomst måste uttryckligen aktiveras i Office 365 med standardgodkärörsgruppen och inkludera en uppsättning systemkonton som du vill ska uteslutas från åtkomstkontrollen för privilegierad åtkomsthantering.</span><span class="sxs-lookup"><span data-stu-id="4fbbb-123">Privileged access needs to be explicitly turned on in Office 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control.</span></span> <span data-ttu-id="4fbbb-124">Var noga med att aktivera privilegierad åtkomst i organisationen innan fas 3 i den här guiden startas.</span><span class="sxs-lookup"><span data-stu-id="4fbbb-124">Be sure to enable privileged access in your organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="4fbbb-125">Fas 3: Kontrollera att godkännande krävs för förhöjda och privilegierade uppgifter</span><span class="sxs-lookup"><span data-stu-id="4fbbb-125">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="4fbbb-126">I den här fasen kontrollerar du att principen för privilegierad åtkomst fungerar och att användare kräver godkännande för att utföra definierade förhöjda och privilegierade uppgifter.</span><span class="sxs-lookup"><span data-stu-id="4fbbb-126">In this phase, you verify that the privileged access policy is working and users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="4fbbb-127">Testförmåga att utföra en uppgift SOM INTE har definierats i en privilegierad åtkomstprincip</span><span class="sxs-lookup"><span data-stu-id="4fbbb-127">Test ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="4fbbb-128">Anslut först till Exchange Management PowerShell med autentiseringsuppgifterna för en användare som konfigurerats som global administratör i testmiljön och försök skapa en ny journalregel.</span><span class="sxs-lookup"><span data-stu-id="4fbbb-128">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="4fbbb-129">[Aktiviteten Ny journalRule](https://docs.microsoft.com/powershell/module/exchange/new-journalrule?view=exchange-ps) har för närvarande inte definierats i en privilegierad åtkomstprincip för din organisation.</span><span class="sxs-lookup"><span data-stu-id="4fbbb-129">The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/new-journalrule?view=exchange-ps) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="4fbbb-130">Öppna och logga in på Exchange Online Remote PowerShell-modulen på **Microsoft Corporation**Microsoft Exchange Online Remote PowerShell Module på den lokala datorn  >  **Microsoft Exchange Online Remote PowerShell Module** med hjälp av det globala administratörskontot för din testmiljö.</span><span class="sxs-lookup"><span data-stu-id="4fbbb-130">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="4fbbb-131">Skapa en ny journalregel för din organisation i PowerShell för Exchange Management:</span><span class="sxs-lookup"><span data-stu-id="4fbbb-131">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```

4. <span data-ttu-id="4fbbb-132">Visa att den nya journalregeln har skapats i PowerShell för Exchange Management.</span><span class="sxs-lookup"><span data-stu-id="4fbbb-132">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="4fbbb-133">Skapa en ny princip för privilegierad åtkomst för aktiviteten Ny journalregel</span><span class="sxs-lookup"><span data-stu-id="4fbbb-133">Create a new privileged access policy for the New-JournalRule task</span></span>

>[!NOTE]
><span data-ttu-id="4fbbb-134">Om du inte redan har slutfört steg 1 och 2 från fas 2 i den här guiden måste du följa stegen för att skapa en godkännares grupp med namnet "Privilege Access Approvers" och aktivera privilegierad åtkomst i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="4fbbb-134">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" and to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="4fbbb-135">Logga in på [Microsoft 365-administrationscentret](https://admin.microsoft.com) med autentiseringsuppgifterna för det globala administratörskontot för testmiljön.</span><span class="sxs-lookup"><span data-stu-id="4fbbb-135">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="4fbbb-136">Gå till **Inställningar**  >  **&**  >  **sekretessbehörighet i**administrationscentret .</span><span class="sxs-lookup"><span data-stu-id="4fbbb-136">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="4fbbb-137">Välj **Hantera åtkomstprinciper och begäranden**.</span><span class="sxs-lookup"><span data-stu-id="4fbbb-137">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="4fbbb-138">Välj **Konfigurera principer** och välj Lägg till en **princip**.</span><span class="sxs-lookup"><span data-stu-id="4fbbb-138">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="4fbbb-139">Markera eller ange följande värden i listrutan:</span><span class="sxs-lookup"><span data-stu-id="4fbbb-139">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="4fbbb-140">**Principtyp**: Uppgift</span><span class="sxs-lookup"><span data-stu-id="4fbbb-140">**Policy type**: Task</span></span>

    <span data-ttu-id="4fbbb-141">**Policyomfattning**: Exchange</span><span class="sxs-lookup"><span data-stu-id="4fbbb-141">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="4fbbb-142">**Policynamn**: Ny journalregel</span><span class="sxs-lookup"><span data-stu-id="4fbbb-142">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="4fbbb-143">**Typ av godkännande**: Manuell</span><span class="sxs-lookup"><span data-stu-id="4fbbb-143">**Approval type**: Manual</span></span>

    <span data-ttu-id="4fbbb-144">**Godkännandegrupp**: Privilegierade åtkomstgodkännare</span><span class="sxs-lookup"><span data-stu-id="4fbbb-144">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="4fbbb-145">Välj **Skapa** och **stäng**sedan .</span><span class="sxs-lookup"><span data-stu-id="4fbbb-145">Select **Create** and then **Close**.</span></span> <span data-ttu-id="4fbbb-146">Det kan ta några minuter innan principen konfigureras och aktiveras helt.</span><span class="sxs-lookup"><span data-stu-id="4fbbb-146">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="4fbbb-147">Var noga med att ge tid för principen att vara fullt aktiverad innan du testar godkännandekravet i nästa steg.</span><span class="sxs-lookup"><span data-stu-id="4fbbb-147">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="4fbbb-148">Testgodkännandekrav för den new-journalRule-uppgift som definierats i en princip för privilegierad åtkomst</span><span class="sxs-lookup"><span data-stu-id="4fbbb-148">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="4fbbb-149">Öppna och logga in på Exchange Online Remote PowerShell-modulen på **Microsoft Corporation**Microsoft Exchange Online Remote PowerShell Module på den lokala datorn  >  **Microsoft Exchange Online Remote PowerShell Module** med hjälp av ett globalt administratörskonto för din testmiljö.</span><span class="sxs-lookup"><span data-stu-id="4fbbb-149">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="4fbbb-150">Skapa en ny journalregel för din organisation i PowerShell för Exchange Management:</span><span class="sxs-lookup"><span data-stu-id="4fbbb-150">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. <span data-ttu-id="4fbbb-151">Visa felet "Otillräckliga behörigheter" i PowerShell för Exchange Management:</span><span class="sxs-lookup"><span data-stu-id="4fbbb-151">View "Insufficient permissions" error in Exchange Management PowerShell:</span></span>

```ExchangeManagementPowerShell
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="4fbbb-152">Begär åtkomst för att skapa en ny journalregel med uppgift Ny journalregel</span><span class="sxs-lookup"><span data-stu-id="4fbbb-152">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="4fbbb-153">Logga in på [Microsoft 365-administrationscentret](https://admin.microsoft.com) med hjälp av det globala administratörskontot för testmiljön.</span><span class="sxs-lookup"><span data-stu-id="4fbbb-153">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="4fbbb-154">Gå till **Inställningar**  >  **&**  >  **sekretessbehörighet i**administrationscentret .</span><span class="sxs-lookup"><span data-stu-id="4fbbb-154">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="4fbbb-155">Välj **Hantera åtkomstprinciper och begäranden**.</span><span class="sxs-lookup"><span data-stu-id="4fbbb-155">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="4fbbb-156">Välj **Ny begäran**.</span><span class="sxs-lookup"><span data-stu-id="4fbbb-156">Select **New request**.</span></span> <span data-ttu-id="4fbbb-157">Välj lämpliga värden för din organisation i listrutan:</span><span class="sxs-lookup"><span data-stu-id="4fbbb-157">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="4fbbb-158">**Typ av begäran**: Uppgift</span><span class="sxs-lookup"><span data-stu-id="4fbbb-158">**Request type**: Task</span></span>

    <span data-ttu-id="4fbbb-159">**Omfattning för begäran:** Exchange</span><span class="sxs-lookup"><span data-stu-id="4fbbb-159">**Request scope**: Exchange</span></span>

    <span data-ttu-id="4fbbb-160">**Begäran om**: Ny journalregel</span><span class="sxs-lookup"><span data-stu-id="4fbbb-160">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="4fbbb-161">**Varaktighet (timmar):** 2</span><span class="sxs-lookup"><span data-stu-id="4fbbb-161">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="4fbbb-162">**Kommentarer**: Begär behörighet att skapa en ny journalregel</span><span class="sxs-lookup"><span data-stu-id="4fbbb-162">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="4fbbb-163">Välj **Spara** och **stäng**sedan .</span><span class="sxs-lookup"><span data-stu-id="4fbbb-163">Select **Save** and then **Close**.</span></span> <span data-ttu-id="4fbbb-164">Din begäran kommer att skickas till godkännarens grupp via e-post.</span><span class="sxs-lookup"><span data-stu-id="4fbbb-164">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="4fbbb-165">Godkänna begäran om privilegierad åtkomst för att skapa en ny journalregel</span><span class="sxs-lookup"><span data-stu-id="4fbbb-165">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="4fbbb-166">Logga in på [Microsoft 365-administrationscentret](https://admin.microsoft.com) med autentiseringsuppgifterna för Användare 3 i testmiljön (medlem i säkerhetsgruppen "Privilegierade åtkomstgodtagare" i testmiljön).</span><span class="sxs-lookup"><span data-stu-id="4fbbb-166">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="4fbbb-167">Gå till **Inställningar**  >  **&**  >  **sekretessbehörighet i**administrationscentret .</span><span class="sxs-lookup"><span data-stu-id="4fbbb-167">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="4fbbb-168">Välj **Hantera åtkomstprinciper och begäranden**.</span><span class="sxs-lookup"><span data-stu-id="4fbbb-168">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="4fbbb-169">Välj den väntande begäran och välj **Godkänn** om du vill bevilja åtkomst till det globala administratörskontot för att skapa en ny journalregel.</span><span class="sxs-lookup"><span data-stu-id="4fbbb-169">Select the pending request and select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="4fbbb-170">Ett e-postmeddelande som bekräftar att godkännande har beviljats skickas till det globala administratörskontot (den begärande användaren).</span><span class="sxs-lookup"><span data-stu-id="4fbbb-170">A notification email confirming that approval has been granted will be sent to the Global Admin account (the requesting user).</span></span>  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="4fbbb-171">Testa att skapa en ny journalregel med privilegierad åtkomst godkänd för aktiviteten Ny journalregel</span><span class="sxs-lookup"><span data-stu-id="4fbbb-171">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="4fbbb-172">Öppna och logga in på Exchange Online Remote PowerShell-modulen på **Microsoft Corporation**Microsoft Exchange Online Remote PowerShell Module på den lokala datorn  >  **Microsoft Exchange Online Remote PowerShell Module** med hjälp av det globala administratörskontot för din testmiljö.</span><span class="sxs-lookup"><span data-stu-id="4fbbb-172">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="4fbbb-173">Skapa en ny journalregel för din organisation i PowerShell för Exchange Management:</span><span class="sxs-lookup"><span data-stu-id="4fbbb-173">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. <span data-ttu-id="4fbbb-174">Visa att den nya journalregeln har skapats i PowerShell för Exchange Management.</span><span class="sxs-lookup"><span data-stu-id="4fbbb-174">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="4fbbb-175">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="4fbbb-175">Next step</span></span>

<span data-ttu-id="4fbbb-176">Utforska ytterligare funktioner och funktioner för [informationsskydd](m365-enterprise-test-lab-guides.md#information-protection) i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="4fbbb-176">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="4fbbb-177">Se även</span><span class="sxs-lookup"><span data-stu-id="4fbbb-177">See also</span></span>

[<span data-ttu-id="4fbbb-178">Testlabbguider för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4fbbb-178">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="4fbbb-179">Distribuera Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4fbbb-179">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="4fbbb-180">Microsoft 365 Enterprise-dokumentation</span><span class="sxs-lookup"><span data-stu-id="4fbbb-180">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
