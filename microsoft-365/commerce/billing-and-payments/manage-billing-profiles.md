---
title: Förstå faktureringsprofiler
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
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
search.appverid: MET150
description: Läs om hur faktureringsprofiler har stöd för fakturor.
ms.date: 04/02/2021
ms.openlocfilehash: e66efe12e05d2aaf286b689c955f17c8401144f1
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537337"
---
# <a name="understand-billing-profiles"></a>Förstå faktureringsprofiler

En faktureringsprofil innehåller ett betalningssätt, faktureringsinformation och andra fakturainställningar, till exempel inköpsordernummer och fakturainställning via e-post. Du använder en faktureringsprofil för att betala för de produkter som du köper från Microsoft. En faktureringsprofil skapas automatiskt när en användare gör ett självbetjäningsköp. Varje faktureringsprofil faktureras separat.

> [!NOTE]
>
> Faktureringsprofiler är inte tillgängliga för kunder som köper produkter  och tjänster från Microsoft.com eller på sidan Köptjänster Microsoft 365 administrationscentret.

## <a name="what-are-billing-profile-roles"></a>Vad är faktureringsprofilroller?

Roller i faktureringsprofiler har behörighet att styra inköp och visa och hantera fakturor. Tilldela de här rollerna till användare som spårar, organiserar och betalar fakturor. Till exempel medlemmar i organisationens inköpsteam.

| Roll                         | Beskrivning                                                                      |
|----------------------------- |--------------------------------------------------------------------------------- |
| Faktureringsprofilägare        | Hantera allt för en faktureringsprofil                                          |
| Deltagare i faktureringsprofil  | Hantera allt utom behörigheter i en faktureringsprofil                        |
| Faktureringsprofilläsare       | Skrivskyddad vy av allt i en faktureringsprofil                                |
| Fakturaansvarig              | Visa och betala räkningar och har en skrivskyddad vy av allt i en faktureringsprofil  |

## <a name="view-my-billing-profiles"></a>Visa mina faktureringsprofiler

> [!NOTE]
>
> Om du följer de här stegen och listan med faktureringsprofiler är tom innebär det att du inte har en faktureringsprofil och kan inte använda den här funktionen.

1. I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Fakturor och betalningar</a>.
2. Välj fliken **Faktureringsprofil** och välj sedan en faktureringsprofil i listan.

Varje faktureringsprofil innehåller följande information:

- **Namn och status för faktureringsprofilen** &ndash; Det unika namnet på faktureringsprofilen och om faktureringsprofilen är aktiv eller inaktiverad för köp.
- **Fakturainställningar** &ndash; Valuta baserat på landet för faktureringskontot, information om fakturafrekvens och datum, alternativet att ta emot fakturor som e-postbilagor och valfritt fält för inköpsordernummer
- **Betalningsmetoder** &ndash; Visar den primära betalningsmetoden och den eventuella betalningsmetoden för profilen
- **Faktureringskonto** &ndash; Namnet på faktureringskontot som profilen är relaterad till. Mer information om faktureringskonton finns i [Förstå faktureringskonton.](../manage-billing-accounts.md)
- **Kontaktinformation** &ndash; Faktureringsadress och kontaktnamn och e-postadress
- **Faktureringsprofilroller** &ndash; En lista över personer som har tilldelats en av faktureringsprofilrollerna för att göra saker för den profilen. Du kan till exempel betala fakturor, lägga till ett inköpsordernummer eller ersätta den betalningsmetod som används för att göra inköp.

> [!NOTE]
>
> Du kan bara tilldela faktureringsprofilroller till användare i organisationen.

## <a name="need-help-contact-support"></a>Behöver du hjälp? Kontakta support

Om du har frågor eller behöver hjälp med dina Azure-avgifter kan <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">du skapa en supportbegäran med Azure-supporten.</a>

Om du har frågor eller behöver hjälp med din faktureringsprofil i Microsoft 365 kan [du kontakta support.](../../business-video/get-help-support.md)

## <a name="related-content"></a>Relaterat innehåll

[Så här betalar du för prenumerationen med en faktureringsprofil](pay-for-subscription-billing-profile.md) (artikel)\
[Förstå faktureringskonton](../manage-billing-accounts.md) (artikel)\
[Hantera betalningsmetoder](manage-payment-methods.md) (artikel)
