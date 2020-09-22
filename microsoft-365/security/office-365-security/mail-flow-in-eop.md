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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa om alternativen för att konfigurera e-postflöde och routning i Exchange Online Protection (EOP).
ms.openlocfilehash: e1c821e3de8dd7dd18c192522bd18fd32a395dca
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200709"
---
# <a name="mail-flow-in-eop"></a>E-postflöde i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


I Microsoft 365-organisationer med Exchange Online-postlådor eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor kan alla meddelanden som skickas till organisationen passera genom EOP innan dina anställda ser dem. Du har alternativ för att dirigera meddelanden som passerar genom EOP för bearbetning innan de cirkuleras till dina anställdas inkorgar.

## <a name="working-with-messages-and-message-access-options"></a>Arbeta med meddelanden och alternativ för meddelande åtkomst

EOP erbjuder flexibilitet i hur dina meddelanden routas. I följande avsnitt förklaras anvisningar i e-postflöde.

[Använda katalogbaserade Edge-spärr för att avvisa meddelanden som skickats till ogiltiga mottagare](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Beskriver den mappbaserade Edge blockera-funktionen som låter dig avvisa meddelanden för ogiltiga mottagare i tjänst nätverkets perimeter.

[Visa eller redigera hanterade domäner i EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) beskriver hur du hanterar domäner som är kopplade till din EOP-tjänst.

Om du lägger till under domäner i din organisation kan EOP-tjänsten hjälpa dig hantera dem också. Läs mer om under domäner i [Aktivera e-postflöde för under domäner i Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).

[Konfigurera e-postflöde med kopplingar](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introducerar kontakter och visar hur du kan använda dem för att anpassa e-postdirigering. Scenarion inkluderar säker kommunikation med en partner organisation och att konfigurera en smart värd.

[Förbättrad filtrering för kopplingar](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) beskriver hur du konfigurerar anslutningar om din e-post dirigeras till en tjänst eller enhet innan EOP.

I fristående EOP-organisationer måste du utföra ett par konfigurations steg för att säkerställa att skräp post dirigeras korrekt till varje användares skräppost-e-postmapp. Dessa beskrivs i [Konfigurera fristående EOP för att skicka skräp post till skräppostmappen i hybrid miljöer](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). Om du inte vill flytta meddelanden till varje användares skräppost-mapp kan du välja en annan åtgärd genom att redigera principer för skräp post (kallas även för innehålls filter principer). Mer information finns i [Konfigurera principer för skräppostskydd](configure-your-spam-filter-policies.md).

## <a name="verify-mail-flow"></a>Bekräfta e-postflöde

Om du vill kontrol lera att EOP-konfigurationen, inklusive din anslutnings konfiguration, fungerar som den ska, kan du läsa avsnittet "Hur vet du att den här uppgiften fungerade?" avsnitt i [Konfigurera din EOP-tjänst](set-up-your-eop-service.md).

[Testa e-postflöde genom att verifiera dina Microsoft 365-kopplingar](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) finns anvisningar för testning av att ditt e-postflöde är korrekt konfigurerat.
