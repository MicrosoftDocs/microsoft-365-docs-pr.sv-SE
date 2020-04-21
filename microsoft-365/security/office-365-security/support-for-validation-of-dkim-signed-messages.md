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
description: Läs mer om valideringen av DKIM-signerade meddelanden i Exchange Online Protection och Exchange Online
ms.openlocfilehash: 1abe517ed7922b60abb3a78436ed61b4d0b3ed55
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631211"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>Stöd för validering av DKIM-signerade meddelanden

Exchange Online Protection (EOP) och Exchange Online stöder inkommande validering av[DKIM-meddelanden](https://www.rfc-editor.org/rfc/rfc6376.txt)(Domain Keys Identified Mail). DKIM är en metod för att validera att ett meddelande skickades från domänen det står att det kommer från och att det inte var förfalskad av någon annan. Det binder ett e-postmeddelande till den organisation som ansvarar för att skicka det. DKIM-verifiering används automatiskt för alla meddelanden som skickas via IPv6-kommunikation. Microsoft 365 stöder nu också DKIM när e-post skickas via IPv4. (Mer information om IPv6-stöd finns [i Stöd för anonyma inkommande e-postmeddelanden via IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)

DKIM validerar ett digitalt signerat meddelande som visas i DKIM-signature-huvudet i meddelanderubrikerna. Resultatet av en DKIM-signaturvalidering stämplas i autentiseringsresultathuvudet som överensstämmer med RFC 7001 ([Meddelandehuvudfältet för ange meddelandeautentiseringsstatus](https://www.rfc-editor.org/rfc/rfc7001.txt)). Meddelanderubriktexten liknar följande (där contoso.com är avsändare):

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

Administratörer kan skapa [Exchange-regler för e-postflöde](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (kallas även transportregler) om resultatet av en DKIM-validering för att filtrera eller dirigera meddelanden efter behov.
