---
title: API för att hämta aviseringar
description: Läs mer om metoder och egenskaper för resurstypen Avisering i Microsoft Defender för slutpunkt.
keywords: apis, graph api, API som stöds, skaffa, aviseringar, senaste
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: df1a032ffab0490c41edc7d282f0f2cc60608870
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289685"
---
# <a name="alert-resource-type"></a>Aviseringsresurstyp

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="methods"></a>Metoder

Metod |Returtyp |Beskrivning
:---|:---|:---
[Få en avisering](get-alert-info-by-id.md) | [Varning](alerts.md) | Få ett enda [aviseringsobjekt.](alerts.md)
[Listvarningar](get-alerts.md) | [Aviseringssamling](alerts.md) | Samling [med listaviseringar.](alerts.md)
[Uppdateringsavisering](update-alert.md) | [Varning](alerts.md) | Uppdatera specifik [avisering](alerts.md).
[Batchuppdateringsaviseringar](batch-update-alerts.md) | | Uppdatera en uppsättning [aviseringar](alerts.md).
[Skapa varning](create-alert-by-reference.md)|[Varning](alerts.md)|Skapa en avisering baserat på händelsedata från [Avancerad sökning.](run-advanced-query-api.md)
[Visa relaterade domäner](get-alert-related-domain-info.md)|Domänsamling| List-URL:er som är kopplade till aviseringen.
[Lista relaterade filer](get-alert-related-files-info.md) | [Filsamling](files.md) |  Lista de [filenheter](files.md) som är associerade med [aviseringen](alerts.md).
[Lista relaterade IP-adresser](get-alert-related-ip-info.md) | IP-samling | List-IP:er som är associerade med aviseringen.
[Skaffa relaterade datorer](get-alert-related-machine-info.md) | [Maskin](machine.md) | Den [dator](machine.md) som är kopplad till [aviseringen](alerts.md).
[Skaffa relaterade användare](get-alert-related-user-info.md) | [Användare](user.md) | Användaren [som](user.md) är kopplad till [aviseringen](alerts.md).

## <a name="properties"></a>Egenskaper

Egenskap |    Typ    |    Beskrivning
:---|:---|:---
id | Sträng | Aviserings-ID.
rubrik | Sträng | Aviseringsrubrik.
description | Sträng | Aviseringsbeskrivning.
alertCreationTime | Nullable DateTimeOffset | Datum och tid (i UTC) som aviseringen skapades.
lastEventTime | Nullable DateTimeOffset | Den sista förekomsten av händelsen som utlöste aviseringen på samma enhet.
firstEventTime | Nullable DateTimeOffset | Den första förekomsten av händelsen som utlöste aviseringen på enheten.
lastUpdateTime | Nullable DateTimeOffset | Datum och tid (i UTC) som aviseringen uppdaterades senast.
resolvedTime | Nullable DateTimeOffset | Datum och tid då statusen för aviseringen ändrades till Löst.
incidentId | Nullable Long | [Incident-ID](view-incidents-queue.md) för aviseringen.
investigationId | Nullable Long | [Undersöknings-ID](automated-investigations.md) relaterat till aviseringen.
investigationState | Nullbar uppräkning | Aktuell status för [undersökningen](automated-investigations.md). Möjliga värden är: "Okänt", "Avslutat", "SuccessfullyRemediated", 'SuppressedAlert', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.
assignedTo | Sträng | Ägaren av aviseringen.
allvarlighetsgrad | Uppräkning | Aviseringens allvarlighetsgrad. Möjliga värden är: "UnSpecified", 'Informational', 'Low', 'Medium' och 'High'.
status | Uppräkning | Anger aktuell status för aviseringen. Möjliga värden är: "Okänt", "Nytt", "InProgress" och "Löst".
klassificering | Nullbar uppräkning | Specifikation för aviseringen. Möjliga värden är: "Okänt", "FalsktPositiv", "SantPositiv".
determination | Nullbar uppräkning | Anger om aviseringen är bestämd. Möjliga värden är: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'.
kategori| Sträng | Kategorin för aviseringen.
detectionSource | Sträng | Identifieringskälla.
threatFamilyName | Sträng | Hotfamilj.
threatName | Sträng | Hotnamn.
machineId | Sträng | ID för en [maskin](machine.md) entitet som är associerad med aviseringen.
computerDnsName | Sträng | [fullständigt](machine.md) kvalificerat namn.
aadTenantId | Sträng | Detta Azure Active Directory ID.
anslutetId | Sträng | ID för den som utlöste aviseringen.
kommentarer | Lista med aviseringskommentarer | Aviseringskommentarsobjekt innehåller: kommentarssträng, createdBy-sträng och createTime-datumtid.
Bevis | Lista med varningsbevis | Bevis som är relaterade till aviseringen. Se exemplet nedan.

### <a name="response-example-for-getting-single-alert"></a>Svarsexempel för att få en enda avisering:

```http
GET https://api.securitycenter.microsoft.com/api/alerts/da637472900382838869_1364969609
```

```json
{
    "id": "da637472900382838869_1364969609",
    "incidentId": 1126093,
    "investigationId": null,
    "assignedTo": null,
    "severity": "Low",
    "status": "New",
    "classification": null,
    "determination": null,
    "investigationState": "Queued",
    "detectionSource": "WindowsDefenderAtp",
    "detectorId": "17e10bbc-3a68-474a-8aad-faef14d43952",
    "category": "Execution",
    "threatFamilyName": null,
    "title": "Low-reputation arbitrary code executed by signed executable",
    "description": "Binaries signed by Microsoft can be used to run low-reputation arbitrary code. This technique hides the execution of malicious code within a trusted process. As a result, the trusted process might exhibit suspicious behaviors, such as opening a listening port or connecting to a command-and-control (C&C) server.",
    "alertCreationTime": "2021-01-26T20:33:57.7220239Z",
    "firstEventTime": "2021-01-26T20:31:32.9562661Z",
    "lastEventTime": "2021-01-26T20:31:33.0577322Z",
    "lastUpdateTime": "2021-01-26T20:33:59.2Z",
    "resolvedTime": null,
    "machineId": "111e6dd8c833c8a052ea231ec1b19adaf497b625",
    "computerDnsName": "temp123.middleeast.corp.microsoft.com",
    "rbacGroupName": "A",
    "aadTenantId": "a839b112-1253-6432-9bf6-94542403f21c",
    "threatName": null,
    "mitreTechniques": [
        "T1064",
        "T1085",
        "T1220"
    ],
    "relatedUser": {
        "userName": "temp123",
        "domainName": "MIDDLEEAST"
    },
    "comments": [
        {
            "comment": "test comment for docs",
            "createdBy": "secop123@contoso.com",
            "createdTime": "2021-01-26T01:00:37.8404534Z"
        }
    ],
    "evidence": [
        {
            "entityType": "User",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": null,
            "sha256": null,
            "fileName": null,
            "filePath": null,
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": "eranb",
            "domainName": "MIDDLEEAST",
            "userSid": "S-1-5-21-11111607-1111760036-109187956-75141",
            "aadUserId": "11118379-2a59-1111-ac3c-a51eb4a3c627",
            "userPrincipalName": "temp123@microsoft.com",
            "detectionStatus": null
        },
        {
            "entityType": "Process",
            "evidenceCreationTime": "2021-01-26T20:33:58.6133333Z",
            "sha1": "ff836cfb1af40252bd2a2ea843032e99a5b262ed",
            "sha256": "a4752c71d81afd3d5865d24ddb11a6b0c615062fcc448d24050c2172d2cbccd6",
            "fileName": "rundll32.exe",
            "filePath": "C:\\Windows\\SysWOW64",
            "processId": 3276,
            "processCommandLine": "rundll32.exe  c:\\temp\\suspicious.dll,RepeatAfterMe",
            "processCreationTime": "2021-01-26T20:31:32.9581596Z",
            "parentProcessId": 8420,
            "parentProcessCreationTime": "2021-01-26T20:31:32.9004163Z",
            "parentProcessFileName": "rundll32.exe",
            "parentProcessFilePath": "C:\\Windows\\System32",
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        },
        {
            "entityType": "File",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": "8563f95b2f8a284fc99da44500cd51a77c1ff36c",
            "sha256": "dc0ade0c95d6db98882bc8fa6707e64353cd6f7767ff48d6a81a6c2aef21c608",
            "fileName": "suspicious.dll",
            "filePath": "c:\\temp",
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        }
    ]
}
```
