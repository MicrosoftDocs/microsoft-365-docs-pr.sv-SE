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
ms.openlocfilehash: 5d98dcc50f16bc08da787a928beeeacf825201c9
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487430"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a>Återställning av lösenord i testmiljön för Microsoft 365

*Den här test laboratorie guiden kan endast användas för test miljöer med Microsoft 365 för företags nätverk.*

Med självbetjäningen för återställning av lösenord (SSPR) i Azure Active Directory (Azure AD) kan användarna återställa eller låsa upp sina lösenord eller konton.

I den här artikeln beskrivs hur du konfigurerar och testar återställning av lösen ord i Microsoft 365 test miljö.

Att konfigurera SSPR inbegriper tre faser:
- [Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Fas 2: Aktivera tillbakaskrivning av lösenord](#phase-2-enable-password-writeback)
- [Steg 3: Konfigurera och testa återställning av lösenord](#phase-3-configure-and-test-password-reset)
    
![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Om du vill visa en visuell karta till alla artiklar i gruppen Microsoft 365 för Enterprise-testlabbet går du till [Microsoft 365 för Enterprise Test Lab-guide](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön

Följ först anvisningarna i [Synkronisering av lösenordshash](password-hash-sync-m365-ent-test-environment.md). 

Den resulterande konfigurationen ser ut så här:
  
![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Konfigurationen består av:
  
- En utvärderingsprenumeration eller betald prenumeration på Microsoft 365 E5.
- En förenklad organisations intranät som är ansluten till Internet, bestående av de virtuella datorerna DC1, APP1 och KLIENT1 i ett undernät för ett Azure Virtual Network.
- Azure AD Connect körs på APP1 så att TESTLAB AD DS-domänen (Active Directory Domain Services) synkroniseras med Azure AD-klientorganisationen för dina Microsoft 365-prenumerationer.

## <a name="phase-2-enable-password-writeback"></a>Fas 2: Aktivera tillbakaskrivning av lösenord

Följ anvisningarna i [fas 2 i testlabbguiden för tillbakaskrivning av lösenord](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).

Du måste aktivera tillbakaskrivning av lösenord för att kunna använda återställning av lösenord.
  
## <a name="phase-3-configure-and-test-password-reset"></a>Steg 3: Konfigurera och testa återställning av lösenord

I den här fasen konfigurerar du återställning av lösen ord i Azure AD-klient organisationen via grupp medlemskap och kontrollerar sedan att det fungerar.

Börja med att aktivera återställning av lösenord för kontona i en specifik Azure AD-grupp.

1. Öppna [https://portal.azure.com](https://portal.azure.com) i en privat instans av webbläsaren och logga sedan in med inloggningsuppgifterna för ditt globala administratörskonto.
2. I Azure-portalen väljer du ny grupp för **Azure Active Directory**-  >  **grupper**  >  **New group**.
3. Ange **Grupptyp** som **Säkerhet**, **Gruppnamn** som **PWReset** och **Typ av medlemskap** som **Tilldelad**.
4. Välj **medlemmar**, Sök och välj **användare 3**, Välj **Välj**och sedan **skapa**.
5. Stäng fönstret **Grupper**.
6. I fönstret Azure Active Directory väljer du **Återställ lösen ord** i det vänstra navigerings fältet.
7. I fönstret **Egenskaper för återställning av lösenord**, under alternativet **Återställning av lösenord via självbetjäning har aktiverats**, väljer du **Vald**.
8. Välj **Välj grupp**, Markera gruppen **PWReset** och välj sedan **Välj**  >  **Spara**.
9. Stäng den privata webbläsarinstansen.

Testa sedan lösen ords återställning för användare 3-kontot.

1. Öppna en ny privat webbläsarinstans och gå till [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).
1. Logga in med inloggningsuppgifterna för Användare 3-kontot.
1. Välj **Nästa**om du vill **ha mer information**. 
1. I **Förlora aldrig åtkomsten till ditt konto** anger du ditt mobiltelefonnummer som telefonnummer för autentisering och ditt e-postkonto på jobbet eller ditt privata e-postkonto som e-postmeddelande för autentisering.
1. När båda har verifierats väljer du **ser bra ut**och stänger sedan den privata instansen av webbläsaren.
1. Gå till i en ny privat webb läsar instans [https://aka.ms/sspr](https://aka.ms/sspr) .
1. Ange användare 3-konto namnet, ange tecknen från CAPTCHA och välj sedan **Nästa**.
1. För **verifiering steg 1**väljer du **e-post för min alternativa e-post**och väljer sedan **e-post**. Ange verifierings koden när du får e-postmeddelandet och välj sedan **Nästa**.
1. Gå in på **ditt konto**och ange ett nytt lösen ord för kontot för användare 3 och välj sedan **Slutför**. Notera det ändrade lösenordet för kontot Användare 3 och förvara det på en säker plats.
1. Gå till [https://portal.office.com](https://portal.office.com) på en separat flik i samma webbläsare och logga sedan in med kontonamnet Användare 3 och det nya lösenordet. Du bör se **startsidan för Microsoft Office**.

## <a name="next-step"></a>Nästa steg

Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.

## <a name="see-also"></a>Se även

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Microsoft 365 för företags dokumentation](https://docs.microsoft.com/microsoft-365-enterprise/)
