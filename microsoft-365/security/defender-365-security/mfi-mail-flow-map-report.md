---
title: E-postflödeskarta
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
description: Administratörer kan lära sig att använda e-postflödeskartan i instrumentpanelen för e-postflöde i säkerhets- och efterlevnadscentret för & för att visualisera och spåra hur e-post flödar till och från organisationen via kopplingar och utan att använda kopplingar.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6e806dde2e6f3ddde5cce3b61c85fe0b024ba2fe
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071305"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a>E-postflödeskarta i säkerhets- & Säkerhets- och efterlevnadscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**E-postflödeskartan** [på instrumentpanelen](mail-flow-insights-v2.md) för e-postflöde i säkerhets- & [efterlevnadscenter](https://protection.office.com) ger insyn i hur e-post flödar genom organisationen. Du kan använda den här informationen till att lära dig mönster, identifiera problem och åtgärda problem när de uppstår.

![Widget för e-postflödeskarta i instrumentpanelen för e-postflöde & Säkerhets- och efterlevnadscenter](../../media/mfi-mail-flow-map-widget.png)

Som standard visar widgeten e-postflödesmönstret från föregående dag i ett diagram som kallas *för Ett Sankey-diagram.* Du kan använda vänsterpilen ![ Vänsterpil ](../../media/scc-left-arrow.png) och Högerpil för ![ att visa information från olika ](../../media/scc-right-arrow.png) dagar. Varje färg representerar e-postflöde över en annan inkommande eller utgående koppling (eller utan att använda kopplingar). Om du hovrar över en viss färg visas antalet meddelanden för den typen av koppling.

## <a name="report-view-for-the-mail-flow-map"></a>Rapportvy för e-postflödeskartan

Om du klickar på **widgeten E-postflödeskarta** kommer du till **rapporten E-postflödeskarta.**

Följande diagram är tillgängliga i rapportvyn:

- **Visa data för: Översikt:** Det här är i stort sett en större vy av widgeten. Om du hovrar över en viss färg visas antalet meddelanden för den typen av koppling.

  ![Översiktsvyn i rapporten E-postflödeskarta](../../media/mfi-mail-flow-map-report-overview.png)

- **Visa data för: Information:** I den här vyn visas information om kopplingarna och måldomänerna. De översta domänerna för avsändare och mottagare visas och resten finns i **Andra**. Om du hovrar över en viss färg och ett visst avsnitt visas antalet meddelanden.

  ![Detaljvyn i rapporten E-postflödeskarta](../../media/mfi-mail-flow-map-report-detail.png)

Om du klickar **på** Filter i en rapportvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**

Om du vill skicka rapporten med ett visst datumintervall till en eller flera mottagare klickar du på **Begär nedladdning.**

Relaterade insikter visas under e-postflödeskartan om de är tillgängliga (till exempel åtgärda möjliga insikter om [e-postslinga](mfi-mail-loop-insight.md)).

## <a name="details-table-view-for-the-mail-flow-map"></a>Detaljtabellvyn för e-postflödeskartan

Om du **klickar på Visa informationstabell** i en rapportvy visas följande information:

- **Datum**
- **Kategori**
- **Anslutare/tredjepartsleverantör**
- **Sender/Recipient domain**
- **Antal meddelanden**

Om du klickar **på** Filter i en detaljtabellvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**

Om du markerar en rad visas liknande information i en utfällbladstext:

![Utfällbar information från detaljtabellen i e-postflödeskartan](../../media/mfi-mail-flow-map-view-details-table-details.png)

Om du vill skicka rapporten med ett visst datumintervall till en eller flera mottagare klickar du på **Begär nedladdning.**

Om du vill gå tillbaka till rapportvyn klickar du **på Visa rapport**.

## <a name="see-also"></a>Se även

Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinformation i Säkerhets- & efterlevnadscenter.](mail-flow-insights-v2.md)
