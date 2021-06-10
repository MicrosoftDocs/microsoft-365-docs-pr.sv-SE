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
description: Lär dig hur leveranspoolerna används för att skydda ryktet för e-postservrar i Microsoft 365 datacenter.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ac3469150ef5cf5c1040fcddf7f0bc95e7a18805
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599917"
---
# <a name="outbound-delivery-pools"></a>Pooler för utgående leverans

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

E-postservrar i Microsoft 365 datacenter kan tillfälligt bli av med att skicka skräppost. Till exempel en skadlig programvara eller skadlig skräppost-attack i en lokal e-postorganisation som skickar utgående e-post via Microsoft 365 eller komprometterat Microsoft 365 konton. Attacker försöker också undvika identifiering genom att vidarebefordra meddelanden via Microsoft 365 vidarebefordran.

De här scenarierna kan resultera i IP-adressen för Microsoft 365 datacenterservrar som visas på blockeringslistor från tredje part. Mål-e-postorganisationer som använder dessa blockeringslistor avvisar e-post från dessa meddelandekällor.

## <a name="high-risk-delivery-pool"></a>Högriskleveranspool
För att förhindra detta skickas alla utgående meddelanden från Microsoft 365 datacenterservrar som fastställt vara [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) skräppost [](configure-the-outbound-spam-policy.md) eller som överskrider gränserna för att skicka ut tjänster eller utgående skräppost via _högriskleveranspoolen._

Högriskleveranspoolen är en separat IP-adresspool för utgående e-post som bara används för att skicka meddelanden av "låg kvalitet" (till exempel skräppost [och bakåtcatter).](backscatter-messages-and-eop.md) Användning av högriskleveranspoolen förhindrar att den vanliga IP-adresspoolen för utgående e-post skickas som skräppost. Den normala IP-adresspoolen för utgående e-post behåller det rykte som skickar meddelanden av "hög kvalitet", vilket minskar sannolikheten att denna IP-adress visas på IP-blockeringslistor.

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
