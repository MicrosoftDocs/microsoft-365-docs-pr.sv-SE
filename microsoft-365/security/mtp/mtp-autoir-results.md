---
title: Uppgifter och resultat från en automatiserad undersökning
description: Under och efter en automatiserad undersökning kan du Visa resultat och nyckeltal
keywords: automatiserad, undersökning, resultat, analysera, uppgifter, reparation, autoair
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
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 09/16/2020
ms.openlocfilehash: 39f6be70ad7a611f9919bb0529e8c8ed7f9dc339
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683366"
---
# <a name="details-and-results-of-an-automated-investigation"></a>Uppgifter och resultat från en automatiserad undersökning

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

När en automatisk undersökning sker i Microsoft 365 Defender är det möjligt att få information om den undersökningen och efter den automatiska gransknings processen. Om du har [nödvändig behörighet](mtp-action-center.md#required-permissions-for-action-center-tasks)kan du Visa den informationen i vyn granska information. I vyn undersöknings Detaljer får du uppdaterade status och möjlighet att godkänna väntande åtgärder. 

![Gransknings uppgifter](../../media/mtp-air-investdetails.png)

## <a name="open-the-investigation-details-view"></a>Öppna vyn gransknings Detaljer

Du kan öppna vyn gransknings Detaljer på något av följande sätt:
- [Markera ett objekt i åtgärds Center](#select-an-item-in-the-action-center)
- [Välj en undersökning på sidan information om en händelse](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a>Markera ett objekt i åtgärds Center

Använd åtgärds centret för att Visa åtgärder som antingen väntar på godkännande (på fliken **förestående** ) eller som redan har godkänts (på fliken **Historik** ). 

1. Gå till [https://security.microsoft.com](https://security.microsoft.com) och logga in. 

2. I navigerings fönstret väljer du **Åtgärds Center**. 

3. På fliken **förestående** eller **Historik** väljer du ett objekt. Om du har [nödvändig behörighet](mtp-action-center.md#required-permissions-for-action-center-tasks)kan du godkänna (eller avvisa) väntande åtgärder.

### <a name="open-an-investigation-from-an-incident-details-page"></a>Öppna en undersökning från sidan information om en händelse

Använd en informations sida för att visa detaljerad information om en olycka, inklusive aviseringar som utlöste information om eventuella berörda enheter, användar konton eller post lådor.

1. Gå till [https://security.microsoft.com](https://security.microsoft.com) och logga in. 

2. Välj **incidenter** i navigerings fönstret. 

3. Välj ett objekt i listan för att öppna vyn incident information.<br/>![Incident uppgifter](../../media/mtp-incidentdetails-tabs.png)

4. Välj en undersökning i listan på fliken **undersökningar** .

## <a name="investigation-details"></a>Gransknings uppgifter

Använd vyn granska information om du vill visa tidigare, nuvarande och väntande aktiviteter för en undersökning. Vyn gransknings Detaljer ser ut ungefär så här:

![Gransknings uppgifter](../../media/mtp-air-investdetails.png)

I vyn undersöknings Detaljer kan du se information om **undersökningen**, **aviseringar**, **enheter**, **identiteter**, **viktiga resultat**, **entiteter**, **loggning** och **väntande åtgärder** , som beskrivs i följande tabell.

| Fliken | Beskrivning |
|--------|--------|
| **Undersökning**   | Ger en visuell representation av undersökningen. Beskriver enheter och visar en lista med hot och varningar och om åtgärder väntar på godkännande.<br/>Du kan klicka på ett objekt i diagrammet för att visa mer information. Om du till exempel klickar på ikonen **upptäckta hot** tar du till fliken **viktiga resultat** . |
| **Varningar**    | Visar en lista över aviseringar som är associerade med undersökningen. Aviseringar kan komma från hot Protection-funktioner på en användares dator, i Office-appar, Cloud App-säkerhet och andra Microsoft 365 Defender-funktioner.|
| **Enheter** | Visar en lista med maskiner som ingår i undersökningen tillsammans med reparations nivå.|
| **Nyckeltal**  | Visar resultaten från undersökningen tillsammans med status och åtgärder som utförs eller väntar. Du kan godkänna väntande åtgärder för enheter och identiteter på den här fliken.|
| **Posterna**  | Visar en lista över användar aktiviteter, filer, processer, tjänster, driv rutiner, IP-adresser och beständiga metoder som är förknippade med undersökningen samt status och åtgärder som vidtas.|
|**Logga in**    | Visar en detaljerad vy av alla steg som görs under undersökningen, tillsammans med status.|
| **Väntande åtgärder** | Visar de objekt som kräver godkännande för att fortsätta.|

## <a name="next-steps"></a>Nästa steg

- [Godkänna eller avvisa åtgärder relaterade till automatiserad undersökning och svar](mtp-autoir-actions.md)
- [Granska reparations åtgärder](mtp-remediation-actions.md)
