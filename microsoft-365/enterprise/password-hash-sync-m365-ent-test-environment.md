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
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: ''
description: 'Sammanfattning: Konfigurera och demonstrera synkroniseringen av lösenordshash och inloggning för Microsoft 365-testmiljön.'
ms.openlocfilehash: 7b1ba549a9ac9d3faec8b717a0f76cca1200352b
ms.sourcegitcommit: 87eff6e8a08cec3cb0464a3b765434717584a4a9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/26/2020
ms.locfileid: "44371446"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Synkronisering av lösenordshash för Microsoft 365-testmiljön

*Den här testlabbguiden kan användas i både Microsoft 365 Enterprise- och Office 365 Enterprise-testmiljöer.*

Många organisationer använder synkronisering av lösenordshash med Azure AD Connect för att synkronisera konton i den lokala AD DS-skogen (Active Directory Domain Services) med konton i Azure AD-klientorganisationen för Microsoft 365-prenumerationen. I den här artikeln beskrivs hur du kan lägga till synkronisering av lösenordshash i din Microsoft 365-testmiljö, vilket resulterar i följande konfiguration:
  
![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
Konfigurationen av testmiljön består av två faser:
  
1. Skapa Microsoft 365-testmiljön för det simulerade företaget.
2. Installera och konfigurera Azure AD Connect på APP1.
    
> [!TIP]
> Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med Microsoft 365 Enterprise-testlabbguider.
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a>Fas 1: Skapa Microsoft 365-testmiljön för det simulerade företaget.

Följ anvisningarna i [baskonfiguration för simulerat företag för Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). Här är konfigurationsresultatet.
  
![Baskonfiguration för simulerat företag](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
Konfigurationen består av: 
  
- Utvärderingsversioner av eller betalda prenumerationer på Microsoft 365 E5 eller Office 365 E5.
- Ett förenklat företagsintranät anslutet till Internet som består av de virtuella datorerna DC1, APP1 och CLIENT1 i ett virtuellt Azure-nätverk. DC1 är en domänkontrollant för testlab.\<namnet på din offentliga domän > AD DS-domänen.

## <a name="phase-2-create-and-register-the-testlab-domain"></a>Fas 2: Skapa och registrera testlab-domänen

I den här fasen lägger du till en offentlig DNS-domän och lägger till den i din prenumeration.

Kontakta en leverantör av offentlig DNS-registrering för att skapa ett nytt offentligt DNS-domännamn baserat på ditt aktuella domännamn och lägga till det i din prenumeration. Vi rekommenderar att du använder namnet **testlab.**\<din offentliga domän>. Om namnet på din offentliga domän till exempel är **<span>contoso</span>.com** lägger du till det offentliga domännamnet **<span>testlab</span>.contoso.com**.
  
Sedan lägger du till **testlab.**\<din offentliga domän> domän i din utvärderingsversion av eller din betalda prenumeration på Microsoft 365 eller Office 365 genom att gå igenom domänregistreringsprocessen. Detta omfattar att lägga till ytterligare DNS-poster i **testlab.**\<din offentliga domän> domän. Mer information finns i [Lägga till en domän i Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain). 

Här är konfigurationsresultatet.
  
![Registreringen av ditt testlab-domännamn](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
Konfigurationen består av:

- Utvärderingsversioner av eller betalda prenumerationer på Microsoft 365 E5 eller Office 365 E5 med DNS-domänen testlab.\<ditt offentliga domännamn> registrerad.
- Ett förenklat företagsintranät anslutet till Internet som består av de virtuella datorerna DC1, APP1 och CLIENT1 i ett undernät i ett virtuellt Azure-nätverk.

Observera att testlab.\<ditt offentliga domännamn> nu:

- Stöds av offentliga DNS-poster.
- Är registrerat i dina Microsoft 365-prenumerationer.
- Är AD DS-domänen i det simulerade intranätet.
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a>Fas 3: Installera Azure AD Connect på APP1

I den här fasen installerar och konfigurerar du verktyget Azure AD Connect på APP1, och kontrollerar sedan att det fungerar.
  
Först installerar och konfigurerar du Azure AD Connect på APP1.

1. Logga in på [Azure-portalen](https://portal.azure.com) med ditt globala administratörskonto och anslut sedan till APP1 med kontot TESTLAB\\Användare1.
    
2. Gå till skrivbordet på APP1, öppna en kommandotolk i Windows PowerShell på administratörsnivå och kör dessa kommandon för att avaktivera utökad säkerhet för Internet Explorer:
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. Klicka på **Internet Explorer** i Aktivitetsfältet och gå till [https://aka.ms/aadconnect](https://aka.ms/aadconnect).
    
4. På sidan Microsoft Azure Active Directory Connect klickar du på **Ladda ned** och sedan på **Kör**.
    
5. På sidan **Välkommen till Azure AD Connect** klickar du på **Jag accepterar** och sedan på **Fortsätt**.
    
6. På sidan **Standardinställningar** klickar du på **Använd standardinställningar**.
    
7. På sidan **Anslut till Azure AD** skriver du namnet på ditt globala administratörskonto i **Användarnamn**, lösenordet i **Lösenord** och klickar på **Nästa**.
    
8. På sidan **Anslut till AD DS** skriver du **TESTLAB\\Användare1** i **Användarnamn**, lösenordet i **Lösenord** och klickar på **Nästa**.
    
9. På sidan **Klart att konfigurera** klickar du på **Installera**.
    
10. På sidan **Konfigurationen är klar** klickar du på **Avsluta**.
    
11. Gå till administrationscentret för Microsoft 365 i Internet Explorer ([https://portal.microsoft.com](https://portal.microsoft.com)).
    
12. Klicka på **Användare > Aktiva användare** i det vänstra navigeringsfönstret.
    
    Observera kontot som heter **Användare1**. Detta konto kommer från TESTLAB AD DS-domänen och är ett bevis på att katalogsynkroniseringen har fungerat.
    
13. Klicka på kontot **Användare1** och klicka sedan på **Licenser och appar**.
    
14. I **Produktlicenser** väljer du din plats (om det behövs), inaktiverar **Office 365 E5**-licensen och aktiverar **Microsoft 365 E5**-licensen. 

15. Klicka på **Spara** längst ned på sidan och klicka sedan på **Stäng**.
    
Sedan provar du att det går att logga in på din prenumeration med <strong>användare1@testlab.</strong>\<ditt domännamn> användarnamnet för kontot Användare1.

1. Logga ut från APP1 och logga sedan in igen. Den här gången med ett annat konto.

2. När du uppmanas att ange ett användarnamn och lösenord anger du <strong>användare1@testlab.</strong>\<ditt domännamn> och lösenordet för Användare1. Nu ska du loggas in som Användare1. 
 
Observera att User1 visserligen har domänadministratörsbehörighet för TESTLAB AD DS-domänen, men den är inte global administratör. Därför visas inte **administratörsikonen** som ett alternativ. 

Här är konfigurationsresultatet.

![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

Konfigurationen består av: 
  
- Utvärderingsversioner av eller betalda prenumerationer på Microsoft 365 E5 eller Office 365 E5 med DNS-domänen TESTLAB.\<ditt domännamn> registrerad.
- Ett förenklat företagsintranät anslutet till Internet som består av de virtuella datorerna DC1, APP1 och CLIENT1 i ett undernät i ett virtuellt Azure-nätverk. Azure AD Connect körs på APP1 för att synkronisera TESTLAB AD DS-domänen med Azure AD-klientorganisationen för din Microsoft 365-prenumeration regelbundet.
- Användare1-kontot i TESTLAB  AD DS-domänen har synkroniserats med Azure AD-klientorganisationen.

## <a name="next-step"></a>Nästa steg

Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.

## <a name="see-also"></a>Se även

[Testlabbguider för Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Distribuera Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise-dokumentation](https://docs.microsoft.com/microsoft-365-enterprise/)


