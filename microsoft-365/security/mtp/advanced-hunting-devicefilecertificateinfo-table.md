---
title: DeviceFileCertificateInfo-tabellen i det avancerade jaktschemat
description: Lär dig mer om filsigneringsinformation i tabellen DeviceFileCertificateInfo i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, digital signatur, certifikat, filsignering, DeviceFileCertificateInfo
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
ms.openlocfilehash: fcbd487aeed633176c86fd22bfcd156be02fea22
ms.sourcegitcommit: b6c4b514b2cb6739af949780d7e2a5a5c8dcc161
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2020
ms.locfileid: "43900799"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

**Gäller:**
- Microsoft Hotskydd

Tabellen `DeviceFileCertificateInfo` i det [avancerade jaktschemat](advanced-hunting-overview.md) innehåller information om certifikat för filsignering. I den här tabellen används data som erhållits från certifikatverifieringsaktiviteter som regelbundet utförs på filer på slutpunkter.

Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum och tid då händelsen spelades in |
| `DeviceId` | Sträng | Unik identifierare för maskinen i tjänsten |
| `DeviceName` | Sträng | Fullständigt kvalificerat domännamn (FQDN) för maskinen |
| `SHA1` | Sträng | SHA-1 i den akt som den registrerade åtgärden tillämpades på |
| `IsSigned` | Boolean | Anger om filen är signerad |
| `SignatureType` | Sträng | Anger om signaturinformation lästes som inbäddat innehåll i själva filen eller lästes från en extern katalogfil |
| `Signer` | Sträng | Information om undertecknaren av filen |
| `SignerHash` | Sträng | Unikt hash-värde som identifierar undertecknaren |
| `Issuer` | Sträng | Information om den utfärdande certifikatutfärdaren |
| `IssuerHash` | Sträng | Unikt hash-värde som identifierar utfärdande certifikatutfärdarh (CA) |
| `CertificateSerialNumber` | Sträng | Identifierare för certifikatet som är unikt för den utfärdande certifikatutfärdaren |
| `CrlDistributionPointUrls` | Sträng |  JSON-matris med url:er för nätverksresurser som innehåller certifikat och listor över återkallade certifikat (CRL:er) |
| `CertificateCreationTime` | Datetime | Datum och tid då certifikatet skapades |
| `CertificateExpirationTime` | Datetime | Datum och tid då certifikatet har angetts för att upphöra att gälla |
| `CertificateCountersignatureTime` | Datetime | Datum och tid då certifikatet kontrasignerades |
| `IsTrusted` | Boolean | Anger om filen är betrodd baserat på resultaten av winverifytrust-funktionen, som söker efter okänd rotcertifikatinformation, ogiltiga signaturer, återkallade certifikat och andra tvivelaktiga attribut |
| `IsRootSignerMicrosoft` | Boolean | Anger om undertecknaren av rotcertifikatet är Microsoft |
| `ReportId` | Lång | Händelseidentifierare baserat på en upprepande räknare. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp. | 

## <a name="related-topics"></a>Relaterade ämnen
- [Proaktivt jakt efter hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jakten på hot på olika enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
