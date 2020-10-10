---
title: DeviceFileCertificateInfo-tabell i det avancerade jakt-schemat
description: Lär dig mer om fil signerings information i tabellen DeviceFileCertificateInfo för Advanced jakt-schemat
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, digital signatur, certifikat, fil signering, DeviceFileCertificateInfo
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
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 3c9ee14fc316f767ad57fe32920dd3034a1cd795
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412244"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Threat Protection

`DeviceFileCertificateInfo`Tabellen i det [avancerade jakt](advanced-hunting-overview.md) -schemat innehåller information om fil signerings certifikat. I den här tabellen används data som hämtats från certifikat verifierings aktiviteter regelbundet på filer på slut punkter.

Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid när händelsen registrerades |
| `DeviceId` | strängvärdet | Unik identifierare för datorn i tjänsten |
| `DeviceName` | strängvärdet | Det fullständigt kvalificerade domän namnet (FQDN) för datorn |
| `SHA1` | strängvärdet | SHA-1 av filen som den inspelade åtgärden tillämpades på |
| `IsSigned` | returtyp | Anger om filen är signerad |
| `SignatureType` | strängvärdet | Anger om signaturinformation lästes som inbäddat innehåll i filen eller läses från en extern katalog fil |
| `Signer` | strängvärdet | Information om undertecknaren av filen |
| `SignerHash` | strängvärdet | Unikt hashvärde identifierar undertecknaren |
| `Issuer` | strängvärdet | Information om utfärdande av certifikat utfärdare (CA) |
| `IssuerHash` | strängvärdet | Unikt hashvärde identifieras som utfärdar certifikat utfärdare (CA) |
| `CertificateSerialNumber` | strängvärdet | Identifierare för det certifikat som är unikt för den utfärdande certifikat utfärdaren (CA) |
| `CrlDistributionPointUrls` | strängvärdet |  JSON-matris som visar URL-adresserna för nätverks resurser som innehåller certifikat och listor över återkallade certifikat (CRL) |
| `CertificateCreationTime` | datetime | Datum och tid då certifikatet skapades |
| `CertificateExpirationTime` | datetime | Datum och tid då certifikatet är inställt på att upphöra |
| `CertificateCountersignatureTime` | datetime | Datum och tid då certifikatet undertecknades |
| `IsTrusted` | returtyp | Anger om filen är betrodd baserat på resultatet av WinVerifyTrust-funktionen, som söker efter information om okända rot certifikat, ogiltiga signaturer, återkallade certifikat och andra fråge bara attribut |
| `IsRootSignerMicrosoft` | returtyp | Anger om undertecknaren hos rot certifikatet är Microsoft |
| `ReportId` | tids | Händelse identifierare baserad på en upprepande räknare. För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna enhets namn och tidsstämpel. | 

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
