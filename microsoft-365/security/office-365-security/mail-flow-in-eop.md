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
description: Som eop-kund (Exchange Online Protection) passerar alla meddelanden som skickas till din organisation EOP innan dina anställda ser dem. Oavsett om du är värd för alla dina postlådor i molnet med Exchange Online, eller om du är värd för postlådorna lokalt (kallat ett fristående scenario), kanske för att fortsätta att dra nytta av din befintliga infrastruktur, har du alternativ för hur du dirigerar meddelanden som kommer att passera genom EOP för bearbetning innan de dirigeras till din arbetare inkorgar.
ms.openlocfilehash: dfd4457dcdd036798add5ad9611c3246db22d018
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42806797"
---
# <a name="mail-flow-in-eop"></a>E-postflöde i EOP

Som eop-kund (Exchange Online Protection) passerar alla meddelanden som skickas till din organisation EOP innan dina anställda ser dem. Oavsett om du är värd för alla dina postlådor i molnet med Exchange Online, eller om du är värd för postlådorna lokalt (kallat ett fristående scenario), kanske för att fortsätta att dra nytta av din befintliga infrastruktur, har du alternativ för hur du dirigerar meddelanden som kommer att passera genom EOP för bearbetning innan de dirigeras till din arbetare inkorgar.

Du kanske vill konfigurera anpassad e-postroutning så att de överensstämmer med ett affärskrav. Du kan till exempel skicka all utgående e-post via en principfiltreringsapparat.

## <a name="working-with-messages-and-message-access-options"></a>Arbeta med meddelanden och alternativ för meddelandeåtkomst

EOP erbjuder stor flexibilitet i hur dina meddelanden dirigeras. I följande avsnitt förklaras stegen i e-postflödesprocessen.

[Använda katalogbaserad kantblockering för att avvisa meddelanden som skickas till ogiltiga mottagare](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) I artikeln beskrivs funktionen katalogbaserad kantblockering som gör att du kan avvisa meddelanden för ogiltiga mottagare vid servicenätverksperimetern.

[Visa eller redigera hanterade domäner i EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) beskriver hur du hanterar domäner som är associerade med eOP-tjänsten.

Om du lägger till underdomäner i din organisation kan eop-tjänsten hjälpa dig att hantera dessa också. Läs mer om underdomäner på [Aktivera e-postflöde för underdomäner i Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).

[Konfigurera e-postflöde med hjälp av kopplingar i Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introducerar kopplingar och visar hur du kan använda dem för att anpassa e-postroutningen. Scenarier inkluderar att säkerställa säker kommunikation med en partnerorganisation och ställa in en smart värd.

För att säkerställa att skräppost dirigeras korrekt till varje användares skräppostmapp måste du utföra ett par konfigurationssteg. Dessa beskrivs i [Se till att spam dirigeras till varje användares skräppostmapp](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). Om du inte vill flytta meddelanden till varje användares skräppostmapp kan du välja en annan åtgärd genom att redigera innehållsfilterprinciperna i administrationscentret för Exchange. Mer information finns i [Konfigurera principer för skräppostfilter](configure-your-spam-filter-policies.md).

## <a name="verify-mail-flow"></a>Verifiera e-postflödet

Information om att EOP-konfigurationen, inklusive anslutningskonfigurationen, fungerar korrekt läser du "Hur vet du att den här uppgiften fungerade?" i [Konfigurera eop-tjänsten](set-up-your-eop-service.md).

[Testa e-postflödet genom att validera dina Office 365-anslutningar](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) innehåller instruktioner för att testa att ditt e-postflöde är korrekt konfigurerat.
