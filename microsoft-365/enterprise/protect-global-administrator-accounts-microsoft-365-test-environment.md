---
title: Skydda globala administratörskonton i testmiljön för Microsoft 365 Enterprise
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
description: Så här skyddar du globala administratörskonton i microsoft 365 Enterprise-testmiljön.
ms.openlocfilehash: e6b93e3888873b6d78fec1802d179ed9624ffa63
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153874"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a>Skydda globala administratörskonton i testmiljön för Microsoft 365 Enterprise

*Den här testlabbguiden kan bara användas i Microsoft 365 Enterprise-testmiljöer.*

Du kan förhindra digitala attacker mot din organisation genom att se till att administratörskontona är så säkra som möjligt. I den här artikeln beskrivs hur du använder Azure Active Directory (Azure AD) principer för villkorlig åtkomst för att skydda globala administratörskonton.

Det finns två faser för att skydda globala administratörskonton i microsoft 365 Enterprise-testmiljön:

1.  Skapa testmiljön för Microsoft 365 Enterprise.
2.  Skydda ditt dedikerade globala administratörskonto.

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med Microsoft 365 Enterprise-testlabbguider.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fas 1: Bygga ut testmiljön i Microsoft 365 Enterprise

Om du bara vill testa globalt administratörskontoskydd på ett lättviktssätt med minimikraven följer du instruktionerna i [Lightweight base-konfigurationen](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Om du vill testa globalt administratörskontoskydd i ett simulerat företag följer du instruktionerna i [Direktautentisering](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testning av globalt administratörskontoskydd kräver inte den simulerade företagstestmiljön, som innehåller ett simulerat intranät som är anslutet till Internet och katalogsynkronisering för en AD DS (Active Directory Domain Services). Det finns här som ett alternativ så att du kan testa globalt administratörskontoskydd och experimentera med det i en miljö som representerar en typisk organisation. 
  
## <a name="phase-2-configure-conditional-access-policies"></a>Fas 2: Konfigurera principer för villkorlig åtkomst

Skapa först ett nytt användarkonto som en dedikerad global administratör.

1. Öppna [administrationscentret för Microsoft 365 på](https://admin.microsoft.com/)en separat flik .
2. Klicka på **Användare > Aktiva användare**och klicka sedan på Lägg till en **användare**.
3. Skriv **DedicatedAdmin** i **Förnamn**, **Visningsnamn**och **Användarnamn**i fönstret **Lägg till** användare .
4. Klicka på **Lösenord,** klicka på **Låt mig skapa lösenordet**och skriv sedan ett starkt lösenord. Registrera lösenordet för det nya kontot på en säker plats.
5. Klicka på **Nästa**.
6. I fönstret **Tilldela produktlicenser** väljer du **Microsoft 365 E5** eller **Office 365 E5**och klickar sedan på **Nästa**.
7. I fönstret **Valfria inställningar** klickar du på **Roller**och väljer sedan **Åtkomst till administrationscenter** och **Global administratör**. Klicka på **Nästa**.
8. Klicka på Slutför att lägga **till**i fönstret Du är **nästan klar** och klicka sedan på **Stäng**.

Skapa sedan en ny grupp med namnet GlobalAdmins och lägg till kontot DedicatedAdmin i den.

1. Klicka på **Grupper** i den vänstra navigeringen på fliken **Administrationscenter i Microsoft 365** och klicka sedan på **Grupper**.
2. Klicka på **Lägg till en grupp**.
3. I fönstret **Välj grupptyp** väljer du **Säkerhet**och klickar sedan på **Nästa**.
4. Klicka på **Skapa grupp**i fönstret **Konfigurera grunderna** och klicka sedan på **Stäng**.
5. Skriv **GlobalAdmins**i **gruppfönstret Granska och avsluta** och klicka sedan på **Nästa**.
7. Klicka på gruppen **GlobalAdmins** i listan över grupper.
8. Klicka på **Medlemmar**i fönstret **GlobalAdmins** och klicka sedan på **Visa alla och hantera medlemmar**.
9. Klicka på **Lägg till medlemmar**i fönstret **GlobalAdmins,** välj **kontot DedicatedAdmin** och ditt globala administratörskonto och klicka sedan på **Spara > Stäng > Stäng**.

Skapa sedan principer för villkorlig åtkomst för att kräva multifaktorautentisering för globala administratörskonton och för att neka autentisering om inloggningsrisken är medelhög eller hög.

Den här första principen kräver att alla globala administratörskonton använder MFA.

1. Gå till [https://portal.azure.com](https://portal.azure.com).
2. Klicka på **Azure Active Directory > Security > Conditional Access**.
3. I fönstret **Villkorlig åtkomst – Principer** klickar du på **Baslinjeprincip: Kräv MFA för administratörer (förhandsgranskning)**.
4. Klicka på Använd princip i principfönstret **originalplan** **direkt > Spara**.

Den här andra principen blockerar åtkomst till global administratörskontoautentisering när inloggningsrisken är medelhög eller hög.

1. Klicka på **Ny princip**i fönstret Villkorlig åtkomst **– Principer** .
2. Skriv **Globala administratörer** i **Namn**i fönstret **Nytt** .
3. Klicka på **Användare och grupper**i avsnittet **Tilldelningar** .
4. Klicka på Markera användare och grupper **> användare och grupper > Markera**på fliken **Inkludera** i fönstret Användare och **grupper.**
5. Klicka på gruppen **GlobalAdmins** i fönstret **Markera** och klicka sedan på **Markera > klar**.
6. Klicka på **Villkor**i avsnittet **Tilldelningar** .
7. Klicka på Logga **in-risk i**fönstret **Villkor,** klicka på **Ja** för **Konfigurera**, klicka på **Hög** och **Medel**och klicka sedan på **Markera** och **gjort**.
8. Klicka på **Bevilja**i avsnittet **Access-kontroller** i fönstret **Nytt** .
9. Klicka på Blockera **åtkomst**i **fönstret Bevilja** och klicka sedan på **Markera**.
10. Klicka på **På** för **att aktivera principen**i fönstret **Nytt** och klicka sedan på **Skapa**.
11. Stäng flikarna **i Azure-portalen** och **Microsoft 365 admin center.**

Om du vill testa den första principen loggar du ut och loggar in med kontot DedicatedAdmin. Du bör uppmanas att konfigurera MFA. Detta visar att den första principen tillämpas.

Se steget [Skydda globala administratörskonton](identity-create-protect-global-admins.md#identity-global-admin) i identitetsfasen för information och länkar för att skydda dina globala administratörskonton i produktion.

## <a name="next-step"></a>Nästa steg

Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.

## <a name="see-also"></a>Se även

[Fas 2: Identitet](identity-infrastructure.md)

[Testlabbguider för Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Distribution av Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise-dokumentation](https://docs.microsoft.com/microsoft-365-enterprise/)
