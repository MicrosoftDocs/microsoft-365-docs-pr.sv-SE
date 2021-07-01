---
title: Hitta din domänregistrator
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: Lär dig hur du hittar din domänregistrator och DNS-värdtjänst med InterNIC-sökning.
ms.openlocfilehash: 77e4776946d51cb4f8dfe1a746e85d74a9e0a700
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228033"
---
# <a name="find-your-domain-registrar"></a><span data-ttu-id="cebca-103">Hitta din domänregistrator</span><span class="sxs-lookup"><span data-stu-id="cebca-103">Find your domain registrar</span></span>

 <span data-ttu-id="cebca-104">**[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="cebca-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>

## <a name="domain-registrar"></a><span data-ttu-id="cebca-105">Domänregistrator</span><span class="sxs-lookup"><span data-stu-id="cebca-105">Domain registrar</span></span>

### <a name="find-your-domain-name-registrar"></a><span data-ttu-id="cebca-106">Hitta din domännamnsregistrator</span><span class="sxs-lookup"><span data-stu-id="cebca-106">Find your domain name registrar</span></span>

> [!NOTE]
> <span data-ttu-id="cebca-107">Bara domäner som slutar med *.COM*, *.NET* och *.EDU* fungerar med det här verktyget.</span><span class="sxs-lookup"><span data-stu-id="cebca-107">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>

1. <span data-ttu-id="cebca-p101">På [söksidan för InterNIC](https://go.microsoft.com/fwlink/p/?LinkId=402770), i rutan **Whois-sökning** anger du din domän, till exempel  *contoso.com.*</span><span class="sxs-lookup"><span data-stu-id="cebca-p101">On the [InterNIC search page](https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain. For example,  *contoso.com.*</span></span>

2. <span data-ttu-id="cebca-110">Välj alternativet **Domän** och välj sedan **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="cebca-110">Select the **Domain** option, and then select **Submit**.</span></span>

3. <span data-ttu-id="cebca-p102">På sidan **Whois sökresultat** letar du upp rutan **Registrator**. Här hittar du den organisation som tillhandahåller registratorstjänsten för din domän.</span><span class="sxs-lookup"><span data-stu-id="cebca-p102">On the **Whois Search Results** page, locate the **Registrar** entry. This entry lists the organization that provides registrar service for your domain.</span></span>

## <a name="dns-hosting-provider"></a><span data-ttu-id="cebca-113">DNS-värdtjänst</span><span class="sxs-lookup"><span data-stu-id="cebca-113">DNS hosting provider</span></span>

### <a name="find-your-dns-hosting-provider"></a><span data-ttu-id="cebca-114">Hitta din DNS-värdtjänst</span><span class="sxs-lookup"><span data-stu-id="cebca-114">Find your DNS hosting provider</span></span>

> [!NOTE]
> <span data-ttu-id="cebca-115">Bara domäner som slutar med *.COM*, *.NET* och *.EDU* fungerar med det här verktyget.</span><span class="sxs-lookup"><span data-stu-id="cebca-115">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>

1. <span data-ttu-id="cebca-p103">På [söksidan för InterNIC](https://go.microsoft.com/fwlink/p/?LinkId=402770), i rutan **Whois-sökning** anger du din domän, till exempel contoso.com.</span><span class="sxs-lookup"><span data-stu-id="cebca-p103">On the [InterNIC search page](https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain. For example, contoso.com.</span></span>

2. <span data-ttu-id="cebca-118">Välj alternativet **Domain** (Domän) och välj sedan **Submit** (Skicka).</span><span class="sxs-lookup"><span data-stu-id="cebca-118">Select the **Domain** option, and then select **Submit**.</span></span>

3. <span data-ttu-id="cebca-119">På sidan **Whois Search Results** (Whois-sökresultat) söker du efter den första **Name Server** (Namnserver)-posten.</span><span class="sxs-lookup"><span data-stu-id="cebca-119">On the **Whois Search Results** page, locate the first **Name Server** entry.</span></span>

4. <span data-ttu-id="cebca-p104">Kopiera den namnserverinformation (NS) som visas efter kolonet (:) och klistra in den i rutan **Sök** längst upp på sidan. Välj **Namnserver** och välj sedan **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="cebca-p104">Copy the name server (NS) information that appears after the colon (:), and then paste it into the **Search** box at the top of the page. Select **Nameserver**, and then select **Submit**.</span></span>

5. <span data-ttu-id="cebca-p105">På sidan **Whois Search Results** (Whois-sökresultat) letar du upp rutan **Registrar** (Registrator). Här hittar du namnet på den DNS-tjänstleverantör som äger din domäns namnserver.</span><span class="sxs-lookup"><span data-stu-id="cebca-p105">On the **Whois Search Results** page, locate the **Registrar** entry. This entry lists your DNS hosting provider, the DNS provider who owns the name server for your domain.</span></span>

---

