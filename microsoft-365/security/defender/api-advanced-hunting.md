---
title: API för avancerad sökning för Microsoft 365 Defender
description: Lär dig hur du kör avancerade sökfrågor med hjälp av Microsoft 365 Defenders avancerade API för sökning
keywords: Advanced Hunting, API:er, api, MTP, M365 Defender, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 482801bb47429ae370e06cfcbcf26bacfb8b2a92
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074801"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a>API för avancerad sökning för Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft Threat Protection

> [!IMPORTANT]
> En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.

[Avancerad sökning](advanced-hunting-overview.md) är ett verktyg för hot efter hot som använder särskilt uppbyggda frågor för att undersöka de senaste 30 [dagarnas](advanced-hunting-query-language.md) händelsedata i Microsoft 365 Defender. Du kan använda avancerade sökfrågor för att inspektera ovanlig aktivitet, identifiera möjliga hot och även svara på attacker. Med API:t för avancerad sökning kan du programmässigt fråga händelsedata.

## <a name="quotas-and-resource-allocation"></a>Kvoter och resurstilldelning

Följande villkor gäller för alla frågor.

1. Frågor utforskar och returnerar data från de senaste 30 dagarna.
2. Resultatet kan returnera upp till 100 000 rader.
3. Du kan ringa upp till 15 samtal per minut per klientorganisation.
4. Du har 10 minuters körning per timme per klientorganisation.
5. Du har fyra timmar körtid per dag per klientorganisation.
6. Om en enskild begäran körs i mer än 10 minuter time out och returnerar ett fel.
7. En HTTP-svarskod anger att du har nått en kvot, antingen genom antal begäranden som skickas `429` eller med tilldelad löpande tid. Läs svarstexten för att förstå gränsen som du har nått. 

> [!NOTE]
> Alla kvoter som anges ovan (till exempel 15 samtal per min) är per klientorganisationsstorlek. Dessa kvoter är de lägsta.

## <a name="permissions"></a>Behörigheter

En av följande behörigheter krävs för att anropa det avancerade API:t för sökning. Mer information, inklusive hur du väljer behörigheter, finns i Åtkomst till [API:er för Microsoft 365 Defender Protection](api-access.md)

Behörighetstyp | Behörighet | Visningsnamn för behörighet
-|-|-
Program | AdvancedHunting.Read.All | Köra avancerade frågor
Delegerat (arbets- eller skolkonto) | AdvancedHunting.Read | Köra avancerade frågor

>[!Note]
> När du skaffar en token med hjälp av användarautentiseringsuppgifter:
>
>- Användaren måste ha AD-rollen "Visa data"
>- Användaren måste ha åtkomst till enheten, baserat på enhetens gruppinställningar.

## <a name="http-request"></a>HTTP-begäran

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a>Begäran om rubriker

Sidhuvud | Value
-|-
Auktorisering | Bearer {token} **Obs! obligatoriskt**
Innehållstyp | application/json

## <a name="request-body"></a>Begärans brödtext

Ange följande parametrar för ett JSON-objekt i begärans brödtext:

Parameter | Type (Typ) | Beskrivning
-|-|-
Fråga | Text | Frågan som ska köras. **Obs! obligatoriskt**

## <a name="response"></a>Svar

Om det lyckas returnerar den här `200 OK` metoden och _ett QueryResponse-objekt_ i svarets brödtext.

Svarsobjektet innehåller tre egenskaper på översta nivån:

1. Statistik – en ordlista med frågeprestandastatistik.
2. Schema – Schemat för svaret, en lista Name-Type par för varje kolumn.
3. Resultat – En lista över avancerad sökning.

## <a name="example"></a>Exempel

I följande exempel skickar en användare frågan nedan och tar emot ett API-svarsobjekt som `Stats` innehåller `Schema` , och `Results` .

### <a name="query"></a>Fråga

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

- [Åtkomst till Microsoft 365 Defender-API:er](api-access.md)
- [Läs mer om API-begränsningar och licensiering](api-terms.md)
- [Förstå felkoder](api-error-codes.md)
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
