---
title: Nya användare vidarebefordrar insikt via e-post
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: Administratörer kan lära sig att använda de nya användarnas information om vidarebefordran av e-post i säkerhets- och efterlevnadscentret för & för att undersöka när användare i organisationen vidarebefordrar meddelanden till nya domäner.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 807df82ca80e851554db7b8f373a5ca4af02a391
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207241"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a>Nya användare som vidarebefordrar e-postinsikter i & Säkerhets- och efterlevnadscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Det är misstänkt när nya användarkonton i organisationen plötsligt börjar vidarebefordra e-postmeddelanden till externa domäner.

De nya domäner som [&](https://protection.office.com) **vidarebefordras** e-postinsikter i Säkerhets- och efterlevnadscenter meddelar dig när nya användare i organisationen vidarebefordrar meddelanden till externa domäner. Detta villkor kan ange att komprometterade administratörskonton användes för att skapa de nya användarna. Om du misstänker att kontona har komprometterats kan du [gå till Svara på ett komprometterat e-postkonto.](responding-to-a-compromised-email-account.md)

Den här insikten visas bara när problemet identifieras och visas på [sidan Vidarebefordransrapport.](view-mail-flow-reports.md#forwarding-report)

![Nya användare vidarebefordrar insikt via e-post](../../media/mfi-new-users-forwarding-email.png)

När du klickar på widgeten visas en utfällningsruta där du kan hitta [](#forwarding-modifications-report) mer information om vidarebefordrade meddelanden, inklusive en länk till rapporten om ändringar av vidarebefordran som beskrivs senare i den här artikeln.

![Den utfällande informationen för Information som visas när du klickar på e-postinsikten Nya användare som vidarebefordrar e-post](../../media/mfi-new-users-forwarding-email-details.png)

Du kan också gå till den här informationssidan  när du väljer insikten när du har klickat på Visa alla i området **& rekommendationer** på (**Instrumentpanelen** \> **Rapporter** eller <https://protection.office.com/insightdashboard> ).

Du kan klicka på **länken Visa rapport kopplad till insikt** om du vill gå till rapporten Om du vill vidarebefordra ändringar **enligt** beskrivningen i nästa avsnitt.

## <a name="forwarding-modifications-report"></a>Rapporten Om att vidarebefordra ändringar

Rapporten **Vidarebefordra ändringar visar** information om meddelanden som vidarebefordras automatiskt från avsändare i organisationen:

- Nyligen skapade konton som vidarebefordrar meddelanden till externa domäner.
- Konton som vidarebefordrar meddelanden till externa domäner som aldrig har vidarebefordrats till av andra avsändare i organisationen.

Den här typen av vidarebefordrade meddelanden kan utgöra en säkerhets- eller efterlevnadsrisk och kan indikera komprometterade konton.

Rapporten innehåller data för upp till 90 dagar. Som standard visas data för de senaste 7 dagarna i rapporten.

Den här rapporten är inte direkt tillgänglig på instrumentpanelen [för e-postflöde](mail-flow-insights-v2.md) eller i [instrumentpanelen Rapporter.](view-mail-flow-reports.md) Förutom att klicka på länken Visa rapport  kopplad till **insikt** i Nya användare som vidarebefordrar e-postinsikter, kommer du till rapporten genom att:

- Klicka på **länken Vidarebefordran av meddelanden i** rapporten i informationen om de nya domäner som [vidarebefordras e-postinsikter.](mfi-new-domains-being-forwarded-email.md)
- Öppna <https://protection.office.com/reportv2?id=MailFlowNewForwarding> .

### <a name="report-view-for-the-forwarding-modifications-report"></a>Rapportvy för rapporten Ändringar av vidarebefordran

Följande diagram är tillgängliga i rapportvyn:

- **Visa data för: Nya användare av vidarebefordran:**

  ![Ny vy för vidarebefordran av användare i rapporten Om vidarebefordran av ändringar](../../media/forwarding-modifications-report-new-forwarding-users.png)

- **Visa data för: Nya domäner för vidarebefordran:**

  ![Ny vy för vidarebefordrade domäner i rapporten Ändringar av vidarebefordran](../../media/forwarding-modifications-report-new-forwarded-domains.png)

Om du klickar **på** Filter i en rapportvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**

### <a name="details-table-view-for-the-forwarding-modifications-report"></a>Detaljtabellvyn för rapporten Om vidarebefordran av ändringar

Om du **klickar på Visa** informationstabell beror den information som visas på det diagram som du tittar på:

- **Visa data för: Nya användare av vidarebefordran:**

  - **Namn:** Avsändarens e-postadress.
  - **Vidarebefordranstyp**
  - **Mottagaradress**
  - **Information**
  - **Antal**
  - **Första forwardsdatumet**

- **Visa data för: Nya domäner för vidarebefordran:**

  - **Namn:** Avsändarens e-postdomän.
  - **Vidarebefordranstyp**
  - **Mottagaradress**
  - **Information**
  - **Antal**
  - **Första forwardsdatumet**

Om du klickar **på** Filter i en detaljtabellvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**

Om du väljer en rad  i tabellen visas den utfällade informationen Information med följande information:

- **Namn:** Det här är antingen avsändarens e-postadress (från Visa **data för:** Vyn Nya användare för vidarebefordran) eller avsändarens e-postdomän (från Visa **data för:** Vyn Nya domäner för vidarebefordran).
- **Vidarebefordranstyp**
- **Mottagare**
- **Information**
- **Antal**
- **Startdatum**
- **Rekommendation:** Härifrån kan du klicka på länken för att hantera användaren Microsoft 365 administrationscentret.

![Den utfällande informationen från detaljtabellen i vyn Nya användare för vidarebefordran i rapporten Om vidarebefordran](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

Om du vill gå tillbaka till rapportvyn klickar du **på Visa rapport**.

## <a name="related-topics"></a>Relaterade ämnen

Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinformation i Säkerhets- & efterlevnadscenter.](mail-flow-insights-v2.md)
