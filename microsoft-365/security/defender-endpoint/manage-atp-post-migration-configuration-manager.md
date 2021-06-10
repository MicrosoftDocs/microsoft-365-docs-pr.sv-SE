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
ms.openlocfilehash: 71ad8f52fd9347abdf0146969bb84a19d8883262
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843072"
---
# <a name="manage-microsoft-defender-for-endpoint-with-configuration-manager"></a><span data-ttu-id="6b0f6-104">Hantera Microsoft Defender för slutpunkt med Konfigurationshanteraren</span><span class="sxs-lookup"><span data-stu-id="6b0f6-104">Manage Microsoft Defender for Endpoint with Configuration Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6b0f6-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="6b0f6-105">**Applies to:**</span></span>
- [<span data-ttu-id="6b0f6-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="6b0f6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6b0f6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6b0f6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6b0f6-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="6b0f6-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6b0f6-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="6b0f6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="6b0f6-110">Vi rekommenderar att du använder [Microsoft Endpoint Manager](/mem), som inkluderar [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) (Intune) och [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction) (Configuration Manager) för att hantera din organisations skyddsfunktioner för hot för enheter (kallas även slutpunkter).</span><span class="sxs-lookup"><span data-stu-id="6b0f6-110">We recommend using We recommend using [Microsoft Endpoint Manager](/mem), which includes [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) (Intune) and [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction) (Configuration Manager) to manage your organization's threat protection features for devices (also referred to as endpoints).</span></span> 
- [<span data-ttu-id="6b0f6-111">Läs mer om Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="6b0f6-111">Learn more about Endpoint Manager</span></span>](/mem/endpoint-manager-overview)
- [<span data-ttu-id="6b0f6-112">Hantera Microsoft Defender för slutpunkt tillsammans på Windows 10-enheter med Konfigurationshanteraren och Intune</span><span class="sxs-lookup"><span data-stu-id="6b0f6-112">Co-manage Microsoft Defender for Endpoint on Windows 10 devices with Configuration Manager and Intune</span></span>](manage-atp-post-migration-intune.md)

## <a name="configure-microsoft-defender-for-endpoint-with-configuration-manager"></a><span data-ttu-id="6b0f6-113">Konfigurera Microsoft Defender för slutpunkt med Konfigurationshanteraren</span><span class="sxs-lookup"><span data-stu-id="6b0f6-113">Configure Microsoft Defender for Endpoint with Configuration Manager</span></span>

|<span data-ttu-id="6b0f6-114">Uppgift</span><span class="sxs-lookup"><span data-stu-id="6b0f6-114">Task</span></span>  |<span data-ttu-id="6b0f6-115">Resurser för att få mer information</span><span class="sxs-lookup"><span data-stu-id="6b0f6-115">Resources to learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="6b0f6-116">**Installera konfigurationshanterarens** konsol om du inte redan har den</span><span class="sxs-lookup"><span data-stu-id="6b0f6-116">**Install the Configuration Manager console** if you don't already have it</span></span><br/><br/><span data-ttu-id="6b0f6-117">*Om du inte redan har konfigurationskonsolen för hantering kan du använda de här resurserna för att hämta och installera dem.*</span><span class="sxs-lookup"><span data-stu-id="6b0f6-117">*If you don't already have the Configuration Manger console, use these resources to get the bits and install it.*</span></span> |[<span data-ttu-id="6b0f6-118">Skaffa installationsmedia</span><span class="sxs-lookup"><span data-stu-id="6b0f6-118">Get the installation media</span></span>](/mem/configmgr/core/servers/deploy/install/get-install-media)<br/><br/>[<span data-ttu-id="6b0f6-119">Installera konfigurationshanterarens konsol</span><span class="sxs-lookup"><span data-stu-id="6b0f6-119">Install the Configuration Manager console</span></span>](/mem/configmgr/core/servers/deploy/install/install-consoles)  |
|<span data-ttu-id="6b0f6-120">**Använda Konfigurationshanteraren för att registrera enheter** i Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="6b0f6-120">**Use Configuration Manager to onboard devices** to Microsoft Defender for Endpoint</span></span> <br/><br/> <span data-ttu-id="6b0f6-121">*Om du har enheter (eller slutpunkter) som inte redan har installerats i Microsoft Defender för Slutpunkt kan du göra det med Konfigurationshanteraren.*</span><span class="sxs-lookup"><span data-stu-id="6b0f6-121">*If you have devices (or endpoints) not already onboarded to Microsoft Defender for Endpoint, you can do that with Configuration Manager.*</span></span>   |[<span data-ttu-id="6b0f6-122">Gå till Microsoft Defender för slutpunkt med Konfigurationshanteraren</span><span class="sxs-lookup"><span data-stu-id="6b0f6-122">Onboard to Microsoft Defender for Endpoint with Configuration Manager</span></span>](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection#about-onboarding-to-atp-with-configuration-manager)      |
|<span data-ttu-id="6b0f6-123">**Hantera programskyddsprinciper och Windows för klientdatorer** (slutpunkter)</span><span class="sxs-lookup"><span data-stu-id="6b0f6-123">**Manage antimalware policies and Windows Firewall security** for client computers (endpoints)</span></span><br/><br/><span data-ttu-id="6b0f6-124">*Konfigurera funktioner för slutpunktsskydd, inklusive Microsoft Defender för Endpoint, sårbarhetsskydd, programkontroll, programskydd, brandväggsinställningar med mera.*</span><span class="sxs-lookup"><span data-stu-id="6b0f6-124">*Configure endpoint protection features, including Microsoft Defender for Endpoint, exploit protection, application control, antimalware, firewall settings, and more.*</span></span>  |[<span data-ttu-id="6b0f6-125">Konfigurationshanteraren: Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="6b0f6-125">Configuration Manager: Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection)       |
|<span data-ttu-id="6b0f6-126">**Välj metoder för att uppdatera programskyddsuppdateringar** på din organisations enheter</span><span class="sxs-lookup"><span data-stu-id="6b0f6-126">**Choose methods for updating antimalware updates** on your organization's devices</span></span> <br/><br/><span data-ttu-id="6b0f6-127">*Med Endpoint Protection i Configuration Manager kan du välja bland flera olika metoder för att hålla definitioner för program mot skadlig programvara uppdaterade på organisationens enheter.*</span><span class="sxs-lookup"><span data-stu-id="6b0f6-127">*With Endpoint Protection in Configuration Manager, you can choose from several methods to keep antimalware definitions up to date on your organization's devices.*</span></span> |[<span data-ttu-id="6b0f6-128">Konfigurera definitionsuppdateringar för Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="6b0f6-128">Configure definition updates for Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definition-updates) <br/><br/>[<span data-ttu-id="6b0f6-129">Använda Konfigurationshanteraren för att leverera definitionsuppdateringar</span><span class="sxs-lookup"><span data-stu-id="6b0f6-129">Use Configuration Manager to deliver definition updates</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-configmgr) |
|<span data-ttu-id="6b0f6-130">**Aktivera nätverksskydd för** att förhindra att anställda använder program som skadligt innehåll på Internet</span><span class="sxs-lookup"><span data-stu-id="6b0f6-130">**Enable Network Protection** to help prevent employees from using apps that malicious content on the Internet</span></span> <br/><br/><span data-ttu-id="6b0f6-131">*Vi rekommenderar att [du först](/microsoft-365/security/defender-endpoint/evaluate-network-protection) använder granskningsläge för nätverksskydd i en testmiljö för att se vilka appar som ska blockeras innan de lanseras.*</span><span class="sxs-lookup"><span data-stu-id="6b0f6-131">*We recommend using [audit mode](/microsoft-365/security/defender-endpoint/evaluate-network-protection) at first for network protection in a test environment to see which apps would be blocked before rolling out.*</span></span> |[<span data-ttu-id="6b0f6-132">Aktivera nätverksskydd med Konfigurationshanteraren</span><span class="sxs-lookup"><span data-stu-id="6b0f6-132">Turn on network protection with Configuration Manager</span></span>](/microsoft-365/security/defender-endpoint/enable-network-protection#microsoft-endpoint-configuration-manager)  |
|<span data-ttu-id="6b0f6-133">**Konfigurera kontrollerad mappåtkomst för** att skydda mot utpressningstrojaner</span><span class="sxs-lookup"><span data-stu-id="6b0f6-133">**Configure controlled folder access** to protect against ransomware</span></span> <br/><br/><span data-ttu-id="6b0f6-134">*Kontrollerad mappåtkomst kallas även skydd mot skadlig programvara.*</span><span class="sxs-lookup"><span data-stu-id="6b0f6-134">*Controlled folder access is also referred to as antiransomware protection.*</span></span>   |[<span data-ttu-id="6b0f6-135">Slutpunktsskydd: Reglerad mappåtkomst</span><span class="sxs-lookup"><span data-stu-id="6b0f6-135">Endpoint protection: Controlled folder access</span></span>](/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[<span data-ttu-id="6b0f6-136">Aktivera kontrollerad mappåtkomst i Konfigurationshantera microsoft-slutpunkt</span><span class="sxs-lookup"><span data-stu-id="6b0f6-136">Enable controlled folder access in Microsoft Endpoint Configuration Manage</span></span>](/microsoft-365/security/defender-endpoint/enable-controlled-folders#microsoft-endpoint-configuration-manager) |

## <a name="configure-your-microsoft-defender-security-center"></a><span data-ttu-id="6b0f6-137">Konfigurera Microsoft Defender Säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="6b0f6-137">Configure your Microsoft Defender Security Center</span></span>

<span data-ttu-id="6b0f6-138">Om du inte redan har gjort det konfigurerar du din **Microsoft Defender Säkerhetscenter** () för att visa aviseringar, konfigurera skyddsfunktioner för hot och visa detaljerad information om organisationens övergripande [https://securitycenter.windows.com](https://securitycenter.windows.com) säkerhetsvarning.</span><span class="sxs-lookup"><span data-stu-id="6b0f6-138">If you haven't already done so, **configure your Microsoft Defender Security Center** ([https://securitycenter.windows.com](https://securitycenter.windows.com)) to view alerts, configure threat protection features, and view detailed information about your organization's overall security posture.</span></span> 

<span data-ttu-id="6b0f6-139">Du kan också konfigurera om och vilka funktioner slutanvändare kan se i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="6b0f6-139">You can also configure whether and what features end users can see in the Microsoft Defender Security Center.</span></span>

- [<span data-ttu-id="6b0f6-140">Översikt över Microsoft Defender Säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="6b0f6-140">Overview of the Microsoft Defender Security Center</span></span>](/microsoft-365/security/defender-endpoint/use)

- [<span data-ttu-id="6b0f6-141">Slutpunktsskydd: Microsoft Defender Säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="6b0f6-141">Endpoint protection: Microsoft Defender Security Center</span></span>](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a><span data-ttu-id="6b0f6-142">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="6b0f6-142">Next steps</span></span>

- [<span data-ttu-id="6b0f6-143">Få en översikt över Hantering av hot och säkerhetsrisker</span><span class="sxs-lookup"><span data-stu-id="6b0f6-143">Get an overview of threat and vulnerability management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [<span data-ttu-id="6b0f6-144">Besök instrumentpanelen Microsoft Defender Säkerhetscenter säkerhetsåtgärder</span><span class="sxs-lookup"><span data-stu-id="6b0f6-144">Visit the Microsoft Defender Security Center security operations dashboard</span></span>](/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [<span data-ttu-id="6b0f6-145">Hantera Microsoft Defender för slutpunkt med Intune</span><span class="sxs-lookup"><span data-stu-id="6b0f6-145">Manage Microsoft Defender for Endpoint with Intune</span></span>](manage-atp-post-migration-intune.md)
