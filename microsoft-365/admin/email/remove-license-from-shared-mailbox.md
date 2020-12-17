---
title: Ta bort licens från delad postlåda
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: bb229ee9-e7be-4990-b3eb-354e75740496
description: 'Ta bort licensen från en delad post låda för att tilldela den till en annan användare. '
ms.openlocfilehash: 11d5185cc3f79899a737ddccc0a93160acb380bc
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698309"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a>Ta bort en licens från en delad postlåda

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

Delade post lådor kräver normalt ingen licens. Följ de här anvisningarna om du vill ta bort en licens från en delad post låda så att du kan tilldela den till en användare eller returnera licensen så att du inte betalar för en licens som du inte behöver.

> [!NOTE]
> En licens krävs i följande fall:
> 1. Den delade post lådan har mer än 50 GB lagrings utrymme.
> 2. Den delade post lådan använder arkivering på plats.
> 3. Den delade post lådan placeras i en tvist.
> 4. Den delade post lådan har en Microsoft Defender-licens tilldelad.

  
## <a name="remove-the-license"></a>Ta bort licensen

::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.

   > [!NOTE]
   > Du måste ta bort licensen från sidan aktiva användare. Du kan inte ta bort licensen från sidan Delad post låda eftersom licenser är användar inställningar. 
  
2. Välj den delade post lådan.

3. Fliken **licenser och appar** , expandera **licenser** och avmarkera kryss rutan för den licens du vill ta bort.

4. Välj **Spara ändringar**.

5. När du återvänder till sidan **aktiva användare** blir statusen för den delade post lådan **olicensierad**.

6. Du betalar fortfarande för licensen. Om du vill sluta betala för det [tar du bort licensen från din prenumeration](../../commerce/licenses/remove-licenses-from-subscription.md).

::: moniker-end

::: moniker range="o365-germany"

 1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.

    > [!NOTE]
    > Du måste ta bort licensen från sidan aktiva användare. Du kan inte ta bort licensen från sidan Delad post låda eftersom licenser är användar inställningar.

2. Välj den delade post lådan och välj sedan **redigera** bredvid **produkt licenser**.

3. Sidan **produkt licenser** väljer du växling till **av** för den licens du vill ta bort.

4. Välj **Spara**.

5. När du återvänder till sidan **aktiva användare** blir statusen för den delade post lådan **olicensierad**.

6. Du betalar fortfarande för licensen. Om du vill sluta betala för det [tar du bort licensen från din prenumeration](../../commerce/licenses/remove-licenses-from-subscription.md).

::: moniker-end

::: moniker range="o365-21vianet"

 1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.

    > [!NOTE]
    > Du måste ta bort licensen från sidan aktiva användare. Du kan inte ta bort licensen från sidan Delad post låda eftersom licenser är användar inställningar.

2. Välj den delade post lådan och välj sedan **redigera** bredvid **produkt licenser**.

3. Sidan **produkt licenser** väljer du växling till **av** för den licens du vill ta bort.

4. Välj **Spara**.

5. När du återvänder till sidan **aktiva användare** blir statusen för den delade post lådan **olicensierad**.

6. Du betalar fortfarande för licensen. Om du vill sluta betala för det [tar du bort licensen från din prenumeration](../../commerce/licenses/remove-licenses-from-subscription.md).

::: moniker-end 

 

## <a name="related-articles"></a>Relaterade artiklar

[Om delade postlådor](about-shared-mailboxes.md)

[Skapa en delad postlåda](create-a-shared-mailbox.md)

[Konfigurera en delad postlåda](configure-a-shared-mailbox.md)

[Konvertera en användarpostlåda till en delad postlåda](convert-user-mailbox-to-shared-mailbox.md)

[Lösa problem med delade postlådor](resolve-issues-with-shared-mailboxes.md)
