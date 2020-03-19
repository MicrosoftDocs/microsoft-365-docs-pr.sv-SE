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
ms.openlocfilehash: 7b995aedc21305367e4a6621781e138d0d60efd1
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42808198"
---
# <a name="gather-the-information-you-need-to-create-office-365-dns-records"></a><span data-ttu-id="2aef1-103">Samla den information du behöver för att skapa DNS-poster i Office 365</span><span class="sxs-lookup"><span data-stu-id="2aef1-103">Gather the information you need to create Office 365 DNS records</span></span>

 <span data-ttu-id="2aef1-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="2aef1-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="2aef1-105">Steg 1: Hitta TXT-postvärdet och verifiera</span><span class="sxs-lookup"><span data-stu-id="2aef1-105">Step 1: Find the TXT record value and verify</span></span>

1. <span data-ttu-id="2aef1-106">Gå till sidan **Installationsdomäner** \> i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">administrationscentret</a> för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2aef1-106">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
    <span data-ttu-id="2aef1-107">Om du använder Office 365 Tyskland går du till den här <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">domänsidan.</a></span><span class="sxs-lookup"><span data-stu-id="2aef1-107">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span> 
    
    <span data-ttu-id="2aef1-108">Om du använder Office 365 som drivs av 21Vianet går du till den här <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">domänsidan.</a></span><span class="sxs-lookup"><span data-stu-id="2aef1-108">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="2aef1-109">Välj domänen på sidan **Domäner** och välj sedan **Starta installationsprogrammet**.</span><span class="sxs-lookup"><span data-stu-id="2aef1-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="2aef1-110">Du går tillbaka till domäninstallationsguiden för att se det specifika värde som du måste lägga till.</span><span class="sxs-lookup"><span data-stu-id="2aef1-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="2aef1-111">På **sidan Verifiera domän** väljer du **Lägg till en TXT-post i stället**och väljer sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="2aef1-111">On the **Verify domain** page, select **Add a TXT record instead**, then select **Next**.</span></span>
    
4. <span data-ttu-id="2aef1-112">Kopiera **TXT-värdet** som visas.</span><span class="sxs-lookup"><span data-stu-id="2aef1-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="2aef1-113">Det ser ut så här: **MS = msXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="2aef1-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="2aef1-114">Gå till [Skapa DNS-poster hos valfri DNS-värd](create-dns-records-at-any-dns-hosting-provider.md)och välj din DNS-värd från listan över registratorer för att se steg-för-steg-instruktioner.</span><span class="sxs-lookup"><span data-stu-id="2aef1-114">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and select your DNS host from the list of registrars to see the step-by-step instructions.</span></span>
    
6. <span data-ttu-id="2aef1-115">Följ stegen för att skapa TXT-posten (eller MX-posten) hos din DNS-värd och verifiera sedan domänen i Office 365.</span><span class="sxs-lookup"><span data-stu-id="2aef1-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Office 365.</span></span>

7. <span data-ttu-id="2aef1-116">Ta bort TXT-posten (eller MX-posten) från DNS-värden när domänen har verifierats i Office 365.</span><span class="sxs-lookup"><span data-stu-id="2aef1-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Office 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="2aef1-117">Steg 2: Hitta MX-postvärdet för e-post med mera</span><span class="sxs-lookup"><span data-stu-id="2aef1-117">Step 2: Find the MX record value for email and more</span></span>

1. <span data-ttu-id="2aef1-118">Gå till sidan **Installationsdomäner** \> i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">administrationscentret</a> för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2aef1-118">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
    <span data-ttu-id="2aef1-119">Om du använder Office 365 Tyskland går du till den här <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">domänsidan.</a></span><span class="sxs-lookup"><span data-stu-id="2aef1-119">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span> 
    
    <span data-ttu-id="2aef1-120">Om du använder Office 365 som drivs av 21Vianet går du till den här <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">domänsidan.</a></span><span class="sxs-lookup"><span data-stu-id="2aef1-120">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="2aef1-121">Välj en domän på sidan **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="2aef1-121">On the **Domains** page, select your domain.</span></span> 
    
3. <span data-ttu-id="2aef1-122">Under **Obligatoriska DNS-inställningar** visas DNS-posterna som ska läggas till.</span><span class="sxs-lookup"><span data-stu-id="2aef1-122">Under **Required DNS settings**, you'll see the DNS records to add.</span></span>
    
    <span data-ttu-id="2aef1-123">Du behöver ha den här informationen tillgänglig när du gör ändringar hos din DNS-värd, så att du kan kopiera och klistra in värdena.</span><span class="sxs-lookup"><span data-stu-id="2aef1-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="2aef1-124">Grupperna av DNS-poster som visas på sidan är beroende av dina val som visas under **Domänsyfte**.</span><span class="sxs-lookup"><span data-stu-id="2aef1-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="2aef1-125">Gå till [Skapa DNS-poster hos valfri DNS-värd och](create-dns-records-at-any-dns-hosting-provider.md)välj sedan din DNS-värd från listan över registratorer för att se steg-för-steg-instruktioner för att lägga till poster på DNS-värdens webbplats.</span><span class="sxs-lookup"><span data-stu-id="2aef1-125">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and then select your DNS host from the list of registrars to see step-by-step instructions for adding records at that DNS host's website.</span></span>
    
5. <span data-ttu-id="2aef1-126">Följ stegen för att skapa posterna hos din DNS-värd.</span><span class="sxs-lookup"><span data-stu-id="2aef1-126">Follow the steps for creating the records at your DNS host.</span></span>
