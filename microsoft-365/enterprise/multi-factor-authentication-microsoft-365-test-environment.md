---
title: Multifaktorautentisering för testmiljön för Microsoft 365 Enterprise
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Konfigurera multifaktorautentisering med textmeddelanden som skickas till en smart telefon i testmiljön för Microsoft 365 Enterprise.
ms.openlocfilehash: ae8cab25a20cc75992eecc600219d9f1dd869b63
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213146"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="34cb4-103">Multifaktorautentisering för testmiljön för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="34cb4-103">Multi-factor authentication for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="34cb4-104">*Den här testlabbguiden kan användas i både Microsoft 365 Enterprise- och Office 365 Enterprise-testmiljöer.*</span><span class="sxs-lookup"><span data-stu-id="34cb4-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="34cb4-105">Om du vill ha ytterligare en säkerhetsnivå för att logga in på Microsoft 365 eller någon tjänst eller program som använder Azure AD-klienten för din prenumeration kan du aktivera Azure multifaktorautentisering, vilket kräver mer än bara ett användarnamn och lösenord för att verifiera ett konto.</span><span class="sxs-lookup"><span data-stu-id="34cb4-105">For an additional level of security for signing in to Microsoft 365 or any service or application that uses the Azure AD tenant for your subscription, you can enable Azure multi-factor authentication, which requires more than just a username and password to verify an account.</span></span> 

<span data-ttu-id="34cb4-106">Med multifaktorautentisering måste användarna bekräfta ett telefonsamtal, skriva en verifieringskod som skickas i ett textmeddelande eller verifiera autentiseringen med en app på sina smarta telefoner när de har angett sina lösenord korrekt.</span><span class="sxs-lookup"><span data-stu-id="34cb4-106">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or verify the authentication with an app on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="34cb4-107">De kan logga in först när den här andra autentiseringsfaktorn har uppfyllts.</span><span class="sxs-lookup"><span data-stu-id="34cb4-107">They can sign in only after this second authentication factor has been satisfied.</span></span> 
  
<span data-ttu-id="34cb4-108">I den här artikeln beskrivs hur du aktiverar och testar textmeddelandebaserad autentisering för ett visst användarkonto.</span><span class="sxs-lookup"><span data-stu-id="34cb4-108">This article describes how to enable and test text message-based authentication for a specific user account.</span></span>
  
<span data-ttu-id="34cb4-109">Det finns två faser för att konfigurera multifaktorautentisering för ett konto i microsoft 365 Enterprise-testmiljön:</span><span class="sxs-lookup"><span data-stu-id="34cb4-109">There are two phases to setting up multi-factor authentication for an account in your Microsoft 365 Enterprise test environment:</span></span>
  
1. <span data-ttu-id="34cb4-110">Skapa testmiljön för Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="34cb4-110">Create the Microsoft 365 Enterprise test environment.</span></span>
    
2. <span data-ttu-id="34cb4-111">Aktivera och testa multifaktorautentisering för user 2-kontot.</span><span class="sxs-lookup"><span data-stu-id="34cb4-111">Enable and test multi-factor authentication for the User 2 account.</span></span>

3. <span data-ttu-id="34cb4-112">Aktivera och testa multifaktorautentisering med en princip för villkorlig åtkomst (valfritt).</span><span class="sxs-lookup"><span data-stu-id="34cb4-112">Enable and test multi-factor authentication with a conditional access policy (optional).</span></span>

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="34cb4-114">Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med Microsoft 365 Enterprise-testlabbguider.</span><span class="sxs-lookup"><span data-stu-id="34cb4-114">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="34cb4-115">Fas 1: Bygga ut testmiljön i Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="34cb4-115">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="34cb4-116">Om du bara vill testa multifaktorautentisering på ett lätt väg med minimikraven följer du instruktionerna i [Lightweight base-konfigurationen](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="34cb4-116">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="34cb4-117">Om du vill testa multifaktorautentisering i ett simulerat företag följer du instruktionerna i [Direktautentisering](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="34cb4-117">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="34cb4-118">Testning av multifaktorautentisering kräver inte den simulerade företagstestmiljön, som innehåller ett simulerat intranät som är anslutet till Internet och katalogsynkronisering för en AD DS-skog (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="34cb4-118">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="34cb4-119">Det finns här som ett alternativ så att du kan testa multifaktorautentisering och experimentera med den i en miljö som representerar en typisk organisation.</span><span class="sxs-lookup"><span data-stu-id="34cb4-119">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="34cb4-120">Fas 2: Aktivera och testa multifaktorautentisering för user 2-kontot</span><span class="sxs-lookup"><span data-stu-id="34cb4-120">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="34cb4-121">Aktivera multifaktorautentisering för User 2-kontot med följande steg:</span><span class="sxs-lookup"><span data-stu-id="34cb4-121">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="34cb4-122">Öppna en separat, privat instans av webbläsaren, gå till Microsoft 365 admin center ( [https://portal.microsoft.com](https://portal.microsoft.com) ) och logga sedan in med ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="34cb4-122">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="34cb4-123">Klicka på **Användare > Aktiva användare** i det vänstra navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="34cb4-123">In the left navigation, click **Users > Active users**.</span></span>
    
3. <span data-ttu-id="34cb4-124">Klicka på **Multifaktorautentisering**i fönstret Aktiva användare .</span><span class="sxs-lookup"><span data-stu-id="34cb4-124">In the Active users pane, click **Multi-factor authentication**.</span></span>
    
4. <span data-ttu-id="34cb4-125">Välj kontot Användare **2** i listan.</span><span class="sxs-lookup"><span data-stu-id="34cb4-125">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="34cb4-126">Klicka på **Aktivera**under **Snabbsteg**i avsnittet **Användare 2.**</span><span class="sxs-lookup"><span data-stu-id="34cb4-126">In the **User 2** section, under **Quick steps**, click **Enable**.</span></span>
    
6. <span data-ttu-id="34cb4-127">Klicka på **Aktivera autentisering**med flera faktorer i dialogrutan **Om att aktivera autentisering med flera faktorer.**</span><span class="sxs-lookup"><span data-stu-id="34cb4-127">In the **About enabling multi-factor auth** dialog box, click **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="34cb4-128">Klicka på **Stäng**i dialogrutan **Uppdateringar.**</span><span class="sxs-lookup"><span data-stu-id="34cb4-128">In the **Updates successful** dialog box, click **Close**.</span></span>
    
8. <span data-ttu-id="34cb4-129">Klicka på ikonen för användarkontot längst upp till höger på fliken **Administrationscenter för Microsoft 365** och klicka sedan på **Logga ut**.</span><span class="sxs-lookup"><span data-stu-id="34cb4-129">On the **Microsoft 365 admin center** tab, click the user account icon in the upper right, and then click **Sign out**.</span></span>
    
9. <span data-ttu-id="34cb4-130">Stäng webbläsarinstansen.</span><span class="sxs-lookup"><span data-stu-id="34cb4-130">Close your browser instance.</span></span>
   
<span data-ttu-id="34cb4-131">Slutför konfigurationen för user 2-kontot för att använda ett textmeddelande för validering och testa det med följande steg:</span><span class="sxs-lookup"><span data-stu-id="34cb4-131">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="34cb4-132">Öppna en ny, privat instans av din webbläsare.</span><span class="sxs-lookup"><span data-stu-id="34cb4-132">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="34cb4-133">Gå till Office 365-portalen ( [https://portal.office.com](https://portal.office.com) ) och logga in med användaren 2-kontonamnet och lösenordet.</span><span class="sxs-lookup"><span data-stu-id="34cb4-133">Go to the Office 365 portal ([https://portal.office.com](https://portal.office.com)) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="34cb4-134">När du har loggat in uppmanas du att konfigurera kontot för mer information.</span><span class="sxs-lookup"><span data-stu-id="34cb4-134">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="34cb4-135">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="34cb4-135">Click **Next**.</span></span>
    
4. <span data-ttu-id="34cb4-136">På sidan **Ytterligare säkerhetsverifiering:**</span><span class="sxs-lookup"><span data-stu-id="34cb4-136">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="34cb4-137">Välj land eller region.</span><span class="sxs-lookup"><span data-stu-id="34cb4-137">Select your country or region.</span></span>
    
   - <span data-ttu-id="34cb4-138">Skriv telefonnumret till den smarta telefon som tar emot textmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="34cb4-138">Type phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="34cb4-139">I **Metod**klickar du på **Skicka mig en kod via sms**.</span><span class="sxs-lookup"><span data-stu-id="34cb4-139">In **Method**, click **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="34cb4-140">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="34cb4-140">Click **Next**.</span></span>
    
6. <span data-ttu-id="34cb4-141">Ange verifieringskoden från det mottagna sms:et på den smarta telefonen och klicka sedan på **Verifiera**.</span><span class="sxs-lookup"><span data-stu-id="34cb4-141">Enter the verification code from the text message received on your smart phone, and then click **Verify**.</span></span>
    
7. <span data-ttu-id="34cb4-142">På **steg 3: Behåll din befintliga programsida** klickar du på **Klar.**</span><span class="sxs-lookup"><span data-stu-id="34cb4-142">On the **Step 3: Keep your existing applications** page, click **Done**.</span></span>
    
8. <span data-ttu-id="34cb4-143">Om det är första gången du loggade in med kontot Användare 2 uppmanas du att ändra lösenordet.</span><span class="sxs-lookup"><span data-stu-id="34cb4-143">If this is the first time you signed in with the User 2 account, you are prompted to change the password.</span></span> <span data-ttu-id="34cb4-144">Skriv det ursprungliga lösenordet och ett nytt lösenord två gånger och klicka sedan på **Uppdatera lösenord och logga in**.</span><span class="sxs-lookup"><span data-stu-id="34cb4-144">Type the original password and a new password twice, and then click **Update password and sign in**.</span></span> <span data-ttu-id="34cb4-145">Registrera det nya lösenordet på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="34cb4-145">Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="34cb4-146">Du bör se Office-portalen för användare 2 på fliken **Microsoft Office Home** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="34cb4-146">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a><span data-ttu-id="34cb4-147">Fas 3: Aktivera och testa multifaktorautentisering med en princip för villkorlig åtkomst</span><span class="sxs-lookup"><span data-stu-id="34cb4-147">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>

<span data-ttu-id="34cb4-148">*Den här fasen kan bara användas för en Microsoft 365 Enterprise-testmiljö.*</span><span class="sxs-lookup"><span data-stu-id="34cb4-148">*This phase can only be used for a Microsoft 365 Enterprise test environment.*</span></span>

<span data-ttu-id="34cb4-149">I den här fasen aktiverar du multifaktorautentisering för User 3-kontot med hjälp av en grupp och en princip för villkorlig åtkomst.</span><span class="sxs-lookup"><span data-stu-id="34cb4-149">In this phase you enable multi-factor authentication for the User 3 account using a group and a conditional access policy.</span></span>

<span data-ttu-id="34cb4-150">Skapa sedan en ny grupp med namnet MFAUsers och lägg till kontot användare 3 i den.</span><span class="sxs-lookup"><span data-stu-id="34cb4-150">Next, create a new group named MFAUsers and add the User 3 account to it.</span></span>

1. <span data-ttu-id="34cb4-151">Klicka på **Grupper** i den vänstra navigeringen på fliken **Administrationscenter i Microsoft 365** och klicka sedan på **Grupper**.</span><span class="sxs-lookup"><span data-stu-id="34cb4-151">On the **Microsoft 365 admin center** tab, click **Groups** in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="34cb4-152">Klicka på **Lägg till en grupp**.</span><span class="sxs-lookup"><span data-stu-id="34cb4-152">Click **Add a group**.</span></span>
3. <span data-ttu-id="34cb4-153">I fönstret **Välj grupptyp** väljer du **Säkerhet**och klickar sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="34cb4-153">In the **Choose a group type** pane, select **Security**, and then click **Next**.</span></span>
4. <span data-ttu-id="34cb4-154">Klicka på **Skapa grupp**i fönstret **Konfigurera grunderna** och klicka sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="34cb4-154">In the **Set up the basics** pane, click **Create group**, and then click **Close**.</span></span>
5. <span data-ttu-id="34cb4-155">Skriv **MFAUsers**i **gruppfönstret Granska och avsluta** och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="34cb4-155">In the **Review and finish adding group** pane, type **MFAUsers**, and then click **Next**.</span></span>
6. <span data-ttu-id="34cb4-156">Klicka på gruppen **MFAUsers** i listan över grupper.</span><span class="sxs-lookup"><span data-stu-id="34cb4-156">In the list of groups, click the **MFAUsers** group.</span></span>
7. <span data-ttu-id="34cb4-157">Klicka på **Medlemmar**i fönstret **MFAUsers** och klicka sedan på **Visa alla och hantera medlemmar**.</span><span class="sxs-lookup"><span data-stu-id="34cb4-157">In the **MFAUsers** pane, click **Members**, and then click **View all and manage members**.</span></span>
8. <span data-ttu-id="34cb4-158">Klicka på **Lägg till medlemmar**i fönstret **MFAUsers,** välj **kontot Användare 3** och klicka sedan på **Spara > Stäng > Stäng**.</span><span class="sxs-lookup"><span data-stu-id="34cb4-158">In the **MFAUsers** pane, click **Add members**, select the **User 3** account, and then click **Save > Close > Close**.</span></span>

<span data-ttu-id="34cb4-159">Skapa sedan en princip för villkorlig åtkomst för att kräva multifaktorautentisering för medlemmar i MFAUsers-gruppen.</span><span class="sxs-lookup"><span data-stu-id="34cb4-159">Next, create a conditional access policy to require multifactor authentication for members of the MFAUsers group.</span></span>

1. <span data-ttu-id="34cb4-160">Gå till [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="34cb4-160">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="34cb4-161">Klicka på **Azure Active Directory > Security > Conditional Access**.</span><span class="sxs-lookup"><span data-stu-id="34cb4-161">Click **Azure Active Directory > Security > Conditional Access**.</span></span>
3. <span data-ttu-id="34cb4-162">Klicka på **Ny princip**i fönstret Villkorlig åtkomst **– Principer** .</span><span class="sxs-lookup"><span data-stu-id="34cb4-162">In the **Conditional access – Policies** pane, click **New policy**.</span></span>
4. <span data-ttu-id="34cb4-163">Skriv **MFA för användarkonton** i **Namn**i fönstret **Nytt** .</span><span class="sxs-lookup"><span data-stu-id="34cb4-163">In the **New** pane, type **MFA for user accounts** in **Name**.</span></span>
5. <span data-ttu-id="34cb4-164">Klicka på **Användare och grupper**i avsnittet **Tilldelningar** .</span><span class="sxs-lookup"><span data-stu-id="34cb4-164">In the **Assignments** section, click **Users and groups**.</span></span>
6. <span data-ttu-id="34cb4-165">Klicka på Markera användare och grupper **> användare och grupper > Markera**på fliken **Inkludera** i fönstret Användare och **grupper.**</span><span class="sxs-lookup"><span data-stu-id="34cb4-165">On the **Include** tab of the **Users and groups** pane, click **Select users and groups > Users and groups > Select**.</span></span>
7. <span data-ttu-id="34cb4-166">Klicka på gruppen **MFAUsers** i fönstret **Välj** och klicka sedan på **Markera > klar**.</span><span class="sxs-lookup"><span data-stu-id="34cb4-166">In the **Select** pane, click the **MFAUsers** group, and then click **Select > Done**.</span></span>
8. <span data-ttu-id="34cb4-167">Klicka på **Bevilja**i avsnittet **Access-kontroller** i fönstret **Nytt** .</span><span class="sxs-lookup"><span data-stu-id="34cb4-167">In the **Access controls** section of the **New** pane, click **Grant**.</span></span>
9. <span data-ttu-id="34cb4-168">Klicka på **Kräv multifaktorautentisering**i **fönstret Bevilja** och klicka sedan på **Markera**.</span><span class="sxs-lookup"><span data-stu-id="34cb4-168">In the **Grant** pane, click **Require multi-factor authentication**, and then click **Select**.</span></span>
10. <span data-ttu-id="34cb4-169">Klicka på **På** för **att aktivera principen**i fönstret **Nytt** och klicka sedan på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="34cb4-169">In the **New** pane, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="34cb4-170">Stäng flikarna **i Azure-portalen** och **Microsoft 365 admin center.**</span><span class="sxs-lookup"><span data-stu-id="34cb4-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="34cb4-171">Om du vill testa den här principen loggar du ut och loggar in med kontot Användare 3.</span><span class="sxs-lookup"><span data-stu-id="34cb4-171">To test this policy, sign out and sign in with the User 3 account.</span></span> <span data-ttu-id="34cb4-172">Du bör uppmanas att konfigurera MFA.</span><span class="sxs-lookup"><span data-stu-id="34cb4-172">You should be prompted to configure MFA.</span></span> <span data-ttu-id="34cb4-173">Detta visar att principen MFAUsers tillämpas.</span><span class="sxs-lookup"><span data-stu-id="34cb4-173">This demonstrates that the MFAUsers policy is being applied.</span></span>

<span data-ttu-id="34cb4-174">Se steget [Konfigurera multifaktorautentisering](identity-secure-user-sign-ins.md#identity-mfa) i identitetsfasen för information och länkar för att distribuera multifaktorautentisering i produktion.</span><span class="sxs-lookup"><span data-stu-id="34cb4-174">See the [Set up multi-factor authentication](identity-secure-user-sign-ins.md#identity-mfa) step in the Identity phase for information and links to deploy multi-factor authentication in production.</span></span>
    
## <a name="next-step"></a><span data-ttu-id="34cb4-175">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="34cb4-175">Next step</span></span>

<span data-ttu-id="34cb4-176">Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="34cb4-176">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="34cb4-177">Se även</span><span class="sxs-lookup"><span data-stu-id="34cb4-177">See also</span></span>

[<span data-ttu-id="34cb4-178">Fas 2: Identitet</span><span class="sxs-lookup"><span data-stu-id="34cb4-178">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="34cb4-179">Testlabbguider för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="34cb4-179">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="34cb4-180">Distribution av Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="34cb4-180">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="34cb4-181">Microsoft 365 Enterprise-dokumentation</span><span class="sxs-lookup"><span data-stu-id="34cb4-181">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
