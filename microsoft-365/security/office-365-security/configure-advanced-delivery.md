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
ms.openlocfilehash: deaad11b6397cd53017c0972a624b67a9623887f
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879114"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a>Konfigurera leverans av nätfiskebedrägerier från tredje part till användare och ofiltrerade meddelanden till SecOps-postlådor

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Funktionen som beskrivs i den här artikeln är i förhandsversion, är inte tillgänglig för alla och kan komma att ändras.

För att hålla [organisationen](secure-by-default.md)säker som standard tillåter Exchange Online Protection (EOP) inte säkra listor eller filtreringsförkoppling för meddelanden som identifieras som skadlig kod eller nätfiske med hög konfidens. Men det finns särskilda scenarier som kräver leverans av ofiltrerade meddelanden. Till exempel:

- **Nätfiskebedrägerier från tredje** part : Simulerade attacker kan hjälpa dig att identifiera sårbara användare innan en verklig attack påverkar din organisation.
- **Säkerhetsåtgärder (SecOps)-postlådor:** Dedikerade postlådor som används av säkerhetsteam för att samla in och analysera ofiltrerade meddelanden (både bra och dåliga).

Du använder principen _för avancerad leverans i_ Microsoft 365 förhindra att dessa meddelanden i dessa specifika _scenarier_ filtreras. <sup>\*</sup> Med principen för avancerad leverans säkerställer du att meddelanden i följande scenarier uppnår följande resultat:

- Filter i EOP och Microsoft Defender för Office 365 inga åtgärder vidtas på dessa meddelanden.<sup>\*</sup>
- [ZAP (Zero-hour Purge)](zero-hour-auto-purge.md) för skräppost och nätfiske åtgärdar inte dessa meddelanden.<sup>\*</sup>
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

- Du öppnar Microsoft 365 Defender-portalen på <https://security.microsoft.com> . Gå direkt till sidan **Avancerad leverans** genom att öppna <https://security.microsoft.com/advanceddelivery> .

- Du måste ha tilldelats behörigheter innan du kan utföra procedurerna i den här artikeln:
  - Om du vill skapa, ändra eller ta bort konfigurerade inställningar i  den avancerade leveransprincipen måste du vara medlem i  rollgruppen Säkerhetsadministratör i **Microsoft 365 Defender-portalen** och vara medlem i rollgruppen Organisationshantering i **Exchange Online.**  
  - För skrivskyddade åtkomst till avancerade leveransprinciper måste du vara medlem i rollgrupperna **Global Reader** **eller Säkerhetsläsare.**

  Mer information finns i [Behörigheter i Microsoft 365 Defender-portalen](permissions-microsoft-365-security-center.md) och [Behörigheter i Exchange Online.](/exchange/permissions-exo/permissions-exo)

  > [!NOTE]
  > Om du lägger till användare i Azure Active Directory-rollen får användarna de behörigheter  som krävs i Microsoft 365 Defender-portalen samt behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).

## <a name="use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a>Använd Microsoft 365 Defender-portalen för att konfigurera SecOps-postlådor i den avancerade leveransprincipen

1. I Microsoft 365 Defender-portalen går du till avsnittet & för **e&** eller regler för \>  \>  \>  \> **hotprinciper.**

2. På sidan **Advanced delivery** kontrollerar du att **secOps-postlådefliken** är markerad och gör sedan något av följande:
   - Klicka ![ på Redigera-ikonen ](../../media/m365-cc-sc-edit-icon.png) **Redigera.**
   - Om det inte finns några konfigurerade nätfiskebedrägerier klickar du på **Lägg till**.

3. På den **utfäll plats** för Redigera sekOps-postlådor som öppnas anger du en befintlig Exchange Online-postlåda som du vill ange som SecOps-postlåda genom att göra något av följande:
   - Klicka i rutan, lös listan över postlådor och välj sedan postlådan.
   - Klicka i rutan och skriv en identifierare för postlådan (namn, visningsnamn, alias, e-postadress, kontonamn osv.) och välj postlådan (visningsnamn) i resultatet.

     Upprepa det här steget så många gånger det behövs. Distributionsgrupper tillåts inte.

     Om du vill ta bort ett befintligt värde klickar du Ta bort ![Ta bort-ikonen](../../media/m365-cc-sc-remove-selection-icon.png) bredvid värdet.

4. Klicka på **Spara** när du är klar.

Postlådepostlådorna för SecOps som du har konfigurerat visas på **fliken SecOps-postlåda.** Om du vill göra ändringar klickar ![ du på ](../../media/m365-cc-sc-edit-icon.png) **Redigera-ikonen** Redigera på fliken.

## <a name="use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>Använd Microsoft 365 Defender-portalen för att konfigurera nätfiskebedrägerier från tredje part i den avancerade leveranspolicyn

1. I Microsoft 365 Defender-portalen går du till avsnittet & för **e&** eller regler för \>  \>  \>  \> **hotprinciper.**

2. På sidan **Avancerad leverans** väljer du fliken **Phishing simulering** och gör sedan något av följande:
   - Klicka ![ på Redigera-ikonen ](../../media/m365-cc-sc-edit-icon.png) **Redigera.**
   - Om det inte finns några konfigurerade nätfiskebedrägerier klickar du på **Lägg till**.

3. På den **utfällande menyn Redigera nätfiske** från tredje part som öppnas konfigurerar du följande inställningar:

   - **Skicka domän:** Utöka den här inställningen och ange minst en e-postadressdomän (till exempel contoso.com) genom att klicka i rutan, ange ett värde och sedan trycka på Retur eller välja värdet som visas under rutan. Upprepa det här steget så många gånger det behövs. Du kan lägga till upp till 10 poster.
   - **Skicka IP:** Utöka den här inställningen och ange minst en giltig IPv4-adress genom att klicka i rutan, ange ett värde och sedan trycka på Retur eller välja värdet som visas under rutan. Upprepa det här steget så många gånger det behövs. Du kan lägga till upp till 10 poster. Giltiga värden är:
     - Enskild IP: Till exempel 192.168.1.1.
     - IP-intervall: Till exempel 192.168.0.1-192.168.0.254.
     - CIDR IP: Till exempel 192.168.0.1/25.
   - **Simulerings-URL:er** som ska tillåtas: Utöka den här inställningen och ange eventuellt specifika URL-adresser som är en del av din phishing-simuleringskampanj som inte ska blockeras eller detoneras genom att klicka i rutan, ange ett värde och sedan trycka på Retur eller välja värdet som visas under rutan. Du kan lägga till upp till 10 poster.

   Om du vill ta bort ett befintligt värde klickar du Ta bort ![Ta bort-ikonen](../../media/m365-cc-sc-remove-selection-icon.png) bredvid värdet.

4. Gör något av följande när du är klar:
   - **Första gången:** Klicka **på Lägg** till och sedan på **Stäng.**
   - **Redigera befintligt:** Klicka **på Spara** och sedan på **Stäng.**

De simuleringsposter för nätfiske från tredje part som du har konfigurerat visas på fliken **Nätfiskebedrägerier.** Om du vill göra ändringar klickar ![ du på ](../../media/m365-cc-sc-edit-icon.png) **Redigera-ikonen** Redigera på fliken.

## <a name="additional-scenarios-that-require-filtering-bypass"></a>Ytterligare scenarier som kräver förbikoppling av filtrering

Utöver de två scenarier som den avancerade leveransprincipen kan hjälpa dig med finns det andra scenarier som kan innebära att du måste kringgå filtrering:

- **Filter från tredje part:** Om domänens MX-post inte pekar på Office 365 (meddelanden dirigeras någon annanstans [först)](secure-by-default.md) är säker som standard *inte tillgänglig.* 

  Om du vill kringgå Microsoft-filtrering för meddelanden som redan har utvärderats av filtrering från tredje part använder du e-postflödesregler (kallas även transportregler). Mer information finns i Använda [e-postflödesregler för att ange SCL i meddelanden.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md)

- **Falska** positiva resultat under granskning: Du kanske tillfälligt vill tillåta att vissa meddelanden som fortfarande analyseras av Microsoft via administratörer rapporterar kända bra meddelanden som felaktigt [markeras](admin-submission.md) som dåliga för Microsoft (falska positiva resultat). Precis som med alla åsidosättningar rekommenderar **_vi att_** dessa tillåtna produkter är tillfälliga.
