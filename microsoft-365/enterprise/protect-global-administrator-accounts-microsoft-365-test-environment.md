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
ms.openlocfilehash: fff09ca41ff0b648d46b5c33f753affc01242264
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695188"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="7d5c8-103">Skydda globala administratörs konton i test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="7d5c8-103">Protect global administrator accounts in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="7d5c8-104">*Den här test laboratorie guiden kan endast användas för test miljöer med Microsoft 365 för företags nätverk.*</span><span class="sxs-lookup"><span data-stu-id="7d5c8-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="7d5c8-105">Du kan förhindra digitala attacker på din organisation genom att se till att dina administratörs konton är så säkra som möjligt.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="7d5c8-106">I den här artikeln beskrivs hur du använder principer för villkorsstyrd åtkomst i Azure Active Directory (Azure AD) för att skydda globala administratörs konton.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="7d5c8-107">Det finns två faser för att skydda globala administratörs konton i test miljön för Microsoft 365 för företag:</span><span class="sxs-lookup"><span data-stu-id="7d5c8-107">There are two phases to protecting global administrator accounts in your Microsoft 365 for enterprise test environment:</span></span>

1.  <span data-ttu-id="7d5c8-108">Skapa test miljön för Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-108">Create the Microsoft 365 for enterprise test environment.</span></span>
2.  <span data-ttu-id="7d5c8-109">Skydda ditt globala administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-109">Protect your dedicated global administrator account.</span></span>

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="7d5c8-111">Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med testlabbguider för Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="7d5c8-112">Fas 1: bygga ut test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="7d5c8-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="7d5c8-113">Om du bara vill testa globalt administratörs konto skydd på ett enkelt sätt med minimi kraven följer du anvisningarna i [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="7d5c8-113">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="7d5c8-114">Om du vill testa det globala administratörs konto skyddet i ett simulerat företag följer du anvisningarna i [vidarekoppling](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="7d5c8-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7d5c8-115">Testning av globalt administratörs konto kräver inte den simulerade företags test miljön, som innehåller ett simulerat intranät som är kopplat till Internet-och katalogs-synkronisering för en Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="7d5c8-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="7d5c8-116">Det finns här som ett alternativ för att du ska kunna testa det globala administratörs konto skyddet och experimentera med det i en miljö som representerar en typisk organisation.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="7d5c8-117">Fas 2: konfigurera principer för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="7d5c8-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="7d5c8-118">Först skapar du ett nytt användar konto som global administratör.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="7d5c8-119">Öppna [administrations centret för Microsoft 365](https://admin.microsoft.com/)på en separat flik.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="7d5c8-120">Klicka på **användare > aktiva användare**och klicka sedan på **Lägg till en användare**.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-120">Click **Users > Active users**, and then click **Add a user**.</span></span>
3. <span data-ttu-id="7d5c8-121">I fönstret **Lägg till användare** skriver du **DedicatedAdmin** i **förnamn**, **visnings namn**och **användar namn**.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-121">In the **Add user** pane, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
4. <span data-ttu-id="7d5c8-122">Klicka på **lösen ord**, klicka på **Låt mig skapa lösen ordet**och skriv sedan ett starkt lösen ord.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-122">Click **Password**, click **Let me create the password**, and then type a strong password.</span></span> <span data-ttu-id="7d5c8-123">Spela in lösen ordet för det nya kontot på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="7d5c8-124">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-124">Click **Next**.</span></span>
6. <span data-ttu-id="7d5c8-125">I fönstret **tilldela produkt licenser** väljer du **Microsoft 365 E5**och klickar sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-125">In the **Assign product licenses** pane, select **Microsoft 365 E5**, and then click **Next**.</span></span>
7. <span data-ttu-id="7d5c8-126">I fönstret **valfria inställningar** klickar du på **roller**och väljer sedan **Administratörs Center åtkomst** och **Global administratör**. Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-126">In the **Optional settings** pane, click **Roles**, and then select **Admin center access** and **Global admin**. Click **Next**.</span></span>
8. <span data-ttu-id="7d5c8-127">I fönstret **du är nästan klar klickar du** på **Lägg till**och sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-127">On the **You're almost done** pane, click **Finish adding**, and then click **Close**.</span></span>

<span data-ttu-id="7d5c8-128">Skapa sedan en ny grupp med namnet GlobalAdmins och Lägg till DedicatedAdmin-kontot i den.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="7d5c8-129">Klicka på **grupper** i det vänstra navigerings fältet på fliken **administrations center för Microsoft 365** och klicka sedan på **grupper**.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-129">On the **Microsoft 365 admin center** tab, click **Groups** in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="7d5c8-130">Klicka på **Lägg till en grupp**.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-130">Click **Add a group**.</span></span>
3. <span data-ttu-id="7d5c8-131">I fönstret **Välj en grupptyp** väljer du **säkerhet**och sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-131">In the **Choose a group type** pane, select **Security**, and then click **Next**.</span></span>
4. <span data-ttu-id="7d5c8-132">Klicka på **Skapa grupp**i fönstret **Konfigurera grunderna** och klicka sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-132">In the **Set up the basics** pane, click **Create group**, and then click **Close**.</span></span>
5. <span data-ttu-id="7d5c8-133">Skriv **GlobalAdmins**i fönstret **Granska och slutför tillägg** och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-133">In the **Review and finish adding group** pane, type **GlobalAdmins**, and then click **Next**.</span></span>
7. <span data-ttu-id="7d5c8-134">I listan med grupper klickar du på gruppen **GlobalAdmins** .</span><span class="sxs-lookup"><span data-stu-id="7d5c8-134">In the list of groups, click the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="7d5c8-135">I fönstret **GlobalAdmins** klickar du på **medlemmar**och sedan på **Visa alla och hantera medlemmar**.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-135">In the **GlobalAdmins** pane, click **Members**, and then click **View all and manage members**.</span></span>
9. <span data-ttu-id="7d5c8-136">I fönstret **GlobalAdmins** klickar du på **Lägg till medlemmar**, väljer **DedicatedAdmin** -konto och ditt globala administratörs konto och klickar sedan på **Spara > Stäng > Stäng**.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-136">In the **GlobalAdmins** pane, click **Add members**, select the **DedicatedAdmin** account and your global admin account, and then click **Save > Close > Close**.</span></span>

<span data-ttu-id="7d5c8-137">Skapa sedan principer för villkorsstyrd åtkomst för att kräva multifaktorautentisering för globala administratörs konton och för att neka identifiering om inloggnings risken är medel eller hög.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-137">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="7d5c8-138">Den första principen kräver att MFA används för alla globala administratörs konton.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="7d5c8-139">Gå till på en ny flik i webbläsaren [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="7d5c8-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="7d5c8-140">Klicka på **> säkerhets > villkorlig åtkomst för Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-140">Click **Azure Active Directory > Security > Conditional Access**.</span></span>
3. <span data-ttu-id="7d5c8-141">I fönstret **villkorlig åtkomst – principer** klickar du på **bas linje princip: Kräv MFA för administratörer (för hands version)**.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-141">In the **Conditional access – Policies** pane, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="7d5c8-142">I fönstret **rikt linje** klickar du på **använd princip omedelbart > Spara**.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-142">In the **Baseline policy** pane, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="7d5c8-143">Denna andra princip blockerar åtkomst till global administratörs konto identifiering när inloggnings risken är medel eller hög.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="7d5c8-144">Klicka på **ny princip**i fönstret **villkorlig åtkomst – policys** .</span><span class="sxs-lookup"><span data-stu-id="7d5c8-144">In the **Conditional access – Policies** pane, click **New policy**.</span></span>
2. <span data-ttu-id="7d5c8-145">I fönstret **ny** skriver du **globala administratörer** i **namn**.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-145">In the **New** pane, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="7d5c8-146">Klicka på **användare och grupper**i avsnittet **uppgifter** .</span><span class="sxs-lookup"><span data-stu-id="7d5c8-146">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="7d5c8-147">På fliken **Inkludera** i fönstret **användare och grupper** klickar du på **Välj användare och grupper > användare och grupper > välja**.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-147">On the **Include** tab of the **Users and groups** pane, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="7d5c8-148">Klicka på gruppen **GlobalAdmins** i fönstret **Välj** och klicka sedan på **Välj > klar**.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-148">In the **Select** pane, click the **GlobalAdmins** group, and then click **Select > Done**.</span></span>
6. <span data-ttu-id="7d5c8-149">Klicka på **villkor**i avsnittet **uppgifter** .</span><span class="sxs-lookup"><span data-stu-id="7d5c8-149">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="7d5c8-150">Klicka på **inloggnings risk**i fönstret **villkor** , klicka på **Ja** för att **Konfigurera**, klicka på **hög** och **medium**och klicka sedan på **Välj** och **klar**.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-150">In the **Conditions** pane, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="7d5c8-151">Klicka på **Tillåt**i avsnittet **Access-kontroller** i fönstret **nytt** .</span><span class="sxs-lookup"><span data-stu-id="7d5c8-151">In the **Access controls** section of the **New** pane, click **Grant**.</span></span>
9. <span data-ttu-id="7d5c8-152">I fönstret **bidrag** klickar du på **blockera åtkomst**och sedan på **Välj**.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-152">In the **Grant** pane, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="7d5c8-153">I fönstret **ny** klickar du **på** för att **aktivera principer**och klickar sedan på **skapa**.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-153">In the **New** pane, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="7d5c8-154">Stäng flikarna **Azure Portal** och **Microsoft 365 administrations Center** .</span><span class="sxs-lookup"><span data-stu-id="7d5c8-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="7d5c8-155">Om du vill testa den första principen loggar du ut och loggar in med DedicatedAdmin-kontot.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="7d5c8-156">Du bör uppmanas att konfigurera MFA.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="7d5c8-157">Det visar att den första principen tillämpas.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-157">This demonstrates that the first policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="7d5c8-158">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="7d5c8-158">Next step</span></span>

<span data-ttu-id="7d5c8-159">Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="7d5c8-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="7d5c8-160">Se även</span><span class="sxs-lookup"><span data-stu-id="7d5c8-160">See also</span></span>

[<span data-ttu-id="7d5c8-161">Identitets översikt</span><span class="sxs-lookup"><span data-stu-id="7d5c8-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="7d5c8-162">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="7d5c8-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="7d5c8-163">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="7d5c8-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="7d5c8-164">Microsoft 365 för företags dokumentation</span><span class="sxs-lookup"><span data-stu-id="7d5c8-164">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
