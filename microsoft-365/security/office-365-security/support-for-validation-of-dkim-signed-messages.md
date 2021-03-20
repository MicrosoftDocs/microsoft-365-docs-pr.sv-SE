---
title: Stöd för validering av DKIM-signerade e-postmeddelanden (Domain Keys Identified Mail)
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: Läs mer om validering av DKIM-signerade meddelanden i Exchange Online Protection och Exchange Online
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 111bf169d60e386dc48ef086bbe631b8760201a6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916532"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>Stöd för validering av DKIM-signerade meddelanden

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Både Exchange Online Protection (EOP) och Exchange Online har stöd för inkommande validering av[DKIM-meddelanden](https://www.rfc-editor.org/rfc/rfc6376.txt)(Domain Keys Identified Mail).

DKIM verifierar att ett e-postmeddelande inte *kapats* av någon annan och skickades från den domän som det står *att* det kommer från. Det binder ett e-postmeddelande till organisationen som har skickat det. DKIM-verifiering används automatiskt för alla meddelanden som skickas med IPv6. Microsoft 365 stöder även DKIM när e-post skickas över IPv4. (Mer information om stöd för IPv6 finns i [Stöd för anonyma inkommande e-postmeddelanden över IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)

DKIM verifierar ett digitalt signerat meddelande som visas DKIM-Signature i meddelanderubriken. Resultatet av en DKIM-Signature stämplas i Authentication-Results rubrik. Texten i meddelanderubriken liknar följande (contoso.com är avsändaren):

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> Mer information om rubriken Authentication-Results i RFC 7001 (fältet Meddelanderubrik för[att visa autentiseringsstatus för meddelande.](https://www.rfc-editor.org/rfc/rfc7001.txt) Microsofts DKIM-implementering överensstämmer med denna RFC.

Administratörer kan skapa [e-postflödesregler i](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) Exchange (kallas även transportregler) på resultatet av DKIM-verifiering. Med de här e-postflödesreglerna kan administratörer filtrera eller dirigera meddelanden efter behov.