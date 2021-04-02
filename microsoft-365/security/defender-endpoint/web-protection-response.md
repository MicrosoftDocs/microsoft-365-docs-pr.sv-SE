---
title: Svara på webbhot i Microsoft Defender ATP
description: Svara på aviseringar som rör skadliga och oönskade webbplatser. Förstå hur skydd mot webbhot informerar slutanvändarna via deras webbläsare och Windows-meddelanden
keywords: webbskydd, skydd mot webbhot, surfning, varningar, svar, säkerhet, nätfiske, skadlig kod, sårbarhet, webbplatser, nätverksskydd, Edge, Internet Explorer, Chrome, Firefox, webbläsare, meddelanden, slutanvändare, Windows-meddelanden, blockeringssida,
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
ms.openlocfilehash: b0e6bb0d71c14bf7742f8d6508fbb95b76b10a34
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498358"
---
# <a name="respond-to-web-threats"></a>Svara på webbhot

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

Med webbskydd i Microsoft Defender för Slutpunkt kan du effektivt undersöka och svara på aviseringar som rör skadliga webbplatser och webbplatser i din anpassade indikatorlista.

## <a name="view-web-threat-alerts"></a>Visa varningar för webbhot
Microsoft Defender för Slutpunkt genererar följande [aviseringar om](manage-alerts.md) skadlig eller misstänkt webbaktivitet:
- **Misstänkt anslutning som blockeras** av nätverksskydd – den här aviseringen genereras när ett  försök att komma åt en skadlig webbplats eller en webbplats i den anpassade indikatorlistan stoppas av nätverksskydd i *blockeringsläge*
- **Misstänkt anslutning som upptäckts** av nätverksskydd – den här varningen genereras när ett försök att komma åt en skadlig webbplats eller en webbplats i den anpassade indikatorlistan identifieras av nätverksskyddet i *granskningsläge*

Varje avisering ger följande information: 
- Enhet som försökte komma åt den blockerade webbplatsen
- Program eller program som används för att skicka webbbegäran
- Skadlig URL eller URL i den anpassade indikatorlistan
- Rekommenderade åtgärder för svarare

![Bild av en avisering som rör skydd mot webbhot](images/wtp-alert.png)

>[!Note]
>För att minska mängden aviseringar konsoliderar Microsoft Defender för Endpoint identifiering av webbhot för samma domän på samma enhet varje dag till en enda avisering. Endast en avisering skapas och räknas in i [skyddsrapporten för webben.](web-protection-monitoring.md)

## <a name="inspect-website-details"></a>Kontrollera webbplatsinformation
Du kan visa mer genom att välja webbadressen eller domänen för webbplatsen i aviseringen. Då öppnas en sida om just den URL:en eller domänen med olika information, till exempel:
- Enheter som försökte komma åt webbplatsen
- Incidenter och aviseringar relaterade till webbplatsen
- Hur ofta webbplatsen sågs i händelser i organisationen

    ![Bild av informationssidan för domänen eller URL-adressen](images/wtp-website-details.png)

[Läs mer om sidorna för URL- eller domänentitet](investigate-domain.md)

## <a name="inspect-the-device"></a>Kontrollera enheten
Du kan också kontrollera vilken enhet som försökte komma åt en blockerad URL. Om du väljer namnet på enheten på aviseringssidan öppnas en sida med omfattande information om enheten.

[Läs mer om enhetsentitetssidor](investigate-machines.md)

## <a name="web-browser-and-windows-notifications-for-end-users"></a>Webbläsare och Windows-meddelanden för slutanvändare

Med webbskydd i Microsoft Defender för Endpoint hindras slutanvändarna från att besöka skadliga eller oönskade webbplatser med hjälp av Microsoft Edge eller andra webbläsare. Eftersom blockering utförs av [nätverksskydd](network-protection.md)ser de ett allmänt fel från webbläsaren. De ser också ett meddelande från Windows.

![Bild på Microsoft Edge som visar ett 403-fel och Windows-meddelandet ](images/wtp-browser-blocking-page.png)
 *Webbhot blockeras i Microsoft Edge*

![Bild på Chrome-webbläsare som visar en varning om säker anslutning och Webbhotet i Windows ](images/wtp-chrome-browser-blocking-page.png)
 *blockeras i Chrome*

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över webbskydd](web-protection-overview.md)
- [Filtrering av webbinnehåll](web-content-filtering.md)
- [Skydd mot webbhot](web-threat-protection.md)
- [Övervaka webbsäkerhet](web-protection-monitoring.md)
