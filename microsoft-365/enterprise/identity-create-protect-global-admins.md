---
title: 'Steg 1: Skapa och skydda dina globala administratörskonton'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Dina globala administratörskonton kräver särskild hantering för att skydda dem från obehörig inloggning.
ms.openlocfilehash: 27b76671581ebd2dac32304752a85f8a6f60ac98
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42806041"
---
# <a name="step-1-create-and-protect-your-global-admin-accounts"></a><span data-ttu-id="767ac-103">Steg 1: Skapa och skydda dina globala administratörskonton</span><span class="sxs-lookup"><span data-stu-id="767ac-103">Step 1: Create and protect your global admin accounts</span></span>

![Fas 2 – Identitet](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a><span data-ttu-id="767ac-105">Skydda globala administratörskonton</span><span class="sxs-lookup"><span data-stu-id="767ac-105">Protect global administrator accounts</span></span>

<span data-ttu-id="767ac-106">*Det här är obligatoriskt och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="767ac-106">*This is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="767ac-107">I det här avsnittet hjälper du till att förhindra digitala attacker mot din organisation genom att se till att dina administratörskonton är så säkra som möjligt.</span><span class="sxs-lookup"><span data-stu-id="767ac-107">In this section, you'll help prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="767ac-108">För att göra det måste du göra följande:</span><span class="sxs-lookup"><span data-stu-id="767ac-108">To do this, you must:</span></span>

- <span data-ttu-id="767ac-109">Skapa fler än ett dedikerat globalt administratörskonto med [starka lösenord](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) och använd dem bara när det behövs.</span><span class="sxs-lookup"><span data-stu-id="767ac-109">Create more than one dedicated global administrator accounts with [strong passwords](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) and use them only when necessary.</span></span>
- <span data-ttu-id="767ac-110">Utför daglig administration genom att tilldela specifika administratörsroller, t. ex. Exchange-administratör eller Lösenordsadministratör, till andra dedikerade konton för rollerna eller till användarkonton som tillhör IT-personalen efter behov.</span><span class="sxs-lookup"><span data-stu-id="767ac-110">Perform day-to-day administration by assigning specific administrator roles—such as Exchange administrator or Password administrator—to other dedicated accounts for those roles or user accounts of IT staff as needed.</span></span>

<span data-ttu-id="767ac-111">För dina dedikerade globala administratörskonton måste du även:</span><span class="sxs-lookup"><span data-stu-id="767ac-111">For your dedicated global admin accounts, you must also:</span></span>

1. <span data-ttu-id="767ac-112">Testa MFA-inställningar baserat på användarkonto eller villkorlig åtkomst på en testanvändare för att säkerställa att MFA fungerar på rätt sätt och på ett förutsägbart sätt.</span><span class="sxs-lookup"><span data-stu-id="767ac-112">Test per-user account or Conditional Access-based Azure Multi-Factor Authentication (MFA) settings on a test user account to ensure that MFA works correctly and predictably.</span></span> <span data-ttu-id="767ac-113">MFA kräver en sekundär typ av autentisering, t.ex. en verifieringskod som skickas till en smartphone.</span><span class="sxs-lookup"><span data-stu-id="767ac-113">MFA requires a secondary form of authentication, such as a verification code sent to a smart phone.</span></span>
2. <span data-ttu-id="767ac-114">Skapa och aktivera en princip för villkorlig åtkomst för dina globala administratörskonton som kräver MFA och som använder den starkaste formen av sekundär autentisering som är tillgänglig i din organisation.</span><span class="sxs-lookup"><span data-stu-id="767ac-114">Create and enable a Conditional Access policy for your global administrator accounts that requires MFA and uses the strongest form of secondary authentication available in your organization.</span></span> <span data-ttu-id="767ac-115">Mer information finns i [Azure Multi-Factor Authentication](identity-access-prerequisites.md#protecting-administrator-accounts).</span><span class="sxs-lookup"><span data-stu-id="767ac-115">See [Azure Multi-Factor Authentication](identity-access-prerequisites.md#protecting-administrator-accounts) for more information.</span></span>

<span data-ttu-id="767ac-116">Fler skydd finns i [Skydda dina globala administratörskonton för Office 365](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations).</span><span class="sxs-lookup"><span data-stu-id="767ac-116">See [Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations) for additional protections.</span></span>

> [!Note]
> <span data-ttu-id="767ac-117">Nödkonton för akuta scenarier, t.ex. en cyberattack, bör endast vara molnbaserade.</span><span class="sxs-lookup"><span data-stu-id="767ac-117">Emergency accounts for break-glass scenarios in emergencies such as a cyberattack should be cloud-only accounts.</span></span> <span data-ttu-id="767ac-118">Du kan även ha globala administratörskonton (kvalificerade eller permanenta) som inte endast är molnbaserade.</span><span class="sxs-lookup"><span data-stu-id="767ac-118">You may also have global administrator accounts (eligible or permanent) that are not cloud-only.</span></span> <span data-ttu-id="767ac-119">Mer information finns i [Hantera administratörskonton för nödåtkomst i Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span><span class="sxs-lookup"><span data-stu-id="767ac-119">For more information, see [Manage emergency-access administrative accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span>

<span data-ttu-id="767ac-120">Resultatet från det här avsnittet är:</span><span class="sxs-lookup"><span data-stu-id="767ac-120">The results of this section are:</span></span>

- <span data-ttu-id="767ac-121">De enda användarkonton i din prenumeration som har global administratörsroll ska nu vara de dedikerade globala administratörskontona.</span><span class="sxs-lookup"><span data-stu-id="767ac-121">The only user accounts in your subscription that have the global admin role are the dedicated global administrator accounts.</span></span> <span data-ttu-id="767ac-122">Verifiera det här med följande kommando i Azure Active Directory PowerShell för Graph:</span><span class="sxs-lookup"><span data-stu-id="767ac-122">Verify this with the following Azure Active Directory PowerShell for Graph command:</span></span> 
  ```powershell
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- <span data-ttu-id="767ac-123">Alla övriga användarkonton som hanterar dina prenumerationstjänster har administratörsroller som stämmer överens med deras arbetsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="767ac-123">All other user accounts that manage your subscription services have admin roles assigned that are associated with their job responsibilities.</span></span>

> [!Note]
> <span data-ttu-id="767ac-124">Mer information om hur du installerar Azure Active Directory PowerShell för Graph-moduler och loggar in finns under [Ansluta till Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="767ac-124">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in.</span></span>

|||
|:-------|:-----|
|![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="767ac-126">Information om hur du testar den här konfigurationen i en testlabbmiljö finns i [Skydda globala administratörskonton – testlabbguide](protect-global-administrator-accounts-microsoft-365-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="767ac-126">To practice this configuration in a test lab environment, see the [Protect global administrator accounts Test Lab Guide](protect-global-administrator-accounts-microsoft-365-test-environment.md).</span></span> |
|||

<span data-ttu-id="767ac-127">Som en mellanliggande kontrollpunkt kan du läsa [avslutsvillkoren](identity-exit-criteria.md#crit-identity-global-admin) för det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="767ac-127">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-global-admin) for this section.</span></span>


<a name="identity-pim"></a>
## <a name="set-up-on-demand-administrators"></a><span data-ttu-id="767ac-128">Konfigurera administratörer på begäran</span><span class="sxs-lookup"><span data-stu-id="767ac-128">Set up on-demand administrators</span></span>

<span data-ttu-id="767ac-129">*Det här är valfritt och gäller endast E5-versionen av Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="767ac-129">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="767ac-130">I det här avsnittet konfigurerar du Azure AD priviligierade identitetshantering (PIM) för att minska tiden som dina administratörskonton drabbas av angrepp från illvilliga användare.</span><span class="sxs-lookup"><span data-stu-id="767ac-130">In this section, you'll set up Azure AD Privileged Identity Management (PIM) to reduce the amount of time that your administrator accounts are vulnerable to attack by malicious users.</span></span> <span data-ttu-id="767ac-131">PIM tillhandahåller på begäran- och just-in-time-tilldelning av administratörsrollerna vid behov.</span><span class="sxs-lookup"><span data-stu-id="767ac-131">PIM provides on-demand, just-in-time assignment of the administrator roles when needed.</span></span>  

<span data-ttu-id="767ac-132">I stället för att dina administratörskonton permanent har administratörsrättigheter får de kvalificerade administratörsrättigheter.</span><span class="sxs-lookup"><span data-stu-id="767ac-132">Instead of your administrator accounts being permanent admins, they become eligible admins.</span></span> <span data-ttu-id="767ac-133">Rollen som administratör är inaktiv tills någon behöver den.</span><span class="sxs-lookup"><span data-stu-id="767ac-133">The administrator role is inactive until someone needs it.</span></span> <span data-ttu-id="767ac-134">Därefter slutför du en aktiveringsprocess för att lägga till administratörsrollen i administratörskontot under en viss tid.</span><span class="sxs-lookup"><span data-stu-id="767ac-134">You'll then complete an activation process to add the administrator role to the administrator account for a specific amount of time.</span></span> <span data-ttu-id="767ac-135">När tiden går ut tar PIM bort rollen som administratör från administratörskontot.</span><span class="sxs-lookup"><span data-stu-id="767ac-135">When the time expires, PIM removes the administrator role from the administrator account.</span></span>

<span data-ttu-id="767ac-136">PIM finns i Azure Active Directory Premium P2, som ingår i Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="767ac-136">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 E5.</span></span> <span data-ttu-id="767ac-137">Alternativt kan du köpa enskilda Azure Active Directory Premium P2-licenser för dina administratörskonton.</span><span class="sxs-lookup"><span data-stu-id="767ac-137">Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your administrator accounts.</span></span>

<span data-ttu-id="767ac-138">Mer information om hur du konfigurerar PIM för Azure AD-klientorganisationen och administratörskonton finns i [stegen för att konfigurera PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span><span class="sxs-lookup"><span data-stu-id="767ac-138">To enable Azure PIM for your Azure AD tenant and administrator accounts, see the [steps to configure PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="767ac-139">Mer information om hur du skapar en omfattande översikt för att skydda skyddad åtkomst för cyberangripare finns i [Säker åtkomst för åtkomst för hybrid- och molndistributioner i Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span><span class="sxs-lookup"><span data-stu-id="767ac-139">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span></span>

<span data-ttu-id="767ac-140">Som en mellanliggande kontrollpunkt kan du läsa [avslutsvillkoren](identity-exit-criteria.md#crit-identity-pim) för det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="767ac-140">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pim) for this section.</span></span>


<a name="identity-pam"></a>
## <a name="privileged-access-management"></a><span data-ttu-id="767ac-141">Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="767ac-141">Privileged access management</span></span>

<span data-ttu-id="767ac-142">Privileged Access Management aktiveras genom att konfigurera principer som anger just-in-time-åtkomst för uppgiftsbaserade aktiviteter i Office 365-klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="767ac-142">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your Office 365 tenant.</span></span> <span data-ttu-id="767ac-143">Det kan hjälpa dig att skydda din organisation från intrång som kan använda befintliga privilegierade administratörskonton med ständig åtkomst till känsliga data eller åtkomst till kritiska konfigurationsinställningar.</span><span class="sxs-lookup"><span data-stu-id="767ac-143">It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="767ac-144">Du kan t. ex. konfigurera en Privileged Access Management-princip som kräver uttryckligt godkännande för att få åtkomst till och ändra inställningar för organisationens postlådor i Office 365-klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="767ac-144">For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your Office 365 tenant.</span></span>

<span data-ttu-id="767ac-145">I det här steget ska du aktivera Privileged Access Management i din Office 365-klientorganisation och konfigurera principer för privilegierad åtkomst som ger ytterligare säkerhet för aktivitetsbaserad åtkomst till Office 365-data och -konfigurationsinställningar för din organisation.</span><span class="sxs-lookup"><span data-stu-id="767ac-145">In this step, you'll enable privileged access management in your Office 365 tenant and configure privileged access policies that provide additional security for task-based access to Office 365 data and configuration settings for your organization.</span></span> <span data-ttu-id="767ac-146">Det finns tre grundläggande steg för att komma igång med privilegierad åtkomst i din Office 365-organisation:</span><span class="sxs-lookup"><span data-stu-id="767ac-146">There are three basic steps to get started with privileged access in your Office 365 organization:</span></span>

- <span data-ttu-id="767ac-147">Skapa en godkännargrupp</span><span class="sxs-lookup"><span data-stu-id="767ac-147">Creating an approver's group</span></span>
- <span data-ttu-id="767ac-148">Aktivera privilegierad åtkomst</span><span class="sxs-lookup"><span data-stu-id="767ac-148">Enabling privileged access</span></span>
- <span data-ttu-id="767ac-149">Skapa godkännandeprinciper</span><span class="sxs-lookup"><span data-stu-id="767ac-149">Creating approval policies</span></span>

<span data-ttu-id="767ac-150">När du har konfigurerat Privileged Access Management kan din organisation fungera helt utan ständiga privilegier, och ger ett skydd mot säkerhetsproblem som uppstår på grund av sådan ständig administratörsåtkomst.</span><span class="sxs-lookup"><span data-stu-id="767ac-150">One configured, privileged access management will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access.</span></span> <span data-ttu-id="767ac-151">Privilegierad åtkomst kräver godkännanden för att kunna utföra en aktivitet som har en kopplad och definierad godkännandeprincip.</span><span class="sxs-lookup"><span data-stu-id="767ac-151">Privileged access requires approvals for executing any task that has an associated approval policy defined.</span></span> <span data-ttu-id="767ac-152">Användare som behöver utföra aktiviteter som ingår i en godkännandeprincip måste begära och beviljas åtkomstgodkännande för att få behörigheter för att utföra aktiviteter som definierats i principen.</span><span class="sxs-lookup"><span data-stu-id="767ac-152">Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute tasks defined in the policy.</span></span>

<span data-ttu-id="767ac-153">Mer information om hur du aktiverar Privileged Access Management i Office 365 finns i avsnittet [Konfigurera Privileged Access Management i Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration).</span><span class="sxs-lookup"><span data-stu-id="767ac-153">To enable Office 365 privileged access management, see the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic.</span></span>

<span data-ttu-id="767ac-154">Mer information finns i avsnittet [Privileged Access Management i Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span><span class="sxs-lookup"><span data-stu-id="767ac-154">For more information, see the [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) topic.</span></span>


|||
|:-------|:-----|
|![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="767ac-156">Information om hur du testar den här konfigurationen i en testlabbmiljö finns i [Privileged Access Management – testlabbguide](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="767ac-156">To practice this configuration in a test lab environment, see the [Privileged access management Test Lab Guide](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span></span> |
|||

<span data-ttu-id="767ac-157">Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](identity-exit-criteria.md#crit-identity-pam) som motsvarar det här steget.</span><span class="sxs-lookup"><span data-stu-id="767ac-157">As an interim checkpoint, see the [exit criteria](identity-exit-criteria.md#crit-identity-pam) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="767ac-158">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="767ac-158">Next step</span></span>

|||
|:-------|:-----|
|![Steg 2](../media/stepnumbers/Step2.png)| [<span data-ttu-id="767ac-160">Skydda dina lösenord</span><span class="sxs-lookup"><span data-stu-id="767ac-160">Secure your passwords</span></span>](identity-secure-your-passwords.md) |

