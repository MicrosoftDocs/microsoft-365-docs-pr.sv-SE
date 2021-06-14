---
title: Skapa modell
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
description: Använd REST API för att skapa en modell och dess associerade innehållstyp.
ms.openlocfilehash: 4af980d0733fce63767c6570003342eadb079f26
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904297"
---
# <a name="create-model"></a>Skapa modell

Skapar en modell och dess associerade innehållstyp. Observera att det bara skapar modellen. Den kommer fortfarande att behöva tränas i innehållscentret (se [exempel](rest-createmodel-method.md#examples)).

## <a name="http-request"></a>HTTP-begäran

```
POST /_api/machinelearning/models HTTP/1.1
```
## <a name="uri-parameters"></a>URI-parametrar

Ingen

## <a name="request-headers"></a>Frågerubriker

| Rubrik | Värde |
|--------|-------|
|Acceptera|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|Den lämpliga sammanfattningen för aktuell webbplats|

## <a name="request-body"></a>Frågebrödtext

|Namn    |Typ   |Beskrivning |
|--------|-------|------------|
|_metadata|  |Ställ in objektmeta på SPO. Använd alltid värdet: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}. |
|ContentTypeGroup|sträng|Den associerade innehållstypgrupp som är kopplad till modellen. Som standard för “Intelligenta dokumentinnehållstyper".|
|ContentTypeName|sträng|Namnet på den associerade innehållstypen. Den skapade modellfilen kommer att ha samma namn.|

## <a name="responses"></a>Svar

| Namn   | Typ  | Beskrivning|
|--------|-------|------------|
|201 skapad| |Klart|

## <a name="examples"></a>Exempel

### <a name="create-a-new-document-understanding-model-called-contoso-contract"></a>Skapa en ny dokumenttolkningsmodell som heter "Contoso Contract"

#### <a name="sample-request"></a>Exempelbegäran

```
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "ContentTypeGroup": "Intelligent Document Content Types",
    "ContentTypeName": "Contoso Contract",
}
```

#### <a name="sample-response"></a>Exempelsvar

**Statuskod:** 201

## <a name="see-also"></a>Se även

[REST API för dokumenttolkningsmodell i Syntex](syntex-model-rest-api.md)
