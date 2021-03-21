---
title: Tillbakaskrivning av lösenord i testmiljön för Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/22/2019
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
description: 'Sammanfattning: Konfigurera tillbakaskrivning av lösenord i testmiljön för Microsoft 365.'
ms.openlocfilehash: f1118c22ad1f65ea29bb14afacb7506a60d1fe1a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921486"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a><span data-ttu-id="72029-103">Tillbakaskrivning av lösenord i testmiljön för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="72029-103">Password writeback for your Microsoft 365 test environment</span></span>

<span data-ttu-id="72029-104">*Den här testlabbguiden kan endast användas för Microsoft 365 för företagstestmiljöer.*</span><span class="sxs-lookup"><span data-stu-id="72029-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="72029-105">Användare kan använda tillbakaskrivning av lösenord för att uppdatera sina lösenord via Azure Active Directory (Azure AD), som sedan replikeras till AD DS (Local Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="72029-105">Users can use password writeback to update their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="72029-106">Med tillbakaskrivning av lösenord behöver användarna inte uppdatera sina lösenord via den lokala AD DS där deras ursprungliga användarkonton lagras.</span><span class="sxs-lookup"><span data-stu-id="72029-106">With password writeback, users don't have to update their passwords through the on-premises AD DS where their original user accounts are stored.</span></span> <span data-ttu-id="72029-107">Detta hjälper roaming- eller fjärranvändare som inte har en fjärranslutning till sina lokala nätverk.</span><span class="sxs-lookup"><span data-stu-id="72029-107">This helps roaming or remote users who don't have a remote access connection to their on-premises network.</span></span>

<span data-ttu-id="72029-108">I den här artikeln beskrivs hur du konfigurerar Microsoft 365-testmiljön för återskrivning av lösenord.</span><span class="sxs-lookup"><span data-stu-id="72029-108">This article describes how to configure your Microsoft 365 test environment for password writeback.</span></span>

<span data-ttu-id="72029-109">Konfigurering av testmiljön för återställning av lösenord omfattar två faser:</span><span class="sxs-lookup"><span data-stu-id="72029-109">Configuring your test environment for password writeback involves two phases:</span></span>
- [<span data-ttu-id="72029-110">Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön</span><span class="sxs-lookup"><span data-stu-id="72029-110">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="72029-111">Fas 2: Aktivera tillbakaskrivning av lösenord för TESTLAB AD DS-domänen</span><span class="sxs-lookup"><span data-stu-id="72029-111">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>](#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)
  
![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="72029-113">En visuell karta till alla artiklar i Microsoft 365 testlabbguide-stacken för företag finns i Testlabbguide för [Microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)för företag.</span><span class="sxs-lookup"><span data-stu-id="72029-113">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="72029-114">Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön</span><span class="sxs-lookup"><span data-stu-id="72029-114">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="72029-115">Följ först anvisningarna i [Synkronisering av lösenordshash](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="72029-115">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span> <span data-ttu-id="72029-116">Den resulterande konfigurationen ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="72029-116">Your resulting configuration looks like this:</span></span>
  
![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="72029-118">Konfigurationen består av:</span><span class="sxs-lookup"><span data-stu-id="72029-118">This configuration consists of:</span></span>
  
- <span data-ttu-id="72029-119">En utvärderingsprenumeration eller betald prenumeration på Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="72029-119">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="72029-120">Ett förenklat organisationsintranät som är anslutet till internet och består av virtuella DC1-, APP1- och CLIENT1-datorer på ett undernät i ett virtuellt Azure-nätverk.</span><span class="sxs-lookup"><span data-stu-id="72029-120">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="72029-121">Azure AD Connect körs på APP1 för att synkronisera TESTLAB AD DS-domänen med Azure AD-klientorganisationen för din Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="72029-121">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a><span data-ttu-id="72029-122">Fas 2: Aktivera tillbakaskrivning av lösenord för TESTLAB AD DS-domänen</span><span class="sxs-lookup"><span data-stu-id="72029-122">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>

<span data-ttu-id="72029-123">Börja med att konfigurera kontot för användare 1 med rollen global administratör.</span><span class="sxs-lookup"><span data-stu-id="72029-123">First, configure the User 1 account with the global administrator role.</span></span>

1. <span data-ttu-id="72029-124">Logga in med ditt globala administratörskonto från [administrationscentret för Microsoft 365](https://portal.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="72029-124">From the [Microsoft 365 admin center](https://portal.microsoft.com), sign in with your global administrator account.</span></span>

2. <span data-ttu-id="72029-125">Välj **Aktiva användare.**</span><span class="sxs-lookup"><span data-stu-id="72029-125">Select **Active users**.</span></span>
 
3. <span data-ttu-id="72029-126">På sidan **Aktiva** användare väljer du **användarkontot,**</span><span class="sxs-lookup"><span data-stu-id="72029-126">On the **Active users** page, select the **user1** account,</span></span>

4. <span data-ttu-id="72029-127">I fönstret **användare1** väljer du **Redigera** bredvid **Roller.**</span><span class="sxs-lookup"><span data-stu-id="72029-127">On the **user1** pane, select **Edit** next to **Roles**.</span></span>

5. <span data-ttu-id="72029-128">I fönstret **Redigera användarroller** för användare1 väljer **du Global administratör**, väljer **Spara** och sedan **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="72029-128">On the **Edit user roles** pane for user1, select **Global administrator**, select **Save**, and then select **Close**.</span></span>

<span data-ttu-id="72029-129">Konfigurera därefter kontot User 1 med säkerhetsinställningarna som gör det möjligt att ändra lösenord för andra användares räkning i TESTLAB AD DS-domänen.</span><span class="sxs-lookup"><span data-stu-id="72029-129">Next, configure the User 1 account with the security settings that allow it to change passwords on behalf of other users in the TESTLAB AD DS domain.</span></span>

1. <span data-ttu-id="72029-130">Logga in på [Azure-portalen](https://portal.azure.com) med ditt globala administratörskonto och anslut sedan till APP1 med kontot TESTLAB\User1.</span><span class="sxs-lookup"><span data-stu-id="72029-130">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="72029-131">På skrivbordet i APP1 väljer du **Start**, anger **aktiv** och väljer sedan **Active Directory - användare och datorer.**</span><span class="sxs-lookup"><span data-stu-id="72029-131">From the desktop of APP1, select **Start**, enter **active**, and then select **Active Directory Users and Computers**.</span></span>

3. <span data-ttu-id="72029-132">På menyraden väljer du **Visa**.</span><span class="sxs-lookup"><span data-stu-id="72029-132">On the menu bar, select **View**.</span></span> <span data-ttu-id="72029-133">Om **Avancerade funktioner** inte är aktiverade aktiverar du den genom att markera den.</span><span class="sxs-lookup"><span data-stu-id="72029-133">If **Advanced features** is not enabled, select it to enable it.</span></span>

4. <span data-ttu-id="72029-134">I trädfönstret väljer du och håller ned (eller högerklickar på) domänen, väljer **Egenskaper** och väljer sedan **fliken** Säkerhet.</span><span class="sxs-lookup"><span data-stu-id="72029-134">In the tree pane, select and hold (or right-click) your domain, select **Properties**, and then select the **Security** tab.</span></span>

5. <span data-ttu-id="72029-135">Välj **Avancerat**.</span><span class="sxs-lookup"><span data-stu-id="72029-135">Select **Advanced**.</span></span>

6. <span data-ttu-id="72029-136">På fliken **Behörigheter** väljer du Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="72029-136">On the **Permissions** tab, select **Add**.</span></span>

7. <span data-ttu-id="72029-137">Välj **Välj ett huvudnamn**, ange **Användare1** och välj sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="72029-137">Select **Select a principal**, enter **User1**, and then select **OK**.</span></span>

8. <span data-ttu-id="72029-138">I **Gäller för** väljer du **Underordnade användarobjekt**.</span><span class="sxs-lookup"><span data-stu-id="72029-138">In **Applies to**, select **Descendant User objects**.</span></span>

9. <span data-ttu-id="72029-139">Under **Behörigheter** väljer du följande:</span><span class="sxs-lookup"><span data-stu-id="72029-139">Under **Permissions**, select the following:</span></span>

    - <span data-ttu-id="72029-140">**Ändra lösenord**</span><span class="sxs-lookup"><span data-stu-id="72029-140">**Change password**</span></span>
    - <span data-ttu-id="72029-141">**Återställa lösenord**</span><span class="sxs-lookup"><span data-stu-id="72029-141">**Reset password**</span></span>

10. <span data-ttu-id="72029-142">Under **Egenskaper** väljer du följande:</span><span class="sxs-lookup"><span data-stu-id="72029-142">Under **Properties**, select the following:</span></span>
    - <span data-ttu-id="72029-143">**Skriv lockoutTime**</span><span class="sxs-lookup"><span data-stu-id="72029-143">**Write lockoutTime**</span></span>
    - <span data-ttu-id="72029-144">**Skriv pwdLastSet**</span><span class="sxs-lookup"><span data-stu-id="72029-144">**Write pwdLastSet**</span></span>

11. <span data-ttu-id="72029-145">Spara ändringarna genom att välja **OK** tre gånger.</span><span class="sxs-lookup"><span data-stu-id="72029-145">Select **OK** three times to save the changes.</span></span>

12. <span data-ttu-id="72029-146">Stäng **Active Directory – användare och datorer**.</span><span class="sxs-lookup"><span data-stu-id="72029-146">Close **Active Directory Users and Computers**.</span></span>

<span data-ttu-id="72029-147">Konfigurera därefter Azure AD Connect på APP1 för tillbakaskrivning av lösenord.</span><span class="sxs-lookup"><span data-stu-id="72029-147">Next, configure Azure AD Connect on APP1 for password writeback.</span></span>

1. <span data-ttu-id="72029-148">Om det behövs kan du ansluta till APP1 med TESTLAB\User1-kontot.</span><span class="sxs-lookup"><span data-stu-id="72029-148">If needed, connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="72029-149">Dubbelklicka på **Azure AD Connect** på APP1-skrivbordet.</span><span class="sxs-lookup"><span data-stu-id="72029-149">From the desktop of APP1, double-click **Azure AD Connect**.</span></span>

3. <span data-ttu-id="72029-150">På **välkomstsidan väljer** du **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="72029-150">On the **Welcome page**, select **Configure**.</span></span>

4. <span data-ttu-id="72029-151">På sidan **Ytterligare uppgifter** väljer du **Anpassa synkroniseringsalternativ** och sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="72029-151">On the **Additional tasks** page, select **Customize synchronization options**, and then select **Next**.</span></span>

5. <span data-ttu-id="72029-152">På sidan **Anslut till Azure AD** anger du autentiseringsuppgifterna för ditt globala administratörskonto och väljer sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="72029-152">On the **Connect to Azure AD** page, enter your global administrator account credentials, and then select **Next**.</span></span>

6. <span data-ttu-id="72029-153">På sidorna **för anslutningskataloger** och **filtrering av domän/OU** väljer du **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="72029-153">On the **Connect directories** and **Domain/OU filtering** pages, select **Next**.</span></span>

7. <span data-ttu-id="72029-154">På sidan **Valfria** funktioner väljer du **Tillbakaskrivning av lösenord** och väljer sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="72029-154">On the **Optional features** page, select **Password writeback**, and then select **Next**.</span></span>

8. <span data-ttu-id="72029-155">På sidan **Är redo att** konfigurera väljer du **Konfigurera** och väntar till processen är klar.</span><span class="sxs-lookup"><span data-stu-id="72029-155">On the **Ready to configure** page, select **Configure** and wait for the process to finish.</span></span>

9. <span data-ttu-id="72029-156">När konfigurationen är klar väljer du **Avsluta**.</span><span class="sxs-lookup"><span data-stu-id="72029-156">When you see the configuration finish, select **Exit**.</span></span>

<span data-ttu-id="72029-157">Nu kan du testa tillbakaskrivning av lösenord för användare på datorer som inte är anslutna till det virtuella nätverket i ditt simulerade intranät.</span><span class="sxs-lookup"><span data-stu-id="72029-157">You are now ready to test password writeback for users on computers that aren't connected to the virtual network of your simulated intranet.</span></span>

<span data-ttu-id="72029-158">Den resulterande konfigurationen ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="72029-158">Your resulting configuration looks like this:</span></span>

![Det simulerade företaget med en testmiljö med direktautentisering](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="72029-160">Konfigurationen består av:</span><span class="sxs-lookup"><span data-stu-id="72029-160">This configuration consists of:</span></span>

- <span data-ttu-id="72029-161">En utvärderingsversion av Microsoft 365 E5 eller betalda prenumerationer med DNS-domänen TESTLAB.\<*your domain name*></span><span class="sxs-lookup"><span data-stu-id="72029-161">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.\<*your domain name*></span></span> <span data-ttu-id="72029-162">registrerat.</span><span class="sxs-lookup"><span data-stu-id="72029-162">registered.</span></span>
- <span data-ttu-id="72029-163">Ett förenklat organisationsintranät som är anslutet till internet och består av virtuella DC1-, APP1- och CLIENT1-datorer på ett undernät i ett virtuellt Azure-nätverk.</span><span class="sxs-lookup"><span data-stu-id="72029-163">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="72029-164">Azure AD Connect körs på APP1 för att synkronisera listan med konton och grupper från Azure AD-klientorganisationen för din Microsoft 365-prenumeration till TESTLAB AD DS-domänen.</span><span class="sxs-lookup"><span data-stu-id="72029-164">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span>
- <span data-ttu-id="72029-165">Tillbakaskrivning av lösenord är aktiverat så att användare kan ändra sina lösenord i Azure AD utan att behöva ansluta till det förenklade intranätet.</span><span class="sxs-lookup"><span data-stu-id="72029-165">Password writeback is enabled so that users can change their passwords through Azure AD without having to be connected to the simplified intranet.</span></span>

## <a name="next-step"></a><span data-ttu-id="72029-166">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="72029-166">Next step</span></span>

<span data-ttu-id="72029-167">Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="72029-167">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="72029-168">Se även</span><span class="sxs-lookup"><span data-stu-id="72029-168">See also</span></span>

[<span data-ttu-id="72029-169">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="72029-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="72029-170">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="72029-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="72029-171">Dokumentation om Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="72029-171">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)