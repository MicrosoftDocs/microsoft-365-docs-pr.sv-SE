---
title: Åtgärdsåtgärder efter automatisk undersökning i Microsoft Defender för Office 365
keywords: AIR, autoIR, ATP, automatiserad, undersökning, svar, åtgärd, hot, avancerat, hot, skydd
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
description: Läs mer om åtgärder efter automatisk undersökning i Microsoft Defender för Office 365.
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4966ce860c3d27f003a4fd86e158ce80de8252e2
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142639"
---
# <a name="remediation-actions-in-microsoft-defender-for-office-365"></a>Åtgärdsåtgärder i Microsoft Defender för Office 365

## <a name="remediation-actions"></a>Reparationsåtgärder

Skyddsfunktioner i [Microsoft Defender för Office 365](office-365-atp.md) omfattar vissa åtgärder. Sådana åtgärder kan omfatta:

- Mjuk borttagning av e-postmeddelanden och kluster
- Blockera URL (tid för klickning)
- Inaktivera vidarebefordran av extern e-post
- Inaktivera delegering

I Microsoft Defender för Office 365 vidtas inte åtgärdsåtgärder automatiskt. I stället vidtas åtgärder endast efter godkännande av organisationens team för säkerhetsåtgärder.

## <a name="threats-and-remediation-actions"></a>Hot och åtgärder

Microsoft Defender för Office 365 innehåller åtgärder för att hantera olika hot. Automatiserade undersökningar resulterar ofta i en eller flera åtgärder för att granska och godkänna. I vissa fall leder en automatiserad undersökning inte till en specifik åtgärd. Om du vill undersöka ytterligare och vidta lämpliga åtgärder använder du vägsvägledning i följande tabell.

|Kategori|Hot/risk|Åtgärdsåtgärd(er)|
|:---|:---|:---|
|E-post|Skadlig programvara|Mjuk borttagning av e-post/kluster <p> Om mer än ett litet e-postmeddelande i ett kluster innehåller skadlig programvara anses klustret vara skadligt.|
|E-post|Skadlig URL<br/>(En skadlig URL upptäcktes av [Säkra länkar](atp-safe-links.md).)|Mjuk borttagning av e-post/kluster <p>E-post som innehåller en skadlig URL anses vara skadlig.|
|E-post|Nätfiske|Mjuk borttagning av e-post/kluster <p> Om mer än en liten del av e-postmeddelandena i ett kluster innehåller nätfiskeförsök är hela klustret ett försök till nätfiske.|
|E-post|Zapped phish <br>(E-postmeddelanden levererades och [zapped sedan.)](zero-hour-auto-purge.md)|Mjuk borttagning av e-post/kluster <p>Det finns rapporter för att visa zappade meddelanden. [Se om ZAP har flyttat ett meddelande och vanliga frågor och svar.](zero-hour-auto-purge.md#how-to-see-if-zap-moved-your-message)|
|E-post|Missade e-postmeddelanden [har rapporterats](enable-the-report-message-add-in.md) av en användare|[Automatiserad undersökning som utlöses av användarens rapport](automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|E-post|Volymnormnormy <br> (Antalet senaste e-postmeddelanden överskrider de föregående 7–10 dagarna för matchande villkor.)|En automatiserad undersökning resulterar inte i en väntande åtgärd. <p>Volymnorma är inte ett tydligt hot, utan är bara en indikation på större e-postvolymer under de senaste dagarna jämfört med de senaste 7–10 dagarna. <p>Även om ett stort antal e-postmeddelanden kan indikera potentiella problem, krävs bekräftelse på antingen skadliga omdömen eller en manuell granskning av e-postmeddelanden/kluster. Se [Hitta misstänkta e-postmeddelanden som har levererats.](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered)|
|E-post|Inga hot hittades <br> (Inga hot hittades i systemet baserat på filer, URL:er eller analys av e-postkluster.)|En automatiserad undersökning resulterar inte i en väntande åtgärd. <p>Hot som hittas och [zapped](zero-hour-auto-purge.md) efter att en undersökning har slutförts återspeglas inte i de numeriska resultaten för en undersökning, men sådana hot kan visas i [Threat Explorer.](threat-explorer.md)|
|Användare|En användare har klickat på en skadlig URL <br> (En användare som navigerade till en sida som senare visades [](atp-safe-links.md#warning-pages-from-safe-links) vara skadlig, eller så gick en användare förbi en varningssida med säkra länkar för att komma till en skadlig sida.)|En automatiserad undersökning resulterar inte i en viss väntande åtgärd. <p>Använd HotUtforskaren [för att visa data om URL:er och klicka på beslut.](threat-explorer.md#view-phishing-url-and-click-verdict-data) <p>Om din organisation använder [Microsoft Defender för Slutpunkt kan du](https://docs.microsoft.com/windows/security/threat-protection/)undersöka användaren för [att](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) avgöra om deras konto har komprometterats.|
|Användare|En användare skickar skadlig kod/phish|En automatiserad undersökning resulterar inte i en väntande åtgärd. <p> Användaren kan rapportera skadlig kod/phish eller så kan någon [förfalskning av användaren som en](anti-spoofing-protection.md) del av en attack. Använd [Hot Explorer för](threat-explorer.md) att visa och hantera e-postmeddelanden som innehåller [skadlig](threat-explorer-views.md#email--malware) programvara eller [nätt innehåll.](threat-explorer-views.md#email--phish)|
|Användare|Vidarebefordran av e-post <br> (Regler för vidarebefordran av postlådor är konfigurerade, som kan användas för data exfiltration.)|Ta bort vidare vidarebefordran <p> Använd [information om e-postflöde,](mail-flow-insights-v2.md)inklusive rapporten [om automatiskt](mfi-auto-forwarded-messages-report.md)vidarebefordrade meddelanden, om du vill visa mer specifik information om vidarebefordrad e-post.|
|Användare|Regler för e-postdelegering <br> (En användares konto har delegering.)|Ta bort delegeringsregel <p> Om din organisation använder [Microsoft Defender för Slutpunkt kan](https://docs.microsoft.com/windows/security/threat-protection/)du undersöka [användaren](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) som får delegeringsbehörigheten.|
|Användare|Exfiltrering av data <br> (En användare har brutit mot E-post- eller [fildelnings-DLP-principer.)](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)|En automatiserad undersökning resulterar inte i en viss väntande åtgärd. <p> [Visa DLP-rapporter och vidta åtgärder.](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports)|
|Användare|Avvikande e-postavsändande <br> (En användare har nyligen skickat mer e-post än under de föregående 7–10 dagarna.)|En automatiserad undersökning resulterar inte i en viss väntande åtgärd. <p> Att skicka en stor mängd e-post är inte skadligt för sig själv. Användaren kanske bara har skickat e-post till en stor grupp mottagare för ett evenemang. Om du vill undersöka [e-postflödet](mail-flow-insights-v2.md)kan du använda [insikter](mfi-mail-flow-map-report.md) i e-postflödet, inklusive rapporten om e-postflödeskartan, för att avgöra vad som händer och vidta åtgärder.|

## <a name="next-steps"></a>Nästa steg

- [Visa information och resultat från en automatiserad undersökning i Microsoft Defender för Office 365](air-view-investigation-results.md)
- [Visa väntande eller slutförda åtgärder efter en automatiserad undersökning i Microsoft Defender för Office 365](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>Relaterade artiklar

- [Läs mer om automatiserad undersökning i Microsoft Defender för Slutpunkt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [Läs mer om funktionerna i Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
