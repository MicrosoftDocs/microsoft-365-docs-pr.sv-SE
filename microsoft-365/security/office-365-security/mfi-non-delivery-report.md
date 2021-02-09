---
title: Rapport om utebliven leverans på instrumentpanelen för e-postflöde
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
description: Administratörer kan ta reda på hur de använder rapporten information om utebliven leverans i instrumentpanelen för e-postflöde i säkerhets- och efterlevnadscentret för & för att övervaka de felkoder som oftast påträffas i rapporter om utebliven leverans (kallas även NDR-rapporter eller icke-leveranskaviseringar) från avsändare i organisationen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: af4beefb8ba15fd7d98b11ec2571eee65a99e4e3
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150165"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a>Rapport om utebliven leverans i Säkerhets- & Efterlevnadscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender för Office 365 abonnemang 1 och abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Rapporten **Om** utebliven [](mail-flow-insights-v2.md) leverans i instrumentpanelen för e-postflöde i Säkerhets- [&](https://protection.office.com) efterlevnadscenter visar de felkoder som påträffats i rapporter om utebliven leverans (kallas även NDR-rapporter eller icke-leveransk studsande meddelanden) för användare i organisationen. Den här rapporten innehåller information om NDR-rapporter så att du kan felsöka problem med e-postleveransen.

![Widget för rapport om utebliven leverans i instrumentpanelen för e-postflöde & Säkerhets- och efterlevnadscenter](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a>Rapportvy för rapport om utebliven leverans

Om du klickar **på widgeten Rapport om** utebliven leverans kommer du till rapporten Om **utebliven leverans.**

Som standard visas aktiviteten för alla felkoder. Om du klickar **på Visa data** för kan du välja en specifik felkod i listrutan.

Om du hovrar över en viss färg (felkod) en viss dag i diagrammet visas det totala antalet meddelanden för felet.

![Rapportvy i domänrapporten Godkänd](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a>Tabellvyn Information för rapporten om utebliven leverans

Om du **klickar på tabellen Visa** information i en rapportvy visas följande information:

- **Datum**
- **Rapportkod för utebliven leverans**
- **Antal**
- **Exempelmeddelanden:** Meddelande-ID:na för ett exempel på påverkade meddelanden.

Om du klickar **på** Filter i en detaljtabellvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**

Om du vill skicka rapporten för ett visst datumintervall till en eller flera mottagare via e-post klickar du **på Begär nedladdning.**

När du markerar en rad i tabellen visas en utfälltabell med följande information:

- **Datum**
- **Rapportkod för utebliven leverans:** Du kan klicka på länken för att hitta mer information om orsaker och lösningar för den specifika felkoden.
- **Antal**
- **Exempelmeddelanden:** Du kan klicka **på Visa exempelmeddelanden** om du vill visa [meddelandespårningsresultaten](message-trace-scc.md) för ett urval av de aktuella meddelandena.

![Information som visas när du har valt en rad i tabellvyn Detaljer i rapporten Om leverans](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a>Relaterade ämnen

Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinsikter i Säkerhets- & Efterlevnadscenter.](mail-flow-insights-v2.md)
