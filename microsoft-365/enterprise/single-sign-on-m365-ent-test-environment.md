---
title: Sömlös enkel inloggning med Azure AD för din Microsoft 365-testmiljö
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
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Sammanfattning: Konfigurera och testa sömlös enkel inloggning med Azure AD för din Microsoft 365-testmiljö.'
ms.openlocfilehash: 7fcbc82cfb35c598358c8160dd06427c2a9c59a2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904870"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a><span data-ttu-id="44354-103">Sömlös enkel inloggning med Azure AD för din Microsoft 365-testmiljö</span><span class="sxs-lookup"><span data-stu-id="44354-103">Azure AD Seamless Single Sign-on for your Microsoft 365 test environment</span></span>

<span data-ttu-id="44354-104">*Den här testlabbguiden kan användas för både Microsoft 365 för företag Office 365 Enterprise för testmiljöer.*</span><span class="sxs-lookup"><span data-stu-id="44354-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="44354-105">Sömlös enkel inloggning Sign-On Azure AD loggar automatiskt in användare på sina datorer eller enheter som är anslutna till organisationens nätverk.</span><span class="sxs-lookup"><span data-stu-id="44354-105">Azure AD Seamless Single Sign-On (Seamless SSO) automatically signs in users when they are on their PCs or devices that are connected to their organization network.</span></span> <span data-ttu-id="44354-106">Sömlös SSO med Azure AD ger användare enkelt åtkomst till molnbaserade program utan att några ytterligare lokala komponenter behövs.</span><span class="sxs-lookup"><span data-stu-id="44354-106">Azure AD Seamless SSO provides users with easy access to cloud-based applications without needing any additional on-premises components.</span></span>

<span data-ttu-id="44354-107">I den här artikeln beskrivs hur du konfigurerar Microsoft 365 testmiljön för sömlös Azure AD-SSO.</span><span class="sxs-lookup"><span data-stu-id="44354-107">This article describes how to configure your Microsoft 365 test environment for Azure AD Seamless SSO.</span></span>

<span data-ttu-id="44354-108">Att konfigurera sömlös SSO i Azure AD omfattar två faser:</span><span class="sxs-lookup"><span data-stu-id="44354-108">Setting up Azure AD Seamless SSO involves two phases:</span></span>
- [<span data-ttu-id="44354-109">Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön</span><span class="sxs-lookup"><span data-stu-id="44354-109">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="44354-110">Fas 2: Konfigurera Azure AD Connect på APP1 för sömlös SSO med Azure AD</span><span class="sxs-lookup"><span data-stu-id="44354-110">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>](#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso)
   
![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="44354-112">En visuell karta till alla artiklar i Microsoft 365 för företags testlabbguide stack finns i [Microsoft 365 för företags testlabbguide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="44354-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="44354-113">Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön</span><span class="sxs-lookup"><span data-stu-id="44354-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="44354-114">Följ anvisningarna i [synkronisering av lösenordshash för Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="44354-114">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span></span> 

<span data-ttu-id="44354-115">Den resulterande konfigurationen ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="44354-115">Your resulting configuration looks like this:</span></span>
  
![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="44354-117">Konfigurationen består av:</span><span class="sxs-lookup"><span data-stu-id="44354-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="44354-118">En utvärderingsprenumeration eller betald prenumeration på Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="44354-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="44354-119">Ett förenklat organisationsintranät som är anslutet till internet och består av virtuella DC1-, APP1- och CLIENT1-datorer på ett undernät i ett virtuellt Azure-nätverk.</span><span class="sxs-lookup"><span data-stu-id="44354-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="44354-120">Azure AD Anslut körs på APP1 för att regelbundet synkronisera AD DS-domänen (TESTLAB Active Directory Domain Services) med Azure AD-klientorganisationen för Microsoft 365-prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="44354-120">Azure AD Connect runs on APP1 to periodically synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a><span data-ttu-id="44354-121">Fas 2: Konfigurera Azure AD Connect på APP1 för sömlös SSO med Azure AD</span><span class="sxs-lookup"><span data-stu-id="44354-121">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>

<span data-ttu-id="44354-122">I den här fasen konfigurerar du Azure AD Anslut på APP1 för Sömlös Azure AD-SSO och kontrollerar sedan att det fungerar.</span><span class="sxs-lookup"><span data-stu-id="44354-122">In this phase, configure Azure AD Connect on APP1 for Azure AD Seamless SSO, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="44354-123">Konfigurera Azure AD Connect på APP1</span><span class="sxs-lookup"><span data-stu-id="44354-123">Configure Azure AD Connect on APP1</span></span>

1. <span data-ttu-id="44354-124">Logga in på [Azure-portalen](https://portal.azure.com) med ditt globala administratörskonto och anslut sedan till APP1 med kontot TESTLAB\User1.</span><span class="sxs-lookup"><span data-stu-id="44354-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="44354-125">Kör Azure AD-Anslut från appen1 Anslut.</span><span class="sxs-lookup"><span data-stu-id="44354-125">From the APP1 desktop, run Azure AD Connect.</span></span>

3. <span data-ttu-id="44354-126">På **välkomstsidan väljer** du **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="44354-126">On the **Welcome page**, select **Configure**.</span></span>

4. <span data-ttu-id="44354-127">På sidan **Ytterligare uppgifter** väljer du Ändra inloggning **för användare** och sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="44354-127">On the **Additional tasks** page, select **Change user sign-in**, and then select **Next**.</span></span>

5. <span data-ttu-id="44354-128">På sidan **Anslut till Azure AD** anger du autentiseringsuppgifterna för ditt globala administratörskonto och väljer sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="44354-128">On the **Connect to Azure AD** page, enter your global administrator account credentials, and then select **Next**.</span></span>

6. <span data-ttu-id="44354-129">På **inloggningssidan för användare** väljer du **Aktivera enkel inloggning** och sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="44354-129">On the **User sign-in** page, select **Enable single sign-on**, and then select **Next**.</span></span>

7. <span data-ttu-id="44354-130">På sidan **Aktivera enkel inloggning väljer** du Ange **autentiseringsuppgifter**.</span><span class="sxs-lookup"><span data-stu-id="44354-130">On the **Enable single sign-on** page, select **Enter credentials**.</span></span>

8. <span data-ttu-id="44354-131">I dialogrutan **Windows-säkerhet** du **användare1** och lösenordet för användarkontot, väljer **OK** och sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="44354-131">In the **Windows Security** dialog box, enter **user1** and the password of the user1 account, select **OK**, and then select **Next**.</span></span>

9. <span data-ttu-id="44354-132">På sidan **Är redo att konfigurera** väljer du **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="44354-132">On the **Ready to Configure** page, select **Configure**.</span></span>

10. <span data-ttu-id="44354-133">På sidan **Konfiguration slutförd** väljer du **Avsluta**.</span><span class="sxs-lookup"><span data-stu-id="44354-133">On the **Configuration complete** page, select **Exit**.</span></span>

11. <span data-ttu-id="44354-134">I den vänstra rutan i Azure-portalen väljer **du** Azure Active Directory  >  **Azure AD Anslut**.</span><span class="sxs-lookup"><span data-stu-id="44354-134">From the Azure portal, in the left pane, select **Azure Active Directory** > **Azure AD Connect**.</span></span> <span data-ttu-id="44354-135">Kontrollera att funktionen **Sömlös enkel inloggning** visas som **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="44354-135">Verify that the **Seamless single sign-on** feature appears as **Enabled**.</span></span>

<span data-ttu-id="44354-136">Testa sedan möjligheten att logga in på din prenumeration med <strong>user1@testlab.</strong>\<*your public domain*></span><span class="sxs-lookup"><span data-stu-id="44354-136">Next, test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<*your public domain*></span></span> <span data-ttu-id="44354-137">användarnamn för Användare1-kontot.</span><span class="sxs-lookup"><span data-stu-id="44354-137">user name of the User1 account.</span></span>

1. <span data-ttu-id="44354-138">Välj inställningsikonen i Internet Explorer i APP1 och välj sedan **Internetalternativ**.</span><span class="sxs-lookup"><span data-stu-id="44354-138">From Internet Explorer on APP1, select the settings icon, and then select **Internet Options**.</span></span>
 
2. <span data-ttu-id="44354-139">I **Internetalternativ** väljer du **fliken** Säkerhet.</span><span class="sxs-lookup"><span data-stu-id="44354-139">In **Internet Options**, select the **Security** tab.</span></span>

3. <span data-ttu-id="44354-140">Välj **Lokalt intranät** och välj sedan **Webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="44354-140">Select **Local intranet**, and then select **Sites**.</span></span>

4. <span data-ttu-id="44354-141">I **Lokalt intranät** väljer du **Avancerat**.</span><span class="sxs-lookup"><span data-stu-id="44354-141">In **Local intranet**, select **Advanced**.</span></span>

5. <span data-ttu-id="44354-142">I **Lägg till den här webbplatsen i zonen** anger du **<span>https://</span>autologon.microsoftazuread-sso.com** och väljer Lägg **till**  >  **Stäng**  >    >  **OK.**</span><span class="sxs-lookup"><span data-stu-id="44354-142">In **Add this website to the zone**, enter **https <span>://</span>autologon.microsoftazuread-sso.com**, select **Add** > **Close** > **OK** > **OK**.</span></span>

6. <span data-ttu-id="44354-143">Logga ut och logga sedan in igen. Den här gången med ett annat konto.</span><span class="sxs-lookup"><span data-stu-id="44354-143">Sign out, and then sign in again, this time specifying a different account.</span></span>

7. <span data-ttu-id="44354-144">När du uppmanas att logga in anger <strong>du user1@testlab.</strong>\<*your public domain*></span><span class="sxs-lookup"><span data-stu-id="44354-144">When prompted to sign in, specify <strong>user1@testlab.</strong>\<*your public domain*></span></span> <span data-ttu-id="44354-145">och väljer sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="44354-145">name, and then select **Next**.</span></span> <span data-ttu-id="44354-146">Du bör kunna logga in som User1 utan att behöva ange ett lösenord.</span><span class="sxs-lookup"><span data-stu-id="44354-146">You should successfully sign in as User1 without being prompted for a password.</span></span> <span data-ttu-id="44354-147">Detta bekräftar att sömlös enkel inloggning med Azure AD fungerar.</span><span class="sxs-lookup"><span data-stu-id="44354-147">This proves that Azure AD Seamless SSO is working.</span></span>

<span data-ttu-id="44354-148">Observera att User1 visserligen har domänadministratörsbehörighet för TESTLAB AD DS-domänen, men är inte global administratör för Azure AD.</span><span class="sxs-lookup"><span data-stu-id="44354-148">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator for Azure AD.</span></span> <span data-ttu-id="44354-149">Därför visas inte **administratörsikonen** som ett alternativ.</span><span class="sxs-lookup"><span data-stu-id="44354-149">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="44354-150">Här är konfigurationsresultatet:</span><span class="sxs-lookup"><span data-stu-id="44354-150">Here is your resulting configuration:</span></span>

![Det simulerade företaget med en testmiljö med direktautentisering](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="44354-152">Konfigurationen består av:</span><span class="sxs-lookup"><span data-stu-id="44354-152">This configuration consists of:</span></span>

- <span data-ttu-id="44354-153">En Microsoft 365 E5 utvärderingsversion eller betalda prenumerationer med DNS-domäntestlab.\<*your domain name*></span><span class="sxs-lookup"><span data-stu-id="44354-153">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain testlab.\<*your domain name*></span></span> <span data-ttu-id="44354-154">registrerat.</span><span class="sxs-lookup"><span data-stu-id="44354-154">registered.</span></span>
- <span data-ttu-id="44354-155">Ett förenklat organisationsintranät som är anslutet till internet och består av virtuella DC1-, APP1- och CLIENT1-datorer på ett undernät i ett virtuellt Azure-nätverk.</span><span class="sxs-lookup"><span data-stu-id="44354-155">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="44354-156">Azure AD Connect körs på APP1 för att synkronisera listan med konton och grupper från Azure AD-klientorganisationen för din Microsoft 365-prenumeration till TESTLAB AD DS-domänen.</span><span class="sxs-lookup"><span data-stu-id="44354-156">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span>
- <span data-ttu-id="44354-157">Azure AD Sömlös SSO är aktiverat så att datorer på det simulerade intranätet kan logga in på Microsoft 365-molnresurser utan att ange ett lösenord för användarkontot.</span><span class="sxs-lookup"><span data-stu-id="44354-157">Azure AD Seamless SSO is enabled so that computers on the simulated intranet can sign in to Microsoft 365 cloud resources without specifying a user account password.</span></span>

## <a name="next-step"></a><span data-ttu-id="44354-158">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="44354-158">Next step</span></span>

<span data-ttu-id="44354-159">Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="44354-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="44354-160">Se även</span><span class="sxs-lookup"><span data-stu-id="44354-160">See also</span></span>

[<span data-ttu-id="44354-161">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="44354-161">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="44354-162">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="44354-162">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="44354-163">Dokumentation om Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="44354-163">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)