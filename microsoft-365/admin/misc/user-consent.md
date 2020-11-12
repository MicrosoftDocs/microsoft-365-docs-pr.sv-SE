---
title: Hantera användar medgivande till program i Microsoft 365
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: Lär dig mer om användarens medgivande till appar och hur du aktiverar dem så att program från tredje part kan komma åt användarnas Microsoft 365-information.
ms.openlocfilehash: 955ae9e58c14dbb8012a440ef6c336f44b0760a4
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999589"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a><span data-ttu-id="25e73-103">Hantera användar medgivande till program i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="25e73-103">Managing user consent to apps in Microsoft 365</span></span>

<span data-ttu-id="25e73-104">Den här inställningen styr om användare kan ge tillstånd till program som använder OpenID Connect och OAuth 2,0 för inloggning och förfrågningar om att få åtkomst till data.</span><span class="sxs-lookup"><span data-stu-id="25e73-104">This setting controls whether users can give that consent to apps that use OpenID Connect and OAuth 2.0 for sign-in and requests to access data.</span></span> <span data-ttu-id="25e73-105">En app kan skapas i din egen organisation eller så kan den komma från en annan Office 365-organisation eller tredje part.</span><span class="sxs-lookup"><span data-stu-id="25e73-105">An app can be created from within your own organization, or it can come from another Office 365 organization or a third-party.</span></span>

<span data-ttu-id="25e73-106">Om du aktiverar den här inställningen ber dessa appar användare att få åtkomst till organisationens data och användare kan välja om de vill tillåta det.</span><span class="sxs-lookup"><span data-stu-id="25e73-106">If you turn this setting on, those apps will ask users for permission to access your organization’s data, and users can choose whether to allow it.</span></span> <span data-ttu-id="25e73-107">Om du inaktiverar den här inställningen måste administratörer godkänna dessa appar innan användarna kan använda dem.</span><span class="sxs-lookup"><span data-stu-id="25e73-107">If you turn this setting off, then admins must consent to those apps before users may use them.</span></span> <span data-ttu-id="25e73-108">I det här fallet kan du skapa ett arbets flöde för administratörs medgivande i Azure-portalen så att användare får skicka en begäran om administratörs godkännande för att använda blockerade appar.</span><span class="sxs-lookup"><span data-stu-id="25e73-108">In this case, consider setting up an admin consent workflow in the Azure portal so users can send a request for admin approval to use any blocked app.</span></span>

<span data-ttu-id="25e73-109">Det går bara att ge behörighet till sin egen Office 365-information.</span><span class="sxs-lookup"><span data-stu-id="25e73-109">A user can give access only to apps they own that access their Office 365 information.</span></span> <span data-ttu-id="25e73-110">Det går inte att ge åtkomst till andra användares information.</span><span class="sxs-lookup"><span data-stu-id="25e73-110">They can't give an app access to any other user's information.</span></span>

## <a name="turning-user-consent-on-or-off"></a><span data-ttu-id="25e73-111">Aktivera eller inaktivera användar medgivande</span><span class="sxs-lookup"><span data-stu-id="25e73-111">Turning user consent on or off</span></span>
<span data-ttu-id="25e73-112"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="25e73-112"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="25e73-113">Så här aktiverar eller inaktiverar du användar medgivande för appar.</span><span class="sxs-lookup"><span data-stu-id="25e73-113">Here's how to turn User consent to apps on or off.</span></span>

1. <span data-ttu-id="25e73-114">I administrations centret går du till sidan **Inställningar** \> **organisations inställningar**  >  [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) och väljer sedan **användarens medgivande till appar**.</span><span class="sxs-lookup"><span data-stu-id="25e73-114">In the admin center, go to the **Settings** \> **Org settings** > [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) page, and then select **User consent to apps**.</span></span>

2. <span data-ttu-id="25e73-115">På sidan **användare medgivande till program** markerar du alternativet för att aktivera eller inaktivera användar medgivande.</span><span class="sxs-lookup"><span data-stu-id="25e73-115">On the **User consent to apps** page, select the option to turn user consent on or off.</span></span>

## <a name="more-info"></a><span data-ttu-id="25e73-116">Mer information</span><span class="sxs-lookup"><span data-stu-id="25e73-116">More info</span></span>
<span data-ttu-id="25e73-117"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="25e73-117"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="25e73-118">Om du vill veta mer om hur du konfigurerar medgivande inställningar i Azure Active Directory läser du [Konfigurera arbets flödet för administratörs godkännande](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow).</span><span class="sxs-lookup"><span data-stu-id="25e73-118">To learn about how to configure your consent settings in Azure active directory, read [Configure the admin consent workflow](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow).</span></span>

<span data-ttu-id="25e73-119">Om du vill veta mer om hur du hanterar användarens medgivande till appar läser du [Hantera medgivande till program och utvärdering av medgivande förfrågningar](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests).</span><span class="sxs-lookup"><span data-stu-id="25e73-119">To learn about managing user consent to apps, read [Managing consent to applications and evaluating consent requests](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests).</span></span>