---
title: 'Avancerade jakt-API: er'
description: Lär dig hur du kör avancerade frågor med hjälp av Microsoft 365 Defender API
keywords: 'Avancerad jakt, API: er, MTP'
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: c43d263009578af6280ffdc780ab0f9a174a3b97
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844038"
---
# <a name="advanced-hunting-apis"></a>Avancerade jakt-API: er

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

>[!IMPORTANT] 
>Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.

## <a name="limitations"></a>Begränsningar
1. Du kan bara köra en fråga på data från de senaste 30 dagarna.
2. Resultaten inkluderar högst 100 000 rader.
3. Antalet körningar är begränsat per klient organisation: upp till 10 samtal per minut, 10 minuters kör tid varje timme och 4 timmar efter en dag.
4. Maximal körnings tid för en enda begäran är 10 minuter.
5. 429-svaret kommer att representera en kvot gräns antingen per antal begär Anden eller per CPU. Svars texten för 429 anger också tiden tills kvoten förnyas. 


## <a name="permissions"></a>Behörigheter
En av följande behörigheter krävs för att kunna ringa detta API. Om du vill veta mer, inklusive hur du väljer behörigheter, se [Microsoft 365 Defender API: er](api-access.md)

Behörighets typ |   Tillåtelse  |   Visnings namn för behörighet
:---|:---|:---
Program |   AdvancedHunting. Read. all |  "Kör avancerade frågor"
Delegerat (arbets-eller skol konto) | AdvancedHunting. Read | "Kör avancerade frågor"

>[!Note]
> När du erhåller ett token med användar uppgifter:
>- Användaren måste ha AD-rollen "Visa data"
>- Användaren måste ha åtkomst till enheten baserat på Inställningar för enhets grupp.

## <a name="http-request"></a>HTTP-begäran
```
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a>Begärandehuvuden

Meddelande | Värde 
:---|:---
Bemyndigande | Bearer {token}. **Obligatoriskt**.
Innehålls typ    | program/JSON

## <a name="request-body"></a>Brödtext
Ange ett JSON-objekt med följande parametrar i den efterfrågade texten:

Indataparametern | Skriv    | Beskrivning
:---|:---|:---
Frågeserver | Text |  Frågan att köra. **Obligatoriskt**.

## <a name="response"></a>Interimssvar
Om det lyckas returnerar den här metoden 200 OK och _QueryResponse_ -objekt i svars texten. <br><br>

Response-objektet är uppdelat till 3 delar (egenskaper):<br>
1) ```Stats``` -Fråga prestanda statistik.<br>
2) ```Schema``` -Schemat för svaret, en lista över Name-Type par för varje kolumn. <br>
3) ```Results``` – En lista över avancerade jakt händelser.

## <a name="example"></a>Exempel

Ställning

Här är ett exempel på begäran.


```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

Interimssvar

Här är ett exempel på svaret.


```json
{
    "Stats": {
        "ExecutionTime": 4.621215,
        "resource_usage": {
            "cache": {
                "memory": {
                    "hits": 773461,
                    "misses": 4481,
                    "total": 777942
                },
                "disk": {
                    "hits": 994,
                    "misses": 197,
                    "total": 1191
                }
            },
            "cpu": {
                "user": "00:00:19.0468750",
                "kernel": "00:00:00.0156250",
                "total cpu": "00:00:19.0625000"
            },
            "memory": {
                "peak_per_node": 236822432
            }
        },
        "dataset_statistics": [
            {
                "table_row_count": 2,
                "table_size": 102
            }
        ]
    },
    "Schema": [
        {
            "Name": "Timestamp",
            "Type": "DateTime"
        },
        {
            "Name": "FileName",
            "Type": "String"
        },
        {
            "Name": "InitiatingProcessFileName",
            "Type": "String"
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-08-30T06:38:35.7664356Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        },
        {
            "Timestamp": "2020-08-30T06:38:30.5163363Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        }
    ]
}

```

## <a name="related-topic"></a>Närliggande ämne
- [Gå till API för Microsoft 365 Defender](api-access.md)
