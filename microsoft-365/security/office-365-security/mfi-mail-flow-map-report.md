---
title: E-postflödeskarta
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa mer om hur du använder översikten för e-postflöden i instrument panelen för e-postflöde i säkerhets & efterföljandekrav för att visualisera och spåra hur e-flöden kommer till och från sin organisation via kopplingar och utan att använda kopplingar.
ms.openlocfilehash: fc03f05db77c40dbf726692e6fb6069d587a5ffc
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877771"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a>Översikt över e-postflöde i säkerhets & efterlevnad

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**E-postflödes kartan** i [instrument panelen för e-postflöde](mail-flow-insights-v2.md) i [säkerhets & Compliance Center](https://protection.office.com) ger en överblick över hur e-flöden passerar genom din organisation. Du kan använda den här informationen för att lära dig mönster, identifiera avvikelser och åtgärda problem när de uppstår.

![Widget för e-postflödes karta i instrument panelen för säkerhet &](../../media/mfi-mail-flow-map-widget.png)

Som standard visar widgeten e-postflödet från föregående dag i ett diagram som kallas *Sankey* -diagram. Du kan använda vänsterpilen vänsterpil ![ och HÖGERPIL ](../../media/scc-left-arrow.png) ![ ](../../media/scc-right-arrow.png) för att visa information från olika dagar. Varje färg representerar e-postflöden över en annan inkommande eller utgående koppling (eller utan att använda kopplingar). Om du hovrar över en viss färg visas antalet meddelanden för den typen av koppling.

## <a name="report-view-for-the-mail-flow-map"></a>Rapportvy för översikt över e-postflöde

Om du klickar på widgeten **Koppla dokument flöden** tas du till **översikten över e-postflöde** .

Följande diagram är tillgängliga i rapportvyn:

- **Visa data för: översikt** : det här är i stort sett en större vy av widgeten. Om du hovrar över en viss färg visas antalet meddelanden för den typen av koppling.

  ![Vyn Översikt i rapporten e-postflödes karta](../../media/mfi-mail-flow-map-report-overview.png)

- **Visa data för: detail** : den här vyn visar information om kopplingarna och mål domänerna. De översta avsändarna och mottagar domänerna visas och resten placeras i **andra**. Om du hovrar över en viss färg och ett avsnitt visas antalet meddelanden.

  ![Detaljvyn i rapporten dokument flödes karta](../../media/mfi-mail-flow-map-report-detail.png)

Om du klickar på **filter** i en rapportvy kan du ange ett datum intervall med **start datum** och **slutdatum**.

Om du vill skicka rapporten för ett visst datum intervall till en eller flera mottagare klickar du på **Hämta**.

Relaterade insikter visas under översikten över e-postflöden om de är tillgängliga (till exempel [korrigerings filen för möjlig e-postloop](mfi-mail-loop-insight.md)).

## <a name="details-table-view-for-the-mail-flow-map"></a>Vyn detaljerad vy för översikt över e-postflöde

Om du klickar på **Visa informations tabell** i en rapportvy visas följande information:

- **Datum**
- **Kategori**
- **Anslutning/tredjepartsleverantör från tredje part**
- **Avsändare/mottagare**
- **Antal meddelanden**

Om du klickar på **filter** i en detaljerad tabellvy kan du ange ett datum intervall med **start datum** och **slutdatum**.

Om du markerar en rad visas liknande information i en utfällbar lista:

![Information som utfälls från informations tabellen i översikten över e-postflöde](../../media/mfi-mail-flow-map-view-details-table-details.png)

Om du vill skicka rapporten för ett visst datum intervall till en eller flera mottagare klickar du på **Hämta**.

Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.

## <a name="see-also"></a>Se även

Information om andra insikter i instrument panelen för e-postflöden finns i avsnittet om [hur du använder e-postflöde i säkerhets & Compliance Center](mail-flow-insights-v2.md).
