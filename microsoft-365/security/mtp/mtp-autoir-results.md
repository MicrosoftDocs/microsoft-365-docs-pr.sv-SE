---
title: Detaljer och resultat av en automatiserad undersökning
description: Under och efter en automatiserad undersökning kan du visa resultat och viktiga resultat
keywords: automatiserad, undersökning, resultat, analysera, detaljer, sanering, autoair
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 6b3bc068e5da99e02a64463891e32d137c448d64
ms.sourcegitcommit: 133bf7936e5ef1a4d06998429d0d01096bda929f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42809704"
---
# <a name="details-and-results-of-an-automated-investigation"></a>Detaljer och resultat av en automatiserad undersökning

**Gäller:**
- Microsofts hotskydd

När en automatiserad undersökning inträffar i Microsoft Threat Protection finns information om den undersökningen tillgänglig under och efter den automatiska granskningsprocessen. Om du har [de behörigheter som krävs](mtp-action-center.md#required-permissions-for-action-center-tasks)kan du visa dessa uppgifter i en undersökningsinformationsvy. Vyn Undersökningsinformation ger dig aktuell status och möjlighet att godkänna väntande åtgärder. 

![Detaljer om undersökningen](../../media/mtp-air-investdetails.png)

## <a name="open-the-investigation-details-view"></a>Öppna vyn För undersökningsinformation

Du kan öppna vyn undersökningsinformation med någon av följande metoder:
- [Markera ett objekt i åtgärdscentret](#select-an-item-in-the-action-center)
- [Välj en undersökning från en incidentinformationssida](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a>Markera ett objekt i åtgärdscentret

Använd åtgärdscentret för att visa åtgärder som antingen väntar på godkännande (på fliken **Väntande)** eller som redan har godkänts (på fliken **Historik).** 

1. Gå [https://security.microsoft.com](https://security.microsoft.com) till och logga in. 

2. Välj **Åtgärdscenter**i navigeringsfönstret . 

3. Markera ett objekt på fliken **Väntande** eller **Historik.** Om du har [de behörigheter som krävs](mtp-action-center.md#required-permissions-for-action-center-tasks)kan du godkänna (eller avvisa) väntande åtgärder.

### <a name="open-an-investigation-from-an-incident-details-page"></a>Öppna en utredning från en incidentinformationssida

Använd en incidentinformationssida för att visa detaljerad information om en incident, inklusive aviseringar som har utlösts information om alla berörda enheter, användarkonton eller postlådor.

1. Gå [https://security.microsoft.com](https://security.microsoft.com) till och logga in. 

2. Välj **Incidenter**i navigeringsfönstret . 

3. Markera ett objekt i listan om du vill öppna incidentinformationsvyn.<br/>![Information om incidenter](../../media/mtp-incidentdetails-tabs.png)

4. Välj en undersökning i listan på fliken **Undersökningar.**

## <a name="investigation-details"></a>Detaljer om undersökningen

Använd vyn undersökningsinformation för att se tidigare, aktuell och väntande aktivitet som hör till en undersökning. Undersökningens informationsvy liknar följande bild:

![Detaljer om undersökningen](../../media/mtp-air-investdetails.png)

I vyn Undersökningsinformation kan du se information om flikarna **Undersökningsdiagram**, **Aviseringar**, **Enheter**, **Identiteter**, Nyckelresultat , **Entiteter,** **Logg**och **Väntande åtgärder** som beskrivs i följande tabell. **Key findings**

|Tab    |Beskrivning |
|--------|--------|
|Undersökning diagram    |Ger en visuell representation av undersökningen. Visar entiteter och listar hot som hittats, tillsammans med aviseringar och om några åtgärder väntar på godkännande.<br/>Du kan klicka på ett objekt i diagrammet om du vill visa mer information. Om du till exempel klickar på ikonen **Hot hittades** kommer du till fliken **Nyckelresultat.** |
|Varningar |Visar aviseringar som är associerade med undersökningen. Aviseringar kan komma från hotskyddsfunktioner på en användares dator, i Office-appar, Cloud App Security och andra Microsoft 365 Threat Protection-funktioner.|
|Enheter|Listar maskiner som ingår i undersökningen tillsammans med saneringsnivå.|
|Viktiga resultat   |Visar resultat från undersökningen tillsammans med status och åtgärder som vidtagits eller väntar. Du kan godkänna väntande åtgärder för enheter och identiteter på den här fliken.|
|Enheter   |Visar användaraktiviteter, filer, processer, tjänster, drivrutiner, IP-adresser och persistensmetoder som är associerade med undersökningen, tillsammans med status och åtgärder som vidtagits.|
|Logga in    |Ger en detaljerad översikt över alla steg som vidtagits under undersökningen, tillsammans med status.|
|Väntande åtgärder    |Visar en lista över objekt som kräver godkännande för att fortsätta.|

## <a name="next-steps"></a>Nästa steg

- [Få en översikt över behörigheter för Åtgärdscenter](mtp-action-center.md#required-permissions-for-action-center-tasks)

- [Godkänna eller avvisa åtgärder relaterade till automatisk undersökning och svar](mtp-autoir-actions.md)

