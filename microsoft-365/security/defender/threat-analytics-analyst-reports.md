---
title: Förstå analytikernas rapportavsnitt i hotanalyser
ms.reviewer: ''
description: Lär dig mer om analytikernas rapportavsnitt i varje rapport om hotanalyser. Förstå hur den förser dig med information om hot, minskningar, identifieringar, avancerade sökfrågor med mera.
keywords: Analytiker, hotanalyser, identifieringar, avancerade sökfrågor, minskningar,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f916137be71dffeaed7e3718286032a17c9f8e04
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498484"
---
# <a name="understand-the-analyst-report-in-threat-analytics"></a>Förstå analytikerrapporten i hotanalyser

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**
- Microsoft 365 Defender

> Vill du uppleva Microsoft 365 Defender? Du kan [utvärdera det i en laboratoriemiljö](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) eller [köra ett pilotprojekt i produktionen](m365d-pilot.md?ocid=cx-evalpilot).
>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Varje [rapport om hotanalyser](threat-analytics.md) innehåller dynamiska avsnitt och ett omfattande skriftligt avsnitt som kallas _analytikerrapporten._ Öppna rapporten om de spårade hoten för att komma åt det här avsnittet och välj **fliken Analytikerrapport.**

![Bild av analytikerrapportens avsnitt i en rapport om hotanalys](../../media/threat-analytics/ta_analystreport_mtp.png)

_Analytikerrapportavsnitt i en rapport om hotanalys_

## <a name="scan-the-analyst-report"></a>Skanna analytikernas rapport 
Varje avsnitt i analytikerrapporten har utformats för att ge användbar information. Rapporterna varierar, men de flesta rapporter innehåller de avsnitt som beskrivs i följande tabell.

| Rapportavsnitt | Beskrivning |
|--|--|
| Sammanfattning | Översikt över hoten, bland annat när man först såg dem, dess motivation, viktiga händelser, viktiga mål samt distinkta verktyg och tekniker. Du kan använda den här informationen för att ytterligare bedöma hur du prioriterar hot inom ramen för branschen, geografisk plats och nätverk. |
| Analys | Teknisk information om hoten, bland annat information om en attack och hur attacker kan använda en ny teknik eller attackyta | 
| MITRE ATT&CK-tekniker som observerats | Hur observerade tekniker mappas till [MITRE ATT&CK-attackramverket](https://attack.mitre.org/) | 
| [Minskningar](#apply-additional-mitigations) | Rekommendationer som kan stoppa eller minska risken. Det här avsnittet innehåller också åtgärder som inte spåras dynamiskt som en del av rapporten över hotanalyser. |
| [Information om identifiering](#understand-how-each-threat-can-be-detected) | Specifika och allmänna identifieringar som tillhandahålls av Microsoft-säkerhetslösningar som kan hantera aktivitet eller komponenter som är associerade med hot. | 
| [Avancerad jakt](#find-subtle-threat-artifacts-using-advanced-hunting) | [Avancerade sökfrågor för att](advanced-hunting-overview.md) proaktivt identifiera möjliga hotaktiviteter. De flesta frågor tillhandahålls för identifiering av tillägg, särskilt för att hitta potentiellt skadliga komponenter eller beteenden som inte kan utvärderas dynamiskt som skadliga. | 
| Referenser | Microsoft och publikationer från tredje part som analytiker refererade till när de skapade rapporten. Innehållet i hotanalyser baseras på data som validerats av Microsofts forskare. Information från offentligt tillgängliga tredjepartskällor identifieras tydligt som sådan. | 
| Ändra logg | Tidpunkten då rapporten publicerades och när betydande ändringar gjorts i rapporten. |

## <a name="apply-additional-mitigations"></a>Tillämpa ytterligare åtgärder
Hotanalyser spårar dynamiskt [status för säkerhetsuppdateringar och säkra konfigurationer.](threat-analytics.md#mitigations-review-list-of-mitigations-and-the-status-of-your-devices) Den här informationen finns som diagram och tabeller på **fliken Minskningar.**

Förutom de här spårade minskningarna tar analysrapporten även upp åtgärder som inte _övervakas_ dynamiskt. Här är några exempel på viktiga åtgärder som inte spåras dynamiskt:

- Blockera e-postmeddelanden _med LNK-bilagor_ eller andra misstänkta filtyper
- Slumpmässiga lösenord för lokala administratörer
- Utbilda slutanvändare om nätfiske och andra vektorer
- Aktivera specifika [minskningsregler för attackytan](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)

Även om du kan använda **fliken** Minskningar för att bedöma din säkerhetsbegränsning mot ett hot, kan du med hjälp av de här rekommendationerna vidta ytterligare åtgärder för att förbättra säkerheten. Läs noggrant alla minskningsvägledning i analytikerrapporten och använd dem när det är möjligt.

## <a name="understand-how-each-threat-can-be-detected"></a>Förstå hur varje hot kan identifieras
Analysrapporten innehåller även funktioner för identifieringar från Microsoft Defender för Endpoint antivirus _identifiering och åtgärd på slutpunkt_ (Identifiering och åtgärd på slutpunkt).

### <a name="antivirus-detections"></a>Antivirusidentifiering
Dessa identifieringar är tillgängliga på enheter [Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) är påslagna. När de här identifieringarna inträffar på enheter som har introducerats till Microsoft Defender för Endpoint utlöser de även aviseringar som tar upp diagrammen i rapporten.

>[!NOTE]
>Analytikerrapporten visar även **allmänna** identifieringar som kan identifiera en mängd olika hot, utöver komponenter eller beteenden som är specifika för de spårade hoten. Dessa allmänna identifieringar återspeglas inte i diagrammen.

### <a name="endpoint-detection-and-response-edr-alerts"></a>Aviseringar om identifiering av slutpunkt och svar (Identifiering och åtgärd på slutpunkt)
Identifiering och åtgärd på slutpunkt upphöjs för [enheter som är onboarded till Microsoft Defender för Endpoint](/windows/security/threat-protection/microsoft-defender-atp/onboard-configure). Dessa varningar förlitar sig vanligtvis på säkerhetssignaler som samlas in av Microsoft Defender för Endpoint-sensoren och andra slutpunktsfunktioner – till exempel antivirus, nätverksskydd, manipuleringsskydd – som fungerar som kraftfulla signalkällor.

Precis som listan med antivirusidentifieringar är vissa Identifiering och åtgärd på slutpunkt är utformade för att generellt flagga misstänkt beteende som kanske inte är kopplat till det spårade hotet. I sådana fall identifierar rapporten tydligt varningen som "allmän" och att den inte påverkar något av diagrammen i rapporten.

### <a name="email-related-detections-and-mitigations"></a>E-postrelaterade identifieringar och åtgärder
E-postrelaterade identifieringar och åtgärder från Microsoft Defender för Office 365 ingår i analytiker utöver de slutpunktsdata som redan är tillgängliga från Microsoft Defender för Endpoint. 

Information om förhindrade e-postförsök ger dig insikter om huruvida din organisation var ett mål för de hot som har hanterats i analytikerrapporten även om attacken har blockerats effektivt innan den levereras eller levereras till skräppostmappen.

## <a name="find-subtle-threat-artifacts-using-advanced-hunting"></a>Hitta diskreta hotartefakter med avancerad sökning
Vid identifieringar kan du identifiera och stoppa de spårade hoten automatiskt, men många attackaktiviteter lämnar diskreta spårningar som kräver ytterligare kontroll. Vissa attackaktiviteter har beteenden som också kan vara normala, så att de dynamiskt kan leda till driftstörningar eller till och med falska positiva identifieringar.

[Avancerad sökning](advanced-hunting-overview.md) ger ett frågegränssnitt baserat på Kusto-frågespråk som förenklar hitta diskreta indikatorer på hotaktivitet. Du kan också ta fram sammanhangsberoende information och kontrollera om indikatorer är kopplade till ett hot.

Avancerade sökfrågor i analytikernas rapporter har kontrollerats av Microsoft-analytiker och är klara att köra i den avancerade [frågeredigeraren för sökning.](https://security.microsoft.com/advanced-hunting) Du kan också använda frågorna för att skapa anpassade [identifieringsregler som](custom-detection-rules.md) utlöser aviseringar för framtida matchningar.


>[!NOTE]
> Hotanalyser finns också tillgängliga i [Microsoft Defender för Endpoint.](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) Men dataintegreringen mellan Microsoft Defender för Office och Microsoft Defender för slutpunkten som Microsoft 365 Defender-hotanalyser har.


## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över hotanalys](threat-analytics.md)
- [Hitta hot proaktivt med avancerad sökning](advanced-hunting-overview.md) 
- [Anpassade regler för identifiering](custom-detection-rules.md)