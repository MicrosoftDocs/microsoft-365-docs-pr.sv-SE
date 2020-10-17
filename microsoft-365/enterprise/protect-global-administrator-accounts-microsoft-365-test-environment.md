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
ms.openlocfilehash: 1ae04e4761ed86e087e647464ad522466ed6abef
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487642"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a>Skydda globala administratörs konton i test miljön för Microsoft 365 för företag

*Den här test laboratorie guiden kan endast användas för test miljöer med Microsoft 365 för företags nätverk.*

Du kan förhindra digitala attacker på din organisation genom att se till att dina administratörs konton är så säkra som möjligt. 

I den här artikeln beskrivs hur du använder principer för villkorsstyrd åtkomst i Azure Active Directory (Azure AD) för att skydda globala administratörs konton.

Att skydda globala administratörs konton i test miljön för Microsoft 365 för företag inbegriper två faser:
- [Fas 1: bygga ut test miljön för Microsoft 365 för företag](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fas 2: konfigurera principer för villkorsstyrd åtkomst](#phase-2-configure-conditional-access-policies)

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Om du vill visa en visuell karta till alla artiklar i gruppen Microsoft 365 för Enterprise-testlabbet går du till [Microsoft 365 för Enterprise Test Lab-guide](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fas 1: bygga ut test miljön för Microsoft 365 för företag

Om du vill testa det globala administratörs konto skyddet på ett billigt sätt med minimi kraven följer du anvisningarna i [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Om du vill testa det globala administratörs konto skyddet i ett simulerat företag följer du anvisningarna i [vidarekoppling](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testning av globalt administratörs konto kräver inte den simulerade företags test miljön, som innehåller ett simulerat intranät som är kopplat till Internet-och katalogs-synkronisering för en Active Directory Domain Services (AD DS). Det finns här som ett alternativ för att du ska kunna testa det globala administratörs konto skyddet och experimentera med det i en miljö som representerar en typisk organisation. 
  
## <a name="phase-2-configure-conditional-access-policies"></a>Fas 2: konfigurera principer för villkorsstyrd åtkomst

Först skapar du ett nytt användar konto som global administratör.

1. Öppna [administrations centret för Microsoft 365](https://admin.microsoft.com/)på en separat flik.
2. Välj **användare**  >  **aktiva användare**och välj sedan **Lägg till en användare**.
3. I fönstret **Lägg till användare** anger du **DedicatedAdmin** i rutorna **förnamn**, **visnings namn**och **användar namn** .
4. Välj **lösen ord**, Välj **Låt mig skapa lösen ordet**och ange sedan ett starkt lösen ord. Spela in lösen ordet för det nya kontot på en säker plats.
5. Välj **Nästa**.
6. I fönstret **tilldela produkt licenser** väljer du **Microsoft 365 E5**och sedan **Nästa**.
7. I fönstret **valfria inställningar** väljer du den **Roles**  >  **Admin center access**  >  **globala administratörs**rollen för administratörer  >  **Nästa**.
8. I fönstret **du är nästan klar väljer du** **Lägg till**och sedan **Stäng**.

Skapa sedan en ny grupp med namnet GlobalAdmins och Lägg till DedicatedAdmin-kontot i den.

1. Gå till fliken **administrations Center för Microsoft 365** , Välj **grupper** i det vänstra navigerings fältet och välj sedan **grupper**.
2. Välj **Lägg till en grupp**.
3. I fönstret **Välj en grupptyp** väljer du **säkerhet**och sedan **Nästa**.
4. I fönstret **Konfigurera grunderna väljer du** **Skapa grupp**och sedan **Stäng**.
5. Ange **GlobalAdmins**i fönstret **Granska och slutför** och välj sedan **Nästa**.
7. I listan med grupper väljer du gruppen **GlobalAdmins** .
8. I fönstret **GlobalAdmins** väljer du **medlemmar**och sedan **Visa alla och hantera medlemmar**.
9. I fönstret **GlobalAdmins** väljer du **Lägg till medlemmar**, väljer **DedicatedAdmin** -konto och ditt globala administratörs konto och väljer sedan **Spara**  >  **Close**  >  **Close**.

Skapa sedan principer för villkorsstyrd åtkomst för att kräva multifaktorautentisering för globala administratörs konton och för att neka identifiering om inloggnings risken är medel eller hög.

Den första principen kräver att MFA används för alla globala administratörs konton.

1. Gå till på en ny flik i webbläsaren [https://portal.azure.com](https://portal.azure.com) .
2. Klicka på villkorlig åtkomst för **Azure Active Directory**-  >  **säkerhet**  >  **Conditional Access**.
3. I fönstret **villkorlig åtkomst – principer** väljer du **original princip: Kräv MFA för administratörer (för hands version)**.
4. I fönstret **rikt linje** väljer du **använd policy omedelbart > Spara**.

Denna andra princip blockerar åtkomst till global administratörs konto identifiering när inloggnings risken är medel eller hög.

1. I fönstret **villkorlig åtkomst – principer** väljer du **ny princip**.
2. Ange **globala administratörer** i **namn**i fönstret **nytt** .
3. Välj **användare och grupper**i avsnittet **uppgifter** .
4. På fliken **Inkludera** i fönstret **användare och grupper** väljer du **Välj användare och grupper**som  >  **användare och grupper**  >  **väljer**.
5. I fönstret **Välj** väljer du gruppen **GlobalAdmins** och väljer sedan **Välj**  >  **klar**.
6. Välj **villkor**i avsnittet **uppgifter** .
7. I fönstret **villkor** väljer du **inloggnings risker**, väljer **Ja** för **konfigurering**, väljer **hög** och **medium**och väljer sedan **Välj** och **klar**.
8. I avsnittet **Access Controls** i fönstret **ny** väljer du **Grant**.
9. I fönstret **bidrag** väljer du **blockera åtkomst**och väljer sedan **Välj**.
10. I fönstret **nytt** väljer du **på** för **att aktivera principer**och väljer sedan **skapa**.
11. Stäng flikarna **Azure Portal** och **Microsoft 365 administrations Center** .

Om du vill testa den första principen loggar du ut och loggar in med DedicatedAdmin-kontot. Du bör uppmanas att konfigurera MFA. Det visar att den första principen tillämpas.

## <a name="next-step"></a>Nästa steg

Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.

## <a name="see-also"></a>Se även

[Identitets översikt](identity-roadmap-microsoft-365.md)

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Microsoft 365 för företags dokumentation](https://docs.microsoft.com/microsoft-365-enterprise/)
