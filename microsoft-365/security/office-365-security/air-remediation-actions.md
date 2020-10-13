---
title: Reparations åtgärder följer den automatiska undersökningen i Microsoft Defender för Office 365
keywords: LUFT, autoIR, ATP, automatiserad, undersökning, svar, reparation, hot, Avancerat, hot, skydd
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
description: Läs mer om åtgärder som utförs efter en automatiserad undersökning i Microsoft Defender för Office 365.
ms.date: 09/29/2020
ms.custom:
- air
ms.openlocfilehash: ffd0429d3dc85371e7b6bb1c2d1246d9820d0e2e
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446713"
---
# <a name="remediation-actions-following-automated-investigation-in-microsoft-defender-for-office-365"></a>Reparations åtgärder följer den automatiska undersökningen i Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="remediation-actions"></a>Reparationsåtgärder

[Automatiserade undersökningar och svars funktioner](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (Air) i [Microsoft Defender för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) innehåller vissa reparations åtgärder. När en automatiserad undersökning körs eller har genomförts visas normalt en eller flera reparations åtgärder som kräver godkännande av din säkerhets åtgärd för att du ska kunna fortsätta. Sådana reparations åtgärder kan inkludera följande:

- Mjuka ta bort e-postmeddelanden och kluster
- Blockera URL (tid för klick)
- Inaktivera extern e-postvidarekoppling
- Inaktivera delegering

> [!NOTE]
> I Microsoft Defender för Office 365, ger automatisk undersökning inte till åtgärds åtgärder som vidtas automatiskt. Reparations åtgärder vidtas endast vid godkännande från organisationens säkerhets åtgärds team.

## <a name="threats-and-remediation-actions"></a>Åtgärder för hot och reparation

I följande tabell sammanfattas hot och lämpliga reparations åtgärder i Microsoft Defender för Office 365. I vissa fall kan en automatisk undersökning inte resultera i en särskild reparations åtgärd. Din säkerhets åtgärd kan granska och vidta lämpliga åtgärder enligt beskrivningen i tabellen nedan.

****

|Kategori|Hot/risk|Reparations åtgärder|
|---|---|---|
|E-post|Program|Mjukt ta bort e-post/kluster <br/><br/>Om fler än en fåtal av e-postmeddelanden i ett kluster innehåller skadlig program vara anses klustret vara skadligt.|
|E-post|Skadlig URL<br/>(En skadlig URL upptäcktes av [säkra länkar i Office 365 ATP](atp-safe-links.md).|Mjukt ta bort e-post/kluster <br/><br/>E-postmeddelanden som innehåller en illvillig URL anses vara skadlig.|
|E-post|Nätfiske|Mjukt ta bort e-post/kluster <br/><br/>Om fler än en fåtal av e-postmeddelanden i ett kluster innehåller nät fiske försök anses klustret vara Phish.|
|E-post|Zapped phish <br/>(E-postmeddelanden skickades till och [zapped](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge).)|Mjukt ta bort e-post/kluster <br/><br/>Rapporter finns tillgängliga för att Visa zapped-meddelanden. [Se om ZAP har flyttat ett meddelande och vanliga frågor](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge#how-to-see-if-zap-moved-your-message).|
|E-post|Missade Phish-e-post som [rapporter ATS](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) av en användare|[Automatisk granskning utlöst av användarens rapport](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|E-post|Volym avvikelse <br/>(Senaste e-postkvantiteten överskrider de föregående 7-10 dagarna för matchnings villkor.)|Den automatiska undersökningen resulterar inte i en särskild väntande åtgärd. <br/><br/>Volym avvikelser är inget tydligt hot, men det är bara att ange större e-postvolymer under de senaste dagarna jämfört med de senaste 7-10 dagarna. Även om det här kan tyda på potentiella problem måste du bekräfta att du har en verdicts eller manuell recension av e-postmeddelanden/kluster. Se [hitta och ta bort misstänkta e-postmeddelanden som har levererats](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered#find-and-delete-suspicious-email-that-was-delivered).|
|E-post|Inga hot hittades <br/>(Det gick inte att hitta några hot baserat på filer, URL: er eller analys av e-postkluster verdicts.)|Den automatiska undersökningen resulterar inte i en särskild väntande åtgärd. <br/><br/>Hot Funna och [zapped](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge) efter att en undersökning är färdig visas inte i en undersöknings numeriska resultat, men sådana hot visas i [Threat Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer).|
|Användare|En användare klickade på en illvillig URL <br/>(En användare navigerade till en sida som du har hittat för att bli skadlig eller en användare har blockerat en varning om ett [säkert länkar](atp-safe-links.md#warning-pages-from-safe-links) till en skadlig sida.)|Den automatiska undersökningen resulterar inte i en särskild väntande åtgärd. <br/><br/>Använd Threat Explorer för att [Visa data om URL: er och klicka på verdicts](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer#view-data-about-phishing-urls-and-click-verdict). <br/><br/>Om din organisation använder [Microsoft Defender för slut punkten](https://docs.microsoft.com/windows/security/threat-protection/)kan du [pröva användaren](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) att kontrol lera om deras konto är angripet.|
|Användare|En användare skickar skadlig program vara/Phish|Den automatiska undersökningen resulterar inte i en särskild väntande åtgärd. <br/><br/>Användaren kan rapportera skadlig program vara/Phish eller någon kan behöva [falska användaren](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spoofing-protection) som en del av en attack. Använd [Threat Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) för att visa och hantera e-post som innehåller [skadlig kod](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer-views#email--malware) eller [Phish](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer-views#email--phish).|
|Användare|Vidarebefordran av e-post <br/>(Regler för vidarebefordran av post lådor är konfigurerade, vilka kan användas för data exfiltration.)|Ta bort vidarebefordrings regel <br/><br/>Använd [e-postflöde](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-insights-v2), inklusive rapporten för [automatiskt vidarebefordrade meddelanden](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report), för att visa mer detaljerad information om vidarebefordrad e-post.|
|Användare|Regler för e-postombud <br/>(En användares konto har Delegerings inställning.)|Ta bort Delegerings regel <br/><br/> Om din organisation använder [Microsoft Defender för slut punkter](https://docs.microsoft.com/windows/security/threat-protection/)bör du överväga att [undersöka användaren](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) som får behörigheten delegera.|
|Användare|Data exfiltration<br/>(En användare bryter mot e-post eller [DLP-principer](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)för fildelning.)|Den automatiska undersökningen resulterar inte i en särskild väntande åtgärd. <br/><br/>[Visa DLP-rapporter och vidta åtgärder](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports).|
|Användare|Avvikelser via e-post <br/>(En användare skickade nyligen mer e-post än under de föregående 7-10 dagarna.)|Den automatiska undersökningen resulterar inte i en särskild väntande åtgärd. <br/><br/>Att skicka mycket e-post är inte särskilt skadligt. användaren kanske bara har skickat e-post till en stor grupp mottagare för en händelse. Om du vill undersöka kan du använda [e-postflöde](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-insights-v2), inklusive [rapportering av e-postflöde](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-mail-flow-map-report) för att avgöra vad som händer och vidta åtgärder.|
|

## <a name="next-steps"></a>Nästa steg

- [Visa information och resultat från en automatisk undersökning i Microsoft Defender för Office 365](air-view-investigation-results.md)

- [Visa pågående och klara reparations åtgärder efter en automatisk undersökning i Microsoft Defender för Office 365](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>Relaterade artiklar

- [Lär dig mer om automatisk undersökning i Microsoft Defender för slut punkten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Läs mer om ytterligare funktioner i Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
