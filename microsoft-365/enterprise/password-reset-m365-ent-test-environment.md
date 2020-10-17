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
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Sammanfattning: Konfigurera och testa återställning av lösenord i testmiljön för Microsoft 365.'
ms.openlocfilehash: 5d98dcc50f16bc08da787a928beeeacf825201c9
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487430"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="067af-103">Återställning av lösenord i testmiljön för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="067af-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="067af-104">*Den här test laboratorie guiden kan endast användas för test miljöer med Microsoft 365 för företags nätverk.*</span><span class="sxs-lookup"><span data-stu-id="067af-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="067af-105">Med självbetjäningen för återställning av lösenord (SSPR) i Azure Active Directory (Azure AD) kan användarna återställa eller låsa upp sina lösenord eller konton.</span><span class="sxs-lookup"><span data-stu-id="067af-105">Azure Active Directory (Azure AD) self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span>

<span data-ttu-id="067af-106">I den här artikeln beskrivs hur du konfigurerar och testar återställning av lösen ord i Microsoft 365 test miljö.</span><span class="sxs-lookup"><span data-stu-id="067af-106">This article describes how to configure and test password resets in your Microsoft 365 test environment.</span></span>

<span data-ttu-id="067af-107">Att konfigurera SSPR inbegriper tre faser:</span><span class="sxs-lookup"><span data-stu-id="067af-107">Setting up SSPR involves three phases:</span></span>
- [<span data-ttu-id="067af-108">Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön</span><span class="sxs-lookup"><span data-stu-id="067af-108">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="067af-109">Fas 2: Aktivera tillbakaskrivning av lösenord</span><span class="sxs-lookup"><span data-stu-id="067af-109">Phase 2: Enable password writeback</span></span>](#phase-2-enable-password-writeback)
- [<span data-ttu-id="067af-110">Steg 3: Konfigurera och testa återställning av lösenord</span><span class="sxs-lookup"><span data-stu-id="067af-110">Phase 3: Configure and test password reset</span></span>](#phase-3-configure-and-test-password-reset)
    
![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="067af-112">Om du vill visa en visuell karta till alla artiklar i gruppen Microsoft 365 för Enterprise-testlabbet går du till [Microsoft 365 för Enterprise Test Lab-guide](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="067af-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="067af-113">Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön</span><span class="sxs-lookup"><span data-stu-id="067af-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="067af-114">Följ först anvisningarna i [Synkronisering av lösenordshash](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="067af-114">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span> 

<span data-ttu-id="067af-115">Den resulterande konfigurationen ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="067af-115">Your resulting configuration looks like this:</span></span>
  
![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="067af-117">Konfigurationen består av:</span><span class="sxs-lookup"><span data-stu-id="067af-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="067af-118">En utvärderingsprenumeration eller betald prenumeration på Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="067af-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="067af-119">En förenklad organisations intranät som är ansluten till Internet, bestående av de virtuella datorerna DC1, APP1 och KLIENT1 i ett undernät för ett Azure Virtual Network.</span><span class="sxs-lookup"><span data-stu-id="067af-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="067af-120">Azure AD Connect körs på APP1 så att TESTLAB AD DS-domänen (Active Directory Domain Services) synkroniseras med Azure AD-klientorganisationen för dina Microsoft 365-prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="067af-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback"></a><span data-ttu-id="067af-121">Fas 2: Aktivera tillbakaskrivning av lösenord</span><span class="sxs-lookup"><span data-stu-id="067af-121">Phase 2: Enable password writeback</span></span>

<span data-ttu-id="067af-122">Följ anvisningarna i [fas 2 i testlabbguiden för tillbakaskrivning av lösenord](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="067af-122">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

<span data-ttu-id="067af-123">Du måste aktivera tillbakaskrivning av lösenord för att kunna använda återställning av lösenord.</span><span class="sxs-lookup"><span data-stu-id="067af-123">You must have password writeback enabled to use password reset.</span></span>
  
## <a name="phase-3-configure-and-test-password-reset"></a><span data-ttu-id="067af-124">Steg 3: Konfigurera och testa återställning av lösenord</span><span class="sxs-lookup"><span data-stu-id="067af-124">Phase 3: Configure and test password reset</span></span>

<span data-ttu-id="067af-125">I den här fasen konfigurerar du återställning av lösen ord i Azure AD-klient organisationen via grupp medlemskap och kontrollerar sedan att det fungerar.</span><span class="sxs-lookup"><span data-stu-id="067af-125">In this phase, configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="067af-126">Börja med att aktivera återställning av lösenord för kontona i en specifik Azure AD-grupp.</span><span class="sxs-lookup"><span data-stu-id="067af-126">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="067af-127">Öppna [https://portal.azure.com](https://portal.azure.com) i en privat instans av webbläsaren och logga sedan in med inloggningsuppgifterna för ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="067af-127">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="067af-128">I Azure-portalen väljer du ny grupp för **Azure Active Directory**-  >  **grupper**  >  **New group**.</span><span class="sxs-lookup"><span data-stu-id="067af-128">In the Azure portal, select **Azure Active Directory** > **Groups** > **New group**.</span></span>
3. <span data-ttu-id="067af-129">Ange **Grupptyp** som **Säkerhet**, **Gruppnamn** som **PWReset** och **Typ av medlemskap** som **Tilldelad**.</span><span class="sxs-lookup"><span data-stu-id="067af-129">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**.</span></span>
4. <span data-ttu-id="067af-130">Välj **medlemmar**, Sök och välj **användare 3**, Välj **Välj**och sedan **skapa**.</span><span class="sxs-lookup"><span data-stu-id="067af-130">Select **Members**, find and select **User 3**, select **Select**, and then select **Create**.</span></span>
5. <span data-ttu-id="067af-131">Stäng fönstret **Grupper**.</span><span class="sxs-lookup"><span data-stu-id="067af-131">Close the **Groups** pane.</span></span>
6. <span data-ttu-id="067af-132">I fönstret Azure Active Directory väljer du **Återställ lösen ord** i det vänstra navigerings fältet.</span><span class="sxs-lookup"><span data-stu-id="067af-132">In the Azure Active Directory pane, select **Password reset** in the left navigation.</span></span>
7. <span data-ttu-id="067af-133">I fönstret **Egenskaper för återställning av lösenord**, under alternativet **Återställning av lösenord via självbetjäning har aktiverats**, väljer du **Vald**.</span><span class="sxs-lookup"><span data-stu-id="067af-133">In the **Password reset-Properties** pane, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
8. <span data-ttu-id="067af-134">Välj **Välj grupp**, Markera gruppen **PWReset** och välj sedan **Välj**  >  **Spara**.</span><span class="sxs-lookup"><span data-stu-id="067af-134">Select **Select group**, select the **PWReset** group, and then select **Select** > **Save**.</span></span>
9. <span data-ttu-id="067af-135">Stäng den privata webbläsarinstansen.</span><span class="sxs-lookup"><span data-stu-id="067af-135">Close the private browser instance.</span></span>

<span data-ttu-id="067af-136">Testa sedan lösen ords återställning för användare 3-kontot.</span><span class="sxs-lookup"><span data-stu-id="067af-136">Next, test password reset for the User 3 account.</span></span>

1. <span data-ttu-id="067af-137">Öppna en ny privat webbläsarinstans och gå till [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span><span class="sxs-lookup"><span data-stu-id="067af-137">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
1. <span data-ttu-id="067af-138">Logga in med inloggningsuppgifterna för Användare 3-kontot.</span><span class="sxs-lookup"><span data-stu-id="067af-138">Sign in with the User 3 account credentials.</span></span>
1. <span data-ttu-id="067af-139">Välj **Nästa**om du vill **ha mer information**.</span><span class="sxs-lookup"><span data-stu-id="067af-139">In **More information required**, select **Next**.</span></span> 
1. <span data-ttu-id="067af-140">I **Förlora aldrig åtkomsten till ditt konto** anger du ditt mobiltelefonnummer som telefonnummer för autentisering och ditt e-postkonto på jobbet eller ditt privata e-postkonto som e-postmeddelande för autentisering.</span><span class="sxs-lookup"><span data-stu-id="067af-140">In **Don't lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
1. <span data-ttu-id="067af-141">När båda har verifierats väljer du **ser bra ut**och stänger sedan den privata instansen av webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="067af-141">After both are verified, select **Looks good**, and then close the private instance of the browser.</span></span>
1. <span data-ttu-id="067af-142">Gå till i en ny privat webb läsar instans [https://aka.ms/sspr](https://aka.ms/sspr) .</span><span class="sxs-lookup"><span data-stu-id="067af-142">In a new private browser instance, go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
1. <span data-ttu-id="067af-143">Ange användare 3-konto namnet, ange tecknen från CAPTCHA och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="067af-143">Enter the User 3 account name, enter the characters from the CAPTCHA, and then select **Next**.</span></span>
1. <span data-ttu-id="067af-144">För **verifiering steg 1**väljer du **e-post för min alternativa e-post**och väljer sedan **e-post**.</span><span class="sxs-lookup"><span data-stu-id="067af-144">For **verification step 1**, select **Email my alternate email**, and then select **Email**.</span></span> <span data-ttu-id="067af-145">Ange verifierings koden när du får e-postmeddelandet och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="067af-145">When you receive the email, enter the verification code, and then select **Next**.</span></span>
1. <span data-ttu-id="067af-146">Gå in på **ditt konto**och ange ett nytt lösen ord för kontot för användare 3 och välj sedan **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="067af-146">In **Get back into your account**, enter a new password for the User 3 account, and then select **Finish**.</span></span> <span data-ttu-id="067af-147">Notera det ändrade lösenordet för kontot Användare 3 och förvara det på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="067af-147">Note the changed password of the User 3 account and store it in a safe location.</span></span>
1. <span data-ttu-id="067af-148">Gå till [https://portal.office.com](https://portal.office.com) på en separat flik i samma webbläsare och logga sedan in med kontonamnet Användare 3 och det nya lösenordet.</span><span class="sxs-lookup"><span data-stu-id="067af-148">In a separate tab of the same browser, go to [https://portal.office.com](https://portal.office.com), and then sign in with the User 3 account name and its new password.</span></span> <span data-ttu-id="067af-149">Du bör se **startsidan för Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="067af-149">You should see the **Microsoft Office Home** page.</span></span>

## <a name="next-step"></a><span data-ttu-id="067af-150">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="067af-150">Next step</span></span>

<span data-ttu-id="067af-151">Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="067af-151">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="067af-152">Se även</span><span class="sxs-lookup"><span data-stu-id="067af-152">See also</span></span>

[<span data-ttu-id="067af-153">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="067af-153">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="067af-154">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="067af-154">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="067af-155">Microsoft 365 för företags dokumentation</span><span class="sxs-lookup"><span data-stu-id="067af-155">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
