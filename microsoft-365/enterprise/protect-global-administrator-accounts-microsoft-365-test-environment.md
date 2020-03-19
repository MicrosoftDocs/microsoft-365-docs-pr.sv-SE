---
title: Skydda globala administratörskonton i testmiljön för Microsoft 365 Enterprise
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
description: Så här skyddar du globala administratörskonton i microsoft 365 Enterprise-testmiljön.
ms.openlocfilehash: 9452ac7bafec416833ece9cbcb645bd7eeee21cc
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42811447"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="f80c0-103">Skydda globala administratörskonton i testmiljön för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f80c0-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="f80c0-104">*Den här testlabbet-guiden kan endast användas för Microsoft 365 Enterprise-testmiljöer.*</span><span class="sxs-lookup"><span data-stu-id="f80c0-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="f80c0-105">Du kan förhindra digitala attacker mot din organisation genom att se till att administratörskontona är så säkra som möjligt.</span><span class="sxs-lookup"><span data-stu-id="f80c0-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="f80c0-106">I den här artikeln beskrivs hur du använder principer för villkorlig åtkomst i Azure Active Directory (Azure AD) för att skydda globala administratörskonton.</span><span class="sxs-lookup"><span data-stu-id="f80c0-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="f80c0-107">Det finns två faser för att skydda globala administratörskonton i microsoft 365 Enterprise-testmiljön:</span><span class="sxs-lookup"><span data-stu-id="f80c0-107">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="f80c0-108">Skapa testmiljön för Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f80c0-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="f80c0-109">Skydda ditt dedikerade globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="f80c0-109">Protect your dedicated global administrator account.</span></span>

![Testlabbguider för Microsoft-molnet](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="f80c0-111">Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill ha en visuell karta till alla artiklar i Microsoft 365 Enterprise Test Lab Guide-stacken.</span><span class="sxs-lookup"><span data-stu-id="f80c0-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="f80c0-112">Fas 1: Bygg ut testmiljön för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f80c0-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="f80c0-113">Om du bara vill testa globalt administratörskontoskydd på ett lättviktssätt med minimikraven följer du instruktionerna i [Lightweight base-konfigurationen](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="f80c0-113">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="f80c0-114">Om du vill testa globalt administratörskontoskydd i ett simulerat företag följer du instruktionerna i [Direktautentisering](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="f80c0-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f80c0-115">Testning av globalt administratörskontoskydd kräver inte den simulerade företagstestmiljön, som innehåller ett simulerat intranät som är anslutet till Internet och katalogsynkronisering för en AD DS (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="f80c0-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="f80c0-116">Det finns här som ett alternativ så att du kan testa globalt administratörskontoskydd och experimentera med det i en miljö som representerar en typisk organisation.</span><span class="sxs-lookup"><span data-stu-id="f80c0-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="f80c0-117">Fas 2: Konfigurera principer för villkorlig åtkomst</span><span class="sxs-lookup"><span data-stu-id="f80c0-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="f80c0-118">Skapa först ett nytt användarkonto som en dedikerad global administratör.</span><span class="sxs-lookup"><span data-stu-id="f80c0-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="f80c0-119">Öppna [administrationscentret för Microsoft 365 på](https://admin.microsoft.com/)en separat flik .</span><span class="sxs-lookup"><span data-stu-id="f80c0-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="f80c0-120">Klicka på **Användare > Aktiva användare**och klicka sedan på Lägg till en **användare**.</span><span class="sxs-lookup"><span data-stu-id="f80c0-120">Click **Users > Active users**, and then click **Add a user**.</span></span>
3. <span data-ttu-id="f80c0-121">Skriv **DedicatedAdmin** i **Förnamn**, **Visningsnamn**och **Användarnamn**i fönstret **Lägg till** användare .</span><span class="sxs-lookup"><span data-stu-id="f80c0-121">In the **Add user** pane, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
4. <span data-ttu-id="f80c0-122">Klicka på **Lösenord,** klicka på **Låt mig skapa lösenordet**och skriv sedan ett starkt lösenord.</span><span class="sxs-lookup"><span data-stu-id="f80c0-122">Click **Password**, click **Let me create the password**, and then type a strong password.</span></span> <span data-ttu-id="f80c0-123">Registrera lösenordet för det nya kontot på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="f80c0-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="f80c0-124">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="f80c0-124">Click **Next**.</span></span>
6. <span data-ttu-id="f80c0-125">I fönstret **Tilldela produktlicenser** väljer du **Microsoft 365 E5** eller **Office 365 E5**och klickar sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="f80c0-125">In the **Assign product licenses** pane, select **Microsoft 365 E5** or **Office 365 E5**, and then click **Next**.</span></span>
7. <span data-ttu-id="f80c0-126">I fönstret **Valfria inställningar** klickar du på **Roller**och väljer sedan **Åtkomst till administrationscenter** och **Global administratör**. Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="f80c0-126">In the **Optional settings** pane, click **Roles**, and then select **Admin center access** and **Global admin**. Click **Next**.</span></span>
8. <span data-ttu-id="f80c0-127">Klicka på Slutför att lägga **till**i fönstret Du är **nästan klar** och klicka sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="f80c0-127">On the **You're almost done** pane, click **Finish adding**, and then click **Close**.</span></span>

<span data-ttu-id="f80c0-128">Skapa sedan en ny grupp med namnet GlobalAdmins och lägg till kontot DedicatedAdmin i den.</span><span class="sxs-lookup"><span data-stu-id="f80c0-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="f80c0-129">Klicka på **Grupper** i den vänstra navigeringen på fliken **Administrationscenter i Microsoft 365** och klicka sedan på **Grupper**.</span><span class="sxs-lookup"><span data-stu-id="f80c0-129">On the **Microsoft 365 admin center** tab, click **Groups** in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="f80c0-130">Klicka på **Lägg till en grupp**.</span><span class="sxs-lookup"><span data-stu-id="f80c0-130">Click **Add a group**.</span></span>
3. <span data-ttu-id="f80c0-131">I fönstret **Välj grupptyp** väljer du **Säkerhet**och klickar sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="f80c0-131">In the **Choose a group type** pane, select **Security**, and then click **Next**.</span></span>
4. <span data-ttu-id="f80c0-132">Klicka på **Skapa grupp**i fönstret **Konfigurera grunderna** och klicka sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="f80c0-132">In the **Set up the basics** pane, click **Create group**, and then click **Close**.</span></span>
5. <span data-ttu-id="f80c0-133">Skriv **GlobalAdmins**i **gruppfönstret Granska och avsluta** och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="f80c0-133">In the **Review and finish adding group** pane, type **GlobalAdmins**, and then click **Next**.</span></span>
7. <span data-ttu-id="f80c0-134">Klicka på gruppen **GlobalAdmins** i listan över grupper.</span><span class="sxs-lookup"><span data-stu-id="f80c0-134">In the list of groups, click the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="f80c0-135">Klicka på **Medlemmar**i fönstret **GlobalAdmins** och klicka sedan på **Visa alla och hantera medlemmar**.</span><span class="sxs-lookup"><span data-stu-id="f80c0-135">In the **GlobalAdmins** pane, click **Members**, and then click **View all and manage members**.</span></span>
9. <span data-ttu-id="f80c0-136">Klicka på **Lägg till medlemmar**i fönstret **GlobalAdmins,** välj **kontot DedicatedAdmin** och ditt globala administratörskonto och klicka sedan på **Spara > Stäng > Stäng**.</span><span class="sxs-lookup"><span data-stu-id="f80c0-136">In the **GlobalAdmins** pane, click **Add members**, select the **DedicatedAdmin** account and your global admin account, and then click **Save > Close > Close**.</span></span>

<span data-ttu-id="f80c0-137">Skapa sedan principer för villkorlig åtkomst för att kräva multifaktorautentisering för globala administratörskonton och för att neka autentisering om inloggningsrisken är medelhög eller hög.</span><span class="sxs-lookup"><span data-stu-id="f80c0-137">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="f80c0-138">Den här första principen kräver att alla globala administratörskonton använder MFA.</span><span class="sxs-lookup"><span data-stu-id="f80c0-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="f80c0-139">Gå till [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="f80c0-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="f80c0-140">Klicka på **Azure Active Directory > Security > Conditional Access**.</span><span class="sxs-lookup"><span data-stu-id="f80c0-140">Click **Azure Active Directory > Security > Conditional Access**.</span></span>
3. <span data-ttu-id="f80c0-141">I fönstret **Villkorlig åtkomst – Principer** klickar du på **Baslinjeprincip: Kräv MFA för administratörer (förhandsgranskning)**.</span><span class="sxs-lookup"><span data-stu-id="f80c0-141">In the **Conditional access – Policies** pane, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="f80c0-142">Klicka på Använd princip i principfönstret **originalplan** **direkt > Spara**.</span><span class="sxs-lookup"><span data-stu-id="f80c0-142">In the **Baseline policy** pane, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="f80c0-143">Den här andra principen blockerar åtkomst till global administratörskontoautentisering när inloggningsrisken är medelhög eller hög.</span><span class="sxs-lookup"><span data-stu-id="f80c0-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="f80c0-144">Klicka på **Ny princip**i fönstret Villkorlig åtkomst **– Principer** .</span><span class="sxs-lookup"><span data-stu-id="f80c0-144">In the **Conditional access – Policies** pane, click **New policy**.</span></span>
2. <span data-ttu-id="f80c0-145">Skriv **Globala administratörer** i **Namn**i fönstret **Nytt** .</span><span class="sxs-lookup"><span data-stu-id="f80c0-145">In the **New** pane, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="f80c0-146">Klicka på **Användare och grupper**i avsnittet **Tilldelningar** .</span><span class="sxs-lookup"><span data-stu-id="f80c0-146">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="f80c0-147">Klicka på Markera användare och grupper **> användare och grupper > Markera**på fliken **Inkludera** i fönstret Användare och **grupper.**</span><span class="sxs-lookup"><span data-stu-id="f80c0-147">On the **Include** tab of the **Users and groups** pane, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="f80c0-148">Klicka på gruppen **GlobalAdmins** i fönstret **Markera** och klicka sedan på **Markera > klar**.</span><span class="sxs-lookup"><span data-stu-id="f80c0-148">In the **Select** pane, click the **GlobalAdmins** group, and then click **Select > Done**.</span></span>
6. <span data-ttu-id="f80c0-149">Klicka på **Villkor**i avsnittet **Tilldelningar** .</span><span class="sxs-lookup"><span data-stu-id="f80c0-149">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="f80c0-150">Klicka på Logga **in-risk i**fönstret **Villkor,** klicka på **Ja** för **Konfigurera**, klicka på **Hög** och **Medel**och klicka sedan på **Markera** och **gjort**.</span><span class="sxs-lookup"><span data-stu-id="f80c0-150">In the **Conditions** pane, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="f80c0-151">Klicka på **Bevilja**i avsnittet **Access-kontroller** i fönstret **Nytt** .</span><span class="sxs-lookup"><span data-stu-id="f80c0-151">In the **Access controls** section of the **New** pane, click **Grant**.</span></span>
9. <span data-ttu-id="f80c0-152">Klicka på Blockera **åtkomst**i **fönstret Bevilja** och klicka sedan på **Markera**.</span><span class="sxs-lookup"><span data-stu-id="f80c0-152">In the **Grant** pane, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="f80c0-153">Klicka på **På** för **att aktivera principen**i fönstret **Nytt** och klicka sedan på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="f80c0-153">In the **New** pane, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="f80c0-154">Stäng flikarna **i Azure-portalen** och **Microsoft 365 admin center.**</span><span class="sxs-lookup"><span data-stu-id="f80c0-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="f80c0-155">Om du vill testa den första principen loggar du ut och loggar in med kontot DedicatedAdmin.</span><span class="sxs-lookup"><span data-stu-id="f80c0-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="f80c0-156">Du bör uppmanas att konfigurera MFA.</span><span class="sxs-lookup"><span data-stu-id="f80c0-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="f80c0-157">Detta visar att den första principen tillämpas.</span><span class="sxs-lookup"><span data-stu-id="f80c0-157">This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="f80c0-158">Se steget [Skydda globala administratörskonton](identity-create-protect-global-admins.md#identity-global-admin) i identitetsfasen för information och länkar för att skydda dina globala administratörskonton i produktion.</span><span class="sxs-lookup"><span data-stu-id="f80c0-158">See the [Protect global administrator accounts](identity-create-protect-global-admins.md#identity-global-admin) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="f80c0-159">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="f80c0-159">Next step</span></span>

<span data-ttu-id="f80c0-160">Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) och funktioner i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="f80c0-160">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="f80c0-161">Se även</span><span class="sxs-lookup"><span data-stu-id="f80c0-161">See also</span></span>

[<span data-ttu-id="f80c0-162">Fas 2: Identitet</span><span class="sxs-lookup"><span data-stu-id="f80c0-162">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="f80c0-163">Testlaboratorikguider för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f80c0-163">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="f80c0-164">Distribution av Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f80c0-164">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="f80c0-165">Dokumentation från Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f80c0-165">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
