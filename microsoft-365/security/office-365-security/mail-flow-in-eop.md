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
description: I den här artikeln kan EOP-kunder (Exchange Online Protection) lära sig mer om hur du konfigurerar anpassad e-postroutning som kan uppfylla deras affärskrav.
ms.openlocfilehash: cdc919c628f2254ffc971678f7887c37786d2528
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034238"
---
# <a name="mail-flow-in-eop"></a>E-postflöde i EOP

Som en Exchange Online Protection (EOP) kund, alla meddelanden som skickas till din organisation passerar via EOP innan dina anställda se dem. Oavsett om du är värd för alla dina postlådor i molnet med Exchange Online, eller om du är värd för dina postlådor lokalt (ett så kallat fristående scenario), kanske för att fortsätta dra nytta av din befintliga infrastruktur, har du alternativ för hur du dirigerar meddelanden som kommer att passera via EOP för bearbetning innan de dirigeras till dina arbetsinkorgar.

Du kanske vill konfigurera anpassad e-postroutning så att den överensstämmer med dina meddelanden enligt ett affärskrav. Du kan till exempel skicka all utgående e-post via en principfiltreringsapparat.

## <a name="working-with-messages-and-message-access-options"></a>Arbeta med meddelanden och alternativ för meddelandeåtkomst

EOP erbjuder stor flexibilitet i hur dina meddelanden dirigeras. I följande avsnitt beskrivs steg i e-postflödesprocessen.

[Använda katalogbaserad kantblockering för att avvisa meddelanden som skickas till ogiltiga mottagare](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) I artikeln beskrivs funktionen Directory Based Edge Blocking som gör att du kan avvisa meddelanden för ogiltiga mottagare vid tjänstnätverkets omkrets.

[Visa eller redigera hanterade domäner i EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) beskriver hur du hanterar domäner som är associerade med din EOP-tjänst.

Om du lägger till underdomäner i din organisation kan din EOP-tjänst hjälpa dig att hantera dessa också. Läs mer om underdomäner på [Aktivera e-postflöde för underdomäner i Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).

[Konfigurera e-postflöde med kopplingar i Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introducerar kopplingar och visar hur du kan använda dem för att anpassa e-postroutning. Scenarier inkluderar att säkerställa säker kommunikation med en partnerorganisation och konfigurera en smart värd.

Om du vill vara säkra på att skräppost dirigeras korrekt till varje användares skräppostmapp måste du utföra ett par konfigurationssteg. Dessa beskrivs i [Konfigurera fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). Om du inte vill flytta meddelanden till varje användares skräppostmapp kan du välja en annan åtgärd genom att redigera innehållsfilterprinciperna i administrationscentret för Exchange. Mer information finns i [Konfigurera principer för skräppostskydd](configure-your-spam-filter-policies.md).

## <a name="verify-mail-flow"></a>Verifiera e-postflöde

Om du vill kontrollera att eop-konfigurationen, inklusive anslutningskonfigurationen, fungerar korrekt läser du "Hur vet du att den här uppgiften fungerade?" i [Konfigurera din EOP-tjänst](set-up-your-eop-service.md).

[Testa e-postflödet genom att validera dina Microsoft 365-kontakter](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) innehåller instruktioner för hur du testar att e-postflödet är korrekt konfigurerat.
