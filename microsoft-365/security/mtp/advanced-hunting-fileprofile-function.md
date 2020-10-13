---
title: FileProfile ()-funktion i avancerad jakt för skydd mot Microsoft Threat
description: Lär dig hur du använder FileProfile () för att utöka informationen om filer i de avancerade frågeresultaten
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, FileProfile, fil profil, funktion och berikning
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: e99e545b5578b5eff8c19345dc672f735e4f7bd2
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430591"
---
# <a name="fileprofile"></a>FileProfile()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Threat Protection

`FileProfile()`Funktionen är en mångsidig funktion i [Avancerad jakt](advanced-hunting-overview.md) som lägger till följande data i filer som hittas av frågan.

| Kolumn | Datatyp | Beskrivning |
|------------|-------------|-------------|
| SHA1 | strängvärdet | SHA-1 av filen som den inspelade åtgärden tillämpades på |
| SHA256 | strängvärdet | SHA-256 av filen som den inspelade åtgärden tillämpades på |
| MD5 | strängvärdet | MD5-hash för filen som den inspelade åtgärden tillämpades för |
| Storlek | signera | Storleken på filen i byte |
| GlobalPrevalence | signera | Antal instanser av enheten som Microsoft globalt har iakttagit |
| GlobalFirstSeen | datetime | Datum och tid då enheten först observerades av Microsoft globalt |
| GlobalLastSeen | datetime | Datum och tid då enheten senast kom från Microsoft globalt |
| Undertecknarens | strängvärdet | Information om undertecknaren av filen |
| Utgivaren | strängvärdet | Information om utfärdande av certifikat utfärdare (CA) |
| SignerHash | strängvärdet | Unikt hashvärde identifierar undertecknaren |
| IsCertificateValid | returtyp | Om certifikatet som används för att signera filen är giltigt |
| IsRootSignerMicrosoft | returtyp | Anger om undertecknaren hos rot certifikatet är Microsoft |
| IsExecutable | returtyp | Om filen är en fil för Portable körbara filer (PE) |
| ThreatName | strängvärdet | Identifierings namn för skadlig program vara eller andra hot Funna |
| Publisher | strängvärdet | Namn på organisationen som har publicerat filen |
| SoftwareName | strängvärdet | Namnet på program varu produkten |

## <a name="syntax"></a>Frågesyntaxen

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>Argument

- **x**— kolumnen fil-ID som ska användas: `SHA1` , `SHA256` ,, `InitiatingProcessSHA1` eller `InitiatingProcessSHA256` ;-funktionen används `SHA1` om ospecificerad
- **y**– begränsa antalet poster som ska utökas, 1-1000; funktionen använder 100 om ospecificerad

## <a name="examples"></a>Exempel

### <a name="project-only-the-sha1-column-and-enrich-it"></a>Endast kolumnen SHA1 och utöka den

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a>Utöka de första 500-posterna och visa en lista över lågprioriterade filer

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
- [Exempel på fler frågor](advanced-hunting-shared-queries.md)
