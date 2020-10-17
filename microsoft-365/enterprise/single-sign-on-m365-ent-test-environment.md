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
ms.openlocfilehash: f98f82de50feb2a9f92d1ecc4775c5307b314a72
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487612"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a><span data-ttu-id="e1d3b-103">Sömlös enkel inloggning med Azure AD för din Microsoft 365-testmiljö</span><span class="sxs-lookup"><span data-stu-id="e1d3b-103">Azure AD Seamless Single Sign-on for your Microsoft 365 test environment</span></span>

<span data-ttu-id="e1d3b-104">*Den här test laboratorie guiden kan användas för både Microsoft 365 för företags-och Office 365 företags test miljöer.*</span><span class="sxs-lookup"><span data-stu-id="e1d3b-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="e1d3b-105">Azure AD-sömlös enda Sign-On (sömlös SSO) loggar automatiskt in användare när de använder sina datorer eller enheter som är anslutna till deras organisations nätverk.</span><span class="sxs-lookup"><span data-stu-id="e1d3b-105">Azure AD Seamless Single Sign-On (Seamless SSO) automatically signs in users when they are on their PCs or devices that are connected to their organization network.</span></span> <span data-ttu-id="e1d3b-106">Sömlös SSO med Azure AD ger användare enkelt åtkomst till molnbaserade program utan att några ytterligare lokala komponenter behövs.</span><span class="sxs-lookup"><span data-stu-id="e1d3b-106">Azure AD Seamless SSO provides users with easy access to cloud-based applications without needing any additional on-premises components.</span></span>

<span data-ttu-id="e1d3b-107">I den här artikeln beskrivs hur du konfigurerar din Microsoft 365 test miljö för Azure AD sömlös SSO.</span><span class="sxs-lookup"><span data-stu-id="e1d3b-107">This article describes how to configure your Microsoft 365 test environment for Azure AD Seamless SSO.</span></span>

<span data-ttu-id="e1d3b-108">Installation av Azure AD sömlös SSO handlar om två faser:</span><span class="sxs-lookup"><span data-stu-id="e1d3b-108">Setting up Azure AD Seamless SSO involves two phases:</span></span>
- [<span data-ttu-id="e1d3b-109">Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön</span><span class="sxs-lookup"><span data-stu-id="e1d3b-109">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="e1d3b-110">Fas 2: Konfigurera Azure AD Connect på APP1 för sömlös SSO med Azure AD</span><span class="sxs-lookup"><span data-stu-id="e1d3b-110">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>](#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso)
   
![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="e1d3b-112">Om du vill visa en visuell karta till alla artiklar i gruppen Microsoft 365 för Enterprise-testlabbet går du till [Microsoft 365 för Enterprise Test Lab-guide](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="e1d3b-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="e1d3b-113">Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön</span><span class="sxs-lookup"><span data-stu-id="e1d3b-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="e1d3b-114">Följ anvisningarna i [synkronisering av lösenordshash för Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="e1d3b-114">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span></span> 

<span data-ttu-id="e1d3b-115">Den resulterande konfigurationen ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="e1d3b-115">Your resulting configuration looks like this:</span></span>
  
![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="e1d3b-117">Konfigurationen består av:</span><span class="sxs-lookup"><span data-stu-id="e1d3b-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="e1d3b-118">En utvärderingsprenumeration eller betald prenumeration på Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="e1d3b-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="e1d3b-119">En förenklad organisations intranät som är ansluten till Internet, bestående av de virtuella datorerna DC1, APP1 och KLIENT1 i ett undernät för ett Azure Virtual Network.</span><span class="sxs-lookup"><span data-stu-id="e1d3b-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="e1d3b-120">Azure AD Connect körs på APP1 för att synkronisera TESTLAB AD DS-domän (Active Directory Domain Services) regelbundet till Azure AD-klient organisationen för din Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="e1d3b-120">Azure AD Connect runs on APP1 to periodically synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a><span data-ttu-id="e1d3b-121">Fas 2: Konfigurera Azure AD Connect på APP1 för sömlös SSO med Azure AD</span><span class="sxs-lookup"><span data-stu-id="e1d3b-121">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>

<span data-ttu-id="e1d3b-122">I den här fasen konfigurerar du Azure AD Connect på APP1 för Azure AD sömlös SSO och kontrollerar sedan att det fungerar.</span><span class="sxs-lookup"><span data-stu-id="e1d3b-122">In this phase, configure Azure AD Connect on APP1 for Azure AD Seamless SSO, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="e1d3b-123">Konfigurera Azure AD Connect på APP1</span><span class="sxs-lookup"><span data-stu-id="e1d3b-123">Configure Azure AD Connect on APP1</span></span>

1. <span data-ttu-id="e1d3b-124">Logga in på [Azure-portalen](https://portal.azure.com) med ditt globala administratörskonto och anslut sedan till APP1 med kontot TESTLAB\User1.</span><span class="sxs-lookup"><span data-stu-id="e1d3b-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="e1d3b-125">Kör Azure AD Connect från APP1 skriv bord.</span><span class="sxs-lookup"><span data-stu-id="e1d3b-125">From the APP1 desktop, run Azure AD Connect.</span></span>

3. <span data-ttu-id="e1d3b-126">På **Välkomst sidan**väljer du **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="e1d3b-126">On the **Welcome page**, select **Configure**.</span></span>

4. <span data-ttu-id="e1d3b-127">På sidan **Ytterligare aktiviteter** väljer du **ändra användar inloggning**och sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="e1d3b-127">On the **Additional tasks** page, select **Change user sign-in**, and then select **Next**.</span></span>

5. <span data-ttu-id="e1d3b-128">På sidan **Anslut till Azure AD** anger du dina globala administratörs konto uppgifter och väljer sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="e1d3b-128">On the **Connect to Azure AD** page, enter your global administrator account credentials, and then select **Next**.</span></span>

6. <span data-ttu-id="e1d3b-129">På **inloggnings** sidan för användare väljer du **aktivera enkel inloggning**och sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="e1d3b-129">On the **User sign-in** page, select **Enable single sign-on**, and then select **Next**.</span></span>

7. <span data-ttu-id="e1d3b-130">På sidan **aktivera enkel inloggning** väljer du **ange autentiseringsuppgifter**.</span><span class="sxs-lookup"><span data-stu-id="e1d3b-130">On the **Enable single sign-on** page, select **Enter credentials**.</span></span>

8. <span data-ttu-id="e1d3b-131">I dialog rutan **Windows-säkerhet** anger du **Användare1** och lösen ordet för user1-kontot, väljer **OK**och sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="e1d3b-131">In the **Windows Security** dialog box, enter **user1** and the password of the user1 account, select **OK**, and then select **Next**.</span></span>

9. <span data-ttu-id="e1d3b-132">På sidan **redo att konfigurera** väljer du **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="e1d3b-132">On the **Ready to Configure** page, select **Configure**.</span></span>

10. <span data-ttu-id="e1d3b-133">På sidan **slutförd konfigurering** väljer du **Avsluta**.</span><span class="sxs-lookup"><span data-stu-id="e1d3b-133">On the **Configuration complete** page, select **Exit**.</span></span>

11. <span data-ttu-id="e1d3b-134">I det vänstra fönstret i Azure-portalen väljer du **Azure Active Directory**  >  **Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="e1d3b-134">From the Azure portal, in the left pane, select **Azure Active Directory** > **Azure AD Connect**.</span></span> <span data-ttu-id="e1d3b-135">Kontrollera att funktionen **Sömlös enkel inloggning** visas som **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="e1d3b-135">Verify that the **Seamless single sign-on** feature appears as **Enabled**.</span></span>

<span data-ttu-id="e1d3b-136">Prova sedan att logga in på ditt abonnemang med <strong>user1@testlab.</strong>\<*your public domain*></span><span class="sxs-lookup"><span data-stu-id="e1d3b-136">Next, test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<*your public domain*></span></span> <span data-ttu-id="e1d3b-137">användarnamn för Användare1-kontot.</span><span class="sxs-lookup"><span data-stu-id="e1d3b-137">user name of the User1 account.</span></span>

1. <span data-ttu-id="e1d3b-138">I Internet Explorer på APP1 väljer du ikonen Inställningar och sedan **Internet-alternativ**.</span><span class="sxs-lookup"><span data-stu-id="e1d3b-138">From Internet Explorer on APP1, select the settings icon, and then select **Internet Options**.</span></span>
 
2. <span data-ttu-id="e1d3b-139">I **Internet alternativ**väljer du fliken **säkerhet** .</span><span class="sxs-lookup"><span data-stu-id="e1d3b-139">In **Internet Options**, select the **Security** tab.</span></span>

3. <span data-ttu-id="e1d3b-140">Välj **Lokalt intranät**och välj sedan **webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="e1d3b-140">Select **Local intranet**, and then select **Sites**.</span></span>

4. <span data-ttu-id="e1d3b-141">I **Lokalt intranät**väljer du **Avancerat**.</span><span class="sxs-lookup"><span data-stu-id="e1d3b-141">In **Local intranet**, select **Advanced**.</span></span>

5. <span data-ttu-id="e1d3b-142">I **Lägg till den här webbplatsen i zonen**anger du **https<span>://</span>AutoLogon.microsoftazuread-SSO.com**väljer du **Add**  >  **Close**  >  **OK**  >  **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1d3b-142">In **Add this website to the zone**, enter **https<span>://</span>autologon.microsoftazuread-sso.com**, select **Add** > **Close** > **OK** > **OK**.</span></span>

6. <span data-ttu-id="e1d3b-143">Logga ut och logga sedan in igen. Den här gången med ett annat konto.</span><span class="sxs-lookup"><span data-stu-id="e1d3b-143">Sign out, and then sign in again, this time specifying a different account.</span></span>

7. <span data-ttu-id="e1d3b-144">När du uppmanas att logga in anger du <strong>user1@testlab.</strong>\<*your public domain*></span><span class="sxs-lookup"><span data-stu-id="e1d3b-144">When prompted to sign in, specify <strong>user1@testlab.</strong>\<*your public domain*></span></span> <span data-ttu-id="e1d3b-145">och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="e1d3b-145">name, and then select **Next**.</span></span> <span data-ttu-id="e1d3b-146">Du bör kunna logga in som User1 utan att behöva ange ett lösenord.</span><span class="sxs-lookup"><span data-stu-id="e1d3b-146">You should successfully sign in as User1 without being prompted for a password.</span></span> <span data-ttu-id="e1d3b-147">Detta bekräftar att sömlös enkel inloggning med Azure AD fungerar.</span><span class="sxs-lookup"><span data-stu-id="e1d3b-147">This proves that Azure AD Seamless SSO is working.</span></span>

<span data-ttu-id="e1d3b-148">Observera att User1 visserligen har domänadministratörsbehörighet för TESTLAB AD DS-domänen, men är inte global administratör för Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e1d3b-148">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator for Azure AD.</span></span> <span data-ttu-id="e1d3b-149">Därför visas inte **administratörsikonen** som ett alternativ.</span><span class="sxs-lookup"><span data-stu-id="e1d3b-149">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="e1d3b-150">Här är konfigurationsresultatet:</span><span class="sxs-lookup"><span data-stu-id="e1d3b-150">Here is your resulting configuration:</span></span>

![Det simulerade företaget med en testmiljö med direktautentisering](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="e1d3b-152">Konfigurationen består av:</span><span class="sxs-lookup"><span data-stu-id="e1d3b-152">This configuration consists of:</span></span>

- <span data-ttu-id="e1d3b-153">En utvärderings version av Microsoft 365 E5 eller betalda abonnemang med DNS-testlab.\<*your domain name*></span><span class="sxs-lookup"><span data-stu-id="e1d3b-153">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain testlab.\<*your domain name*></span></span> <span data-ttu-id="e1d3b-154">registrerat.</span><span class="sxs-lookup"><span data-stu-id="e1d3b-154">registered.</span></span>
- <span data-ttu-id="e1d3b-155">En förenklad organisations intranät som är ansluten till Internet, bestående av de virtuella datorerna DC1, APP1 och KLIENT1 i ett undernät för ett Azure Virtual Network.</span><span class="sxs-lookup"><span data-stu-id="e1d3b-155">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="e1d3b-156">Azure AD Connect körs på APP1 för att synkronisera listan med konton och grupper från Azure AD-klientorganisationen för din Microsoft 365-prenumeration till TESTLAB AD DS-domänen.</span><span class="sxs-lookup"><span data-stu-id="e1d3b-156">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span>
- <span data-ttu-id="e1d3b-157">Azure AD sömlös SSO är aktiverat så att datorer i det simulerade intranätet kan logga in på Microsoft 365-moln resurser utan att ange ett lösen ord för kontot.</span><span class="sxs-lookup"><span data-stu-id="e1d3b-157">Azure AD Seamless SSO is enabled so that computers on the simulated intranet can sign in to Microsoft 365 cloud resources without specifying a user account password.</span></span>

## <a name="next-step"></a><span data-ttu-id="e1d3b-158">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="e1d3b-158">Next step</span></span>

<span data-ttu-id="e1d3b-159">Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="e1d3b-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="e1d3b-160">Se även</span><span class="sxs-lookup"><span data-stu-id="e1d3b-160">See also</span></span>

[<span data-ttu-id="e1d3b-161">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="e1d3b-161">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="e1d3b-162">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="e1d3b-162">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="e1d3b-163">Microsoft 365 för företags dokumentation</span><span class="sxs-lookup"><span data-stu-id="e1d3b-163">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
