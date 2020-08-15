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
ms.openlocfilehash: a25a47b81ce8c119e7aeb44660af32bb9cafb08a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685564"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a>Automatisera licensierings-och grupp medlemskap för test miljön av Microsoft 365 för företag

*Den här test laboratorie guiden kan endast användas för test miljöer med Microsoft 365 för företags nätverk.*

Gruppbaserade licenser tilldelar eller tar bort licenser automatiskt för ett användar konto baserat på grupp medlemskap. Dynamiskt grupp medlemskap lägger till eller tar bort medlemmar i en grupp baserat på Egenskaper för användar konton, till exempel avdelning eller land. I den här artikeln beskrivs en demonstration av båda test miljöerna i Microsoft 365 för företag.

Det finns två faser för att konfigurera automatisk licensiering och dynamiskt grupp medlemskap i test miljön för Microsoft 365 för företag:

1. Skapa test miljön för Microsoft 365 för företag.
2. Konfigurera och testa dynamiskt grupp medlemskap och automatisk licensiering.

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med testlabbguider för Microsoft 365 för företag.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fas 1: bygga ut test miljön för Microsoft 365 för företag

Om du bara vill testa automatiserade licensierings-och grupp medlemskap på ett enkelt sätt med minimi kraven följer du anvisningarna i [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Om du vill testa automatiserade licensierings-och grupp medlemskap i ett simulerat företag följer du anvisningarna i [vidarekoppling](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> För testning av automatiserade licensierings-och grupp medlemskap krävs inte den simulerade företags test miljön, som innehåller ett simulerat intranät som är kopplat till Internet och Directory-synkronisering för en AD DS-skog (Active Directory Domain Services). Det tillhandahålls här som ett alternativ så att du kan testa automatiserad licensiering och grupp medlemskap och experimentera med den i en miljö som representerar en typisk organisation. 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>Fas 2: Konfigurera och testa dynamiskt grupp medlemskap och automatisk licensiering

Först skapar du en ny Sälj grupp och lägger till en regel för dynamiskt grupp medlemskap så att användar konton med avdelningen satt till Sales läggs till automatiskt i Sälj gruppen.

1. Använd en privat instans av webbläsaren och logga in på [administrations centret för microsoft 365](https://admin.microsoft.com) med det globala administratörs kontot för ditt Microsoft 365 E5 test labb-abonnemang.
2. Gå till Azure Portal på en separat flik i webbläsaren [https://portal.azure.com](https://portal.azure.com) .
3. I Azure-portalen skriver du **grupper** i sökrutan och klickar sedan på **grupper**.
4. i fönstret **alla grupper** klickar du på **ny grupp**.
5. Välj **Microsoft 365**i **grupptyp**.
6. I **grupp namn**skriver du **Sales**.
7. Välj **dynamisk användare**i **typ av medlemskap**.
8. Klicka på **dynamiska användar medlemmar**.
9. I fönstret **regler för dynamisk medlemskap** : 
   - Välj egenskapen **avdelning** .
   - Välj operatorn **Equal** .
   - Ange **försäljning** i **värde**.
10. Klicka på **Spara**.
11. Klicka på **Skapa**.

Sedan konfigurerar du Sälj gruppen så att medlemmar tilldelas automatiskt Microsoft 365 E5-licensen.

1. Klicka på **försäljnings** gruppen och sedan på **licenser**.
2. I fönstret **Uppdatera licens tilldelningar** väljer du **Microsoft 365 E5**och klickar sedan på **Spara**.
3. Stäng fliken för Azure-portalen i webbläsaren.

Sedan testar du dynamiskt grupp medlemskap och automatisk licensiering på användare 4-kontot. 

1. Klicka på **admin**på fliken **Microsoft Office Home** i webbläsaren.
2. På fliken **administrations Center för Microsoft 365** klickar du på **aktiva användare**.
3. På sidan **aktiva användare** klickar du på kontot **användare 4** .
4. Klicka på **Redigera** för **produkt licenser**i fönstret **användare 4** .
5. I fönstret **produkt licenser** inaktiverar du **Microsoft 365 E5** -licensen och klickar sedan på **Spara > Stäng**.
6. I egenskaperna för användare 4-kontot kontrollerar du att inga produkt licenser har tilldelats och att det inte finns några grupp medlemskap.
7. Klicka på **redigera** för **kontakt information**.
8. Klicka på **kontakt information**i fönstret **Redigera kontakt information** .
9. I fältet **avdelning** skriver du **försäljning**och klickar sedan på **Spara > Stäng**.
10. Vänta några minuter och klicka sedan på ikonen uppdatera längst upp till höger i användarens konto fönster. 

I tid bör du se:

- **Grupp medlemskaps** egenskapen har uppdaterats med **Sälj** gruppen.
- Egenskapen **produkt licenser** har uppdaterats med **Microsoft 365 E5** -licensen.

Se dessa artiklar för att distribuera dynamiskt grupp medlemskap och automatisk licensiering i produktion:

- LÄNKA TBD
- LÄNKA TBD

## <a name="next-step"></a>Nästa steg

Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.

## <a name="see-also"></a>Se även

[Identitets översikt](identity-roadmap-microsoft-365.md)

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Microsoft 365 för företags dokumentation](https://docs.microsoft.com/microsoft-365-enterprise/)
