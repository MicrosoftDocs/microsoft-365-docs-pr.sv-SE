---
title: Funktionen FileProfile() i avancerad sökning efter Microsoft Defender för Endpoint
description: Lär dig använda FileProfile() för att utöka information om filer i avancerade sökresultat för sökfrågor
keywords: avancerad sökning, hotsökning, sökning efter cyberhot, mdatp, Microsoft Defender ATP, Microsoft Defender för slutpunkt, Windows Defender, Windows Defender ATP, Windows Defender Avancerat skydd, sökning, fråga, telemetri, schemareferens, kusto, FileProfile, filprofil, funktion, vinst
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 6c828418d27db24cbd6e87f040486b3abc45e6c6
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499556"
---
# <a name="fileprofile"></a>FileProfile()

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

Funktionen `FileProfile()` är en funktion för [](advanced-hunting-overview.md) avancerad sökning som lägger till följande data i filer som hittas av frågan.

Kolumn | Datatyp | Beskrivning
-|-|-
SHA1 | sträng | SHA-1 för filen som den inspelade åtgärden tillämpats på
SHA256 | sträng | SHA-256 av filen som den inspelade åtgärden tillämpats på
MD5 | sträng | MD5-hash för filen som den inspelade åtgärden tillämpats på
FileSize | int | Storlek på filen i byte
GlobalPrevalence | int | Antal förekomster av entitet som observerats av Microsoft globalt
GlobalFirstSeen | datetime | Datum och tid då enheten för första gången observerades av Microsoft globalt
GlobalLastSeen | datetime | Datum och tid då enheten senast observerades av Microsoft globalt
Undertecknaren | sträng | Information om den som signerar filen
Utfärdare | sträng | Information om den utfärdar certifikatutfärdaren (CA)
SignerHash | sträng | Unikt hashvärde som identifierar undertecknaren
IsCertificateValid | boolesk | Om det certifikat som används för att signera filen är giltigt
IsRootSignerMicrosoft | boolesk | Anger om undertecknaren av rotcertifikatet är Microsoft
IsExecutable | boolesk | Om filen är en PE-fil (Portable Executable)
ThreatName | sträng | Namn för identifiering av skadlig programvara eller andra hot som påträffades
Publisher | sträng | Namnet på organisationen som publicerade filen
SoftwareName | sträng | Namnet på programvaruprodukten

## <a name="syntax"></a>Syntax

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>Argument

- **x** – kolumn med fil-ID som ska användas: , eller ; funktion `SHA1` som används om det inte är `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` anspekt
- **y** – begränsning till antalet poster att utöka, 1-1000; funktionen använder 100 om det inte är anspekt

## <a name="examples"></a>Exempel

### <a name="project-only-the-sha1-column-and-enrich-it"></a>Projicera endast KOLUMNEN SHA1 och utöka den

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a>Förbättra de första 500 posterna och lista filer med låg nivå av arkiv

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
- [Förstå schemat](advanced-hunting-schema-reference.md)
