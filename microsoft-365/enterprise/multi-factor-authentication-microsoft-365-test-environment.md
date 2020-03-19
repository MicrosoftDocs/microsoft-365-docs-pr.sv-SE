---
title: Multifaktorautentisering för din Testmiljö för Microsoft 365 Enterprise
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
description: Konfigurera multifaktorautentisering med textmeddelanden som skickas till en smart telefon i din Testmiljö för Microsoft 365 Enterprise.
ms.openlocfilehash: ea2041a463b224781df101251dab0f4d9f0e8753
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42812214"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a>Multifaktorautentisering för din Testmiljö för Microsoft 365 Enterprise

*Den här testlabbguiden kan användas för både testmiljöer för Microsoft 365 Enterprise och Office 365 Enterprise.*

Om du vill ha ytterligare en säkerhetsnivå för att logga in på Microsoft 365 eller någon tjänst eller ett program som använder Azure AD-klienten för din prenumeration kan du aktivera Azure multifaktorautentisering, vilket kräver mer än bara ett användarnamn och lösenord för att verifiera en Konto. 

Med multifaktorautentisering måste användarna bekräfta ett telefonsamtal, skriva en verifieringskod som skickas i ett sms eller ange ett applösenord på sina smarta telefoner när de har angett sina lösenord på rätt sätt. De kan logga in först efter att den andra autentiseringsfaktorn har uppfyllts. 
  
I den här artikeln beskrivs hur du aktiverar och testar textmeddelandebaserad autentisering för ett visst användarkonto.
  
Det finns två faser för att konfigurera multifaktorautentisering för ett konto i din Testmiljö för Microsoft 365 Enterprise:
  
1. Skapa testmiljön för Microsoft 365 Enterprise.
    
2. Aktivera och testa multifaktorautentisering för user 2-kontot.

3. Aktivera och testa multifaktorautentisering med en princip för villkorlig åtkomst (valfritt).

![Testa labbguider för Microsoft-molnet](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) för en visuell karta till alla artiklar i Microsoft 365 Enterprise Test Lab Guide stacken.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fas 1: Bygg upp din Testmiljö för Microsoft 365 Enterprise

Om du bara vill testa multifaktorautentisering på ett lätt sätt med minimikraven följer du instruktionerna i [Lightweight baskonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Om du vill testa multifaktorautentisering i ett simulerat företag följer du instruktionerna i [direktautentisering](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testning av multifaktorautentisering kräver inte den simulerade företagstestmiljön, som innehåller ett simulerat intranät som är anslutet till Internet- och katalogsynkroniseringen för en AD DS-skog (Active Directory Domain Services). Det finns här som ett alternativ så att du kan testa multifaktorautentisering och experimentera med den i en miljö som representerar en typisk organisation. 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>Fas 2: Aktivera och testa multifaktorautentisering för user 2-kontot

Aktivera multifaktorautentisering för user 2-kontot med följande steg:
  
1. Öppna en separat, privat instans av webbläsaren, gå till[https://portal.microsoft.com](https://portal.microsoft.com)administrationscentret för Microsoft 365 ( ) och logga sedan in med ditt globala administratörskonto.
    
2. Klicka på Användare **> Aktiva användare**i den vänstra navigeringen.
    
3. Klicka på **Multifaktorautentisering i**fönstret Aktiva användare .
    
4. Välj användarkontot **för användare 2** i listan.
    
5. Klicka på **Aktivera**under **Snabbsteg**i avsnittet **Användare 2** .
    
6. Klicka på **Aktivera flerfaktorsauth i**dialogrutan **Om att aktivera flerfaktorsauth** .
    
7. Klicka på **Stäng**i dialogrutan **Uppdateringar.**
    
8. Klicka på ikonen för användarkontot längst upp till höger på fliken **Administrationscenter i Microsoft 365** och klicka sedan på **Logga ut**.
    
9. Stäng webbläsarinstansen.
   
Slutför konfigurationen för user 2-kontot för att använda ett textmeddelande för validering och testa det med följande steg:
  
1. Öppna en ny, privat instans av din webbläsare.
    
2. Gå till Office 365-portalen ([https://portal.office.com](https://portal.office.com)) och logga in med användarnamn2-kontots namn och lösenord.
    
3. När du har loggat in uppmanas du att konfigurera kontot för mer information. Klicka på **Nästa**.
    
4. På sidan **Ytterligare säkerhetsverifiering:**
    
   - Välj land eller region.
    
   - Skriv telefonnummer till den smarta telefonen som tar emot textmeddelanden.
    
   - I **Metod**klickar du på **Skicka mig en kod via sms**.
    
5. Klicka på **Nästa**.
    
6. Ange verifieringskoden från det sms som tas emot på din smarta telefon och klicka sedan på **Verifiera**.
    
7. På sidan **Steg 3: Behåll sidan befintliga program** registrerar du det visade applösenordet för användarkontot för användare 2 på en säker plats och klickar sedan på **Klar**.
    
8. Om det är första gången du loggade in med user 2-kontot uppmanas du att ändra lösenordet. Skriv det ursprungliga lösenordet och ett nytt lösenord två gånger och klicka sedan på **Uppdatera lösenord och logga in**. Spela in det nya lösenordet på en säker plats.
    
    Du bör se Office-portalen för användare 2 på fliken **Microsoft Office Home** i webbläsaren.

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a>Fas 3: Aktivera och testa multifaktorautentisering med en princip för villkorlig åtkomst

*Den här fasen kan endast användas för en Testmiljö för Microsoft 365 Enterprise.*

I den här fasen aktiverar du multifaktorautentisering för user 3-kontot med hjälp av en grupp och en princip för villkorlig åtkomst.

Skapa sedan en ny grupp med namnet MFAUsers och lägg till user 3-kontot i den.

1. Klicka på **Grupper** i den vänstra navigeringen på fliken **Administrationscenter i Microsoft 365** och klicka sedan på **Grupper**.
2. Klicka på **Lägg till en grupp**.
3. Välj **Säkerhet**i fönstret **Välj en grupptyp** och klicka sedan på **Nästa**.
4. Klicka **på** **Skapa i**fönstret Konfigurera grunderna och klicka sedan på **Stäng**.
5. Skriv **MFAUsers**i **gruppfönstret Granska och avsluta** och klicka sedan på **Nästa**.
6. Klicka på gruppen **MFAUsers** i listan över grupper.
7. Klicka på **Medlemmar**i fönstret **MFAUsers** och sedan på **Visa alla och hantera medlemmar**.
8. Klicka på Lägg till **medlemmar**i fönstret **MFAUsers,** välj **användarkontot för användare** och klicka sedan på Spara > **Stäng > Stäng**.

Skapa sedan en princip för villkorlig åtkomst för att kräva multifaktorautentisering för medlemmar i gruppen MFAUsers.

1. På en ny flik i [https://portal.azure.com](https://portal.azure.com)webbläsaren går du till .
2. Klicka på **Azure Active Directory > security > villkorlig åtkomst**.
3. Klicka på **Ny princip**i fönstret **Villkorsstyrd åtkomst – principer** .
4. Skriv **MFA för användarkonton** i **Namn**i fönstret **Nytt** .
5. Klicka på **Användare och grupper**i avsnittet **Tilldelningar** .
6. Klicka på Välj användare och grupper **> Användare och grupper > Välj**på fliken **Inkludera** i fönstret Användare **och grupper.**
7. Klicka på gruppen **MFAUsers** i fönstret **Välj** och klicka sedan på **Välj > klar**.
8. Klicka på **Bevilja**i avsnittet **Access-kontroller** i fönstret **Nytt** .
9. Klicka på **Kräv multifaktorautentisering**i fönstret **Anslag** och klicka sedan på **Välj**.
10. Klicka på **På** för **Aktivera-princip**i fönstret **Nytt** och klicka sedan på **Skapa**.
11. Stäng **flikarna Azure-portalen** och **Microsoft 365-administrationscenter.**

Om du vill testa den här principen loggar du ut och loggar in med användarkontot för användare. Du bör uppmanas att konfigurera MFA. Detta visar att MFAUsers-principen tillämpas.

Se [steget Konfigurera multifaktorautentisering](identity-secure-user-sign-ins.md#identity-mfa) i identitetsfasen för information och länkar för att distribuera multifaktorautentisering i produktionen.
    
## <a name="next-step"></a>Nästa steg

Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) och funktioner i testmiljön.

## <a name="see-also"></a>Se även

[Fas 2: Identitet](identity-infrastructure.md)

[Labbguider för Microsoft 365 Enterprise Test](m365-enterprise-test-lab-guides.md)

[Distribution av Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Dokumentation för Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
