---
title: Samla den information du behöver för att skapa DNS-poster i Office 365
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: 'Lär dig att hitta de värden/den information du behöver för att skapa DNS-poster för Office 365. '
ms.custom: okr_smb
ms.openlocfilehash: d6093dd8a7e8d901be7b172a31dcd0e56c549ab3
ms.sourcegitcommit: 732bb72a0b5ae09cb39536185aa29d6097ec72fd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/08/2020
ms.locfileid: "43189002"
---
# <a name="gather-the-information-you-need-to-create-office-365-dns-records"></a><span data-ttu-id="bbd27-103">Samla den information du behöver för att skapa DNS-poster i Office 365</span><span class="sxs-lookup"><span data-stu-id="bbd27-103">Gather the information you need to create Office 365 DNS records</span></span>

 <span data-ttu-id="bbd27-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="bbd27-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="bbd27-105">Steg 1: Hitta TXT-postvärdet och verifiera</span><span class="sxs-lookup"><span data-stu-id="bbd27-105">Step 1: Find the TXT record value and verify</span></span>

1. <span data-ttu-id="bbd27-106">Gå till sidan <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Installationsdomäner i administrationscentret</a> **för** \> Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bbd27-106">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker range="o365-germany"

1. <span data-ttu-id="bbd27-107">Gå till den här sidan <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domäner i administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="bbd27-107">In the admin center, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="bbd27-108">Gå till den här sidan <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domäner i administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="bbd27-108">In the admin center, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="bbd27-109">På sidan **Domäner** väljer du din domän och väljer sedan **Starta installation**.</span><span class="sxs-lookup"><span data-stu-id="bbd27-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="bbd27-110">Du går tillbaka till domäninstallationsguiden för att se det specifika värde som du måste lägga till.</span><span class="sxs-lookup"><span data-stu-id="bbd27-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="bbd27-111">På sidan **Verifiera domän** väljer du Lägg till **en TXT-post i stället**och väljer sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="bbd27-111">On the **Verify domain** page, select **Add a TXT record instead**, then select **Next**.</span></span>
    
4. <span data-ttu-id="bbd27-112">Kopiera **TXT-värdet** som visas.</span><span class="sxs-lookup"><span data-stu-id="bbd27-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="bbd27-113">Det ser ut så här: **MS=msXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="bbd27-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="bbd27-114">Gå till [Skapa DNS-poster hos alla DNS-värdleverantörer](create-dns-records-at-any-dns-hosting-provider.md)och välj din DNS-värd i listan över registratorer för att se steg-för-steg-instruktioner.</span><span class="sxs-lookup"><span data-stu-id="bbd27-114">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and select your DNS host from the list of registrars to see the step-by-step instructions.</span></span>
    
6. <span data-ttu-id="bbd27-115">Följ stegen för att skapa TXT-posten (eller MX-posten) hos din DNS-värd och verifiera sedan domänen i Office 365.</span><span class="sxs-lookup"><span data-stu-id="bbd27-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Office 365.</span></span>

7. <span data-ttu-id="bbd27-116">Ta bort TXT-posten (eller MX-posten) från DNS-värden när domänen har verifierats i Office 365.</span><span class="sxs-lookup"><span data-stu-id="bbd27-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Office 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="bbd27-117">Steg 2: Hitta MX-postvärdet för e-post med mera</span><span class="sxs-lookup"><span data-stu-id="bbd27-117">Step 2: Find the MX record value for email and more</span></span>

1. <span data-ttu-id="bbd27-118">Gå till sidan <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Installationsdomäner i administrationscentret</a> **för** \> Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bbd27-118">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
::: moniker range="o365-germany"

1. <span data-ttu-id="bbd27-119">Gå till den här sidan <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domäner i administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="bbd27-119">In the admin center, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="bbd27-120">Gå till den här sidan <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domäner i administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="bbd27-120">In the admin center, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="bbd27-121">Välj en domän på sidan **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="bbd27-121">On the **Domains** page, select your domain.</span></span> 
    
3. <span data-ttu-id="bbd27-122">Under **Obligatoriska DNS-inställningar** visas DNS-posterna som ska läggas till.</span><span class="sxs-lookup"><span data-stu-id="bbd27-122">Under **Required DNS settings**, you'll see the DNS records to add.</span></span>
    
    <span data-ttu-id="bbd27-123">Du behöver ha den här informationen tillgänglig när du gör ändringar hos din DNS-värd, så att du kan kopiera och klistra in värdena.</span><span class="sxs-lookup"><span data-stu-id="bbd27-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="bbd27-124">Grupperna av DNS-poster som visas på sidan är beroende av dina val som visas under **Domänsyfte**.</span><span class="sxs-lookup"><span data-stu-id="bbd27-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="bbd27-125">Gå till [Skapa DNS-poster hos valfri DNS-värd](create-dns-records-at-any-dns-hosting-provider.md)och välj sedan din DNS-värd från listan över registratorer för att se steg-för-steg-instruktioner för att lägga till poster på DNS-värdens webbplats.</span><span class="sxs-lookup"><span data-stu-id="bbd27-125">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and then select your DNS host from the list of registrars to see step-by-step instructions for adding records at that DNS host's website.</span></span>
    
5. <span data-ttu-id="bbd27-126">Följ stegen för att skapa posterna hos din DNS-värd.</span><span class="sxs-lookup"><span data-stu-id="bbd27-126">Follow the steps for creating the records at your DNS host.</span></span>
