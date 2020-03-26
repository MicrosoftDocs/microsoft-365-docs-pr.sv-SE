---
title: Automatisk undersökning och svar (AIR) i Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Få en översikt över automatiska undersöknings- och svarsfunktioner i Office 365 Advanced Threat Protection Plan 2.
ms.custom: air
ms.openlocfilehash: f6bbad82f3dce7080aca079a5f750dfc1fea068b
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955583"
---
# <a name="automated-investigation-and-response-air-in-office-365"></a>Automatisk undersökning och svar (AIR) i Office 365

När säkerhetsaviseringar utlöses är det upp till säkerhetsoperationsteamet att titta på dessa aviseringar och vidta åtgärder för att skydda din organisation. Ibland kan säkerhetsoperationsteam känna sig överväldigade av mängden aviseringar som utlöses. Automatiska funktioner för undersökningar och svar (AIR) i Office 365 kan hjälpa dig. AIR gör det möjligt för ditt säkerhetsteam att arbeta mer effektivt och ändamålsenligt. AIR-funktioner inkluderar automatiserade undersökningsprocesser som svar på välkända hot som finns idag. Lämpliga åtgärder väntar på godkännande, så att säkerhetsoperationsgruppen kan svara på upptäckta hot. 

Den här artikeln innehåller en översikt över AIR. När du är redo att komma igång med AIR läser du [Undersök och svara på hot automatiskt i Office 365](office-365-air.md).

## <a name="at-a-high-level"></a>På en hög nivå

När aviseringar utlöses träder säkerhetsspelböcker i kraft. Beroende på situationen kan en [automatiserad undersökningsprocess påbörjas.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) Under och efter en automatiserad undersökning rekommenderas [åtgärder för reparation.](air-remediation-actions.md) Inga åtgärder vidtas automatiskt i Office 365 Advanced Threat Protection. Säkerhetsåtgärdsteamet granskar och [godkänner eller avvisar](air-review-approve-pending-completed-actions.md)sedan varje åtgärd , och när detta är klart slutförs varje undersökning. Alla dessa aktiviteter spåras och kan visas i Office 365 Security & Compliance Center (se [Visa information om en undersökning](air-view-investigation-results.md#view-details-of-an-investigation)).

I följande avsnitt finns mer information om aviseringar, säkerhetsspelböcker och exempel på AIR i aktion.

## <a name="alerts"></a>Varningar

[Aviseringar](../../compliance/alert-policies.md#viewing-alerts) representerar utlösare för säkerhetsoperationsteamarbetsflöden för incidenthantering. Att prioritera rätt uppsättning varningar för utredning, samtidigt som man ser till att inga hot inte åtgärdas är en utmaning. När undersökningar av aviseringar utförs manuellt måste säkerhetsoperationsteam jaga och korrelera entiteter (till exempel innehåll, enheter och användare) som riskerar att hotas. Sådana uppgifter och arbetsflöden kan vara mycket tidskrävande och involvera flera verktyg och system. Med AIR automatiseras säkerhetshändelser för granskning och svar för Office 365 genom att viktiga säkerhets- och hothanteringsvarningar automatiskt utlöser spelböcker för säkerhetssvar. 

För närvarande för AIR undersöks aviseringar som genereras från följande typer av varningsprinciper automatiskt:  

- Ett potentiellt skadligt URL-klick upptäcktes
- E-post som rapporteras av användaren som phish*
- E-postmeddelanden som innehåller skadlig kod som tagits bort efter leverans*
- E-postmeddelanden som innehåller phish webbadresser som tagits bort efter leverans*
- Misstänkta e-postutskicksmönster har upptäckts #
- Användare som är begränsad från att skicka e-post #

> [!NOTE]
> Aviseringarna som markerats med en asterisk (*) tilldelas en *informations allvarlighetsgrad* i respektive varningsprinciper i Security & Compliance Center, med e-postmeddelanden inaktiverade. E-postmeddelanden kan aktiveras via [konfiguration av aviseringsprincip](../../compliance/alert-policies.md#alert-policy-settings). Aviseringar som är markerade med en hash (#) är allmänt tillgängliga aviseringar som är associerade med offentliga förhandsversionsspelböcker.

Om du vill visa aviseringar väljer du **Aviseringar** > **visa aviseringar**i Säkerhets- & Compliance Center . Välj en avisering om du vill visa dess information och därifrån använd **länken Visa undersökning** för att gå till motsvarande [undersökning](air-view-investigation-results.md#investigation-graph).  

> [!NOTE]
> Informationsaviseringar döljs som standard i varningsvyn. Om du vill se dem ändrar du varningsfiltreringen så att informationsaviseringar inkluderas.

Om din organisation hanterar dina säkerhetsaviseringar via ett varningshanteringssystem, tjänsthanteringssystem eller SIEM-system (Security Information and Event Management) kan du skicka Office 365-aviseringar till det systemet via antingen e-postmeddelanden eller via [API:et för office 365 Management Activity.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference) Utredningens varningsmeddelanden via e-post eller API innehåller länkar för att komma åt aviseringarna i Security & Compliance Center, vilket gör att den tilldelade säkerhetsadministratören snabbt kan navigera till undersökningen.

![Varningar som länkar till utredningar](../../media/air-alerts-page-details.png) 

## <a name="security-playbooks"></a>Spelböcker för säkerhet

Säkerhetsuppspelningsböcker är backend-principer som är kärnan i automatiseringen i Office Advanced Threat Protection och Microsoft Threat Protection. Säkerhetsspelböckerna i AIR baseras på vanliga verkliga säkerhetsscenarier och utvecklas baserat på feedback från säkerhetsteam. En säkerhetsuppspelningsbok startas automatiskt när specifika aviseringar utlöses inom organisationen. När aviseringen utlöses körs den associerade spelboken av air-systemet (Automated Investigation and Response). Undersökningen går igenom en analys av aviseringen baserat på den specifika aviseringens spelbok och tittar på alla associerade metadata (inklusive e-postmeddelanden, användare, ämnen, avsändare osv.). Baserat på undersökningsuppspelningsbokens resultat rekommenderar AIR en uppsättning åtgärder som organisationens säkerhetsteam kan vidta för att kontrollera och minska hotet. 

De säkerhetsspelböcker du får med AIR är utformade för att hantera de vanligaste hoten som organisationer möter idag med e-post. De baseras på indata från team för säkerhetsoperationer och incidenthantering, inklusive de som hjälper till att försvara Microsoft och våra kunders tillgångar.

### <a name="security-playbooks-are-rolling-out-in-phases"></a>Säkerhet playbooks rullas ut i faser

Som en del av AIR, säkerhet spelböcker rullas ut i faser. Fas 1 är nu allmänt tillgänglig och innehåller flera spelböcker som ger rekommendationer för åtgärder som säkerhetsadministratörer kan granska och godkänna:
- Användarrapporterat phish-meddelande
- URL klicka dom förändring
- Malware upptäckt efter leverans (Malware ZAP)
- Phish upptäckt efter leverans ZAP (Phish ZAP)

Fas 1 innehåller även stöd för administratörsutlösta e-postundersökningar (med [Threat Explorer).](threat-explorer.md)

Fas 2 går nu vidare med följande spelböcker i **den offentliga förhandsversionen,** ger rekommendationer för åtgärder och hjälper säkerhetsadministratörer att undersöka problem:
- Användare som rapporterats som komprometterade (offentlig förhandsversion)

Ytterligare spelböcker kommer att släppas när de är klara. Besök [Översikten över Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) för att se vad som planeras och kommer snart.

### <a name="playbooks-include-investigation-and-recommendations"></a>Spelböcker inkluderar undersökning och rekommendationer

I AIR innehåller varje säkerhetsspelbok: 
- En rotundersökning av ett e-postmeddelandes enheter (filer, webbadresser, mottagare, IP-adresser osv.).
- ytterligare jakt på liknande e-postmeddelanden som mottagits av organisationen 
- åtgärder som vidtagits för att identifiera och korrelera andra potentiella hot, och 
- rekommenderade åtgärder för att åtgärda hot.

Varje steg på hög nivå innehåller ett antal understeg som utförs för att ge ett djupt, detaljerat och uttömmande svar på hot.

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>Exempel: Ett användarrapporterat phish-meddelande startar en undersökningsspelbok

Anta att en användare i organisationen får ett e-postmeddelande som de tror är ett nätfiskeförsök. Användaren, som är tränad att rapportera sådana meddelanden, använder [tillägget Rapportmeddelande för Outlook eller Outlook Web App för](enable-the-report-message-add-in.md) att skicka det till Microsoft för analys. Inlämningen skickas också till ditt system och visas i Utforskaren i **vyn Inlämningar** (tidigare kallad **användarrapporterad** vy). Dessutom utlöser det användarrapporterade meddelandet nu en systembaserad informationsavisering, som automatiskt startar undersökningsuppspelningsboken.

Under rotutredningsfasen bedöms olika aspekter av e-postmeddelandet. Dessa inkluderar:
- En bestämning om vilken typ av hot det kan vara;
- Vem sände den;
- Var e-postmeddelandet skickades från (skicka infrastruktur);
- Om andra instanser av e-postmeddelandet levererades eller blockerades.
- En bedömning från våra analytiker;
- Om e-postmeddelandet är associerat med kända kampanjer.
- med mera.

När rotundersökningen är klar innehåller spelboken en lista över rekommenderade åtgärder som ska vidtas på det ursprungliga e-postmeddelandet och entiteterna som är associerade med den.
  
Därefter utförs flera hotutredningar och jaktsteg:

- Liknande e-postmeddelanden identifieras via e-postklustersökningar.
- Signalen delas med andra plattformar, till exempel [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).
- En bedömning görs om huruvida några användare har klickat igenom några skadliga länkar i misstänkta e-postmeddelanden.
- En kontroll görs i Office 365 Exchange Online Protection[(EOP)](exchange-online-protection-eop.md)och Office 365 Advanced Threat Protection[(ATP)](office-365-atp.md)för att se om det finns några andra liknande meddelanden som rapporterats av användare.
- En kontroll görs för att se om en användare har komprometterats. Den här kontrollen utnyttjar signaler över Office 365, [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)och Azure Active [Directory](https://docs.microsoft.com/azure/active-directory), korrelerar relaterade avvikelser i användaraktiviteten. 

Under jaktfasen sätts risker och hot på olika jaktsteg. 

Reparation är den sista fasen av spelboken. Under denna fas vidtas saneringsåtgärder på grundval av utrednings- och jaktfaserna. 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>Exempel: En säkerhetsadministratör utlöser en undersökning från Threat Explorer

Förutom automatiska undersökningar som utlöses av en avisering kan organisationens säkerhetsoperationsteam utlösa en automatisk undersökning från en vy i [Threat Explorer](threat-explorer.md).

Anta till exempel att du använder vyn **Skadlig kod** i Threat Explorer. Med hjälp av flikarna under diagrammet väljer du fliken **E-post.** Om du markerar ett eller flera objekt i listan aktiveras knappen **+ Åtgärder.** 

:::image type="content" source="../../media/Explorer-Malware-Email-ActionsInvestigate.png" alt-text="Explorer med markerade meddelanden":::

Med hjälp av menyn **Åtgärder** kan du välja **Utlösarundersökning**.

:::image type="content" source="../../media/explorer-malwareview-selectedemails-actions.jpg" alt-text="Åtgärdsmenyn för markerade meddelanden":::

I likhet med spelböcker som utlöses av en avisering innehåller automatiska undersökningar som utlöses från en vy i Explorer en rotundersökning, steg för att identifiera och korrelera hot och rekommenderade åtgärder för att minska dessa hot.

## <a name="next-steps"></a>Nästa steg

- [Komma igång med AIR i Office 365](office-365-air.md)

- [Besök Översikten över Microsoft 365 för att se vad som kommer snart och rulla ut](https://www.microsoft.com/microsoft-365/roadmap?filters=)

