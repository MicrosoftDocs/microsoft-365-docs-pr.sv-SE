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
ms.openlocfilehash: 85f200cf226a050762db4ea37255f71241d1f98c
ms.sourcegitcommit: 410f6e1c6cf53c3d9013b89d6e0b40a050ee9cad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/25/2021
ms.locfileid: "53137733"
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


### <a name="relay-pool"></a>Reläpool

Meddelanden som vidarebefordras eller vidarebefordras via Microsoft 365 i vissa fall skickas med en särskild reläpool, eftersom målet inte bör överväga Microsoft 365 som den faktiska avsändaren. Det är viktigt att vi isolerar den här e-posttrafiken eftersom det finns legitima och ogiltiga scenarier för automatisk vidarebefordran eller vidarebefordra e-Microsoft 365. På ungefär samma sätt som högriskleveranspoolen används en separat IP-adresspool för vidarebefordrad e-post. Den här adresspoolen publiceras inte eftersom den kan ändras ofta, och den är inte en del av den publicerade SPF-posten för Microsoft 365.

Microsoft 365 att verifiera att den ursprungliga avsändaren är legitim så att vi kan leverera det vidarebefordrade meddelandet med tillförsikt.

Det vidarebefordrade/vidarebefordrade meddelandet bör uppfylla något av följande kriterier för att undvika att använda reläpoolen:

- Den utgående avsändaren finns i en [godkänd domän.](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)
- SPF passerar när meddelandet kommer till Microsoft 365.
- DKIM för avsändardomänen passeras när meddelandet kommer till Microsoft 365.
 
Du kan se att ett meddelande har skickats via reläpoolen genom att titta på den utgående server-IP:n (reläpoolen finns i intervallet 40.95.0.0/16), eller genom att titta på den utgående servernamnet (har "rly" i namnet).

I fall där vi kan autentisera avsändaren använder vi SRS (Sender Rewriting Scheme) för att hjälpa mottagarens e-postsystem att veta att det vidarebefordrade meddelandet kommer från en betrodd källa. Du kan läsa mer om hur det fungerar och vad du kan göra för att se till att sändningsdomänen skickar autentisering i [SRS (Sender Rewriting Scheme) i Office 365.](/office365/troubleshoot/antispam/sender-rewriting-scheme)

För att DKIM ska fungera måste du aktivera DKIM för att skicka domän. Till exempel fabrikam.com en del av contoso.com och definieras i organisationens godkända domäner. Om meddelandets avsändare är sender@fabrikam.com, måste DKIM aktiveras för fabrikam.com. du kan läsa om hur du aktiverar i [Use DKIM to validate outbound email sent from your custom domain](use-dkim-to-validate-outbound-email.md).

Om du vill lägga till en egen domän följer du stegen [i Lägga till en domän i Microsoft 365](../../admin/setup/add-domain.md).
