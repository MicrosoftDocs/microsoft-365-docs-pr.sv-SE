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
ms.openlocfilehash: 66b3f7e446416b6252050e6f41a2b22d99d25767
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209241"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="25f63-104">Förutsättningar för Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="25f63-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="25f63-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="25f63-105">**Applies to:**</span></span>
- <span data-ttu-id="25f63-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="25f63-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="25f63-107">Lär dig mer om licens-, maskinvaru- och programvarukrav och andra konfigurationsinställningar för att etablera och använda Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="25f63-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="25f63-108">Licenskrav</span><span class="sxs-lookup"><span data-stu-id="25f63-108">Licensing requirements</span></span>

>[!IMPORTANT]
><span data-ttu-id="25f63-109">Från och med den 12 maj 2020 kommer Microsoft gradvis att lansera nya, optimerade upplevelser kring licenskrav och [aktivera Microsoft Threat Protection](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="25f63-109">Starting May 12, 2020, Microsoft will gradually roll out new, optimized experiences around licensing requirements and [turning on Microsoft Threat Protection](mtp-enable.md).</span></span> <span data-ttu-id="25f63-110">Under flera veckor under denna period kommer vissa kunder att börja se ändringar i sina portalupplevelser.</span><span class="sxs-lookup"><span data-stu-id="25f63-110">For several weeks during this period, some customers will start to see changes to their portal experiences.</span></span> <span data-ttu-id="25f63-111">Information om de nya upplevelserna markeras **Ny upplevelse** i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="25f63-111">Information about the new experiences are marked **New experience** in this article.</span></span>

<span data-ttu-id="25f63-112">Om du vill använda Microsoft Threat Protection behöver du antingen en enda licens eller en kombination av licenser.</span><span class="sxs-lookup"><span data-stu-id="25f63-112">To use Microsoft Threat Protection, you need either a single license or a combination of licenses.</span></span> <span data-ttu-id="25f63-113">Dessa licenser eller licenskombinationer ger dig tillgång till Microsoft Threat Protection-funktioner utan extra kostnad.</span><span class="sxs-lookup"><span data-stu-id="25f63-113">These licenses or license combinations give you access to Microsoft Threat Protection features without additional cost.</span></span>

### <a name="single-license"></a><span data-ttu-id="25f63-114">Enkel licens</span><span class="sxs-lookup"><span data-stu-id="25f63-114">Single license</span></span>
<span data-ttu-id="25f63-115">Du kan använda *någon* av följande licenser:</span><span class="sxs-lookup"><span data-stu-id="25f63-115">You can use *one* of the following licenses:</span></span>

- <span data-ttu-id="25f63-116">Microsoft 365 E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="25f63-116">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="25f63-117">Microsoft 365 E5 Security eller A5 Security</span><span class="sxs-lookup"><span data-stu-id="25f63-117">Microsoft 365 E5 Security or A5 Security</span></span>

### <a name="combination-of-licenses"></a><span data-ttu-id="25f63-118">Kombination av licenser</span><span class="sxs-lookup"><span data-stu-id="25f63-118">Combination of licenses</span></span>
<span data-ttu-id="25f63-119">Du kan också använda en kombination av licenser för E5- eller A5-prenumerationer på Office 365, *Enterprise Mobility + Security (EMS)* och Windows.</span><span class="sxs-lookup"><span data-stu-id="25f63-119">You can also use a combination of licenses for E5 or A5 subscriptions to Office 365, *Enterprise Mobility + Security (EMS)*, and Windows.</span></span> <span data-ttu-id="25f63-120">Licenskombinationen måste innehålla *alla* dessa licenser:</span><span class="sxs-lookup"><span data-stu-id="25f63-120">The license combination must include *all* of these licenses:</span></span>

- <span data-ttu-id="25f63-121">Office 365 E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="25f63-121">Office 365 E5 or A5</span></span>
- <span data-ttu-id="25f63-122">*Företagsmobilitet + säkerhet (EMS)* E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="25f63-122">*Enterprise Mobility + Security (EMS)* E5 or A5</span></span>
- <span data-ttu-id="25f63-123">Windows 10 Enterprise E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="25f63-123">Windows 10 Enterprise E5 or A5</span></span>

<span data-ttu-id="25f63-124">Mer information [finns i Microsoft 365 Enterprise-tjänstplanerna](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="25f63-124">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="25f63-125">Har du inte licens än?</span><span class="sxs-lookup"><span data-stu-id="25f63-125">Don't have license yet?</span></span> [<span data-ttu-id="25f63-126">Prova eller köp en Microsoft 365-prenumeration</span><span class="sxs-lookup"><span data-stu-id="25f63-126">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)


<span data-ttu-id="25f63-127">**Ny erfarenhet:** Från och med den 12 maj 2020 kommer kunderna gradvis att få ändringar i den här upplevelsen.</span><span class="sxs-lookup"><span data-stu-id="25f63-127">**New experience:** Starting May 12, 2020, customers will gradually receive changes to this experience.</span></span> <span data-ttu-id="25f63-128">För dem med den nya upplevelsen är möjligheten att aktivera Microsoft Threat Protection tillgänglig för *alla* kunder med någon av följande licenser:</span><span class="sxs-lookup"><span data-stu-id="25f63-128">For those with the new experience, the option to turn on Microsoft Threat Protection will be available to *all* customers with any of the following licenses:</span></span>

- <span data-ttu-id="25f63-129">Microsoft 365 E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="25f63-129">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="25f63-130">Microsoft 365 E5 Security eller A5 Security</span><span class="sxs-lookup"><span data-stu-id="25f63-130">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="25f63-131">Windows 10 Enterprise E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="25f63-131">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="25f63-132">Enterprise Mobility + Security (EMS) E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="25f63-132">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="25f63-133">Office 365 E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="25f63-133">Office 365 E5 or A5</span></span>
- <span data-ttu-id="25f63-134">Microsoft Defender Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="25f63-134">Microsoft Defender Advanced Threat Protection</span></span> 
- <span data-ttu-id="25f63-135">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="25f63-135">Azure Advanced Threat Protection</span></span> 
- <span data-ttu-id="25f63-136">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="25f63-136">Microsoft Cloud App Security</span></span> 
- <span data-ttu-id="25f63-137">Avancerat skydd mot Office 365 (plan 2)</span><span class="sxs-lookup"><span data-stu-id="25f63-137">Office 365 Advanced Threat Protection (Plan 2)</span></span> 

### <a name="check-your-existing--licenses"></a><span data-ttu-id="25f63-138">Kontrollera dina befintliga licenser</span><span class="sxs-lookup"><span data-stu-id="25f63-138">Check your existing  licenses</span></span>
<span data-ttu-id="25f63-139">Gå till Microsoft 365 administrationscenter ([admin.microsoft.com](https://admin.microsoft.com/)) för att visa dina befintliga licenser.</span><span class="sxs-lookup"><span data-stu-id="25f63-139">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="25f63-140">Gå till **Billing**  >  **Faktureringslicenser i administrationscentret**.</span><span class="sxs-lookup"><span data-stu-id="25f63-140">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="25f63-141">Du måste tilldelas rollen **Faktureringsadministratör** eller **Global läsare** [i Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) för att kunna se licensinformation.</span><span class="sxs-lookup"><span data-stu-id="25f63-141">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="25f63-142">Om du stöter på åtkomstproblem kontaktar du en global administratör.</span><span class="sxs-lookup"><span data-stu-id="25f63-142">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="25f63-143">Krav på webbläsare</span><span class="sxs-lookup"><span data-stu-id="25f63-143">Browser requirements</span></span>
<span data-ttu-id="25f63-144">Få tillgång till Microsoft Threat Protection i Microsoft 365-säkerhetscentret med Microsoft Edge, Internet Explorer 11 eller valfri HTML 5-kompatibel webbläsare.</span><span class="sxs-lookup"><span data-stu-id="25f63-144">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="us-gcc-and-gcc-high-availability"></a><span data-ttu-id="25f63-145">Us GCC och GCC Hög tillgänglighet</span><span class="sxs-lookup"><span data-stu-id="25f63-145">US GCC and GCC High availability</span></span>
<span data-ttu-id="25f63-146">Microsoft Threat Protection är för närvarande inte tillgängligt för kunder i GCC-molnet (Cloud) och Government Community Cloud High (GCC High).</span><span class="sxs-lookup"><span data-stu-id="25f63-146">Currently, Microsoft Threat Protection is not available to US Government Community Cloud (GCC) and Government Community Cloud High (GCC High) customers.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="25f63-147">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="25f63-147">Related topics</span></span>
- [<span data-ttu-id="25f63-148">Översikt över Microsofts hotskydd</span><span class="sxs-lookup"><span data-stu-id="25f63-148">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="25f63-149">Aktivera Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="25f63-149">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
