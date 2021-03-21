---
title: Skydda globala administratörskonton i testmiljön Microsoft 365 för företag
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
description: Använd de här stegen för att skydda globala administratörskonton i testmiljön Microsoft 365 för företag.
ms.openlocfilehash: 3eab538b59e460857e2fa195aaacf51051f94d6b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918888"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="6d2e6-103">Skydda globala administratörskonton i testmiljön Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="6d2e6-103">Protect global administrator accounts in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="6d2e6-104">*Den här testlabbguiden kan endast användas för Microsoft 365 för företagstestmiljöer.*</span><span class="sxs-lookup"><span data-stu-id="6d2e6-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="6d2e6-105">Du kan förhindra digitala attacker på din organisation genom att se till att dina administratörskonton är så säkra som möjligt.</span><span class="sxs-lookup"><span data-stu-id="6d2e6-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> 

<span data-ttu-id="6d2e6-106">I den här artikeln beskrivs hur du använder villkorsstyrda åtkomstprinciper för Azure Active Directory (Azure AD) för att skydda globala administratörskonton.</span><span class="sxs-lookup"><span data-stu-id="6d2e6-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="6d2e6-107">Skydda globala administratörskonton i din Testmiljö för Microsoft 365 för företag innebär två faser:</span><span class="sxs-lookup"><span data-stu-id="6d2e6-107">Protecting global administrator accounts in your Microsoft 365 for enterprise test environment involves two phases:</span></span>
- [<span data-ttu-id="6d2e6-108">Fas 1: Bygg ut microsoft 365 för företagstestmiljö</span><span class="sxs-lookup"><span data-stu-id="6d2e6-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="6d2e6-109">Fas 2: Konfigurera principer för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="6d2e6-109">Phase 2: Configure conditional access policies</span></span>](#phase-2-configure-conditional-access-policies)

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="6d2e6-111">En visuell karta till alla artiklar i Microsoft 365 testlabbguide-stacken för företag finns i Testlabbguide för [Microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)för företag.</span><span class="sxs-lookup"><span data-stu-id="6d2e6-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="6d2e6-112">Fas 1: Bygg ut microsoft 365 för företagstestmiljö</span><span class="sxs-lookup"><span data-stu-id="6d2e6-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="6d2e6-113">Om du vill testa kontoskyddet för globala administratörer på ett lätt sätt med minimikraven följer du anvisningarna i [Enkel baskonfiguration.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="6d2e6-113">If you want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="6d2e6-114">Om du vill testa kontoskydd för globala administratörer i ett simulerat företag följer du anvisningarna i [Direktautentisering](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="6d2e6-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6d2e6-115">Om du testar kontoskyddet för globala administratörer krävs inte den simulerade företagstestmiljön, som omfattar ett simulerat intranät som är anslutet till Internet och katalogsynkronisering för en AD DS (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="6d2e6-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="6d2e6-116">Den finns här som ett alternativ så att du kan testa det globala administratörskontoskyddet och experimentera med det i en miljö som representerar en vanlig organisation.</span><span class="sxs-lookup"><span data-stu-id="6d2e6-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="6d2e6-117">Fas 2: Konfigurera principer för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="6d2e6-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="6d2e6-118">Börja med att skapa ett nytt användarkonto som en dedikerad global administratör.</span><span class="sxs-lookup"><span data-stu-id="6d2e6-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="6d2e6-119">På en separat flik öppnar du [administrationscentret för Microsoft 365.](https://admin.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="6d2e6-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="6d2e6-120">Välj **Användare**  >  **Aktiva användare** och välj sedan Lägg till en **användare.**</span><span class="sxs-lookup"><span data-stu-id="6d2e6-120">Select **Users** > **Active users**, and then select **Add a user**.</span></span>
3. <span data-ttu-id="6d2e6-121">I fönstret **Lägg till** användare anger du **DedicatedAdmin** i **rutorna Förnamn,** **Visningsnamn** **och** Användarnamn.</span><span class="sxs-lookup"><span data-stu-id="6d2e6-121">In the **Add user** pane, enter **DedicatedAdmin** in the **First name**, **Display name**, and **Username** boxes.</span></span>
4. <span data-ttu-id="6d2e6-122">Välj **Lösenord**, välj **Låt mig skapa lösenordet** och ange sedan ett starkt lösenord.</span><span class="sxs-lookup"><span data-stu-id="6d2e6-122">Select **Password**, select **Let me create the password**, and then enter a strong password.</span></span> <span data-ttu-id="6d2e6-123">Registrera lösenordet för det nya kontot på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="6d2e6-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="6d2e6-124">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="6d2e6-124">Select **Next**.</span></span>
6. <span data-ttu-id="6d2e6-125">I fönstret **Tilldela produktlicenser** väljer du **Microsoft 365 E5** och sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="6d2e6-125">In the **Assign product licenses** pane, select **Microsoft 365 E5**, and then select **Next**.</span></span>
7. <span data-ttu-id="6d2e6-126">I fönstret **Valfria inställningar** väljer du **Rolladministrationscenter**  >  **åtkomst till** Global  >  **administratör**  >  **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="6d2e6-126">In the **Optional settings** pane, select **Roles** > **Admin center access** > **Global admin** > **Next**.</span></span>
8. <span data-ttu-id="6d2e6-127">I fönstret **Du är nästan klar** väljer du Slutför **tilläggning** och sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="6d2e6-127">On the **You're almost done** pane, select **Finish adding**, and then select **Close**.</span></span>

<span data-ttu-id="6d2e6-128">Skapa sedan en ny grupp med namnet GlobalAdmins och lägg till DedicatedAdmin-kontot i den gruppen.</span><span class="sxs-lookup"><span data-stu-id="6d2e6-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="6d2e6-129">På fliken **Administrationscenter för Microsoft 365** väljer **du Grupper** i det vänstra navigeringsfältet och sedan **Grupper.**</span><span class="sxs-lookup"><span data-stu-id="6d2e6-129">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="6d2e6-130">Välj **Lägg till en grupp**.</span><span class="sxs-lookup"><span data-stu-id="6d2e6-130">Select **Add a group**.</span></span>
3. <span data-ttu-id="6d2e6-131">I fönstret **Välj en grupptyp** väljer **du Säkerhet** och sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="6d2e6-131">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="6d2e6-132">I **fönstret Konfigurera grunderna väljer** du **Skapa grupp och** sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="6d2e6-132">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="6d2e6-133">Skriv **GlobalAdmins** **i fönstret** Granska och slutför tilläggen av gruppen och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="6d2e6-133">In the **Review and finish adding group** pane, enter **GlobalAdmins**, and then select **Next**.</span></span>
7. <span data-ttu-id="6d2e6-134">I listan över grupper väljer du **gruppen GlobalAdmins.**</span><span class="sxs-lookup"><span data-stu-id="6d2e6-134">In the list of groups, select the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="6d2e6-135">I fönstret **GlobalAdmins** väljer du **Members** och sedan **Visa alla och hanterar medlemmar.**</span><span class="sxs-lookup"><span data-stu-id="6d2e6-135">In the **GlobalAdmins** pane, select **Members**, and then select **View all and manage members**.</span></span>
9. <span data-ttu-id="6d2e6-136">I fönstret **GlobalAdmins** väljer du **Lägg** till medlemmar , väljer **DedicatedAdmin-kontot** och ditt globala administratörskonto och väljer **sedan Spara**  >    >  **Stäng Stäng.**</span><span class="sxs-lookup"><span data-stu-id="6d2e6-136">In the **GlobalAdmins** pane, select **Add members**, select the **DedicatedAdmin** account and your global admin account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="6d2e6-137">Skapa sedan villkorsstyrda åtkomstprinciper för att kräva multifaktorautentisering för globala administratörskonton och för att neka autentisering om inloggningsrisken är medium eller hög.</span><span class="sxs-lookup"><span data-stu-id="6d2e6-137">Next, create conditional access policies to require multi-factor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="6d2e6-138">Den här första principen kräver att alla globala administratörskonton använder MFA.</span><span class="sxs-lookup"><span data-stu-id="6d2e6-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="6d2e6-139">På en ny flik i webbläsaren går du till [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="6d2e6-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="6d2e6-140">Klicka på **Villkorsstyrd åtkomst för Azure Active**  >    >  **Directory-säkerhet.**</span><span class="sxs-lookup"><span data-stu-id="6d2e6-140">Click **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="6d2e6-141">I fönstret **Villkorsstyrd åtkomst –** Principer väljer du **Baslinjeprincip: Kräv MFA för administratörer (förhandsversion).**</span><span class="sxs-lookup"><span data-stu-id="6d2e6-141">In the **Conditional access – Policies** pane, select **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="6d2e6-142">I fönstret **Originalplansprincip** väljer du **Använd princip direkt > Spara**.</span><span class="sxs-lookup"><span data-stu-id="6d2e6-142">In the **Baseline policy** pane, select **Use policy immediately > Save**.</span></span>

<span data-ttu-id="6d2e6-143">Den här andra principen blockerar åtkomst till autentisering av globalt administratörskonto när inloggningsrisken är medium eller hög.</span><span class="sxs-lookup"><span data-stu-id="6d2e6-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="6d2e6-144">I fönstret **Villkorsstyrd åtkomst –** Principer väljer du **Ny princip.**</span><span class="sxs-lookup"><span data-stu-id="6d2e6-144">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
2. <span data-ttu-id="6d2e6-145">I fönstret **Nytt** anger du **Globala administratörer** i **Namn.**</span><span class="sxs-lookup"><span data-stu-id="6d2e6-145">In the **New** pane, enter **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="6d2e6-146">I avsnittet **Uppgifter** väljer du **Användare och grupper.**</span><span class="sxs-lookup"><span data-stu-id="6d2e6-146">In the **Assignments** section, select **Users and groups**.</span></span>
4. <span data-ttu-id="6d2e6-147">På fliken **Inkludera** i fönstret **Användare och grupper väljer** du Välj användare och grupper **Användare** och  >  **grupper**  >  **Välj**.</span><span class="sxs-lookup"><span data-stu-id="6d2e6-147">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
5. <span data-ttu-id="6d2e6-148">I fönstret **Markera** väljer du **gruppen GlobalAdmins** och väljer sedan **Select**  >  **Done**.</span><span class="sxs-lookup"><span data-stu-id="6d2e6-148">In the **Select** pane, select the **GlobalAdmins** group, and then select **Select** > **Done**.</span></span>
6. <span data-ttu-id="6d2e6-149">I avsnittet **Uppgifter** väljer du **Villkor**.</span><span class="sxs-lookup"><span data-stu-id="6d2e6-149">In the **Assignments** section, select **Conditions**.</span></span>
7. <span data-ttu-id="6d2e6-150">I fönstret **Villkor** väljer du **Inloggningsrisk**  , väljer Ja för Konfigurera , väljer **Hög** och **Medium** och sedan **Välj** och **klar**. </span><span class="sxs-lookup"><span data-stu-id="6d2e6-150">In the **Conditions** pane, select **Sign-in risk**, select **Yes** for **Configure**, select **High** and **Medium**, and then select **Select** and **Done**.</span></span>
8. <span data-ttu-id="6d2e6-151">I avsnittet **Access-kontroller** i **fönstret Nytt** väljer du **Tilldela**.</span><span class="sxs-lookup"><span data-stu-id="6d2e6-151">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="6d2e6-152">I fönstret **Bevilja** väljer du **Blockera åtkomst** och sedan **Välj**.</span><span class="sxs-lookup"><span data-stu-id="6d2e6-152">In the **Grant** pane, select **Block access**, and then select **Select**.</span></span>
10. <span data-ttu-id="6d2e6-153">I fönstret **Nytt** väljer du **På** för **Aktivera princip** och sedan **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="6d2e6-153">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="6d2e6-154">Stäng **flikarna Azure Portal** och **Administrationscenter för Microsoft 365.**</span><span class="sxs-lookup"><span data-stu-id="6d2e6-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="6d2e6-155">Testa den första principen genom att logga ut och logga in med DedicatedAdmin-kontot.</span><span class="sxs-lookup"><span data-stu-id="6d2e6-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="6d2e6-156">Du bör uppmanas att konfigurera MFA.</span><span class="sxs-lookup"><span data-stu-id="6d2e6-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="6d2e6-157">Det visar att den första principen används.</span><span class="sxs-lookup"><span data-stu-id="6d2e6-157">This demonstrates that the first policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="6d2e6-158">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="6d2e6-158">Next step</span></span>

<span data-ttu-id="6d2e6-159">Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="6d2e6-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d2e6-160">Se även</span><span class="sxs-lookup"><span data-stu-id="6d2e6-160">See also</span></span>

[<span data-ttu-id="6d2e6-161">Identitetsöversikt</span><span class="sxs-lookup"><span data-stu-id="6d2e6-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="6d2e6-162">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="6d2e6-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="6d2e6-163">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="6d2e6-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="6d2e6-164">Dokumentation om Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="6d2e6-164">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)