---
title: SIEM-integrering med avancerat hotskydd
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0527a998e7049960df840c7756ef5deaafaf5ade
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035278"
---
# <a name="siem-integration-with-advanced-threat-protection"></a><span data-ttu-id="16f6d-103">SIEM-integrering med avancerat hotskydd</span><span class="sxs-lookup"><span data-stu-id="16f6d-103">SIEM integration with Advanced Threat Protection</span></span>

<span data-ttu-id="16f6d-104">Om din organisation använder en SIEM-server (Security Incident and Event Management) kan du integrera Office 365 Advanced Threat Protection med DIN SIEM-server.</span><span class="sxs-lookup"><span data-stu-id="16f6d-104">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Advanced Threat Protection with your SIEM server.</span></span> <span data-ttu-id="16f6d-105">Med SIEM-integrering kan du visa information, till exempel skadlig kod eller phish som upptäckts av Office 365 Advanced Protection, i dina SIEM-serverrapporter.</span><span class="sxs-lookup"><span data-stu-id="16f6d-105">SIEM integration enables you to view information, such as malware or phish detected by Office 365 Advanced Protection, in your SIEM server reports.</span></span> <span data-ttu-id="16f6d-106">Om du vill konfigurera SIEM-integrering använder du [API:et för Aktivitetshantering i Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span><span class="sxs-lookup"><span data-stu-id="16f6d-106">To set up SIEM integration, you use the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="16f6d-107">Api:et för Aktivitetshantering i Office 365 hämtar information om användar-, administratörs-, system- och principåtgärder och händelser från organisationens Microsoft 365 för företag och Azure Active Directory-aktivitetsloggar.</span><span class="sxs-lookup"><span data-stu-id="16f6d-107">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 for business and Azure Active Directory activity logs.</span></span> <span data-ttu-id="16f6d-108">[Schemat för avancerat skydd mot hot i Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) fungerar med avancerat skydd mot hot, så om din organisation har Office 365 Advanced Threat Protection Plan 1 eller Plan 2 eller Office 365 E5 kan du fortfarande använda samma API för din SIEM-serverintegration.</span><span class="sxs-lookup"><span data-stu-id="16f6d-108">The [Office 365 Advanced Threat Protection schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) works with Advanced Threat Protection, so if your organization has the Office 365 Advanced Threat Protection Plan 1 or Plan 2 or Office 365 E5, you can still use that same API for your SIEM server integration.</span></span> 

<span data-ttu-id="16f6d-109">Som en del av våra senaste uppdateringar har vi också lagt till händelser från automatiska undersöknings- och svarsfunktioner i Office 365 ATP-abonnemang 2 inom Office 365 Management Activity API.</span><span class="sxs-lookup"><span data-stu-id="16f6d-109">As part of our recent updates, we have also added events from automated investigation and response capabilities in Office 365 ATP Plan 2 within the Office 365 Management Activity API.</span></span> <span data-ttu-id="16f6d-110">Förutom att inkludera data om grundläggande undersökningsinformation som ID, namn och status, innehåller den också information på hög nivå om undersökningsåtgärder och enheter.</span><span class="sxs-lookup"><span data-stu-id="16f6d-110">In addition to including data about core investigation details such as ID, name and status, it also contains high-level information about investigation actions and entities.</span></span>   

<span data-ttu-id="16f6d-111">SIEM-servern eller något annat liknande system bör avsöka **audit.general-arbetsbelastningen** för att komma åt identifieringshändelser.</span><span class="sxs-lookup"><span data-stu-id="16f6d-111">The SIEM server or other similar system should poll the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="16f6d-112">Mer information finns [i Komma igång med API:er för hantering av Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="16f6d-112">To learn more see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> <span data-ttu-id="16f6d-113">Dessutom är följande värden för **AuditLogRecordType** relevanta för Office 365 ATP-händelser:</span><span class="sxs-lookup"><span data-stu-id="16f6d-113">In addition, the following values of **AuditLogRecordType** are relevant for Office 365 ATP events:</span></span>

### <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="16f6d-114">Uppräkning: AuditLogRecordType - Typ: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="16f6d-114">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

#### <a name="auditlogrecordtype"></a><span data-ttu-id="16f6d-115">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="16f6d-115">AuditLogRecordType</span></span>

|<span data-ttu-id="16f6d-116">Value</span><span class="sxs-lookup"><span data-stu-id="16f6d-116">Value</span></span>|<span data-ttu-id="16f6d-117">Medlemmens namn</span><span class="sxs-lookup"><span data-stu-id="16f6d-117">Member name</span></span>|<span data-ttu-id="16f6d-118">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="16f6d-118">Description</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="16f6d-119">28</span><span class="sxs-lookup"><span data-stu-id="16f6d-119">28</span></span>|<span data-ttu-id="16f6d-120">HotIntelligens</span><span class="sxs-lookup"><span data-stu-id="16f6d-120">ThreatIntelligence</span></span>|<span data-ttu-id="16f6d-121">Nätfiske- och skadlig kodhändelser från Exchange Online Protection och Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="16f6d-121">Phishing and malware events from Exchange Online Protection and Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="16f6d-122">41</span><span class="sxs-lookup"><span data-stu-id="16f6d-122">41</span></span>|<span data-ttu-id="16f6d-123">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="16f6d-123">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="16f6d-124">ATP Safe Links tid för block- och blockera åsidosättningshändelser från Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="16f6d-124">ATP Safe Links time-of-block and block override events from Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="16f6d-125">47</span><span class="sxs-lookup"><span data-stu-id="16f6d-125">47</span></span>|<span data-ttu-id="16f6d-126">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="16f6d-126">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="16f6d-127">Nätfiske- och skadlig kodhändelser för filer i SharePoint Online, OneDrive för företag och Microsoft Teams från Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="16f6d-127">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams from Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="16f6d-128">64</span><span class="sxs-lookup"><span data-stu-id="16f6d-128">64</span></span>|<span data-ttu-id="16f6d-129">Luftutredning</span><span class="sxs-lookup"><span data-stu-id="16f6d-129">AirInvestigation</span></span>|<span data-ttu-id="16f6d-130">Automatiserade undersöknings- och svarshändelser, till exempel undersökningsinformation och relevanta artefakter från Office 365 Advanced Threat Protection Plan 2.</span><span class="sxs-lookup"><span data-stu-id="16f6d-130">Automated investigation and response events, such as investigation details and relevant artifacts from Office 365 Advanced Threat Protection Plan 2.</span></span>|


> [!IMPORTANT]
> <span data-ttu-id="16f6d-131">Du måste vara global administratör eller ha rollen säkerhetsadministratör tilldelad för Security & Compliance Center för att konfigurera SIEM-integrering med Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="16f6d-131">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Office 365 Advanced Threat Protection.</span></span><br/><span data-ttu-id="16f6d-132">Granskningsloggning måste vara aktiverat för din Microsoft 365-miljö.</span><span class="sxs-lookup"><span data-stu-id="16f6d-132">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="16f6d-133">Information om hur du får hjälp med detta finns i [Aktivera eller inaktivera granskningsloggsökning](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="16f6d-133">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="16f6d-134">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="16f6d-134">Related topics</span></span>

[<span data-ttu-id="16f6d-135">Office 365 undersökning av hot och svar</span><span class="sxs-lookup"><span data-stu-id="16f6d-135">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="16f6d-136">Automatisk undersökning och svar (AIR) i Office 365</span><span class="sxs-lookup"><span data-stu-id="16f6d-136">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)

[<span data-ttu-id="16f6d-137">Office 365 Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="16f6d-137">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

[<span data-ttu-id="16f6d-138">Smarta rapporter och insikter &amp; i Security Compliance Center</span><span class="sxs-lookup"><span data-stu-id="16f6d-138">Smart reports and insights in the Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="16f6d-139">Behörigheter i &amp; Säkerhetsefterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="16f6d-139">Permissions in the Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  
