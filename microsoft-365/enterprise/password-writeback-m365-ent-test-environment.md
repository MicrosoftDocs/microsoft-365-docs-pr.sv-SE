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
ms.openlocfilehash: b999d50b0e98b11638199327bd7ffe7269b261ce
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487134"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a><span data-ttu-id="7c9e8-103">Tillbakaskrivning av lösenord i testmiljön för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7c9e8-103">Password writeback for your Microsoft 365 test environment</span></span>

<span data-ttu-id="7c9e8-104">*Den här test laboratorie guiden kan endast användas för test miljöer med Microsoft 365 för företags nätverk.*</span><span class="sxs-lookup"><span data-stu-id="7c9e8-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="7c9e8-105">Användare kan använda Lösenordssynkronisering för att uppdatera sina lösen ord via Azure Active Directory (Azure AD), som sedan replikeras till din lokala Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="7c9e8-105">Users can use password writeback to update their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="7c9e8-106">Med lösen ords tillbakaskrivning behöver användarna inte uppdatera sina lösen ord via den lokala AD DS där deras ursprungliga användar konton lagras.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-106">With password writeback, users don't have to update their passwords through the on-premises AD DS where their original user accounts are stored.</span></span> <span data-ttu-id="7c9e8-107">Det gör att roaming-eller fjärran vändare som inte har en fjärråtkomstanslutning kan ansluta till deras lokala nätverk.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-107">This helps roaming or remote users who don't have a remote access connection to their on-premises network.</span></span>

<span data-ttu-id="7c9e8-108">I den här artikeln beskrivs hur du konfigurerar din Microsoft 365 test miljö för tillbakaskrivning av lösen ord.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-108">This article describes how to configure your Microsoft 365 test environment for password writeback.</span></span>

<span data-ttu-id="7c9e8-109">När du konfigurerar test miljön för lösen ords ändring görs två faser:</span><span class="sxs-lookup"><span data-stu-id="7c9e8-109">Configuring your test environment for password writeback involves two phases:</span></span>
- [<span data-ttu-id="7c9e8-110">Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön</span><span class="sxs-lookup"><span data-stu-id="7c9e8-110">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="7c9e8-111">Fas 2: Aktivera tillbakaskrivning av lösenord för TESTLAB AD DS-domänen</span><span class="sxs-lookup"><span data-stu-id="7c9e8-111">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>](#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)
  
![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="7c9e8-113">Om du vill visa en visuell karta till alla artiklar i gruppen Microsoft 365 för Enterprise-testlabbet går du till [Microsoft 365 för Enterprise Test Lab-guide](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="7c9e8-113">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="7c9e8-114">Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön</span><span class="sxs-lookup"><span data-stu-id="7c9e8-114">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="7c9e8-115">Följ först anvisningarna i [Synkronisering av lösenordshash](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="7c9e8-115">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span> <span data-ttu-id="7c9e8-116">Den resulterande konfigurationen ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="7c9e8-116">Your resulting configuration looks like this:</span></span>
  
![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="7c9e8-118">Konfigurationen består av:</span><span class="sxs-lookup"><span data-stu-id="7c9e8-118">This configuration consists of:</span></span>
  
- <span data-ttu-id="7c9e8-119">En utvärderingsprenumeration eller betald prenumeration på Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-119">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="7c9e8-120">En förenklad organisations intranät som är ansluten till Internet, bestående av de virtuella datorerna DC1, APP1 och KLIENT1 i ett undernät för ett Azure Virtual Network.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-120">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="7c9e8-121">Azure AD Connect körs på APP1 för att synkronisera TESTLAB AD DS-domänen med Azure AD-klientorganisationen för din Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-121">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a><span data-ttu-id="7c9e8-122">Fas 2: Aktivera tillbakaskrivning av lösenord för TESTLAB AD DS-domänen</span><span class="sxs-lookup"><span data-stu-id="7c9e8-122">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>

<span data-ttu-id="7c9e8-123">Börja med att konfigurera kontot för användare 1 med rollen global administratör.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-123">First, configure the User 1 account with the global administrator role.</span></span>

1. <span data-ttu-id="7c9e8-124">Logga in med ditt globala administratörskonto från [administrationscentret för Microsoft 365](https://portal.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="7c9e8-124">From the [Microsoft 365 admin center](https://portal.microsoft.com), sign in with your global administrator account.</span></span>

2. <span data-ttu-id="7c9e8-125">Välj **aktiva användare**.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-125">Select **Active users**.</span></span>
 
3. <span data-ttu-id="7c9e8-126">På sidan **aktiva användare** väljer du **Användare1** -kontot</span><span class="sxs-lookup"><span data-stu-id="7c9e8-126">On the **Active users** page, select the **user1** account,</span></span>

4. <span data-ttu-id="7c9e8-127">I fönstret **Användare1** väljer du **Redigera** bredvid **roller**.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-127">On the **user1** pane, select **Edit** next to **Roles**.</span></span>

5. <span data-ttu-id="7c9e8-128">I fönstret **Redigera användar roller** för Användare1 väljer du **Global administratör**, väljer **Spara**och sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-128">On the **Edit user roles** pane for user1, select **Global administrator**, select **Save**, and then select **Close**.</span></span>

<span data-ttu-id="7c9e8-129">Konfigurera därefter kontot User 1 med säkerhetsinställningarna som gör det möjligt att ändra lösenord för andra användares räkning i TESTLAB AD DS-domänen.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-129">Next, configure the User 1 account with the security settings that allow it to change passwords on behalf of other users in the TESTLAB AD DS domain.</span></span>

1. <span data-ttu-id="7c9e8-130">Logga in på [Azure-portalen](https://portal.azure.com) med ditt globala administratörskonto och anslut sedan till APP1 med kontot TESTLAB\User1.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-130">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="7c9e8-131">I Skriv bords versionen av APP1 väljer du **Start**, anger **Active**och sedan **Active Directory-användare och datorer**.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-131">From the desktop of APP1, select **Start**, enter **active**, and then select **Active Directory Users and Computers**.</span></span>

3. <span data-ttu-id="7c9e8-132">På Meny raden väljer du **Visa**.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-132">On the menu bar, select **View**.</span></span> <span data-ttu-id="7c9e8-133">Om **avancerade funktioner** inte är aktiverade väljer du det för att aktivera det.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-133">If **Advanced features** is not enabled, select it to enable it.</span></span>

4. <span data-ttu-id="7c9e8-134">Markera och håll ned (eller högerklicka) på din domän i träd fönstret, Välj **Egenskaper**och välj sedan fliken **säkerhet** .</span><span class="sxs-lookup"><span data-stu-id="7c9e8-134">In the tree pane, select and hold (or right-click) your domain, select **Properties**, and then select the **Security** tab.</span></span>

5. <span data-ttu-id="7c9e8-135">Välj **Avancerat**.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-135">Select **Advanced**.</span></span>

6. <span data-ttu-id="7c9e8-136">Välj **Lägg till**på fliken **behörigheter** .</span><span class="sxs-lookup"><span data-stu-id="7c9e8-136">On the **Permissions** tab, select **Add**.</span></span>

7. <span data-ttu-id="7c9e8-137">Välj **Markera ett huvud konto**, ange **user1**och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-137">Select **Select a principal**, enter **User1**, and then select **OK**.</span></span>

8. <span data-ttu-id="7c9e8-138">I **Gäller för** väljer du **Underordnade användarobjekt**.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-138">In **Applies to**, select **Descendant User objects**.</span></span>

9. <span data-ttu-id="7c9e8-139">Under **Behörigheter** väljer du följande:</span><span class="sxs-lookup"><span data-stu-id="7c9e8-139">Under **Permissions**, select the following:</span></span>

    - <span data-ttu-id="7c9e8-140">**Ändra lösenord**</span><span class="sxs-lookup"><span data-stu-id="7c9e8-140">**Change password**</span></span>
    - <span data-ttu-id="7c9e8-141">**Återställa lösenord**</span><span class="sxs-lookup"><span data-stu-id="7c9e8-141">**Reset password**</span></span>

10. <span data-ttu-id="7c9e8-142">Under **Egenskaper** väljer du följande:</span><span class="sxs-lookup"><span data-stu-id="7c9e8-142">Under **Properties**, select the following:</span></span>
    - <span data-ttu-id="7c9e8-143">**Skriv lockoutTime**</span><span class="sxs-lookup"><span data-stu-id="7c9e8-143">**Write lockoutTime**</span></span>
    - <span data-ttu-id="7c9e8-144">**Skriv pwdLastSet**</span><span class="sxs-lookup"><span data-stu-id="7c9e8-144">**Write pwdLastSet**</span></span>

11. <span data-ttu-id="7c9e8-145">Spara ändringarna genom att välja **OK** tre gånger.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-145">Select **OK** three times to save the changes.</span></span>

12. <span data-ttu-id="7c9e8-146">Stäng **Active Directory – användare och datorer**.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-146">Close **Active Directory Users and Computers**.</span></span>

<span data-ttu-id="7c9e8-147">Konfigurera därefter Azure AD Connect på APP1 för tillbakaskrivning av lösenord.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-147">Next, configure Azure AD Connect on APP1 for password writeback.</span></span>

1. <span data-ttu-id="7c9e8-148">Om det behövs kan du ansluta till APP1 med TESTLAB\User1-kontot.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-148">If needed, connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="7c9e8-149">Dubbelklicka på **Azure AD Connect** på APP1-skrivbordet.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-149">From the desktop of APP1, double-click **Azure AD Connect**.</span></span>

3. <span data-ttu-id="7c9e8-150">På **Välkomst sidan**väljer du **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-150">On the **Welcome page**, select **Configure**.</span></span>

4. <span data-ttu-id="7c9e8-151">På sidan **Ytterligare aktiviteter** väljer du **Anpassa synkroniseringsalternativ**och sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-151">On the **Additional tasks** page, select **Customize synchronization options**, and then select **Next**.</span></span>

5. <span data-ttu-id="7c9e8-152">På sidan **Anslut till Azure AD** anger du dina globala administratörs konto uppgifter och väljer sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-152">On the **Connect to Azure AD** page, enter your global administrator account credentials, and then select **Next**.</span></span>

6. <span data-ttu-id="7c9e8-153">På sidorna **Anslut kataloger** och **domän/ou-filtrering** väljer du **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-153">On the **Connect directories** and **Domain/OU filtering** pages, select **Next**.</span></span>

7. <span data-ttu-id="7c9e8-154">Välj **tillbakaskrivning för lösen ordet**på sidan **valfria funktioner** och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-154">On the **Optional features** page, select **Password writeback**, and then select **Next**.</span></span>

8. <span data-ttu-id="7c9e8-155">På sidan **redo att konfigurera** väljer du **Konfigurera** och vänta för att slutföra processen.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-155">On the **Ready to configure** page, select **Configure** and wait for the process to finish.</span></span>

9. <span data-ttu-id="7c9e8-156">När konfigurationen är klar väljer du **Avsluta**.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-156">When you see the configuration finish, select **Exit**.</span></span>

<span data-ttu-id="7c9e8-157">Du är nu redo att testa tillbakaskrivning för lösen ord för användare på datorer som inte är anslutna till det virtuella nätverket i det simulerade intranätet.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-157">You are now ready to test password writeback for users on computers that aren't connected to the virtual network of your simulated intranet.</span></span>

<span data-ttu-id="7c9e8-158">Den resulterande konfigurationen ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="7c9e8-158">Your resulting configuration looks like this:</span></span>

![Det simulerade företaget med en testmiljö med direktautentisering](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="7c9e8-160">Konfigurationen består av:</span><span class="sxs-lookup"><span data-stu-id="7c9e8-160">This configuration consists of:</span></span>

- <span data-ttu-id="7c9e8-161">En utvärderings version av Microsoft 365 E5 eller betalda abonnemang med DNS-TESTLAB.\<*your domain name*></span><span class="sxs-lookup"><span data-stu-id="7c9e8-161">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.\<*your domain name*></span></span> <span data-ttu-id="7c9e8-162">registrerat.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-162">registered.</span></span>
- <span data-ttu-id="7c9e8-163">En förenklad organisations intranät som är ansluten till Internet, bestående av de virtuella datorerna DC1, APP1 och KLIENT1 i ett undernät för ett Azure Virtual Network.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-163">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="7c9e8-164">Azure AD Connect körs på APP1 för att synkronisera listan med konton och grupper från Azure AD-klientorganisationen för din Microsoft 365-prenumeration till TESTLAB AD DS-domänen.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-164">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span>
- <span data-ttu-id="7c9e8-165">Tillbakaskrivning av lösenord är aktiverat så att användare kan ändra sina lösenord i Azure AD utan att behöva ansluta till det förenklade intranätet.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-165">Password writeback is enabled so that users can change their passwords through Azure AD without having to be connected to the simplified intranet.</span></span>

## <a name="next-step"></a><span data-ttu-id="7c9e8-166">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="7c9e8-166">Next step</span></span>

<span data-ttu-id="7c9e8-167">Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="7c9e8-167">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c9e8-168">Se även</span><span class="sxs-lookup"><span data-stu-id="7c9e8-168">See also</span></span>

[<span data-ttu-id="7c9e8-169">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="7c9e8-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="7c9e8-170">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="7c9e8-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="7c9e8-171">Microsoft 365 för företags dokumentation</span><span class="sxs-lookup"><span data-stu-id="7c9e8-171">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


