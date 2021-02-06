---
title: Hantera behörighetsbehörigheter för testmiljön Microsoft 365 för företag
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
description: Använd den här testlabbguiden för att aktivera hantering av privilegierad åtkomst i testmiljön Microsoft 365 för företag.
ms.openlocfilehash: e9684ebd2aa147049dadfbda9408257ff801aff0
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126423"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="6886b-103">Hantera behörighetsbehörigheter för testmiljön Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="6886b-103">Privileged access management for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="6886b-104">*Den här testlabbguiden kan användas för både testmiljöerna Microsoft 365 för företag och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="6886b-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="6886b-105">I den här artikeln beskrivs hur du konfigurerar hantering av privilegierad åtkomst för att öka säkerheten i testmiljön Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="6886b-105">This article describes how to configure privileged access management to increase security in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="6886b-106">Konfigurering av hantering av priviled access innebär tre faser:</span><span class="sxs-lookup"><span data-stu-id="6886b-106">Configuring priviledged access management involves three phases:</span></span>
- [<span data-ttu-id="6886b-107">Fas 1: Bygg ut testmiljön Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="6886b-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="6886b-108">Fas 2: Konfigurera hantering av privilegierad åtkomst</span><span class="sxs-lookup"><span data-stu-id="6886b-108">Phase 2: Configure privileged access management</span></span>](#phase-2-configure-privileged-access-management)
- [<span data-ttu-id="6886b-109">Steg 3: Kontrollera att godkännande krävs för uppgifter med förhöjd behörighet</span><span class="sxs-lookup"><span data-stu-id="6886b-109">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="6886b-111">En visuell karta till alla artiklar i stacken med testlabbguider för Microsoft 365 för företag finns i Microsoft 365 för företags [testlabbguide.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="6886b-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="6886b-112">Fas 1: Bygg ut testmiljön Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="6886b-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="6886b-113">Om du vill konfigurera hantering av privilegierad åtkomst på ett lätt sätt med minimikraven följer du anvisningarna i Den här [grundkonfigurationen för enkel åtkomst.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="6886b-113">If you want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="6886b-114">Om du vill konfigurera hantering av behörighetsbehörighet i ett simulerat företag följer du anvisningarna i [direktautentisering.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="6886b-114">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
>[!NOTE]
><span data-ttu-id="6886b-115">Om hantering av behörighet testas krävs inte den simulerade företagstestmiljön, som omfattar ett simulerat intranät som är anslutet till Internet och katalogsynkronisering för en Active Directory DS skog.</span><span class="sxs-lookup"><span data-stu-id="6886b-115">Testing privileged access management doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services forest.</span></span> <span data-ttu-id="6886b-116">Det tillhandahålls här som ett alternativ så att du kan testa hantering av behörighet och experimentera med det i en miljö som representerar en vanlig organisation.</span><span class="sxs-lookup"><span data-stu-id="6886b-116">It's provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="6886b-117">Fas 2: Konfigurera hantering av privilegierad åtkomst</span><span class="sxs-lookup"><span data-stu-id="6886b-117">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="6886b-118">I den här fasen konfigurerar du en godkännargrupp och aktiverar hantering av privilegierad åtkomst för testmiljön Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="6886b-118">In this phase, configure an approvers group and enable privileged access management for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="6886b-119">Mer information och en översikt över hantering av privilegierad åtkomst finns i [Hantera privilegierad åtkomst.](../compliance/privileged-access-management-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6886b-119">For additional details and an overview of privileged access management, see [Privileged access management](../compliance/privileged-access-management-overview.md).</span></span>

<span data-ttu-id="6886b-120">Gör så här om du vill konfigurera och använda behörighetsbehörighet i din organisation.</span><span class="sxs-lookup"><span data-stu-id="6886b-120">To set up and use privileged access in your organization, perform the following steps.</span></span>

#### <a name="step-1-create-an-approvers-group"></a>[<span data-ttu-id="6886b-121">Steg 1: Skapa en godkännaresgrupp</span><span class="sxs-lookup"><span data-stu-id="6886b-121">Step 1: Create an approver's group</span></span>](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

<span data-ttu-id="6886b-122">Innan du börjar använda behörighet ska du bestämma vilka som ska ha behörighet för godkännande för inkommande förfrågningar om åtkomst till aktiviteter med förhöjd behörighet.</span><span class="sxs-lookup"><span data-stu-id="6886b-122">Before you start using privileged access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="6886b-123">Alla användare som ingår i godkännarnas grupp kan godkänna åtkomstförfrågningar.</span><span class="sxs-lookup"><span data-stu-id="6886b-123">All users who are part of the Approvers’ group can approve access requests.</span></span> <span data-ttu-id="6886b-124">Om du vill använda behörighet måste du skapa en e-postaktiverad säkerhetsgrupp i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6886b-124">To use privileged access, you must create a mail-enabled security group in Microsoft 365.</span></span> <span data-ttu-id="6886b-125">I testmiljön ger du den nya säkerhetsgruppen namnet "Godkännare för privilegierad åtkomst" och lägger till "Användare 3" som tidigare skapades i tidigare testlabbguider.</span><span class="sxs-lookup"><span data-stu-id="6886b-125">In your test environment, name the new security group "Privileged Access Approvers" and add the "User 3" that was previously created in previous test lab guide steps.</span></span>

#### <a name="step-2-enable-privileged-access"></a>[<span data-ttu-id="6886b-126">Steg 2: Aktivera behörighetsbehörighet</span><span class="sxs-lookup"><span data-stu-id="6886b-126">Step 2: Enable privileged access</span></span>](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

<span data-ttu-id="6886b-127">Behörighetsbehörighet måste uttryckligen aktiveras i Microsoft 365 för standard godkännaregruppen, och den måste innehålla en uppsättning systemkonton som du vill ska undantas från behörighetshanteringsåtkomstkontrollen.</span><span class="sxs-lookup"><span data-stu-id="6886b-127">Privileged access needs to be explicitly turned on in Microsoft 365 with the default approver group, and it must include a set of system accounts that you want excluded from the privileged access management access control.</span></span> <span data-ttu-id="6886b-128">Se till att aktivera privilegierad åtkomst i organisationen innan du påbörjar fas 3 i den här guiden.</span><span class="sxs-lookup"><span data-stu-id="6886b-128">Be sure to enable privileged access in your organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="6886b-129">Steg 3: Kontrollera att godkännande krävs för uppgifter med förhöjd behörighet</span><span class="sxs-lookup"><span data-stu-id="6886b-129">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="6886b-130">I den här fasen kontrollerar du att behörighetsprincipen fungerar och att användarna kräver godkännande för att utföra definierade uppgifter med förhöjd behörighet.</span><span class="sxs-lookup"><span data-stu-id="6886b-130">In this phase, verify that the privileged access policy is working and that users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="6886b-131">Testa möjligheten att utföra en uppgift SOM INTE definierats i en behörighetsbehörighetsprincip</span><span class="sxs-lookup"><span data-stu-id="6886b-131">Test the ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="6886b-132">Anslut först till Exchange Management PowerShell med autentiseringsuppgifterna för en användare som har konfigurerats som global administratör i testmiljön och försök skapa en ny journalregel.</span><span class="sxs-lookup"><span data-stu-id="6886b-132">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="6886b-133">Uppgiften [Ny journalföring är](/powershell/module/exchange/new-journalrule) för närvarande inte definierad i någon behörighetsprincip för din organisation.</span><span class="sxs-lookup"><span data-stu-id="6886b-133">The [New-JournalRule](/powershell/module/exchange/new-journalrule) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="6886b-134">Öppna och logga in på Exchange Online Remote PowerShell-modulen på din lokala dator hos **Microsoft Corporation**  >  **Microsoft Exchange Online Remote PowerShell-modulen** med det globala administratörskontot för testmiljön.</span><span class="sxs-lookup"><span data-stu-id="6886b-134">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="6886b-135">Skapa en ny journalregel för din organisation i Exchange Management PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6886b-135">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="6886b-136">Visa att den nya journalregeln har skapats i Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6886b-136">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="6886b-137">Skapa en ny behörighetsprincip för New-JournalRule behörighetsuppgift</span><span class="sxs-lookup"><span data-stu-id="6886b-137">Create a new privileged access policy for the New-JournalRule task</span></span>

>[!NOTE]
><span data-ttu-id="6886b-138">Om du inte redan har slutfört steg 1 och 2 från fas 2 i den här guiden ska du följa stegen för att skapa en godkännaresgrupp som heter "Godkännare av behörigheter" för att aktivera behörighet i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="6886b-138">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="6886b-139">Logga in på [administrationscentret för Microsoft 365](https://admin.microsoft.com) med autentiseringsuppgifter som global administratör för testmiljön.</span><span class="sxs-lookup"><span data-stu-id="6886b-139">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="6886b-140">I administrationscentret går du till Inställningar för  >  **säkerhet & behörighet för**  >  **sekretess.**</span><span class="sxs-lookup"><span data-stu-id="6886b-140">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="6886b-141">Välj **Hantera åtkomstprinciper och -begäranden.**</span><span class="sxs-lookup"><span data-stu-id="6886b-141">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="6886b-142">Välj **Konfigurera principer** och välj sedan Lägg till en **princip.**</span><span class="sxs-lookup"><span data-stu-id="6886b-142">Select **Configure policies**, and then select **Add a policy**.</span></span>

5. <span data-ttu-id="6886b-143">Välj eller ange följande värden i listfälten:</span><span class="sxs-lookup"><span data-stu-id="6886b-143">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="6886b-144">**Principtyp**: Aktivitet</span><span class="sxs-lookup"><span data-stu-id="6886b-144">**Policy type**: Task</span></span>

    <span data-ttu-id="6886b-145">**Policyomfattning**: Exchange</span><span class="sxs-lookup"><span data-stu-id="6886b-145">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="6886b-146">**Principnamn:** Ny journalregel</span><span class="sxs-lookup"><span data-stu-id="6886b-146">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="6886b-147">**Godkännandetyp:** Manuell</span><span class="sxs-lookup"><span data-stu-id="6886b-147">**Approval type**: Manual</span></span>

    <span data-ttu-id="6886b-148">**Godkännandegrupp**: Godkännare för behörighet</span><span class="sxs-lookup"><span data-stu-id="6886b-148">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="6886b-149">Välj **Skapa** och sedan **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="6886b-149">Select **Create**, and then select **Close**.</span></span> <span data-ttu-id="6886b-150">Det kan ta några minuter innan principen är helt konfigurerad och aktiverad.</span><span class="sxs-lookup"><span data-stu-id="6886b-150">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="6886b-151">Se till att det finns tid för att principen ska vara helt aktiverad innan du testar godkännandekravet i nästa steg.</span><span class="sxs-lookup"><span data-stu-id="6886b-151">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="6886b-152">Testa godkännandekrav för den New-JournalRule som definierats i en behörighetsåtkomstprincip</span><span class="sxs-lookup"><span data-stu-id="6886b-152">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="6886b-153">Öppna och logga in på Exchange Online Remote PowerShell-modulen på din lokala dator hos **Microsoft Corporation**  >  **Microsoft Exchange Online Remote PowerShell-modulen** och använd ett global administratör-konto för testmiljön.</span><span class="sxs-lookup"><span data-stu-id="6886b-153">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="6886b-154">Skapa en ny journalregel för din organisation i Exchange Management PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6886b-154">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. <span data-ttu-id="6886b-155">Visa felmeddelandet "Otillräckliga behörigheter" i Exchange Management PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6886b-155">View the "Insufficient permissions" error in Exchange Management PowerShell:</span></span>

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="6886b-156">Begära åtkomst för att skapa en ny journalregel med hjälp New-JournalRule uppgift</span><span class="sxs-lookup"><span data-stu-id="6886b-156">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="6886b-157">Logga in på [administrationscentret för Microsoft 365](https://admin.microsoft.com) med globalt administratörskonto för testmiljön.</span><span class="sxs-lookup"><span data-stu-id="6886b-157">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="6886b-158">I administrationscentret går du till Inställningar för **säkerhet &**  >  **behörighet för**  >  **sekretess.**</span><span class="sxs-lookup"><span data-stu-id="6886b-158">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="6886b-159">Välj **Hantera åtkomstprinciper och -begäranden.**</span><span class="sxs-lookup"><span data-stu-id="6886b-159">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="6886b-160">Välj **Ny begäran.**</span><span class="sxs-lookup"><span data-stu-id="6886b-160">Select **New request**.</span></span> <span data-ttu-id="6886b-161">Välj lämpliga värden för din organisation i listfälten:</span><span class="sxs-lookup"><span data-stu-id="6886b-161">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="6886b-162">**Typ av begäran:** Uppgift</span><span class="sxs-lookup"><span data-stu-id="6886b-162">**Request type**: Task</span></span>

    <span data-ttu-id="6886b-163">**Begärandeomfattning**: Exchange</span><span class="sxs-lookup"><span data-stu-id="6886b-163">**Request scope**: Exchange</span></span>

    <span data-ttu-id="6886b-164">**Begäran om:** Ny journalregel</span><span class="sxs-lookup"><span data-stu-id="6886b-164">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="6886b-165">**Varaktighet (timmar)**: 2</span><span class="sxs-lookup"><span data-stu-id="6886b-165">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="6886b-166">**Kommentarer:** Begära behörighet att skapa en ny journalregel</span><span class="sxs-lookup"><span data-stu-id="6886b-166">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="6886b-167">Välj **Spara** och sedan **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="6886b-167">Select **Save**, and then select **Close**.</span></span> <span data-ttu-id="6886b-168">Din begäran skickas till godkännaren via e-post.</span><span class="sxs-lookup"><span data-stu-id="6886b-168">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="6886b-169">Godkänna behörighetsåtkomstbegäran för att skapa en ny journalregel</span><span class="sxs-lookup"><span data-stu-id="6886b-169">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="6886b-170">Logga in på administrationscentret för [Microsoft 365](https://admin.microsoft.com) med autentiseringsuppgifterna för Användare 3 i testmiljön (medlem i säkerhetsgruppen Godkännare av behörighet i testmiljön).</span><span class="sxs-lookup"><span data-stu-id="6886b-170">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="6886b-171">I administrationscentret går du till Inställningar för  >  **säkerhet & behörighet för**  >  **sekretess.**</span><span class="sxs-lookup"><span data-stu-id="6886b-171">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="6886b-172">Välj **Hantera åtkomstprinciper och -begäranden.**</span><span class="sxs-lookup"><span data-stu-id="6886b-172">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="6886b-173">Markera den väntande begäran och välj sedan Godkänn **för att** bevilja åtkomst till det globala administratörskontot för att skapa en ny journalregel.</span><span class="sxs-lookup"><span data-stu-id="6886b-173">Select the pending request, and then select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="6886b-174">Det globala administratörskontot (den som begär användaren) får en e-postbekräftelse på att godkännande har beviljats.</span><span class="sxs-lookup"><span data-stu-id="6886b-174">The Global Admin account (the requesting user) will receive an email confirmation that approval was granted.</span></span>

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="6886b-175">Testa att skapa en ny journalregel med behörighetsbehörighet godkänd New-JournalRule uppgiften</span><span class="sxs-lookup"><span data-stu-id="6886b-175">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="6886b-176">Öppna och logga in på Exchange Online Remote PowerShell-modulen på din lokala dator hos **Microsoft Corporation**  >  **Microsoft Exchange Online Remote PowerShell-modulen** med det globala administratörskontot för testmiljön.</span><span class="sxs-lookup"><span data-stu-id="6886b-176">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="6886b-177">Skapa en ny journalregel för din organisation i Exchange Management PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6886b-177">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="6886b-178">Visa att den nya journalregeln har skapats i Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6886b-178">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="6886b-179">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="6886b-179">Next step</span></span>

<span data-ttu-id="6886b-180">Utforska ytterligare [informationsskyddsfunktioner](m365-enterprise-test-lab-guides.md#information-protection) i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="6886b-180">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="6886b-181">Se även</span><span class="sxs-lookup"><span data-stu-id="6886b-181">See also</span></span>

[<span data-ttu-id="6886b-182">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="6886b-182">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="6886b-183">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="6886b-183">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="6886b-184">Dokumentation om Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="6886b-184">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)
