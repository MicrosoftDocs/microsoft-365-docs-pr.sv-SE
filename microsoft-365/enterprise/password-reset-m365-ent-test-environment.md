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
ms.openlocfilehash: 98e6b8d8432c86e9d1c432128ed6d223da83610e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686542"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a>Återställning av lösenord i testmiljön för Microsoft 365

*Den här test laboratorie guiden kan endast användas för test miljöer med Microsoft 365 för företags nätverk.*

Med självbetjäningen för återställning av lösenord (SSPR) i Azure Active Directory (Azure AD) kan användarna återställa eller låsa upp sina lösenord eller konton. 

I den här artikeln beskrivs hur du kan konfigurera och testa lösenordsåterställning i Microsoft 365-testmiljön i tre faser:

1.    Skapa test miljön för Microsoft 365 för företag.
2.  Aktivera tillbakaskrivning av lösenord.
3.    Konfigurera och testa lösenordsåterställningen för kontot Användare 3.
    
![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med testlabbguider för Microsoft 365 för företag.

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön

Följ först anvisningarna i [Synkronisering av lösenordshash](password-hash-sync-m365-ent-test-environment.md). Här är konfigurationsresultatet.
  
![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Konfigurationen består av: 
  
- En utvärderingsprenumeration eller betald prenumeration på Microsoft 365 E5.
- Ett förenklat företagsintranät anslutet till Internet som består av de virtuella datorerna DC1, APP1 och CLIENT1 i ett undernät i ett virtuellt Azure-nätverk. 
- Azure AD Connect körs på APP1 så att TESTLAB AD DS-domänen (Active Directory Domain Services) synkroniseras med Azure AD-klientorganisationen för dina Microsoft 365-prenumerationer.

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
5. I **Förlora aldrig åtkomsten till ditt konto** anger du ditt mobiltelefonnummer som telefonnummer för autentisering och ditt e-postkonto på jobbet eller ditt privata e-postkonto som e-postmeddelande för autentisering.
7. När båda har verifierats klickar du på **Ser bra ut** och stänger den privata instansen av webbläsaren.
8. Öppna en ny privat webbläsarinstans och gå till [https://aka.ms/sspr](https://aka.ms/sspr).
9. Skriv in Användare 3-kontonamnet, skriv tecknen som finns i CAPTCHA och klicka sedan på **Nästa**.
10. För **verifieringssteg 1** klickar du på **Skicka e-post till min alternativa e-postadress** och sedan på **E-post**. När du får e-postmeddelandet skriver du verifieringskoden och klickar sedan på **Nästa**.
11. I **Få tillgång till kontot igen** skriver du ett nytt lösenord för Användare 3-kontot och klickar på **Slutför**. Notera det ändrade lösenordet för kontot Användare 3 och förvara det på en säker plats.
12. Gå till [https://portal.office.com](https://portal.office.com) på en separat flik i samma webbläsare och logga sedan in med kontonamnet Användare 3 och det nya lösenordet. Du bör se **startsidan för Microsoft Office**.

## <a name="next-step"></a>Nästa steg

Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.

## <a name="see-also"></a>Se även

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Microsoft 365 för företags dokumentation](https://docs.microsoft.com/microsoft-365-enterprise/)
