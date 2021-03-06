---
title: Namnge ändringar i det avancerade sökschemat i Microsoft 365 Defender
description: Spåra och granska namnändringar – tabeller och kolumner i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, data, namnändringar, namnbyte, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 31a2f647351c05842f36198ad05b149086b53b1f
ms.sourcegitcommit: a6b998fef5bdb35ec6726c743a24fea721535fcd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/05/2021
ms.locfileid: "50509308"
---
# <a name="advanced-hunting-schema---naming-changes"></a>Avancerat schema för sök – namnändringar

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Det [avancerade sökschemat](advanced-hunting-schema-tables.md) uppdateras regelbundet för att lägga till nya tabeller och kolumner. I vissa fall byter befintliga kolumnnamn namn eller ersätts för att förbättra användarupplevelsen. I den här artikeln kan du läsa om vilka namnändringar som kan påverka dina frågor.

Namnändringar tillämpas automatiskt på frågor som sparas i säkerhetscentret, inklusive frågor som används av anpassade identifieringsregler. Du behöver inte uppdatera dessa frågor manuellt. Du måste dock uppdatera följande frågor:
- Frågor som körs med API:t
- Frågor som sparas någon annanstans utanför säkerhetscentret

## <a name="december-2020"></a>December 2020

| Tabellnamn | Ursprungligt kolumnnamn | Nytt kolumnnamn | Orsak till ändring
|--|--|--|--|
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | Feedback från kunder |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | Feedback från kunder |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | Feedback från kunder |

## <a name="january-2021"></a>Januari 2021

| Kolumnnamn | Det ursprungliga värdenamnet | Nytt värdenamn | Orsak till ändring
|--|--|--|--|
| `DetectionSource` | MCAS |    Microsoft Cloud App Security | Rebranding |
| `DetectionSource` | WindowsDefenderAtp|   EDR| Rebranding |
| `DetectionSource` | WindowsDefenderAv | Antivirus | Rebranding |
| `DetectionSource` | WindowsDefender SmartScreen |  SmartScreen | Rebranding |
| `DetectionSource` | CustomerTI |  Anpassat TI | Rebranding |
| `DetectionSource` | OfficeATP | Microsoft Defender för Office 365 | Rebranding |
| `DetectionSource` | MTP   | Microsoft 365 Defender | Rebranding |
| `DetectionSource` | AzureATP |    Microsoft Defender for Identity | Rebranding |
| `DetectionSource` | CustomDetection   | Anpassad identifiering | Rebranding |
| `DetectionSource` | AutomatedInvestigation |Automatiserad undersökning | Rebranding |
| `DetectionSource` | ThreatExperts | Microsoft Threat Experts | Rebranding |
| `DetectionSource` | TI från tredje part | Tredje parts sensor | Rebranding |
| `ServiceSource` | Microsoft Defender Avancerat skydd| Microsoft Defender för Endpoint | Rebranding |
|`ServiceSource` |Microsoft Hotskydd   | Microsoft 365 Defender | Rebranding |
| `ServiceSource` | Skaffa Office 365 ATP  |Microsoft Defender för Office 365 | Rebranding |
| `ServiceSource` |Azure ATP    |Microsoft Defender for Identity | Rebranding |

`DetectionSource`är tillgängligt i [tabellen AlertInfo.](advanced-hunting-alertinfo-table.md) `ServiceSource`är tillgängligt i [tabellerna AlertEvidence](advanced-hunting-alertevidence-table.md) [och AlertInfo.](advanced-hunting-alertinfo-table.md) 

## <a name="february-2021"></a>Februari 2021

1. I [tabellerna EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) och [EmailEvents](advanced-hunting-emailevents-table.md) `MalwareFilterVerdict` har `PhishFilterVerdict` kolumnerna ersatts med `ThreatTypes` kolumnen. Kolumnerna `MalwareDetectionMethod` och de har också `PhishDetectionMethod` ersatts med `DetectionMethods` kolumnen. På så sätt kan vi ge mer information under de nya kolumnerna. Mappningen anges nedan.

| Tabellnamn | Ursprungligt kolumnnamn | Nytt kolumnnamn | Orsak till ändring
|--|--|--|--|
| `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | Inkludera fler identifieringsmetoder |
| `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | Inkludera fler hottyper |
| `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | Inkludera fler identifieringsmetoder |
| `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | Inkludera fler hottyper |


2. I `EmailAttachmentInfo` tabellerna `EmailEvents` och kolumnen har lagts till för att ge mer information om `ThreatNames` e-posthotet. Den här kolumnen innehåller värden som Spam eller Phish.

3. I [tabellen DeviceInfo](advanced-hunting-deviceinfo-table.md) har kolumnen `DeviceObjectId` ersatts med kolumnen `AadDeviceId` baserat på feedback från kunder.

4. I tabellen [DeviceEvents](advanced-hunting-deviceevents-table.md) har flera ActionType-namn ändrats för att bättre återspegla beskrivningen av åtgärden. Information om ändringarna finns nedan.

| Tabellnamn | Ursprungligt ActionType-namn | Nytt ActionType-namn | Orsak till ändring
|--|--|--|--|
| `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | Feedback från kunder |
| `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | Feedback från kunder |
| `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | Feedback från kunder |
| `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | Feedback från kunder |
| `DeviceEvents` | `AntivirusDetection` | `EdrBlock` | Feedback från kunder |





## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)