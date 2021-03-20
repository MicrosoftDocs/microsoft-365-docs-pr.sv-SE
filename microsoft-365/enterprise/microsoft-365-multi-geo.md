---
title: Microsoft 365 Multi-Geo
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: seo-marvel-apr2020
ms.collection: Strat_SP_gtc
localization_priority: Normal
f1.keywords:
- NOCSH
description: I den här artikeln får du lära dig hur du utökar Microsoft 365-närvaron till flera geografiska områden med Microsoft 365 Multi-Geo.
ms.openlocfilehash: 2805470f1a35bb5978f3d25c30aa07523ad21afb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909556"
---
# <a name="microsoft-365-multi-geo"></a><span data-ttu-id="c3c30-103">Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="c3c30-103">Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="c3c30-104">Med Microsoft 365 Multi-Geo kan organisationen utöka sin Microsoft 365-närvaro till flera geografiska regioner och/eller länder inom din befintliga klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="c3c30-104">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span> <span data-ttu-id="c3c30-105">Kontakta ditt Microsoft-kontoteam och registrera ditt Multi-National Company för Microsoft 365 Multi-Geo.</span><span class="sxs-lookup"><span data-stu-id="c3c30-105">Reach out to your Microsoft Account Team to sign up your Multi-National Company for Microsoft 365 Multi-Geo.</span></span>
  
<span data-ttu-id="c3c30-106">Med Microsoft 365 Multi-Geo kan du tillhandahålla och lagra data i vila på de geoplatser som du har valt att uppfylla krav för datalagring och samtidigt låsa upp den globala delen av den moderna produktivitetsupplevelsen för arbetsstyrkan.</span><span class="sxs-lookup"><span data-stu-id="c3c30-106">With Microsoft 365 Multi-Geo, you can provision and store data at rest in the geo locations that you've chosen to meet data residency requirements, and at the same time unlock your global roll out of modern productivity experiences to your workforce.</span></span>

<span data-ttu-id="c3c30-107">En videointroduktion till Microsoft 365 Multi-Geo finns i SharePoint Online och [OneDrive Multi-Geo](https://www.youtube.com/watch?v=Do9U3JuROhk)där du kan styra var dina data finns.</span><span class="sxs-lookup"><span data-stu-id="c3c30-107">For a video introduction to Microsoft 365 Multi-Geo, see [SharePoint Online and OneDrive Multi-Geo to control where your data resides](https://www.youtube.com/watch?v=Do9U3JuROhk).</span></span>

## <a name="multi-geo-architecture"></a><span data-ttu-id="c3c30-108">Multi-Geo-arkitektur</span><span class="sxs-lookup"><span data-stu-id="c3c30-108">Multi-Geo architecture</span></span>

<span data-ttu-id="c3c30-109">I en Multi-Geo-miljö består Microsoft 365-klientorganisationen av en central plats (där Microsoft 365-prenumerationen ursprungligen skapades) och en eller flera satellitplatser.</span><span class="sxs-lookup"><span data-stu-id="c3c30-109">In a Multi-Geo environment, your Microsoft 365 tenant consists of a central location (where your Microsoft 365 subscription was originally provisioned) and one or more satellite locations.</span></span> <span data-ttu-id="c3c30-110">I en flera geoklienter kan du hantera information om geografiska platser, grupper och användarinformation i Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="c3c30-110">In a multi-geo tenant, the information about geo locations, groups, and user information, is mastered in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="c3c30-111">Eftersom din information om klientorganisationen är centraliserad och synkroniserad till varje geoplats, delning och upplevelser som innefattar alla på ditt företag är globala medvetenheten.</span><span class="sxs-lookup"><span data-stu-id="c3c30-111">Because your tenant information is mastered centrally and synchronized into each geo location, sharing and experiences involving anyone from your company contain global awareness.</span></span>

![Skärmbild av en multigeokarta från administrationscentret för SharePoint](../media/multi-geo-world-map.png)

<span data-ttu-id="c3c30-113">Observera att Microsoft 365 Multi-Geo inte är avsett för prestandaoptimering, utan har utformats för att uppfylla krav på datalagring.</span><span class="sxs-lookup"><span data-stu-id="c3c30-113">Note that Microsoft 365 Multi-Geo is not designed for performance optimization, it is designed to meet data residency requirements.</span></span> <span data-ttu-id="c3c30-114">Mer information om prestandaoptimering för Microsoft 365 finns i Nätverksplanering och prestandajustering för [Microsoft 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) eller kontakta supportgruppen.</span><span class="sxs-lookup"><span data-stu-id="c3c30-114">For information about performance optimization for Microsoft 365, see [Network planning and performance tuning for Microsoft 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) or contact your support group.</span></span>

## <a name="terminology"></a><span data-ttu-id="c3c30-115">Terminologi</span><span class="sxs-lookup"><span data-stu-id="c3c30-115">Terminology</span></span>

<span data-ttu-id="c3c30-116">Här är de viktigaste termer som används i beskrivningen av Microsoft 365 Multi-Geo:</span><span class="sxs-lookup"><span data-stu-id="c3c30-116">Here are the key terms used in describing Microsoft 365 Multi-Geo:</span></span>

- <span data-ttu-id="c3c30-117">**Central plats** – den geoplats där klientorganisationen ursprungligen skapades.</span><span class="sxs-lookup"><span data-stu-id="c3c30-117">**Central location** - the geo location where your tenant was originally provisioned.</span></span>
- <span data-ttu-id="c3c30-118">**Geoadministratör** – En administratör som kan administrera en eller flera angivna satellitplatser.</span><span class="sxs-lookup"><span data-stu-id="c3c30-118">**Geo administrator** - An administrator who can administer one or more specified satellite locations.</span></span>
- <span data-ttu-id="c3c30-119">**Geokod** – en kod på tre bokstäver för en viss geoplats.</span><span class="sxs-lookup"><span data-stu-id="c3c30-119">**Geo code** - a three-letter code for a given geo location.</span></span>
- <span data-ttu-id="c3c30-120">**Geoplats** – En geografisk plats som kan användas i en geoklient för flera platser för att lagra data, inklusive Exchange-postlådor och OneDrive- och SharePoint-webbplatser.</span><span class="sxs-lookup"><span data-stu-id="c3c30-120">**Geo location** – A geographic location that can be used in a multi-geo tenant to host data, including Exchange mailboxes and OneDrive and SharePoint sites.</span></span>
- <span data-ttu-id="c3c30-121">**Önskad dataplats (PDL) –** En användaregenskap som anges av administratören som anger var den geoplats där användarnas Exchange-postlåda och OneDrive ska etableras.</span><span class="sxs-lookup"><span data-stu-id="c3c30-121">**Preferred Data Location (PDL)** – A user property set by the administrator that indicates where the geo location where the users Exchange mailbox and OneDrive should be provisioned.</span></span> <span data-ttu-id="c3c30-122">PDL avgör också var SharePoint-webbplatser som skapas av användaren etableras.</span><span class="sxs-lookup"><span data-stu-id="c3c30-122">The PDL also determines where SharePoint sites that are created by the user are provisioned.</span></span>
- <span data-ttu-id="c3c30-123">**Satellitplats** – De geoplatser där Microsoft 365-arbetsbelastningen (SharePoint, OneDrive och Exchange) är aktiverade i en multigeoklient.</span><span class="sxs-lookup"><span data-stu-id="c3c30-123">**Satellite location** – The geo locations where the geo-aware Microsoft 365 workloads (SharePoint, OneDrive, and Exchange) are enabled in a multi-geo tenant.</span></span>
- <span data-ttu-id="c3c30-124">**Klientorganisation** – En organisations representation i Microsoft 365 som normalt har en eller flera domäner kopplade till den (till exempel contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c3c30-124">**Tenant** – An organization's representation in Microsoft 365 which typically has one or more domains associated with it (for example, contoso.com).</span></span>

## <a name="licensing"></a><span data-ttu-id="c3c30-125">Licensiering</span><span class="sxs-lookup"><span data-stu-id="c3c30-125">Licensing</span></span>

<span data-ttu-id="c3c30-126">Microsoft 365 Multi-Geo är tillgänglig som ett tillägg till följande Microsoft 365-abonnemang för Enterprise Agreement-kunder med minst 250 Microsoft 365-platser i klientorganisationen och minst 5 % av dessa platser med multi-geo.</span><span class="sxs-lookup"><span data-stu-id="c3c30-126">Microsoft 365 Multi-Geo is available as an add-on to the following Microsoft 365 subscription plans for Enterprise Agreement customers with a minimum of 250 Microsoft 365 seats in their tenant, and a minimum of 5% of those seats using multi-geo.</span></span> <span data-ttu-id="c3c30-127">Användarprenumerationslicenser måste ha samma Enterprise-avtal som multi-geo services-licenser.</span><span class="sxs-lookup"><span data-stu-id="c3c30-127">User subscription licenses must be on the same Enterprise Agreement as the Multi-Geo Services licenses.</span></span> <span data-ttu-id="c3c30-128">Kontakta ditt Microsoft-kontoteam om du vill ha mer information.</span><span class="sxs-lookup"><span data-stu-id="c3c30-128">Please contact your Microsoft account team for details.</span></span>

- <span data-ttu-id="c3c30-129">Microsoft 365 F1, F3, E3 eller E5</span><span class="sxs-lookup"><span data-stu-id="c3c30-129">Microsoft 365 F1, F3, E3, or E5</span></span>
- <span data-ttu-id="c3c30-130">Office 365 F3, E1, E3 eller E5</span><span class="sxs-lookup"><span data-stu-id="c3c30-130">Office 365 F3, E1, E3, or E5</span></span>
- <span data-ttu-id="c3c30-131">Exchange Online, abonnemang 1 eller abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="c3c30-131">Exchange Online Plan 1 or Plan 2</span></span>
- <span data-ttu-id="c3c30-132">OneDrive för företag-abonnemang 1 eller abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="c3c30-132">OneDrive for Business Plan 1 or Plan 2</span></span>
- <span data-ttu-id="c3c30-133">SharePoint Online (abonnemang 1 eller abonnemang 2)</span><span class="sxs-lookup"><span data-stu-id="c3c30-133">SharePoint Online Plan 1 or Plan 2</span></span>

## <a name="microsoft-365-multi-geo-availability"></a><span data-ttu-id="c3c30-134">Microsoft 365 Multi-Geo-tillgänglighet</span><span class="sxs-lookup"><span data-stu-id="c3c30-134">Microsoft 365 Multi-Geo availability</span></span>

<span data-ttu-id="c3c30-135">Microsoft 365 Multi-Geo erbjuds för närvarande i dessa regioner och länder:</span><span class="sxs-lookup"><span data-stu-id="c3c30-135">Microsoft 365 Multi-Geo is currently offered in these regions and countries:</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="getting-started"></a><span data-ttu-id="c3c30-136">Komma igång</span><span class="sxs-lookup"><span data-stu-id="c3c30-136">Getting started</span></span>

<span data-ttu-id="c3c30-137">Följ de här anvisningarna för att komma igång med multi-geo:</span><span class="sxs-lookup"><span data-stu-id="c3c30-137">Follow these steps to get started with multi-geo:</span></span>

1. <span data-ttu-id="c3c30-138">Arbeta med kontoteamet och lägg till _Multi-Geo Capabilities i Microsoft 365-tjänstabonnemanget._</span><span class="sxs-lookup"><span data-stu-id="c3c30-138">Work with your account team to add the _Multi-Geo Capabilities in Microsoft 365_ service plan.</span></span> <span data-ttu-id="c3c30-139">Du får hjälp med att lägga till det antal licenser som behövs.</span><span class="sxs-lookup"><span data-stu-id="c3c30-139">They will guide you to add the number of licenses needed.</span></span> <span data-ttu-id="c3c30-140">Multi-Geo-funktionen är tillgänglig för EA-kunder med minst 250 Microsoft 365-prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="c3c30-140">Multi-Geo feature is available to EA customers with a minimum of 250 Microsoft 365 subscriptions.</span></span>

   <span data-ttu-id="c3c30-141">Innan du kan börja använda Microsoft 365 Multi-Geo måste Microsoft konfigurera Exchange Online-klienten för multi-geo support.</span><span class="sxs-lookup"><span data-stu-id="c3c30-141">Before you can start using Microsoft 365 Multi-Geo, Microsoft needs to configure your Exchange Online tenant for multi-geo support.</span></span> <span data-ttu-id="c3c30-142">Den här konfigurationen krävs en gång när du beställer *Multi-Geo Capabilities i Microsoft 365-tjänstabonnemanget* och licenserna visas i din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="c3c30-142">This one-time configuration process is triggered after you order the *Multi-Geo Capabilities in Microsoft 365* service plan and the licenses show up in your tenant.</span></span> <span data-ttu-id="c3c30-143">Du får meddelanden om arbetsbelastningsspecifika meddelanden i [Microsoft 365-meddelandecentret](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) när klientorganisationen har slutfört konfigurationsprocessen för varje arbetsbelastning, och sedan kan du börja konfigurera och använda dina Microsoft 365 Multi-Geo-funktioner.</span><span class="sxs-lookup"><span data-stu-id="c3c30-143">You will receive workload-specific notifications in the [Microsoft 365 message center](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) once your tenant has completed the configuration process for each workload, and you then may begin configuring and using your Microsoft 365 Multi-Geo capabilities.</span></span> <span data-ttu-id="c3c30-144">Tiden som krävs för att konfigurera en klientorganisation för Multi-Geo-support varierar från klientorganisation till klientorganisation, men de flesta klientorganisationen slutförs inom en månad efter att du fått funktionslicenserna.</span><span class="sxs-lookup"><span data-stu-id="c3c30-144">The time required to configure a tenant for Multi-Geo support varies from tenant to tenant, but most tenants finish within a month after receipt of the feature licenses.</span></span> <span data-ttu-id="c3c30-145">Större eller mer komplexa klientorganisationen kan behöva mer tid för att slutföra konfigurationsprocessen.</span><span class="sxs-lookup"><span data-stu-id="c3c30-145">Larger or more complex tenants may require more time to complete the configuration process.</span></span> <span data-ttu-id="c3c30-146">Kontakta ditt kontoteam för mer information om din specifika klientorganisation om du skulle behöva den.</span><span class="sxs-lookup"><span data-stu-id="c3c30-146">Please contact your account team for details on your specific tenant should you require it.</span></span>

2. <span data-ttu-id="c3c30-147">Läs [Planera din multigeobaserade miljö](plan-for-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="c3c30-147">Read [Plan your multi-geo environment](plan-for-multi-geo.md).</span></span>

3. <span data-ttu-id="c3c30-148">Lär dig [hur du administrerar en miljö med flera](administering-a-multi-geo-environment.md) geografiska miljöer och hur användarna upplever [miljön.](multi-geo-user-experience.md)</span><span class="sxs-lookup"><span data-stu-id="c3c30-148">Learn about [administering a multi-geo environment](administering-a-multi-geo-environment.md) and [how your users will experience the environment](multi-geo-user-experience.md).</span></span>

4. <span data-ttu-id="c3c30-149">När du är redo att konfigurera Microsoft 365 Multi-Geo konfigurerar [du klientorganisationen för multi-geo.](multi-geo-tenant-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="c3c30-149">When you are ready to set up Microsoft 365 Multi-Geo, [configure your tenant for multi-geo](multi-geo-tenant-configuration.md).</span></span>

5. <span data-ttu-id="c3c30-150">[Konfigurera sökning](configure-search-for-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="c3c30-150">[Set up search](configure-search-for-multi-geo.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c3c30-151">Se även</span><span class="sxs-lookup"><span data-stu-id="c3c30-151">See also</span></span>

[<span data-ttu-id="c3c30-152">Multi-Geo i Exchange Online och OneDrive</span><span class="sxs-lookup"><span data-stu-id="c3c30-152">Multi-Geo in Exchange Online and OneDrive</span></span>](https://Aka.ms/GoMultiGeo)

[<span data-ttu-id="c3c30-153">Multi-Geo Capabilities i OneDrive och SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="c3c30-153">Multi-Geo Capabilities in OneDrive and SharePoint Online</span></span>](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)

[<span data-ttu-id="c3c30-154">Multi-Geo Capabilities i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c3c30-154">Multi-Geo Capabilities in Exchange Online</span></span>](multi-geo-capabilities-in-exchange-online.md)

[<span data-ttu-id="c3c30-155">Teams-upplevelse i en geomiljö med flera miljöer</span><span class="sxs-lookup"><span data-stu-id="c3c30-155">Teams experience in a multi-geo environment</span></span>](/microsoftteams/teams-experience-o365odb-spo-multi-geo)