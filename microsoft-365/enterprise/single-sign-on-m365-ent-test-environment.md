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
ms.openlocfilehash: 3ba229a62f66cad715f604bab91cd12032da7be8
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685778"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a><span data-ttu-id="862d3-103">Sömlös enkel inloggning med Azure AD för din Microsoft 365-testmiljö</span><span class="sxs-lookup"><span data-stu-id="862d3-103">Azure AD Seamless Single Sign-on for your Microsoft 365 test environment</span></span>

<span data-ttu-id="862d3-104">*Den här test laboratorie guiden kan användas för både Microsoft 365 för företags-och Office 365 företags test miljöer.*</span><span class="sxs-lookup"><span data-stu-id="862d3-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="862d3-105">Med Azure AD sömlös enkel inloggning (SSO) kan du automatiskt logga in användare när de använder sina datorer eller enheter som är anslutna till organisationens nätverk.</span><span class="sxs-lookup"><span data-stu-id="862d3-105">Azure AD Seamless Single Sign-On (SSO) automatically signs in users when they are on their PCs or devices that are connected to their organization network.</span></span> <span data-ttu-id="862d3-106">Sömlös SSO med Azure AD ger användare enkelt åtkomst till molnbaserade program utan att några ytterligare lokala komponenter behövs.</span><span class="sxs-lookup"><span data-stu-id="862d3-106">Azure AD Seamless SSO provides users with easy access to cloud-based applications without needing any additional on-premises components.</span></span>

<span data-ttu-id="862d3-107">I den här artikeln beskrivs hur du kan konfigurera Microsoft 365-testmiljön för sömlös SSO med Azure AD.</span><span class="sxs-lookup"><span data-stu-id="862d3-107">This article describes how you can configure your Microsoft 365 test environment for Azure AD Seamless SSO.</span></span>

<span data-ttu-id="862d3-108">Det finns två faser för att konfigurera detta:</span><span class="sxs-lookup"><span data-stu-id="862d3-108">There are two phases to setting this up:</span></span>

1.    <span data-ttu-id="862d3-109">Skapa Microsoft 365-testmiljön för det simulerade företaget med synkronisering av lösenordshash.</span><span class="sxs-lookup"><span data-stu-id="862d3-109">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.    <span data-ttu-id="862d3-110">Konfigurera Azure AD Connect på APP1 för sömlös SSO med Azure AD.</span><span class="sxs-lookup"><span data-stu-id="862d3-110">Configure Azure AD Connect on APP1 for Azure AD Seamless SSO.</span></span>
    
![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="862d3-112">Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med testlabbguider för Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="862d3-112">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="862d3-113">Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön</span><span class="sxs-lookup"><span data-stu-id="862d3-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="862d3-114">Följ anvisningarna i [synkronisering av lösenordshash för Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="862d3-114">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span></span> <span data-ttu-id="862d3-115">Här är konfigurationsresultatet.</span><span class="sxs-lookup"><span data-stu-id="862d3-115">Here is your resulting configuration.</span></span>
  
![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="862d3-117">Konfigurationen består av:</span><span class="sxs-lookup"><span data-stu-id="862d3-117">This configuration consists of:</span></span> 
  
- <span data-ttu-id="862d3-118">En utvärderingsprenumeration eller betald prenumeration på Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="862d3-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="862d3-119">Ett förenklat företagsintranät anslutet till Internet som består av de virtuella datorerna DC1, APP1 och CLIENT1 i ett undernät i ett virtuellt Azure-nätverk.</span><span class="sxs-lookup"><span data-stu-id="862d3-119">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="862d3-120">Azure AD Connect körs på APP1 så att TESTLAB AD DS-domänen (Active Directory Domain Services) synkroniseras med Azure AD-klientorganisationen för dina Microsoft 365-prenumerationer med jämna mellanrum.</span><span class="sxs-lookup"><span data-stu-id="862d3-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscription periodically.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a><span data-ttu-id="862d3-121">Fas 2: Konfigurera Azure AD Connect på APP1 för sömlös SSO med Azure AD</span><span class="sxs-lookup"><span data-stu-id="862d3-121">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>

<span data-ttu-id="862d3-122">I den här fasen konfigurerar du Azure AD Connect på APP1 för sömlös SSO med Azure AD och kontrollerar sedan att det fungerar.</span><span class="sxs-lookup"><span data-stu-id="862d3-122">In this phase, you configure Azure AD Connect on APP1 for Azure AD Seamless SSO, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="862d3-123">Konfigurera Azure AD Connect på APP1</span><span class="sxs-lookup"><span data-stu-id="862d3-123">Configure Azure AD Connect on APP1</span></span>

1. <span data-ttu-id="862d3-124">Logga in på [Azure-portalen](https://portal.azure.com) med ditt globala administratörskonto och anslut sedan till APP1 med kontot TESTLAB\User1.</span><span class="sxs-lookup"><span data-stu-id="862d3-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="862d3-125">Kör Azure AD Connect på skrivbordet för APP1.</span><span class="sxs-lookup"><span data-stu-id="862d3-125">From the desktop of APP1, run Azure AD Connect.</span></span>

3. <span data-ttu-id="862d3-126">På **välkomstsidan** klickar du på **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="862d3-126">On the **Welcome page**, click **Configure**.</span></span>

4. <span data-ttu-id="862d3-127">På sidan **Ytterligare aktiviteter** klickar du på **Ändra användarinloggning** och sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="862d3-127">On the **Additional tasks** page, click **Change user sign-in**, and then click **Next**.</span></span>

5. <span data-ttu-id="862d3-128">På sidan **Anslut till Azure AD** skriver du autentiseringsuppgifterna för ditt globala administratörskonto. Klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="862d3-128">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6. <span data-ttu-id="862d3-129">På sidan **Användarinloggning** väljer du **Aktivera enkel inloggning** och klickar sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="862d3-129">On the **User sign-in** page, select **Enable single sign-on**, and then click **Next**.</span></span>

7. <span data-ttu-id="862d3-130">På sidan **Aktivera enkel inloggning** klickar du på **Ange autentiseringsuppgifter**.</span><span class="sxs-lookup"><span data-stu-id="862d3-130">On the **Enable single sign-on** page, click **Enter credentials**.</span></span>

8. <span data-ttu-id="862d3-131">I dialogrutan **Windows-säkerhet** skriver du **user1** och lösenordet för user1-kontot. Klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="862d3-131">In the **Windows Security** dialog box, type **user1** and the password of the user1 account, and then click **OK**.</span></span> <span data-ttu-id="862d3-132">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="862d3-132">Click **Next**.</span></span>

9. <span data-ttu-id="862d3-133">På sidan **Klart att konfigurera** klickar du på **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="862d3-133">On the **Ready to Configure** page, click **Configure**.</span></span>

10. <span data-ttu-id="862d3-134">På sidan **Konfigurationen är klar** klickar du på **Avsluta**.</span><span class="sxs-lookup"><span data-stu-id="862d3-134">On the **Configuration complete** page, click **Exit**.</span></span>

11. <span data-ttu-id="862d3-135">Gå till den vänstra rutan i Azure-portalen och klicka på **Azure Active Directory > Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="862d3-135">From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**.</span></span> <span data-ttu-id="862d3-136">Kontrollera att funktionen **Sömlös enkel inloggning** visas som **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="862d3-136">Verify that the **Seamless single sign-on** feature appears as **Enabled**.</span></span>

<span data-ttu-id="862d3-137">Prova sedan att logga in på ditt abonnemang med <strong>user1@testlab.</strong>\<your public domain></span><span class="sxs-lookup"><span data-stu-id="862d3-137">Next, test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<your public domain></span></span> <span data-ttu-id="862d3-138">användarnamn för Användare1-kontot.</span><span class="sxs-lookup"><span data-stu-id="862d3-138">user name of the User1 account.</span></span>

1. <span data-ttu-id="862d3-139">Från Internet Explorer på APP1 klickar du på ikonen för inställningar och sedan på **Internetalternativ**.</span><span class="sxs-lookup"><span data-stu-id="862d3-139">From Internet Explorer on APP1, click the settings icon, and then click **Internet Options**.</span></span>
 
2. <span data-ttu-id="862d3-140">I **Internetalternativ** klickar du på fliken **Säkerhet**.</span><span class="sxs-lookup"><span data-stu-id="862d3-140">In **Internet Options**, click the **Security** tab.</span></span>

3. <span data-ttu-id="862d3-141">Klicka på **Lokalt intranät** och sedan på **Webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="862d3-141">Click **Local intranet**, and then click **Sites**.</span></span>

4. <span data-ttu-id="862d3-142">I **Lokalt intranät** klickar du på **Avancerat**.</span><span class="sxs-lookup"><span data-stu-id="862d3-142">In **Local intranet**, click **Advanced**.</span></span>

5. <span data-ttu-id="862d3-143">I **Lägg till följande webbplats i zonen** skriver du **https<span>://</span>autologon.microsoftazuread-sso.com** och klickar på **Lägg till > Stäng > OK > OK**.</span><span class="sxs-lookup"><span data-stu-id="862d3-143">In **Add this website to the zone**, type **https<span>://</span>autologon.microsoftazuread-sso.com**, click **Add > Close > OK > OK**.</span></span>

6. <span data-ttu-id="862d3-144">Logga ut och logga sedan in igen. Den här gången med ett annat konto.</span><span class="sxs-lookup"><span data-stu-id="862d3-144">Sign out, and then sign in again, this time specifying a different account.</span></span>

7. <span data-ttu-id="862d3-145">När du uppmanas att logga in anger du <strong>user1@testlab.</strong>\<your public domain></span><span class="sxs-lookup"><span data-stu-id="862d3-145">When prompted to sign in, specify <strong>user1@testlab.</strong>\<your public domain></span></span> <span data-ttu-id="862d3-146">och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="862d3-146">name, and then click **Next**.</span></span> <span data-ttu-id="862d3-147">Du bör kunna logga in som User1 utan att behöva ange ett lösenord.</span><span class="sxs-lookup"><span data-stu-id="862d3-147">You should successfully sign in as User1 without being prompted for a password.</span></span> <span data-ttu-id="862d3-148">Detta bekräftar att sömlös enkel inloggning med Azure AD fungerar.</span><span class="sxs-lookup"><span data-stu-id="862d3-148">This proves that Azure AD Seamless SSO is working.</span></span>

<span data-ttu-id="862d3-149">Observera att User1 visserligen har domänadministratörsbehörighet för TESTLAB AD DS-domänen, men är inte global administratör för Azure AD.</span><span class="sxs-lookup"><span data-stu-id="862d3-149">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator for Azure AD.</span></span> <span data-ttu-id="862d3-150">Därför visas inte **administratörsikonen** som ett alternativ.</span><span class="sxs-lookup"><span data-stu-id="862d3-150">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="862d3-151">Här är konfigurationsresultatet:</span><span class="sxs-lookup"><span data-stu-id="862d3-151">Here is your resulting configuration:</span></span>

![Det simulerade företaget med en testmiljö med direktautentisering](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

 
<span data-ttu-id="862d3-153">Konfigurationen består av:</span><span class="sxs-lookup"><span data-stu-id="862d3-153">This configuration consists of:</span></span>

- <span data-ttu-id="862d3-154">En utvärderings version av Microsoft 365 E5 eller betalda abonnemang med DNS-testlab.\<your domain name></span><span class="sxs-lookup"><span data-stu-id="862d3-154">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain testlab.\<your domain name></span></span> <span data-ttu-id="862d3-155">registrerat.</span><span class="sxs-lookup"><span data-stu-id="862d3-155">registered.</span></span>
- <span data-ttu-id="862d3-156">Ett förenklat företagsintranät anslutet till Internet som består av de virtuella datorerna DC1, APP1 och CLIENT1 i ett undernät i ett virtuellt Azure-nätverk.</span><span class="sxs-lookup"><span data-stu-id="862d3-156">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="862d3-157">Azure AD Connect körs på APP1 så att listan med konton och grupper synkroniseras från Azure AD-klientorganisationen för dina Microsoft 365-prenumerationer till TESTLAB AD DS-domänen.</span><span class="sxs-lookup"><span data-stu-id="862d3-157">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span> 
- <span data-ttu-id="862d3-158">Sömlös enkel inloggning med Azure AD är aktiverat så att datorer i det simulerade intranätet kan logga in i Microsoft 365-molnresurser utan att ange ett lösenord för användarkontot.</span><span class="sxs-lookup"><span data-stu-id="862d3-158">Azure AD Seamless SSO is enabled so that computers on the simulated intranet can sign in to Microsoft 365 cloud resources without specifing a user account password.</span></span>

## <a name="next-step"></a><span data-ttu-id="862d3-159">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="862d3-159">Next step</span></span>

<span data-ttu-id="862d3-160">Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="862d3-160">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="862d3-161">Se även</span><span class="sxs-lookup"><span data-stu-id="862d3-161">See also</span></span>

[<span data-ttu-id="862d3-162">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="862d3-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="862d3-163">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="862d3-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="862d3-164">Microsoft 365 för företags dokumentation</span><span class="sxs-lookup"><span data-stu-id="862d3-164">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


