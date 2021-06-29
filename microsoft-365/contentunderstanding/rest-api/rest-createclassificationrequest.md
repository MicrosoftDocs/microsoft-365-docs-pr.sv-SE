---
title: Skapa klassificeringsbegäran
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
description: Använd REST API för att skapa en begäran om att klassificera en eller flera filer med hjälp av en tränad dokumenttolkningsmodell.
ms.openlocfilehash: 3a796bcdb38a9a6930b51f7d585febb69082732e
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177087"
---
# <a name="create-classification-request"></a>Skapa klassificeringsbegäran

Skapar en begäran om att klassificera en eller flera filer med hjälp av den använda den tillämpade dokumenttolkningsmodellen (se [exempel](rest-createclassificationrequest.md#examples)).

SharePoint Onlines (och SharePoint 2016 och senare lokalt) REST-tjänst har stöd för att kombinera flera begäranden. Begäranden kombineras till ett enda anrop till tjänsten med hjälp av frågealternativet OData $batch. Den här metoden kan användas köa arbetsobjekt för klassificering för hundratals dokument samtidigt.

## <a name="http-request"></a>HTTP-begäran

```
POST /_api/machinelearning/workItems HTTP/1.1
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
|_metadata|sträng |Ställ in objektmeta på SPO. Använd alltid värdet: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"}. |
|TargetSiteId|guid|ID för webbplatsen där filen som ska klassificera finns.|
|TargetWebId|guid|ID på webben där filen som ska klassificera finns.|
|TargetUniqueId|guid|ID för filen som ska klassificeras.|

## <a name="responses"></a>Svar

| Namn   | Typ  | Beskrivning|
|--------|-------|------------|
|201 skapad| |Klart|

## <a name="examples"></a>Exempel

### <a name="enqueue-a-request-to-classify-a-file-of-id-e6cff8b7-c90c-4564-b5b8-033449090932"></a>Köa en begäran om att klassificera en fil med id "e6cff8b7-c90c-4564-b5b8-033449090932"

#### <a name="sample-request"></a>Exempelbegäran

```
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"
    },
    "TargetSiteId": "f686e63b-aba7-48e5-97c7-68c4c1df292f",
    "TargetWebId": "66d6b64d-6f88-4dd9-b3db-47e6f00c53e8",
    "TargetUniqueId": "e6cff8b7-c90c-4564-b5b8-033449090932"
}
```

#### <a name="sample-response"></a>Exempelsvar

**Statuskod:** 201

## <a name="see-also"></a>Se även

[REST API för dokumenttolkningsmodell i Syntex](syntex-model-rest-api.md)
