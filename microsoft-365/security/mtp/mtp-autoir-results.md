---
title: Information och resultat från en automatiserad undersökning
description: Du kan visa resultaten och viktiga resultat under och efter en automatiserad undersökning
keywords: automatisera, undersöka, resultat, analysera, information, åtgärd, autoair
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 09/16/2020
ms.technology: m365d
ms.openlocfilehash: c050683bb3ed052ae4752ffdee66fe51fb99b88b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930372"
---
# <a name="details-and-results-of-an-automated-investigation"></a>Information och resultat från en automatiserad undersökning

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

När en automatiserad undersökning görs i Microsoft 365 Defender finns det information om undersökningen tillgänglig under och efter den automatiska undersökningsprocessen. Om du har den [behörighet som krävs](mtp-action-center.md#required-permissions-for-action-center-tasks)kan du visa den informationen i en vy med undersökningsinformation. I vyn med undersökningsinformation får du aktuell status och möjlighet att godkänna eventuella väntande åtgärder. 

![Undersökningsinformation](../../media/mtp-air-investdetails.png)

## <a name="open-the-investigation-details-view"></a>Öppna vyn med undersökningsinformation

Du kan öppna vyn med undersökningsinformation med någon av följande metoder:
- [Markera ett objekt i Åtgärdscenter](#select-an-item-in-the-action-center)
- [Välj en undersökning från sidan incidentinformation](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a>Markera ett objekt i Åtgärdscenter

Använd Åtgärdscenter för att visa åtgärder som  antingen väntar på godkännande (på fliken Väntande) eller redan har godkänts (på **fliken** Historik). 

1. Gå till [https://security.microsoft.com](https://security.microsoft.com) och logga in. 

2. Välj Åtgärdscenter i **navigeringsfönstret.** 

3. Välj ett **objekt på** fliken **Väntande** eller Historik. Om du har den [behörighet som krävs](mtp-action-center.md#required-permissions-for-action-center-tasks)kan du godkänna (eller avvisa) väntande åtgärder.

### <a name="open-an-investigation-from-an-incident-details-page"></a>Öppna en undersökning från sidan incidentinformation

Använd en sida med incidentinformation om du vill visa detaljerad information om en händelse, inklusive aviseringar som utlöstes information om enheter, användarkonton eller postlådor som påverkas.

1. Gå till [https://security.microsoft.com](https://security.microsoft.com) och logga in. 

2. Välj Incidenter i **navigeringsfönstret.** 

3. Markera ett objekt i listan för att öppna vyn incidentinformation.<br/>![Incidentinformation](../../media/mtp-incidentdetails-tabs.png)

4. Välj **en undersökning** i listan på fliken Undersökningar.

## <a name="investigation-details"></a>Undersökningsinformation

Använd vyn med undersökningsinformation för att se tidigare, aktuell och väntande aktivitet som hör till en undersökning. Vyn med undersökningsinformation liknar följande bild:

![Undersökningsinformation](../../media/mtp-air-investdetails.png)

I vyn Undersökningsinformation kan du se information om **åtgärdsflikarna** **Undersökning,**  **Varningar,** **Enheter,** Identiteter,  **Enheter,** Enheter, Logg och Väntande åtgärder, som beskrivs i följande tabell.

| Tabb | Beskrivning |
|--------|--------|
| **Undersökningsdiagram**   | Ger en visuell representation av undersökningen. Visar enheter och visar hot som påträffas, tillsammans med aviseringar och om några åtgärder väntar på godkännande.<br/>Du kan klicka på ett objekt i diagrammet om du vill visa mer information. Om du till exempel klickar **på ikonen Hittade** hot kommer du till fliken **Viktiga** resultat. |
| **Varningar**    | Listar aviseringar som är associerade med undersökningen. Varningar kan komma från skyddsfunktioner för hot på en användares dator, i Office-appar, Cloud App Security och andra Microsoft 365 Defender-funktioner.|
| **Enheter** | Visar datorer som ingår i undersökningen tillsammans med åtgärdsnivån.|
| **Viktiga resultat**  | Listor med resultat från undersökningen tillsammans med status och åtgärder som vidtas eller väntar. Du kan godkänna väntande åtgärder för enheter och identiteter på den här fliken.|
| **Enheter**  | Visar användaraktiviteter, filer, processer, tjänster, drivrutiner, IP-adresser och beständighetsmetoder associerade med undersökningen, tillsammans med status och åtgärder som vidtas.|
|**Logg**    | Ger en detaljerad bild av alla steg som vidtas under undersökningen, tillsammans med status.|
| **Väntande åtgärder** | En lista med objekt som kräver godkännande för att fortsätta.|

## <a name="next-steps"></a>Nästa steg

- [Godkänna eller avvisa åtgärder relaterade till automatiserad undersökning och svar](mtp-autoir-actions.md)
- [Granska åtgärder](mtp-remediation-actions.md)
