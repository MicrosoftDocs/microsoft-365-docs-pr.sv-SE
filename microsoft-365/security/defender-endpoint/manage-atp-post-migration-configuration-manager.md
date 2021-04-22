---
title: Hantera Microsoft Defender för slutpunkt med Konfigurationshanteraren
description: Lär dig hur du hanterar Microsoft Defender för slutpunkt med Konfigurationshanteraren
keywords: efter migrering, hantera, åtgärder, underhåll, användning, Konfigurationshanteraren, Microsoft Defender för slutpunkt, edr
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
ms.openlocfilehash: 0cd52388feb987b4231d911cd3c3fd10babba017
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933211"
---
# <a name="manage-microsoft-defender-for-endpoint-with-configuration-manager"></a>Hantera Microsoft Defender för slutpunkt med Konfigurationshanteraren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Vi rekommenderar att du använder [Microsoft Endpoint Manager](https://docs.microsoft.com/mem), som omfattar Microsoft [Intune (Intune)](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) och Microsoft Endpoint Configuration Manager (Configuration [Manager)](https://docs.microsoft.com/mem/configmgr/core/understand/introduction) för att hantera din organisations skyddsfunktioner för hot för enheter (kallas även slutpunkter). 
- [Läs mer om Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview)
- [Samtidig hantering av Microsoft Defender för slutpunkt på Windows 10-enheter med Konfigurationshanteraren och Intune](manage-atp-post-migration-intune.md)

## <a name="configure-microsoft-defender-for-endpoint-with-configuration-manager"></a>Konfigurera Microsoft Defender för slutpunkt med Konfigurationshanteraren

|Uppgift  |Resurser för att få mer information  |
|---------|---------|
|**Installera konfigurationshanterarens** konsol om du inte redan har den<br/><br/>*Om du inte redan har konfigurationskonsolen för hantering kan du använda de här resurserna för att hämta och installera dem.* |[Skaffa installationsmedia](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/install/get-install-media)<br/><br/>[Installera konfigurationshanterarens konsol](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/install/install-consoles)  |
|**Använda Konfigurationshanteraren för att registrera enheter** i Microsoft Defender för Endpoint <br/><br/> *Om du har enheter (eller slutpunkter) som inte redan har installerats i Microsoft Defender för Slutpunkt kan du göra det med Konfigurationshanteraren.*   |[Gå till Microsoft Defender för slutpunkt med Konfigurationshanteraren](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection#about-onboarding-to-atp-with-configuration-manager)      |
|**Hantera programskyddsprinciper och Windows-brandväggens säkerhet** för klientdatorer (slutpunkter)<br/><br/>*Konfigurera funktioner för slutpunktsskydd, inklusive Microsoft Defender för Endpoint, sårbarhetsskydd, programkontroll, programskydd, brandväggsinställningar med mera.*  |[Konfigurationshanteraren: Slutpunktsskydd](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection)       |
|**Välj metoder för att uppdatera programskyddsuppdateringar** på din organisations enheter <br/><br/>*Med Endpoint Protection i Configuration Manager kan du välja bland flera olika metoder för att hålla definitioner för program mot skadlig programvara uppdaterade på organisationens enheter.* |[Konfigurera definitionsuppdateringar för Endpoint Protection](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-definition-updates) <br/><br/>[Använda Konfigurationshanteraren för att leverera definitionsuppdateringar](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-definitions-configmgr) |
|**Aktivera nätverksskydd för** att förhindra att anställda använder program som skadligt innehåll på Internet <br/><br/>*Vi rekommenderar att [du först](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-network-protection) använder granskningsläge för nätverksskydd i en testmiljö för att se vilka appar som ska blockeras innan de lanseras.* |[Aktivera nätverksskydd med Konfigurationshanteraren](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-network-protection#microsoft-endpoint-configuration-manager)  |
|**Konfigurera kontrollerad mappåtkomst för** att skydda mot utpressningstrojaner <br/><br/>*Kontrollerad mappåtkomst kallas även skydd mot skadlig programvara.*   |[Slutpunktsskydd: Reglerad mappåtkomst](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[Aktivera kontrollerad mappåtkomst i Konfigurationshantera microsoft-slutpunkt](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-controlled-folders#microsoft-endpoint-configuration-manager) |

## <a name="configure-your-microsoft-defender-security-center"></a>Konfigurera Microsoft Defender Säkerhetscenter

Om du inte redan har gjort det konfigurerar du **Microsoft Defender Säkerhetscenter** () för att visa aviseringar, konfigurera skyddsfunktioner för hot och visa detaljerad information om organisationens övergripande [https://securitycenter.windows.com](https://securitycenter.windows.com) säkerhetsvarning. 

Du kan också konfigurera om och vilka funktioner slutanvändare kan se i Microsoft Defender Säkerhetscenter.

- [Översikt över Microsoft Defender Säkerhetscenter](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

- [Slutpunktsskydd: Microsoft Defender Säkerhetscenter](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Nästa steg

- [Få en översikt över hot och sårbarhetshantering](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Besök instrumentpanelen för säkerhetsåtgärder i Microsoft Defender Säkerhetscenter](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Hantera Microsoft Defender för slutpunkt med Intune](manage-atp-post-migration-intune.md)
