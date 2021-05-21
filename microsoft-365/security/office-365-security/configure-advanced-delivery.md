---
title: Konfigurera leverans av nätfiskebedrägerier från tredje part till användare och ofiltrerade meddelanden till SecOps-postlådor
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
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Administratörer kan lära sig att använda den avancerade leveransprincipen i Exchange Online Protection (EOP) för att identifiera meddelanden som inte ska filtreras i specifika scenarier som stöds (nätfiskebedrägerier från tredje part och meddelanden som levereras till säkerhetsåtgärder (SecOps)-postlådor.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8bebc094b56a20a43f92d1acf8d374110de43d71
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/21/2021
ms.locfileid: "52594127"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a>Konfigurera leverans av nätfiskebedrägerier från tredje part till användare och ofiltrerade meddelanden till SecOps-postlådor

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Funktionen som beskrivs i den här artikeln är i förhandsversion, är inte tillgänglig för alla och kan komma att ändras.

För att [](secure-by-default.md)hålla organisationen säker som standard tillåter Exchange Online Protection (EOP) inte säkra listor eller filtrering av förbikoppling för meddelanden som resulterar i skadlig kod eller nätfiskeförsök med hög konfidens. Men det finns särskilda scenarier som kräver leverans av ofiltrerade meddelanden. Till exempel:

- **Nätfiskebedrägerier från tredje** part : Simulerade attacker kan hjälpa dig att identifiera sårbara användare innan en verklig attack påverkar din organisation.
- **Säkerhetsåtgärder (SecOps)-postlådor:** Dedikerade postlådor som används av säkerhetsteam för att samla in och analysera ofiltrerade meddelanden (både bra och dåliga).

Du använder principen _för avancerad leverans i_ Microsoft 365 för att förhindra att dessa meddelanden i dessa specifika _scenarier_ <sup>\*</sup> filtreras. Med principen för avancerad leverans säkerställs att meddelanden i följande scenarier inte filtreras:

- Filter i EOP och Microsoft Defender för Office 365 inga åtgärder vidtas på dessa meddelanden.<sup>\*</sup>
- [ZAP (Zero-hour Purge)](zero-hour-auto-purge.md) för skräppost och nätfiske vidtar ingen åtgärd för dessa meddelanden.<sup>\*</sup>
- [Standardsystemaviseringar](alerts.md) utlöses inte för dessa scenarier.
- [AIR och clustering i Defender för Office 365](office-365-air.md) ignorerar dessa meddelanden.
- Särskilt för nätfiskebedrägerier från tredje part:
  - [Administratörsinskick](admin-submission.md) genererar ett automatiskt svar som säger att meddelandet är en del av en phishing-simuleringskampanj och inte är ett riktigt hot. Aviseringar och AIR utlöses inte.
  - [Valv i Defender för Office 365](safe-links.md) blockeras eller avaktiverar inte de specifikt identifierade webbadresserna i dessa meddelanden.
  - [Valv i Defender för Office 365](safe-attachments.md) avaktiverar inte bifogade filer i dessa meddelanden.

<sup>\*</sup> Du kan inte kringgå filtrering av skadlig programvara eller ZAP för skadlig programvara.

Meddelanden som identifieras av den avancerade leveranspolicyn är inte säkerhetshot, så meddelandena markeras som system åsidosätter. Administratörer kan filtrera och analysera dessa system åsidosättningar i följande funktioner:

- [Hotutforskaren/identifieringar i realtid i Defender för Office 365 abonnemang 2](threat-explorer.md)
- Sidan [E-post entitet i Hotutforskaren/realtidsidentifiering](mdo-email-entity-page.md)
- Statusrapport [för skydd mot hot](view-email-security-reports.md#threat-protection-status-report)
- [Avancerad sökning i Microsoft Defender för Slutpunkt](../defender-endpoint/advanced-hunting-overview.md)
- [Kampanjvyer](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Gå direkt till sidan **Avancerad leverans** genom att öppna <https://protection.office.com/advanceddelivery> .

- Du måste ha tilldelats behörigheter innan du kan utföra procedurerna i den här artikeln:
  - Om du vill skapa, ändra eller ta bort konfigurerade inställningar i  den avancerade leveransprincipen måste du vara medlem i  rollgruppen Säkerhetsadministratör i Säkerhets- och efterlevnadscenter **för &** och medlem i rollgruppen Organisationshantering i **Exchange Online.**  
  - För skrivskyddade åtkomst till avancerade leveransprinciper måste du vara medlem i rollgrupperna **Global Reader** **eller Säkerhetsläsare.**

  Mer information finns i [Behörigheter i Säkerhets- & säkerhets- och](permissions-in-the-security-and-compliance-center.md) [behörighetscenter i Exchange Online.](/exchange/permissions-exo/permissions-exo)

## <a name="use-the-security--compliance-center-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>Använd Säkerhets- & efterlevnadscenter för att konfigurera nätfiskebedrägerier från tredje part i den avancerade leveranspolicyn

1. I Säkerhets- & säkerhets- och efterlevnadscenter går du **till Avancerad leverans av** \>  \> **hothanteringspolicy.**

2. På sidan **Avancerad leverans** väljer du fliken Phishing **simulering** och klickar sedan på **Redigera**.

3. Konfigurera följande **inställningar på den utfällbaserade** utfällningen av nätfiske från tredje part som öppnas:

   - **Skicka domän:** Minst en e-postadressdomän krävs (till exempel contoso.com). Du kan lägga till upp till 10 poster.
   - **Skicka IP:** Minst en giltig IPv4-adress krävs. Du kan lägga till upp till 10 poster. Giltiga värden är:
     - Enskild IP: Till exempel 192.168.1.1.
     - IP-intervall: Till exempel 192.168.0.1-192.168.0.254.
     - CIDR IP: Till exempel 192.168.0.1/25.
   - **Simulerings-URL:er som** ska tillåtas : Du kan också ange specifika URL:er som är en del av din nätfiskekampanj som inte ska blockeras eller detoneras. Du kan lägga till upp till 10 poster.

4. Klicka på Spara när du är **klar.**

De simuleringsposter för nätfiske från tredje part som du har konfigurerat visas på fliken **Nätfiskebedrägerier.** Om du vill göra ändringar **klickar du** på Redigera på fliken.

## <a name="use-the-security--compliance-center-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a>Använd Säkerhets- & kompatibilitetscenter för att konfigurera SecOps-postlådor i den avancerade leveranspolicyn

1. I Säkerhets- & efterlevnadscenter går du till **Avancerad leverans av** \>  \> **hothanteringspolicy.**

2. På sidan **Advanced delivery** väljer du fliken **SecOps mailbox** och klickar sedan på **Edit**.

3. I den **utfällklienten** för SecOps-postlådan som öppnas anger du e-postadresserna för Exchange Online postlådor som du vill ange som SecOps-postlådor. Distributionsgrupper tillåts inte.

4. Klicka på **Spara** när du är klar.

Postlådepostlådorna för SecOps som du har konfigurerat visas på **fliken SecOps-postlåda.** Om du vill göra ändringar **klickar du** på Redigera på fliken.

## <a name="additional-scenarios-that-require-filtering-bypass"></a>Ytterligare scenarier som kräver förbikoppling av filtrering

Utöver de två scenarier som den avancerade leveransprincipen kan hjälpa dig med finns det andra scenarier som kan innebära att du måste kringgå filtrering:

- **Filter från tredje part:** Om domänens MX-post inte pekar på Office 365 (meddelanden dirigeras någon annanstans [först)](secure-by-default.md) är säker som standard *inte tillgänglig.* 

  Om du vill kringgå Microsoft-filtrering för meddelanden som redan har utvärderats av filtrering från tredje part använder du e-postflödesregler (kallas även transportregler) i Använda e-postflödesregler för att ange SCL i [meddelanden.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

- **Falska** positiva resultat under granskning: Du kanske tillfälligt vill tillåta att vissa meddelanden som fortfarande analyseras av Microsoft via administratörer rapporterar kända bra meddelanden som felaktigt [markeras](admin-submission.md) som dåliga för Microsoft (falska positiva resultat). Precis som med alla åsidosättningar **_rekommenderar vi starkt_** att dessa tillägg görs tillfälligt.
