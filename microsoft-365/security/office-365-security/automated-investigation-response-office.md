---
title: Så här fungerar automatisk undersökning och svar i Microsoft Defender för Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
keywords: automatiserat incidentsvar, undersökning, åtgärd, skydd mot hot
ms.date: 01/29/2021
description: Se hur automatisk undersökning och svar fungerar i Microsoft Defender för Office 365
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a5a1384208141a42459c009952f89d18498cc21e
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287931"
---
# <a name="how-automated-investigation-and-response-works-in-microsoft-defender-for-office-365"></a>Så här fungerar automatisk undersökning och svar i Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

När säkerhetsvarningar utlöses är det upp till teamet för säkerhetsåtgärder att titta på dessa aviseringar och vidta åtgärder för att skydda organisationen. Ibland kan säkerhetsåtgärder bli överhopad av mängden aviseringar som utlöses. Funktioner för automatisk undersökning och svar (AIR) i Microsoft Defender för Office 365 kan vara till hjälp.

AIR gör att ditt säkerhetsteam kan arbeta effektivare. AIR-funktioner omfattar automatiserade undersökningsprocesser som svar på välkända hot som finns idag. Lämpliga åtgärder väntar på godkännande, vilket gör det möjligt för teamet för säkerhetsåtgärder att svara på identifierade hot.

I den här artikeln beskrivs hur AIR går igenom flera exempel. När du är redo att börja använda AIR kan du gå till [Undersök och reagera på hot automatiskt.](office-365-air.md)

- [Exempel 1: Ett användarrapporterat phish-meddelande startar en spelbok för undersökning](#example-a-user-reported-phish-message-launches-an-investigation-playbook)
- [Exempel 2: En säkerhetsadministratör utlöser en undersökning från Threat Explorer](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)
- [Exempel 3: Ett säkerhetsoperationsteam integrerar AIR med sin SIEM med API för hanteringsaktivitet i Office 365](#example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api)

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>Exempel: Ett användarrapporterat uppgiftsmeddelande startar en spelbok för undersökning

Anta att en användare i organisationen får ett e-postmeddelande om att de tror att det är ett försök till nätfiske. Användaren som är tränad att [](enable-the-report-message-add-in.md) rapportera sådana meddelanden använder [](enable-the-report-phish-add-in.md) tillägget Rapportmeddelande eller tillägget Rapport nätfiske för att skicka det till Microsoft för analys. Inskickingen skickas också till ditt system och  visas i Utforskaren i vyn Inskickade filer (tidigare kallad vyn **Användarrapporter).** Dessutom utlöser det användarrapporterade meddelandet nu en systembaserad informationsvarning, som automatiskt startar spelboken för undersökningen.

Under rotundersökningsfasen kommer olika aspekter av e-postmeddelandet att utvärderas. Dessa aspekter omfattar:

- En vilja att avgöra vilken typ av hot det kan vara;
- Vem har skickat det;
- Vart e-postmeddelandet skickades från (genom att skicka infrastruktur).
- Om andra förekomster av e-postmeddelandet har levererats eller blockerats
- En bedömning från våra analytiker;
- Om e-postmeddelandet är kopplat till kända kampanjer
- med mera.

När rotundersökningen är klar innehåller spelboken en lista med rekommenderade åtgärder att vidta för den ursprungliga e-postadressen och enheter som är kopplade till den.

Sedan utförs flera hotundersöknings- och körningssteg:

- Liknande e-postmeddelanden identifieras via e-postkluster.
- Signalen delas med andra plattformar, till exempel [Microsoft Defender för Slutpunkt.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- Det finns ett avgörande beslut om huruvida användare har klickat genom skadliga länkar i misstänkta e-postmeddelanden.
- En kontroll utförs i Exchange Online Protection[(EOP)](exchange-online-protection-overview.md)och ( Microsoft Defender för[Office 365)](office-365-atp.md)för att se om det finns andra liknande meddelanden som rapporterats av användare.
- En kontroll utförs för att se om en användare har komprometterats. Den här kontrollen utnyttjar signaler i Office 365, [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)och Azure Active [Directory,](https://docs.microsoft.com/azure/active-directory)vilket korrelerar alla relaterade användaraktivitetsaktiviteter.

Under licensfasen tilldelas risker och hot flera olika stegen för att ta del av din säkerhet.

Åtgärd är den sista fasen i spelboken. Under den här fasen vidtas åtgärder baserat på undersöknings- och licensfaserna.

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>Exempel: En säkerhetsadministratör utlöser en undersökning från Threat Explorer

Förutom automatiserade undersökningar som utlöses av en varning kan organisationens säkerhetsteam utlösa en automatiserad undersökning från en vy i [Hotutforskaren.](threat-explorer.md)  Den här undersökningen skapar också en varning, så att Microsoft Defender-incidenter och externa SIEM-verktyg kan se att undersökningen har utlösts.

Anta till exempel att du använder vyn Skadlig **programvara** i Utforskaren. Med hjälp av flikarna under diagrammet väljer du fliken **E-post.** Om du markerar ett eller flera objekt i listan aktiveras knappen **+** åtgärder.

![Utforskaren med markerade meddelanden](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

Med hjälp **av menyn** Åtgärder kan du välja undersökning **av utlösare.**

![Menyn Åtgärder för markerade meddelanden](../../media/explorer-malwareview-selectedemails-actions.jpg)

I likhet med spelböcker som utlöses av en varning inkluderar automatiska undersökningar som utlöses från en vy i Utforskaren en rotundersökning, åtgärder för att identifiera och korrelera hot och rekommenderade åtgärder för att minimera dessa hot.

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a>Exempel: Ett säkerhetsoperationsteam integrerar AIR med sin SIEM med API för Hanteringsaktivitet i Office 365

AIR-funktionerna i Microsoft Defender för Office 365 innehåller & [innehåller](air-view-investigation-results.md) information om säkerhetsåtgärder som grupper kan använda för att övervaka och hantera hot. Men du kan också integrera AIR-funktioner med andra lösningar. Några exempel är ett säkerhetsinformations- och händelsehanteringssystem (SIEM), ett ärendehanteringssystem eller en anpassad rapporteringslösning. Dessa typer av integreringar kan göras med hjälp av [API:t för hanteringsaktivitet i Office 365.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)

Nyligen konfigurerade till exempel en organisation ett sätt för sitt säkerhetsteam att visa användarrapporterade phish-aviseringar som redan bearbetats av AIR. Lösningen integrerar relevanta varningar med organisationens SIEM-server och deras case-management system. Lösningen minskar kraftigt antalet falska positiva försök så att deras säkerhetsteam kan fokusera sin tid och sitt arbete på verkliga hot. Mer information om den här anpassade lösningen finns i Tech Community-bloggen: Effektivisera soc-bloggen med Microsoft Defender för [Office 365 och O365 Management API.](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)

## <a name="next-steps"></a>Nästa steg

- [Komma igång med AIR](office-365-air.md)
- [Visa väntande eller slutförda åtgärder](air-review-approve-pending-completed-actions.md)
