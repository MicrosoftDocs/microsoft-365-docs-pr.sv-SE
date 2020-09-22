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
ms.openlocfilehash: 6d657990417cab2a8cbb1b03b8b79a65c095d1a5
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202215"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="5429f-103">Integrering av säkerhets information och Event Management (SIEM) med Microsoft 365-tjänster och-program</span><span class="sxs-lookup"><span data-stu-id="5429f-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="summary"></a><span data-ttu-id="5429f-104">Sammanfattning</span><span class="sxs-lookup"><span data-stu-id="5429f-104">Summary</span></span>

<span data-ttu-id="5429f-105">Använder du din organisation för att få en server för säkerhets information och Event Management (SIEM)?</span><span class="sxs-lookup"><span data-stu-id="5429f-105">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="5429f-106">Du kanske undrar hur det är integrerat med Microsoft 365 eller Office 365.</span><span class="sxs-lookup"><span data-stu-id="5429f-106">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="5429f-107">I den här artikeln finns en lista med resurser som du kan använda för att integrera din SIEM-server med Microsoft 365-tjänster och-program.</span><span class="sxs-lookup"><span data-stu-id="5429f-107">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="5429f-108">Om du inte har en SIEM-Server ännu och utforskar dina alternativ bör du överväga **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span><span class="sxs-lookup"><span data-stu-id="5429f-108">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="5429f-109">Behöver jag en SIEM-Server?</span><span class="sxs-lookup"><span data-stu-id="5429f-109">Do I need a SIEM server?</span></span>

<span data-ttu-id="5429f-110">Om du behöver en SIEM-Server beror på många faktorer, till exempel organisationens säkerhets krav och var dina data finns.</span><span class="sxs-lookup"><span data-stu-id="5429f-110">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="5429f-111">Microsoft 365 innehåller en mängd olika säkerhetsfunktioner som uppfyller många organisationers säkerhets behov utan extra servrar, till exempel en SIEM-Server.</span><span class="sxs-lookup"><span data-stu-id="5429f-111">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="5429f-112">Vissa organisationer har särskilda omständigheter som kräver användning av en SIEM-Server.</span><span class="sxs-lookup"><span data-stu-id="5429f-112">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="5429f-113">Här är några exempel:</span><span class="sxs-lookup"><span data-stu-id="5429f-113">Here are some examples:</span></span>

- <span data-ttu-id="5429f-114">*Fabrikam* har ett visst innehåll och program i lokaler och vissa i molnet (de har en hybrid moln distribution).</span><span class="sxs-lookup"><span data-stu-id="5429f-114">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="5429f-115">Fabrikam har implementerat en SIEM-Server för att få säkerhets rapporter för allt innehåll och alla program.</span><span class="sxs-lookup"><span data-stu-id="5429f-115">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>

- <span data-ttu-id="5429f-116">*Contoso* är en finans tjänst organisation som har särskilt stränga säkerhets krav.</span><span class="sxs-lookup"><span data-stu-id="5429f-116">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="5429f-117">De har lagt till en SIEM-server i sin miljö för att utnyttja det extra säkerhets skydd de kräver.</span><span class="sxs-lookup"><span data-stu-id="5429f-117">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="5429f-118">SIEM Server integration med Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5429f-118">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="5429f-119">En SIEM-Server kan ta emot data från en mängd olika Microsoft 365-tjänster och-program.</span><span class="sxs-lookup"><span data-stu-id="5429f-119">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="5429f-120">I följande tabell visas flera Microsoft 365-tjänster och-program, tillsammans med SIEM och resurser för att få mer information.</span><span class="sxs-lookup"><span data-stu-id="5429f-120">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

****

|<span data-ttu-id="5429f-121">Microsoft 365-tjänsten eller-programmet</span><span class="sxs-lookup"><span data-stu-id="5429f-121">Microsoft 365 Service or Application</span></span>|<span data-ttu-id="5429f-122">SIEM-Server data/metoder</span><span class="sxs-lookup"><span data-stu-id="5429f-122">SIEM server inputs/methods</span></span>|<span data-ttu-id="5429f-123">Resurser för att få mer information</span><span class="sxs-lookup"><span data-stu-id="5429f-123">Resources to learn more</span></span>|
|---|---|---|
|[<span data-ttu-id="5429f-124">Office 365 Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="5429f-124">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)|<span data-ttu-id="5429f-125">Gransknings loggar</span><span class="sxs-lookup"><span data-stu-id="5429f-125">Audit logs</span></span>|[<span data-ttu-id="5429f-126">SIEM integrering med Office 365 Avancerat skydd för hotet</span><span class="sxs-lookup"><span data-stu-id="5429f-126">SIEM integration with Office 365 Advanced Threat Protection</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="5429f-127">Microsoft Defender Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="5429f-127">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)|<span data-ttu-id="5429f-128">HTTPS-slutpunkt med Azure värd</span><span class="sxs-lookup"><span data-stu-id="5429f-128">HTTPS endpoint hosted in Azure</span></span> <br/><span data-ttu-id="5429f-129">REST API</span><span class="sxs-lookup"><span data-stu-id="5429f-129">REST API</span></span>|[<span data-ttu-id="5429f-130">Dra aviseringar till dina SIEM-verktyg</span><span class="sxs-lookup"><span data-stu-id="5429f-130">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[<span data-ttu-id="5429f-131">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="5429f-131">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="5429f-132">Logg integrering</span><span class="sxs-lookup"><span data-stu-id="5429f-132">Log integration</span></span>|[<span data-ttu-id="5429f-133">SIEM integrering med säkerhet för Microsoft Cloud App</span><span class="sxs-lookup"><span data-stu-id="5429f-133">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="5429f-134">Ta en titt på [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span><span class="sxs-lookup"><span data-stu-id="5429f-134">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span></span> <span data-ttu-id="5429f-135">Azure Sentinel kommer med anslutningar för Microsoft Solutions.</span><span class="sxs-lookup"><span data-stu-id="5429f-135">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="5429f-136">Dessa kopplingar är tillgängliga "i kartongen" och möjliggör integrering i real tid.</span><span class="sxs-lookup"><span data-stu-id="5429f-136">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="5429f-137">Du kan använda Azure Sentinel med Microsoft Threat Protection Solutions och Microsoft 365-tjänsterna, inklusive Office 365, Azure AD, Azure ATP, Microsoft Cloud App Security och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="5429f-137">You can use Azure Sentinel with your Microsoft Threat Protection solutions and Microsoft 365 services, including Office 365, Azure AD, Azure ATP, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="5429f-138">Gransknings loggning måste aktive ras</span><span class="sxs-lookup"><span data-stu-id="5429f-138">Audit logging must be turned on</span></span>

<span data-ttu-id="5429f-139">Kontrol lera att gransknings loggning är aktiverat innan du konfigurerar SIEM.</span><span class="sxs-lookup"><span data-stu-id="5429f-139">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="5429f-140">För SharePoint Online, OneDrive för företag och Azure Active Directory [aktive ras gransknings loggning i säkerhets & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="5429f-140">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="5429f-141">För Exchange Online, se [hantera granskning av post låda](../../compliance/enable-mailbox-auditing.md).</span><span class="sxs-lookup"><span data-stu-id="5429f-141">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="5429f-142">Fler resurser</span><span class="sxs-lookup"><span data-stu-id="5429f-142">More resources</span></span>

[<span data-ttu-id="5429f-143">Integrera säkerhetslösningar i Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="5429f-143">Integrate security solutions in Azure Security Center</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="5429f-144">Integrera Microsoft Graph-säkerhetsfunktionerna med en SIEM</span><span class="sxs-lookup"><span data-stu-id="5429f-144">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)
