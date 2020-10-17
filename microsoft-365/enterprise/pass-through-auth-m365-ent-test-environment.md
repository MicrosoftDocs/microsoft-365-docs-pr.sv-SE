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
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: ''
description: 'Sammanfattning: Konfigurera direktautentisering för Microsoft 365-testmiljön.'
ms.openlocfilehash: d83de4ece4d1eaeddac882cf46a4fe85b8ba7cd4
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487452"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a><span data-ttu-id="35c48-103">Direktautentisering för Microsoft 365-testmiljön</span><span class="sxs-lookup"><span data-stu-id="35c48-103">Pass-through authentication for your Microsoft 365 test environment</span></span>

<span data-ttu-id="35c48-104">*Den här test laboratorie guiden kan användas för både Microsoft 365 för företags-och Office 365 företags test miljöer.*</span><span class="sxs-lookup"><span data-stu-id="35c48-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="35c48-105">Organisationer som direkt vill använda sin lokala Active Directory Domain Services-infrastruktur vid autentisering till Microsofts molnbaserade tjänster och program, kan använda direktautentisering.</span><span class="sxs-lookup"><span data-stu-id="35c48-105">Organizations that want to directly use their on-premises Active Directory Domain Services (AD DS) infrastructure for authentication to Microsoft cloud-based services and applications can use pass-through authentication.</span></span> <span data-ttu-id="35c48-106">I den här artikeln beskrivs hur du konfigurerar Microsoft 365-testmiljön för direktautentisering, vilket ger följande konfiguration:</span><span class="sxs-lookup"><span data-stu-id="35c48-106">This article describes how you can configure your Microsoft 365 test environment for pass-through authentication, resulting in the following configuration:</span></span>
  
![Det simulerade företaget med en testmiljö med direktautentisering](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="35c48-108">Konfigurationen av testmiljön består av två faser:</span><span class="sxs-lookup"><span data-stu-id="35c48-108">There are two phases to setting up this test environment:</span></span>

1.    <span data-ttu-id="35c48-109">Skapa Microsoft 365-testmiljön för det simulerade företaget med synkronisering av lösenordshash.</span><span class="sxs-lookup"><span data-stu-id="35c48-109">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.    <span data-ttu-id="35c48-110">Konfigurera Azure AD Connect på APP1 för direktautentisering.</span><span class="sxs-lookup"><span data-stu-id="35c48-110">Configure Azure AD Connect on APP1 for pass-through authentication.</span></span>
    
![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="35c48-112">Klicka [här](../downloads/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med testlabbguider för Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="35c48-112">Click [here](../downloads/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="35c48-113">Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön</span><span class="sxs-lookup"><span data-stu-id="35c48-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="35c48-114">Följ anvisningarna i [synkronisering av lösenordshash för Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="35c48-114">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span></span> <span data-ttu-id="35c48-115">Här är konfigurationsresultatet.</span><span class="sxs-lookup"><span data-stu-id="35c48-115">Here is your resulting configuration.</span></span>
  
![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="35c48-117">Konfigurationen består av:</span><span class="sxs-lookup"><span data-stu-id="35c48-117">This configuration consists of:</span></span> 
  
- <span data-ttu-id="35c48-118">Microsoft 365 E5-prov eller betalt abonnemang.</span><span class="sxs-lookup"><span data-stu-id="35c48-118">Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="35c48-119">Ett förenklat företagsintranät anslutet till Internet som består av de virtuella datorerna DC1, APP1 och CLIENT1 i ett undernät i ett virtuellt Azure-nätverk.</span><span class="sxs-lookup"><span data-stu-id="35c48-119">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="35c48-120">Azure AD Connect körs på APP1 för att synkronisera TESTLAB AD DS-domänen med Azure AD-klientorganisationen för din Microsoft 365-prenumeration regelbundet.</span><span class="sxs-lookup"><span data-stu-id="35c48-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription periodically.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a><span data-ttu-id="35c48-121">Fas 2: Konfigurera Azure AD Connect på APP1 för direktautentisering</span><span class="sxs-lookup"><span data-stu-id="35c48-121">Phase 2: Configure Azure AD Connect on APP1 for pass-through authentication</span></span>

<span data-ttu-id="35c48-122">I den här fasen konfigurerar du att Azure AD Connect använder direktautentisering på APP1 och sedan kontrollerar du att det fungerar.</span><span class="sxs-lookup"><span data-stu-id="35c48-122">In this phase, you configure Azure AD Connect on APP1 to use pass-through authentication, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="35c48-123">Konfigurera Azure AD Connect på APP1</span><span class="sxs-lookup"><span data-stu-id="35c48-123">Configure Azure AD Connect on APP1</span></span>

1.    <span data-ttu-id="35c48-124">Logga in på [Azure-portalen](https://portal.azure.com) med ditt globala administratörskonto och anslut sedan till APP1 med kontot TESTLAB\User1.</span><span class="sxs-lookup"><span data-stu-id="35c48-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2.    <span data-ttu-id="35c48-125">Kör Azure AD Connect på skrivbordet för APP1.</span><span class="sxs-lookup"><span data-stu-id="35c48-125">From the desktop of APP1, run Azure AD Connect.</span></span>

3.    <span data-ttu-id="35c48-126">På **välkomstsidan** klickar du på **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="35c48-126">On the **Welcome page**, click **Configure**.</span></span>

4.    <span data-ttu-id="35c48-127">På sidan Ytterligare uppgifter klickar du på **Ändra användarinloggning** och sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="35c48-127">On the Additional tasks page, click **Change user sign-in**, and then click **Next**.</span></span>

5.    <span data-ttu-id="35c48-128">På sidan **Anslut till Azure AD** skriver du dina globala administratörsautentiseringsuppgifter. Klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="35c48-128">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6.    <span data-ttu-id="35c48-129">På sidan **Användarinloggning** klickar du på **Direktautentisering** och sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="35c48-129">On the **User sign-in** page, click **Pass-through authentication**, and then click **Next**.</span></span>

7.    <span data-ttu-id="35c48-130">Klicka på **Konfigurera** på sidan **Klart att konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="35c48-130">On the **Ready to configure** page, click **Configure**.</span></span>

8.    <span data-ttu-id="35c48-131">På sidan **Konfigurationen är klar** klickar du på **Avsluta**.</span><span class="sxs-lookup"><span data-stu-id="35c48-131">On the **Configuration complete** page, click **Exit**.</span></span>

9.    <span data-ttu-id="35c48-132">Gå till den vänstra rutan i Azure-portalen och klicka på **Azure Active Directory > Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="35c48-132">From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**.</span></span> <span data-ttu-id="35c48-133">Kontrollera att funktionen **Direktautentisering** visas som **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="35c48-133">Verify that the **Pass-through authentication** feature appears as **Enabled**.</span></span>

10.    <span data-ttu-id="35c48-134">Klicka på **Direktautentisering**.</span><span class="sxs-lookup"><span data-stu-id="35c48-134">Click **Pass-through authentication**.</span></span> <span data-ttu-id="35c48-135">I fönstret **Direktautentisering** visas servrarna där dina autentiseringsagenter är installerade.</span><span class="sxs-lookup"><span data-stu-id="35c48-135">The **Pass-through authentication** pane lists the servers where your Authentication Agents are installed.</span></span> <span data-ttu-id="35c48-136">Du bör se APP1 i listan.</span><span class="sxs-lookup"><span data-stu-id="35c48-136">You should see APP1 in the list.</span></span> <span data-ttu-id="35c48-137">Stäng fönstret **Direktautentisering**.</span><span class="sxs-lookup"><span data-stu-id="35c48-137">Close the **Pass-through authentication** pane.</span></span>

<span data-ttu-id="35c48-138">Prova sedan att logga in på ditt abonnemang med <strong>user1@testlab.</strong>\<your public domain></span><span class="sxs-lookup"><span data-stu-id="35c48-138">Next, test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<your public domain></span></span> <span data-ttu-id="35c48-139">användarnamn för Användare1-kontot.</span><span class="sxs-lookup"><span data-stu-id="35c48-139">user name of the User1 account.</span></span>

1. <span data-ttu-id="35c48-140">Logga ut från APP1 och logga sedan in igen. Den här gången med ett annat konto.</span><span class="sxs-lookup"><span data-stu-id="35c48-140">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="35c48-141">När du uppmanas att ange ett användarnamn och lösenord anger du <strong>användare1@testlab.</strong>\<your public domain></span><span class="sxs-lookup"><span data-stu-id="35c48-141">When prompted for a user name and password, specify <strong>user1@testlab.</strong>\<your public domain></span></span> <span data-ttu-id="35c48-142">och lösenordet för Användare1.</span><span class="sxs-lookup"><span data-stu-id="35c48-142">and the User1 password.</span></span> <span data-ttu-id="35c48-143">Nu ska du loggas in som Användare1.</span><span class="sxs-lookup"><span data-stu-id="35c48-143">You should successfully sign in as User1.</span></span>

<span data-ttu-id="35c48-144">Observera att User1 visserligen har domänadministratörsbehörighet för TESTLAB AD DS-domänen, men den är inte global administratör.</span><span class="sxs-lookup"><span data-stu-id="35c48-144">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="35c48-145">Därför visas inte **administratörsikonen** som ett alternativ.</span><span class="sxs-lookup"><span data-stu-id="35c48-145">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="35c48-146">Här är konfigurationsresultatet:</span><span class="sxs-lookup"><span data-stu-id="35c48-146">Here is your resulting configuration:</span></span>

![Det simulerade företaget med en testmiljö med direktautentisering](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
<span data-ttu-id="35c48-148">Konfigurationen består av:</span><span class="sxs-lookup"><span data-stu-id="35c48-148">This configuration consists of:</span></span>

- <span data-ttu-id="35c48-149">En utvärderings version av Microsoft 365 E5 eller betalda abonnemang med DNS-testlab.\<your domain name></span><span class="sxs-lookup"><span data-stu-id="35c48-149">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain testlab.\<your domain name></span></span> <span data-ttu-id="35c48-150">registrerat.</span><span class="sxs-lookup"><span data-stu-id="35c48-150">registered.</span></span>
- <span data-ttu-id="35c48-151">Ett förenklat företagsintranät anslutet till Internet som består av de virtuella datorerna DC1, APP1 och CLIENT1 i ett undernät i ett virtuellt Azure-nätverk.</span><span class="sxs-lookup"><span data-stu-id="35c48-151">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="35c48-152">En autentiseringsagent körs i APP1 och hanterar direktautentiseringsförfrågningar från Azure AD-klienten för din Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="35c48-152">An Authentication Agent runs on APP1 to handle pass-through authentication requests from the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="next-step"></a><span data-ttu-id="35c48-153">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="35c48-153">Next step</span></span>

<span data-ttu-id="35c48-154">Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="35c48-154">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="35c48-155">Se även</span><span class="sxs-lookup"><span data-stu-id="35c48-155">See also</span></span>

[<span data-ttu-id="35c48-156">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="35c48-156">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="35c48-157">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="35c48-157">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="35c48-158">Microsoft 365 för företags dokumentation</span><span class="sxs-lookup"><span data-stu-id="35c48-158">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
