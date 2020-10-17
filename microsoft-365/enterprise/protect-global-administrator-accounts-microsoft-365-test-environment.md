---
title: Skydda globala administratörs konton i test miljön för Microsoft 365 för företag
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
description: Använd de här stegen för att skydda globala administratörs konton i test miljön för Microsoft 365 för företag.
ms.openlocfilehash: 1ae04e4761ed86e087e647464ad522466ed6abef
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487642"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="fe038-103">Skydda globala administratörs konton i test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="fe038-103">Protect global administrator accounts in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="fe038-104">*Den här test laboratorie guiden kan endast användas för test miljöer med Microsoft 365 för företags nätverk.*</span><span class="sxs-lookup"><span data-stu-id="fe038-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="fe038-105">Du kan förhindra digitala attacker på din organisation genom att se till att dina administratörs konton är så säkra som möjligt.</span><span class="sxs-lookup"><span data-stu-id="fe038-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> 

<span data-ttu-id="fe038-106">I den här artikeln beskrivs hur du använder principer för villkorsstyrd åtkomst i Azure Active Directory (Azure AD) för att skydda globala administratörs konton.</span><span class="sxs-lookup"><span data-stu-id="fe038-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="fe038-107">Att skydda globala administratörs konton i test miljön för Microsoft 365 för företag inbegriper två faser:</span><span class="sxs-lookup"><span data-stu-id="fe038-107">Protecting global administrator accounts in your Microsoft 365 for enterprise test environment involves two phases:</span></span>
- [<span data-ttu-id="fe038-108">Fas 1: bygga ut test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="fe038-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="fe038-109">Fas 2: konfigurera principer för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="fe038-109">Phase 2: Configure conditional access policies</span></span>](#phase-2-configure-conditional-access-policies)

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="fe038-111">Om du vill visa en visuell karta till alla artiklar i gruppen Microsoft 365 för Enterprise-testlabbet går du till [Microsoft 365 för Enterprise Test Lab-guide](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="fe038-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="fe038-112">Fas 1: bygga ut test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="fe038-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="fe038-113">Om du vill testa det globala administratörs konto skyddet på ett billigt sätt med minimi kraven följer du anvisningarna i [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="fe038-113">If you want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="fe038-114">Om du vill testa det globala administratörs konto skyddet i ett simulerat företag följer du anvisningarna i [vidarekoppling](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="fe038-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="fe038-115">Testning av globalt administratörs konto kräver inte den simulerade företags test miljön, som innehåller ett simulerat intranät som är kopplat till Internet-och katalogs-synkronisering för en Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="fe038-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="fe038-116">Det finns här som ett alternativ för att du ska kunna testa det globala administratörs konto skyddet och experimentera med det i en miljö som representerar en typisk organisation.</span><span class="sxs-lookup"><span data-stu-id="fe038-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="fe038-117">Fas 2: konfigurera principer för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="fe038-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="fe038-118">Först skapar du ett nytt användar konto som global administratör.</span><span class="sxs-lookup"><span data-stu-id="fe038-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="fe038-119">Öppna [administrations centret för Microsoft 365](https://admin.microsoft.com/)på en separat flik.</span><span class="sxs-lookup"><span data-stu-id="fe038-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="fe038-120">Välj **användare**  >  **aktiva användare**och välj sedan **Lägg till en användare**.</span><span class="sxs-lookup"><span data-stu-id="fe038-120">Select **Users** > **Active users**, and then select **Add a user**.</span></span>
3. <span data-ttu-id="fe038-121">I fönstret **Lägg till användare** anger du **DedicatedAdmin** i rutorna **förnamn**, **visnings namn**och **användar namn** .</span><span class="sxs-lookup"><span data-stu-id="fe038-121">In the **Add user** pane, enter **DedicatedAdmin** in the **First name**, **Display name**, and **Username** boxes.</span></span>
4. <span data-ttu-id="fe038-122">Välj **lösen ord**, Välj **Låt mig skapa lösen ordet**och ange sedan ett starkt lösen ord.</span><span class="sxs-lookup"><span data-stu-id="fe038-122">Select **Password**, select **Let me create the password**, and then enter a strong password.</span></span> <span data-ttu-id="fe038-123">Spela in lösen ordet för det nya kontot på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="fe038-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="fe038-124">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="fe038-124">Select **Next**.</span></span>
6. <span data-ttu-id="fe038-125">I fönstret **tilldela produkt licenser** väljer du **Microsoft 365 E5**och sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="fe038-125">In the **Assign product licenses** pane, select **Microsoft 365 E5**, and then select **Next**.</span></span>
7. <span data-ttu-id="fe038-126">I fönstret **valfria inställningar** väljer du den **Roles**  >  **Admin center access**  >  **globala administratörs**rollen för administratörer  >  **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="fe038-126">In the **Optional settings** pane, select **Roles** > **Admin center access** > **Global admin** > **Next**.</span></span>
8. <span data-ttu-id="fe038-127">I fönstret **du är nästan klar väljer du** **Lägg till**och sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="fe038-127">On the **You're almost done** pane, select **Finish adding**, and then select **Close**.</span></span>

<span data-ttu-id="fe038-128">Skapa sedan en ny grupp med namnet GlobalAdmins och Lägg till DedicatedAdmin-kontot i den.</span><span class="sxs-lookup"><span data-stu-id="fe038-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="fe038-129">Gå till fliken **administrations Center för Microsoft 365** , Välj **grupper** i det vänstra navigerings fältet och välj sedan **grupper**.</span><span class="sxs-lookup"><span data-stu-id="fe038-129">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="fe038-130">Välj **Lägg till en grupp**.</span><span class="sxs-lookup"><span data-stu-id="fe038-130">Select **Add a group**.</span></span>
3. <span data-ttu-id="fe038-131">I fönstret **Välj en grupptyp** väljer du **säkerhet**och sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="fe038-131">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="fe038-132">I fönstret **Konfigurera grunderna väljer du** **Skapa grupp**och sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="fe038-132">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="fe038-133">Ange **GlobalAdmins**i fönstret **Granska och slutför** och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="fe038-133">In the **Review and finish adding group** pane, enter **GlobalAdmins**, and then select **Next**.</span></span>
7. <span data-ttu-id="fe038-134">I listan med grupper väljer du gruppen **GlobalAdmins** .</span><span class="sxs-lookup"><span data-stu-id="fe038-134">In the list of groups, select the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="fe038-135">I fönstret **GlobalAdmins** väljer du **medlemmar**och sedan **Visa alla och hantera medlemmar**.</span><span class="sxs-lookup"><span data-stu-id="fe038-135">In the **GlobalAdmins** pane, select **Members**, and then select **View all and manage members**.</span></span>
9. <span data-ttu-id="fe038-136">I fönstret **GlobalAdmins** väljer du **Lägg till medlemmar**, väljer **DedicatedAdmin** -konto och ditt globala administratörs konto och väljer sedan **Spara**  >  **Close**  >  **Close**.</span><span class="sxs-lookup"><span data-stu-id="fe038-136">In the **GlobalAdmins** pane, select **Add members**, select the **DedicatedAdmin** account and your global admin account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="fe038-137">Skapa sedan principer för villkorsstyrd åtkomst för att kräva multifaktorautentisering för globala administratörs konton och för att neka identifiering om inloggnings risken är medel eller hög.</span><span class="sxs-lookup"><span data-stu-id="fe038-137">Next, create conditional access policies to require multi-factor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="fe038-138">Den första principen kräver att MFA används för alla globala administratörs konton.</span><span class="sxs-lookup"><span data-stu-id="fe038-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="fe038-139">Gå till på en ny flik i webbläsaren [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="fe038-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="fe038-140">Klicka på villkorlig åtkomst för **Azure Active Directory**-  >  **säkerhet**  >  **Conditional Access**.</span><span class="sxs-lookup"><span data-stu-id="fe038-140">Click **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="fe038-141">I fönstret **villkorlig åtkomst – principer** väljer du **original princip: Kräv MFA för administratörer (för hands version)**.</span><span class="sxs-lookup"><span data-stu-id="fe038-141">In the **Conditional access – Policies** pane, select **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="fe038-142">I fönstret **rikt linje** väljer du **använd policy omedelbart > Spara**.</span><span class="sxs-lookup"><span data-stu-id="fe038-142">In the **Baseline policy** pane, select **Use policy immediately > Save**.</span></span>

<span data-ttu-id="fe038-143">Denna andra princip blockerar åtkomst till global administratörs konto identifiering när inloggnings risken är medel eller hög.</span><span class="sxs-lookup"><span data-stu-id="fe038-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="fe038-144">I fönstret **villkorlig åtkomst – principer** väljer du **ny princip**.</span><span class="sxs-lookup"><span data-stu-id="fe038-144">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
2. <span data-ttu-id="fe038-145">Ange **globala administratörer** i **namn**i fönstret **nytt** .</span><span class="sxs-lookup"><span data-stu-id="fe038-145">In the **New** pane, enter **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="fe038-146">Välj **användare och grupper**i avsnittet **uppgifter** .</span><span class="sxs-lookup"><span data-stu-id="fe038-146">In the **Assignments** section, select **Users and groups**.</span></span>
4. <span data-ttu-id="fe038-147">På fliken **Inkludera** i fönstret **användare och grupper** väljer du **Välj användare och grupper**som  >  **användare och grupper**  >  **väljer**.</span><span class="sxs-lookup"><span data-stu-id="fe038-147">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
5. <span data-ttu-id="fe038-148">I fönstret **Välj** väljer du gruppen **GlobalAdmins** och väljer sedan **Välj**  >  **klar**.</span><span class="sxs-lookup"><span data-stu-id="fe038-148">In the **Select** pane, select the **GlobalAdmins** group, and then select **Select** > **Done**.</span></span>
6. <span data-ttu-id="fe038-149">Välj **villkor**i avsnittet **uppgifter** .</span><span class="sxs-lookup"><span data-stu-id="fe038-149">In the **Assignments** section, select **Conditions**.</span></span>
7. <span data-ttu-id="fe038-150">I fönstret **villkor** väljer du **inloggnings risker**, väljer **Ja** för **konfigurering**, väljer **hög** och **medium**och väljer sedan **Välj** och **klar**.</span><span class="sxs-lookup"><span data-stu-id="fe038-150">In the **Conditions** pane, select **Sign-in risk**, select **Yes** for **Configure**, select **High** and **Medium**, and then select **Select** and **Done**.</span></span>
8. <span data-ttu-id="fe038-151">I avsnittet **Access Controls** i fönstret **ny** väljer du **Grant**.</span><span class="sxs-lookup"><span data-stu-id="fe038-151">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="fe038-152">I fönstret **bidrag** väljer du **blockera åtkomst**och väljer sedan **Välj**.</span><span class="sxs-lookup"><span data-stu-id="fe038-152">In the **Grant** pane, select **Block access**, and then select **Select**.</span></span>
10. <span data-ttu-id="fe038-153">I fönstret **nytt** väljer du **på** för **att aktivera principer**och väljer sedan **skapa**.</span><span class="sxs-lookup"><span data-stu-id="fe038-153">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="fe038-154">Stäng flikarna **Azure Portal** och **Microsoft 365 administrations Center** .</span><span class="sxs-lookup"><span data-stu-id="fe038-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="fe038-155">Om du vill testa den första principen loggar du ut och loggar in med DedicatedAdmin-kontot.</span><span class="sxs-lookup"><span data-stu-id="fe038-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="fe038-156">Du bör uppmanas att konfigurera MFA.</span><span class="sxs-lookup"><span data-stu-id="fe038-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="fe038-157">Det visar att den första principen tillämpas.</span><span class="sxs-lookup"><span data-stu-id="fe038-157">This demonstrates that the first policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="fe038-158">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="fe038-158">Next step</span></span>

<span data-ttu-id="fe038-159">Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="fe038-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="fe038-160">Se även</span><span class="sxs-lookup"><span data-stu-id="fe038-160">See also</span></span>

[<span data-ttu-id="fe038-161">Identitets översikt</span><span class="sxs-lookup"><span data-stu-id="fe038-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="fe038-162">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="fe038-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="fe038-163">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="fe038-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="fe038-164">Microsoft 365 för företags dokumentation</span><span class="sxs-lookup"><span data-stu-id="fe038-164">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
