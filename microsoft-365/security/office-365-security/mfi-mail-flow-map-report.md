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
description: Administratörer kan lära sig att använda e-postflödeskartan i instrumentpanelen för e-postflöde i Säkerhets- & och efterlevnadscenter för att visualisera och spåra hur e-post flödar till och från organisationen via kopplingar och utan att använda kopplingar.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2f507f7f01999492d17e168a2a56da906bfcb52d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290591"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a>E-postflödeskarta i Säkerhets- & Efterlevnadscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

**E-postflödeskartan** [i](mail-flow-insights-v2.md) instrumentpanelen för e-postflöde i Säkerhets- & [efterlevnadscenter](https://protection.office.com) ger insyn i hur e-post flödar genom organisationen. Du kan använda den här informationen för att lära dig mönster, identifiera problem och åtgärda problem när de uppstår.

![Widget för e-postflödeskarta i instrumentpanelen för e-postflöde & Säkerhets- och efterlevnadscenter](../../media/mfi-mail-flow-map-widget.png)

Som standard visar widgeten e-postflödesmönstret från föregående dag i ett diagram som kallas *Sankey-diagram.* Du kan använda vänsterpilen ![ och ](../../media/scc-left-arrow.png) högerpilen till höger om ![ du vill visa information från olika ](../../media/scc-right-arrow.png) dagar. Varje färg representerar e-postflöde över en annan inkommande eller utgående koppling (eller utan att använda kopplingar). Om du hovrar över en viss färg visas antalet meddelanden för den typen av koppling.

## <a name="report-view-for-the-mail-flow-map"></a>Rapportvy för e-postflödeskartan

Om du klickar på **widgeten för e-postflödeskartan** kommer du till rapporten **E-postflödeskarta.**

Följande diagram är tillgängliga i rapportvyn:

- **Visa data för: Översikt:** Det här är i stort sett en större vy av widgeten. Om du hovrar över en viss färg visas antalet meddelanden för den typen av koppling.

  ![Översiktsvy i rapporten E-postflödeskarta](../../media/mfi-mail-flow-map-report-overview.png)

- **Visa data för: Information:** I den här vyn visas information om kopplingar och måldomäner. De översta domänerna för avsändare och mottagare visas och resten läggs i **Andra.** Om du hovrar över en viss färg och ett visst avsnitt visas antalet meddelanden.

  ![Detaljvyn i rapporten E-postflödeskarta](../../media/mfi-mail-flow-map-report-detail.png)

Om du klickar **på** Filter i en rapportvy kan du ange ett datumintervall **med startdatum** **och slutdatum.**

Om du vill skicka rapporten för ett visst datumintervall till en eller flera mottagare via e-post klickar du **på Begär nedladdning.**

Relaterade insikter visas under e-postflödeskartan om de är tillgängliga (till exempel information om att åtgärda [möjlig e-postslinga).](mfi-mail-loop-insight.md)

## <a name="details-table-view-for-the-mail-flow-map"></a>Detaljtabellvy för e-postflödeskartan

Om du **klickar på Tabellen Visa** information i en rapportvy visas följande information:

- **Datum**
- **Kategori**
- **Anslutare/tjänstprovider**
- **Domän för avsändare/mottagare**
- **Antal meddelanden**

Om du klickar **på** Filter i en detaljtabellvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**

Om du markerar en rad visas liknande information i en utfällig plats:

![Utfällbar information från detaljtabellen på e-postflödeskartan](../../media/mfi-mail-flow-map-view-details-table-details.png)

Om du vill skicka rapporten för ett visst datumintervall till en eller flera mottagare via e-post klickar du **på Begär nedladdning.**

Om du vill gå tillbaka till rapportvyn klickar du **på Visa rapport.**

## <a name="see-also"></a>Se även

Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinsikter i Säkerhets- & Efterlevnadscenter.](mail-flow-insights-v2.md)
