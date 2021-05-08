---
title: Förstå faktureringsprofiler
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_billing
- PPM_jmueller
search.appverid: MET150
description: Läs om hur faktureringsprofiler har stöd för fakturor.
ms.date: 04/02/2021
ms.openlocfilehash: 57786df370246c2b4fda556a9c48eb828db1cb4f
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52280793"
---
# <a name="understand-billing-profiles"></a>Förstå faktureringsprofiler

För kommersiella kunder som köper produkter och tjänster från Microsoft kan du anpassa faktureringsprofilerna vilka artiklar som ingår på fakturan och hur du betalar dina fakturor.

Faktureringsprofiler innehåller följande information:

- **Faktureringskonto** &ndash; Namnet på faktureringskontot som profilen är relaterad till
- **Betalningsmetoder** &ndash; Kredit- eller betalkort, bankkonton, check eller banköverföring
- **Kontaktinformation** &ndash; Faktureringsadress och kontaktnamn
- **Fakturainställningar** &ndash; Valuta baserat på landet för faktureringskontot, ett valfritt inköpsordernummer och alternativet att ta emot fakturor som e-postbilagor
- **Behörigheter** &ndash; Behörigheter som gör att du kan ändra faktureringsprofil, betala räkningar eller använda betalningsmetoden i faktureringsprofilen för att göra inköp

Använd faktureringsprofiler för att styra dina köp och anpassa fakturan. En månadsfaktura skapas för produkter som köpts med faktureringsprofilen. Du kan anpassa fakturan, till exempel uppdatera inköpsordernumret och inställningen för e-postfaktura.

En faktureringsprofil skapas automatiskt för ditt faktureringskonto vid ditt första köp. Du kan skapa faktureringsprofiler på <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">sidan Faktureringsprofiler</a> om du vill konfigurera fler fakturor. Du kan till exempel använda olika faktureringsprofiler när du gör inköp för varje avdelning i organisationen. På nästa faktureringsdatum får du en faktura för varje faktureringsprofil.

## <a name="billing-profile-roles"></a>Faktureringsprofilroller

Roller i faktureringsprofiler har behörighet att styra inköp och visa och hantera fakturor. Tilldela de här rollerna till användare som spårar, organiserar och betalar fakturor, t.ex. medlemmar i organisationens anskaffningsteam.

| Roll                         | Beskrivning                                                                      |
|----------------------------- |--------------------------------------------------------------------------------- |
| Faktureringsprofilägare        | Hantera allt för en faktureringsprofil                                          |
| Deltagare i faktureringsprofil  | Hantera allt utom behörigheter i en faktureringsprofil                        |
| Faktureringsprofilläsare       | Skrivskyddad vy av allt i en faktureringsprofil                                |
| Fakturaansvarig              | Visa och betala räkningar och har en skrivskyddad vy av allt i en faktureringsprofil  |

## <a name="view-billing-profiles"></a>Visa faktureringsprofiler

1. I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Fakturor och betalningar</a>.
2. Välj **Faktureringsprofiler** och välj sedan en faktureringsprofil i listan.

    - På fliken **Översikt** kan du redigera faktureringsprofilinformation och aktivera eller inaktivera fakturautskick via e-post.
    - På fliken **Behörigheter** kan du tilldela roller till användare för att betala fakturor.
    - På fliken **Azure-kreditsaldo** kan Azure-kunder se historik för transaktionssaldo för Azure-krediter som används av den faktureringsprofilen.
    - På fliken **Azure-krediter** kan Azure-kunder se en lista över Azure-krediter som är kopplade till den faktureringsprofilen och deras utgångsdatum.

    > [!NOTE]
    > Om du inte har några Azure-krediter visas inte flikarna **Azure-kreditsaldo** **eller Azure-krediter.**

## <a name="need-help-contact-support"></a>Behöver du hjälp? Kontakta support

Om du har frågor eller behöver hjälp med dina Azure-avgifter kan <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">du skapa en supportbegäran med Azure-supporten.</a>

Om du har frågor eller behöver hjälp med din faktureringsprofil i Microsoft 365 kan [du kontakta supporten för företagsprodukter.](../../business-video/get-help-support.md)
