---
title: Konfigurera vidarebefordran av e-post
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Konfigurera vidarebefordran av e-post till ett eller flera e-postkonton med hjälp av Office365.
ms.openlocfilehash: cdefab3df59f1c57abbc221943b58c978ff582a9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51050720"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a>Konfigurera vidarebefordran av e-post i Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).

::: moniker-end

Som administratör för en organisation kanske du behöver konfigurera vidarebefordran av e-post för en användares postlåda. Med vidarebefordran av e-post kan du vidarebefordra e-postmeddelanden som skickas till en användares brevlåda till en annan användares brevlåda i eller utanför organisationen.

> [!IMPORTANT]
> Du kan använda principer för utgående skräppostfilter för att styra automatisk vidarebefordran till externa mottagare. Mer information finns i Styra [automatisk vidarebefordran av extern e-post i Microsoft 365.](https://docs.microsoft.com/microsoft-365/security/defender-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls)

## <a name="configure-email-forwarding"></a>Konfigurera vidarebefordran av e-post

Innan du konfigurerar vidarebefordran av e-post ska du observera följande:

- När du har ställt in vidarebefordran av e-post **vidarebefordras** bara nya  *e-postmeddelanden*  som skickas till från postlådan.

- Vidarebefordran av e-post kräver  *att från-kontot*  har en licens. Om du konfigurerar vidarebefordran av e-post eftersom användaren har lämnat organisationen är ett annat alternativ att [göra om postlådan till en delad postlåda](convert-user-mailbox-to-shared-mailbox.md). På det sättet kan flera personer komma åt den. En delad postlåda kan dock inte vara större än 50 GB.

Du måste vara Exchange-administratör eller global administratör i Microsoft 365 för att kunna göra följande. Mer information finns i avsnittet Om [administratörsroller.](../add-users/about-admin-roles.md)

::: moniker range="o365-worldwide"

1. I administrationscentret går du till **sidan Användare** \> **[aktiva](https://go.microsoft.com/fwlink/p/?linkid=834822)** användare.

2. Välj namnet på den användare vars e-post du vill vidarebefordra för att öppna egenskapssidan.

3. På fliken **E-post** väljer du Hantera **vidarebefordran av e-post**.

4. På sidan för vidarebefordran av e-post väljer du Vidarebefordra alla e-postmeddelanden som skickats till den här postlådan **,** anger adressen för vidarebefordran och väljer om du vill behålla en kopia av vidarebefordrade e-postmeddelanden. Se till att en licens tilldelas till användarkontot om du inte ser det här alternativet. Välj **Spara ändringar**.

    **Om du vill vidarebefordra till flera e-postadresser** kan du be användaren att ange en regel i Outlook som vidarebefordras till adresserna. Mer information finns i Använda [regler för att automatiskt vidarebefordra meddelanden](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).

     I administrationscentret kan du skapa en [distributionsgrupp](../setup/create-distribution-lists.md) [,](add-user-or-contact-to-distribution-list.md)lägga till adresser till den och sedan konfigurera vidarebefordran så att den pekar på distributionslistan med hjälp av instruktionerna i den här artikeln.

5. Ta inte bort kontot för användaren som vidarebefordrar e-post eller ta bort deras licens!  Om du gör det stoppas vidarebefordran av e-post.

::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till **sidan Användare** \> **[aktiva](https://go.microsoft.com/fwlink/p/?linkid=847686)** användare.

2. Välj namnet på den användare vars e-post du vill vidarebefordra för att öppna egenskapssidan.

3. Expandera **e-postinställningarna** och välj **sedan** Redigera i avsnittet Vidarebefordran av **e-post.**

4. På sidan för vidarebefordran av e-post ställer du in växlingsknappen på På **,** anger adressen för vidarebefordran och väljer om du vill behålla en kopia av vidarebefordrade e-postmeddelanden. Se till att en licens tilldelas till användarkontot om du inte ser det här alternativet. Välj **Spara**.

   **Om du vill vidarebefordra till flera e-postadresser** kan du be användaren att ange en regel i Outlook som vidarebefordras till adresserna. Mer information finns i Använda [regler för att automatiskt vidarebefordra meddelanden](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).

   I administrationscentret kan du skapa en [distributionsgrupp](../setup/create-distribution-lists.md) [,](add-user-or-contact-to-distribution-list.md)lägga till adresser till den och sedan konfigurera vidarebefordran så att den pekar på distributionslistan med hjälp av instruktionerna i den här artikeln.

5. Ta inte bort kontot för användaren som vidarebefordrar e-post eller ta bort deras licens!  Om du gör det stoppas vidarebefordran av e-post.

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till **sidan Användare** \> **[aktiva](https://go.microsoft.com/fwlink/p/?linkid=850628)** användare.

2. Välj namnet på den användare vars e-post du vill vidarebefordra för att öppna egenskapssidan.

3. Expandera **e-postinställningarna** och välj **sedan** Redigera i avsnittet Vidarebefordran av **e-post.**

4. På sidan för vidarebefordran av e-post ställer du in växlingsknappen på På **,** anger adressen för vidarebefordran och väljer om du vill behålla en kopia av vidarebefordrade e-postmeddelanden. Se till att en licens tilldelas till användarkontot om du inte ser det här alternativet. Välj **Spara**.

   **Om du vill vidarebefordra till flera e-postadresser** kan du be användaren att ange en regel i Outlook som vidarebefordras till adresserna. Mer information finns i Använda [regler för att automatiskt vidarebefordra meddelanden](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).

   I administrationscentret kan du skapa en [distributionsgrupp](../setup/create-distribution-lists.md) [,](add-user-or-contact-to-distribution-list.md)lägga till adresser till den och sedan konfigurera vidarebefordran så att den pekar på distributionslistan med hjälp av instruktionerna i den här artikeln.

5. Ta inte bort kontot för användaren som vidarebefordrar e-post eller ta bort deras licens!  Om du gör det stoppas vidarebefordran av e-post.

::: moniker-end