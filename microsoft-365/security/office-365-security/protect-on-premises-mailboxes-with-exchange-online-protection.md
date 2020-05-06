---
title: Skydda lokal postlåda - Exchange Online Protection
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 6/1/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
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
description: I den här artikeln får du lära dig hur du skyddar lokala postlådor med Exchange Online Protection (EOP)
ms.openlocfilehash: bdfebf16d77f26f3e3bb2890bd4aa8ccfa12f27b
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033884"
---
# <a name="protect-on-premises-mailboxes-with-exchange-online-protection"></a>Skydda lokala postlådor med Exchange Online Protection

> [!NOTE]
> Den här artikeln gäller endast Office 365 som drivs av 21Vianet i Kina.

Även om du planerar att vara värd för vissa eller alla dina postlådor lokalt kan du fortfarande skydda postlådorna med Exchange Online Protection (EOP). Om du vill konfigurera kopplingar måste ditt konto vara en global administratör eller en Exchange Company-administratör (rollgruppen Organisationshantering). Information om hur Office 365-behörigheter relaterar till Exchange-behörigheter finns [i Tilldela administratörsroller i Office 365 som drivs av 21Vianet](https://docs.microsoft.com/office365/admin/add-users/assign-admin-roles?&view=o365-21vianet). Om alla Exchange-postlådor är lokala följer du dessa steg för att konfigurera eOP-tjänsten.

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Steg 1: Använda administrationscentret för Microsoft 365 för att lägga till och verifiera din domän

1. I administrationscentret för Microsoft 365 navigerar du till installationsprogrammet för att lägga till domänen i tjänsten.

2. Följ stegen i portalen för att lägga till tillämpliga DNS-poster i din DNS-värd för att verifiera domänägarskap.

> [!TIP]
> [Lägga till din domän och användare i Office 365 som drivs av 21Vianet](https://docs.microsoft.com/office365/admin/setup/add-domain?&view=o365-21vianet) och [Skapa DNS-poster för Office 365 när du hanterar DINA DNS-poster](https://docs.microsoft.com/office365/admin/services-in-china/create-dns-records-when-you-manage-your-dns-records?&view=o365-21vianet) är användbara resurser att referera till när du lägger till domänen i tjänsten och konfigurerar DNS.

### <a name="step-2-add-recipients-and-configure-the-domain-type"></a>Steg 2: Lägga till mottagare och konfigurera domäntypen

Innan du konfigurerar din e-post så att den flödar till och från EOP-tjänsten rekommenderar vi att du lägger till mottagarna i tjänsten. Det finns flera sätt att göra detta, vilket dokumenteras i [Hantera e-postanvändare i EOP](manage-mail-users-in-eop.md). Om du vill aktivera DBEB (Directory Based Edge Blocking) för att framtvinga mottagarverifiering inom tjänsten efter att du har lagt till mottagarna måste du ställa in domäntypen till Auktoritär. Mer information om DBEB finns i [Använda katalogbaserad kantblockering för att avvisa meddelanden som skickas till ogiltiga mottagare](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Steg 3: Använd EAC för att ställa in e-postflöde

Skapa kopplingar i Administrationscenter för Exchange (EAC) som möjliggör e-postflöde mellan EOP och dina lokala e-postservrar. Detaljerade instruktioner finns i [Konfigurera e-postflöde med kopplingar i Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

 Hur vet du att den här uppgiften fungerade?

 Se [Testa e-postflöde genom att verifiera dina Office 365-kopplingar](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Steg 4: Tillåt inkommande port 25 SMTP-åtkomst

När du har konfigurerat kopplingar väntar du 72 timmar på att tillåta spridning av DNS-postuppdateringar. Därefter begränsar du inkommande port-25 SMTP-trafik på brandväggen eller e-postservrarna så att den bara tar emot e-post från EOP-datacenter, särskilt från IP-adresserna som anges vid [URL:er och IP-adressintervall för Office 365](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints). Detta skyddar din lokala miljö genom att begränsa omfattningen av inkommande meddelanden som du kan ta emot. Om du har inställningar på e-postservern som styr de IP-adresser som tillåts ansluta för e-postrelä uppdaterar du dessutom dessa inställningar.

> [!TIP]
> Konfigurera inställningar på SMTP-servern med en anslutningstid på 60 sekunder. Den här inställningen är godtagbar för de flesta situationer, vilket möjliggör viss fördröjning när det gäller ett meddelande som skickas med en stor bifogad fil, till exempel.

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Steg 5: Se till att skräppost dirigeras till varje användares skräppostmapp

Om du vill vara säkra på att skräppost e-post dirigeras korrekt till varje användares skräppostmapp måste du utföra ett par konfigurationssteg. Stegen finns i [Konfigurera fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). Om du inte vill flytta meddelanden till varje användares skräppostmapp kan du välja en annan åtgärd genom att redigera innehållsfilterprinciperna i administrationscentret för Exchange. Mer information finns i [Konfigurera principer för skräppostskydd i Office 365](configure-your-spam-filter-policies.md).

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Steg 6: Använd administrationscentret för Microsoft 365 för att peka ut MX-posten till EOP

Följ konfigurationsstegen för Office 365-domänen för att uppdatera MX-posten för din domän så att din inkommande e-post flödar via EOP. Om du vill ha mer information kan du återigen referera till [Skapa DNS-poster för Office 365 när du hanterar dina DNS-poster](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

Hur vet du att den här uppgiften fungerade?

 Se [Testa e-postflöde genom att verifiera dina Office 365-kopplingar](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).

Nu har du verifierat tjänstleverans för en korrekt konfigurerad utgående lokal anslutningsapp och du har verifierat att MX-posten pekar på EOP. Du kan nu välja att köra följande ytterligare tester för att kontrollera att ett e-postmeddelande kommer att levereras av tjänsten till din lokala miljö:

- Klicka på fliken **Office 365** i Remote Connectivity Analyzer och kör sedan det **inkommande SMTP-e-e-posttestet** som finns under **Internet-e-posttester**.

- Skicka ett e-postmeddelande från ett webbaserat e-postkonto till en e-postmottagare i organisationen vars domän matchar domänen som du lade till i tjänsten. Bekräfta leveransen av meddelandet till den lokala postlådan med Microsoft Outlook eller en annan e-postklient.

- Om du vill köra ett utgående e-posttest kan du skicka ett e-postmeddelande från en användare i organisationen till ett webbaserat e-postkonto och bekräfta att meddelandet tas emot.

## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a>Mindre vanligt: En hybridinstallation med postlådor lokalt och i molnet

Om du har Exchange-postlådor lokalt och en eller flera postlådor i molnet i Exchange Online har du en *hybridkonfiguration.* I en hybridkonfiguration fungerar funktioner som ledig/upptagen kalenderdelning och e-postroutning tillsammans i lokala miljöer och molnmiljöer. Du kan ha en hybridkonfiguration på plats medan du överför postlådor till Exchange Online. En hybridmiljö ställs in på ett annat sätt än EOP-fristående skydd.

Du kan välja ett hybridscenario för att dra nytta av molnbaserad e-post för de flesta av dina anställda. Du kan göra detta samtidigt som du är värd för vissa postlådor lokalt. till exempel för din juridiska avdelning.

En hybridinställning kan vara komplex, men den har många fördelar. Mer information om hur du konfigurerar hybridscenarier med Exchange finns i [Hybriddistributioner av Exchange Server](https://docs.microsoft.com/Exchange/exchange-hybrid).
