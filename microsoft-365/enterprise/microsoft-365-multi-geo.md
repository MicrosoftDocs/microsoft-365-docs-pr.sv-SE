---
title: Microsoft 365 multi-geo
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: seo-marvel-apr2020
ms.collection: Strat_SP_gtc
localization_priority: Normal
f1.keywords:
- NOCSH
description: I den här artikeln lär du dig hur du expanderar din Microsoft 365-närvaro till flera geografiska regioner med Microsoft 365 multi-geo.
ms.openlocfilehash: a5843b98b5d64dfb3872c3d8a5d48c0e56949c02
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694746"
---
# <a name="microsoft-365-multi-geo"></a><span data-ttu-id="1ee77-103">Microsoft 365 multi-geo</span><span class="sxs-lookup"><span data-stu-id="1ee77-103">Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="1ee77-104">Med Microsoft 365 multi-geo kan din organisation utöka sin Microsoft 365-närvaro till flera geografiska regioner och/eller länder inom din befintliga klient organisation.</span><span class="sxs-lookup"><span data-stu-id="1ee77-104">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span> <span data-ttu-id="1ee77-105">Nå ut till ditt Microsoft-konto för att registrera ett företag med flera nationella inställningar för Microsoft 365 multi-geo.</span><span class="sxs-lookup"><span data-stu-id="1ee77-105">Reach out to your Microsoft Account Team to sign up your Multi-National Company for Microsoft 365 Multi-Geo.</span></span>
  
<span data-ttu-id="1ee77-106">Med Microsoft 365 multi-geo kan du tillhandahålla och lagra data på andra geo platser som du har valt att uppfylla data de kraven och samtidigt låsa upp din globala upplevelse av moderna produktivitets upplevelser till din arbets styrka.</span><span class="sxs-lookup"><span data-stu-id="1ee77-106">With Microsoft 365 Multi-Geo, you can provision and store data at rest in the geo locations that you've chosen to meet data residency requirements, and at the same time unlock your global roll out of modern productivity experiences to your workforce.</span></span>

#### <a name="video-introducing-microsoft-365-multi-geo"></a><span data-ttu-id="1ee77-107">Video: Introduktion till Microsoft 365 multi-geo</span><span class="sxs-lookup"><span data-stu-id="1ee77-107">Video: Introducing Microsoft 365 Multi-Geo</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1Yk6B?autoplay=false]

<span data-ttu-id="1ee77-108">I en multi-geo-miljö består din Microsoft 365-klient organisation av en central plats (där din prenumeration på Microsoft 365 ursprungligen etablerades) och en eller flera satellit platser.</span><span class="sxs-lookup"><span data-stu-id="1ee77-108">In a Multi-Geo environment, your Microsoft 365 tenant consists of a central location (where your Microsoft 365 subscription was originally provisioned) and one or more satellite locations.</span></span> <span data-ttu-id="1ee77-109">I en multi-geo-klient organisation är informationen om geo-platser, grupper och användar information som hanteras i Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="1ee77-109">In a multi-geo tenant, the information about geo locations, groups, and user information, is mastered in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="1ee77-110">Eftersom klient informationen hanteras centralt och synkroniseras till varje Geo-plats, kan delning och erfarenheter involverar vem som helst i ditt företag en global medvetenhet.</span><span class="sxs-lookup"><span data-stu-id="1ee77-110">Because your tenant information is mastered centrally and synchronized into each geo location, sharing and experiences involving anyone from your company contain global awareness.</span></span>

![Skärm bild av en geo-karta från administrations centret för SharePoint](../media/multi-geo-world-map.png)

<span data-ttu-id="1ee77-112">Observera att Microsoft 365 multi-geo inte är utformat för prestanda optimering, att det är utformat för att uppfylla data de kraven.</span><span class="sxs-lookup"><span data-stu-id="1ee77-112">Note that Microsoft 365 Multi-Geo is not designed for performance optimization, it is designed to meet data residency requirements.</span></span> <span data-ttu-id="1ee77-113">Information om prestanda optimering för Microsoft 365 finns i [nätverks planering och prestanda justering för microsoft 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) eller kontakta support gruppen.</span><span class="sxs-lookup"><span data-stu-id="1ee77-113">For information about performance optimization for Microsoft 365, see [Network planning and performance tuning for Microsoft 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) or contact your support group.</span></span>

## <a name="terminology"></a><span data-ttu-id="1ee77-114">Terminologi</span><span class="sxs-lookup"><span data-stu-id="1ee77-114">Terminology</span></span>

<span data-ttu-id="1ee77-115">Här är de viktigaste villkoren som används för att beskriva Microsoft 365 multi-geo:</span><span class="sxs-lookup"><span data-stu-id="1ee77-115">Here are the key terms used in describing Microsoft 365 Multi-Geo:</span></span>

- <span data-ttu-id="1ee77-116">**Central plats** -den Geo-plats där klient organisationen ursprungligen etablerades.</span><span class="sxs-lookup"><span data-stu-id="1ee77-116">**Central location** - the geo location where your tenant was originally provisioned.</span></span>
- <span data-ttu-id="1ee77-117">**Geo-administratör** – en administratör som kan administrera en eller flera angivna satellit platser.</span><span class="sxs-lookup"><span data-stu-id="1ee77-117">**Geo administrator** - An administrator who can administer one or more specified satellite locations.</span></span>
- <span data-ttu-id="1ee77-118">**Geo-kod** – en kod med tre bokstäver för en viss Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="1ee77-118">**Geo code** - a three-letter code for a given geo location.</span></span>
- <span data-ttu-id="1ee77-119">**Geo plats** – en geografisk plats som kan användas i en multi-geo-klient organisation för att hantera data, inklusive Exchange-postlådor och OneDrive-och SharePoint-webbplatser.</span><span class="sxs-lookup"><span data-stu-id="1ee77-119">**Geo location** – A geographic location that can be used in a multi-geo tenant to host data, including Exchange mailboxes and OneDrive and SharePoint sites.</span></span>
- <span data-ttu-id="1ee77-120">**Önskad data plats (PDL)** – en användar egenskap som anges av administratören och anger var den Geo-plats där användarna Exchange-postlådan och OneDrive ska etableras.</span><span class="sxs-lookup"><span data-stu-id="1ee77-120">**Preferred Data Location (PDL)** – A user property set by the administrator that indicates where the geo location where the users Exchange mailbox and OneDrive should be provisioned.</span></span> <span data-ttu-id="1ee77-121">I PDL fastställs också var SharePoint-webbplatser som skapas av användaren etableras.</span><span class="sxs-lookup"><span data-stu-id="1ee77-121">The PDL also determines where SharePoint sites that are created by the user are provisioned.</span></span>
- <span data-ttu-id="1ee77-122">**Satellit plats** – geo platserna där de geo-kompatibla Microsoft 365-arbets belastningarna (SharePoint, OneDrive och Exchange) är aktiverade i en multi-geo-klient organisation.</span><span class="sxs-lookup"><span data-stu-id="1ee77-122">**Satellite location** – The geo locations where the geo-aware Microsoft 365 workloads (SharePoint, OneDrive, and Exchange) are enabled in a multi-geo tenant.</span></span>
- <span data-ttu-id="1ee77-123">**Innehavare** – en organisations representation i Microsoft 365 som normalt har en eller flera domäner kopplade till sig (till exempel contoso.com).</span><span class="sxs-lookup"><span data-stu-id="1ee77-123">**Tenant** – An organization's representation in Microsoft 365 which typically has one or more domains associated with it (for example, contoso.com).</span></span>

## <a name="licensing"></a><span data-ttu-id="1ee77-124">Licensiering</span><span class="sxs-lookup"><span data-stu-id="1ee77-124">Licensing</span></span>

<span data-ttu-id="1ee77-125">Microsoft 365 multi-geo är tillgängligt som ett tillägg till följande Microsoft 365-prenumerations abonnemang för kunder med minst 250 Microsoft 365-platser i sin klient organisation och minst 5% av dessa säten med multi-geo.</span><span class="sxs-lookup"><span data-stu-id="1ee77-125">Microsoft 365 Multi-Geo is available as an add-on to the following Microsoft 365 subscription plans for EA customers with a minimum of 250 Microsoft 365 seats in their tenant, and a minimum of 5% of those seats using multi-geo.</span></span> <span data-ttu-id="1ee77-126">Kontakta ditt Microsoft-konto för mer information.</span><span class="sxs-lookup"><span data-stu-id="1ee77-126">Please contact your Microsoft account team for details.</span></span>

- <span data-ttu-id="1ee77-127">Microsoft 365 F1, E1, E3 eller E5</span><span class="sxs-lookup"><span data-stu-id="1ee77-127">Microsoft 365 F1, E1, E3, or E5</span></span>
- <span data-ttu-id="1ee77-128">Exchange Online-abonnemang 1 eller abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="1ee77-128">Exchange Online Plan 1 or Plan 2</span></span>
- <span data-ttu-id="1ee77-129">OneDrive för företag, abonnemang 1 eller abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="1ee77-129">OneDrive for Business Plan 1 or Plan 2</span></span>
- <span data-ttu-id="1ee77-130">SharePoint Online-abonnemang 1 eller abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="1ee77-130">SharePoint Online Plan 1 or Plan 2</span></span>

## <a name="microsoft-365-multi-geo-availability"></a><span data-ttu-id="1ee77-131">Microsoft 365 multi-geo-tillgänglighet</span><span class="sxs-lookup"><span data-stu-id="1ee77-131">Microsoft 365 Multi-Geo availability</span></span>

<span data-ttu-id="1ee77-132">Microsoft 365 multi-geo erbjuds för närvarande i dessa regioner och länder:</span><span class="sxs-lookup"><span data-stu-id="1ee77-132">Microsoft 365 Multi-Geo is currently offered in these regions and countries:</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="getting-started"></a><span data-ttu-id="1ee77-133">Komma igång</span><span class="sxs-lookup"><span data-stu-id="1ee77-133">Getting started</span></span>

<span data-ttu-id="1ee77-134">Följ de här stegen för att komma igång med multi-geo:</span><span class="sxs-lookup"><span data-stu-id="1ee77-134">Follow these steps to get started with multi-geo:</span></span>

1. <span data-ttu-id="1ee77-135">Arbeta med ditt konto team för att lägga till _flera geo funktioner i Microsoft 365_ service plan.</span><span class="sxs-lookup"><span data-stu-id="1ee77-135">Work with your account team to add the _Multi-Geo Capabilities in Microsoft 365_ service plan.</span></span> <span data-ttu-id="1ee77-136">De hjälper dig att lägga till antalet licenser som behövs.</span><span class="sxs-lookup"><span data-stu-id="1ee77-136">They will guide you to add the number of licenses needed.</span></span> <span data-ttu-id="1ee77-137">Multi-geo-funktionen är tillgänglig för kunder med minst 250 Microsoft 365-abonnemang.</span><span class="sxs-lookup"><span data-stu-id="1ee77-137">Multi-Geo feature is available to EA customers with a minimum of 250 Microsoft 365 subscriptions.</span></span>

   <span data-ttu-id="1ee77-138">Innan du kan börja använda Microsoft 365 multi-geo måste Microsoft konfigurera Exchange Online-klienten för multi-geo-stöd.</span><span class="sxs-lookup"><span data-stu-id="1ee77-138">Before you can start using Microsoft 365 Multi-Geo, Microsoft needs to configure your Exchange Online tenant for multi-geo support.</span></span> <span data-ttu-id="1ee77-139">Denna konfigurations process i real tid utlöses efter att du beställt *flera geo-funktioner i Microsoft 365* service plan och de licenser som visas i klient organisationen.</span><span class="sxs-lookup"><span data-stu-id="1ee77-139">This one-time configuration process is triggered after you order the *Multi-Geo Capabilities in Microsoft 365* service plan and the licenses show up in your tenant.</span></span> <span data-ttu-id="1ee77-140">Du får aviseringar i [meddelande Center för microsoft 365](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) när dina multi-geo-licenser används och sedan kan du börja konfigurera och använda dina Microsoft 365 multi-geo-funktioner.</span><span class="sxs-lookup"><span data-stu-id="1ee77-140">You'll receive notifications in the [Microsoft 365 message center](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) once your Multi-Geo licenses are applied and you then may begin configuring and using your Microsoft 365 Multi-Geo capabilities.</span></span>

2. <span data-ttu-id="1ee77-141">Läs [Planera din multi-geo-miljö](plan-for-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="1ee77-141">Read [Plan your multi-geo environment](plan-for-multi-geo.md).</span></span>

3. <span data-ttu-id="1ee77-142">Lär dig mer om hur du [administrerar en multi-geo-miljö](administering-a-multi-geo-environment.md) och [hur användarna kommer att uppleva miljön](multi-geo-user-experience.md).</span><span class="sxs-lookup"><span data-stu-id="1ee77-142">Learn about [administering a multi-geo environment](administering-a-multi-geo-environment.md) and [how your users will experience the environment](multi-geo-user-experience.md).</span></span>

4. <span data-ttu-id="1ee77-143">När du är redo att konfigurera Microsoft 365 multi-geo konfigurerar du [din klient organisation för multi-geo](multi-geo-tenant-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="1ee77-143">When you are ready to set up Microsoft 365 Multi-Geo, [configure your tenant for multi-geo](multi-geo-tenant-configuration.md).</span></span>

5. <span data-ttu-id="1ee77-144">[Konfigurera sökning](configure-search-for-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="1ee77-144">[Set up search](configure-search-for-multi-geo.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1ee77-145">Se även</span><span class="sxs-lookup"><span data-stu-id="1ee77-145">See also</span></span>

[<span data-ttu-id="1ee77-146">Multi-geo i Exchange Online och OneDrive</span><span class="sxs-lookup"><span data-stu-id="1ee77-146">Multi-Geo in Exchange Online and OneDrive</span></span>](https://Aka.ms/GoMultiGeo)

[<span data-ttu-id="1ee77-147">Multi-geo-funktioner i OneDrive och SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="1ee77-147">Multi-Geo Capabilities in OneDrive and SharePoint Online</span></span>](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)

[<span data-ttu-id="1ee77-148">Multi-geo-funktioner i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="1ee77-148">Multi-Geo Capabilities in Exchange Online</span></span>](multi-geo-capabilities-in-exchange-online.md)

[<span data-ttu-id="1ee77-149">Teams erfarenhet i en multi-geo-miljö</span><span class="sxs-lookup"><span data-stu-id="1ee77-149">Teams experience in a multi-geo environment</span></span>](https://docs.microsoft.com/microsoftteams/teams-experience-o365odb-spo-multi-geo)