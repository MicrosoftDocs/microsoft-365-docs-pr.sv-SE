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
description: Under och efter en automatiserad undersökning i Microsoft 365 kan du visa resultat och viktiga resultat.
ms.date: 01/29/2021
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8bf18a9fb80805581a1439b3965a664fd0868248
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207116"
---
# <a name="details-and-results-of-an-automated-investigation-in-microsoft-365"></a>Information och resultat från en automatiserad undersökning i Microsoft 365

**Gäller för**
- [Microsoft Defender för Office 365 abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

När en [automatiserad undersökning](office-365-air.md) sker i Microsoft Defender för [Office 365](defender-for-office-365.md)finns information om undersökningen tillgänglig under och efter den automatiska undersökningen. Om du har nödvändiga behörigheter kan du visa den informationen i Säkerhetscenter för Microsoft 365. Undersökningsinformation ger dig aktuell status och möjlighet att godkänna eventuella väntande åtgärder.

> [!TIP]
> Titta på den nya sidan för enhetlig undersökning i Säkerhetscenter för Microsoft 365. Mer information finns i [(NYTT!) Sida för enhetlig undersökning](../defender/m365d-autoir-results.md#new-unified-investigation-page).

## <a name="investigation-status"></a>Undersökningsstatus

Undersökningsstatusen anger förloppet för analysen och åtgärderna. När undersökningen körs ändras statusen för att ange om hot hittades och om åtgärder har godkänts.

|Status|Beskrivning|
|:---|:---|
|**Startar**|Undersökningen har utlösts och väntar på att starta.|
|**Körs**|Undersökningsprocessen har startat och pågår. Det här tillståndet inträffar även [när väntande åtgärder](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions) har godkänts.|
|**Inga hot hittades**|Undersökningen har slutförts och inga hot (användarkonto, e-postmeddelande, URL eller fil) har identifierats. <p> **TIPS:** Om du misstänker att något har missats (t.ex. falskt negativa) kan du vidta åtgärder med hjälp av [Hotutforskaren.](threat-explorer.md)|
|**Hot hittades**|Den automatiska undersökningen hittade problem, men det finns inga specifika åtgärdsåtgärder för att lösa problemen. <p> Statusen **Hot hittades** kan uppstå när någon typ av användaraktivitet har identifierats men inga rensningsåtgärder är tillgängliga. Några exempel är några av följande användaraktiviteter: <br/>- En [DLP-händelse (skydd](../../compliance/data-loss-prevention-policies.md) mot dataförlust)<br/>- Ett e-postmeddelande som skickar avvikande avvikelse<br/>- Skickad skadlig programvara<br/>- Skickad phish <p> Undersökningen hittade inga skadliga URL:er, filer eller e-postmeddelanden för att åtgärda och ingen postlådeaktivitet för att åtgärda, till exempel inaktivera regler för vidarebefordran eller delegering. <p> **TIPS:** Om du misstänker att något har missats (t.ex. falskt negativa) kan du undersöka och vidta åtgärder med hjälp av [Hotutforskaren.](threat-explorer.md)|
|**Avslutas av system**|Undersökningen har stoppats. En undersökning kan avbrytas av flera orsaker: <br/>- Undersökningens väntande åtgärder har upphört att gälla. Väntande åtgärder tar slut när du väntar på godkännande för en vecka.<br/>- Det finns för många åtgärder. Om till exempel för många användare klickar på skadliga URL-adresser kan det överskrida undersökningens möjlighet att köra alla analysverktyg, så undersökningen pausar.<p> **TIPS:** Om en undersökning stannar innan åtgärder vidtas kan du använda [Hotutforskaren](threat-explorer.md) för att hitta och åtgärda hot.|
|**Väntande åtgärd**|Undersökningen har hittat ett hot, till exempel en skadlig e-post, en skadlig URL-adress eller en riskabel postlåda samt en åtgärd för att åtgärda att hoten [väntar på godkännande.](air-review-approve-pending-completed-actions.md) <p> Statusen **Väntande** åtgärd utlöses när ett hot med en motsvarande åtgärd hittas. Listan med väntande åtgärder kan dock öka i och med att en undersökning körs. Visa undersökningsinformation för att se om andra objekt fortfarande är slutförda.|
|**Åtgärdat**|Undersökningen slutfördes och alla åtgärder godkänts (antecknas som helt åtgärdade). <p> **Obs!** Godkända åtgärdsåtgärder kan ha fel som hindrar att åtgärderna vidtas. Oavsett om åtgärdsåtgärder slutförs ändras inte undersökningsstatusen. Visa undersökningsinformation.|
|**Delvis åtgärdat**|Undersökningen resulterade i åtgärder och vissa godkänts och slutförts. Andra åtgärder väntar [fortfarande.](air-review-approve-pending-completed-actions.md)|
|**Misslyckades**|Minst en undersökningsanalys körde ett problem där det inte gick att slutföra korrekt. <p> **OBS!** Om en undersökning misslyckas efter att åtgärdsåtgärder godkänts kan det hända att åtgärdsåtgärderna fortfarande har godkänts. Visa undersökningsuppgifterna. |
|**I kö efter begränsning**|En undersökning görs i en kö. När andra undersökningar är klara påbörjas undersökningar i kö. Begränsning hjälper till att undvika dålig tjänstprestanda.  <p> **TIPS:** Väntande åtgärder kan begränsa hur många nya undersökningar som kan köras. Godkänn [(eller avvisa) väntande åtgärder](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions).|
|**Avslutas av begränsning**|Om en undersökning hålls i kön för länge stoppas den. <p> **TIPS:** Du kan [starta en undersökning från Hotutforskaren.](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)|
|

## <a name="view-details-of-an-investigation"></a>Visa information om en undersökning

1. Gå till Säkerhetscenter för Microsoft 365 ( <https://security.microsoft.com> ) och logga in.
2. Välj Åtgärdscenter i **navigeringsfönstret.**
3. Välj en **åtgärd på flikarna** **Väntande** eller Historik. Den utfällna rutan öppnas.
4. Välj Öppna undersökningssida i den **utfällfällade fönsterrutan**. 
5. Använd de olika flikarna om du vill veta mer om undersökningen.

## <a name="view-details-about-an-alert-related-to-an-investigation"></a>Visa information om en avisering relaterad till en undersökning

Vissa typer av aviseringar utlöser automatisk undersökning i Microsoft 365. Mer information finns i [aviseringsprinciper som utlöser automatiska undersökningar.](office-365-air.md#which-alert-policies-trigger-automated-investigations)

1. Gå till Säkerhetscenter för Microsoft 365 ( <https://security.microsoft.com> ) och logga in.
2. Välj Åtgärdscenter i **navigeringsfönstret.**
3. Välj en **åtgärd på flikarna** **Väntande** eller Historik. Den utfällna rutan öppnas.
4. Välj Öppna undersökningssida i den **utfällfällade fönsterrutan**. 
5. Välj fliken **Aviseringar** om du vill visa en lista över alla aviseringar som är associerade med undersökningen.
6. Markera ett objekt i listan för att öppna det utfällade fönstret. Där kan du visa mer information om aviseringen.

## <a name="keep-the-following-points-in-mind"></a>Tänk på följande

- E-posträkning beräknas vid tiden för undersökningen och vissa antal beräknas om när du öppnar utfällpunkter för undersökning (baserat på en underliggande fråga).

- E-postantalen som visas för  e-postkluster på fliken E-post och värdet för e-postantal som visas på den utfällna bilden i ett kluster beräknas vid undersökning, och ändras inte.

- Antalet e-postmeddelanden som visas  längst ned på fliken E-post i e-postkluster som visas och antalet e-postmeddelanden som visas i Utforskaren speglar e-postmeddelanden som tagits emot efter undersökningens första analys.

  Ett e-postkluster som visar den ursprungliga mängden 10 e-postmeddelanden skulle alltså visa en e-postlista på totalt 15 när ytterligare fem e-postmeddelanden kommer mellan undersökningsanalysfasen och när administratören granskar undersökningen. På samma sätt kan gamla undersökningar börja visa högre antal än vad Explorer-frågor visar, eftersom data i Microsoft Defender för Office 365 abonnemang 2 förfaller efter sju dagar för provperioder och efter 30 dagar för betalda licenser.

  Både antal historiska och aktuella antal i olika vyer utförs för att ange e-post påverkan vid undersökningsstiden och den aktuella påverkan fram till den tidpunkt då reparationen körs.

- Inom ramen för e-post kan det hända att du ser en volymnormnormy för hotytan inom ramen för undersökningen. En volymnorma tyder på en ökning av liknande e-postmeddelanden kring undersökningens händelsetid jämfört med tidigare tidsramar. En insamling av e-posttrafik tillsammans med vissa egenskaper (till exempel ämnes- och avsändardomän, body similarity och avsändar-IP) är typiskt för starten av e-postkampanjer eller attacker. Mass-, skräppost- och legitima e-postkampanjer delar emellertid ofta dessa egenskaper.

- Volymmakar representerar ett potentiellt hot och kan därmed vara mindre allvarligt jämfört med skadlig kod eller nätfingrshot som identifieras med hjälp av antivirusmotorer, detonation eller skadligt rykte.

- Du behöver inte godkänna alla åtgärder. Om du inte godkänner den rekommenderade åtgärden eller din organisation inte väljer  vissa typer av åtgärder kan du välja att Ignorera åtgärderna eller helt enkelt ignorera dem och inte vidta någon åtgärd.

- Om du godkänner och/eller ignorerar alla åtgärder kan undersökningen stängas helt (status åtgärdas), medan vissa åtgärder inte är slutförda eftersom undersökningsstatusen ändras till ett delvis åtgärdat tillstånd.

## <a name="next-steps"></a>Nästa steg

- [Granska och godkänna väntande åtgärder](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)
