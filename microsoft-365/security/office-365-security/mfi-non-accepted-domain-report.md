---
title: Icke-godkänd domänrapport i instrumentpanelen för e-postflöde
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
description: Administratörer kan ta reda på hur de använder rapporten om icke-godkända domäner i instrumentpanelen för e-postflöde i säkerhets- och efterlevnadscentret för & för att övervaka meddelanden från den lokala organisationen där avsändarens domän inte har konfigurerats i Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 573fb0ba2bf7981b6eb7df4eec7c8c4e5d596cac
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150826"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a>Icke-godkänd domänrapport i Säkerhets- & Efterlevnadscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender för Office 365 abonnemang 1 och abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

I instrumentpanelen för e-postflöde i säkerhets- och efterlevnadscentret för [&](https://protection.office.com) visas information om meddelanden från din lokala e-postorganisation där avsändarens domän inte har konfigurerats som en godkänd domän i Microsoft [](mail-flow-insights-v2.md) 365-organisationen. 

Microsoft 365 kan begränsa dessa meddelanden om vi har data som bevisar att avsikten med dessa meddelanden är skadliga. Därför är det viktigt att du förstår vad som händer och åtgärdar problemet.

![Domänwidget som inte godkänts i instrumentpanelen för e-postflöde i & Efterlevnadscenter](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a>Rapportvy för domänrapporten Godkänd

Om du klickar på diagrammet **på widgeten Ej godkänd** domän kommer du till rapporten Om domänen inte **godkänns.**

Som standard visas aktiviteten för alla berörda kopplingar. Om du klickar **på Visa data** för kan du välja en specifik koppling i listrutan.

Om du hovrar över en datapunkt (dag) i diagrammet visas det totala antalet meddelanden för kopplingen.

![Rapportvy i domänrapporten Godkänd](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a>Detaljtabellvy för domänrapporten Godkänd

Om du **klickar på Tabellen Visa** information i en rapportvy visas följande information:

- **Datum**
- **Namn på inkommande koppling**
- **Avsändningsdomän**
- **Antal meddelanden**
- **Exempelmeddelanden:** Meddelande-ID:na för ett urval av påverkade meddelanden.

Om du klickar **på** Filter i en detaljtabellvy kan du ange ett datumintervall **med startdatum** **och slutdatum.**

Om du vill skicka rapporten för ett visst datumintervall till en eller flera mottagare via e-post klickar du **på Begär nedladdning.**

När du markerar en rad i tabellen visas en utfälltabell med följande information:

- **Datum**
- **Namn på inkommande koppling**
- **Avsändningsdomän**
- **Antal meddelanden**
- **Exempelmeddelanden:** Du kan klicka **på Visa exempelmeddelanden** om du vill visa [meddelandespårningsresultaten](message-trace-scc.md) för ett urval av de aktuella meddelandena.

![Information som visas när du har valt en rad i tabellvyn Detaljer i rapporten Om godkänd domän](../../media/mfi-non-accepted-domain-report-details-flyout.png)

Om du vill gå tillbaka till rapportvyn klickar du **på Visa rapport.**

## <a name="related-topics"></a>Relaterade ämnen

Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinsikter i Säkerhets- & Efterlevnadscenter.](mail-flow-insights-v2.md)
