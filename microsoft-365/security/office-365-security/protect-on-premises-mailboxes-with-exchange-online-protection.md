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
description: Administratörer i Kina som använder Office 365 som drivs av 21Vianet kan läsa mer om hur du använder fristående Exchange Online Protection (EOP) för att skydda sina lokala post lådor.
ms.openlocfilehash: ca3f7f1ffc91b404ac59e92b40ae1f95709ec3ff
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307755"
---
# <a name="protect-on-premises-mailboxes-in-china-with-standalone-eop"></a>Skydda lokala postlådor i Kina med fristående EOP

> [!NOTE]
> Den här artikeln gäller endast för Office 365 som drivs av 21Vianet i Kina.

Även om du planerar att hantera vissa eller alla dina post lådor lokalt kan du fortfarande skydda post lådorna med Exchange Online Protection (EOP). För att kunna konfigurera kopplingar måste ditt konto vara en global administratör eller en Exchange-kontoadministratör (organisations hanterings grupp). Information om hur Office 365-behörigheter relaterar till Exchange-behörigheter finns i [tilldela administratörs roller i Office 365 som drivs av 21Vianet](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-21vianet). Om alla dina Exchange-postlådor finns på plats gör du så här för att konfigurera EOP-tjänsten.

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Steg 1: Använd administrations centret för Microsoft 365 för att lägga till och verifiera din domän

1. I administrations centret för Microsoft 365 navigerar du till installations programmet för att lägga till domänen i tjänsten.

2. Följ stegen i portalen för att lägga till de DNS-poster som är tillämpliga på din DNS-värd för att verifiera domänens ägarskap.

> [!TIP]
> [Lägga till din domän och användare i office 365 som drivs av 21Vianet](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain?view=o365-21vianet) och [Skapa DNS-poster för Office 365 när du hanterar dina DNS-poster](https://docs.microsoft.com/microsoft-365/admin/services-in-china/create-dns-records-when-you-manage-your-dns-records?view=o365-21vianet) är användbara resurser att referera till när du lägger till domänen till tjänsten och konfigurerar DNS.

### <a name="step-2-add-recipients-and-configure-the-domain-type"></a>Steg 2: Lägg till mottagare och konfigurera domän typen

Innan du konfigurerar din e-post som ska flöda till och från EOP-tjänsten rekommenderar vi att du lägger till mottagarna i tjänsten. Det finns flera sätt som du kan göra det på, som dokumenterade i [Hantera e-postanvändare i EOP](manage-mail-users-in-eop.md). Om du vill aktivera Directory-baserad Edge-blockering (DBEB) för att tvinga mottagar verifiering i tjänsten efter att du har lagt till mottagarna måste du ange domän typen till auktoritär. Mer information om DBEB finns i [använda katalogbaserade kant spärr för att neka meddelanden skickade till ogiltiga mottagare](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Steg 3: använda UK för att konfigurera e-postflöde

Skapa kopplingar i administrations centret för Exchange (UK) som möjliggör e-postflöde mellan EOP och dina lokala e-postservrar. Detaljerade anvisningar finns i [Konfigurera e-postflöde med kopplingar i Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

 Hur vet jag att den här uppgiften fungerade?

 Se [Testa e-postflödet genom att verifiera dina Office 365-kopplingar](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Steg 4: Tillåt inkommande port 25 SMTP-åtkomst

När du har konfigurerat kopplingar väntar du 72 timmar för att tillåta spridningen av DNS-postuppdateringarna. Därefter kan du begränsa inkommande port-25 SMTP-trafik på din brand vägg eller e-postserver så att den endast kan skicka e-post från EOP Data Center, specifikt från IP-adresserna som visas i [URL: er och IP-adressintervall för Office 365](https://docs.microsoft.com/microsoft-365/enterprise/managing-office-365-endpoints). Då skyddas den lokala miljön genom att begränsa omfattningen av inkommande meddelanden som du kan ta emot. Om du har inställningar på din e-postserver som styr vilka IP-adresser som är tillåtna för att ansluta till e-post kan du även uppdatera dessa inställningar.

> [!TIP]
> Konfigurera inställningar på SMTP-servern med en anslutnings tid på 60 sekunder. Den här inställningen är acceptabel i de flesta fall, vilket gör att en viss fördröjning i ett meddelande som skickas med en stor bilaga till exempel.

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Steg 5: kontrol lera att skräp post vidarebefordras till varje användares mapp för skräp post

För att säkerställa att skräp post meddelanden vidarebefordras korrekt till varje användares skräppost-mapp måste du utföra några olika konfigurations steg. Anvisningarna finns i [Konfigurera fristående EOP för att skicka skräp post till skräppostmappen i hybrid miljöer](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). Om du inte vill flytta meddelanden till varje användares skräppost-mapp kan du välja en annan åtgärd genom att redigera principer för skräp post (kallas även för innehålls filter principer). Mer information finns i [Konfigurera principer för skräppostskydd i Office 365](configure-your-spam-filter-policies.md).

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Steg 6: Använd administrations centret för Microsoft 365 för att peka din MX-post på EOP

Följ stegen i domän konfigurationen för Office 365 för att uppdatera MX-posten för din domän så att dina inkommande e-postmeddelanden genom EOP. Om du vill ha mer information kan du återigen referera till [Skapa DNS-poster för Office 365 när du hanterar dina DNS-poster](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

Hur vet jag att den här uppgiften fungerade?

 Se [Testa e-postflödet genom att verifiera dina Office 365-kopplingar](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).

I det här läget har du bekräftat tjänste leverans för en korrekt konfigurerad utgående lokal koppling, och du har verifierat att din MX-post pekar på EOP. Du kan välja att köra följande ytterligare test för att verifiera att ett e-postmeddelande kommer att skickas till din lokala miljö:

- I fjärr anslutnings analys klickar du på fliken **Office 365** och kör sedan det **inkommande SMTP-** Testtestet under **Internet-e-PostTest**.

- Skicka ett e-postmeddelande från ett webbaserat e-postkonto till en e-postmottagare i din organisation vars domän matchar den domän som du har lagt till i tjänsten. Bekräfta leverans av meddelandet till den lokala post lådan med hjälp av Microsoft Outlook eller en annan e-postklient.

- Om du vill köra ett utgående e-PostTest kan du skicka ett e-postmeddelande från en användare i din organisation till ett webbaserat e-postkonto och bekräfta att meddelandet har tagits emot.

## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a>Mindre vanligt: en hybrid installation med post lådor lokalt och i molnet

Om du har Exchange-postlådor lokalt och en eller flera post lådor i molnet i Exchange Online har du en *hybrid* konfiguration. I en hybrid installation fungerar funktioner som ledig/upptagen kalender delning och e-postdirigering i dina lokala och moln miljöer. Du kanske har en hybrid installation när du över gång till post lådor till Exchange Online. En hybrid miljö är inställd på annat sätt än EOP fristående skydd.

Du kan välja ett hybrid scenario för att utnyttja det molnbaserade e-postmeddelandet för de flesta anställda. Du kan göra detta samtidigt som du är värd för vissa post lådor lokalt; för din juridiska avdelning.

En hybrid konfiguration kan vara komplicerad men har många fördelar. Mer information om hur du konfigurerar hybrid scenarier med Exchange finns i [Exchange Server hybrid distributioner](https://docs.microsoft.com/Exchange/exchange-hybrid).
