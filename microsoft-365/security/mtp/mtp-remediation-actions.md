---
title: Åtgärdsåtgärder i Microsoft 365 Defender
description: Få en översikt över åtgärder som följer på automatiserade undersökningar i Microsoft 365 Defender
keywords: automatiserad, undersökning, varning, utlösare, åtgärd, åtgärd
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
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: c6b0275335f32419b470c789d83b069be7839c36
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932856"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a>Åtgärdsåtgärder i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

## <a name="remediation-actions"></a>Reparationsåtgärder

Under och efter en automatisk undersökning i Microsoft 365 Defender identifieras åtgärder för skadliga eller misstänkta objekt. Vissa typer av åtgärder vidtas på enheter, även kallade slutpunkter. Andra åtgärder vidtas på e-postinnehåll. Automatiserade undersökningar slutförs efter att åtgärder har vidtagits, godkänts eller avvisats.

> [!IMPORTANT]
> Huruvida åtgärder vidtas automatiskt eller bara på godkännande beror på vissa inställningar, till exempel hur automatiseringsnivåer används. Mer information finns i följande artiklar:
> - [Konfigurera automatisk undersökning och svarsfunktioner i Microsoft 365 Defender](mtp-configure-auto-investigation-response.md)
> - [Hur hot åtgärdas på enheter](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
> - [Hot och åtgärder för e-post och & samarbetsinnehåll](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions#threats-and-remediation-actions)

I följande tabell sammanfattas de åtgärder som stöds för närvarande i Microsoft 365 Defender: 

|Åtgärdsåtgärder för enhet (slutpunkt)  |Åtgärder för e-postreparation  |
|---------|---------|
|- Samla in undersökningspaket <br/>- Isolera enhet (den här åtgärden kan ångras)<br/>- Offboard-dator <br/>- Släppa kodkörning <br/>- Släpp från karantän <br/>- Exempel på förfrågan <br/>– Begränsa körning av kod (den här åtgärden kan ångras) <br/>- Kör antivirussökning <br/>- Stoppa och sätta i karantän      |- Blockera URL (tid för klickning)<br/>- Mjuk borttagning av e-postmeddelanden och kluster<br/>- Sätt e-post i karantän<br/>- Sätt en e-postbilaga i karantän<br/>- Inaktivera vidarebefordran av extern e-post          |

Åtgärdsåtgärder, oavsett om de väntar på godkännande eller redan har slutförts, kan visas i [Åtgärdscenter.](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)

## <a name="remediation-actions-that-follow-automated-investigations"></a>Åtgärdsåtgärder som följer på automatiska undersökningar

När en automatiserad undersökning slutförs, nås en bedömning för alla bevis som ingår. Beroende på vilket beslut det gäller identifieras åtgärdsåtgärder. I vissa fall vidtas åtgärder automatiskt. i andra fall väntar åtgärder på godkännande. Det beror på hur [automatisk undersökning och svar har konfigurerats.](mtp-configure-auto-investigation-response.md)

I följande tabell visas möjliga utfall:

| Bedömning    | Område    | Resultat|
|------|------|------|
| Skadlig    | Enheter (slutpunkter)    | Åtgärder vidtas automatiskt (under förutsättning att din organisations [enhetsgrupper](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) är inställda på Fullständiga – åtgärda **hot automatiskt)**|
| Skadlig    | E-postinnehåll (URL:er eller bifogade filer) | Rekommenderade åtgärder väntar på godkännande|
| Misstänkt    | Enheter eller e-postinnehåll | Rekommenderade åtgärder väntar på godkännande|
| Inga hot hittades    | Enheter eller e-postinnehåll    | Inga åtgärder krävs|


## <a name="remediation-actions-that-are-taken-manually"></a>Åtgärder som vidtas manuellt

Förutom åtgärder som följer på automatiserade undersökningar kan säkerhetsteamet även vidta vissa åtgärder manuellt. Det kan till exempel vara följande åtgärder:

- Manuell enhetsåtgärd, till exempel enhetsisolering eller karantän för filer.
- Manuell e-poståtgärd, till exempel mjuk borttagning av e-postmeddelanden. 
- [Avancerad sökåtgärd](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) på enheter eller e-post.
- [Åtgärder](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) i Utforskaren för e-postinnehåll, till exempel flytta e-post till skräppost, mjuk borttagning av e-post eller hård borttagning av e-post.
- Manuell [svarsåtgärd,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) till exempel att ta bort en fil, stoppa en process och ta bort en schemalagd aktivitet.
- Åtgärd för livesvar med [Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis)för slutpunkts-API:er, till exempel att isolera en enhet, köra en antivirussökning och hämta information om en fil. 

## <a name="next-steps"></a>Nästa steg

- [Besök åtgärden centret](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [Godkänna eller avvisa väntande åtgärder](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [Hantera falska positiva/negativa tal i automatisk undersökning och svarsfunktioner](mtp-autoir-report-false-positives-negatives.md)
