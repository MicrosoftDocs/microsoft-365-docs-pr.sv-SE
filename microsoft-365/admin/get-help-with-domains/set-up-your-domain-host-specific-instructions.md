---
title: Konfigurera din domän (tjänstspecifika instruktioner)
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
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: ae950c9e-e8d9-4108-b0cb-449156998580
description: Lär dig hur du hanterar dina egna DNS-poster eller låter Microsoft hantera dina DNS-poster åt dig.
ms.openlocfilehash: ddf3b7faf7ac336b2d7caf3b7d35d9a4f101b122
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126365"
---
# <a name="set-up-your-domain-host-specific-instructions"></a><span data-ttu-id="92301-103">Konfigurera din domän (tjänstspecifika instruktioner)</span><span class="sxs-lookup"><span data-stu-id="92301-103">Set up your domain (host-specific instructions)</span></span>

<span data-ttu-id="92301-104">Om du vill börja använda en egen domän (contoso.com) med Microsoft 365 måste du verifiera domänen och konfigurera domänens DNS-poster.</span><span class="sxs-lookup"><span data-stu-id="92301-104">To start using a custom domain (contoso.com) with Microsoft 365, you need to verify your domain and configure your domain's DNS records.</span></span> 
  
<span data-ttu-id="92301-105">Du kan lägga till och hantera DNS-poster med de administrativa verktygen hos domänvärden, eller ge Microsoft kontroll över dina domänposter så konfigureras de åt dig.</span><span class="sxs-lookup"><span data-stu-id="92301-105">You can add and manage DNS records using the administrative tools at your domain host, or give Microsoft control of your domain records and we'll set them up for you.</span></span>
  
<span data-ttu-id="92301-106">Välj din domänvärd nedan för de exakta stegen.</span><span class="sxs-lookup"><span data-stu-id="92301-106">Select your domain host below for the exact steps.</span></span> <span data-ttu-id="92301-107">Om du inte är säker på vem din värd är kan du gå [till Hitta din domänregistrator.](find-your-domain-registrar.md)</span><span class="sxs-lookup"><span data-stu-id="92301-107">If you're not sure who your host is, see [Find your domain registrar](find-your-domain-registrar.md).</span></span>
  

## <a name="let-microsoft-365-manage-your-dns-records"></a><span data-ttu-id="92301-108">Låt Microsoft 365 hantera dina DNS-poster</span><span class="sxs-lookup"><span data-stu-id="92301-108">Let Microsoft 365 manage your DNS records</span></span>

||
|---|---|
|[<span data-ttu-id="92301-109">1&1 I KANT</span><span class="sxs-lookup"><span data-stu-id="92301-109">1&1 IONOS</span></span>](../dns/change-nameservers-at-1-1-internet.md) |
|[<span data-ttu-id="92301-110">Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="92301-110">Amazon Web Services (AWS)</span></span>](../dns/change-nameservers-at-aws.md) |
 [<span data-ttu-id="92301-111">Bluehost</span><span class="sxs-lookup"><span data-stu-id="92301-111">Bluehost</span></span>](../dns/change-nameservers-at-bluehost.md)|
|[<span data-ttu-id="92301-112">Google Domains</span><span class="sxs-lookup"><span data-stu-id="92301-112">Google   Domains</span></span>](../dns/change-nameservers-at-google-domains.md) |
|[<span data-ttu-id="92301-113">Hostgator   </span><span class="sxs-lookup"><span data-stu-id="92301-113">Hostgator   </span></span>](../dns/change-nameservers-at-hostgator.md)  |  
|[<span data-ttu-id="92301-114">MyDomain</span><span class="sxs-lookup"><span data-stu-id="92301-114">MyDomain</span></span>](../dns/change-nameservers-at-mydomain.md) | 
|[<span data-ttu-id="92301-115">Namecheap</span><span class="sxs-lookup"><span data-stu-id="92301-115">Namecheap</span></span>](../dns/change-nameservers-at-namecheap.md)|
|[<span data-ttu-id="92301-116">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="92301-116">Network Solutions</span></span>](../dns/change-nameservers-at-network-solutions.md) |  

<span data-ttu-id="92301-117">Eller lär dig hur du [ändrar namnservrar för att konfigurera Microsoft 365 med valfri domänregistrator.](change-nameservers-at-any-domain-registrar.md)</span><span class="sxs-lookup"><span data-stu-id="92301-117">Or, learn how to [change nameservers to set up Microsoft 365 with any domain registrar](change-nameservers-at-any-domain-registrar.md).</span></span>

## <a name="manage-your-own-dns-records"></a><span data-ttu-id="92301-118">Hantera dina egna DNS-poster</span><span class="sxs-lookup"><span data-stu-id="92301-118">Manage your own DNS records</span></span>

|                           |                          |
|---------------------------|--------------------------|
| [<span data-ttu-id="92301-119">1&1 I KANT</span><span class="sxs-lookup"><span data-stu-id="92301-119">1&1 IONOS</span></span>](../dns/create-dns-records-at-1-1-internet.md) | [<span data-ttu-id="92301-120">Hover</span><span class="sxs-lookup"><span data-stu-id="92301-120">Hover</span></span>](../dns/create-dns-records-at-hover.md) |
| [<span data-ttu-id="92301-121">123-reg.co.uk</span><span class="sxs-lookup"><span data-stu-id="92301-121">123-reg.co.uk</span></span>](../dns/create-dns-records-at-123-reg-co-uk.md) | [<span data-ttu-id="92301-122">Hanteras av Google (eNom)</span><span class="sxs-lookup"><span data-stu-id="92301-122">Managed   by Google (eNom)</span></span>](../dns/create-dns-records-for-domain-managed-by-google-enom.md)|
| [<span data-ttu-id="92301-123">Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="92301-123">Amazon Web Services (AWS)</span></span>](../dns/create-dns-records-at-aws.md) | [<span data-ttu-id="92301-124">MyDomain</span><span class="sxs-lookup"><span data-stu-id="92301-124">MyDomain</span></span>](../dns/create-dns-records-at-mydomain.md) |
| [<span data-ttu-id="92301-125">Azure DNS-zoner</span><span class="sxs-lookup"><span data-stu-id="92301-125">Azure DNS zones</span></span>](../dns/create-dns-records-for-azure-dns-zones.md) | [<span data-ttu-id="92301-126">name.com</span><span class="sxs-lookup"><span data-stu-id="92301-126">name.com</span></span>](../dns/create-dns-records-at-name-com.md) |
| [<span data-ttu-id="92301-127">Bluehost</span><span class="sxs-lookup"><span data-stu-id="92301-127">Bluehost</span></span>](../dns/create-dns-records-at-bluehost.md) | [<span data-ttu-id="92301-128">Namecheap</span><span class="sxs-lookup"><span data-stu-id="92301-128">Namecheap</span></span>](../dns/create-dns-records-at-namecheap.md)|
| [<span data-ttu-id="92301-129">Cloudflare</span><span class="sxs-lookup"><span data-stu-id="92301-129">Cloudflare</span></span>](../dns/create-dns-records-at-cloudflare.md)| [<span data-ttu-id="92301-130">Names.co.uk</span><span class="sxs-lookup"><span data-stu-id="92301-130">Names.co.uk</span></span>](../dns/create-dns-records-at-names-co-uk.md) |
|  [<span data-ttu-id="92301-131">Crazy Domains</span><span class="sxs-lookup"><span data-stu-id="92301-131">Crazy Domains</span></span>](../dns/create-dns-records-at-crazy-domains.md)| [<span data-ttu-id="92301-132">Netregistry</span><span class="sxs-lookup"><span data-stu-id="92301-132">Netregistry</span></span>](../dns/create-dns-records-at-netregistry.md) |
|[<span data-ttu-id="92301-133">DNSMadeEasy</span><span class="sxs-lookup"><span data-stu-id="92301-133">DNSMadeEasy</span></span>](../dns/create-dns-records-at-dnsmadeeasy.md) | [<span data-ttu-id="92301-134">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="92301-134">Network   Solutions</span></span>](../dns/create-dns-records-at-network-solutions.md) |
|[<span data-ttu-id="92301-135">Dreamhost</span><span class="sxs-lookup"><span data-stu-id="92301-135">Dreamhost</span></span>](../dns/create-dns-records-at-dreamhost.md)  | [<span data-ttu-id="92301-136">OVH</span><span class="sxs-lookup"><span data-stu-id="92301-136">OVH</span></span>](../dns/create-dns-records-at-ovh.md) |
|  [<span data-ttu-id="92301-137">Dyn.com</span><span class="sxs-lookup"><span data-stu-id="92301-137">Dyn.com</span></span>](../dns/create-dns-records-at-dyn-com.md) | [<span data-ttu-id="92301-138">Register.com</span><span class="sxs-lookup"><span data-stu-id="92301-138">Register.com</span></span>](../dns/create-dns-records-at-register-com.md) |
| [<span data-ttu-id="92301-139">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="92301-139">eNomCentral</span></span>](../dns/create-dns-records-at-enomcentral.md)| [<span data-ttu-id="92301-140">Register365 för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="92301-140">Register365 for Microsoft 365</span></span>](../dns/create-dns-records-at-register365.md)  |
| [<span data-ttu-id="92301-141">Freenom</span><span class="sxs-lookup"><span data-stu-id="92301-141">Freenom</span></span>](../dns/create-dns-records-at-freenom.md) | [<span data-ttu-id="92301-142"> web.com </span><span class="sxs-lookup"><span data-stu-id="92301-142"> web.com </span></span>](../dns/create-dns-records-at-web-com.md)|
|[<span data-ttu-id="92301-143">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="92301-143">GoDaddy</span></span>](../dns/create-dns-records-at-godaddy.md)|[<span data-ttu-id="92301-144"> Windows-baserad DNS</span><span class="sxs-lookup"><span data-stu-id="92301-144"> Windows-based DNS</span></span>](../dns/create-dns-records-using-windows-based-dns.md)   |
| [<span data-ttu-id="92301-145">Google Domains</span><span class="sxs-lookup"><span data-stu-id="92301-145">Google Domains</span></span>](../dns/create-dns-records-at-google-domains.md) |[<span data-ttu-id="92301-146">Wix</span><span class="sxs-lookup"><span data-stu-id="92301-146">Wix</span></span>](../dns/create-dns-records-at-wix.md) |
|[<span data-ttu-id="92301-147">Hostgator</span><span class="sxs-lookup"><span data-stu-id="92301-147">Hostgator</span></span>](../dns/create-dns-records-at-hostgator.md)  | [<span data-ttu-id="92301-148">Yahoo!   Small Business</span><span class="sxs-lookup"><span data-stu-id="92301-148">Yahoo!   Small Business</span></span>](../dns/create-dns-records-at-yahoo-small-business.md)  |

[<span data-ttu-id="92301-149">Jag behöver allmänna instruktioner eftersom min domänvärd inte finns med på den här listan. </span><span class="sxs-lookup"><span data-stu-id="92301-149">I need general instructions, because my domain host isn't on this list. </span></span>](create-dns-records-at-any-dns-hosting-provider.md)
   
