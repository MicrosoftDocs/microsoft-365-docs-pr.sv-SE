---
title: UpdateModelSettings
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: reference
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: m365initiative-syntex
localization_priority: Priority
description: Använd REST API för att uppdatera inställningar för tillgängliga modeller för dokumenttolkningsmodell i SharePoint Syntex.
ms.openlocfilehash: f24fc8428adbf22ded2ca6d7a49cabc84b385770
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904307"
---
# <a name="updatemodelsettings"></a>UpdateModelSettings

Uppdaterar tillgängliga modellers inställningar (tillhörande bevarandeetikett och modellbeskrivning) för en dokumenttolkningsmodell i SharePoint Syntex (se [exempel](rest-updatemodelsettings-method.md#examples)).

## <a name="http-request"></a>HTTP-begäran

```HTTP
POST /_api/machinelearning/models/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a>URI-parametrar

Ingen

## <a name="request-headers"></a>Frågerubrik

| Rubrik | Värde |
|--------|-------|
|Acceptera|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|Lämplig sammanfattning för den aktuella webbplatsen.|

## <a name="request-body"></a>Frågebrödtext

|Namn    |Typ   |Beskrivning |
|--------|-------|-------|
|ModelSettings|sträng|JSON för modellinställningar.|
|Beskrivning|sträng|Modellbeskrivningen. |
|RetentionLabel| |Information om den associerade etiketten (etikett-ID och namn).|

## <a name="responses"></a>Svar

| Namn   | Typ  | Beskrivning|
|--------|-------|------------|
|200 OK| |Klart|

## <a name="examples"></a>Exempel

### <a name="update-model-settings-for-contoso-contract"></a>Uppdatera modellinställningar för Contoso Contract

I det här exemplet uppdateras modellbeskrivningen och kvarhållningsetiketten "Standard Hold". ID:t för kvarhållningstaggen är `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.

#### <a name="sample-request"></a>Exempelbegäran

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a>Exempelsvar

**Statuskod:** 200

## <a name="see-also"></a>Se även

[REST API för dokumenttolkningsmodell i Syntex](syntex-model-rest-api.md)
