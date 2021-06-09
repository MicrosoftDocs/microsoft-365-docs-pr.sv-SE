---
title: Förbered säkerheten för den första händelsen
description: Konfigurera din Microsoft 365 säkerhet för den första incidenten i Microsoft 365 Defender.
keywords: incidenter, aviseringar, undersöker, korrelation, attack, datorer, enheter, användare, identiteter, identiteter, postlåda, e-post, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: da9147955c5da9ea727854420b3d4d160583ef73
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840952"
---
# <a name="prepare-your-security-posture-for-your-first-incident"></a>Förbered säkerheten för den första händelsen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**
- Microsoft 365 Defender

Förberedelse för incidenthantering omfattar att konfigurera tillräckligt skydd av organisationens nätverk från olika typer av säkerhetsincidenter. För att minska risken för säkerhetsincidenter rekommenderar National Institute of Standards and Technology (NIST) flera säkerhetsmetoder, bland annat riskbedömning, hårdnande värdsäkerhet, konfigurera nätverk säkert och förhindra skadlig programvara. 

Microsoft 365 Defender kan åtgärda flera aspekter av incidentskydd: 

- Implementera ett [Zero Trust Framework](/security/zero-trust/)
- Fastställa din säkerhet genom att tilldela ett poäng med [Microsoft Secure Score](microsoft-secure-score.md)
- Förhindra hot genom sårbarhetsutvärderingar i [hot- och sårbarhetshantering](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)
- Förstå de senaste säkerhetshoten så att du kan förbereda dem

## <a name="step-1-implement-zero-trust"></a>Steg 1. Implementera nollförtroende

[Zero Trust](/security/zero-trust/) är en integrerad säkerhetsstrategi som tar hänsyn till hur komplex en modern miljö är, inklusive den mobila arbetsstyrkan och användare, enheter, program och data, var de än befinner sig. Genom att ha ett enda fönster med fönster för att hantera alla identifieringar på ett konsekvent sätt [](/security/zero-trust/#guiding-principles-of-zero-trust) kan Microsoft 365 Defender göra det enklare för din säkerhetsgrupp att implementera de vägledande principerna för Zero Trust. 

Komponenter i Microsoft 365 Defender kan visa överträdelser av regler som har implementerats för att upprätta villkorsstyrda åtkomstprinciper för Zero Trust genom att integrera data från Microsoft Defender för slutpunkt (MDE) eller andra mobila säkerhetsleverantörer som en informationskälla för principer för enhetsefterlevnad och implementering av enhetsbaserade villkorsbaserade principer. 

Enhetsrisker påverkar direkt vilka resurser som är tillgängliga för användaren av enheten. Denial of access to resources based on certain criteria is the main theme of Zero Trust and Microsoft 365 Defender provides information needed to determine the trust level criteria. Till exempel kan Microsoft 365 Defender tillhandahålla programvaruversionsnivån för en enhet via sidan Threat and Vulnerability Management medan villkorsstyrd åtkomst begränsar enheter som har inaktuella eller sårbara versioner.

Automation är en viktig del i implementeringen och underhållet av en nollförtroendemiljö samtidigt som antalet aviseringar som potentiellt skulle leda till incidentåtgärdshändelser (IR-händelser) minskar. Komponenter i Microsoft 365 Defender kan automatiseras, till exempel åtgärder [(kallas](m365d-autoir.md) undersökningar för en incident i säkerhetscentret i Microsoft 365), aviseringsåtgärder och till och med skapandet av supportärenden i [ServiceNow.](https://microsoft.service-now.com/sp/)

## <a name="step-2-determine-your-organizations-security-posture"></a>Steg 2. Fastställa säkerheten i din organisation

Därefter kan organisationer använda [Microsoft Secure Score](microsoft-secure-score.md) i Microsoft 365 Defender för att avgöra vilken säkerhetsrisk du har och fundera på rekommendationer om hur du kan förbättra den. Ju högre poäng desto fler säkerhetsrekommendationer och förbättringsåtgärder har genomförts av organisationen. Rekommendationer om Secure Score kan användas i olika produkter och organisationer kan höja sina resultat ännu högre. 

:::image type="content" source="../../media/first-incident-prepare/first-incident-secure-score.png" alt-text="Exempel på Microsoft Secure Score i Microsofts säkerhetscenter":::
 
## <a name="step-3-assess-your-organizations-vulnerability-exposure"></a>Steg 3. Utvärdera exponering av risker för din organisation

Att förhindra incidenter kan effektivisera arbetet med säkerhetsåtgärder för att fokusera på viktiga säkerhetsincidenter som är viktiga i det här processen. Säkerhetsproblem av programvara är ofta en startpunkt som kan förhindras för attacker som kan leda till datastöld, dataförlust eller störningar i affärsåtgärder. Om inga attacker är i gång måste säkerhetsåtgärder strävar efter att uppnå och upprätthålla en godtagbar nivå av [exponering](../defender-endpoint/tvm-exposure-score.md) av sårbarheter i organisationen.

Om du vill kontrollera förloppet [](../defender-endpoint/next-gen-threat-and-vuln-mgt.md) för programkorrigeringar går du till sidan Hantering av hot och sårbarhet i Defender för slutpunkt, som du kan komma åt från Microsoft 365 Defender på **fliken Fler** resurser.

:::image type="content" source="../../media/first-incident-prepare/first-incident-vulnerability.png" alt-text="Exempel på sidan Hot och sårbarhet i Microsofts säkerhetscenter"::: 
 
## <a name="4-understand-emerging-threats"></a>4. Förstå nya hot

Använd [hotanalyser](threat-analytics.md) i Microsoft 365 säkerhetscenter för att hålla dig uppdaterad om de aktuella hot landskapen. En expert som Microsoft-säkerhetsexpert skapar rapporter som beskriver de senaste cyberhoten i detalj så att du förstår hur de kan påverka Microsoft 365 prenumeration, enheter och användare. Dessa rapporter kan innehålla:

- Aktiva hot-aktör och deras kampanjer
- Populära och nya attacktekniker
- Kritiska säkerhetsproblem
- Vanliga attackytor
- Vanligast förekommande skadlig programvara

Hotanalyser tittar också på din konfiguration och aviseringar för att fastställa hur riskabel du är och om det finns aktiva aviseringar som gäller för en rapport.

Du kan implementera rekommendationerna om ett framväxande hot för att stärka din säkerhetsrisk och minimera ditt attackområde.

Se till att ha tid i schemat för att [regelbundet kontrollera avsnittet om](threat-analytics.md) hotanalys Microsoft 365 säkerhetscenter.

## <a name="next-step"></a>Nästa steg

[![Steg 1: Lär dig att undersöka och analysera incidenter](../../media/first-incident-overview/first-incident-path-step1.png)](first-incident-analyze.md)

Lär dig att [undersöka och analysera incidenter.](first-incident-analyze.md)

## <a name="see-also"></a>Se även

- [Översikt över incidenter](incidents-overview.md)
- [Undersöka incidenter](investigate-incidents.md)
- [Hantera incidenter](manage-incidents.md)
