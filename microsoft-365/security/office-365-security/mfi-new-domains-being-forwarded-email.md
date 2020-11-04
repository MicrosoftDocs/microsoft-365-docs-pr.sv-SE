---
title: Nya domäner som vidarebefordras via e-post
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: Administratörer kan läsa mer om hur du använder de nya domänerna som vidarebefordrar e-postmeddelande inblick i det moderna administrations centret för Exchange för att undersöka när användare i organisationen vidarebefordrar meddelanden till externa domäner som aldrig har vidarebefordrats till.
ms.openlocfilehash: 7dfdd63a9358b1057313962bc21424a325d7bc52
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877747"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>Nya domäner vidarebefordras med e-post i säkerhets & efterlevnad

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Även om du kan ha giltiga företags skäl att vidarebefordra e-postmeddelanden till externa mottagare i vissa domäner är det misstänkt när användare i organisationen plötsligt startar vidarebefordran av meddelanden till externa domäner och ingen i organisationen har översänt meddelanden till dessa domäner före (nya domäner). Detta kan tyda på att användar kontona har komprometterats. Om du misstänker att kontona är inaktiverade kan du läsa mer i [svara på ett komprometterat e-postkonto](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).

De **nya domänerna som vidarebefordras via e-post** i [säkerhets & för regelefterlevnad](https://protection.office.com) meddelar dig när användare i organisationen vidarebefordrar meddelanden till nya domäner.

Denna inblick visas bara när problemet identifieras och visas på sidan för [vidarebefordran av rapporter](view-mail-flow-reports.md#forwarding-report) .

![Nya domäner som vidarebefordras via e-post](../../media/mfi-new-domains-being-forwarded.png)

När du klickar på widgeten visas en utfällbar plats där du kan hitta mer information om de vidarebefordrade meddelandena, inklusive en länk tillbaka till [vidarebefordrings rapporten](view-mail-flow-reports.md#forwarding-report).

![Den utfällbara informationen som visas när du klickar på den nya domänen som vidarebefordrar e-postinsikt](../../media/mfi-new-domains-being-forwarded-details.png)

Du kan också komma åt den här informations sidan när du väljer inblicken när du klickar på **Visa alla** i området **Top Insights & rekommendationer** på ( **rapport** \> **instrument panel** eller <https://protection.office.com/insightdashboard> ).

För att förhindra automatisk vidarebefordran av meddelanden till externa domäner konfigurerar du en fjärrdomän för vissa eller alla externa domäner. Mer information finns i [Hantera fjärrdomäner i Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).

## <a name="related-topics"></a>Relaterade ämnen

Information om andra insikter i instrument panelen för e-postflöden finns i avsnittet om [hur du använder e-postflöde i säkerhets & Compliance Center](mail-flow-insights-v2.md).
