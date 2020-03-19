---
title: SIEM-integrering med Office 365 Avancerat hotskydd
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
ms.date: 11/22/2019
ms.collection:
- M365-security-compliance
description: Integrera organisationens SIEM-server med Office 365 Advanced Threat Protection och relaterade hothändelser i Office 365 Activity Management API.
ms.openlocfilehash: 8a870e02a37ea7f4961d0b8dc42a49cb59d2bace
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42807652"
---
# <a name="siem-integration-with-office-365-advanced-threat-protection"></a><span data-ttu-id="d0985-103">SIEM-integrering med Office 365 Avancerat hotskydd</span><span class="sxs-lookup"><span data-stu-id="d0985-103">SIEM integration with Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="d0985-104">Om din organisation använder en SIEM-server (Security Incident and Event Management) kan du integrera Office 365 Advanced Threat Protection med SIEM-servern.</span><span class="sxs-lookup"><span data-stu-id="d0985-104">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Advanced Threat Protection with your SIEM server.</span></span> <span data-ttu-id="d0985-105">Med SIEM-integrering kan du visa information, till exempel skadlig kod eller phish som upptäckts av Office 365 Advanced Protection, i SIEM-serverrapporterna.</span><span class="sxs-lookup"><span data-stu-id="d0985-105">SIEM integration enables you to view information, such as malware or phish detected by Office 365 Advanced Protection, in your SIEM server reports.</span></span> <span data-ttu-id="d0985-106">Om du vill konfigurera SIEM-integrering använder du [API:et för Aktivitetshantering i Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span><span class="sxs-lookup"><span data-stu-id="d0985-106">To set up SIEM integration, you use the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="d0985-107">Office 365 Activity Management API hämtar information om åtgärder och åtgärder och händelser för användare, administratörer, system och principer från organisationens Aktivitetsloggar för Office 365 och Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d0985-107">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Office 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="d0985-108">[Office 365 Advanced Threat Protection-schemat](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) fungerar med avancerat hotskydd, så om din organisation har Office 365 Advanced Threat Protection Plan 1 eller Plan 2 eller Office 365 E5 kan du fortfarande använda samma API för din SIEM-serverintegrering.</span><span class="sxs-lookup"><span data-stu-id="d0985-108">The [Office 365 Advanced Threat Protection schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) works with Advanced Threat Protection, so if your organization has the Office 365 Advanced Threat Protection Plan 1 or Plan 2 or Office 365 E5, you can still use that same API for your SIEM server integration.</span></span> 

<span data-ttu-id="d0985-109">Som en del av våra senaste uppdateringar har vi också lagt till händelser från automatiska undersöknings- och svarsfunktioner i Office 365 ATP Plan 2 i Api:et för Office 365 Management Activity.</span><span class="sxs-lookup"><span data-stu-id="d0985-109">As part of our recent updates, we have also added events from automated investigation and response capabilities in Office 365 ATP Plan 2 within the Office 365 Management Activity API.</span></span> <span data-ttu-id="d0985-110">Förutom att inkludera data om centrala undersökningsdetaljer som ID, namn och status innehåller den även information på hög nivå om utredningsåtgärder och enheter.</span><span class="sxs-lookup"><span data-stu-id="d0985-110">In addition to including data about core investigation details such as ID, name and status, it also contains high-level information about investigation actions and entities.</span></span>   

<span data-ttu-id="d0985-111">SIEM-servern eller något annat liknande system bör avsöka **den audit.general-arbetsbelastningen** för att komma åt identifieringshändelser.</span><span class="sxs-lookup"><span data-stu-id="d0985-111">The SIEM server or other similar system should poll the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="d0985-112">Mer information finns i [Komma igång med Office 365 Management API:er](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="d0985-112">To learn more see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> <span data-ttu-id="d0985-113">Dessutom är följande värden för **AuditLogRecordType** relevanta för Office 365 ATP-händelser:</span><span class="sxs-lookup"><span data-stu-id="d0985-113">In addition, the following values of **AuditLogRecordType** are relevant for Office 365 ATP events:</span></span>

### <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="d0985-114">Uppräkning: AuditLogRecordType - Typ: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="d0985-114">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

#### <a name="auditlogrecordtype"></a><span data-ttu-id="d0985-115">Granskaloggposttyp</span><span class="sxs-lookup"><span data-stu-id="d0985-115">AuditLogRecordType</span></span>

|<span data-ttu-id="d0985-116">Value</span><span class="sxs-lookup"><span data-stu-id="d0985-116">Value</span></span>|<span data-ttu-id="d0985-117">Medlemsnamn</span><span class="sxs-lookup"><span data-stu-id="d0985-117">Member name</span></span>|<span data-ttu-id="d0985-118">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="d0985-118">Description</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d0985-119">28</span><span class="sxs-lookup"><span data-stu-id="d0985-119">28</span></span>|<span data-ttu-id="d0985-120">HotIntelligens</span><span class="sxs-lookup"><span data-stu-id="d0985-120">ThreatIntelligence</span></span>|<span data-ttu-id="d0985-121">Händelser med nätfiske och skadlig kod från Exchange Online Protection och Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="d0985-121">Phishing and malware events from Exchange Online Protection and Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="d0985-122">41</span><span class="sxs-lookup"><span data-stu-id="d0985-122">41</span></span>|<span data-ttu-id="d0985-123">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="d0985-123">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="d0985-124">TIME-of-block-händelser och blockera ATP-säkerhetslänkar och blockera åsidosätta händelser från Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="d0985-124">ATP Safe Links time-of-block and block override events from Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="d0985-125">47</span><span class="sxs-lookup"><span data-stu-id="d0985-125">47</span></span>|<span data-ttu-id="d0985-126">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="d0985-126">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="d0985-127">Händelser för nätfiske och skadlig kod för filer i SharePoint Online, OneDrive för företag och Microsoft Teams från Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="d0985-127">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams from Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="d0985-128">64</span><span class="sxs-lookup"><span data-stu-id="d0985-128">64</span></span>|<span data-ttu-id="d0985-129">Flygutredning</span><span class="sxs-lookup"><span data-stu-id="d0985-129">AirInvestigation</span></span>|<span data-ttu-id="d0985-130">Automatiserade gransknings- och svarshändelser, till exempel undersökningsinformation och relevanta artefakter från Office 365 Advanced Threat Protection Plan 2.</span><span class="sxs-lookup"><span data-stu-id="d0985-130">Automated investigation and response events, such as investigation details and relevant artifacts from Office 365 Advanced Threat Protection Plan 2.</span></span>|


> [!IMPORTANT]
> <span data-ttu-id="d0985-131">Du måste vara en global Office 365-administratör eller ha rollen säkerhetsadministratör som tilldelats säkerhets& Compliance Center för att konfigurera SIEM-integrering med Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="d0985-131">You must be an Office 365 global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Office 365 Advanced Threat Protection.</span></span><br/><span data-ttu-id="d0985-132">Granskningsloggning måste vara aktiverad för din Office 365-miljö.</span><span class="sxs-lookup"><span data-stu-id="d0985-132">Audit logging must be turned on for your Office 365 environment.</span></span> <span data-ttu-id="d0985-133">Information om hur du får hjälp med detta finns [i Aktivera eller inaktivera sökningen i granskningsloggen för Office 365](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="d0985-133">To get help with this, see [Turn Office 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d0985-134">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="d0985-134">Related topics</span></span>

[<span data-ttu-id="d0985-135">Office 365 hotutredning och svar</span><span class="sxs-lookup"><span data-stu-id="d0985-135">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="d0985-136">Automatiserad undersökning och svar (AIR) i Office 365</span><span class="sxs-lookup"><span data-stu-id="d0985-136">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)

[<span data-ttu-id="d0985-137">Office 365 Avancerat hotskydd</span><span class="sxs-lookup"><span data-stu-id="d0985-137">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

[<span data-ttu-id="d0985-138">Smarta rapporter och insikter i Office &amp; 365 Security Compliance Center</span><span class="sxs-lookup"><span data-stu-id="d0985-138">Smart reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="d0985-139">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="d0985-139">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  
