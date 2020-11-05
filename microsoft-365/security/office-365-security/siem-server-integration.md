---
title: SIEM Server integration med Microsoft 365-tjänster och-program
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
- seo-marvel-apr2020
description: Få en översikt över säkerhets information och SIEM Server integration med Microsoft 365-molntjänster och-program
ms.openlocfilehash: 17e21d19463187744afe855b2304ac71956545d2
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919770"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="dbaf3-103">Integrering av säkerhets information och Event Management (SIEM) med Microsoft 365-tjänster och-program</span><span class="sxs-lookup"><span data-stu-id="dbaf3-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="summary"></a><span data-ttu-id="dbaf3-104">Sammanfattning</span><span class="sxs-lookup"><span data-stu-id="dbaf3-104">Summary</span></span>

<span data-ttu-id="dbaf3-105">Använder du din organisation för att få en server för säkerhets information och Event Management (SIEM)?</span><span class="sxs-lookup"><span data-stu-id="dbaf3-105">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="dbaf3-106">Du kanske undrar hur det är integrerat med Microsoft 365 eller Office 365.</span><span class="sxs-lookup"><span data-stu-id="dbaf3-106">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="dbaf3-107">I den här artikeln finns en lista med resurser som du kan använda för att integrera din SIEM-server med Microsoft 365-tjänster och-program.</span><span class="sxs-lookup"><span data-stu-id="dbaf3-107">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="dbaf3-108">Om du inte har en SIEM-Server ännu och utforskar dina alternativ bör du överväga **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span><span class="sxs-lookup"><span data-stu-id="dbaf3-108">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="dbaf3-109">Behöver jag en SIEM-Server?</span><span class="sxs-lookup"><span data-stu-id="dbaf3-109">Do I need a SIEM server?</span></span>

<span data-ttu-id="dbaf3-110">Om du behöver en SIEM-Server beror på många faktorer, till exempel organisationens säkerhets krav och var dina data finns.</span><span class="sxs-lookup"><span data-stu-id="dbaf3-110">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="dbaf3-111">Microsoft 365 innehåller en mängd olika säkerhetsfunktioner som uppfyller många organisationers säkerhets behov utan extra servrar, till exempel en SIEM-Server.</span><span class="sxs-lookup"><span data-stu-id="dbaf3-111">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="dbaf3-112">Vissa organisationer har särskilda omständigheter som kräver användning av en SIEM-Server.</span><span class="sxs-lookup"><span data-stu-id="dbaf3-112">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="dbaf3-113">Här är några exempel:</span><span class="sxs-lookup"><span data-stu-id="dbaf3-113">Here are some examples:</span></span>

- <span data-ttu-id="dbaf3-114">*Fabrikam* har ett visst innehåll och program i lokaler och vissa i molnet (de har en hybrid moln distribution).</span><span class="sxs-lookup"><span data-stu-id="dbaf3-114">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="dbaf3-115">Fabrikam har implementerat en SIEM-Server för att få säkerhets rapporter för allt innehåll och alla program.</span><span class="sxs-lookup"><span data-stu-id="dbaf3-115">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>

- <span data-ttu-id="dbaf3-116">*Contoso* är en finans tjänst organisation som har särskilt stränga säkerhets krav.</span><span class="sxs-lookup"><span data-stu-id="dbaf3-116">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="dbaf3-117">De har lagt till en SIEM-server i sin miljö för att utnyttja det extra säkerhets skydd de kräver.</span><span class="sxs-lookup"><span data-stu-id="dbaf3-117">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="dbaf3-118">SIEM Server integration med Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dbaf3-118">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="dbaf3-119">En SIEM-Server kan ta emot data från en mängd olika Microsoft 365-tjänster och-program.</span><span class="sxs-lookup"><span data-stu-id="dbaf3-119">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="dbaf3-120">I följande tabell visas flera Microsoft 365-tjänster och-program, tillsammans med SIEM och resurser för att få mer information.</span><span class="sxs-lookup"><span data-stu-id="dbaf3-120">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

****

|<span data-ttu-id="dbaf3-121">Microsoft 365-tjänsten eller-programmet</span><span class="sxs-lookup"><span data-stu-id="dbaf3-121">Microsoft 365 Service or Application</span></span>|<span data-ttu-id="dbaf3-122">SIEM-Server data/metoder</span><span class="sxs-lookup"><span data-stu-id="dbaf3-122">SIEM server inputs/methods</span></span>|<span data-ttu-id="dbaf3-123">Resurser för att få mer information</span><span class="sxs-lookup"><span data-stu-id="dbaf3-123">Resources to learn more</span></span>|
|---|---|---|
|[<span data-ttu-id="dbaf3-124">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="dbaf3-124">Microsoft Defender for Office 365</span></span>](office-365-atp.md)|<span data-ttu-id="dbaf3-125">Gransknings loggar</span><span class="sxs-lookup"><span data-stu-id="dbaf3-125">Audit logs</span></span>|[<span data-ttu-id="dbaf3-126">SIEM integrering med Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="dbaf3-126">SIEM integration with Microsoft Defender for Office 365</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="dbaf3-127">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="dbaf3-127">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)|<span data-ttu-id="dbaf3-128">HTTPS-slutpunkt med Azure värd</span><span class="sxs-lookup"><span data-stu-id="dbaf3-128">HTTPS endpoint hosted in Azure</span></span> <br/><span data-ttu-id="dbaf3-129">REST API</span><span class="sxs-lookup"><span data-stu-id="dbaf3-129">REST API</span></span>|[<span data-ttu-id="dbaf3-130">Dra aviseringar till dina SIEM-verktyg</span><span class="sxs-lookup"><span data-stu-id="dbaf3-130">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[<span data-ttu-id="dbaf3-131">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="dbaf3-131">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="dbaf3-132">Logg integrering</span><span class="sxs-lookup"><span data-stu-id="dbaf3-132">Log integration</span></span>|[<span data-ttu-id="dbaf3-133">SIEM integrering med säkerhet för Microsoft Cloud App</span><span class="sxs-lookup"><span data-stu-id="dbaf3-133">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="dbaf3-134">Ta en titt på [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span><span class="sxs-lookup"><span data-stu-id="dbaf3-134">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span></span> <span data-ttu-id="dbaf3-135">Azure Sentinel kommer med anslutningar för Microsoft Solutions.</span><span class="sxs-lookup"><span data-stu-id="dbaf3-135">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="dbaf3-136">Dessa kopplingar är tillgängliga "i kartongen" och möjliggör integrering i real tid.</span><span class="sxs-lookup"><span data-stu-id="dbaf3-136">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="dbaf3-137">Du kan använda Azure Sentinel med Microsoft 365 Defender-lösningarna och Microsoft 365-tjänsterna, inklusive Office 365, Azure AD, Microsoft Defender för identitet, Microsoft Cloud App-säkerhet och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="dbaf3-137">You can use Azure Sentinel with your Microsoft 365 Defender solutions and Microsoft 365 services, including Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="dbaf3-138">Gransknings loggning måste aktive ras</span><span class="sxs-lookup"><span data-stu-id="dbaf3-138">Audit logging must be turned on</span></span>

<span data-ttu-id="dbaf3-139">Kontrol lera att gransknings loggning är aktiverat innan du konfigurerar SIEM.</span><span class="sxs-lookup"><span data-stu-id="dbaf3-139">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="dbaf3-140">För SharePoint Online, OneDrive för företag och Azure Active Directory [aktive ras gransknings loggning i säkerhets & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="dbaf3-140">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="dbaf3-141">För Exchange Online, se [hantera granskning av post låda](../../compliance/enable-mailbox-auditing.md).</span><span class="sxs-lookup"><span data-stu-id="dbaf3-141">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="dbaf3-142">Fler resurser</span><span class="sxs-lookup"><span data-stu-id="dbaf3-142">More resources</span></span>

[<span data-ttu-id="dbaf3-143">Integrera säkerhetslösningar i Azure Defender</span><span class="sxs-lookup"><span data-stu-id="dbaf3-143">Integrate security solutions in Azure Defender</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="dbaf3-144">Integrera Microsoft Graph-säkerhetsfunktionerna med en SIEM</span><span class="sxs-lookup"><span data-stu-id="dbaf3-144">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)
