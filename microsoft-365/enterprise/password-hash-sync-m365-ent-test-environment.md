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
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Synkronisering av lösenordshash för Microsoft 365-testmiljön

*Den här testlabbguiden kan användas för både Microsoft 365 för företag- och Office 365 Enterprise-testmiljöer.*

Många organisationer använder synkronisering av lösenordshash med Azure AD Connect för att synkronisera konton i den lokala AD DS-skogen (Active Directory Domain Services) med konton i Azure AD-klientorganisationen för Microsoft 365-prenumerationen. 

I den här artikeln beskrivs hur du lägger till synkronisering av lösenordshashar i din Microsoft 365-testmiljö, som resulterar i den här konfigurationen:
  
![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
För inställning av den här testmiljön ingår tre faser:
- [Fas 1: Skapa Microsoft 365-testmiljön för det simulerade företaget.](#phase-1-create-the-microsoft-365-simulated-enterprise-test-environment)
- [Fas 2: Skapa och registrera testlab-domänen](#phase-2-create-and-register-the-testlab-domain)
- [Fas 3: Installera Azure AD Connect på APP1](#phase-3-install-azure-ad-connect-on-app1)
    
> [!TIP]
> En visuell karta till alla artiklar i Microsoft 365 testlabbguide-stacken för företag finns i Testlabbguide för [Microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)för företag.
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a>Fas 1: Skapa Microsoft 365-testmiljön för det simulerade företaget.

Följ anvisningarna i [baskonfiguration för simulerat företag för Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). Den resulterande konfigurationen ser ut så här:
  
![Baskonfiguration för simulerat företag](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
Konfigurationen består av:
  
- En utvärderingsprenumeration eller betald prenumeration på Microsoft 365 E5.
- Ett förenklat organisations intranät som är anslutet till internet och består av virtuella DC1-, APP1- och CLIENT1-maskiner i ett virtuellt Azure-nätverk. DC1 är en domänkontrollant för testlab.<din offentliga *domän>* AD DS-domän.

## <a name="phase-2-create-and-register-the-testlab-domain"></a>Fas 2: Skapa och registrera testlab-domänen

I den här fasen lägger du till en offentlig DNS-domän och lägger sedan till den i din prenumeration.

Börja med din offentliga DNS-registreringsleverantör och skapa ett nytt offentligt DNS-domännamn som baseras på ditt nuvarande domännamn, och lägg sedan till det i prenumerationen. Vi rekommenderar att du använder **namnet testlab.<*den offentliga domänen.* >** Om ditt offentliga domännamn till exempel är **<span>contoso</span>.com** lägger du till det offentliga domännamnet: **<span>testlab</span>.contoso.com**.
  
Lägg sedan till **testlab.< >** din offentliga domän i din utvärderingsversion av Microsoft 365 eller betalprenumeration genom att gå igenom domänregistreringsprocessen. Det består av att lägga till ytterligare DNS-poster **till testlab.<*den offentliga domänen.* >** Mer information finns i Lägga [till en domän i Microsoft 365.](../admin/setup/add-domain.md)

Den resulterande konfigurationen ser ut så här:
  
![Registreringen av ditt testlab-domännamn](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
Konfigurationen består av:

- En utvärderingsversion av Microsoft 365 E5 eller betald prenumeration med DNS-domänen testlab.<ditt offentliga *>* registrerat.
- Ett förenklat organisationsintranät som är anslutet till internet och består av virtuella DC1-, APP1- och CLIENT1-datorer på ett undernät i ett virtuellt Azure-nätverk.

Lägg märke till hur testlab.<ditt offentliga *domännamn*> är nu:

- Stöds av offentliga DNS-poster.
- Är registrerat i dina Microsoft 365-prenumerationer.
- Är AD DS-domänen i det simulerade intranätet.
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a>Fas 3: Installera Azure AD Connect på APP1

I den här fasen installerar och konfigurerar du Azure AD Connect-verktyget i APP1 och kontrollerar sedan att det fungerar.
  
Först installerar och konfigurerar du Azure AD Connect i APP1.

1. Logga in på [Azure-portalen](https://portal.azure.com) med ditt globala administratörskonto och anslut sedan till APP1 med kontot TESTLAB\\Användare1.
    
2. Gå till skrivbordet på APP1, öppna en kommandotolk i Windows PowerShell på administratörsnivå och kör dessa kommandon för att avaktivera utökad säkerhet för Internet Explorer:
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. Välj Internet Explorer i **Aktivitetsfältet och** gå till [https://aka.ms/aadconnect](https://aka.ms/aadconnect) .
    
4. På sidan Microsoft Azure Active Directory Connect väljer du **Ladda** ned och sedan **Kör**.
    
5. På sidan **Välkommen till Azure AD Connect** väljer du Jag **godkänner** och väljer sedan **Fortsätt.**
    
6. På sidan **Expressinställningar** väljer du **Använd standardinställningar**.
    
7. På sidan **Anslut till Azure AD** anger du namnet på ditt globala administratörskonto i **Användarnamn,** anger lösenordet i **Lösenord** och väljer sedan **Nästa.**
    
8. På sidan **Anslut till AD DS** anger du **TESTLAB \\ User1** i **Användarnamn,** anger lösenordet i **Lösenord** och väljer sedan **Nästa.**
    
9. På sidan **Är redo att konfigurera** väljer du **Installera**.
    
10. På sidan **Konfiguration slutförd** väljer du **Avsluta**.
    
11. Gå till administrationscentret för Microsoft 365 i Internet Explorer ([https://portal.microsoft.com](https://portal.microsoft.com)).
    
12. I det vänstra navigeringsfönstret väljer du **Användare > Aktiva användare.**
    
    Observera kontot som heter **Användare1**. Detta konto kommer från TESTLAB AD DS-domänen och är ett bevis på att katalogsynkroniseringen har fungerat.
    
13. Välj **Användarkonto och** sedan Licenser **och appar.**
    
14. I **Produktlicenser** väljer du plats (om det behövs), **inaktiverar Office 365 E5-licensen** och aktiverar **sedan Microsoft 365 E5-licensen.** 

15. Välj **Spara** längst ned på sidan och välj sedan **Stäng**.
    
Testa sedan möjligheten att logga in på din prenumeration **med  > user1@testlab.<** ditt domännamn användarnamn för User1-kontot:

1. Logga ut från APP1 och logga sedan in igen. Den här gången med ett annat konto.

2. När du uppmanas att ange ett användarnamn och lösenord **anger user1@testlab.<*ditt domännamn* >** och lösenordet Användare1. Nu ska du loggas in som Användare1.
 
Observera att User1 visserligen har domänadministratörsbehörighet för TESTLAB AD DS-domänen, men den är inte global administratör. Därför visas inte **administratörsikonen** som ett alternativ. 

Den resulterande konfigurationen ser ut så här:

![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

Konfigurationen består av: 
  
- Utvärderingsversionen av Microsoft 365 E5 eller Office 365 E5 eller betalda prenumerationer med DNS-domänen TESTLAB.<*domännamnet*> registrerat.
- Ett förenklat organisationsintranät som är anslutet till internet och består av virtuella DC1-, APP1- och CLIENT1-datorer på ett undernät i ett virtuellt Azure-nätverk. Azure AD Connect körs på APP1 för att regelbundet synkronisera TESTLAB AD DS-domänen till Azure AD-klientorganisationen för Microsoft 365-prenumerationen.
- Användare1-kontot i TESTLAB  AD DS-domänen har synkroniserats med Azure AD-klientorganisationen.

## <a name="next-step"></a>Nästa steg

Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.

## <a name="see-also"></a>Se även

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Dokumentation om Microsoft 365 för företag](/microsoft-365-enterprise/)