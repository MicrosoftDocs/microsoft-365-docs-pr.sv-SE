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
description: Administratörer kan läsa mer om rapporten Om vidarebefordrade meddelanden automatiskt i instrumentpanelen för e-postflöde i Säkerhets- & efterlevnadscenter.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 75cf060d9a597bb991fc8af2c4c70f9ecc592ad7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929366"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>Information om automatiskt vidarebefordrade meddelanden i Säkerhets- & Säkerhets- och efterlevnadscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Insikten om vidarebefordrade meddelanden [](mail-flow-insights-v2.md) i instrumentpanelen för **e-postflöde** i Säkerhets- och & [efterlevnadscenter](https://protection.office.com) visar information om meddelanden som automatiskt vidarebefordras från organisationen till mottagare i externa domäner.

![Widget för automatiskt vidarebefordrade meddelanden i Säkerhets- & Säkerhets- och efterlevnadscenter](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a>Information om automatiskt vidarebefordrade meddelanden

När du klickar på antalet meddelanden i widgeten visas en utfällig ruta med mer information om automatiskt vidarebefordrade meddelanden:

- **Meddelanden som vidarebefordras automatiskt med vidarebefordransmetoder:**

  - **Efter e-postflödesregler**
  - **Efter inkorgsregler**
  - **Genom SMTP-vidarebefordran:** Den här metoden anger automatisk vidarebefordran som administratörer kan konfigurera för en postlåda enligt beskrivningen i Konfigurera vidarebefordran av [e-post för en postlåda.](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)
  - En länk till [vidarebefordransrapporten för](view-mail-flow-reports.md#forwarding-report) mer information.

- **Meddelanden vidarebefordras automatiskt av domäner och användare:**

  - **De 5 översta domänerna vidarebefordras till**
  - **Nya domäner (förra veckan)**
  - **De 5 främsta användarna av vidarebefordran**
  - **Nya användare (förra veckan)**
  - En länk till rapporten [Ändringar av vidarebefordran om](mfi-new-users-forwarding-email.md#forwarding-modifications-report) du vill ha mer information.

![Den utfällande informationen för rapporten Automatiskt vidarebefordrade meddelanden i säkerhets- & Säkerhets- och efterlevnadscenter](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a>Insikter

Två insikter skapas baserat på rapportdata:

- [Nya användare vidarebefordrar e-post](mfi-new-users-forwarding-email.md)
- [Nya domäner som vidarebefordras e-post](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a>Se även

Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinformation i Säkerhets- & efterlevnadscenter.](mail-flow-insights-v2.md)