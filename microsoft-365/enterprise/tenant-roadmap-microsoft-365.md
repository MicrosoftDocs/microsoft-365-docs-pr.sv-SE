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
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: Översikten för konfiguration av klient organisationer för Microsoft 365.
ms.openlocfilehash: 0f1fa91bb81fd6cc87820f2b2d48e00e1b75a0c4
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446013"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="48349-103">Klient organisations översikt för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="48349-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="48349-104">Din Microsoft 365-klient är den uppsättning tjänster som är tilldelade till din organisation.</span><span class="sxs-lookup"><span data-stu-id="48349-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="48349-105">Den här innehavaren är normalt kopplad till ett eller flera av dina DNS-domännamn och fungerar som en central behållare för olika prenumerationer och de licenser som du tilldelar användar konton.</span><span class="sxs-lookup"><span data-stu-id="48349-105">Typically, this tenant is associated with one or more of your DNS domain names and acts as a central container for different subscriptions and the licenses within them that you assign to user accounts.</span></span>

<span data-ttu-id="48349-106">När du skapar en Microsoft 365-klient organisation tilldelar du den till en specifik geografisk plats.</span><span class="sxs-lookup"><span data-stu-id="48349-106">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="48349-107">Du kan också ha en innehavare med flera geografiska platser och flytta klient organisationen från en plats till en annan.</span><span class="sxs-lookup"><span data-stu-id="48349-107">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="48349-108">För att få klient organisationen redo för de grundläggande tjänsterna i nätverk och identitet är det viktigt att noggrant planera och köra klient konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="48349-108">To get your tenant ready for the foundational services of networking and identity, it's critical to carefully plan and execute your tenant configuration.</span></span>

## <a name="plan"></a><span data-ttu-id="48349-109">Planera</span><span class="sxs-lookup"><span data-stu-id="48349-109">Plan</span></span>

<span data-ttu-id="48349-110">Så här planerar du för klient implementering:</span><span class="sxs-lookup"><span data-stu-id="48349-110">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="48349-111">Förstå abonnemang, licenser och Azure Active Directory (Azure AD)-klient organisationer</span><span class="sxs-lookup"><span data-stu-id="48349-111">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="48349-112">Förstå hur du använder SSL-certifikat från tredje part</span><span class="sxs-lookup"><span data-stu-id="48349-112">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="48349-113">Förstå hur en Microsoft 365-klient är integrerad med Azure AD-tjänster</span><span class="sxs-lookup"><span data-stu-id="48349-113">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="48349-114">Planera stöd för klient program</span><span class="sxs-lookup"><span data-stu-id="48349-114">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="48349-115">Bestämma hur hybrid modern</span><span class="sxs-lookup"><span data-stu-id="48349-115">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="48349-116">Planera för Office 2007-och Office 2010-uppgraderingar</span><span class="sxs-lookup"><span data-stu-id="48349-116">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="48349-117">Förstå klient isolering</span><span class="sxs-lookup"><span data-stu-id="48349-117">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)
- [<span data-ttu-id="48349-118">Få information om Microsoft 365-tjänsten</span><span class="sxs-lookup"><span data-stu-id="48349-118">Get the details on Microsoft 365 service assurance</span></span>](https://docs.microsoft.com/microsoft-365/compliance/service-assurance)

## <a name="deploy"></a><span data-ttu-id="48349-119">Distribuera</span><span class="sxs-lookup"><span data-stu-id="48349-119">Deploy</span></span>

<span data-ttu-id="48349-120">Om du vill distribuera din klient organisation [lägger du till DNS-domänerna](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) för organisationen och använder [installations guiderna i Microsoft 365 Admin Center](setup-guides-for-microsoft-365.md).</span><span class="sxs-lookup"><span data-stu-id="48349-120">To deploy your tenant, [add the DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization and use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>

## <a name="tenants-with-multiple-geographic-locations"></a><span data-ttu-id="48349-121">Klient organisationer med flera geografiska platser</span><span class="sxs-lookup"><span data-stu-id="48349-121">Tenants with multiple geographic locations</span></span>

<span data-ttu-id="48349-122">Med Microsoft 365 multi-geo kan din organisation utöka sin Microsoft 365-närvaro till flera geografiska regioner och/eller länder inom din befintliga klient organisation.</span><span class="sxs-lookup"><span data-stu-id="48349-122">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="48349-123">Information om Microsoft 365 multi-geo, inklusive hur du planerar, konfigurerar och administrerar den, finns [här](microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="48349-123">For information about Microsoft 365 Multi-Geo, including how to plan, configure, and administer it, [start here](microsoft-365-multi-geo.md).</span></span>

## <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="48349-124">Flytta en innehavares geografiska platser</span><span class="sxs-lookup"><span data-stu-id="48349-124">Move a tenant's geographic locations</span></span>

<span data-ttu-id="48349-125">Microsoft fortsätter att öppna nya data Center geografiska platser (geos) för Microsoft 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="48349-125">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="48349-126">De här nya data Center geos lägger till kapacitet och kan beräkna resurser för att stödja kund behov och förbruknings tillväxt.</span><span class="sxs-lookup"><span data-stu-id="48349-126">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="48349-127">Dessutom ger det nya data Center geos in-Geo data de för grundläggande kunddata.</span><span class="sxs-lookup"><span data-stu-id="48349-127">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="48349-128">[Börja här](moving-data-to-new-datacenter-geos.md)om du vill ha information om Microsoft 365 Data Center geo, inklusive hur du kan begära en Geo data flytt.</span><span class="sxs-lookup"><span data-stu-id="48349-128">For information about Microsoft 365 datacenter geo, including how to request a geo data move, [start here](moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="next-step"></a><span data-ttu-id="48349-129">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="48349-129">Next step</span></span>

<span data-ttu-id="48349-130">Starta klient organisations planeringen med [abonnemang, licenser, konton och innehavare](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span><span class="sxs-lookup"><span data-stu-id="48349-130">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

