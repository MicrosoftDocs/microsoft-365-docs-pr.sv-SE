---
title: Microsoft 365 för företagstestmiljö multifaktorautentisering
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
- seo-marvel-apr2020
description: Konfigurera multifaktorautentisering med sms som skickas till en smartphone i Microsoft 365 för företagstestmiljö.
ms.openlocfilehash: aeb8940a9499909b8c568d1230f9aa45aee07b3d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923762"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="250d0-103">Multifaktorautentisering för din Microsoft 365 för företagstestmiljö</span><span class="sxs-lookup"><span data-stu-id="250d0-103">Multi-factor authentication for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="250d0-104">*Den här testlabbguiden kan användas för både Microsoft 365 för företag Office 365 Enterprise för testmiljöer.*</span><span class="sxs-lookup"><span data-stu-id="250d0-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="250d0-105">Om du vill ha ytterligare en säkerhetsnivå för att logga in på Microsoft 365 eller någon tjänst eller ett program som använder Azure AD-klientorganisationen för prenumerationen kan du aktivera multifaktorautentisering i Azure AD, vilket kräver mer än bara ett användarnamn och lösenord för att verifiera ett konto.</span><span class="sxs-lookup"><span data-stu-id="250d0-105">For an additional level of security for signing in to Microsoft 365 or any service or application that uses the Azure AD tenant for your subscription, you can enable Azure AD multi-factor authentication, which requires more than just a username and password to verify an account.</span></span>

<span data-ttu-id="250d0-106">Med multifaktorautentisering måste användarna bekräfta ett telefonsamtal, skriva en verifieringskod som skickats i ett sms eller verifiera autentiseringen med en app på sina smartphones när de har skrivit in sina lösenord korrekt.</span><span class="sxs-lookup"><span data-stu-id="250d0-106">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or verify the authentication with an app on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="250d0-107">De kan bara logga in efter att den här andra autentiseringsfaktorn är nöjd.</span><span class="sxs-lookup"><span data-stu-id="250d0-107">They can sign in only after this second authentication factor is satisfied.</span></span>
  
<span data-ttu-id="250d0-108">I den här artikeln beskrivs hur du aktiverar och testar textmeddelandebaserad autentisering för ett visst användarkonto.</span><span class="sxs-lookup"><span data-stu-id="250d0-108">This article describes how to enable and test text message-based authentication for a specific user account.</span></span>
  
<span data-ttu-id="250d0-109">Att konfigurera multifaktorautentisering för ett konto i Microsoft 365 för företagstestmiljö omfattar två faser och en tredje valfri fas:</span><span class="sxs-lookup"><span data-stu-id="250d0-109">Setting up multi-factor authentication for an account in your Microsoft 365 for enterprise test environment involves two phases and a third optional phase:</span></span>
- [<span data-ttu-id="250d0-110">Fas 1: Bygg ut din Microsoft 365 för företagstestmiljö</span><span class="sxs-lookup"><span data-stu-id="250d0-110">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="250d0-111">Fas 2: Aktivera och testa multifaktorautentisering för Användarkontot 2</span><span class="sxs-lookup"><span data-stu-id="250d0-111">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [<span data-ttu-id="250d0-112">Fas 3: Aktivera och testa multifaktorautentisering med en princip för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="250d0-112">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="250d0-114">En visuell karta till alla artiklar i Microsoft 365 för företags testlabbguide stack finns i [Microsoft 365 för företags testlabbguide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="250d0-114">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="250d0-115">Fas 1: Bygg ut din Microsoft 365 för företagstestmiljö</span><span class="sxs-lookup"><span data-stu-id="250d0-115">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="250d0-116">Om du bara vill testa multifaktorautentisering på ett lätt sätt med minimikraven följer du anvisningarna i [Enkel baskonfiguration.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="250d0-116">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="250d0-117">Om du vill testa multifaktorautentisering i ett simulerat företag följer du anvisningarna i [Direktautentisering](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="250d0-117">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="250d0-118">Om du testar multifaktorautentisering krävs inte den simulerade företagstestmiljön, som omfattar ett simulerat intranät som är anslutet till Internet och katalogsynkronisering för en AD DS-skog (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="250d0-118">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="250d0-119">Den finns här som ett alternativ så att du kan testa multifaktorautentisering och experimentera med den i en miljö som representerar en vanlig organisation.</span><span class="sxs-lookup"><span data-stu-id="250d0-119">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="250d0-120">Fas 2: Aktivera och testa multifaktorautentisering för Användarkontot 2</span><span class="sxs-lookup"><span data-stu-id="250d0-120">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="250d0-121">Aktivera multifaktorautentisering för User 2-kontot genom att följa de här stegen:</span><span class="sxs-lookup"><span data-stu-id="250d0-121">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="250d0-122">Öppna en separat, privat instans av webbläsaren, gå Microsoft 365 ( ) [https://portal.microsoft.com](https://portal.microsoft.com) och logga sedan in med ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="250d0-122">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="250d0-123">Välj Användare aktiva användare i det  >  **vänstra navigeringsfältet.**</span><span class="sxs-lookup"><span data-stu-id="250d0-123">In the left navigation, select **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="250d0-124">Välj Multifaktorautentisering i **fönstret Aktiva användare.**</span><span class="sxs-lookup"><span data-stu-id="250d0-124">In the Active users pane, select **Multi-factor authentication**.</span></span>
    
4. <span data-ttu-id="250d0-125">Välj Användarkontot användare **2 i** listan.</span><span class="sxs-lookup"><span data-stu-id="250d0-125">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="250d0-126">I avsnittet **Användare 2,** under **Snabbsteg,** väljer du **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="250d0-126">In the **User 2** section, under **Quick steps**, select **Enable**.</span></span>
    
6. <span data-ttu-id="250d0-127">I dialogrutan **Om att aktivera Multi-Factor Auth** markerar **du Aktivera Multi-Factor Auth.**</span><span class="sxs-lookup"><span data-stu-id="250d0-127">In the **About enabling multi-factor auth** dialog box, select **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="250d0-128">Välj **Stäng i** dialogrutan Uppdateringar **lyckades.**</span><span class="sxs-lookup"><span data-stu-id="250d0-128">In the **Updates successful** dialog box, select **Close**.</span></span>
    
8. <span data-ttu-id="250d0-129">På Microsoft 365 **i administrationscentret** väljer du ikonen för användarkontot längst upp till höger och väljer sedan **Logga ut**.</span><span class="sxs-lookup"><span data-stu-id="250d0-129">On the **Microsoft 365 admin center** tab, select the user account icon in the upper right, and then select **Sign out**.</span></span>
    
9. <span data-ttu-id="250d0-130">Stäng webbläsarinstansen.</span><span class="sxs-lookup"><span data-stu-id="250d0-130">Close your browser instance.</span></span>
   
<span data-ttu-id="250d0-131">Slutför konfigurationen för användarkontot för användare 2 för att använda ett textmeddelande för verifiering och testa det med följande steg:</span><span class="sxs-lookup"><span data-stu-id="250d0-131">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="250d0-132">Öppna en ny, privat instans av webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="250d0-132">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="250d0-133">Gå till [Microsoft 365 och logga](https://admin.microsoft.com) in med Användarnamn och lösenord för User 2.</span><span class="sxs-lookup"><span data-stu-id="250d0-133">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="250d0-134">När du har loggat in uppmanas du att konfigurera kontot för mer information.</span><span class="sxs-lookup"><span data-stu-id="250d0-134">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="250d0-135">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="250d0-135">Select **Next**.</span></span>
    
4. <span data-ttu-id="250d0-136">På sidan **Ytterligare säkerhetsverifiering:**</span><span class="sxs-lookup"><span data-stu-id="250d0-136">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="250d0-137">Välj land eller region.</span><span class="sxs-lookup"><span data-stu-id="250d0-137">Select your country or region.</span></span>
    
   - <span data-ttu-id="250d0-138">Ange telefonnumret för den smartphone som ska ta emot SMS.</span><span class="sxs-lookup"><span data-stu-id="250d0-138">Enter the phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="250d0-139">I **Metod** väljer du **Skicka en kod via SMS.**</span><span class="sxs-lookup"><span data-stu-id="250d0-139">In **Method**, select **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="250d0-140">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="250d0-140">Select **Next**.</span></span>
    
6. <span data-ttu-id="250d0-141">Ange verifieringskoden från sms:et du fick på din smartphone och välj sedan **Verifiera**.</span><span class="sxs-lookup"><span data-stu-id="250d0-141">Enter the verification code from the text message received on your smart phone, and then select **Verify**.</span></span>
    
7. <span data-ttu-id="250d0-142">På sidan **Steg 3: Behåll befintliga program** väljer du **Klar**.</span><span class="sxs-lookup"><span data-stu-id="250d0-142">On the **Step 3: Keep your existing applications** page, select **Done**.</span></span>
    
8. <span data-ttu-id="250d0-143">Om det är första gången du loggar in med User 2-kontot uppmanas du att ändra lösenordet.</span><span class="sxs-lookup"><span data-stu-id="250d0-143">If this is the first time you signed in with the User 2 account, you are prompted to change the password.</span></span> <span data-ttu-id="250d0-144">Ange det ursprungliga lösenordet och ett nytt lösenord två gånger och välj sedan **Uppdatera lösenord och logga in**.</span><span class="sxs-lookup"><span data-stu-id="250d0-144">Enter the original password and a new password twice, and then select **Update password and sign in**.</span></span> <span data-ttu-id="250d0-145">Registrera det nya lösenordet på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="250d0-145">Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="250d0-146">Du bör se Office för användare 2 på **Microsoft Office Start** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="250d0-146">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a><span data-ttu-id="250d0-147">Fas 3: Aktivera och testa multifaktorautentisering med en princip för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="250d0-147">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>

<span data-ttu-id="250d0-148">*Den här fasen kan endast användas för en Microsoft 365 för företagstestmiljö.*</span><span class="sxs-lookup"><span data-stu-id="250d0-148">*This phase can only be used for a Microsoft 365 for enterprise test environment.*</span></span>

<span data-ttu-id="250d0-149">I den här fasen aktiverar du multifaktorautentisering för User 3-kontot med en grupp och en princip för villkorsstyrd åtkomst.</span><span class="sxs-lookup"><span data-stu-id="250d0-149">In this phase, you enable multi-factor authentication for the User 3 account using a group and a conditional access policy.</span></span>

<span data-ttu-id="250d0-150">Skapa sedan en ny grupp med namnet MFAUsers och lägg till Användarkontot 3 i den gruppen.</span><span class="sxs-lookup"><span data-stu-id="250d0-150">Next, create a new group named MFAUsers and add the User 3 account to it.</span></span>

1. <span data-ttu-id="250d0-151">På Microsoft 365 **i administrationscentret** väljer **du Grupper i** det vänstra navigeringsfältet och sedan **Grupper.**</span><span class="sxs-lookup"><span data-stu-id="250d0-151">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="250d0-152">Välj **Lägg till en grupp**.</span><span class="sxs-lookup"><span data-stu-id="250d0-152">Select **Add a group**.</span></span>
3. <span data-ttu-id="250d0-153">I fönstret **Välj en grupptyp** väljer **du Säkerhet** och sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="250d0-153">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="250d0-154">I **fönstret Konfigurera grunderna väljer** du **Skapa grupp och** sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="250d0-154">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="250d0-155">I fönstret **Granska och slutför tillägget av** grupp anger du **MFAUsers** och väljer **sedan Nästa.**</span><span class="sxs-lookup"><span data-stu-id="250d0-155">In the **Review and finish adding group** pane, enter **MFAUsers**, and then select **Next**.</span></span>
6. <span data-ttu-id="250d0-156">Välj gruppen **MFAUsers** i listan över grupper.</span><span class="sxs-lookup"><span data-stu-id="250d0-156">In the list of groups, select the **MFAUsers** group.</span></span>
7. <span data-ttu-id="250d0-157">I fönstret **MFAUsers** väljer du **Members** och sedan **Visa alla och hanterar medlemmar.**</span><span class="sxs-lookup"><span data-stu-id="250d0-157">In the **MFAUsers** pane, select **Members**, and then select **View all and manage members**.</span></span>
8. <span data-ttu-id="250d0-158">I fönstret **MFAUsers** väljer du **Lägg till medlemmar**, väljer **Användarkontot 3** och sedan **Spara**  >  **Stäng**  >  **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="250d0-158">In the **MFAUsers** pane, select **Add members**, select the **User 3** account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="250d0-159">Skapa sedan en princip för villkorsstyrd åtkomst för att kräva multifaktorautentisering för medlemmar i gruppen MFAUsers.</span><span class="sxs-lookup"><span data-stu-id="250d0-159">Next, create a conditional access policy to require multifactor authentication for members of the MFAUsers group.</span></span>

1. <span data-ttu-id="250d0-160">På en ny flik i webbläsaren går du till [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="250d0-160">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="250d0-161">Välj Azure Active Directory   >  **villkorsstyrd**  >  **åtkomst för säkerhet.**</span><span class="sxs-lookup"><span data-stu-id="250d0-161">Select **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="250d0-162">I fönstret **Villkorsstyrd åtkomst –** Principer väljer du **Ny princip.**</span><span class="sxs-lookup"><span data-stu-id="250d0-162">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
4. <span data-ttu-id="250d0-163">I fönstret **Nytt** anger du **MFA för användarkonton** i **rutan** Namn.</span><span class="sxs-lookup"><span data-stu-id="250d0-163">In the **New** pane, enter **MFA for user accounts** in the **Name** box.</span></span>
5. <span data-ttu-id="250d0-164">I avsnittet **Uppgifter** väljer du **Användare och grupper.**</span><span class="sxs-lookup"><span data-stu-id="250d0-164">In the **Assignments** section, select **Users and groups**.</span></span>
6. <span data-ttu-id="250d0-165">På fliken **Inkludera** i fönstret **Användare och grupper väljer** du Välj användare och grupper **Användare** och  >  **grupper**  >  **Välj**.</span><span class="sxs-lookup"><span data-stu-id="250d0-165">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
7. <span data-ttu-id="250d0-166">I fönstret **Välj** väljer du gruppen **MFAUsers** och väljer sedan **Select**  >  **Done**.</span><span class="sxs-lookup"><span data-stu-id="250d0-166">In the **Select** pane, select the **MFAUsers** group, and then select **Select** > **Done**.</span></span>
8. <span data-ttu-id="250d0-167">I avsnittet **Access-kontroller** i **fönstret Nytt** väljer du **Tilldela**.</span><span class="sxs-lookup"><span data-stu-id="250d0-167">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="250d0-168">I fönstret **Bevilja** väljer du **Kräv multifaktorautentisering** och väljer sedan **Välj**.</span><span class="sxs-lookup"><span data-stu-id="250d0-168">In the **Grant** pane, select **Require multi-factor authentication**, and then select **Select**.</span></span>
10. <span data-ttu-id="250d0-169">I fönstret **Nytt** väljer du **På** för **Aktivera princip** och sedan **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="250d0-169">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="250d0-170">Stäng **Azure Portal och** Microsoft 365 **flikarna i administrationscentret.**</span><span class="sxs-lookup"><span data-stu-id="250d0-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="250d0-171">Du kan testa den här principen genom att logga ut och logga in med User 3-kontot.</span><span class="sxs-lookup"><span data-stu-id="250d0-171">To test this policy, sign out and sign in with the User 3 account.</span></span> <span data-ttu-id="250d0-172">Du bör uppmanas att konfigurera MFA.</span><span class="sxs-lookup"><span data-stu-id="250d0-172">You should be prompted to configure MFA.</span></span> <span data-ttu-id="250d0-173">Det visar att MFAUsers-principen tillämpas.</span><span class="sxs-lookup"><span data-stu-id="250d0-173">This demonstrates that the MFAUsers policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="250d0-174">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="250d0-174">Next step</span></span>

<span data-ttu-id="250d0-175">Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="250d0-175">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="250d0-176">Se även</span><span class="sxs-lookup"><span data-stu-id="250d0-176">See also</span></span>

[<span data-ttu-id="250d0-177">Identitetsöversikt</span><span class="sxs-lookup"><span data-stu-id="250d0-177">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="250d0-178">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="250d0-178">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="250d0-179">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="250d0-179">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="250d0-180">Dokumentation om Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="250d0-180">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)