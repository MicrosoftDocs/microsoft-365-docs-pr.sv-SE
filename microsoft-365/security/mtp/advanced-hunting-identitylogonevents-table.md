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
ms.openlocfilehash: 19437caf4f3b0dcb6eb6ccad81d1ed3917df7996
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204917"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

**Gäller:**
- Microsoft Hotskydd

`IdentityLogonEvents`Tabellen i det avancerade [jaktschemat](advanced-hunting-overview.md) innehåller information om autentiseringsaktiviteter som görs via din lokala Active Directory som fångas av Azure ATP och autentiseringsaktiviteter relaterade till Microsofts onlinetjänster som fångas av Microsoft Cloud App Security. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

>[!NOTE]
>Den här tabellen täcker Azure Active Directory (AD) inloggningsaktiviteter som spåras av Cloud App Security, särskilt interaktiva inloggningar och autentiseringsaktiviteter med ActiveSync och andra äldre protokoll. Icke-interaktiva inloggningar som inte är tillgängliga i den här tabellen kan visas i Granskningsloggen för Azure AD. [Läs mer om hur du ansluter Cloud App Security till Microsoft 365](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum och tid då händelsen spelades in |
| `ActionType` | Sträng | Typ av aktivitet som utlöste händelsen |
| `LogonType` | Sträng | Typ av inloggningssession, särskilt:<br><br> - **Interaktiv** - Användaren interagerar fysiskt med maskinen med det lokala tangentbordet och skärmen<br><br> - **Fjärr interaktiva (RDP)-inloggningar** - Användaren interagerar med datorn på distans med fjärrskrivbord, Terminal Services, Fjärrhjälp eller andra RDP-klienter<br><br> - **Nätverk** - Session initieras när datorn används med PsExec eller när delade resurser på datorn, till exempel skrivare och delade mappar, används<br><br> - **Batch** - Session initierad av schemalagda aktiviteter<br><br> - **Service** - Session initierad av tjänster när de börjar |
| `Application` | Sträng | Ansökan som utförde den inspelade åtgärden |
| `Protocol` | Sträng | Nätverksprotokoll som används |
| `FailureReason` | Sträng | Information som förklarar varför den registrerade åtgärden misslyckades |
| `AccountName` | Sträng | Kontots användarnamn |
| `AccountDomain` | Sträng | Kontots domän |
| `AccountUpn` | Sträng | Användarens huvudnamn (UPN) för kontot |
| `AccountSid` | Sträng | Säkerhetsidentifierare (SID) för kontot |
| `AccountObjectId` | Sträng | Unik identifierare för kontot i Azure AD |
| `AccountDisplayName` | Sträng | Namn på den kontoanvändare som visas i adressboken. Vanligtvis en kombination av ett givet eller förnamn, en mellaninitiering och ett efternamn eller efternamn. |
| `DeviceName` | Sträng | Fullständigt kvalificerat domännamn (FQDN) för enheten |
| `DeviceType` | Sträng | Typ av enhet |
| `OSPlatform` | Sträng | Plattform för operativsystemet som körs på maskinen. Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7. |
| `IPAddress` | Sträng | IP-adress som tilldelats slutpunkten och som används under relaterad nätverkskommunikation |
| `DestinationDeviceName` | Sträng | Namn på den enhet som kör serverprogrammet som bearbetade den inspelade åtgärden |
| `DestinationIPAddress` | Sträng | IP-adressen för den enhet som kör serverprogrammet som bearbetade den inspelade åtgärden |
| `TargetDeviceName` | Sträng | Fullständigt kvalificerat domännamn (FQDN) för den enhet som den registrerade åtgärden tillämpades på |
| `TargetAccountDisplayName` | Sträng | Visa namnet på det konto som den registrerade åtgärden tillämpades på |
| `Location` | Sträng | Ort, land eller annan geografisk plats som är associerad med händelsen |
| `Isp` | Sträng | Internet-leverantör (ISP) som är associerad med IP-adressen för slutpunkten |
| `ReportId` | Lång | Unik identifierare för händelsen |
| `AdditionalFields` | Sträng | Ytterligare information om entiteten eller händelsen |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jakten på hot på olika enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)