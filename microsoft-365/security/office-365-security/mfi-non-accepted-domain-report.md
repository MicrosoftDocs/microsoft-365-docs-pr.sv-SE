---
title: Icke godkänd domän rapport i instrument panelen för e-postflöde
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig att använda den icke godkända domän rapporten i instrument panelen för e-postflöde i säkerhets & efterlevnad för att övervaka meddelanden från din lokala organisation där avsändarens domän inte är konfigurerad i Microsoft 365.
ms.openlocfilehash: 649163729bbb73140f9cfb7e75c9fd06f3908cce
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577479"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a>Icke godkänd domän rapport i Center för säkerhets &

Den **icke godkända domän** rapporten i [instrument panelen för e-postflöde](mail-flow-insights-v2.md) i säkerhets & Compliance Center visar information om meddelanden från din lokala e-postorganisation där avsändarens domän inte är konfigurerad som en godkänd domän i Microsoft 365-organisationen.

Microsoft 365 kan begränsa dessa meddelanden om vi har data som visar att syftet med dessa meddelanden är skadligt. Därför är det viktigt att du förstår vad som händer och för att åtgärda problemet.

![Icke godkänd domän-widget i instrument panelen för e-postflöde i säkerhets & efterlevnad](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a>Rapportvy för den icke godkände domän rapporten

Om du klickar på diagrammet i widgeten **icke godkänd domän** tas du till den **icke godkända domän** rapporten.

Aktiviteten för alla berörda kopplingar visas som standard. Om du klickar på **Visa data för**kan du välja en specifik koppling i list rutan.

Om du hovrar över en data punkt (dag) i diagrammet visas det totala antalet meddelanden för kopplingen.

![Rapportvy i rapporten icke godkänd domän](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a>Vyn detaljerad tabell för icke godkänd domän rapport

Om du klickar på **Visa informations tabell** i en rapportvy visas följande information:

- **Datum**
- **Namn på inkommande anslutning**
- **Avsändningsdomän**
- **Antal meddelanden**
- **Exempel meddelanden**: meddelande-ID för ett urval av påverkade meddelanden.

Om du klickar på **filter** i en detaljerad tabellvy kan du ange ett datum intervall med **start datum** och **slutdatum**.

Om du vill skicka rapporten för ett visst datum intervall till en eller flera mottagare klickar du på **Hämta**.

När du markerar en rad i tabellen visas en utfällbar tabell med följande information:

- **Datum**
- **Namn på inkommande anslutning**
- **Avsändningsdomän**
- **Antal meddelanden**
- **Exempel meddelanden**: du kan klicka på **Visa exempel meddelanden** om du vill visa [meddelande spårnings](message-trace-scc.md) resultaten för ett prov av de påverkade meddelandena.

![Utfällda detaljer när du har markerat en rad i tabellvy för information i den icke godkända domän rapporten](../../media/mfi-non-accepted-domain-report-details-flyout.png)

Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.

## <a name="related-topics"></a>Relaterade ämnen

Information om andra insikter i instrument panelen för e-postflöden finns i avsnittet om [hur du använder e-postflöde i säkerhets & Compliance Center](mail-flow-insights-v2.md).
