---
title: Hantera faktureringsprofiler
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: Läs om hur faktureringsprofiler stöder fakturor.
keywords: faktureringsprofil, fakturor, avgifter, hanterade avgifter
ms.openlocfilehash: c9bd089843bcb620dc3feb8ec3e8f946cd739d17
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42811497"
---
# <a name="manage-billing-profiles"></a>Hantera faktureringsprofiler
För kommersiella kunder som köper produkter och tjänster från Microsoft kan du med faktureringsprofilerna anpassa vilka artiklar som ingår på fakturan och hur du betalar dina fakturor.

Faktureringsprofiler innehåller följande information:

- **Faktureringskonto** &ndash; Namnet på faktureringskontot som profilen är relaterad till
- **Betalningsmetoder** &ndash; Kredit- eller betalkort, bankkonton, check eller banköverföring
- **Kontaktuppgifter** &ndash; Faktureringsadress och ett kontaktnamn
- **Fakturainställningar** &ndash; Valuta baserat på faktureringskontots land, ett valfritt inköpsordernummer och möjlighet att ta emot fakturor som e-postbilagor
- **Behörigheter** &ndash; behörigheter som gör att du kan ändra faktureringsprofil, lönefakturor eller använda betalningsmetoden i faktureringsprofilen för att göra inköp

Använd faktureringsprofiler för att styra dina inköp och anpassa fakturan. En månadsfaktura genereras för de produkter som köps med faktureringsprofilen. Du kan anpassa fakturan, till exempel uppdatera inköpsordernumret och inställningen för e-postfaktura.

En faktureringsprofil skapas automatiskt för ditt faktureringskonto under ditt första köp. Du kan skapa faktureringsprofiler på sidan <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Faktureringsprofiler</a> för att ställa in fler fakturor. Du kan till exempel använda olika faktureringsprofiler när du gör inköp för varje avdelning i organisationen. På nästa faktureringsdatum får du en faktura för varje faktureringsprofil.

## <a name="billing-profile-roles"></a>Roller för faktureringsprofil

Roller för faktureringsprofiler har behörighet att styra inköp och visa och hantera fakturor. Tilldela dessa roller till användare som spårar, organiserar och betalar fakturor, till exempel medlemmar i anskaffningsteamet i organisationen.

| Roll                          | Beskrivning                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| Ägare av faktureringsprofil         | Hantera allt för en faktureringsprofil                                           |
| Deltagare i faktureringsprofil   | Hantera allt utom behörigheter i en faktureringsprofil                         |
| Läsare av faktureringsprofiler        | Skrivskyddad vy över allt i en faktureringsprofil                                 |
| Fakturaansvarig               | Visa och betala räkningar och har en skrivskyddad bild av allt i en faktureringsprofil   |

## <a name="view-billing-profiles"></a>Visa faktureringsprofiler

1. I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848039" target="_blank">Fakturor och betalningar</a>.

2. Välj **Faktureringsprofiler**och välj sedan en faktureringsprofil i listan.

    - På fliken **Översikt** kan du redigera information om faktureringsprofil och aktivera eller inaktivera skicka en faktura via e-post.

    - På fliken **Behörigheter** kan du tilldela roller till användare att betala fakturor.

    - På fliken **Azure-kreditsaldo** kan Azure-kunder se transaktionsbalanshistorik för Azure-krediter som används av faktureringsprofilen.

    - På fliken **Azure-krediter kan Azure-kunder** se en lista över Azure-krediter som är associerade med faktureringsprofilen och deras utgångsdatum.

    > [!NOTE]
    > Om du inte har några Azure-krediter visas inte flikarna **Azure-kreditsaldo** eller **Azure-krediter.**

## <a name="need-help-contact-support"></a>Behöver du hjälp? Kontakta supporten.

Om du har frågor eller behöver hjälp med dina <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">Azure-avgifter skapar du en supportbegäran med Azure-supporten</a>.

Om du har frågor eller behöver hjälp med din faktureringsprofil i Microsoft 365 administrationscenter [kontaktar du supporten för företagsprodukter](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).
