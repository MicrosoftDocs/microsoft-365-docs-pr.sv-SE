---
title: Förutsättningar för Microsoft Threat Protection
description: Lär dig mer om licens-, maskinvaru- och programvarukrav och andra konfigurationsinställningar för Microsoft Threat Protection
keywords: krav, krav, hårdvara, mjukvara, webbläsare, MTP, M365, licens, E5, A5, EMS, köp
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 71e7b532e046015dd64e51fd422d276433d65b3a
ms.sourcegitcommit: 6ea9a910a8106a5f1aa589c55d166bfa67fd12a8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2020
ms.locfileid: "44280540"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="047e1-104">Förutsättningar för Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="047e1-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="047e1-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="047e1-105">**Applies to:**</span></span>
- <span data-ttu-id="047e1-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="047e1-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="047e1-107">Lär dig mer om licens-, maskinvaru- och programvarukrav och andra konfigurationsinställningar för att etablera och använda Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="047e1-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="047e1-108">Licenskrav</span><span class="sxs-lookup"><span data-stu-id="047e1-108">Licensing requirements</span></span>

>[!IMPORTANT]
><span data-ttu-id="047e1-109">Från och med den 12 maj 2020 kommer Microsoft gradvis att lansera nya, optimerade upplevelser kring licenskrav och [aktivera Microsoft Threat Protection](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="047e1-109">Starting May 12, 2020, Microsoft will gradually roll out new, optimized experiences around licensing requirements and [turning on Microsoft Threat Protection](mtp-enable.md).</span></span> <span data-ttu-id="047e1-110">Under flera veckor under denna period kommer vissa kunder att börja se ändringar i sina portalupplevelser.</span><span class="sxs-lookup"><span data-stu-id="047e1-110">For several weeks during this period, some customers will start to see changes to their portal experiences.</span></span> <span data-ttu-id="047e1-111">Information om de nya upplevelserna markeras **Ny upplevelse** i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="047e1-111">Information about the new experiences are marked **New experience** in this article.</span></span>

<span data-ttu-id="047e1-112">Om du vill använda Microsoft Threat Protection behöver du antingen en enda licens eller en kombination av licenser.</span><span class="sxs-lookup"><span data-stu-id="047e1-112">To use Microsoft Threat Protection, you need either a single license or a combination of licenses.</span></span> <span data-ttu-id="047e1-113">Dessa licenser eller licenskombinationer ger dig tillgång till Microsoft Threat Protection-funktioner utan extra kostnad.</span><span class="sxs-lookup"><span data-stu-id="047e1-113">These licenses or license combinations give you access to Microsoft Threat Protection features without additional cost.</span></span>

### <a name="single-license"></a><span data-ttu-id="047e1-114">Enkel licens</span><span class="sxs-lookup"><span data-stu-id="047e1-114">Single license</span></span>
<span data-ttu-id="047e1-115">Du kan använda *någon* av följande licenser:</span><span class="sxs-lookup"><span data-stu-id="047e1-115">You can use *one* of the following licenses:</span></span>

- <span data-ttu-id="047e1-116">Microsoft 365 E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="047e1-116">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="047e1-117">Microsoft 365 E5 Security eller A5 Security</span><span class="sxs-lookup"><span data-stu-id="047e1-117">Microsoft 365 E5 Security or A5 Security</span></span>

### <a name="combination-of-licenses"></a><span data-ttu-id="047e1-118">Kombination av licenser</span><span class="sxs-lookup"><span data-stu-id="047e1-118">Combination of licenses</span></span>
<span data-ttu-id="047e1-119">Du kan också använda en kombination av licenser för E5- eller A5-prenumerationer på Office 365, *Enterprise Mobility + Security (EMS)* och Windows.</span><span class="sxs-lookup"><span data-stu-id="047e1-119">You can also use a combination of licenses for E5 or A5 subscriptions to Office 365, *Enterprise Mobility + Security (EMS)*, and Windows.</span></span> <span data-ttu-id="047e1-120">Licenskombinationen måste innehålla *alla* dessa licenser:</span><span class="sxs-lookup"><span data-stu-id="047e1-120">The license combination must include *all* of these licenses:</span></span>

- <span data-ttu-id="047e1-121">Office 365 E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="047e1-121">Office 365 E5 or A5</span></span>
- <span data-ttu-id="047e1-122">*Företagsmobilitet + säkerhet (EMS)* E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="047e1-122">*Enterprise Mobility + Security (EMS)* E5 or A5</span></span>
- <span data-ttu-id="047e1-123">Windows 10 Enterprise E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="047e1-123">Windows 10 Enterprise E5 or A5</span></span>

<span data-ttu-id="047e1-124">Mer information [finns i Microsoft 365 Enterprise-tjänstplanerna](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="047e1-124">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="047e1-125">Har du inte licens än?</span><span class="sxs-lookup"><span data-stu-id="047e1-125">Don't have license yet?</span></span> [<span data-ttu-id="047e1-126">Prova eller köp en Microsoft 365-prenumeration</span><span class="sxs-lookup"><span data-stu-id="047e1-126">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)


<span data-ttu-id="047e1-127">**Ny erfarenhet:** Från och med den 12 maj 2020 kommer kunderna gradvis att få ändringar i den här upplevelsen.</span><span class="sxs-lookup"><span data-stu-id="047e1-127">**New experience:** Starting May 12, 2020, customers will gradually receive changes to this experience.</span></span> <span data-ttu-id="047e1-128">För dem med den nya upplevelsen är möjligheten att aktivera Microsoft Threat Protection tillgänglig för *alla* kunder med någon av följande licenser:</span><span class="sxs-lookup"><span data-stu-id="047e1-128">For those with the new experience, the option to turn on Microsoft Threat Protection will be available to *all* customers with any of the following licenses:</span></span>

- <span data-ttu-id="047e1-129">Microsoft 365 E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="047e1-129">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="047e1-130">Microsoft 365 E5 Security eller A5 Security</span><span class="sxs-lookup"><span data-stu-id="047e1-130">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="047e1-131">Windows 10 Enterprise E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="047e1-131">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="047e1-132">Enterprise Mobility + Security (EMS) E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="047e1-132">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="047e1-133">Office 365 E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="047e1-133">Office 365 E5 or A5</span></span>
- <span data-ttu-id="047e1-134">Microsoft Defender Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="047e1-134">Microsoft Defender Advanced Threat Protection</span></span> 
- <span data-ttu-id="047e1-135">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="047e1-135">Azure Advanced Threat Protection</span></span> 
- <span data-ttu-id="047e1-136">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="047e1-136">Microsoft Cloud App Security</span></span> 
- <span data-ttu-id="047e1-137">Avancerat skydd mot Office 365 (plan 2)</span><span class="sxs-lookup"><span data-stu-id="047e1-137">Office 365 Advanced Threat Protection (Plan 2)</span></span> 

### <a name="check-your-existing--licenses"></a><span data-ttu-id="047e1-138">Kontrollera dina befintliga licenser</span><span class="sxs-lookup"><span data-stu-id="047e1-138">Check your existing  licenses</span></span>
<span data-ttu-id="047e1-139">Gå till Microsoft 365 administrationscenter ([admin.microsoft.com](https://admin.microsoft.com/)) för att visa dina befintliga licenser.</span><span class="sxs-lookup"><span data-stu-id="047e1-139">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="047e1-140">Gå till **Billing**  >  **Faktureringslicenser i administrationscentret**.</span><span class="sxs-lookup"><span data-stu-id="047e1-140">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="047e1-141">Du måste tilldelas rollen **Faktureringsadministratör** eller **Global läsare** [i Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) för att kunna se licensinformation.</span><span class="sxs-lookup"><span data-stu-id="047e1-141">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="047e1-142">Om du stöter på åtkomstproblem kontaktar du en global administratör.</span><span class="sxs-lookup"><span data-stu-id="047e1-142">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="047e1-143">Krav på webbläsare</span><span class="sxs-lookup"><span data-stu-id="047e1-143">Browser requirements</span></span>
<span data-ttu-id="047e1-144">Få tillgång till Microsoft Threat Protection i Microsoft 365-säkerhetscentret med Microsoft Edge, Internet Explorer 11 eller valfri HTML 5-kompatibel webbläsare.</span><span class="sxs-lookup"><span data-stu-id="047e1-144">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="047e1-145">Tillgänglighet till amerikanska GCC, GCC High och andra amerikanska statliga institutioner</span><span class="sxs-lookup"><span data-stu-id="047e1-145">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="047e1-146">Microsoft Threat Protection är för närvarande *inte* tillgängligt för:</span><span class="sxs-lookup"><span data-stu-id="047e1-146">Currently, Microsoft Threat Protection is *not* available to:</span></span>
- <span data-ttu-id="047e1-147">Moln för usa:s myndighetsgemenskap (GCC)</span><span class="sxs-lookup"><span data-stu-id="047e1-147">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="047e1-148">Us-regeringgemenskap moln kick (GCC kick)</span><span class="sxs-lookup"><span data-stu-id="047e1-148">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="047e1-149">Usa:s försvarsdepartement</span><span class="sxs-lookup"><span data-stu-id="047e1-149">US Department of Defense</span></span>
- <span data-ttu-id="047e1-150">Alla amerikanska statliga institutioner med kommersiella licenser</span><span class="sxs-lookup"><span data-stu-id="047e1-150">All US government institutions with commercial licenses</span></span>

## <a name="related-topics"></a><span data-ttu-id="047e1-151">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="047e1-151">Related topics</span></span>
- [<span data-ttu-id="047e1-152">Översikt över Microsofts hotskydd</span><span class="sxs-lookup"><span data-stu-id="047e1-152">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="047e1-153">Aktivera Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="047e1-153">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
