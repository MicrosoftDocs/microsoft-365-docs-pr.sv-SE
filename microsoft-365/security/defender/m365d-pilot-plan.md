---
title: Planera ditt Microsoft 365 Defender-pilotprojekt
description: Planera ditt Microsoft 365 Defender-pilotprojekt med intressenter för att hantera förväntningar och säkerställa ett lyckat resultat.
keywords: Microsoft 365 Defender-pilot, planera pilottestning av Microsoft 365 Defender-projekt, utvärdera Microsoft 365 Defender i produktion, Microsoft 365 Defender-pilotprojekt, cybersäkerhet, avancerade beständiga hot, företagssäkerhet, enheter, enheter, identitet, användare, data, program, incidenter, automatisk undersökning och åtgärd, avancerad sökning
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 98f0c91a51cc2b73cc26e6fb53143a417a7a147e
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932553"
---
# <a name="planning-your-pilot-microsoft-365-defender-project"></a>Planera ditt Microsoft 365 Defender-pilotprojekt 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

|![Planering](../../media/phase-diagrams/1-planning.png)<br/>Planering|[![Förbereda](../../media/phase-diagrams/2-prepare.png)](prepare-m365d-eval.md)<br/>[Förberedelse](prepare-m365d-eval.md) | [![Simulera attack](../../media/phase-diagrams/3-simluate.png)](m365d-pilot-simulate.md)<br/>[Simulera attack](m365d-pilot-simulate.md) | [![Stäng och sammanfatta](../../media/phase-diagrams/4-summary.png)](m365d-pilot-close.md)<br/>[Stäng och sammanfatta](m365d-pilot-close.md)|
|--|--|--|--|
|*Du är här!*| | | |

Du befinner dig för närvarande i planeringsfasen.

För att pilotprojektet ska vara lyckat måste du planera i detalj och få godkännanden från intressenter från början. Planeringselementen omfattar att identifiera omfattning, användningsfall, krav och kriterier för framgång.

I den här guiden får du hjälp med att planera ditt pilotprojekt. 

>[!IMPORTANT]
>För bästa resultat bör du följa pilotinstruktionerna så nära som möjligt.


## <a name="scope"></a>Omfattning

Pilotens omfattning avgör hur omfattande testet ska vara, baserat på din miljö och godtagbara testmetoder. Här är några exempel på omfattningar att tänka på:
- Utvecklings- eller testmiljö som omfattar slutpunkter, servrar och domänkontrollanter.
- Produktionsmiljö med Microsoft 365, Azure, Active Directory-tjänster, slutpunkter och servrar

>[!NOTE]
>Om du inte har fullständiga licenser ännu kan du få utvärderingslicenser för att utvärdera [Microsoft 365 Defender](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) – planera, förbereda, konfigurera, konfigurera och köra ditt pilotprojekt. Intressenterna kommer att ha en stor roll för att underlätta processen från början till slut.

Vilka typer av operativsystem som ska utvärderas bör också definieras utifrån organisationsstruktur. Detta kan inkludera följande: [Mac-slutpunkter,](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements) [Linux-servrar,](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements) [Windows 10-slutpunkter](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions), [Windows Server 2016](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions).

## <a name="use-cases"></a>Användningsfall

Användningsfall representerar instruktioner om hur verktyget som testas är avsett att användas av de avsedda användarna. De kan utformas som användarberättelser ur perspektiv hos en viss person, till exempel som SOC-analytiker. Till exempel:
- Som SOC-analytiker behöver jag visa, korrelera, bedöma och hantera aviseringar och händelser för olika enheter, användare och postlådor i nätverket. [Incidenthantering]
- Som SOC-analytiker måste jag ha verktyget och processen för att automatiskt undersöka och svara på skadliga händelser i nätverket. [Automatisk IR]
- Som SOC-analytiker måste jag söka efter data från min miljö för att hitta kända och potentiella hot och misstänkta aktiviteter. [Advanced Hunting]

Kom ihåg att dessa användningsfall bör skapas inom parametrarna för den definierade omfattningen. Om till exempel omfattningen av testningen inte omfattar en utvärdering av verktyg som Microsoft Cloud App Security ska du inte skapa ärenden som förlitar sig på detta som datakälla.

## <a name="requirements"></a>Krav

Från listan över användningsfall kan du börja skapa krav. Kraven omfattar funktioner som ett verktyg måste ha för att uppfylla användningsfallen. De här kraven kan delas in i kategorier som konfiguration och underhåll, stöd för integrationer och funktionsspecifika krav som möjligheten att hitta och möjligheten att skapa anpassade aviseringar.

## <a name="test-plan"></a>Testplan

Olika testmetoder kan vara lämpliga beroende på kraven. Om kravet till exempel är att utvärdera hur effektiv Automatiserad åtgärd är, måste testplanen innehålla steg för att generera beteendet som utlöser en automatiserad åtgärd inom Microsoft 365 Defender. Om kravet är att identifiera ett visst beteende eller en viss attack kan testet innebära fler steg. Poängen är att ha en plan för att testa mot dina krav korrekt.

## <a name="success-criteria"></a>Kriterier för framgång

Framgångskriterierna är i slutänden den stapel som mäter mot det du testar. Oavsett om du testar Microsoft 365 Defender (eller någon annan teknik för den delen) mot andra verktyg eller för sig själv, måste det finnas några kvantifierbara villkor för att fastställa vilket värde verktyget tillhandahåller. Utifrån omfattningen, kraven och testplanen avgör framgångskriterierna hur testet ska betygstesta. Det bör vara mindre godkänt eller misslyckat och mer av en viktad poäng baserat på dina behov. Ett verktyg kan till exempel behöva poäng över 80 % i vissa kritiska områden som du identifierar.

## <a name="scorecard"></a>Styrkort

Ett sätt att samla alla delar av planen kan vara att skapa ett styrkort. Se ett exempel på styrkort nedan:

| Användningsfall | Krav | Konfigurationskrav | Testplan | Förväntat resultat | Teststatus | Poäng | Kommentarer |
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|Incidenthantering|- Microsoft 365 Defender  </br></br>- Microsoft Defender för identitet </br></br>- Microsoft Defender för Slutpunkt </br></br>- Microsoft Cloud App Security (valfritt)|Mer information [finns i](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) förutsättningarna för att förbereda, konfigurera och konfigurera |[Simulera attack](m365d-pilot-simulate.md) <br></br>[Undersök incidenten](./m365d-pilot-simulate.md#investigate-an-incident) |En verksamhet kan förstå händelsens omfattning och påverkan och hur den hanteras||||
|AutoIR|- Microsoft 365 Defender </br></br>- Microsoft Defender för identitet </br></br>- Microsoft Defender för Slutpunkt |Mer information [finns i](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) förutsättningarna för att förbereda, konfigurera och konfigurera <br>Aktivera AutoIR  |[Simulera attack](m365d-pilot-simulate.md) <br></br>[Automatiserad undersökning](m365d-pilot-simulate.md#automated-investigation-and-remediation) |Aviseringar och incidenter åtgärdas automatiskt av Microsoft 365 Defender||||
|Avancerad jakt|- Microsoft 365 Defender </br></br>- Microsoft Defender för Slutpunkt </br></br>-Microsoft Defender för Office 365 |Mer information [finns i](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) förutsättningarna för att förbereda, konfigurera och konfigurera|[Avancerat sökningsscenario](./m365d-pilot-simulate.md#advanced-hunting-scenario) |Funktioner kan hitta data via avancerad sökning, pivotering till berörda enheter och genom att skapa anpassade identifieringar||||



## <a name="next-step"></a>Nästa steg
|![Förberedelsefas](../../media/mtp/prep.png) <br>[Förberedelsefas](prepare-m365d-eval.md) | Förbereda pilotmiljön i Microsoft 365 Defender
|:-------|:-----|
