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
ms.openlocfilehash: def9fbe201e158f1e071a67caeaf29ed26732f97
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256849"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a><span data-ttu-id="c7376-103">Samla den information du behöver för att skapa DNS-poster</span><span class="sxs-lookup"><span data-stu-id="c7376-103">Gather the information you need to create DNS records</span></span>

 <span data-ttu-id="c7376-104">**[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="c7376-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="c7376-105">Steg 1: Hitta TXT-postvärdet och verifiera</span><span class="sxs-lookup"><span data-stu-id="c7376-105">Step 1: Find the TXT record value and verify</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c7376-106">I Administrationscenter för Microsoft 365 går du till sidan **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains.</a></span><span class="sxs-lookup"><span data-stu-id="c7376-106">In the Microsoft 365 admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c7376-107">I administrationscentret går du till **Inställningar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="c7376-107">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c7376-108">I administrationscentret går du till **Inställningar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="c7376-108">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="c7376-109">På sidan **Domäner** väljer du din domän och sedan **Starta installationen.**</span><span class="sxs-lookup"><span data-stu-id="c7376-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="c7376-110">Du går tillbaka till domäninstallationsguiden för att se det specifika värde som du måste lägga till.</span><span class="sxs-lookup"><span data-stu-id="c7376-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="c7376-111">På sidan **Domain Verification** väljer du Add a TXT record to **the domain's DNS records** och väljer sedan **Continue**.</span><span class="sxs-lookup"><span data-stu-id="c7376-111">On the **Domain Verification** page, select **Add a TXT record to the domain's DNS records**, then select **Continue**.</span></span>
    
4. <span data-ttu-id="c7376-112">Kopiera **TXT-värdet som** visas.</span><span class="sxs-lookup"><span data-stu-id="c7376-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="c7376-113">Så här ser det ut: **MS=msXXXXXXXX.**</span><span class="sxs-lookup"><span data-stu-id="c7376-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="c7376-114">Gå till [Lägg till DNS-poster för att](create-dns-records-at-any-dns-hosting-provider.md)ansluta din domän och följ anvisningarna för att lägga till poster på DNS-värdens webbplats.</span><span class="sxs-lookup"><span data-stu-id="c7376-114">Go to [Add DNS records to connect your domain](create-dns-records-at-any-dns-hosting-provider.md), and follow the steps to add records at your DNS host's website.</span></span>
    
6. <span data-ttu-id="c7376-115">Följ stegen för att skapa TXT-posten (eller MX-posten) hos din DNS-värd och verifiera sedan domänen i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c7376-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Microsoft 365.</span></span>

7. <span data-ttu-id="c7376-116">Ta bort TXT-posten (eller MX-posten) från din DNS-värd när domänen har verifierats i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c7376-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Microsoft 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="c7376-117">Steg 2: Hitta MX-postvärdet för e-post och mycket mer</span><span class="sxs-lookup"><span data-stu-id="c7376-117">Step 2: Find the MX record value for email and more</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c7376-118">I Administrationscenter för Microsoft 365 går du till sidan **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains.</a></span><span class="sxs-lookup"><span data-stu-id="c7376-118">In the Microsoft 365 admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
::: moniker range="o365-germany"

1. <span data-ttu-id="c7376-119">I administrationscentret går du till **Inställningar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="c7376-119">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c7376-120">I administrationscentret går du till **Inställningar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a>.</span><span class="sxs-lookup"><span data-stu-id="c7376-120">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="c7376-121">Välj en domän på sidan **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="c7376-121">On the **Domains** page, select your domain.</span></span>
    
3. <span data-ttu-id="c7376-122">Välj **Manage DNS**, select More Options **Add** your own  >  **DNS** and select Continue **to** see the DNS records to add.</span><span class="sxs-lookup"><span data-stu-id="c7376-122">Choose  **Manage DNS**, select **More Options** > **Add your own DNS** and select **Continue** to see the DNS records to add.</span></span>
    
    <span data-ttu-id="c7376-123">Du behöver ha den här informationen tillgänglig när du gör ändringar hos din DNS-värd, så att du kan kopiera och klistra in värdena.</span><span class="sxs-lookup"><span data-stu-id="c7376-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="c7376-124">Grupperna av DNS-poster som visas på sidan är beroende av dina val som visas under **Domänsyfte**.</span><span class="sxs-lookup"><span data-stu-id="c7376-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="c7376-125">Gå till [Lägg till DNS-poster för att](create-dns-records-at-any-dns-hosting-provider.md)ansluta din domän och följ anvisningarna för att lägga till poster på DNS-värdens webbplats.</span><span class="sxs-lookup"><span data-stu-id="c7376-125">Go to [Add DNS records to connect your domain](create-dns-records-at-any-dns-hosting-provider.md), and follow the steps to add records at your DNS host's website.</span></span>

5. <span data-ttu-id="c7376-126">Följ stegen för att skapa posterna hos din DNS-värd.</span><span class="sxs-lookup"><span data-stu-id="c7376-126">Follow the steps for creating the records at your DNS host.</span></span>

## <a name="related-content"></a><span data-ttu-id="c7376-127">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="c7376-127">Related content</span></span>

<span data-ttu-id="c7376-128">[Vanliga frågor och svar om domäner](../setup/domains-faq.yml) (artikel)</span><span class="sxs-lookup"><span data-stu-id="c7376-128">[Domains FAQ](../setup/domains-faq.yml) (article)</span></span>\
<span data-ttu-id="c7376-129">[Hitta och åtgärda problem när du har lagt till din domän eller DNS-register](find-and-fix-issues.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="c7376-129">[Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article)</span></span>\
<span data-ttu-id="c7376-130">[Hantera domäner](index.yml) (länksida)</span><span class="sxs-lookup"><span data-stu-id="c7376-130">[Manage domains](index.yml) (link page)</span></span>