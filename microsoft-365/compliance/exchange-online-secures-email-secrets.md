---
title: Så säkrar Exchange Online dina e-posthemligheter
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2019
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
ms.collection:
- M365-security-compliance
description: Förutom säkerhetscentret i Office 365 som tillhandahåller information om säkerhet, sekretess och efterlevnad för Microsoft 365 kan det vara bra att veta hur Microsoft skyddar hemligheterna som du lagrar i dess datacenter. Vi använder en teknik som kallas DKM (Distributed Key Manager).
ms.openlocfilehash: 2f6e51b7fe9cd75cbd265c3135050a08130f34d8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161935"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a>Så säkrar Exchange Online dina e-posthemligheter

I den här artikeln beskrivs hur Microsoft skyddar dina e-posthemligheter i sina datacenter.
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a>Hur skyddar vi hemlig information som tillhandahålls av dig?

Förutom säkerhetscentret i Office 365 som tillhandahåller information om [säkerhet,](./get-started-with-service-trust-portal.md)sekretess och efterlevnad för Office 365 vill du kanske veta hur Microsoft hjälper till att skydda de hemligheter som du ger i sina datacenter. Vi använder en teknik som kallas DKM (Distributed Key Manager).
  
[DKM (Distributed Key Manager)](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) är en klientfunktion som använder en uppsättning hemliga nycklar för att kryptera och dekryptera information. Endast medlemmar i en viss säkerhetsgrupp i Active Directory Domain Services kan komma åt dessa nycklar för att dekryptera data som krypteras med DKM. I Exchange Online är endast vissa tjänstkonton där Exchange-processerna körs en del av den säkerhetsgruppen. Som en del av standardoperativsystemet i datacentret får ingen användare autentiseringsuppgifter som ingår i den här säkerhetsgruppen och därför har ingen person tillgång till de nycklar som kan dekryptera dessa hemligheter.
  
För felsökning, felsökning eller granskning måste en datacenteradministratör begära utökad åtkomst för att få tillfälliga autentiseringsuppgifter som ingår i säkerhetsgruppen. För den här processen krävs flera nivåer av juridiskt godkännande. Om åtkomst beviljas loggas alla aktiviteter och granskas. Dessutom beviljas åtkomst endast för ett tidsintervall efter vilket den automatiskt förfaller.
  
För extra skydd inkluderar DKM-tekniken automatiserad nyckelrullning och arkivering. Det här säkerställer också att du kan fortsätta att komma åt ditt äldre innehåll utan att behöva förlita dig på samma nyckel ett obestämt säkert sätt.
  
## <a name="where-does-exchange-online-make-use-of-dkm"></a>Var använder Exchange Online av DKM?

Microsoft använder [Distributed Key Manager för](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) att kryptera dina hemligheter Exchange Online datacenter. Till exempel:
  
- Autentiseringsuppgifter för e-postkonto för anslutna konton. Anslutna konton är konton från tredje part, till exempel Hotmail, Gmail och Yahoo! e-postkonton.

- Kundnyckel. Om du använder [Tjänstkryptering med Kundnyckel](customer-key-overview.md)använder du [Azure-nyckelvalvet för](/azure/key-vault/key-vault-whatis) att skydda dina hemligheter.

## <a name="related-topics"></a>Relaterade ämnen

[Kryptering i Office 365](encryption.md)
  
[Teknisk referensinformation om kryptering](technical-reference-details-about-encryption.md)
  
[Tjänstgranskning i &amp; Säkerhetsefterlevnadscenter](./service-assurance.md)
