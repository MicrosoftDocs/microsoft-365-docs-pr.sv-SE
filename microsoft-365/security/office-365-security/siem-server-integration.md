---
title: SIEM-serverintegrering med Microsoft 365-tjänster och -program
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
description: Få en översikt över säkerhetsinformation och händelsehantering (SIEM) serverintegrering med Microsoft 365-molntjänster och -program
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b4490d52cbd403bf4ce2cc3f3fb3c5a91c5646b9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290387"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="2577b-103">Säkerhetsinformation och händelsehantering (SIEM) serverintegrering med Microsoft 365-tjänster och -program</span><span class="sxs-lookup"><span data-stu-id="2577b-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

<span data-ttu-id="2577b-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="2577b-104">**Applies to**</span></span>
- [<span data-ttu-id="2577b-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2577b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="2577b-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="2577b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="2577b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2577b-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a><span data-ttu-id="2577b-108">Sammanfattning</span><span class="sxs-lookup"><span data-stu-id="2577b-108">Summary</span></span>

<span data-ttu-id="2577b-109">Använder eller planerar organisationen en säkerhetsinformations- och händelsehanteringsserver (SIEM)?</span><span class="sxs-lookup"><span data-stu-id="2577b-109">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="2577b-110">Du kanske undrar hur det är integrerat med Microsoft 365 eller Office 365.</span><span class="sxs-lookup"><span data-stu-id="2577b-110">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="2577b-111">Den här artikeln innehåller en lista över resurser som du kan använda för att integrera DIN SIEM-server med Microsoft 365-tjänster och -program.</span><span class="sxs-lookup"><span data-stu-id="2577b-111">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="2577b-112">Om du inte har en SIEM-server ännu och utforskar alternativen kan du överväga **[Microsoft Azure Sentinel.](https://docs.microsoft.com/azure/sentinel/overview)**</span><span class="sxs-lookup"><span data-stu-id="2577b-112">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="2577b-113">Behöver jag en SIEM-server?</span><span class="sxs-lookup"><span data-stu-id="2577b-113">Do I need a SIEM server?</span></span>

<span data-ttu-id="2577b-114">Om du behöver en SIEM-server beror på många faktorer, till exempel organisationens säkerhetskrav och var dina data finns.</span><span class="sxs-lookup"><span data-stu-id="2577b-114">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="2577b-115">Microsoft 365 innehåller ett brett utbud av säkerhetsfunktioner som uppfyller många organisationers säkerhetsbehov utan ytterligare servrar, till exempel en SIEM-server.</span><span class="sxs-lookup"><span data-stu-id="2577b-115">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="2577b-116">Vissa organisationer har särskilda omständigheter som kräver användningen av en SIEM-server.</span><span class="sxs-lookup"><span data-stu-id="2577b-116">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="2577b-117">Här är några exempel:</span><span class="sxs-lookup"><span data-stu-id="2577b-117">Here are some examples:</span></span>

- <span data-ttu-id="2577b-118">*Fabrikam* har en del innehåll och program lokalt och vissa i molnet (de har en hybridmolndistribution).</span><span class="sxs-lookup"><span data-stu-id="2577b-118">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="2577b-119">För att få fram säkerhetsrapporter i allt innehåll och i alla program har Fabrikam implementerat en SIEM-server.</span><span class="sxs-lookup"><span data-stu-id="2577b-119">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>

- <span data-ttu-id="2577b-120">*Contoso* är en organisation för finansiella tjänster som har särskilt strikta säkerhetskrav.</span><span class="sxs-lookup"><span data-stu-id="2577b-120">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="2577b-121">De har lagt till en SIEM-server i sin miljö för att dra nytta av det extra säkerhetsskydd som de kräver.</span><span class="sxs-lookup"><span data-stu-id="2577b-121">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="2577b-122">SIEM-serverintegrering med Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2577b-122">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="2577b-123">En SIEM-server kan ta emot data från en mängd olika Microsoft 365-tjänster och -program.</span><span class="sxs-lookup"><span data-stu-id="2577b-123">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="2577b-124">I följande tabell finns flera Microsoft 365-tjänster och -program samt SIEM-serverindata och resurser för mer information.</span><span class="sxs-lookup"><span data-stu-id="2577b-124">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

****

|<span data-ttu-id="2577b-125">Microsoft 365-tjänst eller -program</span><span class="sxs-lookup"><span data-stu-id="2577b-125">Microsoft 365 Service or Application</span></span>|<span data-ttu-id="2577b-126">SIEM-serverindata/-metoder</span><span class="sxs-lookup"><span data-stu-id="2577b-126">SIEM server inputs/methods</span></span>|<span data-ttu-id="2577b-127">Resurser för att få mer information</span><span class="sxs-lookup"><span data-stu-id="2577b-127">Resources to learn more</span></span>|
|---|---|---|
|[<span data-ttu-id="2577b-128">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="2577b-128">Microsoft Defender for Office 365</span></span>](office-365-atp.md)|<span data-ttu-id="2577b-129">Granskningsloggar</span><span class="sxs-lookup"><span data-stu-id="2577b-129">Audit logs</span></span>|[<span data-ttu-id="2577b-130">SIEM-integrering med Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="2577b-130">SIEM integration with Microsoft Defender for Office 365</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="2577b-131">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="2577b-131">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)|<span data-ttu-id="2577b-132">HTTPS-slutpunkt i Azure</span><span class="sxs-lookup"><span data-stu-id="2577b-132">HTTPS endpoint hosted in Azure</span></span> <p> <span data-ttu-id="2577b-133">REST API</span><span class="sxs-lookup"><span data-stu-id="2577b-133">REST API</span></span>|[<span data-ttu-id="2577b-134">Dra aviseringar till dina SIEM-verktyg</span><span class="sxs-lookup"><span data-stu-id="2577b-134">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[<span data-ttu-id="2577b-135">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2577b-135">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="2577b-136">Loggintegrering</span><span class="sxs-lookup"><span data-stu-id="2577b-136">Log integration</span></span>|[<span data-ttu-id="2577b-137">SIEM-integrering med Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2577b-137">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="2577b-138">Ta en titt på [Azure Sentinel.](https://docs.microsoft.com/azure/sentinel/overview)</span><span class="sxs-lookup"><span data-stu-id="2577b-138">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span></span> <span data-ttu-id="2577b-139">Azure Sentinel levereras med kopplingar för Microsoft-lösningar.</span><span class="sxs-lookup"><span data-stu-id="2577b-139">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="2577b-140">De här anslutningarna är tillgängliga så att de kan integreras i realtid.</span><span class="sxs-lookup"><span data-stu-id="2577b-140">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="2577b-141">Du kan använda Azure Sentinel med dina Microsoft 365 Defender-lösningar och Microsoft 365-tjänster, inklusive Office 365, Azure AD, Microsoft Defender för identitet, Microsoft Cloud App Security med mera.</span><span class="sxs-lookup"><span data-stu-id="2577b-141">You can use Azure Sentinel with your Microsoft 365 Defender solutions and Microsoft 365 services, including Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="2577b-142">Granskningsloggning måste vara aktiverad</span><span class="sxs-lookup"><span data-stu-id="2577b-142">Audit logging must be turned on</span></span>

<span data-ttu-id="2577b-143">Kontrollera att granskningsloggning är aktiverad innan du konfigurerar SIEM-serverintegrering.</span><span class="sxs-lookup"><span data-stu-id="2577b-143">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="2577b-144">För SharePoint Online, OneDrive för företag och Azure Active Directory är granskningsloggning aktiverad i Säkerhets- [& Efterlevnadscenter.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="2577b-144">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="2577b-145">Mer information om Exchange Online finns i [Hantera granskning av postlådor.](../../compliance/enable-mailbox-auditing.md)</span><span class="sxs-lookup"><span data-stu-id="2577b-145">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="2577b-146">Fler resurser</span><span class="sxs-lookup"><span data-stu-id="2577b-146">More resources</span></span>

[<span data-ttu-id="2577b-147">Integrera säkerhetslösningar i Azure Defender</span><span class="sxs-lookup"><span data-stu-id="2577b-147">Integrate security solutions in Azure Defender</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="2577b-148">Integrera Microsoft Graph-säkerhets-API-aviseringar med en SIEM</span><span class="sxs-lookup"><span data-stu-id="2577b-148">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)
