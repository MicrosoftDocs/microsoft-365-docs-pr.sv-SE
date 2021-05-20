---
title: Api:et för listincidenter i Microsoft 365 Defender
description: Läs om hur du listar API för incidenter i Microsoft 365 Defender
keywords: lista, incident, incidenter, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 6f0c92371e7e9b7a3348f90df788ee8c3a46374b
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572159"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a>Api:et för listincidenter i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**

- Microsoft 365 Defender

> [!IMPORTANT]
> En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.


## <a name="api-description"></a>API-beskrivning

Api:et för listincidenter låter dig sortera igenom incidenter för att skapa ett informerat cybersäkerhetssvar. Den visar en samling incidenter som har flaggats i nätverket inom det tidsintervall som du angav i principen för miljö kvarhållning. De senaste incidenterna visas högst upp i listan. Varje incident innehåller en matris med relaterade aviseringar och deras relaterade entiteter.

API:et stöder följande **OData-operatorer:**

- `$filter` på `lastUpdateTime` , `createdTime` , och `status` `assignedTo` egenskaper
- `$top`, med ett maximalt värde på **100**
- `$skip`

## <a name="limitations"></a>Begränsningar

1. Maximal sidstorlek är **100 incidenter**.
2. Maximal frekvens för förfrågningar är **50 samtal per minut och** **1500 samtal per timme**.

## <a name="permissions"></a>Behörigheter

En av följande behörigheter krävs för att anropa det här API:et. Mer information om hur du väljer behörigheter finns i [Access Microsoft 365 Defender API:er](api-access.md)

Typ av behörighet | Behörighet | Namn på behörighetsvisning
-|-|-
Program | Incident.Read.All | Läs alla incidenter
Program | Incident.ReadWrite.All | Läsa och skriva alla incidenter
Delegerat (arbets- eller skolkonto) | Incident.Läs | Läs incidenter
Delegerat (arbets- eller skolkonto) | Incident.ReadWrite (på plats) | Läsa och skriva incidenter

> [!Note]
> När du skaffar en token med användarautentiseringsuppgifter:
>
> - Användaren måste ha visningsbehörighet för incidenter i portalen.
> - Svaret kommer endast att innehålla incidenter som användaren utsätts för.

## <a name="http-request"></a>HTTP-begäran

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a>Begär rubriker

Namn | Typ | Beskrivning
-|-|-
tillstånd | Sträng | Bärare {token}. **Obligatoriskt**


## <a name="request-body"></a>Begär brödtext

ingen.

## <a name="response"></a>svar

Om den här metoden lyckas returneras `200 OK` den och en lista över incidenter [i](api-incident.md) svarstexten.

## <a name="schema-mapping"></a>Schemamappning

### <a name="incident-metadata"></a>Metadata för incidenter

fältnamn | Beskrivning | Exempelvärde
-|-|-
incidentId | Unik identifierare som representerar incidenten | 924565
omdirigeraIncidentId | Endast ifyllt om en incident grupperas tillsammans med en annan incident, som en del av incident bearbetnings logiken. | 924569
incidentName | Strängvärde tillgängligt för varje incident. | Ransomware-aktivitet
createdTime | Tid då incidenten först skapades. | 2020-09-06T14:46:57.0733333Z
lastUpdateTime | Tid då incidenten senast uppdaterades på backend.<br /><br /> Det här fältet kan användas när du anger parametern för begäran för det tidsintervall som incidenter hämtas. | 2020-09-06T14:46:57.29Z
tilldeladTill | Ägare till incidenten, eller *null* om ingen ägare har tilldelats. | secop2@contoso.com
klassificering | Specifikationen för incidenten. Egenskapsvärdena är: *Okänd*, *FalsePositive*, *TruePositive* | Okänd
beslutsamhet | Anger bestämningen av incidenten. Egenskapsvärdena är: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* | Intetillgänglig
status | Kategorisera incidenter (som aktiva *eller* *lösta*). Det kan hjälpa dig att organisera och hantera ditt svar på incidenter. | Aktiv
stränghet | Anger den möjliga påverkan på tillgångar. Ju högre svårighetsgrad desto större blir effekten. Vanligtvis kräver objekt med högre allvarlighetsgrad den mest omedelbara uppmärksamheten.<br /><br />Ett av följande värden: *Information ,* *Låg*, *Medel och *Hög*. | Medel
Taggar | Matris med anpassade taggar som är associerade med en incident, till exempel för att flagga en grupp incidenter med en gemensam egenskap. | \[\]
Kommentarer | Matris med kommentarer som skapats av secops när incidenten hanterades, till exempel ytterligare information om klassificeringsvalet. | \[\]
Varningar | Matris som innehåller alla aviseringar relaterade till incidenten, plus annan information, till exempel allvarlighetsgrad, entiteter som var involverade i aviseringen och källan till aviseringarna. | \[\] (se detaljer om varningsfält nedan)

### <a name="alerts-metadata"></a>Aviseringar metadata

fältnamn | Beskrivning | Exempelvärde
-|-|-
alertId (på-)alertId | Unik identifierare som representerar aviseringen | caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC
incidentId | Unik identifierare som representerar incidenten som aviseringen är associerad med | 924565
tjänstKälla | Tjänst som aviseringen kommer från, till exempel Microsoft Defender för Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity eller Microsoft Defender för Office 365. | MicrosoftCloudAppSäkerhet
skapaTime | Tid då aviseringen först skapades. | 2020-09-06T14:46:55.7182276Z
senasteUppdateradeTime | Tid då aviseringen senast uppdaterades i backend. | 2020-09-06T14:46:57.2433333Z
löstTime | Tid då aviseringen löstes. | 2020-09-10T05:22:59Z
förstaAktivitet | Tid då aviseringen först rapporterade att aktiviteten uppdaterades i backend.| 2020-09-04T05:22:59Z
titel | Kort identifiering av strängvärde som är tillgängligt för varje avisering. | Ransomware-aktivitet
beskrivning | Strängvärde som beskriver varje avisering. | Användaren Test User2 (testUser2@contoso.com) manipulerade 99 filer med flera tillägg som slutade med den ovanliga *förlängningen herunterladen*. Detta är ett ovanligt antal filmanipulationer och tyder på en potentiell ransomware-attack.
kategori | Visuell och numerisk bild av hur långt attacken har kommit längs dödskedjan. Anpassad till [MITRE ATT&CK™ ramverk .](https://attack.mitre.org/) | Påverkan
status | Kategorisera aviseringar (som *nya,* aktiva *eller* *lösta*). Det kan hjälpa dig att organisera och hantera ditt svar på aviseringar. | Ny
stränghet | Anger den möjliga påverkan på tillgångar. Ju högre svårighetsgrad desto större blir effekten. Vanligtvis kräver objekt med högre allvarlighetsgrad den mest omedelbara uppmärksamheten.<br>Ett av följande värden: *Information ,* *Låg*, *Medel och *Hög*. | Medel
utredningId | Det automatiska undersöknings-ID:t som utlöses av den här aviseringen. | 1234
undersökningState | Information om utredningens aktuella status. Något av följande värden: *Okänd*, *Avslutad*, *FramgångsriktRemediated*, *Benign*, *Misslyckades*, *DelvisRemediated*, *Kör*, *PendingApproval*, *PendingResource*, *Delvisinvesterad*, *AvslutadByUser*, *TerminatedBySystem*, *Köad*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*. | AlertType som inte stöds
klassificering | Specifikationen för incidenten. Egenskapsvärdena är: *Okänd*, *FalsePositive*, *TruePositive* eller *null* | Okänd
beslutsamhet | Anger bestämningen av incidenten. Egenskapsvärdena är: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null* | Apt.
tilldeladTill | Ägare till incidenten, eller *null* om ingen ägare har tilldelats. | secop2@contoso.com
skådespelareName | Aktivitetsgruppen, om sådan finns, är associerad med den här aviseringen. | bor
hotFamilyName | Hotfamilj som är associerad med den här aviseringen. | noll
mitreTeknik | Attackteknikerna, i linje med [MITRE ATT&CK](https://attack.mitre.org/)™ ramverk. | \[\]
Enheter | Alla enheter där aviseringar relaterade till incidenten skickades. | \[\] (se information om entitetsfält nedan)

### <a name="device-format"></a>Enhetsformat

fältnamn | Beskrivning | Exempelvärde
-|-|-
DeviceId (på alla) | Enhets-ID:t som anges i Microsoft Defender för Slutpunkt. | 24c222b0b60fe148eeece49ac83910cc6a7ef491
aadDeviceId (på 1997) |  Enhets-ID:t enligt [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis). Endast tillgängligt för domänakade enheter. | noll
deviceDnsName | Enhetens fullständigt kvalificerade domännamn. | user5cx.middleeast.corp.contoso.com
osPlatform (på något sätt) | OS-plattformen som enheten kör.| WindowsServer2016
osByggd | Byggversionen för operativsystemet som enheten kör. | 14393
rbacGroupName (på)rbacGroupName | Den [rollbaserade åtkomstkontrollgruppen](/azure/role-based-access-control/overview) (RBAC) som är associerad med enheten. | WDATP-Ring0
förstSeen | Tid då enheten först sågs. | 2020-02-06T14:16:01.9330135Z
hälsaStatus | Enhetens hälsotillstånd. | Aktiv
riskScore | Risk poängen för enheten. | Högsta
enheter | Alla entiteter som har identifierats som en del av eller relaterade till en viss avisering. | \[\] (se information om entitetsfält nedan)

### <a name="entity-format"></a>Entitetsformat

fältnamn | Beskrivning | Exempelvärde
-|-|-
entityType (på)entitet | Entiteter som har identifierats som en del av eller relaterade till en viss avisering.<br>Egenskapsvärdena är: *Användare*, *Ip*, *Url*, *Fil*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Register* | Användare
sha1 (sha1) | Tillgänglig om entityType är *fil*.<br>Filhhhh för aviseringar som är associerade med en fil eller process. | 5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd
sha256 (på 256) | Tillgänglig om entityType är *fil*.<br>Filhhhh för aviseringar som är associerade med en fil eller process. | 28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043
filnamn | Tillgänglig om entityType är *fil*.<br>Filnamnet för aviseringar som är associerade med en fil eller process | Detector.UnitTests.dll
filePath (på 100 | Tillgänglig om entityType är *fil*.<br>Filsökvägen för aviseringar som är associerade med en fil eller process | C: \\ \agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out
processId (på alla) | Tillgänglig om entityType är *Process*. | 24348
processCommandLine | Tillgänglig om entityType är *Process*. | "Din fil är redo att laddas \_1911150169.exe"
processSkapaTid | Tillgänglig om entityType är *Process*. | 2020-07-18T03:25:38.5269993Z
överordnadProcessId | Tillgänglig om entityType är *Process*. | 16840
överordnadProcessCreationTime | Tillgänglig om entityType är *Process*. | 2020-07-18T02:12:32.8616797Z
ipAddress (på 5000) | Tillgänglig om entityType är *Ip*. <br>IP-adress för aviseringar som är associerade med nätverkshändelser, till exempel *kommunikation till ett skadligt nätverksmål*. | 62.216.203.204
URL | Tillgänglig om entityType är *Url*. <br>Url för aviseringar som är associerade med nätverkshändelser, till exempel *Kommunikation till ett skadligt nätverksmål*. | down.esales360.cn
kontoNamn | Tillgänglig om entityType är *användare*. | testUser2
domänNamn | Tillgänglig om entityType är *användare*. | europa.corp.contoso
userSid | Tillgänglig om entityType är *användare*. | S-1-5-21-1721254763-462695806-1538882281-4156657
aadUserId (på alla) | Tillgänglig om entityType är *användare*. | fc8f7484-f813-4db2-afab-bc1507913fb6
userPrincipalName | Tillgänglig om entityType är *User* / *MailBox* / *MailMessage*. | testUser2@contoso.com
postlådaDisplayName | Tillgänglig om entityType är *MailBox*. | testa användare2
brevlådaAdress | Tillgänglig om entityType är *User* / *MailBox* / *MailMessage*. | testUser2@contoso.com
klusterBy | Tillgänglig om entityType är  *MailCluster*. | Angående; P2SenderDomain; ContentType (på 800
avsändare | Tillgänglig om entityType är *User* / *MailBox* / *MailMessage*. | user.abc@mail.contoso.co.in
mottagare | Tillgängligt om entityType är *MailMessage*. | testUser2@contoso.com
subjekt | Tillgängligt om entityType är *MailMessage*. | \[EXTERN \] UPPMÄRKSAMHET
leveransÅtgärder | Tillgängligt om entityType är *MailMessage*. | Levereras
säkerhetGroupId | Tillgängligt om entityType är  *SecurityGroup*. | 301c47c8-e15f-4059-ab09-e2ba9ffd372b
säkerhetsgruppNamn | Tillgängligt om entityType är  *SecurityGroup*. | Operatörer av nätverkskonfiguration
registryHive (registretHive) | Tillgänglig om entityType är  *Registry*. | HKEY \_ LOKAL \_ MASKIN |
registryKey (registernyckel) | Tillgänglig om entityType är  *Registry*. | PROGRAMVARA\Microsoft\Windows NT\CurrentVersion\Winlogon
registerValueType | Tillgänglig om entityType är  *Registry*. | Sträng
registerValuta | Tillgänglig om entityType är  *Registry*. | 31-00-00-00
deviceId (på 100 | ID:t, om det finns något, för den enhet som är relaterad till entiteten. | 986e5df8b73dacd43c8917d17e523e76b13c75cd

## <a name="example"></a>Exempel

**begäran**

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

**svar**

```json
{
    "@odata.context": "https://api.security.microsoft.com/api/$metadata#Incidents",
    "value": [
            {
            "incidentId": 924565,
            "redirectIncidentId": null,
            "incidentName": "Ransomware activity",
            "createdTime": "2020-09-06T14:46:57.0733333Z",
            "lastUpdateTime": "2020-09-06T14:46:57.29Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Medium",
            "tags": [],
            "comments": [
                {
                    "comment": "test comment for docs",
                    "createdBy": "secop123@contoso.com",
                    "createdTime": "2021-01-26T01:00:37.8404534Z"
                }
            ],
            "alerts": [
                {
                    "alertId": "caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC",
                    "incidentId": 924565,
                    "serviceSource": "MicrosoftCloudAppSecurity",
                    "creationTime": "2020-09-06T14:46:55.7182276Z",
                    "lastUpdatedTime": "2020-09-06T14:46:57.2433333Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-04T05:22:59Z",
                    "lastActivity": "2020-09-04T05:22:59Z",
                    "title": "Ransomware activity",
                    "description": "The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension herunterladen. This is an unusual number of file manipulations and is indicative of a potential ransomware attack.",
                    "category": "Impact",
                    "status": "New",
                    "severity": "Medium",
                    "investigationId": null,
                    "investigationState": "UnsupportedAlertType",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "MCAS",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "User",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": "testUser2",
                            "domainName": "europe.corp.contoso",
                            "userSid": "S-1-5-21-1721254763-462695806-1538882281-4156657",
                            "aadUserId": "fc8f7484-f813-4db2-afab-bc1507913fb6",
                            "userPrincipalName": "testUser2@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "62.216.203.204",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924521,
            "redirectIncidentId": null,
            "incidentName": "'Mimikatz' hacktool was detected on one endpoint",
            "createdTime": "2020-09-06T12:18:03.6266667Z",
            "lastUpdateTime": "2020-09-06T12:18:03.81Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Low",
            "tags": [],
            "comments": [],
            "alerts": [
                {
                    "alertId": "da637349914833441527_393341063",
                    "incidentId": 924521,
                    "serviceSource": "MicrosoftDefenderATP",
                    "creationTime": "2020-09-06T12:18:03.3285366Z",
                    "lastUpdatedTime": "2020-09-06T12:18:04.2566667Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:15:07.7272048Z",
                    "lastActivity": "2020-09-06T12:15:07.7272048Z",
                    "title": "'Mimikatz' hacktool was detected",
                    "description": "Readily available tools, such as hacking programs, can be used by unauthorized individuals to spy on users. When used by attackers, these tools are often installed without authorization and used to compromise targeted machines.\n\nThese tools are often used to collect personal information from browser records, record key presses, access email and instant messages, record voice and video conversations, and take screenshots.\n\nThis detection might indicate that Windows Defender Antivirus has stopped the tool from being installed and used effectively. However, it is prudent to check the machine for the files and processes associated with the detected tool.",
                    "category": "Malware",
                    "status": "New",
                    "severity": "Low",
                    "investigationId": null,
                    "investigationState": "UnsupportedOs",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "WindowsDefenderAv",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": "Mimikatz",
                    "mitreTechniques": [],
                    "devices": [
                        {
                            "mdatpDeviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491",
                            "aadDeviceId": null,
                            "deviceDnsName": "user5cx.middleeast.corp.contoso.com",
                            "osPlatform": "WindowsServer2016",
                            "version": "1607",
                            "osProcessor": "x64",
                            "osBuild": 14393,
                            "healthStatus": "Active",
                            "riskScore": "High",
                            "rbacGroupName": "WDATP-Ring0",
                            "rbacGroupId": 9,
                            "firstSeen": "2020-02-06T14:16:01.9330135Z"
                        }
                    ],
                    "entities": [
                        {
                            "entityType": "File",
                            "sha1": "5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd",
                            "sha256": null,
                            "fileName": "Detector.UnitTests.dll",
                            "filePath": "C:\\Agent\\_work\\_temp\\Deploy_SYSTEM 2020-09-06 12_14_54\\Out",
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491"
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924518,
            "redirectIncidentId": null,
            "incidentName": "Email reported by user as malware or phish",
            "createdTime": "2020-09-06T12:07:55.1366667Z",
            "lastUpdateTime": "2020-09-06T12:07:55.32Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Informational",
            "tags": [],
            "comments": [],
            "alerts": [
                {
                    "alertId": "faf8edc936-85f8-a603-b800-08d8525cf099",
                    "incidentId": 924518,
                    "serviceSource": "OfficeATP",
                    "creationTime": "2020-09-06T12:07:54.3716642Z",
                    "lastUpdatedTime": "2020-09-06T12:37:40.88Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:04:00Z",
                    "lastActivity": "2020-09-06T12:04:00Z",
                    "title": "Email reported by user as malware or phish",
                    "description": "This alert is triggered when any email message is reported as malware or phish by users -V1.0.0.2",
                    "category": "InitialAccess",
                    "status": "InProgress",
                    "severity": "Informational",
                    "investigationId": null,
                    "investigationState": "Queued",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "OfficeATP",
                    "assignedTo": "Automation",
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser3@contoso.com",
                            "mailboxDisplayName": "test User3",
                            "mailboxAddress": "testUser3@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser4@contoso.com",
                            "mailboxDisplayName": "test User4",
                            "mailboxAddress": "test.User4@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailMessage",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "test.User4@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": "user.abc@mail.contoso.co.in",
                            "recipient": "test.User4@contoso.com",
                            "subject": "[EXTERNAL] Attention",
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "49.50.81.121",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        ...
    ]
}
```

## <a name="related-articles"></a>Relaterade artiklar

- [Komma åt Microsoft 365 Defender API:erna](api-access.md)
- [Lär dig mer om API-gränser och licensiering](api-terms.md)
- [Förstå felkoder](api-error-codes.md)
- [Översikt över incidenter](incidents-overview.md)
- [API:er för tillbud](api-incident.md)
- [Uppdatera incident-API](api-update-incidents.md)
