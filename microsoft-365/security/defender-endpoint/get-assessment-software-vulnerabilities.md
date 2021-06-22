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
ms.openlocfilehash: 87fb5c62b520168a686cc0b95a321becdd4656ba
ms.sourcegitcommit: 4d26a57c37ff7efbb8d235452c78498b06a59714
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53052969"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a>Exportera bedömningar av säkerhetsproblem för programvara per enhet

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

>
Returnerar alla kända säkerhetsproblem i programvaran och deras information för alla enheter, per enhet.

Det finns olika API-anrop för att få olika typer av data. Eftersom mängden data kan vara mycket stor kan den hämtas på två sätt:

1. [Exportera säkerhetsproblem för programvara, **bedömning JSON-svar**](#1-export-software-vulnerabilities-assessment-json-response)  API:t hämtar alla data i organisationen som Json-svar. Den här metoden är bäst _för små organisationer med mindre än 100 K-enheter._ Svaret är paginerat, så du kan använda \@ odata.nextLink-fältet från svaret för att hämta nästa resultat.

2. [Exportera utvärdering av säkerhetsproblem för programvara **via filer**](#2-export-software-vulnerabilities-assessment-via-files) Med den här API-lösningen kan du hämta stora mängder data snabbare och mer tillförlitligt. Via-filer rekommenderas för stora organisationer med fler än 100 K-enheter. Detta API hämtar alla data i organisationen som nedladdningsfiler. Svaret innehåller URL:er för att ladda ned alla data från Azure Storage. Med det här API:t kan du ladda ned alla dina data Azure Storage enligt följande:

   - Anropa API:t för att få en lista med hämtningsadresser med alla dina organisationsdata.

   - Ladda ned alla filer med hjälp av URL:er för nedladdning och bearbeta dina data som du vill.

3. [Delta i export av säkerhetsproblem vid **bedömning av JSON-svar**](#3-delta-export-software-vulnerabilities-assessment-json-response)  Returnerar en tabell med en post för varje unik kombination av: DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId och EventTimestamp.
API:t hämtar data i organisationen som Json-svar. Svaret är paginerat, så du kan använda fältet @odata.nextLink från svaret för att hämta nästa resultat. <br><br> Till skillnad från den fullständiga utvärderingen av säkerhetsproblem för programvara (JSON-svar) – som används för att erhålla en hel ögonblicksbild av säkerhetsproblem i programvarans bedömning av organisationen per enhet – används deltaexport-API-anropet för att bara hämta de ändringar som har inträffat mellan ett valt datum och dagens datum (delta-API-anropet). I stället för att få en fullständig export med en stor mängd data varje gång får du bara specifik information om nya, korrigerade och uppdaterade svagheter. Deltaexportera JSON-svars-API-anrop kan också användas för att beräkna olika KPI:er, till exempel "hur många säkerhetsproblem har åtgärdats?" eller "hur många nya säkerhetsproblem lades till i organisationen?" <br><br> Eftersom deltaexporten av JSON-svars-API:t för svagheter i programvaran returnerar data endast för ett måldatumintervall anses det inte vara _en fullständig export._

Data som samlas in (med hjälp av _Antingen Json-svar_ eller _via_ filer) är den aktuella ögonblicksbilden av den aktuella statusen, och innehåller inte historiska data. För att kunna samla in historiska data måste kunderna spara data i sina egna datalagringar.

> [!Note]
>
> Om inget annat anges exporteras alla utvärderingsmetoder som **_listas för fullständig export_** **_och_** efter enhet (kallas även **_per enhet)._**

## <a name="1-export-software-vulnerabilities-assessment-json-response"></a>1. Exportera utvärdering av säkerhetsproblem för programvara (JSON-svar)

### <a name="11-api-method-description"></a>1.1 API-metodbeskrivning

Det här API-svaret innehåller alla data om installerad programvara per enhet. Returnerar en tabell med en post för varje unik kombination av DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.

#### <a name="111-limitations"></a>1.1.1 Begränsningar

- Maximal sidstorlek är 200 000.

- Prisbegränsningar för detta API är 30 samtal per minut och 1 000 samtal per timme.

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

>[!Note]
>
>- Varje post är cirka 1 kB data. Du bör ta med detta i beräkningen när du väljer rätt pageSize-parameter.
>
>- Vissa ytterligare kolumner kan returneras i svaret. Kolumnerna är tillfälliga och kan komma att tas bort. Använd bara de dokumenterade kolumnerna.
>
>- Egenskaperna som definieras i följande tabell anges i alfabetisk ordning, efter egenskaps-ID.  När du kör det här API:t returneras inte resultatet nödvändigtvis i samma ordning som anges i den här tabellen.

<br/>

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
OSPlatform | sträng | Operativsystemets plattform som körs på enheten. Den här egenskapen anger specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7. Mer information finns i Operativsystem och plattformar som stöds av TVM. | Windows10
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

## <a name="3-delta-export-software-vulnerabilities-assessment-json-response"></a>3. Sårbarhetsbedömning av deltaexportprogramvara (JSON-svar)

### <a name="31-api-method-description"></a>3.1 API-metodbeskrivning

Returnerar en tabell med en post för varje unik kombination av DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId. API:t hämtar data i organisationen som Json-svar. Svaret är paginerat, så du kan använda fältet @odata.nextLink från svaret för att hämta nästa resultat. Till skillnad från den fullständiga utvärderingen av säkerhetsproblem för programvara (JSON-svar), som används för att erhålla en hel ögonblicksbild av säkerhetsproblem i programvarans bedömning av organisationen efter enhet, används deltaexports-JSON-svars-API-anropet för att bara hämta ändringar som har skett mellan ett valt datum och dagens datum (delta-API-anropet). I stället för att få en fullständig export med en stor mängd data varje gång får du bara specifik information om nya, korrigerade och uppdaterade svagheter. Deltaexportera JSON-svars-API-anrop kan också användas för att beräkna olika KPI:er, till exempel "hur många säkerhetsproblem har åtgärdats?" eller "hur många nya säkerhetsproblem lades till i organisationen?"

>[!NOTE]
>
>Vi rekommenderar starkt att du använder säkerhetsproblemen vid export av programvara genom enhets-API-anrop minst en gång i veckan, och detta ytterligare säkerhetsproblem vid export av programvara ändras efter enhet (delta) API-anrop alla övriga dagar i veckan.  Till skillnad från andra JSON-svars-API:er för utvärderingar är "deltaexporten" inte en fullständig export. Deltaexporten innehåller bara de ändringar som har skett mellan ett valt datum och dagens datum (API-anropet "delta").

#### <a name="311-limitations"></a>3.1.1 Begränsningar

- Maximal sidstorlek är 200 000.

- Parametern sinceTime har högst 14 dagar.

- Prisbegränsningar för detta API är 30 samtal per minut och 1 000 samtal per timme.

### <a name="32-permissions"></a>3.2 Behörigheter

En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er för mer information.](apis-intro.md)

Behörighetstyp | Behörighet | Visningsnamn för behörighet
---|---|---
Program | Vulnerability.Read.All | "Läs sårbarhetsinformation för hot och sårbarhetshantering"
Delegerat (arbets- eller skolkonto) | Sårbarhet.Läsa | "Läs sårbarhetsinformation för hot och sårbarhetshantering"

### <a name="33-url"></a>3.3 URL

```http
GET /api/machines/SoftwareVulnerabilityChangesByMachine 
```

### <a name="34-parameters"></a>3.4 Parametrar

- sinceTime (obligatoriskt) – Data mellan en vald tid och idag.
- pageSize (standard = 50 000) – antal resultat som svar
- $top – antal resultat som ska returneras (returnerar inte @odata.nextLink och därför inte alla data)

### <a name="35-properties"></a>3.5 Egenskaper

Varje returnerad post innehåller alla data från säkerhetsproblem i exportprogramvaran som bedömer efter enhets-API, plus ytterligare två fält: _**EventTimestamp**_ och _**Status.**_

>[!NOTE]
>- Vissa ytterligare kolumner kan returneras i svaret. Kolumnerna är tillfälliga och kan komma att tas bort, så använd bara de dokumenterade kolumnerna.
>
>- Egenskaperna som definieras i följande tabell anges i alfabetisk ordning, efter egenskaps-ID.  När du kör det här API:t returneras inte resultatet nödvändigtvis i samma ordning som anges i den här tabellen.
<br><br/>

Egenskap (ID) | Datatyp | Beskrivning | Exempel på returnerat värde
:---|:---|:---|:---
CveId | sträng | Unikt ID tilldelat till säkerhetshålet under systemet för vanliga säkerhetsproblem och exponeringar (CVE). | CVE-2020-15992  
CvssScore | sträng | CVSS-poäng för CVE. | 6.2  
DeviceId | sträng | Unikt ID för enheten i tjänsten. | 9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1  
DeviceName | sträng | Fullständigt kvalificerat domännamn (FQDN) för enheten. | johnlaptop.europe.contoso.com  
DiskPaths | Matris[sträng] | Disk bevis för att produkten är installerad på enheten. | [ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]  
EventTimestamp | Sträng | Tidpunkten då deltahändelsen hittades. | 2021-01-11T11:06:08.291Z
ExploitabilityLevel | sträng | Sårbarhetsnivån för detta sårbarhet (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit) | ExploitIsInKit  
FirstSeenTimestamp | sträng | Första gången CVE för den här produkten sågs på enheten. | 2020-11-03 10:13:34.8476880  
ID | sträng | Unikt ID för posten. | 123ABG55_573AG&mnp!  
LastSeenTimestamp | sträng | Senaste gången CVE sågs på enheten. | 2020-11-03 10:13:34.8476880  
OSPlatform | sträng | Operativsystemets plattform som körs på enheten. Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7. Mer information finns i Operativsystem och plattformar som stöds av TVM. | Windows10  
RbacGroupName | sträng | Den rollbaserade åtkomstkontrollgruppen (RBAC). Om enheten inte är tilldelad till någon RBAC-grupp kommer värdet att vara "Ej tilldelat". Om organisationen inte innehåller några RBAC-grupper blir värdet "Ingen". | Servrar  
RekommendationReference | sträng | En referens till det rekommendations-ID som hör till den här programvaran. | va--microsoft--silverlight  
RecommendedSecurityUpdate  | sträng | Namn eller beskrivning av säkerhetsuppdateringen som tillhandahålls av programvaruleverantören för att hantera problemet. | Säkerhetsuppdateringar för april 2020  
RecommendedSecurityUpdateId  | sträng | Identifierare för tillämpliga säkerhetsuppdateringar eller identifierare för motsvarande vägledning eller kunskapsbas (KB) artiklar | 4550961  
RegistryPaths  | Matris[sträng] | Register bevis för att produkten är installerad på enheten. | [ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Google Chrome" ]  
SoftwareName | sträng | Namnet på programvaruprodukten. | chrome  
SoftwareVendor | sträng | Namnet på programvaruleverantören. | google  
SoftwareVersion | sträng | Versionsnummer för programvaran. | 81.0.4044.138  
Status | Sträng | **Ny**   (för en ny säkerhetsrisk som introducerades på en enhet)  (1) **Åtgärdat**(om det här problemet inte finns längre på   enheten, vilket innebär att det har åtgärdats). (2)  **Uppdaterad**   (om ett sårbarhetsproblem på en enhet har ändrats. De möjliga ändringarna är: CVSS-poäng, sårbarhetsnivå, allvarlighetsnivå, DiskPaths, RegistryPaths, RecommendedSecurityUpdate). | Åtgärdat
VulnerabilitySeverityLevel | sträng | Allvarlighetsnivå tilldelad till säkerhetsrisken baserat på CVSS-poäng och dynamiska faktorer som påverkas av hotbilden. | Medel  

#### <a name="clarifications"></a>Förtydligande

- Om programvaran uppdaterades från version 1.0 till version 2.0 och båda versionerna exponeras för CVE-A, får du 2 separata händelser:  
   1. Åtgärdat – CVE-A i version 1.0 har åtgärdats  
   1. Nytt – CVE-A på version 2.0 lades till

- Om ett specifikt problem (till exempel CVE-A) först sågs vid en viss tidpunkt (till exempel 10 januari) på programvara med version 1.0, och några dagar senare uppdaterades programvaran till version 2.0 som också exponerades för samma CVE-A, får du dessa två separata händelser:  
   1. Åtgärdat – CVE-X, FirstSeenTimestamp 10 januari, version 1,0.  
   1. Nytt – CVE-X, FirstSeenTimestamp 10 januari, version 2.0.

### <a name="36-examples"></a>3.6 Exempel

#### <a name="361-request-example"></a>3.6.1 Exempel på begäran

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilityChangesByMachine?pageSize=5&sinceTime=2021-05-19T18%3A35%3A49.924Z
```

#### <a name="362-response-example"></a>3.6.2 Svarsexempel

```json
{ 
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.DeltaAssetVulnerability)", 
    "value": [ 
        { 
            "id": "008198251234544f7dfa715e278d4cec0c16c171_chrome_87.0.4280.88__", 
            "deviceId": "008198251234544f7dfa715e278b4cec0c19c171",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_1c8fee370690ca24b6a0d3f34d193b0424943a8b8.DomainPII_0dc1aee0fa366d175e514bd91a9e7a5b2b07ee8e.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "google", 
            "softwareName": "chrome", 
            "softwareVersion": "87.0.4280.88", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Google Chrome" 
            ], 
            "lastSeenTimestamp": "2021-01-04 00:29:42", 
            "firstSeenTimestamp": "2020-11-06 03:12:44", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-google-_-chrome", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "00e59c61234533860738ecf488eec8abf296e41e_onedrive_20.64.329.3__", 
            "deviceId": "00e56c91234533860738ecf488eec8abf296e41e",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_82c13a8ad8cf3dbaf7bf34fada9fa3aebc124116.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.18363.1256", 
            "osArchitecture": "x64", 
            "softwareVendor": "microsoft", 
            "softwareName": "onedrive", 
            "softwareVersion": "20.64.329.3", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [], 
            "registryPaths": [ 
                "HKEY_USERS\\S-1-5-21-2127521184-1604012920-1887927527-24918864\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe" 
            ], 
            "lastSeenTimestamp": "2020-12-11 19:49:48", 
            "firstSeenTimestamp": "2020-12-07 18:25:47", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-microsoft-_-onedrive", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "01aa8c73095bb12345918663f3f94ce322107d24_firefox_83.0.0.0_CVE-2020-26971_", 
            "deviceId": "01aa8c73065bb12345918693f3f94ce322107d24", 
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_42684eb981bea2d670027e7ad2caafd3f2b381a3.DomainPII_21eed80b086e76dbfa178eabfa25e8de9acfa346.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "mozilla", 
            "softwareName": "firefox", 
            "softwareVersion": "83.0.0.0", 
            "cveId": "CVE-2020-26971", 
            "vulnerabilitySeverityLevel": "High", 
            "recommendedSecurityUpdate": "193220", 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Mozilla Firefox\\firefox.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Mozilla Firefox 83.0 (x86 en-US)" 
            ], 
            "lastSeenTimestamp": "2021-01-05 17:04:30", 
            "firstSeenTimestamp": "2020-05-06 12:42:19", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-mozilla-_-firefox", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "026f0fcb12345fbd2decd1a339702131422d362e_project_16.0.13701.20000__", 
            "deviceId": "029f0fcb13245fbd2decd1a336702131422d392e", 
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_a5706750acba75f15d69cd17f4a7fcd268d6422c.DomainPII_f290e982685f7e8eee168b4332e0ae5d2a069cd6.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "microsoft", 
            "softwareName": "project", 
            "softwareVersion": "16.0.13701.20000", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\ProjectProRetail - en-us" 
            ], 
            "lastSeenTimestamp": "2021-01-03 23:38:03", 
            "firstSeenTimestamp": "2019-08-01 22:56:12", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-microsoft-_-project", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "038df381234510b357ac19d0113ef622e4e212b3_chrome_81.0.4044.138_CVE-2020-16011_", 
            "deviceId": "038df381234510d357ac19b0113ef922e4e212b3",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_365f5c0bb7202c163937dad3d017969b2d760eb4.DomainPII_29596a43a2ef2bbfa00f6a16c0cb1d108bc63e32.DomainPII_3c5fefd2e6fda2f36257359404f6c1092aa6d4b8.net", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.18363.1256", 
            "osArchitecture": "x64", 
            "softwareVendor": "google", 
            "softwareName": "chrome", 
            "softwareVersion": "81.0.4044.138", 
            "cveId": "CVE-2020-16011", 
            "vulnerabilitySeverityLevel": "High", 
            "recommendedSecurityUpdate": "ADV 200002", 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{C4EBFDFD-0C55-3E5F-A919-E3C54949024A}" 
            ], 
            "lastSeenTimestamp": "2020-12-10 22:45:41", 
            "firstSeenTimestamp": "2020-07-26 02:13:43", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-google-_-chrome", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        } 
    ], 
    "@odata.nextLink": "https://wpatdadi-eus-stg.cloudapp.net/api/machines/SoftwareVulnerabilitiesTimeline?sincetime=2021-01-11&pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9" 
} 
```

## <a name="see-also"></a>Se även

- [Exportera utvärderingsmetoder och egenskaper per enhet](get-assessment-methods-properties.md)

- [Exportera utvärdering av säker konfiguration per enhet](get-assessment-secure-config.md)

- [Exportera utvärdering av programvaruinventering per enhet](get-assessment-software-inventory.md)

Andra relaterade

- [Riskbaserade hot & hantering av säkerhetsrisker](next-gen-threat-and-vuln-mgt.md)

- [Svagheter i organisationen](tvm-weaknesses.md)
