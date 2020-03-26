---
title: Krav för identitets- och enhetsåtkomst för synkronisering av lösenordshash i din Microsoft 365-testmiljö
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Skapa en Microsoft 365-miljö för att testa identitets- och enhetsåtkomst med kraven för autentisering av synkronisering av lösenordshash.
ms.openlocfilehash: 125d8c6e1e954a05edd630c8f4d55848fa3314b3
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42807632"
---
# <a name="identity-and-device-access-prerequisites-for-password-hash-synchronization-in-your-microsoft-365-test-environment"></a><span data-ttu-id="64669-103">Krav för identitets- och enhetsåtkomst för synkronisering av lösenordshash i din Microsoft 365-testmiljö</span><span class="sxs-lookup"><span data-stu-id="64669-103">Identity and device access prerequisites for password hash synchronization in your Microsoft 365 test environment</span></span>

<span data-ttu-id="64669-104">*Den här testlabbguiden kan bara användas i Microsoft 365 Enterprise-testmiljöer.*</span><span class="sxs-lookup"><span data-stu-id="64669-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="64669-105">[Konfigurationer för identitets- och enhetsåtkomst](microsoft-365-policies-configurations.md) är en uppsättning konfigurationer och principer för villkorsstyrd åtkomst som skyddar åtkomsten till alla tjänster som är integrerade med Azure Active Directory (Azure AD), inklusive Office 365 och Enterprise Mobility + Security (EMS) i Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="64669-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="64669-106">I den här artikeln beskrivs hur du kan konfigurera en Microsoft 365-testmiljö som uppfyller kraven för [konfiguration av Active Directory med förutsättningar för synkronisering av lösenordshash](identity-access-prerequisites.md#prerequisites) för identitets- och enhetsåtkomst.</span><span class="sxs-lookup"><span data-stu-id="64669-106">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [Active Directory with password hash sync prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="64669-107">Konfigurationen av testmiljön består av åtta faser:</span><span class="sxs-lookup"><span data-stu-id="64669-107">There are eight phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="64669-108">Skapa ett simulerat företag med testmiljö för synkronisering av lösenordshash</span><span class="sxs-lookup"><span data-stu-id="64669-108">Create a simulated enterprise with password hash sync test environment</span></span>
2.  <span data-ttu-id="64669-109">Konfigurera enkel inloggning med Azure AD</span><span class="sxs-lookup"><span data-stu-id="64669-109">Configure Azure AD seamless single sign-on</span></span>
3.  <span data-ttu-id="64669-110">Konfigurera namngivna platser</span><span class="sxs-lookup"><span data-stu-id="64669-110">Configure named locations</span></span>
4.  <span data-ttu-id="64669-111">Konfigurera tillbakaskrivning av lösenord</span><span class="sxs-lookup"><span data-stu-id="64669-111">Configure password writeback</span></span>
5.  <span data-ttu-id="64669-112">Konfigurera lösenordsåterställning via självbetjäning för alla användarkonton</span><span class="sxs-lookup"><span data-stu-id="64669-112">Configure self-service password reset for all user accounts</span></span>
6.  <span data-ttu-id="64669-113">Konfigurera multifaktorautentisering för alla användarkonton</span><span class="sxs-lookup"><span data-stu-id="64669-113">Configure multifactor authentication for all user accounts</span></span>
7.  <span data-ttu-id="64669-114">Aktivera Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="64669-114">Enable Azure AD Identity Protection</span></span>
8.  <span data-ttu-id="64669-115">Aktivera modern autentisering för Exchange Online och Skype för företag – Online</span><span class="sxs-lookup"><span data-stu-id="64669-115">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-simulated-enterprise-with-password-hash-sync-microsoft-365-test-environment"></a><span data-ttu-id="64669-116">Fas 1: Bygg ut det simulerade företaget med lösenordshash-synkronisering för Microsoft 365-testmiljön</span><span class="sxs-lookup"><span data-stu-id="64669-116">Phase 1: Build out your simulated enterprise with password hash sync Microsoft 365 test environment</span></span>

<span data-ttu-id="64669-117">Följ anvisningarna i [Synkronisering av hash-lösenord](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="64669-117">Follow the instructions in [Password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span>
<span data-ttu-id="64669-118">Här är konfigurationsresultatet.</span><span class="sxs-lookup"><span data-stu-id="64669-118">Here is the resulting configuration.</span></span>

![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="64669-120">Fas 2: Konfigurera enkel inloggning med Azure AD</span><span class="sxs-lookup"><span data-stu-id="64669-120">Phase 2: Configure Azure AD seamless single sign-on</span></span>

<span data-ttu-id="64669-121">Följ anvisningarna i [fas 2 i testlabbguiden för enkel inloggning med Azure AD](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span><span class="sxs-lookup"><span data-stu-id="64669-121">Follow the instructions in [Phase 2 of the Azure AD Seamless Single Sign-on Test Lab Guide](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span></span>

## <a name="phase-3-configure-named-locations"></a><span data-ttu-id="64669-122">Fas 3: Konfigurera namngivna platser</span><span class="sxs-lookup"><span data-stu-id="64669-122">Phase 3: Configure named locations</span></span>

<span data-ttu-id="64669-123">Bestäm först de offentliga IP-adresser eller adress intervall som används av din organisation.</span><span class="sxs-lookup"><span data-stu-id="64669-123">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="64669-124">Följ sedan anvisningarna i [Konfigurera namngivna platser i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) för att lägga till adresserna eller adressintervallen som namngivna platser.</span><span class="sxs-lookup"><span data-stu-id="64669-124">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-4-configure-password-writeback"></a><span data-ttu-id="64669-125">Fas 4: Konfigurera tillbakaskrivning av lösenord</span><span class="sxs-lookup"><span data-stu-id="64669-125">Phase 4: Configure password writeback</span></span>

<span data-ttu-id="64669-126">Följ anvisningarna i [fas 2 i testlabbguiden för tillbakaskrivning av lösenord](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="64669-126">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-5-configure-self-service-password-reset"></a><span data-ttu-id="64669-127">Fas 5: Konfigurera lösenordsåterställning via självbetjäning</span><span class="sxs-lookup"><span data-stu-id="64669-127">Phase 5: Configure self-service password reset</span></span>

<span data-ttu-id="64669-128">Följ anvisningarna i [fas 3 i testlabbguiden för återställning av lösenord](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span><span class="sxs-lookup"><span data-stu-id="64669-128">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="64669-129">När du aktiverar återställning av lösenord för kontona i en särskild Azure AD-grupp lägger du till de här kontona i gruppen för**lösenordsåterställning**:</span><span class="sxs-lookup"><span data-stu-id="64669-129">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="64669-130">Användare 2</span><span class="sxs-lookup"><span data-stu-id="64669-130">User 2</span></span>
- <span data-ttu-id="64669-131">Användare 3</span><span class="sxs-lookup"><span data-stu-id="64669-131">User 3</span></span>
- <span data-ttu-id="64669-132">Användare 4</span><span class="sxs-lookup"><span data-stu-id="64669-132">User 4</span></span>
- <span data-ttu-id="64669-133">Användare 5</span><span class="sxs-lookup"><span data-stu-id="64669-133">User 5</span></span>

<span data-ttu-id="64669-134">Testa lösen ordet bara för användar 2-konto.</span><span class="sxs-lookup"><span data-stu-id="64669-134">Test password reset only for the User 2 account.</span></span>

## <a name="phase-6-configure-multi-factor-authentication"></a><span data-ttu-id="64669-135">Fas 6: Konfigurera multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="64669-135">Phase 6: Configure multi-factor authentication</span></span>

<span data-ttu-id="64669-136">Följ anvisningarna i [fas 2 i testlabbguiden för multifaktorautentisering](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) för följande användarkonton:</span><span class="sxs-lookup"><span data-stu-id="64669-136">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="64669-137">Användare 2</span><span class="sxs-lookup"><span data-stu-id="64669-137">User 2</span></span>
- <span data-ttu-id="64669-138">Användare 3</span><span class="sxs-lookup"><span data-stu-id="64669-138">User 3</span></span>
- <span data-ttu-id="64669-139">Användare 4</span><span class="sxs-lookup"><span data-stu-id="64669-139">User 4</span></span>
- <span data-ttu-id="64669-140">Användare 5</span><span class="sxs-lookup"><span data-stu-id="64669-140">User 5</span></span>

<span data-ttu-id="64669-141">Testa endast multifaktorautentisering för kontot Användare 2.</span><span class="sxs-lookup"><span data-stu-id="64669-141">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-7-enable-azure-ad-identity-protection"></a><span data-ttu-id="64669-142">Fas 7: Aktivera Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="64669-142">Phase 7: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="64669-143">Följ anvisningarna i [fas 2 i testlabbguiden för Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="64669-143">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="64669-144">Fas 8: Aktivera modern autentisering för Exchange Online och Skype för företag – Online</span><span class="sxs-lookup"><span data-stu-id="64669-144">Phase 8: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="64669-145">Följ [dessa anvisningar](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later) för Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="64669-145">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="64669-146">För Skype för företag – Online:</span><span class="sxs-lookup"><span data-stu-id="64669-146">For Skype for Business Online:</span></span>

1. <span data-ttu-id="64669-147">Ansluta till [Skype för företag – Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="64669-147">Connect to [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="64669-148">Kör det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="64669-148">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="64669-149">Kör följande kommando för att verifiera att ändringen genomfördes.</span><span class="sxs-lookup"><span data-stu-id="64669-149">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="64669-150">Resultatet är en testmiljö som uppfyller kraven för [konfiguration av Active Directory med förutsättningar för synkronisering av lösenordshash](identity-access-prerequisites.md#prerequisites) för identitets- och enhetsåtkomst.</span><span class="sxs-lookup"><span data-stu-id="64669-150">The result is a test environment that meets the requirements of the [Active Directory with password hash sync prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="64669-151">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="64669-151">Next step</span></span>

<span data-ttu-id="64669-152">Använd [vanliga identitets- och enhetsprinciper](identity-access-policies.md) när du vill konfigurera de principer som bygger på kraven och skyddar identiteter och enheter.</span><span class="sxs-lookup"><span data-stu-id="64669-152">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="64669-153">Snabbreferens</span><span class="sxs-lookup"><span data-stu-id="64669-153">See also</span></span>

[<span data-ttu-id="64669-154">Fler testlabbguider för identitet</span><span class="sxs-lookup"><span data-stu-id="64669-154">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="64669-155">Fas 2: identitet</span><span class="sxs-lookup"><span data-stu-id="64669-155">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="64669-156">Testlabbguider för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="64669-156">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="64669-157">Distribution av Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="64669-157">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="64669-158">Microsoft 365 Enterprise-dokumentation</span><span class="sxs-lookup"><span data-stu-id="64669-158">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
