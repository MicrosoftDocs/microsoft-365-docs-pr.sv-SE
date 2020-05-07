---
title: Lösa licenskonflikter
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 796f7eda-b1f8-479a-adee-bd9226ca47ec
description: Läs om hur du löser licenskonflikter med din Microsoft 365 för företag-prenumeration.
ms.openlocfilehash: 7d7da843ba747679f36539bcf920b1b9b2b7ad28
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2020
ms.locfileid: "44139583"
---
# <a name="resolve-license-conflicts"></a><span data-ttu-id="9ce3f-103">Lösa licenskonflikter</span><span class="sxs-lookup"><span data-stu-id="9ce3f-103">Resolve license conflicts</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="9ce3f-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="9ce3f-104">The admin center is changing.</span></span> <span data-ttu-id="9ce3f-105">Om din upplevelse inte stämmer överens med informationen som presenteras här läser du [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="9ce3f-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="9ce3f-106">Vi rekommenderar att du köper de licenser som du behöver för din prenumeration innan du skapar nya användare.</span><span class="sxs-lookup"><span data-stu-id="9ce3f-106">We recommend that you buy the licenses that you need for your subscription before you create new users.</span></span> <span data-ttu-id="9ce3f-107">Då kan en licens tilldelas till nya användare när användarkonton skapas.</span><span class="sxs-lookup"><span data-stu-id="9ce3f-107">That way, a license can be assigned to new users as user accounts are created.</span></span> <span data-ttu-id="9ce3f-108">Det uppstår licenskonflikter om du redan har tilldelat alla dina licenser till användare, men vissa licenser har gått ut, eller om du försöker ta bort en licens som redan är tilldelad till en användare.</span><span class="sxs-lookup"><span data-stu-id="9ce3f-108">If you have already assigned all of your licenses to users, but some of the licenses have expired, or you try to remove a license that is already assigned to a user, you will have license conflicts.</span></span> <span data-ttu-id="9ce3f-109">Mer information finns i [Ta bort licenser från prenumerationen](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="9ce3f-109">For more information, see [Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>
  
## <a name="how-do-i-view-license-conflicts"></a><span data-ttu-id="9ce3f-110">Hur visar jag licenskonflikter?</span><span class="sxs-lookup"><span data-stu-id="9ce3f-110">How do I view license conflicts?</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="9ce3f-111">Gå till sidan > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Faktureringslicenser</a> i administrationscentret. **Billing**</span><span class="sxs-lookup"><span data-stu-id="9ce3f-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="9ce3f-112">Gå till sidan > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Faktureringslicenser</a> i administrationscentret. **Billing**</span><span class="sxs-lookup"><span data-stu-id="9ce3f-112">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="9ce3f-113">Gå till sidan > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Faktureringslicenser</a> i administrationscentret. **Billing**</span><span class="sxs-lookup"><span data-stu-id="9ce3f-113">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="9ce3f-114">Titta i kolumnen **Status** för information om konflikten.</span><span class="sxs-lookup"><span data-stu-id="9ce3f-114">Check the **Status** column for information about the conflict.</span></span> <span data-ttu-id="9ce3f-115">Om det finns en konflikt visas ett varningsmeddelande som säger att en eller flera användare behöver en giltig licens.</span><span class="sxs-lookup"><span data-stu-id="9ce3f-115">If there's a conflict, you'll see a warning message, that says one or more users need a valid license.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9ce3f-116">Du kommer inte att se kolumnen **Status** om det inte finns några konflikter.</span><span class="sxs-lookup"><span data-stu-id="9ce3f-116">You won't see the **Status** column if there are no conflicts.</span></span>

## <a name="how-do-i-resolve-license-conflicts"></a><span data-ttu-id="9ce3f-117">Hur löser jag licenskonflikter?</span><span class="sxs-lookup"><span data-stu-id="9ce3f-117">How do I resolve license conflicts?</span></span>

<span data-ttu-id="9ce3f-118">Du kan lösa licenskonflikter genom att antingen [köpa fler licenser](../../commerce/licenses/buy-licenses.md) eller genom att ta bort licenser från användare som inte längre behöver [dem](remove-licenses-from-users.md).</span><span class="sxs-lookup"><span data-stu-id="9ce3f-118">You can resolve license conflicts by either [buying more licenses](../../commerce/licenses/buy-licenses.md) or by [removing licenses from users who no longer need them](remove-licenses-from-users.md).</span></span> <span data-ttu-id="9ce3f-119">Du kan också [ta bort ett användarkonto för att frigöra en licens](../add-users/delete-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="9ce3f-119">You can optionally [delete a user account to free a license](../add-users/delete-a-user.md).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="9ce3f-120">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="9ce3f-120">Related articles</span></span> 

[<span data-ttu-id="9ce3f-121">Tilldela licenser till användare</span><span class="sxs-lookup"><span data-stu-id="9ce3f-121">Assign licenses to users</span></span>](assign-licenses-to-users.md)
  
[<span data-ttu-id="9ce3f-122">Ta bort licenser från användare</span><span class="sxs-lookup"><span data-stu-id="9ce3f-122">Remove licenses from users</span></span>](remove-licenses-from-users.md)
