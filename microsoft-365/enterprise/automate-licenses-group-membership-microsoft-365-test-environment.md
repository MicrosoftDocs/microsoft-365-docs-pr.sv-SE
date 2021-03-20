---
title: Automatisera licensiering och gruppmedlemskap i microsoft 365 för företagstestmiljö
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Konfigurera gruppbaserad licensiering och dynamiskt gruppmedlemskap i din Microsoft 365 för företagstestmiljö.
ms.openlocfilehash: 26840e2884202a0fa9c4bb563f3d7c653482ef87
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905374"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a>Automatisera licensiering och gruppmedlemskap i microsoft 365 för företagstestmiljö

*Den här testlabbguiden kan endast användas för Microsoft 365 för företagstestmiljöer.*

Gruppbaserad licensiering tilldelar eller tar automatiskt bort licenser för ett användarkonto baserat på gruppmedlemskap. Dynamiskt gruppmedlemskap lägger till eller tar bort medlemmar i en grupp baserat på egenskaper för användarkonton, t.ex. **Avdelning** eller **Land.** Den här artikeln beskriver demonstrationer av att lägga till och ta bort gruppmedlemmar i testmiljön Microsoft 365 för företag.

Att konfigurera automatisk licensiering och dynamiskt gruppmedlemskap i testmiljön Microsoft 365 för företag innebär två faser:

- [Fas 1: Bygg ut microsoft 365 för företagstestmiljö](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fas 2: Konfigurera och testa dynamiskt gruppmedlemskap och automatisk licensiering](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> En visuell karta till alla artiklar i Microsoft 365 testlabbguide-stacken för företag finns i Testlabbguide för [Microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)för företag.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fas 1: Bygg ut microsoft 365 för företagstestmiljö

Om du bara vill testa automatisk licensiering och gruppmedlemskap på ett lätt sätt med minimikraven följer du anvisningarna i [Lätt baskonfiguration.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Om du vill testa automatisk licensiering och gruppmedlemskap i ett simulerat företag följer du anvisningarna i [Direktautentisering](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Om du testar automatiserad licensiering och gruppmedlemskap krävs inte den simulerade företagstestmiljön, som omfattar en simulerad intranätansluten till Internet och katalogsynkronisering för en AD DS-skog (Active Directory Domain Services). Här finns ett alternativ så att du kan testa automatisk licensiering och gruppmedlemskap och experimentera med det i en miljö som representerar en vanlig organisation.
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>Fas 2: Konfigurera och testa dynamiskt gruppmedlemskap och automatisk licensiering

Skapa först en ny grupp med namnet Försäljning och lägg till  en dynamisk  regel för gruppmedlemskap så att användarkonton med Department inställt på Försäljning automatiskt ska gå med i gruppen Försäljning.

1. I en privat instans av webbläsaren loggar du in på administrationscentret för [Microsoft 365](https://admin.microsoft.com) med det globala administratörskontot för Microsoft 365 E5-provlabbprenumerationen.
2. På en separat flik i webbläsaren går du till Azure Portal på [https://portal.azure.com](https://portal.azure.com) .
3. I Azure Portal anger du **grupper** i sökrutan och väljer sedan **Grupper**.
4. i fönstret **Alla grupper** väljer du **Ny grupp**.
5. I **Grupptyp** väljer du **Microsoft 365**.
6. Ange **Försäljning i** **Gruppnamn.**
7. Välj **Dynamisk användare** i **Medlemskapstyp.**
8. Välj **Dynamiska användarmedlemmar.**
9. I fönstret **Regler för dynamiskt** medlemskap: 
   - Välj **avdelningsegenskapen.**
   - Välj **operatorn Lika med.**
   - I rutan **Värde** anger du **Försäljning.**
10. Välj **Spara**.
11. Välj **Skapa**.

Konfigurera sedan gruppen Försäljning så att medlemmarna automatiskt tilldelas Microsoft 365 E5-licensen.

1. Välj **gruppen** Försäljning och välj sedan **Licenser**.
2. I fönstret **Uppdatera licenstilldelningar** väljer du **Microsoft 365 E5** och sedan **Spara**.
3. Stäng fliken Azure Portal i webbläsaren.

Testa sedan dynamiskt gruppmedlemskap och automatisk licensiering på User 4-kontot:

1. På **fliken Microsoft Office Start** i webbläsaren väljer du **Admin**.
2. Välj  **Aktiva användare på fliken administrationscenter för Microsoft 365.**
3. Välj **Användare** **4-kontot** på sidan Aktiva användare.
4. I fönstret **Användare 4** väljer du **Redigera** för **produktlicenser.**
5. I fönstret **Produktlicenser** inaktiverar du **Microsoft 365 E5-licensen** och väljer sedan **Spara**  >  **stäng.**
6. I egenskaperna för Användarkontot 4 kontrollerar du att inga produktlicenser har tilldelats och att det inte finns några gruppmedlemskap.
7. För **Kontaktinformation** väljer du **Redigera**.
8. Välj **Kontaktinformation i** fönstret Redigera **kontaktinformation.**
9. I rutan **Avdelning** anger du **Försäljning** och väljer sedan **Spara**  >  **Stäng.**
10. Vänta några minuter och välj sedan regelbundet ikonen **Uppdatera** i det övre högra hörnet av fönstret Användare 4-konto.

Med tiden bör du se:

- **Egenskapen Gruppmedlemskap** uppdaterad med **gruppen** Försäljning.
- **Produktlicensegenskap** som uppdaterats **med Microsoft 365 E5-licensen.**

Läs följande artiklar om hur du distribuerar dynamiskt gruppmedlemskap och automatisk licensiering i produktionen:

- [Gruppbaserad licensiering i Azure Active Directory](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [Dynamiska grupper i Azure Active Directory](/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a>Nästa steg

Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.

## <a name="see-also"></a>Se även

[Identitetsöversikt](identity-roadmap-microsoft-365.md)

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Dokumentation om Microsoft 365 för företag](/microsoft-365-enterprise/)