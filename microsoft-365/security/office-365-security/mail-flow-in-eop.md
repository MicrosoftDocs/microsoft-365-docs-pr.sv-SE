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
ms.openlocfilehash: c988f58a04abf2322e993ae1b75106a338674acb
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289657"
---
# <a name="mail-flow-in-eop"></a>E-postflöde i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

I Microsoft 365-organisationer med Exchange Online-postlådor eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor passerar alla meddelanden till organisationen via EOP innan dina medarbetare ser dem. Du har alternativ för hur du dirigerar meddelanden som passerar genom EOP för bearbetning innan de dirigeras till dina inkorgar för anställda.

## <a name="working-with-messages-and-message-access-options"></a>Arbeta med alternativ för meddelande- och meddelandeåtkomst

EOP ger flexibilitet i hur meddelanden dirigeras. I följande avsnitt förklaras stegen i e-postflödesprocessen.

[Använda katalogbaserad Edge-blockering för att avvisa meddelanden som skickas till ogiltiga mottagare](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Här beskrivs den katalogbaserade edge-blockeringsfunktionen som gör att du kan avvisa meddelanden till ogiltiga mottagare på tjänstens nätverks perimeter.

[Visa eller redigera hanterade domäner i EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) beskriver hur du hanterar domäner som är kopplade till din EOP-tjänst.

Om du lägger till underdomäner i organisationen kan EOP-tjänsten hjälpa dig att hantera även dessa. Läs mer om underdomäner i Aktivera [e-postflöde för underdomäner i Exchange Online.](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)

[Genom att konfigurera e-postflöde med kopplingar](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduceras kopplingar och du ser hur du kan använda dem för att anpassa e-postdirigeringen. Scenarierna omfattar att säkerställa säker kommunikation med en partnerorganisation och konfigurera en smart värd.

[Förbättrad filtrering för kopplingar beskriver](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) hur du konfigurerar kopplingar om din e-post dirigeras till en tjänst eller enhet före EOP.

I fristående EOP-organisationer måste du utföra ett par konfigurationssteg för att säkerställa att skräppost dirigeras korrekt till varje användares skräppostmapp. Mer information finns i [Konfigurera fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer.](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) Om du inte vill flytta meddelanden till varje användares skräppostmapp kan du välja en annan åtgärd genom att redigera principerna för skydd mot skräppost (kallas även principer för innehållsfilter). Mer information finns i [Konfigurera principer för skräppostskydd](configure-your-spam-filter-policies.md).

## <a name="verify-mail-flow"></a>Kontrollera e-postflödet

Kontrollera att EOP-konfigurationen, inklusive din kopplingskonfiguration, fungerar som den ska genom att gå till "Hur vet du att uppgiften fungerade?" i Konfigurera [EOP-tjänsten.](set-up-your-eop-service.md)

[Testa e-postflödet genom att verifiera Dina Microsoft 365-kopplingar](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) ger instruktioner för att testa att e-postflödet är korrekt inställt.
