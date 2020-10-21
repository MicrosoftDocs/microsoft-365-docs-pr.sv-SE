---
title: Hantera faktureringsprofiler
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Lär dig hur fakturerings profiler stöder fakturor.
keywords: fakturerings profil, fakturor, avgifter, hanterade avgifter
ms.openlocfilehash: de6d6cd65d9e83e7211bcdc33f1774aaec3d1729
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638453"
---
# <a name="manage-billing-profiles"></a>Hantera faktureringsprofiler

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

För kommersiella kunder som köper produkter och tjänster från Microsoft kan du med hjälp av fakturerings profiler anpassa vilka objekt som ska ingå på din faktura och hur du betalar dina fakturor.

Fakturerings profiler innehåller följande information:

- **Fakturerings konto** &ndash; Namnet på kontot som profilen är relaterad till
- **Betalnings metoder** &ndash; Kredit-eller betalkort, bank konton, check eller överföring
- **Kontakt information** &ndash; Fakturerings adress och ett kontakt namn
- **Faktura inställningar** &ndash; Valuta baserat på fakturerings kontots land, ett valfritt inköps order nummer och alternativet att ta emot fakturor som e-postbilagor
- **Behörigheter** &ndash; för Behörigheter som gör att du kan ändra fakturerings profil, betala räkningar eller använda betalnings metoden i fakturerings profilen för att göra inköp

Använd betalnings profiler för att kontrol lera dina inköp och anpassa din faktura. En månads faktura genereras för de produkter som köpts med fakturerings profilen. Du kan anpassa fakturan, till exempel uppdatera inköps order numret och preferensen för e-post.

En fakturerings profil skapas automatiskt för ditt fakturerings konto under ditt första inköp. Du kan skapa fakturerings profiler på sidan <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">faktura profiler</a> för att registrera fler fakturor. Du kan till exempel använda olika fakturerings profiler när du gör inköp för varje avdelning i organisationen. Vid nästa fakturerings datum får du en faktura för varje fakturerings profil.

## <a name="billing-profile-roles"></a>Roller för fakturerings profiler

Roller i fakturerings profiler har behörighet att kontrol lera inköp samt Visa och hantera fakturor. Tilldela dessa roller till användare som spårar, strukturerar och betalar fakturor, till exempel medlemmar i anskaffnings gruppen i din organisation.

| Roll                          | Beskrivning                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| Ägare till fakturerings profil         | Hantera allt för en fakturerings profil                                           |
| Deltagare i fakturerings profil   | Hantera allt utom behörigheter i en fakturerings profil                         |
| Profil läsare        | Skrivskyddad vy av allt i en fakturerings profil                                 |
| Faktura chef               | Visa och betala räkningar och har en skrivskyddad vy av allt i en fakturerings profil   |

## <a name="view-billing-profiles"></a>Visa fakturerings profiler

1. I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Fakturor och betalningar</a>.

2. Välj **betalnings profiler**och välj sedan en fakturerings profil i listan.

    - På fliken **Översikt** kan du redigera information om fakturerings profiler och aktivera eller inaktivera en faktura via e-post.

    - På fliken **behörigheter** kan du tilldela roller till användare för att betala fakturor.

    - På fliken för **Azure-saldot** kan Azure-kunder se historik för transaktions sal Don för de Azure-tillgodohavanden som används av den betalnings profilen.

    - På fliken **Azure-kredit** kan Azure-kunderna se en lista över de Azure-tillgodohavanden som är kopplade till fakturerings profilen och deras utgångs datum.

    > [!NOTE]
    > Om du inte har något Azure-tillgodohavande visas inte flikarna för **Azure-saldo** eller **Azure** -kredit.

## <a name="need-help-contact-support"></a>Behöver du hjälp? Kontakta supporten.

Om du har frågor eller behöver hjälp med dina Azure-avgifter kan du <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">skapa en supportbegäran med Azure-support</a>.

Om du har frågor eller behöver hjälp med din fakturerings profil i Microsoft 365 Admin Center kan du [kontakta supporten för företags produkter](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).
