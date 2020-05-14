---
title: I tabellen IdentityLogonEvents i det avancerade jaktschemat
description: Lär dig mer om autentiseringshändelser som registrerats av Active Directory i tabellen IdentityLogonEvents i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, IdentityLogonEvents, Azure AD, Active Directory, Azure ATP, identiteter
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
ms.openlocfilehash: 754c9476e81dd84e2140e18b8684061f52c287ba
ms.sourcegitcommit: ad789f1e7bf9c9dc0d45c731373e667a26ed30b1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/13/2020
ms.locfileid: "42929332"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

**Gäller:**
- Microsoft Hotskydd

`IdentityLogonEvents`Tabellen i det avancerade [jaktschemat](advanced-hunting-overview.md) innehåller information om autentiseringsaktiviteter som registrerats av Azure Active Directory och andra Microsoft-molnappar och -tjänster. Använd den här referensen om du vill skapa frågor som returnerar information från den här tabellen.

Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum och tid då händelsen spelades in |
| `ActionType` | Sträng | Typ av aktivitet som utlöste händelsen |
| `LogonType` | Sträng | Typ av inloggningssession, särskilt:<br><br> - **Interaktiv** - Användaren interagerar fysiskt med maskinen med det lokala tangentbordet och skärmen<br><br> - **Fjärr interaktiva (RDP)-inloggningar** - Användaren interagerar med datorn på distans med fjärrskrivbord, Terminal Services, Fjärrhjälp eller andra RDP-klienter<br><br> - **Nätverk** - Session initieras när datorn används med PsExec eller när delade resurser på datorn, till exempel skrivare och delade mappar, används<br><br> - **Batch** - Session initierad av schemalagda aktiviteter<br><br> - **Service** - Session initierad av tjänster när de startar |
| `Application` | Sträng | Ansökan som utförde den registrerade åtgärden |
| `Protocol` | Sträng | Protokoll som används under kommunikationen |
| `AccountName` | Sträng | Kontots användarnamn |
| `AccountDomain` | Sträng | Kontots domän |
| `AccountUpn` | Sträng | Kontots användarnamn (UPN) |
| `AccountSid` | Sträng | Säkerhetsidentifierare (SID) för kontot |
| `AccountObjectId` | Sträng | Unik identifierare för kontot i Azure AD |
| `AccountDisplayName` | Sträng | Namn på den kontoanvändare som visas i adressboken. Vanligtvis en kombination av ett givet eller förnamn, en mellaninitiering och ett efternamn eller efternamn. |
| `DeviceName` | Sträng | Fullständigt kvalificerat domännamn (FQDN) för maskinen |
| `DeviceType` | Sträng | Typ av enhet |
| `OSPlatform` | Sträng | Plattform för operativsystemet som körs på maskinen. Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7. |
| `IPAddress` | Sträng | IP-adress som tilldelats slutpunkten och som används under relaterad nätverkskommunikation |
| `Location` | Sträng | Ort, land eller annan geografisk plats som är associerad med händelsen |
| `Isp` | Sträng | Internet-leverantör (ISP) som är associerad med ip-adressen för slutpunkten |

## <a name="related-topics"></a>Relaterade ämnen
- [Proaktivt jakt efter hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jakten på hot på olika enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
