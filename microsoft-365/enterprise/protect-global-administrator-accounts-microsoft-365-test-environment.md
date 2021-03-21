---
title: Skydda globala administratörskonton i testmiljön Microsoft 365 för företag
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
description: Använd de här stegen för att skydda globala administratörskonton i testmiljön Microsoft 365 för företag.
ms.openlocfilehash: 3eab538b59e460857e2fa195aaacf51051f94d6b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918888"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a>Skydda globala administratörskonton i testmiljön Microsoft 365 för företag

*Den här testlabbguiden kan endast användas för Microsoft 365 för företagstestmiljöer.*

Du kan förhindra digitala attacker på din organisation genom att se till att dina administratörskonton är så säkra som möjligt. 

I den här artikeln beskrivs hur du använder villkorsstyrda åtkomstprinciper för Azure Active Directory (Azure AD) för att skydda globala administratörskonton.

Skydda globala administratörskonton i din Testmiljö för Microsoft 365 för företag innebär två faser:
- [Fas 1: Bygg ut microsoft 365 för företagstestmiljö](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fas 2: Konfigurera principer för villkorsstyrd åtkomst](#phase-2-configure-conditional-access-policies)

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> En visuell karta till alla artiklar i Microsoft 365 testlabbguide-stacken för företag finns i Testlabbguide för [Microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)för företag.

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fas 1: Bygg ut microsoft 365 för företagstestmiljö

Om du vill testa kontoskyddet för globala administratörer på ett lätt sätt med minimikraven följer du anvisningarna i [Enkel baskonfiguration.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Om du vill testa kontoskydd för globala administratörer i ett simulerat företag följer du anvisningarna i [Direktautentisering](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Om du testar kontoskyddet för globala administratörer krävs inte den simulerade företagstestmiljön, som omfattar ett simulerat intranät som är anslutet till Internet och katalogsynkronisering för en AD DS (Active Directory Domain Services). Den finns här som ett alternativ så att du kan testa det globala administratörskontoskyddet och experimentera med det i en miljö som representerar en vanlig organisation. 
  
## <a name="phase-2-configure-conditional-access-policies"></a>Fas 2: Konfigurera principer för villkorsstyrd åtkomst

Börja med att skapa ett nytt användarkonto som en dedikerad global administratör.

1. På en separat flik öppnar du [administrationscentret för Microsoft 365.](https://admin.microsoft.com/)
2. Välj **Användare**  >  **Aktiva användare** och välj sedan Lägg till en **användare.**
3. I fönstret **Lägg till** användare anger du **DedicatedAdmin** i **rutorna Förnamn,** **Visningsnamn** **och** Användarnamn.
4. Välj **Lösenord**, välj **Låt mig skapa lösenordet** och ange sedan ett starkt lösenord. Registrera lösenordet för det nya kontot på en säker plats.
5. Välj **Nästa**.
6. I fönstret **Tilldela produktlicenser** väljer du **Microsoft 365 E5** och sedan **Nästa.**
7. I fönstret **Valfria inställningar** väljer du **Rolladministrationscenter**  >  **åtkomst till** Global  >  **administratör**  >  **Nästa.**
8. I fönstret **Du är nästan klar** väljer du Slutför **tilläggning** och sedan **Stäng**.

Skapa sedan en ny grupp med namnet GlobalAdmins och lägg till DedicatedAdmin-kontot i den gruppen.

1. På fliken **Administrationscenter för Microsoft 365** väljer **du Grupper** i det vänstra navigeringsfältet och sedan **Grupper.**
2. Välj **Lägg till en grupp**.
3. I fönstret **Välj en grupptyp** väljer **du Säkerhet** och sedan **Nästa**.
4. I **fönstret Konfigurera grunderna väljer** du **Skapa grupp och** sedan **Stäng**.
5. Skriv **GlobalAdmins** **i fönstret** Granska och slutför tilläggen av gruppen och välj sedan **Nästa.**
7. I listan över grupper väljer du **gruppen GlobalAdmins.**
8. I fönstret **GlobalAdmins** väljer du **Members** och sedan **Visa alla och hanterar medlemmar.**
9. I fönstret **GlobalAdmins** väljer du **Lägg** till medlemmar , väljer **DedicatedAdmin-kontot** och ditt globala administratörskonto och väljer **sedan Spara**  >    >  **Stäng Stäng.**

Skapa sedan villkorsstyrda åtkomstprinciper för att kräva multifaktorautentisering för globala administratörskonton och för att neka autentisering om inloggningsrisken är medium eller hög.

Den här första principen kräver att alla globala administratörskonton använder MFA.

1. På en ny flik i webbläsaren går du till [https://portal.azure.com](https://portal.azure.com) .
2. Klicka på **Villkorsstyrd åtkomst för Azure Active**  >    >  **Directory-säkerhet.**
3. I fönstret **Villkorsstyrd åtkomst –** Principer väljer du **Baslinjeprincip: Kräv MFA för administratörer (förhandsversion).**
4. I fönstret **Originalplansprincip** väljer du **Använd princip direkt > Spara**.

Den här andra principen blockerar åtkomst till autentisering av globalt administratörskonto när inloggningsrisken är medium eller hög.

1. I fönstret **Villkorsstyrd åtkomst –** Principer väljer du **Ny princip.**
2. I fönstret **Nytt** anger du **Globala administratörer** i **Namn.**
3. I avsnittet **Uppgifter** väljer du **Användare och grupper.**
4. På fliken **Inkludera** i fönstret **Användare och grupper väljer** du Välj användare och grupper **Användare** och  >  **grupper**  >  **Välj**.
5. I fönstret **Markera** väljer du **gruppen GlobalAdmins** och väljer sedan **Select**  >  **Done**.
6. I avsnittet **Uppgifter** väljer du **Villkor**.
7. I fönstret **Villkor** väljer du **Inloggningsrisk**  , väljer Ja för Konfigurera , väljer **Hög** och **Medium** och sedan **Välj** och **klar**. 
8. I avsnittet **Access-kontroller** i **fönstret Nytt** väljer du **Tilldela**.
9. I fönstret **Bevilja** väljer du **Blockera åtkomst** och sedan **Välj**.
10. I fönstret **Nytt** väljer du **På** för **Aktivera princip** och sedan **Skapa**.
11. Stäng **flikarna Azure Portal** och **Administrationscenter för Microsoft 365.**

Testa den första principen genom att logga ut och logga in med DedicatedAdmin-kontot. Du bör uppmanas att konfigurera MFA. Det visar att den första principen används.

## <a name="next-step"></a>Nästa steg

Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.

## <a name="see-also"></a>Se även

[Identitetsöversikt](identity-roadmap-microsoft-365.md)

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Dokumentation om Microsoft 365 för företag](/microsoft-365-enterprise/)