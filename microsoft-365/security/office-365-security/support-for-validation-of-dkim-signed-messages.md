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
description: Läs mer om valideringav DKIM-signerade meddelanden i Exchange Online Protection and Exchange Online
ms.openlocfilehash: 1dc160a4aa01a1a1e46a9b31bb09206d4b385d68
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42812608"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>Stöd för validering av DKIM-signerade meddelanden

EOP-meddelanden (Exchange Online Protection) och Exchange Online-stöd för inkommande validering av Meddelanden om identifierade e-postmeddelanden[(Domain](https://www.rfc-editor.org/rfc/rfc6376.txt)Keys Identified Mail). DKIM är en metod för att validera att ett meddelande skickades från domänen den säger att det härstammar från och att det inte var förfalskad av någon annan. Det binder ett e-postmeddelande till den organisation som ansvarar för att skicka det. DKIM-verifiering används automatiskt för alla meddelanden som skickas via IPv6-kommunikation. Office 365 stöder nu även DKIM när e-post skickas över IPv4. (Mer information om IPv6-support finns i [Support för anonyma inkommande e-postmeddelanden via IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)

DKIM validerar ett digitalt signerat meddelande som visas i DKIM-signaturhuvudet i meddelanderubrikerna. Resultaten av en DKIM-signaturvalidering stämplas i rubriken Autentiseringsresultat som överensstämmer med RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt)). Texten i meddelandehuvudet visas ungefär så här (där contoso.com är avsändaren):

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

Administratörer kan skapa [Exchange-regler för e-postflöde](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (kallas även transportregler) för resultaten av en DKIM-validering för att filtrera eller dirigera meddelanden efter behov.
