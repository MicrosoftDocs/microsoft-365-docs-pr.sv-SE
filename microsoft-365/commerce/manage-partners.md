---
title: Hantera partner relationer
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Lär dig hur du arbetar med Microsoft-certifierade lösnings leverantörer (partners) för att köpa och hantera produkter och tjänster för din organisation eller skola.
ms.openlocfilehash: 6cce3640a321d1eab31d527369a303cfde646718
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430028"
---
# <a name="manage-partner-relationships"></a><span data-ttu-id="8c584-103">Hantera partner relationer</span><span class="sxs-lookup"><span data-stu-id="8c584-103">Manage partner relationships</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="8c584-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="8c584-104">The admin center is changing.</span></span> <span data-ttu-id="8c584-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="8c584-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="8c584-106">Du kan arbeta med Microsoft-certifierade lösnings leverantörer (partner) för att köpa och hantera produkter och tjänster för organisationen eller skolan.</span><span class="sxs-lookup"><span data-stu-id="8c584-106">You can work with Microsoft-certified solution providers (partners) to purchase and manage products and services for your organization or school.</span></span> <span data-ttu-id="8c584-107">Det finns några olika sätt att komma igång med saker.</span><span class="sxs-lookup"><span data-stu-id="8c584-107">There are a few steps involved in getting things set up.</span></span>

1. <span data-ttu-id="8c584-108">Administratörer hittar och kontaktar en partner med hjälp av formuläret på <a href="https://www.microsoft.com/solution-providers/home" target="_blank">https://www.microsoft.com/solution-providers/home</a> .</span><span class="sxs-lookup"><span data-stu-id="8c584-108">Admins find and contact a partner using the form at <a href="https://www.microsoft.com/solution-providers/home" target="_blank">https://www.microsoft.com/solution-providers/home</a>.</span></span>
2. <span data-ttu-id="8c584-109">Partner skickar en e-postbegäran till kunder för att etablera ett partner förhållande.</span><span class="sxs-lookup"><span data-stu-id="8c584-109">Partners send an email request to customers to establish a partner relationship.</span></span>
3. <span data-ttu-id="8c584-110">Kunderna accepterar inbjudan i Microsoft 365 Admin Center och börjar arbeta med partnern.</span><span class="sxs-lookup"><span data-stu-id="8c584-110">Customers accept the invitation in Microsoft 365 admin center and start working with the partner.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8c584-111">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="8c584-111">Before you begin</span></span>

<span data-ttu-id="8c584-112">Du måste antingen vara global eller fakturerings administratör för att kunna utföra de här stegen.</span><span class="sxs-lookup"><span data-stu-id="8c584-112">You must be either a Global or Billing admin to do these steps.</span></span> <span data-ttu-id="8c584-113">Mer information finns i [Om administratörsroller](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="8c584-113">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-can-a-partner-do-for-my-organization-or-school"></a><span data-ttu-id="8c584-114">Vad kan en partner göra för min organisation eller skola?</span><span class="sxs-lookup"><span data-stu-id="8c584-114">What can a partner do for my organization or school?</span></span>

<span data-ttu-id="8c584-115">Det finns flera sätt som en partner kan arbeta med dig på.</span><span class="sxs-lookup"><span data-stu-id="8c584-115">There are several ways that a partner can work with you.</span></span> <span data-ttu-id="8c584-116">Beroende på dina företags behov väljer du någon av dessa typer när de skickar sin begäran om att få arbeta med dig.</span><span class="sxs-lookup"><span data-stu-id="8c584-116">Based on your stated business needs, they choose one of these types when they send their request to work with you.</span></span>

| <span data-ttu-id="8c584-117">Partner typ</span><span class="sxs-lookup"><span data-stu-id="8c584-117">Partner type</span></span> | <span data-ttu-id="8c584-118">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8c584-118">Description</span></span> |
| ------ | ------------------- |
| <span data-ttu-id="8c584-119">Åter försäljaren</span><span class="sxs-lookup"><span data-stu-id="8c584-119">Reseller</span></span> | <span data-ttu-id="8c584-120">Partner som säljer Microsoft-produkter till din organisation eller skola.</span><span class="sxs-lookup"><span data-stu-id="8c584-120">Partners that sell Microsoft products to your organization or school.</span></span> |
| <span data-ttu-id="8c584-121">Delegerad administratör</span><span class="sxs-lookup"><span data-stu-id="8c584-121">Delegated administrator</span></span> | <span data-ttu-id="8c584-122">Partner som hanterar produkter och tjänster för din organisation eller skola.</span><span class="sxs-lookup"><span data-stu-id="8c584-122">Partners that manage products and services for your organization or school.</span></span> <span data-ttu-id="8c584-123">I Azure Active Directory (AD) är partnern en global administratör för din klient organisation.</span><span class="sxs-lookup"><span data-stu-id="8c584-123">In Azure Active Directory (AD), the partner is a Global Administrator for your tenant.</span></span> <span data-ttu-id="8c584-124">Med den här rollen kan de hantera tjänster som att skapa användar konton, tilldela och hantera licenser samt återställa lösen ord.</span><span class="sxs-lookup"><span data-stu-id="8c584-124">This role lets them manage services like creating user accounts, assigning and managing licenses, and password resets.</span></span> |
| <span data-ttu-id="8c584-125">Åter försäljaren & delegerad administratör</span><span class="sxs-lookup"><span data-stu-id="8c584-125">Reseller & delegated administrator</span></span> | <span data-ttu-id="8c584-126">Partner som säljer och hanterar Microsofts produkter och tjänster till din organisation eller skola.</span><span class="sxs-lookup"><span data-stu-id="8c584-126">Partners that sell and manage Microsoft products and services to your organization or school.</span></span> |
| <span data-ttu-id="8c584-127">Partner</span><span class="sxs-lookup"><span data-stu-id="8c584-127">Partner</span></span> | <span data-ttu-id="8c584-128">Du ger din partner ett användar konto i din klient organisation och de samarbetar med andra Microsoft-tjänster åt dig.</span><span class="sxs-lookup"><span data-stu-id="8c584-128">You give your partner a user account in your tenant, and they work with other Microsoft services on your behalf.</span></span> |
| <span data-ttu-id="8c584-129">Rådgivare</span><span class="sxs-lookup"><span data-stu-id="8c584-129">Advisor</span></span> | <span data-ttu-id="8c584-130">Partners kan återställa lösen ord och hantera support händelser åt dig.</span><span class="sxs-lookup"><span data-stu-id="8c584-130">Partners can reset passwords and handle support incidents for you.</span></span> |
| <span data-ttu-id="8c584-131">Microsoft Products & Services Agreement (MPSA)-partner</span><span class="sxs-lookup"><span data-stu-id="8c584-131">Microsoft Products & Services Agreement (MPSA) partner</span></span> | <span data-ttu-id="8c584-132">Om du har arbetat med flera partners via MPSA program kan du låta dem se inköp som görs av varandra.</span><span class="sxs-lookup"><span data-stu-id="8c584-132">If you've worked with multiple partners through the MPSA program, you can allow them to see purchases made by each other.</span></span> |
| <span data-ttu-id="8c584-133">Partner för företags verksamhet (LOB)</span><span class="sxs-lookup"><span data-stu-id="8c584-133">Line-of-business (LOB) partner</span></span> | <span data-ttu-id="8c584-134">Partners kan utveckla, skicka och hantera LOB-program som är specifika för din organisation eller skola.</span><span class="sxs-lookup"><span data-stu-id="8c584-134">Partners can develop, submit, and manage LOB apps specific for your organization or school.</span></span> |

## <a name="find-a-partner"></a><span data-ttu-id="8c584-135">Hitta en partner</span><span class="sxs-lookup"><span data-stu-id="8c584-135">Find a partner</span></span>

1. <span data-ttu-id="8c584-136">Gå till <a href="https://www.microsoft.com/en-us/solution-providers/home" target="_blank">https://www.microsoft.com/en-us/solution-providers/home</a>.</span><span class="sxs-lookup"><span data-stu-id="8c584-136">Go to <a href="https://www.microsoft.com/en-us/solution-providers/home" target="_blank">https://www.microsoft.com/en-us/solution-providers/home</a>.</span></span>
2. <span data-ttu-id="8c584-137">Ange din plats, Välj organisationens storlek, Lägg till nyckelord för den typ av tjänster du behöver och välj sedan **gå**.</span><span class="sxs-lookup"><span data-stu-id="8c584-137">Enter your location, choose your organization size, add keywords for the type of services you need, then select **Go**.</span></span>
3. <span data-ttu-id="8c584-138">Välj en eller flera partners och välj sedan **Kontakta valda leverantörer**.</span><span class="sxs-lookup"><span data-stu-id="8c584-138">Choose one or more partners, then select **Contact selected providers**.</span></span>
4. <span data-ttu-id="8c584-139">Fyll i formuläret och Beskriv dina affärs behov och välj sedan **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="8c584-139">Complete the form to describe your business needs, then select **Send**.</span></span>

<span data-ttu-id="8c584-140">Partnern kontaktar dig och ger dig en chans att få reda på mer om dem.</span><span class="sxs-lookup"><span data-stu-id="8c584-140">The partner contacts you and gives you a chance to learn more about them.</span></span> <span data-ttu-id="8c584-141">Om du bestämmer dig för att arbeta med dem kan de skicka en inbjudan via e-post för att etablera ett partner förhållande.</span><span class="sxs-lookup"><span data-stu-id="8c584-141">If you decide to work with them, they send you an email invitation to establish a partner relationship.</span></span>

## <a name="review-and-accept-a-partner-relationship-and-microsoft-customer-agreement"></a><span data-ttu-id="8c584-142">Granska och acceptera ett partner-och Microsoft-kundavtal</span><span class="sxs-lookup"><span data-stu-id="8c584-142">Review and accept a partner relationship and Microsoft Customer Agreement</span></span>

<span data-ttu-id="8c584-143">När du har hittat en partner och bestämmer dig för att arbeta med dem, skickar de en e-postinbjudan.</span><span class="sxs-lookup"><span data-stu-id="8c584-143">After you find a partner and decide to work with them, they send you an email invitation.</span></span>

1. <span data-ttu-id="8c584-144">I e-postmeddelandet väljer du länken för att gå till administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8c584-144">In the email, select the link to go to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="8c584-145">På sidan **Godkänn avtal & Godkänn partner** väljer du länken för **Microsofts kund avtal**och läser dokumentet.</span><span class="sxs-lookup"><span data-stu-id="8c584-145">On the **Accept agreement & authorize partner** page, select the link for the **Microsoft Customer Agreement**, and read the document.</span></span>
3. <span data-ttu-id="8c584-146">Markera rutan för att bekräfta att du läser avtalet.</span><span class="sxs-lookup"><span data-stu-id="8c584-146">Check the box to acknowledge that you read the agreement.</span></span>
4. <span data-ttu-id="8c584-147">Välj **acceptera & verifiera**.</span><span class="sxs-lookup"><span data-stu-id="8c584-147">Select **Accept & Authorize**.</span></span>
5. <span data-ttu-id="8c584-148">Listan över partners som du arbetar med visas.</span><span class="sxs-lookup"><span data-stu-id="8c584-148">The list of partners that you’re working with is displayed.</span></span> <span data-ttu-id="8c584-149">Välj en partner för att visa detaljer.</span><span class="sxs-lookup"><span data-stu-id="8c584-149">Select any partner to see details.</span></span>

## <a name="review-and-accept-a-microsoft-customer-agreement"></a><span data-ttu-id="8c584-150">Granska och acceptera ett Microsoft-kundavtal</span><span class="sxs-lookup"><span data-stu-id="8c584-150">Review and accept a Microsoft Customer Agreement</span></span>

<span data-ttu-id="8c584-151">Om du redan har en partner men ännu inte har undertecknat ett Microsoft-avtal måste du godkänna avtalet innan de kan göra inköp eller hantera dina abonnemang åt dig.</span><span class="sxs-lookup"><span data-stu-id="8c584-151">If you already have a partner but haven’t yet signed a Microsoft Customer Agreement, you must accept the agreement before they can make purchases or manage your subscriptions on your behalf.</span></span>

1. <span data-ttu-id="8c584-152">Om du får ett e-postmeddelande från din partner väljer du länken för att gå till administrations centret för Microsoft 365 eller gå till sidan <a href="https://go.microsoft.com/fwlink/?linkid=2116573" target="_blank">Godkänn avtal</a> .</span><span class="sxs-lookup"><span data-stu-id="8c584-152">If you receive an email from your partner, select the link to go to the Microsoft 365 admin center, or go to the <a href="https://go.microsoft.com/fwlink/?linkid=2116573" target="_blank">Accept agreement</a> page.</span></span>
2. <span data-ttu-id="8c584-153">Välj länken för **Microsofts kund avtal** och Läs dokumentet.</span><span class="sxs-lookup"><span data-stu-id="8c584-153">Select the link for the **Microsoft Customer Agreement** and read the document.</span></span>
3. <span data-ttu-id="8c584-154">Markera rutan för att bekräfta att du läser avtalet.</span><span class="sxs-lookup"><span data-stu-id="8c584-154">Check the box to acknowledge that you read the agreement.</span></span>
4. <span data-ttu-id="8c584-155">Välj **acceptera**.</span><span class="sxs-lookup"><span data-stu-id="8c584-155">Select **Accept**.</span></span>
5. <span data-ttu-id="8c584-156">Listan över partners som du arbetar med visas.</span><span class="sxs-lookup"><span data-stu-id="8c584-156">The list of partners that you’re working with is displayed.</span></span> <span data-ttu-id="8c584-157">Välj en partner för att visa detaljer.</span><span class="sxs-lookup"><span data-stu-id="8c584-157">Select any partner to see details.</span></span>

## <a name="remove-partner-admin-roles"></a><span data-ttu-id="8c584-158">Ta bort roller för partner administratörer</span><span class="sxs-lookup"><span data-stu-id="8c584-158">Remove partner admin roles</span></span>

<span data-ttu-id="8c584-159">Beroende på vilken begäran som utfärdas av partnern godkänner du att ge dem globala roller för administratörer och supportavdelning.</span><span class="sxs-lookup"><span data-stu-id="8c584-159">Depending on the request made by the partner, when you accept the invitation, you agree to give them Global and Helpdesk admin roles.</span></span> <span data-ttu-id="8c584-160">När du ger dessa administratörs roller till en partner ger du automatiskt delegerade administratörs behörigheter i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8c584-160">When you give these admin roles to a partner, you automatically grant them delegated admin privileges in Azure AD.</span></span> <span data-ttu-id="8c584-161">Mer information finns i [delegerade administratörs behörigheter i Azure AD](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#delegated-admin-privileges-in-azure-ad).</span><span class="sxs-lookup"><span data-stu-id="8c584-161">To learn more, see [Delegated admin privileges in Azure AD](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#delegated-admin-privileges-in-azure-ad).</span></span>

<span data-ttu-id="8c584-162">Om du inte vill ge administratörs rollerna till partnern kan du avbryta inbjudan i stället för att acceptera den.</span><span class="sxs-lookup"><span data-stu-id="8c584-162">If you don't want to give the admin roles to the partner, cancel the invitation instead of accepting it.</span></span>

<span data-ttu-id="8c584-163">Du kan när som helst ta bort administratörs roller från en partner.</span><span class="sxs-lookup"><span data-stu-id="8c584-163">You can remove admin roles from a partner at any time.</span></span> <span data-ttu-id="8c584-164">Om du tar bort administratörs rollerna tas inte partner relationen bort.</span><span class="sxs-lookup"><span data-stu-id="8c584-164">Removing the admin roles doesn’t remove the partner relationship.</span></span> <span data-ttu-id="8c584-165">De kan fortfarande arbeta med dig i en annan kapacitet, till exempel åter försäljare.</span><span class="sxs-lookup"><span data-stu-id="8c584-165">They can still work with you in a different capacity, such as a Reseller.</span></span> <span data-ttu-id="8c584-166">Om du bestämmer dig för att du inte vill arbeta med en partner längre kontaktar du din partner för att avsluta relationen.</span><span class="sxs-lookup"><span data-stu-id="8c584-166">If you decide that you don’t want to work with a partner anymore, contact your partner to end the relationship.</span></span>

1. <span data-ttu-id="8c584-167">Gå till sidan för **fakturerings**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">partner relationer</a> i administrations centret.</span><span class="sxs-lookup"><span data-stu-id="8c584-167">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">Partner relationships</a> page.</span></span>
2. <span data-ttu-id="8c584-168">På sidan **partner relationer** markerar du den rad som innehåller namnet på den partner du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="8c584-168">On the **Partner relationships** page, select the row that contains the name of the partner that you want to remove.</span></span>
3. <span data-ttu-id="8c584-169">Markera raden som innehåller namnet på partnern.</span><span class="sxs-lookup"><span data-stu-id="8c584-169">Select the row that contains the name of the partner.</span></span>
4. <span data-ttu-id="8c584-170">På sidan partner väljer du **ta bort roller**.</span><span class="sxs-lookup"><span data-stu-id="8c584-170">On the partner page, select **Remove roles**.</span></span>
5. <span data-ttu-id="8c584-171">I dialog rutan **ta bort roller?** väljer du **Ja**.</span><span class="sxs-lookup"><span data-stu-id="8c584-171">In the **Remove roles?** dialog box, select **Yes**.</span></span>
