---
title: IdentityLogonEvents-tabell i det avancerade jakt-schemat
description: Lär dig mer om de autentiseringsnivåer som Active Directory har registrerat i IdentityLogonEvents-tabellen för det avancerade jakt schemat
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, IdentityLogonEvents, Azure AD, Active Directory, Azure ATP, identiteter
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
ms.openlocfilehash: 212189c89f354b186072bb109f119cf048680d08
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48431093"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Threat Protection

`IdentityLogonEvents`Tabellen i det [avancerade](advanced-hunting-overview.md) antivirus programmet innehåller information om de autentiseringsförfrågningar som görs via den lokala Active Directory som tagits fram av Azure ATP-och budgetaktiviteter som är relaterade till Microsoft Online Services som fångats av Microsoft Cloud App Security. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

>[!TIP]
> Detaljerad information om de händelse typer ( `ActionType` värden) som stöds av en tabell finns i den [inbyggda schema referensen](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) i säkerhets Center.

>[!NOTE]
>I den här tabellen beskrivs Azure Active Directory (AD)-inloggnings aktiviteter som spåras av Cloud App Security, särskilt interaktiva inloggnings-och autentiseringsdata med ActiveSync och andra äldre protokoll. Icke-interaktiva inloggningar som inte är tillgängliga i den här tabellen kan visas i Azure AD audit-loggen. [Läs mer om att ansluta Cloud App Security till Microsoft 365](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid när händelsen registrerades |
| `ActionType` | strängvärdet | Typ av aktivitet som utlöste händelsen. Mer information finns [i referens för in-Portal schema](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `LogonType` | strängvärdet | Typ av inloggningssession, särskilt:<br><br> - **Interaktivt** -användaren interagerar med datorn med det lokala tangent bordet och skärmen<br><br> - **Interaktivt (RDP) inloggningar** – användaren interagerar med datorn via fjärr skrivbord, Terminal Services, Fjärrhjälp eller andra RDP-klienter<br><br> - En **nätverks** session initieras när datorn nås med PsExec eller när delade resurser på datorn, till exempel skrivare och delade mappar, används<br><br> - **Batch** Gruppsession initierad av schemalagda aktiviteter<br><br> - **Tjänst** -session initierad av tjänster allteftersom de startas |
| `Application` | strängvärdet | Program som utförde den inspelade åtgärden |
| `Protocol` | strängvärdet | Använda nätverks protokoll |
| `FailureReason` | strängvärdet | Information som förklarar varför den inspelade åtgärden misslyckades |
| `AccountName` | strängvärdet | Kontots användar namn |
| `AccountDomain` | strängvärdet | Kontots domän |
| `AccountUpn` | strängvärdet | Kontots huvud namn (UPN) |
| `AccountSid` | strängvärdet | Kontots säkerhets identifierare (SID) |
| `AccountObjectId` | strängvärdet | Unik identifierare för kontot i Azure AD |
| `AccountDisplayName` | strängvärdet | Namnet på kontot som visas i adress boken. Vanligt vis en kombination av ett visst eller förnamn, en mellan initiering och ett efter namn eller från gång. |
| `DeviceName` | strängvärdet | Det fullständigt kvalificerade domän namnet (FQDN) för enheten |
| `DeviceType` | strängvärdet | Enhets typ |
| `OSPlatform` | strängvärdet | Plattformen för det operativ system som körs på datorn. Detta indikerar specifika operativ system, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7. |
| `IPAddress` | strängvärdet | IP-adress tilldelad till slut punkten och används under relaterad nätverkskommunikation |
| `DestinationDeviceName` | strängvärdet | Namn på den enhet som kör serverprogrammet som bearbetade den inspelade åtgärden |
| `DestinationIPAddress` | strängvärdet | IP-adress för enheten som kör serverprogrammet som bearbetade den inspelade åtgärden |
| `TargetDeviceName` | strängvärdet | Det fullständigt kvalificerade domän namnet (FQDN) för enheten som den inspelade åtgärden tillämpades på |
| `TargetAccountDisplayName` | strängvärdet | Visnings namn för det konto som den inspelade åtgärden tillämpades på |
| `Location` | strängvärdet | Ort, land eller annan geografisk plats som är kopplad till evenemanget |
| `Isp` | strängvärdet | Internet leverantör (ISP) associerad med slut punktens IP-adress |
| `ReportId` | tids | Unik identifierare för händelsen |
| `AdditionalFields` | strängvärdet | Ytterligare information om enheten eller händelsen |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
