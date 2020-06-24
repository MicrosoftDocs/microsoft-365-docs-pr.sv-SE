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
ms.openlocfilehash: c64adf870d3669b983e11093196f59c82b1f59e0
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844912"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="c3f1d-104">Förutsättningar för Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c3f1d-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="c3f1d-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="c3f1d-105">**Applies to:**</span></span>
- <span data-ttu-id="c3f1d-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="c3f1d-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="c3f1d-107">Lär dig mer om licensiering och andra krav för etablering och användning av [Microsoft Threat Protection](microsoft-threat-protection.md).</span><span class="sxs-lookup"><span data-stu-id="c3f1d-107">Learn about licensing and other requirements for provisioning and using [Microsoft Threat Protection](microsoft-threat-protection.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="c3f1d-108">Licenskrav</span><span class="sxs-lookup"><span data-stu-id="c3f1d-108">Licensing requirements</span></span>
<span data-ttu-id="c3f1d-109">Alla dessa licenser ger dig tillgång till Microsoft Threat Protection-funktioner i Microsoft 365-säkerhetscenter utan extra kostnad:</span><span class="sxs-lookup"><span data-stu-id="c3f1d-109">Any of these licenses gives you access to Microsoft Threat Protection features in Microsoft 365 security center without additional cost:</span></span>

- <span data-ttu-id="c3f1d-110">Microsoft 365 E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="c3f1d-110">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="c3f1d-111">Microsoft 365 E5-säkerhet eller A5-säkerhet</span><span class="sxs-lookup"><span data-stu-id="c3f1d-111">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="c3f1d-112">Windows 10 Enterprise E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="c3f1d-112">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="c3f1d-113">Enterprise Mobility + Security (EMS) E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="c3f1d-113">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="c3f1d-114">Office 365 E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="c3f1d-114">Office 365 E5 or A5</span></span>
- <span data-ttu-id="c3f1d-115">Microsoft Defender Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="c3f1d-115">Microsoft Defender Advanced Threat Protection</span></span>
- <span data-ttu-id="c3f1d-116">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c3f1d-116">Azure Advanced Threat Protection</span></span> 
- <span data-ttu-id="c3f1d-117">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c3f1d-117">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="c3f1d-118">Avancerat skydd mot Office 365 (plan 2)</span><span class="sxs-lookup"><span data-stu-id="c3f1d-118">Office 365 Advanced Threat Protection (Plan 2)</span></span>

> [!NOTE]
> <span data-ttu-id="c3f1d-119">Utvärderingslicenser för Office 365 ger för närvarande inte åtkomst till Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="c3f1d-119">Trial licenses for Office 365 currently do not provide access to Microsoft Threat Protection.</span></span>

<span data-ttu-id="c3f1d-120">Mer information [finns i Microsoft 365 Enterprise-tjänstplanerna](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="c3f1d-120">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="c3f1d-121">Har du inte licens än?</span><span class="sxs-lookup"><span data-stu-id="c3f1d-121">Don't have license yet?</span></span> [<span data-ttu-id="c3f1d-122">Prova eller köp en Microsoft 365-prenumeration</span><span class="sxs-lookup"><span data-stu-id="c3f1d-122">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="c3f1d-123">Kontrollera dina befintliga licenser</span><span class="sxs-lookup"><span data-stu-id="c3f1d-123">Check your existing  licenses</span></span>
<span data-ttu-id="c3f1d-124">Gå till Microsoft 365 administrationscenter ([admin.microsoft.com](https://admin.microsoft.com/)) för att visa dina befintliga licenser.</span><span class="sxs-lookup"><span data-stu-id="c3f1d-124">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="c3f1d-125">Gå till **Billing**  >  **Faktureringslicenser i administrationscentret**.</span><span class="sxs-lookup"><span data-stu-id="c3f1d-125">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="c3f1d-126">Du måste tilldelas rollen **Faktureringsadministratör** eller **Global läsare** [i Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) för att kunna se licensinformation.</span><span class="sxs-lookup"><span data-stu-id="c3f1d-126">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="c3f1d-127">Om du stöter på åtkomstproblem kontaktar du en global administratör.</span><span class="sxs-lookup"><span data-stu-id="c3f1d-127">If you encounter access problems, contact a global admin.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="c3f1d-128">Nödvändiga behörigheter</span><span class="sxs-lookup"><span data-stu-id="c3f1d-128">Required permissions</span></span>
<span data-ttu-id="c3f1d-129">Du måste vara **global administratör** eller **säkerhetsadministratör** i Azure Active Directory för att kunna aktivera Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="c3f1d-129">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> <span data-ttu-id="c3f1d-130">En lista över roller som krävs för att använda Microsoft Threat Protection och information om hur åtkomst till data regleras läser du om [hur du hanterar åtkomsten till Microsoft Threat Protection](mtp-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="c3f1d-130">For the list of roles required to use Microsoft Threat Protection and information on how access to data is regulated, read about [managing access to Microsoft Threat Protection](mtp-permissions.md).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="c3f1d-131">Krav på webbläsare</span><span class="sxs-lookup"><span data-stu-id="c3f1d-131">Browser requirements</span></span>
<span data-ttu-id="c3f1d-132">Få tillgång till Microsoft Threat Protection i Microsoft 365-säkerhetscentret med Microsoft Edge, Internet Explorer 11 eller valfri HTML 5-kompatibel webbläsare.</span><span class="sxs-lookup"><span data-stu-id="c3f1d-132">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="c3f1d-133">Tillgänglighet till amerikanska GCC, GCC High och andra amerikanska statliga institutioner</span><span class="sxs-lookup"><span data-stu-id="c3f1d-133">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="c3f1d-134">Microsoft Threat Protection är för närvarande *inte* tillgängligt för:</span><span class="sxs-lookup"><span data-stu-id="c3f1d-134">Currently, Microsoft Threat Protection is *not* available to:</span></span>
- <span data-ttu-id="c3f1d-135">Moln för amerikanska myndigheter (GCC)</span><span class="sxs-lookup"><span data-stu-id="c3f1d-135">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="c3f1d-136">Usa:s myndighets molnhög (GCC-hög)</span><span class="sxs-lookup"><span data-stu-id="c3f1d-136">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="c3f1d-137">Usa:s försvarsdepartement</span><span class="sxs-lookup"><span data-stu-id="c3f1d-137">US Department of Defense</span></span>
- <span data-ttu-id="c3f1d-138">Alla amerikanska statliga institutioner med kommersiella licenser</span><span class="sxs-lookup"><span data-stu-id="c3f1d-138">All US government institutions with commercial licenses</span></span>

## <a name="related-topics"></a><span data-ttu-id="c3f1d-139">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="c3f1d-139">Related topics</span></span>
- [<span data-ttu-id="c3f1d-140">Översikt över Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c3f1d-140">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="c3f1d-141">Aktivera Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="c3f1d-141">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
- [<span data-ttu-id="c3f1d-142">Hantera åtkomst och behörigheter</span><span class="sxs-lookup"><span data-stu-id="c3f1d-142">Manage access and permissions</span></span>](mtp-permissions.md)
