---
title: Automatisk undersökning och svar (luft) Översikt
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
ms.date: 08/21/2020
description: Få en översikt över automatiserade undersökningar och svars funktioner i Office 365 Avancerat skydds plan 2.
ms.custom: air - seo-marvel-mar2020
ms.openlocfilehash: 27a2330d5f1ff339aabf6a0fccb94a15dec30852
ms.sourcegitcommit: 37da941919036a714da42eaa039682ccbe0da670
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2020
ms.locfileid: "46860727"
---
# <a name="an-overview-of-automated-investigation-and-response-air-in-microsoft-365"></a>En översikt över automatiserad undersökning och svar (AIR) i Microsoft 365

När säkerhets varningar utlöses är det upp till din säkerhets åtgärds grupp för att titta på dessa meddelanden och vidta åtgärder för att skydda din organisation. Ibland kan säkerhets Operations teamen bli försäkrade av volymen av de larm som utlöses. Automatiserade undersökningar och svar (AIR) i Office 365 Avancerat skydd (Office 365 ATP) kan hjälpa dig. 

AIR gör det möjligt för din säkerhets plan att fungera mer effektivt och effektivt. FLYGTRAFIK funktioner inkluderar automatiserade undersökningar som svar på välkända hot som existerar idag. Lämpliga reparations åtgärder väntar på godkännande och gör det möjligt för ditt säkerhets arbete att reagera på identifierade hot. 

Den här artikeln innehåller en översikt över luft. När du är redo att komma igång med AIR läser du [automatiskt och svarar på hot](office-365-air.md).

## <a name="at-a-high-level"></a>På en hög nivå

När notifieringar utlöses blir säkerhets playbooks träder i kraft. Beroende på situationen kan en [automatiserad undersöknings process](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) påbörjas. Under och efter en automatisk undersökning rekommenderas [reparations åtgärder](air-remediation-actions.md) . Inga åtgärder vidtas automatiskt i Office 365 Avancerat skydd. Din säkerhets Operations team granskar och [godkänner eller avvisar varje åtgärd](air-review-approve-pending-completed-actions.md)för att åtgärda. När alla åtgärder som följer med undersökningen har godkänts eller avvisats slutförs undersökningen. Alla de här aktiviteterna spåras och visas i avsnittet om säkerhets & efterlevnad (se [detaljerad information om en undersökning](air-view-investigation-results.md#view-details-of-an-investigation)).

I följande avsnitt finns mer information om aviseringar, säkerhets playbooks och flyg exempel.

## <a name="alerts"></a>Varningar

[Aviseringar](../../compliance/alert-policies.md#viewing-alerts) representerar utlösare för säkerhets åtgärds team arbets flöden för samtals svar. Prioritera de rätta uppsättningarna med aviseringar och kontrol lera att inga hot är avadresserade är utmanande. När undersökningar av notifieringar utförs manuellt måste säkerhets åtgärds teamerna nå och korrelera enheter (till exempel innehåll, enheter och användare) till risk för hot. Sådana uppgifter och arbets flöden kan vara mycket tidsödande och involvera flera verktyg och system. Med luft, undersökning och svar för säkerhets händelser automatiseras genom att viktiga säkerhets-och Threat Management Alerts playbooks automatiskt. 

För närvarande är det automatiskt undersökta notifieringar som genereras från följande typer av larm principer:  

- En potentiellt skadlig URL-adress klickning upptäcktes
- E-post som rapporter ATS av användaren som Phish`*`
- E-postmeddelanden som innehåller skadlig kod tas bort efter leverans`*`
- E-postmeddelanden som innehåller Phish-URL: er tas bort efter leverans`*`
- Misstänkta e-postskickade mönster`#`
- Användare begränsad från att skicka e-post`#`

> [!NOTE]
> Aviseringarna som är markerade med en asterisk ( `*` ) har tilldelats en allvarlighets grad för *information* i respektive larm policy i säkerhets & efterlevnad, med e-postaviseringar inaktiverade. E-postaviseringar kan aktive ras genom [konfigurering av aviserings principer](../../compliance/alert-policies.md#alert-policy-settings). Aviseringar som marker ATS med en hash ( `#` ) finns i allmänhet tillgängliga för förhands granskning playbooks.

Om du vill visa aviseringar väljer du **varningar**i avsnittet säkerhet & efterlevnad  >  **View alerts**. Välj en avisering om du vill visa dess uppgifter och därifrån kan du använda länken **Visa undersökning** för att gå till motsvarande [undersökning](air-view-investigation-results.md#investigation-graph).  

> [!NOTE]
> Informations varningar döljs som standard i vyn avisering. För att se dem kan du ändra varnings filtreringen så att den innehåller informations aviseringar.

Om din organisation hanterar dina säkerhets varningar via ett system för aviserings hantering, tjänst hanterings system eller SIEM (Security information and Event Management) kan du skicka aviseringar till det systemet via ett e-postmeddelande eller via [API för hanterings aktivitet i Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). Undersöknings aviseringar via e-post eller API innehåller länkar för åtkomst till aviseringarna i säkerhets & Compliance Center, vilket gör att den tilldelade säkerhets administratören snabbt kan navigera till undersökningen.

![Aviseringar som länkar till undersökningar](../../media/air-alerts-page-details.png) 

## <a name="security-playbooks"></a>Säkerhets playbooks

Säkerhets playbooks är backend-principer som är till för att fungera i automatiserings syfte i Office-Avancerat skydd och skydd mot Microsoft Threat. De säkerhets playbooks som tillhandahålls i AIR är baserade på vanliga scenarier för verklig säkerhet och utvecklad utifrån feedback från team för säkerhets åtgärder. En säkerhets Playbook startas automatiskt när specifika aviseringar utlöses inom din organisation. När notifieringen utlöses körs den associerade Playbook av den automatiska undersöknings-och svars systemet. Undersöknings stegen genom analys av aviseringen baserat på den specifika aviseringens Playbook, som visar alla associerade metadata (inklusive e-postmeddelanden, användare, ämnen, avsändare osv.). På grund av undersökningen playbooks resultat rekommenderar AIR en uppsättning åtgärder som organisationens säkerhets team kan vidta för att kontrol lera och minska hotet. 

Playbooks som du får med flyg är avsedda att klara de hot som organisationer drabbar idag med e-post. De baseras på inmatningar från säkerhets åtgärder och arbets grupps svar, inklusive personer som kan försvara Microsoft och våra kunders till gångar.

### <a name="security-playbooks-are-rolling-out-in-phases"></a>Säkerhets playbooks tas upp i faser

Som en del av luft bevaras säkerhets playbooks i faser. Fas 1 är nu allmänt tillgänglig och innehåller flera playbooks som ger rekommendationer för åtgärder som säkerhets administratörer kan granska och godkänna:

- Rapporterat Phish meddelande
- URL-Klicka på Verdict ändra
- Skadlig kod identifierad efter leverans (malware, ZAP)
- Phish upptäckte att det är en Phish

Fas 1 inkluderar stöd för administratörer som utlöser e-postutredning (med hjälp av [Threat Explorer](threat-explorer.md)).

Fas 2 fortskrider nu med följande playbooks i **offentlig för hands version**, med rekommendationer för åtgärder och aiding säkerhets administratörer för att undersöka problem:

- Användare som rapporter ATS som kompromissad (offentlig för hands version)

Fler playbooks frigörs när de har slutförts. Besök [Microsoft 365-översikten](https://www.microsoft.com/microsoft-365/roadmap) för att se vad mer som är planerat och kommer snart.

### <a name="playbooks-include-investigation-and-recommendations"></a>Playbooks innehåller undersökningar och rekommendationer

I luft inkluderar varje säkerhets Playbook: 

- en rot undersökning av ett e-postmeddelandes enheter (till exempel filer, URL: er, mottagare, IP-adresser och mer).
- ytterligare jakt efter liknande e-postmeddelanden som tas emot av organisationen 
- steg som vidtogs för att identifiera och korrelera andra potentiella hot. 
- rekommenderade hot åtgärds åtgärder.

Varje steg i hög nivå innehåller ett antal under steg som utförs för att ge ett djupgående, detaljerat och komplett svar på hot.

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>Exempel: ett användardefinierat Phish meddelande öppnar en undersökning Playbook

Anta att en användare i din organisation får ett e-postmeddelande om att de tycker är ett nät fiske försök. Användaren, utbildad att rapportera sådana meddelanden, använder [tillägget rapport meddelande](enable-the-report-message-add-in.md) för att skicka det till Microsoft för analys. Överföringen skickas också till ditt system och visas i Utforskaren i vyn för **skickade** samtal (kallades tidigare vyn **användare-rapporterad** ). Dessutom utlöser det användardefinierade meddelandet en systembaserad informations avisering, som automatiskt startar undersökningen Playbook.

Under den här fasen av rot undersökningen bedöms olika delar av e-postmeddelandet. De här aspekterna inkluderar:

- En analys av vilken typ av hotet det är.
- Vem skickade det;
- Varifrån e-postmeddelandet skickades (med infrastruktur);
- Om andra instanser av e-postmeddelandet levererades eller blockerades;
- En utvärdering från våra analytiker;
- Om e-postmeddelandet är kopplat till alla kända kampanjer;
- och mycket annat.

När du har slutfört rot undersökningen tillhandahåller Playbook en lista över rekommenderade åtgärder att vidta på den ursprungliga e-postmeddelandet och de enheter som är kopplade till den.
  
Nu utförs flera hot undersökningar och jakt steg:

- Likartade e-postmeddelanden identifieras via e-postklusters ökning.
- Signalen delas med andra plattformar, till exempel [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).
- En bestämning görs på om en användare har klickat på några illasinnade länkar i misstänkta e-postmeddelanden.
- En kontroll görs med Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) och Office 365 Avancerat skydd ([ATP](office-365-atp.md)) för att se om det finns andra liknande meddelanden som rapporteras av användarna.
- En kontroll görs för att se om en användare har fått ett problem. Den här kontrollen används för att utnyttja signaler mellan Office 365, [Microsoft Cloud App-säkerhet](https://docs.microsoft.com/cloud-app-security)och [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), som korrelerar relaterade användar aktiviteter.

Under jakt fasen är riskerna och hot tilldelade till olika jakt steg. 

Reparation är den sista fasen i Playbook. Under den här fasen vidtas reparations steg, baserat på undersökningen och jakt faserna. 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>Exempel: en säkerhets administratör utlöser en undersökning från Threat Explorer

Utöver automatiserade utredningar som löses genom en avisering kan organisationens säkerhets åtgärds team utlösa en automatiserad undersökning från en vy i [Threat Explorer](threat-explorer.md).

Antag till exempel att du använder vyn **mot skadlig kod** i Threat Explorer. Använd flikarna nedanför diagrammet och välj fliken **e-post** . Om du markerar ett eller flera objekt i listan aktive ras knappen **+-åtgärder** . 

![Utforskaren med valda meddelanden](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

Med menyn **åtgärder** kan du välja **Utlös ande undersökning**.

![Menyn åtgärder för valda meddelanden](../../media/explorer-malwareview-selectedemails-actions.jpg)

På liknande sätt som playbooks utlöst av en avisering, inkluderar automatiska utredningar som utlöses från en vy i Utforskaren en rot undersökning, steg för att identifiera och korrelera hot och rekommenderade åtgärder för att minska dessa hot.

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a>Exempel: en säkerhets åtgärds grupp integrerar AIR med sina SIEM med hjälp av API för hanterings aktivitet i Office 365

LUFT funktioner i Office 365 ATP inkluderar [rapporter & Detaljer](air-view-investigation-results.md) som säkerhets åtgärds gruppen kan använda för att övervaka och adressera hot. Men du kan också integrera AIR-funktioner med andra lösningar. Exemplen innehåller ett system för säkerhets information och Event Management (SIEM), ett ärende hanterings system eller en anpassad rapporterings lösning. Dessa integrerings typer kan göras med hjälp av [API för hanterings aktivitet i Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). 

Till exempel har en organisation ställt in ett sätt för sin säkerhets åtgärds grupp för att Visa rapporterade Phish-aviseringar som redan bearbetats av AIR. Sin lösning integrerar relevanta aviseringar med organisationens SIEM-Server och ärende hanterings system. Lösningen minskar mängden falsk identifiering så att deras säkerhets åtgärd kan fokusera sin tid och ansträngning för riktiga hot. Om du vill veta mer om den här anpassade lösningen kan du läsa [teknisk community-blogg: förbättra effektiviteten hos din SOC med Office 365 ATP och O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).

## <a name="next-step"></a>Nästa steg

- [Komma igång med luft](office-365-air.md)

## <a name="see-also"></a>Se även

- [Microsoft 365-översikt](https://www.microsoft.com/microsoft-365/roadmap?filters=)

- [Automatiserad undersökning och svars funktioner i Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir?view=o365-worldwide)