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
ms.openlocfilehash: b8c89ca7ef967c423b89db4559ef04f715a5f869
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686232"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a><span data-ttu-id="35e1a-103">Tillbakaskrivning av lösenord i testmiljön för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="35e1a-103">Password writeback for your Microsoft 365 test environment</span></span>

<span data-ttu-id="35e1a-104">*Den här test laboratorie guiden kan endast användas för test miljöer med Microsoft 365 för företags nätverk.*</span><span class="sxs-lookup"><span data-stu-id="35e1a-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="35e1a-105">Med tillbakaskrivning av lösenord kan användare uppdatera sina lösenord via Azure Active Directory (Azure AD), som sedan replikeras till din lokala Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="35e1a-105">Password writeback allows users to update their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="35e1a-106">Med funktionen för tillbakaskrivning av lösenord behöver användarna inte uppdatera sina lösenord via den lokala AD DS där de ursprungliga användarkontona lagras.</span><span class="sxs-lookup"><span data-stu-id="35e1a-106">With password writeback, users don't need to update their passwords through the on-premises AD DS where their original user accounts are stored.</span></span> <span data-ttu-id="35e1a-107">Det här underlättar vid nätverksväxling och för fjärranvändare som inte har en fjärråtkomstanslutning till det lokala nätverket.</span><span class="sxs-lookup"><span data-stu-id="35e1a-107">This helps roaming or remote users who do not have a remote access connection to their on-premises network.</span></span>

<span data-ttu-id="35e1a-108">I den här artikeln beskrivs hur du kan konfigurera Microsoft 365-testmiljön för tillbakaskrivning av lösenord.</span><span class="sxs-lookup"><span data-stu-id="35e1a-108">This article describes how you can configure your Microsoft 365 test environment for password writeback.</span></span>

<span data-ttu-id="35e1a-109">Det finns två faser för att konfigurera detta:</span><span class="sxs-lookup"><span data-stu-id="35e1a-109">There are two phases to setting this up:</span></span>

1.    <span data-ttu-id="35e1a-110">Skapa Microsoft 365-testmiljön för det simulerade företaget med synkronisering av lösenordshash.</span><span class="sxs-lookup"><span data-stu-id="35e1a-110">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.    <span data-ttu-id="35e1a-111">Aktivera tillbakaskrivning av lösenord för TESTLAB AD DS-domänen.</span><span class="sxs-lookup"><span data-stu-id="35e1a-111">Enable password writeback for the TESTLAB AD DS domain.</span></span>
    
![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="35e1a-113">Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med testlabbguider för Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="35e1a-113">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="35e1a-114">Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön</span><span class="sxs-lookup"><span data-stu-id="35e1a-114">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="35e1a-115">Följ först anvisningarna i [Synkronisering av lösenordshash](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="35e1a-115">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span> <span data-ttu-id="35e1a-116">Här är konfigurationsresultatet.</span><span class="sxs-lookup"><span data-stu-id="35e1a-116">Here is your resulting configuration.</span></span>
  
![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="35e1a-118">Konfigurationen består av:</span><span class="sxs-lookup"><span data-stu-id="35e1a-118">This configuration consists of:</span></span> 
  
- <span data-ttu-id="35e1a-119">En utvärderingsprenumeration eller betald prenumeration på Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="35e1a-119">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="35e1a-120">Ett förenklat företagsintranät anslutet till Internet som består av de virtuella datorerna DC1, APP1 och CLIENT1 i ett undernät i ett virtuellt Azure-nätverk.</span><span class="sxs-lookup"><span data-stu-id="35e1a-120">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="35e1a-121">Azure AD Connect körs på APP1 för att synkronisera TESTLAB AD DS-domänen med Azure AD-klientorganisationen för din Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="35e1a-121">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a><span data-ttu-id="35e1a-122">Fas 2: Aktivera tillbakaskrivning av lösenord för TESTLAB AD DS-domänen</span><span class="sxs-lookup"><span data-stu-id="35e1a-122">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>

<span data-ttu-id="35e1a-123">Börja med att konfigurera kontot för användare 1 med rollen global administratör.</span><span class="sxs-lookup"><span data-stu-id="35e1a-123">First, configure the User 1 account with the global administrator role.</span></span>

1. <span data-ttu-id="35e1a-124">Logga in med ditt globala administratörskonto från [administrationscentret för Microsoft 365](https://portal.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="35e1a-124">From the [Microsoft 365 admin center](https://portal.microsoft.com), sign in with your global administrator account.</span></span>

2. <span data-ttu-id="35e1a-125">Klicka på **Aktiva användare**.</span><span class="sxs-lookup"><span data-stu-id="35e1a-125">Click **Active users**.</span></span>
 
3. <span data-ttu-id="35e1a-126">På sidan **Aktiva användare** klickar du på kontot **user1**.</span><span class="sxs-lookup"><span data-stu-id="35e1a-126">On the **Active users** page, click the **user1** account,</span></span>

4. <span data-ttu-id="35e1a-127">I fönstret **user1** klickar du på **Redigera** bredvid **Roller**.</span><span class="sxs-lookup"><span data-stu-id="35e1a-127">On the **user1** pane, click **Edit** next to **Roles**.</span></span>

5. <span data-ttu-id="35e1a-128">Gå till fönstret **Redigera användarroller** för user1 och klicka på **Global administrator**.</span><span class="sxs-lookup"><span data-stu-id="35e1a-128">On the **Edit user roles** pane for user1, click **Global administrator**.</span></span> <span data-ttu-id="35e1a-129">Klicka på **Spara** och sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="35e1a-129">Click **Save**, and then click **Close**.</span></span>

<span data-ttu-id="35e1a-130">Konfigurera därefter kontot User 1 med säkerhetsinställningarna som gör det möjligt att ändra lösenord för andra användares räkning i TESTLAB AD DS-domänen.</span><span class="sxs-lookup"><span data-stu-id="35e1a-130">Next, configure the User 1 account with the security settings that allow it to change passwords on behalf of other users in the TESTLAB AD DS domain.</span></span>

1. <span data-ttu-id="35e1a-131">Logga in på [Azure-portalen](https://portal.azure.com) med ditt globala administratörskonto och anslut sedan till APP1 med kontot TESTLAB\User1.</span><span class="sxs-lookup"><span data-stu-id="35e1a-131">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2.  <span data-ttu-id="35e1a-132">Klicka på **Start** på skrivbordet för APP1. Skriv **active**och klicka sedan på **Active Directory – användare och datorer**.</span><span class="sxs-lookup"><span data-stu-id="35e1a-132">From the desktop of APP1, click **Start**, type **active**, and then click **Active Directory Users and Computers**.</span></span>

3. <span data-ttu-id="35e1a-133">Klicka på **Visa** i menyraden.</span><span class="sxs-lookup"><span data-stu-id="35e1a-133">Click **View** in the menu bar.</span></span> <span data-ttu-id="35e1a-134">Om **Avancerade funktioner** inte har aktiverats, aktiverar du det genom att klicka på det.</span><span class="sxs-lookup"><span data-stu-id="35e1a-134">If **Advanced features** is not enabled, click it to enable it.</span></span>

4. <span data-ttu-id="35e1a-135">Högerklicka på din domän i trädfönstret, klicka på **Egenskaper** och klicka sedan på fliken **Säkerhet**.</span><span class="sxs-lookup"><span data-stu-id="35e1a-135">In the tree pane, right-click your domain, click **Properties**, and then click the **Security** tab.</span></span>

5. <span data-ttu-id="35e1a-136">Klicka på **Avancerat**.</span><span class="sxs-lookup"><span data-stu-id="35e1a-136">Click **Advanced**.</span></span>

6. <span data-ttu-id="35e1a-137">På fliken **Behörigheter** klickar du på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="35e1a-137">On the **Permissions** tab, click **Add**.</span></span>

7. <span data-ttu-id="35e1a-138">Klicka på **Välj ett huvudkonto**, skriv **User1** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="35e1a-138">Click **Select a principal**, type **User1**, and then click **OK**.</span></span>

8. <span data-ttu-id="35e1a-139">I **Gäller för** väljer du **Underordnade användarobjekt**.</span><span class="sxs-lookup"><span data-stu-id="35e1a-139">In **Applies to**, select **Descendant User objects**.</span></span>

9. <span data-ttu-id="35e1a-140">Under **Behörigheter** väljer du följande:</span><span class="sxs-lookup"><span data-stu-id="35e1a-140">Under **Permissions**, select the following:</span></span>

    - <span data-ttu-id="35e1a-141">Ändra lösenord</span><span class="sxs-lookup"><span data-stu-id="35e1a-141">Change password</span></span>
    - <span data-ttu-id="35e1a-142">Återställa lösenord</span><span class="sxs-lookup"><span data-stu-id="35e1a-142">Reset password</span></span>

10. <span data-ttu-id="35e1a-143">Under **Egenskaper** väljer du följande:</span><span class="sxs-lookup"><span data-stu-id="35e1a-143">Under **Properties**, select the following:</span></span>
    - <span data-ttu-id="35e1a-144">Skriv lockoutTime</span><span class="sxs-lookup"><span data-stu-id="35e1a-144">Write lockoutTime</span></span>
    - <span data-ttu-id="35e1a-145">Skriv pwdLastSet</span><span class="sxs-lookup"><span data-stu-id="35e1a-145">Write pwdLastSet</span></span>

11. <span data-ttu-id="35e1a-146">Klicka på **OK** tre gånger för att spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="35e1a-146">Click **OK** three times to save the changes.</span></span>

12. <span data-ttu-id="35e1a-147">Stäng **Active Directory – användare och datorer**.</span><span class="sxs-lookup"><span data-stu-id="35e1a-147">Close **Active Directory Users and Computers**.</span></span>

<span data-ttu-id="35e1a-148">Konfigurera därefter Azure AD Connect på APP1 för tillbakaskrivning av lösenord.</span><span class="sxs-lookup"><span data-stu-id="35e1a-148">Next, configure Azure AD Connect on APP1 for password writeback.</span></span>

1. <span data-ttu-id="35e1a-149">Om det behövs kan du ansluta till APP1 med TESTLAB\User1-kontot.</span><span class="sxs-lookup"><span data-stu-id="35e1a-149">If needed, connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="35e1a-150">Dubbelklicka på **Azure AD Connect** på APP1-skrivbordet.</span><span class="sxs-lookup"><span data-stu-id="35e1a-150">From the desktop of APP1, double-click **Azure AD Connect**.</span></span>

3. <span data-ttu-id="35e1a-151">På **välkomstsidan** klickar du på **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="35e1a-151">On the **Welcome page**, click **Configure**.</span></span>

4. <span data-ttu-id="35e1a-152">På sidan **Ytterligare uppgifter** klickar du på **Anpassa synkroniseringsalternativ** och sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="35e1a-152">On the **Additional tasks** page, click **Customize synchronization options**, and then click **Next**.</span></span>

5. <span data-ttu-id="35e1a-153">På sidan **Anslut till Azure AD** skriver du dina globala administratörsautentiseringsuppgifter. Klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="35e1a-153">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6. <span data-ttu-id="35e1a-154">På sidorna **Anslut kataloger** och **Domän-/OU-filtrering** klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="35e1a-154">On the **Connect directories** and **Domain/OU filtering** pages, click **Next**.</span></span>

7. <span data-ttu-id="35e1a-155">På sidan **Valfria funktioner** väljer du **Tillbakaskrivning av lösenord** och klickar på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="35e1a-155">On the **Optional features** page, select **Password writeback** and click **Next**.</span></span> 

8. <span data-ttu-id="35e1a-156">På sidan **Redo att konfigurera** klickar du på **Konfigurera** och väntar tills processen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="35e1a-156">On the **Ready to configure** page, click **Configure** and wait for the process to finish.</span></span>

9. <span data-ttu-id="35e1a-157">När konfigurationen är klar klickar du på **Avsluta**.</span><span class="sxs-lookup"><span data-stu-id="35e1a-157">When you see the configuration finish, click **Exit**.</span></span>

<span data-ttu-id="35e1a-158">Du är nu redo att testa tillbakaskrivning av lösenord för användare på datorer som inte är anslutna till det virtuella nätverket i det simulerade intranätet.</span><span class="sxs-lookup"><span data-stu-id="35e1a-158">You are now ready to test password writeback for users on computers that are not connected to the virtual network of your simulated intranet.</span></span>

<span data-ttu-id="35e1a-159">Här är konfigurationsresultatet:</span><span class="sxs-lookup"><span data-stu-id="35e1a-159">Here is your resulting configuration:</span></span>

![Det simulerade företaget med en testmiljö med direktautentisering](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="35e1a-161">Konfigurationen består av:</span><span class="sxs-lookup"><span data-stu-id="35e1a-161">This configuration consists of:</span></span>

- <span data-ttu-id="35e1a-162">En utvärderings version av Microsoft 365 E5 eller betalda abonnemang med DNS-TESTLAB.\<your domain name></span><span class="sxs-lookup"><span data-stu-id="35e1a-162">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.\<your domain name></span></span> <span data-ttu-id="35e1a-163">registrerat.</span><span class="sxs-lookup"><span data-stu-id="35e1a-163">registered.</span></span>
- <span data-ttu-id="35e1a-164">Ett förenklat företagsintranät anslutet till Internet som består av de virtuella datorerna DC1, APP1 och CLIENT1 i ett undernät i ett virtuellt Azure-nätverk.</span><span class="sxs-lookup"><span data-stu-id="35e1a-164">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="35e1a-165">Azure AD Connect körs på APP1 för att synkronisera listan med konton och grupper från Azure AD-klientorganisationen för din Microsoft 365-prenumeration till TESTLAB AD DS-domänen.</span><span class="sxs-lookup"><span data-stu-id="35e1a-165">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span> 
- <span data-ttu-id="35e1a-166">Tillbakaskrivning av lösenord är aktiverat så att användare kan ändra sina lösenord i Azure AD utan att behöva ansluta till det förenklade intranätet.</span><span class="sxs-lookup"><span data-stu-id="35e1a-166">Password writeback is enabled so that users can change their passwords through Azure AD without having to be connected to the simplified intranet.</span></span>

## <a name="next-step"></a><span data-ttu-id="35e1a-167">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="35e1a-167">Next step</span></span>

<span data-ttu-id="35e1a-168">Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="35e1a-168">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="35e1a-169">Se även</span><span class="sxs-lookup"><span data-stu-id="35e1a-169">See also</span></span>

[<span data-ttu-id="35e1a-170">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="35e1a-170">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="35e1a-171">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="35e1a-171">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="35e1a-172">Microsoft 365 för företags dokumentation</span><span class="sxs-lookup"><span data-stu-id="35e1a-172">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


