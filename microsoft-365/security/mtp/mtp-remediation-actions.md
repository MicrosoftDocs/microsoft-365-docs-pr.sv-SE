---
title: Åtgärdsåtgärder i Microsoft 365 Defender
description: Få en översikt över åtgärder som följer automatiska undersökningar i Microsoft 365 Defender
keywords: automatiserad, undersökning, avisering, utlösare, åtgärd, åtgärd
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
ms.date: 01/29/2021
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 7dd95e8d7fe6424e294fbc9500fb908819463678
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928634"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a>Åtgärdsåtgärder i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

## <a name="remediation-actions"></a>Reparationsåtgärder

Under och efter en automatiserad undersökning i Microsoft 365 Defender identifieras åtgärder för skadliga eller misstänkta objekt. Vissa typer av åtgärdsåtgärder vidtas på enheter, även kallade slutpunkter. Andra åtgärder vidtas på e-postinnehållet. Automatiserade undersökningar slutförs efter att åtgärder har vidtagits, godkänts eller avvisats.

> [!IMPORTANT]
> Om åtgärder vidtas automatiskt eller bara på godkännande beror på vissa inställningar, till exempel hur automatiseringsnivåer används. Mer information finns i följande artiklar:
> - [Konfigurera automatisk undersökning och svarsfunktioner i Microsoft 365 Defender](mtp-configure-auto-investigation-response.md)
> - [Hur hot åtgärdas på enheter](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
> - [Hot och åtgärdsåtgärder för e-& och samarbetsinnehåll](../office-365-security/air-remediation-actions.md#threats-and-remediation-actions)

I följande tabell sammanfattas de åtgärder som stöds för närvarande i Microsoft 365 Defender: 

|Åtgärdsåtgärder för enhet (slutpunkt)  |Åtgärder för e-postreparation  |
|:---------|:---------|
|- Paket för insamling av undersökning <br/>- Isolera enhet (den här åtgärden kan ångras)<br/>- Offboard-dator <br/>- Körning av släppkod <br/>- Släpp från karantän <br/>- Exempel på förfrågan <br/>– Begränsa körning av kod (den här åtgärden kan ångras) <br/>- Kör antivirussökning <br/>- Stopp och karantän      |- Blockera URL (tid för klickning)<br/>- Mjuk borttagning av e-postmeddelanden eller kluster<br/>- Sätt e-post i karantän<br/>– sätt i karantän för en e-postbilaga<br/>- Inaktivera vidarebefordran av extern e-post          |

Åtgärdsåtgärder, oavsett om de väntar på godkännande eller redan har slutförts, kan visas i [Åtgärdscenter.](./mtp-action-center.md)

## <a name="remediation-actions-that-follow-automated-investigations"></a>Åtgärdsåtgärder som följer automatiska undersökningar

När en automatiserad undersökning har slutförts nås en bedömning för alla bevis som ingår. Beroende på omdömet identifieras åtgärdsåtgärder. I vissa fall vidtas åtgärder automatiskt. i andra fall väntar åtgärder på godkännande. Det beror på hur [automatisk undersökning och svar har konfigurerats.](mtp-configure-auto-investigation-response.md)

I följande tabell visas möjliga bedömningar och resultat:

| Bedömning    | Område    | Resultat|
|------|------|------|
| Skadlig    | Enheter (slutpunkter)    | Åtgärdsåtgärder vidtas automatiskt (under förutsättning att din organisations [enhetsgrupper](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) är inställda på **Fullständiga – åtgärda hot automatiskt)**|
| Skadlig    | E-postinnehåll (URL:er eller bifogade filer) | Rekommenderade åtgärdsåtgärder väntar på godkännande|
| Misstänkt    | Enheter eller e-postinnehåll | Rekommenderade åtgärdsåtgärder väntar på godkännande|
| Inga hot hittades    | Enheter eller e-postinnehåll    | Inga åtgärder krävs|


## <a name="remediation-actions-that-are-taken-manually"></a>Åtgärder som vidtas manuellt

Förutom åtgärder som följer på automatiska undersökningar kan säkerhetsoperationsteamet vidta vissa åtgärder manuellt. Detta omfattar följande åtgärder:

- Manuell enhetsåtgärd, till exempel enhetsisolering eller karantänen för filer.
- Manuell e-poståtgärd, till exempel mjuk borttagning av e-postmeddelanden. 
- [Avancerad sökåtgärd](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) på enheter eller e-post.
- [Åtgärden](../office-365-security/threat-explorer.md) i Utforskaren för e-postinnehåll, t.ex. flytta e-post till skräppost, mjuk borttagning av e-post eller borttagning av e-post.
- Manuell [svarsåtgärd,](/windows/security/threat-protection/microsoft-defender-atp/live-response) till exempel ta bort en fil, stoppa en process och ta bort en schemalagd aktivitet.
- Åtgärd för livesvar med Microsoft Defender för [slutpunkts-API:er,](/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis)till exempel att isolera en enhet, köra en antivirussökning och hämta information om en fil. 

## <a name="next-steps"></a>Nästa steg

- [Besök åtgärden centret](./mtp-action-center.md)
- [Visa och hantera åtgärdsåtgärder](./mtp-autoir-actions.md)
- [Hantera falska positiva/negativa i automatiska undersöknings- och svarsfunktioner](mtp-autoir-report-false-positives-negatives.md)