---
title: Lägga till stöd för anonym inkommande e-post via IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
description: Administratör kan lära sig hur du konfigurerar stöd för anonym inkommande e-post från IPv6-källor i Exchange Online och Exchange Online Protection.
ms.openlocfilehash: 414c10f3387138ed7e62f2de4e8549e45d128d2e
ms.sourcegitcommit: 256184cf731c1851b04a07dd7d59ecf020d02635
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/03/2020
ms.locfileid: "43131525"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-office-365"></a>Lägga till stöd för anonym inkommande e-post via IPv6 i Office 365

Office 365-organisationer med Exchange Online-postlådor och fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor stöder anonym inkommande e-post via IPv6. Käll-IPv6-e-postservern måste uppfylla båda följande krav:

- Käll-IPv6-adressen måste ha en giltig PTR-post (Reverse DNS lookup) som gör att målet kan hitta domännamnet från IPv6-adressen.

- Avsändaren måste godkänna antingen SPF-verifiering (definierad i [RFC 7208)](https://tools.ietf.org/html/rfc7208)eller [DKIM-verifiering](https://dkim.org/) (definierad i [RFC 6376).](https://www.rfc-editor.org/rfc/rfc6376.txt)

Innan din organisation kan ta emot anonymt inkommande e-postmeddelande via IPv6 måste en administratör kontakta Microsoft-supporten och be om den. Instruktioner om hur du öppnar en supportbegäran finns i [Kontakta support för företagsprodukter - Hjälp om administratörer](../../admin/contact-support-for-business-products.md).

När anonymt inkommande IPv6-meddelandestöd har aktiverats i din organisation går meddelandet igenom den normala meddelandefiltrering som tillhandahålls av tjänsten.

## <a name="troubleshooting"></a>Felsökning

- Om källmeddelandeservern inte har en omvänd DNS-sökningspost för IPv6 avvisas meddelandena med följande fel:

  > 450 4.7.25 Tjänsten är inte tillgänglig, vilket skickar IPv6-adress [2a01:111:f200:2004::240] måste ha omvänd DNS-post.

- Om avsändaren inte skickar SPF- eller DKIM-validering avvisas meddelandena med följande fel:

  > 450 4.7.26 Tjänsten är inte tillgänglig, meddelande som skickas via IPv6 [2a01:111:f200:2004::240] måste passera antingen SPF- eller DKIM-validering.

- Om du försöker ta emot anonyma IPv6-meddelanden innan du har anmält dig kommer meddelandet att avvisas med följande fel:

  > 550 5.2.1 Tjänsten är inte tillgänglig, [contoso.com] accepterar inte e-post via IPv6.

## <a name="for-more-information"></a>Mer information

[Stöd för validering av DKIM-signerade meddelanden](support-for-validation-of-dkim-signed-messages.md)
