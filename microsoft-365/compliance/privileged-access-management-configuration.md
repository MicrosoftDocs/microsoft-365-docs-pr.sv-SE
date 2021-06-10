---
title: Kom igång med privilegierad åtkomsthantering
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: ''
description: I den här artikeln kan du läsa mer om hur du aktiverar och konfigurerar hantering av behörighet Office 365.
ms.openlocfilehash: 0b8d79c3012ecd321d7b00c1566aa557077d55f1
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/06/2021
ms.locfileid: "52161794"
---
# <a name="get-started-with-privileged-access-management"></a><span data-ttu-id="93b1f-103">Kom igång med privilegierad åtkomsthantering</span><span class="sxs-lookup"><span data-stu-id="93b1f-103">Get started with privileged access management</span></span>

<span data-ttu-id="93b1f-104">I det här avsnittet får du hjälp med att aktivera och konfigurera hantering av behörighet i din organisation.</span><span class="sxs-lookup"><span data-stu-id="93b1f-104">This topic guides you through enabling and configuring privileged access management in your organization.</span></span> <span data-ttu-id="93b1f-105">Du kan använda antingen Microsoft 365 administrationscenter eller PowerShell Exchange management för att hantera och använda behörighet.</span><span class="sxs-lookup"><span data-stu-id="93b1f-105">You can use either the Microsoft 365 admin center or Exchange Management PowerShell to manage and use privileged access.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="93b1f-106">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="93b1f-106">Before you begin</span></span>

<span data-ttu-id="93b1f-107">Innan du kommer igång med hantering av behörighet ska du bekräfta [Microsoft 365-prenumerationen](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) och alla tillägg.</span><span class="sxs-lookup"><span data-stu-id="93b1f-107">Before you get started with privileged access management, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) and any add-ons.</span></span> <span data-ttu-id="93b1f-108">Om du vill komma åt och använda hantering av privilegierad åtkomst måste din organisation ha någon av följande prenumerationer eller tillägg:</span><span class="sxs-lookup"><span data-stu-id="93b1f-108">To access and use privileged access management, your organization must have one of the following subscriptions or add-ons:</span></span>

- <span data-ttu-id="93b1f-109">Microsoft 365 E5 prenumeration (betald version eller utvärderingsversion)</span><span class="sxs-lookup"><span data-stu-id="93b1f-109">Microsoft 365 E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="93b1f-110">Microsoft 365 E3 -prenumeration (Office 365 E3-abonnemang + Enterprise Mobility and Security E3)+ Microsoft 365 E5 Compliance-tillägget</span><span class="sxs-lookup"><span data-stu-id="93b1f-110">Microsoft 365 E3 subscription (or Office 365 E3 subscription + Enterprise Mobility and Security E3 subscription) + the Microsoft 365 E5 Compliance add-on</span></span>
- <span data-ttu-id="93b1f-111">Alla Microsoft 365, Office 365, Exchange, SharePoint eller OneDrive för företag-prenumerationen + Microsoft 365 E5-tillägget Microsoft 365 E5 Insider Risk Management</span><span class="sxs-lookup"><span data-stu-id="93b1f-111">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Business subscription + the Microsoft 365 E5 Insider Risk Management add-on</span></span>  
- <span data-ttu-id="93b1f-112">Microsoft 365 A5-prenumeration (betald eller utvärderingsversion)</span><span class="sxs-lookup"><span data-stu-id="93b1f-112">Microsoft 365 A5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="93b1f-113">Microsoft 365 A3-abonnemang (Office 365 A3 prenumeration + Enterprise Mobility and Security A3-prenumeration) + tillägget Microsoft A5 efterlevnad</span><span class="sxs-lookup"><span data-stu-id="93b1f-113">Microsoft 365 A3 subscription (or Office 365 A3 subscription + Enterprise Mobility and Security A3 subscription) + the Microsoft A5 Compliance add-on</span></span>
- <span data-ttu-id="93b1f-114">Alla Microsoft 365, Office 365, Exchange, SharePoint eller OneDrive för utbildning-prenumerationen + Microsoft 365 A5 Insider Risk Management-tillägget</span><span class="sxs-lookup"><span data-stu-id="93b1f-114">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Education subscription + the Microsoft 365 A5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="93b1f-115">Office 365 Enterprise E5-prenumeration (betald eller utvärderingsversion)</span><span class="sxs-lookup"><span data-stu-id="93b1f-115">Office 365 Enterprise E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="93b1f-116">Office 365 Enterprise E3-prenumeration + Office 365 Advanced Compliance-tillägget (inte längre tillgängligt för nya prenumerationer, se anteckningen)</span><span class="sxs-lookup"><span data-stu-id="93b1f-116">Office 365 Enterprise E3 subscription + the Office 365 Advanced Compliance add-on (no longer available for new subscriptions, see note)</span></span>

<span data-ttu-id="93b1f-117">Användare som skickar och svarar på begäran om behörighet för åtkomsthantering måste tilldelas någon av licenserna ovan.</span><span class="sxs-lookup"><span data-stu-id="93b1f-117">Users submitting and responding to privileged access management requests must be assigned one of the licenses above.</span></span>

>[!IMPORTANT]
><span data-ttu-id="93b1f-118">Office 365 Advanced Compliance säljs inte längre som en fristående prenumeration.</span><span class="sxs-lookup"><span data-stu-id="93b1f-118">Office 365 Advanced Compliance is no longer sold as a standalone subscription.</span></span> <span data-ttu-id="93b1f-119">När aktuella prenumerationer går ut bör kunderna gå över till en av prenumerationerna ovan, som innehåller samma eller ytterligare efterlevnadsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="93b1f-119">When current subscriptions expire, customers should transition to one of the subscriptions above, which contain the same or additional compliance features.</span></span>

<span data-ttu-id="93b1f-120">Om du inte har ett befintligt Office 365 Enterprise E5-abonnemang och vill prova hantering av behörighet kan du lägga till [](https://www.microsoft.com/microsoft-365/enterprise) [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) i din befintliga Office 365-prenumeration eller registrera dig för en utvärderingsversion av Microsoft 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="93b1f-120">If you don't have an existing Office 365 Enterprise E5 plan and want to try privileged access management, you can [add Microsoft 365](/office365/admin/try-or-buy-microsoft-365) to your existing Office 365 subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Microsoft 365 Enterprise E5.</span></span>

## <a name="enable-and-configure-privileged-access-management"></a><span data-ttu-id="93b1f-121">Aktivera och konfigurera hantering av privilegierad åtkomst</span><span class="sxs-lookup"><span data-stu-id="93b1f-121">Enable and configure privileged access management</span></span>

<span data-ttu-id="93b1f-122">Följ de här anvisningarna för att konfigurera och använda behörighetsbehörighet i din organisation:</span><span class="sxs-lookup"><span data-stu-id="93b1f-122">Follow these steps to set up and use privileged access in your organization:</span></span>

- [<span data-ttu-id="93b1f-123">Steg 1: Skapa en godkännaresgrupp</span><span class="sxs-lookup"><span data-stu-id="93b1f-123">Step 1: Create an approver's group</span></span>](privileged-access-management-configuration.md#step1)

    <span data-ttu-id="93b1f-124">Innan du börjar använda behörighet ska du bestämma vem som behöver godkännandebehörighet för inkommande förfrågningar om åtkomst till uppgifter med förhöjd behörighet.</span><span class="sxs-lookup"><span data-stu-id="93b1f-124">Before you start using privilege access, determine who needs approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="93b1f-125">Alla användare som ingår i godkännargruppen kan godkänna åtkomstförfrågningar.</span><span class="sxs-lookup"><span data-stu-id="93b1f-125">Any user who is part of the Approvers' group is able to approve access requests.</span></span> <span data-ttu-id="93b1f-126">Den här gruppen aktiveras genom att en e-postaktiverad säkerhetsgrupp skapas i Office 365.</span><span class="sxs-lookup"><span data-stu-id="93b1f-126">This group is enabled by creating a mail-enabled security group in Office 365.</span></span>

- [<span data-ttu-id="93b1f-127">Steg 2: Aktivera privilegierad åtkomst</span><span class="sxs-lookup"><span data-stu-id="93b1f-127">Step 2: Enable privileged access</span></span>](privileged-access-management-configuration.md#step2)

    <span data-ttu-id="93b1f-128">Behörighet måste uttryckligen aktiveras i Office 365 med standardbehörighetsgruppen för godkännare, inklusive en uppsättning systemkonton som du vill ska undantas från åtkomsthanteringens åtkomstkontroll.</span><span class="sxs-lookup"><span data-stu-id="93b1f-128">Privileged access must be explicitly enabled in Office 365 with the default approver group, including a set of system accounts that you want excluded from the privileged access management access control.</span></span>

- [<span data-ttu-id="93b1f-129">Steg 3: Skapa en åtkomstprincip</span><span class="sxs-lookup"><span data-stu-id="93b1f-129">Step 3: Create an access policy</span></span>](privileged-access-management-configuration.md#step3)

    <span data-ttu-id="93b1f-130">Om du skapar en godkännandeprincip kan du definiera specifika godkännandekrav som gäller för enskilda uppgifter.</span><span class="sxs-lookup"><span data-stu-id="93b1f-130">Creating an approval policy allows you to define the specific approval requirements scoped at individual tasks.</span></span> <span data-ttu-id="93b1f-131">Alternativen för godkännandetyper är **Automatiska** eller **Manuella**.</span><span class="sxs-lookup"><span data-stu-id="93b1f-131">The approval type options are **Auto** or **Manual**.</span></span>

- [<span data-ttu-id="93b1f-132">Steg 4: Skicka/godkänna behörighetsåtkomstförfrågningar</span><span class="sxs-lookup"><span data-stu-id="93b1f-132">Step 4: Submit/approve privileged access requests</span></span>](privileged-access-management-configuration.md#step4)

    <span data-ttu-id="93b1f-133">När den är aktiverad kräver behörigheten godkännanden för alla aktiviteter som har en associerad godkännandeprincip definierad.</span><span class="sxs-lookup"><span data-stu-id="93b1f-133">Once enabled, privileged access requires approvals for any task that has an associated approval policy defined.</span></span> <span data-ttu-id="93b1f-134">För uppgifter som ingår i en godkännandeprincip måste användarna begära och beviljas behörighetsgodkännande för att få den behörighet som krävs för att utföra uppgiften.</span><span class="sxs-lookup"><span data-stu-id="93b1f-134">For tasks included in an approval policy, users must request and be granted access approval to have permissions necessary to execute the task.</span></span>

<span data-ttu-id="93b1f-135">När godkännande har beviljats kan den som begär behörighet köra den avsedda uppgiften och behörigheten att auktorisera och köra uppgiften åt användaren.</span><span class="sxs-lookup"><span data-stu-id="93b1f-135">After approval is granted, the requesting user can execute the intended task and privileged access will authorize and execute the task on behalf of the user.</span></span> <span data-ttu-id="93b1f-136">Godkännandet förblir giltigt under den begärda varaktigheten (standardlängden är 4 timmar), under vilken den som begär kan köra den avsedda aktiviteten flera gånger.</span><span class="sxs-lookup"><span data-stu-id="93b1f-136">The approval remains valid for the requested duration (default duration is 4 hours), during which the requester can execute the intended task multiple times.</span></span> <span data-ttu-id="93b1f-137">Alla sådana körningar loggas och görs tillgängliga för granskning av säkerhet och efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="93b1f-137">All such executions are logged and made available for security and compliance auditing.</span></span> 

>[!NOTE]
><span data-ttu-id="93b1f-138">Om du vill använda Exchange Management PowerShell för att aktivera och konfigurera behörighetsåtkomst följer du stegen i [Anslut för Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) med multifaktorautentisering för att ansluta till Exchange Online PowerShell med dina Office 365-autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="93b1f-138">If you want to use Exchange Management PowerShell to enable and configure privileged access, follow the steps in [Connect to Exchange Online PowerShell using Multi-Factor authentication](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) to connect to Exchange Online PowerShell with your Office 365 credentials.</span></span> <span data-ttu-id="93b1f-139">Du behöver inte aktivera multifaktorautentisering för din organisation för att kunna använda stegen för att aktivera privilegierad åtkomst när du ansluter till Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93b1f-139">You do not need to enable multi-factor authentication for your organization to use the steps to enable privileged access while connecting to Exchange Online PowerShell.</span></span> <span data-ttu-id="93b1f-140">Om du ansluter med multifaktorautentisering skapas en OAuth-token som används av behörig åtkomst för att signera dina begäranden.</span><span class="sxs-lookup"><span data-stu-id="93b1f-140">Connecting with multi-factor authentication creates an OAuth token that is used by privileged access for signing your requests.</span></span>

<span data-ttu-id="93b1f-141"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="93b1f-141"><a name="step1"> </a></span></span>

## <a name="step-1-create-an-approvers-group"></a><span data-ttu-id="93b1f-142">Steg 1: Skapa en godkännaresgrupp</span><span class="sxs-lookup"><span data-stu-id="93b1f-142">Step 1: Create an approver's group</span></span>

1. <span data-ttu-id="93b1f-143">Logga in Microsoft 365 [administrationscenter med](https://admin.microsoft.com) autentiseringsuppgifter för ett administratörskonto i organisationen.</span><span class="sxs-lookup"><span data-stu-id="93b1f-143">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="93b1f-144">Gå till Lägg till grupp i  >  **administrationscentret.**</span><span class="sxs-lookup"><span data-stu-id="93b1f-144">In the Admin Center, go to **Groups** > **Add a group**.</span></span>

3. <span data-ttu-id="93b1f-145">Välj **e-postaktiverad säkerhetsgrupp** och fyll i **fälten Namn,** Grupp-e-postadress **och** Beskrivning för den nya gruppen. </span><span class="sxs-lookup"><span data-stu-id="93b1f-145">Select **mail-enabled security group** and then complete the **Name**, **Group email address**, and **Description** fields for the new group.</span></span>

4. <span data-ttu-id="93b1f-146">Spara gruppen.</span><span class="sxs-lookup"><span data-stu-id="93b1f-146">Save the group.</span></span> <span data-ttu-id="93b1f-147">Det kan ta några minuter innan gruppen har konfigurerats helt och visas i Microsoft 365 administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="93b1f-147">It may take a few minutes for the group to be fully configured and to appear in the Microsoft 365 admin center.</span></span>

5. <span data-ttu-id="93b1f-148">Välj den nya godkännaren och välj Redigera för **att** lägga till användare i gruppen.</span><span class="sxs-lookup"><span data-stu-id="93b1f-148">Select the new approver's group and select **edit** to add users to the group.</span></span>

6. <span data-ttu-id="93b1f-149">Spara gruppen.</span><span class="sxs-lookup"><span data-stu-id="93b1f-149">Save the group.</span></span>

<span data-ttu-id="93b1f-150"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="93b1f-150"><a name="step2"> </a></span></span>

## <a name="step-2-enable-privileged-access"></a><span data-ttu-id="93b1f-151">Steg 2: Aktivera privilegierad åtkomst</span><span class="sxs-lookup"><span data-stu-id="93b1f-151">Step 2: Enable privileged access</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="93b1f-152">I Microsoft 365 Administrationscenter</span><span class="sxs-lookup"><span data-stu-id="93b1f-152">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="93b1f-153">Logga in på [Microsoft 365 administrationscenter med](https://admin.microsoft.com) autentiseringsuppgifter för ett administratörskonto i organisationen.</span><span class="sxs-lookup"><span data-stu-id="93b1f-153">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="93b1f-154">Gå till administrationscentret och gå till sidan **Inställningar**  >  **för Inställningar** åtkomst &  >  **sekretessbehörighet.**  >  </span><span class="sxs-lookup"><span data-stu-id="93b1f-154">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="93b1f-155">Aktivera kontrollen **Kräv godkännanden för behöriga** uppgifter.</span><span class="sxs-lookup"><span data-stu-id="93b1f-155">Enable the **Require approvals for privileged tasks** control.</span></span>

4. <span data-ttu-id="93b1f-156">Tilldela godkännaren den grupp du skapade i steg 1 som **standard godkännare.**</span><span class="sxs-lookup"><span data-stu-id="93b1f-156">Assign the approver's group you created in Step 1 as the **Default approvers group**.</span></span>

5. <span data-ttu-id="93b1f-157">**Spara** och **stäng**.</span><span class="sxs-lookup"><span data-stu-id="93b1f-157">**Save** and **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="93b1f-158">I Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="93b1f-158">In Exchange Management PowerShell</span></span>

<span data-ttu-id="93b1f-159">Om du vill aktivera behörighetsåtkomst och tilldela godkännarens grupp kör du följande kommando i Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="93b1f-159">To enable privileged access and to assign the approver's group, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

<span data-ttu-id="93b1f-160">Exempel:</span><span class="sxs-lookup"><span data-stu-id="93b1f-160">Example:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', 'sys2@fabrikamorg.onmicrosoft.com')
```

>[!NOTE]
><span data-ttu-id="93b1f-161">Funktionen för systemkonton är tillgänglig för att säkerställa att vissa automatiseringar inom organisationen kan fungera utan att vara beroende av privilegierad åtkomst, men vi rekommenderar att sådana undantag blir undantag som inte är tillåtna och att de tillåts godkänns och granskas regelbundet.</span><span class="sxs-lookup"><span data-stu-id="93b1f-161">System accounts feature is made available to ensure certain automations within your organizations can work without dependency on privileged access, however it is recommended that such exclusions be exceptional and those allowed should be approved and audited regularly.</span></span>

<span data-ttu-id="93b1f-162"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="93b1f-162"><a name="step3"> </a></span></span>

## <a name="step-3-create-an-access-policy"></a><span data-ttu-id="93b1f-163">Steg 3: Skapa en åtkomstprincip</span><span class="sxs-lookup"><span data-stu-id="93b1f-163">Step 3: Create an access policy</span></span>

<span data-ttu-id="93b1f-164">Du kan skapa och konfigurera upp till 30 principer för behörighet för din organisation.</span><span class="sxs-lookup"><span data-stu-id="93b1f-164">You can create and configure up to 30 privileged access policies for your organization.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="93b1f-165">I Microsoft 365 Administrationscenter</span><span class="sxs-lookup"><span data-stu-id="93b1f-165">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="93b1f-166">Logga in på [Microsoft 365 administrationscenter med](https://admin.microsoft.com) autentiseringsuppgifter för ett administratörskonto i organisationen.</span><span class="sxs-lookup"><span data-stu-id="93b1f-166">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="93b1f-167">Gå till administrationscentret och gå till sidan **Inställningar**  >  **för Inställningar** åtkomst &  >  **sekretessbehörighet.**  >  </span><span class="sxs-lookup"><span data-stu-id="93b1f-167">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="93b1f-168">Välj **Hantera åtkomstprinciper och -begäranden.**</span><span class="sxs-lookup"><span data-stu-id="93b1f-168">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="93b1f-169">Välj **Konfigurera principer** och välj Lägg till en **princip.**</span><span class="sxs-lookup"><span data-stu-id="93b1f-169">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="93b1f-170">I listrutan väljer du lämpliga värden för din organisation:</span><span class="sxs-lookup"><span data-stu-id="93b1f-170">From the drop-down fields, select the appropriate values for your organization:</span></span>
    
    <span data-ttu-id="93b1f-171">**Principtyp**: Aktivitet, Roll eller Rollgrupp</span><span class="sxs-lookup"><span data-stu-id="93b1f-171">**Policy type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="93b1f-172">**Policyomfattning**: Exchange</span><span class="sxs-lookup"><span data-stu-id="93b1f-172">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="93b1f-173">**Principnamn:** Välj bland tillgängliga principer</span><span class="sxs-lookup"><span data-stu-id="93b1f-173">**Policy name**: Select from the available policies</span></span>

    <span data-ttu-id="93b1f-174">**Godkännandetyp**: Manuell eller Automatisk</span><span class="sxs-lookup"><span data-stu-id="93b1f-174">**Approval type**: Manual or Auto</span></span>

    <span data-ttu-id="93b1f-175">**Godkännandegrupp:** Välj den godkännargrupp som skapades i steg 1</span><span class="sxs-lookup"><span data-stu-id="93b1f-175">**Approval group**: Select the approvers group created in Step 1</span></span>

6. <span data-ttu-id="93b1f-176">Välj **Skapa** och sedan **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="93b1f-176">Select **Create** and then **Close**.</span></span> <span data-ttu-id="93b1f-177">Det kan ta några minuter innan principen har konfigurerats och aktiverats helt.</span><span class="sxs-lookup"><span data-stu-id="93b1f-177">It may take a few minutes for the policy to be fully configured and enabled.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="93b1f-178">I Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="93b1f-178">In Exchange Management PowerShell</span></span>

<span data-ttu-id="93b1f-179">Om du vill skapa och definiera en godkännandeprincip kör du följande kommando i Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="93b1f-179">To create and define an approval policy, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

<span data-ttu-id="93b1f-180">Exempel:</span><span class="sxs-lookup"><span data-stu-id="93b1f-180">Example:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<span data-ttu-id="93b1f-181"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="93b1f-181"><a name="step4"> </a></span></span>

## <a name="step-4-submitapprove-privileged-access-requests"></a><span data-ttu-id="93b1f-182">Steg 4: Skicka/godkänna behörighetsåtkomstförfrågningar</span><span class="sxs-lookup"><span data-stu-id="93b1f-182">Step 4: Submit/approve privileged access requests</span></span>

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a><span data-ttu-id="93b1f-183">Begära autentisering av höjd för att utföra behöriga uppgifter</span><span class="sxs-lookup"><span data-stu-id="93b1f-183">Requesting elevation authorization to execute privileged tasks</span></span>

<span data-ttu-id="93b1f-184">Begäranden om behörighet är giltiga i upp till 24 timmar efter att begäran har skickats.</span><span class="sxs-lookup"><span data-stu-id="93b1f-184">Requests for privileged access are valid for up to 24 hours after the request is submitted.</span></span> <span data-ttu-id="93b1f-185">Om begärandena inte har godkänts eller nekats, upphör att gälla och åtkomst är inte godkända.</span><span class="sxs-lookup"><span data-stu-id="93b1f-185">If not approved or denied, the requests expire and access is not approved.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="93b1f-186">I Microsoft 365 Administrationscenter</span><span class="sxs-lookup"><span data-stu-id="93b1f-186">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="93b1f-187">Logga in på [Microsoft 365 administrationscenter med](https://admin.microsoft.com) dina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="93b1f-187">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using your credentials.</span></span>

2. <span data-ttu-id="93b1f-188">Gå till administrationscentret och gå till sidan **Inställningar**  >  **för Inställningar** åtkomst &  >  **sekretessbehörighet.**  >  </span><span class="sxs-lookup"><span data-stu-id="93b1f-188">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="93b1f-189">Välj **Hantera åtkomstprinciper och -begäranden.**</span><span class="sxs-lookup"><span data-stu-id="93b1f-189">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="93b1f-190">Välj **Ny begäran.**</span><span class="sxs-lookup"><span data-stu-id="93b1f-190">Select **New request**.</span></span> <span data-ttu-id="93b1f-191">I listrutan väljer du lämpliga värden för din organisation:</span><span class="sxs-lookup"><span data-stu-id="93b1f-191">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="93b1f-192">**Typ av** begäran: Uppgift, Roll eller Rollgrupp</span><span class="sxs-lookup"><span data-stu-id="93b1f-192">**Request type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="93b1f-193">**Begäran om omfattning:** Exchange</span><span class="sxs-lookup"><span data-stu-id="93b1f-193">**Request scope**: Exchange</span></span>

    <span data-ttu-id="93b1f-194">**Begäran om:** Välj bland tillgängliga principer</span><span class="sxs-lookup"><span data-stu-id="93b1f-194">**Request for**: Select from the available policies</span></span>

    <span data-ttu-id="93b1f-195">**Varaktighet (timmar)**: Antal timmar begärd åtkomst.</span><span class="sxs-lookup"><span data-stu-id="93b1f-195">**Duration (hours)**: Number of hours of requested access.</span></span> <span data-ttu-id="93b1f-196">Det finns ingen gräns för hur många timmar som kan begäras.</span><span class="sxs-lookup"><span data-stu-id="93b1f-196">There isn't a limit on the number of hours that can be requested.</span></span>

    <span data-ttu-id="93b1f-197">**Kommentarer:** Textfält för kommentarer som är relaterade till din åtkomstbegäran</span><span class="sxs-lookup"><span data-stu-id="93b1f-197">**Comments**: Text field for comments related to your access request</span></span>

5. <span data-ttu-id="93b1f-198">Välj **Spara** och sedan **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="93b1f-198">Select **Save** and then **Close**.</span></span> <span data-ttu-id="93b1f-199">Din begäran skickas till godkännarens grupp via e-post.</span><span class="sxs-lookup"><span data-stu-id="93b1f-199">Your request will be sent to the approver's group via email.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="93b1f-200">I Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="93b1f-200">In Exchange Management PowerShell</span></span>

<span data-ttu-id="93b1f-201">Kör följande kommando i Exchange Online PowerShell för att skapa och skicka en begäran om godkännande till godkännaren:</span><span class="sxs-lookup"><span data-stu-id="93b1f-201">Run the following command in Exchange Online PowerShell to create and submit an approval request to the approver's group:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

<span data-ttu-id="93b1f-202">Exempel:</span><span class="sxs-lookup"><span data-stu-id="93b1f-202">Example:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a><span data-ttu-id="93b1f-203">Visa status för höjdbegäranden</span><span class="sxs-lookup"><span data-stu-id="93b1f-203">View status of elevation requests</span></span>

<span data-ttu-id="93b1f-204">När en begäran om godkännande har skapats kan status för höjdbegäran granskas i administrationscentret eller i Exchange Management PowerShell med hjälp av det som är associerat med begärande-ID.</span><span class="sxs-lookup"><span data-stu-id="93b1f-204">After an approval request is created, elevation request status can be reviewed in the admin center or in Exchange Management PowerShell using the associated with request ID.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="93b1f-205">I Microsoft 365 administrationscenter</span><span class="sxs-lookup"><span data-stu-id="93b1f-205">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="93b1f-206">Logga in på [Microsoft 365 administrationscenter](https://admin.microsoft.com) med dina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="93b1f-206">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="93b1f-207">Gå till administrationscentret och gå till sidan **Inställningar**  >  **för Inställningar** åtkomst &  >  **sekretessbehörighet.**  >  </span><span class="sxs-lookup"><span data-stu-id="93b1f-207">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="93b1f-208">Välj **Hantera åtkomstprinciper och -begäranden.**</span><span class="sxs-lookup"><span data-stu-id="93b1f-208">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="93b1f-209">Välj **Visa** för att filtrera skickade begäranden **efter Status för Väntande**, **Godkänd**, Nekad **eller Customer Lockbox.** </span><span class="sxs-lookup"><span data-stu-id="93b1f-209">Select **View** to filter submitted requests by **Pending**, **Approved**, **Denied**, or **Customer Lockbox** status.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="93b1f-210">I Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="93b1f-210">In Exchange Management PowerShell</span></span>

<span data-ttu-id="93b1f-211">Kör följande kommando i Exchange Online PowerShell för att visa statusen för en begärande för ett visst ID:</span><span class="sxs-lookup"><span data-stu-id="93b1f-211">Run the following command in Exchange Online PowerShell to view an approval request status for a specific request ID:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

<span data-ttu-id="93b1f-212">Exempel:</span><span class="sxs-lookup"><span data-stu-id="93b1f-212">Example:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a><span data-ttu-id="93b1f-213">Godkänna en begäran om autentiseringssökning</span><span class="sxs-lookup"><span data-stu-id="93b1f-213">Approving an elevation authorization request</span></span>

<span data-ttu-id="93b1f-214">När en begäran om godkännande skapas får medlemmar i den relevanta godkännargruppen ett e-postmeddelande och kan godkänna den begäran som är kopplad till begärans ID.</span><span class="sxs-lookup"><span data-stu-id="93b1f-214">When an approval request is created, members of the relevant approver group receive an email notification and can approve the request associated with the request ID.</span></span> <span data-ttu-id="93b1f-215">Beställaren meddelas om begärans godkännande eller av nekande via e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="93b1f-215">The requestor is notified of the request approval or denial via email message.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="93b1f-216">I Microsoft 365 administrationscenter</span><span class="sxs-lookup"><span data-stu-id="93b1f-216">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="93b1f-217">Logga in på [Microsoft 365 administrationscenter](https://admin.microsoft.com) med dina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="93b1f-217">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="93b1f-218">Gå till administrationscentret och gå till sidan **Inställningar**  >  **för Inställningar** åtkomst &  >  **sekretessbehörighet.**  >  </span><span class="sxs-lookup"><span data-stu-id="93b1f-218">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="93b1f-219">Välj **Hantera åtkomstprinciper och -begäranden.**</span><span class="sxs-lookup"><span data-stu-id="93b1f-219">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="93b1f-220">Välj en begäran i listan för att visa informationen och vidta åtgärder för begäran.</span><span class="sxs-lookup"><span data-stu-id="93b1f-220">Select a listed request to view the details and to take action on the request.</span></span>

5. <span data-ttu-id="93b1f-221">Välj **Godkänn** för att godkänna begäran eller **välj Neka** för att neka begäran.</span><span class="sxs-lookup"><span data-stu-id="93b1f-221">Select **Approve** to approve the request or select **Deny** to deny the request.</span></span> <span data-ttu-id="93b1f-222">Tidigare godkända begäranden kan få åtkomst återkallad genom att välja **Återkalla**.</span><span class="sxs-lookup"><span data-stu-id="93b1f-222">Previously approved requests can have access revoked by selecting **Revoke**.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="93b1f-223">I Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="93b1f-223">In Exchange Management PowerShell</span></span>

<span data-ttu-id="93b1f-224">Om du vill godkänna en begäran om autentiseringssökning kör du följande kommando i Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="93b1f-224">To approve an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

<span data-ttu-id="93b1f-225">Exempel:</span><span class="sxs-lookup"><span data-stu-id="93b1f-225">Example:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

<span data-ttu-id="93b1f-226">Om du vill neka en autentiseringsbegäran för höjd kör du följande kommando i Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="93b1f-226">To deny an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

<span data-ttu-id="93b1f-227">Exempel:</span><span class="sxs-lookup"><span data-stu-id="93b1f-227">Example:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a><span data-ttu-id="93b1f-228">Ta bort en princip för privilegierad åtkomst i Office 365</span><span class="sxs-lookup"><span data-stu-id="93b1f-228">Delete a privileged access policy in Office 365</span></span>

<span data-ttu-id="93b1f-229">Om den inte längre behövs i organisationen kan du ta bort en princip för privilegierad åtkomst.</span><span class="sxs-lookup"><span data-stu-id="93b1f-229">If it is no longer needed in your organization, you can delete a privileged access policy.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="93b1f-230">I Microsoft 365 administrationscenter</span><span class="sxs-lookup"><span data-stu-id="93b1f-230">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="93b1f-231">Logga in Microsoft 365 [administrationscenter med](https://admin.microsoft.com) autentiseringsuppgifter för ett administratörskonto i organisationen.</span><span class="sxs-lookup"><span data-stu-id="93b1f-231">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="93b1f-232">Gå till administrationscentret och gå till sidan **Inställningar**  >  **för Inställningar** åtkomst &  >  **sekretessbehörighet.**  >  </span><span class="sxs-lookup"><span data-stu-id="93b1f-232">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="93b1f-233">Välj **Hantera åtkomstprinciper och -begäranden.**</span><span class="sxs-lookup"><span data-stu-id="93b1f-233">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="93b1f-234">Välj **Konfigurera principer.**</span><span class="sxs-lookup"><span data-stu-id="93b1f-234">Select **Configure policies**.</span></span>

5. <span data-ttu-id="93b1f-235">Markera den princip du vill ta bort och välj sedan Ta **bort princip.**</span><span class="sxs-lookup"><span data-stu-id="93b1f-235">Select the policy you want to delete, then select **Remove Policy**.</span></span>

6. <span data-ttu-id="93b1f-236">Välj **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="93b1f-236">Select **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="93b1f-237">I Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="93b1f-237">In Exchange Management PowerShell</span></span>

<span data-ttu-id="93b1f-238">Om du vill ta bort en princip för privilegierad åtkomst kör du följande kommando Exchange Online Powershell:</span><span class="sxs-lookup"><span data-stu-id="93b1f-238">To delete a privileged access policy, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a><span data-ttu-id="93b1f-239">Inaktivera behörighet i Office 365</span><span class="sxs-lookup"><span data-stu-id="93b1f-239">Disable privileged access in Office 365</span></span>

<span data-ttu-id="93b1f-240">Om det behövs kan du inaktivera hantering av behörighet för organisationen.</span><span class="sxs-lookup"><span data-stu-id="93b1f-240">If needed, you can disable privileged access management for your organization.</span></span> <span data-ttu-id="93b1f-241">Om du inaktiverar behörighet tas inte associerade principer eller godkännargrupper bort.</span><span class="sxs-lookup"><span data-stu-id="93b1f-241">Disabling privileged access does not delete any associated approval policies or approver groups.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="93b1f-242">I Microsoft 365 administrationscenter</span><span class="sxs-lookup"><span data-stu-id="93b1f-242">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="93b1f-243">Logga in på [Microsoft 365 administrationscenter](https://admin.microsoft.com) med autentiseringsuppgifter för ett administratörskonto i organisationen.</span><span class="sxs-lookup"><span data-stu-id="93b1f-243">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="93b1f-244">Gå till administrationscentret och gå till sidan **Inställningar**  >  **för Inställningar** åtkomst &  >  **sekretessbehörighet.**  >  </span><span class="sxs-lookup"><span data-stu-id="93b1f-244">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="93b1f-245">Aktivera funktionen **Kräv godkännanden för behörighetsbehörighet.**</span><span class="sxs-lookup"><span data-stu-id="93b1f-245">Enable the **Require approvals for privileged access** control.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="93b1f-246">I Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="93b1f-246">In Exchange Management PowerShell</span></span>

<span data-ttu-id="93b1f-247">Om du vill inaktivera behörighet kör du följande kommando i Exchange Online Powershell:</span><span class="sxs-lookup"><span data-stu-id="93b1f-247">To disable privileged access, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Disable-ElevatedAccessControl
```
