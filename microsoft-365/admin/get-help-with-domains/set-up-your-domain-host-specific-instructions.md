---
title: Konfigurera din domän (tjänstspecifika instruktioner)
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
search.appverid:
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: ae950c9e-e8d9-4108-b0cb-449156998580
description: Lär dig hur du hanterar dina egna DNS-poster eller låter Office 365 hantera dina DNS-poster åt dig.
ms.custom: okr_smb
ms.openlocfilehash: dbd9dda6f84803732777ac75163f031b50419732
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42812341"
---
# <a name="set-up-your-domain-host-specific-instructions"></a><span data-ttu-id="989b7-103">Konfigurera din domän (tjänstspecifika instruktioner)</span><span class="sxs-lookup"><span data-stu-id="989b7-103">Set up your domain (host-specific instructions)</span></span>

<span data-ttu-id="989b7-104">Om du vill börja använda en anpassad domän (contoso.com) med Office 365 måste du verifiera domänen och konfigurera domänens DNS-poster.</span><span class="sxs-lookup"><span data-stu-id="989b7-104">To start using a custom domain (contoso.com) with Office 365, you need to verify your domain and configure your domain's DNS records.</span></span> 
  
<span data-ttu-id="989b7-105">Du kan lägga till och hantera DNS-poster med hjälp av de administrativa verktygen på domänvärden eller ge Office 365 kontroll över dina domänposter så konfigurerar vi dem åt dig.</span><span class="sxs-lookup"><span data-stu-id="989b7-105">You can add and manage DNS records using the administrative tools at your domain host, or give Office 365 control of your domain records and we'll set them up for you.</span></span>
  
<span data-ttu-id="989b7-106">Välj domänvärden nedan för de exakta stegen.</span><span class="sxs-lookup"><span data-stu-id="989b7-106">Select your domain host below for the exact steps.</span></span> <span data-ttu-id="989b7-107">Om du inte är säker på vem värden är läser du [Hitta domänregistratorn](find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="989b7-107">If you're not sure who your host is, see [Find your domain registrar](find-your-domain-registrar.md).</span></span>
  

## <a name="let-office-365-manage-your-dns-records"></a><span data-ttu-id="989b7-108">Låta Office 365 hantera dina DNS-poster</span><span class="sxs-lookup"><span data-stu-id="989b7-108">Let Office 365 manage your DNS records</span></span>

||
|---|---|
|[<span data-ttu-id="989b7-109">1&1 IONOS</span><span class="sxs-lookup"><span data-stu-id="989b7-109">1&1 IONOS</span></span>](../dns/change-nameservers-at-1-1-internet.md) |
|[<span data-ttu-id="989b7-110">Amazon Webbtjänster (AWS)</span><span class="sxs-lookup"><span data-stu-id="989b7-110">Amazon Web Services (AWS)</span></span>](../dns/change-nameservers-at-aws.md) |
 [<span data-ttu-id="989b7-111">Bluehost</span><span class="sxs-lookup"><span data-stu-id="989b7-111">Bluehost</span></span>](../dns/change-nameservers-at-bluehost.md)|
|[<span data-ttu-id="989b7-112">Google-domäner</span><span class="sxs-lookup"><span data-stu-id="989b7-112">Google   Domains</span></span>](../dns/change-nameservers-at-google-domains.md) |
|[<span data-ttu-id="989b7-113">Hostgator</span><span class="sxs-lookup"><span data-stu-id="989b7-113">Hostgator   </span></span>](../dns/change-nameservers-at-hostgator.md)  |  
|[<span data-ttu-id="989b7-114">Mydomain</span><span class="sxs-lookup"><span data-stu-id="989b7-114">MyDomain</span></span>](../dns/change-nameservers-at-mydomain.md) | 
|[<span data-ttu-id="989b7-115">Namnbilligt</span><span class="sxs-lookup"><span data-stu-id="989b7-115">Namecheap</span></span>](../dns/change-nameservers-at-namecheap.md)|
|[<span data-ttu-id="989b7-116">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="989b7-116">Network Solutions</span></span>](../dns/change-nameservers-at-network-solutions.md) |  

<span data-ttu-id="989b7-117">Du kan också lära dig hur du [ändrar namnservrar för att konfigurera Office 365 med en domänregistrator](change-nameservers-at-any-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="989b7-117">Or, learn how to [change nameservers to set up Office 365 with any domain registrar](change-nameservers-at-any-domain-registrar.md).</span></span>

## <a name="manage-your-own-dns-records"></a><span data-ttu-id="989b7-118">Hantera dina egna DNS-poster</span><span class="sxs-lookup"><span data-stu-id="989b7-118">Manage your own DNS records</span></span>

|                           |                          |
|---------------------------|--------------------------|
| [<span data-ttu-id="989b7-119">1&1 IONOS</span><span class="sxs-lookup"><span data-stu-id="989b7-119">1&1 IONOS</span></span>](../dns/create-dns-records-at-1-1-internet.md) | [<span data-ttu-id="989b7-120">Hover</span><span class="sxs-lookup"><span data-stu-id="989b7-120">Hover</span></span>](../dns/create-dns-records-at-hover.md) |
| [<span data-ttu-id="989b7-121">123-reg.co.uk</span><span class="sxs-lookup"><span data-stu-id="989b7-121">123-reg.co.uk</span></span>](../dns/create-dns-records-at-123-reg-co-uk.md) | [<span data-ttu-id="989b7-122">Hanteras av Google (eNom)</span><span class="sxs-lookup"><span data-stu-id="989b7-122">Managed   by Google (eNom)</span></span>](../dns/create-dns-records-for-domain-managed-by-google-enom.md)|
| [<span data-ttu-id="989b7-123">Amazon Webbtjänster (AWS)</span><span class="sxs-lookup"><span data-stu-id="989b7-123">Amazon Web Services (AWS)</span></span>](../dns/create-dns-records-at-aws.md) | [<span data-ttu-id="989b7-124">Mydomain</span><span class="sxs-lookup"><span data-stu-id="989b7-124">MyDomain</span></span>](../dns/create-dns-records-at-mydomain.md) |
| [<span data-ttu-id="989b7-125">Azure DNS-zoner</span><span class="sxs-lookup"><span data-stu-id="989b7-125">Azure DNS zones</span></span>](../dns/create-dns-records-for-azure-dns-zones.md) | [<span data-ttu-id="989b7-126">name.com</span><span class="sxs-lookup"><span data-stu-id="989b7-126">name.com</span></span>](../dns/create-dns-records-at-name-com.md) |
| [<span data-ttu-id="989b7-127">Bluehost</span><span class="sxs-lookup"><span data-stu-id="989b7-127">Bluehost</span></span>](../dns/create-dns-records-at-bluehost.md) | [<span data-ttu-id="989b7-128">Namnbilligt</span><span class="sxs-lookup"><span data-stu-id="989b7-128">Namecheap</span></span>](../dns/create-dns-records-at-namecheap.md)|
| [<span data-ttu-id="989b7-129">Cloudflare (molnflare)</span><span class="sxs-lookup"><span data-stu-id="989b7-129">Cloudflare</span></span>](../dns/create-dns-records-at-cloudflare.md)| [<span data-ttu-id="989b7-130">Names.co.uk</span><span class="sxs-lookup"><span data-stu-id="989b7-130">Names.co.uk</span></span>](../dns/create-dns-records-at-names-co-uk.md) |
|  [<span data-ttu-id="989b7-131">Galna domäner</span><span class="sxs-lookup"><span data-stu-id="989b7-131">Crazy Domains</span></span>](../dns/create-dns-records-at-crazy-domains.md)| [<span data-ttu-id="989b7-132">Netregistry (netregistry)</span><span class="sxs-lookup"><span data-stu-id="989b7-132">Netregistry</span></span>](../dns/create-dns-records-at-netregistry.md) |
|[<span data-ttu-id="989b7-133">DNSMadeEasy (på 800)</span><span class="sxs-lookup"><span data-stu-id="989b7-133">DNSMadeEasy</span></span>](../dns/create-dns-records-at-dnsmadeeasy.md) | [<span data-ttu-id="989b7-134">Nätverkslösningar</span><span class="sxs-lookup"><span data-stu-id="989b7-134">Network   Solutions</span></span>](../dns/create-dns-records-at-network-solutions.md) |
|[<span data-ttu-id="989b7-135">Dreamhost</span><span class="sxs-lookup"><span data-stu-id="989b7-135">Dreamhost</span></span>](../dns/create-dns-records-at-dreamhost.md)  | [<span data-ttu-id="989b7-136">Ovh</span><span class="sxs-lookup"><span data-stu-id="989b7-136">OVH</span></span>](../dns/create-dns-records-at-ovh.md) |
|  [<span data-ttu-id="989b7-137">Dyn.com</span><span class="sxs-lookup"><span data-stu-id="989b7-137">Dyn.com</span></span>](../dns/create-dns-records-at-dyn-com.md) | [<span data-ttu-id="989b7-138">Register.com</span><span class="sxs-lookup"><span data-stu-id="989b7-138">Register.com</span></span>](../dns/create-dns-records-at-register-com.md) |
| [<span data-ttu-id="989b7-139">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="989b7-139">eNomCentral</span></span>](../dns/create-dns-records-at-enomcentral.md)| [<span data-ttu-id="989b7-140">Registrera 365 för Office 365</span><span class="sxs-lookup"><span data-stu-id="989b7-140">Register365 for Office 365</span></span>](../dns/create-dns-records-at-register365.md)  |
| [<span data-ttu-id="989b7-141">Freenom (fritt)</span><span class="sxs-lookup"><span data-stu-id="989b7-141">Freenom</span></span>](../dns/create-dns-records-at-freenom.md) | [<span data-ttu-id="989b7-142">web.com</span><span class="sxs-lookup"><span data-stu-id="989b7-142"> web.com </span></span>](../dns/create-dns-records-at-web-com.md)|
|[<span data-ttu-id="989b7-143">Godaddy</span><span class="sxs-lookup"><span data-stu-id="989b7-143">GoDaddy</span></span>](../dns/create-dns-records-at-godaddy.md)|[<span data-ttu-id="989b7-144">Windows-baserad DNS</span><span class="sxs-lookup"><span data-stu-id="989b7-144"> Windows-based DNS</span></span>](../dns/create-dns-records-using-windows-based-dns.md)   |
| [<span data-ttu-id="989b7-145">Google-domäner</span><span class="sxs-lookup"><span data-stu-id="989b7-145">Google Domains</span></span>](../dns/create-dns-records-at-google-domains.md) |[<span data-ttu-id="989b7-146">Wix</span><span class="sxs-lookup"><span data-stu-id="989b7-146">Wix</span></span>](../dns/create-dns-records-at-wix.md) |
|[<span data-ttu-id="989b7-147">Hostgator</span><span class="sxs-lookup"><span data-stu-id="989b7-147">Hostgator</span></span>](../dns/create-dns-records-at-hostgator.md)  | [<span data-ttu-id="989b7-148">Yahoo!   Småföretag</span><span class="sxs-lookup"><span data-stu-id="989b7-148">Yahoo!   Small Business</span></span>](../dns/create-dns-records-at-yahoo-small-business.md)  |

[<span data-ttu-id="989b7-149">Jag behöver allmänna instruktioner, eftersom min domänvärd inte finns med i den här listan.</span><span class="sxs-lookup"><span data-stu-id="989b7-149">I need general instructions, because my domain host isn't on this list. </span></span>](create-dns-records-at-any-dns-hosting-provider.md)
   
