---
title: Ta bort en domän
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Lär dig hur du tar bort en gammal domän från Microsoft 365 och flyttar användare och grupper till en annan domän eller avbryter prenumerationen.
ms.openlocfilehash: ce75be758edf330226692395dbc6a2c332ed9069
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286255"
---
# <a name="remove-a-domain"></a>Ta bort en domän

 **[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter.

Tar du bort en domän på grund av att du vill lägga till den i ett annat Microsoft 365-abonnemang? Eller vill du avbryta din prenumeration? Du kan [ändra ditt abonnemang eller din prenumeration](../../commerce/subscriptions/switch-to-a-different-plan.md) eller [avbryta prenumerationen](../../commerce/subscriptions/cancel-your-subscription.md).

### <a name="step-1-move-users-to-another-domain"></a>Steg 1: Flytta användare till en annan domän

#### <a name="move-users"></a>Flytta användare

::: moniker range="o365-worldwide"

1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">administrationscentret</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a>.

::: moniker-end

2. Välj **Användare**  >  **Aktiva användare.**

3. Markera kryssrutorna för alla användare som du vill flytta.

4. Högst upp på sidan och välj sedan **Ändra domäner**.

5. Välj **en annan domän** i fönstret Ändra domäner.

Du måste även göra detta för dig själv om du använder den domän som du vill ta bort. När du redigerar domänen för ditt konto måste du logga ut och logga in igen med den nya domänen du har valt.

#### <a name="move-yourself"></a>Flytta dig själv

::: moniker range="o365-worldwide"

1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">administrationscentret</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a>.

::: moniker-end

2. Gå  till \> **Användare aktiva** användare och välj ditt konto i listan.

3. På fliken **Konto** väljer du **Hantera användarnamn** och väljer sedan en annan domän.

4. Högst upp väljer du ditt kontonamn och sedan Logga **ut**.

5. Logga in med den nya domänen och ditt lösenord.

Du kan också använda PowerShell för att flytta användare till en annan domän. Se [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname) för mer information. Om du vill ange standarddomänen använder du [Set-MsolDomain](/powershell/module/msonline/set-msoldomain).

### <a name="step-2-move-groups-to-another-domain"></a>Steg 2: Flytta användare till en annan domän

::: moniker range="o365-worldwide"

1. Gå till sidan Grupper i **administrationscentret.** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a>

::: moniker-end
::: moniker range="o365-germany"

1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">sidan Grupper</a>i  >  administrationscentret.

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">sidan Grupper</a>i  >  administrationscentret.

::: moniker-end

2. Markera gruppens namn och välj sedan Redigera **på fliken** Allmänt under **E-postadress,** **Primär**.

3. Välj en annan domän i listrutan.

4. Välj **Spara** och sedan **Stäng**. Upprepa proceduren för alla grupper eller distributionslistor som är kopplade till den domän som du försöker ta bort.

### <a name="step-3-remove-the-old-domain"></a>Steg 3: Ta bort den gamla domänen

::: moniker range="o365-worldwide"

1. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.

::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till **sidan** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Konfigurera</a> domäner.

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till **sidan** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Konfigurera</a> domäner.

::: moniker-end

2. På sidan **Domäner** väljer du den domän som du vill ta bort.

3. Välj Ta bort i det högra **fönstret.**

4. Följ eventuella ytterligare uppmaningar och välj sedan **Stäng**.

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a>Hur länge dröjer det innan en domän tas bort?

Det kan ta så lite som 5 minuter för Microsoft 365 att ta bort en domän om den inte finns med på många platser, till exempel säkerhetsgrupper, distributionslistor, användare Microsoft 365 säkerhetsgrupper. Om det finns många referenser till domänen kan det ta flera timmar (ett dygn) innan domänen tas bort.

Om du har hundratals eller tusentals användare använder du PowerShell och letar upp alla användare och flyttar dem till en annan domän. Annars kan det hända att några användare missas i gränssnittet och när du sedan försöker ta bort domänen så går det inte och du kommer inte att veta varför. Mer information finns i [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname). Om du vill ange standarddomänen använder du [Set-MsolDomain](/powershell/module/msonline/set-msoldomain).

## <a name="still-need-help"></a>Behöver du fortfarande hjälp?

::: moniker range="o365-worldwide"

> [!NOTE]
> Du kan inte ta bort domänen [".onmicrosoft.com"](../setup/domains-faq.yml) från ditt konto. När du tar bort en domän återgår användarkontona till ".onmicrosoft.com"-adressen som primärt SMTP/UserprincipalName.

Fungerar det fortfarande inte? Domänen kan behöva tas bort manuellt. [Ring oss](../../business-video/get-help-support.md) så kan vi hjälpa dig med det!

::: moniker-end

::: moniker range="o365-germany"

> [!NOTE]
> Du kan inte ta bort [domänen ".onmicrosoft.de"](../setup/domains-faq.yml) från kontot. När du tar bort en domän återgår användarkontona till ".onmicrosoft.de"-adressen som primärt SMTP/UserprincipalName.

Fungerar det fortfarande inte? Domänen kan behöva tas bort manuellt. [Ring oss](../../business-video/get-help-support.md?view=o365-germany&preserve-view=true) så kan vi hjälpa dig med det!

::: moniker-end

::: moniker range="o365-21vianet"

> [!NOTE]
> Du kan inte ta bort [domänen ".partner.onmschina.cn"](../setup/domains-faq.yml) från kontot. När du tar bort en domän återgår användarkontona till ".partner.onmschina.cn"-adressen som primärt SMTP/UserprincipalName.

Fungerar det fortfarande inte? Domänen kan behöva tas bort manuellt. [Ring oss](../../business-video/get-help-support.md?view=o365-21vianet&preserve-view=true) så kan vi hjälpa dig med det!

::: moniker-end

## <a name="related-content"></a>Relaterat innehåll

[Domänens vanliga frågor och svar](../setup/domains-faq.yml) (artikel)

[Byta till ett annat Microsoft 365 för företag-abonnemang](../../commerce/subscriptions/switch-to-a-different-plan.md) (artikel)

[Avsluta din prenumeration](../../commerce/subscriptions/cancel-your-subscription.md) (artikel)
