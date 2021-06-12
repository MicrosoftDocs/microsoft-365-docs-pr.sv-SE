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
ms.date: 06/11/2021
ms.reviewer: chventou
ms.openlocfilehash: 5fde3bfad69a5851dd94b76afb262f8be12d0360
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908263"
---
# <a name="manage-microsoft-defender-for-endpoint-with-configuration-manager"></a>Hantera Microsoft Defender för slutpunkt med Konfigurationshanteraren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Vi rekommenderar att du använder [Microsoft Endpoint Manager](/mem), som inkluderar [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) (Intune) och [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction) (Configuration Manager) för att hantera din organisations skyddsfunktioner för hot för enheter (kallas även slutpunkter). 
- [Läs mer om Endpoint Manager](/mem/endpoint-manager-overview)
- [Hantera Microsoft Defender för slutpunkt tillsammans på Windows 10-enheter med Konfigurationshanteraren och Intune](manage-atp-post-migration-intune.md)

## <a name="configure-microsoft-defender-for-endpoint-with-configuration-manager"></a>Konfigurera Microsoft Defender för slutpunkt med Konfigurationshanteraren

|Uppgift  |Resurser för att få mer information  |
|---------|---------|
|**Installera konfigurationshanterarens** konsol om du inte redan har den<br/><br/>*Om du inte redan har konfigurationskonsolen för hantering kan du använda de här resurserna för att hämta och installera dem.* |[Skaffa installationsmedia](/mem/configmgr/core/servers/deploy/install/get-install-media)<br/><br/>[Installera konfigurationshanterarens konsol](/mem/configmgr/core/servers/deploy/install/install-consoles)  |
|**Använda Konfigurationshanteraren för att registrera enheter** i Microsoft Defender för Endpoint <br/><br/> *Om du har enheter (eller slutpunkter) som inte redan har installerats i Microsoft Defender för Slutpunkt kan du göra det med Konfigurationshanteraren.*   |[Gå till Microsoft Defender för slutpunkt med Konfigurationshanteraren](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection#about-onboarding-to-atp-with-configuration-manager)      |
|**Hantera programskyddsprinciper och Windows för klientdatorer** (slutpunkter)<br/><br/>*Konfigurera funktioner för slutpunktsskydd, inklusive Microsoft Defender för Endpoint, sårbarhetsskydd, programkontroll, programskydd, brandväggsinställningar med mera.*  |[Konfigurationshanteraren: Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection)       |
|**Välj metoder för att uppdatera programskyddsuppdateringar** på din organisations enheter <br/><br/>*Med Endpoint Protection i Configuration Manager kan du välja bland flera olika metoder för att hålla definitioner för program mot skadlig programvara uppdaterade på organisationens enheter.* |[Konfigurera definitionsuppdateringar för Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-definition-updates) <br/><br/>[Använda Konfigurationshanteraren för att leverera definitionsuppdateringar](/mem/configmgr/protect/deploy-use/endpoint-definitions-configmgr) |
|**Aktivera nätverksskydd för** att förhindra att anställda använder program som skadligt innehåll på Internet <br/><br/>*Vi rekommenderar att [du först](/microsoft-365/security/defender-endpoint/evaluate-network-protection) använder granskningsläge för nätverksskydd i en testmiljö för att se vilka appar som ska blockeras innan de lanseras.* |[Aktivera nätverksskydd med Konfigurationshanteraren](/microsoft-365/security/defender-endpoint/enable-network-protection#microsoft-endpoint-configuration-manager)  |
|**Konfigurera kontrollerad mappåtkomst för** att skydda mot utpressningstrojaner <br/><br/>*Kontrollerad mappåtkomst kallas även skydd mot skadlig programvara.*   |[Slutpunktsskydd: Reglerad mappåtkomst](/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[Aktivera kontrollerad mappåtkomst i Konfigurationshantera microsoft-slutpunkt](/microsoft-365/security/defender-endpoint/enable-controlled-folders#microsoft-endpoint-configuration-manager) |

## <a name="configure-your-microsoft-defender-security-center"></a>Konfigurera Microsoft Defender Säkerhetscenter

Om du inte redan har gjort det konfigurerar du din Microsoft 365 Defender-portal för att visa aviseringar, konfigurera skyddsfunktioner för hot och visa detaljerad information om organisationens övergripande säkerhetsvarning. Se [Microsoft Defender Säkerhetscenter](microsoft-defender-security-center.md). Du kan också konfigurera om och vilka funktioner slutanvändare kan se i Microsoft 365 Defender-portalen.

- [Översikt över Microsoft Defender Säkerhetscenter](/microsoft-365/security/defender-endpoint/use)

- [Slutpunktsskydd: Microsoft Defender Säkerhetscenter](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Nästa steg

- [Få en översikt över Hantering av hot och säkerhetsrisker](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Besök instrumentpanelen Microsoft Defender Säkerhetscenter säkerhetsåtgärder](/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Hantera Microsoft Defender för slutpunkt med Intune](manage-atp-post-migration-intune.md)
