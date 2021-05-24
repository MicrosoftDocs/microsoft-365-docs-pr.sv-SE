---
title: Hantera användarens medgivande för appar i Microsoft 365
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
description: Läs mer om användarens medgivande till appar och hur du aktiverar dem för att tillåta tredje parts appar att få åtkomst Microsoft 365 information.
ms.openlocfilehash: b8f65b50e50b0e0b4d978388463bbd380ca60d4e
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624507"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a><span data-ttu-id="26b19-103">Hantera användarens medgivande för appar i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="26b19-103">Managing user consent to apps in Microsoft 365</span></span>

<span data-ttu-id="26b19-104">Den här inställningen styr om användare kan ge det medgivande till appar som använder OpenID Anslut och OAuth 2.0 för inloggning och förfrågningar om åtkomst till data.</span><span class="sxs-lookup"><span data-stu-id="26b19-104">This setting controls whether users can give that consent to apps that use OpenID Connect and OAuth 2.0 for sign-in and requests to access data.</span></span> <span data-ttu-id="26b19-105">Du kan skapa en app inom din egen organisation eller så kan den komma från Office 365 annan organisation eller tredje part.</span><span class="sxs-lookup"><span data-stu-id="26b19-105">An app can be created from within your own organization, or it can come from another Office 365 organization or a third-party.</span></span>

<span data-ttu-id="26b19-106">Om du aktiverar den här inställningen ber de apparna om behörighet till organisationens data och användarna kan välja om de vill tillåta dem.</span><span class="sxs-lookup"><span data-stu-id="26b19-106">If you turn this setting on, those apps will ask users for permission to access your organization’s data, and users can choose whether to allow it.</span></span> <span data-ttu-id="26b19-107">Om du inaktiverar den här inställningen måste administratörer godkänna dessa appar innan användarna kan använda dem.</span><span class="sxs-lookup"><span data-stu-id="26b19-107">If you turn this setting off, then admins must consent to those apps before users may use them.</span></span> <span data-ttu-id="26b19-108">I det här fallet kan du konfigurera ett arbetsflöde för administratörsmedgivande i Azure Portal så att användarna kan skicka en begäran om administratörsgodkännande för att använda en blockerad app.</span><span class="sxs-lookup"><span data-stu-id="26b19-108">In this case, consider setting up an admin consent workflow in the Azure portal so users can send a request for admin approval to use any blocked app.</span></span>

<span data-ttu-id="26b19-109">Det går bara att ge behörighet till sin egen Office 365-information.</span><span class="sxs-lookup"><span data-stu-id="26b19-109">A user can give access only to apps they own that access their Office 365 information.</span></span> <span data-ttu-id="26b19-110">Det går inte att ge åtkomst till andra användares information.</span><span class="sxs-lookup"><span data-stu-id="26b19-110">They can't give an app access to any other user's information.</span></span>

## <a name="turning-user-consent-on-or-off"></a><span data-ttu-id="26b19-111">Aktivera eller inaktivera användarmedgivande</span><span class="sxs-lookup"><span data-stu-id="26b19-111">Turning user consent on or off</span></span>
<span data-ttu-id="26b19-112"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="26b19-112"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="26b19-113">Så här aktiverar eller inaktiverar du användarmedgivande för appar.</span><span class="sxs-lookup"><span data-stu-id="26b19-113">Here's how to turn User consent to apps on or off.</span></span>

1. <span data-ttu-id="26b19-114">I administrationscentret går du till sidan **för Inställningar** \> **Organisationsinställningar** och väljer  >  [](https://go.microsoft.com/fwlink/p/?linkid=2053743) sedan **Användarens medgivande för appar**.</span><span class="sxs-lookup"><span data-stu-id="26b19-114">In the admin center, go to the **Settings** \> **Org settings** > [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) page, and then select **User consent to apps**.</span></span>

2. <span data-ttu-id="26b19-115">På sidan **Användarens medgivande till appar** väljer du alternativet att aktivera eller inaktivera användarens medgivande.</span><span class="sxs-lookup"><span data-stu-id="26b19-115">On the **User consent to apps** page, select the option to turn user consent on or off.</span></span>

## <a name="related-content"></a><span data-ttu-id="26b19-116">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="26b19-116">Related content</span></span> 
<span data-ttu-id="26b19-117"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="26b19-117"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="26b19-118">[Konfigurera arbetsflödet för administratörsmedgivande](/azure/active-directory/manage-apps/configure-admin-consent-workflow) (artikel)</span><span class="sxs-lookup"><span data-stu-id="26b19-118">[Configure the admin consent workflow](/azure/active-directory/manage-apps/configure-admin-consent-workflow) (article)</span></span>\
<span data-ttu-id="26b19-119">[Hantera medgivande för program och utvärdera medgivandeförfrågningar](/azure/active-directory/manage-apps/manage-consent-requests) (artikel)</span><span class="sxs-lookup"><span data-stu-id="26b19-119">[Managing consent to applications and evaluating consent requests](/azure/active-directory/manage-apps/manage-consent-requests) (article)</span></span>