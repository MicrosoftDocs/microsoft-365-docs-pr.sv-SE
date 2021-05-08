---
title: Granska åtgärdsåtgärder efter automatiska undersökningar
description: Granska och godkänna (eller avvisa) åtgärdsåtgärder efter en automatiserad undersökning.
keywords: autoir, automatiserad, undersökning, identifiering, åtgärd, väntande, godkänd
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.date: 01/29/2021
ms.technology: mde
ms.openlocfilehash: b0c983f4ba939cee6485570af774c8a728c73944
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274934"
---
# <a name="review-remediation-actions-following-an-automated-investigation"></a>Granska åtgärdsåtgärder efter en automatiserad undersökning

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


## <a name="remediation-actions"></a>Reparationsåtgärder

När en [automatiserad undersökning](automated-investigations.md) körs genereras en bedömning för varje bevis som undersöks. Omdömen kan vara *skadliga,* *misstänkta* eller *inga hot hittades.* 

Beroende på

- typen av hot, 
- den resulterande bedömningen och 
- hur din organisations [enhetsgrupper](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups) konfigureras 

Åtgärdsåtgärder kan ske automatiskt eller bara om godkännande har godkänts av organisationens team för säkerhetsåtgärder. 

Här är några exempel:

- **Exempel 1:** Fabrikams enhetsgrupper är inställda på **Fullständiga –** åtgärda hot automatiskt (den rekommenderade inställningen). I det här fallet vidtas åtgärder automatiskt för artefakter som anses vara skadliga efter en automatiserad undersökning (se [Granska slutförda åtgärder).](#review-completed-actions)

- **Exempel 2:** Contosos enheter ingår i en enhetsgrupp som är inställd på Semi – kräver **godkännande för alla åtgärder.** I det här fallet måste Contosos säkerhetsoperationsteam granska och godkänna alla åtgärder efter en automatiserad undersökning (se [Granska väntande åtgärder](#review-pending-actions)).

- **Exempel 3:** Tailspin Toys har sina enhetsgrupper inställda på **Inget automatiskt svar** (rekommenderas inte). I det här fallet förekommer inte automatiska undersökningar. Inga åtgärder vidtas eller väntar och inga åtgärder loggas [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center) i Åtgärdscenter för sina enheter (se [Hantera enhetsgrupper](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups#manage-device-groups)).

Oavsett om en automatisk undersökning vidtas automatiskt eller efter godkännande kan en automatiserad undersökning resultera i en eller flera av åtgärderna:
- Sätt en fil i karantän
- Ta bort en registernyckel 
- "Kill a process" 
- Stoppa en tjänst 
- Inaktivera en drivrutin 
- Ta bort en schemalagd aktivitet

## <a name="review-pending-actions"></a>Granska väntande åtgärder

1. Gå till Microsoft 365 ( ) [https://security.microsoft.com](https://security.microsoft.com) och logga in.
2. Välj Åtgärdscenter i **navigeringsfönstret.** 
3. Granska objekten på **fliken Väntande.** 
4. Välj en åtgärd för att öppna det utfällade fönstret.
5. Granska informationen i den utfällade fönsterrutan och gör sedan något av följande:
   - Välj **Sidan Öppna undersökning** om du vill visa mer information om undersökningen.
   - Välj **Godkänn** för att påbörja en väntande åtgärd.
   - Välj **Avvisa** för att förhindra att en väntande åtgärd vidtas.
   - Välj **Sök för** att gå till Avancerad [sökning](advanced-hunting-overview.md). 

## <a name="review-completed-actions"></a>Granska slutförda åtgärder

1. Gå till Microsoft 365 ( ) [https://security.microsoft.com](https://security.microsoft.com) och logga in.
2. Välj Åtgärdscenter i **navigeringsfönstret.** 
3. Granska objekten på **fliken** Historik. 
4. Markera ett objekt om du vill visa mer information om den åtgärden.
 
## <a name="undo-completed-actions"></a>Ångra slutförda åtgärder

Om du har fastställt att en enhet eller en fil inte är ett hot kan du ångra åtgärder som har vidtagits, oavsett om dessa åtgärder har vidtagits automatiskt eller manuellt. På fliken Historik i **Åtgärdscenter** kan du ångra något av följande:  

| Åtgärdskälla | Åtgärder som stöds |
|:---|:---|
| - Automatiserad undersökning <br/>- Microsoft Defender Antivirus <br/>- Manuella svarsåtgärder | - Isolera enhet <br/>- Begränsa kodkörning <br/>- Sätt en fil i karantän <br/>- Ta bort en registernyckel <br/>- Stoppa en tjänst <br/>- Inaktivera en drivrutin <br/>- Ta bort en schemalagd aktivitet |

### <a name="to-undo-multiple-actions-at-one-time"></a>Ångra flera åtgärder samtidigt

1. Gå till Åtgärdscenter ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) och logga in.
2. Markera **de åtgärder** du vill ångra på fliken Historik. Se till att markera objekt som har samma åtgärdstyp. Ett utfällt fönster öppnas.
3. Välj Ångra i den utfällade **rutan.**

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>Ta bort en fil från karantän på flera enheter 

1. Gå till Åtgärdscenter ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) och logga in.
2. På fliken **Historik** väljer du ett objekt som har karantänfilen **Åtgärdstyp.**
3. Välj Använd på X fler instanser av **filen i det utfällade fönstret** och välj sedan **Ångra**.

## <a name="automation-levels-automated-investigation-results-and-resulting-actions"></a>Automatiseringsnivåer, automatiska undersökningsresultat och resulterande åtgärder

Automatiseringsnivåer påverkar om vissa åtgärder vidtas automatiskt eller bara vid godkännande. Ibland har säkerhetsoperationsteamet fler åtgärder att vidta, beroende på resultatet av en automatiserad undersökning. I följande tabell sammanfattas automationsnivåer, resultaten från automatiserade undersökningar och vad du ska göra i varje fall. 

|Enhetsgruppinställning | Resultat från automatiserad undersökning | Vad kan jag göra? |
|:---|:---|:---|
|**Full – åtgärda hot automatiskt** (den rekommenderade inställningen) |En bedömning av *skadlig* är uppnådd för ett bevis. <br/><br/>Lämpliga åtgärder vidtas automatiskt. |[Granska slutförda åtgärder](#review-completed-actions) |
|**Full – åtgärda hot automatiskt** |En bedömning av *misstänkt* resultat har uppnåtts om det finns bevis för det. <br/><br/>Åtgärdsåtgärder väntar på godkännande för att fortsätta. | [Godkänna (eller avvisa) väntande åtgärder](#review-pending-actions) |
|**Semi – kräv godkännande för åtgärd**  |En bedömning av *antingen* Skadlig *eller Misstänkt* har nåtts som bevis. <br/><br/>Åtgärdsåtgärder väntar på godkännande för att fortsätta.  |[Godkänna (eller avvisa) väntande åtgärder](#review-pending-actions) |
|**Semi – kräver godkännande för åtgärd av basmappar** |En bedömning av *skadlig* är uppnådd för ett bevis. <br/><br/>Om artefakten är en fil eller körbar och finns i en operativsystemkatalog, till exempel mappen Windows eller mappen Programfiler, väntar åtgärder på att godkännas. <br/><br/>Om artefakten *inte* finns i en katalog i operativsystemet vidtas åtgärder automatiskt. |1. [Godkänna (eller avvisa) väntande åtgärder](#review-pending-actions)<br/><br/>2. [Granska slutförda åtgärder](#review-completed-actions) |
|**Semi – kräver godkännande för åtgärd av basmappar** |En bedömning av *misstänkt* resultat har uppnåtts om det finns bevis för det. <br/><br/>Åtgärdsåtgärder väntar på godkännande.  |[Godkänna (eller avvisa) väntande åtgärder](#review-pending-actions).|
|**Semi – kräver godkännande för åtgärder som inte är tillfälliga mappar** |En bedömning av *skadlig* är uppnådd för ett bevis. <br/><br/>Om artefakten är en fil eller körbar som inte finns i en tillfällig mapp, till exempel användarens mapp för nedladdningar eller tillfällig mapp, väntar åtgärder på att godkännas. <br/><br/>Om artefakten är en fil eller körbar *som* finns i en tillfällig mapp vidtas åtgärder automatiskt.  |1. [Godkänna (eller avvisa) väntande åtgärder](#review-pending-actions)<br/><br/>2. [Granska slutförda åtgärder](#review-completed-actions)  |
|**Semi – kräver godkännande för åtgärder som inte är tillfälliga mappar** |En bedömning av *misstänkt* resultat har uppnåtts om det finns bevis för det. <br/><br/>Åtgärdsåtgärder väntar på godkännande. |[Godkänna (eller avvisa) väntande åtgärder](#review-pending-actions)  | 
|Alla automationsnivåer **med helt** **eller semi** |En bedömning av *Inga hot hittades* som bevis. <br/><br/>Inga åtgärdsåtgärder vidtas och inga åtgärder väntar på att godkännas. |[Visa detaljer och resultat av automatiserade undersökningar](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/auto-investigation-action-center) |
|**Inget automatiskt svar** (rekommenderas inte)|Ingen automatiserad undersökning körs, så inga bedömningar har uppnåtts och inga åtgärder vidtas eller väntar på godkännande. |[Överväg att konfigurera eller ändra enhetsgrupper så att fullständig **eller** **semi-automation** används](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups) |

I Microsoft Defender för Endpoint spåras alla beslut i [Åtgärdscenter](auto-investigation-action-center.md#new-a-unified-action-center).

## <a name="next-steps"></a>Nästa steg

- [Läs mer om funktioner för livesvar](live-response.md)
- [Proaktiv sökning efter hot med avancerad sökning](advanced-hunting-overview.md)
- [Åtgärda falska positiva/negativa i Microsoft Defender för Endpoint](defender-endpoint-false-positives-negatives.md)

## <a name="see-also"></a>Se även

- [Översikt över automatiserade undersökningar](automated-investigations.md)
