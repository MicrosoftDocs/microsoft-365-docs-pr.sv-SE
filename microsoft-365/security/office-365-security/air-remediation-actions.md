---
title: Åtgärdsåtgärder i Microsoft Defender för Office 365
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
ms.date: 02/09/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 273682571a1eb6bf2fd9566d8498ccbb618cd2d3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917611"
---
# <a name="remediation-actions-in-microsoft-defender-for-office-365"></a>Åtgärdsåtgärder i Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

## <a name="remediation-actions"></a>Reparationsåtgärder

Skyddsfunktioner i [Microsoft Defender för Office 365](office-365-atp.md) omfattar vissa åtgärder. Sådana åtgärder kan omfatta:

- Mjuk borttagning av e-postmeddelanden och kluster
- Blockera URL (tid för klickning)
- Inaktivera vidarebefordran av extern e-post
- Inaktivera delegering

I Microsoft Defender för Office 365 vidtas inte åtgärdsåtgärder automatiskt. I stället vidtas åtgärder endast om godkännande har godkänts av organisationens team för säkerhetsåtgärder.

## <a name="threats-and-remediation-actions"></a>Hot och åtgärder

Microsoft Defender för Office 365 innehåller åtgärdsåtgärder för att hantera olika hot. Automatiserade undersökningar resulterar ofta i en eller flera åtgärder som måste granskas och godkännas. I vissa fall leder inte en automatiserad undersökning till en specifik åtgärd. Om du vill undersöka och vidta lämpliga åtgärder använder du vägledning i följande tabell.

|Kategori|Hot/risk|Åtgärdsåtgärder|
|:---|:---|:---|
|E-post|Skadlig programvara|Mjuk borttagning av e-post/kluster <p> Om mer än ett litet antal e-postmeddelanden i ett kluster innehåller skadlig programvara anses klustret vara skadligt.|
|E-post|Skadlig URL<br/>(En skadlig URL identifierades av [Säkra länkar](atp-safe-links.md).)|Mjuk borttagning av e-post/kluster <br/>Blockera URL (tid för klickning av verifiering)<p> E-post som innehåller en skadlig URL anses vara skadlig.|
|E-post|Phish|Mjuk borttagning av e-post/kluster <p> Om mer än ett litet antal e-postmeddelanden i ett kluster innehåller nätfiskeförsök betraktas hela klustret som ett försök till nätfiske.|
|E-post|Zapped phish <br>(E-postmeddelanden levererades och [sedan zapped](zero-hour-auto-purge.md).)|Mjuk borttagning av e-post/kluster <p>Rapporter finns tillgängliga för att visa zapped meddelanden. [Se om ZAP har flyttat ett meddelande och vanliga frågor och svar](zero-hour-auto-purge.md#how-to-see-if-zap-moved-your-message).|
|E-post|Missat e-postmeddelande [som rapporterats](enable-the-report-message-add-in.md) av en användare|[Automatiserad undersökning som utlösts av användarens rapport](automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|E-post|Volymnormnormy <br> (Antalet nya e-postmeddelanden överskrider de föregående 7–10 dagarna för matchande villkor.)|Automatisk undersökning leder inte till en viss väntande åtgärd. <p>Volymnormer är inte ett tydligt hot, utan är bara en indikation på större e-postvolymer under de senaste dagarna jämfört med de senaste 7–10 dagarna. <p>Även om en stor mängd e-post kan indikera potentiella problem behövs bekräftelse på antingen skadliga omdömen eller en manuell granskning av e-postmeddelanden/kluster. Se [Hitta misstänkta e-postmeddelanden som har levererats](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered).|
|E-post|Inga hot hittades <br> (Systemet hittade inte några hot baserat på filer, URL:er eller analys av e-postkluster.)|Automatisk undersökning leder inte till en viss väntande åtgärd. <p>Hot som påträffas [och zapped](zero-hour-auto-purge.md) efter att en undersökning har slutförts återspeglas inte i en undersöknings numeriska resultat, men sådana hot kan visas i [Threat Explorer.](threat-explorer.md)|
|Användare|En användare har klickat på en skadlig URL <br> (En användare navigerade till en sida som senare visades vara skadlig, eller så gick en användare förbi en varningssida [med säkra](atp-safe-links.md#warning-pages-from-safe-links) länkar för att komma till en skadlig sida.)|Automatisk undersökning leder inte till en viss väntande åtgärd. <p>Blockera URL (tid för klickning) <p>Använd Hotutforskaren [för att visa data om URL:er och klicka på beslut](threat-explorer.md#view-phishing-url-and-click-verdict-data). <p>Om din organisation använder [Microsoft Defender för Slutpunkt kan du](/windows/security/threat-protection/)undersöka användaren för [att](/windows/security/threat-protection/microsoft-defender-atp/investigate-user) avgöra om deras konto har komprometterats.|
|Användare|En användare skickar skadlig kod/phish|Automatisk undersökning leder inte till en viss väntande åtgärd. <p> Användaren kan rapportera skadlig kod/phish eller så kan någon [kapa användaren](anti-spoofing-protection.md) som en del av en attack. Använd [Threat Explorer för](threat-explorer.md) att visa och hantera e-postmeddelanden som innehåller [skadlig](threat-explorer-views.md#email--malware) programvara [eller nätt innehåll.](threat-explorer-views.md#email--phish)|
|Användare|Vidarebefordran av e-post <br> (Regler för vidarebefordran av postlåda är konfigurerade, som kan användas för data exfiltrering.)|Ta bort vidare vidarebefordranregel <p> Använd [insikter i e-postflödet,](mail-flow-insights-v2.md)inklusive rapporten [Meddelanden som vidarebefordras automatiskt,](mfi-auto-forwarded-messages-report.md)om du vill visa mer specifik information om vidarebefordrad e-post.|
|Användare|Regler för e-postdelegering <br> (En användares konto har delegering konfigurerat.)|Ta bort delegeringsregel <p> Om din organisation använder [Microsoft Defender för Endpoint kan](/windows/security/threat-protection/)du undersöka [användaren](/windows/security/threat-protection/microsoft-defender-atp/investigate-user) som får delegeringsbehörigheten.|
|Användare|Data exfiltrering <br> (En användare har brutit mot E-post eller [DLP-principer för fildelning](../../compliance/data-loss-prevention-policies.md).)|Automatisk undersökning leder inte till en viss väntande åtgärd. <p> [Visa DLP-rapporter och vidta åtgärder.](../../compliance/view-the-dlp-reports.md)|
|Användare|Avvikande e-postavsändande <br> (En användare skickade nyligen fler e-postmeddelanden än under de föregående 7–10 dagarna.)|Automatisk undersökning leder inte till en viss väntande åtgärd. <p> Att skicka en stor mängd e-post är inte skadligt för sig. Användaren kanske precis har skickat e-post till en stor grupp mottagare för ett evenemang. Undersök genom att använda insikter [om e-postflöde](mail-flow-insights-v2.md), [inklusive](mfi-mail-flow-map-report.md) rapporten e-postflödeskarta för att avgöra vad som händer och vidta åtgärder.|

## <a name="next-steps"></a>Nästa steg

- [Visa information och resultat från en automatiserad undersökning i Microsoft Defender för Office 365](air-view-investigation-results.md)
- [Visa väntande eller slutförda åtgärdsåtgärder efter en automatiserad undersökning i Microsoft Defender för Office 365](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>Relaterade artiklar

- [Läs mer om automatiserad undersökning i Microsoft Defender för Endpoint](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [Läs mer om funktionerna i Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)