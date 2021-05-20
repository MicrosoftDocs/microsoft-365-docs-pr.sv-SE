---
title: Samla den information du behöver för att skapa DNS-poster
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: Samla in de värden/den information du behöver för att skapa DNS-poster för att ansluta din domän Microsoft 365 prenumerationen.
ms.openlocfilehash: c8ff30c27e67c8a29b7122ea80a6a33f0594b1b9
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/20/2021
ms.locfileid: "52582962"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a><span data-ttu-id="5a7cd-103">Samla den information du behöver för att skapa DNS-poster</span><span class="sxs-lookup"><span data-stu-id="5a7cd-103">Gather the information you need to create DNS records</span></span>

 <span data-ttu-id="5a7cd-104">**[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="5a7cd-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="5a7cd-105">Steg 1: Hitta TXT-postvärdet och verifiera</span><span class="sxs-lookup"><span data-stu-id="5a7cd-105">Step 1: Find the TXT record value and verify</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5a7cd-106">I Microsoft 365 administrationscentret går du till **sidan** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Konfigurera</a> domäner.</span><span class="sxs-lookup"><span data-stu-id="5a7cd-106">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="5a7cd-107">I administrationscentret går du till **sidan** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Konfigurera</a> domäner.</span><span class="sxs-lookup"><span data-stu-id="5a7cd-107">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5a7cd-108">I administrationscentret går du till **sidan** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Konfigurera</a> domäner.</span><span class="sxs-lookup"><span data-stu-id="5a7cd-108">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="5a7cd-109">På sidan **Domäner** väljer du din domän och sedan **Starta installationen.**</span><span class="sxs-lookup"><span data-stu-id="5a7cd-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="5a7cd-110">Du går tillbaka till domäninstallationsguiden för att se det specifika värde som du måste lägga till.</span><span class="sxs-lookup"><span data-stu-id="5a7cd-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="5a7cd-111">På sidan **Verifiera domän** väljer du Lägg till **en TXT-post i stället** och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="5a7cd-111">On the **Verify domain** page, select **Add a TXT record instead**, then select **Next**.</span></span>
    
4. <span data-ttu-id="5a7cd-112">Kopiera **TXT-värdet som** visas.</span><span class="sxs-lookup"><span data-stu-id="5a7cd-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="5a7cd-113">Så här ser det ut: **MS=msXXXXXXXX.**</span><span class="sxs-lookup"><span data-stu-id="5a7cd-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="5a7cd-114">Gå till [Skapa DNS-poster](create-dns-records-at-any-dns-hosting-provider.md)hos en DNS-värd och välj din DNS-värd i listan med registratorer om du vill ha stegvisa anvisningar.</span><span class="sxs-lookup"><span data-stu-id="5a7cd-114">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and select your DNS host from the list of registrars to see the step-by-step instructions.</span></span>
    
6. <span data-ttu-id="5a7cd-115">Följ stegen för att skapa TXT-posten (eller MX-posten) hos din DNS-värd och verifiera sedan domänen i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5a7cd-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Microsoft 365.</span></span>

7. <span data-ttu-id="5a7cd-116">Ta bort TXT-posten (eller MX-posten) från din DNS-värd när domänen har verifierats i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5a7cd-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Microsoft 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="5a7cd-117">Steg 2: Hitta MX-postvärdet för e-post och mycket mer</span><span class="sxs-lookup"><span data-stu-id="5a7cd-117">Step 2: Find the MX record value for email and more</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5a7cd-118">I Microsoft 365 administrationscentret går du till **sidan** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Konfigurera</a> domäner.</span><span class="sxs-lookup"><span data-stu-id="5a7cd-118">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
::: moniker range="o365-germany"

1. <span data-ttu-id="5a7cd-119">I administrationscentret går du till **sidan** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Konfigurera</a> domäner.</span><span class="sxs-lookup"><span data-stu-id="5a7cd-119">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5a7cd-120">I administrationscentret går du till **sidan** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Konfigurera</a> domäner.</span><span class="sxs-lookup"><span data-stu-id="5a7cd-120">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="5a7cd-121">Välj en domän på sidan **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="5a7cd-121">On the **Domains** page, select your domain.</span></span> 
    
3. <span data-ttu-id="5a7cd-122">Under **Obligatoriska DNS-inställningar** visas DNS-posterna som ska läggas till.</span><span class="sxs-lookup"><span data-stu-id="5a7cd-122">Under **Required DNS settings**, you'll see the DNS records to add.</span></span>
    
    <span data-ttu-id="5a7cd-123">Du behöver ha den här informationen tillgänglig när du gör ändringar hos din DNS-värd, så att du kan kopiera och klistra in värdena.</span><span class="sxs-lookup"><span data-stu-id="5a7cd-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="5a7cd-124">Grupperna av DNS-poster som visas på sidan är beroende av dina val som visas under **Domänsyfte**.</span><span class="sxs-lookup"><span data-stu-id="5a7cd-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="5a7cd-125">Gå till [Skapa DNS-poster](create-dns-records-at-any-dns-hosting-provider.md)hos en DNS-värd och välj sedan din DNS-värd i listan med registratorer om du vill se stegvisa instruktioner för hur du lägger till poster på DNS-värdens webbplats.</span><span class="sxs-lookup"><span data-stu-id="5a7cd-125">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and then select your DNS host from the list of registrars to see step-by-step instructions for adding records at that DNS host's website.</span></span>
    
5. <span data-ttu-id="5a7cd-126">Följ stegen för att skapa posterna hos din DNS-värd.</span><span class="sxs-lookup"><span data-stu-id="5a7cd-126">Follow the steps for creating the records at your DNS host.</span></span>

## <a name="related-content"></a><span data-ttu-id="5a7cd-127">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="5a7cd-127">Related content</span></span>

<span data-ttu-id="5a7cd-128">[Vanliga frågor och svar](../setup/domains-faq.yml) om domäner (artikel)</span><span class="sxs-lookup"><span data-stu-id="5a7cd-128">[Domains FAQ](../setup/domains-faq.yml) (article)</span></span>

<span data-ttu-id="5a7cd-129">[Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster](find-and-fix-issues.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="5a7cd-129">[Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article)</span></span>

<span data-ttu-id="5a7cd-130">[Hantera domäner](index.yml) (länksida)</span><span class="sxs-lookup"><span data-stu-id="5a7cd-130">[Manage domains](index.yml) (link page)</span></span>