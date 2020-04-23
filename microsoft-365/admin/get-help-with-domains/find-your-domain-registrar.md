---
title: Hitta din domänregistrator
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
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
ms.openlocfilehash: 234578c5622a883296a001ce7f226627dd9d93b5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628464"
---
# <a name="find-your-domain-registrar"></a><span data-ttu-id="c9665-103">Hitta din domänregistrator</span><span class="sxs-lookup"><span data-stu-id="c9665-103">Find your domain registrar</span></span>

 <span data-ttu-id="c9665-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="c9665-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
## <a name="domain-registrar"></a><span data-ttu-id="c9665-105">Domänregistrator</span><span class="sxs-lookup"><span data-stu-id="c9665-105">Domain registrar</span></span>
  
### <a name="find-your-domain-name-registrar"></a><span data-ttu-id="c9665-106">Hitta din domännamnsregistrator</span><span class="sxs-lookup"><span data-stu-id="c9665-106">Find your domain name registrar</span></span>

>[!NOTE]
> <span data-ttu-id="c9665-107">Bara domäner som slutar med *.COM*, *.NET* och *.EDU* fungerar med det här verktyget.</span><span class="sxs-lookup"><span data-stu-id="c9665-107">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="c9665-108">På [söksidan InterNIC](https://go.microsoft.com/fwlink/p/?LinkId=402770), i rutan **Whois Search** (Whois-sökning), anger du din domän.</span><span class="sxs-lookup"><span data-stu-id="c9665-108">On the [InterNIC search page](https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain.</span></span> <span data-ttu-id="c9665-109">Till exempel *contoso.com.*</span><span class="sxs-lookup"><span data-stu-id="c9665-109">For example,  *contoso.com.*</span></span> 
    
2. <span data-ttu-id="c9665-110">Välj alternativet **Domain** (Domän) och välj sedan **Submit** (Skicka).</span><span class="sxs-lookup"><span data-stu-id="c9665-110">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="c9665-111">På sidan **Whois Search Results** (Whois-sökresultat) letar du upp rutan **Registrar** (Registrator).</span><span class="sxs-lookup"><span data-stu-id="c9665-111">On the **Whois Search Results** page, locate the **Registrar** entry.</span></span> <span data-ttu-id="c9665-112">Här hittar du den organisation som tillhandahåller registreringstjänsten för din domän.</span><span class="sxs-lookup"><span data-stu-id="c9665-112">This entry lists the organization that provides registrar service for your domain.</span></span> 
    
## <a name="dns-hosting-provider"></a><span data-ttu-id="c9665-113">DNS-värdtjänst</span><span class="sxs-lookup"><span data-stu-id="c9665-113">DNS hosting provider</span></span>
  
### <a name="find-your-dns-hosting-provider"></a><span data-ttu-id="c9665-114">Hitta din DNS-värdtjänst</span><span class="sxs-lookup"><span data-stu-id="c9665-114">Find your DNS hosting provider</span></span>

>[!NOTE]
> <span data-ttu-id="c9665-115">Bara domäner som slutar med *.COM*, *.NET* och *.EDU* fungerar med det här verktyget.</span><span class="sxs-lookup"><span data-stu-id="c9665-115">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="c9665-116">På [söksidan InterNIC]( https://go.microsoft.com/fwlink/p/?LinkId=402770), i rutan **Whois Search** (Whois-sökning), anger du din domän.</span><span class="sxs-lookup"><span data-stu-id="c9665-116">On the [InterNIC search page]( https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain.</span></span> <span data-ttu-id="c9665-117">Till exempel contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c9665-117">For example, contoso.com.</span></span> 
    
2. <span data-ttu-id="c9665-118">Välj alternativet **Domain** (Domän) och välj sedan **Submit** (Skicka).</span><span class="sxs-lookup"><span data-stu-id="c9665-118">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="c9665-119">På sidan **Whois Search Results** (Whois-sökresultat) söker du efter den första **Name Server** (Namnserver)-posten.</span><span class="sxs-lookup"><span data-stu-id="c9665-119">On the **Whois Search Results** page, locate the first **Name Server** entry.</span></span> 
    
4. <span data-ttu-id="c9665-120">Kopiera den namnserverinformation som visas efter kolonet (:) och klistra in den i rutan **Search** (Sök) längst upp på sidan.</span><span class="sxs-lookup"><span data-stu-id="c9665-120">Copy the name server (NS) information that appears after the colon (:), and then paste it into the **Search** box at the top of the page.</span></span> <span data-ttu-id="c9665-121">Välj **Nameserver** (Namnserver) och välj sedan **Submit** (Skicka).</span><span class="sxs-lookup"><span data-stu-id="c9665-121">Select **Nameserver**, and then select **Submit**.</span></span>
    
5. <span data-ttu-id="c9665-p105">På sidan **Whois Search Results** (Whois-sökresultat) letar du upp rutan **Registrar** (Registrator). Här hittar du namnet på den DNS-tjänstleverantör som äger din domäns namnserver.</span><span class="sxs-lookup"><span data-stu-id="c9665-p105">On the **Whois Search Results** page, locate the **Registrar** entry. This entry lists your DNS hosting provider, the DNS provider who owns the name server for your domain.</span></span> 
    
---

