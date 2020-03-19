---
title: Förutsättningar för skydd av Microsoft
description: Lär dig mer om licensiering, maskinvaru- och programvarukrav och andra konfigurationsinställningar för Microsoft Threat Protection
keywords: krav, förutsättningar, hårdvara, mjukvara, webbläsare, MTP, M365, licens, E5, A5, EMS, köp
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
ms.openlocfilehash: c482e46cf51cbf11960c02663221df0c136b067c
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857185"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="c1195-104">Förutsättningar för skydd av Microsoft</span><span class="sxs-lookup"><span data-stu-id="c1195-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="c1195-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="c1195-105">**Applies to:**</span></span>
- <span data-ttu-id="c1195-106">Skydd av Hot mot Microsoft</span><span class="sxs-lookup"><span data-stu-id="c1195-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="c1195-107">Lär dig mer om kraven på licensiering, maskinvara och programvara och andra konfigurationsinställningar för att etablera och använda Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="c1195-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="c1195-108">Licenskrav</span><span class="sxs-lookup"><span data-stu-id="c1195-108">Licensing requirements</span></span>
<span data-ttu-id="c1195-109">Om du vill använda Microsoft Threat Protection behöver du antingen en enda licens eller en kombination av licenser.</span><span class="sxs-lookup"><span data-stu-id="c1195-109">To use Microsoft Threat Protection, you need either a single license or a combination of licenses.</span></span>

### <a name="single-license"></a><span data-ttu-id="c1195-110">Enkel licens</span><span class="sxs-lookup"><span data-stu-id="c1195-110">Single license</span></span>
<span data-ttu-id="c1195-111">Du kan använda *någon* av följande licenser:</span><span class="sxs-lookup"><span data-stu-id="c1195-111">You can use *one* of the following licenses:</span></span>

- <span data-ttu-id="c1195-112">Microsoft 365 E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="c1195-112">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="c1195-113">Microsoft 365 E5-säkerhet eller A5-säkerhet</span><span class="sxs-lookup"><span data-stu-id="c1195-113">Microsoft 365 E5 Security or A5 Security</span></span>

### <a name="combination-of-licenses"></a><span data-ttu-id="c1195-114">Kombination av licenser</span><span class="sxs-lookup"><span data-stu-id="c1195-114">Combination of licenses</span></span>
<span data-ttu-id="c1195-115">Du kan också använda en kombination av licenser för E5- eller A5-prenumerationer på Office 365, *Enterprise Mobility + Security (EMS)* och Windows.</span><span class="sxs-lookup"><span data-stu-id="c1195-115">You can also use a combination of licenses for E5 or A5 subscriptions to Office 365, *Enterprise Mobility + Security (EMS)*, and Windows.</span></span> <span data-ttu-id="c1195-116">Licenskombinationen måste innehålla *alla* dessa licenser:</span><span class="sxs-lookup"><span data-stu-id="c1195-116">The license combination must include *all* of these licenses:</span></span>

- <span data-ttu-id="c1195-117">Office 365 E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="c1195-117">Office 365 E5 or A5</span></span>
- <span data-ttu-id="c1195-118">*Rörlighet för företag + Säkerhet (EMS)* E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="c1195-118">*Enterprise Mobility + Security (EMS)* E5 or A5</span></span>
- <span data-ttu-id="c1195-119">Windows E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="c1195-119">Windows E5 or A5</span></span>

<span data-ttu-id="c1195-120">Mer information [finns i serviceabonnemangen för Microsoft 365 Enterprise](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="c1195-120">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="c1195-121">Har du inte licens än?</span><span class="sxs-lookup"><span data-stu-id="c1195-121">Don't have license yet?</span></span> [<span data-ttu-id="c1195-122">Prova eller köpa en Microsoft 365-prenumeration</span><span class="sxs-lookup"><span data-stu-id="c1195-122">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="c1195-123">Kontrollera dina befintliga licenser</span><span class="sxs-lookup"><span data-stu-id="c1195-123">Check your existing  licenses</span></span>
<span data-ttu-id="c1195-124">Gå till Administrationscentret för Microsoft 365[(admin.microsoft.com](https://admin.microsoft.com/)) för att visa dina befintliga licenser.</span><span class="sxs-lookup"><span data-stu-id="c1195-124">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="c1195-125">Gå till > **Faktureringslicenser**i administrationscentret. **Billing**</span><span class="sxs-lookup"><span data-stu-id="c1195-125">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="c1195-126">Du måste tilldelas antingen rollen **Faktureringsadministratör** eller **Global reader** [i Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) för att kunna se licensinformation.</span><span class="sxs-lookup"><span data-stu-id="c1195-126">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="c1195-127">Om du stöter på åtkomstproblem kontaktar du en global administratör.</span><span class="sxs-lookup"><span data-stu-id="c1195-127">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="c1195-128">Webbläsarkrav</span><span class="sxs-lookup"><span data-stu-id="c1195-128">Browser requirements</span></span>
<span data-ttu-id="c1195-129">Få tillgång till Microsoft Threat Protection i Microsoft 365-säkerhetscentret med Microsoft Edge, Internet Explorer 11 eller en HTML 5-kompatibel webbläsare.</span><span class="sxs-lookup"><span data-stu-id="c1195-129">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="microsoft-threat-protection-for-us-government-community-cloud-and-us-government-community-cloud-high-gcc-high-customers"></a><span data-ttu-id="c1195-130">Microsoft Threat Protection för kunder i den amerikanska regeringen Community Cloud och AMERIKANSKA Government Community Cloud High (GCC High)</span><span class="sxs-lookup"><span data-stu-id="c1195-130">Microsoft Threat Protection for US Government Community Cloud and US Government Community Cloud High (GCC High) customers</span></span>
<span data-ttu-id="c1195-131">För närvarande är Microsoft Threat Protection inte tillgängligt för amerikanska GCC- och GCC High-kunder.</span><span class="sxs-lookup"><span data-stu-id="c1195-131">Currently, Microsoft Threat Protection is not available to US GCC and GCC High customers.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="c1195-132">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="c1195-132">Related topics</span></span>
- [<span data-ttu-id="c1195-133">Översikt över Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c1195-133">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="c1195-134">Aktivera Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c1195-134">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
