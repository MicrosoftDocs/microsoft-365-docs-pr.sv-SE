---
title: Anpassade rapportlösningar med automatiserad undersökning och svar
keywords: SIEM, API, AIR, autoIR, ATP, automatisk undersökning, integrering, anpassad rapport
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Lär dig att integrera automatisk undersökning och svar med en anpassad eller tredje parts rapporteringslösning.
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 13782a8e0a8c691a66f214d3f9f03ef9cad4da1f
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287143"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a><span data-ttu-id="98d9b-104">Anpassade rapportlösningar eller rapportlösningar från tredje part för Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="98d9b-104">Custom or third-party reporting solutions for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="98d9b-105">Med [Microsoft Defender för Office 365](office-365-atp.md)får du detaljerad information om automatiska [undersökningar.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="98d9b-105">With [Microsoft Defender for Office 365](office-365-atp.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="98d9b-106">Men vissa organisationer använder också en anpassad lösning eller en rapportlösning från tredje part.</span><span class="sxs-lookup"><span data-stu-id="98d9b-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="98d9b-107">Om din organisation vill integrera information om [automatiserade undersökningar](office-365-air.md) med en sådan lösning kan du använda API:t för hanteringsaktivitet i Office 365.</span><span class="sxs-lookup"><span data-stu-id="98d9b-107">If your organization wants to integrate information about [automated investigations](office-365-air.md) with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="98d9b-108">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="98d9b-108">**Applies to**</span></span>
- [<span data-ttu-id="98d9b-109">Microsoft Defender för Office 365 abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="98d9b-109">Microsoft Defender for Office 365 plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="98d9b-110">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="98d9b-110">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="98d9b-111">Med [Microsoft Defender för Office 365](office-365-atp.md)får du detaljerad information om automatiska [undersökningar.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="98d9b-111">With [Microsoft Defender for Office 365](office-365-atp.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="98d9b-112">Men vissa organisationer använder också en anpassad lösning eller en rapporteringslösning från tredje part.</span><span class="sxs-lookup"><span data-stu-id="98d9b-112">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="98d9b-113">Om din organisation vill integrera information om automatiserade undersökningar med en sådan lösning kan du använda API:t för hanteringsaktivitet i Office 365.</span><span class="sxs-lookup"><span data-stu-id="98d9b-113">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

|<span data-ttu-id="98d9b-114">Resurs</span><span class="sxs-lookup"><span data-stu-id="98d9b-114">Resource</span></span>|<span data-ttu-id="98d9b-115">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="98d9b-115">Description</span></span>|
|:---|:---|
|[<span data-ttu-id="98d9b-116">Översikt över API:er för hantering av Office 365</span><span class="sxs-lookup"><span data-stu-id="98d9b-116">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|<span data-ttu-id="98d9b-117">API:t för hanteringsaktivitet i Office 365 innehåller information om olika användar-, administratörs-, system- och principåtgärder och händelser från Microsoft 365- och Azure Active Directory-aktivitetsloggar.</span><span class="sxs-lookup"><span data-stu-id="98d9b-117">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="98d9b-118">Komma igång med API:er för hantering av Office 365</span><span class="sxs-lookup"><span data-stu-id="98d9b-118">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="98d9b-119">Office 365 Management API använder Azure AD för att tillhandahålla autentiseringstjänster för ditt program för att få åtkomst till Microsoft 365-data.</span><span class="sxs-lookup"><span data-stu-id="98d9b-119">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="98d9b-120">Följ anvisningarna i den här artikeln för att konfigurera det här.</span><span class="sxs-lookup"><span data-stu-id="98d9b-120">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="98d9b-121">API för hanteringsaktivitet i Office 365, referens</span><span class="sxs-lookup"><span data-stu-id="98d9b-121">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="98d9b-122">Du kan använda API:t för hanteringsaktivitet i Office 365 för att hämta information om användar-, administratörs-, system- och principåtgärder och händelser från aktivitetsloggarna för Microsoft 365 och Azure AD.</span><span class="sxs-lookup"><span data-stu-id="98d9b-122">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="98d9b-123">Läs den här artikeln om du vill veta mer om hur det fungerar.</span><span class="sxs-lookup"><span data-stu-id="98d9b-123">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="98d9b-124">API för hanteringsaktivitet i Office 365. schema</span><span class="sxs-lookup"><span data-stu-id="98d9b-124">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="98d9b-125">Få en översikt över det vanliga [schemat](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) och Defender för [Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) samt hotundersöknings- och svarsschemat om du vill lära dig mer om specifika typer av data som är tillgängliga via API:t för hanteringsaktivitet i Office 365.</span><span class="sxs-lookup"><span data-stu-id="98d9b-125">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Defender for Office 365 and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="98d9b-126">Se även</span><span class="sxs-lookup"><span data-stu-id="98d9b-126">See also</span></span>

- [<span data-ttu-id="98d9b-127">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="98d9b-127">Microsoft Defender for Office 365</span></span>](office-365-atp.md)
- [<span data-ttu-id="98d9b-128">Automatiserad undersökning och svar i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="98d9b-128">Automated investigation and response in Microsoft 365 Defender</span></span>](../mtp/mtp-autoir.md)
