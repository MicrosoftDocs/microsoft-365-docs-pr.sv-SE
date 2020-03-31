---
title: Återställning av lösenord i testmiljön för Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/13/2019
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
description: 'Sammanfattning: Konfigurera och testa återställning av lösenord i testmiljön för Microsoft 365.'
ms.openlocfilehash: c8d5ed0c7feac98afd3230a305f4ab1f850ca7f8
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42806789"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="b71b2-103">Återställning av lösenord i testmiljön för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b71b2-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="b71b2-104">*Den här testlabbguiden kan bara användas i Microsoft 365 Enterprise-testmiljöer.*</span><span class="sxs-lookup"><span data-stu-id="b71b2-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="b71b2-105">Med självbetjäningen för återställning av lösenord (SSPR) i Azure Active Directory (Azure AD) kan användarna återställa eller låsa upp sina lösenord eller konton.</span><span class="sxs-lookup"><span data-stu-id="b71b2-105">Azure Active Directory (Azure AD) self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> 

<span data-ttu-id="b71b2-106">I den här artikeln beskrivs hur du kan konfigurera och testa lösenordsåterställning i Microsoft 365-testmiljön i tre faser:</span><span class="sxs-lookup"><span data-stu-id="b71b2-106">This article describes how you can configure and test password resets in your Microsoft 365 test environment in three phases:</span></span>

1.  <span data-ttu-id="b71b2-107">Skapa testmiljön för Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="b71b2-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="b71b2-108">Aktivera tillbakaskrivning av lösenord.</span><span class="sxs-lookup"><span data-stu-id="b71b2-108">Enable password writeback.</span></span>
3.  <span data-ttu-id="b71b2-109">Konfigurera och testa lösenordsåterställningen för kontot Användare 3.</span><span class="sxs-lookup"><span data-stu-id="b71b2-109">Configure and test password reset for the User 3 account.</span></span>
    
![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="b71b2-111">Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med Microsoft 365 Enterprise-testlabbguider.</span><span class="sxs-lookup"><span data-stu-id="b71b2-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="b71b2-112">Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön</span><span class="sxs-lookup"><span data-stu-id="b71b2-112">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="b71b2-113">Följ först anvisningarna i [Synkronisering av lösenordshash](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="b71b2-113">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span> <span data-ttu-id="b71b2-114">Här är konfigurationsresultatet.</span><span class="sxs-lookup"><span data-stu-id="b71b2-114">Here is your resulting configuration.</span></span>
  
![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="b71b2-116">Konfigurationen består av:</span><span class="sxs-lookup"><span data-stu-id="b71b2-116">This configuration consists of:</span></span> 
  
- <span data-ttu-id="b71b2-117">Utvärderingsversioner eller betalda prenumerationer för Microsoft 365 E5 eller Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="b71b2-117">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="b71b2-118">Ett förenklat företagsintranät anslutet till Internet som består av de virtuella datorerna DC1, APP1 och CLIENT1 i ett undernät i ett virtuellt Azure-nätverk.</span><span class="sxs-lookup"><span data-stu-id="b71b2-118">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="b71b2-119">Azure AD Connect körs på APP1 så att TESTLAB AD DS-domänen (Active Directory Domain Services) synkroniseras med Azure AD-klientorganisationen för din Microsoft 365- eller Office 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="b71b2-119">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 or Office 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback"></a><span data-ttu-id="b71b2-120">Fas 2: Aktivera tillbakaskrivning av lösenord</span><span class="sxs-lookup"><span data-stu-id="b71b2-120">Phase 2: Enable password writeback</span></span>

<span data-ttu-id="b71b2-121">Följ anvisningarna i [fas 2 i testlabbguiden för tillbakaskrivning av lösenord](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="b71b2-121">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

<span data-ttu-id="b71b2-122">Du måste aktivera tillbakaskrivning av lösenord för att kunna använda återställning av lösenord.</span><span class="sxs-lookup"><span data-stu-id="b71b2-122">You must have password writeback enabled to use password reset.</span></span>
  
## <a name="phase-3-configure-and-test-password-reset"></a><span data-ttu-id="b71b2-123">Steg 3: Konfigurera och testa återställning av lösenord</span><span class="sxs-lookup"><span data-stu-id="b71b2-123">Phase 3: Configure and test password reset</span></span>

<span data-ttu-id="b71b2-124">I den här fasen konfigurerar du återställning av lösenord i Azure AD-klientorganisationen via gruppmedlemskap och kontrollerar sedan att det fungerar.</span><span class="sxs-lookup"><span data-stu-id="b71b2-124">In this phase, you configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="b71b2-125">Börja med att aktivera återställning av lösenord för kontona i en specifik Azure AD-grupp.</span><span class="sxs-lookup"><span data-stu-id="b71b2-125">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="b71b2-126">Öppna [https://portal.azure.com](https://portal.azure.com) i en privat instans av webbläsaren och logga sedan in med inloggningsuppgifterna för ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="b71b2-126">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="b71b2-127">I Azure-portalen klickar du på **Azure Active Directory > Grupper > Ny grupp**.</span><span class="sxs-lookup"><span data-stu-id="b71b2-127">In the Azure portal, click **Azure Active Directory > Groups > New group**.</span></span>
3. <span data-ttu-id="b71b2-128">Ange **Grupptyp** som **Säkerhet**, **Gruppnamn** som **PWReset** och **Typ av medlemskap** som **Tilldelad**.</span><span class="sxs-lookup"><span data-stu-id="b71b2-128">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**.</span></span> 
4. <span data-ttu-id="b71b2-129">Klicka på **Medlemmar**, leta upp och välj **Användare 3** och klicka sedan på **Välj** och på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="b71b2-129">Click **Members**, find and select **User 3**, and then click **Select**, and then click **Create**.</span></span>
5. <span data-ttu-id="b71b2-130">Stäng fönstret **Grupper**.</span><span class="sxs-lookup"><span data-stu-id="b71b2-130">Close the **Groups** pane.</span></span>
6. <span data-ttu-id="b71b2-131">I Azure Active Directory-fönstret klickar du på **Återställ lösenord** i det vänstra navigeringsfältet.</span><span class="sxs-lookup"><span data-stu-id="b71b2-131">In the Azure Active Directory pane, click **Password reset** in the left navigation.</span></span>
7. <span data-ttu-id="b71b2-132">I fönstret **Egenskaper för återställning av lösenord**, under alternativet **Återställning av lösenord via självbetjäning har aktiverats**, väljer du **Vald**.</span><span class="sxs-lookup"><span data-stu-id="b71b2-132">In the **Password reset-Properties** pane, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
8. <span data-ttu-id="b71b2-133">Klicka på **Välj grupp**, välj gruppen **PWReset** och klicka sedan på **Välj > Spara**.</span><span class="sxs-lookup"><span data-stu-id="b71b2-133">Click **Select group**, select the **PWReset** group, and then click **Select > Save**.</span></span>
9. <span data-ttu-id="b71b2-134">Stäng den privata webbläsarinstansen.</span><span class="sxs-lookup"><span data-stu-id="b71b2-134">Close the private browser instance.</span></span>

<span data-ttu-id="b71b2-135">Testa därefter lösenordsåterställningen för kontot Användare 3.</span><span class="sxs-lookup"><span data-stu-id="b71b2-135">Next, you test password reset for the User 3 account.</span></span>

1. <span data-ttu-id="b71b2-136">Öppna en ny privat webbläsarinstans och gå till [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span><span class="sxs-lookup"><span data-stu-id="b71b2-136">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
2. <span data-ttu-id="b71b2-137">Logga in med inloggningsuppgifterna för Användare 3-kontot.</span><span class="sxs-lookup"><span data-stu-id="b71b2-137">Sign in with the User 3 account credentials.</span></span>
3. <span data-ttu-id="b71b2-138">I **Mer information krävs** klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="b71b2-138">In **More information required**, click **Next**.</span></span> 
5. <span data-ttu-id="b71b2-139">I **Förlora aldrig åtkomsten till ditt konto** anger du ditt mobiltelefonnummer för telefonnummer för autentisering och ditt e-postkonto för arbetet eller ditt personliga e-postkonto för e-postmeddelande för autentisering.</span><span class="sxs-lookup"><span data-stu-id="b71b2-139">In **Don’t lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
7. <span data-ttu-id="b71b2-140">När båda har verifierats klickar du på **Ser bra ut** och stänger den privata instansen av webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="b71b2-140">After both are verified, click **Looks good** and close the private instance of the browser.</span></span>
8. <span data-ttu-id="b71b2-141">Öppna en ny privat webbläsarinstans och gå till [https://aka.ms/sspr](https://aka.ms/sspr).</span><span class="sxs-lookup"><span data-stu-id="b71b2-141">Open a new private browser instance and go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
9. <span data-ttu-id="b71b2-142">Skriv in Användare 3-kontonamnet, skriv tecknen som finns i CAPTCHA och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="b71b2-142">Type the User 3 account name, type the characters from the CAPTCHA, and then click **Next**.</span></span>
10. <span data-ttu-id="b71b2-143">För **verifieringssteg 1** klickar du på **Skicka e-post till min alternativa e-postadress** och sedan på **E-post**.</span><span class="sxs-lookup"><span data-stu-id="b71b2-143">For **verification step 1**, click **Email my alternate email**, and then click **Email**.</span></span> <span data-ttu-id="b71b2-144">När du får e-postmeddelandet skriver du verifieringskoden och klickar sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="b71b2-144">When you receive the email, type the verification code, and then click **Next**.</span></span>
11. <span data-ttu-id="b71b2-145">I **Få tillgång till kontot igen** skriver du ett nytt lösenord för Användare 3-kontot och klickar på **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="b71b2-145">In **Get back into your account**, type a new password for the User 3 account, and then click **Finish**.</span></span> <span data-ttu-id="b71b2-146">Notera det ändrade lösenordet för kontot Användare 3 och förvara det på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="b71b2-146">Note the changed password of the User 3 account and store it in a safe location.</span></span>
12. <span data-ttu-id="b71b2-147">Gå till [https://portal.office.com](https://portal.office.com) på en separat flik i samma webbläsare och logga sedan in med kontonamnet Användare 3 och det nya lösenordet.</span><span class="sxs-lookup"><span data-stu-id="b71b2-147">In a separate tab of the same browser, go to [https://portal.office.com](https://portal.office.com), and then sign in with the User 3 account name and its new password.</span></span> <span data-ttu-id="b71b2-148">Du bör se **startsidan för Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="b71b2-148">You should see the **Microsoft Office Home** page.</span></span>

<span data-ttu-id="b71b2-149">I steget [Enklare återställning av lösenord](identity-secure-your-passwords.md#identity-pw-reset) i Identitet-fasen finns mer information om och länkar till hur du konfigurerar återställning av lösenord i produktion.</span><span class="sxs-lookup"><span data-stu-id="b71b2-149">See the [Simplify password resets](identity-secure-your-passwords.md#identity-pw-reset) step in the Identity phase for information and links to configure password resets in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="b71b2-150">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="b71b2-150">Next step</span></span>

<span data-ttu-id="b71b2-151">Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="b71b2-151">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="b71b2-152">Se även</span><span class="sxs-lookup"><span data-stu-id="b71b2-152">See also</span></span>

[<span data-ttu-id="b71b2-153">Testlabbguider för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b71b2-153">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="b71b2-154">Distribuera Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b71b2-154">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="b71b2-155">Microsoft 365 Enterprise-dokumentation</span><span class="sxs-lookup"><span data-stu-id="b71b2-155">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
