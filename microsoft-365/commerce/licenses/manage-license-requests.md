---
title: Hantera licens förfrågningar
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- commerce
ms.custom: MACBillingLicensesRequests
search.appverid:
- MET150
description: Lär dig att granska och godkänna eller avvisa licens förfrågningar från användare för din Microsoft 365 för företag-prenumeration.
ms.date: 08/07/2020
ms.openlocfilehash: cbcdc5550d404278832cc702560ac55f6ace8a44
ms.sourcegitcommit: 9550298946f8accb90cd59be7b46b71d4bf4f8cc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597664"
---
# <a name="manage-license-requests"></a><span data-ttu-id="7c6d4-103">Hantera licens förfrågningar</span><span class="sxs-lookup"><span data-stu-id="7c6d4-103">Manage license requests</span></span>

> [!NOTE]
> <span data-ttu-id="7c6d4-104">Informationen i den här artikeln gäller endast självbetjänings köps produkter.</span><span class="sxs-lookup"><span data-stu-id="7c6d4-104">The information in this article only applies to self-service purchased products.</span></span> <span data-ttu-id="7c6d4-105">Mer information finns i [vanliga frågor och svar om inköp](../subscriptions/self-service-purchase-faq.md).</span><span class="sxs-lookup"><span data-stu-id="7c6d4-105">To learn more, see [Self-service purchase FAQ](../subscriptions/self-service-purchase-faq.md).</span></span>

<span data-ttu-id="7c6d4-106">Om du inaktiverar självbetjänings köp i din organisation kan du använda licens förfrågningar för att hantera processen för licenser för användare.</span><span class="sxs-lookup"><span data-stu-id="7c6d4-106">If you disable self-service purchases in your organization, you can use licenses requests to manage the license request process for your users.</span></span> <span data-ttu-id="7c6d4-107">När en användare försöker göra en självbetjänings köp för en produkt som du har blockerat kan de skicka en begäran om en licens till dig, administratören. När de gör en begäran kan de lägga till namnen på andra användare som också behöver licenser för produkten.</span><span class="sxs-lookup"><span data-stu-id="7c6d4-107">When a user tries to make a self-service purchase for a product that you’ve blocked, they can submit a request for a license to you, the admin. When they make a request, they can add the names of other users who also need licenses for the product.</span></span>

> [!NOTE]
> <span data-ttu-id="7c6d4-108">Om du spärrar användare från att göra självbetjänings köp skickar Microsoft inte ut reklam för e-post.</span><span class="sxs-lookup"><span data-stu-id="7c6d4-108">If you block users from making self-service purchases, Microsoft doesn’t send them marketing emails.</span></span> <span data-ttu-id="7c6d4-109">Om de använder en utvärderings version av en produkt visas inga uppmaningar att köpa den.</span><span class="sxs-lookup"><span data-stu-id="7c6d4-109">Also, if they’re using a trial version of a product, they don’t see prompts to buy it.</span></span> <span data-ttu-id="7c6d4-110">Mer information finns i [Hantera självbetjänings köp (administratör)](../subscriptions/manage-self-service-purchases-admins.md).</span><span class="sxs-lookup"><span data-stu-id="7c6d4-110">To learn more, see [Manage self-service purchases (Admin)](../subscriptions/manage-self-service-purchases-admins.md).</span></span>

<span data-ttu-id="7c6d4-111">För att se och hantera licens förfrågningar använder administratören fliken **begär Anden** på sidan **licensiering** .</span><span class="sxs-lookup"><span data-stu-id="7c6d4-111">To see and manage license requests, admin uses the **Requests** tab on the **Licensing** page.</span></span> <span data-ttu-id="7c6d4-112">I listan visas namnet på den efterfrågade produkten, namnet på den person som begär en licens, datum och status för begäran.</span><span class="sxs-lookup"><span data-stu-id="7c6d4-112">The list shows the name of the product that is requested, name of the person requesting a license, date requested, and status of the request.</span></span> <span data-ttu-id="7c6d4-113">Administratörer kan filtrera listan för att Visa begär Anden som väntar eller slutförts.</span><span class="sxs-lookup"><span data-stu-id="7c6d4-113">Admins can filter the list to show requests that are pending or completed.</span></span> <span data-ttu-id="7c6d4-114">Förfrågningar sparas i 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="7c6d4-114">Requests are held for 30 days.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7c6d4-115">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="7c6d4-115">Before you begin</span></span>

<span data-ttu-id="7c6d4-116">Du måste vara global administratör för att utföra åtgärderna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="7c6d4-116">You must be a Global admin to perform the tasks in this article.</span></span> <span data-ttu-id="7c6d4-117">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="7c6d4-117">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="use-your-own-request-process"></a><span data-ttu-id="7c6d4-118">Använd din egen begäran</span><span class="sxs-lookup"><span data-stu-id="7c6d4-118">Use your own request process</span></span>

<span data-ttu-id="7c6d4-119">Om din organisation har en egen förfrågnings process kan du använda den istället.</span><span class="sxs-lookup"><span data-stu-id="7c6d4-119">If your organization has its own request process, you can use it instead.</span></span> <span data-ttu-id="7c6d4-120">Du skapar ett meddelande som visas för användarna när de efterfrågar en licens.</span><span class="sxs-lookup"><span data-stu-id="7c6d4-120">You create a message that is displayed to users when they request a license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7c6d4-121">Om du använder din egen begär ande process visas inga förfrågningar på fliken **begär** Anden. befintliga förfrågningar från innan du lade till ditt meddelande visas tills du godkänner eller tackar nej.</span><span class="sxs-lookup"><span data-stu-id="7c6d4-121">If you use your own request process, no requests are displayed on the **Requests** tab. Existing requests from before you added your message continue to appear until you approve or decline them.</span></span>

1. <span data-ttu-id="7c6d4-122">I administrations centret går du till sidan **fakturerings**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenser</a> och väljer sedan fliken **begär Anden** .</span><span class="sxs-lookup"><span data-stu-id="7c6d4-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="7c6d4-123">Välj **Använd din befintliga förfrågan i stället**.</span><span class="sxs-lookup"><span data-stu-id="7c6d4-123">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="7c6d4-124">I den högra rutan, i rutan **meddelande** , skriver du det meddelande som du vill att användarna ska se när de efterfrågar en licens.</span><span class="sxs-lookup"><span data-stu-id="7c6d4-124">In the right pane, in the **Message** box, type the message you want users to see when they request a license.</span></span> <span data-ttu-id="7c6d4-125">Om du även vill inkludera en länk till din organisations princip eller annan dokumentation anger du URL-adressen i text rutan **länk till Documentation (valfritt)** .</span><span class="sxs-lookup"><span data-stu-id="7c6d4-125">If you want to also include a link to your organizations policy or other documentation, enter the URL in the **Link to documentation (optional)** text box.</span></span>
4. <span data-ttu-id="7c6d4-126">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="7c6d4-126">Select **Save**.</span></span>

<span data-ttu-id="7c6d4-127">När du går tillbaka till listan **förfrågningar** ser du det meddelande **som du använder för din egen licens förfrågnings process**.</span><span class="sxs-lookup"><span data-stu-id="7c6d4-127">When you return to the **Requests** list, you see the message **You’re using your own license request process**.</span></span> <span data-ttu-id="7c6d4-128">Om du vill göra ändringar i meddelandet som skickas till användarna väljer du **Använd din befintliga förfrågan i stället**.</span><span class="sxs-lookup"><span data-stu-id="7c6d4-128">To make changes to the message that is sent to users, select **Use your existing request process instead**.</span></span>

## <a name="stop-using-your-own-request-process"></a><span data-ttu-id="7c6d4-129">Sluta använda din egen begäran</span><span class="sxs-lookup"><span data-stu-id="7c6d4-129">Stop using your own request process</span></span>

1. <span data-ttu-id="7c6d4-130">I administrations centret går du till sidan **fakturerings**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenser</a> och väljer sedan fliken **begär Anden** .</span><span class="sxs-lookup"><span data-stu-id="7c6d4-130">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="7c6d4-131">Välj **Använd din befintliga förfrågan i stället**.</span><span class="sxs-lookup"><span data-stu-id="7c6d4-131">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="7c6d4-132">I den högra rutan avmarkerar du kryss rutan **Använd min organisations begärans process** .</span><span class="sxs-lookup"><span data-stu-id="7c6d4-132">In the right pane, clear the **Use my organization’s request process** check box.</span></span>
4. <span data-ttu-id="7c6d4-133">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="7c6d4-133">Select **Save**.</span></span>

## <a name="approve-or-deny-a-license-request"></a><span data-ttu-id="7c6d4-134">Godkänna eller neka en licens ansökan</span><span class="sxs-lookup"><span data-stu-id="7c6d4-134">Approve or deny a license request</span></span>

1. <span data-ttu-id="7c6d4-135">I administrations centret går du till sidan **fakturerings**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenser</a> och väljer sedan fliken **begär Anden** .</span><span class="sxs-lookup"><span data-stu-id="7c6d4-135">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="7c6d4-136">Markera raden som innehåller den begäran du vill granska.</span><span class="sxs-lookup"><span data-stu-id="7c6d4-136">Select the row that contains the request you want to review.</span></span> <span data-ttu-id="7c6d4-137">I det högra fönstret visas information om vilka användare som har licenser för produkten.</span><span class="sxs-lookup"><span data-stu-id="7c6d4-137">The right pane shows details about which users want licenses to the product.</span></span>
3. <span data-ttu-id="7c6d4-138">Om du vill neka hela begäran väljer du **Godkänn inte**och väljer **Godkänn inte**i dialog rutan.</span><span class="sxs-lookup"><span data-stu-id="7c6d4-138">To deny the entire request, select **Don’t approve**, and in the dialog box, select **Don’t approve**.</span></span>
4. <span data-ttu-id="7c6d4-139">För att neka vissa användare åt begäran, men Godkänn andra, Välj X efter namnet på de användare som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="7c6d4-139">To deny some users for the request, but approve others, select the X by the name of the users that you want to remove.</span></span> <span data-ttu-id="7c6d4-140">Deras namn flyttas under **tilldela inte dessa användare**.</span><span class="sxs-lookup"><span data-stu-id="7c6d4-140">Their names are moved under **Do not assign to these users**.</span></span>
5. <span data-ttu-id="7c6d4-141">Om du har fler än en produkt väljer du den du vill använda för att tilldela licenser under **Välj en produkt**.</span><span class="sxs-lookup"><span data-stu-id="7c6d4-141">If you have more than one product, under **Select a product**, select the one that you want to use to assign licenses for.</span></span>
6. <span data-ttu-id="7c6d4-142">För att neka användare åtkomst till vissa appar och tjänster expanderar du **Aktivera och inaktivera program och tjänster**och avmarkerar sedan kryss rutorna för de som du vill undanta.</span><span class="sxs-lookup"><span data-stu-id="7c6d4-142">To deny users access to certain app and services, expand **Turn apps and services on or off**, then clear the check boxes for the ones you want to exclude.</span></span>
7. <span data-ttu-id="7c6d4-143">Skriv ett valfritt meddelande i text rutan längst ned i fönstret.</span><span class="sxs-lookup"><span data-stu-id="7c6d4-143">At the bottom of the pane, type an optional message in the text box.</span></span>
8. <span data-ttu-id="7c6d4-144">Välj **Godkänn**när du är klar.</span><span class="sxs-lookup"><span data-stu-id="7c6d4-144">When you’re finished, select **Approve**.</span></span> <span data-ttu-id="7c6d4-145">I det högra fönstret visas information om begäran.</span><span class="sxs-lookup"><span data-stu-id="7c6d4-145">The right pane shows the details of the request.</span></span>
9. <span data-ttu-id="7c6d4-146">Stänga fönstret till höger.</span><span class="sxs-lookup"><span data-stu-id="7c6d4-146">Close the right pane.</span></span>
    <span data-ttu-id="7c6d4-147">Användare får ett e-postmeddelande om att begäran har godkänts eller nekats.</span><span class="sxs-lookup"><span data-stu-id="7c6d4-147">Users receive an email that says their request was approved or denied.</span></span>

## <a name="related-content"></a><span data-ttu-id="7c6d4-148">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="7c6d4-148">Related content</span></span>

<span data-ttu-id="7c6d4-149">[Tilldela licenser till användare](../../admin/manage/assign-licenses-to-users.md) (artikel) </span><span class="sxs-lookup"><span data-stu-id="7c6d4-149">[Assign licenses to users](../../admin/manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="7c6d4-150">[Flytta användare till en annan prenumeration](../subscriptions/move-users-different-subscription.md) (artikel) </span><span class="sxs-lookup"><span data-stu-id="7c6d4-150">[Move users to a different subscription](../subscriptions/move-users-different-subscription.md) (article)</span></span>\
<span data-ttu-id="7c6d4-151">[Köpa eller ta bort prenumerations licenser](buy-licenses.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="7c6d4-151">[Buy or remove subscription licenses](buy-licenses.md) (article)</span></span>