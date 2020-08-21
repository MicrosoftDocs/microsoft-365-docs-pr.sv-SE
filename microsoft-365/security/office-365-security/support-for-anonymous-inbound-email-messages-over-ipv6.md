---
title: Lägga till stöd för anonym inkommande e-post över IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratören kan läsa om hur du konfigurerar stöd för anonym inkommande e-post från IPv6-källor i Exchange Online och Exchange Online Protection.
ms.openlocfilehash: 7384c1044cc02ec20079dc03068c2ca99e68d2c2
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826783"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a>Lägga till stöd för anonym inkommande e-post via IPv6 i Microsoft 365

Microsoft 365-organisationer med Exchange Online-postlådor och fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor stöder anonym inkommande e-post via IPv6. Käll-e-postservern för IPv6 måste uppfylla följande krav:

- Källans IPv6-adress måste ha en giltig PTR-post (omvänd DNS lookup) som tillåter målet att hitta domän namnet från IPv6-adressen.

- Avsändaren måste klara antingen SPF-verifiering (definieras i [rfc 7208](https://tools.ietf.org/html/rfc7208)) eller [DKIM-verifiering](https://dkim.org/) (definieras i [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).

Innan din organisation kan ta emot anonym inkommande e-post via IPv6 måste en administratör kontakta Microsoft support och be om det. Anvisningar för hur du öppnar en supportbegäran finns i [kontakta supporten för företags produkter – hjälp för administratörer](../../admin/contact-support-for-business-products.md).

När anonymt stöd för inkommande IPv6-meddelanden är aktiverat i din organisation kommer meddelandet att gå igenom den vanliga meddelande filtreringen som tillhandahålls av tjänsten.

## <a name="troubleshooting"></a>Felsökning

- Om käll-e-postservern inte har en omvänd IPv4-uppslags post nekas meddelandena med följande fel:

  > 450 4.7.25-tjänsten är inte tillgänglig, skickar IPv6-adress [2a01: F200:2004:: 240] måste ha omvänd DNS-post.

- Om avsändaren inte skickar SPF-eller DKIM-verifiering nekas meddelandena med följande fel:

  > 450 4.7.26-tjänsten är inte tillgänglig, meddelande skickat via IPv6 [2a01:111: F200:2004:: 240] måste klara antingen SPF-eller DKIM-verifiering.

- Om du försöker ta emot anonyma IPv6-meddelanden innan du har angett avvisas meddelandet med följande fel:

  > 550 5.2.1-tjänsten är inte tillgänglig, [contoso.com] accepterar inte e-post via IPv6.

## <a name="related-topics"></a>Relaterade ämnen

[Stöd för validering av DKIM-signerade meddelanden](support-for-validation-of-dkim-signed-messages.md)