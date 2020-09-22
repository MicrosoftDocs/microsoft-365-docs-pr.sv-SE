---
title: Stöd för validering av DKIM-signerade meddelanden
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
ms.openlocfilehash: e2e91fe426348487fa4dfa8ef929d2d8129ffddc
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202143"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>Stöd för validering av DKIM-signerade meddelanden

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange Online Protection (EOP) och Exchange Online-Support för inkommande verifiering av domän nycklar identifieras e-postmeddelanden ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)). DKIM är en metod för att verifiera att ett meddelande har skickats från den domän som det står från och att det inte har manipulerats av någon annan. Det besvarar ett e-postmeddelande till den organisation som är ansvarig för att skicka det. DKIM-verifiering används automatiskt för alla meddelanden som skickas via IPv6-kommunikation. Microsoft 365 stöder nu DKIM när e-post skickas via IPv4. (Mer information om IPv6-support finns i [stöd för anonyma inkommande e-postmeddelanden över IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)

DKIM verifierar ett digitalt signerat meddelande som visas i DKIM rubrik i meddelande huvudet. Resultatet av en verifiering med DKIM är stämplat i det verifierings resultat huvud som följer med RFC 7001 ([meddelande huvudet för att ange meddelande verifierings status](https://www.rfc-editor.org/rfc/rfc7001.txt)). Meddelandets rubrik text ser ut ungefär så här (där contoso.com är avsändaren):

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

Administratörer kan skapa regler för Exchange [-flöden](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (kallas även transport regler) för resultaten av en DKIM-verifiering för att filtrera eller dirigera meddelanden efter behov.
