---
title: SIEM integrering med Microsoft Defender för Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Integrera din organisations SIEM-server med Microsoft Defender för Office 365 och relaterade hot händelser i Office 365 Activity Management API.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 185e6e816cfff4131d7b5af11c4e3ea9cf94b338
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843582"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a><span data-ttu-id="cd924-103">SIEM integrering med Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="cd924-103">SIEM integration with Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="cd924-104">Om din organisation använder en säkerhets information och en server för Event Management (SIEM) kan du integrera Microsoft Defender för Office 365 med din SIEM-Server.</span><span class="sxs-lookup"><span data-stu-id="cd924-104">If your organization is using a security information and event management (SIEM) server, you can integrate Microsoft Defender for Office 365 with your SIEM server.</span></span> <span data-ttu-id="cd924-105">Du kan ställa in denna integrering genom att använda [API för aktivitets hantering i Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span><span class="sxs-lookup"><span data-stu-id="cd924-105">You can set up this integration by using the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="cd924-106">SIEM integrering gör att du kan visa information, till exempel skadlig program vara eller Phish som identifieras av Microsoft Defender för Office 365, i dina SIEM Server-rapporter.</span><span class="sxs-lookup"><span data-stu-id="cd924-106">SIEM integration enables you to view information, such as malware or phish detected by Microsoft Defender for Office 365, in your SIEM server reports.</span></span> 

- <span data-ttu-id="cd924-107">Om du vill se ett exempel på SIEM-integrering med Microsoft Defender för Office 365, se Tech (community) för [SOC med Defender för office 365 och O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span><span class="sxs-lookup"><span data-stu-id="cd924-107">To see an example of SIEM integration with Microsoft Defender for Office 365, see [Tech Community blog: Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="cd924-108">Mer information om API-gränssnitten för Office 365 finns i [Översikt över API för office 365 Management](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span><span class="sxs-lookup"><span data-stu-id="cd924-108">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="cd924-109">Så fungerar SIEM-integrering</span><span class="sxs-lookup"><span data-stu-id="cd924-109">How SIEM integration works</span></span>

<span data-ttu-id="cd924-110">API: t för aktivitets hantering i Office 365 hämtar information om åtgärder och händelser för användare, administratörer, system och principer från organisationens Microsoft 365-och Azure Active Directory-aktivitets loggar.</span><span class="sxs-lookup"><span data-stu-id="cd924-110">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="cd924-111">Om din organisation har Microsoft Defender för Office 365 abonnemang 1 eller 2 eller Office 365 E5 kan du använda [Microsoft Defender för office 365-schemat](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span><span class="sxs-lookup"><span data-stu-id="cd924-111">If your organization has Microsoft Defender for Office 365 Plan 1 or 2, or Office 365 E5, you can use the [Microsoft Defender for Office 365 schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>  

<span data-ttu-id="cd924-112">Nyligen har händelser från automatiserade undersökningar och svars funktioner i [Microsoft Defender för office 365 abonnemang 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) lagts till i API för hanterings aktiviteten för Office 365.</span><span class="sxs-lookup"><span data-stu-id="cd924-112">Recently, events from automated investigation and response capabilities in [Microsoft Defender for Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="cd924-113">Förutom att inkludera uppgifter om grundläggande undersöknings uppgifter, till exempel ID, namn och status, innehåller API: n också information om undersöknings åtgärder och-enheter.</span><span class="sxs-lookup"><span data-stu-id="cd924-113">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="cd924-114">SIEM-servern eller liknande system avsöker **granskningen. allmänna** arbets belastning för att få åtkomst till identifierings händelser.</span><span class="sxs-lookup"><span data-stu-id="cd924-114">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="cd924-115">Mer information finns i [komma igång med Office 365 Management API: er](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="cd924-115">To learn more, see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> 

## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="cd924-116">Enum: AuditLogRecordType-Type: EDM. Int32</span><span class="sxs-lookup"><span data-stu-id="cd924-116">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="cd924-117">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="cd924-117">AuditLogRecordType</span></span>

<span data-ttu-id="cd924-118">I följande tabell sammanfattas de värden för **AuditLogRecordType** som är relevanta för Microsoft Defender för Office 365-händelser:</span><span class="sxs-lookup"><span data-stu-id="cd924-118">The following table summarizes the values of **AuditLogRecordType** that are relevant for Microsoft Defender for Office 365 events:</span></span>

|<span data-ttu-id="cd924-119">Värde</span><span class="sxs-lookup"><span data-stu-id="cd924-119">Value</span></span>|<span data-ttu-id="cd924-120">Medlems namn</span><span class="sxs-lookup"><span data-stu-id="cd924-120">Member name</span></span>|<span data-ttu-id="cd924-121">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="cd924-121">Description</span></span>|
|---|---|---|
|<span data-ttu-id="cd924-122">28</span><span class="sxs-lookup"><span data-stu-id="cd924-122">28</span></span>|<span data-ttu-id="cd924-123">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="cd924-123">ThreatIntelligence</span></span>|<span data-ttu-id="cd924-124">Phishing-och malware-händelser från Exchange Online Protection och Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="cd924-124">Phishing and malware events from Exchange Online Protection and Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="cd924-125">41</span><span class="sxs-lookup"><span data-stu-id="cd924-125">41</span></span>|<span data-ttu-id="cd924-126">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="cd924-126">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="cd924-127">Säkra länkar tids-och Blocks händelser från Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="cd924-127">Safe Links time-of-block and block override events from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="cd924-128">47</span><span class="sxs-lookup"><span data-stu-id="cd924-128">47</span></span>|<span data-ttu-id="cd924-129">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="cd924-129">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="cd924-130">Phishing-och malware-händelser för filer i SharePoint Online, OneDrive för företag och Microsoft Teams från Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="cd924-130">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="cd924-131">64</span><span class="sxs-lookup"><span data-stu-id="cd924-131">64</span></span>|<span data-ttu-id="cd924-132">Luftprövning</span><span class="sxs-lookup"><span data-stu-id="cd924-132">AirInvestigation</span></span>|<span data-ttu-id="cd924-133">Automatiserade undersökningar och svars händelser, till exempel information om undersökningar och relevanta artefakter, från Microsoft Defender för Office 365 abonnemang 2.</span><span class="sxs-lookup"><span data-stu-id="cd924-133">Automated investigation and response events, such as investigation details and relevant artifacts, from Microsoft Defender for Office 365 Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="cd924-134">Du måste vara global administratör eller ha rollen som säkerhets administratör tilldelad för säkerhets & Compliance Center för att konfigurera SIEM-integrering med Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="cd924-134">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Microsoft Defender for Office 365.</span></span><br/><span data-ttu-id="cd924-135">Gransknings loggning måste vara aktiverat för din Microsoft 365-miljö.</span><span class="sxs-lookup"><span data-stu-id="cd924-135">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="cd924-136">Om du behöver hjälp kan du läsa [Aktivera och inaktivera gransknings loggs ökning](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="cd924-136">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cd924-137">Se även</span><span class="sxs-lookup"><span data-stu-id="cd924-137">See also</span></span>

[<span data-ttu-id="cd924-138">Office 365 undersökning av hot och svar</span><span class="sxs-lookup"><span data-stu-id="cd924-138">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="cd924-139">Automatisk undersökning och svar (AIR) i Office 365</span><span class="sxs-lookup"><span data-stu-id="cd924-139">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)

