---
title: Microsoft 365 Defender-krav
description: Läs mer om licens-, maskinvaru- och programvarukrav och andra konfigurationsinställningar för Microsoft 365 Defender
keywords: krav, krav, maskinvara, programvara, webbläsare, Microsoft 365 Defender, M365, licens, E5, A5, EMS, köp
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 69345a0db42ec838dc0758cdb0e93a49a8ba6cfd
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259409"
---
# <a name="microsoft-365-defender-prerequisites"></a><span data-ttu-id="fd2f7-104">Microsoft 365 Defender-krav</span><span class="sxs-lookup"><span data-stu-id="fd2f7-104">Microsoft 365 Defender prerequisites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="fd2f7-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="fd2f7-105">**Applies to:**</span></span>
- <span data-ttu-id="fd2f7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fd2f7-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="fd2f7-107">Läs mer om licensiering och andra krav för etablering och användning [av Microsoft 365 Defender](microsoft-365-defender.md).</span><span class="sxs-lookup"><span data-stu-id="fd2f7-107">Learn about licensing and other requirements for provisioning and using [Microsoft 365 Defender](microsoft-365-defender.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="fd2f7-108">Licenskrav</span><span class="sxs-lookup"><span data-stu-id="fd2f7-108">Licensing requirements</span></span>
<span data-ttu-id="fd2f7-109">Någon av dessa licenser ger dig tillgång Microsoft 365 Defender-funktioner Microsoft 365 säkerhetscenter utan extra kostnad:</span><span class="sxs-lookup"><span data-stu-id="fd2f7-109">Any of these licenses gives you access to Microsoft 365 Defender features in Microsoft 365 security center without additional cost:</span></span>

- <span data-ttu-id="fd2f7-110">Microsoft 365 E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="fd2f7-110">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="fd2f7-111">Microsoft 365 E3 med Microsoft 365 E5 Security tillägg</span><span class="sxs-lookup"><span data-stu-id="fd2f7-111">Microsoft 365 E3 with the Microsoft 365 E5 Security add-on</span></span>
- <span data-ttu-id="fd2f7-112">Microsoft 365 A3 med Microsoft 365 tillägg för A5-säkerhet</span><span class="sxs-lookup"><span data-stu-id="fd2f7-112">Microsoft 365 A3 with the Microsoft 365 A5 Security add-on</span></span>
- <span data-ttu-id="fd2f7-113">Windows 10 Enterprise E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="fd2f7-113">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="fd2f7-114">Enterprise Mobility + Security (EMS) E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="fd2f7-114">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="fd2f7-115">Office 365 E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="fd2f7-115">Office 365 E5 or A5</span></span>
- <span data-ttu-id="fd2f7-116">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="fd2f7-116">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="fd2f7-117">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="fd2f7-117">Microsoft Defender for Identity</span></span> 
- <span data-ttu-id="fd2f7-118">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="fd2f7-118">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="fd2f7-119">Defender för Office 365 (abonnemang 2)</span><span class="sxs-lookup"><span data-stu-id="fd2f7-119">Defender for Office 365 (Plan 2)</span></span>

<span data-ttu-id="fd2f7-120">Mer information finns [i Microsoft 365 Enterprise tjänstplaner.](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)</span><span class="sxs-lookup"><span data-stu-id="fd2f7-120">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="fd2f7-121">Har du inte licens ännu?</span><span class="sxs-lookup"><span data-stu-id="fd2f7-121">Don't have license yet?</span></span> [<span data-ttu-id="fd2f7-122">Prova eller köp en Microsoft 365-prenumeration</span><span class="sxs-lookup"><span data-stu-id="fd2f7-122">Try or buy a Microsoft 365 subscription</span></span>](../../commerce/try-or-buy-microsoft-365.md)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="fd2f7-123">Kontrollera dina befintliga licenser</span><span class="sxs-lookup"><span data-stu-id="fd2f7-123">Check your existing  licenses</span></span>
<span data-ttu-id="fd2f7-124">Gå till Microsoft 365 (i[admin.microsoft.com)](https://admin.microsoft.com/)för att visa dina befintliga licenser.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-124">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="fd2f7-125">Gå till Faktureringslicenser i  >  **administrationscentret.**</span><span class="sxs-lookup"><span data-stu-id="fd2f7-125">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="fd2f7-126">Du måste ha tilldelats rollen **Faktureringsadministratör** **eller Global** läsare i [Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) för att kunna se licensinformation.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-126">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="fd2f7-127">Kontakta en global administratör om du stöter på åtkomstproblem.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-127">If you encounter access problems, contact a global admin.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="fd2f7-128">Behörighet som krävs</span><span class="sxs-lookup"><span data-stu-id="fd2f7-128">Required permissions</span></span>
<span data-ttu-id="fd2f7-129">Du måste vara **global administratör eller** **säkerhetsadministratör i Azure Active Directory** kunna aktivera Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-129">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> <span data-ttu-id="fd2f7-130">Den lista över roller som krävs för att använda Microsoft 365 Defender och information om hur åtkomsten till data är reglerade finns i hantera åtkomst till [Microsoft 365 Defender.](m365d-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="fd2f7-130">For the list of roles required to use Microsoft 365 Defender and information on how access to data is regulated, read about [managing access to Microsoft 365 Defender](m365d-permissions.md).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="fd2f7-131">Webbläsarkrav</span><span class="sxs-lookup"><span data-stu-id="fd2f7-131">Browser requirements</span></span>
<span data-ttu-id="fd2f7-132">Access Microsoft 365 Defender i säkerhetscentret i Microsoft 365 via Microsoft Edge, Internet Explorer 11 eller en HTML 5-kompatibel webbläsare.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-132">Access Microsoft 365 Defender in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="fd2f7-133">Tillgänglighet för amerikanska GCC, GCC hög och andra amerikanska statliga myndigheter</span><span class="sxs-lookup"><span data-stu-id="fd2f7-133">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="fd2f7-134">För närvarande Microsoft 365 Defender *inte* tillgänglig för:</span><span class="sxs-lookup"><span data-stu-id="fd2f7-134">Currently, Microsoft 365 Defender is *not* available to:</span></span>
- <span data-ttu-id="fd2f7-135">Us Government Community Cloud (GCC)</span><span class="sxs-lookup"><span data-stu-id="fd2f7-135">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="fd2f7-136">Us Government Community Cloud High (GCC High)</span><span class="sxs-lookup"><span data-stu-id="fd2f7-136">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="fd2f7-137">US Department of Defense</span><span class="sxs-lookup"><span data-stu-id="fd2f7-137">US Department of Defense</span></span>
- <span data-ttu-id="fd2f7-138">Alla amerikanska statliga myndigheter med kommersiella licenser</span><span class="sxs-lookup"><span data-stu-id="fd2f7-138">All US government institutions with commercial licenses</span></span>

## <a name="related-topics"></a><span data-ttu-id="fd2f7-139">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="fd2f7-139">Related topics</span></span>
- [<span data-ttu-id="fd2f7-140">Microsoft 365 Defender-översikt</span><span class="sxs-lookup"><span data-stu-id="fd2f7-140">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="fd2f7-141">Aktivera Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fd2f7-141">Turn on Microsoft 365 Defender</span></span>](m365d-enable.md)
- [<span data-ttu-id="fd2f7-142">Hantera åtkomst och behörigheter</span><span class="sxs-lookup"><span data-stu-id="fd2f7-142">Manage access and permissions</span></span>](m365d-permissions.md)
