---
title: Hitta din domänregistrator för Office 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Priority
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
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: Lär dig hur du hittar din domänregistrator och DNS-värdtjänst med InterNIC-sökning.
ms.openlocfilehash: 058eb4468e073b6929fbc763b3d9bdb189063213
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42812342"
---
# <a name="find-your-domain-registrar-for-office-365"></a><span data-ttu-id="d342f-103">Hitta din domänregistrator för Office 365</span><span class="sxs-lookup"><span data-stu-id="d342f-103">Find your domain registrar for Office 365</span></span>

 <span data-ttu-id="d342f-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="d342f-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
## <a name="domain-registrar"></a><span data-ttu-id="d342f-105">Domänregistrator</span><span class="sxs-lookup"><span data-stu-id="d342f-105">Domain registrar</span></span>
  
### <a name="find-your-domain-name-registrar"></a><span data-ttu-id="d342f-106">Hitta din domännamnsregistrator</span><span class="sxs-lookup"><span data-stu-id="d342f-106">Find your domain name registrar</span></span>

>[!NOTE]
> <span data-ttu-id="d342f-107">Bara domäner som slutar med *.COM*, *.NET* och *.EDU* fungerar med det här verktyget.</span><span class="sxs-lookup"><span data-stu-id="d342f-107">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="d342f-108">På [söksidan InterNIC](https://go.microsoft.com/fwlink/p/?LinkId=402770), i rutan **Whois Search** (Whois-sökning), anger du din domän.</span><span class="sxs-lookup"><span data-stu-id="d342f-108">On the [InterNIC search page](https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain.</span></span> <span data-ttu-id="d342f-109">Till exempel *contoso.com.*</span><span class="sxs-lookup"><span data-stu-id="d342f-109">For example,  *contoso.com.*</span></span> 
    
2. <span data-ttu-id="d342f-110">Välj alternativet **Domain** (Domän) och välj sedan **Submit** (Skicka).</span><span class="sxs-lookup"><span data-stu-id="d342f-110">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="d342f-111">På sidan **Whois Search Results** (Whois-sökresultat) letar du upp rutan **Registrar** (Registrator).</span><span class="sxs-lookup"><span data-stu-id="d342f-111">On the **Whois Search Results** page, locate the **Registrar** entry.</span></span> <span data-ttu-id="d342f-112">Här hittar du den organisation som tillhandahåller registreringstjänsten för din domän.</span><span class="sxs-lookup"><span data-stu-id="d342f-112">This entry lists the organization that provides registrar service for your domain.</span></span> 
    
## <a name="dns-hosting-provider"></a><span data-ttu-id="d342f-113">DNS-värdtjänst</span><span class="sxs-lookup"><span data-stu-id="d342f-113">DNS hosting provider</span></span>
  
### <a name="find-your-dns-hosting-provider"></a><span data-ttu-id="d342f-114">Hitta din DNS-värdtjänst</span><span class="sxs-lookup"><span data-stu-id="d342f-114">Find your DNS hosting provider</span></span>

>[!NOTE]
> <span data-ttu-id="d342f-115">Bara domäner som slutar med *.COM*, *.NET* och *.EDU* fungerar med det här verktyget.</span><span class="sxs-lookup"><span data-stu-id="d342f-115">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="d342f-116">På [söksidan InterNIC]( https://go.microsoft.com/fwlink/p/?LinkId=402770), i rutan **Whois Search** (Whois-sökning), anger du din domän.</span><span class="sxs-lookup"><span data-stu-id="d342f-116">On the [InterNIC search page]( https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain.</span></span> <span data-ttu-id="d342f-117">Till exempel contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d342f-117">For example, contoso.com.</span></span> 
    
2. <span data-ttu-id="d342f-118">Välj alternativet **Domain** (Domän) och välj sedan **Submit** (Skicka).</span><span class="sxs-lookup"><span data-stu-id="d342f-118">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="d342f-119">På sidan **Whois Search Results** (Whois-sökresultat) söker du efter den första **Name Server** (Namnserver)-posten.</span><span class="sxs-lookup"><span data-stu-id="d342f-119">On the **Whois Search Results** page, locate the first **Name Server** entry.</span></span> 
    
4. <span data-ttu-id="d342f-120">Kopiera den namnserverinformation som visas efter kolonet (:) och klistra in den i rutan **Search** (Sök) längst upp på sidan.</span><span class="sxs-lookup"><span data-stu-id="d342f-120">Copy the name server (NS) information that appears after the colon (:), and then paste it into the **Search** box at the top of the page.</span></span> <span data-ttu-id="d342f-121">Välj **Nameserver** (Namnserver) och välj sedan **Submit** (Skicka).</span><span class="sxs-lookup"><span data-stu-id="d342f-121">Select **Nameserver**, and then select **Submit**.</span></span>
    
5. <span data-ttu-id="d342f-p105">På sidan **Whois Search Results** (Whois-sökresultat) letar du upp rutan **Registrar** (Registrator). Här hittar du namnet på den DNS-tjänstleverantör som äger din domäns namnserver.</span><span class="sxs-lookup"><span data-stu-id="d342f-p105">On the **Whois Search Results** page, locate the **Registrar** entry. This entry lists your DNS hosting provider, the DNS provider who owns the name server for your domain.</span></span> 
    
---

