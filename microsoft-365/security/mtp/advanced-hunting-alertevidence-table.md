---
title: AlertEvidence-tabell i det avancerade jakt-schemat
description: Lär dig mer om information som är associerad med aviseringar i AlertEvidence-tabellen för Advanced jakt-schemat
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, AlertInfo, avisering, enheter, bevis, fil, IP-adress, enhet, dator, användare, konto
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
ms.openlocfilehash: 7f6a4f7592e6a8fde0b7ae6269f07ce7f76a5730
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430169"
---
# <a name="alertevidence"></a>AlertEvidence

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Threat Protection

`AlertEvidence`Tabellen i det [avancerade jakt](advanced-hunting-overview.md) -schemat innehåller information om olika enheter — filer, IP-adresser, URL: er, användare eller enheter – associerade med aviseringar från Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security och Azure ATP. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid när händelsen registrerades |
| `AlertId` | strängvärdet | Unik identifierare för aviseringen |
| `ServiceSource` | strängvärdet | Produkt eller tjänst som tillhandahöll aviserings informationen |
| `EntityType` | strängvärdet | Typ av objekt, till exempel en fil, en process, en enhet eller en användare |
| `EvidenceRole` | strängvärdet | Hur enheten är involverad i en avisering och visar om den påverkas eller bara är relaterad |
| `EvidenceDirection` | strängvärdet | Anger om enheten är källa eller mål för en nätverks anslutning |
| `FileName` | strängvärdet | Namnet på filen som den inspelade åtgärden tillämpades för |
| `FolderPath` | strängvärdet | Mapp som innehåller filen som den inspelade åtgärden tillämpades för |
| `SHA1` | strängvärdet | SHA-1 av filen som den inspelade åtgärden tillämpades på |
| `SHA256` | strängvärdet | SHA-256 av filen som den registrerade åtgärden tillämpades på. Det här fältet är oftast inte ifyllt – Använd SHA1-kolumnen när det är tillgängligt. |
| `FileSize` | signera | Storleken på filen i byte |
| `ThreatFamily` | strängvärdet | Familjen skadlig program vara som den misstänkta eller skadliga filen eller processen har klassificerats under |
| `RemoteIP` | strängvärdet | IP-adress som var ansluten till |
| `RemoteUrl` | strängvärdet | URL-adressen eller det fullständigt kvalificerade domän namnet (FQDN) som anslöts till |
| `AccountName` | strängvärdet | Kontots användar namn |
| `AccountDomain` | strängvärdet | Kontots domän |
| `AccountSid` | strängvärdet | Kontots säkerhets identifierare (SID) |
| `AccountObjectId` | strängvärdet | Unik identifierare för kontot i Azure Active Directory |
| `DeviceId` | strängvärdet | Unik identifierare för enheten i tjänsten |
| `DeviceName` | strängvärdet | Det fullständigt kvalificerade domän namnet (FQDN) för datorn |
| `LocalIP` | strängvärdet | IP-adress som tilldelats till den lokala enheten under kommunikationen |
| `NetworkMessageId` | strängvärdet | Unik identifierare för e-posten som genereras av Office 365 |
| `EmailSubject` | strängvärdet | Ämne för e-postmeddelandet |
| `ApplicationId` | strängvärdet | Unik identifierare för programmet |
| `Application` | strängvärdet | Program som utförde den inspelade åtgärden |
| `ProcessCommandLine` | strängvärdet | Kommando rad som används för att skapa den nya processen |
| `AdditionalFields` | strängvärdet | Ytterligare information om händelsen i JSON-mat ris format |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
