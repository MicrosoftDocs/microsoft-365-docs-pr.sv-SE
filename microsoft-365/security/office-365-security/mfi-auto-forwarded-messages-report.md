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
ms.openlocfilehash: 8f5e7088a88307576a054a1f6833101789d68d01
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290639"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>Information om automatiskt vidarebefordrade meddelanden i Säkerhets- & Efterlevnadscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Insikten om vidarebefordrade meddelanden [](mail-flow-insights-v2.md) i instrumentpanelen för **e-postflöde** i Säkerhets- [&](https://protection.office.com) efterlevnadscenter visar information om meddelanden som automatiskt vidarebefordras från organisationen till mottagare i externa domäner.

![Widget för automatiskt vidarebefordrade meddelanden i Säkerhets- & Efterlevnadscenter](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a>Information om automatiskt vidarebefordrade meddelanden

När du klickar på antalet meddelanden i widgeten visas en utfällig ruta med mer information om automatiskt vidarebefordrade meddelanden:

- **Automatiskt vidarebefordrade meddelanden genom vidarebefordransmetoder:**

  - **Efter e-postflödesregler**
  - **Efter regler för Inkorgen**
  - **Genom SMTP-vidarebefordran:** Den här metoden anger automatisk vidarebefordran som administratörer kan konfigurera för en postlåda enligt beskrivningen i Konfigurera vidarebefordran av [e-post för en postlåda.](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)
  - En länk till [vidarebefordransrapporten](view-mail-flow-reports.md#forwarding-report) för mer information.

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
