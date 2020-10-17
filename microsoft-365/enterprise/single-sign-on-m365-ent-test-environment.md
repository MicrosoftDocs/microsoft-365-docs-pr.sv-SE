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
ms.openlocfilehash: f98f82de50feb2a9f92d1ecc4775c5307b314a72
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487612"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a>Sömlös enkel inloggning med Azure AD för din Microsoft 365-testmiljö

*Den här test laboratorie guiden kan användas för både Microsoft 365 för företags-och Office 365 företags test miljöer.*

Azure AD-sömlös enda Sign-On (sömlös SSO) loggar automatiskt in användare när de använder sina datorer eller enheter som är anslutna till deras organisations nätverk. Sömlös SSO med Azure AD ger användare enkelt åtkomst till molnbaserade program utan att några ytterligare lokala komponenter behövs.

I den här artikeln beskrivs hur du konfigurerar din Microsoft 365 test miljö för Azure AD sömlös SSO.

Installation av Azure AD sömlös SSO handlar om två faser:
- [Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Fas 2: Konfigurera Azure AD Connect på APP1 för sömlös SSO med Azure AD](#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso)
   
![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Om du vill visa en visuell karta till alla artiklar i gruppen Microsoft 365 för Enterprise-testlabbet går du till [Microsoft 365 för Enterprise Test Lab-guide](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön

Följ anvisningarna i [synkronisering av lösenordshash för Microsoft 365](password-hash-sync-m365-ent-test-environment.md). 

Den resulterande konfigurationen ser ut så här:
  
![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Konfigurationen består av:
  
- En utvärderingsprenumeration eller betald prenumeration på Microsoft 365 E5.
- En förenklad organisations intranät som är ansluten till Internet, bestående av de virtuella datorerna DC1, APP1 och KLIENT1 i ett undernät för ett Azure Virtual Network.
- Azure AD Connect körs på APP1 för att synkronisera TESTLAB AD DS-domän (Active Directory Domain Services) regelbundet till Azure AD-klient organisationen för din Microsoft 365-prenumeration.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a>Fas 2: Konfigurera Azure AD Connect på APP1 för sömlös SSO med Azure AD

I den här fasen konfigurerar du Azure AD Connect på APP1 för Azure AD sömlös SSO och kontrollerar sedan att det fungerar.

### <a name="configure-azure-ad-connect-on-app1"></a>Konfigurera Azure AD Connect på APP1

1. Logga in på [Azure-portalen](https://portal.azure.com) med ditt globala administratörskonto och anslut sedan till APP1 med kontot TESTLAB\User1.

2. Kör Azure AD Connect från APP1 skriv bord.

3. På **Välkomst sidan**väljer du **Konfigurera**.

4. På sidan **Ytterligare aktiviteter** väljer du **ändra användar inloggning**och sedan **Nästa**.

5. På sidan **Anslut till Azure AD** anger du dina globala administratörs konto uppgifter och väljer sedan **Nästa**.

6. På **inloggnings** sidan för användare väljer du **aktivera enkel inloggning**och sedan **Nästa**.

7. På sidan **aktivera enkel inloggning** väljer du **ange autentiseringsuppgifter**.

8. I dialog rutan **Windows-säkerhet** anger du **Användare1** och lösen ordet för user1-kontot, väljer **OK**och sedan **Nästa**.

9. På sidan **redo att konfigurera** väljer du **Konfigurera**.

10. På sidan **slutförd konfigurering** väljer du **Avsluta**.

11. I det vänstra fönstret i Azure-portalen väljer du **Azure Active Directory**  >  **Azure AD Connect**. Kontrollera att funktionen **Sömlös enkel inloggning** visas som **Aktiverad**.

Prova sedan att logga in på ditt abonnemang med <strong>user1@testlab.</strong>\<*your public domain*> användarnamn för Användare1-kontot.

1. I Internet Explorer på APP1 väljer du ikonen Inställningar och sedan **Internet-alternativ**.
 
2. I **Internet alternativ**väljer du fliken **säkerhet** .

3. Välj **Lokalt intranät**och välj sedan **webbplatser**.

4. I **Lokalt intranät**väljer du **Avancerat**.

5. I **Lägg till den här webbplatsen i zonen**anger du **https<span>://</span>AutoLogon.microsoftazuread-SSO.com**väljer du **Add**  >  **Close**  >  **OK**  >  **OK**.

6. Logga ut och logga sedan in igen. Den här gången med ett annat konto.

7. När du uppmanas att logga in anger du <strong>user1@testlab.</strong>\<*your public domain*> och välj sedan **Nästa**. Du bör kunna logga in som User1 utan att behöva ange ett lösenord. Detta bekräftar att sömlös enkel inloggning med Azure AD fungerar.

Observera att User1 visserligen har domänadministratörsbehörighet för TESTLAB AD DS-domänen, men är inte global administratör för Azure AD. Därför visas inte **administratörsikonen** som ett alternativ.

Här är konfigurationsresultatet:

![Det simulerade företaget med en testmiljö med direktautentisering](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

Konfigurationen består av:

- En utvärderings version av Microsoft 365 E5 eller betalda abonnemang med DNS-testlab.\<*your domain name*> registrerat.
- En förenklad organisations intranät som är ansluten till Internet, bestående av de virtuella datorerna DC1, APP1 och KLIENT1 i ett undernät för ett Azure Virtual Network.
- Azure AD Connect körs på APP1 för att synkronisera listan med konton och grupper från Azure AD-klientorganisationen för din Microsoft 365-prenumeration till TESTLAB AD DS-domänen.
- Azure AD sömlös SSO är aktiverat så att datorer i det simulerade intranätet kan logga in på Microsoft 365-moln resurser utan att ange ett lösen ord för kontot.

## <a name="next-step"></a>Nästa steg

Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.

## <a name="see-also"></a>Se även

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Microsoft 365 för företags dokumentation](https://docs.microsoft.com/microsoft-365-enterprise/)
