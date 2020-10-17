---
title: Automatisera licensierings-och grupp medlemskap för test miljön av Microsoft 365 för företag
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
description: Konfigurera gruppbaserade licensierings-och dynamiskt grupp medlemskap i test miljön för Microsoft 365 för företag.
ms.openlocfilehash: d770e7be3b0b55855f1fee26a45d55260c3074cb
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487582"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a>Automatisera licensierings-och grupp medlemskap för test miljön av Microsoft 365 för företag

*Den här test laboratorie guiden kan endast användas för test miljöer med Microsoft 365 för företags nätverk.*

Gruppbaserade licenser tilldelar eller tar bort licenser automatiskt för ett användar konto baserat på grupp medlemskap. Dynamiskt grupp medlemskap lägger till eller tar bort medlemmar i en grupp baserat på Egenskaper för användar konton, till exempel **avdelning** eller **land**. I den här artikeln beskrivs hur du gör demonstrationer av både att lägga till och ta bort grupp medlemmar i test miljön för Microsoft 365 för företag.

Att konfigurera automatisk licensiering och dynamiskt grupp medlemskap i test miljön för Microsoft 365 för företag omfattar två faser:

- [Fas 1: bygga ut test miljön för Microsoft 365 för företag](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fas 2: Konfigurera och testa dynamiskt grupp medlemskap och automatisk licensiering](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Om du vill visa en visuell karta till alla artiklar i gruppen Microsoft 365 för Enterprise-testlabbet går du till [Microsoft 365 för Enterprise Test Lab-guide](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fas 1: bygga ut test miljön för Microsoft 365 för företag

Om du bara vill testa automatiserade licensierings-och grupp medlemskap på ett enkelt sätt med minimi kraven följer du anvisningarna i [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Om du vill testa automatiserade licensierings-och grupp medlemskap i ett simulerat företag följer du anvisningarna i [vidarekoppling](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> För testning av automatiserade licensierings-och grupp medlemskap krävs inte den simulerade företags test miljön, som innehåller ett simulerat intranät som är kopplat till Internet och Directory-synkronisering för en AD DS-skog (Active Directory Domain Services). Det finns här som ett alternativ så att du kan testa automatiserad licensiering och grupp medlemskap och experimentera med den i en miljö som representerar en typisk organisation.
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>Fas 2: Konfigurera och testa dynamiskt grupp medlemskap och automatisk licensiering

Börja med att skapa en ny grupp med namnet försäljning och Lägg till en regel för dynamiskt grupp medlemskap så att användar kontona med **avdelningen** angett till **försäljning** automatiskt ansluter till Sälj gruppen.

1. Logga in på [administrations centret för microsoft 365](https://admin.microsoft.com) i en privat instans av din webbläsare med det globala administratörs kontot för ditt Microsoft 365 E5 test labb-abonnemang.
2. Gå till Azure Portal på en separat flik i webbläsaren [https://portal.azure.com](https://portal.azure.com) .
3. I Azure-portalen anger du **grupper** i sökrutan och väljer sedan **grupper**.
4. Välj **ny grupp**i fönstret **alla grupper** .
5. Välj **Microsoft 365**i **grupptyp**.
6. Ange **försäljning**i **grupp namn**.
7. Välj **dynamisk användare**i **typ av medlemskap**.
8. Välj **dynamiska användar medlemmar**.
9. I fönstret **regler för dynamisk medlemskap** : 
   - Välj egenskapen **avdelning** .
   - Välj operatorn **Equal** .
   - I rutan **värde** anger du **Sales**.
10. Välj **Spara**.
11. Välj **Skapa**.

Konfigurera sedan Sälj gruppen så att medlemmar tilldelas automatiskt Microsoft 365 E5-licensen.

1. Välj **Sälj** gruppen och sedan **licenser**.
2. I fönstret **Uppdatera licens tilldelningar** väljer du **Microsoft 365 E5**och väljer sedan **Spara**.
3. I webbläsaren stänger du Azure Portal-fliken.

Testa sedan dynamiskt grupp medlemskap och automatisk licensiering på användare 4-kontot:

1. Välj **admin**på fliken **Microsoft Office Home** i webbläsaren.
2. På fliken **administrations Center för Microsoft 365** väljer **du aktiva användare**.
3. På sidan **aktiva användare** väljer du kontot **användare 4** .
4. I fönstret **användare 4** väljer du **Redigera** för **produkt licenser**.
5. I fönstret **produkt licenser** inaktiverar du **Microsoft 365 E5** -licensen och väljer sedan **Spara**  >  **stängning**.
6. I egenskaperna för användare 4-kontot kontrollerar du att inga produkt licenser har tilldelats och att det inte finns några grupp medlemskap.
7. För **kontakt information**väljer du **Redigera**.
8. Välj **kontakt information**i fönstret **Redigera kontakt information** .
9. I rutan **avdelning** anger du **försäljning**och väljer sedan **Spara**  >  **stängning**.
10. Vänta några minuter och välj sedan **Uppdatera** ikonen i det övre högra hörnet i konto fönstret för användare 4.

I tid bör du se:

- **Grupp medlemskaps** egenskapen har uppdaterats med **Sälj** gruppen.
- Egenskapen **produkt licenser** har uppdaterats med **Microsoft 365 E5** -licensen.

Se dessa artiklar för att distribuera dynamiskt grupp medlemskap och automatisk licensiering i produktion:

- [Gruppbaserad licensiering i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [Dynamiska grupper i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a>Nästa steg

Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.

## <a name="see-also"></a>Se även

[Identitets översikt](identity-roadmap-microsoft-365.md)

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Microsoft 365 för företags dokumentation](https://docs.microsoft.com/microsoft-365-enterprise/)
