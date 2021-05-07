---
title: Skydda användar- och enhetsåtkomst
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/17/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: Lär dig hur du skyddar användare och enheters åtkomst Microsoft 365 data och tjänster och skyddar mot dataförlust.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9ff7bd2ff8b4b333eb30a6cc82797a8968941e0b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "52162337"
---
# <a name="protect-user-and-device-access"></a><span data-ttu-id="37e8e-103">Skydda användar- och enhetsåtkomst</span><span class="sxs-lookup"><span data-stu-id="37e8e-103">Protect user and device access</span></span>

<span data-ttu-id="37e8e-104">Att skydda åtkomsten Microsoft 365 data och tjänster är avgörande för att försvara sig mot cyberattacker och bevaka dataförlust.</span><span class="sxs-lookup"><span data-stu-id="37e8e-104">Protecting access to your Microsoft 365 data and services is crucial to defending against cyberattacks and guarding against data loss.</span></span> <span data-ttu-id="37e8e-105">Samma skydd kan tillämpas på andra SaaS-program i din miljö och även på lokala program som publiceras med Azure Active Directory Programproxy.</span><span class="sxs-lookup"><span data-stu-id="37e8e-105">The same protections can be applied to other SaaS applications in your environment and even to on-premises applications published with Azure Active Directory Application Proxy.</span></span>
  
## <a name="step-1-review-recommendations"></a><span data-ttu-id="37e8e-106">Steg 1: Granska rekommendationer</span><span class="sxs-lookup"><span data-stu-id="37e8e-106">Step 1: Review recommendations</span></span>

<span data-ttu-id="37e8e-107">Rekommenderade funktioner för att skydda identiteter och enheter som kommer åt Office 365, andra SaaS-tjänster och lokala program som publicerats med Azure AD-programproxy.</span><span class="sxs-lookup"><span data-stu-id="37e8e-107">Recommended capabilities for protecting identities and devices that access Office 365, other SaaS services, and on-premises applications published with Azure AD Application Proxy.</span></span>
  
<span data-ttu-id="37e8e-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656)  |  [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657)  |  [Fler språk](https://www.microsoft.com/download/details.aspx?id=55032)</span><span class="sxs-lookup"><span data-stu-id="37e8e-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [More languages](https://www.microsoft.com/download/details.aspx?id=55032)</span></span>
  
## <a name="step-2-protect-administrator-accounts-and-access"></a><span data-ttu-id="37e8e-109">Steg 2: Skydda administratörskonton och åtkomst</span><span class="sxs-lookup"><span data-stu-id="37e8e-109">Step 2: Protect administrator accounts and access</span></span>
<span data-ttu-id="37e8e-110">De administratörskonton du använder för att administrera Microsoft 365-miljön inkluderar förhöjda behörigheter.</span><span class="sxs-lookup"><span data-stu-id="37e8e-110">The administrative accounts you use to administer your Microsoft 365 environment include elevated privileges.</span></span> <span data-ttu-id="37e8e-111">Det här är värdefulla mål för hackare och cyberattacker.</span><span class="sxs-lookup"><span data-stu-id="37e8e-111">These are valuable targets for hackers and cyberattackers.</span></span> 

<span data-ttu-id="37e8e-112">Börja med att bara använda administratörskonton för administration.</span><span class="sxs-lookup"><span data-stu-id="37e8e-112">Begin by using administrator accounts only for administration.</span></span> <span data-ttu-id="37e8e-113">Administratörer bör ha ett separat användarkonto för normal, icke-administrativ användning och bara använda sitt administratörskonto när det behövs för att slutföra en uppgift som är kopplad till jobbfunktionen.</span><span class="sxs-lookup"><span data-stu-id="37e8e-113">Admins should have a separate user account for regular, non-administrative use and only use their administrative account when necessary to complete a task associated with their job function.</span></span>

<span data-ttu-id="37e8e-114">Skydda dina administratörskonton med multifaktorautentisering och villkorlig åtkomst.</span><span class="sxs-lookup"><span data-stu-id="37e8e-114">Protect your administrator accounts with multi-factor authentication and conditional access.</span></span> <span data-ttu-id="37e8e-115">Mer information finns i Skydda [administratörskonton](../security/defender-365-security/identity-access-prerequisites.md#protecting-administrator-accounts).</span><span class="sxs-lookup"><span data-stu-id="37e8e-115">For more information, see [Protecting administrator accounts](../security/defender-365-security/identity-access-prerequisites.md#protecting-administrator-accounts).</span></span> 

<span data-ttu-id="37e8e-116">Konfigurera sedan hantering av behörighet i Office 365.</span><span class="sxs-lookup"><span data-stu-id="37e8e-116">Next, configure privileged access management in Office 365.</span></span> <span data-ttu-id="37e8e-117">Med hantering av behörighetsbehörighet kan du få detaljerad åtkomstkontroll över administrativa uppgifter med Office 365.</span><span class="sxs-lookup"><span data-stu-id="37e8e-117">Privileged access management allows granular access control over privileged admin tasks in Office 365.</span></span> <span data-ttu-id="37e8e-118">Det kan skydda organisationen från överträdelser som kan använda befintliga behöriga administratörskonton med stående åtkomst till känsliga data eller åtkomst till viktiga konfigurationsinställningar.</span><span class="sxs-lookup"><span data-stu-id="37e8e-118">It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span>

- [<span data-ttu-id="37e8e-119">Översikt över hantering av privilegierad åtkomst</span><span class="sxs-lookup"><span data-stu-id="37e8e-119">Overview of privileged access management</span></span>](privileged-access-management-overview.md)
- [<span data-ttu-id="37e8e-120">Konfigurera hantering av privilegierad åtkomst</span><span class="sxs-lookup"><span data-stu-id="37e8e-120">Configure privileged access management</span></span>](privileged-access-management-configuration.md)

<span data-ttu-id="37e8e-121">En annan rekommendation är att använda arbetsstationer som är särskilt konfigurerade för administrativt arbete.</span><span class="sxs-lookup"><span data-stu-id="37e8e-121">Another top recommendation is to use workstations specifically configured for administrative work.</span></span> <span data-ttu-id="37e8e-122">Det här är dedikerade enheter som bara används för administrativa uppgifter.</span><span class="sxs-lookup"><span data-stu-id="37e8e-122">These are dedicated devices that are only used for administrative tasks.</span></span> <span data-ttu-id="37e8e-123">Se [Skydda privilegierad åtkomst.](/windows-server/identity/securing-privileged-access/securing-privileged-access)</span><span class="sxs-lookup"><span data-stu-id="37e8e-123">See [Securing privileged access](/windows-server/identity/securing-privileged-access/securing-privileged-access).</span></span>

<span data-ttu-id="37e8e-124">Slutligen kan du minimera effekterna av oavsiktlig brist på administrativ åtkomst genom att skapa två eller flera konton för nödåtkomst i klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="37e8e-124">Finally, you can mitigate the impact of inadvertent lack of administrative access by creating two or more emergency access accounts in your tenant.</span></span> <span data-ttu-id="37e8e-125">Se [Hantera konton för nödsamtal i Azure AD.](/azure/active-directory/users-groups-roles/directory-emergency-access)</span><span class="sxs-lookup"><span data-stu-id="37e8e-125">See [Manage emergency access accounts in Azure AD](/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span> 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a><span data-ttu-id="37e8e-126">Steg 3: Konfigurera rekommenderade principer för identitet och enhetsåtkomst</span><span class="sxs-lookup"><span data-stu-id="37e8e-126">Step 3: Configure recommended identity and device access policies</span></span>
<span data-ttu-id="37e8e-127">Multifaktorautentisering (MFA) och villkorsstyrda åtkomstprinciper är kraftfulla verktyg för att minska skydd mot komprometterade konton och obehörig åtkomst.</span><span class="sxs-lookup"><span data-stu-id="37e8e-127">Multi-factor authentication (MFA) and conditional access policies are powerful tools for mitigating against compromised accounts and unauthorized access.</span></span> <span data-ttu-id="37e8e-128">Vi rekommenderar att du implementerar en uppsättning principer som har testats tillsammans.</span><span class="sxs-lookup"><span data-stu-id="37e8e-128">We recommend implementing a set of policies that have been tested together.</span></span> <span data-ttu-id="37e8e-129">Mer information, inklusive distributionssteg, finns i [Konfigurationer för identitets- och enhetsåtkomst.](../security/defender-365-security/microsoft-365-policies-configurations.md)</span><span class="sxs-lookup"><span data-stu-id="37e8e-129">For more information, including deployment steps, see [Identity and device access configurations](../security/defender-365-security/microsoft-365-policies-configurations.md).</span></span>

 <span data-ttu-id="37e8e-130">Dessa principer implementerar följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="37e8e-130">These policies implement the following capabilities:</span></span>
- <span data-ttu-id="37e8e-131">Multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="37e8e-131">Mult-factor authentication</span></span>
- <span data-ttu-id="37e8e-132">Villkorlig åtkomst</span><span class="sxs-lookup"><span data-stu-id="37e8e-132">Conditional access</span></span>
- <span data-ttu-id="37e8e-133">Intune-appskydd (app- och dataskydd för enheter)</span><span class="sxs-lookup"><span data-stu-id="37e8e-133">Intune app protection (app and data protection for devices)</span></span>
- <span data-ttu-id="37e8e-134">Intune enhetsefterlevnad</span><span class="sxs-lookup"><span data-stu-id="37e8e-134">Intune device compliance</span></span>
- <span data-ttu-id="37e8e-135">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="37e8e-135">Azure AD Identity Protection</span></span>

<span data-ttu-id="37e8e-136">För implementering av Intune enhetsefterlevnad krävs enhetsregistrering.</span><span class="sxs-lookup"><span data-stu-id="37e8e-136">Implementing Intune device compliance requires device enrollment.</span></span> <span data-ttu-id="37e8e-137">Om du hanterar enheter kan du säkerställa att de är felfria och kompatibla innan du ger dem åtkomst till resurser i din miljö.</span><span class="sxs-lookup"><span data-stu-id="37e8e-137">Managing devices allows you to ensure that they are healthy and compliant before allowing them access to resources in your environment.</span></span> <span data-ttu-id="37e8e-138">Se [Registrera enheter för hantering i Intune](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="37e8e-138">See [Enroll devices for management in Intune](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span></span>

## <a name="step-4-configure-sharepoint-device-access-policies"></a><span data-ttu-id="37e8e-139">Steg 4: Konfigurera SharePoint för enhetsåtkomst</span><span class="sxs-lookup"><span data-stu-id="37e8e-139">Step 4: Configure SharePoint device access policies</span></span>

<span data-ttu-id="37e8e-140">Microsoft rekommenderar att du skyddar innehåll på SharePoint webbplatser med känsligt och starkt reglerat innehåll med enhetsåtkomstkontroller.</span><span class="sxs-lookup"><span data-stu-id="37e8e-140">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls.</span></span> <span data-ttu-id="37e8e-141">Mer information finns i [Principrekommendationer för att skydda SharePoint och filer.](../security/defender-365-security/sharepoint-file-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="37e8e-141">For more information, see [Policy recommendations for securing SharePoint sites and files](../security/defender-365-security/sharepoint-file-access-policies.md).</span></span>



