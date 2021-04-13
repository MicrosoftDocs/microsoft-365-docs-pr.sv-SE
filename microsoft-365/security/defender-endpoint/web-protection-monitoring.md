---
title: Övervaka webbsurfningssäkerhet i Microsoft Defender för Endpoint
description: Använda webbskydd i Microsoft Defender för slutpunkt för att övervaka webbsurfningssäkerhet
keywords: webbskydd, skydd mot webbhot, surfning, övervakning, rapporter, kort, domänlista, säkerhet, nätfiske, skadlig kod, sårbarhet, webbplatser, nätverksskydd, Edge, Internet Explorer, Chrome, Firefox, webbläsare
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ee6388c779d2c5bc09a82f5e9064d1b981e885cb
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687429"
---
# <a name="monitor-web-browsing-security"></a>Övervaka surfsäkerhet

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

Med webbskydd kan du övervaka organisationens webbsurfningssäkerhet genom rapporter under **Rapporter > skydd på** webben i Microsoft Defender Säkerhetscenter. Rapporten innehåller kort som tillhandahåller statistik för identifiering av webbhot.

- **Identifiering av skydd** mot webbhot med tiden – det här trendkortet visar antalet webbhot som upptäckts av typ under den valda tidsperioden (de senaste 30 dagarna, de senaste 3 månaderna, de senaste 6 månaderna)
 
    ![Bild på kortet som visar identifieringar av skydd mot webbhot över tid](images/wtp-blocks-over-time.png)

- **Sammanfattning av skydd** mot webbhot – det här kortet visar totalt antal identifieringar av webbhot under de senaste 30 dagarna, med distribution för olika typer av webbhot. Om du väljer en sektor öppnas listan med domäner som hittades med skadliga eller oönskade webbplatser.

    ![Bild på kortet som visar en sammanfattning av skydd mot webbhot](images/wtp-summary.png)

>[!Note]
>Det kan ta upp till 12 timmar innan ett block visas på korten eller i domänlistan.

## <a name="types-of-web-threats"></a>Typer av webbhot

Webbskydd kategoriserar skadliga och oönskade webbplatser som:

- **Nätfiske** – webbplatser som innehåller falska webbformulär och andra former av nätfiske som designats för att lura användare att dela upp autentiseringsuppgifter och annan känslig information
- **Skadlig** – webbplatser som är värd för skadlig programvara och sårbarhetskod
- **Anpassad indikator** – webbplatser vars URL:er eller domäner du har lagt till i din [anpassade indikatorlista för](manage-indicators.md) blockering

## <a name="view-the-domain-list"></a>Visa domänlistan

Välj en specifik kategori för webbhot i **sammanfattningskortet för skydd mot webbhot** för att öppna **sidan** Domäner. Den här sidan visar listan över domänerna under den hotkategorin. Sidan innehåller följande information för varje domän:

- **Antal åtkomst** – antal förfrågningar om URL-adresser i domänen
- **Block** – antal gånger som förfrågningar har blockerats
- **Access-trend** – ändra antalet åtkomstförsök
- **Hotkategori** – typ av webbhot
- **Enheter** – antal enheter med åtkomstförsök

Välj en domän för att visa listan över enheter som har försökt komma åt URL:er i den domänen och listan med URL:er.

## <a name="related-topics"></a>Relaterade ämnen

- [Översikt över webbskydd](web-protection-overview.md)
- [Filtrering av webbinnehåll](web-content-filtering.md)
- [Skydd mot webbhot](web-threat-protection.md)
- [Svara på webbhot](web-protection-response.md)
