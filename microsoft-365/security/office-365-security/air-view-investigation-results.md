---
title: Visa resultatet av en automatiserad undersökning i Microsoft 365
keywords: AIR, autoIR, ATP, automatiserad, undersökning, åtgärd, åtgärder
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
description: Du kan visa resultat och viktiga resultat under och efter en automatiserad undersökning i Microsoft 365.
ms.date: 01/29/2021
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7ebfa8bb7060b633bdb48c77bc661477ad3e201b
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142519"
---
# <a name="details-and-results-of-an-automated-investigation-in-microsoft-365"></a>Information och resultat från en automatiserad undersökning i Microsoft 365

När en [automatiserad](office-365-air.md) undersökning sker i Microsoft Defender för [Office 365](office-365-atp.md)är information om undersökningen tillgänglig under och efter den automatiska undersökningsprocessen. Om du har den behörighet som krävs kan du visa den informationen i säkerhetscentret. Undersökningsinformation ger dig aktuell status och möjlighet att godkänna eventuella väntande åtgärder.

> [!TIP]
> Ta en titta på den nya, enhetliga undersökningssidan i Säkerhetscenter för Microsoft 365. Mer information finns i [(NY!) Sida för enhetlig undersökning.](../mtp/mtp-autoir-results.md#new-unified-investigation-page)

## <a name="investigation-status"></a>Undersökningsstatus

Undersökningsstatusen anger förloppet för analysen och åtgärderna. När undersökningen körs ändras statusen för att ange om hot hittades och om åtgärder har godkänts.

|Status|Beskrivning|
|:---|:---|
|**Startar**|Undersökningen har utlösts och väntar på att starta.|
|**Körs**|Undersökningen har startat och pågår. Den här statusen inträffar också [när väntande åtgärder](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions) har godkänts.|
|**Inga hot hittades**|Undersökningen har slutförts och inga hot har identifierats (användarkonto, e-postmeddelande, URL eller fil). <p> **TIPS:** Om du misstänker att något har missats (till exempel falskt negativt) kan du vidta åtgärder med hjälp av [Hotutforskaren.](threat-explorer.md)|
|**Hot hittades**|Den automatiska undersökningen hittade problem, men det finns inga specifika åtgärder för att lösa problemen. <p> Statusen för de hot som påträffades kan uppstå när någon typ av användaraktivitet har **identifierats** men inga rensningsåtgärder är tillgängliga. Några exempel är några av följande användaraktiviteter: <br/>- En [DLP-händelse (Data Loss Prevention)](https://docs.microsoft.com/Microsoft-365/compliance/data-loss-prevention-policies)<br/>- Ett e-postmeddelande som skickar avvikelser<br/>- Skickad skadlig programvara<br/>- Skickad phish <p> Undersökningen hittade inga skadliga URL:er, filer eller e-postmeddelanden för att åtgärda och ingen postlådeaktivitet att åtgärda, till exempel att stänga av regler för vidarebefordran eller delegering. <p> **TIPS:** Om du misstänker att något har missats (till exempel falskt negativt) kan du undersöka och vidta åtgärder med hjälp av [Hotutforskaren.](threat-explorer.md)|
|**Avslutas av systemet**|Undersökningen har stoppats. En undersökning kan avbrytas av flera orsaker: <br/>- Undersökningens väntande åtgärder har upphört att gälla. Väntande åtgärder tar slut efter att du väntar på godkännande i en vecka.<br/>- Det finns för många åtgärder. Om det till exempel finns för många användare som klickar på skadliga URL:er kan det överskrida undersökningens möjlighet att köra alla analysverktyg, så undersökningen pausar.<p> **TIPS:** Om en undersökning stannar innan åtgärder vidtas kan du använda [Hotutforskaren](threat-explorer.md) för att hitta och hantera hot.|
|**Väntande åtgärd**|Undersökningen har hittat ett hot, till exempel en skadlig e-post, en skadlig URL eller en riskabel postlåda och en åtgärd för att åtgärda att hot väntar [på godkännande.](air-review-approve-pending-completed-actions.md) <p> Statusen **väntande** åtgärd utlöses när ett hot med en motsvarande åtgärd hittas. Listan med väntande åtgärder kan dock öka när en undersökning körs. Visa undersökningsinformation för att se om andra objekt fortfarande är väntande.|
|**Åtgärdat**|Undersökningen slutfördes och alla åtgärder har godkänts (antecknas som helt åtgärdade). <p> **OBS!** Godkända åtgärdsåtgärder kan ha fel som hindrar att åtgärder vidtas. Oavsett om åtgärdsåtgärderna slutförs ändras inte undersökningsstatusen. Visa undersökningsinformation.|
|**Delvis åtgärdat**|Undersökningen resulterade i åtgärder, och vissa har godkänts och slutförts. Andra åtgärder väntar [fortfarande.](air-review-approve-pending-completed-actions.md)|
|**Misslyckades**|Minst en undersökningsanalys har stött på ett problem där det inte kunde slutföras korrekt. <p> **OBS!** Om en undersökning misslyckas efter att åtgärder har godkänts kan åtgärden fortfarande ha lyckats. Visa undersökningsinformationen. |
|**I kö efter begränsning**|En undersökning hålls i en kö. När andra undersökningar är slutförda påbörjas köade undersökningar. Begränsning hjälper till att undvika dålig tjänstprestanda.  <p> **TIPS:** Väntande åtgärder kan begränsa hur många nya undersökningar som kan köras. Godkänn [(eller avvisa) väntande åtgärder.](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)|
|**Avslutas av begränsning**|Om en undersökning hålls i kön för lång avbryts den. <p> **TIPS:** Du kan [starta en undersökning från Hotutforskaren.](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)|
|

## <a name="view-details-of-an-investigation"></a>Visa information om en undersökning

1. Gå till Microsoft 365 [https://security.microsoft.com](https://security.microsoft.com) säkerhetscenter) och logga in.
2. Välj Åtgärdscenter i **navigeringsfönstret.**
3. Välj en åtgärd **på flikarna** **Väntande** eller Historik. Det utfällfönster som visas.
4. Välj öppna undersökningssida i det **utfällofönstret.** 
5. Använd flikarna för att få mer information om undersökningen.

## <a name="view-details-about-an-alert-related-to-an-investigation"></a>Visa information om en varning relaterad till en undersökning

Vissa typer av aviseringar utlöser automatisk undersökning i Microsoft 365. Mer information finns i [aviseringsprinciper som utlöser automatiserade undersökningar.](office-365-air.md#which-alert-policies-trigger-automated-investigations)

1. Gå till Microsoft 365 [https://security.microsoft.com](https://security.microsoft.com) säkerhetscenter) och logga in.
2. Välj Åtgärdscenter i **navigeringsfönstret.**
3. Välj en åtgärd **på flikarna** **Väntande** eller Historik. Det utfällfönster som visas.
4. Välj öppna undersökningssida i det **utfällade fönstret.** 
5. Välj fliken **Aviseringar** om du vill visa en lista över alla aviseringar som är associerade med undersökningen.
6. Markera ett objekt i listan för att öppna det utfällna fönstret. Där kan du visa mer information om aviseringen.

## <a name="keep-the-following-points-in-mind"></a>Tänk på följande punkter

- E-postantal beräknas vid tidpunkten för undersökningen och vissa antal beräknas om när du öppnar en utfällande undersökning (baserat på en underliggande fråga).

- Antalet e-postmeddelanden som visas för  e-postkluster på fliken E-post och värdet för antal e-postmeddelanden som visas på den utfällvärda gruppen beräknas vid tidpunkten för undersökningen och ändras inte.

- Antalet e-postmeddelanden som visas  längst ned på fliken E-post i e-postkluster, och antalet e-postmeddelanden som visas i Utforskaren speglar e-postmeddelanden som tagits emot efter undersökningens första analys.

  Ett e-postkluster som visar det ursprungliga antalet 10 e-postmeddelanden skulle därmed visa en sammanlagd e-postlista på 15 när ytterligare fem e-postmeddelanden kommer mellan undersökningsanalysfasen och när administratören granskar undersökningen. På samma sätt kan gamla undersökningar börja visa högre antal än vad frågorna i Utforskaren visar, eftersom data i Microsoft Defender för Office 365 abonnemang 2 löper ut efter sju dagar för försök och efter 30 dagar för betalda licenser.

  Både antal historiska och aktuella antal i olika vyer utförs för att ange e-post påverkan vid undersökningstiden och den aktuella påverkan fram till den tid som åtgärdats körs.

- När det gäller e-post kan du se en volymnormnormy hotyta som en del av undersökningen. En volymnorma anger en ökning av liknande e-postmeddelanden kring undersökningshändelsetiden jämfört med tidigare tidsramar. En insamling av e-posttrafik tillsammans med vissa egenskaper (till exempel ämnes- och avsändardomän, likhet mellan brödtext och avsändar-IP) är typiskt för starten av e-postkampanjer eller attacker. Mass-, skräppost- och legitima e-postkampanjer har däremot ofta dessa egenskaper.

- Volymkontrollknapparna är ett potentiellt hot och kan därmed vara mindre allvarliga jämfört med skadlig programvara eller phish-hot som identifieras med hjälp av antivirusmotorer, detonation eller skadligt rykte.

- Du behöver inte godkänna alla åtgärder. Om du inte godkänner den rekommenderade åtgärden eller din organisation inte väljer  vissa typer av åtgärder kan du välja att Avvisa åtgärderna eller helt enkelt ignorera dem och inte vidta någon åtgärd.

- Om du godkänner och/eller ignorerar alla åtgärder kan undersökningen stängas helt (status åtgärdas), medan vissa åtgärder blir ofullständiga resultat i om undersökningens status ändras till ett delvis åtgärdat tillstånd.

## <a name="next-steps"></a>Nästa steg

- [Granska och godkänna väntande åtgärder](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)
