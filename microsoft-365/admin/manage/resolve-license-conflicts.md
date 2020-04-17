---
title: Lösa licenskonflikter i Office 365 för företag
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 796f7eda-b1f8-479a-adee-bd9226ca47ec
description: Läs om hur du löser licenskonflikter med din Office 365 för företag-prenumeration.
ms.openlocfilehash: de0a6c988b9ca2ae033a24c012b7f36bc1db58a3
ms.sourcegitcommit: 4988934836eee45c890b9bdd5ef73590656c78ba
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2020
ms.locfileid: "43540921"
---
# <a name="resolve-license-conflicts-in-office-365-for-business"></a>Lösa licenskonflikter i Office 365 för företag

Vi rekommenderar att du köper de licenser som du behöver för din prenumeration innan du skapar nya användare. Då kan en licens tilldelas till nya användare när användarkonton skapas. Det uppstår licenskonflikter om du redan har tilldelat alla dina licenser till användare, men vissa licenser har gått ut, eller om du försöker ta bort en licens som redan är tilldelad till en användare. Mer information finns i [Ta bort licenser från prenumerationen](../../commerce/licenses/remove-licenses-from-subscription.md).
  
## <a name="how-do-i-view-license-conflicts"></a>Hur visar jag licenskonflikter?

::: moniker range="o365-worldwide"

1. Gå till sidan > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Faktureringslicenser</a> i administrationscentret. **Billing**

::: moniker-end

::: moniker range="o365-germany"

1. Gå till sidan > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Faktureringslicenser</a> i administrationscentret. **Billing**

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till sidan > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Faktureringslicenser</a> i administrationscentret. **Billing**

::: moniker-end


2. Titta i kolumnen **Status** för information om konflikten. Om det finns en konflikt visas ett varningsmeddelande som säger att en eller flera användare behöver en giltig licens.

    > [!NOTE]
    > Du kommer inte att se kolumnen **Status** om det inte finns några konflikter.

## <a name="how-do-i-resolve-license-conflicts"></a>Hur löser jag licenskonflikter?

Du kan lösa licenskonflikter genom att antingen [köpa fler licenser](../../commerce/licenses/buy-licenses.md) eller genom att ta bort licenser från användare som inte längre behöver [dem](remove-licenses-from-users.md). Du kan också [ta bort ett användarkonto för att frigöra en licens](../add-users/delete-a-user.md).
  
## <a name="related-articles"></a>Relaterade artiklar 

[Tilldela licenser till användare](assign-licenses-to-users.md)
  
[Ta bort licenser från användare](remove-licenses-from-users.md)
