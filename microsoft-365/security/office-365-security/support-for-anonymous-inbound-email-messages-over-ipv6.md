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
description: Administratören kan lära sig hur de konfigurerar stöd för anonym inkommande e-post från IPv6-källor i Exchange Online och Exchange Online Protection.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 80fdcc9dcfe3006ef8b21aa19856fe8c0ea3ff70
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300055"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a>Lägga till stöd för anonym inkommande e-post via IPv6 i Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 organisationer med Exchange Online och fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online stöder anonym inkommande e-post via IPv6. Käll-IPv6-e-postservern måste uppfylla båda följande krav:

- Käll-IPv6-adressen måste ha en giltig omvänd DNS-uppslagspost (PTR) som gör att destinationen kan hitta domännamnet från IPv6-adressen.

- Avsändaren måste överföra antingen SPF-verifiering (definierad i [RFC 7208)](https://tools.ietf.org/html/rfc7208)eller [DKIM-verifiering](http://dkim.org/) (definierad i [RFC 6376).](https://www.rfc-editor.org/rfc/rfc6376.txt)

Innan din organisation kan ta emot anonym inkommande e-post via IPv6 måste en administratör kontakta Microsofts support och be om det. Anvisningar om hur du öppnar en supportbegäran finns i [Kontakta supporten för företagsprodukter – hjälp för administratörer.](../../business-video/get-help-support.md)

När stöd för anonyma inkommande IPv6-meddelanden har aktiverats i organisationen går meddelandet igenom den vanliga meddelandefiltrering som tillhandahålls av tjänsten.

## <a name="troubleshooting"></a>Felsökning

- Om käll-e-postservern inte har en IPv6 omvänd DNS-uppslagspost, avvisas meddelandena med följande fel:

  > 450 4.7.25 Tjänsten är inte tillgänglig och skickar IPv6-adress [2a01:111:f200:2004::240] måste ha omvänd DNS-post.

- Om avsändaren inte klarar SPF- eller DKIM-valideringen avvisas meddelandena med följande felmeddelande:

  > 450 4.7.26 Tjänsten är inte tillgänglig, meddelande som skickas via IPv6 [2a01:111:f200:2004::240] måste överföra antingen SPF- eller DKIM-validering.

- Om du försöker ta emot anonyma IPv6-meddelanden innan du har valt att delta avvisas meddelandet med följande felmeddelande:

  > 550 5.2.1 Tjänsten är inte tillgänglig, [contoso.com] accepterar inte e-post över IPv6.

## <a name="related-topics"></a>Relaterade ämnen

[Stöd för validering av DKIM-signerade meddelanden](support-for-validation-of-dkim-signed-messages.md)
