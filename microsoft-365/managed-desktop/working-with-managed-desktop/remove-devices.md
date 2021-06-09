---
title: Ta bort enheter
description: Ta bort enheter Microsoft Hanterat skrivbord hantering
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: fa1cb7307fddd815a2a9249c5a98739d21bd2418
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893929"
---
# <a name="remove-devices"></a>Ta bort enheter

Du kan ta bort enheter Microsoft Hanterat skrivbord hantering med hjälp av administrationsportalen. Den här åtgärden är permanent, men du kan registrera dem i Microsoft Hanterat skrivbord igen genom att följa [registreringsstegen.](../get-started/register-devices-self.md)

När du tar bort en enhet inträffar följande:

- Vi tar bort enheten från Autopilot.
- Vi tar bort enheten från alla enhetsgrupper på "Modern Workplace".
- Vi tar bort enheten från **bladet** Enheter i administrationsportalen.

När du tar bort en enhet kan du även ta bort den från Azure Active Directory (Azure AD) och Microsoft Intune.
 
> [!CAUTION]
> Borttagning av objekt relaterade till en enhet från Azure AD och Microsoft Intune är permanent. Om du tar bort objekten kan du inte visa eller hantera enheter från Intune- och Azure-portalerna. Enheterna kommer inte att kunna komma åt företagets resurser. Företagsdata kan tas bort från dem om enheterna försöker logga in efter att de tagits bort.

1. I [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)väljer du **Enheter** i det vänstra navigeringsfönstret.
2. Titta efter **Microsoft Hanterat skrivbord** i menyn och välj **Enheter**.
3. I arbetsytan Microsoft Hanterat skrivbord Enheter väljer du de enheter som du vill ta bort.
4. Välj **Enhetsåtgärder** och välj sedan Ta **bort enhet som** öppnar en flyg in för att ta bort enheterna.
5. Kontrollera de valda enheterna i infället och välj sedan Ta **bort enheter**. Om du även vill ta bort Azure AD- och Intune-objekten samtidigt markerar du kryssrutan. Borttagning av enheter kan ta några minuter att slutföra.

> [!NOTE]
> Du kan inte ta bort enheter som har ett **väntande** registreringstillstånd.