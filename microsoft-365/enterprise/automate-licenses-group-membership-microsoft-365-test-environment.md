---
title: Automatisera licensiering och gruppmedlemskap för microsoft 365 Enterprise-testmiljön
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
description: Konfigurera gruppbaserad licensiering och dynamiskt gruppmedlemskap i microsoft 365 Enterprise-testmiljön.
ms.openlocfilehash: 266ae8cb133eccf74ea75382b400ca8241782ec5
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42809331"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a>Automatisera licensiering och gruppmedlemskap för microsoft 365 Enterprise-testmiljön

*Den här testlabbet-guiden kan endast användas för Microsoft 365 Enterprise-testmiljöer.*

Gruppbaserad licensiering tilldelar eller tar automatiskt bort licenser för ett användarkonto baserat på gruppmedlemskap. Dynamiskt gruppmedlemskap lägger till eller tar bort medlemmar i en grupp baserat på användarkontoegenskaper, till exempel Avdelning eller Land. I den här artikeln beskrivs en demonstration av båda i microsoft 365 Enterprise-testmiljön.

Det finns två faser för att konfigurera automatisk licensiering och dynamiskt gruppmedlemskap i microsoft 365 Enterprise-testmiljön:

1. Skapa testmiljön för Microsoft 365 Enterprise.
2. Konfigurera och testa dynamiskt gruppmedlemskap och automatisk licensiering.

![Testlabbguider för Microsoft-molnet](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill ha en visuell karta till alla artiklar i Microsoft 365 Enterprise Test Lab Guide-stacken.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fas 1: Bygg ut testmiljön för Microsoft 365 Enterprise

Om du bara vill testa automatiserad licensiering och gruppmedlemskap på ett lätt väg med minimikraven följer du instruktionerna i [Lightweight base-konfigurationen](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Om du vill testa automatiserad licensiering och gruppmedlemskap i ett simulerat företag följer du instruktionerna i [Direktautentisering](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testning av automatiserad licensiering och gruppmedlemskap kräver inte den simulerade företagstestmiljön, som innehåller ett simulerat intranät som är anslutet till Internet och katalogsynkronisering för en AD DS-skog (Active Directory Domain Services). Det finns här som ett alternativ så att du kan testa automatiserad licensiering och gruppmedlemskap och experimentera med det i en miljö som representerar en typisk organisation. 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>Fas 2: Konfigurera och testa dynamiskt gruppmedlemskap och automatisk licensiering

Först skapar du en ny försäljningsgrupp och lägger till en dynamisk gruppmedlemskapsregel så att användarkonton med avdelningen som försäljning läggs automatiskt till i gruppen Försäljning.

1. Logga in på Office 365-portalen med det [https://portal.office.com](https://portal.office.com) globala administratörskontot för din Microsoft 365 E5-testlabbprenumeration med en privat instans av webbläsaren.
2. På en separat flik i webbläsaren går [https://portal.azure.com](https://portal.azure.com)du till Azure-portalen på .
3. Skriv **grupper** i sökrutan i Azure-portalen och klicka sedan på **Grupper**.
4. Klicka på **Ny grupp**i fönstret **Alla grupper** .
5. Välj **Office 365**i **Grupptyp**.
6. Skriv **Försäljning**i **Gruppnamn**.
7. I **medlemstyp**väljer du **Dynamisk användare**.
8. Klicka på **Dynamiska användare.**
9. I fönstret **Regler för dynamiskt medlemskap:** 
   - Välj **egenskapen avdelning.**
   - Välj operatorn **Lika med.**
   - Skriv **Försäljning** i **värde**.
10. Klicka på **Spara**.
11. Klicka på **Skapa**.

Därefter konfigurerar du försäljningsgruppen så att medlemmarna tilldelas Microsoft 365 E5-licensen automatiskt.

1. Klicka på gruppen **Försäljning** och sedan på **Licenser**.
2. Välj **Microsoft 365 E5**i fönstret **Uppdatera licenstilldelningar** och klicka sedan på **Spara**.
3. Stäng fliken Azure-portal i webbläsaren.

Därefter testar du dynamiskt gruppmedlemskap och automatisk licensiering på User 4-kontot. 

1. Klicka på **Admin**på fliken **Start för Microsoft Office** i webbläsaren .
2. Klicka på **Aktiva användare**på fliken Administrationscenter för **Microsoft 365** .
3. Klicka på kontot Användare **4** på sidan **Aktiva användare.**
4. Klicka på **Redigera** för **produktlicenser**i fönstret **Användare 4** .
5. Inaktivera **Microsoft 365 E5-licensen** i fönstret **Produktlicenser** och klicka sedan på **Spara > Stäng**.
6. I egenskaperna för User 4-kontot kontrollerar du att inga produktlicenser har tilldelats och att det inte finns några gruppmedlemskap.
7. Klicka på **Redigera** för **kontaktinformation**.
8. Klicka på Kontaktinformation i fönstret **Redigera kontaktinformation.** **Contact information**
9. Skriv **Försäljning**i fältet **Avdelning** och klicka sedan på Spara **> Stäng**.
10. Vänta några minuter och klicka sedan regelbundet på uppdateringsikonen längst upp till höger i fönstret Användare 4-konto. 

Med tiden bör du se:

- **Egenskapen Gruppmedlemskap** har uppdaterats med gruppen **Försäljning.**
- **Egenskapen Product licenses** har uppdaterats med **Microsoft 365** E5-licensen.

Se de här stegen i identitetsfasen för information och länkar för att distribuera dynamiskt gruppmedlemskap och automatisk licensiering i produktion:

- [Konfigurera automatisk licensiering](identity-use-group-management.md#identity-group-license)
- [Konfigurera dynamiskt gruppmedlemskap](identity-use-group-management.md#identity-dyn-groups)

## <a name="next-step"></a>Nästa steg

Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) och funktioner i testmiljön.

## <a name="see-also"></a>Se även

[Fas 2: Identitet](identity-infrastructure.md)

[Testlaboratorikguider för Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Distribution av Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Dokumentation från Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
