---
title: Direktautentisering för Microsoft 365-testmiljön
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
description: 'Sammanfattning: Konfigurera direktautentisering för Microsoft 365-testmiljön.'
ms.openlocfilehash: 4f9941b017f00b40a6ae7e893211131cae51c611
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806441"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a>Direktautentisering för Microsoft 365-testmiljön

*Den här testlabbguiden kan användas i både Microsoft 365 Enterprise- och Office 365 Enterprise-testmiljöer.*

Organisationer som direkt vill använda sin lokala Active Directory Domain Services-infrastruktur vid autentisering till Microsofts molnbaserade tjänster och program, kan använda direktautentisering. I den här artikeln beskrivs hur du konfigurerar Microsoft 365-testmiljön för direktautentisering, vilket ger följande konfiguration:
  
![Det simulerade företaget med en testmiljö med direktautentisering](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
Konfigurationen av testmiljön består av två faser:

1.  Skapa Microsoft 365-testmiljön för det simulerade företaget med synkronisering av lösenordshash.
2.  Konfigurera Azure AD Connect på APP1 för direktautentisering.
    
![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med Microsoft 365 Enterprise-testlabbguider.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön

Följ anvisningarna i [synkronisering av lösenordshash för Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Här är konfigurationsresultatet.
  
![Det simulerade företaget med en testmiljö för synkronisering av lösenordshash](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Konfigurationen består av: 
  
- Utvärderingsversioner av eller betalda prenumerationer för Microsoft 365 E5 eller Office 365 E5.
- Ett förenklat företagsintranät som är anslutet till Internet. Det består av de virtuella datorerna DC1, APP1 och CLIENT1 som körs i ett undernät i ett virtuellt Azure-nätverk. Azure AD Connect körs på APP1 för att synkronisera TESTLAB AD DS-domänen med Azure AD-klientorganisationen för din Microsoft 365- eller Office 365-prenumeration regelbundet.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a>Fas 2: Konfigurera Azure AD Connect på APP1 för direktautentisering

I den här fasen konfigurerar du att Azure AD Connect använder direktautentisering på APP1 och sedan kontrollerar du att det fungerar.

### <a name="configure-azure-ad-connect-on-app1"></a>Konfigurera Azure AD Connect på APP1

1.  Logga in på [Azure-portalen](https://portal.azure.com) med ditt globala administratörskonto och anslut sedan till APP1 med kontot TESTLAB\User1.

2.  Kör Azure AD Connect på skrivbordet för APP1.

3.  På **välkomstsidan** klickar du på **Konfigurera**.

4.  På sidan Ytterligare uppgifter klickar du på **Ändra användarinloggning** och sedan på **Nästa**.

5.  På sidan **Anslut till Azure AD** skriver du dina globala administratörsautentiseringsuppgifter. Klicka sedan på **Nästa**.

6.  På sidan **Användarinloggning** klickar du på **Direktautentisering** och sedan på **Nästa**.

7.  Klicka på **Konfigurera** på sidan **Klart att konfigurera**.

8.  På sidan **Konfigurationen är klar** klickar du på **Avsluta**.

9.  Gå till den vänstra rutan i Azure-portalen och klicka på **Azure Active Directory > Azure AD Connect**. Kontrollera att funktionen **Direktautentisering** visas som **Aktiverad**.

10. Klicka på **Direktautentisering**. I fönstret **Direktautentisering** visas servrarna där dina autentiseringsagenter är installerade. Du bör se APP1 i listan. Stäng fönstret **Direktautentisering**.

Prova sedan att det går att logga in på din prenumeration med <strong>user1@testlab.</strong>\<din offentliga domän> användarnamnet för User1-kontot.

1. Logga ut från APP1 och logga sedan in igen med ett annat konto.

2. När du uppmanas att ange ett användarnamn och lösenord, skriver du <strong>user1@testlab.</strong>\<din offentliga domän> och User1-lösenordet. Nu ska du loggas in som User1.

Observera att User1 visserligen har domänadministratörsbehörighet för TESTLAB AD DS-domänen, men den är inte global administratör. Därför visas inte ikonen **Administratör** som ett alternativ.

Här är konfigurationsresultatet:

![Det simulerade företaget med en testmiljö med direktautentisering](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
Konfigurationen består av:

- Utvärderingsversion eller betald prenumeration för Microsoft 365 E5 eller Office 365 E5 med DNS-domänen testlab.\<ditt domännamn> registrerad.
- Ett förenklat företagsintranät som är anslutet till Internet. Det består av de virtuella datorerna DC1, APP1 och CLIENT1 som körs i ett undernät i ett virtuellt Azure-nätverk. En autentiseringsagent körs i APP1 och hanterar direktautentiseringsbegäranden från Azure AD-klienten för din Microsoft 365- eller Office 365-prenumeration.

## <a name="next-step"></a>Nästa steg

Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.

## <a name="see-also"></a>Se även

[Testlabbguider för Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Distribuera Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise-dokumentation](https://docs.microsoft.com/microsoft-365-enterprise/)
