---
title: Auto-vidarebefordrade meddelanden insikt
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: Administratörer kan läsa mer om rapporten om automatiskt vidarebefordrade meddelanden i instrumentpanelen för e-postflöde i Säkerhets- & Efterlevnadscenter.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c95c403e0b342bf0466c45804ba3975c492b8e1b
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150610"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>Information om automatiskt vidarebefordrade meddelanden i Säkerhets- & Efterlevnadscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender för Office 365 abonnemang 1 och abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Insikten om vidarebefordrade meddelanden [](mail-flow-insights-v2.md) i instrumentpanelen för **e-postflöde** i Säkerhets- [&](https://protection.office.com) efterlevnadscenter visar information om meddelanden som automatiskt vidarebefordras från organisationen till mottagare i externa domäner.

![Widget för automatiskt vidarebefordrade meddelanden i Säkerhets- & Efterlevnadscenter](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a>Information om automatiskt vidarebefordrade meddelanden

När du klickar på antalet meddelanden i widgeten visas en utfällig ruta som visar mer information om automatiskt vidarebefordrade meddelanden:

- **Automatiskt vidarebefordrade meddelanden genom vidarebefordransmetoder:**

  - **Efter e-postflödesregler**
  - **Efter regler för Inkorgen**
  - **Genom SMTP-vidarebefordran:** Den här metoden anger automatisk vidarebefordran som administratörer kan konfigurera för en postlåda enligt beskrivningen i Konfigurera vidarebefordran av [e-post för en postlåda.](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)
  - En länk till [vidarebefordransrapporten för](view-mail-flow-reports.md#forwarding-report) mer information.

- **Automatiskt vidarebefordrade meddelanden efter domäner och användare:**

  - **De 5 översta domänerna vidarebefordrade till**
  - **Nya domäner (förra veckan)**
  - **De 5 främsta användarna för vidarebefordran**
  - **Nya användare (förra veckan)**
  - En länk till rapporten [Om att vidarebefordra ändringar för](mfi-new-users-forwarding-email.md#forwarding-modifications-report) mer information.

![Den utfällande informationen för rapporten om automatiskt vidarebefordrade meddelanden i & Säkerhets- och efterlevnadscenter](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a>Insikter

Två insikter skapas baserat på rapportdata:

- [Nya användare vidarebefordrar e-post](mfi-new-users-forwarding-email.md)
- [Nya domäner som vidarebefordras e-post](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a>Se även

Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinsikter i Säkerhets- & Efterlevnadscenter.](mail-flow-insights-v2.md)
