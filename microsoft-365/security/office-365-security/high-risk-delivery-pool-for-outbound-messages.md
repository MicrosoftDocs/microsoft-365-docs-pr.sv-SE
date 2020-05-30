---
title: Utgående leveranspooler
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Lär dig hur leveranspoolerna används för att skydda ryktet för e-postservrar i Microsoft 365-datacenter.
ms.openlocfilehash: 213149eda3dd121b65b64e3bddbb4bd73d66f57c
ms.sourcegitcommit: 6746fae2f68400fd985711b1945b66766d2a59a4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/29/2020
ms.locfileid: "44419166"
---
# <a name="outbound-delivery-pools"></a>Utgående leveranspooler

E-postservrar i Microsoft 365 datacenter kan vara tillfälligt skyldiga till att skicka skräppost. Till exempel en skadlig kod eller skadlig skräppostattack i en lokal e-postorganisation som skickar utgående e-post via Microsoft 365 eller komprometterade Microsoft 365-konton. Angripare försöker också undvika identifiering genom att vidarebefordra meddelanden via Microsoft 365-vidarebefordran.

Dessa scenarier kan resultera i IP-adressen för de berörda Microsoft 365 datacenterservrar som visas på tredje parts blocklistor. Mål e-postorganisationer som använder dessa blocklistor kommer att avvisa e-post från dessa meddelanden källor.

## <a name="high-risk-delivery-pool"></a>Leveranspool med hög risk
För att förhindra detta skickas alla utgående meddelanden från Microsoft 365 datacenterservrar som är fast beslutna att vara skräppost eller som överskrider sändningsgränserna för [tjänsten](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) eller [utgående skräppostpolicyer](configure-the-outbound-spam-policy.md) via _högriskleveranspoolen_.

Högriskleveranspoolen är en separat IP-adresspool för utgående e-post som endast används för att skicka meddelanden av "låg kvalitet" (till exempel skräppost och [backscatter).](backscatter-messages-and-eop.md) Med hjälp av hög risk leveranspoolen hjälper till att förhindra den normala IP-adresspoolen för utgående e-post från att skicka skräppost. Den normala IP-adresspoolen för utgående e-post upprätthåller ryktet att skicka "högkvalitativa" meddelanden, vilket minskar sannolikheten för att dessa IP-adresser visas på IP-blockeringslistor.

Den mycket verkliga möjligheten att IP-adresser i högriskleveranspoolen kommer att placeras på IP-blocklistor kvarstår, men detta är avsiktligt. Leverans till de avsedda mottagarna är inte garanterad, eftersom många e-postorganisationer inte accepterar meddelanden från högriskleveranspoolen.

Mer information finns i [Kontrollera utgående skräppost](outbound-spam-controls.md).

> [!NOTE]
> Meddelanden där källe-domänen inte har någon A-post och ingen MX-post som definieras i offentlig DNS dirigeras alltid genom högriskleveranspoolen, oavsett deras spam eller skicka gränsdisposition.

### <a name="bounce-messages"></a>Studsa meddelanden

Den utgående högriskleveranspoolen hanterar leveransen för alla rapporter som inte levereras (kallas även NDRs, avstudsmeddelanden, leveransstatusmeddelanden eller DSN-nätverk).

Möjliga orsaker till en ökning av NDR inkluderar:

- En förfalskningskampanj som påverkar en av kunderna som använder tjänsten.
- En katalog skörd attack.
- En spamattack.
- En oseriös e-postserver.

Alla dessa problem kan resultera i en plötslig ökning av antalet NDR som behandlas av tjänsten. Många gånger, dessa NDRs verkar vara spam till andra e-postservrar och tjänster (även känd som _[backscatter).](backscatter-messages-and-eop.md)_

## <a name="relay-pool"></a>Reläpool

Meddelanden som vidarebefordras eller vidarebefordras från Microsoft 365 skickas med en särskild reläpool, eftersom slutmålet inte bör betraktas som den faktiska avsändaren. Det är också viktigt för oss att isolera den här trafiken, eftersom det finns legitima och illegitmate scenarier för automatisk vidarebefordran eller vidarebefordra e-post från Microsoft 365. I likhet med högriskleveranspoolen används en separat IP-adresspool för vidarebefordrad e-post. Den här adresspoolen publiceras inte eftersom den kan ändras ofta. 

Microsoft 365 måste verifiera att den ursprungliga avsändaren är legitim så att vi tryggt kan leverera det vidarebefordrade meddelandet. För att göra det måste e-postautentisering (SPF, DKIM och DMARC) passera när meddelandet kommer till oss. I de fall där vi kan autentisera avsändaren använder vi Sender Rewriting för att hjälpa mottagaren att veta att det vidarebefordrade meddelandet kommer från en betrodd källa. Du kan läsa mer om hur det fungerar och vad du kan göra för att se till att den sändande domänen skickar autentisering i [SRS (Sender Rewriting Scheme).](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme)
