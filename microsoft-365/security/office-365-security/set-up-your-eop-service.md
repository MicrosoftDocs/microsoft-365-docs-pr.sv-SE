---
title: Konfigurera din fristående EOP-tjänst
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
ms.assetid: d74c6ddf-11b0-43ee-b298-8bb0340895f0
description: Administratörer kan läsa mer om hur du installerar ett fristående Exchange Online Protection (EOP) för att skydda lokala e-postmiljöer.
ms.openlocfilehash: 2d63057e77e6965616e19452de824a94ba0ccda8
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659423"
---
# <a name="set-up-your-standalone-eop-service"></a>Konfigurera din fristående EOP-tjänst

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


I det här avsnittet förklaras hur du konfigurerar fristående Exchange Online Protection (EOP). Om du kommer hit från guiden Office 365-domäner går du tillbaka till guiden för Office 365-domäner om du inte vill använda Exchange Online Protection. Om du vill ha mer information om hur du konfigurerar anslutningar kan du läsa [Konfigurera e-postflöde med kopplingar i Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

> [!NOTE]
> I det här avsnittet förutsätts det att du har lokala post lådor och du vill skydda dem med EOP, som kallas ett fristående scenario. Om du vill hantera alla dina post lådor i molnet med Exchange Online behöver du inte göra alla steg i den här artikeln. Gå till [Jämför Exchange Online-abonnemang](https://products.office.com/exchange/compare-microsoft-exchange-online-plans) för att registrera dig och köpa moln post lådor.
>
> Om du vill använda en del av dina post lådor på lokala platser och i molnet, kallas detta ett hybrid scenario. Det kräver mer avancerade inställningar för e-postflöde. Med [hybrid distributioner av Exchange Server](https://docs.microsoft.com/exchange/exchange-hybrid) förklaras hybrid meddelanden och länkar till resurser som visar hur du ställer in det.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Uppskattad tid för att slutföra uppgiften: 1 timme

- Du måste ha behörighet i Exchange Online Protection innan du kan göra det i den här artikeln. Specifikt behöver du rollen **Remote och godkände Domains** , som tilldelats roll grupperna **organisations hantering** (globala administratörer) och **administratör för e-postflöde** . Mer information finns i [behörigheter i fristående EOP](feature-permissions-in-eop.md) och [Använd UK för att ändra listan över medlemmar i roll grupper](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Om du inte har registrerat dig för EOP kan du gå till [Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection) och välja att köpa eller prova tjänsten.

- Information om kortkommandon som kan gälla för procedurerna i den här artikeln finns i kortkommandon [för administrations centret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Har du problem? Be om hjälp i [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Steg 1: Använd administrations centret för Microsoft 365 för att lägga till och verifiera din domän

1. I [administrations centret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/admin-overview/about-the-admin-center)går du till **Konfigurera** för att lägga till domänen i tjänsten.

2. Följ stegen för att lägga till de DNS-poster som är tillämpliga på din DNS-värd för att verifiera domänens ägarskap.

> [!TIP]
> [Lägga till en domän i Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) och [Skapa DNS-poster på vilken DNS-värd som helst för Office 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) är användbart resurser att hänvisa till när du lägger till domänen till tjänsten och konfigurerar DNS.

## <a name="step-2-add-recipients-and-optionally-enable-dbeb"></a>Steg 2: Lägg till mottagare och aktivera eventuellt DBEB

Innan du konfigurerar din e-post som ska flöda till och från EOP-tjänsten rekommenderar vi att du lägger till mottagarna i tjänsten. Det finns flera sätt som du kan göra det på, som dokumenterade i [Hantera e-postanvändare i EOP](manage-mail-users-in-eop.md). Om du vill aktivera Directory-baserad Edge-blockering (DBEB) för att tvinga mottagar verifiering i tjänsten efter att du har lagt till mottagarna måste du ange domän typen till auktoritär. Mer information om DBEB finns i [använda katalogbaserade kant spärr för att neka meddelanden skickade till ogiltiga mottagare](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Steg 3: använda UK för att konfigurera e-postflöde

Skapa kopplingar i administrations centret för Exchange (UK) som möjliggör e-postflöde mellan EOP och dina lokala e-postservrar. Detaljerade anvisningar finns i [Konfigurera kopplingar för att dirigera e-post mellan Microsoft 365 och dina egna e-postservrar](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail).

### <a name="how-do-you-know-this-task-worked"></a>Hur vet jag att den här uppgiften fungerade?

Kontrol lera e-postflödet mellan tjänsten och din miljö. Mer information finns i [Testa e-postflöde genom att verifiera dina Microsoft 365-kopplingar](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Steg 4: Tillåt inkommande port 25 SMTP-åtkomst

När du har konfigurerat kopplingar väntar du 72 timmar för att tillåta spridning av DNS-postuppdateringarna. Därefter kan du begränsa inkommande port-25 SMTP-trafik på din brand vägg eller e-postserver så att den endast accepterar e-post från EOP Data Center, särskilt från IP-adresserna som visas i [Exchange Online Protection IP-adresser](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges). Då skyddas den lokala miljön genom att begränsa omfattningen av inkommande meddelanden som du kan ta emot. Om du har inställningar på din e-postserver som styr vilka IP-adresser som är tillåtna för att ansluta till e-post kan du även uppdatera dessa inställningar.

> [!TIP]
> Konfigurera inställningar på SMTP-servern med en anslutnings tid på 60 sekunder. Den här inställningen är acceptabel i de flesta fall och gör det möjligt för en viss fördröjning om ett meddelande skickas med en stor bifogad fil.

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Steg 5: kontrol lera att skräp post vidarebefordras till varje användares mapp för skräp post

För att säkerställa att skräp post meddelanden vidarebefordras korrekt till varje användares skräppost-mapp måste du utföra några olika konfigurations steg. Anvisningarna finns i [Konfigurera fristående EOP för att skicka skräp post till skräppostmappen i hybrid miljöer](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

Om du inte vill flytta meddelanden till varje användares skräppost-mapp kan du välja en annan åtgärd genom att redigera principer för skräp post. Mer information finns i [Konfigurera principer för skräppostskydd i Office 365](configure-your-spam-filter-policies.md).

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Steg 6: Använd administrations centret för Microsoft 365 för att peka din MX-post på EOP

Följ stegen i domän konfigurationen för att uppdatera MX-posten för din domän så att din inkommande e-post genom EOP. Se till att du pekar din MX-post direkt till EOP i stället för att ha ett e-postmeddelande med filter tjänsten från tredje part till EOP. Om du vill ha mer information kan du återigen referera till [Skapa DNS-poster för Office 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

> [!NOTE]
> Om du måste peka din MX-post på en annan server eller tjänst som finns framför EOP läser du [förbättrad filtrering för kopplingar i Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

### <a name="how-do-you-know-this-task-worked"></a>Hur vet jag att den här uppgiften fungerade?

I det här läget har du bekräftat tjänste leverans för en korrekt konfigurerad utgående lokal koppling, och du har verifierat att din MX-post pekar på EOP. Du kan välja att köra följande ytterligare test för att verifiera att ett e-postmeddelande kommer att skickas till din lokala miljö:

- Kontrol lera e-postflödet mellan tjänsten och din miljö. Mer information finns i [Testa e-postflöde genom att verifiera dina Microsoft 365-kopplingar](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).

- Skicka ett e-postmeddelande från ett webbaserat e-postkonto till en e-postmottagare i din organisation vars domän matchar den domän som du har lagt till i tjänsten. Bekräfta leverans av meddelandet till den lokala post lådan med hjälp av Microsoft Outlook eller en annan e-postklient.

- Om du vill köra ett utgående e-PostTest kan du skicka ett e-postmeddelande från en användare i din organisation till ett webbaserat e-postkonto och bekräfta att meddelandet har tagits emot.

> [!TIP]
> När du har slutfört installationen behöver du inte utföra några extra steg för att göra EOP för att ta bort skräp post och skadlig program vara. EOP tar bort skräp post och malware automatiskt. Men du kan finjustera dina inställningar utifrån dina företags behov. Mer information finns i [anti-spam och skydd mot skadlig program vara i Office 365](anti-spam-and-anti-malware-protection.md) och [Konfigurera förfalsknings information](learn-about-spoof-intelligence.md).
>
> Nu när din tjänst körs rekommenderar vi att du läser [metod tips för att konfigurera EOP](best-practices-for-configuring-eop.md), som beskriver rekommenderade inställningar och överväganden när du har konfigurerat EOP.
