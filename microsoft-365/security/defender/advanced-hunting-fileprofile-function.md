---
title: Funktionen FileProfile() i avancerad sökning för Microsoft 365 Defender
description: Lär dig använda FileProfile() för att utöka information om filer i avancerade sökresultat för sökfrågor
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, FileProfile, file profile, function, enrichment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ea4f22b70e607b42155342dde1ac16b1ad640981
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498455"
---
# <a name="fileprofile"></a>FileProfile()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Funktionen `FileProfile()` är en funktion för [](advanced-hunting-overview.md) avancerad sökning som lägger till följande data i filer som hittas av frågan.

| Kolumn | Datatyp | Beskrivning |
|------------|---------------|-------------|
| `SHA1` | sträng | SHA-1 för filen som den inspelade åtgärden tillämpats på |
| `SHA256` | sträng | SHA-256 av filen som den inspelade åtgärden tillämpats på |
| `MD5` | sträng | MD5-hash för filen som den inspelade åtgärden tillämpats på |
| `FileSize` | int | Storlek på filen i byte |
| `GlobalPrevalence` | int | Antal förekomster av entitet som observerats av Microsoft globalt |
| `GlobalFirstSeen` | datetime | Datum och tid då enheten för första gången observerades av Microsoft globalt |
| `GlobalLastSeen` | datetime | Datum och tid då enheten senast observerades av Microsoft globalt |
| `Signer` | sträng | Information om den som signerar filen |
| `Issuer` | sträng | Information om den utfärdar certifikatutfärdaren (CA) |
| `SignerHash` | sträng | Unikt hashvärde som identifierar undertecknaren |
| `IsCertificateValid` | boolesk | Om det certifikat som används för att signera filen är giltigt |
| `IsRootSignerMicrosoft` | boolesk | Anger om undertecknaren av rotcertifikatet är Microsoft |
| `SignatureState` | sträng | Status för filsignaturen: SigneradeValid – filen är signerad med en giltig signatur, SigneradInvalid – filen har signerats men certifikatet är ogiltigt, inte signerat – filen är inte signerad, okänd – information om filen kan inte hämtas
| `IsExecutable` | boolesk | Om filen är en PE-fil (Portable Executable) |
| `ThreatName` | sträng | Namn för identifiering av skadlig programvara eller andra hot som påträffades |
| `Publisher` | sträng | Namnet på organisationen som publicerade filen |
| `SoftwareName` | sträng | Namnet på programvaruprodukten |

## <a name="syntax"></a>Syntax

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>Argument

- **x**– den kolumn med fil-ID som ska användas med funktionen : , , eller ; om `SHA1` det inte är `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` användningsområden
- **y**– begränsning till antalet poster att utöka, 1-1000; funktionen använder 100 om det inte är anspekt


>[!TIP]
> Tilläggsfunktioner visar endast kompletterande information när de är tillgängliga. Tillgängligheten för informationen är varierad och beror på en mängd faktorer. Tänk på det här när du använder FileProfile() i dina frågor eller när du skapar anpassade identifieringar. För bästa resultat rekommenderar vi att du använder funktionen FileProfile() med SHA1.

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
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Hämta fler frågeexempel](advanced-hunting-shared-queries.md)
