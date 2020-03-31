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
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Sammanfattning: Konfigurera och testa sömlös enkel inloggning med Azure AD för din Microsoft 365-testmiljö.'
ms.openlocfilehash: d2b17acb2b57e379fe204e3ea4402b3f00ef7d6c
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42808971"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a><span data-ttu-id="8d00f-103">Sömlös enkel inloggning med Azure AD för din Microsoft 365-testmiljö</span><span class="sxs-lookup"><span data-stu-id="8d00f-103">Azure AD Seamless Single Sign-on for your Microsoft 365 test environment</span></span>

<span data-ttu-id="8d00f-104">*Den här testlabbguiden kan användas i både Microsoft 365 Enterprise- och Office 365 Enterprise-testmiljöer.*</span><span class="sxs-lookup"><span data-stu-id="8d00f-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="8d00f-105">Med Azure AD sömlös enkel inloggning (SSO) kan du automatiskt logga in användare när de använder sina datorer eller enheter som är anslutna till organisationens nätverk.</span><span class="sxs-lookup"><span data-stu-id="8d00f-105">Azure AD Seamless Single Sign-On (SSO) automatically signs in users when they are on their PCs or devices that are connected to their organization network.</span></span> <span data-ttu-id="8d00f-106">Sömlös SSO med Azure AD ger användare enkelt åtkomst till molnbaserade program utan att några ytterligare lokala komponenter behövs.</span><span class="sxs-lookup"><span data-stu-id="8d00f-106">Azure AD Seamless SSO provides users with easy access to cloud-based applications without needing any additional on-premises components.</span></span>

<span data-ttu-id="8d00f-107">I den här artikeln beskrivs hur du kan konfigurera Microsoft 365-testmiljön för sömlös SSO med Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8d00f-107">This article describes how you can configure your Microsoft 365 test environment for Azure AD Seamless SSO.</span></span>

<span data-ttu-id="8d00f-108">Det finns två faser för att konfigurera detta:</span><span class="sxs-lookup"><span data-stu-id="8d00f-108">There are two phases to setting this up:</span></span>

1.  <span data-ttu-id="8d00f-109">Skapa Microsoft 365-testmiljön för det simulerade företaget med synkronisering av lösenordshash.</span><span class="sxs-lookup"><span data-stu-id="8d00f-109">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="8d00f-110">Konfigurera Azure AD Connect på APP1 för sömlös SSO med Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8d00f-110">Configure Azure AD Connect on APP1 for Azure AD Seamless SSO.</span></span>
    
![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="8d00f-112">Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med Microsoft 365 Enterprise-testlabbguider.</span><span class="sxs-lookup"><span data-stu-id="8d00f-112">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="8d00f-113">Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön</span><span class="sxs-lookup"><span data-stu-id="8d00f-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="8d00f-114">Följ anvisningarna i [synkronisering av lösenordshash för Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="8d00f-114">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span></span> <span data-ttu-id="8d00f-115">Här är konfigurationsresultatet.</span><span class="sxs-lookup"><span data-stu-id="8d00f-115">Here is your resulting configuration.</span></span>
  
![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="8d00f-117">Konfigurationen består av:</span><span class="sxs-lookup"><span data-stu-id="8d00f-117">This configuration consists of:</span></span> 
  
- <span data-ttu-id="8d00f-118">Utvärderingsversioner av eller betalda prenumerationer på Microsoft 365 E5 eller Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="8d00f-118">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="8d00f-119">Ett förenklat företagsintranät anslutet till Internet som består av de virtuella datorerna DC1, APP1 och CLIENT1 i ett undernät i ett virtuellt Azure-nätverk.</span><span class="sxs-lookup"><span data-stu-id="8d00f-119">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="8d00f-120">Azure AD Connect körs på APP1 så att TESTLAB AD DS-domänen (Active Directory Domain Services) synkroniseras med Azure AD-klientorganisationen för dina Microsoft 365- och Office 365-prenumerationer med jämna mellanrum.</span><span class="sxs-lookup"><span data-stu-id="8d00f-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 or Office 365 subscription periodically.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a><span data-ttu-id="8d00f-121">Fas 2: Konfigurera Azure AD Connect på APP1 för sömlös SSO med Azure AD</span><span class="sxs-lookup"><span data-stu-id="8d00f-121">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>

<span data-ttu-id="8d00f-122">I den här fasen konfigurerar du Azure AD Connect på APP1 för sömlös SSO med Azure AD och kontrollerar sedan att det fungerar.</span><span class="sxs-lookup"><span data-stu-id="8d00f-122">In this phase, you configure Azure AD Connect on APP1 for Azure AD Seamless SSO, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="8d00f-123">Konfigurera Azure AD Connect på APP1</span><span class="sxs-lookup"><span data-stu-id="8d00f-123">Configure Azure AD Connect on APP1</span></span>

1. <span data-ttu-id="8d00f-124">Logga in på [Azure-portalen](https://portal.azure.com) med ditt globala administratörskonto och anslut sedan till APP1 med kontot TESTLAB\User1.</span><span class="sxs-lookup"><span data-stu-id="8d00f-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="8d00f-125">Kör Azure AD Connect på skrivbordet för APP1.</span><span class="sxs-lookup"><span data-stu-id="8d00f-125">From the desktop of APP1, run Azure AD Connect.</span></span>

3. <span data-ttu-id="8d00f-126">På **välkomstsidan** klickar du på **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="8d00f-126">On the **Welcome page**, click **Configure**.</span></span>

4. <span data-ttu-id="8d00f-127">På sidan **Ytterligare aktiviteter** klickar du på **Ändra användarinloggning** och sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="8d00f-127">On the **Additional tasks** page, click **Change user sign-in**, and then click **Next**.</span></span>

5. <span data-ttu-id="8d00f-128">På sidan **Anslut till Azure AD** skriver du autentiseringsuppgifterna för ditt globala administratörskonto. Klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="8d00f-128">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6. <span data-ttu-id="8d00f-129">På sidan **Användarinloggning** väljer du **Aktivera enkel inloggning** och klickar sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="8d00f-129">On the **User sign-in** page, select **Enable single sign-on**, and then click **Next**.</span></span>

7. <span data-ttu-id="8d00f-130">På sidan **Aktivera enkel inloggning** klickar du på **Ange autentiseringsuppgifter**.</span><span class="sxs-lookup"><span data-stu-id="8d00f-130">On the **Enable single sign-on** page, click **Enter credentials**.</span></span>

8. <span data-ttu-id="8d00f-131">I dialogrutan **Windows-säkerhet** skriver du **user1** och lösenordet för user1-kontot. Klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="8d00f-131">In the **Windows Security** dialog box, type **user1** and the password of the user1 account, and then click **OK**.</span></span> <span data-ttu-id="8d00f-132">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="8d00f-132">Click **Next**.</span></span>

9. <span data-ttu-id="8d00f-133">På sidan **Klart att konfigurera** klickar du på **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="8d00f-133">On the **Ready to Configure** page, click **Configure**.</span></span>

10. <span data-ttu-id="8d00f-134">På sidan **Konfigurationen är klar** klickar du på **Avsluta**.</span><span class="sxs-lookup"><span data-stu-id="8d00f-134">On the **Configuration complete** page, click **Exit**.</span></span>

11. <span data-ttu-id="8d00f-135">Gå till den vänstra rutan i Azure-portalen och klicka på **Azure Active Directory > Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="8d00f-135">From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**.</span></span> <span data-ttu-id="8d00f-136">Kontrollera att funktionen **Sömlös enkel inloggning** visas som **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="8d00f-136">Verify that the **Seamless single sign-on** feature appears as **Enabled**.</span></span>

<span data-ttu-id="8d00f-137">Sedan provar du att det går att logga in på din prenumeration med användarnamnet <strong>user1@testlab.</strong>\<din offentliga domän> för kontot User1.</span><span class="sxs-lookup"><span data-stu-id="8d00f-137">Next, test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<your public domain> user name of the User1 account.</span></span>

1. <span data-ttu-id="8d00f-138">Från Internet Explorer på APP1 klickar du på ikonen för inställningar och sedan på **Internetalternativ**.</span><span class="sxs-lookup"><span data-stu-id="8d00f-138">From Internet Explorer on APP1, click the settings icon, and then click **Internet Options**.</span></span>
 
2. <span data-ttu-id="8d00f-139">I **Internetalternativ** klickar du på fliken **Säkerhet**.</span><span class="sxs-lookup"><span data-stu-id="8d00f-139">In **Internet Options**, click the **Security** tab.</span></span>

3. <span data-ttu-id="8d00f-140">Klicka på **Lokalt intranät** och sedan på **Webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="8d00f-140">Click **Local intranet**, and then click **Sites**.</span></span>

4. <span data-ttu-id="8d00f-141">I **Lokalt intranät** klickar du på **Avancerat**.</span><span class="sxs-lookup"><span data-stu-id="8d00f-141">In **Local intranet**, click **Advanced**.</span></span>

5. <span data-ttu-id="8d00f-142">I **Lägg till följande webbplats i zonen** skriver du **https<span>://</span>autologon.microsoftazuread-sso.com** och klickar på **Lägg till > Stäng > OK > OK**.</span><span class="sxs-lookup"><span data-stu-id="8d00f-142">In **Add this website to the zone**, type **https<span>://</span>autologon.microsoftazuread-sso.com**, click **Add > Close > OK > OK**.</span></span>

6. <span data-ttu-id="8d00f-143">Logga ut och logga sedan in igen. Den här gången med ett annat konto.</span><span class="sxs-lookup"><span data-stu-id="8d00f-143">Sign out, and then sign in again, this time specifying a different account.</span></span>

7. <span data-ttu-id="8d00f-144">När du uppmanas att logga in anger du namnet <strong>user1@testlab.</strong>\<din offentliga domän> och klickar sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="8d00f-144">When prompted to sign in, specify <strong>user1@testlab.</strong>\<your public domain> name, and then click **Next**.</span></span> <span data-ttu-id="8d00f-145">Du bör kunna logga in som User1 utan att behöva ange ett lösenord.</span><span class="sxs-lookup"><span data-stu-id="8d00f-145">You should successfully sign in as User1 without being prompted for a password.</span></span> <span data-ttu-id="8d00f-146">Detta bekräftar att sömlös enkel inloggning med Azure AD fungerar.</span><span class="sxs-lookup"><span data-stu-id="8d00f-146">This proves that Azure AD Seamless SSO is working.</span></span>

<span data-ttu-id="8d00f-147">Observera att User1 visserligen har domänadministratörsbehörighet för TESTLAB AD DS-domänen, men är inte global administratör för Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8d00f-147">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator for Azure AD.</span></span> <span data-ttu-id="8d00f-148">Därför visas inte **administratörsikonen** som ett alternativ.</span><span class="sxs-lookup"><span data-stu-id="8d00f-148">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="8d00f-149">Här är konfigurationsresultatet:</span><span class="sxs-lookup"><span data-stu-id="8d00f-149">Here is your resulting configuration:</span></span>

![Det simulerade företaget med testmiljö med direktautentisering](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

 
<span data-ttu-id="8d00f-151">Konfigurationen består av:</span><span class="sxs-lookup"><span data-stu-id="8d00f-151">This configuration consists of:</span></span>

- <span data-ttu-id="8d00f-152">Utvärderingsversioner av eller betalda prenumerationer på Microsoft 365 E5 eller Office 365 E5 med DNS-domänen testlab.\<ditt domännamn> registrerad.</span><span class="sxs-lookup"><span data-stu-id="8d00f-152">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain testlab.\<your domain name> registered.</span></span>
- <span data-ttu-id="8d00f-153">Ett förenklat företagsintranät anslutet till Internet som består av de virtuella datorerna DC1, APP1 och CLIENT1 i ett undernät i ett virtuellt Azure-nätverk.</span><span class="sxs-lookup"><span data-stu-id="8d00f-153">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="8d00f-154">Azure AD Connect körs på APP1 så att listan med konton och grupper synkroniseras från Azure AD-klientorganisationen för dina Microsoft 365- eller Office 365-prenumerationer till TESTLAB AD DS-domänen.</span><span class="sxs-lookup"><span data-stu-id="8d00f-154">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 or Office 365 subscription to the TESTLAB AD DS domain.</span></span> 
- <span data-ttu-id="8d00f-155">Sömlös enkel inloggning med Azure AD är aktiverat så att datorer i det simulerade intranätet kan logga in i Microsoft 365-molnresurser utan att ange ett lösenord för användarkontot.</span><span class="sxs-lookup"><span data-stu-id="8d00f-155">Azure AD Seamless SSO is enabled so that computers on the simulated intranet can sign in to Microsoft 365 cloud resources without specifing a user account password.</span></span>

<span data-ttu-id="8d00f-156">I steget [Förenkla användarinloggning](identity-secure-your-passwords.md#identity-sso) i Identitet-fasen finns mer information om och länkar till hur du konfigurerar sömlös enkel inloggning med Azure AD i produktion.</span><span class="sxs-lookup"><span data-stu-id="8d00f-156">See the [Simplify user sign-in](identity-secure-your-passwords.md#identity-sso) step in the Identity phase for information and links to configure Azure AD Seamless SSO in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="8d00f-157">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="8d00f-157">Next step</span></span>

<span data-ttu-id="8d00f-158">Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="8d00f-158">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="8d00f-159">Se även</span><span class="sxs-lookup"><span data-stu-id="8d00f-159">See also</span></span>

[<span data-ttu-id="8d00f-160">Testlabbguider för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="8d00f-160">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="8d00f-161">Distribuera Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="8d00f-161">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="8d00f-162">Microsoft 365 Enterprise-dokumentation</span><span class="sxs-lookup"><span data-stu-id="8d00f-162">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


