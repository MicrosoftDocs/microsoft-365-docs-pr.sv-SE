---
title: Krav för identitets- och enhetsåtkomst för moln i din Microsoft 365-testmiljö
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
description: Skapa en Microsoft 365-miljö för att testa identitets- och enhetsåtkomst med kraven för molnautentisering.
ms.openlocfilehash: a8025a2543a53a229be13d19c246165fe88ad433
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685790"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a><span data-ttu-id="5787e-103">Krav för identitets- och enhetsåtkomst för moln i din Microsoft 365-testmiljö</span><span class="sxs-lookup"><span data-stu-id="5787e-103">Identity and device access prerequisites for cloud only in your Microsoft 365 test environment</span></span>

<span data-ttu-id="5787e-104">*Den här test laboratorie guiden kan endast användas för test miljöer med Microsoft 365 för företags nätverk.*</span><span class="sxs-lookup"><span data-stu-id="5787e-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="5787e-105">[Konfigurationer för identitets-och enhets åtkomst](microsoft-365-policies-configurations.md) är en uppsättning konfigurationer och villkorsstyrda åtkomst principer för att skydda åtkomst till alla tjänster som är integrerade med Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="5787e-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="5787e-106">I den här artikeln beskrivs hur du kan konfigurera en Microsoft 365-testmiljö som uppfyller kraven för [konfiguration av förutsättningar endast för moln](identity-access-prerequisites.md#prerequisites) för identitets- och enhetsåtkomst.</span><span class="sxs-lookup"><span data-stu-id="5787e-106">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [cloud only prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="5787e-107">Konfigurationen av testmiljön består av sju faser:</span><span class="sxs-lookup"><span data-stu-id="5787e-107">There are seven phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="5787e-108">Bygg ut din förenklade testmiljö</span><span class="sxs-lookup"><span data-stu-id="5787e-108">Build out your lightweight test environment</span></span>
2.  <span data-ttu-id="5787e-109">Konfigurera namngivna platser</span><span class="sxs-lookup"><span data-stu-id="5787e-109">Configure named locations</span></span>
3.  <span data-ttu-id="5787e-110">Konfigurera tillbakaskrivning av lösenord</span><span class="sxs-lookup"><span data-stu-id="5787e-110">Configure password writeback</span></span>
4.  <span data-ttu-id="5787e-111">Konfigurera lösenordsåterställning via självbetjäning</span><span class="sxs-lookup"><span data-stu-id="5787e-111">Configure self-service password resets</span></span>
5.  <span data-ttu-id="5787e-112">Konfigurera multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="5787e-112">Configure multifactor authentication</span></span>
6.  <span data-ttu-id="5787e-113">Aktivera Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="5787e-113">Enable Azure AD Identity Protection</span></span>
7.  <span data-ttu-id="5787e-114">Aktivera modern autentisering för Exchange Online och Skype för företag – Online</span><span class="sxs-lookup"><span data-stu-id="5787e-114">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a><span data-ttu-id="5787e-115">Fas 1: Bygga ut din förenklade testmiljö för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5787e-115">Phase 1: Build out your lightweight Microsoft 365 test environment</span></span>

<span data-ttu-id="5787e-116">Följ anvisningarna i [Enkel baskonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="5787e-116">Follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
<span data-ttu-id="5787e-117">Här är konfigurationsresultatet.</span><span class="sxs-lookup"><span data-stu-id="5787e-117">Here is the resulting configuration.</span></span>

![Den förenklade testmiljön för Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 

## <a name="phase-2-configure-named-locations"></a><span data-ttu-id="5787e-119">Fas 2: Konfigurera namngivna platser</span><span class="sxs-lookup"><span data-stu-id="5787e-119">Phase 2: Configure named locations</span></span>

<span data-ttu-id="5787e-120">Bestäm först de offentliga IP-adresser eller adress intervall som används av din organisation.</span><span class="sxs-lookup"><span data-stu-id="5787e-120">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="5787e-121">Följ sedan anvisningarna i [Konfigurera namngivna platser i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) för att lägga till adresserna eller adressintervallen som namngivna platser.</span><span class="sxs-lookup"><span data-stu-id="5787e-121">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-3-configure-password-writeback"></a><span data-ttu-id="5787e-122">Fas 3: Konfigurera tillbakaskrivning av lösenord</span><span class="sxs-lookup"><span data-stu-id="5787e-122">Phase 3: Configure password writeback</span></span>

<span data-ttu-id="5787e-123">Följ anvisningarna i [fas 2 i testlabbguiden för tillbakaskrivning av lösenord](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="5787e-123">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-4-configure-self-service-password-reset"></a><span data-ttu-id="5787e-124">Fas 4: Konfigurera lösenordsåterställning via självbetjäning</span><span class="sxs-lookup"><span data-stu-id="5787e-124">Phase 4: Configure self-service password reset</span></span>

<span data-ttu-id="5787e-125">Följ anvisningarna i [fas 3 i testlabbguiden för återställning av lösenord](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span><span class="sxs-lookup"><span data-stu-id="5787e-125">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="5787e-126">När du aktiverar återställning av lösenord för kontona i en särskild Azure AD-grupp lägger du till de här kontona i gruppen för **lösenordsåterställning**:</span><span class="sxs-lookup"><span data-stu-id="5787e-126">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="5787e-127">Användare 2</span><span class="sxs-lookup"><span data-stu-id="5787e-127">User 2</span></span>
- <span data-ttu-id="5787e-128">Användare 3</span><span class="sxs-lookup"><span data-stu-id="5787e-128">User 3</span></span>
- <span data-ttu-id="5787e-129">Användare 4</span><span class="sxs-lookup"><span data-stu-id="5787e-129">User 4</span></span>
- <span data-ttu-id="5787e-130">Användare 5</span><span class="sxs-lookup"><span data-stu-id="5787e-130">User 5</span></span>

<span data-ttu-id="5787e-131">Testa lösen ordet bara för användar 2-konto.</span><span class="sxs-lookup"><span data-stu-id="5787e-131">Test password reset only for the User 2 account.</span></span>

## <a name="phase-5-configure-multi-factor-authentication"></a><span data-ttu-id="5787e-132">Fas 5: Konfigurera multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="5787e-132">Phase 5: Configure multi-factor authentication</span></span>

<span data-ttu-id="5787e-133">Följ anvisningarna i [fas 2 i testlabbguiden för multifaktorautentisering](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) för följande användarkonton:</span><span class="sxs-lookup"><span data-stu-id="5787e-133">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="5787e-134">Användare 2</span><span class="sxs-lookup"><span data-stu-id="5787e-134">User 2</span></span>
- <span data-ttu-id="5787e-135">Användare 3</span><span class="sxs-lookup"><span data-stu-id="5787e-135">User 3</span></span>
- <span data-ttu-id="5787e-136">Användare 4</span><span class="sxs-lookup"><span data-stu-id="5787e-136">User 4</span></span>
- <span data-ttu-id="5787e-137">Användare 5</span><span class="sxs-lookup"><span data-stu-id="5787e-137">User 5</span></span>

<span data-ttu-id="5787e-138">Testa endast multifaktorautentisering för kontot Användare 2.</span><span class="sxs-lookup"><span data-stu-id="5787e-138">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-6-enable-azure-ad-identity-protection"></a><span data-ttu-id="5787e-139">Fas 6: Aktivera Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="5787e-139">Phase 6: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="5787e-140">Följ anvisningarna i [fas 2 i testlabbguiden för Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="5787e-140">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-7-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="5787e-141">Fas 7: Aktivera modern autentisering för Exchange Online och Skype för företag – Online</span><span class="sxs-lookup"><span data-stu-id="5787e-141">Phase 7: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="5787e-142">Följ [dessa anvisningar](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later) för Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5787e-142">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="5787e-143">För Skype för företag – Online:</span><span class="sxs-lookup"><span data-stu-id="5787e-143">For Skype for Business Online:</span></span>

1. <span data-ttu-id="5787e-144">Anslut till [Skype för företag – Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="5787e-144">Connect to [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="5787e-145">Kör det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="5787e-145">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="5787e-146">Kör följande kommando för att verifiera att ändringen genomfördes.</span><span class="sxs-lookup"><span data-stu-id="5787e-146">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="5787e-147">Resultatet är en testmiljö som uppfyller kraven för [konfiguration av förutsättningar endast för moln](identity-access-prerequisites.md#prerequisites) för identitets- och enhetsåtkomst.</span><span class="sxs-lookup"><span data-stu-id="5787e-147">The result is a test environment that meets the requirements of the [cloud only prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="5787e-148">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="5787e-148">Next step</span></span>

<span data-ttu-id="5787e-149">Använd [vanliga identitets- och enhetsprinciper](identity-access-policies.md) när du vill konfigurera de principer som bygger på kraven och skyddar identiteter och enheter.</span><span class="sxs-lookup"><span data-stu-id="5787e-149">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="5787e-150">Se även</span><span class="sxs-lookup"><span data-stu-id="5787e-150">See also</span></span>

[<span data-ttu-id="5787e-151">Fler testlabbguider för identitet</span><span class="sxs-lookup"><span data-stu-id="5787e-151">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="5787e-152">Identitets översikt</span><span class="sxs-lookup"><span data-stu-id="5787e-152">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="5787e-153">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="5787e-153">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="5787e-154">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="5787e-154">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="5787e-155">Microsoft 365 för företags dokumentation</span><span class="sxs-lookup"><span data-stu-id="5787e-155">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
