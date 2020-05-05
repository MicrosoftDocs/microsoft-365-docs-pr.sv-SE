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
ms.openlocfilehash: 12e68cd8fcd7c784b1d0b4c70c5c25370cbbb409
ms.sourcegitcommit: 997f6227f33c3683ade9672e881d09216df22ee9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2020
ms.locfileid: "44016008"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="900e7-104">Förutsättningar för Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="900e7-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="900e7-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="900e7-105">**Applies to:**</span></span>
- <span data-ttu-id="900e7-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="900e7-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="900e7-107">Lär dig mer om licens-, maskinvaru- och programvarukrav och andra konfigurationsinställningar för att etablera och använda Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="900e7-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="900e7-108">Licenskrav</span><span class="sxs-lookup"><span data-stu-id="900e7-108">Licensing requirements</span></span>

<span data-ttu-id="900e7-109">Om du vill använda Microsoft Threat Protection behöver du antingen en enda licens eller en kombination av licenser.</span><span class="sxs-lookup"><span data-stu-id="900e7-109">To use Microsoft Threat Protection, you need either a single license or a combination of licenses.</span></span> <span data-ttu-id="900e7-110">Dessa licenser eller licenskombinationer ger dig tillgång till Microsoft Threat Protection-funktioner utan extra kostnad.</span><span class="sxs-lookup"><span data-stu-id="900e7-110">These licenses or license combinations give you access to Microsoft Threat Protection features without additional cost.</span></span>

### <a name="single-license"></a><span data-ttu-id="900e7-111">Enkel licens</span><span class="sxs-lookup"><span data-stu-id="900e7-111">Single license</span></span>
<span data-ttu-id="900e7-112">Du kan använda *någon* av följande licenser:</span><span class="sxs-lookup"><span data-stu-id="900e7-112">You can use *one* of the following licenses:</span></span>

- <span data-ttu-id="900e7-113">Microsoft 365 E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="900e7-113">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="900e7-114">Microsoft 365 E5 Security eller A5 Security</span><span class="sxs-lookup"><span data-stu-id="900e7-114">Microsoft 365 E5 Security or A5 Security</span></span>

### <a name="combination-of-licenses"></a><span data-ttu-id="900e7-115">Kombination av licenser</span><span class="sxs-lookup"><span data-stu-id="900e7-115">Combination of licenses</span></span>
<span data-ttu-id="900e7-116">Du kan också använda en kombination av licenser för E5- eller A5-prenumerationer på Office 365, *Enterprise Mobility + Security (EMS)* och Windows.</span><span class="sxs-lookup"><span data-stu-id="900e7-116">You can also use a combination of licenses for E5 or A5 subscriptions to Office 365, *Enterprise Mobility + Security (EMS)*, and Windows.</span></span> <span data-ttu-id="900e7-117">Licenskombinationen måste innehålla *alla* dessa licenser:</span><span class="sxs-lookup"><span data-stu-id="900e7-117">The license combination must include *all* of these licenses:</span></span>

- <span data-ttu-id="900e7-118">Office 365 E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="900e7-118">Office 365 E5 or A5</span></span>
- <span data-ttu-id="900e7-119">*Företagsmobilitet + säkerhet (EMS)* E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="900e7-119">*Enterprise Mobility + Security (EMS)* E5 or A5</span></span>
- <span data-ttu-id="900e7-120">Windows 10 Enterprise E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="900e7-120">Windows 10 Enterprise E5 or A5</span></span>

<span data-ttu-id="900e7-121">Mer information [finns i Microsoft 365 Enterprise-tjänstplanerna](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="900e7-121">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="900e7-122">Har du inte licens än?</span><span class="sxs-lookup"><span data-stu-id="900e7-122">Don't have license yet?</span></span> [<span data-ttu-id="900e7-123">Prova eller köp en Microsoft 365-prenumeration</span><span class="sxs-lookup"><span data-stu-id="900e7-123">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="900e7-124">Kontrollera dina befintliga licenser</span><span class="sxs-lookup"><span data-stu-id="900e7-124">Check your existing  licenses</span></span>
<span data-ttu-id="900e7-125">Gå till Microsoft 365 administrationscenter ([admin.microsoft.com](https://admin.microsoft.com/)) för att visa dina befintliga licenser.</span><span class="sxs-lookup"><span data-stu-id="900e7-125">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="900e7-126">Gå till > **Faktureringslicenser i administrationscentret**. **Billing**</span><span class="sxs-lookup"><span data-stu-id="900e7-126">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="900e7-127">Du måste tilldelas rollen **Faktureringsadministratör** eller **Global läsare** [i Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) för att kunna se licensinformation.</span><span class="sxs-lookup"><span data-stu-id="900e7-127">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="900e7-128">Om du stöter på åtkomstproblem kontaktar du en global administratör.</span><span class="sxs-lookup"><span data-stu-id="900e7-128">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="900e7-129">Krav på webbläsare</span><span class="sxs-lookup"><span data-stu-id="900e7-129">Browser requirements</span></span>
<span data-ttu-id="900e7-130">Få tillgång till Microsoft Threat Protection i Microsoft 365-säkerhetscentret med Microsoft Edge, Internet Explorer 11 eller valfri HTML 5-kompatibel webbläsare.</span><span class="sxs-lookup"><span data-stu-id="900e7-130">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="microsoft-threat-protection-for-us-government-community-cloud-and-us-government-community-cloud-high-gcc-high-customers"></a><span data-ttu-id="900e7-131">Microsoft Threat Protection för kunder i US Government Community Cloud och US Government Community Cloud High (GCC High)</span><span class="sxs-lookup"><span data-stu-id="900e7-131">Microsoft Threat Protection for US Government Community Cloud and US Government Community Cloud High (GCC High) customers</span></span>
<span data-ttu-id="900e7-132">Microsoft Threat Protection är för närvarande inte tillgängligt för kunder med globala globala och globala kunder i USA.</span><span class="sxs-lookup"><span data-stu-id="900e7-132">Currently, Microsoft Threat Protection is not available to US GCC and GCC High customers.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="900e7-133">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="900e7-133">Related topics</span></span>
- [<span data-ttu-id="900e7-134">Översikt över Microsofts hotskydd</span><span class="sxs-lookup"><span data-stu-id="900e7-134">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="900e7-135">Aktivera Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="900e7-135">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
