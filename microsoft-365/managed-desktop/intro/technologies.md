---
title: Teknologier i Microsoft Hanterat skrivbord
description: Den här artikeln innehåller teknikerna och apparna som används i Microsoft Managed Desktop.
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 22371d22562960efdc50235657a08e15dba893d3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920582"
---
# <a name="microsoft-managed-desktop-technologies"></a>Teknologier i Microsoft Hanterat skrivbord

Den här artikeln innehåller teknikerna och apparna som används i Microsoft Managed Desktop.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise-licensiering krävs för alla användare av Microsoft Managed Desktop. Mer information om licenskrav för tjänsten finns i Krav [för Microsoft Managed Desktop.](../get-ready/prerequisites.md)

Den här artikeln sammanfattar komponenterna som ingår i de obligatoriska Enterprise-licenserna, med en beskrivning av hur varje komponent används med Microsoft Managed Desktop-enheter. Specifika roller och ansvarsområden för varje område anges i dokumentationen för Microsoft Managed Desktop. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 eller E5
 |
 --- | ---
Microsoft 365-appar för företag (64-bitar) | Dessa Office-program levereras med enheten: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype för företag, OneNote.<br><br>64-bitarsversionen av Microsoft Project och Microsoft Visio ingår inte. Men eftersom installationen av de här programmen beror på installation av Microsoft 365-appar för företag har Microsoft Managed Desktop skapat standarddistributioner och säkerhetsgrupper för Microsoft Intune som du sedan kan använda för att distribuera programmen till licensierade användare. Mer information finns i Installera [Microsoft Project eller Microsoft Visio på Microsoft Managed Desktop-enheter.](../get-started/project-visio.md)
OneDrive |Azure Active Directory enkel inloggning är aktiverat för användare när de först loggar in på OneDrive.<br><br>Omdirigering av kända mappar för "Skrivbord", "Dokument" och "Bilder" ingår. aktiverat och konfigurerat av Microsoft Managed Desktop.
Store-appar |    Microsoft Sway och Power BI levereras inte med enheten. De här apparna kan laddas ned från Microsoft Store.
Win32-program |    Teams levereras inte med enheten, utan paketeras och tillhandahålls av Microsoft för Microsoft-enheter som hanteras av datorn. Azure Information Protection Client levereras inte med enheten, men du kan få den paketerad för distribution.
Webbprogram |  Yammer, Office i en webbläsare, Delve, Flow, StaffHub, PowerApps och Planner levereras inte med enheten. Användarna kan komma åt webbversionen av de här programmen via en webbläsare.


## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Enterprise E5 eller E3 med Microsoft Defender för Slutpunkt
Vi rekommenderar att IT-administratörerna konfigurerar följande inställningar. De här inställningarna ingår eller hanteras inte som en del av Microsoft Managed Desktop.

 |
 --- | ---
Windows Hello för företag | Du bör implementera Windows Hello för företag för att ersätta lösenord med stark tvåfaktorautentisering för Microsoft Managed Desktop-enheter. Mer information finns i [Windows Hello för företag.](/windows/security/identity-protection/hello-for-business/hello-identity-verification)
Application Virtualization | Du kan distribuera Application Virtualization (App-V) paket med Intune Win32-apphanteringsklienten. Mer information finns i [Application Virtualization](/windows/application-management/app-v/appv-technical-reference).
Dataförlustskydd i Microsoft 365 | Du bör implementera dataförlustskydd i Microsoft 365 för att övervaka de åtgärder som vidtas på objekt som du har fastställt vara känsliga och för att förhindra oavsiktlig delning av dessa objekt. Mer information finns i [Dataförlustskydd i Microsoft 365.](../../compliance/endpoint-dlp-learn-about.md)


Funktioner som ingår och hanteras som en del av Microsoft Managed Desktop:

 |
 --- | ---
BitLocker-diskkryptering | BitLocker-diskkryptering används för att kryptera alla systemenheter. Mer information finns i [BitLocker-diskkryptering.](/windows/security/information-protection/bitlocker/bitlocker-overview)
Windows Defender System Guard | Skyddar systemintegriteten vid start och verifierar att systemintegriteten verkligen har bibehållas. Mer information finns i [Windows Defender System Guard.]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)
Windows Defender Credential Guard | Windows Defender Credential Guard använder virtualiseringsbaserad säkerhet för att isolera hemligheter så att endast privilegierad systemprogramvara kan komma åt dem. Mer information finns i [Windows Defender System Guard.]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)
Microsoft Defender för slutpunkt – identifiering och svar av slutpunkt | Microsoft Hanterade säkerhetsåtgärder för stationära datorer svarar på aviseringar och vidtar åtgärder för att åtgärda hot med hjälp av slutpunktsidentifiering och svar. Mer information finns i [Microsoft Defender för slutpunkt – identifiering av slutpunkt och svar.](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)
Microsoft Defender för Endpoint – hotexperter | Microsoft Managed Desktop är integrerat med insikter och data från hotexperter via riktade attackmeddelanden. Du måste ge ytterligare tillstånd innan den här tjänsten aktiveras. Mer information finns i [Microsoft Defender för Endpoint – Hotexperter](/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts).
Microsoft Defender för slutpunkt – hantering av hot och sårbarhet | Krävs för framtida användning i tjänstabonnemanget Microsoft Managed Desktop. Mer information finns i [Microsoft Defender för Slutpunkt – Hot och sårbarhetshantering.](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
Microsoft Defender för slutpunkt – Minska attackytan | Minskning av attackytan riktar in sig på riskfyllda programvarubeteenden som ofta används av attackerare. Mer information finns i [Microsoft Defender för Slutpunkt – Minskning av attackytan.](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)
Microsoft Defender för slutpunkt – sårbarhetsskydd | Skyddar mot skadlig programvara som använder sårbarheter för att smitta enheter och sprida genom att automatiskt utnyttja minskningsteknik på både operativsystemprocesser och appar. Mer information finns i [Microsoft Defender för Slutpunkt – sårbarhetsskydd.](/windows/security/threat-protection/microsoft-defender-atp/exploit-protection)
Microsoft Defender för slutpunkt – nätverksskydd | Nätverksskydd utökar Omfattningen av Microsoft Defender SmartScreen för att blockera all utgående HTTP- och HTTPS-trafik som försöker ansluta till källor med låg rykte. Mer information finns i [Microsoft Defender för Slutpunkt – Nätverksskydd.](/windows/security/threat-protection/microsoft-defender-atp/network-protection)
Skydd mot manipulering i Microsoft Defender | Skydd mot manipulering i Windows används för att förhindra att säkerhetsinställningar som skydd mot virus ändras. Mer information finns i [Microsoft Defender Manipuleringsskydd](/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection).
Microsoft Defender Antivirus Behavior-baserat, heuristiskt och realtidsskydd för antivirus | Söker alltid efter fil- och processhot som kanske inte identifieras som skadlig programvara. Mer information finns i [Antivirusskyddet Microsoft Defender Antivirus- och heuristiskt skydd samt realtidsskydd.]( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)
Molnskydd för Microsoft Defender Antivirus | Ger dynamiskt, automatiserat skydd mot nya och nya hot. Mer information finns i [Microsoft Defender Antivirus Cloud-delivered Protection.](/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
Microsoft Defender "Blockera vid första synen" | Tillhandahåller identifiering och blockering av ny skadlig programvara när Windows upptäcker en misstänkt eller okänd fil. Mer information finns i [Microsoft Defender Block vid första anblicken.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)
Microsoft Defender AV potentiellt oönskade program | Potentiellt oönskade program används för att blockera appar som kan få datorn att köras långsamt, visa oväntade annonser eller i värsta fall installera annan programvara som kan vara oväntade eller oönskade. Mer information finns i [Microsoft Defender AV Potentiellt oönskade program.](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
Windows Defender-brandväggen med avancerad säkerhet | Värdbaserad, tvåvägsfiltrering av nätverkstrafik för en enhet, Windows Defender-brandväggen blockerar obehörig nätverkstrafik som går in i eller ut från den lokala enheten. Mer information finns i [Windows Defender-brandväggen med avancerad säkerhet.](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
Användarkontokontroll | User Account Control växlar till Säkert skrivbord när en uppgift eller åtgärd kräver åtkomst av administratörskontotyp. Microsoft Managed Desktop-användare tilldelas standardanvändaråtkomst vid registrering. Mer information finns i [User Account Control](/windows/security/identity-protection/user-account-control/how-user-account-control-works).


## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Du kan använda alla funktioner i Enterprise Mobility + Security E3 och Azure Active Directory Premium P2 för att hantera MDM-enheter.
Microsoft Cloud App Security |  Du kan använda den här valfria funktionen med Microsoft Managed Desktop.
Azure Information Protection P2  | Du kan använda den här valfria funktionen med Microsoft Managed Desktop.