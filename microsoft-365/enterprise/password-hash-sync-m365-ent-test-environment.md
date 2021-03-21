---
title: Synkronisering av lösenordshash för Microsoft 365-testmiljön
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: 'Sammanfattning: Konfigurera och demonstrera synkroniseringen av lösenordshash och inloggning för Microsoft 365-testmiljön.'
ms.openlocfilehash: 9c61745fe322dce4cb2b537b18963634a97c697a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921510"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="dd7c4-103">Synkronisering av lösenordshash för Microsoft 365-testmiljön</span><span class="sxs-lookup"><span data-stu-id="dd7c4-103">Password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="dd7c4-104">*Den här testlabbguiden kan användas för både Microsoft 365 för företag- och Office 365 Enterprise-testmiljöer.*</span><span class="sxs-lookup"><span data-stu-id="dd7c4-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="dd7c4-105">Många organisationer använder synkronisering av lösenordshash med Azure AD Connect för att synkronisera konton i den lokala AD DS-skogen (Active Directory Domain Services) med konton i Azure AD-klientorganisationen för Microsoft 365-prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-105">Many organizations use Azure AD Connect and password hash synchronization to synchronize the set of accounts in their on-premises Active Directory Domain Services (AD DS) forest to the set of accounts in the Azure AD tenant of their Microsoft 365 subscription.</span></span> 

<span data-ttu-id="dd7c4-106">I den här artikeln beskrivs hur du lägger till synkronisering av lösenordshashar i din Microsoft 365-testmiljö, som resulterar i den här konfigurationen:</span><span class="sxs-lookup"><span data-stu-id="dd7c4-106">This article describes how you can add password hash synchronization to your Microsoft 365 test environment, which results in this configuration:</span></span>
  
![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
<span data-ttu-id="dd7c4-108">För inställning av den här testmiljön ingår tre faser:</span><span class="sxs-lookup"><span data-stu-id="dd7c4-108">Setting up this test environment involves three phases:</span></span>
- [<span data-ttu-id="dd7c4-109">Fas 1: Skapa Microsoft 365-testmiljön för det simulerade företaget.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-109">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>](#phase-1-create-the-microsoft-365-simulated-enterprise-test-environment)
- [<span data-ttu-id="dd7c4-110">Fas 2: Skapa och registrera testlab-domänen</span><span class="sxs-lookup"><span data-stu-id="dd7c4-110">Phase 2: Create and register the testlab domain</span></span>](#phase-2-create-and-register-the-testlab-domain)
- [<span data-ttu-id="dd7c4-111">Fas 3: Installera Azure AD Connect på APP1</span><span class="sxs-lookup"><span data-stu-id="dd7c4-111">Phase 3: Install Azure AD Connect on APP1</span></span>](#phase-3-install-azure-ad-connect-on-app1)
    
> [!TIP]
> <span data-ttu-id="dd7c4-112">En visuell karta till alla artiklar i Microsoft 365 testlabbguide-stacken för företag finns i Testlabbguide för [Microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)för företag.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a><span data-ttu-id="dd7c4-113">Fas 1: Skapa Microsoft 365-testmiljön för det simulerade företaget.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-113">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>

<span data-ttu-id="dd7c4-114">Följ anvisningarna i [baskonfiguration för simulerat företag för Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="dd7c4-114">Follow the instructions in [simulated enterprise base configuration for Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md).</span></span> <span data-ttu-id="dd7c4-115">Den resulterande konfigurationen ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="dd7c4-115">Your resulting configuration looks like this:</span></span>
  
![Baskonfiguration för simulerat företag](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="dd7c4-117">Konfigurationen består av:</span><span class="sxs-lookup"><span data-stu-id="dd7c4-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="dd7c4-118">En utvärderingsprenumeration eller betald prenumeration på Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="dd7c4-119">Ett förenklat organisations intranät som är anslutet till internet och består av virtuella DC1-, APP1- och CLIENT1-maskiner i ett virtuellt Azure-nätverk.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines in an Azure virtual network.</span></span> <span data-ttu-id="dd7c4-120">DC1 är en domänkontrollant för testlab.<din offentliga *domän>* AD DS-domän.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-120">DC1 is a domain controller for the testlab.<*your public domain name*> AD DS domain.</span></span>

## <a name="phase-2-create-and-register-the-testlab-domain"></a><span data-ttu-id="dd7c4-121">Fas 2: Skapa och registrera testlab-domänen</span><span class="sxs-lookup"><span data-stu-id="dd7c4-121">Phase 2: Create and register the testlab domain</span></span>

<span data-ttu-id="dd7c4-122">I den här fasen lägger du till en offentlig DNS-domän och lägger sedan till den i din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-122">In this phase, add a public DNS domain, and then add it to your subscription.</span></span>

<span data-ttu-id="dd7c4-123">Börja med din offentliga DNS-registreringsleverantör och skapa ett nytt offentligt DNS-domännamn som baseras på ditt nuvarande domännamn, och lägg sedan till det i prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-123">First, work with your public DNS registration provider to create a new public DNS domain name that's based on your current domain name, and then add it to your subscription.</span></span> <span data-ttu-id="dd7c4-124">Vi rekommenderar att du använder **namnet testlab.<*den offentliga domänen.\* >*\*</span><span class="sxs-lookup"><span data-stu-id="dd7c4-124">We recommend using the name **testlab.<*your public domain*>**.</span></span> <span data-ttu-id="dd7c4-125">Om ditt offentliga domännamn till exempel är **<span>contoso</span>.com** lägger du till det offentliga domännamnet: **<span>testlab</span>.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-125">For example, if your public domain name is **<span>contoso</span>.com**, add the public domain name: **<span>testlab</span>.contoso.com**.</span></span>
  
<span data-ttu-id="dd7c4-126">Lägg sedan till **testlab.< >** din offentliga domän i din utvärderingsversion av Microsoft 365 eller betalprenumeration genom att gå igenom domänregistreringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-126">Next, add the **testlab.<*your public domain*>** domain to your Microsoft 365 trial or paid subscription by going through the domain registration process.</span></span> <span data-ttu-id="dd7c4-127">Det består av att lägga till ytterligare DNS-poster **till testlab.<*den offentliga domänen.\* >*\*</span><span class="sxs-lookup"><span data-stu-id="dd7c4-127">This consists of adding additional DNS records to the **testlab.<*your public domain*>** domain.</span></span> <span data-ttu-id="dd7c4-128">Mer information finns i Lägga [till en domän i Microsoft 365.](../admin/setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="dd7c4-128">For more information, see [Add a domain to Microsoft 365](../admin/setup/add-domain.md).</span></span>

<span data-ttu-id="dd7c4-129">Den resulterande konfigurationen ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="dd7c4-129">Your resulting configuration looks like this:</span></span>
  
![Registreringen av ditt testlab-domännamn](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="dd7c4-131">Konfigurationen består av:</span><span class="sxs-lookup"><span data-stu-id="dd7c4-131">This configuration consists of:</span></span>

- <span data-ttu-id="dd7c4-132">En utvärderingsversion av Microsoft 365 E5 eller betald prenumeration med DNS-domänen testlab.<ditt offentliga *>* registrerat.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-132">A Microsoft 365 E5 trial or paid subscription with the DNS domain testlab.<*your public domain name*> registered.</span></span>
- <span data-ttu-id="dd7c4-133">Ett förenklat organisationsintranät som är anslutet till internet och består av virtuella DC1-, APP1- och CLIENT1-datorer på ett undernät i ett virtuellt Azure-nätverk.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-133">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>

<span data-ttu-id="dd7c4-134">Lägg märke till hur testlab.<ditt offentliga *domännamn*> är nu:</span><span class="sxs-lookup"><span data-stu-id="dd7c4-134">Notice how the testlab.<*your public domain name*> is now:</span></span>

- <span data-ttu-id="dd7c4-135">Stöds av offentliga DNS-poster.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-135">Supported by public DNS records.</span></span>
- <span data-ttu-id="dd7c4-136">Är registrerat i dina Microsoft 365-prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-136">Registered in your Microsoft 365 subscriptions.</span></span>
- <span data-ttu-id="dd7c4-137">Är AD DS-domänen i det simulerade intranätet.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-137">The AD DS domain on your simulated intranet.</span></span>
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a><span data-ttu-id="dd7c4-138">Fas 3: Installera Azure AD Connect på APP1</span><span class="sxs-lookup"><span data-stu-id="dd7c4-138">Phase 3: Install Azure AD Connect on APP1</span></span>

<span data-ttu-id="dd7c4-139">I den här fasen installerar och konfigurerar du Azure AD Connect-verktyget i APP1 och kontrollerar sedan att det fungerar.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-139">In this phase, install and configure the Azure AD Connect tool on APP1, and then verify that it works.</span></span>
  
<span data-ttu-id="dd7c4-140">Först installerar och konfigurerar du Azure AD Connect i APP1.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-140">First, install and configure Azure AD Connect on APP1.</span></span>

1. <span data-ttu-id="dd7c4-141">Logga in på [Azure-portalen](https://portal.azure.com) med ditt globala administratörskonto och anslut sedan till APP1 med kontot TESTLAB\\Användare1.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-141">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\\User1 account.</span></span>
    
2. <span data-ttu-id="dd7c4-142">Gå till skrivbordet på APP1, öppna en kommandotolk i Windows PowerShell på administratörsnivå och kör dessa kommandon för att avaktivera utökad säkerhet för Internet Explorer:</span><span class="sxs-lookup"><span data-stu-id="dd7c4-142">From the desktop of APP1, open an administrator-level Windows PowerShell command prompt, and then run these commands to disable Internet Explorer Enhanced Security:</span></span>
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. <span data-ttu-id="dd7c4-143">Välj Internet Explorer i **Aktivitetsfältet och** gå till [https://aka.ms/aadconnect](https://aka.ms/aadconnect) .</span><span class="sxs-lookup"><span data-stu-id="dd7c4-143">From the taskbar, select **Internet Explorer** and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
4. <span data-ttu-id="dd7c4-144">På sidan Microsoft Azure Active Directory Connect väljer du **Ladda** ned och sedan **Kör**.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-144">On the Microsoft Azure Active Directory Connect page, select **Download**, and then select **Run**.</span></span>
    
5. <span data-ttu-id="dd7c4-145">På sidan **Välkommen till Azure AD Connect** väljer du Jag **godkänner** och väljer sedan **Fortsätt.**</span><span class="sxs-lookup"><span data-stu-id="dd7c4-145">On the **Welcome to Azure AD Connect** page, select **I agree**, and then select **Continue**.</span></span>
    
6. <span data-ttu-id="dd7c4-146">På sidan **Expressinställningar** väljer du **Använd standardinställningar**.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-146">On the **Express Settings** page, select **Use express settings**.</span></span>
    
7. <span data-ttu-id="dd7c4-147">På sidan **Anslut till Azure AD** anger du namnet på ditt globala administratörskonto i **Användarnamn,** anger lösenordet i **Lösenord** och väljer sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="dd7c4-147">On the **Connect to Azure AD** page, enter your global administrator account name in **Username,** enter its password in **Password**, and then select **Next**.</span></span>
    
8. <span data-ttu-id="dd7c4-148">På sidan **Anslut till AD DS** anger du **TESTLAB \\ User1** i **Användarnamn,** anger lösenordet i **Lösenord** och väljer sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="dd7c4-148">On the **Connect to AD DS** page, enter **TESTLAB\\User1** in **Username,** enter its password in **Password**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="dd7c4-149">På sidan **Är redo att konfigurera** väljer du **Installera**.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-149">On the **Ready to configure** page, select **Install**.</span></span>
    
10. <span data-ttu-id="dd7c4-150">På sidan **Konfiguration slutförd** väljer du **Avsluta**.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-150">On the **Configuration complete** page, select **Exit**.</span></span>
    
11. <span data-ttu-id="dd7c4-151">Gå till administrationscentret för Microsoft 365 i Internet Explorer ([https://portal.microsoft.com](https://portal.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="dd7c4-151">In Internet Explorer, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)).</span></span>
    
12. <span data-ttu-id="dd7c4-152">I det vänstra navigeringsfönstret väljer du **Användare > Aktiva användare.**</span><span class="sxs-lookup"><span data-stu-id="dd7c4-152">In the left navigation pane, select **Users > Active users**.</span></span>
    
    <span data-ttu-id="dd7c4-153">Observera kontot som heter **Användare1**.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-153">Note the account named **User1**.</span></span> <span data-ttu-id="dd7c4-154">Detta konto kommer från TESTLAB AD DS-domänen och är ett bevis på att katalogsynkroniseringen har fungerat.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-154">This account is from the TESTLAB AD DS domain and is proof that directory synchronization has worked.</span></span>
    
13. <span data-ttu-id="dd7c4-155">Välj **Användarkonto och** sedan Licenser **och appar.**</span><span class="sxs-lookup"><span data-stu-id="dd7c4-155">Select the **User1** account, and then select **Licenses and apps**.</span></span>
    
14. <span data-ttu-id="dd7c4-156">I **Produktlicenser** väljer du plats (om det behövs), **inaktiverar Office 365 E5-licensen** och aktiverar **sedan Microsoft 365 E5-licensen.**</span><span class="sxs-lookup"><span data-stu-id="dd7c4-156">In **Product licenses**, select your location (if needed), disable the **Office 365 E5** license, and then enable the **Microsoft 365 E5** license.</span></span> 

15. <span data-ttu-id="dd7c4-157">Välj **Spara** längst ned på sidan och välj sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-157">Select **Save** at the bottom of the page, and then select **Close**.</span></span>
    
<span data-ttu-id="dd7c4-158">Testa sedan möjligheten att logga in på din prenumeration **med  > user1@testlab.<** ditt domännamn användarnamn för User1-kontot:</span><span class="sxs-lookup"><span data-stu-id="dd7c4-158">Next, test the ability to sign in to your subscription with the **user1@testlab.<*your domain name*>** user name of the User1 account:</span></span>

1. <span data-ttu-id="dd7c4-159">Logga ut från APP1 och logga sedan in igen. Den här gången med ett annat konto.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-159">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="dd7c4-160">När du uppmanas att ange ett användarnamn och lösenord **anger user1@testlab.<*ditt domännamn\* >*\* och lösenordet Användare1.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-160">When prompted for a user name and password, specify **user1@testlab.<*your domain name*>** and the User1 password.</span></span> <span data-ttu-id="dd7c4-161">Nu ska du loggas in som Användare1.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-161">You should successfully sign in as User1.</span></span>
 
<span data-ttu-id="dd7c4-162">Observera att User1 visserligen har domänadministratörsbehörighet för TESTLAB AD DS-domänen, men den är inte global administratör.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-162">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="dd7c4-163">Därför visas inte **administratörsikonen** som ett alternativ.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-163">Therefore, you will not see the **Admin** icon as an option.</span></span> 

<span data-ttu-id="dd7c4-164">Den resulterande konfigurationen ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="dd7c4-164">Your resulting configuration looks like this:</span></span>

![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

<span data-ttu-id="dd7c4-166">Konfigurationen består av:</span><span class="sxs-lookup"><span data-stu-id="dd7c4-166">This configuration consists of:</span></span> 
  
- <span data-ttu-id="dd7c4-167">Utvärderingsversionen av Microsoft 365 E5 eller Office 365 E5 eller betalda prenumerationer med DNS-domänen TESTLAB.<*domännamnet*> registrerat.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-167">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.<*your domain name*> registered.</span></span>
- <span data-ttu-id="dd7c4-168">Ett förenklat organisationsintranät som är anslutet till internet och består av virtuella DC1-, APP1- och CLIENT1-datorer på ett undernät i ett virtuellt Azure-nätverk.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-168">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="dd7c4-169">Azure AD Connect körs på APP1 för att regelbundet synkronisera TESTLAB AD DS-domänen till Azure AD-klientorganisationen för Microsoft 365-prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-169">Azure AD Connect runs on APP1 to periodically synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>
- <span data-ttu-id="dd7c4-170">Användare1-kontot i TESTLAB  AD DS-domänen har synkroniserats med Azure AD-klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-170">The User1 account in the TESTLAB  AD DS domain has been synchronized with the Azure AD tenant.</span></span>

## <a name="next-step"></a><span data-ttu-id="dd7c4-171">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="dd7c4-171">Next step</span></span>

<span data-ttu-id="dd7c4-172">Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="dd7c4-172">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="dd7c4-173">Se även</span><span class="sxs-lookup"><span data-stu-id="dd7c4-173">See also</span></span>

[<span data-ttu-id="dd7c4-174">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="dd7c4-174">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="dd7c4-175">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="dd7c4-175">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="dd7c4-176">Dokumentation om Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="dd7c4-176">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)