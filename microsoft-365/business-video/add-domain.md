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
ms.openlocfilehash: a641005913f7dfd866366f0f8065019dd5c17fe8
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903748"
---
# <a name="add-another-domain"></a><span data-ttu-id="7b180-103">Lägga till en annan domän</span><span class="sxs-lookup"><span data-stu-id="7b180-103">Add another domain</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

<span data-ttu-id="7b180-104">Ditt företag kan behöva flera domännamn för olika ändamål.</span><span class="sxs-lookup"><span data-stu-id="7b180-104">Your company might need multiple domain names for different purposes.</span></span> <span data-ttu-id="7b180-105">Du kanske till exempel vill lägga till en annan stavning av ditt företagsnamn eftersom kunderna redan använder det och deras meddelanden inte har nå dig.</span><span class="sxs-lookup"><span data-stu-id="7b180-105">For example, you might want to add a different spelling of your company name because customers are already using it and their communications have failed to reach you.</span></span>

## <a name="try-it"></a><span data-ttu-id="7b180-106">Prova!</span><span class="sxs-lookup"><span data-stu-id="7b180-106">Try it!</span></span>

1. <span data-ttu-id="7b180-107">I administrationscentret för Microsoft 365 väljer du **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="7b180-107">In the Microsoft 365 admin center, choose **Setup**.</span></span>
1. <span data-ttu-id="7b180-108">Under **Konfigurera din egen domän väljer** du **Visa**.</span><span class="sxs-lookup"><span data-stu-id="7b180-108">Under **Get your custom domain set up**, select **View**.</span></span>
1. <span data-ttu-id="7b180-109">Välj **Manage** och sedan **Add domain**.</span><span class="sxs-lookup"><span data-stu-id="7b180-109">Choose **Manage**, and then **Add domain**.</span></span>
1. <span data-ttu-id="7b180-110">Ange det nya domännamnet som du vill lägga till och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7b180-110">Enter the new domain name that you want to add, and then select **Next**.</span></span>
1. <span data-ttu-id="7b180-111">Logga in på din domänregistrator, i det här fallet GoDaddy, och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="7b180-111">Sign in to your domain registrar, in this case GoDaddy, and then select **Next**.</span></span>
1. <span data-ttu-id="7b180-112">Logga in på din registrator om du uppmanas till det och välj sedan **Godkänn**.</span><span class="sxs-lookup"><span data-stu-id="7b180-112">If prompted, sign in to your registrar, and then choose **Authorize**.</span></span>
1. <span data-ttu-id="7b180-113">Välj **Add the DNS records for me** och sedan **Next**.</span><span class="sxs-lookup"><span data-stu-id="7b180-113">Choose **Add the DNS records for me**, and then select **Next**.</span></span>
1. <span data-ttu-id="7b180-114">Välj tjänsterna för den nya domänen och avmarkera kryssrutorna för de tjänster som ska hanteras av en annan domän.</span><span class="sxs-lookup"><span data-stu-id="7b180-114">Choose the services for your new domain and clear the check boxes for any services that will be handled by a different domain.</span></span> <span data-ttu-id="7b180-115">Om du till exempel bara vill använda den nya domänen för e-post väljer du **Exchange** och avmarkerar kryssrutorna **för Skype** för företag och Hantering av mobila enheter för **Office 365.**</span><span class="sxs-lookup"><span data-stu-id="7b180-115">For example, if you just want to use the new domain for email, choose **Exchange**, and clear the check boxes for **Skype for Business** and **Mobile Device Management for Office 365**.</span></span>
1. <span data-ttu-id="7b180-116">Välj **Nästa,** **Godkänn** **, Nästa** och sedan **Slutför.**</span><span class="sxs-lookup"><span data-stu-id="7b180-116">Select **Next**, **Authorize**, **Next**,and then **Finish**.</span></span> <span data-ttu-id="7b180-117">Din nya domän har lagts till.</span><span class="sxs-lookup"><span data-stu-id="7b180-117">Your new domain has been added.</span></span>

<span data-ttu-id="7b180-118">Om du vill ta emot e-post på din nya domän måste du lägga till ett nytt e-postalias för varje användare:</span><span class="sxs-lookup"><span data-stu-id="7b180-118">To receive email at your new domain, you'll need to add a new email alias for each user:</span></span>

1. <span data-ttu-id="7b180-119">Välj **Användare**, **Aktiva användare** och välj sedan den användare som ska tilldelas det nya aliaset.</span><span class="sxs-lookup"><span data-stu-id="7b180-119">Select **Users**, **Active users**, and then select the user who will be assigned the new alias.</span></span>
1. <span data-ttu-id="7b180-120">Välj **Hantera e-postalias** och sedan Lägg **till ett alias**.</span><span class="sxs-lookup"><span data-stu-id="7b180-120">Choose **Manage email aliases**, and then **Add an alias**.</span></span>
1. <span data-ttu-id="7b180-121">Ange användarnamnet och välj sedan den nya domänen i listrutan.</span><span class="sxs-lookup"><span data-stu-id="7b180-121">Enter the username, and then choose the new domain from the drop-down list.</span></span>
1. <span data-ttu-id="7b180-122">Välj **Spara** ändringar och stäng sedan fönstret.</span><span class="sxs-lookup"><span data-stu-id="7b180-122">Select **Save changes**, and then close the window.</span></span>
1. <span data-ttu-id="7b180-123">Upprepa de här stegen för alla användare som ska få e-post på den nya domänen.</span><span class="sxs-lookup"><span data-stu-id="7b180-123">Repeat these steps for each user who should receive email at the new domain.</span></span>

## <a name="related-content"></a><span data-ttu-id="7b180-124">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="7b180-124">Related content</span></span>

<span data-ttu-id="7b180-125">Lägga till en domän i [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) (artikel) Lägga till [DNS-poster](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) för att ansluta din domän (artikel) Ändra namnservrar för att konfigurera [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar) med valfri domänregistrator (artikel) [Vanliga](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) frågor och svar om domäner (artikel)</span><span class="sxs-lookup"><span data-stu-id="7b180-125">[Add a domain to Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) (article) [Add DNS records to connect your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) (article) [Change nameservers to set up Microsoft 365 with any domain registrar](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar) (article) [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) (article)</span></span>