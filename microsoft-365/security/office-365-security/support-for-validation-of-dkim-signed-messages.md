---
title: Stöd för validering av domän nycklar identifieras e-postmeddelanden (DKIM) signerade meddelanden
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: Lär dig mer om validering av DKIM-signerade meddelanden i Exchange Online Protection och Exchange Online
ms.openlocfilehash: 91a01f89bb633a38d27ddd3f2945b8707643d7e9
ms.sourcegitcommit: 89097fb648987567b9493b9d94c85c5990562874
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49845065"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>Stöd för validering av DKIM-signerade meddelanden

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Exchange Online Protection (EOP) och Exchange Online båda stöder inkommande verifiering av domän nycklar identifieras e-postmeddelanden ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)).

DKIM verifierar att ett e-postmeddelande inte är *falsk* för någon annan och att det har skickats från den domän det *står* från. Den bevarar ett e-postmeddelande till organisationen som skickade det. DKIM-verifiering används automatiskt för alla meddelanden som skickas med IPv6. Microsoft 365 har också stöd för DKIM när e-post skickas via IPv4. (Mer information om IPv6-support finns i [stöd för anonyma inkommande e-postmeddelanden över IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)

DKIM verifierar ett digitalt signerat meddelande som visas i meddelande rubrikernas DKIM-Signature rubrik. Resultatet av en DKIM-Signature validering är stämplat i Authentication-Results huvudet. Meddelandets rubrik text ser ut ungefär så här (där contoso.com är avsändaren):

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> Mer information om Authentication-Results rubrik finns i RFC 7001 ([meddelande fältet för att ange meddelandets status](https://www.rfc-editor.org/rfc/rfc7001.txt). Microsofts DKIM-implementering följer med RFC.

Administratörer kan skapa regler för Exchange [-flöden](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (kallas även transport regler) på resultaten av DKIM-verifiering. Dessa regler för e-postflöden gör att administratörer kan filtrera eller dirigera meddelanden efter behov.
