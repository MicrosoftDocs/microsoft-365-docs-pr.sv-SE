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
ms.openlocfilehash: 3ba229a62f66cad715f604bab91cd12032da7be8
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685778"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a>Sömlös enkel inloggning med Azure AD för din Microsoft 365-testmiljö

*Den här test laboratorie guiden kan användas för både Microsoft 365 för företags-och Office 365 företags test miljöer.*

Med Azure AD sömlös enkel inloggning (SSO) kan du automatiskt logga in användare när de använder sina datorer eller enheter som är anslutna till organisationens nätverk. Sömlös SSO med Azure AD ger användare enkelt åtkomst till molnbaserade program utan att några ytterligare lokala komponenter behövs.

I den här artikeln beskrivs hur du kan konfigurera Microsoft 365-testmiljön för sömlös SSO med Azure AD.

Det finns två faser för att konfigurera detta:

1.    Skapa Microsoft 365-testmiljön för det simulerade företaget med synkronisering av lösenordshash.
2.    Konfigurera Azure AD Connect på APP1 för sömlös SSO med Azure AD.
    
![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med testlabbguider för Microsoft 365 för företag.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön

Följ anvisningarna i [synkronisering av lösenordshash för Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Här är konfigurationsresultatet.
  
![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Konfigurationen består av: 
  
- En utvärderingsprenumeration eller betald prenumeration på Microsoft 365 E5.
- Ett förenklat företagsintranät anslutet till Internet som består av de virtuella datorerna DC1, APP1 och CLIENT1 i ett undernät i ett virtuellt Azure-nätverk. 
- Azure AD Connect körs på APP1 så att TESTLAB AD DS-domänen (Active Directory Domain Services) synkroniseras med Azure AD-klientorganisationen för dina Microsoft 365-prenumerationer med jämna mellanrum.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a>Fas 2: Konfigurera Azure AD Connect på APP1 för sömlös SSO med Azure AD

I den här fasen konfigurerar du Azure AD Connect på APP1 för sömlös SSO med Azure AD och kontrollerar sedan att det fungerar.

### <a name="configure-azure-ad-connect-on-app1"></a>Konfigurera Azure AD Connect på APP1

1. Logga in på [Azure-portalen](https://portal.azure.com) med ditt globala administratörskonto och anslut sedan till APP1 med kontot TESTLAB\User1.

2. Kör Azure AD Connect på skrivbordet för APP1.

3. På **välkomstsidan** klickar du på **Konfigurera**.

4. På sidan **Ytterligare aktiviteter** klickar du på **Ändra användarinloggning** och sedan på **Nästa**.

5. På sidan **Anslut till Azure AD** skriver du autentiseringsuppgifterna för ditt globala administratörskonto. Klicka sedan på **Nästa**.

6. På sidan **Användarinloggning** väljer du **Aktivera enkel inloggning** och klickar sedan på **Nästa**.

7. På sidan **Aktivera enkel inloggning** klickar du på **Ange autentiseringsuppgifter**.

8. I dialogrutan **Windows-säkerhet** skriver du **user1** och lösenordet för user1-kontot. Klicka sedan på **OK**. Klicka på **Nästa**.

9. På sidan **Klart att konfigurera** klickar du på **Konfigurera**.

10. På sidan **Konfigurationen är klar** klickar du på **Avsluta**.

11. Gå till den vänstra rutan i Azure-portalen och klicka på **Azure Active Directory > Azure AD Connect**. Kontrollera att funktionen **Sömlös enkel inloggning** visas som **Aktiverad**.

Prova sedan att logga in på ditt abonnemang med <strong>user1@testlab.</strong>\<your public domain> användarnamn för Användare1-kontot.

1. Från Internet Explorer på APP1 klickar du på ikonen för inställningar och sedan på **Internetalternativ**.
 
2. I **Internetalternativ** klickar du på fliken **Säkerhet**.

3. Klicka på **Lokalt intranät** och sedan på **Webbplatser**.

4. I **Lokalt intranät** klickar du på **Avancerat**.

5. I **Lägg till följande webbplats i zonen** skriver du **https<span>://</span>autologon.microsoftazuread-sso.com** och klickar på **Lägg till > Stäng > OK > OK**.

6. Logga ut och logga sedan in igen. Den här gången med ett annat konto.

7. När du uppmanas att logga in anger du <strong>user1@testlab.</strong>\<your public domain> och klicka sedan på **Nästa**. Du bör kunna logga in som User1 utan att behöva ange ett lösenord. Detta bekräftar att sömlös enkel inloggning med Azure AD fungerar.

Observera att User1 visserligen har domänadministratörsbehörighet för TESTLAB AD DS-domänen, men är inte global administratör för Azure AD. Därför visas inte **administratörsikonen** som ett alternativ.

Här är konfigurationsresultatet:

![Det simulerade företaget med en testmiljö med direktautentisering](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

 
Konfigurationen består av:

- En utvärderings version av Microsoft 365 E5 eller betalda abonnemang med DNS-testlab.\<your domain name> registrerat.
- Ett förenklat företagsintranät anslutet till Internet som består av de virtuella datorerna DC1, APP1 och CLIENT1 i ett undernät i ett virtuellt Azure-nätverk. 
- Azure AD Connect körs på APP1 så att listan med konton och grupper synkroniseras från Azure AD-klientorganisationen för dina Microsoft 365-prenumerationer till TESTLAB AD DS-domänen. 
- Sömlös enkel inloggning med Azure AD är aktiverat så att datorer i det simulerade intranätet kan logga in i Microsoft 365-molnresurser utan att ange ett lösenord för användarkontot.

## <a name="next-step"></a>Nästa steg

Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.

## <a name="see-also"></a>Se även

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Microsoft 365 för företags dokumentation](https://docs.microsoft.com/microsoft-365-enterprise/)


