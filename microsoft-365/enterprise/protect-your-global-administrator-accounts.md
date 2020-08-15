---
title: Skydda dina Microsoft 365-globala administratörs konton
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/15/2020
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
f1.keywords:
- NOCSH
ms.assetid: 6b4ded77-ac8d-42ed-8606-c014fd947560
description: I den här artikeln finns information om hur du skyddar global administratör till din Microsoft 365-prenumeration.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 08e0960e7150395b2997dbd9ff0a1818822e17e2
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696693"
---
# <a name="protect-your-microsoft-365-global-administrator-accounts"></a><span data-ttu-id="dd8a3-103">Skydda dina Microsoft 365-globala administratörs konton</span><span class="sxs-lookup"><span data-stu-id="dd8a3-103">Protect your Microsoft 365 global administrator accounts</span></span>

<span data-ttu-id="dd8a3-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="dd8a3-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="dd8a3-105">Säkerhets brott för en Microsoft 365-prenumeration, inklusive information om att skörda och nätfiske-attacker, görs normalt genom att kompromissa med autentiseringsuppgifterna för ett globalt administratörs konto för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-105">Security breaches of a Microsoft 365 subscription, including information harvesting and phishing attacks, are typically done by compromising the credentials of a Microsoft 365 global administrator account.</span></span> <span data-ttu-id="dd8a3-106">Säkerhet i molnet är ett samarbete mellan dig och Microsoft:</span><span class="sxs-lookup"><span data-stu-id="dd8a3-106">Security in the cloud is a partnership between you and Microsoft:</span></span>
  
- <span data-ttu-id="dd8a3-107">Microsofts moln tjänster bygger på förtroende och säkerhet.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-107">Microsoft cloud services are built on a foundation of trust and security.</span></span> <span data-ttu-id="dd8a3-108">Microsoft tillhandahåller säkerhets kontroller och funktioner som hjälper dig att skydda dina data och program.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-108">Microsoft provides you security controls and capabilities to help you protect your data and applications.</span></span>
    
- <span data-ttu-id="dd8a3-109">Du äger dina data och identiteter och ansvaret för att skydda dem, säkerheten för dina lokala resurser och säkerheten för de moln komponenter du kontrollerar.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-109">You own your data and identities and the responsibility for protecting them, the security of your on-premises resources, and the security of cloud components you control.</span></span>
    
<span data-ttu-id="dd8a3-110">Microsoft tillhandahåller funktioner för att skydda din organisation, men de gäller bara om du använder dem.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-110">Microsoft provides capabilities to help protect your organization, but they are effective only if you use them.</span></span> <span data-ttu-id="dd8a3-111">Om du inte använder dem kan du vara utsatt för angrepp.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-111">If you do not use them, you may be vulnerable to attack.</span></span> <span data-ttu-id="dd8a3-112">För att skydda dina globala administratörs konton finns Microsoft här för att hjälpa dig med detaljerade instruktioner för att:</span><span class="sxs-lookup"><span data-stu-id="dd8a3-112">To protect your global administrator accounts, Microsoft is here to help you with detailed instructions to:</span></span>
  
1. <span data-ttu-id="dd8a3-113">Skapa dedikerade Microsoft 365-globala administratörs konton och Använd dem bara när det behövs.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-113">Create dedicated Microsoft 365 global administrator accounts and use them only when necessary.</span></span>
    
2. <span data-ttu-id="dd8a3-114">Konfigurera multifaktorautentisering för dina dedikerade Microsoft 365-globala administratörs konton och Använd den starkaste formen av sekundär verifikation.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-114">Configure multi-factor authentication for your dedicated Microsoft 365 global administrator accounts and use the strongest form of secondary authentication.</span></span>
    
> <span data-ttu-id="dd8a3-115">[! OBS! om den här artikeln är inriktad på globala administratörs konton bör du överväga om ytterligare konton med behörighet att få åtkomst till data i ditt abonnemang, till exempel en eDiscovery-administratör eller säkerhets-eller efterlevnad administratörs konton, ska skyddas på samma sätt.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-115">[!NOTES] Although this article is focused on global administrator accounts, you should consider whether additional accounts with wide-ranging permissions to access the data in your subscription, such as eDiscovery administrator or security or compliance administrator accounts, should be protected in the same way.</span></span> <br > <span data-ttu-id="dd8a3-116">Ett globalt administratörs konto kan skapas utan att några licenser läggs till.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-116">A global administrator account can be created without adding any licenses.</span></span>
  
## <a name="step-1-create-dedicated-microsoft-365-global-administrator-accounts-and-use-them-only-when-necessary"></a><span data-ttu-id="dd8a3-117">Steg 1.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-117">Step 1.</span></span> <span data-ttu-id="dd8a3-118">Skapa dedikerade Microsoft 365-globala administratörs konton och Använd dem bara när det behövs</span><span class="sxs-lookup"><span data-stu-id="dd8a3-118">Create dedicated Microsoft 365 global administrator accounts and use them only when necessary</span></span>

<span data-ttu-id="dd8a3-119">Det finns relativt få administrativa uppgifter, till exempel tilldela roller till användar konton, som kräver globala administratörs behörigheter.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-119">There are relatively few administrative tasks, such as assigning roles to user accounts, that require global administrator privileges.</span></span> <span data-ttu-id="dd8a3-120">I stället för att använda vardagliga användar konton som har tilldelats rollen som global administratör gör du därför följande:</span><span class="sxs-lookup"><span data-stu-id="dd8a3-120">Therefore, instead of using everyday user accounts that have been assigned the global admin role, do these steps:</span></span>
  
1. <span data-ttu-id="dd8a3-121">Bestäm vilka användar konton som har tilldelats rollen som global administratör.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-121">Determine the set of user accounts that have been assigned the global admin role.</span></span> <span data-ttu-id="dd8a3-122">Det här kan du göra med kommandot Azure Active (Azure AD) Directory PowerShell for Graph:</span><span class="sxs-lookup"><span data-stu-id="dd8a3-122">You can do this with Azure Active (Azure AD) Directory PowerShell for Graph command:</span></span>
  
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

2. <span data-ttu-id="dd8a3-123">Logga in på din Microsoft 365-prenumeration med ett användar konto som har tilldelats rollen som global administratör.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-123">Sign into your Microsoft 365 subscription with a user account that has been assigned the global admin role.</span></span>
    
3. <span data-ttu-id="dd8a3-124">Skapa upp till fyra dedikerade globala administratörs konton.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-124">Create up to a maximum of four dedicated global administrator user accounts.</span></span> <span data-ttu-id="dd8a3-125">**Använd starka lösen ord som är minst 12 tecken långa.**</span><span class="sxs-lookup"><span data-stu-id="dd8a3-125">**Use strong passwords at least 12 characters long.**</span></span> <span data-ttu-id="dd8a3-126">Mer information finns i [skapa ett starkt lösen ord](https://support.microsoft.com/help/4026406/microsoft-account-create-a-strong-password) .</span><span class="sxs-lookup"><span data-stu-id="dd8a3-126">See [Create a strong password](https://support.microsoft.com/help/4026406/microsoft-account-create-a-strong-password) for more information.</span></span> <span data-ttu-id="dd8a3-127">Lagra lösen orden för de nya kontona på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-127">Store the passwords for the new accounts in a secure location.</span></span> 
    
4. <span data-ttu-id="dd8a3-128">Tilldela den globala administratörs rollen till alla nya dedikerade globala administratörs konton.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-128">Assign the global admin role to each of the new dedicated global administrator user accounts.</span></span>
    
5. <span data-ttu-id="dd8a3-129">Logga ut från Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-129">Sign out of Microsoft 365.</span></span>
    
6. <span data-ttu-id="dd8a3-130">Logga in med ett av de nya dedikerade globala administratörs kontona.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-130">Sign in with one of the new dedicated global administrator user accounts.</span></span>
    
7. <span data-ttu-id="dd8a3-131">För varje befintligt användar konto som har tilldelats rollen global administratör från steg 1:</span><span class="sxs-lookup"><span data-stu-id="dd8a3-131">For each existing user account that had been assigned the global admin role from step 1:</span></span>
    
  - <span data-ttu-id="dd8a3-132">Ta bort rollen som global administratör.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-132">Remove the global admin role.</span></span>
    
  - <span data-ttu-id="dd8a3-133">Tilldela administratörs roller till det konto som är lämpligt för den användarens jobb funktion och ansvar.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-133">Assign admin roles to the account that are appropriate to that user's job function and responsibility.</span></span> <span data-ttu-id="dd8a3-134">Mer information om olika administrativa roller i Microsoft 365 finns i [om administratörs roller](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="dd8a3-134">For more information about various admin roles in Microsoft 365, see [About admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span></span>
    
8. <span data-ttu-id="dd8a3-135">Logga ut från Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-135">Sign out of Microsoft 365.</span></span>
    
<span data-ttu-id="dd8a3-136">Resultatet ska vara:</span><span class="sxs-lookup"><span data-stu-id="dd8a3-136">The result should be:</span></span>
  
- <span data-ttu-id="dd8a3-137">De enda användar konton i prenumerationen som har rollen global administratör är den nya uppsättningen globala administratörs konton.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-137">The only user accounts in your subscription that have the global admin role are the new set of dedicated global administrator accounts.</span></span> <span data-ttu-id="dd8a3-138">Verifiera detta med följande PowerShell-kommando:</span><span class="sxs-lookup"><span data-stu-id="dd8a3-138">Verify this with the following PowerShell command:</span></span>
    
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

- <span data-ttu-id="dd8a3-139">Alla andra användar konton som hanterar ditt abonnemang har administratörs roller kopplade till deras arbets ansvar.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-139">All other everyday user accounts that manage your subscription have admin roles assigned that are associated with their job responsibilities.</span></span>
    
<span data-ttu-id="dd8a3-140">Från och med nu loggar du in med de dedikerade globala administratörs kontona för aktiviteter som kräver globala administratörs behörigheter.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-140">From this moment onward, you sign in with the dedicated global administrator accounts only for tasks that require global administrator privileges.</span></span> <span data-ttu-id="dd8a3-141">All annan Microsoft 365-administration måste göras genom att tilldela andra administrativa roller till användar konton.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-141">All other Microsoft 365 administration must be done by assigning other administration roles to user accounts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dd8a3-142">Detta kräver ytterligare åtgärder för att logga ut som ditt användar konto och logga in med ett dedikerat globalt administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-142">This does require additional steps to sign out as your everyday user account and sign in with a dedicated global administrator account.</span></span> <span data-ttu-id="dd8a3-143">Men detta behöver du bara göra ibland för globala administratörer.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-143">But this only needs to be done occasionally for global administrator operations.</span></span> <span data-ttu-id="dd8a3-144">Överväg att återställa ditt Microsoft 365-abonnemang efter det att ett globalt administratörs konto bryter mot en mängd olika steg.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-144">Consider that recovering your Microsoft 365 subscription after a global administrator account breach requires a lot more steps.</span></span>
  
## <a name="step-2-configure-multi-factor-authentication-for-your-dedicated-microsoft-365-global-administrator-accounts-and-use-the-strongest-form-of-additional-verification"></a><span data-ttu-id="dd8a3-145">Steg 2.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-145">Step 2.</span></span> <span data-ttu-id="dd8a3-146">Konfigurera multifaktorautentisering för dina dedikerade Microsoft 365-globala administratörs konton och Använd den starkaste formen av ytterligare verifiering</span><span class="sxs-lookup"><span data-stu-id="dd8a3-146">Configure multi-factor authentication for your dedicated Microsoft 365 global administrator accounts and use the strongest form of additional verification</span></span>

<span data-ttu-id="dd8a3-147">Multifaktorautentisering kräver ytterligare information utöver konto namn och lösen ord.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-147">Multi-factor authentication (MFA) requires additional information beyond the account name and password.</span></span> <span data-ttu-id="dd8a3-148">Microsoft 365 har stöd för följande ytterligare verifierings metoder:</span><span class="sxs-lookup"><span data-stu-id="dd8a3-148">Microsoft 365 supports these additional verification methods:</span></span>
  
- <span data-ttu-id="dd8a3-149">Microsoft Authenticator-appen</span><span class="sxs-lookup"><span data-stu-id="dd8a3-149">The Microsoft Authenticator app</span></span>

- <span data-ttu-id="dd8a3-150">Ett telefonsamtal</span><span class="sxs-lookup"><span data-stu-id="dd8a3-150">A phone call</span></span>
    
- <span data-ttu-id="dd8a3-151">En slumpvis genererad verifierings kod som skickas via ett textmeddelande</span><span class="sxs-lookup"><span data-stu-id="dd8a3-151">A randomly generated verification code sent through a text message</span></span>
    
- <span data-ttu-id="dd8a3-152">Ett smartkort (virtuellt eller fysiskt)</span><span class="sxs-lookup"><span data-stu-id="dd8a3-152">A smart card (virtual or physical)</span></span>
    
- <span data-ttu-id="dd8a3-153">En biometrisk enhet</span><span class="sxs-lookup"><span data-stu-id="dd8a3-153">A biometric device</span></span>
    
>[!Note]
><span data-ttu-id="dd8a3-154">För organisationer som måste följa nationella institutet för standarder och teknik (NIST) är det bara att använda ett telefonsamtal eller SMS-baserade ytterligare verifierings metoder.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-154">For organizations that must adhere to National Institute of Standards and Technology (NIST) standards, the use of a phone call or text message-based additional verification methods are restricted.</span></span> <span data-ttu-id="dd8a3-155">Klicka [här](https://pages.nist.gov/800-63-FAQ/#q-b01) för mer information.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-155">Click [here](https://pages.nist.gov/800-63-FAQ/#q-b01) for the details.</span></span>
>

<span data-ttu-id="dd8a3-156">Om du har ett litet företag som bara använder användar konton som lagras i molnet (den molnbaserade identitets modellen) följer du de här stegen för att konfigurera MFA med ett telefonsamtal eller en verifierings kod för SMS som skickas till en smart telefon:</span><span class="sxs-lookup"><span data-stu-id="dd8a3-156">If you are a small business that is using user accounts stored only in the cloud (the cloud-only identity model), use these steps to configure MFA using a phone call or a text message verification code sent to a smart phone:</span></span>
  
1. <span data-ttu-id="dd8a3-157">[Konfigurera MFA](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).</span><span class="sxs-lookup"><span data-stu-id="dd8a3-157">[Set up MFA](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>
    
2. <span data-ttu-id="dd8a3-158">Konfigurera [MFA för Microsoft 365](https://support.office.com/article/Set-up-2-step-verification-for-Office-365-ace1d096-61e5-449b-a875-58eb3d74de14) för att ställa in alla dedikerade globala administratörs konton för telefonsamtal eller textmeddelande som verifierings metod.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-158">[Set up MFA for Microsoft 365](https://support.office.com/article/Set-up-2-step-verification-for-Office-365-ace1d096-61e5-449b-a875-58eb3d74de14) to configure each dedicated global administrator account for phone call or text message as the verification method.</span></span> 
    
<span data-ttu-id="dd8a3-159">Om du är en större organisation som använder en Microsoft 365-Hybrid identitets modell har du fler verifierings alternativ.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-159">If you are a larger organization that is using a Microsoft 365 hybrid identity model, you have more verification options.</span></span> <span data-ttu-id="dd8a3-160">Om du inte redan har säkerhets infrastrukturen för bättre metod för sekundär autentisering kan du följa de här stegen:</span><span class="sxs-lookup"><span data-stu-id="dd8a3-160">If you have the security infrastructure already in place for a stronger secondary authentication method, use these steps:</span></span>
  
1. <span data-ttu-id="dd8a3-161">[Konfigurera MFA](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).</span><span class="sxs-lookup"><span data-stu-id="dd8a3-161">[Set up MFA](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>
    
2. <span data-ttu-id="dd8a3-162">Konfigurera [MFA för dina nya globala administratörs konton](https://support.office.com/article/set-up-your-microsoft-365-sign-in-for-multi-factor-authentication-ace1d096-61e5-449b-a875-58eb3d74de14) om du vill att varje dedicerat globalt administratörs konto ska vara tillämpligt.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-162">[Set up MFA for your new global admin accounts](https://support.office.com/article/set-up-your-microsoft-365-sign-in-for-multi-factor-authentication-ace1d096-61e5-449b-a875-58eb3d74de14) to configure each dedicated global administrator account for the appropriate verification method.</span></span> 
    
<span data-ttu-id="dd8a3-163">Om säkerhets infrastrukturen för den önskade starkare verifierings metoden inte är avsedd för Microsoft 365 MFA rekommenderar vi starkt att du konfigurerar dedikerade globala administratörs konton med MFA med hjälp av Microsoft Authenticator-appen, ett telefonsamtal eller en verifierings kod för SMS till en smart telefon för dina globala administratörs konton som en interimistisk säkerhets åtgärd.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-163">If the security infrastructure for the desired stronger verification method is not in place and functioning for Microsoft 365 MFA, we strongly recommend that you configure dedicated global administrator accounts with MFA using the Microsoft Authenticator app, a phone call, or a text message verification code sent to a smart phone for your global administrator accounts as an interim security measure.</span></span> <span data-ttu-id="dd8a3-164">Lämna inte dina dedikerade globala administratörs konton utan ytterligare skydd från MFA.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-164">Do not leave your dedicated global administrator accounts without the additional protection provided by MFA.</span></span>
  
<span data-ttu-id="dd8a3-165">Mer information finns i [Planera för multifaktorautentisering för Microsoft 365-distributioner](https://docs.microsoft.com/office365/admin/security-and-compliance/multi-factor-authentication-plan).</span><span class="sxs-lookup"><span data-stu-id="dd8a3-165">For more information, see [Plan for multi-factor authentication for Microsoft 365 Deployments](https://docs.microsoft.com/office365/admin/security-and-compliance/multi-factor-authentication-plan).</span></span>
  
<span data-ttu-id="dd8a3-166">Om du vill ansluta till Microsoft 365-tjänster med MFA och PowerShell kan du läsa följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="dd8a3-166">To connect to Microsoft 365 services with MFA and PowerShell, see these articles:</span></span>

- [<span data-ttu-id="dd8a3-167">PowerShell för Microsoft 365 för användar konton, grupper och licenser</span><span class="sxs-lookup"><span data-stu-id="dd8a3-167">PowerShell for Microsoft 365 for user accounts, groups, and licenses</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="dd8a3-168">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dd8a3-168">Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-install)
- [<span data-ttu-id="dd8a3-169">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="dd8a3-169">Exchange Online</span></span>](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps#connect-to-exchange-online-powershell-by-using-mfa)
- [<span data-ttu-id="dd8a3-170">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="dd8a3-170">SharePoint Online</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online#to-connect-with-multifactor-authentication-mfa)
- <span data-ttu-id="dd8a3-171">[Skype för företag – Online] hantera-Skype-för-företag-Online-med-Microsoft-365-PowerShell # Connect-on-a-Skype-för-företag-Online-administratör-konto-med-Multi-Factor-Cover)</span><span class="sxs-lookup"><span data-stu-id="dd8a3-171">[Skype for Business Online]manage-skype-for-business-online-with-microsoft-365-powershell#connect-using-a-skype-for-business-online-administrator-account-with-multi-factor-authentication)</span></span>

## <a name="additional-protections-for-enterprise-organizations"></a><span data-ttu-id="dd8a3-172">Ytterligare skydd för företags organisationer</span><span class="sxs-lookup"><span data-stu-id="dd8a3-172">Additional protections for enterprise organizations</span></span>

<span data-ttu-id="dd8a3-173">Efter steg 1 och 2 kan du använda följande metoder för att se till att ditt globala administratörs konto och konfigurationen som du utför använder det är så säkert som möjligt.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-173">After steps 1 and 2, use these additional methods to ensure that your global administrator account, and the configuration that you perform using it, are as secure as possible.</span></span>
  
### <a name="privileged-access-workstation"></a><span data-ttu-id="dd8a3-174">Privilegie rad åtkomst arbets Station</span><span class="sxs-lookup"><span data-stu-id="dd8a3-174">Privileged access workstation</span></span>

<span data-ttu-id="dd8a3-175">Använd en privilegie rad arbets Station (PAW) för att säkerställa att det är så säkert som möjligt att köra mycket privilegierade uppgifter.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-175">To ensure that the execution of highly privileged tasks is as secure as possible, use a privileged access workstation (PAW).</span></span> <span data-ttu-id="dd8a3-176">En PAW är en dedikerad dator som endast används för känsliga konfigurations uppgifter, till exempel Microsoft 365-konfiguration som kräver ett globalt administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-176">A PAW is a dedicated computer that is only used for sensitive configuration tasks, such as Microsoft 365 configuration that requires a global administrator account.</span></span> <span data-ttu-id="dd8a3-177">Eftersom den här datorn inte används dagligen för Internet-surfning eller e-post skyddas den bättre mot Internet attacker och hot.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-177">Because this computer is not used daily for Internet browsing or email, it is better protected from Internet attacks and threats.</span></span>
  
<span data-ttu-id="dd8a3-178">Instruktioner om hur du konfigurerar en PAW finns i [https://aka.ms/cyberpaw](https://aka.ms/cyberpaw) .</span><span class="sxs-lookup"><span data-stu-id="dd8a3-178">For instructions on how to set up a PAW, see [https://aka.ms/cyberpaw](https://aka.ms/cyberpaw).</span></span>
  
### <a name="azure-ad-privileged-identity-management"></a><span data-ttu-id="dd8a3-179">Azure Active Directory Privileged Identity Management</span><span class="sxs-lookup"><span data-stu-id="dd8a3-179">Azure AD Privileged Identity Management</span></span>

<span data-ttu-id="dd8a3-180">I stället för att låta globala administratörs konton vara kopplade till rollen som global administratör kan du använda Azure AD privilegierad identitets hantering (PIM) för att aktivera vid begäran, direkt tilldelning av den globala administratörs rollen när det behövs.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-180">Rather than having your global administrator accounts be permanently assigned the global administrator role, you can use Azure AD Privileged Identity Management (PIM) to enable on-demand, just-in-time assignment of the global administrator role when it is needed.</span></span>
  
<span data-ttu-id="dd8a3-181">I stället för att dina globala administratörs konton är permanenta administratörer blir de berättigade.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-181">Instead of your global administrator accounts being a permanent admin, they become eligible administrators.</span></span> <span data-ttu-id="dd8a3-182">Rollen som global administratör är inaktiv tills någon behöver den.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-182">The global administrator role is inactive until someone needs it.</span></span> <span data-ttu-id="dd8a3-183">Därefter utför du en aktiverings process för att lägga till rollen global administratör till det globala administratörs kontot för en förutbestämd tid.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-183">You then complete an activation process to add the global administrator role to the global administrator account for a predetermined amount of time.</span></span> <span data-ttu-id="dd8a3-184">När tiden går ut tar PIM bort rollen som global administratör från det globala administratörskontot.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-184">When the time expires, PIM removes the global administrator role from the global administrator account.</span></span>
  
<span data-ttu-id="dd8a3-185">Om du använder PIM och den här processen minskar avsevärt hur länge dina globala administratörs konton drabbas av attacker och användning av illvilliga användare.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-185">Using PIM and this process significantly reduces the amount of time that your global administrator accounts are vulnerable to attack and use by malicious users.</span></span>

<span data-ttu-id="dd8a3-186">PIM är tillgängligt med Azure AD Premium P2, som ingår i Microsoft 365 Enterprise, E5 eller Enterprise Mobility + Security (EMS), eller så kan du köpa enskilda licenser för dina globala administratörs konton.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-186">PIM is available with Azure AD Premium P2, which is included with Microsoft 365 Enterprise E5 or Enterprise Mobility + Security (EMS) E5, or you can purchase individual licenses for your global administrator accounts.</span></span>
  
<span data-ttu-id="dd8a3-187">Mer information finns i [Azure AD-privilegierad identitets hantering](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span><span class="sxs-lookup"><span data-stu-id="dd8a3-187">For more information, see [Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>
  
### <a name="security-information-and-event-management-siem-software-for-microsoft-365-logging"></a><span data-ttu-id="dd8a3-188">Säkerhets information och SIEM program vara för Microsoft 365-loggning</span><span class="sxs-lookup"><span data-stu-id="dd8a3-188">Security information and event management (SIEM) software for Microsoft 365 logging</span></span>

<span data-ttu-id="dd8a3-189">SIEM program vara körs på en server utför en analys i real tid av säkerhets varningar och händelser som skapas av program och nätverks maskin vara.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-189">SIEM software run on a server performs real-time analysis of security alerts and events created by applications and network hardware.</span></span> <span data-ttu-id="dd8a3-190">För att din SIEM-Server ska innehålla Microsoft 365-säkerhets varningar och-händelser i dess analys-och rapporterings funktioner integrerar du Azure AD i dig SEIM.</span><span class="sxs-lookup"><span data-stu-id="dd8a3-190">To allow your SIEM server to include Microsoft 365 security alerts and events in its analysis and reporting functions, integrate Azure AD into you SEIM.</span></span> <span data-ttu-id="dd8a3-191">Se [Introduktion till Azure logg integrering](https://docs.microsoft.com/azure/security/security-azure-log-integration-overview).</span><span class="sxs-lookup"><span data-stu-id="dd8a3-191">See [Introduction to Azure Log Integration](https://docs.microsoft.com/azure/security/security-azure-log-integration-overview).</span></span>

## <a name="next-step"></a><span data-ttu-id="dd8a3-192">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="dd8a3-192">Next step</span></span>

<span data-ttu-id="dd8a3-193">Om du konfigurerar identitet för din Microsoft 365-prenumeration, se:</span><span class="sxs-lookup"><span data-stu-id="dd8a3-193">If you're setting up identity for your Microsoft 365 subscription, see:</span></span>

- <span data-ttu-id="dd8a3-194">[Endast moln identiteter](cloud-only-identities.md) om du använder moln-Only-identitet</span><span class="sxs-lookup"><span data-stu-id="dd8a3-194">[Cloud-only identities](cloud-only-identities.md) if you're using cloud-only identity</span></span>
- <span data-ttu-id="dd8a3-195">[Förbereda för Active Directory-synkronisering](prepare-for-directory-synchronization.md) om du använder hybrid identitet</span><span class="sxs-lookup"><span data-stu-id="dd8a3-195">[Prepare for directory synchronization](prepare-for-directory-synchronization.md) if you're using hybrid identity</span></span>

  
## <a name="see-also"></a><span data-ttu-id="dd8a3-196">Se även</span><span class="sxs-lookup"><span data-stu-id="dd8a3-196">See also</span></span>

<span data-ttu-id="dd8a3-197">[Säkerhets översikt för Microsoft 365](https://docs.microsoft.com/office365/securitycompliance/security-roadmap).</span><span class="sxs-lookup"><span data-stu-id="dd8a3-197">[Microsoft 365 security roadmap](https://docs.microsoft.com/office365/securitycompliance/security-roadmap).</span></span>
