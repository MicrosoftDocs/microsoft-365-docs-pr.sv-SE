---
title: Microsoft 365 Defender-krav
description: Läs mer om licens-, maskinvaru- och programvarukrav och andra konfigurationsinställningar för Microsoft 365 Defender
keywords: krav, förutsättningar, maskinvara, programvara, webbläsare, MTP, M365, licens, E5, A5, EMS, köp
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 0184b2c05121e1ea3bf365263df880548f1b9232
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918876"
---
# <a name="microsoft-365-defender-prerequisites"></a><span data-ttu-id="2c727-104">Microsoft 365 Defender-krav</span><span class="sxs-lookup"><span data-stu-id="2c727-104">Microsoft 365 Defender prerequisites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2c727-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="2c727-105">**Applies to:**</span></span>
- <span data-ttu-id="2c727-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2c727-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="2c727-107">Läs mer om licensiering och andra krav för etablering och användning av [Microsoft 365 Defender.](microsoft-threat-protection.md)</span><span class="sxs-lookup"><span data-stu-id="2c727-107">Learn about licensing and other requirements for provisioning and using [Microsoft 365 Defender](microsoft-threat-protection.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="2c727-108">Licenskrav</span><span class="sxs-lookup"><span data-stu-id="2c727-108">Licensing requirements</span></span>
<span data-ttu-id="2c727-109">Någon av dessa licenser ger dig tillgång till Microsoft 365 Defender-funktioner i Microsoft 365 säkerhetscenter utan extra kostnad:</span><span class="sxs-lookup"><span data-stu-id="2c727-109">Any of these licenses gives you access to Microsoft 365 Defender features in Microsoft 365 security center without additional cost:</span></span>

- <span data-ttu-id="2c727-110">Microsoft 365 E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="2c727-110">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="2c727-111">Microsoft 365 E5-säkerhet eller A5-säkerhet</span><span class="sxs-lookup"><span data-stu-id="2c727-111">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="2c727-112">Windows 10 Enterprise E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="2c727-112">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="2c727-113">Enterprise Mobility + Security (EMS) E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="2c727-113">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="2c727-114">Office 365 E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="2c727-114">Office 365 E5 or A5</span></span>
- <span data-ttu-id="2c727-115">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="2c727-115">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="2c727-116">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="2c727-116">Microsoft Defender for Identity</span></span> 
- <span data-ttu-id="2c727-117">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2c727-117">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="2c727-118">Defender för Office 365 (abonnemang 2)</span><span class="sxs-lookup"><span data-stu-id="2c727-118">Defender for Office 365 (Plan 2)</span></span>

<span data-ttu-id="2c727-119">Mer information finns i [Tjänstplaner för Microsoft 365 Enterprise.](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)</span><span class="sxs-lookup"><span data-stu-id="2c727-119">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="2c727-120">Har du inte licens ännu?</span><span class="sxs-lookup"><span data-stu-id="2c727-120">Don't have license yet?</span></span> [<span data-ttu-id="2c727-121">Prova eller köp en Microsoft 365-prenumeration</span><span class="sxs-lookup"><span data-stu-id="2c727-121">Try or buy a Microsoft 365 subscription</span></span>](../../commerce/try-or-buy-microsoft-365.md?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="2c727-122">Kontrollera dina befintliga licenser</span><span class="sxs-lookup"><span data-stu-id="2c727-122">Check your existing  licenses</span></span>
<span data-ttu-id="2c727-123">Gå till administrationscentret för Microsoft 365[(admin.microsoft.com)](https://admin.microsoft.com/)för att visa dina befintliga licenser.</span><span class="sxs-lookup"><span data-stu-id="2c727-123">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="2c727-124">Gå till Faktureringslicenser i  >  **administrationscentret.**</span><span class="sxs-lookup"><span data-stu-id="2c727-124">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="2c727-125">Du måste ha tilldelats rollen **Faktureringsadministratör** **eller Global** läsare i [Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) för att kunna se licensinformation.</span><span class="sxs-lookup"><span data-stu-id="2c727-125">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="2c727-126">Kontakta en global administratör om du stöter på åtkomstproblem.</span><span class="sxs-lookup"><span data-stu-id="2c727-126">If you encounter access problems, contact a global admin.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="2c727-127">Behörighet som krävs</span><span class="sxs-lookup"><span data-stu-id="2c727-127">Required permissions</span></span>
<span data-ttu-id="2c727-128">Du måste vara **global administratör eller** **säkerhetsadministratör i** Azure Active Directory för att kunna aktivera Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="2c727-128">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> <span data-ttu-id="2c727-129">Listan över roller som krävs för att använda Microsoft 365 Defender och information om hur åtkomst till data är reglerade finns i hantera åtkomst till [Microsoft 365 Defender.](mtp-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="2c727-129">For the list of roles required to use Microsoft 365 Defender and information on how access to data is regulated, read about [managing access to Microsoft 365 Defender](mtp-permissions.md).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="2c727-130">Webbläsarkrav</span><span class="sxs-lookup"><span data-stu-id="2c727-130">Browser requirements</span></span>
<span data-ttu-id="2c727-131">Access Microsoft 365 Defender i Microsoft 365 säkerhetscenter med hjälp av Microsoft Edge, Internet Explorer 11 eller en HTML 5-kompatibel webbläsare.</span><span class="sxs-lookup"><span data-stu-id="2c727-131">Access Microsoft 365 Defender in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="2c727-132">Tillgänglighet till us GCC, GCC High och andra amerikanska statliga myndigheter</span><span class="sxs-lookup"><span data-stu-id="2c727-132">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="2c727-133">Microsoft 365 Defender är för *närvarande inte* tillgänglig för:</span><span class="sxs-lookup"><span data-stu-id="2c727-133">Currently, Microsoft 365 Defender is *not* available to:</span></span>
- <span data-ttu-id="2c727-134">US Government Community Cloud (GCC)</span><span class="sxs-lookup"><span data-stu-id="2c727-134">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="2c727-135">US Government Community Cloud High (GCC High)</span><span class="sxs-lookup"><span data-stu-id="2c727-135">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="2c727-136">US Department of Defense</span><span class="sxs-lookup"><span data-stu-id="2c727-136">US Department of Defense</span></span>
- <span data-ttu-id="2c727-137">Alla amerikanska statliga myndigheter med kommersiella licenser</span><span class="sxs-lookup"><span data-stu-id="2c727-137">All US government institutions with commercial licenses</span></span>

## <a name="related-topics"></a><span data-ttu-id="2c727-138">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="2c727-138">Related topics</span></span>
- [<span data-ttu-id="2c727-139">Översikt över Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2c727-139">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="2c727-140">Aktivera Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2c727-140">Turn on Microsoft 365 Defender</span></span>](mtp-enable.md)
- [<span data-ttu-id="2c727-141">Hantera åtkomst och behörigheter</span><span class="sxs-lookup"><span data-stu-id="2c727-141">Manage access and permissions</span></span>](mtp-permissions.md)