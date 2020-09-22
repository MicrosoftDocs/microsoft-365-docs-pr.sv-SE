---
title: Översikt över säkerhets instrument panelen
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Använd den nya säkerhets instrument panelen för att granska status för skydd mot Office 365 och Visa och åtgärda säkerhets varningar.
ms.openlocfilehash: 1bef6d0496c39d5157bbc40893d2710e89d1c734
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200079"
---
# <a name="security-dashboard"></a>Säkerhets instrument panel

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-functions-and-how-to-open-security-dashboard"></a>Grundläggande funktioner och hur du öppnar säkerhets instrument panelen

Med funktionen för [säkerhets & efterlevnad](../../compliance/go-to-the-securitycompliance-center.md) kan organisationen hantera data skydd och efterlevnad. Förutsatt att du har nödvändig behörighet kan du med hjälp av säkerhets instrument panelen kontrol lera skydds status för hotet samt Visa och reagera på säkerhets varningar.

Titta på videon för att få en översikt och Läs sedan mer i den här artikeln.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]

Beroende på vad din organisations abonnemang inkluderar inkluderar säkerhets instrument panelen flera widgetar, till exempel en sammanfattning av hot Management, Hot skydds status, globala vecko hotets identifieringar, skadlig kod och mer, enligt beskrivningen i följande avsnitt.

Om du vill visa säkerhets instrument panelen går du till fliken **Threat Management** på instrument panelen för [säkerhet &](../../compliance/go-to-the-securitycompliance-center.md) \> **Dashboard**.

> [!NOTE]
> Du måste vara global administratör, en säkerhets administratör eller en säkerhets läsare för att Visa säkerhets instrument panelen. Vissa widgetar kräver ytterligare behörigheter för att visas. Mer information finns i [behörigheter i säkerhets & Compliance Center](permissions-in-the-security-and-compliance-center.md).

## <a name="threat-management-summary"></a>Sammanfattning för Threat Management

Med widgeten Threat Management Summary får du en överblick över hur din organisation skyddas mot hot under de senaste sju (7) dagarna.

![Säkerhets instrument panel-widget för Threat Management Summary](../../media/SecDash-ThreatMgmtSummary.png)

Vilken information som visas i sammanfattningen av Threat Management beror på vad du har för abonnemanget. I följande tabell beskrivs vilken information som ingår i Office 365 E3 och Office 365 E5.

|Office 365 E3|Office 365 E5|
|---|---|
|Blockerade meddelanden<br/>Blockerade nätfiske-meddelanden<br>Meddelanden som rapporter ATS av användare<br><br><br><br>|Blockerade meddelanden<br>Blockerade nätfiske-meddelanden<br>Meddelanden som rapporter ATS av användare<br>Ej använda skadlig program vara blockerat<br>Avancerade nät fiske meddelanden upptäcktes<br>Blockerade URL-adresser|

Om du vill visa eller få åtkomst till widgeten Threat Management Summary måste du ha behörighet att visa avancerade hot skydds rapporter. Mer information finns i [vilka behörigheter behövs för att Visa ATP-rapporter?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)

## <a name="threat-protection-status"></a>Status för hot skydd

I widgeten Threat Protection status visas en trend och en detaljerad vy med Phish och skadlig program vara.

![Widget för hot skydd status](../../media/tpswidget.png)

Detaljerna varierar beroende på om ditt Microsoft 365-abonnemang innehåller [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) med eller utan [Office 365 Avancerat skydd](office-365-atp.md) (ATP).

|Om ditt abonnemang inkluderar...|Du kommer att se dessa uppgifter|
|---|---|
|EOP men inte Office 365 ATP|Skadlig e-post som identifieras och blockeras av EOP.<br><br> Se [status rapport för hot Protection (EOP)](view-email-security-reports.md#threat-protection-status-report).|
|Skaffa Office 365 ATP|Skadligt innehåll och skadlig e-post som identifieras och blockeras av EOP och Office 365 ATP<br><br>Sammanslagna antal unika e-postmeddelanden med skadligt innehåll blockerat av motorn mot skadlig program vara, [Automatisk rensning med Tom timme](zero-hour-auto-purge.md)och funktioner för ATP (inklusive [säkra länkar](atp-safe-links.md), [säkra bifogade filer](atp-safe-attachments.md)och [ATP-nätfiske](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)).<br><br>Se [status rapport för hot skydd (ATP)](view-reports-for-atp.md#threat-protection-status-report).|

Om du vill visa eller komma åt skydds widgeten för hotet måste du ha behörighet att visa avancerade hot skydds rapporter. Mer information finns i [vilka behörigheter behövs för att Visa ATP-rapporter?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)

## <a name="global-weekly-threat-detections"></a>Globala vecko risk identifieringar

Den globala borttagnings widgeten för varje vecka visar hur många hot som upptäckts i e-postmeddelanden under de senaste sju (7) dagarna.

![Widget för hot identifierings kontroll för globala veckovis](../../media/globalweeklythreatdetections.png)

Måtten beräknas enligt följande tabell:

|Mät|Så här beräknas den|
|---|---|
|Meddelanden skannade|Antalet e-postmeddelanden som skannats multiplicerat med antalet mottagare|
|Hot stoppade|Antalet e-postmeddelanden som identifieras som innehåller skadlig program vara multiplicerat med antalet mottagare|
|Blockerat av [ATP](office-365-atp.md)|Antalet e-postmeddelanden som blockeras av ATP multiplicerat med antalet mottagare|
|Borttaget efter leverans|Antal meddelanden som tagits bort från en [Tom timme](zero-hour-auto-purge.md) multiplicerat med antalet mottagare|

## <a name="malware"></a>Program

Widgetar skadliga program visar information om trender för skadlig program vara och typer av skadlig program vara under de senaste sju (7) dagarna.

![Trender och familje typer för skadlig program vara](../../media/malwarewidgetatpe5.png)

## <a name="insights"></a>Insikter

Insikter som inte bara innehåller problem med Surface-frågor som du bör granska, men även rekommendationer och åtgärder.

![Smarta insikter](../../media/smartinsights.png)

Du kan till exempel se att nät fiske meddelanden levereras eftersom vissa användare har inaktiverat sina alternativ för skräp post. Mer information om hur insikter fungerar finns i [rapporter och insikter i avsnittet om säkerhets & efterlevnad](reports-and-insights-in-security-and-compliance.md).

## <a name="threat-investigation-and-response"></a>Hot utredning och svar

Om organisationens abonnemang innehåller  [Office 365 Avancerat skydds abonnemang 2](office-365-ti.md), har din säkerhets instrument panel ett avsnitt som innehåller avancerad Threat-granskning och svars verktyg. Dessa verktyg inkluderar [automatiserade funktioner för undersökning och svar](automated-investigation-response-office.md). Den automatiska undersökningen och svaret kan vara till hjälp när det är [lätt att adressera vissa användar konton](address-compromised-users-quickly.md).

Mer information finns i [komma igång med automatisk undersökning och svar (Air) i Office 365](office-365-air.md).

## <a name="trends"></a>Tendens

Längst ned i säkerhets instrument panelen är ett avsnitt för **trender** som sammanfattar e-postflöden i din organisation. Rapporter ger information om e-post kategoriserade som skräp post, skadlig kod, nät fiske försök och bra e-post. Klicka på en panel för att visa mer detaljerad information i rapporten.

![Avsnittet trender sammanfattar trender för e-postflöde för organisationen](../../media/trends.png)

Och om organisationens abonnemang innehåller [Office 365 Avancerat skydds plan 2](office-365-ti.md)kommer du också att ha en **senaste varnings rapport för hot Management** i det här avsnittet som gör det möjligt för din säkerhets grupp att visa och vidta åtgärder för säkerhets varningar med hög prioritet.

Om du vill visa eller komma åt widgeten för skickade och mottagna e-postmeddelanden måste du ha behörighet att visa avancerade hot skydds rapporter. Mer information finns i [vilka behörigheter behövs för att Visa ATP-rapporter?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)

Om du vill visa eller komma åt den senaste widgeten Threat Management Alerts måste du ha behörighet att visa aviseringar. Mer information finns i [behörigheter för RBAC som krävs för att visa aviseringar](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts).

## <a name="related-topics"></a>Relaterade ämnen

[Visa säkerhets rapporter för e-post i säkerhets & efterlevnad](view-email-security-reports.md)

[Visa rapporter för Office 365 Avancerat skydd](view-reports-for-atp.md)

[Office 365 Avancerat skydd](office-365-atp.md)

[Office 365 hot undersökningar och svar](office-365-ti.md)
