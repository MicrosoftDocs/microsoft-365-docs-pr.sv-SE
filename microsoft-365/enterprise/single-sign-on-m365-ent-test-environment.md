---
title: Sömlös enkel inloggning med Azure AD för din Microsoft 365-testmiljö
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
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
description: 'Sammanfattning: Konfigurera och testa sömlös enkel inloggning med Azure AD för din Microsoft 365-testmiljö.'
ms.openlocfilehash: 7fcbc82cfb35c598358c8160dd06427c2a9c59a2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904870"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a>Sömlös enkel inloggning med Azure AD för din Microsoft 365-testmiljö

*Den här testlabbguiden kan användas för både Microsoft 365 för företag- och Office 365 Enterprise-testmiljöer.*

Sömlös enkel inloggning Sign-On Azure AD loggar automatiskt in användare på sina datorer eller enheter som är anslutna till organisationens nätverk. Sömlös SSO med Azure AD ger användare enkelt åtkomst till molnbaserade program utan att några ytterligare lokala komponenter behövs.

I den här artikeln beskrivs hur du konfigurerar Microsoft 365-testmiljön för sömlös Azure AD-SSO.

Att konfigurera sömlös SSO i Azure AD omfattar två faser:
- [Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Fas 2: Konfigurera Azure AD Connect på APP1 för sömlös SSO med Azure AD](#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso)
   
![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> En visuell karta till alla artiklar i Microsoft 365 testlabbguide-stacken för företag finns i Testlabbguide för [Microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)för företag.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön

Följ anvisningarna i [synkronisering av lösenordshash för Microsoft 365](password-hash-sync-m365-ent-test-environment.md). 

Den resulterande konfigurationen ser ut så här:
  
![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Konfigurationen består av:
  
- En utvärderingsprenumeration eller betald prenumeration på Microsoft 365 E5.
- Ett förenklat organisationsintranät som är anslutet till internet och består av virtuella DC1-, APP1- och CLIENT1-datorer på ett undernät i ett virtuellt Azure-nätverk.
- Azure AD Connect körs i APP1 för att regelbundet synkronisera AD DS-domänen (TESTLAB Active Directory Domain Services) till Azure AD-klientorganisationen för Microsoft 365-prenumerationen.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a>Fas 2: Konfigurera Azure AD Connect på APP1 för sömlös SSO med Azure AD

I den här fasen konfigurerar du Azure AD Connect i APP1 för Azure AD Sömlös SSO och kontrollerar sedan att det fungerar.

### <a name="configure-azure-ad-connect-on-app1"></a>Konfigurera Azure AD Connect på APP1

1. Logga in på [Azure-portalen](https://portal.azure.com) med ditt globala administratörskonto och anslut sedan till APP1 med kontot TESTLAB\User1.

2. Kör Azure AD Connect från appen1 på datorn.

3. På **välkomstsidan väljer** du **Konfigurera**.

4. På sidan **Ytterligare uppgifter** väljer du Ändra inloggning **för användare** och sedan **Nästa.**

5. På sidan **Anslut till Azure AD** anger du autentiseringsuppgifterna för ditt globala administratörskonto och väljer sedan **Nästa.**

6. På **inloggningssidan för användare** väljer du **Aktivera enkel inloggning** och sedan **Nästa.**

7. På sidan **Aktivera enkel inloggning väljer** du Ange **autentiseringsuppgifter**.

8. I dialogrutan **Windows-säkerhet** anger du **användare1** och lösenordet för användarkontot. Välj **OK** och välj sedan **Nästa.**

9. På sidan **Är redo att konfigurera** väljer du **Konfigurera**.

10. På sidan **Konfiguration slutförd** väljer du **Avsluta**.

11. I den vänstra rutan i Azure-portalen väljer du **Azure Active Directory** Azure AD  >  **Connect.** Kontrollera att funktionen **Sömlös enkel inloggning** visas som **Aktiverad**.

Testa sedan möjligheten att logga in på din prenumeration med <strong>user1@testlab.</strong>\<*your public domain*> användarnamn för Användare1-kontot.

1. Välj inställningsikonen i Internet Explorer i APP1 och välj sedan **Internetalternativ**.
 
2. I **Internetalternativ** väljer du **fliken** Säkerhet.

3. Välj **Lokalt intranät** och välj sedan **Webbplatser**.

4. I **Lokalt intranät** väljer du **Avancerat**.

5. I **Lägg till den här webbplatsen i zonen** anger du **<span>https://</span>autologon.microsoftazuread-sso.com** och väljer Lägg **till**  >  **Stäng**  >    >  **OK.**

6. Logga ut och logga sedan in igen. Den här gången med ett annat konto.

7. När du uppmanas att logga in anger <strong>du user1@testlab.</strong>\<*your public domain*> och väljer sedan **Nästa.** Du bör kunna logga in som User1 utan att behöva ange ett lösenord. Detta bekräftar att sömlös enkel inloggning med Azure AD fungerar.

Observera att User1 visserligen har domänadministratörsbehörighet för TESTLAB AD DS-domänen, men är inte global administratör för Azure AD. Därför visas inte **administratörsikonen** som ett alternativ.

Här är konfigurationsresultatet:

![Det simulerade företaget med en testmiljö med direktautentisering](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

Konfigurationen består av:

- En utvärderingsversion av Microsoft 365 E5 eller betalda prenumerationer med DNS-domänens testlab.\<*your domain name*> registrerat.
- Ett förenklat organisationsintranät som är anslutet till internet och består av virtuella DC1-, APP1- och CLIENT1-datorer på ett undernät i ett virtuellt Azure-nätverk.
- Azure AD Connect körs på APP1 för att synkronisera listan med konton och grupper från Azure AD-klientorganisationen för din Microsoft 365-prenumeration till TESTLAB AD DS-domänen.
- Azure AD Sömlös SSO aktiveras så att datorer på det simulerade intranätet kan logga in på Microsoft 365-molnresurser utan att ange ett lösenord för användarkontot.

## <a name="next-step"></a>Nästa steg

Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.

## <a name="see-also"></a>Se även

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Dokumentation om Microsoft 365 för företag](/microsoft-365-enterprise/)