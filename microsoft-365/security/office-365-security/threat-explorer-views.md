---
title: Vyer i HotUtforskaren och identifieringar i realtid
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 05/15/2020
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Läs mer om hur du använder Hotutforskaren och rapporten om identifiering i realtid för att undersöka och hantera hot i Säkerhets- & Efterlevnadscenter.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: aef3f7fe69e5cbd1d70b7aee3284f0c5dc6416df
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290291"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a>Vyer i HotUtforskaren och identifieringar i realtid

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)


![Hotutforskaren](../../media/ThreatExplorerFirstOpened.png)

[Threat Explorer](threat-explorer.md) (och rapporten om identifiering i realtid) är ett kraftfullt verktyg i närheten av realtid som hjälper grupper i säkerhetsoperationer att undersöka och reagera på hot i Säkerhets- & Efterlevnadscenter. Utforskaren (och rapporten om identifieringar i realtid) visar information om misstänkt skadlig programvara och phish i e-post och filer i Office 365, samt andra säkerhetshot och risker för din organisation.

- Om du har [Microsoft Defender för Office 365](office-365-atp.md) abonnemang 2 har du Utforskaren.
- Om du har Microsoft Defender för Office 365 abonnemang 1 kan du göra identifieringar i realtid.

När du först öppnar Utforskaren (eller rapporten över identifieringar i realtid) visar standardvyn identifiering av skadlig kod för e-post under de senaste 7 dagarna. Den här rapporten kan också visa identifieringar av Microsoft Defender för Office [](atp-safe-links.md)365, till exempel skadliga URL-adresser som identifieras av säkra länkar och skadliga filer som identifieras av [säkra bifogade filer.](atp-safe-attachments.md) Den här rapporten kan ändras så att den visar data för de senaste 30 dagarna (med en betalprenumeration på Microsoft Defender för Office 365 P2). Utvärderingsprenumerationer innehåller endast data för de senaste sju dagarna.

****

|Prenumeration|Verktyg|Dagar med data|
|---|---|---|
|Utvärderingsversion av Microsoft Defender för Office 365 P1|Identifiering i realtid|7|
|Microsoft Defender för Office 365 P1 betalad|Identifiering i realtid|30|
|Betaltestning av Microsoft Defender för Office 365 P1 för Office 365 P2|Hotutforskaren|7|
|Utvärderingsversion av Microsoft Defender för Office 365 P2|Hotutforskaren|7|
|Microsoft Defender för Office 365 P2 betalad|Hotutforskaren|30|
|

Använd **Visa-menyn** om du vill ändra vilken information som visas. Verktygstips hjälper dig att avgöra vilken vy du ska använda.

![Menyn Visa hotutforskaren](../../media/ThreatExplorerViewMenu.png)

När du har valt en vy kan du använda filter och konfigurera frågor för ytterligare analys. Följande avsnitt innehåller en kort översikt över de olika vyerna som är tillgängliga i Utforskaren (eller identifieringar i realtid).

## <a name="email--malware"></a>E-> skadlig programvara

Om du vill visa den här rapporten i Utforskaren (eller identifiering i realtid) väljer du **Visa skadlig programvara** för \> **e-post.** \>  I den här vyn visas information om e-postmeddelanden som identifierats som innehåller skadlig programvara.

![Visa data om e-post som identifieras som skadlig programvara](../../media/ExplorerEmailMalwareMenu.png)

Klicka **på Avsändaren** för att öppna listan med visningsalternativ. Använd den här listan för att visa data efter avsändare, mottagare, avsändardomän, ämne, identifieringsteknik, skyddsstatus med mera.

Om du till exempel vill se vilka åtgärder som har vidtas på identifierade e-postmeddelanden väljer du **Skydd-status** i listan. Välj ett alternativ och klicka sedan på knappen Uppdatera om du vill använda filtret i rapporten.

![Alternativ för status för skydd mot hot i Utforskaren](../../media/ThreatExplorerProtectionStatusOptions.png)

Under diagrammet kan du visa mer information om specifika meddelanden. När du markerar ett objekt i listan öppnas ett utfällt fönster där du kan läsa mer om det markerade objektet.

![Hotutforskaren med öppnad flygblad](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a>E-> Phish

Om du vill visa den här rapporten i Utforskaren (eller identifiering i realtid) väljer du **Visa** \>  \> **e-post phish.** I den här vyn visas e-postmeddelanden som identifieras som nätfiskeförsök.

![Visa data om e-post som identifieras som nätfiskeförsök](../../media/ThreatExplorerEmailPhish.png)

Klicka **på Avsändaren** för att öppna listan med visningsalternativ. Använd den här listan för att visa data efter avsändare, mottagare, avsändardomän, avsändar-IP, URL-domän, klicka på bedömningsvyn och mycket mer.

Om du till exempel vill se vilka åtgärder som har gjorts när  personer klickade på URL-adresser som identifierades som nätfiskeförsök väljer du Klicka på bedömning i listan, väljer ett eller flera alternativ och klickar sedan på knappen Uppdatera.

![Klicka på alternativ för bedömning av phish-rapporten](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

Under diagrammet kan du visa mer information om specifika meddelanden, URL-klick, URL-adresser och e-postursprung.

![URL:er som identifierats som phish i e-postmeddelanden](../../media/ThreatExplorerEmailPhishURLs.png)

När du markerar ett objekt i listan, till exempel en URL som identifierats, öppnas ett utfällt fönster där du kan läsa mer om det markerade objektet.

![Information om en upptäckt URL](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a>E-> inskickade meddelanden

Om du vill visa den här rapporten i Utforskaren (eller identifiering i realtid) väljer **du Visa** \>  \> **e-postinskick.** I den här vyn visas e-post som användare har rapporterat som skräppost, inte skräppost eller nätfiske.

![E-postmeddelanden som rapporterats av användare](../../media/ThreatExplorerEmailUserReportedViewOptions.png)

Klicka **på Avsändaren** för att öppna listan med visningsalternativ. Använd den här listan för att visa information efter avsändare, mottagare, rapporttyp (användarens avgörande om e-postmeddelandet var skräppost, inte skräppost eller phish) och mycket mer.

Om du till exempel vill visa information om e-postmeddelanden som rapporterats som nätfiskeförsök klickar du på Avsändarrapporttyp, väljer  Phish och klickar sedan \> på knappen Uppdatera. 

![Phish valt för Rapporttypfilter](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

Under diagrammet kan du visa mer information om specifika e-postmeddelanden, till exempel ämnesraden, avsändarens IP-adress, användaren som rapporterat meddelandet som skräppost, inte skräppost eller phish med mera.

![Meddelanden som rapporterats som nätfiskeförsök](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

Markera ett objekt i listan om du vill visa ytterligare information.

## <a name="email--all-email"></a>E-> all e-post

Om du vill visa den här rapporten väljer du Visa **e-post** för all \> **e-post i** \> **Utforskaren.** I de här vyerna visas en vy över e-postaktivitet, inklusive e-post som identifieras som skadlig på grund av nätfiske eller skadlig kod, samt all icke-skadlig e-post (vanlig e-post, skräppost och massutskick).

> [!NOTE]
> Om du får ett felmeddelande där det står För mycket **data** kan du lägga till ett filter och, om det behövs, begränsa det datumintervall som du visar.

Om du vill använda ett filter **väljer du Avsändare,** markerar ett objekt i listan och klickar sedan på knappen Uppdatera. I exemplet använde vi **identifieringsteknik som** ett filter (det finns flera tillgängliga alternativ). Visa information efter avsändare, avsändarens domän, mottagare, ämne, filnamn på bifogad fil, skadlig kodfamilj, skyddsstatus (åtgärder som vidtas av dina skyddsfunktioner och principer i Office 365), identifieringsteknik (hur den skadlig programvara identifierades) och mycket mer.

![Visa data om identifierad e-post med identifieringsteknik](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)

Under diagrammet kan du visa mer information om specifika e-postmeddelanden, till exempel ämnesrad, mottagare, avsändare, status och så vidare.

## <a name="content--malware"></a>Innehållskod > skadlig programvara

Om du vill visa den här rapporten i Utforskaren (eller identifiering i realtid) väljer **du Visa skadlig** programvara \> **för** \> **innehåll.** I den här vyn visas filer som identifierats som skadliga av Microsoft Defender för [Office 365 i SharePoint Online, OneDrive för företag och Microsoft Teams.](atp-for-spo-odb-and-teams.md)

Visa information efter programfamilj, identifieringsteknik (hur skadlig programvara upptäcktes) och arbetsbelastningen (OneDrive, SharePoint eller Teams).

![Visa data om upptäckt skadlig programvara](../../media/d11dc568-b091-4159-b261-df13d76b520b.png)

Under diagrammet kan du visa mer information om specifika filer, till exempel filnamn på bifogade filer, arbetsbelastning, filstorlek, vem som senast ändrade filen och mycket mer.

## <a name="click-to-filter-capabilities"></a>Funktioner för Klicka-och-filtrera

Med Utforskaren (och identifieringar i realtid) kan du använda ett filter med ett klick. Om du klickar på ett objekt i förklaringen blir objektet ett filter för rapporten. Anta till exempel att vi tittar på vyn Skadlig programvara i Utforskaren:

![Gå till \> Hothanteringsutforskaren](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

Om **du klickar på ATP-detonation** i det här diagrammet visas en vy som ser ut så här:

![Utforskaren filtrerad för att endast visa Defender för Detonation-resultat för Office 365](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)

I den här vyn tittar vi nu på data för filer som detonerade av [säkra bifogade filer.](atp-safe-attachments.md) Under diagrammet kan vi se information om specifika e-postmeddelanden som hade bifogade filer som identifierats av säkra bifogade filer.

![Specifik information om e-postmeddelanden med identifierade bifogade filer](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)

Om du markerar ett eller flera objekt aktiveras **menyn** Åtgärder, där det finns flera alternativ att välja bland för de markerade objekten.

![Om du markerar ett objekt aktiveras åtgärdsmenyn](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)

Möjligheten att filtrera med ett klick och navigera till specifika detaljer kan spara mycket tid vid undersökning av hot.

## <a name="queries-and-filters"></a>Frågor och filter

Utforskaren (liksom rapporten över identifieringar i realtid) har flera kraftfulla filter- och frågefunktioner som gör att du kan öka detalj detaljinformationen, till exempel de mest riktade användarna, de mest populära familjerna av skadlig programvara, identifieringsteknik med mera. Varje typ av rapport erbjuder en mängd olika sätt att visa och utforska data.

> [!IMPORTANT]
> Använd inte jokertecken, till exempel en asterisk eller ett frågetecken, i frågefältet för Utforskaren (eller identifieringar i realtid). När du söker i **ämnesfältet** efter e-postmeddelanden utför Utforskaren (eller identifieringar i realtid) delvis matchning och ger resultat som liknar en sökning med jokertecken.
