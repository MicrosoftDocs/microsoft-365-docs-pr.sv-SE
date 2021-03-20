---
title: Hantera användarmedgivande till appar i Microsoft 365
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
description: Läs mer om användarens medgivande till appar och hur du aktiverar dem för att tillåta tredjepartsprogram att få åtkomst till information om Microsoft 365.
ms.openlocfilehash: 1f6f08161d6dd85964f07ec4d48f9f2cc23a1ead
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914570"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a><span data-ttu-id="fe7ab-103">Hantera användarmedgivande till appar i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fe7ab-103">Managing user consent to apps in Microsoft 365</span></span>

<span data-ttu-id="fe7ab-104">Den här inställningen styr om användare kan ge det medgivande till appar som använder OpenID Connect och OAuth 2.0 för inloggning och förfrågningar om åtkomst till data.</span><span class="sxs-lookup"><span data-stu-id="fe7ab-104">This setting controls whether users can give that consent to apps that use OpenID Connect and OAuth 2.0 for sign-in and requests to access data.</span></span> <span data-ttu-id="fe7ab-105">Du kan skapa en app från din egen organisation eller så kan den komma från en annan Office 365-organisation eller tredje part.</span><span class="sxs-lookup"><span data-stu-id="fe7ab-105">An app can be created from within your own organization, or it can come from another Office 365 organization or a third-party.</span></span>

<span data-ttu-id="fe7ab-106">Om du aktiverar den här inställningen ber de apparna om behörighet till organisationens data och användarna kan välja om de vill tillåta dem.</span><span class="sxs-lookup"><span data-stu-id="fe7ab-106">If you turn this setting on, those apps will ask users for permission to access your organization’s data, and users can choose whether to allow it.</span></span> <span data-ttu-id="fe7ab-107">Om du inaktiverar den här inställningen måste administratörer godkänna dessa appar innan användarna kan använda dem.</span><span class="sxs-lookup"><span data-stu-id="fe7ab-107">If you turn this setting off, then admins must consent to those apps before users may use them.</span></span> <span data-ttu-id="fe7ab-108">I det här fallet kan du konfigurera ett arbetsflöde för administratörsmedgivande i Azure Portal så att användarna kan skicka en begäran om administratörsgodkännande för att använda en blockerad app.</span><span class="sxs-lookup"><span data-stu-id="fe7ab-108">In this case, consider setting up an admin consent workflow in the Azure portal so users can send a request for admin approval to use any blocked app.</span></span>

<span data-ttu-id="fe7ab-109">Det går bara att ge behörighet till sin egen Office 365-information.</span><span class="sxs-lookup"><span data-stu-id="fe7ab-109">A user can give access only to apps they own that access their Office 365 information.</span></span> <span data-ttu-id="fe7ab-110">Det går inte att ge åtkomst till andra användares information.</span><span class="sxs-lookup"><span data-stu-id="fe7ab-110">They can't give an app access to any other user's information.</span></span>

## <a name="turning-user-consent-on-or-off"></a><span data-ttu-id="fe7ab-111">Aktivera eller inaktivera användarmedgivande</span><span class="sxs-lookup"><span data-stu-id="fe7ab-111">Turning user consent on or off</span></span>
<span data-ttu-id="fe7ab-112"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="fe7ab-112"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="fe7ab-113">Så här aktiverar eller inaktiverar du användarmedgivande för appar.</span><span class="sxs-lookup"><span data-stu-id="fe7ab-113">Here's how to turn User consent to apps on or off.</span></span>

1. <span data-ttu-id="fe7ab-114">I administrationscentret går du till sidan **Inställningar För** \> **organisationsinställningar** och väljer  >  [](https://go.microsoft.com/fwlink/p/?linkid=2053743) sedan **Användarens medgivande för appar.**</span><span class="sxs-lookup"><span data-stu-id="fe7ab-114">In the admin center, go to the **Settings** \> **Org settings** > [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) page, and then select **User consent to apps**.</span></span>

2. <span data-ttu-id="fe7ab-115">På sidan **Användarens medgivande till appar** väljer du alternativet att aktivera eller inaktivera användarens medgivande.</span><span class="sxs-lookup"><span data-stu-id="fe7ab-115">On the **User consent to apps** page, select the option to turn user consent on or off.</span></span>

## <a name="more-info"></a><span data-ttu-id="fe7ab-116">Mer information</span><span class="sxs-lookup"><span data-stu-id="fe7ab-116">More info</span></span>
<span data-ttu-id="fe7ab-117"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="fe7ab-117"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="fe7ab-118">Mer information om hur du konfigurerar dina medgivandeinställningar i Azure Active Directory finns i Konfigurera [arbetsflödet för administratörsmedgivande.](/azure/active-directory/manage-apps/configure-admin-consent-workflow)</span><span class="sxs-lookup"><span data-stu-id="fe7ab-118">To learn about how to configure your consent settings in Azure active directory, read [Configure the admin consent workflow](/azure/active-directory/manage-apps/configure-admin-consent-workflow).</span></span>

<span data-ttu-id="fe7ab-119">Mer information om hur du hanterar användares medgivande för appar finns i [Hantera medgivande för program och utvärdera medgivandebegäranden.](/azure/active-directory/manage-apps/manage-consent-requests)</span><span class="sxs-lookup"><span data-stu-id="fe7ab-119">To learn about managing user consent to apps, read [Managing consent to applications and evaluating consent requests](/azure/active-directory/manage-apps/manage-consent-requests).</span></span>