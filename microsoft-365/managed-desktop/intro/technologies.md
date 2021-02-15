---
title: Teknologier i Microsoft Hanterat skrivbord
description: Den här artikeln innehåller de tekniker och appar som används i Microsoft Managed Desktop.
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 70e4eb442f9c0e52dbf234280205dd908c135b8d
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233114"
---
# <a name="microsoft-managed-desktop-technologies"></a>Teknologier i Microsoft Hanterat skrivbord

Den här artikeln innehåller de tekniker och appar som används i Microsoft Managed Desktop.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise-licensiering krävs för alla Microsoft Managed Desktop-användare. Mer information om licenskraven för tjänsten finns i [Förutsättningarna för Microsoft Managed Desktop.](../get-ready/prerequisites.md)

Den här artikeln sammanfattar komponenterna som ingår i de obligatoriska Enterprise-licenserna, med en beskrivning av hur tjänsten använder varje komponent med Microsoft Managed Desktop-enheter. Specifika roller och ansvarsområden för varje område beskrivs i microsofts dokumentation för hanterade skrivbord. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 eller E5
 |
 --- | ---
Microsoft 365-appar för företag (64-bitar) | Följande Office-program levereras med enheten: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype för företag, OneNote.<br><br>64-bitarsversionen av Microsoft Project och Microsoft Visio ingår inte. Men eftersom installationen av programmen beror på installation av Microsoft 365-appar för företag har Microsoft Managed Desktop skapat standarddistributioner och säkerhetsgrupper för Microsoft Intune som du sedan kan använda för att distribuera programmen till licensierade användare. Mer information finns i Installera [Microsoft Project eller Microsoft Visio på Microsoft Managed Desktop-enheter.](../get-started/project-visio.md)
OneDrive |Enkel inloggning i Azure Active Directory är aktiverat för användare när de först loggar in på OneDrive.<br><br>Mapparna Omdirigering av kända mappar för "Skrivbord", "Dokument" och "Bilder" ingår. aktiverat och konfigurerat av Microsoft Managed Desktop.
Store-appar |    Microsoft Sway och Power BI levereras inte med enheten. De här apparna kan laddas ned från Microsoft Store.
Win32-program |    Teams levereras inte med enheten, utan paketeras och tillhandahålls av Microsoft för Microsoft Managed Desktop-enheter. Azure Information Protection Client levereras inte med enheten, men du kan få den paketerad för distribution.
Webbprogram |  Yammer, Office i en webbläsare levereras inte Delve, Flow, StaffHub, PowerApps och Planner med enheten. Användare kan komma åt webbversionen av dessa program med en webbläsare.


## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Enterprise E5 eller E3 med Microsoft Defender för Slutpunkt
Vi rekommenderar att IT-administratörerna konfigurerar följande inställningar. De här inställningarna ingår inte eller hanteras inte som en del av Microsoft Hanterat skrivbord.

 |
 --- | ---
Windows Hello för företag | Du bör implementera Windows Hello för företag för att ersätta lösenord med stark tvåfaktorautentisering för Microsoft Managed Desktop-enheter. Mer information finns i [Windows Hello för företag.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)
Application Virtualization | Du kan distribuera Application Virtualization -paket (App-V) med Intune Win32-apphanteringsklienten. Mer information finns i [Application Virtualization.](https://docs.microsoft.com/windows/application-management/app-v/appv-technical-reference)
Skydd mot dataförlust i Microsoft 365 | Du bör implementera skydd mot dataförlust i Microsoft 365 för att övervaka de åtgärder som vidtas på objekt som du har fastställt vara känsliga och för att förhindra oavsiktlig delning av dessa objekt. Mer information finns i [Skydd mot dataförlust i Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about)


Funktioner som ingår och hanteras som en del av Microsoft Managed Desktop:

 |
 --- | ---
BitLocker-diskkryptering | BitLocker-diskkryptering används för att kryptera alla systemenheter. Mer information finns i [BitLocker-diskkryptering.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)
Windows Defender System Guard | Skyddar systemets integritet vid start och verifierar att systemintegriteten verkligen har bibehålls. Mer information finns i [Windows Defender System Guard.]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)
Windows Defender Credential Guard | Windows Defender Credential Guard använder virtualiseringsbaserad säkerhet för att isolera hemligheter så att endast privilegierad systemprogramvara kan komma åt dem. Mer information finns i [Windows Defender System Guard.]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)
Microsoft Defender för slutpunkt – identifiering av slutpunkt och svar | Microsofts säkerhetsåtgärder för stationära datorer svarar på varningar och vidtar åtgärder för att åtgärda hot med hjälp av slutpunktsidentifiering och -svar. Mer information finns i [Microsoft Defender för slutpunkt – identifiering av slutpunkt och svar.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)
Microsoft Defender för Endpoint – Hotexperter | Microsoft Managed Desktop är integrerat med insikter om hotexperter och data via riktade attackmeddelanden. Du måste ge ytterligare tillstånd innan den här tjänsten aktiveras. Mer information finns i [Microsoft Defender för Endpoint – Hotexperter.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts)
Microsoft Defender för Slutpunkt – Hantering av hot och sårbarhet | Krävs för framtida användning i Microsofts tjänstplan för hanterad stationär dator. Mer information finns i [Microsoft Defender för Slutpunkt – Hot och sårbarhetshantering.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
Microsoft Defender för Slutpunkt – Minska attackytan | Minskning av attackytans mål för riskfyllda programvarubeteenden som ofta missbrukas av attackerare. Mer information finns i [Microsoft Defender för Slutpunkt – Attack Surface Reduction.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)
Microsoft Defender för Slutpunkt – sårbarhetsskydd | Skyddar mot skadlig programvara som använder sårbarheter för att smitta enheter och sprida sig genom att automatiskt utnyttja minskningsteknik på både operativsystemprocesser och appar. Mer information finns i [Microsoft Defender för Endpoint – Sårbarhetsskydd.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection)
Microsoft Defender för Slutpunkt – Nätverksskydd | Nätverksskyddet utökar Omfattningen av Microsoft Defender SmartScreen för att blockera all utgående HTTP- och HTTPS-trafik som försöker ansluta till källor med låg rykte. Mer information finns i [Microsoft Defender för Slutpunkt – Nätverksskydd.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/network-protection)
Skydd mot manipulering i Microsoft Defender | Skydd mot manipulering i Windows används för att förhindra att säkerhetsinställningar som antivirusskydd ändras. Mer information finns i [Microsoft Defender Manipuleringsskydd.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection)
Microsoft Defender Antivirus Behavior-baserat, heuristiskt och realtidsskydd för antivirus | Alltid på genomsökning efter fil- och processhot som kanske inte identifieras som skadlig programvara. Mer information finns i [antivirusskyddet för Microsoft Defender Antivirus, heuristiskt och realtidsbaserat skydd.]( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)
Microsoft Defender Antivirus Cloud-delivered Protection | Ger dynamiskt och omedelbart automatiserat skydd mot nya och nya hot. Mer information finns i [Microsoft Defender Antivirus Cloud-delivered Protection.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
Microsoft Defender "Blockera vid första synen" | Identifierar och blockerar ny skadlig programvara när Windows identifierar en misstänkt eller okänd fil. Mer information finns i [Microsoft Defender Block vid första synen.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)
Microsoft Defender AV potentiellt oönskade program | Potentiellt oönskade program används för att blockera appar som kan få datorn att köras långsamt, visa oväntade annonser eller, i värsta fall, installera annan programvara som kan vara oväntad eller oönskad. Mer information finns i [Microsoft Defender AV potentiellt oönskade program.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
Windows Defender-brandväggen med avancerad säkerhet | Värdbaserad tvåvägsfiltrering av nätverkstrafik för en enhet blockerar Windows Defender-brandväggen obehörig nätverkstrafik som går in eller ut från den lokala enheten. Mer information finns i [Windows Defender-brandväggen med avancerad säkerhet.](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
User Account Control | User Account Control växlar till säkert skrivbord när en uppgift eller åtgärd kräver åtkomst av administratörskontotyp. Microsoft Managed Desktop-användare tilldelas standardanvändaråtkomst vid registrering. Mer information finns i [User Account Control.](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/how-user-account-control-works)


## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Du kan använda alla funktioner i Enterprise Mobility + Security E3 och Azure Active Directory Premium P2 för att hantera MDM-enheter.
Microsoft Cloud App Security |  Du kan använda den här valfria funktionen i Microsoft Managed Desktop.
Azure Information Protection P2  | Du kan använda den här valfria funktionen i Microsoft Managed Desktop.
