---
title: Hantera faktureringsaviseringar och fakturabilagor
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: prkalid, guyb
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- okr_SMB
- AdminSurgePortfolio
- commerce_billing
search.appverid:
- MET150
description: Lär dig hur du hanterar vilka som får e-postmeddelanden om faktureringsaviseringar och fakturabilagor.
ms.date: 03/17/2021
ms.openlocfilehash: 75c75175930434619a01886b1096757bf04111c5
ms.sourcegitcommit: 03aa8ed22d9ef685a851e28c7d0cfb725732fe4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52888367"
---
# <a name="manage-billing-notifications-and-invoice-attachments"></a><span data-ttu-id="5e76d-103">Hantera faktureringsaviseringar och fakturabilagor</span><span class="sxs-lookup"><span data-stu-id="5e76d-103">Manage billing notifications and invoice attachments</span></span>

<span data-ttu-id="5e76d-104">På **sidan Faktureringsaviseringar** kan du hantera vilka som får e-postmeddelanden om faktureringsaviseringar för din organisation.</span><span class="sxs-lookup"><span data-stu-id="5e76d-104">The **Billing notifications** page lets you manage who receives billing notification emails for your organization.</span></span> <span data-ttu-id="5e76d-105">På sidan finns också alternativet för att få [din organisations fakturor som e-postbilagor.](#receive-your-organizations-invoices-as-email-attachments)</span><span class="sxs-lookup"><span data-stu-id="5e76d-105">The page also provides the option to [receive your organization's invoices as email attachments](#receive-your-organizations-invoices-as-email-attachments).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5e76d-106">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="5e76d-106">Before you begin</span></span>

<span data-ttu-id="5e76d-107">Du måste vara global administratör för att kunna göra det som beskrivs i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="5e76d-107">You must be a Global admin to do the steps described in this article.</span></span> <span data-ttu-id="5e76d-108">Faktureringsadministratörer kan göra en del av dessa ändringar, som nämnts i avsnitten nedan.</span><span class="sxs-lookup"><span data-stu-id="5e76d-108">Billing admins can make some of these changes, as noted in the sections below.</span></span> <span data-ttu-id="5e76d-109">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="5e76d-109">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="change-the-language-you-receive-email-in"></a><span data-ttu-id="5e76d-110">Ändra det språk som du får e-post på</span><span class="sxs-lookup"><span data-stu-id="5e76d-110">Change the language you receive email in</span></span>

> [!NOTE]
> <span data-ttu-id="5e76d-111">Faktureringsadministratörer kan också följa anvisningarna i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="5e76d-111">Billing admins can also do the steps in this section.</span></span>

<span data-ttu-id="5e76d-112">E-postmeddelanden om faktureringsaviseringar skickas på organisationens föredragna språk.</span><span class="sxs-lookup"><span data-stu-id="5e76d-112">Billing notification emails are sent in your organization’s preferred language.</span></span> <span data-ttu-id="5e76d-113">Använd följande steg om du vill ändra önskat språk.</span><span class="sxs-lookup"><span data-stu-id="5e76d-113">To change the preferred language, use the following steps.</span></span>

1. <span data-ttu-id="5e76d-114">I Microsoft 365 administrationscenter går du till sidan   >  <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Faktureringsfaktureringsaviseringar.</a></span><span class="sxs-lookup"><span data-stu-id="5e76d-114">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="5e76d-115">Välj Redigera **aviseringsinställningar** i **avsnittet Inställningar för faktureringsaviseringar.**</span><span class="sxs-lookup"><span data-stu-id="5e76d-115">In the **Billing notification settings** section, select **Edit notification settings**.</span></span>
3. <span data-ttu-id="5e76d-116">I fönstret Inställningar för faktureringsaviseringar under **Önskat** språk väljer du det språk du vill använda och väljer sedan **Spara**. </span><span class="sxs-lookup"><span data-stu-id="5e76d-116">In the **Billing notification settings** pane, under **Preferred language** select the language you want to use, then select **Save**.</span></span>

## <a name="change-who-receives-billing-notifications"></a><span data-ttu-id="5e76d-117">Ändra vem som får faktureringsaviseringar</span><span class="sxs-lookup"><span data-stu-id="5e76d-117">Change who receives billing notifications</span></span>

<span data-ttu-id="5e76d-118">Din organisations faktureringsaviseringar skickas till den primära och alternativa e-postadressen för varje global administratör och faktureringsadministratör. Gör så här om du vill ändra vilka användare som har rollen Global administratör eller Faktureringsadministratör.</span><span class="sxs-lookup"><span data-stu-id="5e76d-118">Your organization's billing notifications are sent to the primary and alternate email address of every Global and Billing admin. To change which users have the Global or Billing admin role, use the following steps.</span></span>

### <a name="assign-admin-roles-by-using-the-billing-notifications-page"></a><span data-ttu-id="5e76d-119">Tilldela administratörsroller med hjälp av sidan Faktureringsaviseringar</span><span class="sxs-lookup"><span data-stu-id="5e76d-119">Assign admin roles by using the Billing notifications page</span></span>

1. <span data-ttu-id="5e76d-120">Gå till sidan **Fakturering**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Faktureringsmeddelanden</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="5e76d-120">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="5e76d-121">I avsnittet Administratörer som tar emot faktureringsaviseringar väljer du **länken** **Faktureringsadministratör** eller **Global** administratör i beskrivningstexten.</span><span class="sxs-lookup"><span data-stu-id="5e76d-121">In the **Admins receiving billing notifications** section, select the **Billing administrator** or **Global administrator** link in the description text.</span></span>
3. <span data-ttu-id="5e76d-122">På fliken Tilldelade administratörer i den **högra rutan väljer** du Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="5e76d-122">In the right pane, on the **Assigned admins** tab, select **Add**.</span></span>
4. <span data-ttu-id="5e76d-123">I fönstret **Lägg till** administratörer skriver du in användarens visningsnamn eller användarnamn och väljer användaren i listan med förslag.</span><span class="sxs-lookup"><span data-stu-id="5e76d-123">In the **Add admins** pane, type the user’s display name or username, and then select the user from the list of suggestions.</span></span>
5. <span data-ttu-id="5e76d-124">Lägg till flera användare tills du är klar.</span><span class="sxs-lookup"><span data-stu-id="5e76d-124">Add multiple users until you’re done.</span></span>
6. <span data-ttu-id="5e76d-125">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="5e76d-125">Select **Save**.</span></span> <span data-ttu-id="5e76d-126">Användaren läggs till i listan över tilldelade administratörer.</span><span class="sxs-lookup"><span data-stu-id="5e76d-126">The user is added to the list of assigned admins.</span></span>

### <a name="remove-admin-roles-by-using-the-billing-notifications-page"></a><span data-ttu-id="5e76d-127">Ta bort administratörsroller med hjälp av sidan Faktureringsaviseringar</span><span class="sxs-lookup"><span data-stu-id="5e76d-127">Remove admin roles by using the Billing notifications page</span></span>

1. <span data-ttu-id="5e76d-128">Gå till sidan **Fakturering**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Faktureringsmeddelanden</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="5e76d-128">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="5e76d-129">I avsnittet Administratörer som tar emot faktureringsaviseringar väljer du **länken** **Faktureringsadministratör** eller **Global** administratör i beskrivningstexten.</span><span class="sxs-lookup"><span data-stu-id="5e76d-129">In the **Admins receiving billing notifications** section, select the **Billing administrator** or **Global administrator** link in the description text.</span></span>
3. <span data-ttu-id="5e76d-130">I den högra rutan, på **fliken Tilldelade administratörer, väljer** du de användare du vill ta bort från rollen och väljer sedan Ta **bort.**</span><span class="sxs-lookup"><span data-stu-id="5e76d-130">In the right pane, on the **Assigned admins** tab, select the users to remove from the role, and then select **Remove**.</span></span>
4. <span data-ttu-id="5e76d-131">Välj Ta bort i **bekräftelserutan.**</span><span class="sxs-lookup"><span data-stu-id="5e76d-131">In the confirmation box, select **Remove**.</span></span> <span data-ttu-id="5e76d-132">Användaren tas bort från listan med tilldelade administratörer.</span><span class="sxs-lookup"><span data-stu-id="5e76d-132">The user is removed from the list of assigned admins.</span></span>

## <a name="change-the-email-addresses-for-admins"></a><span data-ttu-id="5e76d-133">Ändra administratörers e-postadresser</span><span class="sxs-lookup"><span data-stu-id="5e76d-133">Change the email addresses for admins</span></span>

<span data-ttu-id="5e76d-134">Gör så här om du vill ändra den primära och alternativa e-postadressen till andra administratörer i organisationen:</span><span class="sxs-lookup"><span data-stu-id="5e76d-134">To change the primary and alternate email address of other admins in your organization, use the following steps.</span></span>

> [!NOTE]
> <span data-ttu-id="5e76d-135">Faktureringsadministratörer kan ändra sina egna primära och alternativa e-postadresser, men inte för andra administratörer.</span><span class="sxs-lookup"><span data-stu-id="5e76d-135">Billing admins can change their own primary and alternate email addresses, but not for other admins.</span></span>

1. <span data-ttu-id="5e76d-136">Gå till sidan **Fakturering**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Faktureringsmeddelanden</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="5e76d-136">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="5e76d-137">Välj **ett namn i avsnittet Administratörer som** tar emot faktureringsaviseringar.</span><span class="sxs-lookup"><span data-stu-id="5e76d-137">In the **Admins receiving billing notifications** section, select a name.</span></span>
3. <span data-ttu-id="5e76d-138">I det högra fönstret lägger du till eller uppdaterar den primära och alternativa e-postadressen efter behov och väljer **sedan Spara**.</span><span class="sxs-lookup"><span data-stu-id="5e76d-138">In the right pane, add or update the primary and alternate email address as needed, then select **Save**.</span></span>

## <a name="change-your-organizations-contact-email"></a><span data-ttu-id="5e76d-139">Ändra organisationens kontakt-e-postadress</span><span class="sxs-lookup"><span data-stu-id="5e76d-139">Change your organization's contact email</span></span>

<span data-ttu-id="5e76d-140">Förutom dina globala administratörer och faktureringsadministratörer skickar vi faktureringsaviseringar till din organisations kontakt-e-postadress.</span><span class="sxs-lookup"><span data-stu-id="5e76d-140">In addition to your Global and Billing admins, we send billing notifications to your organization's contact email address.</span></span> <span data-ttu-id="5e76d-141">Använd följande steg om du vill ändra e-postadressen.</span><span class="sxs-lookup"><span data-stu-id="5e76d-141">To change the email address, use the following steps.</span></span>

1. <span data-ttu-id="5e76d-142">Gå till sidan **Fakturering**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Faktureringsmeddelanden</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="5e76d-142">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="5e76d-143">Under **Organisationskontakt som tar emot faktureringsaviseringar** väljer du organisationskontakten.</span><span class="sxs-lookup"><span data-stu-id="5e76d-143">Under **Organization contact receiving billing notifications**, select the organization contact.</span></span>
3. <span data-ttu-id="5e76d-144">I det högra fönstret skriver du den e-postadress som du vill använda och väljer sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="5e76d-144">In the right pane, type the email address that you want to use, then select **Save**.</span></span>

## <a name="receive-your-organizations-invoices-as-email-attachments"></a><span data-ttu-id="5e76d-145">Ta emot din organisations fakturor som e-postbilagor</span><span class="sxs-lookup"><span data-stu-id="5e76d-145">Receive your organization's invoices as email attachments</span></span>

> [!NOTE]
> <span data-ttu-id="5e76d-146">Faktureringsadministratörer kan också följa anvisningarna i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="5e76d-146">Billing admins can also do the steps in this section.</span></span>

<span data-ttu-id="5e76d-147">Du kan bifoga en kopia av organisationens faktura som en PDF-fil för att få fakturaaviseringar via e-post när en ny faktura är klar.</span><span class="sxs-lookup"><span data-stu-id="5e76d-147">You can have a copy of your organization's invoice attached as a PDF file to invoice notification emails when a new invoice is ready.</span></span> <span data-ttu-id="5e76d-148">Använd följande steg för att ta emot fakturor som bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="5e76d-148">Use the following steps to receive invoices as attachments.</span></span>

1. <span data-ttu-id="5e76d-149">Gå till sidan **Fakturering**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Faktureringsmeddelanden</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="5e76d-149">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="5e76d-150">Under **Inställningar för faktureringsavisering** väljer **du Redigera aviseringsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="5e76d-150">Under **Billing notification settings**, select **Edit notification settings**.</span></span>
3. <span data-ttu-id="5e76d-151">I fönstret **Inställningar för faktureringsaviseringar,** under Bifoga en **PDF-fil** till dina fakturameddelanden, markerar du kryssrutan och väljer sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="5e76d-151">In the **Billing notification settings** pane, under **Attach a PDF to your invoice emails**, check the checkbox, then select **Save**.</span></span>

<span data-ttu-id="5e76d-152">Om du inte vill ta emot fakturans bifogade fil när som helst följer du stegen ovan och avmarkerar kryssrutan Bifoga en **PDF-fil** till dina fakturameddelanden i steg 3.</span><span class="sxs-lookup"><span data-stu-id="5e76d-152">To stop receiving the invoice attachment at any time, follow the steps above and clear the **Attach a PDF to your invoice  emails** checkbox in step 3.</span></span>

## <a name="what-if-i-have-a-billing-profile"></a><span data-ttu-id="5e76d-153">Vad händer om jag har en faktureringsprofil?</span><span class="sxs-lookup"><span data-stu-id="5e76d-153">What if I have a billing profile?</span></span>

<span data-ttu-id="5e76d-154">Om du har en faktureringsprofil kan vissa av stegen som beskrivs i den här artikeln vara lite annorlunda för vissa av dina prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="5e76d-154">If you have a billing profile, some of the steps described in this article might be slightly different for some of your subscriptions.</span></span> <span data-ttu-id="5e76d-155">I det här avsnittet beskrivs skillnaderna.</span><span class="sxs-lookup"><span data-stu-id="5e76d-155">This section describes those differences.</span></span> [<span data-ttu-id="5e76d-156">Hur vet jag om jag har en faktureringsprofil?</span><span class="sxs-lookup"><span data-stu-id="5e76d-156">How do I know if I have a billing profile?</span></span>](manage-billing-profiles.md)

### <a name="who-receives-billing-notifications"></a><span data-ttu-id="5e76d-157">Vem faktureringsaviseringar?</span><span class="sxs-lookup"><span data-stu-id="5e76d-157">Who receives Billing notifications?</span></span>

<span data-ttu-id="5e76d-158">E-postmeddelanden om faktureringsaviseringar skickas till de primära och alternativa e-postadresserna för användare som har tilldelats någon av följande roller:</span><span class="sxs-lookup"><span data-stu-id="5e76d-158">Billing notification emails are sent to the primary and alternate email addresses for users who are assigned one of the following roles:</span></span>

- <span data-ttu-id="5e76d-159">Faktureringsprofilägare</span><span class="sxs-lookup"><span data-stu-id="5e76d-159">Billing profile owner</span></span>
- <span data-ttu-id="5e76d-160">Deltagare i faktureringsprofil</span><span class="sxs-lookup"><span data-stu-id="5e76d-160">Billing profile contributor</span></span>
- <span data-ttu-id="5e76d-161">Fakturaansvarig</span><span class="sxs-lookup"><span data-stu-id="5e76d-161">Invoice manager</span></span>

<span data-ttu-id="5e76d-162">Mer information om faktureringsprofilroller och hur du hanterar dem finns i Förstå [administrativa roller i Microsoft Customer Agreement i Azure.](/azure/cost-management-billing/manage/understand-mca-roles)</span><span class="sxs-lookup"><span data-stu-id="5e76d-162">To learn more about billing profile roles and how to manage them, see [Understand Microsoft Customer Agreement administrative roles in Azure](/azure/cost-management-billing/manage/understand-mca-roles).</span></span>

<span data-ttu-id="5e76d-163">Om du vill ändra vem som får organisationens faktureringsaviseringar använder du följande steg för att ändra de roller som användare tilldelats.</span><span class="sxs-lookup"><span data-stu-id="5e76d-163">To change who receives your organization’s billing notifications, use the following steps to change the roles assigned to users.</span></span>

1. <span data-ttu-id="5e76d-164">I administrationscentret går du till sidan  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Faktureringsfakturor & betalningar.</a></span><span class="sxs-lookup"><span data-stu-id="5e76d-164">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="5e76d-165">Välj **en faktureringsprofil** på fliken Faktureringsprofil.</span><span class="sxs-lookup"><span data-stu-id="5e76d-165">On the **Billing profile** tab, select a billing profile.</span></span>
3. <span data-ttu-id="5e76d-166">I avsnittet **Faktureringsprofilroller** tilldelar eller tar du bort roller för **faktureringsprofilägare,** **faktureringsprofilsdeltagare** eller **fakturahanterare.**</span><span class="sxs-lookup"><span data-stu-id="5e76d-166">In the **Billing profile roles** section, assign or remove roles for **Billing profile owner**, **Billing profile contributor**, or **Invoice manager**.</span></span>

### <a name="receive-invoices-as-email-attachments"></a><span data-ttu-id="5e76d-167">Ta emot fakturor som e-postbilagor</span><span class="sxs-lookup"><span data-stu-id="5e76d-167">Receive invoices as email attachments</span></span>

<span data-ttu-id="5e76d-168">Om du vill få dina fakturor som bifogade filer i dina fakturaaviseringar använder du följande steg för att aktivera den här inställningen för en viss faktureringsprofil.</span><span class="sxs-lookup"><span data-stu-id="5e76d-168">To receive your invoices as attachments to your invoice notifications, use the following steps to turn on this setting for a specific billing profile.</span></span>

1. <span data-ttu-id="5e76d-169">I administrationscentret går du till sidan  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Faktureringsfakturor & betalningar.</a></span><span class="sxs-lookup"><span data-stu-id="5e76d-169">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="5e76d-170">Välj fliken **Faktureringsprofiler** och välj sedan en faktureringsprofil i listan.</span><span class="sxs-lookup"><span data-stu-id="5e76d-170">Select the **Billing profiles** tab, then select a billing profile from the list.</span></span>
3. <span data-ttu-id="5e76d-171">På sidan med faktureringsprofilinformation under **Hämta fakturor i e-postbilagor** ändrar du växlingsknappen till **På**.</span><span class="sxs-lookup"><span data-stu-id="5e76d-171">On the billing profile details page, under **Get invoices in email attachments**, switch the toggle to **On**.</span></span>

## <a name="related-content"></a><span data-ttu-id="5e76d-172">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="5e76d-172">Related content</span></span>

<span data-ttu-id="5e76d-173">[Visa din räkning eller faktura](view-your-bill-or-invoice.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="5e76d-173">[View your bill or invoice](view-your-bill-or-invoice.md) (article)</span></span>\
<span data-ttu-id="5e76d-174">[Faktureringsinformation för Microsoft 365 för företag i Mexiko](/microsoft-365/commerce/billing-and-payments/mexico-billing-info) (artikel) </span><span class="sxs-lookup"><span data-stu-id="5e76d-174">[Billing information for Microsoft 365 for business in Mexico](/microsoft-365/commerce/billing-and-payments/mexico-billing-info) (article) </span></span>\
<span data-ttu-id="5e76d-175">[Förstå din faktura för Microsoft 365 för företag](understand-your-invoice2.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="5e76d-175">[Understand your bill or invoice for Microsoft 365 for business](understand-your-invoice2.md) (article)</span></span>\
<span data-ttu-id="5e76d-176">[Lägga till användare och tilldela licenser samtidigt](../../admin/add-users/add-users.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="5e76d-176">[Add users and assign licenses at the same time](../../admin/add-users/add-users.md) (article)</span></span>
