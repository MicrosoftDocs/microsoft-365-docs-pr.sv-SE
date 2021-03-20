---
title: Visa och hantera åtgärder i Åtgärdscenter
description: Använda Åtgärdscenter för att visa och hantera åtgärdsåtgärder
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
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 01/29/2021
ms.technology: m365d
ms.openlocfilehash: fe2c3d4112663b4046a9d503aefc45f832c6c143
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50917110"
---
# <a name="view-and-manage-actions-in-the-action-center"></a>Visa och hantera åtgärder i Åtgärdscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Skyddsfunktioner i Microsoft 365 Defender kan resultera i vissa åtgärder. Här är några exempel:
- [Automatiserade undersökningar](mtp-autoir.md) kan resultera i åtgärder som vidtas automatiskt eller väntar på godkännande.
- Antivirusprogram, program mot skadlig programvara och andra skyddsfunktioner mot hot kan resultera i åtgärder som att blockera en fil, url eller process, eller skicka en artefakt till karantän.
- Ditt team för säkerhetsåtgärder kan vidta åtgärder manuellt, till exempel [under](advanced-hunting-overview.md) avancerad sökning eller under undersökning [av aviseringar](investigate-alerts.md) eller [incidenter.](investigate-incidents.md)

> [!NOTE]
> Du måste ha [tillräcklig behörighet](mtp-action-center.md#required-permissions-for-action-center-tasks) för att godkänna eller avvisa åtgärder. Mer information finns i Krav [för automatiserad undersökning och svar i Microsoft 365 Defender.](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)

## <a name="review-pending-actions-in-the-action-center"></a>Granska väntande åtgärder i Åtgärdscenter

Det är viktigt att godkänna (eller avvisa) väntande åtgärder så snart som möjligt så att de automatiska undersökningarna kan fortsätta och slutföras i tid. 

![Godkänna eller avvisa en åtgärd](../../media/air-actioncenter-itemselected.png)

1. Gå till [https://security.microsoft.com](https://security.microsoft.com) och logga in. 
2. Välj Åtgärdscenter i **navigeringsfönstret.** 
3. Välj ett objekt i **listan på fliken** Väntande i Åtgärdscenter. Den utfällna rutan öppnas.
4. Granska informationen i det utfällfönster som visas och gör sedan något av följande:
   - Välj **Sidan Öppna undersökning** om du vill visa mer information om undersökningen.
   - Välj **Godkänn** för att påbörja en väntande åtgärd.
   - Välj **Avvisa** för att förhindra att en väntande åtgärd vidtas.
   - Välj **Sök för** att gå till Avancerad [sökning](advanced-hunting-overview.md). 

## <a name="undo-completed-actions"></a>Ångra slutförda åtgärder

Om du har fastställt att en enhet eller en fil inte är ett hot kan du ångra åtgärder som har vidtagits, oavsett om dessa åtgärder har vidtagits automatiskt eller manuellt. På fliken Historik i **Åtgärdscenter** kan du ångra något av följande:  

| Åtgärdskälla | Åtgärder som stöds |
|:---|:---|
| - Automatiserad undersökning <br/>- Microsoft Defender Antivirus <br/>- Manuella svarsåtgärder | - Isolera enhet <br/>- Begränsa kodkörning <br/>- Sätt en fil i karantän <br/>- Ta bort en registernyckel <br/>- Stoppa en tjänst <br/>- Inaktivera en drivrutin <br/>- Ta bort en schemalagd aktivitet |

### <a name="undo-one-remediation-action"></a>Ångra en åtgärd

1. Gå till Åtgärdscenter ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) och logga in.
2. Välj **en åtgärd** som du vill ångra på fliken Historik.
3. I fönstret till höger på skärmen väljer du **Ångra**.

### <a name="undo-multiple-remediation-actions"></a>Ångra flera åtgärder

1. Gå till Åtgärdscenter https://security.microsoft.com/action-center) (och logga in).
2. Markera **de åtgärder** du vill ångra på fliken Historik. Se till att markera objekt som har samma åtgärdstyp. Ett utfällt fönster öppnas.
3. Välj Ångra i den utfällade **rutan.**

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>Ta bort en fil från karantän på flera enheter 

1. Gå till Åtgärdscenter ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) och logga in.
2. På fliken **Historik** väljer du en fil som har karantänfilen **Åtgärdstyp.**
3. I fönstret till höger på skärmen väljer du Använd för **fler X-instanser** av den här filen och sedan **Ångra**.

## <a name="next-steps"></a>Nästa steg

- [Visa information och resultat från en automatiserad undersökning](mtp-autoir-results.md)
- [Lär dig hur du hanterar falska positiva/negativa tal (om du får ett)](mtp-autoir-report-false-positives-negatives.md)
