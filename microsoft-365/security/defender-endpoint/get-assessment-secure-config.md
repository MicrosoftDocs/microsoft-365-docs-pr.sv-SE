---
title: Exportera utvärdering av säker konfiguration per enhet
description: Returnerar en post för varje unik kombination av DeviceId, ConfigurationId.
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
ms.openlocfilehash: fe6a4604852965bdcc563ac0e410ca165bc5a088
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789405"
---
# <a name="export-secure-configuration-assessment-per-device"></a>Exportera utvärdering av säker konfiguration per enhet

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
Returnerar alla konfigurationer och deras status per enhet.

Det finns olika API-anrop för att få olika typer av data. Eftersom mängden data kan vara stor kan den hämtas på två sätt:

- [Exportera **OData** för säker](#1-export-secure-configuration-assessment-odata)konfigurationsutvärdering: API:t hämtar alla data i organisationen som Json-svar efter OData-protokollet. Den här metoden är bäst _för små organisationer med mindre än 100 K-enheter._ Svaret är paginerat, så du kan använda \@ odata.nextLink-fältet från svaret för att hämta nästa resultat.

- [Exportera säker konfigurationsbedömning **via filer**](#2-export-secure-configuration-assessment-via-files): Med den här API-lösningen kan du hämta stora mängder data snabbare och mer tillförlitligt. Därför rekommenderas det för stora organisationer med fler än 100 K-enheter. Detta API hämtar alla data i organisationen som nedladdningsfiler. Svaret innehåller URL:er för att ladda ned alla data från Azure Storage. Med det här API:t kan du ladda ned alla dina data Azure Storage enligt följande:

  - Anropa API:t för att få en lista med hämtningsadresser med alla dina organisationsdata.

  - Ladda ned alla filer med hjälp av URL:er för nedladdning och bearbeta dina data som du vill.

Data som samlas in (med hjälp av _antingen OData_ eller _via_ filer) är den aktuella ögonblicksbilden av den aktuella statusen, och innehåller inte historiska data. För att kunna samla in historiska data måste kunderna spara data i sina egna datalagringar.

> [!Note]
>
> Om inget annat anges exporteras alla utvärderingsmetoder som **_listas för fullständig export_** **_och_** efter enhet (kallas även **_per enhet)._**

## <a name="1-export-secure-configuration-assessment-odata"></a>1. Exportera utvärdering av säker konfiguration (OData)

### <a name="11-api-method-description"></a>1.1 API-metodbeskrivning

Det här API-svaret innehåller Secure Configuration Assessment på dina exponerade enheter och returnerar en post för varje unik kombination av DeviceId, ConfigurationId.

#### <a name="111-limitations"></a>1.1.1 Begränsningar

- Maximal sidstorlek är 200 000.

- Prisbegränsningar för detta API är 30 samtal per minut och 1 000 samtal per timme.

### <a name="12-permissions"></a>1.2 Behörigheter

En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md) för mer information.

Behörighetstyp | Behörighet | Visningsnamn för behörighet
---|---|---
Program | Vulnerability.Read.All | \'Läsa sårbarhetsinformation om hot och sårbarhetshantering\'
Delegerat (arbets- eller skolkonto) | Sårbarhet.Läsa | \'Läsa sårbarhetsinformation om hot och sårbarhetshantering\'

### <a name="13-url"></a>1.3 URL

```http
GET /api/machines/SecureConfigurationsAssessmentByMachine
```

### <a name="14-parameters"></a>1.4 Parametrar

- pageSize \( default = 50,000 \) – antal resultat i svar

- \$överst – antalet resultat som ska \( returneras returnerar \@ inte odata.nextLink och hämtar därför inte alla data\)

### <a name="15-properties"></a>1.5 Egenskaper

>[!Note]
>
>- Egenskaperna som definieras i följande tabell anges i alfabetisk ordning, efter egenskaps-ID.  När du kör det här API:t returneras inte resultatet nödvändigtvis i samma ordning som anges i den här tabellen.
>
>- Vissa ytterligare kolumner kan returneras i svaret. Kolumnerna är tillfälliga och kan komma att tas bort. Använd bara de dokumenterade kolumnerna.
>

Egenskap (ID) | Datatyp | Beskrivning | Exempel på ett returnerat värde
:---|:---|:---|:---
ConfigurationCategory | sträng | Kategori eller gruppering som konfigurationen tillhör: Program, OS, Nätverk, Konton, Säkerhetskontroller | Säkerhetskontroller
ConfigurationId | sträng | Unikt ID för en viss konfiguration | scid-10000
ConfigurationImpact | sträng | Klassificerad inverkan av konfigurationen på det övergripande konfigurationsresultatet (1–10) | 9
ConfigurationName | sträng | Visningsnamn för konfigurationen | Registrera enheter till Microsoft Defender för Endpoint
ConfigurationSubcategory | sträng | Underkategori eller undergrupp som konfigurationen tillhör. I många fall beskrivs specifika funktioner. | Onboard-enheter
DeviceId | sträng | Unikt ID för enheten i tjänsten. | 9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1
DeviceName | sträng | Fullständigt kvalificerat domännamn (FQDN) för enheten. | johnlaptop.europe.contoso.com
IsApplicable | bool | Anger om konfigurationen eller principen är tillämplig | true
IsCompliet | bool | Anger om konfigurationen eller principen är korrekt konfigurerad | false
IsExpectedUserImpact | bool | Anger om det kommer att finnas någon påverkan på användaren om konfigurationen ska användas | true
OSPlatform | sträng | Operativsystemets plattform som körs på enheten. Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7. Mer information finns i Operativsystem och plattformar som stöds av TVM. | Windows10
RbacGroupName | sträng | Den rollbaserade åtkomstkontrollgruppen (RBAC). Om enheten inte är tilldelad till någon RBAC-grupp kommer värdet att vara "Ej tilldelat". Om organisationen inte innehåller några RBAC-grupper blir värdet "Ingen". | Servrar
RekommendationReference | sträng | En referens till det rekommendations-ID som hör till den här programvaran. | sca-_scid-20000
Tidsstämpel | sträng | Senaste gången konfigurationen sågs på enheten | 2020-11-03 10:13:34.8476880

### <a name="16-examples"></a>1.6 Exempel

#### <a name="161-request-example"></a>1.6.1 Exempel på begäran

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pageSize=5 
```

#### <a name="162-response-example"></a>1.6.2 Svarsexempel

```json
{
    "@odata.context": "api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetConfiguration)",
    "value": [
        {
            "deviceId": "00013ee62c6b12345b10214e1801b217b50ab455c293d",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_5d96860d69c73fdd06fc8d1679e1eb73eceb8330",
            "osPlatform": "Windows10",
            "osVersion": "NT kernel 6.x",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "0002a1be533813b9a8c6de739785365bce7910",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-20000",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Onboard Devices",
            "configurationImpact": 9,
            "isCompliant": false,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Onboard devices to Microsoft Defender for Endpoint",
            "recommendationReference": "sca-_-scid-20000"
        },
        {
            "deviceId": "0002a1de123456a8c06de736785395d4ce7610",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "00044f912345bdaf756492dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663d45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-39",
            "configurationCategory": "OS",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Enable 'Domain member: Digitally sign secure channel data (when possible)'",
            "recommendationReference": "sca-_-scid-39"
        },
        {
            "deviceId": "00044f912345daf759462bde6bd733d6a9c56ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45612eeb224d2de2f5ea3142726e63f16a.DomainPII_21eed80d086e76dbfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-6093",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Antivirus",
            "configurationImpact": 5,
            "isCompliant": false,
            "isApplicable": false,
            "isExpectedUserImpact": false,
            "configurationName": "Enable Microsoft Defender Antivirus real-time behavior monitoring for Linux",
            "recommendationReference": "sca-_-scid-6093"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-secure-configuration-assessment-via-files"></a>2. Exportera utvärdering av säker konfiguration (via filer)

### <a name="21-api-method-description"></a>2.1 API-metodbeskrivning

Det här API-svaret innehåller Secure Configuration Assessment på dina exponerade enheter och returnerar en post för varje unik kombination av DeviceId, ConfigurationId.

#### <a name="212-limitations"></a>2.1.2 Begränsningar

Prisbegränsningar för detta API är 5 samtal per minut och 20 samtal per timme.

### <a name="22-permissions"></a>2.2 Behörigheter

En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er för mer information.](apis-intro.md)

Behörighetstyp | Behörighet | Visningsnamn för behörighet
---|---|---
Program | Vulnerability.Read.All | \'Läs "Hantering av hot och säkerhetsrisker" sårbarhetsinformation\'
Delegerat (arbets- eller skolkonto) | Sårbarhet.Läsa | \'Läs "Hantering av hot och säkerhetsrisker" sårbarhetsinformation\'

### <a name="23-url"></a>2.3 URL

```http
GET /api/machines/SecureConfigurationsAssessmentExport
```

### <a name="parameters"></a>Parametrar

- sasValidHours – Antalet timmar som hämtnings-URL:erna ska vara giltiga i (högst 24 timmar).

### <a name="25-properties"></a>2.5 Egenskaper

>[!Note]
>
>- Filerna är gzip komprimerade & I multiline Json-format.
>
>- URL-adresser för nedladdning är endast giltiga i 3 timmar. annars kan du använda parametern.
>
>- För maximal nedladdningshastighet för dina data kan du se till att du laddar ned från samma Azure-region som dina data finns i.
>
Egenskap (ID) | Datatyp | Beskrivning | Exempel på ett returnerat värde
:---|:---|:---|:---
Exportera filer | \[matrissträng\] | En lista över hämtnings-URL:er för filer som innehåller den aktuella ögonblicksbilden av organisationen | [  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]
GeneratedTime | sträng | Tidpunkten då exporten skapades. | 2021-05-20T08:00:00Z ]

### <a name="26-examples"></a>2.6 Exempel

#### <a name="261-request-example"></a>2.6.1 Exempel på begäran

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentExport
```

#### <a name="262-response-example"></a>2.6.2 Svarsexempel

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#contoso.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a>Se även

- [Exportera utvärderingsmetoder och egenskaper per enhet](get-assessment-methods-properties.md)

- [Exportera utvärdering av programvaruinventering per enhet](get-assessment-software-inventory.md)

- [Exportera bedömningar av säkerhetsproblem för programvara per enhet](get-assessment-software-vulnerabilities.md)

Andra relaterade

- [Riskbaserade hot & hantering av säkerhetsrisker](next-gen-threat-and-vuln-mgt.md)

- [Svagheter i organisationen](tvm-weaknesses.md)
