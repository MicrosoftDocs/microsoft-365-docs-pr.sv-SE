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
ms.openlocfilehash: db0f9552fce460ca6d25ee74ea2031bea388b8dc
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656013"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="0dcf1-103">Klient organisations översikt för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0dcf1-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="0dcf1-104">Din Microsoft 365-klient är den uppsättning tjänster som är tilldelade till din organisation.</span><span class="sxs-lookup"><span data-stu-id="0dcf1-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="0dcf1-105">Den här innehavaren är normalt kopplad till ett eller flera av dina DNS-domännamn och fungerar som en central behållare för olika prenumerationer och de licenser som du tilldelar användar konton.</span><span class="sxs-lookup"><span data-stu-id="0dcf1-105">Typically, this tenant is associated with one or more of your DNS domain names and acts as a central container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> <span data-ttu-id="0dcf1-106">Mer information finns i [prenumerationer, licenser, konton och innehavare för Microsofts moln tjänster](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span><span class="sxs-lookup"><span data-stu-id="0dcf1-106">For more information, see [Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

<span data-ttu-id="0dcf1-107">När du skapar en Microsoft 365-klient organisation tilldelar du den till en specifik geografisk plats.</span><span class="sxs-lookup"><span data-stu-id="0dcf1-107">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="0dcf1-108">Du kan också ha en innehavare med flera geografiska platser och flytta klient organisationen från en plats till en annan.</span><span class="sxs-lookup"><span data-stu-id="0dcf1-108">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="0dcf1-109">För att förbereda klient organisationen redo för identitet är det viktigt att noggrant planera och utföra konfigurationen av klient organisationen.</span><span class="sxs-lookup"><span data-stu-id="0dcf1-109">To get your tenant ready for identity, it's critical to carefully plan and execute your tenant configuration.</span></span>


## <a name="set-up-your-microsoft-365-tenant"></a><span data-ttu-id="0dcf1-110">Konfigurera din Microsoft 365-klient organisation</span><span class="sxs-lookup"><span data-stu-id="0dcf1-110">Set up your Microsoft 365 tenant</span></span>

<span data-ttu-id="0dcf1-111">När du har kontrollerat att nätverket är optimerat för åtkomst till Microsoft 365 för både lokala och fjärranställda, kan dina kommande stora uppgifter planera för och sedan konfigurera din Microsoft 365-klient för DNS Domain Names, common Services och för den identitets infrastrukturen som stöder säker inloggning.</span><span class="sxs-lookup"><span data-stu-id="0dcf1-111">After ensuring that your networking is optimized for access to Microsoft 365 for both on-premises and remote workers, your next big tasks are planning for and then configuring your Microsoft 365 tenant for DNS domain names, common services, and for that identity infrastructure that supports secure user sign-in.</span></span>

## <a name="plan"></a><span data-ttu-id="0dcf1-112">Planera</span><span class="sxs-lookup"><span data-stu-id="0dcf1-112">Plan</span></span>

<span data-ttu-id="0dcf1-113">Så här planerar du för klient implementering:</span><span class="sxs-lookup"><span data-stu-id="0dcf1-113">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="0dcf1-114">Förstå abonnemang, licenser och Azure Active Directory (Azure AD)-klient organisationer</span><span class="sxs-lookup"><span data-stu-id="0dcf1-114">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="0dcf1-115">Förstå hur du använder SSL-certifikat från tredje part</span><span class="sxs-lookup"><span data-stu-id="0dcf1-115">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="0dcf1-116">Förstå hur en Microsoft 365-klient är integrerad med Azure AD-tjänster</span><span class="sxs-lookup"><span data-stu-id="0dcf1-116">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="0dcf1-117">Planera stöd för klient program</span><span class="sxs-lookup"><span data-stu-id="0dcf1-117">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="0dcf1-118">Bestämma hur hybrid modern</span><span class="sxs-lookup"><span data-stu-id="0dcf1-118">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="0dcf1-119">Planera för Office 2007-och Office 2010-uppgraderingar</span><span class="sxs-lookup"><span data-stu-id="0dcf1-119">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="0dcf1-120">Förstå klient isolering</span><span class="sxs-lookup"><span data-stu-id="0dcf1-120">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)
- [<span data-ttu-id="0dcf1-121">Få information om Microsoft 365-tjänsten</span><span class="sxs-lookup"><span data-stu-id="0dcf1-121">Get the details on Microsoft 365 service assurance</span></span>](microsoft-365-administrative-access-controls-overview.md)

### <a name="deploy"></a><span data-ttu-id="0dcf1-122">Distribuera</span><span class="sxs-lookup"><span data-stu-id="0dcf1-122">Deploy</span></span>

<span data-ttu-id="0dcf1-123">Så här distribuerar du klient organisationen:</span><span class="sxs-lookup"><span data-stu-id="0dcf1-123">To deploy your tenant:</span></span> 

- <span data-ttu-id="0dcf1-124">Lägga till [DNS-domäner](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) för din organisation.</span><span class="sxs-lookup"><span data-stu-id="0dcf1-124">Add the [DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization.</span></span>
- <span data-ttu-id="0dcf1-125">Använd [installations guiderna i administrations centret för Microsoft 365](setup-guides-for-microsoft-365.md).</span><span class="sxs-lookup"><span data-stu-id="0dcf1-125">Use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>
- <span data-ttu-id="0dcf1-126">Bygg upp din [identitets infrastruktur](identity-roadmap-microsoft-365.md) och [skydda dina inloggnings program](microsoft-365-secure-sign-in.md).</span><span class="sxs-lookup"><span data-stu-id="0dcf1-126">Build out your [identity infrastructure](identity-roadmap-microsoft-365.md) and [secure your user sign-ins](microsoft-365-secure-sign-in.md).</span></span>

### <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="0dcf1-127">Flytta en innehavares geografiska platser</span><span class="sxs-lookup"><span data-stu-id="0dcf1-127">Move a tenant's geographic locations</span></span>

<span data-ttu-id="0dcf1-128">Microsoft fortsätter att öppna nya data Center geografiska platser (geos) för Microsoft 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="0dcf1-128">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="0dcf1-129">De här nya data Center geos lägger till kapacitet och kan beräkna resurser för att stödja kund behov och förbruknings tillväxt.</span><span class="sxs-lookup"><span data-stu-id="0dcf1-129">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="0dcf1-130">Dessutom ger det nya data Center geos in-Geo data de för grundläggande kunddata.</span><span class="sxs-lookup"><span data-stu-id="0dcf1-130">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="0dcf1-131">Mer information finns i [Flytta grundläggande data till nya Microsoft 365 Data Center-geos](moving-data-to-new-datacenter-geos.md).</span><span class="sxs-lookup"><span data-stu-id="0dcf1-131">For more information, see [Moving core data to new Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md).</span></span>


## <a name="deploy-microsoft-365-multi-geo"></a><span data-ttu-id="0dcf1-132">Distribuera Microsoft 365 multi-geo</span><span class="sxs-lookup"><span data-stu-id="0dcf1-132">Deploy Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="0dcf1-133">Med Microsoft 365 multi-geo kan din organisation utöka sin Microsoft 365-närvaro till flera geografiska regioner och/eller länder inom din befintliga klient organisation.</span><span class="sxs-lookup"><span data-stu-id="0dcf1-133">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="0dcf1-134">Mer information finns i [Microsoft 365 multi-geo](microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="0dcf1-134">For more information, see [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span></span>

## <a name="manage-multiple-microsoft-365-tenancies"></a><span data-ttu-id="0dcf1-135">Hantera flera Microsoft 365-innehav</span><span class="sxs-lookup"><span data-stu-id="0dcf1-135">Manage multiple Microsoft 365 tenancies</span></span> 

<span data-ttu-id="0dcf1-136">Trots att en enda klient organisation för din oganization är idealisk kan du vara en av många organisationer som har flera innehavare.</span><span class="sxs-lookup"><span data-stu-id="0dcf1-136">Although having a single tenant for your oganization is ideal, you may be one of many organizations that have multiple tenancies.</span></span> <span data-ttu-id="0dcf1-137">Anledningen till att flera innehavare kan inkludera fusioner och förvärv, du vill ha en administrativ isolering eller att du har ett avcentraliserat.</span><span class="sxs-lookup"><span data-stu-id="0dcf1-137">Reasons for multiple tenancies can include mergers and aquisitions, you want administrative isolation, or you have a decentralized IT.</span></span>

<span data-ttu-id="0dcf1-138">Om du har flera Microsoft 365-innehavare kan du läsa de här artiklarna om du vill ha mer information om:</span><span class="sxs-lookup"><span data-stu-id="0dcf1-138">If you have multiple Microsoft 365 tenancies, see these articles for more information about:</span></span>

- [<span data-ttu-id="0dcf1-139">Samarbete mellan klientorganisationer</span><span class="sxs-lookup"><span data-stu-id="0dcf1-139">Inter-tenant collaboration</span></span>](microsoft-365-inter-tenant-collaboration.md)
- [<span data-ttu-id="0dcf1-140">Migrering av postlådor mellan klientorganisationer</span><span class="sxs-lookup"><span data-stu-id="0dcf1-140">Cross-tenant mailbox migration</span></span>](cross-tenant-mailbox-migration.md)
- [<span data-ttu-id="0dcf1-141">Migrering mellan klientorganisationer</span><span class="sxs-lookup"><span data-stu-id="0dcf1-141">Tenant-to-tenant migrations</span></span>](microsoft-365-tenant-to-tenant-migrations.md)


## <a name="next-step"></a><span data-ttu-id="0dcf1-142">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="0dcf1-142">Next step</span></span>

<span data-ttu-id="0dcf1-143">Starta klient organisations planeringen med [abonnemang, licenser, konton och innehavare](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span><span class="sxs-lookup"><span data-stu-id="0dcf1-143">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>
