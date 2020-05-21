---
title: Ta bort licens från delad postlåda
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
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: bb229ee9-e7be-4990-b3eb-354e75740496
description: 'Ta bort licens från en delad postlåda för att tilldela den till en annan användare. '
ms.openlocfilehash: 9ba411c614fee93e37ac45e58fd40bf246a9c2ab
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327248"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a>Ta bort en licens från en delad postlåda

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Delade postlådor kräver vanligtvis ingen licens. Följ dessa instruktioner om du vill ta bort en licens från en delad postlåda så att du antingen kan tilldela den till en användare eller returnera licensen så att du inte betalar för en licens som du inte behöver.

> [!NOTE]
> En licens krävs i följande scenarier:
> 1. Den delade postlådan har mer än 50 GB lagringsutrymme som används.
> 2. Den delade postlådan använder arkivering på plats.
> 3. Den delade postlådan placeras i bevarande av juridiska skäl.

  
## <a name="remove-the-license"></a>Ta bort licensen

::: moniker range="o365-worldwide"

> [!NOTE]
> Om du inte använder det nya administrationscentret för Microsoft 365 kan du aktivera det genom att välja **Prova det nya administrationscentret** längst upp på startsidan.

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.

   > [!NOTE]
   > Du måste ta bort licensen från sidan Aktiva användare. Du kan inte ta bort licensen från sidan Delad postlåda eftersom licenser är användarinställningar. 
  
2. Markera den delade postlådan.

3. En av fliken **Licenser och appar,** expandera **Licenser** och avmarkera rutan för den licens du vill ta bort.

4. Välj **Spara ändringar**.

5. När du går tillbaka till sidan **Aktiva användare** kommer statusen för den delade postlådan att vara **Olicensierad**.

6. Du betalar fortfarande för licensen. Om du vill sluta betala för [den tar du bort licensen från prenumerationen](../../commerce/licenses/remove-licenses-from-subscription.md).

::: moniker-end

::: moniker range="o365-germany"

 1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.

   > [!NOTE]
   > Du måste ta bort licensen från sidan Aktiva användare. Du kan inte ta bort licensen från sidan Delad postlåda eftersom licenser är användarinställningar.

2. Markera den delade postlådan och välj sedan **Redigera bredvid** **Produktlicenser**.

3. En av sidan **Produktlicenser** anger du växlingsknappen till **Av** för den licens som du vill ta bort.

4. Välj **Spara**.

5. När du går tillbaka till sidan **Aktiva användare** kommer statusen för den delade postlådan att vara **Olicensierad**.

6. Du betalar fortfarande för licensen. Om du vill sluta betala för [den tar du bort licensen från prenumerationen](../../commerce/licenses/remove-licenses-from-subscription.md).

::: moniker-end

::: moniker range="o365-21vianet"

 1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.

   > [!NOTE]
   > Du måste ta bort licensen från sidan Aktiva användare. Du kan inte ta bort licensen från sidan Delad postlåda eftersom licenser är användarinställningar.

2. Markera den delade postlådan och välj sedan **Redigera bredvid** **Produktlicenser**.

3. En av sidan **Produktlicenser** anger du växlingsknappen till **Av** för den licens som du vill ta bort.

4. Välj **Spara**.

5. När du går tillbaka till sidan **Aktiva användare** kommer statusen för den delade postlådan att vara **Olicensierad**.

6. Du betalar fortfarande för licensen. Om du vill sluta betala för [den tar du bort licensen från prenumerationen](../../commerce/licenses/remove-licenses-from-subscription.md).

::: moniker-end 

## <a name="related-articles"></a>Relaterade artiklar

[Om delade postlådor](about-shared-mailboxes.md)

[Skapa en delad postlåda](create-a-shared-mailbox.md)

[Konfigurera en delad postlåda](configure-a-shared-mailbox.md)

[Konvertera en användarpostlåda till en delad postlåda](convert-user-mailbox-to-shared-mailbox.md)

[Lösa problem med delade postlådor](resolve-issues-with-shared-mailboxes.md)
