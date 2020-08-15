---
title: Skydda globala administratörs konton i test miljön för Microsoft 365 för företag
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
description: Använd de här stegen för att skydda globala administratörs konton i test miljön för Microsoft 365 för företag.
ms.openlocfilehash: fff09ca41ff0b648d46b5c33f753affc01242264
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695188"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a>Skydda globala administratörs konton i test miljön för Microsoft 365 för företag

*Den här test laboratorie guiden kan endast användas för test miljöer med Microsoft 365 för företags nätverk.*

Du kan förhindra digitala attacker på din organisation genom att se till att dina administratörs konton är så säkra som möjligt. I den här artikeln beskrivs hur du använder principer för villkorsstyrd åtkomst i Azure Active Directory (Azure AD) för att skydda globala administratörs konton.

Det finns två faser för att skydda globala administratörs konton i test miljön för Microsoft 365 för företag:

1.  Skapa test miljön för Microsoft 365 för företag.
2.  Skydda ditt globala administratörs konto.

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med testlabbguider för Microsoft 365 för företag.

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fas 1: bygga ut test miljön för Microsoft 365 för företag

Om du bara vill testa globalt administratörs konto skydd på ett enkelt sätt med minimi kraven följer du anvisningarna i [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Om du vill testa det globala administratörs konto skyddet i ett simulerat företag följer du anvisningarna i [vidarekoppling](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testning av globalt administratörs konto kräver inte den simulerade företags test miljön, som innehåller ett simulerat intranät som är kopplat till Internet-och katalogs-synkronisering för en Active Directory Domain Services (AD DS). Det finns här som ett alternativ för att du ska kunna testa det globala administratörs konto skyddet och experimentera med det i en miljö som representerar en typisk organisation. 
  
## <a name="phase-2-configure-conditional-access-policies"></a>Fas 2: konfigurera principer för villkorsstyrd åtkomst

Först skapar du ett nytt användar konto som global administratör.

1. Öppna [administrations centret för Microsoft 365](https://admin.microsoft.com/)på en separat flik.
2. Klicka på **användare > aktiva användare**och klicka sedan på **Lägg till en användare**.
3. I fönstret **Lägg till användare** skriver du **DedicatedAdmin** i **förnamn**, **visnings namn**och **användar namn**.
4. Klicka på **lösen ord**, klicka på **Låt mig skapa lösen ordet**och skriv sedan ett starkt lösen ord. Spela in lösen ordet för det nya kontot på en säker plats.
5. Klicka på **Nästa**.
6. I fönstret **tilldela produkt licenser** väljer du **Microsoft 365 E5**och klickar sedan på **Nästa**.
7. I fönstret **valfria inställningar** klickar du på **roller**och väljer sedan **Administratörs Center åtkomst** och **Global administratör**. Klicka på **Nästa**.
8. I fönstret **du är nästan klar klickar du** på **Lägg till**och sedan på **Stäng**.

Skapa sedan en ny grupp med namnet GlobalAdmins och Lägg till DedicatedAdmin-kontot i den.

1. Klicka på **grupper** i det vänstra navigerings fältet på fliken **administrations center för Microsoft 365** och klicka sedan på **grupper**.
2. Klicka på **Lägg till en grupp**.
3. I fönstret **Välj en grupptyp** väljer du **säkerhet**och sedan **Nästa**.
4. Klicka på **Skapa grupp**i fönstret **Konfigurera grunderna** och klicka sedan på **Stäng**.
5. Skriv **GlobalAdmins**i fönstret **Granska och slutför tillägg** och klicka sedan på **Nästa**.
7. I listan med grupper klickar du på gruppen **GlobalAdmins** .
8. I fönstret **GlobalAdmins** klickar du på **medlemmar**och sedan på **Visa alla och hantera medlemmar**.
9. I fönstret **GlobalAdmins** klickar du på **Lägg till medlemmar**, väljer **DedicatedAdmin** -konto och ditt globala administratörs konto och klickar sedan på **Spara > Stäng > Stäng**.

Skapa sedan principer för villkorsstyrd åtkomst för att kräva multifaktorautentisering för globala administratörs konton och för att neka identifiering om inloggnings risken är medel eller hög.

Den första principen kräver att MFA används för alla globala administratörs konton.

1. Gå till på en ny flik i webbläsaren [https://portal.azure.com](https://portal.azure.com) .
2. Klicka på **> säkerhets > villkorlig åtkomst för Azure Active Directory**.
3. I fönstret **villkorlig åtkomst – principer** klickar du på **bas linje princip: Kräv MFA för administratörer (för hands version)**.
4. I fönstret **rikt linje** klickar du på **använd princip omedelbart > Spara**.

Denna andra princip blockerar åtkomst till global administratörs konto identifiering när inloggnings risken är medel eller hög.

1. Klicka på **ny princip**i fönstret **villkorlig åtkomst – policys** .
2. I fönstret **ny** skriver du **globala administratörer** i **namn**.
3. Klicka på **användare och grupper**i avsnittet **uppgifter** .
4. På fliken **Inkludera** i fönstret **användare och grupper** klickar du på **Välj användare och grupper > användare och grupper > välja**.
5. Klicka på gruppen **GlobalAdmins** i fönstret **Välj** och klicka sedan på **Välj > klar**.
6. Klicka på **villkor**i avsnittet **uppgifter** .
7. Klicka på **inloggnings risk**i fönstret **villkor** , klicka på **Ja** för att **Konfigurera**, klicka på **hög** och **medium**och klicka sedan på **Välj** och **klar**.
8. Klicka på **Tillåt**i avsnittet **Access-kontroller** i fönstret **nytt** .
9. I fönstret **bidrag** klickar du på **blockera åtkomst**och sedan på **Välj**.
10. I fönstret **ny** klickar du **på** för att **aktivera principer**och klickar sedan på **skapa**.
11. Stäng flikarna **Azure Portal** och **Microsoft 365 administrations Center** .

Om du vill testa den första principen loggar du ut och loggar in med DedicatedAdmin-kontot. Du bör uppmanas att konfigurera MFA. Det visar att den första principen tillämpas.

## <a name="next-step"></a>Nästa steg

Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.

## <a name="see-also"></a>Se även

[Identitets översikt](identity-roadmap-microsoft-365.md)

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Microsoft 365 för företags dokumentation](https://docs.microsoft.com/microsoft-365-enterprise/)
