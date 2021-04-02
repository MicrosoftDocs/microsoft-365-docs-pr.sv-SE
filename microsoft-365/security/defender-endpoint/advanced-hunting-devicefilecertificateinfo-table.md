---
title: Tabellen DeviceFileCertificateInfo i det avancerade sökschemat
description: Mer information om filsignering i tabellen DeviceFileCertificateInfo i det avancerade sökschemat
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, digital signature, certificate, file signing, DeviceFileCertificateInfo
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
ms.date: 01/14/2020
ms.technology: mde
ms.openlocfilehash: f693c54828d8ede1d21167817f77b875ab5680ce
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499170"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

Tabellen `DeviceFileCertificateInfo` i det avancerade schemat för [sökning](advanced-hunting-overview.md) innehåller information om filsigneringscertifikat. I den här tabellen används data som inhämtats från aktiviteter för certifikatverifiering regelbundet som utförs på filer på slutpunkter.

Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökningsschema.](advanced-hunting-schema-reference.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid då händelsen spelades in |
| `DeviceId` | sträng | Unikt ID för enheten i tjänsten |
| `DeviceName` | sträng | Fullständigt kvalificerat domännamn (FQDN) för enheten |
| `SHA1` | sträng | SHA-1 för filen som den inspelade åtgärden tillämpats på |
| `IsSigned` | boolesk | Anger om filen är signerad |
| `SignatureType` | sträng | Anger om signaturinformation har lästs som inbäddat innehåll i själva filen eller läst från en extern katalogfil |
| `Signer` | sträng | Information om den som signerar filen |
| `SignerHash` | sträng | Unikt hashvärde som identifierar undertecknaren |
| `Issuer` | sträng | Information om den utfärdar certifikatutfärdaren (CA) |
| `IssuerHash` | sträng | Unikt hash-värde som identifierar den certifikatutfärdare som utfärdar certifikatutfärdaren (CA) |
| `CertificateSerialNumber` | sträng | Identifierare för certifikatet som är unikt för den certifikatutfärdare som utfärdar certifikatet (CA) |
| `CrlDistributionPointUrls` | sträng |  JSON-matris med URL:er för nätverksresurser som innehåller certifikat och listor över återkallade certifikat (CRL) |
| `CertificateCreationTime` | datetime | Datum och tid då certifikatet skapades |
| `CertificateExpirationTime` | datetime | Datum och tid då certifikatet är inställt på att upphöra |
| `CertificateCountersignatureTime` | datetime | Datum och tid då certifikatet var räknare |
| `IsTrusted` | boolesk | Anger om filen är betrodd baserat på resultaten av WinVerifyTrust-funktionen som söker efter okänd rotcertifikatinformation, ogiltiga signaturer, återkallade certifikat och andra tveksamma attribut |
| `IsRootSignerMicrosoft` | boolesk | Anger om undertecknaren av rotcertifikatet är Microsoft |
| `ReportId` | long | Händelseidentifierare baserat på en räknare för upprepande händelser. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp. |


## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Förstå schemat](advanced-hunting-schema-reference.md)
