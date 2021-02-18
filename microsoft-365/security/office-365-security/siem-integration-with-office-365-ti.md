---
title: SIEM-integrering med Microsoft Defender för Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Integrera organisationens SIEM-server med Microsoft Defender för Office 365 och relaterade hothändelser i API:t för hantering av aktivitetshantering för Office 365.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f637750a31b5034d2ee1110ab0070fa6abcda49b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290399"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a><span data-ttu-id="cb008-103">SIEM-integrering med Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="cb008-103">SIEM integration with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="cb008-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="cb008-104">**Applies to**</span></span>
- [<span data-ttu-id="cb008-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="cb008-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="cb008-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="cb008-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="cb008-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cb008-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="cb008-108">Om organisationen använder en säkerhetsinformations- och händelsehanteringsserver (SIEM) kan du integrera Microsoft Defender för Office 365 med din SIEM-server.</span><span class="sxs-lookup"><span data-stu-id="cb008-108">If your organization is using a security information and event management (SIEM) server, you can integrate Microsoft Defender for Office 365 with your SIEM server.</span></span> <span data-ttu-id="cb008-109">Du kan konfigurera den här integreringen med hjälp av API:t för hantering av [aktivitet i Office 365.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)</span><span class="sxs-lookup"><span data-stu-id="cb008-109">You can set up this integration by using the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

<span data-ttu-id="cb008-110">Med SIEM-integrering kan du visa information, till exempel skadlig kod eller phish som upptäckts av Microsoft Defender för Office 365, i dina SIEM-serverrapporter.</span><span class="sxs-lookup"><span data-stu-id="cb008-110">SIEM integration enables you to view information, such as malware or phish detected by Microsoft Defender for Office 365, in your SIEM server reports.</span></span>

- <span data-ttu-id="cb008-111">Ett exempel på SIEM-integrering med Microsoft Defender för Office 365 finns i Tech Community-bloggen: Effektivisera soc-programmet med Defender för [Office 365 och O365](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)Management API.</span><span class="sxs-lookup"><span data-stu-id="cb008-111">To see an example of SIEM integration with Microsoft Defender for Office 365, see [Tech Community blog: Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="cb008-112">Mer information om API:er för hantering av Office 365 finns i översikten över [API:er för hantering i Office 365.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)</span><span class="sxs-lookup"><span data-stu-id="cb008-112">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="cb008-113">Så här fungerar SIEM-integrering</span><span class="sxs-lookup"><span data-stu-id="cb008-113">How SIEM integration works</span></span>

<span data-ttu-id="cb008-114">API:t för hantering av aktivitet i Office 365 hämtar information om användar-, administratörs-, system- och principåtgärder och händelser från organisationens Microsoft 365- och Azure Active Directory-aktivitetsloggar.</span><span class="sxs-lookup"><span data-stu-id="cb008-114">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="cb008-115">Om din organisation har Microsoft Defender för Office 365 abonnemang 1 eller 2 eller Office 365 E5 kan du använda Microsoft Defender för [Office 365-schemat.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)</span><span class="sxs-lookup"><span data-stu-id="cb008-115">If your organization has Microsoft Defender for Office 365 Plan 1 or 2, or Office 365 E5, you can use the [Microsoft Defender for Office 365 schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>

<span data-ttu-id="cb008-116">Nyligen lades händelser från automatiserad undersökning och svarsfunktioner i Microsoft Defender för [Office 365-abonnemang 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) till i API:t för hanteringsaktivitet i Office 365.</span><span class="sxs-lookup"><span data-stu-id="cb008-116">Recently, events from automated investigation and response capabilities in [Microsoft Defender for Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="cb008-117">Förutom att inkludera data om grundläggande undersökningsinformation, till exempel ID, namn och status, innehåller API:t även högnivåinformation om undersökningsåtgärder och enheter.</span><span class="sxs-lookup"><span data-stu-id="cb008-117">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="cb008-118">SIEM-servern eller något annat liknande system omröstningar om arbetsbelastningen **för audit.general** för åtkomstidentifieringshändelser.</span><span class="sxs-lookup"><span data-stu-id="cb008-118">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="cb008-119">Mer information finns i Komma igång med API:er för hantering av [Office 365.](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)</span><span class="sxs-lookup"><span data-stu-id="cb008-119">To learn more, see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="cb008-120">Uppräkning: AuditLogRecordType – Typ: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="cb008-120">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="cb008-121">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="cb008-121">AuditLogRecordType</span></span>

<span data-ttu-id="cb008-122">I följande tabell sammanfattas värdena för **AuditLogRecordType** som är relevanta för Microsoft Defender för Office 365-händelser:</span><span class="sxs-lookup"><span data-stu-id="cb008-122">The following table summarizes the values of **AuditLogRecordType** that are relevant for Microsoft Defender for Office 365 events:</span></span>

|<span data-ttu-id="cb008-123">Value</span><span class="sxs-lookup"><span data-stu-id="cb008-123">Value</span></span>|<span data-ttu-id="cb008-124">Medlemsnamn</span><span class="sxs-lookup"><span data-stu-id="cb008-124">Member name</span></span>|<span data-ttu-id="cb008-125">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="cb008-125">Description</span></span>|
|---|---|---|
|<span data-ttu-id="cb008-126">28</span><span class="sxs-lookup"><span data-stu-id="cb008-126">28</span></span>|<span data-ttu-id="cb008-127">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="cb008-127">ThreatIntelligence</span></span>|<span data-ttu-id="cb008-128">Nätfiske- och skadlig kodhändelser från Exchange Online Protection och Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="cb008-128">Phishing and malware events from Exchange Online Protection and Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="cb008-129">41</span><span class="sxs-lookup"><span data-stu-id="cb008-129">41</span></span>|<span data-ttu-id="cb008-130">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="cb008-130">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="cb008-131">Tid för blockering av säkra länkar och blockera åsidosättningshändelser från Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="cb008-131">Safe Links time-of-block and block override events from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="cb008-132">47</span><span class="sxs-lookup"><span data-stu-id="cb008-132">47</span></span>|<span data-ttu-id="cb008-133">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="cb008-133">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="cb008-134">Nätfiske- och skadlig kodhändelser för filer i SharePoint Online, OneDrive för företag och Microsoft Teams, från Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="cb008-134">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="cb008-135">64</span><span class="sxs-lookup"><span data-stu-id="cb008-135">64</span></span>|<span data-ttu-id="cb008-136">AirInvestigation</span><span class="sxs-lookup"><span data-stu-id="cb008-136">AirInvestigation</span></span>|<span data-ttu-id="cb008-137">Automatiserad undersökning och svarshändelser, till exempel undersökningsinformation och relevanta artefakter, från Microsoft Defender för Office 365 abonnemang 2.</span><span class="sxs-lookup"><span data-stu-id="cb008-137">Automated investigation and response events, such as investigation details and relevant artifacts, from Microsoft Defender for Office 365 Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="cb008-138">Du måste vara global administratör eller ha säkerhetsadministratörsrollen tilldelad till Säkerhets- och efterlevnadscenter & för att konfigurera SIEM-integrering med Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="cb008-138">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Microsoft Defender for Office 365.</span></span>
>
> <span data-ttu-id="cb008-139">Granskningsloggning måste aktiveras i Microsoft 365-miljön.</span><span class="sxs-lookup"><span data-stu-id="cb008-139">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="cb008-140">Mer information finns i Aktivera eller [inaktivera granskningsloggsökning.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="cb008-140">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cb008-141">Se även</span><span class="sxs-lookup"><span data-stu-id="cb008-141">See also</span></span>

[<span data-ttu-id="cb008-142">Office 365 undersökning av hot och svar</span><span class="sxs-lookup"><span data-stu-id="cb008-142">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="cb008-143">Automatiserad undersökning och svar (AIR) i Office 365</span><span class="sxs-lookup"><span data-stu-id="cb008-143">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)

