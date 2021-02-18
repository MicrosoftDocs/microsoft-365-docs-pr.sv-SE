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
description: Administratörer kan ta reda på hur de kan använda information om vidarebefordran av e-post i Säkerhets- & och efterlevnadscenter för att undersöka när användare i organisationen vidarebefordrar meddelanden till nya domäner.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9706951df480d07f4a6311e99cab5c9f404e999e
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290827"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a>Nya användare som vidarebefordrar e-postinsikter i Säkerhets- & Efterlevnadscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Det är misstänkt när nya användarkonton i organisationen plötsligt börjar vidarebefordra e-postmeddelanden till externa domäner.

De **nya domäner som** vidarebefordras i Säkerhets- & [och](https://protection.office.com) efterlevnadscenter meddelar dig när nyligen skapade användare i organisationen vidarebefordrar meddelanden till externa domäner. Det här villkoret kan ange att komprometterade administratörskonton användes för att skapa nya användare. Om du misstänker att kontona har komprometterats kan du gå [till Svara på ett komprometterat e-postkonto.](responding-to-a-compromised-email-account.md)

Den här insikten visas bara när problemet identifieras och visas på [sidan Med vidarebefordransrapport.](view-mail-flow-reports.md#forwarding-report)

![Nya användare vidarebefordrar insikt via e-post](../../media/mfi-new-users-forwarding-email.png)

När du klickar på widgeten visas en utfällig meny där du kan [](#forwarding-modifications-report) hitta mer information om vidarebefordrade meddelanden, inklusive en länk till rapporten om ändringar av vidarebefordran, som beskrivs senare i den här artikeln.

![Information som visas när du klickar på information för vidarebefordran av e-post för nya användare](../../media/mfi-new-users-forwarding-email-details.png)

Du kan också gå till den här informationssidan  när du väljer insikten när du har klickat på Visa allt i området **& rekommendationer** **på** (Instrumentpanelen Rapporter \>  <https://protection.office.com/insightdashboard> eller).

Du kan klicka på **länken Visa rapport som är** kopplad till insikter om du vill gå till rapporten om ändringar i **vidarebefordran** enligt beskrivningen i nästa avsnitt.

## <a name="forwarding-modifications-report"></a>Rapporten Om att vidarebefordra ändringar

I **rapporten Ändringar av vidarebefordran** visas information om meddelanden som vidarebefordras automatiskt från avsändare i organisationen:

- Nyligen skapade konton som vidarebefordrar meddelanden till externa domäner.
- Konton som vidarebefordrar meddelanden till externa domäner som inte har vidarebefordrats till av andra avsändare i organisationen.

Den här typen av vidarebefordrade meddelanden kan utgöra en säkerhets- eller efterlevnadsrisk och kan indikera komprometterade konton.

Rapporten innehåller data för upp till 90 dagar. Som standard visar rapporten data för de senaste 7 dagarna.

Den här rapporten är inte direkt tillgänglig på instrumentpanelen för [e-postflöde](mail-flow-insights-v2.md) eller i [instrumentpanelen Rapporter.](view-mail-flow-reports.md) Förutom att klicka på länken Visa rapport  som är **kopplad** till insikter i den nya användare som vidarebefordrar e-postinsikter, kommer du till rapporten genom att:

- Klicka på **länken med rapporten om vidarebefordran av** meddelanden i informationen om de nya domäner som [vidarebefordras.](mfi-new-domains-being-forwarded-email.md)
- Öppna <https://protection.office.com/reportv2?id=MailFlowNewForwarding> .

### <a name="report-view-for-the-forwarding-modifications-report"></a>Rapportvy för rapporten Om att vidarebefordra ändringar

Följande diagram är tillgängliga i rapportvyn:

- **Visa data för: Nya vidarebefordran av användare:**

  ![Ny vy för vidarebefordran av användare i rapporten Om vidarebefordran](../../media/forwarding-modifications-report-new-forwarding-users.png)

- **Visa data för: Nya domäner för vidarebefordran:**

  ![Ny vy för vidarebefordrade domäner i rapporten om ändringar av vidarebefordran](../../media/forwarding-modifications-report-new-forwarded-domains.png)

Om du klickar **på** Filter i en rapportvy kan du ange ett datumintervall **med startdatum** **och slutdatum.**

### <a name="details-table-view-for-the-forwarding-modifications-report"></a>Detaljtabellvy för rapporten Om att vidarebefordra ändringar

Om du **klickar på Tabellen** Visa information beror den information som visas på det diagram som du visade:

- **Visa data för: Nya vidarebefordran av användare:**

  - **Namn:** Avsändarens e-postadress.
  - **Vidarebefordranstyp**
  - **Mottagaradress**
  - **Information**
  - **Antal**
  - **Första vidarebefordransdatum**

- **Visa data för: Nya domäner för vidarebefordran:**

  - **Namn:** Avsändarens e-postdomän.
  - **Vidarebefordranstyp**
  - **Mottagaradress**
  - **Information**
  - **Antal**
  - **Första vidarebefordransdatum**

Om du klickar **på** Filter i en detaljtabellvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**

Om du väljer en rad i tabellen visas **en** utfälltabell med följande information:

- **Namn:** Det här är antingen avsändarens e-postadress (från Visa **data för:** Vyn Nya vidarebefordran av användare) eller avsändarens e-postdomän (från Visa **data för:** vyn Nya domäner för vidarebefordran).
- **Vidarebefordranstyp**
- **Mottagare**
- **Information**
- **Antal**
- **Startdatum**
- **Rekommendation:** Härifrån kan du klicka på länken för att hantera användaren i administrationscentret för Microsoft 365.

![Den utfällna informationen från detaljtabellen i vyn Nya användare för vidarebefordran i rapporten Om vidarebefordran](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

Om du vill gå tillbaka till rapportvyn klickar du **på Visa rapport.**

## <a name="related-topics"></a>Relaterade ämnen

Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinsikter i Säkerhets- & Efterlevnadscenter.](mail-flow-insights-v2.md)
