---
title: Använda anpassade rapporteringslösningar med automatisk undersökning och svar i Office 365
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
description: Lär dig hur du integrerar automatiska undersökningar och svar från Office 365 med en anpassad rapporteringslösning eller tredjepartsrapportering.
ms.openlocfilehash: 3df69c9118b3170924a99a1787761b1bb07aadfa
ms.sourcegitcommit: 2f117a6fd27a097ca25afa933dd088b69d483974
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/20/2020
ms.locfileid: "42808166"
---
# <a name="use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="94776-104">Använda API:et för hanteringsaktivitet för Office 365 för anpassade rapporteringslösningar eller tredjepartsrapporteringslösningar</span><span class="sxs-lookup"><span data-stu-id="94776-104">Use the Office 365 Management Activity API for custom or third-party reporting solutions</span></span>

<span data-ttu-id="94776-105">Med [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)får du detaljerad information om [automatiska utredningar](air-view-investigation-results.md).</span><span class="sxs-lookup"><span data-stu-id="94776-105">With [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="94776-106">Vissa organisationer använder dock också en anpassad rapporteringslösning eller en tredjepartsrapporteringslösning.</span><span class="sxs-lookup"><span data-stu-id="94776-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="94776-107">Om din organisation vill integrera information om automatiska undersökningar med en sådan lösning kan du använda API:et för hanteringsaktivitet för Office 365.</span><span class="sxs-lookup"><span data-stu-id="94776-107">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="94776-108">Använd följande resurser för att ställa in detta:</span><span class="sxs-lookup"><span data-stu-id="94776-108">Use the following resources to set this up:</span></span>

|<span data-ttu-id="94776-109">Resurs</span><span class="sxs-lookup"><span data-stu-id="94776-109">Resource</span></span>  |<span data-ttu-id="94776-110">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="94776-110">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="94776-111">Översikt över Api:er för hantering av Office 365</span><span class="sxs-lookup"><span data-stu-id="94776-111">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)     |<span data-ttu-id="94776-112">Api:et för office 365-hanteringsaktivitet innehåller information om olika användar-, administratörs-, system- och principåtgärder och händelser från Office 365- och Azure Active Directory-aktivitetsloggar.</span><span class="sxs-lookup"><span data-stu-id="94776-112">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Office 365 and Azure Active Directory activity logs.</span></span>         |
|[<span data-ttu-id="94776-113">Komma igång med API:er för Hantering av Office 365</span><span class="sxs-lookup"><span data-stu-id="94776-113">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |<span data-ttu-id="94776-114">Office 365 Management API använder Azure AD för att tillhandahålla autentiseringstjänster för ditt program för att komma åt Office 365-data.</span><span class="sxs-lookup"><span data-stu-id="94776-114">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Office 365 data.</span></span> <span data-ttu-id="94776-115">Följ stegen i den här artikeln för att konfigurera detta.</span><span class="sxs-lookup"><span data-stu-id="94776-115">Follow the steps in this article to set this up.</span></span>          |
|[<span data-ttu-id="94776-116">API-referens för Office 365 Management-aktivitet</span><span class="sxs-lookup"><span data-stu-id="94776-116">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |<span data-ttu-id="94776-117">Du kan använda API:et för office 365-hanteringsaktivitet för att hämta information om användar-, administratörs-, system- och principåtgärder och händelser från Office 365- och Azure AD-aktivitetsloggar.</span><span class="sxs-lookup"><span data-stu-id="94776-117">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Office 365 and Azure AD activity logs.</span></span> <span data-ttu-id="94776-118">Läs den här artikeln om du vill veta mer om hur detta fungerar.</span><span class="sxs-lookup"><span data-stu-id="94776-118">Read this article to learn more about how this works.</span></span>        |
|[<span data-ttu-id="94776-119">API-schema för office 365-hanteringsaktivitet</span><span class="sxs-lookup"><span data-stu-id="94776-119">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |<span data-ttu-id="94776-120">Få en översikt över det [gemensamma schemat](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) och [Office 365 ATP- och hotundersöknings- och svarsschemat](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) om du vill veta mer om specifika typer av data som är tillgängliga via API:et för hanteringsaktivitet i Office 365.</span><span class="sxs-lookup"><span data-stu-id="94776-120">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>         |

## <a name="related-articles"></a><span data-ttu-id="94776-121">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="94776-121">Related articles</span></span>

- [<span data-ttu-id="94776-122">Avancerat hotskydd i Office 365</span><span class="sxs-lookup"><span data-stu-id="94776-122">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

- [<span data-ttu-id="94776-123">Läs mer om automatisk undersökning och svar i Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="94776-123">Learn about automated investigation and response in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)