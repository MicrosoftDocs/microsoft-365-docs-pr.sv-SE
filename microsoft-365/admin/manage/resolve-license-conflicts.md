---
title: Lösa licenskonflikter
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 796f7eda-b1f8-479a-adee-bd9226ca47ec
description: Lär dig hur du löser licens konflikter med ditt Microsoft 365 för företag-abonnemang.
ms.openlocfilehash: a7f0b5cbca98a0550954e322c6fbe51d93627ee4
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645089"
---
# <a name="resolve-license-conflicts"></a>Lösa licenskonflikter

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Vi rekommenderar att du köper de licenser du behöver för ditt abonnemang innan du skapar nya användare. Då kan en licens tilldelas till nya användare när användarkonton skapas. Det uppstår licenskonflikter om du redan har tilldelat alla dina licenser till användare, men vissa licenser har gått ut, eller om du försöker ta bort en licens som redan är tilldelad till en användare. Mer information finns i [ta bort licenser från din prenumeration](../../commerce/licenses/remove-licenses-from-subscription.md).
  
## <a name="how-do-i-view-license-conflicts"></a>Hur visar jag licenskonflikter?

::: moniker range="o365-worldwide"

1. Gå till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenser</a> i administrationscentret.

::: moniker-end

::: moniker range="o365-germany"

1. Gå till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenser</a> i administrationscentret.

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenser</a> i administrationscentret.

::: moniker-end

2. Titta i kolumnen **Status** för information om konflikten. Om en konflikt uppstår visas ett varnings meddelande som anger att en eller flera användare behöver en giltig licens.

    > [!NOTE]
    > Du kommer inte att se kolumnen **Status** om det inte finns några konflikter.

## <a name="how-do-i-resolve-license-conflicts"></a>Hur löser jag licenskonflikter?

Du kan lösa licens konflikter genom att antingen [köpa fler licenser](../../commerce/licenses/buy-licenses.md) eller genom att [ta bort licenser från användare som inte längre behöver dem](remove-licenses-from-users.md). Du kan också [ta bort ett användarkonto för att frigöra en licens](../add-users/delete-a-user.md).
  
## <a name="related-articles"></a>Relaterade artiklar

[Tilldela licenser till användare](assign-licenses-to-users.md)
  
[Ta bort licenser från användare](remove-licenses-from-users.md)
