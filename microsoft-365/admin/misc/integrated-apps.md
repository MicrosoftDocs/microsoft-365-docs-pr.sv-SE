---
title: Hantera användarens medgivande till appar i Microsoft 365
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
description: Läs mer om användarens medgivande till appar och hur du aktiverar dem så att appar från tredje part kan komma åt användarnas Microsoft 365-information.
ms.openlocfilehash: 955ae9e58c14dbb8012a440ef6c336f44b0760a4
ms.sourcegitcommit: 7bb3d8a93a85246172e2499d6c58c390e46f5bb9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/02/2020
ms.locfileid: "44498323"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a><span data-ttu-id="c1332-103">Hantera användarens medgivande till appar i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c1332-103">Managing user consent to apps in Microsoft 365</span></span>

<span data-ttu-id="c1332-104">Den här inställningen styr om användare kan ge det medgivandet till appar som använder OpenID Connect och OAuth 2.0 för inloggning och begäranden om åtkomst till data.</span><span class="sxs-lookup"><span data-stu-id="c1332-104">This setting controls whether users can give that consent to apps that use OpenID Connect and OAuth 2.0 for sign-in and requests to access data.</span></span> <span data-ttu-id="c1332-105">En app kan skapas inifrån din egen organisation eller komma från en annan Office 365-organisation eller en tredje part.</span><span class="sxs-lookup"><span data-stu-id="c1332-105">An app can be created from within your own organization, or it can come from another Office 365 organization or a third-party.</span></span>

<span data-ttu-id="c1332-106">Om du aktiverar den här inställningen ber dessa appar användarna om tillåtelse att komma åt organisationens data och användarna kan välja om de vill tillåta det.</span><span class="sxs-lookup"><span data-stu-id="c1332-106">If you turn this setting on, those apps will ask users for permission to access your organization’s data, and users can choose whether to allow it.</span></span> <span data-ttu-id="c1332-107">Om du inaktiverar den här inställningen måste administratörerna samtycka till dessa appar innan användarna kan använda dem.</span><span class="sxs-lookup"><span data-stu-id="c1332-107">If you turn this setting off, then admins must consent to those apps before users may use them.</span></span> <span data-ttu-id="c1332-108">I det här fallet bör du överväga att konfigurera ett arbetsflöde för administratörsgodkännande i Azure-portalen så att användarna kan skicka en begäran om administratörsgodkännande för att använda en blockerad app.</span><span class="sxs-lookup"><span data-stu-id="c1332-108">In this case, consider setting up an admin consent workflow in the Azure portal so users can send a request for admin approval to use any blocked app.</span></span>

<span data-ttu-id="c1332-109">Det går bara att ge behörighet till sin egen Office 365-information.</span><span class="sxs-lookup"><span data-stu-id="c1332-109">A user can give access only to apps they own that access their Office 365 information.</span></span> <span data-ttu-id="c1332-110">Det går inte att ge åtkomst till andra användares information.</span><span class="sxs-lookup"><span data-stu-id="c1332-110">They can't give an app access to any other user's information.</span></span>

## <a name="turning-user-consent-on-or-off"></a><span data-ttu-id="c1332-111">Aktivera eller inaktivera användarens medgivande</span><span class="sxs-lookup"><span data-stu-id="c1332-111">Turning user consent on or off</span></span>
<span data-ttu-id="c1332-112"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="c1332-112"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="c1332-113">Så här aktiverar eller inaktiverar du Användarens medgivande till appar.</span><span class="sxs-lookup"><span data-stu-id="c1332-113">Here's how to turn User consent to apps on or off.</span></span>

1. <span data-ttu-id="c1332-114">Gå till sidan **Inställningar** Org settings Services i administrationscentret \> **Org settings**  >  [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) och välj sedan **Användarens medgivande till appar**.</span><span class="sxs-lookup"><span data-stu-id="c1332-114">In the admin center, go to the **Settings** \> **Org settings** > [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) page, and then select **User consent to apps**.</span></span>

2. <span data-ttu-id="c1332-115">På sidan **Användarens medgivande till appar** väljer du alternativet att aktivera eller inaktivera användarens medgivande.</span><span class="sxs-lookup"><span data-stu-id="c1332-115">On the **User consent to apps** page, select the option to turn user consent on or off.</span></span>

## <a name="more-info"></a><span data-ttu-id="c1332-116">Mer information</span><span class="sxs-lookup"><span data-stu-id="c1332-116">More info</span></span>
<span data-ttu-id="c1332-117"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="c1332-117"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="c1332-118">Mer information om hur du konfigurerar dina inställningar för medgivande i Azure active directory läser [du Konfigurera arbetsflödet för administratörssamtycke](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow).</span><span class="sxs-lookup"><span data-stu-id="c1332-118">To learn about how to configure your consent settings in Azure active directory, read [Configure the admin consent workflow](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow).</span></span>

<span data-ttu-id="c1332-119">Om du vill veta mer om hur du hanterar användarens medgivande till appar läser du [Hantera samtycke till program och utvärdera samtyckesbegäranden](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests).</span><span class="sxs-lookup"><span data-stu-id="c1332-119">To learn about managing user consent to apps, read [Managing consent to applications and evaluating consent requests](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests).</span></span>