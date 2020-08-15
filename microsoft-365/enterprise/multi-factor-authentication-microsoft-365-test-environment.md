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
ms.openlocfilehash: 4ed50d37e0f4e73d5d1fc62e295df374c61b9786
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686280"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a>Multifaktorautentisering för test miljön för Microsoft 365 för företag

*Den här test laboratorie guiden kan användas för både Microsoft 365 för företags-och Office 365 företags test miljöer.*

Om du vill ha ytterligare en säkerhets nivå för att logga in på Microsoft 365 eller någon tjänst eller ett program som använder Azure AD-klient organisationen för din prenumeration kan du aktivera Azure Multi-Factor-verifiering, vilket kräver mer än ett användar namn och lösen ord för att verifiera ett konto. 

Med multifaktorautentisering måste användare bekräfta ett telefonsamtal, ange en verifierings kod som skickas i ett textmeddelande eller verifiera verifieringen med en app på deras smarta telefoner när du har angett lösen orden korrekt. De kan bara logga in när denna faktor har uppfyllts. 
  
I den här artikeln beskrivs hur du aktiverar och testar SMS-baserad lösenordsautentisering för ett specifikt användar konto.
  
Det finns två faser för att konfigurera multifaktorautentisering för ett konto i test miljön för Microsoft 365 för företag:
  
1. Skapa test miljön för Microsoft 365 för företag.
    
2. Aktivera och testa multifaktorautentisering för användare 2-kontot.

3. Aktivera och testa multifaktorautentisering med en princip för villkorsstyrd åtkomst (valfritt).

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Gå till [Guide för testnings laboratorium](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) för en bild karta till alla artiklar i test laboratorie guiden för Microsoft 365 för Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fas 1: bygga ut test miljön för Microsoft 365 för företag

Om du bara vill testa multifaktorautentisering på ett lättviktigt sätt med minimi kraven följer du anvisningarna i [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Om du vill testa multifaktorautentisering i ett simulerat företag följer du anvisningarna i [vidarekoppling](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testning av multifaktorautentisering kräver inte den simulerade företags test miljön, som innehåller ett simulerat intranät som är kopplat till Internet-och katalogs-synkronisering för en AD DS-skog (Active Directory Domain Services). Det finns ett alternativ som gör att du kan testa multifaktorautentisering och experimentera med den i en miljö som representerar en typisk organisation. 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>Fas 2: Aktivera och testa multifaktorautentisering för användare 2-konto

Aktivera multifaktorautentisering för användare 2-kontot med de här stegen:
  
1. Öppna en separat privat instans av webbläsaren, gå till administrations centret för Microsoft 365 [https://portal.microsoft.com](https://portal.microsoft.com) och logga in med ditt globala administratörs konto.
    
2. Klicka på **Användare > Aktiva användare** i det vänstra navigeringsfönstret.
    
3. I fönstret aktiva användare klickar du på **multifaktorautentisering**.
    
4. I listan väljer du **användare 2** -konto.
    
5. Under **snabb steg**i avsnittet **användare 2** klickar du på **Aktivera**.
    
6. I dialog rutan **om aktivering av multifaktorautentisering** klickar du på **Aktivera multifaktorautentisering**.
    
7. Klicka på **Stäng**i dialog rutan **uppdateringar har slutförts** .
    
8. På fliken **administrations Center för Microsoft 365** klickar du på ikonen användar konto längst upp till höger och sedan på **Logga ut**.
    
9. Stäng din instans av webbläsaren.
   
Slutför konfigurationen för användare 2-kontot för att använda ett textmeddelande för verifiering och testa det med de här stegen:
  
1. Öppna en ny privat instans av webbläsaren.
    
2. Gå till [administrations centret för Microsoft 365](https://admin.microsoft.com) och logga in med användar namnet för användare 2 och lösen ordet.
    
3. När du har loggat in uppmanas du att konfigurera kontot för mer information. Klicka på **Nästa**.
    
4. På sidan **ytterligare säkerhets verifiering** :
    
   - Välj land eller region.
    
   - Skriv telefonnumret till den smartphone som tar emot textmeddelanden.
    
   - Klicka **på** **skicka mig en kod efter SMS**.
    
5. Klicka på **Nästa**.
    
6. Ange verifierings koden från textmeddelandet som visas på din mobil telefon och klicka sedan på **Verifiera**.
    
7. På sidan **steg 3: Behåll dina befintliga program** klickar du på **klar**.
    
8. Om det är första gången du loggar in med User 2-kontot uppmanas du att ändra lösen ordet. Skriv det ursprungliga lösen ordet och ett nytt lösen ord två gånger och klicka sedan på **Uppdatera lösen ord och logga in**. Spela in det nya lösen ordet på en säker plats.
    
    Du bör se Office-portalen för användare 2 på fliken **Microsoft Office-Startsida** i webbläsaren.

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a>Fas 3: Aktivera och testa multifaktorautentisering med en princip för villkorsstyrd åtkomst

*Den här fasen kan endast användas för test miljön Microsoft 365 för företag.*

I den här fasen aktiverar du multifaktorautentisering för användare 3-kontot med hjälp av en grupp och en princip för villkorsstyrd åtkomst.

Skapa sedan en ny grupp med namnet MFAUsers och Lägg till användare 3-kontot i den.

1. Klicka på **grupper** i det vänstra navigerings fältet på fliken **administrations center för Microsoft 365** och klicka sedan på **grupper**.
2. Klicka på **Lägg till en grupp**.
3. I fönstret **Välj en grupptyp** väljer du **säkerhet**och sedan **Nästa**.
4. Klicka på **Skapa grupp**i fönstret **Konfigurera grunderna** och klicka sedan på **Stäng**.
5. Skriv **MFAUsers**i fönstret **Granska och slutför tillägg** och klicka sedan på **Nästa**.
6. I listan med grupper klickar du på gruppen **MFAUsers** .
7. I fönstret **MFAUsers** klickar du på **medlemmar**och sedan på **Visa alla och hantera medlemmar**.
8. I fönstret **MFAUsers** klickar du på **Lägg till medlemmar**, väljer **användare 3** -konto och klickar sedan på **Spara > Stäng > Stäng**.

Skapa sedan en villkorsstyrd åtkomst policy som kräver multifaktorautentisering för medlemmar i gruppen MFAUsers.

1. Gå till på en ny flik i webbläsaren [https://portal.azure.com](https://portal.azure.com) .
2. Klicka på **> säkerhets > villkorlig åtkomst för Azure Active Directory**.
3. Klicka på **ny princip**i fönstret **villkorlig åtkomst – policys** .
4. I fönstret **ny** skriver du **MFA för användar konton** i **namn**.
5. Klicka på **användare och grupper**i avsnittet **uppgifter** .
6. På fliken **Inkludera** i fönstret **användare och grupper** klickar du på **Välj användare och grupper > användare och grupper > välja**.
7. Klicka på gruppen **MFAUsers** i fönstret **Välj** och klicka sedan på **Välj > klar**.
8. Klicka på **Tillåt**i avsnittet **Access-kontroller** i fönstret **nytt** .
9. Klicka på **Kräv multifaktorautentisering**i fönstret **bidrag** och klicka sedan på **Välj**.
10. I fönstret **ny** klickar du **på** för att **aktivera principer**och klickar sedan på **skapa**.
11. Stäng flikarna **Azure Portal** och **Microsoft 365 administrations Center** .

Testa den här principen genom att logga ut och logga in med användare 3-kontot. Du bör uppmanas att konfigurera MFA. Det visar att MFAUsers Policy tillämpas.

## <a name="next-step"></a>Nästa steg

Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.

## <a name="see-also"></a>Se även

[Identitets översikt](identity-roadmap-microsoft-365.md)

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Microsoft 365 för företags dokumentation](https://docs.microsoft.com/microsoft-365-enterprise/)
