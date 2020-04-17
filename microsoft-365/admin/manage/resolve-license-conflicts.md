---
title: Lösa licenskonflikter i Office 365 för företag
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
description: Läs om hur du löser licenskonflikter med din Office 365 för företag-prenumeration.
ms.openlocfilehash: de0a6c988b9ca2ae033a24c012b7f36bc1db58a3
ms.sourcegitcommit: 4988934836eee45c890b9bdd5ef73590656c78ba
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2020
ms.locfileid: "43540921"
---
# <a name="resolve-license-conflicts-in-office-365-for-business"></a><span data-ttu-id="6908f-103">Lösa licenskonflikter i Office 365 för företag</span><span class="sxs-lookup"><span data-stu-id="6908f-103">Resolve license conflicts in Office 365 for business</span></span>

<span data-ttu-id="6908f-104">Vi rekommenderar att du köper de licenser som du behöver för din prenumeration innan du skapar nya användare.</span><span class="sxs-lookup"><span data-stu-id="6908f-104">We recommend that you buy the licenses that you need for your subscription before you create new users.</span></span> <span data-ttu-id="6908f-105">Då kan en licens tilldelas till nya användare när användarkonton skapas.</span><span class="sxs-lookup"><span data-stu-id="6908f-105">That way, a license can be assigned to new users as user accounts are created.</span></span> <span data-ttu-id="6908f-106">Det uppstår licenskonflikter om du redan har tilldelat alla dina licenser till användare, men vissa licenser har gått ut, eller om du försöker ta bort en licens som redan är tilldelad till en användare.</span><span class="sxs-lookup"><span data-stu-id="6908f-106">If you have already assigned all of your licenses to users, but some of the licenses have expired, or you try to remove a license that is already assigned to a user, you will have license conflicts.</span></span> <span data-ttu-id="6908f-107">Mer information finns i [Ta bort licenser från prenumerationen](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="6908f-107">For more information, see [Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>
  
## <a name="how-do-i-view-license-conflicts"></a><span data-ttu-id="6908f-108">Hur visar jag licenskonflikter?</span><span class="sxs-lookup"><span data-stu-id="6908f-108">How do I view license conflicts?</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="6908f-109">Gå till sidan > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Faktureringslicenser</a> i administrationscentret. **Billing**</span><span class="sxs-lookup"><span data-stu-id="6908f-109">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="6908f-110">Gå till sidan > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Faktureringslicenser</a> i administrationscentret. **Billing**</span><span class="sxs-lookup"><span data-stu-id="6908f-110">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="6908f-111">Gå till sidan > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Faktureringslicenser</a> i administrationscentret. **Billing**</span><span class="sxs-lookup"><span data-stu-id="6908f-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="6908f-112">Titta i kolumnen **Status** för information om konflikten.</span><span class="sxs-lookup"><span data-stu-id="6908f-112">Check the **Status** column for information about the conflict.</span></span> <span data-ttu-id="6908f-113">Om det finns en konflikt visas ett varningsmeddelande som säger att en eller flera användare behöver en giltig licens.</span><span class="sxs-lookup"><span data-stu-id="6908f-113">If there's a conflict, you'll see a warning message, that says one or more users need a valid license.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6908f-114">Du kommer inte att se kolumnen **Status** om det inte finns några konflikter.</span><span class="sxs-lookup"><span data-stu-id="6908f-114">You won't see the **Status** column if there are no conflicts.</span></span>

## <a name="how-do-i-resolve-license-conflicts"></a><span data-ttu-id="6908f-115">Hur löser jag licenskonflikter?</span><span class="sxs-lookup"><span data-stu-id="6908f-115">How do I resolve license conflicts?</span></span>

<span data-ttu-id="6908f-116">Du kan lösa licenskonflikter genom att antingen [köpa fler licenser](../../commerce/licenses/buy-licenses.md) eller genom att ta bort licenser från användare som inte längre behöver [dem](remove-licenses-from-users.md).</span><span class="sxs-lookup"><span data-stu-id="6908f-116">You can resolve license conflicts by either [buying more licenses](../../commerce/licenses/buy-licenses.md) or by [removing licenses from users who no longer need them](remove-licenses-from-users.md).</span></span> <span data-ttu-id="6908f-117">Du kan också [ta bort ett användarkonto för att frigöra en licens](../add-users/delete-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="6908f-117">You can optionally [delete a user account to free a license](../add-users/delete-a-user.md).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="6908f-118">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="6908f-118">Related articles</span></span> 

[<span data-ttu-id="6908f-119">Tilldela licenser till användare</span><span class="sxs-lookup"><span data-stu-id="6908f-119">Assign licenses to users</span></span>](assign-licenses-to-users.md)
  
[<span data-ttu-id="6908f-120">Ta bort licenser från användare</span><span class="sxs-lookup"><span data-stu-id="6908f-120">Remove licenses from users</span></span>](remove-licenses-from-users.md)
