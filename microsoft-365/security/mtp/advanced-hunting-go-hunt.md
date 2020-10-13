---
title: Få relevant information om en enhet med go-letare
description: Lär dig hur du använder verktyget "go-fest" för att snabbt fråga efter relevant information om en enhet eller händelse med hjälp av avancerad jakt.
keywords: Avancerad jakt, olycka, pivot, enhet, go-evenemang, relevanta händelser, hot mot cyberterrorism hotet om sökning, frågor, telemetri, Microsoft 365, Microsoft Threat Protection
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 4abbedc34b6d77e785c2096d9f334000f9ffb02f
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430473"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a>Hitta snabbt en enhet eller händelse information med go-evenemang

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Threat Protection

Med åtgärden *gå* med, kan du snabbt undersöka händelser och olika entitetstyper med hjälp av kraftfulla frågor baserade på de [avancerade jakt](advanced-hunting-overview.md) funktionerna. Den här åtgärden kör automatiskt en avancerad tilläggsfråga för att hitta relevant information om den markerade händelsen eller enheten.

Åtgärden *Go-letare* är tillgänglig i olika avsnitt i säkerhets Center när händelse-eller entitetsinformation visas. Du kan till exempel använda *Go-leta* från följande avsnitt:

- På [sidan incident](investigate-incidents.md#incident-overview)kan du granska information om användare, enheter och många andra enheter som är kopplade till en olycka. När du väljer en entitet får du ytterligare information och olika åtgärder du kan vidta för den entitity. I exemplet nedan är en post låda markerad, med information om post lådan och även om du väljer att ha mer information om post lådan.

    ![Bild som visar brev låde information med alternativet Sök efter](../../media/mtp-ah/go-hunt-email.png)

- På sidan incident kan du även komma åt en lista med enheter under fliken bevis. Om du väljer någon av dessa enheter kan du snabbt hitta information om den personen.

    ![Bild som visar markerad fil med alternativet Sök efter på fliken bevis](../../media/mtp-ah/go-hunt-evidence-file.png)


- När du visar tids linjen för en enhet kan du välja en händelse i tids linjen för att visa ytterligare information om händelsen. När en händelse är markerad får du möjlighet att hitta alla relevanta händelser i avancerad jakt.

    ![Bild som visar händelse Detaljer med alternativet Sök efter](../../media/mtp-ah/go-hunt-event.png)

När **Go hunt** du väljer Sök **efter relaterade händelser** skickas olika frågor, beroende på om du har valt en enhet eller en händelse.

## <a name="query-for-entity-information"></a>Fråga efter entitetsinformation
När du använder *Go-leta* för att söka efter information om en användare, en enhet eller någon annan typ av enhet kontrollerar frågan alla relevanta schema tabeller för eventuella händelser som berör den entiteten. För att resultaten ska kunna hanteras begränsas frågan till samma tids period som den tidigaste aktiviteten under de senaste 30 dagarna som berör enheten och är kopplad till händelsen.

Här är ett exempel på frågan Sök efter en enhet:

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
Du kan använda *gå* till efter att välja någon av följande typer av enheter:

- Hjälpfiler
- E-postmeddelanden
- E-postkluster
- Post lådor
- Användare
- Anordningar
- IP-adresser
- Garanteras

## <a name="query-for-event-information"></a>Fråga efter händelse information
När du använder *Go-leta* för att få information om en tids linje händelse kontrollerar frågan alla relevanta schema tabeller för andra händelser kring tiden för den markerade händelsen. I följande fråga visas till exempel händelser i olika schema tabeller som har inträffat kring samma tids period på samma enhet:

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
Med lite kunskap om [frågespråket](advanced-hunting-query-language.md)kan du ändra frågan till preferenser. Du kan till exempel justera den här raden, som avgör tidsfönstrets storlek:

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

Förutom att ändra frågan för att få mer relevanta resultat kan du också:
- [Visa resultatet som diagram](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [Skapa en anpassad detektions regel](custom-detection-rules.md)

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Arbeta med frågeresultat](advanced-hunting-query-results.md)
- [Anpassade identifierings regler](custom-detection-rules.md)
