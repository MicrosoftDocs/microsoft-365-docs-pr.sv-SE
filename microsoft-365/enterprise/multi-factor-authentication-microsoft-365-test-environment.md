---
title: Microsoft 365 för företagstestmiljö multifaktorautentisering
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
- seo-marvel-apr2020
description: Konfigurera multifaktorautentisering med sms som skickas till en smartphone i Microsoft 365 för företagstestmiljö.
ms.openlocfilehash: aeb8940a9499909b8c568d1230f9aa45aee07b3d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923762"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a>Multifaktorautentisering för din Microsoft 365 för företagstestmiljö

*Den här testlabbguiden kan användas för både Microsoft 365 för företag Office 365 Enterprise för testmiljöer.*

Om du vill ha ytterligare en säkerhetsnivå för att logga in på Microsoft 365 eller någon tjänst eller ett program som använder Azure AD-klientorganisationen för prenumerationen kan du aktivera multifaktorautentisering i Azure AD, vilket kräver mer än bara ett användarnamn och lösenord för att verifiera ett konto.

Med multifaktorautentisering måste användarna bekräfta ett telefonsamtal, skriva en verifieringskod som skickats i ett sms eller verifiera autentiseringen med en app på sina smartphones när de har skrivit in sina lösenord korrekt. De kan bara logga in efter att den här andra autentiseringsfaktorn är nöjd.
  
I den här artikeln beskrivs hur du aktiverar och testar textmeddelandebaserad autentisering för ett visst användarkonto.
  
Att konfigurera multifaktorautentisering för ett konto i Microsoft 365 för företagstestmiljö omfattar två faser och en tredje valfri fas:
- [Fas 1: Bygg ut din Microsoft 365 för företagstestmiljö](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fas 2: Aktivera och testa multifaktorautentisering för Användarkontot 2](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [Fas 3: Aktivera och testa multifaktorautentisering med en princip för villkorsstyrd åtkomst](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> En visuell karta till alla artiklar i Microsoft 365 för företags testlabbguide stack finns i [Microsoft 365 för företags testlabbguide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fas 1: Bygg ut din Microsoft 365 för företagstestmiljö

Om du bara vill testa multifaktorautentisering på ett lätt sätt med minimikraven följer du anvisningarna i [Enkel baskonfiguration.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Om du vill testa multifaktorautentisering i ett simulerat företag följer du anvisningarna i [Direktautentisering](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Om du testar multifaktorautentisering krävs inte den simulerade företagstestmiljön, som omfattar ett simulerat intranät som är anslutet till Internet och katalogsynkronisering för en AD DS-skog (Active Directory Domain Services). Den finns här som ett alternativ så att du kan testa multifaktorautentisering och experimentera med den i en miljö som representerar en vanlig organisation.
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>Fas 2: Aktivera och testa multifaktorautentisering för Användarkontot 2

Aktivera multifaktorautentisering för User 2-kontot genom att följa de här stegen:
  
1. Öppna en separat, privat instans av webbläsaren, gå Microsoft 365 ( ) [https://portal.microsoft.com](https://portal.microsoft.com) och logga sedan in med ditt globala administratörskonto.
    
2. Välj Användare aktiva användare i det  >  **vänstra navigeringsfältet.**
    
3. Välj Multifaktorautentisering i **fönstret Aktiva användare.**
    
4. Välj Användarkontot användare **2 i** listan.
    
5. I avsnittet **Användare 2,** under **Snabbsteg,** väljer du **Aktivera**.
    
6. I dialogrutan **Om att aktivera Multi-Factor Auth** markerar **du Aktivera Multi-Factor Auth.**
    
7. Välj **Stäng i** dialogrutan Uppdateringar **lyckades.**
    
8. På Microsoft 365 **i administrationscentret** väljer du ikonen för användarkontot längst upp till höger och väljer sedan **Logga ut**.
    
9. Stäng webbläsarinstansen.
   
Slutför konfigurationen för användarkontot för användare 2 för att använda ett textmeddelande för verifiering och testa det med följande steg:
  
1. Öppna en ny, privat instans av webbläsaren.
    
2. Gå till [Microsoft 365 och logga](https://admin.microsoft.com) in med Användarnamn och lösenord för User 2.
    
3. När du har loggat in uppmanas du att konfigurera kontot för mer information. Välj **Nästa**.
    
4. På sidan **Ytterligare säkerhetsverifiering:**
    
   - Välj land eller region.
    
   - Ange telefonnumret för den smartphone som ska ta emot SMS.
    
   - I **Metod** väljer du **Skicka en kod via SMS.**
    
5. Välj **Nästa**.
    
6. Ange verifieringskoden från sms:et du fick på din smartphone och välj sedan **Verifiera**.
    
7. På sidan **Steg 3: Behåll befintliga program** väljer du **Klar**.
    
8. Om det är första gången du loggar in med User 2-kontot uppmanas du att ändra lösenordet. Ange det ursprungliga lösenordet och ett nytt lösenord två gånger och välj sedan **Uppdatera lösenord och logga in**. Registrera det nya lösenordet på en säker plats.
    
    Du bör se Office för användare 2 på **Microsoft Office Start** i webbläsaren.

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a>Fas 3: Aktivera och testa multifaktorautentisering med en princip för villkorsstyrd åtkomst

*Den här fasen kan endast användas för en Microsoft 365 för företagstestmiljö.*

I den här fasen aktiverar du multifaktorautentisering för User 3-kontot med en grupp och en princip för villkorsstyrd åtkomst.

Skapa sedan en ny grupp med namnet MFAUsers och lägg till Användarkontot 3 i den gruppen.

1. På Microsoft 365 **i administrationscentret** väljer **du Grupper i** det vänstra navigeringsfältet och sedan **Grupper.**
2. Välj **Lägg till en grupp**.
3. I fönstret **Välj en grupptyp** väljer **du Säkerhet** och sedan **Nästa**.
4. I **fönstret Konfigurera grunderna väljer** du **Skapa grupp och** sedan **Stäng**.
5. I fönstret **Granska och slutför tillägget av** grupp anger du **MFAUsers** och väljer **sedan Nästa.**
6. Välj gruppen **MFAUsers** i listan över grupper.
7. I fönstret **MFAUsers** väljer du **Members** och sedan **Visa alla och hanterar medlemmar.**
8. I fönstret **MFAUsers** väljer du **Lägg till medlemmar**, väljer **Användarkontot 3** och sedan **Spara**  >  **Stäng**  >  **Stäng.**

Skapa sedan en princip för villkorsstyrd åtkomst för att kräva multifaktorautentisering för medlemmar i gruppen MFAUsers.

1. På en ny flik i webbläsaren går du till [https://portal.azure.com](https://portal.azure.com) .
2. Välj Azure Active Directory   >  **villkorsstyrd**  >  **åtkomst för säkerhet.**
3. I fönstret **Villkorsstyrd åtkomst –** Principer väljer du **Ny princip.**
4. I fönstret **Nytt** anger du **MFA för användarkonton** i **rutan** Namn.
5. I avsnittet **Uppgifter** väljer du **Användare och grupper.**
6. På fliken **Inkludera** i fönstret **Användare och grupper väljer** du Välj användare och grupper **Användare** och  >  **grupper**  >  **Välj**.
7. I fönstret **Välj** väljer du gruppen **MFAUsers** och väljer sedan **Select**  >  **Done**.
8. I avsnittet **Access-kontroller** i **fönstret Nytt** väljer du **Tilldela**.
9. I fönstret **Bevilja** väljer du **Kräv multifaktorautentisering** och väljer sedan **Välj**.
10. I fönstret **Nytt** väljer du **På** för **Aktivera princip** och sedan **Skapa**.
11. Stäng **Azure Portal och** Microsoft 365 **flikarna i administrationscentret.**

Du kan testa den här principen genom att logga ut och logga in med User 3-kontot. Du bör uppmanas att konfigurera MFA. Det visar att MFAUsers-principen tillämpas.

## <a name="next-step"></a>Nästa steg

Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.

## <a name="see-also"></a>Se även

[Identitetsöversikt](identity-roadmap-microsoft-365.md)

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Dokumentation om Microsoft 365 för företag](/microsoft-365-enterprise/)