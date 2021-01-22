---
title: Funktionen FileProfile() för avancerad sökning för Microsoft 365 Defender
description: Lär dig hur du använder FileProfile() för att utöka information om filer i dina avancerade sökfrågeresultat
keywords: avancerad sökning, hotsökning, cyberhot, skydd mot cyberhot, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, FileProfile, filprofil, funktion, vinst
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
ms.openlocfilehash: 68196f126ac470088d7ba5e2923accc492d8764c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929556"
---
# <a name="fileprofile"></a>FileProfile()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Funktionen `FileProfile()` är en funktion för avancerad sökning som [lägger](advanced-hunting-overview.md) till följande data i filer som hittas av frågan.

| Kolumn | Datatyp | Beskrivning |
|------------|-------------|-------------|
| SHA1 | sträng | SHA-1 för den fil som den inspelade åtgärden tillämpats på |
| SHA256 | sträng | SHA-256 för filen som den inspelade åtgärden tillämpats på |
| MD5 | sträng | MD5-hash för filen som den inspelade åtgärden tillämpats på |
| FileSize | int | Storlek på filen i byte |
| GlobalPrevalence | int | Antal förekomster av entitet som observerats av Microsoft globalt |
| GlobalFirstSeen | datetime | Datum och tid då entiteten observerades första gången av Microsoft globalt |
| GlobalLastSeen | datetime | Datum och tid då entiteten senast observerades av Microsoft globalt |
| Undertecknaren | sträng | Information om den som signerar filen |
| Utfärdare | sträng | Information om den certifikatutfärdare som utfärdar certifikatutfärdaren |
| SignerHash | sträng | Unikt hashvärde som identifierar undertecknaren |
| IsCertificateValid | boolesk | Om certifikatet som används för att signera filen är giltigt |
| IsRootSignerMicrosoft | boolesk | Anger om undertecknaren av rotcertifikatet är Microsoft |
| IsExecutable | boolesk | Om filen är en PORTABLE Executable-fil (PE) |
| ThreatName | sträng | Identifieringsnamn för skadlig kod eller andra hot hittades |
| Publisher | sträng | Namn på organisationen som publicerade filen |
| SoftwareName | sträng | Namnet på programvaruprodukten |

## <a name="syntax"></a>Syntax

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>Argument

- **x**– kolumn med fil-ID som ska användas för: , , eller `SHA1` `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` funktionen, `SHA1` om det inte har specificerats
- **y**– begränsa antalet poster att utöka, 1–1 000; används 100 om de inte är angivna

## <a name="examples"></a>Exempel

### <a name="project-only-the-sha1-column-and-enrich-it"></a>Projicera endast SHA1-kolumnen och utöka den

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a>Förbättra de första 500 posterna och lista filer som inte är så högena

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Hämta fler frågeexempel](advanced-hunting-shared-queries.md)
