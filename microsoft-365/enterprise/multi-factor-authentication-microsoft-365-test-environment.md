---
title: Microsoft 365 för företags test miljö multifaktorautentisering
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
description: Konfigurera multifaktorautentisering med text meddelanden som skickas till en smart telefon i test miljön för Microsoft 365 för företag.
ms.openlocfilehash: 4c59405c1ce59cafaf0309e2314e5cbfa4eb080a
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558448"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="51f26-103">Multifaktorautentisering för test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="51f26-103">Multi-factor authentication for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="51f26-104">*Den här test laboratorie guiden kan användas för både Microsoft 365 för företags-och Office 365 företags test miljöer.*</span><span class="sxs-lookup"><span data-stu-id="51f26-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="51f26-105">Om du vill ha ytterligare en säkerhets nivå för att logga in på Microsoft 365 eller någon tjänst eller ett program som använder Azure AD-klient organisationen för din prenumeration kan du aktivera Azure AD Multi-Factor-verifiering, vilket kräver mer än ett användar namn och lösen ord för att verifiera ett konto.</span><span class="sxs-lookup"><span data-stu-id="51f26-105">For an additional level of security for signing in to Microsoft 365 or any service or application that uses the Azure AD tenant for your subscription, you can enable Azure AD multi-factor authentication, which requires more than just a username and password to verify an account.</span></span>

<span data-ttu-id="51f26-106">Med multifaktorautentisering måste användare bekräfta ett telefonsamtal, ange en verifierings kod som skickas i ett textmeddelande eller verifiera verifieringen med en app på deras smarta telefoner när du har angett lösen orden korrekt.</span><span class="sxs-lookup"><span data-stu-id="51f26-106">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or verify the authentication with an app on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="51f26-107">De kan bara logga in när denna faktor är uppfylld.</span><span class="sxs-lookup"><span data-stu-id="51f26-107">They can sign in only after this second authentication factor is satisfied.</span></span>
  
<span data-ttu-id="51f26-108">I den här artikeln beskrivs hur du aktiverar och testar SMS-baserad lösenordsautentisering för ett specifikt användar konto.</span><span class="sxs-lookup"><span data-stu-id="51f26-108">This article describes how to enable and test text message-based authentication for a specific user account.</span></span>
  
<span data-ttu-id="51f26-109">Att konfigurera multifaktorautentisering för ett konto i test miljön för Microsoft 365 för företag inbegriper två faser och en tredje valfria fas:</span><span class="sxs-lookup"><span data-stu-id="51f26-109">Setting up multi-factor authentication for an account in your Microsoft 365 for enterprise test environment involves two phases and a third optional phase:</span></span>
- [<span data-ttu-id="51f26-110">Fas 1: bygga ut test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="51f26-110">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="51f26-111">Fas 2: Aktivera och testa multifaktorautentisering för användare 2-konto</span><span class="sxs-lookup"><span data-stu-id="51f26-111">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [<span data-ttu-id="51f26-112">Fas 3: Aktivera och testa multifaktorautentisering med en princip för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="51f26-112">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="51f26-114">Om du vill visa en visuell karta till alla artiklar i gruppen Microsoft 365 för Enterprise-testlabbet går du till [Microsoft 365 för Enterprise Test Lab-guide](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="51f26-114">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="51f26-115">Fas 1: bygga ut test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="51f26-115">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="51f26-116">Om du bara vill testa multifaktorautentisering på ett lättviktigt sätt med minimi kraven följer du anvisningarna i [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="51f26-116">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="51f26-117">Om du vill testa multifaktorautentisering i ett simulerat företag följer du anvisningarna i [vidarekoppling](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="51f26-117">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="51f26-118">Testning av multifaktorautentisering kräver inte den simulerade företags test miljön, som innehåller ett simulerat intranät som är kopplat till Internet-och katalogs-synkronisering för en AD DS-skog (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="51f26-118">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="51f26-119">Det finns ett alternativ som gör att du kan testa multifaktorautentisering och experimentera med den i en miljö som representerar en typisk organisation.</span><span class="sxs-lookup"><span data-stu-id="51f26-119">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="51f26-120">Fas 2: Aktivera och testa multifaktorautentisering för användare 2-konto</span><span class="sxs-lookup"><span data-stu-id="51f26-120">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="51f26-121">Aktivera multifaktorautentisering för användare 2-kontot med de här stegen:</span><span class="sxs-lookup"><span data-stu-id="51f26-121">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="51f26-122">Öppna en separat privat instans av webbläsaren, gå till administrations centret för Microsoft 365 [https://portal.microsoft.com](https://portal.microsoft.com) och logga in med ditt globala administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="51f26-122">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="51f26-123">I det vänstra navigerings fältet väljer **du användare**  >  **aktiva användare**.</span><span class="sxs-lookup"><span data-stu-id="51f26-123">In the left navigation, select **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="51f26-124">I fönstret aktiva användare väljer du **multifaktorautentisering**.</span><span class="sxs-lookup"><span data-stu-id="51f26-124">In the Active users pane, select **Multi-factor authentication**.</span></span>
    
4. <span data-ttu-id="51f26-125">I listan väljer du **användare 2** -konto.</span><span class="sxs-lookup"><span data-stu-id="51f26-125">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="51f26-126">I avsnittet **User 2** under **snabb steg** väljer du **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="51f26-126">In the **User 2** section, under **Quick steps**, select **Enable**.</span></span>
    
6. <span data-ttu-id="51f26-127">I dialog rutan **om aktivering av multifaktorautentisering** väljer du **Aktivera multifaktorautentisering**.</span><span class="sxs-lookup"><span data-stu-id="51f26-127">In the **About enabling multi-factor auth** dialog box, select **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="51f26-128">I dialog rutan **updates lyckades** väljer du **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="51f26-128">In the **Updates successful** dialog box, select **Close**.</span></span>
    
8. <span data-ttu-id="51f26-129">På fliken **administrations Center för Microsoft 365** väljer du ikonen användar konto längst upp till höger och väljer sedan **Logga ut**.</span><span class="sxs-lookup"><span data-stu-id="51f26-129">On the **Microsoft 365 admin center** tab, select the user account icon in the upper right, and then select **Sign out**.</span></span>
    
9. <span data-ttu-id="51f26-130">Stäng din instans av webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="51f26-130">Close your browser instance.</span></span>
   
<span data-ttu-id="51f26-131">Slutför konfigurationen för användare 2-kontot för att använda ett textmeddelande för verifiering och testa det med de här stegen:</span><span class="sxs-lookup"><span data-stu-id="51f26-131">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="51f26-132">Öppna en ny privat instans av webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="51f26-132">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="51f26-133">Gå till [administrations centret för Microsoft 365](https://admin.microsoft.com) och logga in med användar namnet för användare 2 och lösen ordet.</span><span class="sxs-lookup"><span data-stu-id="51f26-133">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="51f26-134">När du har loggat in uppmanas du att konfigurera kontot för mer information.</span><span class="sxs-lookup"><span data-stu-id="51f26-134">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="51f26-135">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="51f26-135">Select **Next**.</span></span>
    
4. <span data-ttu-id="51f26-136">På sidan **ytterligare säkerhets verifiering** :</span><span class="sxs-lookup"><span data-stu-id="51f26-136">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="51f26-137">Välj land eller region.</span><span class="sxs-lookup"><span data-stu-id="51f26-137">Select your country or region.</span></span>
    
   - <span data-ttu-id="51f26-138">Ange telefonnumret till den smarta telefon som ska ta emot textmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="51f26-138">Enter the phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="51f26-139">I **metod** väljer du **skicka en kod efter SMS**.</span><span class="sxs-lookup"><span data-stu-id="51f26-139">In **Method**, select **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="51f26-140">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="51f26-140">Select **Next**.</span></span>
    
6. <span data-ttu-id="51f26-141">Ange verifierings koden från textmeddelandet som visas på din mobil telefon och välj sedan **Verifiera**.</span><span class="sxs-lookup"><span data-stu-id="51f26-141">Enter the verification code from the text message received on your smart phone, and then select **Verify**.</span></span>
    
7. <span data-ttu-id="51f26-142">På sidan **steg 3: Behåll dina befintliga program** väljer du **klar**.</span><span class="sxs-lookup"><span data-stu-id="51f26-142">On the **Step 3: Keep your existing applications** page, select **Done**.</span></span>
    
8. <span data-ttu-id="51f26-143">Om det är första gången du loggar in med User 2-kontot uppmanas du att ändra lösen ordet.</span><span class="sxs-lookup"><span data-stu-id="51f26-143">If this is the first time you signed in with the User 2 account, you are prompted to change the password.</span></span> <span data-ttu-id="51f26-144">Ange det ursprungliga lösen ordet och ett nytt lösen ord två gånger och välj sedan **Uppdatera lösen ord och logga in**.</span><span class="sxs-lookup"><span data-stu-id="51f26-144">Enter the original password and a new password twice, and then select **Update password and sign in**.</span></span> <span data-ttu-id="51f26-145">Spela in det nya lösen ordet på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="51f26-145">Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="51f26-146">Du bör se Office-portalen för användare 2 på fliken **Microsoft Office-Startsida** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="51f26-146">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a><span data-ttu-id="51f26-147">Fas 3: Aktivera och testa multifaktorautentisering med en princip för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="51f26-147">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>

<span data-ttu-id="51f26-148">*Den här fasen kan endast användas för test miljön Microsoft 365 för företag.*</span><span class="sxs-lookup"><span data-stu-id="51f26-148">*This phase can only be used for a Microsoft 365 for enterprise test environment.*</span></span>

<span data-ttu-id="51f26-149">I den här fasen aktiverar du multifaktorautentisering för användare 3-kontot med hjälp av en grupp och en princip för villkorsstyrd åtkomst.</span><span class="sxs-lookup"><span data-stu-id="51f26-149">In this phase, you enable multi-factor authentication for the User 3 account using a group and a conditional access policy.</span></span>

<span data-ttu-id="51f26-150">Skapa sedan en ny grupp med namnet MFAUsers och Lägg till användare 3-kontot i den.</span><span class="sxs-lookup"><span data-stu-id="51f26-150">Next, create a new group named MFAUsers and add the User 3 account to it.</span></span>

1. <span data-ttu-id="51f26-151">Gå till fliken **administrations Center för Microsoft 365** , Välj **grupper** i det vänstra navigerings fältet och välj sedan **grupper**.</span><span class="sxs-lookup"><span data-stu-id="51f26-151">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="51f26-152">Välj **Lägg till en grupp**.</span><span class="sxs-lookup"><span data-stu-id="51f26-152">Select **Add a group**.</span></span>
3. <span data-ttu-id="51f26-153">I fönstret **Välj en grupptyp** väljer du **säkerhet** och sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="51f26-153">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="51f26-154">I fönstret **Konfigurera grunderna väljer du** **Skapa grupp** och sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="51f26-154">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="51f26-155">Ange **MFAUsers** i fönstret **Granska och slutför** och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="51f26-155">In the **Review and finish adding group** pane, enter **MFAUsers**, and then select **Next**.</span></span>
6. <span data-ttu-id="51f26-156">I listan med grupper väljer du gruppen **MFAUsers** .</span><span class="sxs-lookup"><span data-stu-id="51f26-156">In the list of groups, select the **MFAUsers** group.</span></span>
7. <span data-ttu-id="51f26-157">I fönstret **MFAUsers** väljer du **medlemmar** och sedan **Visa alla och hantera medlemmar**.</span><span class="sxs-lookup"><span data-stu-id="51f26-157">In the **MFAUsers** pane, select **Members**, and then select **View all and manage members**.</span></span>
8. <span data-ttu-id="51f26-158">I fönstret **MFAUsers** väljer du **Lägg till medlemmar**, väljer **användare 3** -konto och väljer sedan **Spara**  >  **Close**  >  **Close**.</span><span class="sxs-lookup"><span data-stu-id="51f26-158">In the **MFAUsers** pane, select **Add members**, select the **User 3** account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="51f26-159">Skapa sedan en villkorsstyrd åtkomst policy som kräver multifaktorautentisering för medlemmar i gruppen MFAUsers.</span><span class="sxs-lookup"><span data-stu-id="51f26-159">Next, create a conditional access policy to require multifactor authentication for members of the MFAUsers group.</span></span>

1. <span data-ttu-id="51f26-160">Gå till på en ny flik i webbläsaren [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="51f26-160">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="51f26-161">Välj villkorlig åtkomst för **Azure Active Directory**-  >  **säkerhet**  >  **Conditional Access**.</span><span class="sxs-lookup"><span data-stu-id="51f26-161">Select **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="51f26-162">I fönstret **villkorlig åtkomst – principer** väljer du **ny princip**.</span><span class="sxs-lookup"><span data-stu-id="51f26-162">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
4. <span data-ttu-id="51f26-163">Ange **MFA för användar konton** i rutan **namn** i fönstret **nytt** .</span><span class="sxs-lookup"><span data-stu-id="51f26-163">In the **New** pane, enter **MFA for user accounts** in the **Name** box.</span></span>
5. <span data-ttu-id="51f26-164">Välj **användare och grupper** i avsnittet **uppgifter** .</span><span class="sxs-lookup"><span data-stu-id="51f26-164">In the **Assignments** section, select **Users and groups**.</span></span>
6. <span data-ttu-id="51f26-165">På fliken **Inkludera** i fönstret **användare och grupper** väljer du **Välj användare och grupper** som  >  **användare och grupper**  >  **väljer**.</span><span class="sxs-lookup"><span data-stu-id="51f26-165">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
7. <span data-ttu-id="51f26-166">I fönstret **Välj** väljer du gruppen **MFAUsers** och väljer sedan **Välj**  >  **klar**.</span><span class="sxs-lookup"><span data-stu-id="51f26-166">In the **Select** pane, select the **MFAUsers** group, and then select **Select** > **Done**.</span></span>
8. <span data-ttu-id="51f26-167">I avsnittet **Access Controls** i fönstret **ny** väljer du **Grant**.</span><span class="sxs-lookup"><span data-stu-id="51f26-167">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="51f26-168">I fönstret **bidrag** väljer du **Kräv multifaktorautentisering** och väljer sedan **Välj**.</span><span class="sxs-lookup"><span data-stu-id="51f26-168">In the **Grant** pane, select **Require multi-factor authentication**, and then select **Select**.</span></span>
10. <span data-ttu-id="51f26-169">I fönstret **nytt** väljer du **på** för **att aktivera principer** och väljer sedan **skapa**.</span><span class="sxs-lookup"><span data-stu-id="51f26-169">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="51f26-170">Stäng flikarna **Azure Portal** och **Microsoft 365 administrations Center** .</span><span class="sxs-lookup"><span data-stu-id="51f26-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="51f26-171">Testa den här principen genom att logga ut och logga in med användare 3-kontot.</span><span class="sxs-lookup"><span data-stu-id="51f26-171">To test this policy, sign out and sign in with the User 3 account.</span></span> <span data-ttu-id="51f26-172">Du bör uppmanas att konfigurera MFA.</span><span class="sxs-lookup"><span data-stu-id="51f26-172">You should be prompted to configure MFA.</span></span> <span data-ttu-id="51f26-173">Det visar att MFAUsers Policy tillämpas.</span><span class="sxs-lookup"><span data-stu-id="51f26-173">This demonstrates that the MFAUsers policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="51f26-174">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="51f26-174">Next step</span></span>

<span data-ttu-id="51f26-175">Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="51f26-175">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="51f26-176">Se även</span><span class="sxs-lookup"><span data-stu-id="51f26-176">See also</span></span>

[<span data-ttu-id="51f26-177">Identitets översikt</span><span class="sxs-lookup"><span data-stu-id="51f26-177">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="51f26-178">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="51f26-178">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="51f26-179">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="51f26-179">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="51f26-180">Microsoft 365 för företags dokumentation</span><span class="sxs-lookup"><span data-stu-id="51f26-180">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
