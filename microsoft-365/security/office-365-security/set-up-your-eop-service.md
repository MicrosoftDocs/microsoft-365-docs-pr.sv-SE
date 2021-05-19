---
title: Konfigurera en fristående EOP-tjänst
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
ms.assetid: d74c6ddf-11b0-43ee-b298-8bb0340895f0
description: Administratörer kan läsa om hur fristående e-Exchange Online Protection (EOP) kan konfigureras för att skydda lokala e-postmiljöer.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 63504dd2d729674fd84eff2fd5548c8d077cd1f1
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538981"
---
# <a name="set-up-your-standalone-eop-service"></a>Konfigurera en fristående EOP-tjänst

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
-  [Exchange Online Protection fristående](exchange-online-protection-overview.md)

I det här avsnittet förklaras hur du ställer in fristående Exchange Online Protection (EOP). Om du hamnade här från Office 365-domänguiden går du tillbaka till Office 365 för domäner om du inte vill använda Exchange Online Protection. Mer information om hur du konfigurerar kopplingar finns i Konfigurera e-postflöde med [kopplingar i Office 365.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)

> [!NOTE]
> Den här artikeln förutsätter att du har lokala postlådor och vill skydda dem med EOP, som kallas för ett fristående scenario. Om du vill ha alla postlådor i molnet med Exchange Online behöver du inte slutföra alla steg i den här artikeln. Gå till [Jämför Exchange Online abonnemang för](https://products.office.com/exchange/compare-microsoft-exchange-online-plans) att registrera dig och köpa molnbaserade postlådor.
>
> Om du vill ha några av dina postlådor lokalt och andra i molnet kallas det här för ett hybridscenario. Det kräver mer avancerade inställningar för e-postflöde. [Exchange Server i hybriddistributioner förklaras](/exchange/exchange-hybrid) e-postflödet för hybriden och innehåller länkar till resurser som visar hur du konfigurerar den.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Beräknad tid för att slutföra aktiviteten: 1 timme

- Du måste ha tilldelats behörigheter i Exchange Online Protection innan du kan utföra procedurerna i den här artikeln. Specifikt behöver du rollen **Fjärr-** och godkända domäner, som tilldelas rollgrupperna **Organisationshantering** (globala administratörer) och E Flow postadministratörsrollgrupper som standard.  Mer information finns i [Behörigheter i fristående EOP](feature-permissions-in-eop.md) och Använda EAC för att [ändra listan över medlemmar i rollgrupper.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Om du inte har registrerat dig för EOP går du [Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection) väljer att köpa eller prova tjänsten.

- Mer information om kortkommandon som kan gälla för procedurerna i den här artikeln finns i Kortkommandon för administrationscentret [Exchange i Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Har du problem? Be om hjälp i [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Steg 1: Använd Microsoft 365 för att lägga till och verifiera din domän

1. I Microsoft 365 [går du](../../admin/admin-overview/about-the-admin-center.md)till Konfigurera **för** att lägga till din domän i tjänsten.

2. Följ stegen för att lägga till tillämpliga DNS-poster i din DNS-värd för att verifiera domänägarskap.

> [!TIP]
> [Att lägga till](../../admin/setup/add-domain.md) en domän Office 365 och Skapa DNS-poster hos en [DNS-värd](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) för Office 365 är användbara resurser att referera till när du lägger till din domän i tjänsten och konfigurerar DNS.

## <a name="step-2-add-recipients-and-optionally-enable-dbeb"></a>Steg 2: Lägg till mottagare och aktivera DBEB om du vill

Innan du konfigurerar e-post så att den flödar till och från EOP-tjänsten rekommenderar vi att du lägger till mottagarna i tjänsten. Du kan göra det på flera olika sätt, vilket beskrivs i Hantera [e-postanvändare i EOP.](manage-mail-users-in-eop.md) Om du vill aktivera DBEB (Directory Based Edge Blocking) för att tvinga mottagarens verifiering inom tjänsten när du har lagt till mottagarna måste du ange domäntypen till Auktoritativ. Mer information om DBEB finns i Använda [katalogbaserad gränsblockering för att avvisa meddelanden som skickas till ogiltiga mottagare.](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Steg 3: Använda EAC för att konfigurera e-postflöde

Skapa kopplingar i Exchange (EAC) som aktiverar e-postflödet mellan EOP och de lokala e-postservrarna. Detaljerade instruktioner finns i Konfigurera [kopplingar för att dirigera e-post mellan Microsoft 365 och dina egna e-postservrar.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail)

### <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Kontrollera e-postflödet mellan tjänsten och din miljö. Mer information finns i [Testa e-postflöde genom att verifiera Microsoft 365-anslutningarna](/exchange/mail-flow-best-practices/test-mail-flow).

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Steg 4: Tillåt inkommande port 25 SMTP-åtkomst

Vänta i 72 timmar efter att du har konfigurerat kopplingar för att tillåta spridning av DNS-postuppdateringar. Här begränsar du inkommande SMTP-trafik med port-25 i brandväggen eller e-postservrarna så att de bara accepterar e-post från EOP-datacenter, särskilt från DE IP-adresser som anges [Exchange Online Protection IP-adresser.](../../enterprise/urls-and-ip-address-ranges.md) Det här skyddar din lokala miljö genom att begränsa omfattningen av inkommande meddelanden som du kan ta emot. Om du dessutom har inställningar på e-postservern som styr vilka IP-adresser som tillåts ansluta för e-postrelä, uppdaterar du även de inställningarna.

> [!TIP]
> Konfigurera inställningar på SMTP-servern med en anslutningstid av 60 sekunder. Den här inställningen är godtagbar för de flesta situationer, till exempel för en viss fördröjning vid ett meddelande som skickas med en stor bifogad fil.

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Steg 5: Kontrollera att skräppost skickas till varje användares skräppostmapp

Om du vill se till att skräppost dirigeras korrekt till användarnas skräppostmappar måste du utföra några konfigurationssteg. Stegen finns i Konfigurera [fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer.](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)

Om du inte vill flytta meddelanden till varje användares skräppostmapp kan du välja en annan åtgärd genom att redigera principerna för skräppostskydd. Mer information finns i [Konfigurera principer för skräppostskydd i Office 365](configure-your-spam-filter-policies.md).

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Steg 6: Använd Microsoft 365 för att peka MX-posten på EOP

Följ domänkonfigurationsstegen för att uppdatera MX-posten för domänen, så att din inkommande e-post flödar via EOP. Se till att du pekar MX-posten direkt till EOP i motsats till att ha en tredje parts filtreringstjänst för e-post till EOP. Mer information finns i Skapa [DNS-poster för Office 365.](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)

> [!NOTE]
> Om du måste peka MX-posten på en annan server eller tjänst som finns framför EOP går du till Utökad filtrering för [kopplingar i Exchange Online.](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

### <a name="how-do-you-know-this-task-worked"></a>Hur vet du att den här uppgiften fungerade?

Nu har du verifierat tjänstleveransen för en korrekt konfigurerad utgående lokal koppling och du har kontrollerat att MX-posten pekar på EOP. Du kan nu välja att köra följande ytterligare tester för att verifiera att ett e-postmeddelande kommer att levereras av tjänsten till din lokala miljö:

- Kontrollera e-postflödet mellan tjänsten och din miljö. Mer information finns i [Testa e-postflöde genom att verifiera Microsoft 365-anslutningarna](/exchange/mail-flow-best-practices/test-mail-flow).

- Skicka ett e-postmeddelande från ett webbaserat e-postkonto till en e-postmottagare i organisationen vars domän matchar den domän som du lade till i tjänsten. Bekräfta leveransen av meddelandet till den lokala postlådan med hjälp av Microsoft-Outlook eller en annan e-postklient.

- Om du vill köra ett utgående e-posttest kan du skicka ett e-postmeddelande från en användare i organisationen till ett webbaserat e-postkonto och bekräfta att meddelandet tas emot.

> [!TIP]
> När du är klar med konfigurationen behöver du inte utföra några extra steg för att ta bort skräppost och skadlig programvara med EOP. EOP tar bort skräppost och skadlig programvara automatiskt. Du kan dock finjustera inställningarna utifrån dina affärskrav. Mer information finns i Skydd mot skräppost och skydd mot skadlig [programvara i EOP](anti-spam-and-anti-malware-protection.md) och Skydd mot [nätfiske i Microsoft 365.](anti-phishing-protection.md)
>
> Nu när tjänsten körs rekommenderar vi att du läser Metodtips för att konfigurera [EOP](best-practices-for-configuring-eop.md), som beskriver rekommenderade inställningar och överväganden för när du har konfigurerat EOP.