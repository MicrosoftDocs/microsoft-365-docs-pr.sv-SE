---
title: Konfigurera din EOP-tjänst
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
ms.assetid: d74c6ddf-11b0-43ee-b298-8bb0340895f0
description: I den här artikeln får du lära dig mer om hur du konfigurerar Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: c00d39cae440bc95e26c853e107d8d7a8f4c50d8
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035290"
---
# <a name="set-up-your-eop-service"></a>Konfigurera din EOP-tjänst

I det här avsnittet beskrivs hur du konfigurerar Microsoft Exchange Online Protection (EOP). Om du landade här från guiden Office 365-domäner går du tillbaka till office 365-domänguiden om du inte vill använda Exchange Online Protection. Om du letar efter mer information om hur du konfigurerar kopplingar läser du [Konfigurera e-postflöde med kopplingar i Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

> [!NOTE]
> Det här avsnittet förutsätter att du har lokala postlådor och du vill skydda dem med EOP, som kallas ett fristående scenario. Om du vill vara värd för alla dina postlådor i molnet med Exchange Online behöver du inte slutföra alla steg i det här avsnittet. Gå till [Jämför Exchange Online-abonnemang](https://products.office.com/exchange/compare-microsoft-exchange-online-plans) för att registrera dig och köpa molnpostlådor. Om du vill vara värd för några av dina postlådor lokalt och några i molnet kallas detta för ett hybridscenario. Det kräver mer avancerade inställningar för e-postflöde. [Hybriddistributioner av Exchange Server](https://docs.microsoft.com/exchange/exchange-hybrid) förklarar hybridpostflödet och har länkar till resurser som visar hur du konfigurerar det.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Beräknad tid för att slutföra den här uppgiften: 1 timme

- Om du vill konfigurera kopplingar måste ditt konto vara en global administratör eller en Exchange Company-administratör (rollgruppen Organisationshantering). Information finns [i Funktionsbehörigheter i EOP](feature-permissions-in-eop.md).

- Om du inte har registrerat dig för EOP besöker du [Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection) och väljer att köpa eller prova tjänsten.

- Information om kortkommandon som kan gälla för procedurerna i det här avsnittet finns [i Kortkommandon för administrationscentret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Har du problem? Be om hjälp i Forumet för [Exchange Online Protection.](https://go.microsoft.com/fwlink/p/?linkId=285351)

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Steg 1: Använda administrationscentret för Microsoft 365 för att lägga till och verifiera din domän

1. I [administrationscentret för Microsoft 365](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center)går du till **Installationsprogrammet** för att lägga till domänen i tjänsten.

2. Följ stegen för att lägga till tillämpliga DNS-poster i din DNS-värd för att verifiera domänägarskap.

> [!TIP]
> [Lägga till en domän i Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain) och [Skapa DNS-poster hos alla DNS-värd för Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) är användbara resurser att referera till när du lägger till domänen i tjänsten och konfigurerar DNS.

## <a name="step-2-add-recipients-and-optionally-enable-dbeb"></a>Steg 2: Lägg till mottagare och aktivera DBEB

Innan du konfigurerar din e-post så att den flödar till och från EOP-tjänsten rekommenderar vi att du lägger till mottagarna i tjänsten. Det finns flera sätt att göra detta, vilket dokumenteras i [Hantera e-postanvändare i EOP](manage-mail-users-in-eop.md). Om du vill aktivera DBEB (Directory Based Edge Blocking) för att framtvinga mottagarverifiering inom tjänsten efter att du har lagt till mottagarna måste du ställa in domäntypen till Auktoritär. Mer information om DBEB finns i [Använda katalogbaserad kantblockering för att avvisa meddelanden som skickas till ogiltiga mottagare](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Steg 3: Använd EAC för att ställa in e-postflöde

Skapa kopplingar i Administrationscenter för Exchange (EAC) som möjliggör e-postflöde mellan EOP och dina lokala e-postservrar. Detaljerade instruktioner finns i [Konfigurera kopplingar för att dirigera e-post mellan Microsft 365 och dina egna e-postservrar](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail).

### <a name="how-do-you-know-this-task-worked"></a>Hur vet du att den här uppgiften fungerade?

Kontrollera e-postflödet mellan tjänsten och din miljö. Mer information finns i [Testa e-postflödet genom att validera dina Microsoft 365-kopplingar](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Steg 4: Tillåt inkommande port 25 SMTP-åtkomst

När du har konfigurerat kopplingar väntar du 72 timmar på att tillåta spridning av DNS-postuppdateringar. Därefter begränsar du inkommande port-25 SMTP-trafik på brandväggen eller e-postservrarna så att den endast tar emot e-post från EOP-datacenter, särskilt från IP-adresserna som anges på [Exchange Online Protection IP-adresser](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). Detta skyddar din lokala miljö genom att begränsa omfattningen av inkommande meddelanden som du kan ta emot. Om du har inställningar på e-postservern som styr de IP-adresser som tillåts ansluta för e-postrelä uppdaterar du dessutom dessa inställningar.

> [!TIP]
> Konfigurera inställningar på SMTP-servern med en anslutningstid på 60 sekunder. Den här inställningen är godtagbar för de flesta situationer, vilket möjliggör viss fördröjning när det gäller ett meddelande som skickas med en stor bilaga, till exempel.

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Steg 5: Se till att skräppost dirigeras till varje användares skräppostmapp

Om du vill vara säkra på att skräppost e-post dirigeras korrekt till varje användares skräppostmapp måste du utföra ett par konfigurationssteg. Stegen finns i [Konfigurera fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

Om du inte vill flytta meddelanden till varje användares skräppostmapp kan du välja en annan åtgärd genom att redigera innehållsfilterprinciperna i administrationscentret för Exchange. Mer information finns i [Konfigurera principer för skräppostskydd i Office 365](configure-your-spam-filter-policies.md).

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Steg 6: Använd administrationscentret för Microsoft 365 för att peka ut MX-posten till EOP

Följ stegen för domänkonfiguration för att uppdatera MX-posten för din domän, så att din inkommande e-post flödar via EOP. Var noga med att peka din MX-post direkt till EOP i stället för att ha en tredje part filtrering tjänst relä e-post till EOP. Mer information finns i [Skapa DNS-poster för Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)igen.

### <a name="how-do-you-know-this-task-worked"></a>Hur vet du att den här uppgiften fungerade?

Nu har du verifierat tjänstleverans för en korrekt konfigurerad utgående lokal anslutningsapp och du har verifierat att MX-posten pekar på EOP. Du kan nu välja att köra följande ytterligare tester för att kontrollera att ett e-postmeddelande kommer att levereras av tjänsten till din lokala miljö:

- Kontrollera e-postflödet mellan tjänsten och din miljö. Mer information finns i [Testa e-postflödet genom att validera dina Microsoft 365-kopplingar](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).

- Skicka ett e-postmeddelande från ett webbaserat e-postkonto till en e-postmottagare i organisationen vars domän matchar domänen som du lade till i tjänsten. Bekräfta leveransen av meddelandet till den lokala postlådan med Microsoft Outlook eller en annan e-postklient.

- Om du vill köra ett utgående e-posttest kan du skicka ett e-postmeddelande från en användare i organisationen till ett webbaserat e-postkonto och bekräfta att meddelandet tas emot.

> [!TIP]
> När du har slutfört installationen behöver du inte utföra extra steg för att få EOP att ta bort skräppost och skadlig kod. EOP tar bort skräppost och skadlig kod automatiskt. Du kan dock finjustera dina inställningar i EAC, baserat på dina affärskrav. Mer information finns [i Skydd mot skräppost och skadlig kod i Office 365](anti-spam-and-anti-malware-protection.md). <br/><br/> Nu när tjänsten körs rekommenderar vi att du läser [metodtips för att konfigurera EOP](best-practices-for-configuring-eop.md), som beskriver rekommenderade inställningar och överväganden för när du har konfigurerat EOP.
