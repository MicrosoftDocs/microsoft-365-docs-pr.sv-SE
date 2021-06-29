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
ms.openlocfilehash: cd288812044f3b02839c3c11c321947bd02cccaa
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177171"
---
# <a name="updatemodelsettings"></a>UpdateModelSettings

Uppdaterar tillgängliga modellers inställningar (tillhörande bevarandeetikett och modellbeskrivning) för en dokumenttolkningsmodell i SharePoint Syntex (se [exempel](rest-updatemodelsettings-method.md#examples)).

## <a name="http-request"></a>HTTP-begäran

```HTTP
POST /_api/machinelearning/models/getbytitle('{modelFileName}')/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a>URI-parametrar

|Namn |In |Obligatoriskt|Typ|Beskrivning|
|-----|---|--------|----|-----------|
|modelFileName|fråga|Sant|sträng|Namnet på Syntex-modellfilen.|

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
