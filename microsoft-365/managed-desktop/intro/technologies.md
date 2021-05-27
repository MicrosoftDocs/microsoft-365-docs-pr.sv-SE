---
title: Teknologier i Microsoft Hanterat skrivbord
description: Den här artikeln innehåller teknikerna och apparna som används i Microsoft Hanterat skrivbord.
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: e653ff84602a5e5546ef9a4c0aca2559b77e43c1
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683517"
---
# <a name="microsoft-managed-desktop-technologies"></a>Teknologier i Microsoft Hanterat skrivbord

Den här artikeln innehåller teknikerna och apparna som används i Microsoft Hanterat skrivbord.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise krävs för alla Microsoft Hanterat skrivbord användare. Mer information om licenskrav för tjänsten finns i [Förutsättningar för Microsoft Hanterat skrivbord](../get-ready/prerequisites.md).

Den här artikeln sammanfattar komponenterna som ingår i de obligatoriska Enterprise-licenserna, med en beskrivning av hur respektive komponent används med Microsoft Hanterat skrivbord enheter. Specifika roller och ansvarsområden för varje område anges i Microsoft Hanterat skrivbord dokumentation. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 eller E5
 |
 --- | ---
Microsoft 365-appar för företag (64-bitar) | Följande Office-program levereras med enheten: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype för företag, OneNote.<br><br>64-bitarsversionen av alla Microsoft Project och Microsoft Visio inte med. Men eftersom installationen av de här programmen beror på Microsoft 365-appar för företag-installationen har Microsoft Hanterat skrivbord skapat standarddistributioner och säkerhetsgrupper för Microsoft Intune som du sedan kan använda för att distribuera programmen till licensierade användare. Mer information finns i Installera [Microsoft Project eller Microsoft Visio på Microsoft Hanterat skrivbord enheter.](../get-started/project-visio.md)
OneDrive |Azure Active Directory Enkel inloggning är aktiverad för användare när de först loggar in på OneDrive.<br><br>Omdirigering av kända mappar för "Skrivbord", "Dokument" och "Bilder" ingår. aktiverat och konfigurerat av Microsoft Hanterat skrivbord.
Store-appar |    Microsoft Sway Power BI levereras inte med enheten. De här apparna kan laddas ned från Microsoft Store.
Win32-program |    Teams levereras inte med enheten utan paketeras och tillhandahålls av Microsoft för Microsoft Hanterat skrivbord enheter. Azure Information Protection Client levereras inte med enheten, men du kan få den paketerad för distribution.
Webbprogram |  Yammer Office i en webbläsare levereras Delve, Flow, StaffHub, PowerApps och Planner inte med enheten. Användarna kan komma åt webbversionen av de här programmen via en webbläsare.


## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Enterprise E5 eller E3 med Microsoft Defender för Endpoint
Vi rekommenderar att IT-administratörerna konfigurerar följande inställningar. De här inställningarna ingår inte och hanteras inte som en del av Microsoft Hanterat skrivbord.

 |
 --- | ---
Windows Hello för företag | Du bör implementera Windows Hello för företag för att ersätta lösenord med stark tvåfaktorautentisering för Microsoft Hanterat skrivbord enheter. Mer information finns i [Windows Hello för företag.](/windows/security/identity-protection/hello-for-business/hello-identity-verification)
Application Virtualization | Du kan distribuera Application Virtualization (App-V) paket med Intune Win32-apphanteringsklienten. Mer information finns i [Application Virtualization](/windows/application-management/app-v/appv-technical-reference).
Microsoft 365 skydd mot dataförlust | Du bör implementera Microsoft 365 skydd mot dataförlust för att övervaka de åtgärder som vidtas på objekt som du har fastställt vara känsliga och för att förhindra oavsiktlig delning av dessa objekt. Mer information finns i Microsoft 365 [skydd mot dataförlust.](../../compliance/endpoint-dlp-learn-about.md)


Funktioner som ingår och hanteras som en del av Microsoft Hanterat skrivbord:

 |
 --- | ---
BitLocker Diskkryptering | BitLocker Enhetskryptering används för att kryptera alla systemenheter. Mer information finns i BitLocker [kryptering av hårddisk.](/windows/security/information-protection/bitlocker/bitlocker-overview)
Windows Defender System Guard | Skyddar systemintegriteten vid start och verifierar att systemintegriteten verkligen har bibehållas. Mer information finns i [Windows Defender System Guard.]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)
Windows Defender Credential Guard | Windows Defender Credential Guard utnyttjar virtualiseringsbaserad säkerhet för att isolera hemligheter så att endast privilegierad systemprogramvara kan komma åt dem. Mer information finns i [Windows Defender System Guard.]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)
Microsoft Defender för slutpunkt – identifiering och svar av slutpunkt | Microsoft Hanterat skrivbord Säkerhetsåtgärder svarar på varningar och åtgärdar hot genom att åtgärda hot med hjälp av slutpunktsidentifiering och svar. Mer information finns i [Microsoft Defender för slutpunkt – identifiering av slutpunkt och svar.](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)
Microsoft Defender för Endpoint – hotexperter | Microsoft Hanterat skrivbord kan integreras med insikter och data från hotexperter via riktade attackmeddelanden. Du måste ge ytterligare tillstånd innan den här tjänsten aktiveras. Mer information finns i [Microsoft Defender för Endpoint – Hotexperter](/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts).
Microsoft Defender för slutpunkt – hantering av hot och sårbarhet | Krävs för framtida användning i Microsoft Hanterat skrivbord-tjänstabonnemanget. Mer information finns i [Microsoft Defender för Slutpunkt – Hot och sårbarhetshantering.](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
Microsoft Defender för slutpunkt – Minska attackytan | Minskning av attackytan riktar in sig på riskfyllda programvarubeteenden som ofta används av attackerare. Mer information finns i [Microsoft Defender för Slutpunkt – Minskning av attackytan.](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)
Microsoft Defender för slutpunkt – sårbarhetsskydd | Skyddar mot skadlig programvara som använder sårbarheter för att smitta enheter och sprida genom att automatiskt utnyttja minskningsteknik på både operativsystemprocesser och appar. Mer information finns i [Microsoft Defender för Slutpunkt – sårbarhetsskydd.](/windows/security/threat-protection/microsoft-defender-atp/exploit-protection)
Microsoft Defender för slutpunkt – nätverksskydd | Nätverksskydd utökar omfattningen av Microsoft Defender SmartScreen att blockera all utgående HTTP- och HTTPS-trafik som försöker ansluta till berykelsekällor. Mer information finns i [Microsoft Defender för Slutpunkt – Nätverksskydd.](/windows/security/threat-protection/microsoft-defender-atp/network-protection)
Skydd mot manipulering i Microsoft Defender | Windows Skydd mot manipulering används för att förhindra att säkerhetsinställningar som antivirusskydd ändras. Mer information finns i [Microsoft Defender Manipuleringsskydd](/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection).
Microsoft Defender Antivirus Funktionsbaserat, heuristiskt och realtidsskydd för antivirus | Söker alltid efter fil- och processhot som kanske inte identifieras som skadlig programvara. Mer information finns i [Microsoft Defender Antivirus ett antivirusprogram med funktionsbaserad, heuristisk och realtidsskyddet.]( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)
Microsoft Defender Antivirus Moln levererat skydd | Ger dynamiskt, automatiserat skydd mot nya och nya hot. Mer information finns i [Microsoft Defender Antivirus Cloud-delivered Protection.](/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
Microsoft Defender "Blockera vid första synen" | Tillhandahåller identifiering och blockering av ny skadlig programvara Windows upptäcker en misstänkt eller okänd fil. Mer information finns i [Microsoft Defender Block vid första anblicken.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)
Microsoft Defender AV potentiellt oönskade program | Potentiellt oönskade program används för att blockera appar som kan få datorn att köras långsamt, visa oväntade annonser eller i värsta fall installera annan programvara som kan vara oväntade eller oönskade. Mer information finns i [Microsoft Defender AV Potentiellt oönskade program.](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
Windows Defender-brandväggen med avancerad säkerhet | Värdbaserad, tvåvägsfiltrering av nätverkstrafik för en enhet Windows Defender-brandväggen obehörig nätverkstrafik som går in i eller ut från den lokala enheten. Mer information finns i Windows Defender-brandväggen [med Avancerad säkerhet.](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
Användarkontokontroll | User Account Control växlar till Säkert skrivbord när en uppgift eller åtgärd kräver åtkomst av administratörskontotyp. Microsoft Hanterat skrivbord tilldelas standardanvändaråtkomst vid registrering. Mer information finns i [User Account Control](/windows/security/identity-protection/user-account-control/how-user-account-control-works).


## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Du kan använda alla funktioner i Enterprise Mobility + Security E3 för att hantera MDM-enheter. Du kan använda Azure Active Directory Premium P2 som en valfri funktion med Microsoft Hanterat skrivbord.
Microsoft Cloud App Security |  Du kan använda den här valfria funktionen Microsoft Hanterat skrivbord.
Azure Information Protection P2  | Du kan använda den här valfria funktionen Microsoft Hanterat skrivbord.
