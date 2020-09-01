---
title: Klient organisations översikt för Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom: it-pro
description: Översikten för konfiguration av klient organisationer för Microsoft 365.
ms.openlocfilehash: 540d1bc53ac06b85d22a8a60a62e51761e10339c
ms.sourcegitcommit: 19515d787246d38c4e0da579a767ce67b9dbc2bc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/31/2020
ms.locfileid: "47315759"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="691a6-103">Klient organisations översikt för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="691a6-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="691a6-104">Din Microsoft 365-klient är den uppsättning tjänster som är tilldelade till din organisation.</span><span class="sxs-lookup"><span data-stu-id="691a6-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="691a6-105">Denna klient organisation är normalt kopplad till ett eller flera av dina DNS-domännamn och fungerar som en central behållare för olika prenumerationer och de licenser som du tilldelar användar konton.</span><span class="sxs-lookup"><span data-stu-id="691a6-105">This tenant is typically associated with one or more of your DNS domain names and acts as a central container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> 

<span data-ttu-id="691a6-106">När du skapar en Microsoft 365-klient organisation tilldelar du den till en specifik geografisk plats.</span><span class="sxs-lookup"><span data-stu-id="691a6-106">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="691a6-107">Du kan också ha en innehavare med flera geografiska platser och flytta klient organisationen från en plats till en annan.</span><span class="sxs-lookup"><span data-stu-id="691a6-107">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="691a6-108">En välplanerad och utförd klient konfiguration är avgörande för att få den att fungera för de grundläggande tjänsterna i nätverk och identitet.</span><span class="sxs-lookup"><span data-stu-id="691a6-108">A well-planned and executed tenant configuration is critical to getting it ready for the foundational services of networking and identity.</span></span>

## <a name="plan"></a><span data-ttu-id="691a6-109">Planera</span><span class="sxs-lookup"><span data-stu-id="691a6-109">Plan</span></span>

<span data-ttu-id="691a6-110">Så här planerar du för klient implementering:</span><span class="sxs-lookup"><span data-stu-id="691a6-110">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="691a6-111">Förstå abonnemang, licenser och Azure Active Directory (Azure AD)-klient organisationer</span><span class="sxs-lookup"><span data-stu-id="691a6-111">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="691a6-112">Förstå hur du använder SSL-certifikat från tredje part</span><span class="sxs-lookup"><span data-stu-id="691a6-112">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="691a6-113">Installations guider för Access i administrations centret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="691a6-113">Access setup guides in the Microsoft 365 admin center</span></span>](setup-guides-for-microsoft-365.md)
- [<span data-ttu-id="691a6-114">Förstå hur en Microsoft 365-klient är integrerad med Azure AD-tjänster</span><span class="sxs-lookup"><span data-stu-id="691a6-114">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="691a6-115">Planera stöd för klient program</span><span class="sxs-lookup"><span data-stu-id="691a6-115">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="691a6-116">Bestämma hur hybrid modern</span><span class="sxs-lookup"><span data-stu-id="691a6-116">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="691a6-117">Planera för Office 2007-och Office 2010-uppgraderingar</span><span class="sxs-lookup"><span data-stu-id="691a6-117">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="691a6-118">Förstå klient isolering</span><span class="sxs-lookup"><span data-stu-id="691a6-118">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)
- [<span data-ttu-id="691a6-119">Få information om Microsoft 365-tjänsten</span><span class="sxs-lookup"><span data-stu-id="691a6-119">Get the details on Microsoft 365 service assurance</span></span>](https://docs.microsoft.com/microsoft-365/compliance/service-assurance)

## <a name="deploy"></a><span data-ttu-id="691a6-120">Distribuera</span><span class="sxs-lookup"><span data-stu-id="691a6-120">Deploy</span></span>

<span data-ttu-id="691a6-121">Om du vill distribuera din klient organisation [lägger du till DNS-domänerna](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) för organisationen.</span><span class="sxs-lookup"><span data-stu-id="691a6-121">To deploy your tenant, [add the DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization.</span></span>

## <a name="tenants-with-multiple-geographic-locations"></a><span data-ttu-id="691a6-122">Klient organisationer med flera geografiska platser</span><span class="sxs-lookup"><span data-stu-id="691a6-122">Tenants with multiple geographic locations</span></span>

<span data-ttu-id="691a6-123">Med Microsoft 365 multi-geo kan din organisation utöka sin Microsoft 365-närvaro till flera geografiska regioner och/eller länder inom din befintliga klient organisation.</span><span class="sxs-lookup"><span data-stu-id="691a6-123">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="691a6-124">[Komma igång](microsoft-365-multi-geo.md) med att förstå, planera, konfigurera och administrera med Microsoft 365 multi-geo.</span><span class="sxs-lookup"><span data-stu-id="691a6-124">[Get started](microsoft-365-multi-geo.md) in understanding, planning, configuring, and then administering with Microsoft 365 Multi-Geo.</span></span>

## <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="691a6-125">Flytta en innehavares geografiska platser</span><span class="sxs-lookup"><span data-stu-id="691a6-125">Move a tenant's geographic locations</span></span>

<span data-ttu-id="691a6-126">Microsoft fortsätter att öppna nya data Center geografiska platser (geos) för Microsoft 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="691a6-126">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="691a6-127">De här nya data Center geos lägger till kapacitet och kan beräkna resurser för att stödja kund behov och förbruknings tillväxt.</span><span class="sxs-lookup"><span data-stu-id="691a6-127">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="691a6-128">Dessutom ger det nya data Center geos in-Geo data de för grundläggande kunddata.</span><span class="sxs-lookup"><span data-stu-id="691a6-128">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="691a6-129">Komma igång med att förstå och begära en Geo data förflyttning med [flytt av grundläggande data till nya Microsoft 365 Data Center geo](moving-data-to-new-datacenter-geos.md).</span><span class="sxs-lookup"><span data-stu-id="691a6-129">Get started in understanding and requesting a geo data move with [Moving core data to new Microsoft 365 datacenter geo](moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="next-step"></a><span data-ttu-id="691a6-130">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="691a6-130">Next step</span></span>

<span data-ttu-id="691a6-131">Starta klient organisations planeringen med [abonnemang, licenser, konton och innehavare](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span><span class="sxs-lookup"><span data-stu-id="691a6-131">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

