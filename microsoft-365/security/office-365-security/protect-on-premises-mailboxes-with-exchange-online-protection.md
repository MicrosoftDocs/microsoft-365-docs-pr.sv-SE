---
title: Skydda lokala postlådor i Kina med fristående EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- GEU150
- GMA150
- GPA150
- MET150
ms.assetid: c5e95951-da67-4ec7-92c5-982abd477e69
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer i Kina som använder Office 365 som drivs av 21Vianet kan lära sig att använda fristående Exchange Online Protection (EOP) för att skydda sina lokala postlådor.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4258d64721fc2042297bb15eaeecafa90dcf4bc1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929294"
---
# <a name="protect-on-premises-mailboxes-in-china-with-standalone-eop"></a>Skydda lokala postlådor i Kina med fristående EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Den här artikeln gäller endast Office 365 som drivs av 21Vianet i Kina.

Även om du planerar att ha några eller alla postlådor lokalt kan du fortfarande skydda dem med Exchange Online Protection (EOP). Om du vill konfigurera kopplingar måste ditt konto vara en global administratör eller Exchange-företagsadministratör (rollgruppen Organisationshantering). Mer information om hur Office 365-behörigheter är relaterade till Exchange-behörigheter finns i Tilldela administratörsroller i [Office 365 som drivs av 21Vianet.](../../admin/add-users/assign-admin-roles.md?preserve-view=true&view=o365-21vianet) Om alla Exchange-postlådor finns lokalt följer du de här anvisningarna för att konfigurera EOP-tjänsten.

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Steg 1: Använda administrationscentret för Microsoft 365 för att lägga till och verifiera din domän

1. Gå till Installation i administrationscentret för Microsoft 365 för att lägga till din domän i tjänsten.

2. Följ stegen i portalen för att lägga till tillämpliga DNS-poster i din DNS-värd för att verifiera domänägarskap.

> [!TIP]
> Lägga till din domän och användare i Office 365 som drivs av [21Vianet](../../admin/setup/add-domain.md?preserve-view=true&view=o365-21vianet) och Skapa DNS-poster för [Office 365](../../admin/services-in-china/create-dns-records-when-you-manage-your-dns-records.md?preserve-view=true&view=o365-21vianet) när du hanterar dina DNS-poster är användbara resurser att referera till när du lägger till din domän i tjänsten och konfigurerar DNS.

### <a name="step-2-add-recipients-and-configure-the-domain-type"></a>Steg 2: Lägg till mottagare och konfigurera domäntypen

Innan du konfigurerar e-post så att den flödar till och från EOP-tjänsten rekommenderar vi att du lägger till mottagarna i tjänsten. Du kan göra det på flera olika sätt, vilket beskrivs i Hantera [e-postanvändare i EOP.](manage-mail-users-in-eop.md) Om du vill aktivera DBEB (Directory Based Edge Blocking) för att tvinga mottagarens verifiering inom tjänsten när du har lagt till mottagarna måste du ange domäntypen till Auktoritativ. Mer information om DBEB finns i Använda [katalogbaserad edge-blockering för att avvisa meddelanden som skickas till ogiltiga mottagare.](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Steg 3: Använda EAC för att konfigurera e-postflöde

Skapa kopplingar i administrationscentret för Exchange (EAC) som aktiverar e-postflödet mellan EOP och de lokala e-postservrarna. Detaljerade instruktioner finns i Konfigurera [e-postflöde med kopplingar i Office 365.](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)

 Hur vet du att den här uppgiften fungerade?

 Läs [Testa e-postflöde genom att verifiera dina Office 365-kopplingar](/exchange/mail-flow-best-practices/test-mail-flow).

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Steg 4: Tillåt inkommande port 25 SMTP-åtkomst

Vänta i 72 timmar efter att du har konfigurerat kopplingar för att tillåta spridning av DNS-postuppdateringar. Här begränsar du inkommande SMTP-trafik med port-25 i brandväggen eller e-postservrarna så att de endast accepterar e-post från EOP-datacenter, speciellt från DE IP-adresser som anges i URL:er och IP-adressintervall för [Office 365.](../../enterprise/managing-office-365-endpoints.md) Det här skyddar din lokala miljö genom att begränsa omfattningen av inkommande meddelanden som du kan ta emot. Om du dessutom har inställningar på e-postservern som styr vilka IP-adresser som tillåts ansluta för e-postrelä, uppdaterar du även de inställningarna.

> [!TIP]
> Konfigurera inställningar på SMTP-servern med en anslutningstid av 60 sekunder. Den här inställningen är godtagbar för de flesta situationer, till exempel för en viss fördröjning vid ett meddelande som skickas med en stor bifogad fil.

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Steg 5: Kontrollera att skräppost skickas till varje användares skräppostmapp

Om du vill se till att skräppost dirigeras korrekt till användarnas skräppostmappar måste du utföra några konfigurationssteg. Stegen finns i Konfigurera [fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer.](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) Om du inte vill flytta meddelanden till varje användares skräppostmapp kan du välja en annan åtgärd genom att redigera principerna för skräppostskydd (kallas även principer för innehållsfilter). Mer information finns i [Konfigurera principer för skräppostskydd i Office 365](configure-your-spam-filter-policies.md).

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Steg 6: Använd administrationscentret för Microsoft 365 för att peka MX-posten på EOP

Följ konfigurationsstegen för Office 365-domänen för att uppdatera MX-posten för domänen, så att din inkommande e-post flödar via EOP. Mer information finns i Skapa [DNS-poster för Office 365 när du hanterar dina DNS-poster.](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md?preserve-view=true&view=o365-21vianet)

Hur vet du att den här uppgiften fungerade?

 Läs [Testa e-postflöde genom att verifiera dina Office 365-kopplingar](/exchange/mail-flow-best-practices/test-mail-flow).

Nu har du verifierat tjänstleveransen för en korrekt konfigurerad utgående lokal koppling och du har kontrollerat att MX-posten pekar på EOP. Du kan nu välja att köra följande ytterligare tester för att verifiera att ett e-postmeddelande kommer att levereras av tjänsten till din lokala miljö:

- I Remote Connectivity Analyzer klickar du på fliken **Office 365** och kör sedan testet **för inkommande** SMTP-e-post under E-posttest **via Internet.**

- Skicka ett e-postmeddelande från ett webbaserat e-postkonto till en e-postmottagare i organisationen vars domän matchar den domän som du lade till i tjänsten. Bekräfta leverans av meddelandet till den lokala postlådan med hjälp av Microsoft Outlook eller en annan e-postklient.

- Om du vill köra ett utgående e-posttest kan du skicka ett e-postmeddelande från en användare i organisationen till ett webbaserat e-postkonto och bekräfta att meddelandet tas emot.

## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a>Mindre vanligt: En hybridkonfiguration med postlådor både lokalt och i molnet

Om du har Exchange-postlådor lokalt och en eller flera postlådor i molnet i Exchange Online har du en *hybridkonfiguration.* I en hybridkonfiguration fungerar funktioner som delning av kalenderinformation om ledig/upptagen tid och e-postdirigering i både den lokala miljön och i molnet. Du kanske har en hybridkonfiguration medan du går över postlådor till Exchange Online. En hybridmiljö konfigureras på ett annat sätt än EOP med fristående skydd.

Du kan välja en hybridscenario om du vill kunna dra nytta av molnbaserad e-post för de flesta anställda. Du kan göra det medan du är värd för vissa postlådor lokalt. till exempel för den juridiska avdelningen.

En hybridkonfiguration kan vara komplex, men den har många fördelar. Mer information om hur du inställningar för hybridscenarier med Exchange finns i [Exchange Server-hybriddistributioner.](/Exchange/exchange-hybrid)