---
title: Använd automatiska undersökningar för att undersöka och åtgärda hot
description: Förstå det automatiska undersökningsflödet i Microsoft Defender för Endpoint.
keywords: automatiserad, undersökning, identifiering, Microsoft Defender för slutpunkt
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
ms.date: 02/02/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.custom: AIR
ms.openlocfilehash: e52471e1b3e9ee3a410de493b536f9d360d60624
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844448"
---
# <a name="overview-of-automated-investigations"></a>Översikt över automatiserade undersökningar

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


Vill du se hur det fungerar? Titta på följande video: <br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bOeh]

Tekniken i automatiserad undersökning använder olika kontrollalgoritmer och baseras på processer som används av säkerhetsanalytiker. AIR-funktionerna är utformade för att undersöka aviseringar och vidta omedelbar åtgärd för att lösa överträdelser. AIR-funktioner sänker meddelandevolymen avsevärt, vilket gör att säkerhetsåtgärder kan fokusera på mer avancerade hot och andra viktiga initiativ. Alla åtgärdsåtgärder, oavsett om de är väntande eller slutförda, spåras i [Åtgärdscenter.](auto-investigation-action-center.md) I Åtgärdscenter godkänns väntande åtgärder (eller avvisas) och slutförda åtgärder kan ångras om det behövs.

Den här artikeln innehåller en översikt över AIR med länkar till nästa steg och ytterligare resurser.

> [!TIP]
> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automated-investigations-abovefoldlink).

## <a name="how-the-automated-investigation-starts"></a>Hur den automatiska undersökningen startar

En automatiserad undersökning kan starta när en avisering utlöses eller när en säkerhetsoperator initierar undersökningen.

|Situation  |Vad som händer  |
|---------|---------|
|En avisering utlöses     | I allmänhet startar en automatiserad undersökning när [en](review-alerts.md) avisering utlöses och [en incident](view-incidents-queue.md) skapas. Anta till exempel att en skadlig fil finns på en enhet. När filen identifieras utlöses en avisering och ett incident skapas. En automatiserad undersökningsprocess påbörjas på enheten. När andra aviseringar genereras på grund av samma fil på andra enheter läggs de till i den associerade incidenten och i den automatiska undersökningen.         |
|En undersökning startas manuellt     | En automatiserad undersökning kan startas manuellt av säkerhetsgruppen. Anta till exempel att en säkerhetsoperatör granskar en lista över enheter och märker att en enhet har hög risknivå. Säkerhetsoperatorn kan välja enheten i listan för att öppna dess utfällning och sedan välja **Initiera automatisk undersökning.** |

## <a name="how-an-automated-investigation-expands-its-scope"></a>Så här utökar en automatiserad undersökning dess omfattning

Medan en undersökning körs läggs alla andra aviseringar som genereras från enheten till i en pågående automatiserad undersökning tills undersökningen har slutförts. Om samma hot visas på andra enheter läggs dessa enheter dessutom till i undersökningen.

Om en okritisk enhet visas på en annan enhet utökas processen för automatisk undersökning så att den omfattar den enheten, och en allmän säkerhetsspelbok startar på den enheten. Om 10 eller fler enheter hittas under den här expansionsprocessen från samma entitet kräver den expanderingsåtgärden ett godkännande och visas på fliken **Väntande** åtgärder.

## <a name="how-threats-are-remediated"></a>Hur hot åtgärdas

När aviseringar utlöses och en automatiserad undersökning körs genereras en bedömning för varje bevis som undersöks. Bedömningarna kan vara 
- *Skadlig*;
- *Misstänkt –* om du har en misstänkt e eller 
- *Inga hot hittades*. 

Eftersom bedömningarna nås kan automatiska undersökningar resultera i en eller flera åtgärder. Exempel på åtgärder är att skicka en fil till karantän, stoppa en tjänst, ta bort en schemalagd aktivitet och mycket mer. Mer information finns [i Åtgärder .](manage-auto-investigation.md#remediation-actions)  

Beroende på [hur automatiseringsnivån](automation-levels.md) är inställd för organisationen, samt andra säkerhetsinställningar, kan åtgärder vidtas automatiskt eller bara vid godkännande från säkerhetsteamet. Ytterligare säkerhetsinställningar som kan påverka automatisk åtgärd är bland [annat skydd mot potentiellt oönskade program](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) (PUA). 

Alla åtgärdsåtgärder, oavsett om de är väntande eller slutförda, spåras i [Åtgärdscenter.](auto-investigation-action-center.md) Om det behövs kan säkerhetsåtgärdsteamet ångra en åtgärd. Mer information finns i [Granska och godkänna åtgärdsåtgärder efter en automatiserad undersökning.](/microsoft-365/security/defender-endpoint/manage-auto-investigation)

> [!TIP]
> Titta på den nya sidan för enhetlig undersökning i Microsoft 365 säkerhetscenter. Mer information finns i [(NYTT!) Sida för enhetlig undersökning](/microsoft-365/security/defender/m365d-autoir-results#new-unified-investigation-page).


## <a name="requirements-for-air"></a>Krav för AIR

Din organisation måste ha Defender för Slutpunkt (se [Minimikraven för Microsoft Defender för Slutpunkt](minimum-requirements.md)).

För närvarande stöder AIR endast följande OS-versioner:
- Windows Server 2019
- Windows 10, version 1709 (OS Build 16299.1085 med [KB4493441)](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441)eller senare
- Windows 10, version 1803 (OS-version 17134.704 med [KB4493464)](https://support.microsoft.com/help/4493464/windows-10-update-kb4493464)eller senare
- Windows 10, version [1803](/windows/release-information/status-windows-10-1809-and-windows-server-2019) eller senare

## <a name="next-steps"></a>Nästa steg

- [Läs mer om automatiseringsnivåer](automation-levels.md)
- [Se den interaktiva guiden: Undersöka och åtgärda hot med Microsoft Defender för Slutpunkt](https://aka.ms/MDATP-IR-Interactive-Guide)
- [Konfigurera funktioner för automatisk undersökning och åtgärder i Microsoft Defender för Endpoint](configure-automated-investigations-remediation.md)

## <a name="see-also"></a>Se även

- [PUA-skydd](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [Automatisk undersökning och svar i Microsoft Defender för Office 365](/microsoft-365/security/office-365-security/office-365-air)
- [Automatiserad undersökning och svar i Microsoft 365 Defender](/microsoft-365/security/defender/mtp-autoir)
