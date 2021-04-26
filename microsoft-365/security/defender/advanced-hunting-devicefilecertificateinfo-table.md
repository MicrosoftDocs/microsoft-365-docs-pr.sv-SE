---
title: Tabellen DeviceFileCertificateInfo i det avancerade sökschemat
description: Mer information om filsignering i tabellen DeviceFileCertificateInfo i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, sökning efter cyberhot, Microsoft 365 Defender, microsoft 365, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, digital signatur, certifikat, filsignering, DeviceFileCertificateInfo
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
ms.openlocfilehash: 1f894f3fc8cff2113004ff9c9e34ec2ca0144799
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023219"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender
- Microsoft Defender för Endpoint

Tabellen `DeviceFileCertificateInfo` i det avancerade schemat för [sökning](advanced-hunting-overview.md) innehåller information om filsigneringscertifikat. I den här tabellen används data som inhämtats från aktiviteter för certifikatverifiering regelbundet som utförs på filer på slutpunkter.

Information om andra tabeller i det avancerade sökschemat finns [i den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid då händelsen spelades in |
| `DeviceId` | sträng | Unikt ID för datorn i tjänsten |
| `DeviceName` | sträng | Fullständigt kvalificerat domännamn (FQDN) för datorn |
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
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
