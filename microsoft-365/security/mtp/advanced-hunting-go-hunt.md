---
title: Få relevant information om en entitet med go-leta
description: Lär dig hur du använder sökverktyget för att snabbt söka efter relevant information om en enhet eller händelse med avancerad sökning.
keywords: avancerad sökning, incident, pivot, entitet, sök, relevanta händelser, hotsökning, sökning, fråga, telemetri, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 9e707fe8b3dff40d0698630cd0592b297042e5fb
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929517"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a>Snabbt jaga efter entitets- eller händelseinformation med go-jagning

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Med *sökåtgärden* Go kan du snabbt undersöka händelser och olika enhetstyper med hjälp av kraftfulla [frågebaserade avancerade](advanced-hunting-overview.md) sökfunktioner. Den här åtgärden kör automatiskt en avancerad sökningsfråga för att hitta relevant information om den valda händelsen eller enheten.

Åtgärden *gå-och-leta* är tillgänglig i olika delar av säkerhetscentret när händelse- eller entitetsinformation visas. Du kan till exempel använda *gå-jaga* från följande avsnitt:

- På [incidentsidan kan](investigate-incidents.md#incident-overview)du granska information om användare, enheter och många andra enheter som är kopplade till en incident. När du väljer en enhet får du ytterligare information samt olika åtgärder du kan utföra på den personen. I exemplet nedan är en postlåda markerad och visar information om postlådan samt alternativet att leta efter mer information om postlådan.

    ![Bild som visar information om postlådan med alternativet gå-och-leta](../../media/mtp-ah/go-hunt-email.png)

- På incidentsidan kan du också komma åt en lista med enheter under bevisfliken. Om du väljer en av dessa enheter kan du snabbt jaga information om enheten.

    ![Bild som visar vald fil med sökalternativet Gå på fliken Bevis](../../media/mtp-ah/go-hunt-evidence-file.png)


- När du visar tidslinjen för en enhet kan du välja en händelse på tidslinjen för att visa ytterligare information om händelsen. När en händelse har valts får du möjlighet att jaga andra relevanta händelser i avancerad sökning.

    ![Bild som visar händelseinformation med alternativet gå-och-leta](../../media/mtp-ah/go-hunt-event.png)

Om **du väljer** **Söksök eller Sök efter relaterade** händelser passeras olika frågor, beroende på om du har valt en enhet eller en händelse.

## <a name="query-for-entity-information"></a>Fråga för entitetsinformation
När du *använder sökfråga* efter information om en användare, enhet eller någon annan typ av entitet genomsöks alla relevanta schematabeller efter händelser som innefattar den enheten. För att resultatet ska kunna hanteras begränsades frågan till ungefär samma tidsperiod som den tidigaste aktiviteten under de senaste 30 dagarna som innefattar enheten och som är associerad med händelsen.

Här är ett exempel på sökfrågan för en enhet:

```kusto
let selectedTimestamp = datetime(2020-06-02T02:06:47.1167157Z);
let deviceName = "fv-az770.example.com";
let deviceId = "device-guid";
search in (DeviceLogonEvents, DeviceProcessEvents, DeviceNetworkEvents, DeviceFileEvents, DeviceRegistryEvents, DeviceImageLoadEvents, DeviceEvents, DeviceImageLoadEvents, IdentityLogonEvents, IdentityQueryEvents)
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
and DeviceName == deviceName
// or RemoteDeviceName == deviceName
// or DeviceId == deviceId
| take 100
```
### <a name="supported-entity-types"></a>Entitetstyper som stöds
Du kan använda *gåsök när* du har valt någon av dessa entitetstyper:

- Filer
- E-postmeddelanden
- E-postkluster
- Postlådor
- Användare
- Enheter
- IP-adresser
- URL:er

## <a name="query-for-event-information"></a>Fråga för händelseinformation
När du *använder sökfråga* efter information om en tidslinjehändelse söker frågan igenom alla relevanta schematabeller efter andra händelser vid den valda händelsens tidpunkt. I följande fråga visas till exempel händelser i olika schematabeller som inträffade under samma tidsperiod på samma enhet:

```kusto
// List relevant events 30 minutes before and after selected LogonAttempted event
let selectedEventTimestamp = datetime(2020-06-04T01:29:09.2496688Z);
search in (DeviceFileEvents, DeviceProcessEvents, DeviceEvents, DeviceRegistryEvents, DeviceNetworkEvents, DeviceImageLoadEvents, DeviceLogonEvents)
    Timestamp between ((selectedEventTimestamp - 30m) .. (selectedEventTimestamp + 30m))
    and DeviceId == "079ecf9c5798d249128817619606c1c47369eb3e"
| sort by Timestamp desc
| extend Relevance = iff(Timestamp == selectedEventTimestamp, "Selected event", iff(Timestamp < selectedEventTimestamp, "Earlier event", "Later event"))
| project-reorder Relevance
```

## <a name="adjust-the-query"></a>Justera frågan
Om du har viss kunskap [om frågespråket](advanced-hunting-query-language.md)kan du justera frågan efter dina önskemål. Du kan till exempel justera den här raden, som bestämmer storleken på ett tidsfönster:

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

Förutom att ändra frågan för att få mer relevanta resultat kan du också:
- [Visa resultatet som diagram](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [Skapa en anpassad identifieringsregel](custom-detection-rules.md)

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Arbeta med frågeresultat](advanced-hunting-query-results.md)
- [Anpassade identifieringsregler](custom-detection-rules.md)
