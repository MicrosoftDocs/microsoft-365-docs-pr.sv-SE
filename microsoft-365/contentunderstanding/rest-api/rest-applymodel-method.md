---
title: Batch-tillämpa modell
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
ms.openlocfilehash: 04f1dfdb0c16110c9ba7de12f5f0735d498d50cf
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286543"
---
# <a name="batch-apply-model"></a>Batch-tillämpa modell

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
|_metadata|ja|sträng|Ställ in objektmeta på SPO. Använd alltid värdet: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"}.|
|Publikationer|ja|MachineLearningPublicationEntityData[]|Samlingen MachineLearningPublicationEntityData som var och en anger modell- och måldokumentbiblioteket.|

### <a name="machinelearningpublicationentitydata"></a>MachineLearningPublicationEntityData

| Namn | Obligatoriskt | Typ | Beskrivning |
|--------|-------|--------|------------|
|ModelUniqueId|ja|sträng|Modellfilens unika ID.|
|TargetSiteUrl|ja|sträng|Den fullständiga URL-adressen till målbibliotekswebbplatsen.|
|TargetWebServerRelativeUrl|ja|sträng|Serverns relativa URL-adress för webben för målbiblioteket.|
|TargetLibraryServerRelativeUrl|ja|sträng|Serverns relativa URL-adress för målbiblioteket.|
|ViewOption|nej|sträng|Anger om den nya modellvyn ska anges som biblioteksstandard.|

## <a name="response"></a>Svar

| Namn   | Typ  | Beskrivning|
|--------|-------|------------|
|201 skapad||Det här är ett anpassat API som stöder tillämpning av en modell för flera dokumentbibliotek. Om det skulle lyckas delvis kan 201 som skapats fortfarande returneras och anroparen måste inspektera svarstexten för att förstå om modellen har tillämpats på ett dokumentbibliotek.|

## <a name="response-body"></a>Svarstext

| Namn   | Typ  | Beskrivning|
|--------|-------|------------|
|TotalSuccccis|int|Det totala antalet modeller som har tillämpats på ett dokumentbibliotek.|
|TotalFailures|int|Det totala antalet modeller som inte kan tillämpas på ett dokumentbibliotek.|
|Information|MachineLearningPublicationResult[]|Samlingen MachineLearningPublicationResult som var och en anger det detaljerade resultatet av att tillämpa modellen på dokumentbiblioteket.|

### <a name="machinelearningpublicationresult"></a>MachineLearningPublicationResult

| Namn   | Typ  | Beskrivning|
|--------|-------|------------|
|StatusCode|int|HTTP-statuskoden.|
|ErrorMessage|sträng|Felmeddelandet som anger vad som är fel när modellen tillämpas på dokumentbiblioteket.|
|Publicering|MachineLearningPublicationEntityData|Den anger modellinformationen och måldokumentbiblioteket.| 

### <a name="machinelearningpublicationentitydata"></a>MachineLearningPublicationEntityData

| Namn | Typ | Beskrivning |
|--------|--------|------------|
|ModelUniqueId|sträng|Modellfilens unika ID.|
|TargetSiteUrl|sträng|Den fullständiga URL-adressen till målbibliotekswebbplatsen.|
|TargetWebServerRelativeUrl|sträng|Serverns relativa URL-adress för webben för målbiblioteket.|
|TargetLibraryServerRelativeUrl|sträng|Serverns relativa URL-adress för målbiblioteket.|

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

**Statuskod:** 201

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
            "StatusCode": 201
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a>Se även

[REST API för dokumenttolkningsmodell i Syntex](syntex-model-rest-api.md)
