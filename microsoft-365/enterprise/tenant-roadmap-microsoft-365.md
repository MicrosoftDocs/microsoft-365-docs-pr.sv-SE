---
title: Klient organisations översikt för Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: Översikten för konfiguration av klient organisationer för Microsoft 365.
ms.openlocfilehash: d2640a036eedda0b0962a15a03dcf0211ea0209b
ms.sourcegitcommit: c84cceb07e748969723a31b350e37f3ec79255ab
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/09/2020
ms.locfileid: "48948403"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="7199d-103">Klient organisations översikt för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7199d-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="7199d-104">Din Microsoft 365-klient är den uppsättning tjänster som är tilldelade till din organisation.</span><span class="sxs-lookup"><span data-stu-id="7199d-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="7199d-105">Vanligt vis är denna klient organisation kopplad till ett eller flera av dina offentliga DNS-domännamn och fungerar som en central och isolerad behållare för olika prenumerationer och de licenser som du tilldelar användar konton.</span><span class="sxs-lookup"><span data-stu-id="7199d-105">Typically, this tenant is associated with one or more of your public DNS domain names and acts as a central and isolated container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> <span data-ttu-id="7199d-106">Mer information finns i [prenumerationer, licenser, konton och innehavare för Microsofts moln tjänster](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span><span class="sxs-lookup"><span data-stu-id="7199d-106">For more information, see [Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

<span data-ttu-id="7199d-107">När du skapar en Microsoft 365-klient organisation tilldelar du den till en specifik geografisk plats.</span><span class="sxs-lookup"><span data-stu-id="7199d-107">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="7199d-108">Du kan också ha en innehavare med flera geografiska platser och flytta klient organisationen från en plats till en annan.</span><span class="sxs-lookup"><span data-stu-id="7199d-108">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="7199d-109">För att förbereda klient organisationen för användare, grupper, licenser och Cloud-appar är det viktigt att noggrant planera och köra klient konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="7199d-109">To get your tenant ready for user, groups, licenses, and cloud apps, it's critical to carefully plan and execute your tenant configuration.</span></span>

## <a name="set-up-your-microsoft-365-tenant"></a><span data-ttu-id="7199d-110">Konfigurera din Microsoft 365-klient organisation</span><span class="sxs-lookup"><span data-stu-id="7199d-110">Set up your Microsoft 365 tenant</span></span>

<span data-ttu-id="7199d-111">När du har kontrollerat att nätverket är optimerat för åtkomst till Microsoft 365 för både lokala och fjärranställda, kan dina kommande stora uppgifter planera för och sedan konfigurera din Microsoft 365-klient för DNS Domain Names, common Services och för den identitets infrastrukturen som stöder säker inloggning.</span><span class="sxs-lookup"><span data-stu-id="7199d-111">After ensuring that your networking is optimized for access to Microsoft 365 for both on-premises and remote workers, your next big tasks are planning for and then configuring your Microsoft 365 tenant for DNS domain names, common services, and for that identity infrastructure that supports secure user sign-in.</span></span>

### <a name="plan"></a><span data-ttu-id="7199d-112">Planera</span><span class="sxs-lookup"><span data-stu-id="7199d-112">Plan</span></span>

<span data-ttu-id="7199d-113">Så här planerar du för klient implementering:</span><span class="sxs-lookup"><span data-stu-id="7199d-113">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="7199d-114">Förstå abonnemang, licenser och Azure Active Directory (Azure AD)-klient organisationer</span><span class="sxs-lookup"><span data-stu-id="7199d-114">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="7199d-115">Förstå hur du använder SSL-certifikat från tredje part</span><span class="sxs-lookup"><span data-stu-id="7199d-115">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="7199d-116">Förstå hur en Microsoft 365-klient är integrerad med Azure AD-tjänster</span><span class="sxs-lookup"><span data-stu-id="7199d-116">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="7199d-117">Planera stöd för klient program</span><span class="sxs-lookup"><span data-stu-id="7199d-117">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="7199d-118">Bestämma hur hybrid modern</span><span class="sxs-lookup"><span data-stu-id="7199d-118">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="7199d-119">Planera för Office 2007-och Office 2010-uppgraderingar</span><span class="sxs-lookup"><span data-stu-id="7199d-119">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="7199d-120">Förstå klient isolering</span><span class="sxs-lookup"><span data-stu-id="7199d-120">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)

### <a name="deploy"></a><span data-ttu-id="7199d-121">Distribuera</span><span class="sxs-lookup"><span data-stu-id="7199d-121">Deploy</span></span>

<span data-ttu-id="7199d-122">Så här distribuerar du klient organisationen:</span><span class="sxs-lookup"><span data-stu-id="7199d-122">To deploy your tenant:</span></span> 

- <span data-ttu-id="7199d-123">Lägga till [DNS-domäner](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) för din organisation.</span><span class="sxs-lookup"><span data-stu-id="7199d-123">Add the [DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization.</span></span>
- <span data-ttu-id="7199d-124">Använd [installations guiderna i administrations centret för Microsoft 365](setup-guides-for-microsoft-365.md).</span><span class="sxs-lookup"><span data-stu-id="7199d-124">Use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>
- <span data-ttu-id="7199d-125">Bygg upp din [identitets infrastruktur](identity-roadmap-microsoft-365.md) och [skydda dina inloggnings program](microsoft-365-secure-sign-in.md).</span><span class="sxs-lookup"><span data-stu-id="7199d-125">Build out your [identity infrastructure](identity-roadmap-microsoft-365.md) and [secure your user sign-ins](microsoft-365-secure-sign-in.md).</span></span>

### <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="7199d-126">Flytta en innehavares geografiska platser</span><span class="sxs-lookup"><span data-stu-id="7199d-126">Move a tenant's geographic locations</span></span>

<span data-ttu-id="7199d-127">Microsoft fortsätter att öppna nya data Center geografiska platser (geos) för Microsoft 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="7199d-127">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="7199d-128">De här nya data Center geos lägger till kapacitet och kan beräkna resurser för att stödja kund behov och förbruknings tillväxt.</span><span class="sxs-lookup"><span data-stu-id="7199d-128">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="7199d-129">Dessutom ger det nya data Center geos in-Geo data de för grundläggande kunddata.</span><span class="sxs-lookup"><span data-stu-id="7199d-129">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="7199d-130">Mer information finns i [Flytta grundläggande data till nya Microsoft 365 Data Center-geos](moving-data-to-new-datacenter-geos.md).</span><span class="sxs-lookup"><span data-stu-id="7199d-130">For more information, see [Moving core data to new Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md).</span></span>


## <a name="deploy-microsoft-365-multi-geo"></a><span data-ttu-id="7199d-131">Distribuera Microsoft 365 multi-geo</span><span class="sxs-lookup"><span data-stu-id="7199d-131">Deploy Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="7199d-132">Med Microsoft 365 multi-geo kan din organisation utöka sin Microsoft 365-närvaro till flera geografiska regioner och/eller länder inom din befintliga klient organisation.</span><span class="sxs-lookup"><span data-stu-id="7199d-132">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="7199d-133">Mer information finns i [Microsoft 365 multi-geo](microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="7199d-133">For more information, see [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span></span>

## <a name="manage-multiple-microsoft-365-tenants"></a><span data-ttu-id="7199d-134">Hantera flera Microsoft 365-klient organisationer</span><span class="sxs-lookup"><span data-stu-id="7199d-134">Manage multiple Microsoft 365 tenants</span></span> 

<span data-ttu-id="7199d-135">Trots att en enda klient organisation för din oganization är idealisk kan du vara en av många organisationer som har flera innehavare.</span><span class="sxs-lookup"><span data-stu-id="7199d-135">Although having a single tenant for your oganization is ideal, you may be one of many organizations that have multiple tenants.</span></span> <span data-ttu-id="7199d-136">Det kan vara bra att inkludera fusioner och förvärv, du vill ha en administrativ isolering eller ett avcentraliserat.</span><span class="sxs-lookup"><span data-stu-id="7199d-136">Reasons can include mergers and aquisitions, you want administrative isolation, or you have a decentralized IT.</span></span>

<span data-ttu-id="7199d-137">Om du har flera Microsoft 365-klient organisationer kan du läsa de här artiklarna om du vill ha mer information om:</span><span class="sxs-lookup"><span data-stu-id="7199d-137">If you have multiple Microsoft 365 tenants, see these articles for more information about:</span></span>

- [<span data-ttu-id="7199d-138">Samarbete mellan klientorganisationer</span><span class="sxs-lookup"><span data-stu-id="7199d-138">Inter-tenant collaboration</span></span>](microsoft-365-inter-tenant-collaboration.md)
- [<span data-ttu-id="7199d-139">Migrering av postlådor mellan klientorganisationer</span><span class="sxs-lookup"><span data-stu-id="7199d-139">Cross-tenant mailbox migration</span></span>](cross-tenant-mailbox-migration.md)
- [<span data-ttu-id="7199d-140">Migrering mellan klientorganisationer</span><span class="sxs-lookup"><span data-stu-id="7199d-140">Tenant-to-tenant migrations</span></span>](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a><span data-ttu-id="7199d-141">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="7199d-141">Next step</span></span>

<span data-ttu-id="7199d-142">Starta klient organisations planeringen med [abonnemang, licenser, konton och innehavare](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span><span class="sxs-lookup"><span data-stu-id="7199d-142">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>
