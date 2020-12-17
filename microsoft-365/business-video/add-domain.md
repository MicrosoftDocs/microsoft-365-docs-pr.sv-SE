---
title: Lägga till en domän
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du lägger till en annan domän i prenumerationen.
ms.openlocfilehash: 16f6c4e416ede560d69014e320eb32c4453fd3f5
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702786"
---
# <a name="add-another-domain"></a><span data-ttu-id="9be97-103">Lägga till en annan domän</span><span class="sxs-lookup"><span data-stu-id="9be97-103">Add another domain</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

<span data-ttu-id="9be97-104">Ditt företag kan behöva flera domän namn för olika ändamål.</span><span class="sxs-lookup"><span data-stu-id="9be97-104">Your company might need multiple domain names for different purposes.</span></span> <span data-ttu-id="9be97-105">Du kanske till exempel vill lägga till en annan stavning i ditt företags namn eftersom kunderna redan använder det och att kommunikationen mellan dem är misslyckad.</span><span class="sxs-lookup"><span data-stu-id="9be97-105">For example, you might want to add a different spelling of your company name because customers are already using it and their communications have failed to reach you.</span></span>

## <a name="try-it"></a><span data-ttu-id="9be97-106">Prova!</span><span class="sxs-lookup"><span data-stu-id="9be97-106">Try it!</span></span>

1. <span data-ttu-id="9be97-107">Välj **installation** i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9be97-107">In the Microsoft 365 admin center, choose **Setup**.</span></span>
1. <span data-ttu-id="9be97-108">Välj **Visa** under **Konfigurera din anpassade domän**.</span><span class="sxs-lookup"><span data-stu-id="9be97-108">Under **Get your custom domain set up**, select **View**.</span></span>
1. <span data-ttu-id="9be97-109">Välj **Hantera** och sedan **Lägg till domän**.</span><span class="sxs-lookup"><span data-stu-id="9be97-109">Choose **Manage**, and then **Add domain**.</span></span>
1. <span data-ttu-id="9be97-110">Ange det nya domän namnet som du vill lägga till och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9be97-110">Enter the new domain name that you want to add, and then select **Next**.</span></span>
1. <span data-ttu-id="9be97-111">Logga in på din domän registrator i det här fallet GoDaddy och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9be97-111">Sign in to your domain registrar, in this case GoDaddy, and then select **Next**.</span></span>
1. <span data-ttu-id="9be97-112">Om du uppmanas att göra det loggar du in på din registrator och väljer sedan **auktorisera**.</span><span class="sxs-lookup"><span data-stu-id="9be97-112">If prompted, sign in to your registrar, and then choose **Authorize**.</span></span>
1. <span data-ttu-id="9be97-113">Välj **Lägg till DNS-posterna åt mig** och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9be97-113">Choose **Add the DNS records for me**, and then select **Next**.</span></span>
1. <span data-ttu-id="9be97-114">Välj tjänster för den nya domänen och avmarkera kryss rutorna för de tjänster som ska hanteras av en annan domän.</span><span class="sxs-lookup"><span data-stu-id="9be97-114">Choose the services for your new domain and clear the check boxes for any services that will be handled by a different domain.</span></span> <span data-ttu-id="9be97-115">Om du till exempel bara vill använda den nya domänen för e-post väljer du **Exchange** och avmarkerar kryss rutorna för hantering av **Skype för företag** och **mobila enheter för Office 365**.</span><span class="sxs-lookup"><span data-stu-id="9be97-115">For example, if you just want to use the new domain for email, choose **Exchange**, and clear the check boxes for **Skype for Business** and **Mobile Device Management for Office 365**.</span></span>
1. <span data-ttu-id="9be97-116">Välj **Nästa**, **auktorisera**, **Nästa** och sedan **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="9be97-116">Select **Next**, **Authorize**, **Next**,and then **Finish**.</span></span> <span data-ttu-id="9be97-117">Den nya domänen har lagts till.</span><span class="sxs-lookup"><span data-stu-id="9be97-117">Your new domain has been added.</span></span>

<span data-ttu-id="9be97-118">Om du vill ta emot e-post från din nya domän måste du lägga till ett nytt e-postalias för varje användare:</span><span class="sxs-lookup"><span data-stu-id="9be97-118">To receive email at your new domain, you'll need to add a new email alias for each user:</span></span>

1. <span data-ttu-id="9be97-119">Välj **användare**, **aktiva användare** och välj sedan den användare som ska tilldelas det nya aliaset.</span><span class="sxs-lookup"><span data-stu-id="9be97-119">Select **Users**, **Active users**, and then select the user who will be assigned the new alias.</span></span>
1. <span data-ttu-id="9be97-120">Välj **Hantera e-postalias** och **Lägg sedan till ett alias**.</span><span class="sxs-lookup"><span data-stu-id="9be97-120">Choose **Manage email aliases**, and then **Add an alias**.</span></span>
1. <span data-ttu-id="9be97-121">Ange användar namnet och välj sedan den nya domänen i list rutan.</span><span class="sxs-lookup"><span data-stu-id="9be97-121">Enter the username, and then choose the new domain from the drop-down list.</span></span>
1. <span data-ttu-id="9be97-122">Välj **Spara ändringar** och stäng sedan fönstret.</span><span class="sxs-lookup"><span data-stu-id="9be97-122">Select **Save changes**, and then close the window.</span></span>
1. <span data-ttu-id="9be97-123">Upprepa de här stegen för varje användare som ska ta emot e-post på den nya domänen.</span><span class="sxs-lookup"><span data-stu-id="9be97-123">Repeat these steps for each user who should receive email at the new domain.</span></span>