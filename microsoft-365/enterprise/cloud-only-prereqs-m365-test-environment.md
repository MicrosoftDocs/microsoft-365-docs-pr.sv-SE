---
title: Krav för identitets- och enhetsåtkomst för moln i din Microsoft 365-testmiljö
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
description: Skapa en Microsoft 365-miljö för att testa identitets- och enhetsåtkomst med kraven för molnautentisering.
ms.openlocfilehash: 3e5a9ef1f610bf3dc6d23c9e584e179fb8ab9ca9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905146"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a><span data-ttu-id="ac5da-103">Krav för identitets- och enhetsåtkomst för moln i din Microsoft 365-testmiljö</span><span class="sxs-lookup"><span data-stu-id="ac5da-103">Identity and device access prerequisites for cloud only in your Microsoft 365 test environment</span></span>

<span data-ttu-id="ac5da-104">*Den här testlabbguiden kan endast användas för Microsoft 365 för företagstestmiljöer.*</span><span class="sxs-lookup"><span data-stu-id="ac5da-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="ac5da-105">[Identitets- och enhetsåtkomstkonfigurationer](../security/office-365-security/microsoft-365-policies-configurations.md) är en uppsättning rekommenderade konfigurationer och villkorsstyrda åtkomstprinciper för att skydda åtkomsten till alla tjänster som är integrerade med Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="ac5da-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of recommended configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="ac5da-106">I den här artikeln beskrivs hur du kan konfigurera en Microsoft 365-testmiljö som uppfyller kraven för [konfiguration av förutsättningar endast för moln](../security/office-365-security/identity-access-prerequisites.md#prerequisites) för identitets- och enhetsåtkomst.</span><span class="sxs-lookup"><span data-stu-id="ac5da-106">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [cloud only prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="ac5da-107">Konfigurationen av testmiljön består av åtta faser. Du behöver:</span><span class="sxs-lookup"><span data-stu-id="ac5da-107">There are eight phases to setting up this test environment:</span></span>

1. <span data-ttu-id="ac5da-108">Bygg ut din förenklade testmiljö</span><span class="sxs-lookup"><span data-stu-id="ac5da-108">Build out your lightweight test environment</span></span>
2. <span data-ttu-id="ac5da-109">Konfigurera namngivna platser</span><span class="sxs-lookup"><span data-stu-id="ac5da-109">Configure named locations</span></span>
3. <span data-ttu-id="ac5da-110">Konfigurera lösenordsåterställning via självbetjäning</span><span class="sxs-lookup"><span data-stu-id="ac5da-110">Configure self-service password reset</span></span>
4. <span data-ttu-id="ac5da-111">Konfigurera multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="ac5da-111">Configure multifactor authentication</span></span>
5. <span data-ttu-id="ac5da-112">Aktivera automatisk enhetsregistrering för domänbaserade Windows-datorer</span><span class="sxs-lookup"><span data-stu-id="ac5da-112">Enable automatic device registration of domain-joined Windows computers</span></span>
6. <span data-ttu-id="ac5da-113">Konfigurera lösenordsskydd i Azure AD</span><span class="sxs-lookup"><span data-stu-id="ac5da-113">Configure Azure AD password protection</span></span> 
7. <span data-ttu-id="ac5da-114">Aktivera Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="ac5da-114">Enable Azure AD Identity Protection</span></span>
8. <span data-ttu-id="ac5da-115">Aktivera modern autentisering för Exchange Online och Skype för företag – Online</span><span class="sxs-lookup"><span data-stu-id="ac5da-115">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a><span data-ttu-id="ac5da-116">Fas 1: Bygga ut din förenklade testmiljö för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ac5da-116">Phase 1: Build out your lightweight Microsoft 365 test environment</span></span>

<span data-ttu-id="ac5da-117">Följ anvisningarna i [Enkel baskonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="ac5da-117">Follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
<span data-ttu-id="ac5da-118">Här är konfigurationsresultatet.</span><span class="sxs-lookup"><span data-stu-id="ac5da-118">Here is the resulting configuration.</span></span>

![Den förenklade testmiljön för Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 
## <a name="phase-2-configure-named-locations"></a><span data-ttu-id="ac5da-120">Fas 2: Konfigurera namngivna platser</span><span class="sxs-lookup"><span data-stu-id="ac5da-120">Phase 2: Configure named locations</span></span>

<span data-ttu-id="ac5da-121">Bestäm först de offentliga IP-adresser eller adress intervall som används av din organisation.</span><span class="sxs-lookup"><span data-stu-id="ac5da-121">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="ac5da-122">Följ sedan anvisningarna i [Konfigurera namngivna platser i Azure Active Directory](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) för att lägga till adresserna eller adressintervallen som namngivna platser.</span><span class="sxs-lookup"><span data-stu-id="ac5da-122">Next, follow the instructions in [Configure named locations in Azure Active Directory](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-3-configure-self-service-password-reset"></a><span data-ttu-id="ac5da-123">Steg 3: Konfigurera självbetjäning för återställning av lösenord</span><span class="sxs-lookup"><span data-stu-id="ac5da-123">Phase 3: Configure self-service password reset</span></span>

<span data-ttu-id="ac5da-124">Följ anvisningarna i [fas 3 i testlabbguiden för återställning av lösenord](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span><span class="sxs-lookup"><span data-stu-id="ac5da-124">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="ac5da-125">När du aktiverar återställning av lösenord för kontona i en särskild Azure AD-grupp lägger du till de här kontona i gruppen för **lösenordsåterställning**:</span><span class="sxs-lookup"><span data-stu-id="ac5da-125">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="ac5da-126">Användare 2</span><span class="sxs-lookup"><span data-stu-id="ac5da-126">User 2</span></span>
- <span data-ttu-id="ac5da-127">Användare 3</span><span class="sxs-lookup"><span data-stu-id="ac5da-127">User 3</span></span>
- <span data-ttu-id="ac5da-128">Användare 4</span><span class="sxs-lookup"><span data-stu-id="ac5da-128">User 4</span></span>
- <span data-ttu-id="ac5da-129">Användare 5</span><span class="sxs-lookup"><span data-stu-id="ac5da-129">User 5</span></span>

<span data-ttu-id="ac5da-130">Testa lösen ordet bara för användar 2-konto.</span><span class="sxs-lookup"><span data-stu-id="ac5da-130">Test password reset only for the User 2 account.</span></span>

## <a name="phase-4-configure-multi-factor-authentication"></a><span data-ttu-id="ac5da-131">Fas 4: Konfigurera multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="ac5da-131">Phase 4: Configure multi-factor authentication</span></span>

<span data-ttu-id="ac5da-132">Följ anvisningarna i [fas 2 i testlabbguiden för multifaktorautentisering](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) för följande användarkonton:</span><span class="sxs-lookup"><span data-stu-id="ac5da-132">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="ac5da-133">Användare 2</span><span class="sxs-lookup"><span data-stu-id="ac5da-133">User 2</span></span>
- <span data-ttu-id="ac5da-134">Användare 3</span><span class="sxs-lookup"><span data-stu-id="ac5da-134">User 3</span></span>
- <span data-ttu-id="ac5da-135">Användare 4</span><span class="sxs-lookup"><span data-stu-id="ac5da-135">User 4</span></span>
- <span data-ttu-id="ac5da-136">Användare 5</span><span class="sxs-lookup"><span data-stu-id="ac5da-136">User 5</span></span>

<span data-ttu-id="ac5da-137">Testa endast multifaktorautentisering för kontot Användare 2.</span><span class="sxs-lookup"><span data-stu-id="ac5da-137">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-5-enable-automatic-device-registration-of-domain-joined-windows-computers"></a><span data-ttu-id="ac5da-138">Steg 5: Aktivera automatisk enhetsregistrering på domänbaserade Windows-datorer</span><span class="sxs-lookup"><span data-stu-id="ac5da-138">Phase 5: Enable automatic device registration of domain-joined Windows computers</span></span> 

<span data-ttu-id="ac5da-139">Följ [de här anvisningarna](/azure/active-directory/devices/hybrid-azuread-join-plan) för att aktivera automatisk enhetsregistrering på domänbaserade Windows-datorer.</span><span class="sxs-lookup"><span data-stu-id="ac5da-139">Follow [these instructions](/azure/active-directory/devices/hybrid-azuread-join-plan) to enable automatic device registration of domain-joined Windows computers.</span></span>

## <a name="phase-6-configure-azure-ad-password-protection"></a><span data-ttu-id="ac5da-140">Steg 6: Konfigurera lösenordsskydd i Azure AD</span><span class="sxs-lookup"><span data-stu-id="ac5da-140">Phase 6: Configure Azure AD password protection</span></span> 

<span data-ttu-id="ac5da-141">Följ [dessa anvisningar](/azure/active-directory/authentication/concept-password-ban-bad) för att blockera kända svaga lösenord och deras varianter.</span><span class="sxs-lookup"><span data-stu-id="ac5da-141">Follow [these instructions](/azure/active-directory/authentication/concept-password-ban-bad) to block known weak passwords and their variants.</span></span>

## <a name="phase-7-enable-azure-ad-identity-protection"></a><span data-ttu-id="ac5da-142">Fas 7: Aktivera Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="ac5da-142">Phase 7: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="ac5da-143">Följ anvisningarna i [fas 2 i testlabbguiden för Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="ac5da-143">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="ac5da-144">Fas 8: Aktivera modern autentisering för Exchange Online och Skype för företag – Online</span><span class="sxs-lookup"><span data-stu-id="ac5da-144">Phase 8: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="ac5da-145">Följ [dessa anvisningar](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later) för Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ac5da-145">For Exchange Online, follow [these instructions](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="ac5da-146">För Skype för företag – Online:</span><span class="sxs-lookup"><span data-stu-id="ac5da-146">For Skype for Business Online:</span></span>

1. <span data-ttu-id="ac5da-147">Anslut till [Skype för företag – Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="ac5da-147">Connect to [Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="ac5da-148">Kör det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="ac5da-148">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="ac5da-149">Kör följande kommando för att verifiera att ändringen genomfördes.</span><span class="sxs-lookup"><span data-stu-id="ac5da-149">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="ac5da-150">Resultatet är en testmiljö som uppfyller kraven för den moln enda nödvändiga [konfigurationen för identiteter](../security/office-365-security/identity-access-prerequisites.md#prerequisites) och enhetsåtkomst.</span><span class="sxs-lookup"><span data-stu-id="ac5da-150">The result is a test environment that meets the requirements of the [cloud-only prerequisite configuration](../security/office-365-security/identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="ac5da-151">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="ac5da-151">Next step</span></span>

<span data-ttu-id="ac5da-152">Använd [vanliga identitets- och enhetsprinciper](../security/office-365-security/identity-access-policies.md) när du vill konfigurera de principer som bygger på kraven och skyddar identiteter och enheter.</span><span class="sxs-lookup"><span data-stu-id="ac5da-152">Use [Common identity and device access policies](../security/office-365-security/identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="ac5da-153">Se även</span><span class="sxs-lookup"><span data-stu-id="ac5da-153">See also</span></span>

[<span data-ttu-id="ac5da-154">Fler testlabbguider för identitet</span><span class="sxs-lookup"><span data-stu-id="ac5da-154">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="ac5da-155">Identitetsöversikt</span><span class="sxs-lookup"><span data-stu-id="ac5da-155">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="ac5da-156">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="ac5da-156">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="ac5da-157">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="ac5da-157">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="ac5da-158">Dokumentation om Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="ac5da-158">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)