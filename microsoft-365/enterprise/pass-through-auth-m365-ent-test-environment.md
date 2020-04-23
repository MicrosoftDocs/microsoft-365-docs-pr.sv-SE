---
title: Direktautentisering för Microsoft 365-testmiljön
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: ''
description: 'Sammanfattning: Konfigurera direktautentisering för Microsoft 365-testmiljön.'
ms.openlocfilehash: 8a9a8847d79e1d114f0ddfb4843cbb7b9f9f0d4c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631423"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a><span data-ttu-id="9e4fd-103">Direktautentisering för Microsoft 365-testmiljön</span><span class="sxs-lookup"><span data-stu-id="9e4fd-103">Pass-through authentication for your Microsoft 365 test environment</span></span>

<span data-ttu-id="9e4fd-104">*Den här testlabbguiden kan användas i både Microsoft 365 Enterprise- och Office 365 Enterprise-testmiljöer.*</span><span class="sxs-lookup"><span data-stu-id="9e4fd-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="9e4fd-105">Organisationer som direkt vill använda sin lokala Active Directory Domain Services-infrastruktur vid autentisering till Microsofts molnbaserade tjänster och program, kan använda direktautentisering.</span><span class="sxs-lookup"><span data-stu-id="9e4fd-105">Organizations that want to directly use their on-premises Active Directory Domain Services (AD DS) infrastructure for authentication to Microsoft cloud-based services and applications can use pass-through authentication.</span></span> <span data-ttu-id="9e4fd-106">I den här artikeln beskrivs hur du konfigurerar Microsoft 365-testmiljön för direktautentisering, vilket ger följande konfiguration:</span><span class="sxs-lookup"><span data-stu-id="9e4fd-106">This article describes how you can configure your Microsoft 365 test environment for pass-through authentication, resulting in the following configuration:</span></span>
  
![Det simulerade företaget med en testmiljö med direktautentisering](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="9e4fd-108">Konfigurationen av testmiljön består av två faser:</span><span class="sxs-lookup"><span data-stu-id="9e4fd-108">There are two phases to setting up this test environment:</span></span>

1.    <span data-ttu-id="9e4fd-109">Skapa Microsoft 365-testmiljön för det simulerade företaget med synkronisering av lösenordshash.</span><span class="sxs-lookup"><span data-stu-id="9e4fd-109">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.    <span data-ttu-id="9e4fd-110">Konfigurera Azure AD Connect på APP1 för direktautentisering.</span><span class="sxs-lookup"><span data-stu-id="9e4fd-110">Configure Azure AD Connect on APP1 for pass-through authentication.</span></span>
    
![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="9e4fd-112">Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med Microsoft 365 Enterprise-testlabbguider.</span><span class="sxs-lookup"><span data-stu-id="9e4fd-112">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="9e4fd-113">Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön</span><span class="sxs-lookup"><span data-stu-id="9e4fd-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="9e4fd-114">Följ anvisningarna i [synkronisering av lösenordshash för Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="9e4fd-114">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span></span> <span data-ttu-id="9e4fd-115">Här är konfigurationsresultatet.</span><span class="sxs-lookup"><span data-stu-id="9e4fd-115">Here is your resulting configuration.</span></span>
  
![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="9e4fd-117">Konfigurationen består av:</span><span class="sxs-lookup"><span data-stu-id="9e4fd-117">This configuration consists of:</span></span> 
  
- <span data-ttu-id="9e4fd-118">Utvärderingsversioner av eller betalda prenumerationer för Microsoft 365 E5 eller Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="9e4fd-118">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="9e4fd-119">Ett förenklat företagsintranät anslutet till Internet som består av de virtuella datorerna DC1, APP1 och CLIENT1 i ett undernät i ett virtuellt Azure-nätverk.</span><span class="sxs-lookup"><span data-stu-id="9e4fd-119">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="9e4fd-120">Azure AD Connect körs på APP1 för att synkronisera TESTLAB AD DS-domänen med Azure AD-klientorganisationen för din Microsoft 365-prenumeration regelbundet.</span><span class="sxs-lookup"><span data-stu-id="9e4fd-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription periodically.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a><span data-ttu-id="9e4fd-121">Fas 2: Konfigurera Azure AD Connect på APP1 för direktautentisering</span><span class="sxs-lookup"><span data-stu-id="9e4fd-121">Phase 2: Configure Azure AD Connect on APP1 for pass-through authentication</span></span>

<span data-ttu-id="9e4fd-122">I den här fasen konfigurerar du att Azure AD Connect använder direktautentisering på APP1 och sedan kontrollerar du att det fungerar.</span><span class="sxs-lookup"><span data-stu-id="9e4fd-122">In this phase, you configure Azure AD Connect on APP1 to use pass-through authentication, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="9e4fd-123">Konfigurera Azure AD Connect på APP1</span><span class="sxs-lookup"><span data-stu-id="9e4fd-123">Configure Azure AD Connect on APP1</span></span>

1.    <span data-ttu-id="9e4fd-124">Logga in på [Azure-portalen](https://portal.azure.com) med ditt globala administratörskonto och anslut sedan till APP1 med kontot TESTLAB\User1.</span><span class="sxs-lookup"><span data-stu-id="9e4fd-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2.    <span data-ttu-id="9e4fd-125">Kör Azure AD Connect på skrivbordet för APP1.</span><span class="sxs-lookup"><span data-stu-id="9e4fd-125">From the desktop of APP1, run Azure AD Connect.</span></span>

3.    <span data-ttu-id="9e4fd-126">På **välkomstsidan** klickar du på **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="9e4fd-126">On the **Welcome page**, click **Configure**.</span></span>

4.    <span data-ttu-id="9e4fd-127">På sidan Ytterligare uppgifter klickar du på **Ändra användarinloggning** och sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9e4fd-127">On the Additional tasks page, click **Change user sign-in**, and then click **Next**.</span></span>

5.    <span data-ttu-id="9e4fd-128">På sidan **Anslut till Azure AD** skriver du dina globala administratörsautentiseringsuppgifter. Klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9e4fd-128">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6.    <span data-ttu-id="9e4fd-129">På sidan **Användarinloggning** klickar du på **Direktautentisering** och sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9e4fd-129">On the **User sign-in** page, click **Pass-through authentication**, and then click **Next**.</span></span>

7.    <span data-ttu-id="9e4fd-130">Klicka på **Konfigurera** på sidan **Klart att konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="9e4fd-130">On the **Ready to configure** page, click **Configure**.</span></span>

8.    <span data-ttu-id="9e4fd-131">På sidan **Konfigurationen är klar** klickar du på **Avsluta**.</span><span class="sxs-lookup"><span data-stu-id="9e4fd-131">On the **Configuration complete** page, click **Exit**.</span></span>

9.    <span data-ttu-id="9e4fd-132">Gå till den vänstra rutan i Azure-portalen och klicka på **Azure Active Directory > Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="9e4fd-132">From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**.</span></span> <span data-ttu-id="9e4fd-133">Kontrollera att funktionen **Direktautentisering** visas som **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="9e4fd-133">Verify that the **Pass-through authentication** feature appears as **Enabled**.</span></span>

10.    <span data-ttu-id="9e4fd-134">Klicka på **Direktautentisering**.</span><span class="sxs-lookup"><span data-stu-id="9e4fd-134">Click **Pass-through authentication**.</span></span> <span data-ttu-id="9e4fd-135">I fönstret **Direktautentisering** visas servrarna där dina autentiseringsagenter är installerade.</span><span class="sxs-lookup"><span data-stu-id="9e4fd-135">The **Pass-through authentication** pane lists the servers where your Authentication Agents are installed.</span></span> <span data-ttu-id="9e4fd-136">Du bör se APP1 i listan.</span><span class="sxs-lookup"><span data-stu-id="9e4fd-136">You should see APP1 in the list.</span></span> <span data-ttu-id="9e4fd-137">Stäng fönstret **Direktautentisering**.</span><span class="sxs-lookup"><span data-stu-id="9e4fd-137">Close the **Pass-through authentication** pane.</span></span>

<span data-ttu-id="9e4fd-138">Prova sedan att det går att logga in på din prenumeration med <strong>user1@testlab.</strong>\<din offentliga domän> användarnamnet för User1-kontot.</span><span class="sxs-lookup"><span data-stu-id="9e4fd-138">Next, test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<your public domain> user name of the User1 account.</span></span>

1. <span data-ttu-id="9e4fd-139">Logga ut från APP1 och logga sedan in igen med ett annat konto.</span><span class="sxs-lookup"><span data-stu-id="9e4fd-139">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="9e4fd-140">När du uppmanas att ange ett användarnamn och lösenord, skriver du <strong>user1@testlab.</strong>\<din offentliga domän> och User1-lösenordet.</span><span class="sxs-lookup"><span data-stu-id="9e4fd-140">When prompted for a user name and password, specify <strong>user1@testlab.</strong>\<your public domain> and the User1 password.</span></span> <span data-ttu-id="9e4fd-141">Nu ska du loggas in som User1.</span><span class="sxs-lookup"><span data-stu-id="9e4fd-141">You should successfully sign in as User1.</span></span>

<span data-ttu-id="9e4fd-142">Observera att User1 visserligen har domänadministratörsbehörighet för TESTLAB AD DS-domänen, men den är inte global administratör.</span><span class="sxs-lookup"><span data-stu-id="9e4fd-142">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="9e4fd-143">Därför visas inte ikonen **Administratör** som ett alternativ.</span><span class="sxs-lookup"><span data-stu-id="9e4fd-143">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="9e4fd-144">Här är konfigurationsresultatet:</span><span class="sxs-lookup"><span data-stu-id="9e4fd-144">Here is your resulting configuration:</span></span>

![Det simulerade företaget med en testmiljö med direktautentisering](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
<span data-ttu-id="9e4fd-146">Konfigurationen består av:</span><span class="sxs-lookup"><span data-stu-id="9e4fd-146">This configuration consists of:</span></span>

- <span data-ttu-id="9e4fd-147">Utvärderingsversion eller betald prenumeration för Microsoft 365 E5 eller Office 365 E5 med DNS-domänen testlab.\<ditt domännamn> registrerad.</span><span class="sxs-lookup"><span data-stu-id="9e4fd-147">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain testlab.\<your domain name> registered.</span></span>
- <span data-ttu-id="9e4fd-148">Ett förenklat företagsintranät anslutet till Internet som består av de virtuella datorerna DC1, APP1 och CLIENT1 i ett undernät i ett virtuellt Azure-nätverk.</span><span class="sxs-lookup"><span data-stu-id="9e4fd-148">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="9e4fd-149">En autentiseringsagent körs i APP1 och hanterar direktautentiseringsförfrågningar från Azure AD-klienten för din Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="9e4fd-149">An Authentication Agent runs on APP1 to handle pass-through authentication requests from the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="next-step"></a><span data-ttu-id="9e4fd-150">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="9e4fd-150">Next step</span></span>

<span data-ttu-id="9e4fd-151">Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="9e4fd-151">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="9e4fd-152">Se även</span><span class="sxs-lookup"><span data-stu-id="9e4fd-152">See also</span></span>

[<span data-ttu-id="9e4fd-153">Testlabbguider för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9e4fd-153">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="9e4fd-154">Distribuera Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9e4fd-154">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="9e4fd-155">Microsoft 365 Enterprise-dokumentation</span><span class="sxs-lookup"><span data-stu-id="9e4fd-155">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
