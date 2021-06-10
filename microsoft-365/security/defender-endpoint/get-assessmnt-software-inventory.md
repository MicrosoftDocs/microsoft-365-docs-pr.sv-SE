---
title: Exportera utvärdering av programvaruinventering per enhet
description: Returnerar en tabell med en post för varje unik kombination av DeviceId, SoftwareVendor, SoftwareName och SoftwareVersion.
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
ms.openlocfilehash: 5663a17de2e601c506b4d1b9ac44eaab6ae6245f
ms.sourcegitcommit: 83df0be7144c9c5d606f70b4efa65369e86693d2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52778361"
---
# <a name="export-software-inventory-assessment-per-device"></a>Exportera utvärdering av programvaruinventering per enhet

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
Det finns olika API-anrop för att få olika typer av data. Eftersom mängden data kan vara mycket stor kan den hämtas på två sätt:

- [Exportera utvärdering av programvaruinventering **av OData**](#1-export-software-inventory-assessment-odata)  API:t hämtar alla data i organisationen som Json-svar efter OData-protokollet. Den här metoden är bäst _för små organisationer med mindre än 100 K-enheter._ Svaret är paginerat, så du kan använda \@ odata.nextLink-fältet från svaret för att hämta nästa resultat.

- [Exportera utvärdering av programvaruinventering **via filer**](#2-export-software-inventory-assessment-via-files)  Med den här API-lösningen kan du hämta stora mängder data snabbare och mer tillförlitligt. Därför rekommenderas det för stora organisationer med fler än 100 K-enheter. Detta API hämtar alla data i organisationen som nedladdningsfiler. Svaret innehåller URL:er för att ladda ned alla data från Azure Storage. Med det här API:t kan du ladda ned alla dina data Azure Storage enligt följande:

  - Anropa API:t för att få en lista med hämtningsadresser med alla dina organisationsdata.

  - Ladda ned alla filer med hjälp av URL:er för nedladdning och bearbeta dina data som du vill.

Data som samlas in (med hjälp av _antingen OData_ eller _via_ filer) är den aktuella ögonblicksbilden av den aktuella statusen, och innehåller inte historiska data. För att kunna samla in historiska data måste kunderna spara data i sina egna datalagringar.

> [!Note]
>
> Om inget annat anges exporteras alla utvärderingsmetoder som **_listas för fullständig export_** **_och_** efter enhet (kallas även **_per enhet)._**

## <a name="1-export-software-inventory-assessment-odata"></a>1. Exportera utvärdering av programvara för lager (OData)

### <a name="11-api-method-description"></a>1.1 API-metodbeskrivning

Det här API-svaret innehåller alla data om installerad programvara per enhet. Returnerar en tabell med en post för varje unik kombination av DeviceId, SoftwareVendor, SoftwareName och SoftwareVersion.

#### <a name="limitations"></a>Begränsningar

- Maximal sidstorlek är 200 000.

- Prisbegränsningar för detta API är 30 samtal per minut och 1 000 samtal per timme.

### <a name="12-permissions"></a>1.2 Behörigheter

En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er för mer information.](apis-intro.md)

Behörighetstyp | Behörighet | Visningsnamn för behörighet
---|---|---
Program | Software.Read.All | \'Läsa sårbarhetsinformation om hot och sårbarhetshantering\'
Delegerat (arbets- eller skolkonto) | Software.Read | \'Läsa sårbarhetsinformation om hot och sårbarhetshantering\'

### <a name="13-url"></a>1.3 URL

```http
GET /api/machines/SoftwareInventoryByMachine
```

### <a name="14-parameters"></a>1.4 Parametrar

- pageSize (standard = 50 000) – antal resultat som svar.

- $top – antal resultat som ska returneras (returnerar inte @odata.nextLink och därför inte alla data)

### <a name="15-properties"></a>1.5 Egenskaper

>[!NOTE]
>
>-Varje post är cirka 0,5 kB data. Du bör ta med detta i beräkningen när du väljer rätt pageSize-parameter.

>-Egenskaperna som definieras i följande tabell anges i alfabetisk ordning, efter egenskaps-ID. När du kör det här API:t returneras inte resultatet nödvändigtvis i samma ordning som anges i den här tabellen.
>
>-Några ytterligare kolumner kan returneras i svaret. Kolumnerna är tillfälliga och kan komma att tas bort. Använd bara de dokumenterade kolumnerna.

Egenskap (ID) | Datatyp | Beskrivning | Exempel på ett returnerat värde
:---|:---|:---|:---
DeviceId | sträng | Unikt ID för enheten i tjänsten. | 9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1
DeviceName | sträng | Fullständigt kvalificerat domännamn (FQDN) för enheten. | johnlaptop.europe.contoso.com
DiskPaths | Matris[sträng]  | Disk bevis för att produkten är installerad på enheten. | [ "C: \\ Program files (x86) \\ Microsoft \\ Silverlight \\ Application \\silverlight.exe" ]
EndOfSupportDate | sträng | Datumet då supporten för den här programvaran har eller kommer att upphöra. | 2020-12-30
EndOfSupportStatus | sträng | Supportstatusen avslutas. Kan innehålla följande möjliga värden: Ingen, EOS-version, Kommande EOS-version, EOS-programvara, kommande EOS-programvara. | Kommande EOS
ID | sträng | Unikt ID för posten. | 123ABG55_573AG&mnp!
NumberOfWeaknesses | int | Antal svagheter på den här programvaran på den här enheten | 3
OSPlatform | sträng | Operativsystemets plattform som körs på enheten. Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7. Mer information finns i Operativsystem och plattformar som stöds av TVM. | Windows10
RbacGroupName | sträng | Den rollbaserade åtkomstkontrollgruppen (RBAC). Om enheten inte är tilldelad till någon RBAC-grupp kommer värdet att vara "Ej tilldelat". Om organisationen inte innehåller några RBAC-grupper blir värdet "Ingen". | Servrar
RegistryPaths | Matris[sträng] | Register bevis för att produkten är installerad på enheten. | [ "HKEY_LOCAL_MACHINE \\ PROGRAMVARA \\ WOW6432Node \\ Microsoft Windows \\ \\ CurrentVersion Avinstallera Microsoft \\ \\ Silverlight" ]
SoftwareFirstSeenTimestamp | sträng | Första gången programvaran sågs på enheten. | 2019-04-07 02:06:47
SoftwareName | sträng | Namnet på programvaruprodukten. | Silverlight
SoftwareVendor | sträng | Namnet på programvaruleverantören. | microsoft
SoftwareVersion | sträng | Versionsnummer för programvaran. | 81.0.4044.138

### <a name="16-examples"></a>1.6 Exempel

#### <a name="161-request-example"></a>1.6.1 Exempel på begäran

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pageSize=5  &sinceTime=2021-05-19T18%3A35%3A49.924Z 
```

#### <a name="162-response-example"></a>1.6.2 Svarsexempel

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(contoso.windowsDefenderATP.api.AssetSoftware)",
    "value": [
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "numberOfWeaknesses": 58,
            "diskPaths": [],
            "registryPaths": [],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "Upcoming EOS Version",
            "endOfSupportDate": "2021-05-11T00:00:00+00:00"
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eed80d086e79bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.7.214.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765ddaf71234bde6bd733d6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178aedfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "configuration_manager",
            "softwareVersion": "5.0.8634.1000",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{B7D3A842-E826-4542-B39B-1D883264B279}"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f38765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0yNS8wMjAwLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-inventory-assessment-via-files"></a>2. Exportera utvärdering av programvara för lager (via filer)

### <a name="21-api-method-description"></a>2.1 API-metodbeskrivning

Det här API-svaret innehåller alla data om installerad programvara per enhet. Returnerar en tabell med en post för varje unik kombination av DeviceId, SoftwareVendor, SoftwareName och SoftwareVersion.

#### <a name="211-limitations"></a>2.1.1 Begränsningar

Prisbegränsningar för detta API är 5 samtal per minut och 20 samtal per timme.

### <a name="22-permissions"></a>2.2 Behörigheter

En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er för mer information.](apis-intro.md)

Behörighetstyp | Behörighet | Visningsnamn för behörighet
---|---|---
Program | Software.Read.All | \'Läsa sårbarhetsinformation om hot och sårbarhetshantering\'
Delegerat (arbets- eller skolkonto) | Software.Read | \'Läsa sårbarhetsinformation om hot och sårbarhetshantering\'

### <a name="23-url"></a>2.3 URL

```http
GET /api/machines/SoftwareInventoryExport
```

### <a name="parameters"></a>Parametrar

- sasValidHours – Antalet timmar som hämtnings-URL:erna ska vara giltiga i (högst 24 timmar)

### <a name="25-properties"></a>2.5 Egenskaper

>[!Note]
>
>- Filerna är gzip komprimerade & I multiline Json-format.
>
>- Url:erna för nedladdning är endast giltiga i 3 timmar. Annars kan du använda parametern.
>
>_ För maximal nedladdningshastighet för dina data kan du se till att du laddar ned från samma Azure-region som dina data finns i.
>
Egenskap (ID) | Datatyp | Beskrivning | Exempel på ett returnerat värde
:---|:---|:---|:---
Exportera filer | \[matrissträng\] | En lista över hämtnings-URL:er för filer som innehåller den aktuella ögonblicksbilden av organisationen | [  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]
GeneratedTime | sträng | Tidpunkten då exporten skapades. | 2021-05-20T08:00:00Z ]

### <a name="26-examples"></a>2.6 Exempel

#### <a name="261-request-example"></a>2.6.1 Exempel på begäran

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryExport
```

#### <a name="262-response-example"></a>2.6.2 Svarsexempel

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a>Se även

- [Exportera utvärderingsmetoder och egenskaper per enhet](get-assessmnt-1methods-properties.md)

- [Exportera utvärdering av säker konfiguration per enhet](get-assessmnt-secure-cfg.md)

- [Exportera bedömningar av säkerhetsproblem för programvara per enhet](get-assessmnt-software-vulnerabilities.md)

Andra relaterade

- [Riskbaserade hot & hantering av säkerhetsrisker](next-gen-threat-and-vuln-mgt.md)

- [Svagheter i organisationen](tvm-weaknesses.md)
