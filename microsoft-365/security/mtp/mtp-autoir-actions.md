---
title: Godkänna eller avvisa väntande åtgärder efter en automatiserad undersökning
description: Använda Åtgärdscenter för att hantera åtgärder relaterade till automatiserad undersökning och svar
keywords: åtgärd, center, autoair, automatiserad, undersökning, svar, åtgärd
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
ms.date: 12/09/2020
ms.technology: m365d
ms.openlocfilehash: 3776dea4a5a24f4695a5c617325af14f1f03494f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930384"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a>Godkänna eller avvisa väntande åtgärder efter en automatiserad undersökning

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

När en automatiserad undersökning körs kan det resultera i en eller [flera åtgärder](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) som kräver godkännande för att fortsätta. Till exempel kan ett kluster av e-postmeddelanden behöva tas bort eller så kan en karantänfil behöva tas bort. Det är viktigt att godkänna (eller avvisa) väntande åtgärder så snart som möjligt så att automatiserade undersökningar kan fortsätta och slutföras i tid. 

> [!TIP]
> Om du tror att något har missats eller identifierats felaktigt av en automatiserad undersökning och svarsfunktioner i Microsoft 365 Defender, berätta det för oss! Se hur du rapporterar falska positiva/negativa tal i automatisk undersökning och [svarsfunktioner (AIR) i Microsoft 365 Defender.](mtp-autoir-report-false-positives-negatives.md)

Väntande åtgärder kan granskas och godkännas med hjälp av [åtgärdscenter](#review-a-pending-action-in-the-action-center) eller [vyn med undersökningsinformation.](#review-a-pending-action-in-the-investigation-details-view)

> [!NOTE]
> Du måste ha [tillräcklig behörighet](mtp-action-center.md#required-permissions-for-action-center-tasks) för att godkänna eller avvisa åtgärder. Mer information finns i [Förutsättningarna för automatisk undersökning och svar i Microsoft 365 Defender.](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)

## <a name="review-a-pending-action-in-the-action-center"></a>Granska en väntande åtgärd i Åtgärdscenter

1. Gå till [https://security.microsoft.com](https://security.microsoft.com) och logga in. 

2. Välj Åtgärdscenter i **navigeringsfönstret.** 

3. Markera ett objekt i listan på **fliken** Väntande i Åtgärdscenter. 

    - Om du väljer ett objekt i **kolumnen Undersökningsnummer** öppnas sidan undersökningsinformation. Där kan du visa resultatet av undersökningen och sedan godkänna eller avvisa den rekommenderade åtgärden.
 
    - Om du markerar en rad i listan öppnas en utfällig meny där du kan visa information om objektet. <br/>![Godkänna eller avvisa en åtgärd](../../media/air-actioncenter-itemselected.png)<br/>Använd länkarna för att visa en associerad varning eller undersökning och godkänn eller avvisa åtgärden.

## <a name="review-a-pending-action-in-the-investigation-details-view"></a>Granska en väntande åtgärd i vyn med undersökningsinformation

![Undersökningsinformation](../../media/mtp-air-investdetails.png)

1. På en [sida med undersökningsinformation](mtp-autoir-results.md) väljer du **fliken Väntande åtgärder** **(eller** Åtgärder). Objekt som väntar på godkännande visas här.

2. Markera ett objekt i listan och välj sedan **Godkänn** eller **Avvisa.**

## <a name="undo-completed-actions"></a>Ångra slutförda åtgärder

Om du har fastställt att en enhet eller en fil inte är ett hot kan du ångra åtgärder som har vidtagits, oavsett om dessa åtgärder har vidtagits automatiskt eller manuellt. På fliken Historik i **Åtgärdscenter** kan du ångra något av följande:  

| Åtgärdskälla | Åtgärder som stöds |
|:---|:---|
| - Automatiserad undersökning <br/>- Microsoft Defender Antivirus <br/>- Manuella svarsåtgärder | - Isolera enhet <br/>- Begränsa kodkörning <br/>- Sätt en fil i karantän <br/>- Ta bort en registernyckel <br/>- Stoppa en tjänst <br/>- Inaktivera en drivrutin <br/>- Ta bort en schemalagd aktivitet |

### <a name="to-undo-a-remediation-action"></a>Ångra en åtgärdsåtgärd

1. Gå till Åtgärdscenter [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () och logga in.

2. Välj en **åtgärd** som du vill ångra på fliken Historik.

3. Välj Ångra i fönstret till höger på **skärmen.**

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>Ta bort en fil från karantän på flera enheter 

1. Gå till Åtgärdscenter [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () och logga in.

2. Välj en **fil** som har karantänfilen åtgärdstyp på fliken **Historik.**

3. I fönstret till höger på skärmen väljer du Använd för **fler X-förekomster** av den här filen och sedan **Ångra.**

## <a name="next-steps"></a>Nästa steg

- [Visa information och resultat från en automatiserad undersökning](mtp-autoir-results.md)
- [Hantera falska positiva/negativa tal i automatisk undersökning och svarsfunktioner](mtp-autoir-report-false-positives-negatives.md)
