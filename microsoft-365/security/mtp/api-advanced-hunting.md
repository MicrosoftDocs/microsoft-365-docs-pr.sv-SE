---
title: Microsoft 365 Defender Advanced jakt-API
description: Lär dig hur du kör avancerade jakt frågor med Microsoft 365 Defender s Advanced jakt API
keywords: 'Avancerad jakt, API: er, MTP, M365 Defender, Microsoft 365 Defender'
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 99f39a10de6231a72220c5c2a90ec915b1a4e44a
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988122"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a>Microsoft 365 Defender Advanced jakt-API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft Threat Protection

> [!IMPORTANT]
> Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.

[Avancerad jakt](advanced-hunting-overview.md) är ett hot-jakt-verktyg som använder [särskilt utformade frågor](advanced-hunting-query-language.md) för att undersöka de senaste 30 dagarna av händelse data i Microsoft 365 Defender. Du kan använda avancerade jakt frågor för att kontrol lera ovanlig aktivitet, upptäcka möjliga hot och till och med reagera på attacker. Med Advanced jakt API kan du programatically fråga efter händelse data.

## <a name="quotas-and-resource-allocation"></a>Kvoter och resurstilldelning

Följande villkor gäller för alla frågor.

1. Frågor utforskar och returnerar data från de senaste 30 dagarna.
2. Resultaten kan returnera upp till 100 000 rader.
3. Du kan ringa upp till 15 samtal per minut per klient organisation.
4. Du har 10 minuters kör tid per timme per klient organisation.
5. Du har fyra totala timmar med kör tid per dag per klient organisation.
6. Om en enda begäran körs i mer än 10 minuter upphör den att fungera och ett fel meddelande returneras.
7. En `429` http-svarskod visar att du har nått en kvot, antingen av antalet begär Anden som skickats eller via utsatt tid för drift. Läs svars texten för att förstå den gräns du har uppnått. 

> [!NOTE]
> Alla kvoter ovan (till exempel 15 samtal per minut) är per innehavare. De här kvoterna är minst.

## <a name="permissions"></a>Behörigheter

En av följande behörigheter krävs för att kunna ringa det avancerade jakt-API: t. Om du vill veta mer, inklusive hur du väljer behörigheter, läser du [gå till Microsoft 365 Defender-skydds-API: erna](api-access.md)

Behörighets typ | Tillåtelse | Visnings namn för behörighet
-|-|-
Program | AdvancedHunting. Read. all | Kör avancerade frågor
Delegerat (arbets-eller skol konto) | AdvancedHunting. Read | Kör avancerade frågor

>[!Note]
> När du erhåller ett token med användar uppgifter:
>
>- Användaren måste ha AD-rollen "Visa data"
>- Användaren måste ha åtkomst till enheten baserat på Inställningar för enhets grupp.

## <a name="http-request"></a>HTTP-begäran

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a>Begärandehuvuden

Meddelande | Value
-|-
Bemyndigande | Bevarad {token} **Obs!**
Innehålls typ | program/JSON

## <a name="request-body"></a>Brödtext

Ange ett JSON-objekt med följande parametrar i den efterfrågade texten:

Indataparametern | Type (Typ) | Beskrivning
-|-|-
Frågeserver | Text | Frågan att köra. **Obs!**

## <a name="response"></a>Interimssvar

Om det lyckas returneras den här metoden `200 OK` och ett _QueryResponse_ -objekt i svars texten.

Response-objektet innehåller tre högsta nivå egenskaper:

1. Statistik – en ord lista med prestanda statistik för frågor.
2. Schema – schemat för svaret, en lista över Name-Type par för varje kolumn.
3. Resultat – en lista över avancerade jakt händelser.

## <a name="example"></a>Exempel

I följande exempel skickar en användare frågan nedan och tar emot ett API-svarsmeddelande som innehåller `Stats` , `Schema` , och `Results` .

### <a name="query"></a>Frågeserver

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a>Response-objekt

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

## <a name="related-articles"></a>Relaterade artiklar

- [Gå till API för Microsoft 365 Defender](api-access.md)
- [Läs mer om API-begränsningar och licensiering](api-terms.md)
- [Förstå felkoder](api-error-codes.md)
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
