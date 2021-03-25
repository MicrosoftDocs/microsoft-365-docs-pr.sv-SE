---
title: E-postflöde i EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: Administratören kan läsa mer om alternativen för att konfigurera e-postflöde och e-postdirigering i Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7cd5bfcc95227c59f645422d4939ea6ff77bee1e
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207309"
---
# <a name="mail-flow-in-eop"></a>E-postflöde i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

I Microsoft 365-organisationer med Exchange Online-postlådor eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor passerar alla meddelanden som skickas till din organisation via EOP innan de anställda ser dem. Du har alternativ för hur du dirigerar meddelanden som passerar genom EOP för bearbetning innan de dirigeras till dina anställdas inkorgar.

## <a name="working-with-messages-and-message-access-options"></a>Arbeta med alternativ för meddelanden och meddelandeåtkomst

EOP ger flexibilitet i hur dina meddelanden dirigeras. I följande avsnitt förklaras stegen i e-postflödet.

[Använda katalogbaserad Edge-blockering för att avvisa meddelanden som skickas till ogiltiga mottagare](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Här beskrivs den katalogbaserade gränsblockeringsfunktionen som gör att du kan avvisa meddelanden till ogiltiga mottagare på tjänstens nätverks perimeter.

[I Visa eller Redigera hanterade domäner i EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) beskrivs hur du hanterar domäner som är kopplade till EOP-tjänsten.

Om du lägger till underdomäner i organisationen kan EOP-tjänsten hjälpa dig att hantera även dessa. Läs mer om underdomäner i [Aktivera e-postflöde för underdomäner i Exchange Online.](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)

[Genom att konfigurera e-postflödet med kopplingar](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduceras kopplingar och du ser hur du kan använda dem för att anpassa e-postdirigeringen. Scenarierna omfattar att säkerställa säker kommunikation med en partnerorganisation och konfigurera en smart värd.

[Förbättrad filtrering för kopplingar beskriver](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) hur du konfigurerar kopplingar om din e-post dirigeras till en tjänst eller enhet före EOP.

I fristående EOP-organisationer måste du utföra ett par konfigurationssteg för att se till att skräppost dirigeras korrekt till varje användares skräppostmapp. Mer information finns i [Konfigurera fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer.](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) Om du inte vill flytta meddelanden till varje användares skräppostmapp kan du välja en annan åtgärd genom att redigera principerna för skydd mot skräppost (kallas även principer för innehållsfilter). Mer information finns i [Konfigurera principer för skräppostskydd](configure-your-spam-filter-policies.md).

## <a name="verify-mail-flow"></a>Kontrollera e-postflödet

Kontrollera att EOP-konfigurationen, inklusive anslutningskonfigurationen, fungerar som den ska genom att gå till "Hur vet du att uppgiften fungerade?" i Konfigurera [EOP-tjänsten](set-up-your-eop-service.md).

[Testa e-postflödet genom att verifiera dina Microsoft 365-kopplingar](/exchange/mail-flow-best-practices/test-mail-flow) ger instruktioner för att testa att e-postflödet är korrekt inställt.