---
title: Microsoft 365 för företags test miljö multifaktorautentisering
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
description: Konfigurera multifaktorautentisering med text meddelanden som skickas till en smart telefon i test miljön för Microsoft 365 för företag.
ms.openlocfilehash: f41fe7ad933f85c4b44a1e90529a998651412191
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487146"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a>Multifaktorautentisering för test miljön för Microsoft 365 för företag

*Den här test laboratorie guiden kan användas för både Microsoft 365 för företags-och Office 365 företags test miljöer.*

Om du vill ha ytterligare en säkerhets nivå för att logga in på Microsoft 365 eller någon tjänst eller ett program som använder Azure AD-klient organisationen för din prenumeration kan du aktivera Azure Multi-Factor-verifiering, vilket kräver mer än ett användar namn och lösen ord för att verifiera ett konto.

Med multifaktorautentisering måste användare bekräfta ett telefonsamtal, ange en verifierings kod som skickas i ett textmeddelande eller verifiera verifieringen med en app på deras smarta telefoner när du har angett lösen orden korrekt. De kan bara logga in när denna faktor är uppfylld.
  
I den här artikeln beskrivs hur du aktiverar och testar SMS-baserad lösenordsautentisering för ett specifikt användar konto.
  
Att konfigurera multifaktorautentisering för ett konto i test miljön för Microsoft 365 för företag inbegriper två faser och en tredje valfria fas:
- [Fas 1: bygga ut test miljön för Microsoft 365 för företag](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fas 2: Aktivera och testa multifaktorautentisering för användare 2-konto](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [Fas 3: Aktivera och testa multifaktorautentisering med en princip för villkorsstyrd åtkomst](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Om du vill visa en visuell karta till alla artiklar i gruppen Microsoft 365 för Enterprise-testlabbet går du till [Microsoft 365 för Enterprise Test Lab-guide](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fas 1: bygga ut test miljön för Microsoft 365 för företag

Om du bara vill testa multifaktorautentisering på ett lättviktigt sätt med minimi kraven följer du anvisningarna i [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Om du vill testa multifaktorautentisering i ett simulerat företag följer du anvisningarna i [vidarekoppling](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testning av multifaktorautentisering kräver inte den simulerade företags test miljön, som innehåller ett simulerat intranät som är kopplat till Internet-och katalogs-synkronisering för en AD DS-skog (Active Directory Domain Services). Det finns ett alternativ som gör att du kan testa multifaktorautentisering och experimentera med den i en miljö som representerar en typisk organisation.
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>Fas 2: Aktivera och testa multifaktorautentisering för användare 2-konto

Aktivera multifaktorautentisering för användare 2-kontot med de här stegen:
  
1. Öppna en separat privat instans av webbläsaren, gå till administrations centret för Microsoft 365 [https://portal.microsoft.com](https://portal.microsoft.com) och logga in med ditt globala administratörs konto.
    
2. I det vänstra navigerings fältet väljer **du användare**  >  **aktiva användare**.
    
3. I fönstret aktiva användare väljer du **multifaktorautentisering**.
    
4. I listan väljer du **användare 2** -konto.
    
5. I avsnittet **User 2** under **snabb steg**väljer du **Aktivera**.
    
6. I dialog rutan **om aktivering av multifaktorautentisering** väljer du **Aktivera multifaktorautentisering**.
    
7. I dialog rutan **updates lyckades** väljer du **Stäng**.
    
8. På fliken **administrations Center för Microsoft 365** väljer du ikonen användar konto längst upp till höger och väljer sedan **Logga ut**.
    
9. Stäng din instans av webbläsaren.
   
Slutför konfigurationen för användare 2-kontot för att använda ett textmeddelande för verifiering och testa det med de här stegen:
  
1. Öppna en ny privat instans av webbläsaren.
    
2. Gå till [administrations centret för Microsoft 365](https://admin.microsoft.com) och logga in med användar namnet för användare 2 och lösen ordet.
    
3. När du har loggat in uppmanas du att konfigurera kontot för mer information. Välj **Nästa**.
    
4. På sidan **ytterligare säkerhets verifiering** :
    
   - Välj land eller region.
    
   - Ange telefonnumret till den smarta telefon som ska ta emot textmeddelanden.
    
   - I **metod**väljer du **skicka en kod efter SMS**.
    
5. Välj **Nästa**.
    
6. Ange verifierings koden från textmeddelandet som visas på din mobil telefon och välj sedan **Verifiera**.
    
7. På sidan **steg 3: Behåll dina befintliga program** väljer du **klar**.
    
8. Om det är första gången du loggar in med User 2-kontot uppmanas du att ändra lösen ordet. Ange det ursprungliga lösen ordet och ett nytt lösen ord två gånger och välj sedan **Uppdatera lösen ord och logga in**. Spela in det nya lösen ordet på en säker plats.
    
    Du bör se Office-portalen för användare 2 på fliken **Microsoft Office-Startsida** i webbläsaren.

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a>Fas 3: Aktivera och testa multifaktorautentisering med en princip för villkorsstyrd åtkomst

*Den här fasen kan endast användas för test miljön Microsoft 365 för företag.*

I den här fasen aktiverar du multifaktorautentisering för användare 3-kontot med hjälp av en grupp och en princip för villkorsstyrd åtkomst.

Skapa sedan en ny grupp med namnet MFAUsers och Lägg till användare 3-kontot i den.

1. Gå till fliken **administrations Center för Microsoft 365** , Välj **grupper** i det vänstra navigerings fältet och välj sedan **grupper**.
2. Välj **Lägg till en grupp**.
3. I fönstret **Välj en grupptyp** väljer du **säkerhet**och sedan **Nästa**.
4. I fönstret **Konfigurera grunderna väljer du** **Skapa grupp**och sedan **Stäng**.
5. Ange **MFAUsers**i fönstret **Granska och slutför** och välj sedan **Nästa**.
6. I listan med grupper väljer du gruppen **MFAUsers** .
7. I fönstret **MFAUsers** väljer du **medlemmar**och sedan **Visa alla och hantera medlemmar**.
8. I fönstret **MFAUsers** väljer du **Lägg till medlemmar**, väljer **användare 3** -konto och väljer sedan **Spara**  >  **Close**  >  **Close**.

Skapa sedan en villkorsstyrd åtkomst policy som kräver multifaktorautentisering för medlemmar i gruppen MFAUsers.

1. Gå till på en ny flik i webbläsaren [https://portal.azure.com](https://portal.azure.com) .
2. Välj villkorlig åtkomst för **Azure Active Directory**-  >  **säkerhet**  >  **Conditional Access**.
3. I fönstret **villkorlig åtkomst – principer** väljer du **ny princip**.
4. Ange **MFA för användar konton** i rutan **namn** i fönstret **nytt** .
5. Välj **användare och grupper**i avsnittet **uppgifter** .
6. På fliken **Inkludera** i fönstret **användare och grupper** väljer du **Välj användare och grupper**som  >  **användare och grupper**  >  **väljer**.
7. I fönstret **Välj** väljer du gruppen **MFAUsers** och väljer sedan **Välj**  >  **klar**.
8. I avsnittet **Access Controls** i fönstret **ny** väljer du **Grant**.
9. I fönstret **bidrag** väljer du **Kräv multifaktorautentisering**och väljer sedan **Välj**.
10. I fönstret **nytt** väljer du **på** för **att aktivera principer**och väljer sedan **skapa**.
11. Stäng flikarna **Azure Portal** och **Microsoft 365 administrations Center** .

Testa den här principen genom att logga ut och logga in med användare 3-kontot. Du bör uppmanas att konfigurera MFA. Det visar att MFAUsers Policy tillämpas.

## <a name="next-step"></a>Nästa steg

Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.

## <a name="see-also"></a>Se även

[Identitets översikt](identity-roadmap-microsoft-365.md)

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Microsoft 365 för företags dokumentation](https://docs.microsoft.com/microsoft-365-enterprise/)
