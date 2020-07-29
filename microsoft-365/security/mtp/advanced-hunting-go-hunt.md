---
title: Få relevant information om en enhet med go hunt
description: Lär dig hur du använder verktyget "go hunt" för att snabbt fråga efter relevant information om en enhet eller händelse med hjälp av avancerad jakt.
keywords: avancerad jakt, incident, pivot, enhet, gå jakt, relevanta händelser, hot jakt, cyber hot jakt, sökning, fråga, telemetri, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: b9afecb3d0efce93ae5d5725bba71d8d9719d17f
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430417"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a>Snabbt jaga enhet eller händelse information med go hunt

**Gäller:**
- Microsoft Hotskydd

Med åtgärden *go hunt* kan du snabbt undersöka händelser och olika entitetstyper med hjälp av kraftfulla frågebaserade [avancerade jaktfunktioner.](advanced-hunting-overview.md) Den här åtgärden kör automatiskt en avancerad jaktfråga för att hitta relevant information om den valda händelsen eller entiteten.

Go *hunt-åtgärden* är tillgänglig i olika delar av säkerhetscentret när händelse- eller entitetsinformation visas. Du kan till exempel använda *go hunt* från följande avsnitt:

- På [incidentsidan](investigate-incidents.md#incident-overview)kan du granska information om användare, enheter och många andra entiteter som är associerade med en incident. När du väljer en entitet får du ytterligare information samt olika åtgärder som du kan vidta på den berättigande. I exemplet nedan väljs en postlåda som visar information om postlådan samt möjlighet att söka efter mer information om postlådan.

    ![Bild som visar brevlåda detaljer med go hunt alternativet](../../media/mtp-ah/go-hunt-email.png)

- På incidentsidan kan du också komma åt en lista över entiteter under fliken Bevis.

    ![Bild som visar markerad fil med alternativet gå jakt på fliken Bevis](../../media/mtp-ah/go-hunt-evidence-file.png)


- När du visar tidslinjen för en enhet kan du välja en händelse på tidslinjen för att visa ytterligare information om händelsen. När ett evenemang har valts får du möjlighet att jaga efter andra relevanta evenemang i avancerad jakt.

    ![Bild som visar händelsedetaljer med alternativet Gå jakt](../../media/mtp-ah/go-hunt-event.png)

Om du väljer **Gå jakt** eller Jakt efter **relaterade händelser** skickas olika frågor, beroende på om du har valt en entitet eller en händelse.

## <a name="query-for-entity-information"></a>Fråga efter entitetsinformation
När du använder *gå jaga* till fråga efter information om en användare, enhet eller någon annan typ av entitet, kontrollerar frågan alla relevanta schematabeller för alla händelser som involverar den entiteten. För att hålla resultaten hanterbara begränsas frågan till ungefär samma tidsperiod som den tidigaste aktiviteten under de senaste 30 dagarna som involverar entiteten och är associerad med incidenten.

Här är ett exempel på go hunt-frågan för en enhet:

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
### <a name="supported-entity-types"></a>Typer av entitet som stöds
Du kan använda *go hunt* efter att du har valt någon av dessa entitetstyper:

- ﬁler
- Email
- E-kluster
- Postlådor
- Användare
- Enheter
- IP-adresser
- Webbadresser

## <a name="query-for-event-information"></a>Fråga efter händelseinformation
När du använder *gå jaga* till fråga efter information om en tidslinje händelse, kontrollerar frågan alla relevanta schematabeller för andra händelser runt tiden för den valda händelsen. Följande fråga visar till exempel händelser i olika schematabeller som inträffade ungefär samma tidsperiod på samma enhet:

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
Med viss kunskap om [frågespråket](advanced-hunting-query-language.md)kan du justera frågan efter dina önskemål. Du kan till exempel justera den här raden, som bestämmer storleken på tidsfönstret:

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

Förutom att ändra frågan för att få mer relevanta resultat kan du också:
- [Visa resultaten som diagram](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [Skapa en anpassad identifieringsregel](custom-detection-rules.md)

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Arbeta med frågeresultat](advanced-hunting-query-results.md)
- [Regler för anpassad identifiering](custom-detection-rules.md)