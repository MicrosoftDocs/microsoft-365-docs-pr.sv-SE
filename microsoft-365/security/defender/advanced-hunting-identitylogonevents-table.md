---
title: Tabellen IdentityLogonEvents i det avancerade jaktschemat
description: Lär dig mer om autentiseringshändelser som registrerats av Active Directory i tabellen IdentityLogonEvents i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, Microsoft 365 Defender, microsoft 365, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, IdentityLogonEvents, Azure AD, Active Directory, Microsoft Defender for Identity, identiteter
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
ms.openlocfilehash: 3cd0c0f371c73a515704791e829be7266d400580
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572759"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Tabellen `IdentityLogonEvents` i det avancerade jaktschemat innehåller information om autentiseringsaktiviteter som görs via din lokala Active Directory som hämtats av Microsoft Defender för [identitets-](advanced-hunting-overview.md) och autentiseringsaktiviteter relaterade till Microsofts onlinetjänster som fångas Microsoft Cloud App Security. Använd den här referensen om du vill skapa frågor som returnerar information från den här tabellen.

>[!TIP]
> Om du vill ha detaljerad information om de händelsetyper `ActionType` (värden) som stöds av en tabell använder du den inbyggda schemareferensen som finns i säkerhetscentret.

>[!NOTE]
>Den här tabellen Azure Active Directory (Azure AD) inloggnings aktiviteter som spåras av Cloud App Security, särskilt interaktiva inloggningar och autentiserings aktiviteter med ActiveSync och andra äldre protokoll. Icke-interaktiva inloggningar som inte är tillgängliga i den här tabellen kan visas i Azure AD-granskningsloggen. [Läs mer om hur du Cloud App Security till Microsoft 365](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

Mer information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).

| Kolumnnamn | datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datumtid | Datum och tid då händelsen spelades in |
| `ActionType` | sträng | Typ av aktivitet som utlöste händelsen. Mer information [finns i schemareferensen i](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) portalen |
| `Application` | sträng | Program som utförde den registrerade åtgärden |
| `LogonType` | sträng | Typ av inloggningssession, särskilt:<br><br> - **Interaktiv** – Användaren interagerar fysiskt med datorn med det lokala tangentbordet och skärmen<br><br> - **Interaktiva fjärrinloggningar (RDP)** – användaren interagerar med datorn på distans med fjärrskrivbord, terminaltjänster, fjärrhjälp eller andra RDP-klienter<br><br> - **Nätverk** – Session som initieras när datorn nås med PsExec eller när delade resurser på datorn, till exempel skrivare och delade mappar, används<br><br> - **Batch** - Session initierad av schemalagda aktiviteter<br><br> - **Service** - Session initierad av tjänster när de startar |
| `Protocol` | sträng | Nätverksprotokoll som används |
| `FailureReason` | sträng | Information som förklarar varför den registrerade åtgärden misslyckades |
| `AccountName` | sträng | Användarkontots användarnamn |
| `AccountDomain` | sträng | Kontots domän |
| `AccountUpn` | sträng | Kontots huvudnamn (UPN) |
| `AccountSid` | sträng | Sid (Security Identifier) för kontot |
| `AccountObjectId` | sträng | Unik identifierare för kontot i Azure AD |
| `AccountDisplayName` | sträng | Namn på kontoanvändaren som visas i adressboken. Vanligtvis en kombination av ett visst eller förnamn, en mellaninitiering och ett efternamn eller efternamn. |
| `DeviceName` | sträng | Fullständigt kvalificerat domännamn (FQDN) för enheten |
| `DeviceType` | sträng | Typ av enhet |
| `OSPlatform` | sträng | Plattform för operativsystemet som körs på datorn. Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7. |
| `IPAddress` | sträng | IP-adress tilldelad slutpunkten och används vid relaterad nätverkskommunikation |
| `Port` | sträng | TCP-port som används under kommunikation |
| `DestinationDeviceName` | sträng | Namn på den enhet som kör serverprogrammet som bearbetade den registrerade åtgärden |
| `DestinationIPAddress` | sträng | IP-adress för den enhet som kör serverprogrammet som bearbetade den registrerade åtgärden |
| `DestinationPort` | sträng | Målport för relaterad nätverkskommunikation |
| `TargetDeviceName` | sträng | Fullständigt kvalificerat domännamn (FQDN) för den enhet som den registrerade åtgärden tillämpades på |
| `TargetAccountDisplayName` | sträng | Visa namnet på kontot som den registrerade åtgärden tillämpades på |
| `Location` | sträng | Ort, land eller annan geografisk plats i samband med händelsen |
| `Isp` | sträng | Internet-leverantör (Isp) som är associerad med slutpunktens IP-adress |
| `ReportId` | lång | Unik identifierare för händelsen |
| `AdditionalFields` | sträng | Ytterligare information om entiteten eller händelsen |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)