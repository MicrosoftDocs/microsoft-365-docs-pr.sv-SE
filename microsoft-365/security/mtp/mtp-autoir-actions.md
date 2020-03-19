---
title: Godkänna eller avvisa väntande åtgärder efter en automatisk undersökning
description: Använd Åtgärdscentret för att hantera åtgärder som är relaterade till automatiserad undersökning och svar
keywords: åtgärd, centrum, autoair, automatiserad, utredning, svar, sanering
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
ms.openlocfilehash: 725d22629d2c81a0edf8f329602214afddde6511
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42809005"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a>Godkänna eller avvisa väntande åtgärder efter en automatisk undersökning

**Gäller:**
- Skydd av Hot mot Microsoft

När en automatiserad undersökning körs kan det resultera i en eller flera [reparationsåtgärder](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) som kräver godkännande för att fortsätta. Ett kluster med e-postmeddelanden kan till exempel behöva tas bort, eller så kan en fil i karantän behöva tas bort. Det är viktigt att godkänna (eller avvisa) pågående åtgärder så snart som möjligt så att dina automatiserade undersökningar kan fortsätta och slutföra i tid. 

> [!TIP]
> Om du tror att något har missats eller upptäckts felaktigt genom automatiskundersökning och svarsfunktioner i Microsoft Threat Protection, låt oss veta! Se [Hur du rapporterar falska positiva/negativa effekter i AIR-funktioner (Automated Investigation and Response) i Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).

Väntande åtgärder kan granskas och godkännas med hjälp av [åtgärdscentret](#review-a-pending-action-in-the-action-center) eller [undersökningsinformationsvyn](#review-a-pending-action-in-the-investigation-details-view).

> [!NOTE]
> Du måste ha [rätt behörighet](mtp-action-center.md#required-permissions-for-action-center-tasks) för att godkänna eller avvisa reparationsåtgärder.

## <a name="review-a-pending-action-in-the-action-center"></a>Granska en väntande åtgärd i åtgärdscentret

1. Gå [https://security.microsoft.com](https://security.microsoft.com) till och logga in. 

2. Välj **Åtgärdscenter i**navigeringsfönstret . 

3. Välj ett objekt i listan på fliken **Väntande** i Åtgärdscenter. 

    - Om du väljer ett objekt i kolumnen **Utredningsnummer** öppnas sidan för undersökningsinformation. Där kan du visa resultatet av undersökningen och sedan antingen godkänna eller avvisa den rekommenderade åtgärden.
 
    - Om du väljer en rad i listan öppnas ett utfällbart objekt där du kan visa information om objektet. <br/>![Godkänna eller avvisa en åtgärd](../../media/air-actioncenter-itemselected.png)<br/>Använd länkarna för att visa en associerad avisering eller en undersökning och godkänna eller avvisa åtgärden.

## <a name="review-a-pending-action-in-the-investigation-details-view"></a>Granska en väntande åtgärd i vyn för utredningsinformation

![Uppgifter om utredning](../../media/mtp-air-investdetails.png)

1. På en [sida med undersökningsinformation](mtp-autoir-results.md) väljer du fliken **Väntande åtgärder** (eller **Åtgärder).**

2. Markera ett objekt i listan och välj sedan **Godkänna** eller **Avvisa**.

## <a name="next-steps"></a>Nästa steg

- [Läs mer om Åtgärdscentret](mtp-action-center.md)

- [Läs mer om incidenter](incidents-overview.md)

- [Lär dig mer om jakt](advanced-hunting-overview.md)
