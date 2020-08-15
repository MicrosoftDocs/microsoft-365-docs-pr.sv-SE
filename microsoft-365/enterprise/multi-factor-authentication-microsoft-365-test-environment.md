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
ms.openlocfilehash: 4ed50d37e0f4e73d5d1fc62e295df374c61b9786
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686280"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="014c3-103">Multifaktorautentisering för test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="014c3-103">Multi-factor authentication for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="014c3-104">*Den här test laboratorie guiden kan användas för både Microsoft 365 för företags-och Office 365 företags test miljöer.*</span><span class="sxs-lookup"><span data-stu-id="014c3-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="014c3-105">Om du vill ha ytterligare en säkerhets nivå för att logga in på Microsoft 365 eller någon tjänst eller ett program som använder Azure AD-klient organisationen för din prenumeration kan du aktivera Azure Multi-Factor-verifiering, vilket kräver mer än ett användar namn och lösen ord för att verifiera ett konto.</span><span class="sxs-lookup"><span data-stu-id="014c3-105">For an additional level of security for signing in to Microsoft 365 or any service or application that uses the Azure AD tenant for your subscription, you can enable Azure multi-factor authentication, which requires more than just a username and password to verify an account.</span></span> 

<span data-ttu-id="014c3-106">Med multifaktorautentisering måste användare bekräfta ett telefonsamtal, ange en verifierings kod som skickas i ett textmeddelande eller verifiera verifieringen med en app på deras smarta telefoner när du har angett lösen orden korrekt.</span><span class="sxs-lookup"><span data-stu-id="014c3-106">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or verify the authentication with an app on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="014c3-107">De kan bara logga in när denna faktor har uppfyllts.</span><span class="sxs-lookup"><span data-stu-id="014c3-107">They can sign in only after this second authentication factor has been satisfied.</span></span> 
  
<span data-ttu-id="014c3-108">I den här artikeln beskrivs hur du aktiverar och testar SMS-baserad lösenordsautentisering för ett specifikt användar konto.</span><span class="sxs-lookup"><span data-stu-id="014c3-108">This article describes how to enable and test text message-based authentication for a specific user account.</span></span>
  
<span data-ttu-id="014c3-109">Det finns två faser för att konfigurera multifaktorautentisering för ett konto i test miljön för Microsoft 365 för företag:</span><span class="sxs-lookup"><span data-stu-id="014c3-109">There are two phases to setting up multi-factor authentication for an account in your Microsoft 365 for enterprise test environment:</span></span>
  
1. <span data-ttu-id="014c3-110">Skapa test miljön för Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="014c3-110">Create the Microsoft 365 for enterprise test environment.</span></span>
    
2. <span data-ttu-id="014c3-111">Aktivera och testa multifaktorautentisering för användare 2-kontot.</span><span class="sxs-lookup"><span data-stu-id="014c3-111">Enable and test multi-factor authentication for the User 2 account.</span></span>

3. <span data-ttu-id="014c3-112">Aktivera och testa multifaktorautentisering med en princip för villkorsstyrd åtkomst (valfritt).</span><span class="sxs-lookup"><span data-stu-id="014c3-112">Enable and test multi-factor authentication with a conditional access policy (optional).</span></span>

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="014c3-114">Gå till [Guide för testnings laboratorium](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) för en bild karta till alla artiklar i test laboratorie guiden för Microsoft 365 för Enterprise.</span><span class="sxs-lookup"><span data-stu-id="014c3-114">Go to [Test Lab Guide Stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="014c3-115">Fas 1: bygga ut test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="014c3-115">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="014c3-116">Om du bara vill testa multifaktorautentisering på ett lättviktigt sätt med minimi kraven följer du anvisningarna i [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="014c3-116">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="014c3-117">Om du vill testa multifaktorautentisering i ett simulerat företag följer du anvisningarna i [vidarekoppling](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="014c3-117">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="014c3-118">Testning av multifaktorautentisering kräver inte den simulerade företags test miljön, som innehåller ett simulerat intranät som är kopplat till Internet-och katalogs-synkronisering för en AD DS-skog (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="014c3-118">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="014c3-119">Det finns ett alternativ som gör att du kan testa multifaktorautentisering och experimentera med den i en miljö som representerar en typisk organisation.</span><span class="sxs-lookup"><span data-stu-id="014c3-119">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="014c3-120">Fas 2: Aktivera och testa multifaktorautentisering för användare 2-konto</span><span class="sxs-lookup"><span data-stu-id="014c3-120">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="014c3-121">Aktivera multifaktorautentisering för användare 2-kontot med de här stegen:</span><span class="sxs-lookup"><span data-stu-id="014c3-121">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="014c3-122">Öppna en separat privat instans av webbläsaren, gå till administrations centret för Microsoft 365 [https://portal.microsoft.com](https://portal.microsoft.com) och logga in med ditt globala administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="014c3-122">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="014c3-123">Klicka på **Användare > Aktiva användare** i det vänstra navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="014c3-123">In the left navigation, click **Users > Active users**.</span></span>
    
3. <span data-ttu-id="014c3-124">I fönstret aktiva användare klickar du på **multifaktorautentisering**.</span><span class="sxs-lookup"><span data-stu-id="014c3-124">In the Active users pane, click **Multi-factor authentication**.</span></span>
    
4. <span data-ttu-id="014c3-125">I listan väljer du **användare 2** -konto.</span><span class="sxs-lookup"><span data-stu-id="014c3-125">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="014c3-126">Under **snabb steg**i avsnittet **användare 2** klickar du på **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="014c3-126">In the **User 2** section, under **Quick steps**, click **Enable**.</span></span>
    
6. <span data-ttu-id="014c3-127">I dialog rutan **om aktivering av multifaktorautentisering** klickar du på **Aktivera multifaktorautentisering**.</span><span class="sxs-lookup"><span data-stu-id="014c3-127">In the **About enabling multi-factor auth** dialog box, click **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="014c3-128">Klicka på **Stäng**i dialog rutan **uppdateringar har slutförts** .</span><span class="sxs-lookup"><span data-stu-id="014c3-128">In the **Updates successful** dialog box, click **Close**.</span></span>
    
8. <span data-ttu-id="014c3-129">På fliken **administrations Center för Microsoft 365** klickar du på ikonen användar konto längst upp till höger och sedan på **Logga ut**.</span><span class="sxs-lookup"><span data-stu-id="014c3-129">On the **Microsoft 365 admin center** tab, click the user account icon in the upper right, and then click **Sign out**.</span></span>
    
9. <span data-ttu-id="014c3-130">Stäng din instans av webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="014c3-130">Close your browser instance.</span></span>
   
<span data-ttu-id="014c3-131">Slutför konfigurationen för användare 2-kontot för att använda ett textmeddelande för verifiering och testa det med de här stegen:</span><span class="sxs-lookup"><span data-stu-id="014c3-131">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="014c3-132">Öppna en ny privat instans av webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="014c3-132">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="014c3-133">Gå till [administrations centret för Microsoft 365](https://admin.microsoft.com) och logga in med användar namnet för användare 2 och lösen ordet.</span><span class="sxs-lookup"><span data-stu-id="014c3-133">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="014c3-134">När du har loggat in uppmanas du att konfigurera kontot för mer information.</span><span class="sxs-lookup"><span data-stu-id="014c3-134">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="014c3-135">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="014c3-135">Click **Next**.</span></span>
    
4. <span data-ttu-id="014c3-136">På sidan **ytterligare säkerhets verifiering** :</span><span class="sxs-lookup"><span data-stu-id="014c3-136">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="014c3-137">Välj land eller region.</span><span class="sxs-lookup"><span data-stu-id="014c3-137">Select your country or region.</span></span>
    
   - <span data-ttu-id="014c3-138">Skriv telefonnumret till den smartphone som tar emot textmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="014c3-138">Type phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="014c3-139">Klicka **på** **skicka mig en kod efter SMS**.</span><span class="sxs-lookup"><span data-stu-id="014c3-139">In **Method**, click **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="014c3-140">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="014c3-140">Click **Next**.</span></span>
    
6. <span data-ttu-id="014c3-141">Ange verifierings koden från textmeddelandet som visas på din mobil telefon och klicka sedan på **Verifiera**.</span><span class="sxs-lookup"><span data-stu-id="014c3-141">Enter the verification code from the text message received on your smart phone, and then click **Verify**.</span></span>
    
7. <span data-ttu-id="014c3-142">På sidan **steg 3: Behåll dina befintliga program** klickar du på **klar**.</span><span class="sxs-lookup"><span data-stu-id="014c3-142">On the **Step 3: Keep your existing applications** page, click **Done**.</span></span>
    
8. <span data-ttu-id="014c3-143">Om det är första gången du loggar in med User 2-kontot uppmanas du att ändra lösen ordet.</span><span class="sxs-lookup"><span data-stu-id="014c3-143">If this is the first time you signed in with the User 2 account, you are prompted to change the password.</span></span> <span data-ttu-id="014c3-144">Skriv det ursprungliga lösen ordet och ett nytt lösen ord två gånger och klicka sedan på **Uppdatera lösen ord och logga in**.</span><span class="sxs-lookup"><span data-stu-id="014c3-144">Type the original password and a new password twice, and then click **Update password and sign in**.</span></span> <span data-ttu-id="014c3-145">Spela in det nya lösen ordet på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="014c3-145">Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="014c3-146">Du bör se Office-portalen för användare 2 på fliken **Microsoft Office-Startsida** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="014c3-146">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a><span data-ttu-id="014c3-147">Fas 3: Aktivera och testa multifaktorautentisering med en princip för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="014c3-147">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>

<span data-ttu-id="014c3-148">*Den här fasen kan endast användas för test miljön Microsoft 365 för företag.*</span><span class="sxs-lookup"><span data-stu-id="014c3-148">*This phase can only be used for a Microsoft 365 for enterprise test environment.*</span></span>

<span data-ttu-id="014c3-149">I den här fasen aktiverar du multifaktorautentisering för användare 3-kontot med hjälp av en grupp och en princip för villkorsstyrd åtkomst.</span><span class="sxs-lookup"><span data-stu-id="014c3-149">In this phase you enable multi-factor authentication for the User 3 account using a group and a conditional access policy.</span></span>

<span data-ttu-id="014c3-150">Skapa sedan en ny grupp med namnet MFAUsers och Lägg till användare 3-kontot i den.</span><span class="sxs-lookup"><span data-stu-id="014c3-150">Next, create a new group named MFAUsers and add the User 3 account to it.</span></span>

1. <span data-ttu-id="014c3-151">Klicka på **grupper** i det vänstra navigerings fältet på fliken **administrations center för Microsoft 365** och klicka sedan på **grupper**.</span><span class="sxs-lookup"><span data-stu-id="014c3-151">On the **Microsoft 365 admin center** tab, click **Groups** in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="014c3-152">Klicka på **Lägg till en grupp**.</span><span class="sxs-lookup"><span data-stu-id="014c3-152">Click **Add a group**.</span></span>
3. <span data-ttu-id="014c3-153">I fönstret **Välj en grupptyp** väljer du **säkerhet**och sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="014c3-153">In the **Choose a group type** pane, select **Security**, and then click **Next**.</span></span>
4. <span data-ttu-id="014c3-154">Klicka på **Skapa grupp**i fönstret **Konfigurera grunderna** och klicka sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="014c3-154">In the **Set up the basics** pane, click **Create group**, and then click **Close**.</span></span>
5. <span data-ttu-id="014c3-155">Skriv **MFAUsers**i fönstret **Granska och slutför tillägg** och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="014c3-155">In the **Review and finish adding group** pane, type **MFAUsers**, and then click **Next**.</span></span>
6. <span data-ttu-id="014c3-156">I listan med grupper klickar du på gruppen **MFAUsers** .</span><span class="sxs-lookup"><span data-stu-id="014c3-156">In the list of groups, click the **MFAUsers** group.</span></span>
7. <span data-ttu-id="014c3-157">I fönstret **MFAUsers** klickar du på **medlemmar**och sedan på **Visa alla och hantera medlemmar**.</span><span class="sxs-lookup"><span data-stu-id="014c3-157">In the **MFAUsers** pane, click **Members**, and then click **View all and manage members**.</span></span>
8. <span data-ttu-id="014c3-158">I fönstret **MFAUsers** klickar du på **Lägg till medlemmar**, väljer **användare 3** -konto och klickar sedan på **Spara > Stäng > Stäng**.</span><span class="sxs-lookup"><span data-stu-id="014c3-158">In the **MFAUsers** pane, click **Add members**, select the **User 3** account, and then click **Save > Close > Close**.</span></span>

<span data-ttu-id="014c3-159">Skapa sedan en villkorsstyrd åtkomst policy som kräver multifaktorautentisering för medlemmar i gruppen MFAUsers.</span><span class="sxs-lookup"><span data-stu-id="014c3-159">Next, create a conditional access policy to require multifactor authentication for members of the MFAUsers group.</span></span>

1. <span data-ttu-id="014c3-160">Gå till på en ny flik i webbläsaren [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="014c3-160">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="014c3-161">Klicka på **> säkerhets > villkorlig åtkomst för Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="014c3-161">Click **Azure Active Directory > Security > Conditional Access**.</span></span>
3. <span data-ttu-id="014c3-162">Klicka på **ny princip**i fönstret **villkorlig åtkomst – policys** .</span><span class="sxs-lookup"><span data-stu-id="014c3-162">In the **Conditional access – Policies** pane, click **New policy**.</span></span>
4. <span data-ttu-id="014c3-163">I fönstret **ny** skriver du **MFA för användar konton** i **namn**.</span><span class="sxs-lookup"><span data-stu-id="014c3-163">In the **New** pane, type **MFA for user accounts** in **Name**.</span></span>
5. <span data-ttu-id="014c3-164">Klicka på **användare och grupper**i avsnittet **uppgifter** .</span><span class="sxs-lookup"><span data-stu-id="014c3-164">In the **Assignments** section, click **Users and groups**.</span></span>
6. <span data-ttu-id="014c3-165">På fliken **Inkludera** i fönstret **användare och grupper** klickar du på **Välj användare och grupper > användare och grupper > välja**.</span><span class="sxs-lookup"><span data-stu-id="014c3-165">On the **Include** tab of the **Users and groups** pane, click **Select users and groups > Users and groups > Select**.</span></span>
7. <span data-ttu-id="014c3-166">Klicka på gruppen **MFAUsers** i fönstret **Välj** och klicka sedan på **Välj > klar**.</span><span class="sxs-lookup"><span data-stu-id="014c3-166">In the **Select** pane, click the **MFAUsers** group, and then click **Select > Done**.</span></span>
8. <span data-ttu-id="014c3-167">Klicka på **Tillåt**i avsnittet **Access-kontroller** i fönstret **nytt** .</span><span class="sxs-lookup"><span data-stu-id="014c3-167">In the **Access controls** section of the **New** pane, click **Grant**.</span></span>
9. <span data-ttu-id="014c3-168">Klicka på **Kräv multifaktorautentisering**i fönstret **bidrag** och klicka sedan på **Välj**.</span><span class="sxs-lookup"><span data-stu-id="014c3-168">In the **Grant** pane, click **Require multi-factor authentication**, and then click **Select**.</span></span>
10. <span data-ttu-id="014c3-169">I fönstret **ny** klickar du **på** för att **aktivera principer**och klickar sedan på **skapa**.</span><span class="sxs-lookup"><span data-stu-id="014c3-169">In the **New** pane, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="014c3-170">Stäng flikarna **Azure Portal** och **Microsoft 365 administrations Center** .</span><span class="sxs-lookup"><span data-stu-id="014c3-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="014c3-171">Testa den här principen genom att logga ut och logga in med användare 3-kontot.</span><span class="sxs-lookup"><span data-stu-id="014c3-171">To test this policy, sign out and sign in with the User 3 account.</span></span> <span data-ttu-id="014c3-172">Du bör uppmanas att konfigurera MFA.</span><span class="sxs-lookup"><span data-stu-id="014c3-172">You should be prompted to configure MFA.</span></span> <span data-ttu-id="014c3-173">Det visar att MFAUsers Policy tillämpas.</span><span class="sxs-lookup"><span data-stu-id="014c3-173">This demonstrates that the MFAUsers policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="014c3-174">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="014c3-174">Next step</span></span>

<span data-ttu-id="014c3-175">Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="014c3-175">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="014c3-176">Se även</span><span class="sxs-lookup"><span data-stu-id="014c3-176">See also</span></span>

[<span data-ttu-id="014c3-177">Identitets översikt</span><span class="sxs-lookup"><span data-stu-id="014c3-177">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="014c3-178">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="014c3-178">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="014c3-179">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="014c3-179">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="014c3-180">Microsoft 365 för företags dokumentation</span><span class="sxs-lookup"><span data-stu-id="014c3-180">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
