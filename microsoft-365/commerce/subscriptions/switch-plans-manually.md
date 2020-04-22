---
title: Byt Microsoft 365 för affärsplaner manuellt
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
- Adm_NonTOC
- commerce
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: eb0d0680-5677-41a0-8c46-4b9d47f1c209
ROBOTS: NOINDEX
description: Byt Microsoft 365 för företag-prenumerationer manuellt genom att köpa en ny prenumeration och se till att båda prenumerationerna visas och är aktiva.
ms.openlocfilehash: f06e6a5f441286cbe048187eea39889772bb4e75
ms.sourcegitcommit: d4d082292dc711a579fe925ad989ea54ec2e27f4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43707517"
---
# <a name="switch-microsoft-365-for-business-plans-manually"></a>Byt Microsoft 365 för affärsplaner manuellt

::: moniker range="o365-worldwide"
> [!NOTE]
> Den här artikeln gäller det gamla administrationscentret. En vy av artikeln om det nya administrationscentret finns i [Ändra planer manuellt](change-plans-manually.md). Det nya administrationscentret är tillgängligt för alla Microsoft 365-administratörer och du kan anmäla dig genom att välja **Växlingsknappen Prova det nya administrationscentret** högst upp på startsidan. Mer information finns i [Om det nya administrationscentret för Microsoft 365](../../admin/microsoft-365-admin-center-preview.md).
::: moniker-end

## <a name="step-1-decide-how-to-switch-plans"></a>Steg 1: Bestäm hur du vill byta abonnemang

Det bästa sättet att växla alla användare från ett abonnemang till ett annat är att använda [knappen Använd knappen Växla abonnemang](switch-to-a-different-plan.md#use-the-switch-plans-button). Ibland går inte det. Gör istället ett manuellt byte:
  
- Om knappen **Byt abonnemang** inte visas.

- Om när du väljer knappen **Byt abonnemang** visas inte det abonnemang du vill använda.

- Om du inte vill byta alla användare på samma sätt. Vissa företag behöver ha olika abonnemang för olika användare. Gör ett manuellt byte i sådana fall.

Om du vill fortsätta med ett manuellt byte läser du [Steg 2: Köpa en ny prenumeration](#step-2-buy-a-new-subscription) i det här avsnittet.
  
## <a name="step-2-buy-a-new-subscription"></a>Steg 2: Köpa en ny prenumeration

 **Har du redan köpt en prenumeration?** Om du redan har en prenumeration som du vill flytta användare till hoppar du över det här steget och går till [Steg 3: Kontrollera din nya prenumeration och dina nya licenser](#step-3-check-your-new-subscription-and-licenses) i det här avsnittet.
  
- eller
  
 **Köp en ny prenumeration och licenser:** Följ stegen i [Köp en annan Microsoft 365 för företag-prenumeration för](../buy-another-subscription.md) att köpa en ny prenumeration.
  
Se till att du köper en prenumeration för samma organisation som användarna finns i nu. Kontrollera till exempel e-postadresserna för de användare som du vill flytta. Om deras e-postadresser innehåller @contoso.com måste du köpa en ny prenumeration för contoso.com. Ta med en licens för varje användare som du vill flytta.
  
 **Om du behöver hjälp med att välja ett abonnemang**läser du [produktjämnsidan för Microsoft 365 för företag](https://go.microsoft.com/fwlink/p/?linkid=842056) eller [samtalssupport](../../admin/contact-support-for-business-products.md).
  
## <a name="step-3-check-your-new-subscription-and-licenses"></a>Steg 3: Kontrollera din nya prenumeration och dina nya licenser

::: moniker range="o365-worldwide"

1. Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Prenumerationer</a> i administrationscentret.

::: moniker-end

::: moniker range="o365-germany"

1. Gå till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Prenumerationer</a> i administrationscentret.

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Prenumerationer</a> i administrationscentret.

::: moniker-end

2. **Kontrollera att båda prenumerationerna visas och är aktiva**

    Den prenumeration du flyttar användare från och den prenumeration du flyttar användare till måste listas tillsammans. Om den nya prenumerationen inte finns när du kontrollerar först försöker du igen senare. Kontrollera att båda prenumerationerna visas under **AKTIV**. [Den nya prenumerationen visas inte eller är inte aktiv.](#the-new-subscription-isnt-listed-or-isnt-active).

3. **Kontrollera att du har tillräckligt med licenser för varje användare**

    Varje användare måste ha en licens som överensstämmer med prenumerationen. Så om du vill flytta tio användare till Microsoft 365 Business Premium måste du se till att tio licenser är tillgängliga. 

4. **Behöver du köpa fler licenser för den nya prenumerationen?** Gå till sidan **Prenumerationer** och [Köp licenser för din Microsoft 365 för företag-prenumeration](../licenses/buy-licenses.md).
  
    [Vad gäller för de gamla licenserna?](#what-about-the-old-licenses)

### <a name="the-new-subscription-isnt-listed-or-isnt-active"></a>Den nya prenumerationen visas inte eller är inte aktiv.

- **Om du har köpt en prenumeration på faktura** och det krävs en kreditkontroll kan det ta upp till två arbetsdagar innan prenumerationen blir tillgänglig.

- **Om du har köpt två prenumerationer och båda inte visas här** kan de ha köpts för olika organisationer (för olika domäner). Prenumerationer kan inte användas över organisationsgränser.

- **Om du vet att du har ytterligare en prenumeration**, och den inte visas här, eller under **AKTIV**[kontaktar du supporten](../../admin/contact-support-for-business-products.md).

### <a name="what-about-the-old-licenses"></a>Vad gäller för de gamla licenserna?

Licenser för den aktuella prenumerationen tas bort senare. Du betalar då bara för de nya licenserna.
  
## <a name="step-4-reassign-licenses"></a>Steg 4: Fördela om licenser

### <a name="reassign-a-license-for-one-user"></a>Fördela om en licens för en användare

::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.

::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till sidan **Användare** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till sidan **Användare** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.

::: moniker-end

2. På sidan **Aktiva användare** markerar du rutan bredvid namnet på den användare som du vill tilldela en licens till.

3. Välj **Redigera**på raden **Produktlicenser** till höger .

4. I fönstret **Produktlicenser** flyttar du reglaget till positionen **På** för den licens du vill tilldela användaren. Som standard är tilldelas alla tjänster som är associerade till den licensen automatiskt till användaren.

    > [!TIP]
    > Om du vill begränsa vilka tjänster som är tillgängliga för användaren drar du reglaget till positionen **Av** för de tjänster som du vill ta bort för den användaren. Om du till exempel vill att användaren ska ha tillgång till alla tillgängliga tjänster utom Skype för företag - Online kan du flytta reglaget för tjänsten Skype för företag - Online till positionen **Av**.
  
5. Växla växlingsknappen till **avpositionen** för licenser som den här användaren inte längre behöver.

6. Längst ned i fönstret **Produktlicenser** väljer du **Tilldela** \> **stäng.** \> **Close**

### <a name="reassign-licenses-for-multiple-users-at-once"></a>Tilldela om licenser för flera användare samtidigt

::: moniker range="o365-worldwide"

1. Gå till sidan Aktiva <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">användare</a> i **administrationscentret.** \>

::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.

::: moniker-end

2. Markera kryssrutorna för de användare som du vill lägga till befintliga licenser för.

3. I fönstret **Massåtgärder** väljer du **Redigera produktlicenser**.

4. I fönstret **Tilldela produkter** väljer du **Ersätt befintliga licenstilldelningar** \> **Nästa**.

5. Ställ reglaget i läget **På** för de produkter du vill lägga till för dessa användare.

    > [!TIP]
    > - Om du vill begränsa vilka tjänster som är tillgängliga för användaren drar du reglaget till positionen **Av** för de tjänster som du vill ta bort för den användaren. Om du till exempel vill att användaren ska ha tillgång till alla tillgängliga tjänster utom Skype för företag - Online kan du flytta reglaget för tjänsten Skype för företag - Online till positionen **Av**.
    > - Alla tidigare tilldelade licenser för de markerade användarna tas bort.
  
6. Längst ned i fönstret **Ersätt befintliga produkter** väljer du **Ersätt** \> **Stäng**.

## <a name="step-5-cancel-subscriptions-or-remove-licenses-that-you-no-longer-need-optional"></a>Steg 5: Avbryt prenumerationer eller ta bort licenser som du inte längre behöver (valfritt)

Om du har flyttat alla användare från ett abonnemang till ett annat och du inte behöver det ursprungliga abonnemanget längre kan du [avbryta abonnemanget](cancel-your-subscription.md).
  
Om du bara har flyttat vissa användare till en annan prenumeration kan du [ta bort licenser](../licenses/remove-licenses-from-subscription.md) som du inte längre behöver.
  
## <a name="call-support-to-help-you-switch-plans"></a>Ring supporten som hjälper dig att byta abonnemang

[Ring support](../../admin/contact-support-for-business-products.md)