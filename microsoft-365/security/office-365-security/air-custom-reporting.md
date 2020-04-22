---
title: Använda anpassade rapporteringslösningar med automatiserad undersökning och svar
keywords: AIR, autoIR, ATP, automatiserad, utredning, svar, sanering, hot, avancerad, hot, skydd
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Lär dig hur du integrerar automatisk undersökning och svar med en anpassad rapporteringslösning eller tredjepartsrapportering.
ms.openlocfilehash: 4bd53de9a880fc774814588ed84dce2284535922
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634724"
---
# <a name="use-the-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="f6a7f-104">Använda API:et för hanteringsaktivitet för anpassade rapporteringslösningar eller tredjepartsrapporteringslösningar</span><span class="sxs-lookup"><span data-stu-id="f6a7f-104">Use the Management Activity API for custom or third-party reporting solutions</span></span>

<span data-ttu-id="f6a7f-105">Med [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)får du detaljerad information om [automatiska utredningar](air-view-investigation-results.md).</span><span class="sxs-lookup"><span data-stu-id="f6a7f-105">With [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="f6a7f-106">Vissa organisationer använder dock också en anpassad rapporteringslösning eller en tredjepartsrapporteringslösning.</span><span class="sxs-lookup"><span data-stu-id="f6a7f-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="f6a7f-107">Om din organisation vill integrera information om automatiska undersökningar med en sådan lösning kan du använda API:et för hanteringsaktivitet för Office 365.</span><span class="sxs-lookup"><span data-stu-id="f6a7f-107">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="f6a7f-108">Använd följande resurser för att ställa in detta:</span><span class="sxs-lookup"><span data-stu-id="f6a7f-108">Use the following resources to set this up:</span></span>

|<span data-ttu-id="f6a7f-109">Resurs</span><span class="sxs-lookup"><span data-stu-id="f6a7f-109">Resource</span></span>  |<span data-ttu-id="f6a7f-110">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="f6a7f-110">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="f6a7f-111">Översikt över Api:er för hantering av Office 365</span><span class="sxs-lookup"><span data-stu-id="f6a7f-111">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)     |<span data-ttu-id="f6a7f-112">Api:et för office 365-hanteringsaktivitet innehåller information om olika användar-, administratörs-, system- och principåtgärder och händelser från Microsoft 365- och Azure Active Directory-aktivitetsloggar.</span><span class="sxs-lookup"><span data-stu-id="f6a7f-112">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>         |
|[<span data-ttu-id="f6a7f-113">Komma igång med API:er för Hantering av Office 365</span><span class="sxs-lookup"><span data-stu-id="f6a7f-113">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |<span data-ttu-id="f6a7f-114">Office 365 Management API använder Azure AD för att tillhandahålla autentiseringstjänster för ditt program för att komma åt Microsoft 365-data.</span><span class="sxs-lookup"><span data-stu-id="f6a7f-114">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="f6a7f-115">Följ stegen i den här artikeln för att konfigurera detta.</span><span class="sxs-lookup"><span data-stu-id="f6a7f-115">Follow the steps in this article to set this up.</span></span>          |
|[<span data-ttu-id="f6a7f-116">API-referens för Office 365 Management-aktivitet</span><span class="sxs-lookup"><span data-stu-id="f6a7f-116">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |<span data-ttu-id="f6a7f-117">Du kan använda API:et för office 365-hanteringsaktivitet för att hämta information om användar-, administratörs-, system- och principåtgärder och händelser från Microsoft 365- och Azure AD-aktivitetsloggar.</span><span class="sxs-lookup"><span data-stu-id="f6a7f-117">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="f6a7f-118">Läs den här artikeln om du vill veta mer om hur detta fungerar.</span><span class="sxs-lookup"><span data-stu-id="f6a7f-118">Read this article to learn more about how this works.</span></span>        |
|[<span data-ttu-id="f6a7f-119">API-schema för office 365-hanteringsaktivitet</span><span class="sxs-lookup"><span data-stu-id="f6a7f-119">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |<span data-ttu-id="f6a7f-120">Få en översikt över det [gemensamma schemat](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) och [Office 365 ATP- och hotundersöknings- och svarsschemat](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) om du vill veta mer om specifika typer av data som är tillgängliga via API:et för hanteringsaktivitet i Office 365.</span><span class="sxs-lookup"><span data-stu-id="f6a7f-120">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>         |

## <a name="related-articles"></a><span data-ttu-id="f6a7f-121">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="f6a7f-121">Related articles</span></span>

- [<span data-ttu-id="f6a7f-122">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="f6a7f-122">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

- [<span data-ttu-id="f6a7f-123">Läs mer om automatisk undersökning och svar i Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f6a7f-123">Learn about automated investigation and response in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)