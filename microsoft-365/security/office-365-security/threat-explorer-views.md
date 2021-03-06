---
title: Vyer i Hotutforskaren och identifiering i realtid
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
description: Läs mer om hur du använder Threat Explorer och rapporten om identifieringar i realtid för att undersöka och hantera hot i Microsoft 365 Defender-portalen.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1c79cc717a2dbe345627f99830590c674fa02f09
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929668"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a>Vyer i Hotutforskaren och identifiering i realtid

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)


![Hotutforskaren](../../media/explorer.png)

[Hotutforskaren](threat-explorer.md) (och rapporten om identifiering i realtid) är ett kraftfullt, när realtidsverktyg som hjälper säkerhetsoperationsgrupper att undersöka och svara på hot i Microsoft 365 Defender-portalen. Utforskaren (och rapporten om identifieringar i realtid) visar information om misstänkt skadlig kod och nätsegeni i e-post och filer i Office 365, liksom andra säkerhetshot och risker för organisationen.

- Om du har [Microsoft Defender Office 365](defender-for-office-365.md) abonnemang 2 har du Utforskaren.
- Om du har Microsoft Defender Office 365 abonnemang 1 kan du göra identifieringar i realtid.

När du först öppnar Utforskaren (eller rapporten över identifieringar i realtid) visar standardvyn identifieringar av skadlig kod för e-post under de senaste 7 dagarna. Den här rapporten kan också visa Microsoft Defender för Office 365 identifieringar, till exempel skadliga URL-adresser som identifieras av [Valv-länkar](safe-links.md)och skadliga filer som identifieras [av Valv bifogade filer.](safe-attachments.md) Den här rapporten kan ändras så att den visar data för de senaste 30 dagarna (med en Microsoft Defender för Office 365 P2-betald prenumeration). Utvärderingsprenumerationer kommer endast att innehålla data för de senaste sju dagarna.

****

|Prenumeration|Utility|Datadagar|
|---|---|---|
|Utvärderingsversion av Microsoft Defender Office 365 P1|Identifiering i realtid|7|
|Microsoft Defender för Office 365 P1 betalad|Identifiering i realtid|30|
|Betalda tester av Defender Office 365 P1 för utvärderingsversion av Microsoft Defender Office 365 P2|Hotutforskaren|7|
|Utvärderingsversion av Microsoft Defender Office 365 P2|Hotutforskaren|7|
|Microsoft Defender för Office 365 P2 betalad|Hotutforskaren|30|
|

> [!NOTE]
> Vi kommer snart att utöka datalagrings- och sökgränsen för databevarande i Utforskaren (och realtidsidentifiering) för utvärderingsklienter från 7 till 30 dagar. Den här ändringen spåras som en del av översiktsobjektet no. 70544 och håller för närvarande på att distribueras.

Använd **Visa-menyn** för att ändra vilken information som visas. Verktygstips hjälper dig att avgöra vilken vy du ska använda.

![Menyn För att visa hot i Utforskaren](../../media/all-email.png)

När du har valt en vy kan du använda filter och konfigurera frågor för vidare analys. I följande avsnitt ges en kort översikt över de olika vyerna som är tillgängliga i Utforskaren (eller identifieringar i realtid).

## <a name="email--malware"></a>E-> skadlig programvara

Om du vill visa den här rapporten i Utforskaren (eller identifiering i realtid) väljer du **Visa skadlig programvara** för \> **e-post.** \>  I den här vyn visas information om e-postmeddelanden som identifierats som innehåller skadlig programvara.

![Visa data om e-post som identifieras som skadlig programvara](../../media/detection-technology.png)

Klicka **på Avsändare** så att listan med visningsalternativ öppnas. Använd den här listan för att visa data efter avsändare, mottagare, avsändardomän, ämne, identifieringsteknik, skyddsstatus med mera.

Om du till exempel vill se vilka åtgärder som har vidtagits för identifierade e-postmeddelanden väljer du **Skyddsstatus** i listan. Välj ett alternativ och klicka sedan på knappen Uppdatera för att använda filtret i rapporten.

![Alternativ för status för skydd mot hot i Utforskaren](../../media/ThreatExplorerProtectionStatusOptions.png)

Under diagrammet kan du visa mer information om specifika meddelanden. När du markerar ett objekt i listan öppnas ett utfällt fönster där du kan läsa mer om det markerade objektet.

![Hotutforskaren med öppnad utfällning](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a>E-> Phish

Om du vill visa den här rapporten i Utforskaren (eller identifieringar i realtid) väljer du **Visa** \> **e-post** \> **phish**. I den här vyn visas e-postmeddelanden som identifieras som nätfiskeförsök.

![Visa data om e-post som identifierats som nätfiskeförsök](../../media/phish.png)

Klicka **på Avsändare** så att listan med visningsalternativ öppnas. Använd den här listan för att visa data efter avsändare, mottagare, avsändardomän, avsändar-IP, URL-domän, klicka på bedömning med mera.

Om du till exempel vill se vilka åtgärder som har vidtagits när  personer klickade på URL-adresser som identifierats som nätfiskeförsök väljer du Klicka på bedömning i listan, väljer ett eller flera alternativ och klickar sedan på knappen Uppdatera.

![Klicka på alternativ för bedömning av phish-rapporten](../../media/click-verdict.png)

Under diagrammet kan du visa mer information om specifika meddelanden, URL-klick, URL:er och e-postursprung.

![URL:er som identifierats som phish i e-postmeddelanden](../../media/ThreatExplorerEmailPhishURLs.png)

När du markerar ett objekt i listan, till exempel en URL som identifierats, öppnas ett utfällt fönster där du kan läsa mer om det markerade objektet.

![Information om en upptäckt URL](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a>Skicka e> postinskick

Om du vill visa den här rapporten i Utforskaren (eller identifiering i realtid) väljer du **Visa e-postinskick.** \>  \>  I den här vyn visas e-post som användare har rapporterat som skräppost, inte skräppost eller nätfiske.

![E-postmeddelanden som rapporterats av användare](../../media/ThreatExplorerEmailUserReportedViewOptions.png)

Klicka **på Avsändare** så att listan med visningsalternativ öppnas. Använd den här listan för att visa information efter avsändare, mottagare, rapporttyp (användarens avgörande om e-postmeddelandet var skräppost, inte skräppost eller nätt syfte) och mycket mer.

Om du till exempel vill visa information om e-postmeddelanden som rapporterats som nätfiskeförsök klickar du på Avsändarrapporttyp , väljer  Phish och klickar \> sedan på knappen Uppdatera.

![Valt phish för Filtret Rapporttyp](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

Under diagrammet kan du visa mer information om specifika e-postmeddelanden, till exempel ämnesraden, avsändarens IP-adress, användaren som rapporterade meddelandet som skräppost, inte skräppost eller nätt syfte med mera.

![Meddelanden som har rapporterats som nätfiskeförsök](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

Markera ett objekt i listan om du vill visa ytterligare information.

## <a name="email--all-email"></a>E-> all e-post

Om du vill visa den här rapporten väljer du Visa e-post **alla** \> **e-postmeddelanden** \> **i Utforskaren.** I de här vyerna visas en vy över all e-postaktivitet, inklusive e-post som identifieras som skadlig på grund av nätfiske eller skadlig kod, samt all icke-skadlig e-post (vanlig e-post, skräppost och massutskick).

> [!NOTE]
> Om du får ett felmeddelande där det står **För mycket data** för att visas lägger du till ett filter och, om det behövs, begränsa det datumintervall du visar.

Om du vill använda ett filter **väljer du Avsändare**, markerar ett objekt i listan och klickar sedan på knappen Uppdatera. I exemplet använde vi **Identifieringsteknik som** ett filter (det finns flera tillgängliga alternativ). Visa information efter avsändare, avsändares domän, mottagare, ämne, filnamn på bifogad fil, skadlig kodfamilj, skyddsstatus (åtgärder som vidtas av dina skyddsfunktioner och principer i Office 365), identifieringsteknik (hur den skadlig programvara upptäcktes) och mycket mer.

![Visa data om identifierad e-post med identifieringsteknik](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)

Under diagrammet kan du visa mer information om specifika e-postmeddelanden, till exempel ämnesraden, mottagare, avsändare, status och så vidare.

## <a name="content--malware"></a>Innehålls > skadlig programvara

Om du vill visa den här rapporten i Utforskaren (eller identifiering i realtid) väljer du **Visa skadlig** \> **programvara för** \> **innehåll.** I den här vyn visas filer som identifierats som skadliga av Microsoft Defender för Office 365 i [SharePoint Online, OneDrive för företag och Microsoft Teams](mdo-for-spo-odb-and-teams.md).

Visa information efter programfamilj, identifieringsteknik (hur den skadlig programvara upptäcktes) och arbetsbelastningen (OneDrive, SharePoint eller Teams).

![Visa data om upptäckt skadlig programvara](../../media/malware-family.png)

Under diagrammet kan du visa mer information om specifika filer, till exempel filnamn på bifogade filer, arbetsbelastning, filstorlek, vem som senast ändrade filen och mycket mer.

## <a name="click-to-filter-capabilities"></a>Klicka-och-filtrera-funktioner

Med Utforskaren (och identifieringar i realtid) kan du använda ett filter med ett klick. Klicka på ett objekt i förklaringen så blir objektet ett filter för rapporten. Anta till exempel att vi tittar på vyn Skadlig programvara i Utforskaren:

![Gå till Utforskaren för hantering av \> hot](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

Om **du klickar på ATP-detonation** i det här diagrammet visas en vy som ser ut så här:

![Utforskaren filtrerad för att endast visa Defender för Office 365 detonationsresultat](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)

I den här vyn tittar vi nu på data för filer som detonerades av Valv [Bifogade filer](safe-attachments.md). Under diagrammet kan du se information om specifika e-postmeddelanden som har bifogade filer som upptäckts av Valv bifogade filer.

![Specifik information om e-postmeddelanden med identifierade bifogade filer](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)

Om du markerar ett eller flera objekt aktiveras **menyn** Åtgärder, där du kan välja mellan flera markerade objekt.

![När du markerar ett objekt aktiveras menyn Åtgärder](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)

Möjligheten att filtrera med ett klick och navigera till specifika detaljer kan spara mycket tid när du undersöker hot.

## <a name="queries-and-filters"></a>Frågor och filter

Utforskaren (liksom rapporten över identifieringar i realtid) har flera kraftfulla filter- och frågefunktioner som gör att du kan öka detaljinformationen, till exempel de mest riktade användarna, de främsta familjerna med skadlig programvara, identifieringsteknik med mera. Varje typ av rapport erbjuder en mängd olika sätt att visa och utforska data.

> [!IMPORTANT]
> Använd inte jokertecken, till exempel asterisk eller frågetecken, i frågefältet för Utforskaren (eller identifieringar i realtid). När du söker i **ämnesfältet** efter e-postmeddelanden utför Utforskaren (eller identifieringar i realtid) delvis matchning och ger resultat som liknar en sökning med jokertecken.
