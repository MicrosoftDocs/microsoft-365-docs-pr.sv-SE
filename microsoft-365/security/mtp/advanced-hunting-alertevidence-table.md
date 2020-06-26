---
title: AlertEvidence-tabellen i det avancerade jaktschemat
description: Lär dig mer om fil-, nätverksadress-, användar- eller enhetsinformation som är associerad med genererade aviseringar i tabellen AlertEvidence i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, Microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, AlertInfo, alert, enheter, bevis, fil, IP-adress, enhet, maskin, användare, konto
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
ms.openlocfilehash: a0f2ae36752a4415da7c1bc39ce35bd7f744a764
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899357"
---
# <a name="alertevidence"></a>AlertEvidence

**Gäller:**
- Microsoft Hotskydd

`AlertEvidence`Tabellen i det avancerade [jaktschemat](advanced-hunting-overview.md) innehåller information om olika entiteter – filer, IP-adresser, webbadresser, användare eller enheter – som är associerade med aviseringar från Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security och Azure ATP. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum och tid då händelsen spelades in |
| `AlertId` | Sträng | Unik identifierare för aviseringen |
| `EntityType` | Sträng | Typ av objekt, till exempel en fil, en process, en enhet eller en användare |
| `EvidenceRole` | Sträng | Hur företaget deltar i en registrering, som anger om den påverkas eller endast är relaterad till |
| `SHA1` | Sträng | SHA-1 i den akt som den registrerade åtgärden tillämpades på |
| `SHA256` | Sträng | SHA-256 i filen som den inspelade åtgärden tillämpades på. Det här fältet fylls vanligtvis inte i – använd kolumnen SHA1 när det är tillgängligt. |
| `RemoteIP` | Sträng | IP-adress som var ansluten till |
| `RemoteUrl` | Sträng | URL eller fullständigt kvalificerat domännamn (FQDN) som var anslutet till |
| `AccountName` | Sträng | Kontots användarnamn |
| `AccountDomain` | Sträng | Kontots domän |
| `AccountSid` | Sträng | Säkerhetsidentifierare (SID) för kontot |
| `AccountObjectId` | Sträng | Unik identifierare för kontot i Azure AD |
| `DeviceId` | Sträng | Unik identifierare för maskinen i tjänsten |
| `ThreatFamily` | Sträng | Malware familj att den misstänkta eller skadliga filen eller processen har klassificerats under |
| `EvidenceDirection` | Sträng | Anger om entiteten är källan eller målet för en nätverksanslutning |
| `AdditionalFields` | Sträng | Ytterligare information om händelsen i JSON-matrisformat |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jakten på hot på olika enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
