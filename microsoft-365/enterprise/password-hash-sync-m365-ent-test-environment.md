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
ms.openlocfilehash: 3c20d1997be2ff47f0b449cbba3afb1e6edcd59a
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487464"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="93c42-103">Synkronisering av lösenordshash för Microsoft 365-testmiljön</span><span class="sxs-lookup"><span data-stu-id="93c42-103">Password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="93c42-104">*Den här test laboratorie guiden kan användas för både Microsoft 365 för företags-och Office 365 företags test miljöer.*</span><span class="sxs-lookup"><span data-stu-id="93c42-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="93c42-105">Många organisationer använder synkronisering av lösenordshash med Azure AD Connect för att synkronisera konton i den lokala AD DS-skogen (Active Directory Domain Services) med konton i Azure AD-klientorganisationen för Microsoft 365-prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="93c42-105">Many organizations use Azure AD Connect and password hash synchronization to synchronize the set of accounts in their on-premises Active Directory Domain Services (AD DS) forest to the set of accounts in the Azure AD tenant of their Microsoft 365 subscription.</span></span> 

<span data-ttu-id="93c42-106">I den här artikeln beskrivs hur du kan lägga till en synkronisering av lösen ords-hash i test miljön för Microsoft 365, som leder till följande:</span><span class="sxs-lookup"><span data-stu-id="93c42-106">This article describes how you can add password hash synchronization to your Microsoft 365 test environment, which results in this configuration:</span></span>
  
![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
<span data-ttu-id="93c42-108">Att konfigurera den här test miljön inbegriper tre faser:</span><span class="sxs-lookup"><span data-stu-id="93c42-108">Setting up this test environment involves three phases:</span></span>
- [<span data-ttu-id="93c42-109">Fas 1: Skapa Microsoft 365-testmiljön för det simulerade företaget.</span><span class="sxs-lookup"><span data-stu-id="93c42-109">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>](#phase-1-create-the-microsoft-365-simulated-enterprise-test-environment)
- [<span data-ttu-id="93c42-110">Fas 2: Skapa och registrera testlab-domänen</span><span class="sxs-lookup"><span data-stu-id="93c42-110">Phase 2: Create and register the testlab domain</span></span>](#phase-2-create-and-register-the-testlab-domain)
- [<span data-ttu-id="93c42-111">Fas 3: Installera Azure AD Connect på APP1</span><span class="sxs-lookup"><span data-stu-id="93c42-111">Phase 3: Install Azure AD Connect on APP1</span></span>](#phase-3-install-azure-ad-connect-on-app1)
    
> [!TIP]
> <span data-ttu-id="93c42-112">Om du vill visa en visuell karta till alla artiklar i gruppen Microsoft 365 för Enterprise-testlabbet går du till [Microsoft 365 för Enterprise Test Lab-guide](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="93c42-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a><span data-ttu-id="93c42-113">Fas 1: Skapa Microsoft 365-testmiljön för det simulerade företaget.</span><span class="sxs-lookup"><span data-stu-id="93c42-113">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>

<span data-ttu-id="93c42-114">Följ anvisningarna i [baskonfiguration för simulerat företag för Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="93c42-114">Follow the instructions in [simulated enterprise base configuration for Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md).</span></span> <span data-ttu-id="93c42-115">Den resulterande konfigurationen ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="93c42-115">Your resulting configuration looks like this:</span></span>
  
![Baskonfiguration för simulerat företag](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="93c42-117">Konfigurationen består av:</span><span class="sxs-lookup"><span data-stu-id="93c42-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="93c42-118">En utvärderingsprenumeration eller betald prenumeration på Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="93c42-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="93c42-119">En förenklad organisations intranät som är ansluten till Internet, bestående av de virtuella datorerna DC1, APP1 och KLIENT1 i ett virtuellt Azure-nätverk.</span><span class="sxs-lookup"><span data-stu-id="93c42-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines in an Azure virtual network.</span></span> <span data-ttu-id="93c42-120">DC1 är en domänkontrollant för testlab. <*ditt offentliga domän namn*> AD DS-domän.</span><span class="sxs-lookup"><span data-stu-id="93c42-120">DC1 is a domain controller for the testlab.<*your public domain name*> AD DS domain.</span></span>

## <a name="phase-2-create-and-register-the-testlab-domain"></a><span data-ttu-id="93c42-121">Fas 2: Skapa och registrera testlab-domänen</span><span class="sxs-lookup"><span data-stu-id="93c42-121">Phase 2: Create and register the testlab domain</span></span>

<span data-ttu-id="93c42-122">Lägg till en offentlig DNS-domän i den här fasen och Lägg sedan till den i din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="93c42-122">In this phase, add a public DNS domain, and then add it to your subscription.</span></span>

<span data-ttu-id="93c42-123">Arbeta först med din offentliga DNS-registreringsbegäran och skapa ett nytt offentligt DNS-domännamn som baseras på ditt nuvarande domän namn och Lägg sedan till det i ditt abonnemang.</span><span class="sxs-lookup"><span data-stu-id="93c42-123">First, work with your public DNS registration provider to create a new public DNS domain name that's based on your current domain name, and then add it to your subscription.</span></span> <span data-ttu-id="93c42-124">Vi rekommenderar att du använder namnet \**testlab. <*din offentliga domän\* > \*\*.</span><span class="sxs-lookup"><span data-stu-id="93c42-124">We recommend using the name **testlab.<*your public domain*>**.</span></span> <span data-ttu-id="93c42-125">Om ditt offentliga domän namn till exempel är \*\* <span>contoso</span>. com**lägger du till den offentliga domänens namn: \*\* <span>testlab</span>. contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="93c42-125">For example, if your public domain name is **<span>contoso</span>.com**, add the public domain name: **<span>testlab</span>.contoso.com**.</span></span>
  
<span data-ttu-id="93c42-126">Lägg sedan till \**testlab. <*din offentliga domän\* > \*\* domän till utvärderings versionen av Microsoft 365 eller det betalda abonnemanget genom att gå igenom domän registrerings processen.</span><span class="sxs-lookup"><span data-stu-id="93c42-126">Next, add the **testlab.<*your public domain*>** domain to your Microsoft 365 trial or paid subscription by going through the domain registration process.</span></span> <span data-ttu-id="93c42-127">Detta består av att lägga till ytterligare DNS-poster i \**testlab. <*din offentliga domän\* > \*\* domän.</span><span class="sxs-lookup"><span data-stu-id="93c42-127">This consists of adding additional DNS records to the **testlab.<*your public domain*>** domain.</span></span> <span data-ttu-id="93c42-128">Mer information finns i [lägga till en domän i Microsoft 365](../admin/setup/add-domain.md).</span><span class="sxs-lookup"><span data-stu-id="93c42-128">For more information, see [Add a domain to Microsoft 365](../admin/setup/add-domain.md).</span></span>

<span data-ttu-id="93c42-129">Den resulterande konfigurationen ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="93c42-129">Your resulting configuration looks like this:</span></span>
  
![Registreringen av ditt testlab-domännamn](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="93c42-131">Konfigurationen består av:</span><span class="sxs-lookup"><span data-stu-id="93c42-131">This configuration consists of:</span></span>

- <span data-ttu-id="93c42-132">En utvärderings version av Microsoft 365 E5 eller betalat med DNS Domain testlab. <*ditt offentliga domän namn*> registrerat.</span><span class="sxs-lookup"><span data-stu-id="93c42-132">A Microsoft 365 E5 trial or paid subscription with the DNS domain testlab.<*your public domain name*> registered.</span></span>
- <span data-ttu-id="93c42-133">En förenklad organisations intranät som är ansluten till Internet, bestående av de virtuella datorerna DC1, APP1 och KLIENT1 i ett undernät för ett Azure Virtual Network.</span><span class="sxs-lookup"><span data-stu-id="93c42-133">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>

<span data-ttu-id="93c42-134">Lägg märke till att testlab <*det offentliga domän namnet*> är nu:</span><span class="sxs-lookup"><span data-stu-id="93c42-134">Notice how the testlab.<*your public domain name*> is now:</span></span>

- <span data-ttu-id="93c42-135">Stöds av offentliga DNS-poster.</span><span class="sxs-lookup"><span data-stu-id="93c42-135">Supported by public DNS records.</span></span>
- <span data-ttu-id="93c42-136">Är registrerat i dina Microsoft 365-prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="93c42-136">Registered in your Microsoft 365 subscriptions.</span></span>
- <span data-ttu-id="93c42-137">Är AD DS-domänen i det simulerade intranätet.</span><span class="sxs-lookup"><span data-stu-id="93c42-137">The AD DS domain on your simulated intranet.</span></span>
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a><span data-ttu-id="93c42-138">Fas 3: Installera Azure AD Connect på APP1</span><span class="sxs-lookup"><span data-stu-id="93c42-138">Phase 3: Install Azure AD Connect on APP1</span></span>

<span data-ttu-id="93c42-139">I den här fasen installerar och konfigurerar du Azure AD Connect Tool på APP1 och kontrollerar sedan att det fungerar.</span><span class="sxs-lookup"><span data-stu-id="93c42-139">In this phase, install and configure the Azure AD Connect tool on APP1, and then verify that it works.</span></span>
  
<span data-ttu-id="93c42-140">Börja med att installera och konfigurera Azure AD Connect på APP1.</span><span class="sxs-lookup"><span data-stu-id="93c42-140">First, install and configure Azure AD Connect on APP1.</span></span>

1. <span data-ttu-id="93c42-141">Logga in på [Azure-portalen](https://portal.azure.com) med ditt globala administratörskonto och anslut sedan till APP1 med kontot TESTLAB\\Användare1.</span><span class="sxs-lookup"><span data-stu-id="93c42-141">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\\User1 account.</span></span>
    
2. <span data-ttu-id="93c42-142">Gå till skrivbordet på APP1, öppna en kommandotolk i Windows PowerShell på administratörsnivå och kör dessa kommandon för att avaktivera utökad säkerhet för Internet Explorer:</span><span class="sxs-lookup"><span data-stu-id="93c42-142">From the desktop of APP1, open an administrator-level Windows PowerShell command prompt, and then run these commands to disable Internet Explorer Enhanced Security:</span></span>
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. <span data-ttu-id="93c42-143">Välj **Internet Explorer** och gå till i aktivitets fältet [https://aka.ms/aadconnect](https://aka.ms/aadconnect) .</span><span class="sxs-lookup"><span data-stu-id="93c42-143">From the taskbar, select **Internet Explorer** and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
4. <span data-ttu-id="93c42-144">Välj **Ladda ned**på sidan Microsoft Azure Active Directory Connect och välj **Kör**.</span><span class="sxs-lookup"><span data-stu-id="93c42-144">On the Microsoft Azure Active Directory Connect page, select **Download**, and then select **Run**.</span></span>
    
5. <span data-ttu-id="93c42-145">På sidan **Välkommen till Azure AD Connect** väljer **du jag accepterar**och väljer sedan **Continue**.</span><span class="sxs-lookup"><span data-stu-id="93c42-145">On the **Welcome to Azure AD Connect** page, select **I agree**, and then select **Continue**.</span></span>
    
6. <span data-ttu-id="93c42-146">På sidan **Express inställningar** väljer du **Använd Express inställningar**.</span><span class="sxs-lookup"><span data-stu-id="93c42-146">On the **Express Settings** page, select **Use express settings**.</span></span>
    
7. <span data-ttu-id="93c42-147">På sidan **Anslut till Azure AD** anger du det globala administratörs konto namnet i **användar namn,** anger lösen ordet i **lösen ord**och väljer sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="93c42-147">On the **Connect to Azure AD** page, enter your global administrator account name in **Username,** enter its password in **Password**, and then select **Next**.</span></span>
    
8. <span data-ttu-id="93c42-148">På sidan **Anslut till AD DS** anger du **TESTLAB \\ Användare1** i **användar namn,** anger lösen ordet i **lösen ord**och väljer sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="93c42-148">On the **Connect to AD DS** page, enter **TESTLAB\\User1** in **Username,** enter its password in **Password**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="93c42-149">På sidan **redo att konfigurera** väljer du **Installera**.</span><span class="sxs-lookup"><span data-stu-id="93c42-149">On the **Ready to configure** page, select **Install**.</span></span>
    
10. <span data-ttu-id="93c42-150">På sidan **slutförd konfigurering** väljer du **Avsluta**.</span><span class="sxs-lookup"><span data-stu-id="93c42-150">On the **Configuration complete** page, select **Exit**.</span></span>
    
11. <span data-ttu-id="93c42-151">Gå till administrationscentret för Microsoft 365 i Internet Explorer ([https://portal.microsoft.com](https://portal.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="93c42-151">In Internet Explorer, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)).</span></span>
    
12. <span data-ttu-id="93c42-152">Välj **användare > aktiva användare**i navigerings fönstret till vänster.</span><span class="sxs-lookup"><span data-stu-id="93c42-152">In the left navigation pane, select **Users > Active users**.</span></span>
    
    <span data-ttu-id="93c42-153">Observera kontot som heter **Användare1**.</span><span class="sxs-lookup"><span data-stu-id="93c42-153">Note the account named **User1**.</span></span> <span data-ttu-id="93c42-154">Detta konto kommer från TESTLAB AD DS-domänen och är ett bevis på att katalogsynkroniseringen har fungerat.</span><span class="sxs-lookup"><span data-stu-id="93c42-154">This account is from the TESTLAB AD DS domain and is proof that directory synchronization has worked.</span></span>
    
13. <span data-ttu-id="93c42-155">Välj **Användare1** -kontot och välj sedan **licenser och appar**.</span><span class="sxs-lookup"><span data-stu-id="93c42-155">Select the **User1** account, and then select **Licenses and apps**.</span></span>
    
14. <span data-ttu-id="93c42-156">I **produkt licenser**väljer du din plats (om det behövs), inaktiverar du **Office 365 E5** -licensen och aktiverar sedan **Microsoft 365 E5** -licensen.</span><span class="sxs-lookup"><span data-stu-id="93c42-156">In **Product licenses**, select your location (if needed), disable the **Office 365 E5** license, and then enable the **Microsoft 365 E5** license.</span></span> 

15. <span data-ttu-id="93c42-157">Välj **Spara** längst ned på sidan och välj sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="93c42-157">Select **Save** at the bottom of the page, and then select **Close**.</span></span>
    
<span data-ttu-id="93c42-158">Prova sedan att logga in på ditt abonnemang med \**user1@testlab. <*ditt domän namn\* > \*\* användar namn för user1-kontot:</span><span class="sxs-lookup"><span data-stu-id="93c42-158">Next, test the ability to sign in to your subscription with the **user1@testlab.<*your domain name*>** user name of the User1 account:</span></span>

1. <span data-ttu-id="93c42-159">Logga ut från APP1 och logga sedan in igen. Den här gången med ett annat konto.</span><span class="sxs-lookup"><span data-stu-id="93c42-159">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="93c42-160">När du uppmanas att ange ett användar namn och ett lösen ord anger du \**user1@testlab. <*domän namnet\* > \*\* och user1-lösenordet.</span><span class="sxs-lookup"><span data-stu-id="93c42-160">When prompted for a user name and password, specify **user1@testlab.<*your domain name*>** and the User1 password.</span></span> <span data-ttu-id="93c42-161">Nu ska du loggas in som Användare1.</span><span class="sxs-lookup"><span data-stu-id="93c42-161">You should successfully sign in as User1.</span></span>
 
<span data-ttu-id="93c42-162">Observera att User1 visserligen har domänadministratörsbehörighet för TESTLAB AD DS-domänen, men den är inte global administratör.</span><span class="sxs-lookup"><span data-stu-id="93c42-162">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="93c42-163">Därför visas inte **administratörsikonen** som ett alternativ.</span><span class="sxs-lookup"><span data-stu-id="93c42-163">Therefore, you will not see the **Admin** icon as an option.</span></span> 

<span data-ttu-id="93c42-164">Den resulterande konfigurationen ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="93c42-164">Your resulting configuration looks like this:</span></span>

![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

<span data-ttu-id="93c42-166">Konfigurationen består av:</span><span class="sxs-lookup"><span data-stu-id="93c42-166">This configuration consists of:</span></span> 
  
- <span data-ttu-id="93c42-167">Microsoft 365 E5 eller Office 365 E5-utvärdering eller betal abonnemang med DNS-TESTLAB. <*ditt domän namn*> registrerat.</span><span class="sxs-lookup"><span data-stu-id="93c42-167">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.<*your domain name*> registered.</span></span>
- <span data-ttu-id="93c42-168">En förenklad organisations intranät som är ansluten till Internet, bestående av de virtuella datorerna DC1, APP1 och KLIENT1 i ett undernät för ett Azure Virtual Network.</span><span class="sxs-lookup"><span data-stu-id="93c42-168">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="93c42-169">Azure AD Connect körs på APP1 för att regelbundet synkronisera TESTLAB AD DS-domänen till Azure AD-klient organisationen för din Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="93c42-169">Azure AD Connect runs on APP1 to periodically synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>
- <span data-ttu-id="93c42-170">Användare1-kontot i TESTLAB  AD DS-domänen har synkroniserats med Azure AD-klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="93c42-170">The User1 account in the TESTLAB  AD DS domain has been synchronized with the Azure AD tenant.</span></span>

## <a name="next-step"></a><span data-ttu-id="93c42-171">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="93c42-171">Next step</span></span>

<span data-ttu-id="93c42-172">Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="93c42-172">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="93c42-173">Se även</span><span class="sxs-lookup"><span data-stu-id="93c42-173">See also</span></span>

[<span data-ttu-id="93c42-174">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="93c42-174">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="93c42-175">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="93c42-175">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="93c42-176">Microsoft 365 för företags dokumentation</span><span class="sxs-lookup"><span data-stu-id="93c42-176">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
