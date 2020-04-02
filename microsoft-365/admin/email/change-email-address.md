---
title: Ändra din e-postadress så att en anpassad domän används
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: f4d8cae9-6d06-4c4b-b4e5-6581fd05ea82
description: 'Ändra din första e-postadress till en vänlig e-postadress som tom@fourthcoffee.com. För att göra detta måste du köpa ett domännamn och lägga till det i Office 365. '
ms.openlocfilehash: 1c3c77f9626cdf292e0fb9400070cef3df05a9d6
ms.sourcegitcommit: 8edad75338cf74712ca1ab5d6631b9b52ff54410
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "43115986"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a><span data-ttu-id="957fe-104">Ändra din e-postadress så att en anpassad domän används</span><span class="sxs-lookup"><span data-stu-id="957fe-104">Change your email address to use your custom domain</span></span>

 <span data-ttu-id="957fe-105">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="957fe-105">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
::: moniker range="o365-worldwide"

<span data-ttu-id="957fe-p102">Den ursprungliga e-postadressen i Office 365 innehåller .onmicrosoft.com, t.ex. tom@fourthcoffee.onmicrosoft.com. Du kan ändra den till en enklare adress som tom@fourthcoffee.com. Du behöver först ditt eget domännamn, till exempel fourthcoffee.com. Om du redan har ett är det toppen! Om inte kan du ta reda på hur du [köper ett från en domänregistrator](../get-help-with-domains/buy-a-domain-name.md).</span><span class="sxs-lookup"><span data-stu-id="957fe-p102">Your initial email address in Office 365 includes .onmicrosoft.com, like tom@fourthcoffee.onmicrosoft.com. You can change it to a friendlier address like tom@fourthcoffee.com. You'll need your own domain name, like fourthcoffee.com first. If you already have one, great! If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="957fe-111">Din första e-postadress i Office 365 Tyskland innehåller .onmicrosoft.de, till exempel tom@fourthcoffee.onmicrosoft.de.</span><span class="sxs-lookup"><span data-stu-id="957fe-111">Your initial email address in Office 365 Germany includes .onmicrosoft.de, like tom@fourthcoffee.onmicrosoft.de.</span></span> <span data-ttu-id="957fe-112">Du kan ändra den till en vänligare adress som tom@fourthcoffee.de.</span><span class="sxs-lookup"><span data-stu-id="957fe-112">You can change it to a friendlier address like tom@fourthcoffee.de.</span></span> <span data-ttu-id="957fe-113">Du behöver ditt eget domännamn, som fourthcoffee.de först.</span><span class="sxs-lookup"><span data-stu-id="957fe-113">You'll need your own domain name, like fourthcoffee.de first.</span></span> <span data-ttu-id="957fe-114">Om du redan har en, bra!</span><span class="sxs-lookup"><span data-stu-id="957fe-114">If you already have one, great!</span></span> <span data-ttu-id="957fe-115">Om inte, kan du lära dig att [köpa en från en domänregistratorer](../get-help-with-domains/buy-a-domain-name.md).</span><span class="sxs-lookup"><span data-stu-id="957fe-115">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="957fe-116">Din första e-postadress i Office 365 som drivs av 21Vianet innehåller partner.onmschina.cn, till exempel tom@fourthcoffee.partner.onmschina.cn.</span><span class="sxs-lookup"><span data-stu-id="957fe-116">Your initial email address in Office 365 operated by 21Vianet includes partner.onmschina.cn, like tom@fourthcoffee.partner.onmschina.cn.</span></span> <span data-ttu-id="957fe-117">Du kan ändra den till en vänligare adress som tom@fourthcoffee.cn.</span><span class="sxs-lookup"><span data-stu-id="957fe-117">You can change it to a friendlier address like tom@fourthcoffee.cn.</span></span> <span data-ttu-id="957fe-118">Du behöver ditt eget domännamn, som fourthcoffee.cn först.</span><span class="sxs-lookup"><span data-stu-id="957fe-118">You'll need your own domain name, like fourthcoffee.cn first.</span></span> <span data-ttu-id="957fe-119">Om du redan har en, bra!</span><span class="sxs-lookup"><span data-stu-id="957fe-119">If you already have one, great!</span></span> <span data-ttu-id="957fe-120">Om inte, kan du lära dig att [köpa en från en domänregistratorer](../get-help-with-domains/buy-a-domain-name.md).</span><span class="sxs-lookup"><span data-stu-id="957fe-120">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

<span data-ttu-id="957fe-p105">När du ändrar din domäns e-post så att den kommer till Office 365, genom att uppdatera domänens MX-post vid konfigureringen, börjar ALL e-post som skickas till den domänen att komma till Office 365. Kontrollera att du har lagt till användare och skapat postlådor i Office 365 för alla som har e-posten på din domän INNAN du ändrar MX-posten. Vill du inte flytta e-posten för alla på domänen till Office 365? Då kan du göra så att [bara vissa e-postadresser använder Office 365](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx).</span><span class="sxs-lookup"><span data-stu-id="957fe-p105">When you change your domain's email to come to Office 365, by updating your domain's MX record during setup, ALL email sent to that domain will start coming to Office 365. Make sure you've added users and created mailboxes in Office 365 for everyone who has email on your domain BEFORE you change the MX record. Don't want to move email for everyone on your domain to Office 365? You can take steps to [pilot Office 365 with just a few email addresses instead](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx).</span></span>
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a><span data-ttu-id="957fe-125">Ändra din e-postadress så att den använder din anpassade domän med hjälp av administrationscentret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="957fe-125">Change your email address to use your custom domain using the Microsoft 365 admin center</span></span>

<span data-ttu-id="957fe-126">Du måste ha ett globalt administratörskonto för att kunna utföra dessa steg.</span><span class="sxs-lookup"><span data-stu-id="957fe-126">You must have a global admin account to perform these steps.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="957fe-127">Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="957fe-127">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span> 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. <span data-ttu-id="957fe-128">Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="957fe-128">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span> 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="957fe-129">Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>.</span><span class="sxs-lookup"><span data-stu-id="957fe-129">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn</a>.</span></span> 

::: moniker-end 

2. <span data-ttu-id="957fe-130">Gå till sidan > **Installationsdomäner.** **Setup**</span><span class="sxs-lookup"><span data-stu-id="957fe-130">Go to the **Setup** > **Domains** page.</span></span> 

3. <span data-ttu-id="957fe-131">På sidan **Domäner** väljer du **Lägg till domän**.</span><span class="sxs-lookup"><span data-stu-id="957fe-131">On the **Domains** page, select **Add domain**.</span></span>
    
4. <span data-ttu-id="957fe-132">Följ instruktionerna för att bekräfta att du äger domänen och för att ändra din e-postadress.</span><span class="sxs-lookup"><span data-stu-id="957fe-132">Follow the steps to confirm that you own your domain and to change your email address.</span></span>
    
<span data-ttu-id="957fe-133">Du vägleds till rätt inställningar av domänen i Office 365.</span><span class="sxs-lookup"><span data-stu-id="957fe-133">You'll be guided to get everything set up correctly with your domain in Office 365.</span></span>

> [!NOTE]
> <span data-ttu-id="957fe-134">Om du inte använder en Exchange-licens kan du inte använda domänen för att skicka eller ta emot e-postmeddelanden från Office 365-klienten.</span><span class="sxs-lookup"><span data-stu-id="957fe-134">If you are not using an Exchange license, you cannot use the domain to send or receive emails from the Office 365 tenant.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="957fe-135">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="957fe-135">Related articles</span></span>

[<span data-ttu-id="957fe-136">Köpa en egen domän med Office 365</span><span class="sxs-lookup"><span data-stu-id="957fe-136">Buy a custom domain using Office 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)
 
