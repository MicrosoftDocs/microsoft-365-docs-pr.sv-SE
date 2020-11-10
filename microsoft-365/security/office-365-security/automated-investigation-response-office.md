---
title: Så här fungerar automatisk undersökning och svar i Microsoft Defender för Office 365
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
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
keywords: automatiskt svar på incident, undersökning, reparation, Hot skydd
ms.date: 11/05/2020
description: Se hur automatiserade funktioner för undersökning och svar fungerar i Microsoft Defender för Office 365
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: 039cca2f6f61d7c82f8c3e85f1fd147a68f84b68
ms.sourcegitcommit: c84cceb07e748969723a31b350e37f3ec79255ab
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/09/2020
ms.locfileid: "48948439"
---
# <a name="how-automated-investigation-and-response-works-in-microsoft-defender-for-office-365"></a>Så här fungerar automatisk undersökning och svar i Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

När säkerhets varningar utlöses är det upp till din säkerhets åtgärds grupp för att titta på dessa meddelanden och vidta åtgärder för att skydda din organisation. Ibland kan säkerhets Operations teamen bli försäkrade av volymen av de larm som utlöses. Automatiserade undersökningar och svar (AIR) i Microsoft Defender för Office 365 kan hjälpa dig.

AIR gör det möjligt för din säkerhets plan att fungera mer effektivt och effektivt. FLYGTRAFIK funktioner inkluderar automatiserade undersökningar som svar på välkända hot som existerar idag. Lämpliga reparations åtgärder väntar på godkännande och gör det möjligt för ditt säkerhets arbete att reagera på identifierade hot.

I den här artikeln beskrivs hur luften fungerar med flera exempel. När du är redo att komma igång med AIR läser du [automatiskt och svarar på hot](office-365-air.md).

- [Exempel 1: ett användardefinierat Phish meddelande öppnar en undersökning Playbook](#example-a-user-reported-phish-message-launches-an-investigation-playbook)
- [Exempel 2: en säkerhets administratör utlöser en undersökning från Threat Explorer](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)
- [Exempel 3: en säkerhets åtgärds grupp integrerar AIR med sina SIEM med hjälp av API för hanterings aktivitet i Office 365](#example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api)


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
- Signalen delas med andra plattformar, till exempel [Microsoft Defender för slut punkten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).
- En bestämning görs på om en användare har klickat på några illasinnade länkar i misstänkta e-postmeddelanden.
- En kontroll görs med Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) och ([Microsoft Defender för Office 365](office-365-atp.md)) för att se om det finns andra liknande meddelanden som rapporteras av användarna.
- En kontroll görs för att se om en användare har fått ett problem. Den här kontrollen används för att utnyttja signaler mellan Office 365, [Microsoft Cloud App-säkerhet](https://docs.microsoft.com/cloud-app-security)och [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), som korrelerar relaterade användar aktiviteter.

Under jakt fasen är riskerna och hot tilldelade till olika jakt steg. 

Reparation är den sista fasen i Playbook. Under den här fasen vidtas reparations steg, baserat på undersökningen och jakt faserna. 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>Exempel: en säkerhets administratör utlöser en undersökning från Threat Explorer

Utöver automatiserade utredningar som löses genom en avisering kan organisationens säkerhets åtgärds team utlösa en automatiserad undersökning från en vy i [Threat Explorer](threat-explorer.md).  Genom den här undersökningen skapas också en avisering, så att Microsoft Defender-tillbud och externa SIEM-verktyg kan se att den här undersökningen har utlösts. 

Antag till exempel att du använder vyn **mot skadlig program vara** i Utforskaren. Använd flikarna nedanför diagrammet och välj fliken **e-post** . Om du markerar ett eller flera objekt i listan aktive ras knappen **+-åtgärder** . 

![Utforskaren med valda meddelanden](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

Med menyn **åtgärder** kan du välja **Utlös ande undersökning**.

![Menyn åtgärder för valda meddelanden](../../media/explorer-malwareview-selectedemails-actions.jpg)

På liknande sätt som playbooks utlöst av en avisering, inkluderar automatiska utredningar som utlöses från en vy i Utforskaren en rot undersökning, steg för att identifiera och korrelera hot och rekommenderade åtgärder för att minska dessa hot.

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a>Exempel: en säkerhets åtgärds grupp integrerar AIR med sina SIEM med hjälp av API för hanterings aktivitet i Office 365

AIR-funktioner i Microsoft Defender för Office 365 innehåller [rapporter & information](air-view-investigation-results.md) som kan användas för att övervaka och adressera hot. Men du kan också integrera AIR-funktioner med andra lösningar. Exemplen innehåller ett system för säkerhets information och Event Management (SIEM), ett ärende hanterings system eller en anpassad rapporterings lösning. Dessa integrerings typer kan du göra med hjälp av [API för hanterings aktivitet i Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). 

Till exempel har en organisation ställt in ett sätt för sin säkerhets åtgärds grupp för att Visa rapporterade Phish-aviseringar som redan bearbetats av AIR. Sin lösning integrerar relevanta aviseringar med organisationens SIEM-Server och ärende hanterings system. Lösningen minskar mängden falsk identifiering så att deras säkerhets åtgärd kan fokusera sin tid och ansträngning för riktiga hot. Om du vill veta mer om den här anpassade lösningen kan du läsa [teknisk community-blogg: förbättra SOC i Microsoft Defender för Office 365 och O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).

## <a name="next-steps"></a>Nästa steg

- [Komma igång med luft](office-365-air.md)

- [Besök Microsoft 365-översikten för att se vad som är planerat och att släppas snart](https://www.microsoft.com/microsoft-365/roadmap?filters=)

- [Lär dig mer om automatiserade undersökningar och svars funktioner i Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir?view=o365-worldwide&preserve-view=true)
