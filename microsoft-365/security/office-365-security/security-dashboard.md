---
title: Översikt över säkerhetsinstrumentpanel
f1.keywords:
- NOCSH
ms.author: siosulli
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Använd den nya säkerhetsinstrumentpanel för att granska status för Office 365 Threat Protection, och visa och agera på säkerhetsvarningar.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 72743f1b052d39ac4762dffc0b3e3e694befa8bc
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "50288329"
---
# <a name="security-dashboard"></a>Säkerhetsinstrumentpanel

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-functions-and-how-to-open-security-dashboard"></a>Grundläggande funktioner och hur du öppnar säkerhetsinstrumentpanel

Säkerhets- [& efterlevnadscenter](../../compliance/go-to-the-securitycompliance-center.md) gör det möjligt för organisationen att hantera dataskydd och efterlevnad. Om du har nödvändiga behörigheter gör säkerhetspanelen att du kan granska din status för skydd mot hot samt visa och agera på säkerhetsvarningar.

Titta på videon för att få en översikt och läs sedan den här artikeln för mer information.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]

Beroende på vad din organisations prenumeration innehåller innehåller Säkerhetsinstrumentpanel flera widgetar, till exempel Sammanfattning av hothantering, Status för skydd mot hot, Global veckovis identifiering av hot, skadlig kod med mera, enligt beskrivningen i följande avsnitt.

Gå till instrumentpanelen för hantering av hot [om du vill &](../../compliance/go-to-the-securitycompliance-center.md)säkerhets- och  \> **säkerhetscentret.**

> [!NOTE]
> Du måste vara global administratör, säkerhetsadministratör eller säkerhetsläsare för att kunna visa instrumentpanelen för säkerhet. För vissa widgetar krävs ytterligare behörigheter för att visa. Mer information finns i [Behörigheter i Säkerhets- & Efterlevnadscenter.](permissions-in-the-security-and-compliance-center.md)

## <a name="threat-management-summary"></a>Sammanfattning av hothantering

Widgeten Sammanfattning av hothantering visar en översikt över hur organisationen har skyddats mot hot under de senaste sju (7) dagarna.

![Instrumentpanel för säkerhet – widget för sammanfattning av hothantering](../../media/SecDash-ThreatMgmtSummary.png)

Informationen som visas i sammanfattningen av hothanteringen beror på vad din prenumeration innehåller. I följande tabell beskrivs vilken information som ingår i Office 365 E3 och Office 365 E5.

|Office 365 E3|Office 365 E5|
|---|---|
|Blockerade skadliga meddelanden<br>Nätfiskemeddelanden blockerade<br>Meddelanden som rapporterats av användare<br><br><br><br>|Blockerade skadliga meddelanden<br>Nätfiskemeddelanden blockerade<br>Meddelanden som rapporterats av användare<br>Nolldagars skadlig programvara blockerad<br>Avancerade nätfiskemeddelanden har upptäckts<br>Skadliga URL:er blockeras|

Om du vill visa eller komma åt widgeten Sammanfattning av hothantering måste du ha behörighet att visa Defender för Office 365-rapporter. Mer information finns i Vilka [behörigheter krävs för att visa Rapporterna i Defender för Office 365?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)

## <a name="threat-protection-status"></a>Status för skydd mot hot

Widgeten Status för skydd mot hot visar hur effektivt skyddet för hot är med en trendande och detaljerad vy av nätt och skadlig programvara.

![Statuswidget för hotskydd](../../media/tpswidget.png)

Informationen beror på om Microsoft 365-prenumerationen omfattar [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) med eller utan Microsoft Defender för Office [365.](office-365-atp.md)

|Om din prenumeration innehåller...|Den här informationen visas|
|---|---|
|EOP men inte Microsoft Defender för Office 365|Skadlig e-post som har upptäckts och blockerats av EOP.<p> Se [rapporten om skydd mot hot (EOP).](view-email-security-reports.md#threat-protection-status-report)|
|Microsoft Defender för Office 365|Skadligt innehåll och skadlig e-post som identifieras och blockeras av EOP och Defender för Office 365 <p> Aggregerat antal unika [e-postmeddelanden](zero-hour-auto-purge.md)med skadligt innehåll som blockerats av antivirusmotorn, automatisk rensning på nolltimmar och Defender [](atp-safe-attachments.md)för Office 365-funktioner (inklusive säkra [länkar,](atp-safe-links.md)säkra bifogade filer och nätfiske i Defender för [Office 365).](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) <p> Se [statusrapporten för skydd mot hot.](view-reports-for-atp.md#threat-protection-status-report)|

Om du vill visa eller komma åt widgeten Skydd mot hot måste du ha behörighet att visa Defender för Office 365-rapporter. Mer information finns i Vilka [behörigheter krävs för att visa rapporterna i Defender för Office 365?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)

## <a name="global-weekly-threat-detections"></a>Global Weekly Threat Detections

Widgeten Global Weekly Threat Detections visar hur många hot som upptäckts i e-postmeddelanden under de senaste sju (7) dagarna.

![Widget för global veckovis identifiering av hot](../../media/globalweeklythreatdetections.png)

Måtten beräknas enligt beskrivningen i följande tabell:

|Metrisk|Så här beräknas det|
|---|---|
|Meddelanden skannade|Antalet e-postmeddelanden som genomsöks multiplicerat med antalet mottagare|
|Hot har stoppats|Antalet e-postmeddelanden som identifierats som innehåller skadlig programvara multiplicerat med antalet mottagare|
|Blockeras av [Defender för Office 365 ](office-365-atp.md)|Antalet e-postmeddelanden som blockeras av Defender för Office 365 multiplicerat med antalet mottagare|
|Tas bort efter leverans|Antalet meddelanden som tagits [bort med automatisk rensning utan timme](zero-hour-auto-purge.md) multiplicerat med antalet mottagare|

## <a name="malware"></a>Skadlig programvara

Widgetar för skadlig programvara visar information om trender i skadlig programvara och familjetyper för skadlig programvara under de senaste sju (7) dagarna.

![Trender i skadlig programvara och familjetyper](../../media/malwarewidgetatpe5.png)

## <a name="insights"></a>Insikter

Insikter tar inte bara fram viktiga problem som du bör granska, de innehåller även rekommendationer och åtgärder att tänka på.

![Smarta insikter](../../media/smartinsights.png)

Du kan till exempel se att nätfiskemeddelanden levereras eftersom vissa användare har inaktiverat sina skräppostalternativ. Mer information om hur insikter fungerar finns i [Rapporter och insikter i Säkerhets- & Efterlevnadscenter.](reports-and-insights-in-security-and-compliance.md)

## <a name="threat-investigation-and-response"></a>Hotundersökning och -svar

Om din organisations prenumeration omfattar Microsoft Defender för  [Office 365 abonnemang 2](office-365-ti.md)har din säkerhetsinstrumentpanel ett avsnitt som innehåller avancerad undersökning av hot och svarsverktyg. Dessa verktyg innehåller [automatisk undersökning och svarsfunktioner.](automated-investigation-response-office.md) Automatiserad undersökning och svar kan vara användbart i scenarier som [att snabbt hantera komprometterade användarkonton.](address-compromised-users-quickly.md)

Mer information finns i [Komma igång med automatiserad undersökning och svar (AIR) i Office 365.](office-365-air.md)

## <a name="trends"></a>Trender

Längst ned på instrumentpanelen för säkerhet finns ett **trends-avsnitt** som sammanfattar e-postflödestrender för din organisation. Med rapporter får du information om e-post som kategoriserats som skräppost, skadlig kod, försök till nätfiske och bra e-post. Klicka på en panel om du vill visa mer detaljerad information i rapporten.

![I avsnittet Trender sammanfattas e-postflödestrender för organisationen](../../media/trends.png)

Om din organisations prenumeration omfattar Defender för [Office 365 abonnemang 2](office-365-ti.md)har du även en rapport om senaste varningar om hothantering i det här avsnittet som gör att säkerhetsteamet kan visa och vidta åtgärder för säkerhetsvarningar med hög prioritet. 

Om du vill visa eller komma åt widgeten Skickad och mottagen e-post måste du ha behörighet att visa Defender för Office 365-rapporter. Mer information finns i Vilka [behörigheter krävs för att visa Rapporterna i Defender för Office 365?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)

Om du vill visa eller komma åt widgeten Senaste hothanteringsvarningar måste du ha behörighet att visa aviseringar. Mer information finns i [RBAC-behörigheter som krävs för att visa aviseringar.](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts)

## <a name="related-topics"></a>Relaterade ämnen

[Visa e-postsäkerhetsrapporter i Säkerhets- & Efterlevnadscenter](view-email-security-reports.md)

[Visa rapporter för Microsoft Defender för Office 365](view-reports-for-atp.md)

[Defender förr Office 365](office-365-atp.md)

[Undersökning och svar av hot i Office 365](office-365-ti.md)
