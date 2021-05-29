---
title: Ta bort licens från delad postlåda
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
ms.reviewer: nicholak
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_licensing
search.appverid:
- BCS160
- MET150
- MOE150
description: 'Ta bort en licens från en delad postlåda för att tilldela den till en annan användare eller returnera licensen så att du inte betalar för den. '
ms.openlocfilehash: d33487879506402c5f0de2f7942c3299c5698b73
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706292"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a>Ta bort en licens från en delad postlåda

Delade postlådor kräver vanligtvis inte en licens. Följ de här anvisningarna om du vill ta bort en licens från en delad postlåda så att du kan tilldela den till en användare eller returnera licensen så att du inte betalar för en licens som du inte behöver.

> [!NOTE]
>
> En licens krävs i följande scenarier:
>
> 1. Den delade postlådan har mer än 50 GB lagringsutrymme som används.
> 2. Den delade postlådan använder arkivering på plats.
> 3. Den delade postlådan ligger i ett bevarande av juridiska skäl.
> 4. Den delade postlådan har en tilldelad Microsoft Defender-licens.

## <a name="remove-the-license"></a>Ta bort licensen

::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.

::: moniker-end

   > [!NOTE]
   > Du måste ta bort licensen från sidan Aktiva användare. Du kan inte ta bort licensen från sidan Delad postlåda eftersom licenser är användarinställningar.
  
2. Välj den delade postlådan.

3. På fliken **Licenser och appar** expanderar du **Licenser** och avmarkerar rutan för den licens du vill ta bort.

4. Välj **Spara ändringar**.

5. När du återgår till **sidan Aktiva** användare blir statusen för den delade postlådan **Ej licensierad.**

6. Du betalar fortfarande för licensen. Ta bort licensen från prenumerationen [om du vill sluta betala för den.](../../commerce/licenses/buy-licenses.md)

## <a name="related-content"></a>Relaterat innehåll

[Om delade postlådor](about-shared-mailboxes.md) (artikel)\
[Skapa en delad postlåda](create-a-shared-mailbox.md) (artikel)\
[Konfigurera en delad postlåda](configure-a-shared-mailbox.md) (artikel)\
[Konvertera en användarpostlåda till en delad postlåda](convert-user-mailbox-to-shared-mailbox.md) (artikel)\
[Lösa problem med delade postlådor](resolve-issues-with-shared-mailboxes.md) (artikel)
