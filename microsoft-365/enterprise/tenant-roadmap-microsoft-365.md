---
title: Översikt över klientorganisation för Microsoft 365
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
description: Översikt över hur du organisationsklienter ska konfigureras för Microsoft 365.
ms.openlocfilehash: fb3b6eecd893a5ab9b71bfa7bdfaea53af43470d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909460"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="9dcd1-103">Översikt över klientorganisation för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9dcd1-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="9dcd1-104">Microsoft 365-klienten är den uppsättning tjänster som tilldelats din organisation.</span><span class="sxs-lookup"><span data-stu-id="9dcd1-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="9dcd1-105">Den här klientorganisationen är vanligtvis kopplad till ett eller flera offentliga DNS-domännamn och fungerar som en central och isolerad behållare för olika prenumerationer och de licenser inom dem som du tilldelar användarkonton.</span><span class="sxs-lookup"><span data-stu-id="9dcd1-105">Typically, this tenant is associated with one or more of your public DNS domain names and acts as a central and isolated container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> <span data-ttu-id="9dcd1-106">Mer information finns i [Prenumerationer, licenser, konton och klientorganisation för Microsofts molntjänster.](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)</span><span class="sxs-lookup"><span data-stu-id="9dcd1-106">For more information, see [Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

<span data-ttu-id="9dcd1-107">När du skapar en Microsoft 365-klientorganisation tilldelar du den till en viss geografisk plats.</span><span class="sxs-lookup"><span data-stu-id="9dcd1-107">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="9dcd1-108">Du kan också ha en klientorganisation med flera geografiska platser och flytta klientorganisationen från en plats till en annan.</span><span class="sxs-lookup"><span data-stu-id="9dcd1-108">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="9dcd1-109">För att klientorganisationen ska bli redo för användare, grupper, licenser och molnappar är det viktigt att planera och genomföra konfigurationen av klientorganisationen noggrant.</span><span class="sxs-lookup"><span data-stu-id="9dcd1-109">To get your tenant ready for user, groups, licenses, and cloud apps, it's critical to carefully plan and execute your tenant configuration.</span></span>

## <a name="set-up-your-microsoft-365-tenant"></a><span data-ttu-id="9dcd1-110">Konfigurera din Microsoft 365-klientorganisation</span><span class="sxs-lookup"><span data-stu-id="9dcd1-110">Set up your Microsoft 365 tenant</span></span>

<span data-ttu-id="9dcd1-111">När du har säkerställt att ditt nätverk är optimerat för åtkomst till Microsoft 365 för både lokala användare och fjärranslutna medarbetare planerar du nästa stora uppgifter för och sedan konfigurerar din Microsoft 365-klientorganisation för DNS-domännamn, vanliga tjänster och för den identitetsinfrastruktur som stöder säker användarregistrering.</span><span class="sxs-lookup"><span data-stu-id="9dcd1-111">After ensuring that your networking is optimized for access to Microsoft 365 for both on-premises and remote workers, your next big tasks are planning for and then configuring your Microsoft 365 tenant for DNS domain names, common services, and for that identity infrastructure that supports secure user sign-in.</span></span>

### <a name="plan"></a><span data-ttu-id="9dcd1-112">Planera</span><span class="sxs-lookup"><span data-stu-id="9dcd1-112">Plan</span></span>

<span data-ttu-id="9dcd1-113">Så här planerar du implementering av klientorganisationen:</span><span class="sxs-lookup"><span data-stu-id="9dcd1-113">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="9dcd1-114">Förstå prenumerationer, licenser och Azure Active Directory-klientorganisationen (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="9dcd1-114">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="9dcd1-115">Förstå hur du använder SSL-certifikat från tredje part</span><span class="sxs-lookup"><span data-stu-id="9dcd1-115">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="9dcd1-116">Förstå hur en Microsoft 365-klient är integrerad med Azure AD-tjänster</span><span class="sxs-lookup"><span data-stu-id="9dcd1-116">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="9dcd1-117">Planera för support för klientprogram</span><span class="sxs-lookup"><span data-stu-id="9dcd1-117">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="9dcd1-118">Avgöra hur du använder modern hybridautentisering</span><span class="sxs-lookup"><span data-stu-id="9dcd1-118">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="9dcd1-119">Planera för uppgraderingar av Office 2007 och Office 2010</span><span class="sxs-lookup"><span data-stu-id="9dcd1-119">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="9dcd1-120">Förstå innehavarisolering</span><span class="sxs-lookup"><span data-stu-id="9dcd1-120">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)

### <a name="deploy"></a><span data-ttu-id="9dcd1-121">Distribuera</span><span class="sxs-lookup"><span data-stu-id="9dcd1-121">Deploy</span></span>

<span data-ttu-id="9dcd1-122">Så här distribuerar du klientorganisationen:</span><span class="sxs-lookup"><span data-stu-id="9dcd1-122">To deploy your tenant:</span></span> 

- <span data-ttu-id="9dcd1-123">Lägg till [DNS-domänerna](../admin/setup/add-domain.md) för din organisation.</span><span class="sxs-lookup"><span data-stu-id="9dcd1-123">Add the [DNS domains](../admin/setup/add-domain.md) for your organization.</span></span>
- <span data-ttu-id="9dcd1-124">Använd [installationsguiderna i administrationscentret för Microsoft 365.](setup-guides-for-microsoft-365.md)</span><span class="sxs-lookup"><span data-stu-id="9dcd1-124">Use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>
- <span data-ttu-id="9dcd1-125">Bygg ut din [identitetsinfrastruktur](identity-roadmap-microsoft-365.md) [och säkra användarnas inloggningar.](microsoft-365-secure-sign-in.md)</span><span class="sxs-lookup"><span data-stu-id="9dcd1-125">Build out your [identity infrastructure](identity-roadmap-microsoft-365.md) and [secure your user sign-ins](microsoft-365-secure-sign-in.md).</span></span>

### <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="9dcd1-126">Flytta en klientorganisations geografiska platser</span><span class="sxs-lookup"><span data-stu-id="9dcd1-126">Move a tenant's geographic locations</span></span>

<span data-ttu-id="9dcd1-127">Microsoft fortsätter att öppna nya geografiska platser i datacenter (geos) för Microsoft 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="9dcd1-127">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="9dcd1-128">Dessa nya datacenter geos lägger till kapacitet och beräknar resurser för att stödja kundbehov och användningstillväxt.</span><span class="sxs-lookup"><span data-stu-id="9dcd1-128">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="9dcd1-129">Det nya datacentret geos erbjuder dessutom geodata som används för basdata.</span><span class="sxs-lookup"><span data-stu-id="9dcd1-129">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="9dcd1-130">Mer information finns i Flytta [basdata till nya geodatadata i Microsoft 365-datacentret.](moving-data-to-new-datacenter-geos.md)</span><span class="sxs-lookup"><span data-stu-id="9dcd1-130">For more information, see [Moving core data to new Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md).</span></span>


## <a name="deploy-microsoft-365-multi-geo"></a><span data-ttu-id="9dcd1-131">Distribuera Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="9dcd1-131">Deploy Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="9dcd1-132">Med Microsoft 365 Multi-Geo kan organisationen utöka sin Microsoft 365-närvaro till flera geografiska regioner och/eller länder inom din befintliga klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="9dcd1-132">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="9dcd1-133">Mer information finns i [Microsoft 365 Multi-Geo.](microsoft-365-multi-geo.md)</span><span class="sxs-lookup"><span data-stu-id="9dcd1-133">For more information, see [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span></span>

## <a name="manage-multiple-microsoft-365-tenants"></a><span data-ttu-id="9dcd1-134">Hantera flera Microsoft 365-klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="9dcd1-134">Manage multiple Microsoft 365 tenants</span></span> 

<span data-ttu-id="9dcd1-135">Även om det är bra att ha en enda klientorganisation för din organisation, kan du vara en av många organisationer som har flera klientorganisationer.</span><span class="sxs-lookup"><span data-stu-id="9dcd1-135">Although having a single tenant for your oganization is ideal, you may be one of many organizations that have multiple tenants.</span></span> <span data-ttu-id="9dcd1-136">Orsaker kan vara sammanslagningar och förvärv, du vill ha administrativ avgränsning eller om du har en decentraliserad IT.</span><span class="sxs-lookup"><span data-stu-id="9dcd1-136">Reasons can include mergers and aquisitions, you want administrative isolation, or you have a decentralized IT.</span></span>

<span data-ttu-id="9dcd1-137">Om du har flera Microsoft 365-klienter kan du läsa följande artiklar för mer information om:</span><span class="sxs-lookup"><span data-stu-id="9dcd1-137">If you have multiple Microsoft 365 tenants, see these articles for more information about:</span></span>

- [<span data-ttu-id="9dcd1-138">Samarbete mellan klientorganisationer</span><span class="sxs-lookup"><span data-stu-id="9dcd1-138">Inter-tenant collaboration</span></span>](microsoft-365-inter-tenant-collaboration.md)
- [<span data-ttu-id="9dcd1-139">Migrering av postlådor mellan klientorganisationer</span><span class="sxs-lookup"><span data-stu-id="9dcd1-139">Cross-tenant mailbox migration</span></span>](cross-tenant-mailbox-migration.md)
- [<span data-ttu-id="9dcd1-140">Migrering mellan klientorganisationer</span><span class="sxs-lookup"><span data-stu-id="9dcd1-140">Tenant-to-tenant migrations</span></span>](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a><span data-ttu-id="9dcd1-141">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="9dcd1-141">Next step</span></span>

<span data-ttu-id="9dcd1-142">Börja planera för klientorganisationen [med prenumerationer, licenser, konton och klientorganisation.](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)</span><span class="sxs-lookup"><span data-stu-id="9dcd1-142">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>