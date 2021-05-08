---
title: Anpassade rapportlösningar med automatiserad undersökning och svar
keywords: SIEM, API, AIR, autoIR, Microsoft Defender för Slutpunkt, automatiserad undersökning, integrering, anpassad rapport
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
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
ms.openlocfilehash: 6ed752f9514f1d2c8cadeb7cbbd1d7b9311b1b5f
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275018"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a><span data-ttu-id="388ce-104">Anpassade eller tredjepartsrapporteringslösningar för Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="388ce-104">Custom or third-party reporting solutions for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="388ce-105">Med [Microsoft Defender för Office 365](defender-for-office-365.md)får du detaljerad information om automatiska [undersökningar](air-view-investigation-results.md).</span><span class="sxs-lookup"><span data-stu-id="388ce-105">With [Microsoft Defender for Office 365](defender-for-office-365.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="388ce-106">Men vissa organisationer använder även en anpassad rapportlösning eller rapporteringslösning från tredje part.</span><span class="sxs-lookup"><span data-stu-id="388ce-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="388ce-107">Om din organisation vill integrera information om [automatiserade undersökningar](office-365-air.md) med en sådan lösning kan du använda API:t Office 365 för hanteringsaktivitet.</span><span class="sxs-lookup"><span data-stu-id="388ce-107">If your organization wants to integrate information about [automated investigations](office-365-air.md) with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="388ce-108">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="388ce-108">**Applies to**</span></span>
- [<span data-ttu-id="388ce-109">Microsoft Defender för Office 365 abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="388ce-109">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="388ce-110">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="388ce-110">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="388ce-111">Med [Microsoft Defender för Office 365](defender-for-office-365.md)får du detaljerad information om automatiska [undersökningar](air-view-investigation-results.md).</span><span class="sxs-lookup"><span data-stu-id="388ce-111">With [Microsoft Defender for Office 365](defender-for-office-365.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="388ce-112">Men vissa organisationer använder även en anpassad rapportlösning eller rapporteringslösning från tredje part.</span><span class="sxs-lookup"><span data-stu-id="388ce-112">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="388ce-113">Om din organisation vill integrera information om automatiserade undersökningar med en sådan lösning kan du använda API:t för Office 365 hanteringsaktivitet.</span><span class="sxs-lookup"><span data-stu-id="388ce-113">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

|<span data-ttu-id="388ce-114">Resurs</span><span class="sxs-lookup"><span data-stu-id="388ce-114">Resource</span></span>|<span data-ttu-id="388ce-115">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="388ce-115">Description</span></span>|
|:---|:---|
|[<span data-ttu-id="388ce-116">Office 365 Översikt över API:er för hantering</span><span class="sxs-lookup"><span data-stu-id="388ce-116">Office 365 Management APIs overview</span></span>](/office/office-365-management-api/office-365-management-apis-overview)|<span data-ttu-id="388ce-117">API:Office 365 för hanteringsaktivitet innehåller information om olika användar-, administratörs-, system- och principåtgärder och händelser från Microsoft 365 och Azure Active Directory aktivitetsloggar.</span><span class="sxs-lookup"><span data-stu-id="388ce-117">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="388ce-118">Komma igång Office 365 API:er för hantering</span><span class="sxs-lookup"><span data-stu-id="388ce-118">Get started with Office 365 Management APIs</span></span>](/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="388ce-119">I Office 365 Management API används Azure AD för att tillhandahålla autentiseringstjänster för ditt program för åtkomst Microsoft 365 data.</span><span class="sxs-lookup"><span data-stu-id="388ce-119">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="388ce-120">Följ stegen i den här artikeln för att konfigurera detta.</span><span class="sxs-lookup"><span data-stu-id="388ce-120">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="388ce-121">API för hanteringsaktivitet i Office 365, referens</span><span class="sxs-lookup"><span data-stu-id="388ce-121">Office 365 Management Activity API reference</span></span>](/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="388ce-122">Du kan använda API:t Office 365 Management Activity för att hämta information om användar-, administratörs-, system- och principåtgärder och händelser från Microsoft 365- och Azure AD-aktivitetsloggar.</span><span class="sxs-lookup"><span data-stu-id="388ce-122">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="388ce-123">Läs den här artikeln om du vill veta mer om hur det fungerar.</span><span class="sxs-lookup"><span data-stu-id="388ce-123">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="388ce-124">API för hanteringsaktivitet i Office 365. schema</span><span class="sxs-lookup"><span data-stu-id="388ce-124">Office 365 Management Activity API schema</span></span>](/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="388ce-125">Få en översikt över [Common-schemat](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) och Defender för Office 365 och threat [investigation and response schema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) om du vill veta mer om specifika typer av data som är tillgängliga via API:t för hanteringsaktivitet Office 365 säkerhetshanteringsaktivitet.</span><span class="sxs-lookup"><span data-stu-id="388ce-125">Get an overview of the [Common schema](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Defender for Office 365 and threat investigation and response schema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="388ce-126">Se även</span><span class="sxs-lookup"><span data-stu-id="388ce-126">See also</span></span>

- [<span data-ttu-id="388ce-127">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="388ce-127">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="388ce-128">Automatiserad undersökning och svar i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="388ce-128">Automated investigation and response in Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/m365d-autoir)
