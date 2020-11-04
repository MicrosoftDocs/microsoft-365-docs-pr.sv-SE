---
title: Rapport om utebliven leverans i instrument panelen för e-postflöde
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
description: Administratörer kan lära dig hur du använder rapporten för information om ej leverans i instrument panelen för e-postflöde i säkerhets & Compliance Center för att övervaka de vanligaste fel koderna i rapporter som inte kunde levereras (kallas även NDR eller studs meddelanden) från avsändare i din organisation.
ms.openlocfilehash: 4967b3b5c294566e46bbc715dd6702c23d618105
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877687"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a>Rapport om utebliven leverans i säkerhets & efterlevnad

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


I **rapporten om utebliven leverans** i [instrument panelen för e-postflöden](mail-flow-insights-v2.md) i [säkerhets & Compliance Center](https://protection.office.com) visas de mest upptäckta fel koderna i rapporter för inte leverans (kallas även för NDR eller studs meddelanden) för användare i organisationen. Den här rapporten visar information om NDR så att du kan felsöka problem med e-postleverans.

![Widget för rapport om utebliven leverans i instrument panelen för e-postflöde i säkerhets & efterlevnad](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a>Rapportvy för rapport om utebliven leverans

Om du klickar på widgeten för **ej leverans rapporter** tas du till **rapporten för ej leverans**.

Aktiviteten för alla felkoder visas som standard. Om du klickar på **Visa data för** kan du välja en specifik felkod i list rutan.

Om du hovrar över en viss färg (felkod) på en viss dag i diagrammet visas det totala antalet meddelanden för felet.

![Rapportvy i rapporten icke godkänd domän](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a>Vyn detaljerad lista för rapport om utebliven leverans

Om du klickar på **Visa informations tabell** i en rapportvy visas följande information:

- **Datum**
- **Rapport kod för ej leverans**
- **Öka**
- **Exempel meddelanden** : meddelande-ID för ett urval av påverkade meddelanden.

Om du klickar på **filter** i en detaljerad tabellvy kan du ange ett datum intervall med **start datum** och **slutdatum**.

Om du vill skicka rapporten för ett visst datum intervall till en eller flera mottagare klickar du på **Hämta**.

När du markerar en rad i tabellen visas en utfällbar tabell med följande information:

- **Datum**
- **Rapport kod för ej leverans** : du kan klicka på länken för att hitta mer information om orsakerna och lösningarna för den specifika felkoden.
- **Öka**
- **Exempel meddelanden** : du kan klicka på **Visa exempel meddelanden** om du vill visa [meddelande spårnings](message-trace-scc.md) resultaten för ett prov av de påverkade meddelandena.

![Utfällda detaljer när du har markerat en rad i Tabellvy i rapporten för ej leverans](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a>Relaterade ämnen

Information om andra insikter i instrument panelen för e-postflöden finns i avsnittet om [hur du använder e-postflöde i säkerhets & Compliance Center](mail-flow-insights-v2.md).
