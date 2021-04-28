---
title: Lista alla åtgärder
description: Returnerar information om alla åtgärder.
keywords: apis, remediation, remediation api, get, remediation tasks,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ac4a777136dcdfc5d7ab61ddc8d496b7452f69e2
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061159"
---
# <a name="list-all-remediation-activities"></a>Lista alla åtgärder

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API-beskrivning

Returnerar information om alla åtgärder.

[Läs mer om åtgärder](tvm-remediation.md).

**URL:** HÄMTA: /api/remediationTasks

**Egenskapsinformation**

Egenskap (id) | Datatyp | Beskrivning | Exempel på ett returnerat värde
:---|:---|:---|:---
kategori | Sträng | Kategori för åtgärdsaktiviteten (konfiguration av programvara/säkerhet) | Programvara
completerEmail | Sträng | Om åtgärdsaktiviteten har slutförts manuellt av någon innehåller den här kolumnen deras e-postadress | null
completerId | Sträng | Om åtgärdsaktiviteten har slutförts manuellt av någon innehåller den här kolumnen deras objekt-ID | null
completionMethod | Sträng | En åtgärdsaktivitet kan slutföras "automatiskt" (om alla enheter är korrigerade) eller "manuellt" av en person som väljer "markera som slutförd" | Automatisk
createdOn | DateTime | Tidpunkten då den här åtgärdsaktiviteten skapades | 2021-01-12T18:54:11.5499478Z
beskrivning | Sträng | Beskrivning av den här åtgärdsaktiviteten | Uppdatera Chrome till en senare version för att minimera kända 1248 säkerhetsproblem som påverkar dina enheter.
dueOn | DateTime | Förfallodatum som skapare uppsättningen för den här åtgärdsaktiviteten | 2021-01-13T00:00:00Z
fixedDevices | . | Antalet enheter som har åtgärdats | 2
id | Sträng | ID för den här åtgärdsaktiviteten | 097d9735-5479-4899-b1b7-77398899df92
nameId | Sträng | Relaterade produktnamn | chrome
prioritet | Sträng | Prioritet för skaparuppsättningen för den här åtgärdsaktiviteten (Hög\Medel\Låg) | Hög
productId | Sträng | Relaterade produkt-ID | google-_-chrome
productivityImpactRemediationType | Sträng | Några konfigurationsändringar kunde endast begäras för enheter utan påverkan från användare. Det här värdet anger valet mellan "alla exponerade enheter" eller "endast enheter utan påverkan från användare". | AllExposedAssets
rbacGroupNames | Sträng | Gruppnamn för relaterade enheter | [ "Windows-servrar", "Windows 10" ]
recommendedProgram | Sträng | Rekommenderat program att uppgradera till | null
recommendedVendor | Sträng | Rekommenderad leverantör att uppgradera till | null
recommendedVersion | Sträng | Rekommenderad version att uppdatera/uppgradera till | null
relatedComponent | Sträng | Relaterad komponent i den här åtgärdsaktiviteten (som liknar den relaterade komponenten för en säkerhetsrekommendationer) | Google Chrome
requesterEmail | Sträng | E-postadress skapad | globaladmin@UserName.contoso.com
requesterId | Sträng | Creator-objekt-ID | r647211f-2e16-43f2-a480-16ar3a2a796r
requesterNotes | Sträng | Anteckningarna (fri text) som skaparen har lagt till för den här åtgärdsaktiviteten | null
scid | Sträng | SCID för relaterad säkerhetsrekommendationer | null
status | Sträng | Status för åtgärdsaktivitet (Aktiv/slutförd) | Aktiv
statusLastModifiedOn | DateTime | Datum när statusfältet uppdaterades | 2021-01-12T18:54:11.5499487Z
targetDevices | Long | Antal exponerade enheter som denna åtgärd gäller för | 43
rubrik | Sträng | Rubrik för den här åtgärdsaktiviteten | Uppdatera Google Chrome
skriv | Sträng | Åtgärdstyp | Uppdatera
vendorId | Sträng | Relaterade leverantörsnamn | google

## <a name="example"></a>Exempel

**Exempel på** förfrågan

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

**Svarsexempel**

```json
{
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks",
    "value": [
        {
            "id": "03942ef5-aewb-4w6e-b555-d6a97013844w",
            "title": "Update Microsoft Silverlight",
            "createdOn": "2021-02-10T13:20:36.4718166Z",
            "requesterId": "65548a1d-ef00-4a7a-8d19-1b967b5c36f4",
            "requesterEmail": "user1@contoso.com",
            "status": "Active",
            "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z",
            "description": "Update Silverlight to a later version  to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.  ",
            "relatedComponent": "Microsoft Silverlight",
            "targetDevices": 18511,
            "rbacGroupNames": [
                "UnassignedGroup",
                "hhh"
            ],
            "fixedDevices": 2866,
            "requesterNotes": "test",
            "dueOn": "2021-02-11T00:00:00Z",
            "category": "Software",
            "productivityImpactRemediationType": null,
            "priority": "Medium",
            "completionMethod": null,
            "completerId": null,
            "completerEmail": null,
            "scid": null,
            "type": "Update",
            "productId": "microsoft-_-silverlight",
            "vendorId": "microsoft",
            "nameId": "silverlight",
            "recommendedVersion": null,
            "recommendedVendor": null,
            "recommendedProgram": null
        }
    ]
}
```

## <a name="see-also"></a>Se även

- [Åtgärdsmetoder och egenskaper](get-remediation-methods-properties.md)

- [Få en åtgärdsaktivitet efter ID](get-remediation-one-activity.md)

- [Lista över exponerade enheter med en åtgärdsaktivitet](get-remediation-exposed-devices-activities.md)

- [Riskbaserade hot & sårbarhetshantering](next-gen-threat-and-vuln-mgt.md)

- [Svagheter i organisationen](tvm-weaknesses.md)
