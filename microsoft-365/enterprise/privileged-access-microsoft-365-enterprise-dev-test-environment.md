---
title: Privilegierad åtkomsthantering för din Testmiljö för Microsoft 365 Enterprise
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
description: Använd den här testlabbguiden för att aktivera privilegierad åtkomsthantering din Testmiljö för Microsoft 365 Enterprise.
ms.openlocfilehash: ce637b94333f088d25e479e61ad2a98176a2f7c6
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806778"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="3bd27-103">Privilegierad åtkomsthantering för din Testmiljö för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="3bd27-103">Privileged access management for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="3bd27-104">*Den här testlabbguiden kan användas för både testmiljöer för Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="3bd27-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="3bd27-105">Med instruktionerna i den här artikeln konfigurerar du privilegierad åtkomsthantering för att öka säkerheten i din Testmiljö för Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="3bd27-105">With the instructions in this article, you configure privileged access management to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Testa labbguider för Microsoft-molnet](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

>[!TIP]
><span data-ttu-id="3bd27-107">Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) för en visuell karta till alla artiklar i Microsoft 365 Enterprise Test Lab Guide stacken.</span><span class="sxs-lookup"><span data-stu-id="3bd27-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="3bd27-108">Fas 1: Bygg upp din Testmiljö för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="3bd27-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="3bd27-109">Om du bara vill konfigurera privilegierad åtkomsthantering på ett lättsätt med minimikraven följer du instruktionerna i [Lightweight-baskonfigurationen](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="3bd27-109">If you just want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="3bd27-110">Om du vill konfigurera privilegierad åtkomsthantering i ett simulerat företag följer du instruktionerna i [direktautentisering](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="3bd27-110">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
>[!NOTE]
><span data-ttu-id="3bd27-111">Testning av privilegierad åtkomsthantering kräver inte den simulerade företagstestmiljön, som innehåller ett simulerat intranät som är anslutet till Internet- och katalogsynkroniseringen för en AD DS-skog.</span><span class="sxs-lookup"><span data-stu-id="3bd27-111">Testing privileged access management does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an AD DS forest.</span></span> <span data-ttu-id="3bd27-112">Det finns här som ett alternativ så att du kan testa privilegierad åtkomsthantering och experimentera med den i en miljö som representerar en typisk organisation.</span><span class="sxs-lookup"><span data-stu-id="3bd27-112">It is provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="3bd27-113">Fas 2: Konfigurera hantering av privilegierad åtkomst</span><span class="sxs-lookup"><span data-stu-id="3bd27-113">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="3bd27-114">I den här fasen konfigurerar du en grupp för godkännare och aktiverar privilegierad åtkomsthantering för din Testmiljö för Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="3bd27-114">In this phase, you configure an approvers group and enable privileged access management for your Microsoft 365 Enterprise test environment.</span></span> <span data-ttu-id="3bd27-115">Mer information och en översikt över hantering av privilegierad åtkomst finns [i Privilegierad åtkomsthantering i Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span><span class="sxs-lookup"><span data-stu-id="3bd27-115">For additional details and an overview of privileged access management, see [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span></span>

<span data-ttu-id="3bd27-116">Följ de här stegen för att konfigurera och använda privilegierad åtkomst i din Office 365-organisation:</span><span class="sxs-lookup"><span data-stu-id="3bd27-116">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="3bd27-117">Steg 1: Skapa en godkännares grupp</span><span class="sxs-lookup"><span data-stu-id="3bd27-117">Step 1: Create an approver's group</span></span>](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-1-create-an-approvers-group)

    <span data-ttu-id="3bd27-118">Innan du börjar använda behörighetsåtkomst bör du bestämma vem som ska ha godkännandebehörighet för inkommande begäranden om åtkomst till upphöjda och privilegierade uppgifter.</span><span class="sxs-lookup"><span data-stu-id="3bd27-118">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="3bd27-119">Alla användare som ingår i gruppen Godkännare kan godkänna åtkomstbegäranden.</span><span class="sxs-lookup"><span data-stu-id="3bd27-119">Any user who is part of the Approvers’ group will be able to approve access requests.</span></span> <span data-ttu-id="3bd27-120">Detta aktiveras genom att skapa en e-postaktiverad säkerhetsgrupp i Office 365.</span><span class="sxs-lookup"><span data-stu-id="3bd27-120">This is enabled by creating a mail-enabled security group in Office 365.</span></span> <span data-ttu-id="3bd27-121">Skapa en ny säkerhetsgrupp med namnet "Privileged Access Godkännare" i testmiljön och lägg till "Användare 3" som tidigare har skapats i tidigare testlabbguidesteg.</span><span class="sxs-lookup"><span data-stu-id="3bd27-121">Create a new security group named "Privileged Access Approvers" in your test environment and add the "User 3" previously created in prior test lab guide steps.</span></span>

- [<span data-ttu-id="3bd27-122">Steg 2: Aktivera privilegierad åtkomst</span><span class="sxs-lookup"><span data-stu-id="3bd27-122">Step 2: Enable privileged access</span></span>](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-2-enable-privileged-access)

    <span data-ttu-id="3bd27-123">Privilegierad åtkomst måste uttryckligen aktiveras i Office 365 med standardgodkännargruppen och inkludera en uppsättning systemkonton som du vill ska uteslutas från den privilegierade åtkomståtkomstkontrollen för åtkomsthantering.</span><span class="sxs-lookup"><span data-stu-id="3bd27-123">Privileged access needs to be explicitly turned on in Office 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control.</span></span> <span data-ttu-id="3bd27-124">Var noga med att aktivera privilegierad åtkomst i din Office 365-organisation innan du startar fas 3 i den här guiden.</span><span class="sxs-lookup"><span data-stu-id="3bd27-124">Be sure to enable privileged access in your Office 365 organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="3bd27-125">Fas 3: Kontrollera att godkännande krävs för förhöjda och privilegierade uppgifter</span><span class="sxs-lookup"><span data-stu-id="3bd27-125">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="3bd27-126">I den här fasen kontrollerar du att principen för privilegierad åtkomst fungerar och att användarna behöver godkännande för att utföra definierade förhöjda och privilegierade uppgifter.</span><span class="sxs-lookup"><span data-stu-id="3bd27-126">In this phase, you verify that the privileged access policy is working and users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="3bd27-127">Testförmåga att utföra en uppgift SOM INTE har definierats i en principiär åtkomst</span><span class="sxs-lookup"><span data-stu-id="3bd27-127">Test ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="3bd27-128">Anslut först till Exchange Management PowerShell med autentiseringsuppgifterna för en användare som konfigurerats som global administratör i testmiljön och försök skapa en ny journalregel.</span><span class="sxs-lookup"><span data-stu-id="3bd27-128">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="3bd27-129">Aktiviteten [Ny journalregel](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) definieras för närvarande inte i en princip för privilegierad åtkomst för din organisation.</span><span class="sxs-lookup"><span data-stu-id="3bd27-129">The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="3bd27-130">Öppna och logga in på Exchange Online Remote PowerShell Module på **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** med hjälp av det globala administratörskontot för testmiljön.</span><span class="sxs-lookup"><span data-stu-id="3bd27-130">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="3bd27-131">Skapa en ny journalregel för din organisation i Exchange Management PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3bd27-131">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```

4. <span data-ttu-id="3bd27-132">Se att den nya journalregeln har skapats i Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3bd27-132">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="3bd27-133">Skapa en ny princip för privilegierad åtkomst för aktiviteten Ny journalregel</span><span class="sxs-lookup"><span data-stu-id="3bd27-133">Create a new privileged access policy for the New-JournalRule task</span></span>

>[!NOTE]
><span data-ttu-id="3bd27-134">Om du inte redan har slutfört steg 1 och 2 från fas 2 i den här guiden måste du följa stegen för att skapa en godkännares grupp med namnet "Privilege Access Godkännare" och för att aktivera privilegierad åtkomst i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="3bd27-134">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" and to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="3bd27-135">Logga in på [administrationscentret för Microsoft 365](https://admin.microsoft.com) med hjälp av autentiseringsuppgifter för global administratörskonto för testmiljön.</span><span class="sxs-lookup"><span data-stu-id="3bd27-135">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="3bd27-136">Gå till **Inställningar** > **sÃ & Sekretessprivilegierad** > **åtkomst**i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="3bd27-136">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="3bd27-137">Välj **Hantera åtkomstprinciper och begäranden**.</span><span class="sxs-lookup"><span data-stu-id="3bd27-137">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="3bd27-138">Välj **Konfigurera principer** och välj Lägg till en **princip**.</span><span class="sxs-lookup"><span data-stu-id="3bd27-138">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="3bd27-139">Markera eller ange följande värden i listrutan:</span><span class="sxs-lookup"><span data-stu-id="3bd27-139">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="3bd27-140">**Principtyp**: Aktivitet</span><span class="sxs-lookup"><span data-stu-id="3bd27-140">**Policy type**: Task</span></span>

    <span data-ttu-id="3bd27-141">**Policyomfattning**: Utbyte</span><span class="sxs-lookup"><span data-stu-id="3bd27-141">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="3bd27-142">**Principnamn**: Ny journalregel</span><span class="sxs-lookup"><span data-stu-id="3bd27-142">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="3bd27-143">**Typgodkännandetyp**: Manuell</span><span class="sxs-lookup"><span data-stu-id="3bd27-143">**Approval type**: Manual</span></span>

    <span data-ttu-id="3bd27-144">**Godkännandegrupp**: Privilegierade åtkomstgodkännare</span><span class="sxs-lookup"><span data-stu-id="3bd27-144">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="3bd27-145">Välj **Skapa** och **stäng**sedan .</span><span class="sxs-lookup"><span data-stu-id="3bd27-145">Select **Create** and then **Close**.</span></span> <span data-ttu-id="3bd27-146">Det kan ta några minuter innan principen är helt konfigurerad och aktiverad.</span><span class="sxs-lookup"><span data-stu-id="3bd27-146">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="3bd27-147">Var noga med att ge tid för principen att aktiveras fullt ut innan godkännandekravet testas i nästa steg.</span><span class="sxs-lookup"><span data-stu-id="3bd27-147">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="3bd27-148">Krav på testgodkännande för aktiviteten Ny journalregel som definierats i en privilegierad åtkomstprincip</span><span class="sxs-lookup"><span data-stu-id="3bd27-148">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="3bd27-149">Öppna och logga in på Exchange Online Remote PowerShell Module på **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** med hjälp av det globala administratörskontot för testmiljön.</span><span class="sxs-lookup"><span data-stu-id="3bd27-149">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="3bd27-150">Skapa en ny journalregel för din organisation i Exchange Management PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3bd27-150">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. <span data-ttu-id="3bd27-151">Visa felet "Otillräckliga behörigheter" i Exchange Management PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3bd27-151">View "Insufficient permissions" error in Exchange Management PowerShell:</span></span>

```ExchangeManagementPowerShell
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="3bd27-152">Begär åtkomst för att skapa en ny journalregel med aktiviteten New JournalRule</span><span class="sxs-lookup"><span data-stu-id="3bd27-152">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="3bd27-153">Logga in på [administrationscentret för Microsoft 365](https://admin.microsoft.com) med hjälp av det globala administratörskontot för testmiljön.</span><span class="sxs-lookup"><span data-stu-id="3bd27-153">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="3bd27-154">Gå till **Inställningar** > **sÃ & Sekretessprivilegierad** > **åtkomst**i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="3bd27-154">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="3bd27-155">Välj **Hantera åtkomstprinciper och begäranden**.</span><span class="sxs-lookup"><span data-stu-id="3bd27-155">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="3bd27-156">Välj **Ny begäran**.</span><span class="sxs-lookup"><span data-stu-id="3bd27-156">Select **New request**.</span></span> <span data-ttu-id="3bd27-157">Välj lämpliga värden för organisationen i listrutan:</span><span class="sxs-lookup"><span data-stu-id="3bd27-157">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="3bd27-158">**Typ av begäran:** Uppgift</span><span class="sxs-lookup"><span data-stu-id="3bd27-158">**Request type**: Task</span></span>

    <span data-ttu-id="3bd27-159">**Ärende :** Exchange</span><span class="sxs-lookup"><span data-stu-id="3bd27-159">**Request scope**: Exchange</span></span>

    <span data-ttu-id="3bd27-160">**Begäran om**: Ny journalregel</span><span class="sxs-lookup"><span data-stu-id="3bd27-160">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="3bd27-161">**Varaktighet (timmar)**: 2</span><span class="sxs-lookup"><span data-stu-id="3bd27-161">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="3bd27-162">**Kommentarer**: Begär behörighet att skapa en ny journalregel</span><span class="sxs-lookup"><span data-stu-id="3bd27-162">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="3bd27-163">Välj **Spara** och **stäng**sedan .</span><span class="sxs-lookup"><span data-stu-id="3bd27-163">Select **Save** and then **Close**.</span></span> <span data-ttu-id="3bd27-164">Din begäran kommer att skickas till godkännarens grupp via e-post.</span><span class="sxs-lookup"><span data-stu-id="3bd27-164">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="3bd27-165">Godkänna begäran om privilegierad åtkomst för att skapa en ny journalregel</span><span class="sxs-lookup"><span data-stu-id="3bd27-165">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="3bd27-166">Logga in på [administrationscentret för Microsoft 365](https://admin.microsoft.com) med hjälp av autentiseringsuppgifterna för användare 3 i testmiljön (medlem i säkerhetsgruppen Privilegierad åtkomst godkännare i testmiljön).</span><span class="sxs-lookup"><span data-stu-id="3bd27-166">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="3bd27-167">Gå till **Inställningar** > **sÃ & Sekretessprivilegierad** > **åtkomst**i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="3bd27-167">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="3bd27-168">Välj **Hantera åtkomstprinciper och begäranden**.</span><span class="sxs-lookup"><span data-stu-id="3bd27-168">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="3bd27-169">Välj väntande begäran och välj **Godkänn** om du vill bevilja åtkomst till det globala administratörskontot för att skapa en ny journalregel.</span><span class="sxs-lookup"><span data-stu-id="3bd27-169">Select the pending request and select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="3bd27-170">Ett e-postmeddelande som bekräftar att godkännande har beviljats kommer att skickas till det globala administratörskontot (den begärande användaren).</span><span class="sxs-lookup"><span data-stu-id="3bd27-170">A notification email confirming that approval has been granted will be sent to the Global Admin account (the requesting user).</span></span>  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="3bd27-171">Testa att skapa en ny journalregel med privilegierad åtkomst som godkänts för aktiviteten New JournalRule</span><span class="sxs-lookup"><span data-stu-id="3bd27-171">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="3bd27-172">Öppna och logga in på Exchange Online Remote PowerShell Module på **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** med hjälp av det globala administratörskontot för testmiljön.</span><span class="sxs-lookup"><span data-stu-id="3bd27-172">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="3bd27-173">Skapa en ny journalregel för din organisation i Exchange Management PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3bd27-173">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. <span data-ttu-id="3bd27-174">Se att den nya journalregeln har skapats i Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3bd27-174">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="3bd27-175">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="3bd27-175">Next step</span></span>

<span data-ttu-id="3bd27-176">Utforska ytterligare [funktioner för informationsskydd](m365-enterprise-test-lab-guides.md#information-protection) i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="3bd27-176">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="3bd27-177">Se även</span><span class="sxs-lookup"><span data-stu-id="3bd27-177">See also</span></span>

[<span data-ttu-id="3bd27-178">Labbguider för Microsoft 365 Enterprise Test</span><span class="sxs-lookup"><span data-stu-id="3bd27-178">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="3bd27-179">Distribuera Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="3bd27-179">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="3bd27-180">Dokumentation för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="3bd27-180">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
