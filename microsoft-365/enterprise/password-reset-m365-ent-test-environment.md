---
title: Återställning av lösenord i testmiljön för Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/13/2019
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
description: 'Sammanfattning: Konfigurera och testa återställning av lösenord i testmiljön för Microsoft 365.'
ms.openlocfilehash: efcaaf9ed1873c0908bb0e64644b8e10de280a01
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921498"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a>Återställning av lösenord i testmiljön för Microsoft 365

*Den här testlabbguiden kan endast användas Microsoft 365 för företagstestmiljöer.*

Med självbetjäningen för återställning av lösenord (SSPR) i Azure Active Directory (Azure AD) kan användarna återställa eller låsa upp sina lösenord eller konton.

I den här artikeln beskrivs hur du konfigurerar och testar återställning av lösenord Microsoft 365 i testmiljön.

Att konfigurera SSPR innebär tre faser:
- [Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Fas 2: Aktivera tillbakaskrivning av lösenord](#phase-2-enable-password-writeback)
- [Steg 3: Konfigurera och testa återställning av lösenord](#phase-3-configure-and-test-password-reset)
    
![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> En visuell karta till alla artiklar i Microsoft 365 för företags testlabbguide stack finns i [Microsoft 365 för företags testlabbguide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön

Följ först anvisningarna i [Synkronisering av lösenordshash](password-hash-sync-m365-ent-test-environment.md). 

Den resulterande konfigurationen ser ut så här:
  
![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Konfigurationen består av:
  
- En utvärderingsprenumeration eller betald prenumeration på Microsoft 365 E5.
- Ett förenklat organisationsintranät som är anslutet till internet och består av virtuella DC1-, APP1- och CLIENT1-datorer på ett undernät i ett virtuellt Azure-nätverk.
- Azure AD Connect körs på APP1 så att TESTLAB AD DS-domänen (Active Directory Domain Services) synkroniseras med Azure AD-klientorganisationen för dina Microsoft 365-prenumerationer.

## <a name="phase-2-enable-password-writeback"></a>Fas 2: Aktivera tillbakaskrivning av lösenord

Följ anvisningarna i [fas 2 i testlabbguiden för tillbakaskrivning av lösenord](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).

Du måste aktivera tillbakaskrivning av lösenord för att kunna använda återställning av lösenord.
  
## <a name="phase-3-configure-and-test-password-reset"></a>Steg 3: Konfigurera och testa återställning av lösenord

I den här fasen konfigurerar du återställning av lösenord i Azure AD-klientorganisationen via gruppmedlemskap och kontrollerar sedan att det fungerar.

Börja med att aktivera återställning av lösenord för kontona i en specifik Azure AD-grupp.

1. Öppna [https://portal.azure.com](https://portal.azure.com) i en privat instans av webbläsaren och logga sedan in med inloggningsuppgifterna för ditt globala administratörskonto.
2. I Azure-portalen väljer du **Azure Active Directory**  >  **Grupper**  >  **Ny grupp.**
3. Ange **Grupptyp** som **Säkerhet**, **Gruppnamn** som **PWReset** och **Typ av medlemskap** som **Tilldelad**.
4. Välj **Medlemmar**, sök efter och **välj Användare 3**, **välj Välj** och välj sedan **Skapa**.
5. Stäng fönstret **Grupper**.
6. I Azure Active Directory väljer du Återställning **av lösenord i** det vänstra navigeringsfältet.
7. I fönstret **Egenskaper för återställning av lösenord**, under alternativet **Återställning av lösenord via självbetjäning har aktiverats**, väljer du **Vald**.
8. Välj **Välj grupp**, välj gruppen **PWReset** och välj sedan **Välj**  >  **Spara**.
9. Stäng den privata webbläsarinstansen.

Testa sedan återställning av lösenord för User 3-kontot.

1. Öppna en ny privat webbläsarinstans och gå till [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).
1. Logga in med inloggningsuppgifterna för Användare 3-kontot.
1. Välj **Nästa i Mer information** **krävs.** 
1. I **Förlora aldrig åtkomsten till ditt konto** anger du ditt mobiltelefonnummer som telefonnummer för autentisering och ditt e-postkonto på jobbet eller ditt privata e-postkonto som e-postmeddelande för autentisering.
1. När båda har verifierats väljer **du Ser bra** ut och stänger sedan den privata instansen av webbläsaren.
1. I en ny privat webbläsarinstans går du till [https://aka.ms/sspr](https://aka.ms/sspr) .
1. Ange användarkontots namn för User 3, ange tecknen från CAPTCHA och välj sedan **Nästa.**
1. För **verifiering steg 1** väljer du Skicka **e-post med alternativ e-post** och väljer sedan **E-post**. När du får e-postmeddelandet anger du verifieringskoden och väljer **nästa**.
1. Ange **ett nytt lösenord för Användarkontot** under Komma in på ditt konto igen och välj sedan **Slutför**. Notera det ändrade lösenordet för kontot Användare 3 och förvara det på en säker plats.
1. Gå till [https://portal.office.com](https://portal.office.com) på en separat flik i samma webbläsare och logga sedan in med kontonamnet Användare 3 och det nya lösenordet. Du bör se **startsidan för Microsoft Office**.

## <a name="next-step"></a>Nästa steg

Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.

## <a name="see-also"></a>Se även

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Dokumentation om Microsoft 365 för företag](/microsoft-365-enterprise/)