---
title: Synkronisering av lösenordshash för Microsoft 365-testmiljön
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: ''
description: 'Sammanfattning: Konfigurera och demonstrera synkroniseringen av lösenordshash och inloggning för Microsoft 365-testmiljön.'
ms.openlocfilehash: 8c0f9b45fc4a57ad5ac50ea2a3340d6e05769b96
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632905"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="ddc0e-103">Synkronisering av lösenordshash för Microsoft 365-testmiljön</span><span class="sxs-lookup"><span data-stu-id="ddc0e-103">Password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="ddc0e-104">*Den här testlabbguiden kan användas i både Microsoft 365 Enterprise- och Office 365 Enterprise-testmiljöer.*</span><span class="sxs-lookup"><span data-stu-id="ddc0e-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="ddc0e-105">Många organisationer använder synkronisering av lösenordshash med Azure AD Connect för att synkronisera konton i den lokala AD DS-skogen (Active Directory Domain Services) med konton i Azure AD-klientorganisationen för Microsoft 365-prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-105">Many organizations use Azure AD Connect and password hash synchronization to synchronize the set of accounts in their on-premises Active Directory Domain Services (AD DS) forest to the set of accounts in the Azure AD tenant of their Microsoft 365 subscription.</span></span> <span data-ttu-id="ddc0e-106">I den här artikeln beskrivs hur du kan lägga till synkronisering av lösenordshash i din Microsoft 365-testmiljö, vilket resulterar i följande konfiguration:</span><span class="sxs-lookup"><span data-stu-id="ddc0e-106">This article describes how you can add password hash synchronization to your Microsoft 365 test environment, resulting in the following configuration:</span></span>
  
![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
<span data-ttu-id="ddc0e-108">Konfigurationen av testmiljön består av två faser:</span><span class="sxs-lookup"><span data-stu-id="ddc0e-108">There are two phases to setting up this test environment:</span></span>
  
1. <span data-ttu-id="ddc0e-109">Skapa Microsoft 365-testmiljön för det simulerade företaget.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-109">Create the Microsoft 365 simulated enterprise test environment.</span></span>
2. <span data-ttu-id="ddc0e-110">Installera och konfigurera Azure AD Connect på APP1.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-110">Install and configure Azure AD Connect on APP1.</span></span>
    
> [!TIP]
> <span data-ttu-id="ddc0e-111">Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med Microsoft 365 Enterprise-testlabbguider.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a><span data-ttu-id="ddc0e-112">Fas 1: Skapa Microsoft 365-testmiljön för det simulerade företaget.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-112">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>

<span data-ttu-id="ddc0e-113">Följ anvisningarna i [baskonfiguration för simulerat företag för Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="ddc0e-113">Follow the instructions in [simulated enterprise base configuration for Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md).</span></span> <span data-ttu-id="ddc0e-114">Här är konfigurationsresultatet.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-114">Here is your resulting configuration.</span></span>
  
![Baskonfiguration för simulerat företag](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="ddc0e-116">Konfigurationen består av:</span><span class="sxs-lookup"><span data-stu-id="ddc0e-116">This configuration consists of:</span></span> 
  
- <span data-ttu-id="ddc0e-117">Utvärderingsversioner av eller betalda prenumerationer på Microsoft 365 E5 eller Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-117">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="ddc0e-118">Ett förenklat företagsintranät anslutet till Internet som består av de virtuella datorerna DC1, APP1 och CLIENT1 i ett virtuellt Azure-nätverk.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-118">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines in an Azure virtual network.</span></span> <span data-ttu-id="ddc0e-119">DC1 är en domänkontrollant för testlab.\<namnet på din offentliga domän > AD DS-domänen.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-119">DC1 is a domain controller for the testlab.\<your public domain name> AD DS domain.</span></span>

## <a name="phase-2-create-and-register-the-testlab-domain"></a><span data-ttu-id="ddc0e-120">Fas 2: Skapa och registrera testlab-domänen</span><span class="sxs-lookup"><span data-stu-id="ddc0e-120">Phase 2: Create and register the testlab domain</span></span>

<span data-ttu-id="ddc0e-121">I den här fasen lägger du till en offentlig DNS-domän och lägger till den i din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-121">In this phase you add a public DNS domain and add it to your subscription.</span></span>

<span data-ttu-id="ddc0e-122">Kontakta en leverantör av offentlig DNS-registrering för att skapa ett nytt offentligt DNS-domännamn baserat på ditt aktuella domännamn och lägga till det i din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-122">First, work with your public DNS registration provider to create a new public DNS domain name based on your current domain name and add it to your subscription.</span></span> <span data-ttu-id="ddc0e-123">Vi rekommenderar att du använder namnet **testlab.**\<din offentliga domän>.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-123">We recommend using the name **testlab.**\<your public domain>.</span></span> <span data-ttu-id="ddc0e-124">Om namnet på din offentliga domän till exempel är **<span>contoso</span>.com** lägger du till det offentliga domännamnet **<span>testlab</span>.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-124">For example, if your public domain name is **<span>contoso</span>.com**, add the public domain name **<span>testlab</span>.contoso.com**.</span></span>
  
<span data-ttu-id="ddc0e-125">Sedan lägger du till **testlab.**\<din offentliga domän> domän i din utvärderingsversion av eller din betalda prenumeration på Microsoft 365 eller Office 365 genom att gå igenom domänregistreringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-125">Next, you add the **testlab.**\<your public domain> domain to your Microsoft 365 or Office 365 trial or paid subscription by going through the domain registration process.</span></span> <span data-ttu-id="ddc0e-126">Detta omfattar att lägga till ytterligare DNS-poster i **testlab.**\<din offentliga domän> domän.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-126">This consists of adding additional DNS records to the **testlab.**\<your public domain> domain.</span></span> <span data-ttu-id="ddc0e-127">Mer information finns i [Lägga till en domän i Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="ddc0e-127">For more information, see [Add a domain to Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain).</span></span> 

<span data-ttu-id="ddc0e-128">Här är konfigurationsresultatet.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-128">Here is your resulting configuration.</span></span>
  
![Registreringen av ditt testlab-domännamn](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="ddc0e-130">Konfigurationen består av:</span><span class="sxs-lookup"><span data-stu-id="ddc0e-130">This configuration consists of:</span></span>

- <span data-ttu-id="ddc0e-131">Utvärderingsversioner av eller betalda prenumerationer på Microsoft 365 E5 eller Office 365 E5 med DNS-domänen testlab.\<ditt offentliga domännamn> registrerad.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-131">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain testlab.\<your public domain name> registered.</span></span>
- <span data-ttu-id="ddc0e-132">Ett förenklat företagsintranät anslutet till Internet som består av de virtuella datorerna DC1, APP1 och CLIENT1 i ett undernät i ett virtuellt Azure-nätverk.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-132">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>

<span data-ttu-id="ddc0e-133">Observera att testlab.\<ditt offentliga domännamn> nu:</span><span class="sxs-lookup"><span data-stu-id="ddc0e-133">Notice how the testlab.\<your public domain name> is now:</span></span>

- <span data-ttu-id="ddc0e-134">Stöds av offentliga DNS-poster.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-134">Supported by public DNS records.</span></span>
- <span data-ttu-id="ddc0e-135">Är registrerat i dina Microsoft 365-prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-135">Registered in your Microsoft 365 subscriptions.</span></span>
- <span data-ttu-id="ddc0e-136">Är AD DS-domänen i det simulerade intranätet.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-136">The AD DS domain on your simulated intranet.</span></span>
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a><span data-ttu-id="ddc0e-137">Fas 3: Installera Azure AD Connect på APP1</span><span class="sxs-lookup"><span data-stu-id="ddc0e-137">Phase 3: Install Azure AD Connect on APP1</span></span>

<span data-ttu-id="ddc0e-138">I den här fasen installerar och konfigurerar du verktyget Azure AD Connect på APP1, och kontrollerar sedan att det fungerar.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-138">In this phase, you install and configure the Azure AD Connect tool on APP1, and then verify that it works.</span></span>
  
<span data-ttu-id="ddc0e-139">Först installerar och konfigurerar du Azure AD Connect på APP1.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-139">First, you install and configure Azure AD Connect on APP1.</span></span>

1. <span data-ttu-id="ddc0e-140">Logga in på [Azure-portalen](https://portal.azure.com) med ditt globala administratörskonto och anslut sedan till APP1 med kontot TESTLAB\\Användare1.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-140">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\\User1 account.</span></span>
    
2. <span data-ttu-id="ddc0e-141">Gå till skrivbordet på APP1, öppna en kommandotolk för Windows PowerShell på administratörsnivå och kör dessa kommandon:</span><span class="sxs-lookup"><span data-stu-id="ddc0e-141">From the desktop of APP1, open an administrator-level Windows PowerShell command prompt, and then run these commands:</span></span>
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. <span data-ttu-id="ddc0e-142">Klicka på **Internet Explorer** i Aktivitetsfältet och gå till [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span><span class="sxs-lookup"><span data-stu-id="ddc0e-142">From the task bar, click **Internet Explorer** and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
4. <span data-ttu-id="ddc0e-143">På sidan Microsoft Azure Active Directory Connect klickar du på **Ladda ned** och sedan på **Kör**.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-143">On the Microsoft Azure Active Directory Connect page, click **Download**, and then click **Run**.</span></span>
    
5. <span data-ttu-id="ddc0e-144">På sidan **Välkommen till Azure AD Connect** klickar du på **Jag accepterar** och sedan på **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-144">On the **Welcome to Azure AD Connect** page, click **I agree**, and then click **Continue**.</span></span>
    
6. <span data-ttu-id="ddc0e-145">På sidan **Standardinställningar** klickar du på **Använd standardinställningar**.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-145">On the **Express Settings** page, click **Use express settings**.</span></span>
    
7. <span data-ttu-id="ddc0e-146">På sidan **Anslut till Azure AD** skriver du namnet på ditt globala administratörskonto i **Användarnamn**, lösenordet i **Lösenord** och klickar på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-146">On the **Connect to Azure AD** page, type your global administrator account name in **Username,** type its password in **Password**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="ddc0e-147">På sidan **Anslut till AD DS** skriver du **TESTLAB\\Användare1** i **Användarnamn**, lösenordet i **Lösenord** och klickar på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-147">On the **Connect to AD DS** page, type **TESTLAB\\User1** in **Username,** type its password in **Password**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="ddc0e-148">På sidan **Klart att konfigurera** klickar du på **Installera**.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-148">On the **Ready to configure** page, click **Install**.</span></span>
    
10. <span data-ttu-id="ddc0e-149">På sidan **Konfigurationen är klar** klickar du på **Avsluta**.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-149">On the **Configuration complete** page, click **Exit**.</span></span>
    
11. <span data-ttu-id="ddc0e-150">Gå till administrationscentret för Microsoft 365 i Internet Explorer ([https://portal.microsoft.com](https://portal.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="ddc0e-150">In Internet Explorer, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)).</span></span>
    
12. <span data-ttu-id="ddc0e-151">Klicka på **Användare > Aktiva användare** i det vänstra navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-151">In the left navigation, click **Users > Active users**.</span></span>
    
    <span data-ttu-id="ddc0e-152">Observera kontot som heter **Användare1**.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-152">Note the account named **User1**.</span></span> <span data-ttu-id="ddc0e-153">Detta konto kommer från TESTLAB AD DS-domänen och är ett bevis på att katalogsynkroniseringen har fungerat.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-153">This account is from the TESTLAB AD DS domain and is proof that directory synchronization has worked.</span></span>
    
13. <span data-ttu-id="ddc0e-154">Klicka på kontot **Användare1** och klicka sedan på **Licenser och appar**.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-154">Click the **User1** account, and then click **Licenses and apps**.</span></span>
    
14. <span data-ttu-id="ddc0e-155">I **Produktlicenser** väljer du din plats (om det behövs), inaktiverar **Office 365 E5**-licensen och aktiverar **Microsoft 365 E5**-licensen.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-155">In **Product licenses**, select your location (if needed), disable the **Office 365 E5** license and enable the **Microsoft 365 E5** license.</span></span> 

15. <span data-ttu-id="ddc0e-156">Klicka på **Spara** längst ned på sidan och klicka sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-156">Click **Save** at the bottom of the page, and then click **Close**.</span></span>
    
<span data-ttu-id="ddc0e-157">Sedan provar du att det går att logga in på din prenumeration med <strong>användare1@testlab.</strong>\<ditt domännamn> användarnamnet för kontot Användare1.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-157">Next, you test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<your domain name> user name of the User1 account.</span></span>

1. <span data-ttu-id="ddc0e-158">Logga ut från APP1 och logga sedan in igen. Den här gången med ett annat konto.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-158">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="ddc0e-159">När du uppmanas att ange ett användarnamn och lösenord anger du <strong>användare1@testlab.</strong>\<ditt domännamn> och lösenordet för Användare1.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-159">When prompted for a user name and password, specify <strong>user1@testlab.</strong>\<your domain name> and the User1 password.</span></span> <span data-ttu-id="ddc0e-160">Nu ska du loggas in som Användare1.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-160">You should successfully sign in as User1.</span></span> 
 
<span data-ttu-id="ddc0e-161">Observera att User1 visserligen har domänadministratörsbehörighet för TESTLAB AD DS-domänen, men den är inte global administratör.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-161">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="ddc0e-162">Därför visas inte **administratörsikonen** som ett alternativ.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-162">Therefore, you will not see the **Admin** icon as an option.</span></span> 

<span data-ttu-id="ddc0e-163">Här är konfigurationsresultatet.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-163">Here is your resulting configuration.</span></span>

![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

<span data-ttu-id="ddc0e-165">Konfigurationen består av:</span><span class="sxs-lookup"><span data-stu-id="ddc0e-165">This configuration consists of:</span></span> 
  
- <span data-ttu-id="ddc0e-166">Utvärderingsversioner av eller betalda prenumerationer på Microsoft 365 E5 eller Office 365 E5 med DNS-domänen TESTLAB.\<ditt domännamn> registrerad.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-166">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.\<your domain name> registered.</span></span>
- <span data-ttu-id="ddc0e-167">Ett förenklat företagsintranät anslutet till Internet som består av de virtuella datorerna DC1, APP1 och CLIENT1 i ett undernät i ett virtuellt Azure-nätverk.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-167">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="ddc0e-168">Azure AD Connect körs på APP1 för att synkronisera TESTLAB AD DS-domänen med Azure AD-klientorganisationen för din Microsoft 365-prenumeration regelbundet.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-168">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription periodically.</span></span>
- <span data-ttu-id="ddc0e-169">Användare1-kontot i TESTLAB  AD DS-domänen har synkroniserats med Azure AD-klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-169">The User1 account in the TESTLAB  AD DS domain has been synchronized with the Azure AD tenant.</span></span>

## <a name="next-step"></a><span data-ttu-id="ddc0e-170">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="ddc0e-170">Next step</span></span>

<span data-ttu-id="ddc0e-171">Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="ddc0e-171">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="ddc0e-172">Se även</span><span class="sxs-lookup"><span data-stu-id="ddc0e-172">See also</span></span>

[<span data-ttu-id="ddc0e-173">Testlabbguider för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ddc0e-173">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="ddc0e-174">Distribuera Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ddc0e-174">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="ddc0e-175">Microsoft 365 Enterprise-dokumentation</span><span class="sxs-lookup"><span data-stu-id="ddc0e-175">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


