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
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Sammanfattning: Konfigurera och testa återställning av lösenord i testmiljön för Microsoft 365.'
ms.openlocfilehash: c8d5ed0c7feac98afd3230a305f4ab1f850ca7f8
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42806789"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a>Återställning av lösenord i testmiljön för Microsoft 365

*Den här testlabbguiden kan bara användas i Microsoft 365 Enterprise-testmiljöer.*

Med självbetjäningen för återställning av lösenord (SSPR) i Azure Active Directory (Azure AD) kan användarna återställa eller låsa upp sina lösenord eller konton. 

I den här artikeln beskrivs hur du kan konfigurera och testa lösenordsåterställning i Microsoft 365-testmiljön i tre faser:

1.  Skapa testmiljön för Microsoft 365 Enterprise.
2.  Aktivera tillbakaskrivning av lösenord.
3.  Konfigurera och testa lösenordsåterställningen för kontot Användare 3.
    
![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med Microsoft 365 Enterprise-testlabbguider.

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön

Följ först anvisningarna i [Synkronisering av lösenordshash](password-hash-sync-m365-ent-test-environment.md). Här är konfigurationsresultatet.
  
![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Konfigurationen består av: 
  
- Utvärderingsversioner eller betalda prenumerationer för Microsoft 365 E5 eller Office 365 E5.
- Ett förenklat företagsintranät anslutet till Internet som består av de virtuella datorerna DC1, APP1 och CLIENT1 i ett undernät i ett virtuellt Azure-nätverk. 
- Azure AD Connect körs på APP1 så att TESTLAB AD DS-domänen (Active Directory Domain Services) synkroniseras med Azure AD-klientorganisationen för din Microsoft 365- eller Office 365-prenumeration.

## <a name="phase-2-enable-password-writeback"></a>Fas 2: Aktivera tillbakaskrivning av lösenord

Följ anvisningarna i [fas 2 i testlabbguiden för tillbakaskrivning av lösenord](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).

Du måste aktivera tillbakaskrivning av lösenord för att kunna använda återställning av lösenord.
  
## <a name="phase-3-configure-and-test-password-reset"></a>Steg 3: Konfigurera och testa återställning av lösenord

I den här fasen konfigurerar du återställning av lösenord i Azure AD-klientorganisationen via gruppmedlemskap och kontrollerar sedan att det fungerar.

Börja med att aktivera återställning av lösenord för kontona i en specifik Azure AD-grupp.

1. Öppna [https://portal.azure.com](https://portal.azure.com) i en privat instans av webbläsaren och logga sedan in med inloggningsuppgifterna för ditt globala administratörskonto.
2. I Azure-portalen klickar du på **Azure Active Directory > Grupper > Ny grupp**.
3. Ange **Grupptyp** som **Säkerhet**, **Gruppnamn** som **PWReset** och **Typ av medlemskap** som **Tilldelad**. 
4. Klicka på **Medlemmar**, leta upp och välj **Användare 3** och klicka sedan på **Välj** och på **Skapa**.
5. Stäng fönstret **Grupper**.
6. I Azure Active Directory-fönstret klickar du på **Återställ lösenord** i det vänstra navigeringsfältet.
7. I fönstret **Egenskaper för återställning av lösenord**, under alternativet **Återställning av lösenord via självbetjäning har aktiverats**, väljer du **Vald**.
8. Klicka på **Välj grupp**, välj gruppen **PWReset** och klicka sedan på **Välj > Spara**.
9. Stäng den privata webbläsarinstansen.

Testa därefter lösenordsåterställningen för kontot Användare 3.

1. Öppna en ny privat webbläsarinstans och gå till [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).
2. Logga in med inloggningsuppgifterna för Användare 3-kontot.
3. I **Mer information krävs** klickar du på **Nästa**. 
5. I **Förlora aldrig åtkomsten till ditt konto** anger du ditt mobiltelefonnummer för telefonnummer för autentisering och ditt e-postkonto för arbetet eller ditt personliga e-postkonto för e-postmeddelande för autentisering.
7. När båda har verifierats klickar du på **Ser bra ut** och stänger den privata instansen av webbläsaren.
8. Öppna en ny privat webbläsarinstans och gå till [https://aka.ms/sspr](https://aka.ms/sspr).
9. Skriv in Användare 3-kontonamnet, skriv tecknen som finns i CAPTCHA och klicka sedan på **Nästa**.
10. För **verifieringssteg 1** klickar du på **Skicka e-post till min alternativa e-postadress** och sedan på **E-post**. När du får e-postmeddelandet skriver du verifieringskoden och klickar sedan på **Nästa**.
11. I **Få tillgång till kontot igen** skriver du ett nytt lösenord för Användare 3-kontot och klickar på **Slutför**. Notera det ändrade lösenordet för kontot Användare 3 och förvara det på en säker plats.
12. Gå till [https://portal.office.com](https://portal.office.com) på en separat flik i samma webbläsare och logga sedan in med kontonamnet Användare 3 och det nya lösenordet. Du bör se **startsidan för Microsoft Office**.

I steget [Enklare återställning av lösenord](identity-secure-your-passwords.md#identity-pw-reset) i Identitet-fasen finns mer information om och länkar till hur du konfigurerar återställning av lösenord i produktion.

## <a name="next-step"></a>Nästa steg

Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.

## <a name="see-also"></a>Se även

[Testlabbguider för Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Distribuera Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise-dokumentation](https://docs.microsoft.com/microsoft-365-enterprise/)
