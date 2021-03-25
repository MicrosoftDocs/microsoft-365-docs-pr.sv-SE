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
localization_priority: Normal
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
ms.openlocfilehash: c81f824a0faaca1c228aa650c003576cce210a67
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199213"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a>Åtgärdsåtgärder i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

## <a name="remediation-actions"></a>Reparationsåtgärder

Under och efter en automatiserad undersökning i Microsoft 365 Defender identifieras åtgärder för skadliga eller misstänkta objekt. Vissa typer av åtgärdsåtgärder vidtas på enheter, även kallade slutpunkter. Andra åtgärder vidtas på e-postinnehållet. Automatiserade undersökningar slutförs efter att åtgärder har vidtagits, godkänts eller avvisats.

> [!IMPORTANT]
> Om åtgärder vidtas automatiskt eller bara på godkännande beror på vissa inställningar, till exempel hur automatiseringsnivåer används. Mer information finns i följande artiklar:
> - [Konfigurera automatisk undersökning och svarsfunktioner i Microsoft 365 Defender](m365d-configure-auto-investigation-response.md)
> - [Hur hot åtgärdas på enheter](../defender-endpoint/automated-investigations.md)
> - [Hot och åtgärdsåtgärder för e-& och samarbetsinnehåll](../office-365-security/air-remediation-actions.md#threats-and-remediation-actions)

I följande tabell sammanfattas de åtgärder som stöds för närvarande i Microsoft 365 Defender: 

|Åtgärdsåtgärder för enhet (slutpunkt)  |Åtgärder för e-postreparation  |
|:---------|:---------|
|- Paket för insamling av undersökning <br/>- Isolera enhet (den här åtgärden kan ångras)<br/>- Offboard-dator <br/>- Körning av släppkod <br/>- Släpp från karantän <br/>- Exempel på förfrågan <br/>– Begränsa körning av kod (den här åtgärden kan ångras) <br/>- Kör antivirussökning <br/>- Stopp och karantän      |- Blockera URL (tid för klickning)<br/>- Mjuk borttagning av e-postmeddelanden eller kluster<br/>- Sätt e-post i karantän<br/>– sätt i karantän för en e-postbilaga<br/>- Inaktivera vidarebefordran av extern e-post          |

Åtgärdsåtgärder, oavsett om de väntar på godkännande eller redan har slutförts, kan visas i [Åtgärdscenter.](m365d-action-center.md)

## <a name="remediation-actions-that-follow-automated-investigations"></a>Åtgärdsåtgärder som följer automatiska undersökningar

När en automatiserad undersökning har slutförts nås en bedömning för alla bevis som ingår. Beroende på omdömet identifieras åtgärdsåtgärder. I vissa fall vidtas åtgärder automatiskt. i andra fall väntar åtgärder på godkännande. Det beror på hur [automatisk undersökning och svar har konfigurerats.](m365d-configure-auto-investigation-response.md)

I följande tabell visas möjliga bedömningar och resultat:

| Bedömning    | Område    | Resultat|
|------|------|------|
| Skadlig    | Enheter (slutpunkter)    | Åtgärdsåtgärder vidtas automatiskt (under förutsättning att din organisations [enhetsgrupper](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) är inställda på **Fullständiga – åtgärda hot automatiskt)**|
| Skadlig    | E-postinnehåll (URL:er eller bifogade filer) | Rekommenderade åtgärdsåtgärder väntar på godkännande|
| Misstänkt    | Enheter eller e-postinnehåll | Rekommenderade åtgärdsåtgärder väntar på godkännande|
| Inga hot hittades    | Enheter eller e-postinnehåll    | Inga åtgärder krävs|


## <a name="remediation-actions-that-are-taken-manually"></a>Åtgärder som vidtas manuellt

Förutom åtgärder som följer på automatiska undersökningar kan säkerhetsoperationsteamet vidta vissa åtgärder manuellt. Detta omfattar följande åtgärder:

- Manuell enhetsåtgärd, till exempel enhetsisolering eller karantänen för filer.
- Manuell e-poståtgärd, till exempel mjuk borttagning av e-postmeddelanden. 
- [Avancerad sökåtgärd](../defender-endpoint/advanced-hunting-overview.md) på enheter eller e-post.
- [Åtgärden](../office-365-security/threat-explorer.md) i Utforskaren för e-postinnehåll, t.ex. flytta e-post till skräppost, mjuk borttagning av e-post eller borttagning av e-post.
- Manuell [svarsåtgärd,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) till exempel ta bort en fil, stoppa en process och ta bort en schemalagd aktivitet.
- Åtgärd för livesvar med Microsoft Defender för [slutpunkts-API:er,](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis)till exempel att isolera en enhet, köra en antivirussökning och hämta information om en fil. 

## <a name="next-steps"></a>Nästa steg

- [Besök åtgärden centret](m365d-action-center.md)
- [Visa och hantera åtgärdsåtgärder]( m365d-autoir-actions.md)
- [Hantera falska positiva/negativa i automatiska undersöknings- och svarsfunktioner](m365d-autoir-report-false-positives-negatives.md)
