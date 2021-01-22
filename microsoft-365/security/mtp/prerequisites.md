---
title: Förutsättningar för Microsoft 365 Defender
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
ms.openlocfilehash: ee1777debdb91a6ac73737db2db48e434ed3e2e2
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930096"
---
# <a name="microsoft-365-defender-prerequisites"></a><span data-ttu-id="2ac44-104">Förutsättningar för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2ac44-104">Microsoft 365 Defender prerequisites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2ac44-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="2ac44-105">**Applies to:**</span></span>
- <span data-ttu-id="2ac44-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2ac44-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="2ac44-107">Läs mer om licensiering och andra krav för etablering och användning av [Microsoft 365 Defender.](microsoft-threat-protection.md)</span><span class="sxs-lookup"><span data-stu-id="2ac44-107">Learn about licensing and other requirements for provisioning and using [Microsoft 365 Defender](microsoft-threat-protection.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="2ac44-108">Licenskrav</span><span class="sxs-lookup"><span data-stu-id="2ac44-108">Licensing requirements</span></span>
<span data-ttu-id="2ac44-109">Alla dessa licenser ger dig tillgång till Microsoft 365 Defender-funktionerna i Microsoft 365 säkerhetscenter utan extra kostnad:</span><span class="sxs-lookup"><span data-stu-id="2ac44-109">Any of these licenses gives you access to Microsoft 365 Defender features in Microsoft 365 security center without additional cost:</span></span>

- <span data-ttu-id="2ac44-110">Microsoft 365 E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="2ac44-110">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="2ac44-111">Microsoft 365 E5- eller A5-säkerhet</span><span class="sxs-lookup"><span data-stu-id="2ac44-111">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="2ac44-112">Windows 10 Enterprise, E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="2ac44-112">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="2ac44-113">Enterprise Mobility + Security (EMS) E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="2ac44-113">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="2ac44-114">Office 365 E5 eller A5</span><span class="sxs-lookup"><span data-stu-id="2ac44-114">Office 365 E5 or A5</span></span>
- <span data-ttu-id="2ac44-115">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="2ac44-115">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="2ac44-116">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="2ac44-116">Microsoft Defender for Identity</span></span> 
- <span data-ttu-id="2ac44-117">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2ac44-117">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="2ac44-118">Defender för Office 365 (abonnemang 2)</span><span class="sxs-lookup"><span data-stu-id="2ac44-118">Defender for Office 365 (Plan 2)</span></span>

> [!NOTE]
> <span data-ttu-id="2ac44-119">Utvärderingslicenser för Office 365 ger för närvarande inte åtkomst till Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="2ac44-119">Trial licenses for Office 365 currently do not provide access to Microsoft 365 Defender.</span></span>

<span data-ttu-id="2ac44-120">Mer information finns i [Microsoft 365 Enterprise-tjänstplaner.](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)</span><span class="sxs-lookup"><span data-stu-id="2ac44-120">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="2ac44-121">Har du ingen licens ännu?</span><span class="sxs-lookup"><span data-stu-id="2ac44-121">Don't have license yet?</span></span> [<span data-ttu-id="2ac44-122">Prova eller köp en Microsoft 365-prenumeration</span><span class="sxs-lookup"><span data-stu-id="2ac44-122">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="2ac44-123">Kontrollera dina befintliga licenser</span><span class="sxs-lookup"><span data-stu-id="2ac44-123">Check your existing  licenses</span></span>
<span data-ttu-id="2ac44-124">Gå till administrationscentret för Microsoft 365[(admin.microsoft.com)](https://admin.microsoft.com/)för att visa dina befintliga licenser.</span><span class="sxs-lookup"><span data-stu-id="2ac44-124">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="2ac44-125">Gå till Faktureringslicenser i  >  **administrationscentret.**</span><span class="sxs-lookup"><span data-stu-id="2ac44-125">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="2ac44-126">Du måste vara antingen **faktureringsadministratör eller** **global läsare** [i Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) för att kunna se licensinformation.</span><span class="sxs-lookup"><span data-stu-id="2ac44-126">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="2ac44-127">Kontakta en global administratör om du stöter på åtkomstproblem.</span><span class="sxs-lookup"><span data-stu-id="2ac44-127">If you encounter access problems, contact a global admin.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="2ac44-128">Behörighet som krävs</span><span class="sxs-lookup"><span data-stu-id="2ac44-128">Required permissions</span></span>
<span data-ttu-id="2ac44-129">Du måste vara **global administratör eller** **säkerhetsadministratör i** Azure Active Directory för att kunna aktivera Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="2ac44-129">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> <span data-ttu-id="2ac44-130">Läs om hantering av åtkomst till [Microsoft 365 Defender](mtp-permissions.md)för listan över roller som krävs för att använda Microsoft 365 Defender och information om hur åtkomst till data ska regleras.</span><span class="sxs-lookup"><span data-stu-id="2ac44-130">For the list of roles required to use Microsoft 365 Defender and information on how access to data is regulated, read about [managing access to Microsoft 365 Defender](mtp-permissions.md).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="2ac44-131">Webbläsarkrav</span><span class="sxs-lookup"><span data-stu-id="2ac44-131">Browser requirements</span></span>
<span data-ttu-id="2ac44-132">Access Microsoft 365 Defender i Microsoft 365 säkerhetscenter med hjälp av Microsoft Edge, Internet Explorer 11 eller en HTML 5-kompatibel webbläsare.</span><span class="sxs-lookup"><span data-stu-id="2ac44-132">Access Microsoft 365 Defender in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="2ac44-133">Tillgänglighet till US GCC, GCC High och andra amerikanska statliga myndigheter</span><span class="sxs-lookup"><span data-stu-id="2ac44-133">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="2ac44-134">För närvarande är Microsoft 365 Defender *inte* tillgänglig för:</span><span class="sxs-lookup"><span data-stu-id="2ac44-134">Currently, Microsoft 365 Defender is *not* available to:</span></span>
- <span data-ttu-id="2ac44-135">Us Government Community Cloud (GCC)</span><span class="sxs-lookup"><span data-stu-id="2ac44-135">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="2ac44-136">US Government Community Cloud High (GCC High)</span><span class="sxs-lookup"><span data-stu-id="2ac44-136">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="2ac44-137">USA:s försvar</span><span class="sxs-lookup"><span data-stu-id="2ac44-137">US Department of Defense</span></span>
- <span data-ttu-id="2ac44-138">Alla amerikanska statliga institutioner med kommersiella licenser</span><span class="sxs-lookup"><span data-stu-id="2ac44-138">All US government institutions with commercial licenses</span></span>

## <a name="related-topics"></a><span data-ttu-id="2ac44-139">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="2ac44-139">Related topics</span></span>
- [<span data-ttu-id="2ac44-140">Översikt över Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2ac44-140">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="2ac44-141">Aktivera Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2ac44-141">Turn on Microsoft 365 Defender</span></span>](mtp-enable.md)
- [<span data-ttu-id="2ac44-142">Hantera åtkomst och behörigheter</span><span class="sxs-lookup"><span data-stu-id="2ac44-142">Manage access and permissions</span></span>](mtp-permissions.md)
