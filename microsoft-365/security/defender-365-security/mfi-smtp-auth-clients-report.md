---
title: Insikt och rapport för SMTP-autentiseringsklienter på instrumentpanelen för e-postflöde
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig att använda SMTP-autentiseringsinsikter och -rapporten i instrumentpanelen för e-postflöde i säkerhets- och efterlevnadscentret för & för att övervaka e-postavsändare i organisationen som använder autentiserad SMTP (SMTP AUTH) för att skicka e-postmeddelanden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a979f0e80fc303868bf2572974563323035fc4bc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070017"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a>Insikt och rapport för SMTP-autentiseringsklienter i Säkerhets- & efterlevnadscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Insikten **för SMTP-autentiseringsklienter** i instrumentpanelen för e-postflöde och rapporten tillhörande [SMTP-autentiseringsklienter](#smtp-auth-clients-report) i kompatibilitetscentret för [säkerhet i &](https://protection.office.com) markerar användningen av sändningsprotokoll för SMTP-AUTH-klienten för användare eller systemkonton i organisationen. [](mail-flow-insights-v2.md) Det här äldre protokollet (som använder slutpunkts-smtp.office365.com) erbjuder endast grundläggande autentisering och är känslig för användning av komprometterade konton för att skicka e-post. Med insikten och rapporten kan du kontrollera ovanlig aktivitet för sändning via SMTP AUTH-e-post. Den visar även TLS-användningsdata för klienter eller enheter som använder SMTP AUTH.

Widgeten anger antalet användare eller tjänstkonton som har använt SMTP-autentiseringsprotokoll under de senaste 7 dagarna.

![Widget för SMTP-autentiseringsklienter på instrumentpanelen för e-postflöde & Säkerhets- och efterlevnadscenter](../../media/mfi-smtp-auth-clients-report-widget.png)

Om du klickar på antalet meddelanden på widgeten visas den utfällade **menyn SMTP Auth-klienter.** Den utfällda utfällningen ger en aggregerad vy över TLS-användning och -volymer för den senaste veckan.

![Information som visas när du klickar på widgeten SMTP Auth-klienter på instrumentpanelen för e-postflöde](../../media/mfi-smtp-auth-clients-report-details.png)

Du kan klicka på **rapportlänken SMTP Auth-klienter** för att gå till rapporten SMTP Auth-klienter enligt beskrivningen i nästa avsnitt.

## <a name="smtp-auth-clients-report"></a>Rapporten SMTP Auth-klienter

### <a name="report-view-for-the-smtp-auth-clients-report"></a>Rapportvyn för rapporten SMTP Auth-klienter

Som standard visar rapporten data för de senaste 7 dagarna, men data är tillgängliga för de senaste 90 dagarna.

Översiktsavsnittet innehåller följande diagram:

- **Visa data efter: Skicka** volym: Som standard visar diagrammet antalet SMTP-klientmeddelanden som skickades från alla domäner **(Visa data för:** Alla avsändardomäner är markerat som standard). Du kan filtrera resultatet till en viss avsändardomän genom att klicka på Visa **data** för och välja avsändardomänen i listrutan. Om du hovrar över en specifik datapunkt (dag) visas antalet meddelanden.

  ![Skicka volymvyn i rapporten SMTP Auth-klienter i säkerhets- & Säkerhets- och efterlevnadscenter](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- **Visa data efter: TLS-användning:** I diagrammet visas procentandelen TLS-användning för alla meddelanden från SMTP-autentiseringsklienten under den valda tidsperioden. Med det här diagrammet kan du identifiera och vidta åtgärder på användare och systemkonton som fortfarande använder äldre versioner av TLS.

  ![Vyn TLS-användning i rapporten SMTP-autentiseringsklienter i & Säkerhets- och efterlevnadscenter](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

Om du klickar **på** Filter i en rapportvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**

Klicka **på Begär rapport** om du vill få en mer detaljerad version av rapporten i ett e-postmeddelande. Du kan ange datumintervallet och mottagarna för att ta emot rapporten.

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a>Tabellvyn Information för rapporten SMTP Auth-klienter

Om du **klickar på Visa** informationstabell beror den information som visas på det diagram som du tittar på:

- **Visa data genom: Skicka volym:** Följande information visas i en tabell:

  - **Avsändarens adress**
  - **Antal meddelanden**

  Om du markerar en rad visas samma information i en utfällbladstext.

- **Visa data efter: TLS-användning:** Följande information visas i en tabell:

  - **Avsändarens adress**
  - **TLS1,0 %**<sup>\*</sup>
  - **TLS1,1 %**<sup>\*</sup>
  - **TLS1,2 %**<sup>\*</sup>
  - **Antal meddelanden**

  <sup>\*</sup> I den här kolumnen visas både procentandelen och antalet meddelanden från avsändaren.

Om du klickar **på** Filter i en detaljtabellvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**

Om du markerar en rad visas liknande information i en utfällbladstext:

![Informationsfällblad från detaljtabellen i TLS-användningsvyn i rapporten SMTP Auth-klienter](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

Klicka **på Begär rapport** om du vill få en mer detaljerad version av rapporten i ett e-postmeddelande. Du kan ange datumintervallet och mottagarna för att ta emot rapporten.

Om du vill gå tillbaka till rapportvyn klickar du **på Visa rapport**.

## <a name="related-topics"></a>Relaterade ämnen

Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinformation i Säkerhets- & efterlevnadscenter.](mail-flow-insights-v2.md)
