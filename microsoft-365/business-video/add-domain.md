---
title: Lägga till en domän
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: Lär dig hur du lägger till en annan domän i din prenumeration.
ms.openlocfilehash: 8899cb9667ffa080746ca9173b61897f9c5db399
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579007"
---
# <a name="add-another-domain"></a><span data-ttu-id="fecf9-103">Lägga till en annan domän</span><span class="sxs-lookup"><span data-stu-id="fecf9-103">Add another domain</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

<span data-ttu-id="fecf9-104">Ditt företag kan behöva flera domännamn för olika ändamål.</span><span class="sxs-lookup"><span data-stu-id="fecf9-104">Your company might need multiple domain names for different purposes.</span></span> <span data-ttu-id="fecf9-105">Du kanske till exempel vill lägga till en annan stavning av ditt företagsnamn eftersom kunderna redan använder det och deras meddelanden inte har nå dig.</span><span class="sxs-lookup"><span data-stu-id="fecf9-105">For example, you might want to add a different spelling of your company name because customers are already using it and their communications have failed to reach you.</span></span>

## <a name="try-it"></a><span data-ttu-id="fecf9-106">Prova!</span><span class="sxs-lookup"><span data-stu-id="fecf9-106">Try it!</span></span>

1. <span data-ttu-id="fecf9-107">I administrationscentret för Microsoft 365 väljer du **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="fecf9-107">In the Microsoft 365 admin center, choose **Setup**.</span></span>
1. <span data-ttu-id="fecf9-108">Under **Konfigurera din egen domän väljer** du **Visa**.</span><span class="sxs-lookup"><span data-stu-id="fecf9-108">Under **Get your custom domain set up**, select **View**.</span></span>
1. <span data-ttu-id="fecf9-109">Välj **Manage** och sedan **Add domain**.</span><span class="sxs-lookup"><span data-stu-id="fecf9-109">Choose **Manage**, and then **Add domain**.</span></span>
1. <span data-ttu-id="fecf9-110">Ange det nya domännamnet som du vill lägga till och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="fecf9-110">Enter the new domain name that you want to add, and then select **Next**.</span></span>
1. <span data-ttu-id="fecf9-111">Logga in på din domänregistrator, i det här fallet GoDaddy, och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="fecf9-111">Sign in to your domain registrar, in this case GoDaddy, and then select **Next**.</span></span>
1. <span data-ttu-id="fecf9-112">Logga in på din registrator om du uppmanas till det och välj sedan **Godkänn**.</span><span class="sxs-lookup"><span data-stu-id="fecf9-112">If prompted, sign in to your registrar, and then choose **Authorize**.</span></span>
1. <span data-ttu-id="fecf9-113">Välj **Add the DNS records for me** och sedan **Next**.</span><span class="sxs-lookup"><span data-stu-id="fecf9-113">Choose **Add the DNS records for me**, and then select **Next**.</span></span>
1. <span data-ttu-id="fecf9-114">Välj tjänsterna för den nya domänen och avmarkera kryssrutorna för de tjänster som ska hanteras av en annan domän.</span><span class="sxs-lookup"><span data-stu-id="fecf9-114">Choose the services for your new domain and clear the check boxes for any services that will be handled by a different domain.</span></span> <span data-ttu-id="fecf9-115">Om du till exempel bara vill använda den nya domänen för e-post väljer du **Exchange** och avmarkerar kryssrutorna **för Skype** för företag och Hantering av mobila enheter för **Office 365.**</span><span class="sxs-lookup"><span data-stu-id="fecf9-115">For example, if you just want to use the new domain for email, choose **Exchange**, and clear the check boxes for **Skype for Business** and **Mobile Device Management for Office 365**.</span></span>
1. <span data-ttu-id="fecf9-116">Välj **Nästa,** **Godkänn** **, Nästa** och sedan **Slutför.**</span><span class="sxs-lookup"><span data-stu-id="fecf9-116">Select **Next**, **Authorize**, **Next**,and then **Finish**.</span></span> <span data-ttu-id="fecf9-117">Din nya domän har lagts till.</span><span class="sxs-lookup"><span data-stu-id="fecf9-117">Your new domain has been added.</span></span>

<span data-ttu-id="fecf9-118">Om du vill ta emot e-post på din nya domän måste du lägga till ett nytt e-postalias för varje användare:</span><span class="sxs-lookup"><span data-stu-id="fecf9-118">To receive email at your new domain, you'll need to add a new email alias for each user:</span></span>

1. <span data-ttu-id="fecf9-119">Välj **Användare**, **Aktiva användare** och välj sedan den användare som ska tilldelas det nya aliaset.</span><span class="sxs-lookup"><span data-stu-id="fecf9-119">Select **Users**, **Active users**, and then select the user who will be assigned the new alias.</span></span>
1. <span data-ttu-id="fecf9-120">Välj **Hantera e-postalias** och sedan Lägg **till ett alias**.</span><span class="sxs-lookup"><span data-stu-id="fecf9-120">Choose **Manage email aliases**, and then **Add an alias**.</span></span>
1. <span data-ttu-id="fecf9-121">Ange användarnamnet och välj sedan den nya domänen i listrutan.</span><span class="sxs-lookup"><span data-stu-id="fecf9-121">Enter the username, and then choose the new domain from the drop-down list.</span></span>
1. <span data-ttu-id="fecf9-122">Välj **Spara** ändringar och stäng sedan fönstret.</span><span class="sxs-lookup"><span data-stu-id="fecf9-122">Select **Save changes**, and then close the window.</span></span>
1. <span data-ttu-id="fecf9-123">Upprepa de här stegen för alla användare som ska få e-post på den nya domänen.</span><span class="sxs-lookup"><span data-stu-id="fecf9-123">Repeat these steps for each user who should receive email at the new domain.</span></span>