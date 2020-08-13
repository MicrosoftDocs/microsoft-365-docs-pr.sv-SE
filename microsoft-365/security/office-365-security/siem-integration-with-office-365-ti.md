---
title: SIEM integrering med avancerat skydd
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
description: Integrera din organisations SIEM-server med Office 365 Avancerat skydd och relaterade hot händelser i Office 365 Activity Management API.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b3ed2efd2b59397853623ffcec93e8011793ab43
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656605"
---
# <a name="siem-integration-with-advanced-threat-protection"></a><span data-ttu-id="317d2-103">SIEM integrering med avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="317d2-103">SIEM integration with Advanced Threat Protection</span></span>

<span data-ttu-id="317d2-104">Om din organisation använder en säkerhets tillbuds Server (SIEM) kan du integrera Office 365 Avancerat skydd med din SIEM-Server.</span><span class="sxs-lookup"><span data-stu-id="317d2-104">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Advanced Threat Protection with your SIEM server.</span></span> <span data-ttu-id="317d2-105">SIEM integrering gör att du kan visa information, till exempel skadlig program vara eller Phish som identifieras av Office 365 Avancerat skydd, i SIEM Server-rapporter.</span><span class="sxs-lookup"><span data-stu-id="317d2-105">SIEM integration enables you to view information, such as malware or phish detected by Office 365 Advanced Protection, in your SIEM server reports.</span></span> <span data-ttu-id="317d2-106">Om du vill ställa in SIEM-integrering använder du [API för aktivitets hantering i Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span><span class="sxs-lookup"><span data-stu-id="317d2-106">To set up SIEM integration, you use the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

<span data-ttu-id="317d2-107">API: t för aktivitets hantering i Office 365 hämtar information om åtgärder och händelser för användare, administratörer, system och principer från organisationens Microsoft 365 för företag-och Azure Active Directory-aktivitets loggar.</span><span class="sxs-lookup"><span data-stu-id="317d2-107">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 for business and Azure Active Directory activity logs.</span></span> <span data-ttu-id="317d2-108">Det avancerade [hotet Protection-schemat för office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) fungerar med avancerat skydd, så om din organisation har Office 365-prenumerationen för avancerat skydd 1 eller abonnemang 2 eller Office 365 E5 kan du fortfarande använda samma API för din Siem Server-integrering.</span><span class="sxs-lookup"><span data-stu-id="317d2-108">The [Office 365 Advanced Threat Protection schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) works with Advanced Threat Protection, so if your organization has the Office 365 Advanced Threat Protection Plan 1 or Plan 2 or Office 365 E5, you can still use that same API for your SIEM server integration.</span></span>

<span data-ttu-id="317d2-109">Som en del av de senaste uppdateringarna har vi också lagt till händelser från automatiserade undersökningar och svars funktioner i Office 365 ATP-abonnemang 2 i administrations aktivitets API för Office 365.</span><span class="sxs-lookup"><span data-stu-id="317d2-109">As part of our recent updates, we have also added events from automated investigation and response capabilities in Office 365 ATP Plan 2 within the Office 365 Management Activity API.</span></span> <span data-ttu-id="317d2-110">Förutom att inkludera uppgifter om grundläggande undersöknings uppgifter, till exempel ID, namn och status, innehåller den också information om undersöknings åtgärder och-enheter.</span><span class="sxs-lookup"><span data-stu-id="317d2-110">In addition to including data about core investigation details such as ID, name and status, it also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="317d2-111">SIEM-servern eller liknande system ska **Granska granskningen. allmän** arbets belastning för att få åtkomst till identifierings händelser.</span><span class="sxs-lookup"><span data-stu-id="317d2-111">The SIEM server or other similar system should poll the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="317d2-112">Mer information finns i [komma igång med Office 365 Management API: er](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="317d2-112">To learn more see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> <span data-ttu-id="317d2-113">Dessutom är följande värden för **AuditLogRecordType** relevanta för Office 365 ATP-händelser:</span><span class="sxs-lookup"><span data-stu-id="317d2-113">In addition, the following values of **AuditLogRecordType** are relevant for Office 365 ATP events:</span></span>

### <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="317d2-114">Enum: AuditLogRecordType-Type: EDM. Int32</span><span class="sxs-lookup"><span data-stu-id="317d2-114">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

#### <a name="auditlogrecordtype"></a><span data-ttu-id="317d2-115">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="317d2-115">AuditLogRecordType</span></span>

****

|<span data-ttu-id="317d2-116">Value</span><span class="sxs-lookup"><span data-stu-id="317d2-116">Value</span></span>|<span data-ttu-id="317d2-117">Medlems namn</span><span class="sxs-lookup"><span data-stu-id="317d2-117">Member name</span></span>|<span data-ttu-id="317d2-118">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="317d2-118">Description</span></span>|
|---|---|---|
|<span data-ttu-id="317d2-119">28</span><span class="sxs-lookup"><span data-stu-id="317d2-119">28</span></span>|<span data-ttu-id="317d2-120">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="317d2-120">ThreatIntelligence</span></span>|<span data-ttu-id="317d2-121">Phishing-och malware-händelser från Exchange Online Protection och Office 365 Avancerat skydd.</span><span class="sxs-lookup"><span data-stu-id="317d2-121">Phishing and malware events from Exchange Online Protection and Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="317d2-122">41</span><span class="sxs-lookup"><span data-stu-id="317d2-122">41</span></span>|<span data-ttu-id="317d2-123">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="317d2-123">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="317d2-124">ATP-säkra länkar tids-för-blockera och blockera händelser från Office 365 Avancerat skydd.</span><span class="sxs-lookup"><span data-stu-id="317d2-124">ATP Safe Links time-of-block and block override events from Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="317d2-125">47</span><span class="sxs-lookup"><span data-stu-id="317d2-125">47</span></span>|<span data-ttu-id="317d2-126">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="317d2-126">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="317d2-127">Phishing-och malware-händelser för filer i SharePoint Online, OneDrive för företag och Microsoft Teams från Office 365 Avancerat skydd.</span><span class="sxs-lookup"><span data-stu-id="317d2-127">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams from Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="317d2-128">64</span><span class="sxs-lookup"><span data-stu-id="317d2-128">64</span></span>|<span data-ttu-id="317d2-129">Luftprövning</span><span class="sxs-lookup"><span data-stu-id="317d2-129">AirInvestigation</span></span>|<span data-ttu-id="317d2-130">Automatiserade undersökningar och svars händelser, till exempel information om undersökningar och relevanta artefakter från Office 365 Avancerat skydds abonnemang 2.</span><span class="sxs-lookup"><span data-stu-id="317d2-130">Automated investigation and response events, such as investigation details and relevant artifacts from Office 365 Advanced Threat Protection Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="317d2-131">Du måste vara global administratör eller ha rollen som säkerhets administratör tilldelad för säkerhets & efterlevnad för att konfigurera SIEM-integrering med Office 365 Avancerat skydd.</span><span class="sxs-lookup"><span data-stu-id="317d2-131">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Office 365 Advanced Threat Protection.</span></span><br/><span data-ttu-id="317d2-132">Gransknings loggning måste vara aktiverat för din Microsoft 365-miljö.</span><span class="sxs-lookup"><span data-stu-id="317d2-132">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="317d2-133">Om du behöver hjälp kan du läsa [Aktivera och inaktivera gransknings loggs ökning](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="317d2-133">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="317d2-134">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="317d2-134">Related topics</span></span>

[<span data-ttu-id="317d2-135">Office 365 undersökning av hot och svar</span><span class="sxs-lookup"><span data-stu-id="317d2-135">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="317d2-136">Automatisk undersökning och svar (AIR) i Office 365</span><span class="sxs-lookup"><span data-stu-id="317d2-136">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)

[<span data-ttu-id="317d2-137">Office 365 Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="317d2-137">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

[<span data-ttu-id="317d2-138">Smarta rapporter och insikter i säkerhetsrelaterade &amp; Center</span><span class="sxs-lookup"><span data-stu-id="317d2-138">Smart reports and insights in the Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="317d2-139">Behörigheter i säkerhetsrelaterade &amp; Center</span><span class="sxs-lookup"><span data-stu-id="317d2-139">Permissions in the Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
