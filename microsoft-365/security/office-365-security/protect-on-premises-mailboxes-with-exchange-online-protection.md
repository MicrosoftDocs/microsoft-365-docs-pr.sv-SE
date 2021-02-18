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
ms.openlocfilehash: f4f27fa9237d76422e936555c9872b83655d7b6b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289431"
---
# <a name="protect-on-premises-mailboxes-in-china-with-standalone-eop"></a>Skydda lokala postlådor i Kina med fristående EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Den här artikeln gäller endast Office 365 som drivs av 21Vianet i Kina.

Även om du planerar att ha några eller alla postlådor lokalt kan du fortfarande skydda postlådorna med Exchange Online Protection (EOP). Om du vill konfigurera kopplingar måste ditt konto vara global administratör eller Exchange-företagsadministratör (rollgruppen Organisationshantering). Mer information om hur Office 365-behörigheter relaterar till Exchange-behörigheter finns i Tilldela administratörsroller i [Office 365 som drivs av 21Vianet.](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-21vianet&preserve-view=true) Om alla Exchange-postlådor finns lokalt följer du de här anvisningarna för att konfigurera EOP-tjänsten.

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Steg 1: Använd administrationscentret för Microsoft 365 för att lägga till och verifiera din domän

1. Gå till installationsprogrammet i administrationscentret för Microsoft 365 för att lägga till din domän i tjänsten.

2. Följ stegen i portalen för att lägga till tillämpliga DNS-poster i din DNS-värd för att verifiera domänägarskap.

> [!TIP]
> Lägg till din domän och användare i Office 365 som drivs av [21Vianet](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain?view=o365-21vianet&preserve-view=true) och skapa DNS-poster för [Office 365](https://docs.microsoft.com/microsoft-365/admin/services-in-china/create-dns-records-when-you-manage-your-dns-records?view=o365-21vianet&preserve-view=true) när du hanterar dina DNS-poster är användbara resurser att referera till när du lägger till din domän i tjänsten och konfigurerar DNS.

### <a name="step-2-add-recipients-and-configure-the-domain-type"></a>Steg 2: Lägg till mottagare och konfigurera domäntypen

Innan du konfigurerar din e-post så att den flödar till och från EOP-tjänsten rekommenderar vi att du lägger till mottagarna i tjänsten. Du kan göra det på flera olika sätt, vilket beskrivs i [Hantera e-postanvändare i EOP.](manage-mail-users-in-eop.md) Om du vill aktivera DBEB (Directory Based Edge Blocking) för att tvinga mottagarens verifiering i tjänsten när du har lagt till mottagarna måste du ange domäntypen till Auktoritativ. Mer information om DBEB finns i Använda [katalogbaserad edge-blockering för att avvisa meddelanden som skickas till ogiltiga mottagare.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Steg 3: Använda EAC för att konfigurera e-postflöde

Skapa kopplingar i administrationscentret för Exchange (EAC) som aktiverar e-postflödet mellan EOP och dina lokala e-postservrar. Detaljerade instruktioner finns i Konfigurera [e-postflöde med kopplingar i Office 365.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)

 Hur vet du att den här uppgiften fungerade?

 Se [Testa e-postflödet genom att verifiera Office 365-anslutningarna.](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Steg 4: Tillåt inkommande port 25 SMTP-åtkomst

När du har konfigurerat kopplingar väntar du i 72 timmar för att tillåta spridning av DNS-postuppdateringarna. Därefter begränsar du inkommande SMTP-trafik med port 25 i brandväggen eller e-postservrarna så att du endast accepterar e-post från EOP-datacenter, särskilt från IP-adresser som anges i URL:er och IP-adressintervall för [Office 365.](../../enterprise/managing-office-365-endpoints.md) Det här skyddar din lokala miljö genom att begränsa omfattningen av inkommande meddelanden som du kan ta emot. Om du har inställningar på e-postservern som styr vilka IP-adresser som tillåts ansluta för e-postrelä uppdaterar du även de inställningarna.

> [!TIP]
> Konfigurera inställningar på SMTP-servern med en anslutningstid på 60 sekunder. Den här inställningen är godtagbar för de flesta situationer, till exempel om ett meddelande som skickas med en stor bifogad fil kan fördröjas.

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Steg 5: Kontrollera att skräppost dirigeras till varje användares skräppostmapp

Om du vill att skräppost (skräppost) ska dirigeras korrekt till varje användares skräppostmapp måste du utföra några konfigurationssteg. Stegen finns i Konfigurera [fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer.](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) Om du inte vill flytta meddelanden till varje användares skräppostmapp kan du välja en annan åtgärd genom att redigera principerna för skydd mot skräppost (kallas även principer för innehållsfilter). Mer information finns i [Konfigurera principer för skräppostskydd i Office 365](configure-your-spam-filter-policies.md).

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Steg 6: Använd administrationscentret för Microsoft 365 för att peka MX-posten på EOP

Följ konfigurationsstegen för Office 365-domänen för att uppdatera MX-posten för din domän, så att din inkommande e-post flödar via EOP. Mer information finns i Skapa [DNS-poster för Office 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider?view=o365-21vianet&preserve-view=true)när du hanterar dina DNS-poster.

Hur vet du att den här uppgiften fungerade?

 Se [Testa e-postflödet genom att verifiera Office 365-anslutningarna.](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)

Nu har du verifierat tjänstleverans för en korrekt konfigurerad utgående lokal koppling och du har kontrollerat att MX-posten pekar på EOP. Du kan nu välja att köra följande ytterligare tester för att verifiera att ett e-postmeddelande levereras av tjänsten till din lokala miljö:

- I Remote Connectivity Analyzer klickar du på fliken **Office 365** och kör sedan testet för **inkommande** SMTP-e-post under **Internet-e-posttester.**

- Skicka ett e-postmeddelande från ett webbaserat e-postkonto till en e-postmottagare i organisationen vars domän överensstämmer med den domän du lade till i tjänsten. Bekräfta leverans av meddelandet till den lokala postlådan med hjälp av Microsoft Outlook eller en annan e-postklient.

- Om du vill köra ett utgående e-posttest kan du skicka ett e-postmeddelande från en användare i organisationen till ett webbaserat e-postkonto och bekräfta att meddelandet tas emot.

## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a>Mindre vanligt: En hybridkonfiguration med postlådor både lokalt och i molnet

Om du har Exchange-postlådor lokalt och en eller flera postlådor i molnet i Exchange Online har du en *hybridkonfiguration.* I en hybridkonfiguration fungerar funktioner som kalenderdelning ledig/upptagen och e-postdirigering i både din lokala miljö och din molnmiljö. Du kanske har en hybridkonfiguration medan du går över postlådor till Exchange Online. En hybridmiljö konfigureras på ett annat sätt än EOP som fristående skydd.

Du kan välja en hybridscenario om du vill kunna dra nytta av molnbaserad e-post för de flesta anställda. Du kan göra det medan du även är värd för vissa postlådor lokalt. till exempel för den juridiska avdelningen.

En hybridkonfiguration kan vara komplex, men den har många fördelar. Mer information om hur du inställningar för hybridscenarier med Exchange [finns Exchange Server hybriddistributioner.](https://docs.microsoft.com/Exchange/exchange-hybrid)
