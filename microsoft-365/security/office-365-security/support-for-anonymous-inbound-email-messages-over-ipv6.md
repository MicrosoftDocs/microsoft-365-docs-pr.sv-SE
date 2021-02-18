---
title: Lägga till stöd för anonym inkommande e-post över IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratören kan läsa mer om hur du konfigurerar stöd för anonym inkommande e-post från IPv6-källor i Exchange Online och Exchange Online Protection.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 63c9434fbd1f69c0cbd3145717b712857eb17e28
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290279"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a>Lägga till stöd för anonym inkommande e-post via IPv6 i Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Microsoft 365-organisationer med Exchange Online-postlådor och fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor har stöd för anonym inkommande e-post via IPv6. Käll-IPv6-e-postservern måste uppfylla båda följande krav:

- Käll-IPv6-adressen måste ha en giltig omvänd DNS-uppslagspost (PTR) som gör att destinationen kan hitta domännamnet från IPv6-adressen.

- Avsändaren måste överföra antingen SPF-verifiering (definierad i [RFC 7208)](https://tools.ietf.org/html/rfc7208)eller [DKIM-verifiering](http://dkim.org/) (definierad i [RFC 6376).](https://www.rfc-editor.org/rfc/rfc6376.txt)

Innan din organisation kan ta emot anonym inkommande e-post via IPv6 måste en administratör kontakta Microsofts support och be om det. Anvisningar om hur du öppnar en supportbegäran finns i [Kontakta supporten för företagsprodukter – hjälp för administratörer.](../../admin/contact-support-for-business-products.md)

När stödet för anonyma inkommande IPv6-meddelanden har aktiverats i organisationen går meddelandet igenom den vanliga meddelandefiltrering som tillhandahålls av tjänsten.

## <a name="troubleshooting"></a>Felsökning

- Om käll-e-postservern inte har en IPv6 omvänd DNS-uppslagspost, avvisas meddelandena med följande felmeddelande:

  > 450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.

- Om avsändaren inte klarar SPF- eller DKIM-valideringen avvisas meddelandena med följande felmeddelande:

  > 450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.

- Om du försöker ta emot anonyma IPv6-meddelanden innan du har valt att delta, avvisas meddelandet med följande felmeddelande:

  > 550 5.2.1 Tjänsten är inte tillgänglig, [contoso.com] accepterar inte e-post via IPv6.

## <a name="related-topics"></a>Relaterade ämnen

[Stöd för validering av DKIM-signerade meddelanden](support-for-validation-of-dkim-signed-messages.md)
