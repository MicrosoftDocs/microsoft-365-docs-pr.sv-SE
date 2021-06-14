---
title: BatchDelete
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
description: Använd REST API för att ta bort en tillämpad dokumenttolkningsmodell från ett eller flera bibliotek.
ms.openlocfilehash: 8c7aeb449da161fe49050631643c63c93268a13f
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904277"
---
# <a name="batchdelete"></a>BatchDelete

Tar bort en tillämpad dokumenttolkningsmodell från ett eller flera bibliotek. Observera att en modell måste tas bort från alla bibliotek innan den ska kunna tas bort (se [exempel](rest-batchdelete-method.md#examples)).

## <a name="http-request"></a>HTTP-begäran

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a>URI-parametrar

Ingen

## <a name="request-headers"></a>Frågerubriker

| Rubrik | Värde |
|--------|-------|
|Acceptera|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|Den lämpliga sammanfattningen för aktuell webbplats.|

## <a name="request-body"></a>Frågebrödtext

| Namn | Obligatoriskt | Typ | Beskrivning |
|--------|-------|--------|------------|
|ModelUniqueId|ja|sträng|Modellfilens unika ID.|
TargetSiteUrl|ja|sträng|Den fullständiga URL-adressen till målbibliotekswebbplatsen.|
TargetWebServerRelativeUrl|ja|sträng|Serverns relativa webbadress för webben för målbiblioteket.|
TargetLibraryServerRelativeUrl|ja|sträng|Serverns relativa URL-adress för målbiblioteket.|
ViewOption|ingen|sträng|Anger om den nya modellvyn ska anges som biblioteksstandard.|

## <a name="response"></a>Svar

| Namn   | Typ  | Beskrivning|
|--------|-------|------------|
|200 OK| |Klart|


## <a name="examples"></a>Exempel

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a>Ta bort en modell från kontraktsdokumentbiblioteket i lagringsplatsen

I det här exemplet är ID:t för dokumenttolkningsmodellen i Contoso Contract `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.

#### <a name="sample-request"></a>Exempelbegäran

```HTTP
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"
    },
    "Publications": {
        "results": [
            {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            }
        ]
    }
}
```


#### <a name="sample-response"></a>Exempelsvar

I svaret refererar TotalFailures och TotalSuccesses till antalet misslyckanden och framgångar för modellen som tillämpas på de angivna biblioteken.

**Statuskod:** 200

```JSON
{
    "Details": [
        {
            "ErrorMessage": null,
            "Publication": {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            },
            "StatusCode": 200
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a>Se även

[REST API för dokumenttolkningsmodell i Syntex](syntex-model-rest-api.md)
