---
title: Tabellen IdentityLogonEvents i det avancerade sökschemat
description: Lär dig mer om autentiseringshändelser som registrerats av Active Directory i tabellen IdentityLogonEvents i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, sökning efter cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, IdentityLogonEvents, Azure AD, Active Directory, Azure ATP, identiteter
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 1df1295b3386b94e3737c53ac8226c719c8bfa08
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929928"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Tabellen i det avancerade sökschemat innehåller information om autentiseringsaktiviteter som görs via din lokala Active Directory som avbildats av Microsoft Defender för identitets- och autentiseringsaktiviteter relaterade till Microsofts onlinetjänster som avbildats av `IdentityLogonEvents` Microsoft Cloud App Security. [](advanced-hunting-overview.md) Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

>[!TIP]
> Om du vill ha detaljerad information om de händelsetyper (värden) som stöds av en tabell kan du använda den `ActionType` [inbyggda schemareferensen](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) som finns i säkerhetscentret.

>[!NOTE]
>Den här tabellen tar upp inloggningsaktiviteter för Azure Active Directory (AD) som spåras av Cloud App Security, särskilt interaktiva inloggningar och autentiseringsaktiviteter med ActiveSync och andra äldre protokoll. Icke-interaktiva inloggningar som inte är tillgängliga i den här tabellen kan visas i Azure AD-granskningsloggen. [Läs mer om hur du ansluter Cloud App Security till Microsoft 365](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid då händelsen spelades in |
| `ActionType` | sträng | Typ av aktivitet som utlöste händelsen. Mer information [finns i referensen till portalschemat](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `LogonType` | sträng | Typ av inloggningssession, särskilt:<br><br> - **Interaktiv** – användaren interagerar fysiskt med datorn med det lokala tangentbordet och den lokala skärmen<br><br> - **Fjärranslutna interaktiva inloggningar (RDP)** – Användaren interagerar med datorn på distans med Fjärrskrivbord, Terminal Services, Fjärrhjälp eller andra RDP-klienter<br><br> - **Nätverk** – Session initierad när datorn används med PsExec eller när delade resurser på datorn, till exempel skrivare och delade mappar, används<br><br> - **Batch** – session initierad av schemalagda aktiviteter<br><br> - **Tjänst** – Session initierad av tjänster när de startar |
| `Application` | sträng | Program som utförde den inspelade åtgärden |
| `Protocol` | sträng | Nätverksprotokoll som används |
| `FailureReason` | sträng | Information som förklarar varför den inspelade åtgärden misslyckades |
| `AccountName` | sträng | Användarnamn för kontot |
| `AccountDomain` | sträng | Domän för kontot |
| `AccountUpn` | sträng | Kontots huvudnamn (UPN) |
| `AccountSid` | sträng | Säkerhetsidentifierare (SID) för kontot |
| `AccountObjectId` | sträng | Unikt ID för kontot i Azure AD |
| `AccountDisplayName` | sträng | Namnet på kontoanvändaren som visas i adressboken. Vanligtvis en kombination av ett visst namn eller förnamn, en mellaninititiering och ett efternamn eller efternamn. |
| `DeviceName` | sträng | Fullständigt kvalificerat domännamn (FQDN) för enheten |
| `DeviceType` | sträng | Typ av enhet |
| `OSPlatform` | sträng | Operativsystemets plattform som körs på datorn. Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7. |
| `IPAddress` | sträng | IP-adress som tilldelats slutpunkten och som används under relaterad nätverkskommunikation |
| `DestinationDeviceName` | sträng | Namn på den enhet som kör serverprogrammet som hanterade den inspelade åtgärden |
| `DestinationIPAddress` | sträng | IP-adressen för den enhet som kör serverprogrammet som hanterade den inspelade åtgärden |
| `TargetDeviceName` | sträng | Fullständigt kvalificerat domännamn (FQDN) för enheten som den inspelade åtgärden tillämpats på |
| `TargetAccountDisplayName` | sträng | Visningsnamn för det konto som den inspelade åtgärden tillämpats på |
| `Location` | sträng | Stad, land eller annan geografisk plats som är kopplad till händelsen |
| `Isp` | sträng | Internet tjänstprovider (ISP) som är kopplad till slutpunktens IP-adress |
| `ReportId` | long | Unikt ID för händelsen |
| `AdditionalFields` | sträng | Ytterligare information om entiteten eller händelsen |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
