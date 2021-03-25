---
title: Hantera Microsoft Defender för slutpunkt efter migrering
description: Nu när du har gått över till Microsoft Defender för Endpoint är nästa steg att hantera dina skyddsfunktioner för hot
keywords: efter migrering, hantera, åtgärder, underhåll, användning, windows defender avancerat skydd mot hot, atp, edr
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
ms.topic: conceptual
ms.date: 01/26/2021
ms.reviewer: chventou
ms.openlocfilehash: fbc0abdb9def860df7e553963d7fa3c7f5b5da24
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074337"
---
# <a name="manage-microsoft-defender-for-endpoint-post-migration"></a>Hantera Microsoft Defender för Slutpunkt efter migrering

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

När du har flyttat från ditt tidigare slutpunktsskydd och antiviruslösning till Microsoft Defender för Endpoint är nästa steg att hantera funktioner och funktioner. Vi rekommenderar att [du använder Microsoft Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview), som inkluderar Microsoft [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) och [Microsoft Endpoint Configuration Manager,](https://docs.microsoft.com/mem/configmgr/core/understand/introduction)för att hantera din organisations enheter och säkerhetsinställningar. Du kan emellertid använda andra verktyg/metoder, till exempel [Grupprincipobjekt i Azure Active Directory Domain Services.](https://docs.microsoft.com/azure/active-directory-domain-services/manage-group-policy) 

I följande tabell finns olika verktyg/metoder som du kan använda, med länkar till mer information. 
<br/><br/>

|Verktyg/metod  |Beskrivning  |
|---------|---------|
|**[Instrumentpanelsinsikter för hantering av hot](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-dashboard-insights)** och sårbarhet i Microsoft Defender Säkerhetscenter ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) |Hoten & instrumentpanel för sårbarhetshantering tillhandahåller användbar information som teamet för säkerhetsåtgärder kan använda för att minska exponering och förbättra organisationens säkerhetsåtgärd. <br/><br/>Se [hot & säkerhetshantering](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) [och Översikt över Microsoft Defender Säkerhetscenter.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)  |
|**[Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)**  (rekommenderas)    |Microsoft Intune (Intune), en komponent i [Microsoft Endpoint Manager,](https://docs.microsoft.com/mem/endpoint-manager-overview)fokuserar på hantering av mobila enheter (MDM) och hantering av mobila enheter (MAM). Med Intune kan du styra hur organisationens enheter används, till exempel mobiltelefoner, surfplattor och bärbara datorer. Du kan också konfigurera specifika principer för att styra program. <br/><br/>Se [Hantera Microsoft Defender för Slutpunkt med Intune](manage-atp-post-migration-intune.md).         |
|**[Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction)**     |Microsoft Endpoint Manager (Configuration Manager), kallades tidigare System Center Configuration Manager, är en komponent i [Microsoft Endpoint Manager.](https://docs.microsoft.com/mem/endpoint-manager-overview) Konfigurationshanteraren är ett kraftfullt verktyg för att hantera användare, enheter och programvara.<br/><br/>Se [Hantera Microsoft Defender för Slutpunkt med Konfigurationshanteraren](manage-atp-post-migration-configuration-manager.md).        |
|**[Grupprincipobjekt i Azure Active Directory Domain Services](https://docs.microsoft.com/azure/active-directory-domain-services/manage-group-policy)** |[Azure Active Directory Domain Services](https://docs.microsoft.com/azure/active-directory-domain-services/overview) innehåller inbyggda grupprincipobjekt för användare och enheter. Du kan anpassa de inbyggda grupprincipobjekten efter behov för din miljö, samt skapa egna grupprincipobjekt och organisationsenheter (OUs). <br/><br/>Se [Hantera Microsoft Defender för slutpunkt med grupprincipobjekt](manage-atp-post-migration-group-policy-objects.md). |
|**[PowerShell, WMI och MPCmdRun.exe](manage-atp-post-migration-other-tools.md)** |*Vi rekommenderar att du använder Microsoft Endpoint Manager (som innehåller Intune och Konfigurationshanteraren) för att hantera skyddsfunktioner för hot på din organisations enheter. Du kan konfigurera vissa inställningar, till exempel inställningar för Microsoft Defender Antivirus på enskilda enheter (slutpunkter) med PowerShell, WMI eller MPCmdRun.exe antivirusverktyget.*<br/><br/>Du kan använda PowerShell för att hantera Microsoft Defender Antivirus, sårbarhetsskydd och minskningsregler för attackytor. Se [Konfigurera Microsoft Defender för slutpunkt med PowerShell](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-powershell).<br/><br/>Du kan använda Windows Management Instrumentation (WMI) för att hantera Microsoft Defender Antivirus och undantag. Se [Konfigurera Microsoft Defender för slutpunkt med WMI.](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi)<br/><br/>Du kan använda Microsoft Malware Protection Command-Line Utility (MPCmdRun.exe) för att hantera Microsoft Defender Antivirus och undantag, samt verifiera anslutningar mellan nätverket och molnet. Se [Konfigurera Microsoft Defender för slutpunkt med MPCmdRun.exe](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe). |

## <a name="see-also"></a>Se även

- [Adressera falska positiva/negativa tal i Microsoft Defender för Endpoint](defender-endpoint-false-positives-negatives.md)
