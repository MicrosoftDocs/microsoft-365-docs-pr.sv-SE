---
title: DeviceFileCertificateInfo-tabell i det avancerade schemat för sökning
description: Läs mer om filsigneringsinformation i tabellen DeviceFileCertificateInfo i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, digital signatur, certifikat, filsignering, DeviceFileCertificateInfo
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
ms.openlocfilehash: e35e8e86f6814a5f90a7921f71ccab7247fcc1bc
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931320"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Tabellen `DeviceFileCertificateInfo` i det avancerade [utbildningsschemat](advanced-hunting-overview.md) innehåller information om filsigneringscertifikat. I den här tabellen används data som hämtas från aktiviteter för certifikatverifiering som regelbundet utförs på filer på slutpunkter.

Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid då händelsen spelades in |
| `DeviceId` | sträng | Unikt ID för datorn i tjänsten |
| `DeviceName` | sträng | Fullständigt kvalificerat domännamn (FQDN) för datorn |
| `SHA1` | sträng | SHA-1 för den fil som den inspelade åtgärden tillämpats på |
| `IsSigned` | boolesk | Anger om filen är signerad |
| `SignatureType` | sträng | Anger om signaturinformation har lästs som inbäddat innehåll i själva filen eller lästs från en extern katalogfil |
| `Signer` | sträng | Information om den som signerar filen |
| `SignerHash` | sträng | Unikt hashvärde som identifierar undertecknaren |
| `Issuer` | sträng | Information om den certifikatutfärdare som utfärdar certifikatutfärdaren |
| `IssuerHash` | sträng | Unikt hash-värde som identifierar den certifikatutfärdare som utfärdats (CA) |
| `CertificateSerialNumber` | sträng | Identifierare för certifikatet som är unikt för den utfärdar certifikatutfärdaren (CA) |
| `CrlDistributionPointUrls` | sträng |  JSON-matris med WEBBADRESSer till nätverksresurser som innehåller certifikat och CRL-listor (Certificate Revocation Lists) |
| `CertificateCreationTime` | datetime | Datum och tid då certifikatet skapades |
| `CertificateExpirationTime` | datetime | Datum och tid då certifikatet har ställts in att upphöra |
| `CertificateCountersignatureTime` | datetime | Datum och tid då certifikatet kontrasignerades |
| `IsTrusted` | boolesk | Anger om filen är betrodd baserat på resultaten av WinVerifyTrust-funktionen som söker efter okänd rotcertifikatinformation, ogiltiga signaturer, återkallade certifikat och andra frågebara attribut |
| `IsRootSignerMicrosoft` | boolesk | Anger om undertecknaren av rotcertifikatet är Microsoft |
| `ReportId` | long | Händelseidentifierare baserade på en återkommande räknare. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp. | 

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
