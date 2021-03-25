---
title: Undersök enheter i listan Defender för Endpoint Defender ATP-enheter
description: Undersök berörda enheter genom att granska aviseringar, nätverksanslutningsinformation, lägga till enhetstaggar och grupper och kontrollera tjänstens hälsa.
keywords: enheter, taggar, grupper, slutpunkt, aviseringar, kö, aviseringar, enhetsnamn, domän, senast sedd, intern IP, aktiva aviseringar, hotkategori, filtrera, sortera, granska aviseringar, nätverk, anslutning, typ, lösenords stjäla, utpressningstrojaner, sårbarhet, hot, låg allvarlighetsgrad, tjänstens hälsa
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8873177f13ebe8d60533877fa9b8dc0be96a66f9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074978"
---
# <a name="investigate-devices-in-the-microsoft-defender-for-endpoint-devices-list"></a>Undersöka enheter i listan Microsoft Defender för slutpunktsenheter

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatemachines-abovefoldlink)

Undersök informationen om en avisering som upphöjts på en specifik enhet för att identifiera andra beteenden eller händelser som kan vara relaterade till aviseringen eller den möjliga omfattningen av intrånget.

> [!NOTE]
> Som en del av undersökningen eller svarsprocessen kan du samla in ett undersökningspaket från en enhet. Gör så här: Samla [in undersökningspaket från enheter](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices).

Du kan klicka på berörda enheter när du ser dem i portalen för att öppna en detaljerad rapport om enheten. Enheter som påverkas identifieras i följande områden:

- [Listan Enheter](investigate-machines.md)
- [Kön Aviseringar](alerts-queue.md)
- [Instrumentpanel för säkerhetsåtgärder](security-operations-dashboard.md)
- Alla enskilda aviseringar
- Alla enskilda vy med filinformation
- En IP-adress eller domäninformationsvy

När du undersöker en specifik enhet visas:

- Enhetsinformation
- Svarsåtgärder
- Flikar (översikt, varningar, tidslinje, säkerhetsrekommendationer, programlager, identifierade säkerhetsproblem, saknade KBS)
- Kort (aktiva aviseringar, inloggade användare, säkerhetsbedömning)

![Bild på enhetsvy](images/specific-device.png)

## <a name="device-details"></a>Enhetsinformation

Avsnittet med enhetsinformation innehåller information som enhetens domän, operativsystem och status. Om det finns ett undersökningspaket tillgängligt på enheten visas en länk som gör att du kan ladda ned paketet.

## <a name="response-actions"></a>Svarsåtgärder

Svarsåtgärder löper högst upp på en specifik enhet och omfattar:

- Hantera taggar
- Identifiera enhet
- Begränsa appkörning
- Kör antivirussökning
- Paket för insamling av undersökning
- Starta Live Response-session
- Initiera en automatiserad undersökning
- Kontakta en hotexpert
- Åtgärdscenter

Du kan vidta åtgärder för svar i Åtgärdscenter, på en viss enhet eller på en viss filsida.

Mer information om hur du vidta åtgärder på en enhet finns i [Vidta svarsåtgärder på en enhet.](respond-machine-alerts.md)

Mer information finns i Undersöka [användarenheter.](investigate-user.md)

## <a name="tabs"></a>Flikar

Flikarna ger relevant information om säkerhet och skydd mot hot som är relaterade till enheten. På varje flik kan du anpassa de kolumner som visas genom att välja **Anpassa kolumner** från fältet ovanför kolumnrubrikerna.

### <a name="overview"></a>Översikt
På **fliken** Översikt visas [korten](#cards) för aktiva aviseringar, inloggade användare och säkerhetsbedömning.

![Bild av översiktsfliken på sidan för enheten](images/overview-device.png)

### <a name="alerts"></a>Varningar

På **fliken** Aviseringar finns en lista med aviseringar som är associerade med enheten. Den här listan är en [](alerts-queue.md)filtrerad version av kön Aviseringar och visar en kort beskrivning av aviseringen, allvarlighetsgraden (hög, medium, låg, information), status i kön (ny, pågående, löst), klassificering (inte inställd, falsk avisering, verklig varning), undersökningstillstånd, kategori av avisering, vem som adresserar aviseringen och den senaste aktiviteten. Du kan också filtrera aviseringarna.

![Bild på aviseringar relaterade till enheten](images/alerts-device.png)

När cirkelikonen till vänster om en avisering är markerad visas en utfällsymbol. Från den här panelen kan du hantera aviseringen och visa mer information, till exempel incidentnummer och relaterade enheter. Du kan välja flera aviseringar åt gången.

Om du vill se en helsida med en avisering som innehåller incidentdiagram och processträd väljer du aviseringens rubrik.

### <a name="timeline"></a>Tidslinje

På **fliken** Tidslinje visas en kronologisk vy över händelserna och tillhörande aviseringar som har observerats på enheten. Det kan hjälpa dig korrelera händelser, filer och IP-adresser i relation till enheten.

På tidslinjen kan du även selektivt granska nedåt i händelser som inträffat under en viss tidsperiod. Du kan visa tidssekvensen av händelser som inträffat på en enhet under en viss tidsperiod. Om du vill ha mer kontroll över vyn kan du filtrera efter händelsegrupper eller anpassa kolumnerna.

>[!NOTE]
> För att brandväggshändelser ska visas måste du aktivera granskningsprincipen i Anslutning till [granskningsfiltreringsplattform.](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-filtering-platform-connection)
>Brandväggen omfattar följande händelser
>
>- [5025 –](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5025) brandväggstjänsten har stoppats
>- [5031](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5031) – programmet kan inte acceptera inkommande anslutningar i nätverket
>- [5157](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5157) – blockerad anslutning

![Bild av tidslinjen på enheten med händelser](images/timeline-device.png)

Några av funktionerna omfattar:

- Söka efter specifika händelser
  - Använd sökfältet för att söka efter specifika tidslinjehändelser.
- Filtrera händelser från ett visst datum
  - Välj kalenderikonen uppe till vänster i tabellen om du vill visa händelser under den senaste dagen, veckan, 30 dagar eller det anpassade intervallet. Som standard är enhetens tidslinje inställd på att visa händelser från de senaste 30 dagarna.
  - Använd tidslinjen för att hoppa till en viss tidpunkt genom att markera avsnittet. Pilarna på tidslinjens pinpoint för automatiserade undersökningar
- Exportera detaljerade tidslinjehändelser för enheter
  - Exportera enhetens tidslinje för det aktuella datumet eller ett angivet datumintervall upp till sju dagar.

Mer information om vissa händelser finns i **avsnittet Ytterligare information.** Den här informationen varierar beroende på typen av händelse, till exempel: 

- Finns av Application Guard – webbläsarhändelsen begränsades av en isolerad behållare
- Aktiva hot upptäcktes – hotidentifieringen inträffade medan hoten kördes
- Åtgärd lyckades inte – ett försök att åtgärda det identifierade hotet anropades men misslyckades
- Åtgärd lyckades – det identifierade hotet har stoppats och åtgärdats
- Varning som förbikopplats av användaren – Windows Defender SmartScreen-varningen avvisades och åsidosättdes av en användare
- Misstänkt skript har upptäckts – ett skript som kan vara skadligt hittades när det kördes
- Aviseringskategorin – om händelsen ledde till en avisering genereras aviseringskategorin ("T.ex. aviseringsrörelse")

#### <a name="event-details"></a>Händelseinformation
Välj en händelse om du vill visa relevant information om händelsen. En panel visas för att visa allmän händelseinformation. När tillämpliga data är tillgängliga visas även ett diagram som visar relaterade enheter och deras relationer.

Om du vill kontrollera händelsen ytterligare och relaterade händelser kan du snabbt köra en [avancerad fråga om sökning](advanced-hunting-overview.md) genom att välja Sök efter relaterade **händelser.** Frågan returnerar den valda händelsen och listan med andra händelser som inträffade samtidigt på samma slutpunkt.

![Bild på panelen med händelseinformation](images/event-details.png)

### <a name="security-recommendations"></a>Säkerhetsrekommendationer

**Säkerhetsrekommendationer** genereras från Microsoft Defender för Endpoints hot för [& Sårbarhetshantering.](tvm-dashboard-insights.md) Om du väljer en rekommendation visas en panel där du kan se relevant information, till exempel en beskrivning av rekommendationen och potentiella risker som är förknippade med att inte anta den. Mer [information finns i Säkerhetsrekommendationer.](tvm-security-recommendation.md)

![Bild av fliken säkerhetsrekommendationer](images/security-recommendations-device.png)

### <a name="software-inventory"></a>Inventering av programvara

På **fliken För inventering** av programvara kan du visa programvara på enheten och se eventuella hot eller svagheter. Om du markerar namnet på programvaran kommer du till sidan med programvaruinformation där du kan se säkerhetsrekommendationer, identifierade säkerhetsproblem, installerade enheter och versionsdistribution. Se [Inventering av programvara](tvm-software-inventory.md) för mer information

![Bild på fliken för programvaruinventering](images/software-inventory-device.png)

### <a name="discovered-vulnerabilities"></a>Upptäckta säkerhetsproblem

På **fliken Identifierade säkerhetsproblem** visas namn, allvarlighetsgrad och information om hot om identifierade säkerhetsproblem på enheten. Om du väljer specifika säkerhetsproblem visas en beskrivning och information.

![Fliken upptäckta säkerhetsproblem](images/discovered-vulnerabilities-device.png)

### <a name="missing-kbs"></a>Saknade KBs
På **fliken saknade KB** visas de säkerhetsuppdateringar som saknas för enheten.

![Bild på fliken kbs som saknas](images/missing-kbs-device.png)

## <a name="cards"></a>Kort

### <a name="active-alerts"></a>Aktiva aviseringar

**Kortet Azure Advanced Threat Protection** visar en översikt över aviseringar relaterade till enheten och deras risknivå, om du har aktiverat Azure ATP-funktionen och det finns aktiva aviseringar. Mer information finns i den granskande detaljgranskningen "Aviseringar".

![Bild på aktiva varningskort](images/risk-level-small.png)

>[!NOTE]
>Du måste aktivera integreringen på både Azure ATP och Defender för Endpoint om du vill använda den här funktionen. I Defender för Slutpunkt kan du aktivera den här funktionen i avancerade funktioner. Mer information om hur du aktiverar avancerade funktioner finns i [Aktivera avancerade funktioner.](advanced-features.md)

### <a name="logged-on-users"></a>Inloggade användare

Kortet **Inloggade användare visar** hur många användare som har loggat in de senaste 30 dagarna, tillsammans med de mest och minst vanliga användarna. Om du väljer länken "Visa alla användare" öppnas informationsfönstret med information som användartyp, inloggningstyp och när användaren sågs för första och sista gången. Mer information finns i Undersöka [användarenheter.](investigate-user.md)

![Bild av fönstret med användarinformation](images/logged-on-users.png)

### <a name="security-assessments"></a>Säkerhetsutvärderingar

Kortet **för säkerhetsutvärderingar** visar den totala exponeringsnivån, säkerhetsrekommendationer, installerad programvara och identifierade säkerhetsproblem. Exponeringsnivån för en enhet bestäms av den kumulativa effekten av de väntande säkerhetsrekommendationerna.

![Bild på kortet med säkerhetsutvärderingar](images/security-assessments.png)

## <a name="related-topics"></a>Relaterade ämnen

- [Visa och ordna kön Microsoft Defender för slutpunktsaviseringar](alerts-queue.md)
- [Hantera Microsoft Defender för slutpunktsaviseringar](manage-alerts.md)
- [Undersöka Microsoft Defender för slutpunktsaviseringar](investigate-alerts.md)
- [Undersöka en fil som är kopplad till en Defender för slutpunktsavisering](investigate-files.md)
- [Undersöka en IP-adress som är kopplad till en Defender för Slutpunktsavisering](investigate-ip.md)
- [Undersöka en domän som är kopplad till en Defender för slutpunktsavisering](investigate-domain.md)
- [Undersöka ett användarkonto i Defender för Slutpunkt](investigate-user.md)
- [Säkerhetsrekommendationer](tvm-security-recommendation.md)
- [Inventering av programvara](tvm-software-inventory.md)
