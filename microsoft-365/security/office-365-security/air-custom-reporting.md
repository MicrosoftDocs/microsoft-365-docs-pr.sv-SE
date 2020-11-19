---
title: Använda anpassade rapporterings lösningar med automatiserad undersökning och svar
keywords: SIEM, API, AIR, autoIR, ATP, automatisk undersökning, integrering, anpassad rapport
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
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Lär dig hur du integrerar automatisk undersökning och svar med en egen rapporterings lösning eller tredje part.
ms.date: 09/29/2020
ms.custom:
- air
ms.openlocfilehash: 7b0b0570624b2e0dd40d40b178951a747698afe2
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357473"
---
# <a name="use-the-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="162ad-104">Använda API för hanterings aktivitet för egna eller tredje parts rapporterings lösningar</span><span class="sxs-lookup"><span data-stu-id="162ad-104">Use the Management Activity API for custom or third-party reporting solutions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="162ad-105">Med [Microsoft Defender för Office 365](office-365-atp.md)får du [detaljerad information om automatiserade utredningar](air-view-investigation-results.md).</span><span class="sxs-lookup"><span data-stu-id="162ad-105">With [Microsoft Defender for Office 365](office-365-atp.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="162ad-106">I vissa organisationer används emellertid en egen rapporterings lösning.</span><span class="sxs-lookup"><span data-stu-id="162ad-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="162ad-107">Om din organisation vill integrera information om automatiserade undersökningar med en sådan lösning kan du använda API för hanterings aktivitet i Office 365.</span><span class="sxs-lookup"><span data-stu-id="162ad-107">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="162ad-108">Använd följande resurser för att konfigurera detta:</span><span class="sxs-lookup"><span data-stu-id="162ad-108">Use the following resources to set this up:</span></span>

****

|<span data-ttu-id="162ad-109">Resurspool</span><span class="sxs-lookup"><span data-stu-id="162ad-109">Resource</span></span>|<span data-ttu-id="162ad-110">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="162ad-110">Description</span></span>|
|---|---|
|[<span data-ttu-id="162ad-111">Översikt över API för hantering av Office 365</span><span class="sxs-lookup"><span data-stu-id="162ad-111">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|<span data-ttu-id="162ad-112">API för hanterings aktivitet i Office 365 ger information om olika åtgärder för användare, administratörer, system och händelser från Microsoft 365-och Azure Active Directory-aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="162ad-112">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="162ad-113">Komma igång med API för hantering av Office 365</span><span class="sxs-lookup"><span data-stu-id="162ad-113">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="162ad-114">Office 365 Management API använder Azure AD för att tillhandahålla autentiseringstjänster för ditt program att få åtkomst till Microsoft 365-data.</span><span class="sxs-lookup"><span data-stu-id="162ad-114">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="162ad-115">Följ stegen i den här artikeln för att konfigurera detta.</span><span class="sxs-lookup"><span data-stu-id="162ad-115">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="162ad-116">API för hanteringsaktivitet i Office 365, referens</span><span class="sxs-lookup"><span data-stu-id="162ad-116">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="162ad-117">Du kan använda API: t för hanterings aktiviteten för Office 365 för att hämta information om åtgärder och händelser för användare, administratörer, system och principer från Microsoft 365 och Azure AD-aktivitets loggar.</span><span class="sxs-lookup"><span data-stu-id="162ad-117">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="162ad-118">Läs den här artikeln om du vill veta mer om hur det fungerar.</span><span class="sxs-lookup"><span data-stu-id="162ad-118">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="162ad-119">API för hanteringsaktivitet i Office 365. schema</span><span class="sxs-lookup"><span data-stu-id="162ad-119">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="162ad-120">Få en översikt över [gemensamt schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) och [Defender för Office 365-och svars schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) för att få information om specifika typer av data som finns tillgängliga via API för hanterings aktivitet i Office 365.</span><span class="sxs-lookup"><span data-stu-id="162ad-120">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Defender for Office 365 and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="162ad-121">Se även</span><span class="sxs-lookup"><span data-stu-id="162ad-121">See also</span></span>

- [<span data-ttu-id="162ad-122">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="162ad-122">Microsoft Defender for Office 365</span></span>](office-365-atp.md)

- [<span data-ttu-id="162ad-123">Automatisk undersökning och svar i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="162ad-123">Automated investigation and response in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
