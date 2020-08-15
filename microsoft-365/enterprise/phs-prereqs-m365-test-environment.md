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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Skapa en Microsoft 365-miljö för att testa identitets- och enhetsåtkomst med kraven för autentisering av synkronisering av lösenordshash.
ms.openlocfilehash: 6aa6b1cd1b8f9459b27e46fa67c62b35014b2d7e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686256"
---
# <a name="identity-and-device-access-prerequisites-for-password-hash-synchronization-in-your-microsoft-365-test-environment"></a><span data-ttu-id="62620-103">Krav för identitets- och enhetsåtkomst för synkronisering av lösenordshash i din Microsoft 365-testmiljö</span><span class="sxs-lookup"><span data-stu-id="62620-103">Identity and device access prerequisites for password hash synchronization in your Microsoft 365 test environment</span></span>

<span data-ttu-id="62620-104">*Den här test laboratorie guiden kan endast användas för test miljöer med Microsoft 365 för företags nätverk.*</span><span class="sxs-lookup"><span data-stu-id="62620-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="62620-105">[Konfigurationer för identitets-och enhets åtkomst](microsoft-365-policies-configurations.md) är en uppsättning konfigurationer och villkorsstyrda åtkomst principer för att skydda åtkomst till alla tjänster i Microsoft 365 för företag som är integrerade med Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="62620-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of configurations and conditional access policies to protect access to all services in Microsoft 365 for enterprise that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="62620-106">I den här artikeln beskrivs hur du kan konfigurera en Microsoft 365-testmiljö som uppfyller kraven för [konfiguration av Active Directory med förutsättningar för synkronisering av lösenordshash](identity-access-prerequisites.md#prerequisites) för identitets- och enhetsåtkomst.</span><span class="sxs-lookup"><span data-stu-id="62620-106">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [Active Directory with password hash sync prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="62620-107">Konfigurationen av testmiljön består av åtta faser:</span><span class="sxs-lookup"><span data-stu-id="62620-107">There are eight phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="62620-108">Skapa ett simulerat företag med testmiljö för synkronisering av lösenordshash</span><span class="sxs-lookup"><span data-stu-id="62620-108">Create a simulated enterprise with password hash sync test environment</span></span>
2.  <span data-ttu-id="62620-109">Konfigurera enkel inloggning med Azure AD</span><span class="sxs-lookup"><span data-stu-id="62620-109">Configure Azure AD seamless single sign-on</span></span>
3.  <span data-ttu-id="62620-110">Konfigurera namngivna platser</span><span class="sxs-lookup"><span data-stu-id="62620-110">Configure named locations</span></span>
4.  <span data-ttu-id="62620-111">Konfigurera tillbakaskrivning av lösenord</span><span class="sxs-lookup"><span data-stu-id="62620-111">Configure password writeback</span></span>
5.  <span data-ttu-id="62620-112">Konfigurera lösenordsåterställning via självbetjäning för alla användarkonton</span><span class="sxs-lookup"><span data-stu-id="62620-112">Configure self-service password reset for all user accounts</span></span>
6.  <span data-ttu-id="62620-113">Konfigurera multifaktorautentisering för alla användarkonton</span><span class="sxs-lookup"><span data-stu-id="62620-113">Configure multifactor authentication for all user accounts</span></span>
7.  <span data-ttu-id="62620-114">Aktivera Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="62620-114">Enable Azure AD Identity Protection</span></span>
8.  <span data-ttu-id="62620-115">Aktivera modern autentisering för Exchange Online och Skype för företag – Online</span><span class="sxs-lookup"><span data-stu-id="62620-115">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-simulated-enterprise-with-password-hash-sync-microsoft-365-test-environment"></a><span data-ttu-id="62620-116">Fas 1: Bygg ut det simulerade företaget med lösenordshash-synkronisering för Microsoft 365-testmiljön</span><span class="sxs-lookup"><span data-stu-id="62620-116">Phase 1: Build out your simulated enterprise with password hash sync Microsoft 365 test environment</span></span>

<span data-ttu-id="62620-117">Följ anvisningarna i [Synkronisering av hash-lösenord](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="62620-117">Follow the instructions in [Password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span>
<span data-ttu-id="62620-118">Här är konfigurationsresultatet.</span><span class="sxs-lookup"><span data-stu-id="62620-118">Here is the resulting configuration.</span></span>

![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="62620-120">Fas 2: Konfigurera enkel inloggning med Azure AD</span><span class="sxs-lookup"><span data-stu-id="62620-120">Phase 2: Configure Azure AD seamless single sign-on</span></span>

<span data-ttu-id="62620-121">Följ anvisningarna i [fas 2 i testlabbguiden för enkel inloggning med Azure AD](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span><span class="sxs-lookup"><span data-stu-id="62620-121">Follow the instructions in [Phase 2 of the Azure AD Seamless Single Sign-on Test Lab Guide](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span></span>

## <a name="phase-3-configure-named-locations"></a><span data-ttu-id="62620-122">Fas 3: Konfigurera namngivna platser</span><span class="sxs-lookup"><span data-stu-id="62620-122">Phase 3: Configure named locations</span></span>

<span data-ttu-id="62620-123">Bestäm först de offentliga IP-adresser eller adress intervall som används av din organisation.</span><span class="sxs-lookup"><span data-stu-id="62620-123">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="62620-124">Följ sedan anvisningarna i [Konfigurera namngivna platser i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) för att lägga till adresserna eller adressintervallen som namngivna platser.</span><span class="sxs-lookup"><span data-stu-id="62620-124">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-4-configure-password-writeback"></a><span data-ttu-id="62620-125">Fas 4: Konfigurera tillbakaskrivning av lösenord</span><span class="sxs-lookup"><span data-stu-id="62620-125">Phase 4: Configure password writeback</span></span>

<span data-ttu-id="62620-126">Följ anvisningarna i [fas 2 i testlabbguiden för tillbakaskrivning av lösenord](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="62620-126">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-5-configure-self-service-password-reset"></a><span data-ttu-id="62620-127">Fas 5: Konfigurera lösenordsåterställning via självbetjäning</span><span class="sxs-lookup"><span data-stu-id="62620-127">Phase 5: Configure self-service password reset</span></span>

<span data-ttu-id="62620-128">Följ anvisningarna i [fas 3 i testlabbguiden för återställning av lösenord](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span><span class="sxs-lookup"><span data-stu-id="62620-128">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="62620-129">När du aktiverar återställning av lösenord för kontona i en särskild Azure AD-grupp lägger du till de här kontona i gruppen för **lösenordsåterställning**:</span><span class="sxs-lookup"><span data-stu-id="62620-129">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="62620-130">Användare 2</span><span class="sxs-lookup"><span data-stu-id="62620-130">User 2</span></span>
- <span data-ttu-id="62620-131">Användare 3</span><span class="sxs-lookup"><span data-stu-id="62620-131">User 3</span></span>
- <span data-ttu-id="62620-132">Användare 4</span><span class="sxs-lookup"><span data-stu-id="62620-132">User 4</span></span>
- <span data-ttu-id="62620-133">Användare 5</span><span class="sxs-lookup"><span data-stu-id="62620-133">User 5</span></span>

<span data-ttu-id="62620-134">Testa lösen ordet bara för användar 2-konto.</span><span class="sxs-lookup"><span data-stu-id="62620-134">Test password reset only for the User 2 account.</span></span>

## <a name="phase-6-configure-multi-factor-authentication"></a><span data-ttu-id="62620-135">Fas 6: Konfigurera multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="62620-135">Phase 6: Configure multi-factor authentication</span></span>

<span data-ttu-id="62620-136">Följ anvisningarna i [fas 2 i testlabbguiden för multifaktorautentisering](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) för följande användarkonton:</span><span class="sxs-lookup"><span data-stu-id="62620-136">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="62620-137">Användare 2</span><span class="sxs-lookup"><span data-stu-id="62620-137">User 2</span></span>
- <span data-ttu-id="62620-138">Användare 3</span><span class="sxs-lookup"><span data-stu-id="62620-138">User 3</span></span>
- <span data-ttu-id="62620-139">Användare 4</span><span class="sxs-lookup"><span data-stu-id="62620-139">User 4</span></span>
- <span data-ttu-id="62620-140">Användare 5</span><span class="sxs-lookup"><span data-stu-id="62620-140">User 5</span></span>

<span data-ttu-id="62620-141">Testa endast multifaktorautentisering för kontot Användare 2.</span><span class="sxs-lookup"><span data-stu-id="62620-141">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-7-enable-azure-ad-identity-protection"></a><span data-ttu-id="62620-142">Fas 7: Aktivera Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="62620-142">Phase 7: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="62620-143">Följ anvisningarna i [fas 2 i testlabbguiden för Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="62620-143">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="62620-144">Fas 8: Aktivera modern autentisering för Exchange Online och Skype för företag – Online</span><span class="sxs-lookup"><span data-stu-id="62620-144">Phase 8: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="62620-145">Följ [dessa anvisningar](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later) för Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="62620-145">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="62620-146">För Skype för företag – Online:</span><span class="sxs-lookup"><span data-stu-id="62620-146">For Skype for Business Online:</span></span>

1. <span data-ttu-id="62620-147">Anslut till [Skype för företag – Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="62620-147">Connect to [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="62620-148">Kör det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="62620-148">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="62620-149">Kör följande kommando för att verifiera att ändringen genomfördes.</span><span class="sxs-lookup"><span data-stu-id="62620-149">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="62620-150">Resultatet är en testmiljö som uppfyller kraven för [konfiguration av Active Directory med förutsättningar för synkronisering av lösenordshash](identity-access-prerequisites.md#prerequisites) för identitets- och enhetsåtkomst.</span><span class="sxs-lookup"><span data-stu-id="62620-150">The result is a test environment that meets the requirements of the [Active Directory with password hash sync prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="62620-151">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="62620-151">Next step</span></span>

<span data-ttu-id="62620-152">Använd [vanliga identitets- och enhetsprinciper](identity-access-policies.md) när du vill konfigurera de principer som bygger på kraven och skyddar identiteter och enheter.</span><span class="sxs-lookup"><span data-stu-id="62620-152">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="62620-153">Se även</span><span class="sxs-lookup"><span data-stu-id="62620-153">See also</span></span>

[<span data-ttu-id="62620-154">Fler testlabbguider för identitet</span><span class="sxs-lookup"><span data-stu-id="62620-154">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="62620-155">Identitets översikt</span><span class="sxs-lookup"><span data-stu-id="62620-155">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="62620-156">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="62620-156">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="62620-157">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="62620-157">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="62620-158">Microsoft 365 för företags dokumentation</span><span class="sxs-lookup"><span data-stu-id="62620-158">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
