---
title: Automatiseringsnivåer i automatiserad undersökning och åtgärd
description: Få en översikt över automatiseringsnivåer och hur de fungerar i Microsoft Defender för Endpoint
keywords: automatiserad, undersökande, nivå, Microsoft Defender för Slutpunkt
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
ms.date: 10/22/2020
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.custom: AIR
ms.openlocfilehash: 6d453a8b6e5c4947c0fb03131c539b083227c28a
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844652"
---
# <a name="automation-levels-in-automated-investigation-and-remediation-capabilities"></a>Automatiseringsnivåer i automatiserad undersökning och åtgärdsfunktioner

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Funktioner för automatisk undersökning och åtgärder (AIR) i Microsoft Defender för Endpoint kan konfigureras på någon av flera nivåer av automatisering. Din automatiseringsnivå påverkar om åtgärder efter AIR-undersökningar vidtas automatiskt eller bara efter godkännande.  
- *Fullständig automation* (rekommenderas) innebär att åtgärder vidtas automatiskt på artefakter som fastställt vara skadliga.
- *Semi-automation* innebär att vissa åtgärder vidtas automatiskt, men andra åtgärder väntar på godkännande innan de vidtas. (Se tabellen i [Nivåer av automation](#levels-of-automation).)
- Alla åtgärdsåtgärder, oavsett om de är väntande eller slutförda, spåras i Åtgärdscenter ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ). 

> [!TIP]
> För bästa resultat rekommenderar vi att du använder fullständig automation när du [konfigurerar AIR.](configure-automated-investigations-remediation.md) Data som har samlats in och analyserats under det senaste året visar att kunder som använder fullständig automation hade 40 % mer högförtroende exempel på skadlig programvara borttagna än kunder som använder lägre automatiseringsnivåer. Fullständig automation kan frigöra dina resurser för säkerhetsåtgärder så att du kan fokusera mer på dina strategiska initiativ.

## <a name="levels-of-automation"></a>Nivåer av automation

I följande tabell beskrivs varje nivå av automatisering och hur det fungerar.

|Automationsnivå | Beskrivning|
|:---|:---|
|**Full – åtgärda hot automatiskt** <br/>(kallas även *fullständig automation)*| Med fullständig automation utförs åtgärdsåtgärder automatiskt. Alla åtgärder som vidtas kan visas i [Åtgärdscenter på](auto-investigation-action-center.md) fliken **Historik.** Om det behövs kan en åtgärd ångras.<br/><br/>**_Fullständig automation_* rekommenderas och väljs som standard för klientorganisationer som skapades den 16 augusti 2020 eller senare med Microsoft Defender för slutpunkten, utan att enhetsgrupper har definierats än.*  |
|**Semi – kräv godkännande för åtgärd** <br/>(kallas även *semi-automation)*| Med den här nivån av semi-automation krävs godkännande *för* alla åtgärder. Sådana väntande åtgärder kan visas och godkännas [i Åtgärdscenter](auto-investigation-action-center.md)på **fliken Väntande.**<br/><br/>*Den här nivån av semi-automation är markerad som standard för klientorganisationer som skapades före 16 augusti 2020 med Microsoft Defender för Slutpunkt, utan att enhetsgrupper har definierats.*|
|**Semi – kräver godkännande för åtgärd av basmappar** <br/>(också en typ av *semi-automation*)  | Med den här nivån av semi-automation krävs godkännande för åtgärder som krävs för filer eller körbara filer i huvudmappar. Basmappar innehåller operativsystemskataloger, till exempel **Windows** ( `\windows\*` ).<br/><br/>Åtgärder kan vidtas automatiskt på filer eller körbara filer som finns i andra mappar (icke-kärnmappar). <br/><br/>Väntande åtgärder för filer eller körbara filer i huvudmappar kan visas och godkännas i [Åtgärdscenter](auto-investigation-action-center.md)på **fliken Väntande.** <br/><br/>Åtgärder som har utförts på filer eller körbara filer i andra mappar kan visas i [Åtgärdscenter](auto-investigation-action-center.md)på **fliken Historik.** |
|**Semi – kräver godkännande för åtgärder som inte är tillfälliga mappar** <br/>(också en typ av *semi-automation*)| Med den här nivån av semi-automation krävs godkännande för åtgärder som krävs för filer eller körbara filer som inte *finns* i tillfälliga mappar. <br/><br/>Tillfälliga mappar kan innehålla följande exempel: <br/>- `\users\*\appdata\local\temp\*`<br/>- `\documents and settings\*\local settings\temp\*` <br/>- `\documents and settings\*\local settings\temporary\*`<br/>- `\windows\temp\*`<br/>- `\users\*\downloads\*`<br/>- `\program files\` <br/>- `\program files (x86)\*`<br/>- `\documents and settings\*\users\*`<br/><br/>Åtgärder kan vidtas automatiskt på filer eller körbara filer som finns i tillfälliga mappar. <br/><br/>Väntande åtgärder för filer eller körbara filer som inte finns i tillfälliga mappar kan visas och godkännas i [Åtgärdscenter](auto-investigation-action-center.md)på **fliken Väntande.**<br/><br/>Åtgärder som har utförts på filer eller körbara filer i tillfälliga mappar kan visas och godkännas i [Åtgärdscenter](auto-investigation-action-center.md)på **fliken Historik.**   |
|**Inget automatiserat svar** <br/>(kallas även *ingen automation)* | Ingen automatisering innebär att automatisk undersökning körs på organisationens enheter. Därför vidtas inga åtgärder eller väntande åtgärder på grund av automatiserad undersökning. Men andra skyddsfunktioner som [](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)skydd mot potentiellt oönskade program kan påverkas, beroende på hur antivirus- och nästa generations skyddsfunktioner är konfigurerade.<br/><br/>***Vi rekommenderar *inte* att du använder någon** automation, eftersom det minskar säkerheten för din organisations enheter. [Överväg att ställa in din automatiseringsnivå till fullständig automation (eller åtminstone semi-automation)](/microsoft-365/security/defender-endpoint/machine-groups)*. |

## <a name="important-points-about-automation-levels"></a>Viktiga punkter om automatiseringsnivåer

- Fullständig automation har visat sig vara tillförlitlig, effektiv och säker, och rekommenderas för alla kunder. Med fullständig automation frigör du dina kritiska säkerhetsresurser så att de kan fokusera mer på dina strategiska initiativ.

- Nya klientorganisationar (som omfattar klientorganisationen som skapades den 16 augusti 2020 eller senare) med Microsoft Defender för Slutpunkt är inställda på fullständig automation som standard.

- Om ditt säkerhetsteam har definierat enhetsgrupper med en automatiseringsnivå ändras inte de inställningarna i de nya standardinställningarna som lanseras. 

- Du kan behålla standardinställningarna för automatisering eller ändra dem efter organisationens behov. Om du vill ändra dina [inställningar anger du automatiseringsnivån.](/microsoft-365/security/defender-endpoint/configure-automated-investigations-remediation#set-up-device-groups)

## <a name="next-steps"></a>Nästa steg

- [Konfigurera funktioner för automatisk undersökning och åtgärder i Microsoft Defender för Endpoint](configure-automated-investigations-remediation.md)

- [Besök Åtgärdscenter](/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
