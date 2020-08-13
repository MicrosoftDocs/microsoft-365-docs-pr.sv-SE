---
title: AlertEvidence-tabell i det avancerade jakt-schemat
description: Lär dig mer om fil-, nätverks adress-, användar-eller enhets information som är kopplad till genererade aviseringar i AlertEvidence-tabellen för Advanced jakt-schemat
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 8fc713db33b0e40adcd0975d26c10daece636ab1
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649517"
---
# <a name="alertevidence"></a>AlertEvidence

**Gäller för:**
- Microsoft Hotskydd

`AlertEvidence`Tabellen i det [avancerade jakt](advanced-hunting-overview.md) -schemat innehåller information om olika enheter — filer, IP-adresser, URL: er, användare eller enheter – associerade med aviseringar från Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security och Azure ATP. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid när händelsen registrerades |
| `AlertId` | strängvärdet | Unik identifierare för aviseringen |
| `EntityType` | strängvärdet | Typ av objekt, till exempel en fil, en process, en enhet eller en användare |
| `EvidenceRole` | strängvärdet | Hur enheten är involverad i en avisering och visar om den påverkas eller bara är relaterad |
| `SHA1` | strängvärdet | SHA-1 av filen som den inspelade åtgärden tillämpades på |
| `SHA256` | strängvärdet | SHA-256 av filen som den registrerade åtgärden tillämpades på. Det här fältet är oftast inte ifyllt – Använd SHA1-kolumnen när det är tillgängligt. |
| `RemoteIP` | strängvärdet | IP-adress som var ansluten till |
| `RemoteUrl` | strängvärdet | URL-adressen eller det fullständigt kvalificerade domän namnet (FQDN) som anslöts till |
| `AccountName` | strängvärdet | Kontots användar namn |
| `AccountDomain` | strängvärdet | Kontots domän |
| `AccountSid` | strängvärdet | Kontots säkerhets identifierare (SID) |
| `AccountObjectId` | strängvärdet | Unik identifierare för kontot i Azure AD |
| `DeviceId` | strängvärdet | Unik identifierare för datorn i tjänsten |
| `ThreatFamily` | strängvärdet | Familjen skadlig program vara som den misstänkta eller skadliga filen eller processen har klassificerats under |
| `EvidenceDirection` | strängvärdet | Anger om enheten är källa eller mål för en nätverks anslutning |
| `AdditionalFields` | strängvärdet | Ytterligare information om händelsen i JSON-mat ris format |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
