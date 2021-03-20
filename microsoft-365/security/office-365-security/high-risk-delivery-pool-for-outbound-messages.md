---
title: Pooler för utgående leverans
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Lär dig hur leveranspoolerna används för att skydda ryktet för e-postservrar i Microsoft 365-datacenter.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5b35474c4d2b00c70e02f6f0127c3191a1e459bc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910732"
---
# <a name="outbound-delivery-pools"></a>Pooler för utgående leverans

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

E-postservrar i Microsoft 365-datacenter kan tillfälligt bli av med att skicka skräppost. Till exempel skadlig programvara eller skadlig skräppost-attack i en lokal e-postorganisation som skickar utgående e-post via Microsoft 365 eller som har komprometterat Microsoft 365-konton. Attacker försöker också undvika identifiering genom att vidarebefordra meddelanden via Microsoft 365-vidarebefordran.

De här scenarierna kan resultera i att IP-adressen för de berörda Microsoft 365-datacenterservrarna visas på blockeringslistor från tredje part. De mål-e-postorganisationer som använder dessa blockeringslistor avvisar e-post från dessa meddelandekällor.

## <a name="high-risk-delivery-pool"></a>Högriskleveranspool
För att förhindra detta skickas alla utgående meddelanden från Microsoft 365-datacenterservrar som har [](configure-the-outbound-spam-policy.md) fastställt vara skräppost eller som överskrider begränsningsgränserna för sändning av tjänsten eller utgående skräppost via högriskleveranspoolen. [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)

Högriskleveranspoolen är en separat IP-adresspool för utgående e-post som bara används för att skicka meddelanden av "låg kvalitet" (till exempel skräppost [och bakåtcatter).](backscatter-messages-and-eop.md) Användning av högriskleveranspoolen förhindrar att den vanliga IP-adresspoolen för utgående e-post skickas som skräppost. Den normala IP-adresspoolen för utgående e-post behåller det rykte som skickar meddelanden av "hög kvalitet", vilket minskar sannolikheten att denna IP-adress visas i IP-blockeringslistor.

Den mycket stora risken att IP-adresser i högriskpoolen placeras i IP-blockeringslistor finns kvar, men detta är enligt design. Leverans till de avsedda mottagarna är inte garanterad, eftersom många e-postorganisationer inte tar emot meddelanden från högriskleveranspoolen.

Mer information finns i [Kontrollera utgående skräppost.](outbound-spam-controls.md)

> [!NOTE]
> Meddelanden där käll-e-postdomänen inte har någon A-post och ingen MX-post som definierats i offentlig DNS dirigeras alltid genom högriskleveranspoolen, oavsett deras disposition av skräppost eller sändningsgräns.

### <a name="bounce-messages"></a>Studsande meddelanden

Leveranspoolen för utgående högriskleverans hanterar leveransen för alla rapporter om utebliven leverans (kallas även NDR-rapporter, icke-leveranskaviseringar, leveransstatusmeddelanden och DSN-meddelanden).

Möjliga orsaker till en ökning av NDR-fel är:

- En förfalskningskampanj som påverkar en av kunderna som använder tjänsten.
- En katalogd till-skördeattack.
- En skräppostattack.
- En falsk e-postserver.

Alla dessa problem kan resultera i en plötsligt ökning av antalet NDR-resultat som bearbetas av tjänsten. Ofta verkar dessa NDR-meddelanden vara skräppost till andra e-postservrar och -tjänster (kallas även _[bakåtcatter).](backscatter-messages-and-eop.md)_

## <a name="relay-pool"></a>Reläpool

Meddelanden som vidarebefordras eller vidarebefordras från Microsoft 365 skickas med en särskild reläpool, eftersom Microsoft 365 inte bör vara den faktiska avsändaren vid den slutliga destinationen. Det är också viktigt att isolera den här trafiken, eftersom det finns legitima och ogiltiga scenarier för automatisk vidarebefordran eller vidarebefordra e-post från Microsoft 365. På ungefär samma sätt som högriskleveranspoolen används en separat IP-adresspool för vidarebefordrad e-post. Den här adresspoolen publiceras inte eftersom den kan ändras ofta.

Microsoft 365 behöver verifiera att den ursprungliga avsändaren är legitim så att vi kan tryggt leverera det vidarebefordrade meddelandet. För att kunna göra det måste e-postautentisering (SPF, DKIM och DMARC) passera när meddelandet kommer till oss. I fall där vi kan autentisera avsändaren använder vi sender rewriting för att hjälpa mottagaren att veta att det vidarebefordrade meddelandet kommer från en betrodd källa. Du kan läsa mer om hur det fungerar och vad du kan göra för att se till att den avsändande domänen skickar autentisering i [SRS (Sender Rewriting Scheme).](/office365/troubleshoot/antispam/sender-rewriting-scheme)