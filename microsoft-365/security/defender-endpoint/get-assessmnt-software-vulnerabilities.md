---
title: Exportera bedömningar av säkerhetsproblem för programvara per enhet
description: API-svaret är per enhet och innehåller sårbar programvara som installeras på dina exponerade enheter samt alla kända säkerhetsproblem i dessa programvaruprodukter. Den här tabellen innehåller även information om operativsystemet, CVE-ID och allvarlighetsgradsinformation.
keywords: api, apis, exportutvärdering, per enhetsutvärdering, sårbarhetsutvärderingsrapport, enhetsbristbedömning, enhetsproblemrapport, säker konfigurationsutvärdering, säker konfigurationsrapport, utvärdering av programvarubrister, programsäkerhetsproblemsrapport, sårbarhetsrapport efter maskin,
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
ms.custom: api
ms.openlocfilehash: 951f78ba361a12e404a5cce2071f931eab30c43f
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689219"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a>Exportera bedömningar av säkerhetsproblem för programvara per enhet

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
Returnerar alla kända säkerhetsproblem i programvaran och deras information för alla enheter, per enhet.

Det finns olika API-anrop för att få olika typer av data. Eftersom mängden data kan vara mycket stor kan den hämtas på två sätt:

- [Exportera säkerhetsproblem med programvara, utvärdering av OData](#1-export-software-vulnerabilities-assessment-odata)  API:t hämtar alla data i organisationen som Json-svar efter OData-protokollet. Den här metoden är bäst _för små organisationer med mindre än 100 K-enheter._ Svaret är paginerat, så du kan använda \@ odata.nextLink-fältet från svaret för att hämta nästa resultat.

- [Exportera utvärdering av säkerhetsproblem för programvara via filer](#2-export-software-vulnerabilities-assessment-via-files) Med den här API-lösningen kan du hämta stora mängder data snabbare och mer tillförlitligt. Därför rekommenderas det för stora organisationer med fler än 100 K-enheter. Detta API hämtar alla data i organisationen som nedladdningsfiler. Svaret innehåller URL:er för att ladda ned alla data från Azure Storage. Med det här API:t kan du ladda ned alla dina data Azure Storage enligt följande:

  - Anropa API:t för att få en lista med hämtningsadresser med alla dina organisationsdata.

  - Ladda ned alla filer med hjälp av URL:er för nedladdning och bearbeta dina data som du vill.

Data som samlas in (med hjälp av _antingen OData_ eller _via_ filer) är den aktuella ögonblicksbilden av den aktuella statusen, och innehåller inte historiska data. För att kunna samla in historiska data måste kunderna spara data i sina egna datalagringar.

> [!Note]
>
> Om inget annat anges exporteras alla utvärderingsmetoder som **_listas för fullständig export_** **_och_** efter enhet (kallas även **_per enhet)._**

## <a name="1-export-software-vulnerabilities-assessment-odata"></a>1. Utvärdering av säkerhetsproblem med programvara (OData)

### <a name="11-api-method-description"></a>1.1 API-metodbeskrivning

Det här API-svaret innehåller alla data om installerad programvara per enhet. Returnerar en tabell med en post för varje unik kombination av DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.

#### <a name="limitations"></a>Begränsningar

>- Maximal sidstorlek är 200 000.
>
>- Prisbegränsningar för detta API är 30 samtal per minut och 1 000 samtal per timme.

### <a name="12-permissions"></a>1.2 Behörigheter

En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er för mer information.](apis-intro.md)

Behörighetstyp | Behörighet | Visningsnamn för behörighet
---|---|---
Program | Vulnerability.Read.All | \'Läsa sårbarhetsinformation om hot och sårbarhetshantering\'
Delegerat (arbets- eller skolkonto) | Sårbarhet.Läsa | \'Läsa sårbarhetsinformation om hot och sårbarhetshantering\'

### <a name="13-url"></a>1.3 URL

```http
GET /api/machines/SoftwareVulnerabilitiesByMachine
```

### <a name="14-parameters"></a>1.4 Parametrar

- pageSize (standard = 50 000) – antal resultat som svar
- $top – antal resultat som ska returneras (returnerar inte @odata.nextLink och därför inte alla data)

### <a name="15-properties"></a>1.5 Egenskaper
>
>[!Note]
>
>- Varje post motsvarar ungefär 1 kB data. Du bör ta med detta i beräkningen när du väljer rätt pageSize-parameter.
>
>- Vissa ytterligare kolumner kan returneras i svaret. Kolumnerna är tillfälliga och kan komma att tas bort. Använd bara de dokumenterade kolumnerna.
>
>- Egenskaperna som definieras i följande tabell anges i alfabetisk ordning, efter egenskaps-ID.  När du kör det här API:t returneras inte resultatet nödvändigtvis i samma ordning som anges i den här tabellen.
>

Egenskap (ID) | Datatyp | Beskrivning | Exempel på ett returnerat värde
:---|:---|:---|:---
CveId | sträng | Unikt ID tilldelat till säkerhetshålet under systemet för vanliga säkerhetsproblem och exponeringar (CVE). | CVE-2020-15992
CvssScore | sträng | CVSS-poäng för CVE. | 6.2
DeviceId | sträng | Unikt ID för enheten i tjänsten. | 9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1
DeviceName | sträng | Fullständigt kvalificerat domännamn (FQDN) för enheten. | johnlaptop.europe.contoso.com
DiskPaths  | \[Matrissträng\] | Disk bevis för att produkten är installerad på enheten. | [ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]
ExploitabilityLevel | sträng | Sårbarhetsnivån för detta sårbarhet (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit) | ExploitIsInKit
FirstSeenTimestamp | sträng | Första gången CVE för den här produkten sågs på enheten. | 2020-11-03 10:13:34.8476880
ID | sträng | Unikt ID för posten. | 123ABG55_573AG&mnp!
LastSeenTimestamp | sträng | Senaste gången CVE sågs på enheten. | 2020-11-03 10:13:34.8476880
OSPlatform | sträng | Operativsystemets plattform som körs på enheten. Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7. Mer information finns i Operativsystem och plattformar som stöds av TVM. | Windows10
RbacGroupName  | sträng | Den rollbaserade åtkomstkontrollgruppen (RBAC). Om enheten inte är tilldelad till någon RBAC-grupp kommer värdet att vara "Ej tilldelat". Om organisationen inte innehåller några RBAC-grupper blir värdet "Ingen". | Servrar
RekommendationReference | sträng | En referens till det rekommendations-ID som hör till den här programvaran. | va-_-microsoft-_-silverlight
RecommendedSecurityUpdate (valfritt) | sträng | Namn eller beskrivning av säkerhetsuppdateringen som tillhandahålls av programvaruleverantören för att hantera problemet. | Säkerhetsuppdateringar för april 2020
RecommendedSecurityUpdateId (valfritt) | sträng | Identifierare för tillämpliga säkerhetsuppdateringar eller identifierare för motsvarande vägledning eller kunskapsbas (KB) artiklar | 4550961
RegistryPaths  | \[Matrissträng\] | Register bevis för att produkten är installerad på enheten. | [ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]
SoftwareName | sträng | Namnet på programvaruprodukten. | chrome
SoftwareVendor | sträng | Namnet på programvaruleverantören. | google
SoftwareVersion | sträng | Versionsnummer för programvaran. | 81.0.4044.138
VulnerabilitySeverityLevel  | sträng | Allvarlighetsnivå tilldelad till säkerhetsrisken baserat på CVSS-poäng och dynamiska faktorer som påverkas av hotbilden. | Medel

### <a name="16-examples"></a>1.6 Exempel

#### <a name="161-request-example"></a>1.6.1 Exempel på begäran

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pageSize=5
```

#### <a name="162-response-example"></a>1.6.2 Svarsexempel

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetVulnerability)",
    "value": [
        {
            "id": "00044f612345baf759462dbe6db733b6a9c59ab4_edge_10.0.17763.1637__",
            "deviceId": "00044f612345daf756462bde6bd733b9a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d089e79bdfa178eabfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "edge",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-edge"
        },
        {
            "id": "00044f912345baf756462bde6db733b9a9c56ad4_.net_framework_4.0.0.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e79bdfa178eabfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-.net_framework"
        },
        {
            "id": "00044f912345baf756462dbe6db733d6a9c59ab4_system_center_2012_endpoint_protection_4.10.209.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eed80b089e79bdfa178eadfa25e8be6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-system_center_2012_endpoint_protection"
        },
        {
            "id": "00044f612345bdaf759462dbe6bd733b6a9c59ab4_onedrive_20.245.1206.2__",
            "deviceId": "00044f91234daf759492dbe6bd733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_189663d45612eed224b2be2f5ea3142729e63f16a.DomainPII_21eed80b086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "onedrive",
            "softwareVersion": "20.245.1206.2",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_USERS\\S-1-5-21-2944539346-1310925172-2349113062-1001\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-onedrive"
        },
        {
            "id": "00044f912345daf759462bde6db733b6a9c56ab4_windows_10_10.0.17763.1637__",
            "deviceId": "00044f912345daf756462dbe6db733d6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eeb224d2be2f5ea3142729e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-windows_10"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-vulnerabilities-assessment-via-files"></a>2. Exportera utvärdering av säkerhetsproblem för programvara (via filer)

### <a name="21-api-method-description"></a>2.1 API-metodbeskrivning

Det här API-svaret innehåller alla data om installerad programvara per enhet. Returnerar en tabell med en post för varje unik kombination av DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.

#### <a name="212-limitations"></a>2.1.2 Begränsningar

Prisbegränsningar för detta API är 5 samtal per minut och 20 samtal per timme.

### <a name="22-permissions"></a>2.2 Behörigheter

En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er för mer information.](apis-intro.md)

Behörighetstyp | Behörighet | Visningsnamn för behörighet
---|---|---
Program | Vulnerability.Read.All | \'Läsa sårbarhetsinformation om hot och sårbarhetshantering\'
Delegerat (arbets- eller skolkonto) | Sårbarhet.Läsa | \'Läsa sårbarhetsinformation om hot och sårbarhetshantering\'

### <a name="23-url"></a>2.3 URL

```http
GET /api/machines/SoftwareVulnerabilitiesExport
```

### <a name="24-parameters"></a>2.4 Parametrar

- sasValidHours – Antalet timmar som hämtnings-URL:erna ska vara giltiga i (högst 24 timmar)

### <a name="25-properties"></a>2.5 Egenskaper

>[!Note]
>
>- Filerna är gzip komprimerade & I multiline Json-format.
>
>- URL-adresser för nedladdning är endast giltiga i 3 timmar. annars kan du använda parametern.
>
>- För maximal nedladdningshastighet för dina data kan du se till att du laddar ned från samma Azure-region som dina data finns i.
>

>[!Note]
>
>- Varje post motsvarar ungefär 1 kB data. Du bör ta med detta i beräkningen när du väljer rätt pageSize-parameter.
>
>- Vissa ytterligare kolumner kan returneras i svaret. Kolumnerna är tillfälliga och kan komma att tas bort. Använd bara de dokumenterade kolumnerna.
>

Egenskap (ID) | Datatyp | Beskrivning | Exempel på ett returnerat värde
:---|:---|:---|:---
Exportera filer | \[matrissträng\]  | En lista med hämtnings-URL:er för filer som innehåller den aktuella ögonblicksbilden av organisationen. | [  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]
GeneratedTime | sträng | Tidpunkten då exporten skapades. | 2021-05-20T08:00:00Z

### <a name="26-examples"></a>2.6 Exempel

#### <a name="261-request-example"></a>2.6.1 Exempel på begäran

```http
GET https://api-us.securitycenter.contoso.com/api/machines/SoftwareVulnerabilitiesExport
```

#### <a name="262-response-example"></a>2.6.2 Svarsexempel

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c002.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a>Se även

- [Exportera utvärderingsmetoder och egenskaper per enhet](get-assessmnt-1methods-properties.md)

- [Exportera utvärdering av säker konfiguration per enhet](get-assessmnt-secure-cfg.md)

- [Exportera utvärdering av programvaruinventering per enhet](get-assessmnt-software-inventory.md)

Andra relaterade

- [Riskbaserade hot & hantering av säkerhetsrisker](next-gen-threat-and-vuln-mgt.md)

- [Svagheter i organisationen](tvm-weaknesses.md)
