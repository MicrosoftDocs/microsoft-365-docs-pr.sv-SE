---
title: Hantera Microsoft Defender för Slutpunkt med Hjälp av PowerShell, WMI och MPCmdRun.exe
description: Lär dig hur du hanterar Microsoft Defender för Slutpunkt med PowerShell, WMI och MPCmdRun.exe
keywords: efter migrering, hantera, åtgärder, underhåll, utnyttjandet, PowerShell, WMI, MPCmdRun.exe, Microsoft Defender för Slutpunkt, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.topic: article
ms.date: 09/22/2020
ms.reviewer: chventou
ms.openlocfilehash: d2238703e3b1205287d4ab6239af20095b51df13
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841924"
---
# <a name="manage-microsoft-defender-for-endpoint-with-powershell-wmi-and-mpcmdrunexe"></a>Hantera Microsoft Defender för slutpunkt med PowerShell, WMI och MPCmdRun.exe

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> Vi rekommenderar att [Microsoft Endpoint Manager](/mem) du använder för att hantera din organisations skyddsfunktioner för hot för enheter (kallas även slutpunkter). Endpoint Manager omfattar [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) och [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction). 
> - [Läs mer om Endpoint Manager](/mem/endpoint-manager-overview)
> - [Hantera Microsoft Defender för slutpunkt tillsammans på Windows 10-enheter med Konfigurationshanteraren och Intune](manage-atp-post-migration-intune.md)
> - [Hantera Microsoft Defender för slutpunkt med Intune](manage-atp-post-migration-intune.md) 

Du kan hantera vissa Microsoft Defender Antivirus-inställningar på enheter med [PowerShell](#configure-microsoft-defender-for-endpoint-with-powershell), [Windows Management Instrumentation](#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi) (WMI) och [Microsoft Malware Protection Command Line Utility](#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe) (MPCmdRun.exe). Du kan till exempel hantera vissa Microsoft Defender Antivirus inställningar. I vissa fall kan du även anpassa minskningsregler för attackytor och utnyttja skyddsinställningar. 

> [!IMPORTANT]
> Skyddsfunktioner som du konfigurerar med PowerShell, WMI eller MCPmdRun.exe kan skrivas över av konfigurationsinställningar som distribueras med Intune eller Configuration Manager.

## <a name="configure-microsoft-defender-for-endpoint-with-powershell"></a>Konfigurera Microsoft Defender för Slutpunkt med PowerShell

Du kan använda PowerShell för att hantera Microsoft Defender Antivirus, sårbarhetsskydd och minska attackytan.

|Uppgift  |Resurser för att få mer information  |
|---------|---------|
|**Hantera Microsoft Defender Antivirus** <br/><br/>*Visa status för skydd mot skadlig programvara, konfigurera inställningar för antivirussökningar & uppdateringar och göra andra ändringar i antivirusskyddet.*    |[Använda PowerShell-cmdlets för att konfigurera och hantera Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/use-powershell-cmdlets-microsoft-defender-antivirus)  <br/><br/>[Använda PowerShell-cmdlets för att aktivera moln levererat skydd](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-powershell-cmdlets-to-enable-cloud-delivered-protection)       |
|**Konfigurera sårbarhetsskydd** för att minska hot på organisationens enheter<br/><br/> *Vi rekommenderar att du först använder [sårbarhetsskydd i](/microsoft-365/security/defender-endpoint/evaluate-exploit-protection#powershell) granskningsläge. På så sätt kan du se hur sårbarhetsskydd påverkar appar som din organisation använder.*     | [Anpassa exploateringsskydd](/microsoft-365/security/defender-endpoint/customize-exploit-protection)<br/><br/>[PowerShell-cmdlets för sårbarhetsskydd](/microsoft-365/security/defender-endpoint/customize-exploit-protection#powershell-reference)        |
|**Konfigurera regler för att minska attackytan** med PowerShell <br/><br/>*Du kan använda PowerShell för att utesluta filer och mappar från minskningsregler för attackytor.* |[Anpassa minskningsregler för attackytan: Använd PowerShell för att utesluta filer & mappar](/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-powershell-to-exclude-files-and-folders)<br/><br/>Se även [António Vasconcelos](https://github.com/anvascon/MDATP_PoSh_Scripts/tree/master/ASR%20GUI)grafiska användargränssnittsverktyg för att ställa in regler för att minska attackytan med PowerShell. |
|**Aktivera nätverksskydd** med PowerShell <br/><br/>*Du kan använda PowerShell för att aktivera nätverksskydd.* |[Aktivera nätverksskydd med PowerShell](/microsoft-365/security/defender-endpoint/enable-network-protection#powershell) |
|**Konfigurera kontrollerad mappåtkomst för** att skydda mot utpressningstrojaner <br/><br/>*[Kontrollerad mappåtkomst](/microsoft-365/security/defender-endpoint/controlled-folders) kallas även skydd mot skadlig programvara.* |[Aktivera reglerad mappåtkomst med PowerShell](/microsoft-365/security/defender-endpoint/enable-controlled-folders#powershell) |
|**Konfigurera Microsoft Defender-brandväggen** att blockera obehörig nätverkstrafik som går till eller ut från din organisations enheter |[Microsoft Defender-brandväggen med avancerad säkerhetsadministration med Windows PowerShell](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-administration-with-windows-powershell) |
|**Konfigurera kryptering BitLocker** skydda information på organisationens enheter som kör Windows |[BitLocker Referensguide för PowerShell](/powershell/module/bitlocker/?view=win10-ps&preserve-view=true) |

## <a name="configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi"></a>Konfigurera Microsoft Defender för slutpunkt med Windows Management Instrumentation (WMI)

WMI är ett skriptgränssnitt där du kan hämta, ändra och uppdatera inställningar. Mer information finns i [Använda WMI.](/windows/win32/wmisdk/using-wmi) 

|Uppgift  |Resurser för att få mer information  |
|---------|---------|
|**Aktivera moln levererat skydd** på en enhet    |[Använd Windows management instruction (WMI) för att aktivera skydd mot moln levererat](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-windows-management-instruction-wmi-to-enable-cloud-delivered-protection)       |
|**Hämta, ändra och uppdatera inställningar** för Microsoft Defender Antivirus     | [Använda WMI för att konfigurera och hantera Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/use-wmi-microsoft-defender-antivirus)<br/><br/>[Granska listan över tillgängliga WMI-klasser och exempelskript](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) <br/><br/>Se även den arkiverade [informationen Windows Defender WMIv2-providerns referensinformation](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal?redirectedfrom=MSDN)   |


## <a name="configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe"></a>Konfigurera Microsoft Defender för Slutpunkt med Microsoft Malware Protection Command-Line Utility (MPCmdRun.exe)

På en enskild enhet kan du köra en genomsökning, starta diagnostikspårning, söka efter säkerhetsintelligensuppdateringar och mycket mer med hjälp mpcmdrun.exe-kommandoradsverktyget. Du hittar verktyget i `%ProgramFiles%\Windows Defender\MpCmdRun.exe` . Kör det från en kommandotolk.

|Uppgift  |Resurser för att få mer information  |
|---------|---------|
|**Hantera Microsoft Defender Antivirus**  |[Konfigurera och hantera Microsoft Defender Antivirus med mpcmdrun.exe](/windows/security/threat-protection/microsoft-defender-antivirus/command-line-arguments-microsoft-defender-antivirus)        |

## <a name="configure-your-microsoft-defender-security-center"></a>Konfigurera Microsoft Defender Säkerhetscenter

Om du inte redan har gjort det konfigurerar du din **Microsoft Defender Säkerhetscenter** () för att visa aviseringar, konfigurera skyddsfunktioner för hot och visa detaljerad information om organisationens övergripande [https://securitycenter.windows.com](https://securitycenter.windows.com) säkerhetsvarning. 

Du kan också konfigurera om och vilka funktioner slutanvändare kan se i Microsoft Defender Säkerhetscenter.

- [Översikt över Microsoft Defender Säkerhetscenter](/microsoft-365/security/defender-endpoint/use)

- [Slutpunktsskydd: Microsoft Defender Säkerhetscenter](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)


## <a name="next-steps"></a>Nästa steg

- [Få en översikt över Hantering av hot och säkerhetsrisker](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Besök instrumentpanelen Microsoft Defender Säkerhetscenter säkerhetsåtgärder](/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Hantera Microsoft Defender för slutpunkt med Intune](manage-atp-post-migration-intune.md)
