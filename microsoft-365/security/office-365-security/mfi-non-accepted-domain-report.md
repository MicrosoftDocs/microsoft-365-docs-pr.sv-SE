---
title: Rapport om ej godkänd domän på instrumentpanelen för e-postflöde
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
description: Administratörer kan lära sig hur de använder rapporten Ej godkänd domän i instrumentpanelen för e-postflöde i säkerhets- och efterlevnadscentret för & för att övervaka meddelanden från den lokala organisationen där avsändarens domän inte har konfigurerats i Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fb33feb56bf2b52731c03273ce0c6444c333f348
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207297"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a>Rapport om ej godkänd domän i Säkerhets- & Säkerhets- och efterlevnadscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

I rapporten Ej godkänd [](mail-flow-insights-v2.md) domän i instrumentpanelen för e-postflöde i Säkerhets- och efterlevnadscenter för [&](https://protection.office.com) visas information om meddelanden från din lokala e-postorganisation där avsändarens domän inte är konfigurerad som en godkänd domän i din Microsoft 365-organisation. 

Microsoft 365 kan begränsa dessa meddelanden om vi har data som bevisar att avsikten med dessa meddelanden är skadliga. Därför är det viktigt att du förstår vad som händer och kan åtgärda problemet.

![Domänwidget som inte godkänts på instrumentpanelen för e-postflöde & Säkerhets- och efterlevnadscenter](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a>Rapportvy för rapporten Ej godkänd domän

Om du klickar på diagrammet **på widgeten Godkänd** inte domän kommer du till **rapporten Ej godkänd** domän.

Som standard visas aktiviteten för alla berörda kopplingar. Om du klickar **på Visa data för** kan du välja en specifik koppling i listrutan.

Om du hovrar över en datapunkt (dag) i diagrammet visas det totala antalet meddelanden för kopplingen.

![Rapportvyn i rapporten Ej godkänd domän](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a>Tabellvyn Detaljerad information för rapporten Om godkänd domän

Om du **klickar på Visa informationstabell** i en rapportvy visas följande information:

- **Datum**
- **Namn på inkommande koppling**
- **Avsändningsdomän**
- **Antal meddelanden**
- **Exempelmeddelanden:** Meddelande-ID:na för ett exempel på påverkade meddelanden.

Om du klickar **på** Filter i en detaljtabellvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**

Om du vill skicka rapporten med ett visst datumintervall till en eller flera mottagare klickar du på **Begär nedladdning.**

När du markerar en rad i tabellen visas en utfälltabell med följande information:

- **Datum**
- **Namn på inkommande koppling**
- **Avsändningsdomän**
- **Antal meddelanden**
- **Exempelmeddelanden:** Du kan klicka på **Visa exempelmeddelanden** om du vill se [resultatet av meddelandespårningen](message-trace-scc.md) för ett exempel på de berörda meddelandena.

![Information som visas när du har valt en rad i tabellvyn Information i rapporten Ej godkänd domän](../../media/mfi-non-accepted-domain-report-details-flyout.png)

Om du vill gå tillbaka till rapportvyn klickar du **på Visa rapport**.

## <a name="related-topics"></a>Relaterade ämnen

Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinformation i Säkerhets- & efterlevnadscenter.](mail-flow-insights-v2.md)
