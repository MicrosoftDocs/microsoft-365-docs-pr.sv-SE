---
title: FileProfile() funktion i avancerad jakt på Microsoft Threat Protection
description: Lär dig hur du använder FileProfile() för att berika information om filer i dina avancerade jaktfrågeresultat
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, FileProfile, filprofil, funktion, anrikning
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 039b9dc038cd1a1645aee2289f3bdb389eb3f426
ms.sourcegitcommit: eee4f651bd51d5aedd64e42d02bfed8ccb9be4cd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/02/2020
ms.locfileid: "44515940"
---
# <a name="fileprofile"></a>FileProfile()

**Gäller:**
- Microsoft Hotskydd

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

`FileProfile()`Funktionen är en anrikningsfunktion i avancerad [jakt](advanced-hunting-overview.md) som lägger till följande data i filer som hittades av frågan.

| Kolumn | Datatyp | Beskrivning |
|------------|-------------|-------------|
| SHA1 (SHA1) | Sträng | SHA-1 i den akt som den registrerade åtgärden tillämpades på |
| SHA256 (SHA256) | Sträng | SHA-256 i den akt som den registrerade åtgärden tillämpades på |
| VD5 | Sträng | MD5-hash i filen som den registrerade åtgärden tillämpades på |
| Filstorlek | Int | Filens storlek i byte |
| GlobalPrevalence | Int | Antal instanser av den enhet som Microsoft observerat globalt |
| GlobalFirstSeen | Datetime | Datum och tid då enheten först observerades av Microsoft globalt |
| GlobalSeen | Datetime | Datum och tid då entiteten senast observerades av Microsoft globalt |
| Signerat | Sträng | Information om undertecknaren av filen |
| Emittenten | Sträng | Information om den utfärdande certifikatutfärdaren |
| SignerHash (Teckenhash) | Sträng | Unikt hash-värde som identifierar undertecknaren |
| IsCertificateValid | Boolean | Om certifikatet som används för att signera filen är giltigt |
| IsRootSignerMicrosoft | Boolean | Anger om undertecknaren av rotcertifikatet är Microsoft |
| Ärutgrundbar | Boolean | Om filen är en PE-fil (Portable Executable) |
| ThreatName (HotName) | Sträng | Identifieringsnamn för skadlig kod eller andra hot som hittats |
| Publisher | Sträng | Namn på den organisation som publicerade filen |
| SoftwareName (SoftwareName) | Sträng | Namnet på programvaruprodukten |

## <a name="syntax"></a>Syntax

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>Argument

- **x** — fil-ID-kolumn som ska användas: `SHA1` , , eller ; funktionen använder om den inte `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` anges
- **y** — gräns för antalet poster som ska berikas, 1–1000. funktion använder 100 om ospecificerad

## <a name="examples"></a>Exempel

### <a name="project-only-the-sha1-column-and-enrich-it"></a>Projicera endast SHA1-kolumnen och berika den

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a>Berika de första 500 posterna och lista filer med lågprevalens

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