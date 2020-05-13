---
title: E-postflöde i EOP
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
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: Administratören kan lära sig mer om alternativen för att konfigurera e-postflöde och routning i Exchange Online Protection (EOP).
ms.openlocfilehash: cb2ae7370d50fe32802ad5c279cc2170eb35f581
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208336"
---
# <a name="mail-flow-in-eop"></a>E-postflöde i EOP

I Microsoft 365-organisationer med Exchange Online-postlådor eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor passerar alla meddelanden som skickas till din organisation EOP innan dina arbetare ser dem. Du har alternativ för hur du dirigerar meddelanden som passerar via EOP för bearbetning innan de dirigeras till dina arbetskorgar.

## <a name="working-with-messages-and-message-access-options"></a>Arbeta med meddelanden och alternativ för meddelandeåtkomst

EOP erbjuder flexibilitet i hur dina meddelanden dirigeras. I följande avsnitt beskrivs steg i e-postflödesprocessen.

[Använda katalogbaserad kantblockering för att avvisa meddelanden som skickas till ogiltiga mottagare](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) I artikeln beskrivs funktionen Directory Based Edge Blocking som gör att du kan avvisa meddelanden för ogiltiga mottagare vid tjänstnätverkets omkrets.

[Visa eller redigera hanterade domäner i EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) beskriver hur du hanterar domäner som är associerade med din EOP-tjänst.

Om du lägger till underdomäner i din organisation kan din EOP-tjänst hjälpa dig att hantera dessa också. Läs mer om underdomäner på [Aktivera e-postflöde för underdomäner i Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).

[Konfigurera e-postflöde med kopplingar](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introducerar kopplingar och visar hur du kan använda dem för att anpassa e-postroutning. Scenarier inkluderar att säkerställa säker kommunikation med en partnerorganisation och konfigurera en smart värd.

[Förbättrad filtrering för anslutningsappar](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) beskriver hur du konfigurerar kopplingar om din e-post dirigeras till en tjänst eller enhet före EOP.

I fristående EOP-organisationer måste du utföra ett par konfigurationssteg för att säkerställa att skräppost dirigeras korrekt till varje användares skräppostmapp. Dessa beskrivs i [Konfigurera fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). Om du inte vill flytta meddelanden till varje användares skräppostmapp kan du välja en annan åtgärd genom att redigera dina policyer mot skräppost (kallas även principer för innehållsfilter). Mer information finns i [Konfigurera principer för skräppostskydd](configure-your-spam-filter-policies.md).

## <a name="verify-mail-flow"></a>Verifiera e-postflöde

Om du vill kontrollera att eop-konfigurationen, inklusive anslutningskonfigurationen, fungerar korrekt läser du "Hur vet du att den här uppgiften fungerade?" i [Konfigurera din EOP-tjänst](set-up-your-eop-service.md).

[Testa e-postflödet genom att validera dina Microsoft 365-kontakter](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) innehåller instruktioner för hur du testar att e-postflödet är korrekt konfigurerat.
