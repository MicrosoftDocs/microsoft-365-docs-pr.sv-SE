---
title: API för listincidenter i Microsoft 365 Defender
description: Lär dig hur du listar incident-API i Microsoft 365 Defender
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 39a170a1845ab33f67d77b2de3d5f298f67fdc99
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932076"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a>API för listincidenter i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Viss information gäller förhandsversioner av produkter som kan komma att ändras väsentligt innan de släpps till kommersiellt bruk. Microsoft ger inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.


## <a name="api-description"></a>API-beskrivning

Med API:t för listincidenter kan du sortera olika incidenter för att skapa en välinformerad cybersäkerhet. Här visas en samling incidenter som har flaggats i nätverket, inom det angivna tidsperioden i din miljöbevarandeprincip. De senaste incidenterna visas högst upp i listan. Varje incident innehåller en matris med relaterade aviseringar och deras relaterade enheter.

API:t stöder följande **OData-operatorer:**

- `$filter` på `lastUpdateTime` fliken `createdTime` `status` , och `assignedTo` egenskaperna
- `$top`, med maximalt **värde 100**
- `$skip`

## <a name="limitations"></a>Begränsningar

1. Maximal sidstorlek är **100 ärenden.**
2. Maximalt antal förfrågningar är **50 samtal per minut och** **1 500 samtal per timme.**

## <a name="permissions"></a>Behörigheter

En av följande behörigheter krävs för att anropa detta API. Mer information, inklusive hur du väljer behörigheter, finns i [Access-API:er för Microsoft 365 Defender](api-access.md)

Behörighetstyp | Behörighet | Visningsnamn för behörighet
-|-|-
Program | Incident.Read.All | Läs alla incidenter
Program | Incident.ReadWrite.All | Läsa och skriva alla incidenter
Delegerat (arbets- eller skolkonto) | Incident.Read | Läs incidenter
Delegerat (arbets- eller skolkonto) | Incident.ReadWrite | Läs- och skrivincidenter

> [!Note]
> När du skaffar ett token med användarautentiseringsuppgifter:
>
> - Användaren måste ha visningsbehörighet för ärenden i portalen.
> - Svaret inkluderar bara incidenter som användaren exponeras för.

## <a name="http-request"></a>HTTP-begäran

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a>Begär sidhuvuden

Namn | Type (Typ) | Beskrivning
-|-|-
Auktorisering | Sträng | Bearer {token}. **Obligatoriskt**


## <a name="request-body"></a>Begärandetext

Inget.

## <a name="response"></a>Svar

Om det lyckas returneras den `200 OK` här metoden och en lista över [incidenter](api-incident.md) i svarstexten.

## <a name="schema-mapping"></a>Schemamappning

### <a name="incident-metadata"></a>Incidentmetadata

Fältnamn | Beskrivning | Exempelvärde
-|-|-
incidentId | Unikt ID som representerar incidenten | 924565
redirectIncidentId | Fylls bara i om en incident grupperas tillsammans med en annan incident, som en del av händelsebearbetningslogiken. | 924569
incidentName | Ett strängvärde som är tillgängligt för varje incident. | Utpressningstrojanaktivitet
createdTime | Tidpunkt när incidenten skapades först. | 2020-09-06T14:46:57.0733333Z
lastUpdateTime | Tid då incidenten uppdaterades senast på backend.<br /><br /> Det här fältet kan användas när du anger parametern för begäran för det tidsintervall som incidenterna ska hämtas. | 2020-09-06T14:46:57.29Z
assignedTo | Ägaren till incidenten, eller *null* om ingen ägare har tilldelats. | secop2@contoso.com
klassificering | Specifikationen för incidenten. Egenskapsvärdena är: *Okänt, FalsktPositive,* *TruePositive*  | Okänd
determination | Anger incidentens avgörande. Egenskapsvärdena är: *NotAvailable,* *Apt,* *Malware,* *SecurityPersonnel,* *SecurityTesting,* *UnwantedSoftware,* *Other* | NotAvailable
status | Kategorisera incidenter (som *aktiva* eller *lösta).* Det kan hjälpa dig att organisera och hantera dina svar på incidenter. | Aktiv
allvarlighetsgrad | Anger den möjliga påverkan på tillgångar. Ju högre allvarlighetsgrad desto större påverkan. Vanligtvis kräver objekt med högre allvarlighetsgrad mest omedelbar uppmärksamhet.<br /><br />Ett av följande värden: *Information,* *Låg,**Medel och *Hög.* | Medel
taggar | Matris med anpassade taggar kopplade till en incident, till exempel för att flagga en grupp med incidenter med en gemensam egenskap. | \[\]
aviseringar | Matris som innehåller alla aviseringar som är relaterade till händelsen samt annan information, till exempel allvarlighetsgrad, enheter som var inblandade i aviseringen och källan till aviseringarna. | \[\] (se information om aviseringsfälten nedan)

### <a name="alerts-metadata"></a>Aviseringsmetadata

Fältnamn | Beskrivning | Exempelvärde
-|-|-
alertid | Unik identifierare som representerar aviseringen | caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC
incidentId | Unikt ID som representerar den händelse som den här aviseringen är associerad med | 924565
serviceSource | Tjänst som aviseringen kommer från, till exempel Microsoft Defender för Slutpunkt, Microsoft Cloud App Security, Microsoft Defender för identitet eller Microsoft Defender för Office 365. | MicrosoftCloudAppSecurity
creationTime | Tidpunkt när aviseringen skapades. | 2020-09-06T14:46:55.7182276Z
lastUpdatedTime | Tid när aviseringen senast uppdaterades på backend. | 2020-09-06T14:46:57.2433333Z
resolvedTime | Tid när aviseringen löstes. | 2020-09-10T05:22:59Z
firstActivity | Tid när aviseringen först rapporterade att aktiviteten uppdaterades på backend.| 2020-09-04T05:22:59Z
rubrik | Kort identifiering av strängvärdet som är tillgängligt för varje avisering. | Utpressningstrojanaktivitet
beskrivning | Strängvärde som beskriver varje avisering. | Användaren Test User2 (testUser2@contoso.com) har manipulerat 99 filer med flera tillägg som slutar med den ovanliga filnamnstillägget *herunterladen.* Det här är ett ovanligt antal filmanipuleringar och är därför en potentiell utpressningstrojanattack.
kategori | Visuell och numerisk vy över hur långt attacken har fortskridt längs kill chain. I linje med [MITRE ATT&CK™ framework.](https://attack.mitre.org/) | Påverkan
status | Kategorisera aviseringar (som *Ny,* *Aktiv* eller *Matchad).* Det kan hjälpa dig att organisera och hantera dina svar på aviseringar. | Ny
allvarlighetsgrad | Anger den möjliga påverkan på tillgångar. Ju högre allvarlighetsgrad desto större påverkan. Vanligtvis kräver objekt med högre allvarlighetsgrad mest omedelbar uppmärksamhet.<br>Ett av följande värden: *Information,* *Låg,**Medel och *Hög.* | Medel
investigationId | Detta är det automatiska undersöknings-ID som utlöses av den här aviseringen. | 1234
investigationState | Information om undersökningens aktuella status. Ett av följande *värden:* *Okänt,* Avslutat, *Lyckades,*  *Misslyckades,* Delvis åtgärdat, Körs, *VäntandeApproval,* *PendingResource,* *DelvisInvesterat,* *AvslutatByUser,* *TerminatedBySystem,* *Queued,* *InnerFailure,* *PreexistingAlert,* *UnsupportedOs,* *UnsupportedAlertType,* *SuppressedAlert.*   | UnsupportedAlertType
klassificering | Specifikationen för incidenten. Egenskapsvärdena *är:* *Okänt, FalsktPositive,* *TruePositive* eller *null* | Okänd
determination | Anger incidentens avgörande. Egenskapsvärdena är: *NotAvailable,* *Apt,* *Malware,* *SecurityPersonnel,* *SecurityTesting,* *UnwantedSoftware,* *Other* eller  *null* | Apt
assignedTo | Ägaren till händelsen, eller *null om* ingen ägare har tilldelats. | secop2@contoso.com
actorName | Om det finns en aktivitetsgrupp som är kopplad till den här aviseringen. | BORON
threatFamilyName | Hotfamilj kopplad till den här aviseringen. | null
mitreTechniques | Attacktekniker, i enlighet med [MITRE ATT&CK-™](https://attack.mitre.org/)ramverket. | \[\]
enheter | Alla enheter där aviseringar om händelsen har skickats. | \[\] (se information om entitetsfälten nedan)

### <a name="device-format"></a>Enhetsformat

Fältnamn | Beskrivning | Exempelvärde
-|-|-
DeviceId | Enhets-ID:t som angetts i Microsoft Defender ATP. | 24c222b0b60fe148eeece49ac83910cc6a7ef491
aadDeviceId |  Det enhets-ID som angetts [i Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) Endast tillgängligt för domän anslutna enheter. | null
deviceDnsName | Det fullständigt kvalificerade domännamnet för enheten. | user5cx.middleeast.corp.contoso.com
osPlatform | Den OS-plattform som enheten körs på.| WindowsServer2016
osBuild | Versionsversionen för operativsystemet som enheten kör. | 14393
rbacGroupName | Den [rollbaserade åtkomstkontrollgruppen](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) som är kopplad till enheten. | WDATP-Ring0
firstSeen | Tid när enheten sågs för första gången. | 2020-02-06T14:16:01.9330135Z
healthStatus | Status för enheten. | Aktiv
riskScore | Riskresultatet för enheten. | Högsta
enheter | Alla enheter som har identifierats som en del av, eller relaterade till, en viss avisering. | \[\] (se information om entitetsfälten nedan)

### <a name="entity-format"></a>Entitetsformat

Fältnamn | Beskrivning | Exempelvärde
-|-|-
entityType | Enheter som har identifierats som en del av eller relaterade till en viss avisering.<br>Egenskapsvärdena är: *Användare,* *Ip,* *URL,* *Fil,* *Process,* *MailBox,* *MailMessage,* *MailCluster,* *Registry* | Användare
sha1 | Tillgängligt om entityType är *File*.<br>Filhash för aviseringar som associeras med en fil eller process. | 5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd
sha256 | Tillgängligt om entityType är *File*.<br>Filhash för aviseringar som associeras med en fil eller process. | 28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043
fileName | Tillgängligt om entityType är *File*.<br>Filnamnet för aviseringar som associeras med en fil eller process | Detector.UnitTests.dll
filePath | Tillgängligt om entityType är *File*.<br>Filsökvägen för aviseringar som associeras med en fil eller process | C: \\ \agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out
processId | Tillgängligt om entityType är *Process.* | 24348
processCommandLine | Tillgängligt om entityType är *Process.* | "Filen är klar att laddas ned \_1911150169.exe"
processCreationTime | Tillgängligt om entityType är *Process.* | 2020-07-18T03:25:38.5269993Z
parentProcessId | Tillgängligt om entityType är *Process.* | 16840
parentProcessCreationTime | Tillgängligt om entityType är *Process.* | 2020-07-18T02:12:32.8616797Z
ipAddress | Tillgängligt om entityType är *IP.* <br>IP-adress för aviseringar som associeras med nätverkshändelser, till exempel *kommunikation till ett skadligt nätverksdestination.* | 62.216.203.204
url | Tillgängligt om entityType är *URL.* <br>URL för aviseringar som är associerade med nätverkshändelser, till exempel *kommunikation till ett skadligt nätverksdestination.* | down.esales360.cn
accountName | Tillgängligt om entityType är *Användare.* | testUser2
domainName | Tillgängligt om entityType är *User.* | europe.corp.contoso
userSid | Tillgängligt om entityType är *User.* | S-1-5-21-1721254763-462695806-1538882281-4156657
aadUserId | Tillgängligt om entityType är *User.* | fc8f7484-f813-4db2-afab-bc1507913fb6
userPrincipalName | Tillgängligt om entityType är *User* / *MailBox* / *MailMessage.* | testUser2@contoso.com
mailboxDisplayName | Tillgängligt om entityType är *MailBox.* | testa Användare2
mailboxAddress | Tillgängligt om entityType är *User* / *MailBox* / *MailMessage.* | testUser2@contoso.com
clusterBy | Tillgängligt om entityType är *MailCluster.* | Ämne; P2SenderDomain; ContentType
avsändare | Tillgängligt om entityType är *User* / *MailBox* / *MailMessage.* | user.abc@mail.contoso.co.in
mottagare | Tillgängligt om entityType är *MailMessage.* | testUser2@contoso.com
ämne | Tillgängligt om entityType är *MailMessage.* | \[EXTERN \] uppmärksamhet
deliveryAction | Tillgängligt om entityType är *MailMessage.* | Levererad
securityGroupId | Tillgängligt om entityType är *SecurityGroup.* | 301c47c8-e15f-4059-ab09-e2ba9ffd372b
securityGroupName | Tillgängligt om entityType är *SecurityGroup.* | Nätverkskonfigurationsoperatorer
registryHive | Tillgängligt om entityType är *register.* | HKEY \_ LOCAL \_ MACHINE |
registryKey | Tillgängligt om entityType är *register.* | SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon
registryValueType | Tillgängligt om entityType är *register.* | Sträng
registryValue | Tillgängligt om entityType är *register.* | 31-00-00-00
deviceId | EVENTUELLA ID:n för enheten som är relaterad till enheten. | 986e5df8b73dacd43c8917d17e523e76b13c75cd

## <a name="example"></a>Exempel

**Begäran**

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

**Svar**

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

- [Få åtkomst till API:er för Microsoft 365 Defender](api-access.md)
- [Läs mer om API-begränsningar och -licensiering](api-terms.md)
- [Förstå felkoder](api-error-codes.md)
- [Incidentöversikt](incidents-overview.md)
- [API:er för tillbud](api-incident.md)
- [API för uppdateringshändelse](api-update-incidents.md)
