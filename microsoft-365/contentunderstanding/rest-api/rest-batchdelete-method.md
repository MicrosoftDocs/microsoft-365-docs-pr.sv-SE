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
ms.openlocfilehash: bbd3e496b50d3fddb31342fbc07d30984544e744
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287459"
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
|Publikationer|ja|MachineLearningPublicationEntityData[]|Samlingen MachineLearningPublicationEntityData som var och en anger modell- och måldokumentbiblioteket.|

### <a name="machinelearningpublicationentitydata"></a>MachineLearningPublicationEntityData

| Namn | Obligatoriskt | Typ | Beskrivning |
|--------|-------|--------|------------|
|ModelUniqueId|ja|sträng|Modellfilens unika ID.|
|TargetSiteUrl|ja|sträng|Den fullständiga URL-adressen till målbibliotekswebbplatsen.|
|TargetWebServerRelativeUrl|ja|sträng|Serverns relativa URL-adress för webben för målbiblioteket.|
|TargetLibraryServerRelativeUrl|ja|sträng|Serverns relativa URL-adress för målbiblioteket.|

## <a name="response"></a>Svar

| Namn   | Typ  | Beskrivning|
|--------|-------|------------|
|200 OK||Det här är ett anpassat API som stöder borttagning av en modell från bibliotek med flera dokument. Vid delvis lyckad åtgärd kan 200 OK fortfarande returneras och anroparen måste inspektera svarstexten för att förstå om modellen har tagits bort från ett dokumentbibliotek.|

## <a name="response-body"></a>Svarstext

| Namn   | Typ  | Beskrivning|
|--------|-------|------------|
|TotalSuccccis|int|Det totala antalet modeller som tas bort från ett dokumentbibliotek.|
|TotalFailures|int|Det totala antalet modeller som inte kan tas bort från ett dokumentbibliotek.|
|Information|MachineLearningPublicationResult[]|Samlingen MachineLearningPublicationResult som var och en anger det detaljerade resultatet av att ta bort modellen från ett dokumentbibliotek.|

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

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a>Ta bort en modell från kontraktsdokumentbiblioteket i lagringsplatsen

I det här exemplet är ID:t för dokumenttolkningsmodellen i Contoso Contract `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.

#### <a name="sample-request"></a>Exempelbegäran

```HTTP
{ 
    "publications": [ 
        { 
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc", 
            "TargetSiteUrl": "https://constco.sharepoint-df.com/sites/docsite", 
            "TargetWebServerRelativeUrl": "/sites/docsite ", 
            "TargetLibraryServerRelativeUrl": "/sites/dcocsite/joedcos" 
        } 
    ] 
} 
```

#### <a name="sample-response"></a>Exempelsvar

I svaret refererar TotalFailures och TotalSuccesses till antalet misslyckanden och framgångar för modellen som tas bort på de angivna biblioteken.

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
