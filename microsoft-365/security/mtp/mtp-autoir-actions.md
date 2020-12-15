---
title: Godkänna eller avvisa väntande åtgärder efter en automatisk undersökning
description: Använd åtgärds centret för att hantera åtgärder relaterade till automatiserad undersökning och svar
keywords: åtgärd, Center, autoair, automatiserad, undersökning, svar, reparation
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
ms.date: 12/09/2020
ms.openlocfilehash: b34f4a532571d6215500ab2bec022489fd462d0f
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683373"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a>Godkänna eller avvisa väntande åtgärder efter en automatisk undersökning

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

När en automatisk undersökning körs kan den resultera i en eller flera [reparations åtgärder](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) som kräver godkännande för att fortsätta. Ett kluster med e-postmeddelanden kan till exempel behöva tas bort, eller så måste en fil i karantän tas bort. Det är viktigt att godkänna (eller avvisa) pågående åtgärder så snart som möjligt så att dina automatiserade utredningar kan fortsätta och genomföras i god tid. 

> [!TIP]
> Om du tror att något har missats eller upptäckts felaktigt av automatiserade undersökningar och svars funktioner i Microsoft 365 Defender kan du tala om det för oss! Lär dig [hur du rapporterar falskta positiva eller negativa negativ i en automatiserad undersökning och svar (Air) i Microsoft 365 Defender](mtp-autoir-report-false-positives-negatives.md).

Väntande åtgärder kan granskas och godkännas med hjälp av [Åtgärds centret](#review-a-pending-action-in-the-action-center) eller [vyn granska information](#review-a-pending-action-in-the-investigation-details-view).

> [!NOTE]
> Du måste ha [rätt behörighet](mtp-action-center.md#required-permissions-for-action-center-tasks) för att godkänna eller avvisa reparations åtgärder. För mer information, se [förutsättningar för automatisk undersökning och svar i Microsoft 365 Defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).

## <a name="review-a-pending-action-in-the-action-center"></a>Granska en väntande åtgärd i åtgärds centret

1. Gå till [https://security.microsoft.com](https://security.microsoft.com) och logga in. 

2. I navigerings fönstret väljer du **Åtgärds Center**. 

3. På fliken **förestående** i åtgärds Center väljer du ett objekt i listan. 

    - Om du markerar ett objekt i kolumnen **analys nummer** öppnas sidan med gransknings information. Där kan du se resultatet av undersökningen och sedan antingen godkänna eller avvisa den rekommenderade åtgärden.
 
    - Om du markerar en rad i listan öppnas en utfällbar tabell där du kan visa information om objektet. <br/>![Godkänna eller avvisa en åtgärd](../../media/air-actioncenter-itemselected.png)<br/>Använd länkarna för att visa en associerad avisering eller en undersökning och godkänna eller avvisa åtgärden.

## <a name="review-a-pending-action-in-the-investigation-details-view"></a>Granska en väntande åtgärd i vyn granska information

![Gransknings uppgifter](../../media/mtp-air-investdetails.png)

1. På en [undersöknings](mtp-autoir-results.md) sida väljer du fliken **pågående åtgärder** (eller **åtgärder**). Objekt som väntar på godkännande finns här.

2. Markera ett objekt i listan och välj sedan **Godkänn** eller **avvisa**.

## <a name="next-steps"></a>Nästa steg

- [Visa information och resultat från en automatisk undersökning](mtp-autoir-results.md)
- [Hantera felaktiga positiva/negativa negativ i automatiserade undersökningar och svars funktioner](mtp-autoir-report-false-positives-negatives.md)
