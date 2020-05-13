---
title: Multifaktorautentisering för testmiljön för Microsoft 365 Enterprise
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
description: Konfigurera multifaktorautentisering med textmeddelanden som skickas till en smart telefon i testmiljön för Microsoft 365 Enterprise.
ms.openlocfilehash: ae8cab25a20cc75992eecc600219d9f1dd869b63
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213146"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a>Multifaktorautentisering för testmiljön för Microsoft 365 Enterprise

*Den här testlabbguiden kan användas i både Microsoft 365 Enterprise- och Office 365 Enterprise-testmiljöer.*

Om du vill ha ytterligare en säkerhetsnivå för att logga in på Microsoft 365 eller någon tjänst eller program som använder Azure AD-klienten för din prenumeration kan du aktivera Azure multifaktorautentisering, vilket kräver mer än bara ett användarnamn och lösenord för att verifiera ett konto. 

Med multifaktorautentisering måste användarna bekräfta ett telefonsamtal, skriva en verifieringskod som skickas i ett textmeddelande eller verifiera autentiseringen med en app på sina smarta telefoner när de har angett sina lösenord korrekt. De kan logga in först när den här andra autentiseringsfaktorn har uppfyllts. 
  
I den här artikeln beskrivs hur du aktiverar och testar textmeddelandebaserad autentisering för ett visst användarkonto.
  
Det finns två faser för att konfigurera multifaktorautentisering för ett konto i microsoft 365 Enterprise-testmiljön:
  
1. Skapa testmiljön för Microsoft 365 Enterprise.
    
2. Aktivera och testa multifaktorautentisering för user 2-kontot.

3. Aktivera och testa multifaktorautentisering med en princip för villkorlig åtkomst (valfritt).

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med Microsoft 365 Enterprise-testlabbguider.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fas 1: Bygga ut testmiljön i Microsoft 365 Enterprise

Om du bara vill testa multifaktorautentisering på ett lätt väg med minimikraven följer du instruktionerna i [Lightweight base-konfigurationen](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Om du vill testa multifaktorautentisering i ett simulerat företag följer du instruktionerna i [Direktautentisering](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testning av multifaktorautentisering kräver inte den simulerade företagstestmiljön, som innehåller ett simulerat intranät som är anslutet till Internet och katalogsynkronisering för en AD DS-skog (Active Directory Domain Services). Det finns här som ett alternativ så att du kan testa multifaktorautentisering och experimentera med den i en miljö som representerar en typisk organisation. 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>Fas 2: Aktivera och testa multifaktorautentisering för user 2-kontot

Aktivera multifaktorautentisering för User 2-kontot med följande steg:
  
1. Öppna en separat, privat instans av webbläsaren, gå till Microsoft 365 admin center ( [https://portal.microsoft.com](https://portal.microsoft.com) ) och logga sedan in med ditt globala administratörskonto.
    
2. Klicka på **Användare > Aktiva användare** i det vänstra navigeringsfönstret.
    
3. Klicka på **Multifaktorautentisering**i fönstret Aktiva användare .
    
4. Välj kontot Användare **2** i listan.
    
5. Klicka på **Aktivera**under **Snabbsteg**i avsnittet **Användare 2.**
    
6. Klicka på **Aktivera autentisering**med flera faktorer i dialogrutan **Om att aktivera autentisering med flera faktorer.**
    
7. Klicka på **Stäng**i dialogrutan **Uppdateringar.**
    
8. Klicka på ikonen för användarkontot längst upp till höger på fliken **Administrationscenter för Microsoft 365** och klicka sedan på **Logga ut**.
    
9. Stäng webbläsarinstansen.
   
Slutför konfigurationen för user 2-kontot för att använda ett textmeddelande för validering och testa det med följande steg:
  
1. Öppna en ny, privat instans av din webbläsare.
    
2. Gå till Office 365-portalen ( [https://portal.office.com](https://portal.office.com) ) och logga in med användaren 2-kontonamnet och lösenordet.
    
3. När du har loggat in uppmanas du att konfigurera kontot för mer information. Klicka på **Nästa**.
    
4. På sidan **Ytterligare säkerhetsverifiering:**
    
   - Välj land eller region.
    
   - Skriv telefonnumret till den smarta telefon som tar emot textmeddelanden.
    
   - I **Metod**klickar du på **Skicka mig en kod via sms**.
    
5. Klicka på **Nästa**.
    
6. Ange verifieringskoden från det mottagna sms:et på den smarta telefonen och klicka sedan på **Verifiera**.
    
7. På **steg 3: Behåll din befintliga programsida** klickar du på **Klar.**
    
8. Om det är första gången du loggade in med kontot Användare 2 uppmanas du att ändra lösenordet. Skriv det ursprungliga lösenordet och ett nytt lösenord två gånger och klicka sedan på **Uppdatera lösenord och logga in**. Registrera det nya lösenordet på en säker plats.
    
    Du bör se Office-portalen för användare 2 på fliken **Microsoft Office Home** i webbläsaren.

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a>Fas 3: Aktivera och testa multifaktorautentisering med en princip för villkorlig åtkomst

*Den här fasen kan bara användas för en Microsoft 365 Enterprise-testmiljö.*

I den här fasen aktiverar du multifaktorautentisering för User 3-kontot med hjälp av en grupp och en princip för villkorlig åtkomst.

Skapa sedan en ny grupp med namnet MFAUsers och lägg till kontot användare 3 i den.

1. Klicka på **Grupper** i den vänstra navigeringen på fliken **Administrationscenter i Microsoft 365** och klicka sedan på **Grupper**.
2. Klicka på **Lägg till en grupp**.
3. I fönstret **Välj grupptyp** väljer du **Säkerhet**och klickar sedan på **Nästa**.
4. Klicka på **Skapa grupp**i fönstret **Konfigurera grunderna** och klicka sedan på **Stäng**.
5. Skriv **MFAUsers**i **gruppfönstret Granska och avsluta** och klicka sedan på **Nästa**.
6. Klicka på gruppen **MFAUsers** i listan över grupper.
7. Klicka på **Medlemmar**i fönstret **MFAUsers** och klicka sedan på **Visa alla och hantera medlemmar**.
8. Klicka på **Lägg till medlemmar**i fönstret **MFAUsers,** välj **kontot Användare 3** och klicka sedan på **Spara > Stäng > Stäng**.

Skapa sedan en princip för villkorlig åtkomst för att kräva multifaktorautentisering för medlemmar i MFAUsers-gruppen.

1. Gå till [https://portal.azure.com](https://portal.azure.com) .
2. Klicka på **Azure Active Directory > Security > Conditional Access**.
3. Klicka på **Ny princip**i fönstret Villkorlig åtkomst **– Principer** .
4. Skriv **MFA för användarkonton** i **Namn**i fönstret **Nytt** .
5. Klicka på **Användare och grupper**i avsnittet **Tilldelningar** .
6. Klicka på Markera användare och grupper **> användare och grupper > Markera**på fliken **Inkludera** i fönstret Användare och **grupper.**
7. Klicka på gruppen **MFAUsers** i fönstret **Välj** och klicka sedan på **Markera > klar**.
8. Klicka på **Bevilja**i avsnittet **Access-kontroller** i fönstret **Nytt** .
9. Klicka på **Kräv multifaktorautentisering**i **fönstret Bevilja** och klicka sedan på **Markera**.
10. Klicka på **På** för **att aktivera principen**i fönstret **Nytt** och klicka sedan på **Skapa**.
11. Stäng flikarna **i Azure-portalen** och **Microsoft 365 admin center.**

Om du vill testa den här principen loggar du ut och loggar in med kontot Användare 3. Du bör uppmanas att konfigurera MFA. Detta visar att principen MFAUsers tillämpas.

Se steget [Konfigurera multifaktorautentisering](identity-secure-user-sign-ins.md#identity-mfa) i identitetsfasen för information och länkar för att distribuera multifaktorautentisering i produktion.
    
## <a name="next-step"></a>Nästa steg

Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.

## <a name="see-also"></a>Se även

[Fas 2: Identitet](identity-infrastructure.md)

[Testlabbguider för Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Distribution av Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise-dokumentation](https://docs.microsoft.com/microsoft-365-enterprise/)
