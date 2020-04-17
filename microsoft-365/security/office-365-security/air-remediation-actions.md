---
title: Åtgärder för reparation i office 365-automatiska undersökningar och svar
keywords: AIR, autoIR, ATP, automatiserad, utredning, svar, sanering, hot, avancerad, hot, skydd
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
description: Lär dig mer om reparationsåtgärder i automatiska undersöknings- och svarsfunktioner i Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: d0f08c3e89882e21263c18246612949ea68ac1ad
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2020
ms.locfileid: "43528935"
---
# <a name="remediation-actions-in-office-365"></a>Åtgärdsåtgärder i Office 365

## <a name="remediation-actions"></a>Reparationsåtgärder

[Automatiska undersöknings- och svarsfunktioner](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) i [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) Plan 2 innehåller vissa åtgärder för reparation. När en automatisk undersökning körs eller har slutförts ser du vanligtvis en eller flera reparationsåtgärder som kräver godkännande av säkerhetsoperationsteamet för att fortsätta. Sådana saneringsåtgärder kan omfatta följande:

- E-postmeddelanden eller kluster för mjuk borttagning
- Blockera URL (tid för klick)
- Inaktivera vidarebefordran av extern e-post
- Inaktivera delegering

> [!NOTE]
> I Office 365 ATP åtgärdas inte automatiska undersökningar automatiskt. Reparationsåtgärder vidtas endast efter godkännande av organisationens säkerhetsteam.

## <a name="threats-and-remediation-actions"></a>Hot och saneringsåtgärder

I följande tabell sammanfattas hot och lämpliga åtgärder för reparation i Office 365 ATP. I vissa fall leder en automatiserad undersökning inte till någon särskild saneringsåtgärd. Din säkerhetsoperationsgrupp kan undersöka och vidta lämpliga åtgärder enligt beskrivningen i tabellen nedan.

||||
|---|---|---|
|**Kategori**|**Hot/risk**|**Åtgärder för reparation**|
|E-post|Malware| E-post/kluster för mjuk borttagning <br/><br/>Om mer än en handfull e-postmeddelanden i ett kluster innehåller skadlig kod anses klustret vara skadligt.|
|E-post|Skadlig URL<br/>(En skadlig URL upptäcktes av [Office 365 ATP Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/how-atp-safe-links-works).)|E-post/kluster för mjuk borttagning <br/><br/>E-post som innehåller en skadlig WEBBADRESS anses vara skadlig.|
|E-post|Phish| E-post/kluster för mjuk borttagning <br/><br/>Om mer än en handfull e-postmeddelanden i ett kluster innehåller nätfiskeförsök anses klustret vara phish.|
|E-post|Zapped phish (zappade phish) <br/>(E-postmeddelanden levererades och [zappade](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge).)|E-post/kluster för mjuk borttagning <br/><br/>Rapporter finns tillgängliga för att visa zapped meddelanden. [Se om ZAP har flyttat ett meddelande och vanliga frågor](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge#how-to-see-if-zap-moved-your-message).|
|E-post|Missade phish e-post [som rapporterats](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) av en användare| [Automatiserad undersökning som utlöses av användarens rapport](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|E-post|Volym avvikelse <br/>(De senaste e-postkvantiteterna överskrider de föregående 7-10 dagarna för matchande villkor.)|Automatisk undersökning resulterar inte i en specifik väntande åtgärd. <br/><br/>Volym anomali är inte ett tydligt hot, men är bara en indikation på större e-volymer under de senaste dagarna jämfört med de senaste 7-10 dagarna. Även om detta kan indikera potentiella problem, krävs bekräftelse i form av antingen skadliga domar eller en manuell granskning av e-postmeddelanden /kluster. Se [Hitta och ta bort misstänkt e-post som levererades](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered#find-and-delete-suspicious-email-that-was-delivered).|
|E-post|Inga hot hittades <br/>(Systemet hittade inga hot baserat på filer, webbadresser eller analys av e-kluster domar.)|Automatisk undersökning resulterar inte i en specifik väntande åtgärd. <br/><br/>Hot som hittats och [zapped](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge) efter en undersökning är klar återspeglas inte i en undersökning numeriska resultat, men sådana hot kan ses i [Threat Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer).|
|Användare|En användare klickade på en skadlig URL <br/>(En användare navigerade till en sida som senare visade sig vara skadlig, eller en användare förbi en [varningssida](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links-warning-pages) för säkra länkar för att komma till en skadlig sida.)|Automatisk undersökning resulterar inte i en specifik väntande åtgärd. <br/><br/>Använd Threat Explorer för att [visa data om webbadresser och klicka på domar](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer#view-data-about-phishing-urls-and-click-verdict). <br/><br/>Om din organisation använder [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/)kan du undersöka [användaren](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) för att avgöra om deras konto har komprometterats.|
|Användare|En användare skickar skadlig kod/phish|Automatisk undersökning resulterar inte i en specifik väntande åtgärd. <br/><br/>Användaren kan rapportera skadlig kod /phish, eller någon kan [förfalska användaren](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spoofing-protection) som en del av en attack. Använd [Threat Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) för att visa och hantera e-post som innehåller skadlig [kod](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer-views#email--malware) eller [phish](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer-views#email--phish).|
|Användare|Vidarebefordran av e-post <br/>(Reglerna för vidarebefordran av postlådor är konfigurerade, som kan användas för dataexfiltration.)|Ta bort vidarebefordringsregel <br/><br/>Använd [statistik för e-postflöde](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-insights-v2), inklusive [rapporten Meddelanden som vidarebefordras automatiskt,](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report)om du vill visa mer specifik information om vidarebefordrad e-post.|
|Användare|Regler för delegering av e-post <br/>(En användares konto har delegering konfigurerat.)|Ta bort delegeringsregel <br/><br/> Om din organisation använder [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/)kan du undersöka [användaren](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) som får delegeringsbehörigheten.|
|Användare|Data exfiltration<br/>(En användare bröt mot [DLP-principer för](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)e-post eller fildelning .)|Automatisk undersökning resulterar inte i en specifik väntande åtgärd. <br/><br/>[Visa DLP-rapporter och vidta åtgärder](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports).|
|Användare|Avvikande e-postsändning <br/>(En användare har nyligen skickat mer e-post än under de föregående 7-10 dagarna.)|Automatisk undersökning resulterar inte i en specifik väntande åtgärd. <br/><br/>Att skicka mycket e-post är inte skadligt av sig självt. Användaren kan bara ha skickat e-post till en stor grupp mottagare för en händelse. Du kan undersöka genom att använda [statistik för e-postflödet](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-insights-v2), inklusive [rapporten för mappningsrapporten för e-postflödet](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-mail-flow-map-report) för att ta reda på vad som händer och vidta åtgärder.|
|

## <a name="next-steps"></a>Nästa steg

- [Visa information och resultat av en automatiserad undersökning i Office 365](air-view-investigation-results.md)

- [Visa väntande eller slutförda reparationsåtgärder efter en automatisk undersökning i Office 365](air-review-approve-pending-completed-actions.md)


## <a name="related-articles"></a>Relaterade artiklar

- [Automatiserad undersökning i Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Läs mer om Microsofts hotskydd](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
