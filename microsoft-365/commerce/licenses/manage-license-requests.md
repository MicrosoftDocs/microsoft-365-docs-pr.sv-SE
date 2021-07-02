---
title: Hantera licensbegäranden
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: micurn, nicholak
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- MACBillingLicensesRequests
- AdminSurgePortfolio
- commerce_licensing
search.appverid: MET150
description: Läs om hur du granskar och godkänner eller nekar licensbegäranden från användare för Microsoft 365 för företag-prenumerationen.
ms.date: 06/07/2021
ms.openlocfilehash: 23258d21ebb413c56323aa4dab25cee60baf2be0
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256813"
---
# <a name="manage-license-requests"></a><span data-ttu-id="8aa00-103">Hantera licensbegäranden</span><span class="sxs-lookup"><span data-stu-id="8aa00-103">Manage license requests</span></span>

> [!NOTE]
> <span data-ttu-id="8aa00-104">Informationen i den här artikeln gäller endast självbetjäningsprodukter som köpts.</span><span class="sxs-lookup"><span data-stu-id="8aa00-104">The information in this article only applies to self-service purchased products.</span></span> <span data-ttu-id="8aa00-105">Mer information finns i Vanliga frågor [och svar om självbetjäning för köp.](../subscriptions/self-service-purchase-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="8aa00-105">To learn more, see [Self-service purchase FAQ](../subscriptions/self-service-purchase-faq.yml).</span></span>

<span data-ttu-id="8aa00-106">Om du inaktiverar självbetjäning för köp i organisationen kan du använda licensförfrågningar för att hantera licensbegäran för användarna.</span><span class="sxs-lookup"><span data-stu-id="8aa00-106">If you disable self-service purchases in your organization, you can use licenses requests to manage the license request process for your users.</span></span> <span data-ttu-id="8aa00-107">När en användare försöker göra ett självbetjäningsköp för en produkt som du har blockerat kan han/hon skicka en begäran om en licens till dig som administratör. När de gör en begäran kan de lägga till namnen på andra användare som också behöver licenser för produkten.</span><span class="sxs-lookup"><span data-stu-id="8aa00-107">When a user tries to make a self-service purchase for a product that you’ve blocked, they can submit a request for a license to you, the admin. When they make a request, they can add the names of other users who also need licenses for the product.</span></span>

> [!NOTE]
> <span data-ttu-id="8aa00-108">Om du blockerar användare från att göra köp via självbetjäning skickar Microsoft inte marknadsföringsmeddelanden till dem.</span><span class="sxs-lookup"><span data-stu-id="8aa00-108">If you block users from making self-service purchases, Microsoft doesn’t send them marketing emails.</span></span> <span data-ttu-id="8aa00-109">Om de använder en utvärderingsversion av en produkt ser de heller inte uppmaningarna att köpa den.</span><span class="sxs-lookup"><span data-stu-id="8aa00-109">Also, if they’re using a trial version of a product, they don’t see prompts to buy it.</span></span> <span data-ttu-id="8aa00-110">Mer information finns i [Hantera självbetjäning för köp (administratör)](../subscriptions/manage-self-service-purchases-admins.md).</span><span class="sxs-lookup"><span data-stu-id="8aa00-110">To learn more, see [Manage self-service purchases (Admin)](../subscriptions/manage-self-service-purchases-admins.md).</span></span>

<span data-ttu-id="8aa00-111">För att visa och hantera licensbegäranden använder administratören **fliken** Begäranden på **sidan** Licensiering.</span><span class="sxs-lookup"><span data-stu-id="8aa00-111">To see and manage license requests, admin uses the **Requests** tab on the **Licensing** page.</span></span> <span data-ttu-id="8aa00-112">Listan visar namnet på den produkt som begärs, namnet på den person som begär en licens, begärt datum och status för begäran.</span><span class="sxs-lookup"><span data-stu-id="8aa00-112">The list shows the name of the product that is requested, name of the person requesting a license, date requested, and status of the request.</span></span> <span data-ttu-id="8aa00-113">Administratörer kan filtrera listan för att visa väntande eller slutförda begäranden.</span><span class="sxs-lookup"><span data-stu-id="8aa00-113">Admins can filter the list to show requests that are pending or completed.</span></span> <span data-ttu-id="8aa00-114">Begäranden hålls i 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="8aa00-114">Requests are held for 30 days.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8aa00-115">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="8aa00-115">Before you begin</span></span>

<span data-ttu-id="8aa00-116">Du måste vara global administratör för att utföra uppgifterna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="8aa00-116">You must be a Global admin to perform the tasks in this article.</span></span> <span data-ttu-id="8aa00-117">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="8aa00-117">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="use-your-own-request-process"></a><span data-ttu-id="8aa00-118">Använd din egen process för förfrågan</span><span class="sxs-lookup"><span data-stu-id="8aa00-118">Use your own request process</span></span>

<span data-ttu-id="8aa00-119">Om din organisation har en egen process för begäran kan du använda den i stället.</span><span class="sxs-lookup"><span data-stu-id="8aa00-119">If your organization has its own request process, you can use it instead.</span></span> <span data-ttu-id="8aa00-120">Du skapar ett meddelande som visas för användarna när de begär en licens.</span><span class="sxs-lookup"><span data-stu-id="8aa00-120">You create a message that is displayed to users when they request a license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8aa00-121">Om du använder en egen begärandeprocess visas inga begäranden på **fliken Begäranden.** Befintliga förfrågningar från innan du lagt till meddelandet fortsätter att visas tills du godkänner eller avböjer dem.</span><span class="sxs-lookup"><span data-stu-id="8aa00-121">If you use your own request process, no requests are displayed on the **Requests** tab. Existing requests from before you added your message continue to appear until you approve or decline them.</span></span>

1. <span data-ttu-id="8aa00-122">I administrationscentret går du till sidan  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Faktureringslicenser</a> och väljer sedan **fliken Begäranden.**</span><span class="sxs-lookup"><span data-stu-id="8aa00-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="8aa00-123">Välj **Använd din befintliga begärandeprocess i stället**.</span><span class="sxs-lookup"><span data-stu-id="8aa00-123">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="8aa00-124">I det högra fönstret, i rutan **Meddelande,** skriver du det meddelande som du vill att användare ska se när de begär en licens.</span><span class="sxs-lookup"><span data-stu-id="8aa00-124">In the right pane, in the **Message** box, type the message you want users to see when they request a license.</span></span> <span data-ttu-id="8aa00-125">Om du även vill ta med en länk till organisationens policy eller annan dokumentation anger du URL-adressen i textrutan **Länka** till dokumentation (valfritt).</span><span class="sxs-lookup"><span data-stu-id="8aa00-125">If you want to also include a link to your organizations policy or other documentation, enter the URL in the **Link to documentation (optional)** text box.</span></span>
4. <span data-ttu-id="8aa00-126">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8aa00-126">Select **Save**.</span></span>

<span data-ttu-id="8aa00-127">När du återgår **till listan** Begäranden visas meddelandet Du använder din egen process **för licensbegäran.**</span><span class="sxs-lookup"><span data-stu-id="8aa00-127">When you return to the **Requests** list, you see the message **You’re using your own license request process**.</span></span> <span data-ttu-id="8aa00-128">Om du vill ändra meddelandet som skickas till användarna väljer du Använd **din befintliga begäran i stället.**</span><span class="sxs-lookup"><span data-stu-id="8aa00-128">To make changes to the message that is sent to users, select **Use your existing request process instead**.</span></span>

## <a name="stop-using-your-own-request-process"></a><span data-ttu-id="8aa00-129">Sluta använda din egen process för begäran</span><span class="sxs-lookup"><span data-stu-id="8aa00-129">Stop using your own request process</span></span>

1. <span data-ttu-id="8aa00-130">I administrationscentret går du till sidan  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Faktureringslicenser</a> och väljer sedan **fliken Begäranden.**</span><span class="sxs-lookup"><span data-stu-id="8aa00-130">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="8aa00-131">Välj **Använd din befintliga begärandeprocess i stället**.</span><span class="sxs-lookup"><span data-stu-id="8aa00-131">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="8aa00-132">I det högra fönstret avmarkerar **du kryssrutan Använd organisationens** begärandeprocess.</span><span class="sxs-lookup"><span data-stu-id="8aa00-132">In the right pane, clear the **Use my organization’s request process** check box.</span></span>
4. <span data-ttu-id="8aa00-133">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8aa00-133">Select **Save**.</span></span>

## <a name="approve-or-deny-a-license-request"></a><span data-ttu-id="8aa00-134">Godkänna eller neka en licensbegäran</span><span class="sxs-lookup"><span data-stu-id="8aa00-134">Approve or deny a license request</span></span>

1. <span data-ttu-id="8aa00-135">I administrationscentret går du till sidan  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Faktureringslicenser</a> och väljer sedan **fliken Begäranden.**</span><span class="sxs-lookup"><span data-stu-id="8aa00-135">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="8aa00-136">Markera raden som innehåller den begäran du vill granska.</span><span class="sxs-lookup"><span data-stu-id="8aa00-136">Select the row that contains the request you want to review.</span></span> <span data-ttu-id="8aa00-137">I fönstret till höger visas information om vilka användare som vill ha licenser för produkten.</span><span class="sxs-lookup"><span data-stu-id="8aa00-137">The right pane shows details about which users want licenses to the product.</span></span>
3. <span data-ttu-id="8aa00-138">Om du vill neka hela begäran **väljer du Godkänn inte** och i dialogrutan väljer du Godkänn **inte.**</span><span class="sxs-lookup"><span data-stu-id="8aa00-138">To deny the entire request, select **Don’t approve**, and in the dialog box, select **Don’t approve**.</span></span>
4. <span data-ttu-id="8aa00-139">Om du vill neka vissa användare för begäran, men godkänna andra, väljer du X vid namnet på de användare som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="8aa00-139">To deny some users for the request, but approve others, select the X by the name of the users that you want to remove.</span></span> <span data-ttu-id="8aa00-140">Deras namn flyttas under **Tilldela inte till dessa användare.**</span><span class="sxs-lookup"><span data-stu-id="8aa00-140">Their names are moved under **Do not assign to these users**.</span></span>
5. <span data-ttu-id="8aa00-141">Om du har fler än en produkt **väljer** du den produkt som du vill använda för att tilldela licenser för under Välj en produkt.</span><span class="sxs-lookup"><span data-stu-id="8aa00-141">If you have more than one product, under **Select a product**, select the one that you want to use to assign licenses for.</span></span>
6. <span data-ttu-id="8aa00-142">Om du vill neka användare åtkomst till vissa appar och tjänster expanderar du Aktivera eller inaktivera appar och tjänster och avmarkerar sedan kryssrutorna för de du vill utesluta.</span><span class="sxs-lookup"><span data-stu-id="8aa00-142">To deny users access to certain app and services, expand **Turn apps and services on or off**, then clear the check boxes for the ones you want to exclude.</span></span>
7. <span data-ttu-id="8aa00-143">Skriv ett meddelande (valfritt) i textrutan längst ned i fönstret.</span><span class="sxs-lookup"><span data-stu-id="8aa00-143">At the bottom of the pane, type an optional message in the text box.</span></span>
8. <span data-ttu-id="8aa00-144">När du är klar väljer du **Godkänn**.</span><span class="sxs-lookup"><span data-stu-id="8aa00-144">When you’re finished, select **Approve**.</span></span> <span data-ttu-id="8aa00-145">I det högra fönstret visas information om begäran.</span><span class="sxs-lookup"><span data-stu-id="8aa00-145">The right pane shows the details of the request.</span></span>
9. <span data-ttu-id="8aa00-146">Stäng det högra fönstret.</span><span class="sxs-lookup"><span data-stu-id="8aa00-146">Close the right pane.</span></span>
    <span data-ttu-id="8aa00-147">Användarna får ett e-postmeddelande om att begäran har godkänts eller nekats.</span><span class="sxs-lookup"><span data-stu-id="8aa00-147">Users receive an email that says their request was approved or denied.</span></span>

## <a name="related-content"></a><span data-ttu-id="8aa00-148">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="8aa00-148">Related content</span></span>

<span data-ttu-id="8aa00-149">[Tilldela licenser till användare](../../admin/manage/assign-licenses-to-users.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="8aa00-149">[Assign licenses to users](../../admin/manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="8aa00-150">[Flytta användare till en annan prenumeration](../subscriptions/move-users-different-subscription.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="8aa00-150">[Move users to a different subscription](../subscriptions/move-users-different-subscription.md) (article)</span></span>\
<span data-ttu-id="8aa00-151">[Köpa eller ta bort prenumerationslicenser](buy-licenses.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="8aa00-151">[Buy or remove subscription licenses](buy-licenses.md) (article)</span></span>
