---
title: SIEM-integrering med Microsoft Defender för Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Integrera organisationens SIEM-server med Microsoft Defender för Office 365 och relaterade hothändelser i OFFICE 365 Activity Management API.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f3d6bbacb4a64060ecd03cbb28eee3256f41827e
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929785"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a><span data-ttu-id="16d3b-103">SIEM-integrering med Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="16d3b-103">SIEM integration with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="16d3b-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="16d3b-104">**Applies to**</span></span>
- [<span data-ttu-id="16d3b-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="16d3b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="16d3b-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="16d3b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="16d3b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="16d3b-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="16d3b-108">Om organisationen använder en säkerhetsinformations- och händelsehanteringsserver (SIEM) kan du integrera Microsoft Defender för Office 365 med SIEM-servern.</span><span class="sxs-lookup"><span data-stu-id="16d3b-108">If your organization is using a security information and event management (SIEM) server, you can integrate Microsoft Defender for Office 365 with your SIEM server.</span></span> <span data-ttu-id="16d3b-109">Du kan konfigurera den här integreringen med hjälp [Office 365 API för hanteringsaktivitet.](/office/office-365-management-api/office-365-management-activity-api-reference)</span><span class="sxs-lookup"><span data-stu-id="16d3b-109">You can set up this integration by using the [Office 365 Activity Management API](/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

<span data-ttu-id="16d3b-110">Med SIEM-integrering kan du visa information, t.ex. skadlig kod eller phish som upptäckts av Microsoft Defender för Office 365, i dina SIEM-serverrapporter.</span><span class="sxs-lookup"><span data-stu-id="16d3b-110">SIEM integration enables you to view information, such as malware or phish detected by Microsoft Defender for Office 365, in your SIEM server reports.</span></span>

- <span data-ttu-id="16d3b-111">Ett exempel på SIEM-integrering med Microsoft Defender för Office 365 finns i [Tech Community-bloggen:](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)Öka effektiviteten i SOC med Defender för Office 365 och O365 Management API.</span><span class="sxs-lookup"><span data-stu-id="16d3b-111">To see an example of SIEM integration with Microsoft Defender for Office 365, see [Tech Community blog: Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="16d3b-112">Mer information om hur du Office 365 API:er för hantering finns i Office 365 [över API:er för hantering.](/office/office-365-management-api/office-365-management-apis-overview)</span><span class="sxs-lookup"><span data-stu-id="16d3b-112">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="16d3b-113">Så här fungerar SIEM-integrering</span><span class="sxs-lookup"><span data-stu-id="16d3b-113">How SIEM integration works</span></span>

<span data-ttu-id="16d3b-114">Med API Office 365 Activity Management hämtas information om användar-, administratörs-, system- och principåtgärder och -händelser från organisationens Microsoft 365 och Azure Active Directory aktivitetsloggar.</span><span class="sxs-lookup"><span data-stu-id="16d3b-114">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="16d3b-115">Om din organisation har Microsoft Defender för Office 365 abonnemang 1 eller 2 eller Office 365 E5 kan du använda [Microsoft Defender för Office 365 schema.](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)</span><span class="sxs-lookup"><span data-stu-id="16d3b-115">If your organization has Microsoft Defender for Office 365 Plan 1 or 2, or Office 365 E5, you can use the [Microsoft Defender for Office 365 schema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>

<span data-ttu-id="16d3b-116">Nyligen lades händelser från automatiserad undersökning och svarsfunktioner i [Microsoft Defender för Office 365 abonnemang 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) till i API:t för hanteringsaktivitet Office 365 hanteringsaktivitet.</span><span class="sxs-lookup"><span data-stu-id="16d3b-116">Recently, events from automated investigation and response capabilities in [Microsoft Defender for Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="16d3b-117">Förutom att inkludera data om grundläggande undersökningsinformation som ID, namn och status innehåller API:et även hög nivå-information om undersökningsåtgärder och enheter.</span><span class="sxs-lookup"><span data-stu-id="16d3b-117">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="16d3b-118">SIEM-servern eller något annat liknande system avsöker arbetsbelastningen **audit.general** för att komma åt identifieringshändelser.</span><span class="sxs-lookup"><span data-stu-id="16d3b-118">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="16d3b-119">Mer information finns i Komma [igång med att Office 365 API:er för hantering.](/office/office-365-management-api/get-started-with-office-365-management-apis)</span><span class="sxs-lookup"><span data-stu-id="16d3b-119">To learn more, see [Get started with Office 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="16d3b-120">Uppräkning: AuditLogRecordType – Typ: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="16d3b-120">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="16d3b-121">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="16d3b-121">AuditLogRecordType</span></span>

<span data-ttu-id="16d3b-122">I följande tabell sammanfattas värdena för **AuditLogRecordType** som är relevanta för Microsoft Defender för Office 365 händelser:</span><span class="sxs-lookup"><span data-stu-id="16d3b-122">The following table summarizes the values of **AuditLogRecordType** that are relevant for Microsoft Defender for Office 365 events:</span></span>

|<span data-ttu-id="16d3b-123">Värde</span><span class="sxs-lookup"><span data-stu-id="16d3b-123">Value</span></span>|<span data-ttu-id="16d3b-124">Medlemsnamn</span><span class="sxs-lookup"><span data-stu-id="16d3b-124">Member name</span></span>|<span data-ttu-id="16d3b-125">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="16d3b-125">Description</span></span>|
|---|---|---|
|<span data-ttu-id="16d3b-126">28</span><span class="sxs-lookup"><span data-stu-id="16d3b-126">28</span></span>|<span data-ttu-id="16d3b-127">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="16d3b-127">ThreatIntelligence</span></span>|<span data-ttu-id="16d3b-128">Nätfiske- och skadlig programvara från Exchange Online Protection och Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="16d3b-128">Phishing and malware events from Exchange Online Protection and Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="16d3b-129">41</span><span class="sxs-lookup"><span data-stu-id="16d3b-129">41</span></span>|<span data-ttu-id="16d3b-130">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="16d3b-130">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="16d3b-131">Valv Länkar tid för blockering och blockering av händelser från Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="16d3b-131">Safe Links time-of-block and block override events from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="16d3b-132">47</span><span class="sxs-lookup"><span data-stu-id="16d3b-132">47</span></span>|<span data-ttu-id="16d3b-133">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="16d3b-133">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="16d3b-134">Nätfiske- och skadlig kod för filer i SharePoint Online, OneDrive för företag och Microsoft Teams från Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="16d3b-134">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="16d3b-135">64</span><span class="sxs-lookup"><span data-stu-id="16d3b-135">64</span></span>|<span data-ttu-id="16d3b-136">AirInvestigation</span><span class="sxs-lookup"><span data-stu-id="16d3b-136">AirInvestigation</span></span>|<span data-ttu-id="16d3b-137">Automatisk undersökning och svarshändelser, till exempel undersökningsinformation och relevanta artefakter, från Microsoft Defender för Office 365 abonnemang 2.</span><span class="sxs-lookup"><span data-stu-id="16d3b-137">Automated investigation and response events, such as investigation details and relevant artifacts, from Microsoft Defender for Office 365 Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="16d3b-138">Du måste vara global administratör eller ha säkerhetsadministratörsrollen tilldelad till Microsoft 365 Defender-portalen för att konfigurera SIEM-integrering med Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="16d3b-138">You must be a global administrator or have the security administrator role assigned for the Microsoft 365 Defender portal to set up SIEM integration with Microsoft Defender for Office 365.</span></span>
>
> <span data-ttu-id="16d3b-139">Granskningsloggning måste vara aktiverad i Microsoft 365 miljö.</span><span class="sxs-lookup"><span data-stu-id="16d3b-139">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="16d3b-140">Om du behöver hjälp med detta kan du [gå till Aktivera eller inaktivera granskningsloggsökning.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="16d3b-140">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="16d3b-141">Se även</span><span class="sxs-lookup"><span data-stu-id="16d3b-141">See also</span></span>

[<span data-ttu-id="16d3b-142">Office 365 undersökning av hot och svar</span><span class="sxs-lookup"><span data-stu-id="16d3b-142">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="16d3b-143">Automatisk undersökning och svar (AIR) i Office 365</span><span class="sxs-lookup"><span data-stu-id="16d3b-143">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)