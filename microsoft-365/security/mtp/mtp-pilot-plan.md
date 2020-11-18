---
title: Planera piloten Microsoft 365 Defender Project
description: Planera ditt pilot Microsoft 365 Defender-projekt med intressenter för att hantera förväntningar och se till att resultatet lyckades.
keywords: Microsoft Threat Protection pilot, planera pilotprogram varan Microsoft Threat Protection Project, utvärdera Microsoft Threat Protection i Production, Microsoft Threat Protection Pilot-projekt, cyberterrorism-säkerhet, Avancerat, beständiga hot, företags säkerhet, enheter, enhet, identitet, användare, data, program, tillbud, automatiserad undersökning och reparation, avancerad jakt
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: 4420342f964564305bb113c45ee0e3107f8a822e
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130987"
---
# <a name="planning-your-pilot-microsoft-365-defender-project"></a>Planera piloten Microsoft 365 Defender Project 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

|![Planering](../../media/phase-diagrams/1-planning.png)<br/>Planering|[![Förbereda](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)<br/>[Förberedelse](prepare-mtpeval.md) | [![Simulera attack](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)<br/>[Simulera attack](mtp-pilot-simulate.md) | [![Stäng och sammanfatta](../../media/phase-diagrams/4-summary.png)](mtp-pilot-close.md)<br/>[Stäng och sammanfatta](mtp-pilot-close.md)|
|--|--|--|--|
|*Nu är det här!*| | | |

Du befinner dig i planerings fasen.

För att se till att ditt Pilot projekt är framgångs rika är det viktigt att planera omsorgsfullt med och få godkännanden från dina intressenter i början. Planerings element inkluderar identifierings omfattning, användnings villkor och krav på framgång.

Den här guiden hjälper dig att planera pilot projektet. 

>[!IMPORTANT]
>För optimalt resultat följer du pilot instruktionerna så nära som möjligt.


## <a name="scope"></a>Sitt

Omfattningen av piloten bestämmer hur breda testet kommer att vara, baserat på din miljö och acceptabla test metoder. Här följer några exempel på omfattningar:
- Utvecklings-eller test miljö som inkluderar slut punkter, servrar, domänkontrollanter.
- Produktions miljö med Microsoft 365, Azure, Active Directory-tjänster, slut punkter och servrar

>[!NOTE]
>Om du inte har de fullständiga licenserna ännu kan du få prov licenser för [utvärdering av Microsoft 365 Defender](https://aka.ms/mtp-trial-lab) – planera, förbereda, konfigurera och köra ett pilot projekt. Dina intressenter spelar en stor roll för att under lätta processen från början till slut.

Vilka typer av operativ system som ska utvärderas ska också definieras baserat på organisationens makeup. Det kan vara följande: [Mac-slutpunkter](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements), [Linux-servrar](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements), [Windows 10-slutpunkter](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions), [Windows Server 2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions).

## <a name="use-cases"></a>Användnings fall

Användnings fall utgör en översikt över hur verktyget testas är avsett att förbrukas av dess avsedda användare. Dessa kan formuleras som användar berättelser från en viss person, till exempel en SOC analytiker. Till exempel:
- Som SOC analytiker måste jag visa, korrelera, bedöma och hantera aviseringar och händelser mellan enheter, användare och post lådor i mitt nätverk. [Ärende hantering]
- Som SOC analytiker måste jag ha verktyget och processen för att automatiskt undersöka och reagera på illvilliga händelser i nätverket. [Auto-IR]
- Som SOC analytiker måste jag söka data från min miljö för att hitta kända och potentiella hot samt misstänkta aktiviteter. [Avancerad jakt]

Kom ihåg att dessa användnings fall ska skapas i parametrarna för det definierade omfånget. Om test omfattningen inte inkluderar en utvärdering av verktyg som Microsoft Cloud App Security, ska du använda ärenden som är beroende av detta som data källa.

## <a name="requirements"></a>Krav

I listan över användnings fall kan du börja skapa krav. Kraven inkluderar funktioner som ett verktyg måste uppfylla för användnings fall. Dessa krav kan delas upp i kategorier som konfiguration och underhåll, support för integreringar och särskilda krav som jakt möjligheter och möjlighet att bygga anpassade larm.

## <a name="test-plan"></a>Test plan

Beroende på kraven kan de olika test metoderna vara lämpliga. Om behovet är att utvärdera hur automatisk reparation fungerar måste test planen innehålla instruktioner för att generera de beteenden som skulle utlösa en automatisk reparations åtgärd i Microsoft 365 Defender. Om behovet är att upptäcka ett visst beteende eller en attack kan testet innehålla fler steg. Det är bara att planera ett abonnemang mot dina behov.

## <a name="success-criteria"></a>Villkor för framgång

Villkoren för framgång är i sista hand för att mäta det du testar. Oavsett om du testar Microsoft 365 Defender (eller någon annan teknik) mot andra verktyg eller själv, måste det finnas vissa kriterier för att avgöra vilket värde verktyget erbjuder. Utifrån omfattning, krav och test plan bestämmer villkoren för framgång hur du ska räkna med testet. Detta bör vara mindre av ett pass eller fel och mer av viktat poäng baserat på dina behov. För att lyckas kan ett verktyg behöva gå över 80% i vissa kritiska områden som du anger.

## <a name="scorecard"></a>Styrkort

Ett sätt att samla ihop alla element i planen är att skapa ett styrkort. Visa ett exempel på ett styrkort nedan:

| Användnings fall | Krav | Konfigurations krav | Test plan | Förväntat resultat | Test status | Poäng | Kommentarer |
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|Ärende hantering|-Microsoft 365 Defender  </br></br>-Microsoft Defender för identitet </br></br>-Microsoft Defender för slut punkt </br></br>-Säkerhet för Microsoft Cloud App (valfritt)|Se [förutsättningarna](https://aka.ms/mtp-trial-lab) för förberedelse, konfigurering och konfiguration för information |[Simulera attack](mtp-pilot-simulate.md) <br></br>[Undersök problemet](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#investigate-an-incident) |Prövare kan förstå omfattningen och konsekvenserna av incidenten och hantera händelsen||||
|AutoIR|-Microsoft 365 Defender </br></br>-Microsoft Defender för identitet </br></br>-Microsoft Defender för slut punkt |Se [förutsättningarna](https://aka.ms/mtp-trial-lab) för förberedelse, konfigurering och konfiguration för information <br>Aktivera AutoIR  |[Simulera attack](mtp-pilot-simulate.md) <br></br>[Automatisk undersökning](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#automated-investigation-and-remediation) |Aviseringar och händelser åtgärdas automatiskt av Microsoft 365 Defender||||
|Avancerad jakt|-Microsoft 365 Defender </br></br>-Microsoft Defender för slut punkt </br></br>-Microsoft Defender för Office 365 |Se [förutsättningarna](https://aka.ms/mtp-trial-lab) för förberedelse, konfigurering och konfiguration för information|[Avancerat jakt scenario](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#advanced-hunting-scenario) |Prövare kan hitta data genom avancerad jakt, pivotering till förverkningarade enheter och genom att skapa anpassade identifieringar||||



## <a name="next-step"></a>Nästa steg
|![Förberedelse fas](../../media/mtp/prep.png) <br>[Förberedelse fas](prepare-mtpeval.md) | Förbereda din Microsoft 365 Defender pilot miljö
|:-------|:-----|
