---
title: Tillämpa en modell
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
description: Använd REST API för att tillämpa en dokumenttolkningsmodell på ett eller flera bibliotek.
ms.openlocfilehash: d4cadad3c45dd7af0cdaeb4e1b367426289db870
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904357"
---
# <a name="apply-model"></a>Tillämpa en modell

Tillämpar (eller synkroniserar) en tränad dokumenttolkningsmodell på ett eller flera bibliotek (se [exempel](rest-applymodel-method.md#examples)).

## <a name="http-request"></a>HTTP-begäran

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
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
TargetWebServerRelativeUrl|ja|sträng|Serverns relativa URL-adress för webben för målbiblioteket.|
TargetLibraryServerRelativeUrl|ja|sträng|Serverns relativa URL-adress för målbiblioteket.|
ViewOption|nej|sträng|Anger om den nya modellvyn ska anges som biblioteksstandard.|

## <a name="response"></a>Svar

| Namn   | Typ  | Beskrivning|
|--------|-------|------------|
|200 OK| |Klart|
|201 skapad| |Observera att eftersom detta API stöder att tillämpa modell för flera bibliotek kan 201 returneras även om det inte går att tillämpa modellen på ett av biblioteken. <br>Kontrollera svarbrödtexten för att förstå om modellen har tillämpats på alla angivna bibliotek. Gå till [Frågebrödtext](rest-applymodel-method.md#request-body) för mer information.|

## <a name="examples"></a>Exempel

### <a name="apply-a-model-to-the-contracts-document-library-in-the-repository-site"></a>Tillämpa en modell på kontraktsdokumentbiblioteket i lagringsplatsen

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
