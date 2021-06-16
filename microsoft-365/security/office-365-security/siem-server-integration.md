---
title: SIEM-serverintegrering med Microsoft 365 och program
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: Få en översikt över säkerhetsinformation och händelsehantering (SIEM) serverintegrering med dina Microsoft 365 och program
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8b9c17ba2dcefa65b60a53ab8bff405de4850fc0
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929797"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="905b3-103">Säkerhetsinformation och händelsehantering (SIEM)-serverintegrering med Microsoft 365 och program</span><span class="sxs-lookup"><span data-stu-id="905b3-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

<span data-ttu-id="905b3-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="905b3-104">**Applies to**</span></span>
- [<span data-ttu-id="905b3-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="905b3-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="905b3-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="905b3-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="905b3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="905b3-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a><span data-ttu-id="905b3-108">Sammanfattning</span><span class="sxs-lookup"><span data-stu-id="905b3-108">Summary</span></span>

<span data-ttu-id="905b3-109">Använder eller planerar din organisation att skaffa en säkerhetsinformations- och händelsehanteringsserver (SIEM) ?</span><span class="sxs-lookup"><span data-stu-id="905b3-109">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="905b3-110">Du kanske undrar hur det går att integrera med Microsoft 365 eller Office 365.</span><span class="sxs-lookup"><span data-stu-id="905b3-110">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="905b3-111">Den här artikeln innehåller en lista över resurser som du kan använda för att integrera DIN SIEM-server Microsoft 365 tjänster och program.</span><span class="sxs-lookup"><span data-stu-id="905b3-111">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="905b3-112">Om du inte har en SIEM-server ännu och utforskar alternativen kan du överväga **[att Microsoft Azure Sentinel.](/azure/sentinel/overview)**</span><span class="sxs-lookup"><span data-stu-id="905b3-112">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="905b3-113">Behöver jag en SIEM-server?</span><span class="sxs-lookup"><span data-stu-id="905b3-113">Do I need a SIEM server?</span></span>

<span data-ttu-id="905b3-114">Om du behöver en SIEM-server beror på många faktorer, till exempel organisationens säkerhetskrav och var dina data finns.</span><span class="sxs-lookup"><span data-stu-id="905b3-114">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="905b3-115">Microsoft 365 innehåller ett brett utbud av säkerhetsfunktioner som uppfyller många organisationers säkerhetsbehov utan ytterligare servrar, till exempel en SIEM-server.</span><span class="sxs-lookup"><span data-stu-id="905b3-115">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="905b3-116">Vissa organisationer har särskilda omständigheter som kräver användningen av en SIEM-server.</span><span class="sxs-lookup"><span data-stu-id="905b3-116">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="905b3-117">Här är några exempel:</span><span class="sxs-lookup"><span data-stu-id="905b3-117">Here are some examples:</span></span>

- <span data-ttu-id="905b3-118">*Fabrikam* har en del innehåll och program lokalt och en del i molnet (de har en hybridmolndistribution).</span><span class="sxs-lookup"><span data-stu-id="905b3-118">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="905b3-119">För att få säkerhetsrapporter för allt innehåll och alla program har Fabrikam implementerat en SIEM-server.</span><span class="sxs-lookup"><span data-stu-id="905b3-119">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>

- <span data-ttu-id="905b3-120">*Contoso* är en organisation för finansiella tjänster som har särskilt strikta säkerhetskrav.</span><span class="sxs-lookup"><span data-stu-id="905b3-120">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="905b3-121">De har lagt till en SIEM-server i miljön för att kunna dra nytta av det extra säkerhetsskydd de behöver.</span><span class="sxs-lookup"><span data-stu-id="905b3-121">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="905b3-122">SIEM-serverintegrering med Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="905b3-122">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="905b3-123">En SIEM-server kan ta emot data från en mängd Microsoft 365 tjänster och program.</span><span class="sxs-lookup"><span data-stu-id="905b3-123">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="905b3-124">I följande tabell visas flera Microsoft 365-tjänster och -program, tillsammans med SIEM-serverindata och -resurser för mer information.</span><span class="sxs-lookup"><span data-stu-id="905b3-124">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

****

|<span data-ttu-id="905b3-125">Microsoft 365 Tjänst eller program</span><span class="sxs-lookup"><span data-stu-id="905b3-125">Microsoft 365 Service or Application</span></span>|<span data-ttu-id="905b3-126">SIEM-serverindata/-metoder</span><span class="sxs-lookup"><span data-stu-id="905b3-126">SIEM server inputs/methods</span></span>|<span data-ttu-id="905b3-127">Resurser för att få mer information</span><span class="sxs-lookup"><span data-stu-id="905b3-127">Resources to learn more</span></span>|
|---|---|---|
|[<span data-ttu-id="905b3-128">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="905b3-128">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)|<span data-ttu-id="905b3-129">Granskningsloggar</span><span class="sxs-lookup"><span data-stu-id="905b3-129">Audit logs</span></span>|[<span data-ttu-id="905b3-130">SIEM-integrering med Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="905b3-130">SIEM integration with Microsoft Defender for Office 365</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="905b3-131">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="905b3-131">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)|<span data-ttu-id="905b3-132">HTTPS-slutpunkt med Azure som värd</span><span class="sxs-lookup"><span data-stu-id="905b3-132">HTTPS endpoint hosted in Azure</span></span> <p> <span data-ttu-id="905b3-133">REST-API</span><span class="sxs-lookup"><span data-stu-id="905b3-133">REST API</span></span>|[<span data-ttu-id="905b3-134">Dra aviseringar till dina SIEM-verktyg</span><span class="sxs-lookup"><span data-stu-id="905b3-134">Pull alerts to your SIEM tools</span></span>](../defender-endpoint/configure-siem.md)|
|[<span data-ttu-id="905b3-135">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="905b3-135">Microsoft Cloud App Security</span></span>](/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="905b3-136">Loggintegrering</span><span class="sxs-lookup"><span data-stu-id="905b3-136">Log integration</span></span>|[<span data-ttu-id="905b3-137">SIEM-integrering med Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="905b3-137">SIEM integration with Microsoft Cloud App Security</span></span>](/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="905b3-138">Ta en titt på [Azure Sentinel](/azure/sentinel/overview).</span><span class="sxs-lookup"><span data-stu-id="905b3-138">Take a look at [Azure Sentinel](/azure/sentinel/overview).</span></span> <span data-ttu-id="905b3-139">Azure Sentinel levereras med kopplingar för Microsoft-lösningar.</span><span class="sxs-lookup"><span data-stu-id="905b3-139">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="905b3-140">Dessa kopplingar är tillgängliga "utan att använda" och ger integration i realtid.</span><span class="sxs-lookup"><span data-stu-id="905b3-140">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="905b3-141">Du kan använda Azure Sentinel med dina Microsoft 365 Defender-lösningar och Microsoft 365-tjänster, inklusive Office 365, Azure AD, Microsoft Defender för identitet, Microsoft Cloud App Security med mera.</span><span class="sxs-lookup"><span data-stu-id="905b3-141">You can use Azure Sentinel with your Microsoft 365 Defender solutions and Microsoft 365 services, including Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="905b3-142">Granskningsloggning måste vara aktiverat</span><span class="sxs-lookup"><span data-stu-id="905b3-142">Audit logging must be turned on</span></span>

<span data-ttu-id="905b3-143">Kontrollera att granskningsloggning är aktiverat innan du konfigurerar SIEM-serverintegrering.</span><span class="sxs-lookup"><span data-stu-id="905b3-143">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="905b3-144">För SharePoint Online, OneDrive för företag och Azure Active Directory är granskningsloggning aktiverad i [Microsoft 365 Defender-portalen.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="905b3-144">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Microsoft 365 Defender portal](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="905b3-145">Mer Exchange Online finns i Hantera [granskning av postlåda.](../../compliance/enable-mailbox-auditing.md)</span><span class="sxs-lookup"><span data-stu-id="905b3-145">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="905b3-146">Fler resurser</span><span class="sxs-lookup"><span data-stu-id="905b3-146">More resources</span></span>

[<span data-ttu-id="905b3-147">Integrera säkerhetslösningar i Azure Defender</span><span class="sxs-lookup"><span data-stu-id="905b3-147">Integrate security solutions in Azure Defender</span></span>](/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="905b3-148">Integrera Microsoft Graph-säkerhets-API-aviseringar med ett SIEM</span><span class="sxs-lookup"><span data-stu-id="905b3-148">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](/graph/security-integration)