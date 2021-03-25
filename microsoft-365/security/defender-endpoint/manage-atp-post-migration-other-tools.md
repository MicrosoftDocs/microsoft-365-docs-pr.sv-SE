---
title: Hantera Microsoft Defender för Slutpunkt med Hjälp av PowerShell, WMI och MPCmdRun.exe
description: Lär dig hur du hanterar Microsoft Defender för Slutpunkt med PowerShell, WMI och MPCmdRun.exe
keywords: efter migrering, hantera, åtgärder, underhåll, utnyttjandet, PowerShell, WMI, MPCmdRun.exe, windows defender avancerat skydd, atp, edr
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
ms.openlocfilehash: 5f0e94360cfaa0c66aedec400e81adc85f4f5450
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185879"
---
# <a name="manage-microsoft-defender-for-endpoint-with-powershell-wmi-and-mpcmdrunexe"></a>Hantera Microsoft Defender för slutpunkt med PowerShell, WMI och MPCmdRun.exe

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> Vi rekommenderar att [du använder Microsoft Endpoint Manager](https://docs.microsoft.com/mem) för att hantera din organisations skyddsfunktioner för hot för enheter (kallas även slutpunkter). Endpoint Manager innehåller [Microsoft Intune och](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) [Konfigurationshanteraren för Microsoft Endpoint.](https://docs.microsoft.com/mem/configmgr/core/understand/introduction) 
> - [Läs mer om Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview)
> - [Samtidig hantering av Microsoft Defender för slutpunkt på Windows 10-enheter med Konfigurationshanteraren och Intune](manage-atp-post-migration-intune.md)
> - [Hantera Microsoft Defender för slutpunkt med Intune](manage-atp-post-migration-intune.md) 

Du kan hantera vissa inställningar för Microsoft Defender Antivirus på enheter med [PowerShell,](#configure-microsoft-defender-for-endpoint-with-powershell)  [Windows Management Instrumentation](#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi) (WMI) och [Microsoft Malware Protection Command Line Utility](#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe) (MPCmdRun.exe). Du kan till exempel hantera vissa inställningar för Microsoft Defender Antivirus. I vissa fall kan du även anpassa minskningsregler för attackytor och utnyttja skyddsinställningar. 

> [!IMPORTANT]
> Skyddsfunktioner som du konfigurerar med PowerShell, WMI eller MCPmdRun.exe kan skrivas över av konfigurationsinställningar som distribueras med Intune eller Configuration Manager.

## <a name="configure-microsoft-defender-for-endpoint-with-powershell"></a>Konfigurera Microsoft Defender för Slutpunkt med PowerShell

Du kan använda PowerShell för att hantera Microsoft Defender Antivirus, sårbarhetsskydd och minskningsregler för attackytor.

|Uppgift  |Resurser för att få mer information  |
|---------|---------|
|**Hantera Microsoft Defender Antivirus** <br/><br/>*Visa status för skydd mot skadlig programvara, konfigurera inställningar för antivirussökningar & uppdateringar och göra andra ändringar i antivirusskyddet.*    |[Använda PowerShell-cmdlets för att konfigurera och hantera Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-powershell-cmdlets-microsoft-defender-antivirus)  <br/><br/>[Använda PowerShell-cmdlets för att aktivera moln levererat skydd](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-powershell-cmdlets-to-enable-cloud-delivered-protection)       |
|**Konfigurera sårbarhetsskydd** för att minska hot på organisationens enheter<br/><br/> *Vi rekommenderar att du först använder [sårbarhetsskydd i](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-exploit-protection#powershell) granskningsläge. På så sätt kan du se hur sårbarhetsskydd påverkar appar som din organisation använder.*     | [Anpassa sårbarhetsskydd](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-exploit-protection)<br/><br/>[PowerShell-cmdlets för sårbarhetsskydd](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-exploit-protection#powershell-reference)        |
|**Konfigurera regler för att minska attackytan** med PowerShell <br/><br/>*Du kan använda PowerShell för att utesluta filer och mappar från minskningsregler för attackytor.* |[Anpassa minskningsregler för attackytan: Använd PowerShell för att utesluta filer & mappar](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-powershell-to-exclude-files-and-folders)<br/><br/>Se även [António Vasconcelos](https://github.com/anvascon/MDATP_PoSh_Scripts/tree/master/ASR%20GUI)grafiska användargränssnittsverktyg för att ställa in regler för att minska attackytan med PowerShell. |
|**Aktivera nätverksskydd** med PowerShell <br/><br/>*Du kan använda PowerShell för att aktivera nätverksskydd.* |[Aktivera nätverksskydd med PowerShell](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-network-protection#powershell) |
|**Konfigurera kontrollerad mappåtkomst för** att skydda mot utpressningstrojaner <br/><br/>*[Kontrollerad mappåtkomst](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/controlled-folders) kallas även skydd mot skadlig programvara.* |[Aktivera reglerad mappåtkomst med PowerShell](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-controlled-folders#powershell) |
|**Konfigurera Microsoft Defender-brandväggen** för att blockera obehörig nätverkstrafik som går till eller ut från din organisations enheter |[Microsoft Defender-brandväggen med avancerad säkerhetsadministration med Windows PowerShell](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-administration-with-windows-powershell) |
|**Konfigurera kryptering och BitLocker** för att skydda information på din organisations enheter med Windows |[Referensguide för BitLocker PowerShell](https://docs.microsoft.com/powershell/module/bitlocker/?view=win10-ps&preserve-view=true) |

## <a name="configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi"></a>Konfigurera Microsoft Defender för slutpunkt med WMI (Windows Management Instrumentation)

WMI är ett skriptgränssnitt där du kan hämta, ändra och uppdatera inställningar. Mer information finns i [Använda WMI.](https://docs.microsoft.com/windows/win32/wmisdk/using-wmi) 

|Uppgift  |Resurser för att få mer information  |
|---------|---------|
|**Aktivera moln levererat skydd** på en enhet    |[Använd Windows Management Instruction (WMI) för att aktivera skydd som levereras med molnet](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-windows-management-instruction-wmi-to-enable-cloud-delivered-protection)       |
|**Hämta, ändra och uppdatera inställningar för** Microsoft Defender Antivirus     | [Använda WMI för att konfigurera och hantera Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-wmi-microsoft-defender-antivirus)<br/><br/>[Granska listan över tillgängliga WMI-klasser och exempelskript](https://docs.microsoft.com/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) <br/><br/>Se även den arkiverade [referensinformationen för Windows Defender WMIv2-providern](https://docs.microsoft.com/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal?redirectedfrom=MSDN)   |


## <a name="configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe"></a>Konfigurera Microsoft Defender för Slutpunkt med Microsoft Malware Protection Command-Line Utility (MPCmdRun.exe)

På en enskild enhet kan du köra en genomsökning, starta diagnostikspårning, söka efter säkerhetsintelligensuppdateringar och mycket mer med hjälp mpcmdrun.exe-kommandoradsverktyget. Du hittar verktyget i `%ProgramFiles%\Windows Defender\MpCmdRun.exe` . Kör det från en kommandotolk.

|Uppgift  |Resurser för att få mer information  |
|---------|---------|
|**Hantera Microsoft Defender Antivirus**  |[Konfigurera och hantera Microsoft Defender Antivirus med mpcmdrun.exe](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/command-line-arguments-microsoft-defender-antivirus)        |

## <a name="configure-your-microsoft-defender-security-center"></a>Konfigurera Microsoft Defender Säkerhetscenter

Om du inte redan har gjort det konfigurerar du **Microsoft Defender Säkerhetscenter** () för att visa aviseringar, konfigurera skyddsfunktioner för hot och visa detaljerad information om organisationens övergripande [https://securitycenter.windows.com](https://securitycenter.windows.com) säkerhetsvarning. 

Du kan också konfigurera om och vilka funktioner slutanvändare kan se i Microsoft Defender Säkerhetscenter.

- [Översikt över Microsoft Defender Säkerhetscenter](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

- [Slutpunktsskydd: Microsoft Defender Säkerhetscenter](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)


## <a name="next-steps"></a>Nästa steg

- [Få en översikt över hot och sårbarhetshantering](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Besök instrumentpanelen för säkerhetsåtgärder i Microsoft Defender Säkerhetscenter](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Hantera Microsoft Defender för slutpunkt med Intune](manage-atp-post-migration-intune.md)
