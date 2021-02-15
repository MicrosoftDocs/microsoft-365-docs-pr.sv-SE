---
title: Krav för identitets- och enhetsåtkomst för direktautentisering i din Microsoft 365-testmiljö
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Skapa en Microsoft 365-miljö för att testa identitets- och enhetsåtkomst med kraven för direktautentisering.
ms.openlocfilehash: 71ba116ee45f031b156934e0924a0c3d460110d5
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233768"
---
# <a name="identity-and-device-access-prerequisites-for-pass-through-authentication-in-your-microsoft-365-test-environment"></a><span data-ttu-id="58300-103">Krav för identitets- och enhetsåtkomst för direktautentisering i din Microsoft 365-testmiljö</span><span class="sxs-lookup"><span data-stu-id="58300-103">Identity and device access prerequisites for pass-through authentication in your Microsoft 365 test environment</span></span>

<span data-ttu-id="58300-104">*Den här testlabbguiden kan endast användas för Microsoft 365 för företags testmiljöer.*</span><span class="sxs-lookup"><span data-stu-id="58300-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="58300-105">[Konfigurationer för identitets-](../security/office-365-security/microsoft-365-policies-configurations.md) och enhetsåtkomst är en uppsättning konfigurationer och villkorsstyrda åtkomstprinciper för att skydda åtkomsten till alla tjänster i Microsoft 365 för företag som är integrerade med Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="58300-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of configurations and conditional access policies to protect access to all services in Microsoft 365 for enterprise that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="58300-106">I den här artikeln beskrivs hur du kan konfigurera en Microsoft 365-testmiljö som uppfyller kraven för [konfiguration av direktautentisering](../security/office-365-security/identity-access-prerequisites.md#prerequisites) för identitets- och enhetsåtkomst.</span><span class="sxs-lookup"><span data-stu-id="58300-106">This article describes how you can configure a Microsoft 365 test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="58300-107">Det finns tio faser för att konfigurera testmiljön:</span><span class="sxs-lookup"><span data-stu-id="58300-107">There are ten phases to setting up this test environment:</span></span>

1. <span data-ttu-id="58300-108">Bygga ut det simulerade företaget med direktautentisering för Microsoft 365-testmiljön</span><span class="sxs-lookup"><span data-stu-id="58300-108">Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>
2. <span data-ttu-id="58300-109">Konfigurera enkel inloggning med Azure AD</span><span class="sxs-lookup"><span data-stu-id="58300-109">Configure Azure AD seamless single sign-on</span></span>
3. <span data-ttu-id="58300-110">Konfigurera namngivna platser</span><span class="sxs-lookup"><span data-stu-id="58300-110">Configure named locations</span></span>
4. <span data-ttu-id="58300-111">Konfigurera tillbakaskrivning av lösenord</span><span class="sxs-lookup"><span data-stu-id="58300-111">Configure password writeback</span></span>
5. <span data-ttu-id="58300-112">Konfigurera lösenordsåterställning via självbetjäning</span><span class="sxs-lookup"><span data-stu-id="58300-112">Configure self-service password reset</span></span>
6. <span data-ttu-id="58300-113">Konfigurera multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="58300-113">Configure multifactor authentication</span></span>
7. <span data-ttu-id="58300-114">Aktivera automatisk enhetsregistrering för domänaktivade Windows-datorer</span><span class="sxs-lookup"><span data-stu-id="58300-114">Enable automatic device registration of domain-joined Windows computers</span></span>
8. <span data-ttu-id="58300-115">Konfigurera lösenordsskydd i Azure AD</span><span class="sxs-lookup"><span data-stu-id="58300-115">Configure Azure AD password protection</span></span> 
9. <span data-ttu-id="58300-116">Aktivera Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="58300-116">Enable Azure AD Identity Protection</span></span>
10. <span data-ttu-id="58300-117">Aktivera modern autentisering för Exchange Online och Skype för företag – Online</span><span class="sxs-lookup"><span data-stu-id="58300-117">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-simulated-enterprise-with-pass-through-authentication-microsoft-365-test-environment"></a><span data-ttu-id="58300-118">Fas 1: Bygga ut det simulerade företaget med direktautentisering för Microsoft 365-testmiljön</span><span class="sxs-lookup"><span data-stu-id="58300-118">Phase 1: Build out your simulated enterprise with pass-through authentication Microsoft 365 test environment</span></span>

<span data-ttu-id="58300-119">Följ anvisningarna i [Direktautentisering](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="58300-119">Follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

<span data-ttu-id="58300-120">Här är konfigurationsresultatet.</span><span class="sxs-lookup"><span data-stu-id="58300-120">Here is the resulting configuration.</span></span>

![Det simulerade företaget med testmiljö med direktautentisering](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="58300-122">Fas 2: Konfigurera enkel inloggning med Azure AD</span><span class="sxs-lookup"><span data-stu-id="58300-122">Phase 2: Configure Azure AD seamless single sign-on</span></span>

<span data-ttu-id="58300-123">Följ anvisningarna i [fas 2 i testlabbguiden för enkel inloggning med Azure AD](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span><span class="sxs-lookup"><span data-stu-id="58300-123">Follow the instructions in [Phase 2 of the Azure AD Seamless Single Sign-on Test Lab Guide](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span></span>

## <a name="phase-3-configure-named-locations"></a><span data-ttu-id="58300-124">Fas 3: Konfigurera namngivna platser</span><span class="sxs-lookup"><span data-stu-id="58300-124">Phase 3: Configure named locations</span></span>

<span data-ttu-id="58300-125">Bestäm först de offentliga IP-adresser eller adress intervall som används av din organisation.</span><span class="sxs-lookup"><span data-stu-id="58300-125">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="58300-126">Följ sedan anvisningarna i [Konfigurera namngivna platser i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) för att lägga till adresserna eller adressintervallen som namngivna platser.</span><span class="sxs-lookup"><span data-stu-id="58300-126">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-4-configure-password-writeback"></a><span data-ttu-id="58300-127">Fas 4: Konfigurera tillbakaskrivning av lösenord</span><span class="sxs-lookup"><span data-stu-id="58300-127">Phase 4: Configure password writeback</span></span>

<span data-ttu-id="58300-128">Följ anvisningarna i [fas 2 i testlabbguiden för tillbakaskrivning av lösenord](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="58300-128">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-5-configure-self-service-password-reset"></a><span data-ttu-id="58300-129">Fas 5: Konfigurera lösenordsåterställning via självbetjäning</span><span class="sxs-lookup"><span data-stu-id="58300-129">Phase 5: Configure self-service password reset</span></span>

<span data-ttu-id="58300-130">Följ anvisningarna i [fas 3 i testlabbguiden för återställning av lösenord](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span><span class="sxs-lookup"><span data-stu-id="58300-130">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="58300-131">När du aktiverar återställning av lösenord för kontona i en särskild Azure AD-grupp lägger du till de här kontona i gruppen för **lösenordsåterställning**:</span><span class="sxs-lookup"><span data-stu-id="58300-131">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="58300-132">Användare 2</span><span class="sxs-lookup"><span data-stu-id="58300-132">User 2</span></span>
- <span data-ttu-id="58300-133">Användare 3</span><span class="sxs-lookup"><span data-stu-id="58300-133">User 3</span></span>
- <span data-ttu-id="58300-134">Användare 4</span><span class="sxs-lookup"><span data-stu-id="58300-134">User 4</span></span>
- <span data-ttu-id="58300-135">Användare 5</span><span class="sxs-lookup"><span data-stu-id="58300-135">User 5</span></span>

<span data-ttu-id="58300-136">Testa lösen ordet bara för användar 2-konto.</span><span class="sxs-lookup"><span data-stu-id="58300-136">Test password reset only for the User 2 account.</span></span>

## <a name="phase-6-configure-multi-factor-authentication"></a><span data-ttu-id="58300-137">Fas 6: Konfigurera multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="58300-137">Phase 6: Configure multi-factor authentication</span></span>

<span data-ttu-id="58300-138">Följ anvisningarna i [fas 2 i testlabbguiden för multifaktorautentisering](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) för följande användarkonton:</span><span class="sxs-lookup"><span data-stu-id="58300-138">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="58300-139">Användare 2</span><span class="sxs-lookup"><span data-stu-id="58300-139">User 2</span></span>
- <span data-ttu-id="58300-140">Användare 3</span><span class="sxs-lookup"><span data-stu-id="58300-140">User 3</span></span>
- <span data-ttu-id="58300-141">Användare 4</span><span class="sxs-lookup"><span data-stu-id="58300-141">User 4</span></span>
- <span data-ttu-id="58300-142">Användare 5</span><span class="sxs-lookup"><span data-stu-id="58300-142">User 5</span></span>

<span data-ttu-id="58300-143">Testa endast multifaktorautentisering för kontot Användare 2.</span><span class="sxs-lookup"><span data-stu-id="58300-143">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-7-enable-automatic-device-registration-of-domain-joined-windows-computers"></a><span data-ttu-id="58300-144">Fas 7: Aktivera automatisk enhetsregistrering för domänaktivade Windows-datorer</span><span class="sxs-lookup"><span data-stu-id="58300-144">Phase 7: Enable automatic device registration of domain-joined Windows computers</span></span> 

<span data-ttu-id="58300-145">Följ [de här anvisningarna](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan) för att aktivera automatisk enhetsregistrering för domänaktivade Windows-datorer.</span><span class="sxs-lookup"><span data-stu-id="58300-145">Follow [these instructions](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan) to enable automatic device registration of domain-joined Windows computers.</span></span>

## <a name="phase-8-configure-azure-ad-password-protection"></a><span data-ttu-id="58300-146">Steg 8: Konfigurera lösenordsskydd i Azure AD</span><span class="sxs-lookup"><span data-stu-id="58300-146">Phase 8: Configure Azure AD password protection</span></span> 

<span data-ttu-id="58300-147">Följ [de här anvisningarna](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) för att blockera kända svaga lösenord och deras varianter.</span><span class="sxs-lookup"><span data-stu-id="58300-147">Follow [these instructions](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) to block known weak passwords and their variants.</span></span>

## <a name="phase-9-enable-azure-ad-identity-protection"></a><span data-ttu-id="58300-148">Fas 9: Aktivera Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="58300-148">Phase 9: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="58300-149">Följ anvisningarna i [fas 2 i testlabbguiden för Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="58300-149">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-10-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="58300-150">Fas 10: Aktivera modern autentisering för Exchange Online och Skype för företag – Online</span><span class="sxs-lookup"><span data-stu-id="58300-150">Phase 10: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="58300-151">Följ [dessa anvisningar](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later) för Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="58300-151">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="58300-152">För Skype för företag – Online:</span><span class="sxs-lookup"><span data-stu-id="58300-152">For Skype for Business Online:</span></span>

1. <span data-ttu-id="58300-153">Anslut till [Skype för företag – Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="58300-153">Connect to [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="58300-154">Kör det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="58300-154">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="58300-155">Kör följande kommando för att verifiera att ändringen genomfördes.</span><span class="sxs-lookup"><span data-stu-id="58300-155">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="58300-156">Resultatet är en testmiljö som uppfyller kraven för [konfiguration av direktautentisering](../security/office-365-security/identity-access-prerequisites.md#prerequisites) för identitets- och enhetsåtkomst.</span><span class="sxs-lookup"><span data-stu-id="58300-156">The result is a test environment that meets the requirements of the [Pass-through authentication prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="58300-157">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="58300-157">Next step</span></span>

<span data-ttu-id="58300-158">Använd [vanliga identitets- och enhetsprinciper](identity-access-policies.md) när du vill konfigurera de principer som bygger på kraven och skyddar identiteter och enheter.</span><span class="sxs-lookup"><span data-stu-id="58300-158">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="58300-159">Se även</span><span class="sxs-lookup"><span data-stu-id="58300-159">See also</span></span>

[<span data-ttu-id="58300-160">Fler testlabbguider för identitet</span><span class="sxs-lookup"><span data-stu-id="58300-160">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="58300-161">Identitetsöversikt</span><span class="sxs-lookup"><span data-stu-id="58300-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="58300-162">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="58300-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="58300-163">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="58300-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="58300-164">Dokumentation om Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="58300-164">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

