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
description: Din organisation kan behöva flera domäner så att kunderna kan hitta dig. Lär dig hur du lägger till en annan domän i din prenumeration.
ms.openlocfilehash: 13fc3cf73a112945db4372231cce70c1837c1321
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706436"
---
# <a name="add-another-domain"></a><span data-ttu-id="08d53-104">Lägga till en annan domän</span><span class="sxs-lookup"><span data-stu-id="08d53-104">Add another domain</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

<span data-ttu-id="08d53-105">Ditt företag kan behöva flera domännamn för olika ändamål.</span><span class="sxs-lookup"><span data-stu-id="08d53-105">Your company might need multiple domain names for different purposes.</span></span> <span data-ttu-id="08d53-106">Du kanske till exempel vill lägga till en annan stavning av ditt företagsnamn eftersom kunderna redan använder det och deras meddelanden inte har nå dig.</span><span class="sxs-lookup"><span data-stu-id="08d53-106">For example, you might want to add a different spelling of your company name because customers are already using it and their communications have failed to reach you.</span></span>

## <a name="try-it"></a><span data-ttu-id="08d53-107">Prova själv!</span><span class="sxs-lookup"><span data-stu-id="08d53-107">Try it!</span></span>

1. <span data-ttu-id="08d53-108">Välj Microsoft 365 i **administrationscentret.**</span><span class="sxs-lookup"><span data-stu-id="08d53-108">In the Microsoft 365 admin center, choose **Setup**.</span></span>
1. <span data-ttu-id="08d53-109">Under **Konfigurera din egen domän väljer** du **Visa**.</span><span class="sxs-lookup"><span data-stu-id="08d53-109">Under **Get your custom domain set up**, select **View**.</span></span>
1. <span data-ttu-id="08d53-110">Välj **Manage** och sedan **Add domain**.</span><span class="sxs-lookup"><span data-stu-id="08d53-110">Choose **Manage**, and then **Add domain**.</span></span>
1. <span data-ttu-id="08d53-111">Ange det nya domännamnet som du vill lägga till och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="08d53-111">Enter the new domain name that you want to add, and then select **Next**.</span></span>
1. <span data-ttu-id="08d53-112">Logga in på din domänregistrator, i det här fallet GoDaddy, och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="08d53-112">Sign in to your domain registrar, in this case GoDaddy, and then select **Next**.</span></span>
1. <span data-ttu-id="08d53-113">Logga in på din registrator om du uppmanas till det och välj sedan **Godkänn**.</span><span class="sxs-lookup"><span data-stu-id="08d53-113">If prompted, sign in to your registrar, and then choose **Authorize**.</span></span>
1. <span data-ttu-id="08d53-114">Välj **Add the DNS records for me** och sedan **Next**.</span><span class="sxs-lookup"><span data-stu-id="08d53-114">Choose **Add the DNS records for me**, and then select **Next**.</span></span>
1. <span data-ttu-id="08d53-115">Välj tjänsterna för den nya domänen och avmarkera kryssrutorna för de tjänster som ska hanteras av en annan domän.</span><span class="sxs-lookup"><span data-stu-id="08d53-115">Choose the services for your new domain and clear the check boxes for any services that will be handled by a different domain.</span></span> <span data-ttu-id="08d53-116">Om du till exempel bara vill använda den nya domänen för e-post väljer du **Exchange** och avmarkerar kryssrutorna **för Skype för företag** och **Mobile Device Management för Office 365**.</span><span class="sxs-lookup"><span data-stu-id="08d53-116">For example, if you just want to use the new domain for email, choose **Exchange**, and clear the check boxes for **Skype for Business** and **Mobile Device Management for Office 365**.</span></span>
1. <span data-ttu-id="08d53-117">Välj **Nästa,** **Godkänn** **, Nästa** och sedan **Slutför.**</span><span class="sxs-lookup"><span data-stu-id="08d53-117">Select **Next**, **Authorize**, **Next**,and then **Finish**.</span></span> <span data-ttu-id="08d53-118">Din nya domän har lagts till.</span><span class="sxs-lookup"><span data-stu-id="08d53-118">Your new domain has been added.</span></span>

<span data-ttu-id="08d53-119">Om du vill ta emot e-post på din nya domän måste du lägga till ett nytt e-postalias för varje användare:</span><span class="sxs-lookup"><span data-stu-id="08d53-119">To receive email at your new domain, you'll need to add a new email alias for each user:</span></span>

1. <span data-ttu-id="08d53-120">Välj **Användare**, **Aktiva användare** och välj sedan den användare som ska tilldelas det nya aliaset.</span><span class="sxs-lookup"><span data-stu-id="08d53-120">Select **Users**, **Active users**, and then select the user who will be assigned the new alias.</span></span>
1. <span data-ttu-id="08d53-121">Välj **Hantera e-postalias** och sedan Lägg **till ett alias**.</span><span class="sxs-lookup"><span data-stu-id="08d53-121">Choose **Manage email aliases**, and then **Add an alias**.</span></span>
1. <span data-ttu-id="08d53-122">Ange användarnamnet och välj sedan den nya domänen i listrutan.</span><span class="sxs-lookup"><span data-stu-id="08d53-122">Enter the username, and then choose the new domain from the drop-down list.</span></span>
1. <span data-ttu-id="08d53-123">Välj **Spara** ändringar och stäng sedan fönstret.</span><span class="sxs-lookup"><span data-stu-id="08d53-123">Select **Save changes**, and then close the window.</span></span>
1. <span data-ttu-id="08d53-124">Upprepa de här stegen för alla användare som ska få e-post på den nya domänen.</span><span class="sxs-lookup"><span data-stu-id="08d53-124">Repeat these steps for each user who should receive email at the new domain.</span></span>

## <a name="related-content"></a><span data-ttu-id="08d53-125">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="08d53-125">Related content</span></span>

<span data-ttu-id="08d53-126">[Lägga till en domän Microsoft 365](../admin/setup/add-domain.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="08d53-126">[Add a domain to Microsoft 365](../admin/setup/add-domain.md) (article)</span></span>\
<span data-ttu-id="08d53-127">[Lägg till DNS-poster för att ansluta din domän](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="08d53-127">[Add DNS records to connect your domain](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) (article)</span></span>\
<span data-ttu-id="08d53-128">[Ändra namnservrar för att konfigurera Microsoft 365 med valfri domänregistrator](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="08d53-128">[Change nameservers to set up Microsoft 365 with any domain registrar](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md) (article)</span></span>\
<span data-ttu-id="08d53-129">[Domänens vanliga frågor och svar](../admin/setup/domains-faq.yml) (artikel)</span><span class="sxs-lookup"><span data-stu-id="08d53-129">[Domains FAQ](../admin/setup/domains-faq.yml) (article)</span></span>