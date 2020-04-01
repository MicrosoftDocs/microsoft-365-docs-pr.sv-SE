---
title: " Siem-serverintegration (Security Information and Event Management) med Microsoft 365-tjänster och -program"
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: Få en översikt över SIEM-serverintegrering (Security Information and Event Management) med dina Microsoft 365-molntjänster och -program
ms.openlocfilehash: a4ef144d02ebf0481481861c3dfa60a43b4f3ace
ms.sourcegitcommit: a7b2cd892cb65a61ee246268e1af2f8b9e526f6b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2020
ms.locfileid: "43081226"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="91ec8-103">Siem-serverintegration (Security Information and Event Management) med Microsoft 365-tjänster och -program</span><span class="sxs-lookup"><span data-stu-id="91ec8-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

## <a name="summary"></a><span data-ttu-id="91ec8-104">Sammanfattning</span><span class="sxs-lookup"><span data-stu-id="91ec8-104">Summary</span></span>

<span data-ttu-id="91ec8-105">Använder eller planerar din organisation att skaffa en SIEM-server (Security Information and Event Management).</span><span class="sxs-lookup"><span data-stu-id="91ec8-105">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="91ec8-106">Du kanske undrar hur den integreras med Microsoft 365 eller Office 365.</span><span class="sxs-lookup"><span data-stu-id="91ec8-106">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="91ec8-107">Den här artikeln innehåller en lista över resurser som du kan använda för att integrera din SIEM-server med Microsoft 365-tjänster och -program.</span><span class="sxs-lookup"><span data-stu-id="91ec8-107">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="91ec8-108">Om du inte har en SIEM-server ännu och utforskar dina alternativ bör du överväga **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span><span class="sxs-lookup"><span data-stu-id="91ec8-108">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="91ec8-109">Behöver jag en SIEM-server?</span><span class="sxs-lookup"><span data-stu-id="91ec8-109">Do I need a SIEM server?</span></span>

<span data-ttu-id="91ec8-110">Om du behöver en SIEM-server beror på många faktorer, till exempel organisationens säkerhetskrav och var dina data finns.</span><span class="sxs-lookup"><span data-stu-id="91ec8-110">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="91ec8-111">Microsoft 365 innehåller en mängd olika säkerhetsfunktioner som uppfyller många organisationers säkerhetsbehov utan ytterligare servrar, till exempel en SIEM-server.</span><span class="sxs-lookup"><span data-stu-id="91ec8-111">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="91ec8-112">Vissa organisationer har särskilda omständigheter som kräver användning av en SIEM-server.</span><span class="sxs-lookup"><span data-stu-id="91ec8-112">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="91ec8-113">Här är några exempel:</span><span class="sxs-lookup"><span data-stu-id="91ec8-113">Here are some examples:</span></span>

- <span data-ttu-id="91ec8-114">*Fabrikam* har visst innehåll och program lokalt, och vissa i molnet (de har en hybridmolndistribution).</span><span class="sxs-lookup"><span data-stu-id="91ec8-114">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="91ec8-115">För att få säkerhetsrapporter över allt innehåll och alla program har Fabrikam implementerat en SIEM-server.</span><span class="sxs-lookup"><span data-stu-id="91ec8-115">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>

- <span data-ttu-id="91ec8-116">*Contoso* är en organisation för finansiella tjänster som har särskilt stränga säkerhetskrav.</span><span class="sxs-lookup"><span data-stu-id="91ec8-116">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="91ec8-117">De har lagt till en SIEM-server i sin miljö för att dra nytta av det extra säkerhetsskydd de behöver.</span><span class="sxs-lookup"><span data-stu-id="91ec8-117">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="91ec8-118">SIEM-serverintegrering med Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="91ec8-118">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="91ec8-119">En SIEM-server kan ta emot data från en mängd olika Microsoft 365-tjänster och -program.</span><span class="sxs-lookup"><span data-stu-id="91ec8-119">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="91ec8-120">I följande tabell visas flera Microsoft 365-tjänster och -program, tillsammans med SIEM-serverindata och resurser för att lära dig mer.</span><span class="sxs-lookup"><span data-stu-id="91ec8-120">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

||||
|---|---|---|
|<span data-ttu-id="91ec8-121">**Microsoft 365-tjänst eller program**</span><span class="sxs-lookup"><span data-stu-id="91ec8-121">**Microsoft 365 Service or Application**</span></span>|<span data-ttu-id="91ec8-122">**SIEM-serveringångar/metoder**</span><span class="sxs-lookup"><span data-stu-id="91ec8-122">**SIEM server inputs/methods**</span></span>|<span data-ttu-id="91ec8-123">**Resurser för att få mer information**</span><span class="sxs-lookup"><span data-stu-id="91ec8-123">**Resources to learn more**</span></span>|
|[<span data-ttu-id="91ec8-124">Office 365 Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="91ec8-124">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)|<span data-ttu-id="91ec8-125">Granskningsloggar</span><span class="sxs-lookup"><span data-stu-id="91ec8-125">Audit logs</span></span>|[<span data-ttu-id="91ec8-126">SIEM-integrering med avancerat hotskydd i Office 365</span><span class="sxs-lookup"><span data-stu-id="91ec8-126">SIEM integration with Office 365 Advanced Threat Protection</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="91ec8-127">Microsoft Defender Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="91ec8-127">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)|<span data-ttu-id="91ec8-128">HTTPS-slutpunkt som finns i Azure</span><span class="sxs-lookup"><span data-stu-id="91ec8-128">HTTPS endpoint hosted in Azure</span></span> <br/><span data-ttu-id="91ec8-129">REST API</span><span class="sxs-lookup"><span data-stu-id="91ec8-129">REST API</span></span>|[<span data-ttu-id="91ec8-130">Dra varningar till dina SIEM-verktyg</span><span class="sxs-lookup"><span data-stu-id="91ec8-130">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[<span data-ttu-id="91ec8-131">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="91ec8-131">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="91ec8-132">Loggintegrering</span><span class="sxs-lookup"><span data-stu-id="91ec8-132">Log integration</span></span>|[<span data-ttu-id="91ec8-133">SIEM-integrering med Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="91ec8-133">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="91ec8-134">Ta en titt på [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span><span class="sxs-lookup"><span data-stu-id="91ec8-134">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span></span> <span data-ttu-id="91ec8-135">Azure Sentinel levereras med kopplingar för Microsoft-lösningar.</span><span class="sxs-lookup"><span data-stu-id="91ec8-135">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="91ec8-136">Dessa kopplingar är tillgängliga "out of the box" och ger för integration i realtid.</span><span class="sxs-lookup"><span data-stu-id="91ec8-136">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="91ec8-137">Du kan använda Azure Sentinel med dina Microsoft Threat Protection-lösningar och Microsoft 365-tjänster, inklusive Office 365, Azure AD, Azure ATP, Microsoft Cloud App Security med mera.</span><span class="sxs-lookup"><span data-stu-id="91ec8-137">You can use Azure Sentinel with your Microsoft Threat Protection solutions and Microsoft 365 services, including Office 365, Azure AD, Azure ATP, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="91ec8-138">Granskningsloggning måste vara aktiverat</span><span class="sxs-lookup"><span data-stu-id="91ec8-138">Audit logging must be turned on</span></span>

<span data-ttu-id="91ec8-139">Kontrollera att granskningsloggning är aktiverat innan du konfigurerar INTEGRERING av SIEM-servrar.</span><span class="sxs-lookup"><span data-stu-id="91ec8-139">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="91ec8-140">För SharePoint Online, OneDrive för företag och Azure Active Directory [aktiveras granskningsloggning i Security & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="91ec8-140">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="91ec8-141">För Exchange Online finns i [Hantera granskning av postlådan](../../compliance/enable-mailbox-auditing.md).</span><span class="sxs-lookup"><span data-stu-id="91ec8-141">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="91ec8-142">Fler resurser</span><span class="sxs-lookup"><span data-stu-id="91ec8-142">More resources</span></span>

[<span data-ttu-id="91ec8-143">Integrera säkerhetslösningar i Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="91ec8-143">Integrate security solutions in Azure Security Center</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="91ec8-144">Integrera Microsoft Graph Security API-varningar med en SIEM</span><span class="sxs-lookup"><span data-stu-id="91ec8-144">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)
