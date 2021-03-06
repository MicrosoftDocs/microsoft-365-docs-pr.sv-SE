---
title: Överföra en domän från Microsoft till en annan värd
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: 'Läs anvisningarna här om du vill överföra en domän från Microsoft till en annan registrator. '
ms.openlocfilehash: f34e9733ab53c8bdc6f4432c96e6232ecc26ee06
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126353"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a>Överföra en domän från Microsoft till en annan värd

Du kan inte överföra en Microsoft 365 domän till en annan registrator i 60 dagar efter att du har köpt domänen från Microsoft.

> [!NOTE]
> En _Whois-fråga_   visar en Microsoft-köpt domänregistrator som Wild West Domains LLC. Men kontakta endast Microsoft angående din domän Microsoft 365 köpta domänen.

Följ dessa steg för att få en kod på Microsoft 365 och gå sedan till den andra domänregistratorns webbplats för att överföra domännamnet till den nya registratorn.

## <a name="transfer-a-domain"></a>Överföra en domän

1. I administrationscentret går du till   **Inställningar**   >  **Domains.**

2. På sidan **Domäner** väljer du den Microsoft 365 domän som du vill överföra till en annan domänregistrator och väljer sedan **Kontrollera hälsa.**

3. Högst upp på sidan väljer du **Överför domän**.

4. På sidan **Välj vart domänen ska överföras** väljer du En annan **registrator** och klickar sedan på **Nästa.**

5. På sidan **Lås upp domänöverföring** väljer **du Lås upp överföring för <_din_ >** domän och välj sedan **Nästa**.

6. Kontrollera kontaktinformationen för domänöverföring och välj **sedan Nästa**.

7. Kopiera auktoriseringskoden och vänta i ca 30  minuter på att  din domänöverföringsstatus ändras till Olåst för överföring på fliken Registrering innan du fortsätter med nästa steg.

8. Gå till webbplatsen för den domänregistrator som du vill hantera domännamnet i framtiden. Följ anvisningarna för att överföra en domän (sök efter hjälp på deras webbplats). Det innebär vanligtvis att betala överföringsavgifter och att ge autentiseringskoden till den nya registratorn så att de kan inleda överföringen. Microsoft skickar ett e-postmeddelande för att bekräfta att vi har fått överföringsbegäran, och domänen kommer att överföras inom 5 dagar.

    Du hittar fliken Registrering av **auktoriseringskod**  **på sidan** Domäner i Microsoft 365.
    
    > [!TIP]
    > För .uk-domäner krävs en annan procedur. Kontakta Microsoft Support och begär en **IPS-taggändring** så att den matchar registratorn du vill hantera din domän i framtiden. När taggen ändras överförs domänen omedelbart till den nya registratorn. Då måste du arbeta med den nya registratorn för att slutföra överföringen, troliga överföringsavgifter och lägga till den överförda domänen i ditt konto hos din nya registrator.

9. När överföringen är klar förnyar du domänen hos den nya domänregistratorn.

10. Slutför processen genom att gå tillbaka till sidan **Domäner** i administrationscentret och välja Slutför   **domänöverföring.** Då markeras domänen som ej längre köpt från Microsoft 365 och domänprenumerationen inaktiveras. Domänen tas inte bort från klientorganisationen och påverkar inte befintliga användare och postlådor på domänen.

> [!NOTE]
> Microsoft 365 köpta domäner är inte berättigade till namnserverändringar eller överföring av domänen mellan Microsoft 365 organisationer. Om något av dessa krävs måste domänregistreringen överföras till en annan registrator.
