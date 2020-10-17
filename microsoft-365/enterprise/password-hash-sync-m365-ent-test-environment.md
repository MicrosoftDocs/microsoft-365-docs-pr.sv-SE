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
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Synkronisering av lösenordshash för Microsoft 365-testmiljön

*Den här test laboratorie guiden kan användas för både Microsoft 365 för företags-och Office 365 företags test miljöer.*

Många organisationer använder synkronisering av lösenordshash med Azure AD Connect för att synkronisera konton i den lokala AD DS-skogen (Active Directory Domain Services) med konton i Azure AD-klientorganisationen för Microsoft 365-prenumerationen. 

I den här artikeln beskrivs hur du kan lägga till en synkronisering av lösen ords-hash i test miljön för Microsoft 365, som leder till följande:
  
![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
Att konfigurera den här test miljön inbegriper tre faser:
- [Fas 1: Skapa Microsoft 365-testmiljön för det simulerade företaget.](#phase-1-create-the-microsoft-365-simulated-enterprise-test-environment)
- [Fas 2: Skapa och registrera testlab-domänen](#phase-2-create-and-register-the-testlab-domain)
- [Fas 3: Installera Azure AD Connect på APP1](#phase-3-install-azure-ad-connect-on-app1)
    
> [!TIP]
> Om du vill visa en visuell karta till alla artiklar i gruppen Microsoft 365 för Enterprise-testlabbet går du till [Microsoft 365 för Enterprise Test Lab-guide](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a>Fas 1: Skapa Microsoft 365-testmiljön för det simulerade företaget.

Följ anvisningarna i [baskonfiguration för simulerat företag för Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). Den resulterande konfigurationen ser ut så här:
  
![Baskonfiguration för simulerat företag](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
Konfigurationen består av:
  
- En utvärderingsprenumeration eller betald prenumeration på Microsoft 365 E5.
- En förenklad organisations intranät som är ansluten till Internet, bestående av de virtuella datorerna DC1, APP1 och KLIENT1 i ett virtuellt Azure-nätverk. DC1 är en domänkontrollant för testlab. <*ditt offentliga domän namn*> AD DS-domän.

## <a name="phase-2-create-and-register-the-testlab-domain"></a>Fas 2: Skapa och registrera testlab-domänen

Lägg till en offentlig DNS-domän i den här fasen och Lägg sedan till den i din prenumeration.

Arbeta först med din offentliga DNS-registreringsbegäran och skapa ett nytt offentligt DNS-domännamn som baseras på ditt nuvarande domän namn och Lägg sedan till det i ditt abonnemang. Vi rekommenderar att du använder namnet **testlab. <*din offentliga domän* > **. Om ditt offentliga domän namn till exempel är ** <span>contoso</span>. com**lägger du till den offentliga domänens namn: ** <span>testlab</span>. contoso.com**.
  
Lägg sedan till **testlab. <*din offentliga domän* > ** domän till utvärderings versionen av Microsoft 365 eller det betalda abonnemanget genom att gå igenom domän registrerings processen. Detta består av att lägga till ytterligare DNS-poster i **testlab. <*din offentliga domän* > ** domän. Mer information finns i [lägga till en domän i Microsoft 365](../admin/setup/add-domain.md).

Den resulterande konfigurationen ser ut så här:
  
![Registreringen av ditt testlab-domännamn](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
Konfigurationen består av:

- En utvärderings version av Microsoft 365 E5 eller betalat med DNS Domain testlab. <*ditt offentliga domän namn*> registrerat.
- En förenklad organisations intranät som är ansluten till Internet, bestående av de virtuella datorerna DC1, APP1 och KLIENT1 i ett undernät för ett Azure Virtual Network.

Lägg märke till att testlab <*det offentliga domän namnet*> är nu:

- Stöds av offentliga DNS-poster.
- Är registrerat i dina Microsoft 365-prenumerationer.
- Är AD DS-domänen i det simulerade intranätet.
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a>Fas 3: Installera Azure AD Connect på APP1

I den här fasen installerar och konfigurerar du Azure AD Connect Tool på APP1 och kontrollerar sedan att det fungerar.
  
Börja med att installera och konfigurera Azure AD Connect på APP1.

1. Logga in på [Azure-portalen](https://portal.azure.com) med ditt globala administratörskonto och anslut sedan till APP1 med kontot TESTLAB\\Användare1.
    
2. Gå till skrivbordet på APP1, öppna en kommandotolk i Windows PowerShell på administratörsnivå och kör dessa kommandon för att avaktivera utökad säkerhet för Internet Explorer:
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. Välj **Internet Explorer** och gå till i aktivitets fältet [https://aka.ms/aadconnect](https://aka.ms/aadconnect) .
    
4. Välj **Ladda ned**på sidan Microsoft Azure Active Directory Connect och välj **Kör**.
    
5. På sidan **Välkommen till Azure AD Connect** väljer **du jag accepterar**och väljer sedan **Continue**.
    
6. På sidan **Express inställningar** väljer du **Använd Express inställningar**.
    
7. På sidan **Anslut till Azure AD** anger du det globala administratörs konto namnet i **användar namn,** anger lösen ordet i **lösen ord**och väljer sedan **Nästa**.
    
8. På sidan **Anslut till AD DS** anger du **TESTLAB \\ Användare1** i **användar namn,** anger lösen ordet i **lösen ord**och väljer sedan **Nästa**.
    
9. På sidan **redo att konfigurera** väljer du **Installera**.
    
10. På sidan **slutförd konfigurering** väljer du **Avsluta**.
    
11. Gå till administrationscentret för Microsoft 365 i Internet Explorer ([https://portal.microsoft.com](https://portal.microsoft.com)).
    
12. Välj **användare > aktiva användare**i navigerings fönstret till vänster.
    
    Observera kontot som heter **Användare1**. Detta konto kommer från TESTLAB AD DS-domänen och är ett bevis på att katalogsynkroniseringen har fungerat.
    
13. Välj **Användare1** -kontot och välj sedan **licenser och appar**.
    
14. I **produkt licenser**väljer du din plats (om det behövs), inaktiverar du **Office 365 E5** -licensen och aktiverar sedan **Microsoft 365 E5** -licensen. 

15. Välj **Spara** längst ned på sidan och välj sedan **Stäng**.
    
Prova sedan att logga in på ditt abonnemang med **user1@testlab. <*ditt domän namn* > ** användar namn för user1-kontot:

1. Logga ut från APP1 och logga sedan in igen. Den här gången med ett annat konto.

2. När du uppmanas att ange ett användar namn och ett lösen ord anger du **user1@testlab. <*domän namnet* > ** och user1-lösenordet. Nu ska du loggas in som Användare1.
 
Observera att User1 visserligen har domänadministratörsbehörighet för TESTLAB AD DS-domänen, men den är inte global administratör. Därför visas inte **administratörsikonen** som ett alternativ. 

Den resulterande konfigurationen ser ut så här:

![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

Konfigurationen består av: 
  
- Microsoft 365 E5 eller Office 365 E5-utvärdering eller betal abonnemang med DNS-TESTLAB. <*ditt domän namn*> registrerat.
- En förenklad organisations intranät som är ansluten till Internet, bestående av de virtuella datorerna DC1, APP1 och KLIENT1 i ett undernät för ett Azure Virtual Network. Azure AD Connect körs på APP1 för att regelbundet synkronisera TESTLAB AD DS-domänen till Azure AD-klient organisationen för din Microsoft 365-prenumeration.
- Användare1-kontot i TESTLAB  AD DS-domänen har synkroniserats med Azure AD-klientorganisationen.

## <a name="next-step"></a>Nästa steg

Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.

## <a name="see-also"></a>Se även

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Microsoft 365 för företags dokumentation](https://docs.microsoft.com/microsoft-365-enterprise/)
