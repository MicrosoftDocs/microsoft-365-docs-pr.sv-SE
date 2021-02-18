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
description: Lär dig hur leveranspooler används för att skydda ryktet för e-postservrar i Microsoft 365-datacenter.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 89aac1478d3e5840df4379b9f49832b79d0e133a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289811"
---
# <a name="outbound-delivery-pools"></a>Pooler för utgående leverans

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

E-postservrar i Microsoft 365-datacenter kan tillfälligt skickas skräppost. Till exempel skadlig kod eller skadlig skräppost-attack i en lokal e-postorganisation som skickar utgående e-post via Microsoft 365 eller komprometterat Microsoft 365-konton. Attacker försöker också undvika identifiering genom att vidarebefordra meddelanden via Microsoft 365-vidarebefordran.

De här scenarierna kan resultera i IP-adressen för de påverkade Microsoft 365-datacenterservrarna som visas på blockeringslistor från tredje part. De mål-e-postorganisationer som använder de här blockeringslistorna avvisar e-post från dessa meddelandekällor.

## <a name="high-risk-delivery-pool"></a>Högriskleveranspool
För att förhindra detta skickas alla utgående meddelanden från Microsoft 365-datacenterservrar som fastställt [](configure-the-outbound-spam-policy.md) vara skräppost eller som överskrider avsändargränserna för tjänsten eller principer för utgående skräppost via högriskleveranspoolen. [](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)

Högriskleveranspoolen är en separat IP-adresspool för utgående e-post som bara används för att skicka meddelanden av "låg kvalitet" (till exempel skräppost [och bakåtcatter).](backscatter-messages-and-eop.md) Genom att använda högriskleveranspoolen förhindrar du att den vanliga IP-adresspoolen för utgående e-post skickar skräppost. Den normala IP-adresspoolen för utgående e-post upprätthåller det rykte som skickar meddelanden av "hög kvalitet", vilket minskar sannolikheten för att denna IP-adress visas på blockeringslistor för IP.

Den verkliga risken att IP-adresser i högriskleveranspoolen placeras i listor över IP-blockeringar finns kvar, men detta är enligt design. Leverans till de avsedda mottagarna kan inte garanteras, eftersom många e-postorganisationer inte tar emot meddelanden från högriskleveranspoolen.

Mer information finns i [Kontrollera utgående skräppost.](outbound-spam-controls.md)

> [!NOTE]
> Meddelanden där käll-e-postdomänen inte har någon A-post och ingen MX-post som definierats i offentlig DNS dirigeras alltid genom högriskleveranspoolen, oavsett hur många som är skräppost eller hur många som skickas.

### <a name="bounce-messages"></a>Studsa meddelanden

Den utgående högriskleveranspoolen hanterar leveransen för alla rapporter om utebliven leverans (kallas även NDR-rapporter, icke-leveranskaviseringar, leveransstatusmeddelanden och DSN).

Möjliga orsaker till en ökning av NDR-inkluderar:

- En förfalskningskampanj som påverkar en av de kunder som använder tjänsten.
- En katalogd till exempel en skördeattack.
- En skräppostattack.
- En falsk e-postserver.

Alla dessa problem kan resultera i en plötsligt ökning av antalet NDR-resultat som bearbetas av tjänsten. Ofta verkar dessa NDR-meddelanden vara skräppost till andra e-postservrar och -tjänster (kallas _[även bakåtcatter).](backscatter-messages-and-eop.md)_

## <a name="relay-pool"></a>Reläpool

Meddelanden som vidarebefordras eller vidarebefordras från Microsoft 365 skickas med en särskild reläpool, eftersom Microsoft 365 inte bör vara den faktiska avsändaren vid slutdestinationen. Det är också viktigt att isolera den här trafiken eftersom det finns legitima och ogiltiga scenarier för automatisk vidarebefordran eller e-postutskick från Microsoft 365. På ungefär samma sätt som högriskleveranspoolen används en separat IP-adresspool för vidarebefordrad e-post. Den här adresspoolen publiceras inte eftersom den kan ändras ofta.

Microsoft 365 behöver verifiera att den ursprungliga avsändaren är legitim så att vi kan leverera det vidarebefordrade meddelandet med säkerhet. För att kunna göra det måste e-postautentisering (SPF, DKIM och DMARC) passera när meddelandet kommer till oss. I fall där vi kan autentisera avsändaren använder vi Sender Rewriting för att hjälpa mottagaren att veta att det vidarebefordrade meddelandet kommer från en betrodd källa. Du kan läsa mer om hur det fungerar och vad du kan göra för att se till att avsändardomänen skickar autentisering i [Sender Rewriting Scheme (SRS)](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme).
