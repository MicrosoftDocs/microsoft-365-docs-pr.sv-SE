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
- okr_smb
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: ae950c9e-e8d9-4108-b0cb-449156998580
description: Lär dig hur du hanterar dina egna DNS-poster eller låter Microsoft hantera dina DNS-poster åt dig.
ms.openlocfilehash: a22968fdfcdb6be8ecfdc9dde351de034edce4b2
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645305"
---
# <a name="set-up-your-domain-host-specific-instructions"></a><span data-ttu-id="15bbe-103">Konfigurera din domän (tjänstspecifika instruktioner)</span><span class="sxs-lookup"><span data-stu-id="15bbe-103">Set up your domain (host-specific instructions)</span></span>

<span data-ttu-id="15bbe-104">Om du vill börja använda en anpassad domän (contoso.com) med Microsoft 365 måste du verifiera din domän och konfigurera domänens DNS-poster.</span><span class="sxs-lookup"><span data-stu-id="15bbe-104">To start using a custom domain (contoso.com) with Microsoft 365, you need to verify your domain and configure your domain's DNS records.</span></span> 
  
<span data-ttu-id="15bbe-105">Du kan lägga till och hantera DNS-poster med hjälp av administrations verktyg på din domän värd eller ge Microsoft kontroll över dina domän poster och ställa in dem åt dig.</span><span class="sxs-lookup"><span data-stu-id="15bbe-105">You can add and manage DNS records using the administrative tools at your domain host, or give Microsoft control of your domain records and we'll set them up for you.</span></span>
  
<span data-ttu-id="15bbe-106">Välj din domän värd nedan för att få exakta steg.</span><span class="sxs-lookup"><span data-stu-id="15bbe-106">Select your domain host below for the exact steps.</span></span> <span data-ttu-id="15bbe-107">Om du är osäker på vilken värd du använder kan du läsa [hitta din domän registrator](find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="15bbe-107">If you're not sure who your host is, see [Find your domain registrar](find-your-domain-registrar.md).</span></span>
  

## <a name="let-microsoft-365-manage-your-dns-records"></a><span data-ttu-id="15bbe-108">Låt Microsoft 365 hantera dina DNS-poster</span><span class="sxs-lookup"><span data-stu-id="15bbe-108">Let Microsoft 365 manage your DNS records</span></span>

||
|---|---|
|[<span data-ttu-id="15bbe-109">1&1 IONOS</span><span class="sxs-lookup"><span data-stu-id="15bbe-109">1&1 IONOS</span></span>](../dns/change-nameservers-at-1-1-internet.md) |
|[<span data-ttu-id="15bbe-110">Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="15bbe-110">Amazon Web Services (AWS)</span></span>](../dns/change-nameservers-at-aws.md) |
 [<span data-ttu-id="15bbe-111">Bluehost</span><span class="sxs-lookup"><span data-stu-id="15bbe-111">Bluehost</span></span>](../dns/change-nameservers-at-bluehost.md)|
|[<span data-ttu-id="15bbe-112">Google-domäner</span><span class="sxs-lookup"><span data-stu-id="15bbe-112">Google   Domains</span></span>](../dns/change-nameservers-at-google-domains.md) |
|[<span data-ttu-id="15bbe-113">Host Gator   </span><span class="sxs-lookup"><span data-stu-id="15bbe-113">Hostgator   </span></span>](../dns/change-nameservers-at-hostgator.md)  |  
|[<span data-ttu-id="15bbe-114">MyDomain</span><span class="sxs-lookup"><span data-stu-id="15bbe-114">MyDomain</span></span>](../dns/change-nameservers-at-mydomain.md) | 
|[<span data-ttu-id="15bbe-115">NameCheap</span><span class="sxs-lookup"><span data-stu-id="15bbe-115">Namecheap</span></span>](../dns/change-nameservers-at-namecheap.md)|
|[<span data-ttu-id="15bbe-116">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="15bbe-116">Network Solutions</span></span>](../dns/change-nameservers-at-network-solutions.md) |  

<span data-ttu-id="15bbe-117">Eller så kan du [ändra namnservrar för att konfigurera Microsoft 365 med valfri domän registrator](change-nameservers-at-any-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="15bbe-117">Or, learn how to [change nameservers to set up Microsoft 365 with any domain registrar](change-nameservers-at-any-domain-registrar.md).</span></span>

## <a name="manage-your-own-dns-records"></a><span data-ttu-id="15bbe-118">Hantera dina egna DNS-poster</span><span class="sxs-lookup"><span data-stu-id="15bbe-118">Manage your own DNS records</span></span>

|                           |                          |
|---------------------------|--------------------------|
| [<span data-ttu-id="15bbe-119">1&1 IONOS</span><span class="sxs-lookup"><span data-stu-id="15bbe-119">1&1 IONOS</span></span>](../dns/create-dns-records-at-1-1-internet.md) | [<span data-ttu-id="15bbe-120">Hover</span><span class="sxs-lookup"><span data-stu-id="15bbe-120">Hover</span></span>](../dns/create-dns-records-at-hover.md) |
| [<span data-ttu-id="15bbe-121">123-reg.co.uk</span><span class="sxs-lookup"><span data-stu-id="15bbe-121">123-reg.co.uk</span></span>](../dns/create-dns-records-at-123-reg-co-uk.md) | [<span data-ttu-id="15bbe-122">Hanteras av Google (eNom)</span><span class="sxs-lookup"><span data-stu-id="15bbe-122">Managed   by Google (eNom)</span></span>](../dns/create-dns-records-for-domain-managed-by-google-enom.md)|
| [<span data-ttu-id="15bbe-123">Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="15bbe-123">Amazon Web Services (AWS)</span></span>](../dns/create-dns-records-at-aws.md) | [<span data-ttu-id="15bbe-124">MyDomain</span><span class="sxs-lookup"><span data-stu-id="15bbe-124">MyDomain</span></span>](../dns/create-dns-records-at-mydomain.md) |
| [<span data-ttu-id="15bbe-125">Azure DNS-zoner</span><span class="sxs-lookup"><span data-stu-id="15bbe-125">Azure DNS zones</span></span>](../dns/create-dns-records-for-azure-dns-zones.md) | [<span data-ttu-id="15bbe-126">name.com</span><span class="sxs-lookup"><span data-stu-id="15bbe-126">name.com</span></span>](../dns/create-dns-records-at-name-com.md) |
| [<span data-ttu-id="15bbe-127">Bluehost</span><span class="sxs-lookup"><span data-stu-id="15bbe-127">Bluehost</span></span>](../dns/create-dns-records-at-bluehost.md) | [<span data-ttu-id="15bbe-128">NameCheap</span><span class="sxs-lookup"><span data-stu-id="15bbe-128">Namecheap</span></span>](../dns/create-dns-records-at-namecheap.md)|
| [<span data-ttu-id="15bbe-129">CloudFlare</span><span class="sxs-lookup"><span data-stu-id="15bbe-129">Cloudflare</span></span>](../dns/create-dns-records-at-cloudflare.md)| [<span data-ttu-id="15bbe-130">Names.co.uk</span><span class="sxs-lookup"><span data-stu-id="15bbe-130">Names.co.uk</span></span>](../dns/create-dns-records-at-names-co-uk.md) |
|  [<span data-ttu-id="15bbe-131">Galna-domäner</span><span class="sxs-lookup"><span data-stu-id="15bbe-131">Crazy Domains</span></span>](../dns/create-dns-records-at-crazy-domains.md)| [<span data-ttu-id="15bbe-132">Netregistry</span><span class="sxs-lookup"><span data-stu-id="15bbe-132">Netregistry</span></span>](../dns/create-dns-records-at-netregistry.md) |
|[<span data-ttu-id="15bbe-133">DNSMadeEasy</span><span class="sxs-lookup"><span data-stu-id="15bbe-133">DNSMadeEasy</span></span>](../dns/create-dns-records-at-dnsmadeeasy.md) | [<span data-ttu-id="15bbe-134">Nätverks lösningar</span><span class="sxs-lookup"><span data-stu-id="15bbe-134">Network   Solutions</span></span>](../dns/create-dns-records-at-network-solutions.md) |
|[<span data-ttu-id="15bbe-135">Dreamhost</span><span class="sxs-lookup"><span data-stu-id="15bbe-135">Dreamhost</span></span>](../dns/create-dns-records-at-dreamhost.md)  | [<span data-ttu-id="15bbe-136">OVH</span><span class="sxs-lookup"><span data-stu-id="15bbe-136">OVH</span></span>](../dns/create-dns-records-at-ovh.md) |
|  [<span data-ttu-id="15bbe-137">Dyn.com</span><span class="sxs-lookup"><span data-stu-id="15bbe-137">Dyn.com</span></span>](../dns/create-dns-records-at-dyn-com.md) | [<span data-ttu-id="15bbe-138">Register.com</span><span class="sxs-lookup"><span data-stu-id="15bbe-138">Register.com</span></span>](../dns/create-dns-records-at-register-com.md) |
| [<span data-ttu-id="15bbe-139">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="15bbe-139">eNomCentral</span></span>](../dns/create-dns-records-at-enomcentral.md)| [<span data-ttu-id="15bbe-140">Register365 för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="15bbe-140">Register365 for Microsoft 365</span></span>](../dns/create-dns-records-at-register365.md)  |
| [<span data-ttu-id="15bbe-141">Freenom</span><span class="sxs-lookup"><span data-stu-id="15bbe-141">Freenom</span></span>](../dns/create-dns-records-at-freenom.md) | [<span data-ttu-id="15bbe-142"> web.com </span><span class="sxs-lookup"><span data-stu-id="15bbe-142"> web.com </span></span>](../dns/create-dns-records-at-web-com.md)|
|[<span data-ttu-id="15bbe-143">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="15bbe-143">GoDaddy</span></span>](../dns/create-dns-records-at-godaddy.md)|[<span data-ttu-id="15bbe-144"> Windows-baserad DNS</span><span class="sxs-lookup"><span data-stu-id="15bbe-144"> Windows-based DNS</span></span>](../dns/create-dns-records-using-windows-based-dns.md)   |
| [<span data-ttu-id="15bbe-145">Google-domäner</span><span class="sxs-lookup"><span data-stu-id="15bbe-145">Google Domains</span></span>](../dns/create-dns-records-at-google-domains.md) |[<span data-ttu-id="15bbe-146">WIX</span><span class="sxs-lookup"><span data-stu-id="15bbe-146">Wix</span></span>](../dns/create-dns-records-at-wix.md) |
|[<span data-ttu-id="15bbe-147">Host Gator</span><span class="sxs-lookup"><span data-stu-id="15bbe-147">Hostgator</span></span>](../dns/create-dns-records-at-hostgator.md)  | [<span data-ttu-id="15bbe-148">Yahoo!   Småföretag</span><span class="sxs-lookup"><span data-stu-id="15bbe-148">Yahoo!   Small Business</span></span>](../dns/create-dns-records-at-yahoo-small-business.md)  |

[<span data-ttu-id="15bbe-149">Jag behöver allmänna instruktioner, eftersom min domän värd inte finns med i listan. </span><span class="sxs-lookup"><span data-stu-id="15bbe-149">I need general instructions, because my domain host isn't on this list. </span></span>](create-dns-records-at-any-dns-hosting-provider.md)
   
