---
title: Översikt över säkerhetsinstrumentpanel
f1.keywords:
- NOCSH
ms.author: siosulli
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Använd den nya säkerhetspanelen för att Office 365 status för skydd mot hot, och visa och agera på säkerhetsvarningar.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 71c077853c8dbb68b78c8073f650bcb2df4d1b9a
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246459"
---
# <a name="security-dashboard"></a>Säkerhetsinstrumentpanel

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-functions-and-how-to-open-security-dashboard"></a>Grundläggande funktioner och hur du öppnar Säkerhetsinstrumentpanel

Säkerhets- [& efterlevnadscenter](../../compliance/microsoft-365-compliance-center.md) gör det möjligt för organisationen att hantera dataskydd och efterlevnad. Om du har de behörigheter som krävs kan du med hjälp av instrumentpanelen för säkerhet granska din status för skydd mot hot samt visa och agera på säkerhetsvarningar.

Titta på videon för att få en översikt och läs sedan den här artikeln om du vill veta mer.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]

Beroende på vad din organisations prenumeration inkluderar innehåller instrumentpanelen för säkerhet flera widgetar, till exempel Sammanfattning av hothantering, Hotskyddsstatus, Global veckovis identifiering av hot, skadlig programvara med mera, som beskrivs i följande avsnitt.

Om du vill visa Säkerhetsinstrumentpanel går [du & Säkerhets- och efterlevnadscenter](../../compliance/microsoft-365-compliance-center.md)på **Instrumentpanelen för hantering av** \> **hot.**

> [!NOTE]
> Du måste vara global administratör, säkerhetsadministratör eller säkerhetsläsare för att kunna visa instrumentpanelen för säkerhet. Vissa widgetar kräver ytterligare behörigheter för att visa. Mer information finns i [Behörigheter i Säkerhets- & Kompatibilitetscenter.](permissions-in-the-security-and-compliance-center.md)

## <a name="threat-management-summary"></a>Sammanfattning av hothantering

Widgeten Sammanfattning av hothantering visar direkt hur organisationen har skyddats mot hot under de senaste sju (7) dagarna.

![Instrumentpanel för säkerhet – widget för sammanfattning av hothantering](../../media/SecDash-ThreatMgmtSummary.png)

Vilken information du ser i sammanfattningen av hothanteringen beror på vad din prenumeration innehåller. I följande tabell beskrivs vilken information som ingår i Office 365 E3 och Office 365 E5.

|Office 365 E3|Office 365 E5|
|---|---|
|Skadliga meddelanden blockerade<br>Nätfiskemeddelanden är blockerade<br>Meddelanden som rapporterats av användare<br><br><br><br>|Skadliga meddelanden blockerade<br>Nätfiskemeddelanden är blockerade<br>Meddelanden som rapporterats av användare<br>Nolldagars skadlig programvara blockerad<br>Avancerade nätfiskemeddelanden har upptäckts<br>Skadliga URL:er blockeras|

Om du vill visa eller komma åt widgeten Sammanfattning av hothantering måste du ha behörighet att visa Defender Office 365. Mer information finns i [Vilka behörigheter krävs för att visa Defender för Office 365 rapporter?](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports).

## <a name="threat-protection-status"></a>Status för skydd mot hot

Widgeten Hotskyddsstatus visar hur effektivt skyddet för hot är med en trendande och detaljerad vy över nätt och skadlig programvara.

![Widget för hotskyddsstatus](../../media/tpswidget.png)

Informationen beror på om EOP (Microsoft 365 Subscription includes [Exchange Online Protection)](exchange-online-protection-overview.md) med eller utan [Microsoft Defender för Office 365.](defender-for-office-365.md)

|Om din prenumeration inkluderar...|Den här informationen visas|
|---|---|
|EOP men inte Microsoft Defender för Office 365|Skadlig e-post som har upptäckts och blockerats av EOP.<p> Se [Statusrapport för skydd mot hot (EOP).](view-email-security-reports.md#threat-protection-status-report)|
|Microsoft Defender för Office 365|Skadligt innehåll och skadlig e-post som identifieras och blockeras av EOP och Defender för Office 365 <p> Aggregerat antal unika e-postmeddelanden med skadligt innehåll som [](zero-hour-auto-purge.md)blockerats av antivirusmotorn, automatisk rensning utan timme och Defender för Office 365-funktioner (inklusive [Valv-länkar,](safe-links.md) [Valv-bilagor](safe-attachments.md)och skydd mot nätfiske i Defender för [Office 365).](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) <p> Se [statusrapport om skydd mot hot.](view-reports-for-mdo.md#threat-protection-status-report)|

Om du vill visa eller komma åt widgeten Hotskyddsstatus måste du ha behörighet att visa Defender Office 365 rapporter. Mer information finns i [Vilka behörigheter krävs för att visa Defender för Office 365 rapporter?](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)

## <a name="global-weekly-threat-detections"></a>Global veckovis identifiering av hot

Widgeten Global Weekly Threat Detections visar hur många hot som har upptäckts i e-postmeddelanden under de senaste sju (7) dagarna.

![Widget för global veckovis identifiering av hot](../../media/globalweeklythreatdetections.png)

Måtten beräknas enligt beskrivningen i följande tabell:

|Metrisk|Så här beräknas det|
|---|---|
|Meddelanden skannade|Antalet e-postmeddelanden som genomsöks multiplicerat med antalet mottagare|
|Hot har stoppats|Antalet e-postmeddelanden som identifierats som innehåller skadlig programvara multiplicerat med antalet mottagare|
|Blockeras av [Defender för Office 365](defender-for-office-365.md)|Antalet e-postmeddelanden som blockeras av Defender för Office 365 multiplicerat med antalet mottagare|
|Tas bort efter leverans|Antalet meddelanden som tagits [bort med en automatisk rensning på nolltimmar](zero-hour-auto-purge.md) multiplicerat med antalet mottagare|

## <a name="malware"></a>Skadlig programvara

Widgetar för skadlig programvara visar information om trender och familjetyper för skadlig programvara under de senaste sju (7) dagarna.

![Trender och familjetyper för skadlig programvara](../../media/malwarewidgetatpe5.png)

## <a name="insights"></a>Insikter

Insikter tar inte bara upp viktiga problem som du bör granska, de innehåller även rekommendationer och åtgärder att överväga.

![Smarta insikter](../../media/smartinsights.png)

Du kan till exempel se att nätfiskemeddelanden levereras eftersom vissa användare har inaktiverat sina skräppostalternativ. Mer information om hur insikter fungerar finns i Rapporter och insikter i Säkerhets- & [Efterlevnadscenter.](reports-and-insights-in-security-and-compliance.md)

## <a name="threat-investigation-and-response"></a>Undersökning och svar på hot

Om din organisations prenumeration omfattar Microsoft Defender för [Office 365 abonnemang 2](office-365-ti.md)har din säkerhetsinstrumentpanel ett avsnitt som innehåller avancerade undersöknings- och svarsverktyg för hot. Dessa verktyg innehåller [automatiserad undersökning och svarsfunktioner.](automated-investigation-response-office.md) Automatisk undersökning och svar kan vara användbart i scenarier som att [hantera komprometterade användarkonton snabbt.](address-compromised-users-quickly.md)

Mer information finns i [Komma igång med automatiserad undersökning och svar (AIR) i Office 365.](office-365-air.md)

## <a name="trends"></a>Trender

Längst ned på instrumentpanelen för säkerhet finns avsnittet **Trender,** som sammanfattar e-postflödestrender för din organisation. Med rapporter får du information om e-post som kategoriserats som skräppost, skadlig kod, försök till nätfiske och bra e-post. Klicka på en panel om du vill visa mer detaljerad information i rapporten.

![I avsnittet Trender sammanfattas e-postflödestrender för organisationen](../../media/trends.png)

Om din organisations prenumeration omfattar Defender för [Office 365 abonnemang 2](office-365-ti.md)har du  även en rapport om händelser för hantering av hot i det här avsnittet som gör att säkerhetsteamet kan se och vidta åtgärder för högprioriterade säkerhetsvarningar.

Om du vill visa eller komma åt widgeten Skickad och mottagen e-post måste du ha behörighet att visa Defender Office 365 rapporter. Mer information finns i [Vilka behörigheter krävs för att visa Defender för Office 365 rapporter?](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports).

Om du vill visa eller komma åt widgeten Senaste hothanteringsvarningar måste du ha behörighet att visa aviseringar. Mer information finns i [RBAC-behörigheter som krävs för att visa aviseringar.](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts)

## <a name="related-topics"></a>Relaterade ämnen

[Visa e-postsäkerhetsrapporter i Säkerhets- & Säkerhets- och efterlevnadscenter](view-email-security-reports.md)

[Visa rapporter för Microsoft Defender för Office 365](view-reports-for-mdo.md)

[Microsoft Defender för Office 365](defender-for-office-365.md)

[Office 365 Undersökning och svar på hot](office-365-ti.md)