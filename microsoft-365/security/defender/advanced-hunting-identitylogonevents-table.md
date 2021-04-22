---
title: Tabellen IdentityLogonEvents i det avancerade sökschemat
description: Lär dig mer om autentiseringshändelser som registrerats av Active Directory i tabellen IdentityLogonEvents i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, sökning efter cyberhot, Microsoft 365 Defender, microsoft 365, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, IdentityLogonEvents, Azure AD, Active Directory, Microsoft Defender för identitet, identiteter
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
ms.openlocfilehash: 55ec52acd5419729f46779f1d4205cd55ce27f9d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935815"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Tabellen i det avancerade sökschemat innehåller information om autentiseringsaktiviteter som görs via din lokala Active Directory som fångas av Microsoft Defender för identitets- och autentiseringsaktiviteter relaterade till Microsofts onlinetjänster som fångats av `IdentityLogonEvents` Microsoft Cloud App Security. [](advanced-hunting-overview.md) Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

>[!TIP]
> Om du vill ha detaljerad information om de händelsetyper (värden) som stöds av en tabell kan du använda den `ActionType` inbyggda schemareferensen som finns i säkerhetscentret.

>[!NOTE]
>Den här tabellen beskriver inloggningsaktiviteter för Azure Active Directory (AD) som spåras av Cloud App Security, särskilt interaktiva inloggningar och autentiseringsaktiviteter med ActiveSync och andra äldre protokoll. Icke-interaktiva inloggningar som inte är tillgängliga i den här tabellen kan visas i Azure AD-granskningsloggen. [Läs mer om hur du ansluter Cloud App Security till Microsoft 365](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

Information om andra tabeller i det avancerade sökschemat finns [i den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid då händelsen spelades in |
| `ActionType` | sträng | Typ av aktivitet som utlöste händelsen. Mer information [finns i schemareferensen](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) i portalen |
| `Application` | sträng | Program som utförde den inspelade åtgärden |
| `LogonType` | sträng | Typ av inloggningssession, särskilt:<br><br> - **Interaktivt** – Användaren interagerar fysiskt med datorn med det lokala tangentbordet och den lokala skärmen<br><br> - **Fjärranslutna interaktiva inloggningar (RDP)** – Användaren interagerar med datorn via fjärrstyrning med Fjärrskrivbord, Terminal Services, Fjärrhjälp eller andra RDP-klienter<br><br> - **Nätverk** - Session initierad när datorn nås med PsExec eller när delade resurser på datorn, till exempel skrivare och delade mappar, används<br><br> - **Batch** – session initierad av schemalagda aktiviteter<br><br> - **Tjänst** – session initierad av tjänster när de startar |
| `Protocol` | sträng | Nätverksprotokoll som används |
| `FailureReason` | sträng | Information som förklarar varför den inspelade åtgärden misslyckades |
| `AccountName` | sträng | Användarnamn för kontot |
| `AccountDomain` | sträng | Domän för kontot |
| `AccountUpn` | sträng | Användarkontons huvudnamn (UPN) |
| `AccountSid` | sträng | Säkerhetsidentifierare (SID) för kontot |
| `AccountObjectId` | sträng | Unikt ID för kontot i Azure AD |
| `AccountDisplayName` | sträng | Namnet på kontoanvändaren som visas i adressboken. Detta är en kombination av ett visst namn eller förnamn, en mellaninititiering och efternamn eller efternamn. |
| `DeviceName` | sträng | Fullständigt kvalificerat domännamn (FQDN) för enheten |
| `DeviceType` | sträng | Typ av enhet |
| `OSPlatform` | sträng | Operativsystemets plattform som körs på datorn. Detta indikerar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7. |
| `IPAddress` | sträng | IP-adress tilldelad till slutpunkten och används under relaterad nätverkskommunikation |
| `Port` | sträng | TCP-port som används under kommunikation |
| `DestinationDeviceName` | sträng | Namn på den enhet som kör serverprogrammet som bearbetat den inspelade åtgärden |
| `DestinationIPAddress` | sträng | IP-adress för den enhet som kör serverprogrammet som bearbetat den inspelade åtgärden |
| `DestinationPort` | sträng | Målport för relaterad nätverkskommunikation |
| `TargetDeviceName` | sträng | Fullständigt kvalificerat domännamn (FQDN) för enheten som den inspelade åtgärden tillämpats på |
| `TargetAccountDisplayName` | sträng | Visningsnamn för det konto som den inspelade åtgärden tillämpats på |
| `Location` | sträng | Stad, land eller annan geografisk plats som är kopplad till händelsen |
| `Isp` | sträng | Internetleverantör (ISP) som är kopplad till slutpunktens IP-adress |
| `ReportId` | long | Unikt ID för händelsen |
| `AdditionalFields` | sträng | Ytterligare information om entiteten eller händelsen |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)