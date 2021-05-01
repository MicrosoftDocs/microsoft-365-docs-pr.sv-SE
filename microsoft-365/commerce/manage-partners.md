---
title: Hantera partnerrelationer
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
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
- PPM_jmueller
ms.reviewer: tugu
search.appverid:
- MET150
description: Lär dig hur du arbetar med Microsoft-certifierade lösningsleverantörer (partners) för att köpa och hantera produkter och tjänster för din organisation eller skola.
ms.date: 04/13/2021
ms.openlocfilehash: e225fa0c525d484e8c5a3887b82277a1da5861b0
ms.sourcegitcommit: 794f9767aaebe13ab1aead830b214ea674289d19
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52107574"
---
# <a name="manage-partner-relationships"></a><span data-ttu-id="2600b-103">Hantera partnerrelationer</span><span class="sxs-lookup"><span data-stu-id="2600b-103">Manage partner relationships</span></span>

<span data-ttu-id="2600b-104">Du kan samarbeta med Microsoft-certifierade lösningsleverantörer (partners) för att köpa och hantera produkter och tjänster för din organisation eller skola.</span><span class="sxs-lookup"><span data-stu-id="2600b-104">You can work with Microsoft-certified solution providers (partners) to purchase and manage products and services for your organization or school.</span></span> <span data-ttu-id="2600b-105">Det ingår några steg i att konfigurera saker.</span><span class="sxs-lookup"><span data-stu-id="2600b-105">There are a few steps involved in getting things set up.</span></span>

1. <span data-ttu-id="2600b-106">Administratörer hittar och kontaktar en partner med hjälp av formuläret på <a href="https://www.microsoft.com/solution-providers/home" target="_blank">https://www.microsoft.com/solution-providers/home</a> .</span><span class="sxs-lookup"><span data-stu-id="2600b-106">Admins find and contact a partner using the form at <a href="https://www.microsoft.com/solution-providers/home" target="_blank">https://www.microsoft.com/solution-providers/home</a>.</span></span>
2. <span data-ttu-id="2600b-107">Partner skickar en e-postförfrågan till kunder för att upprätta en partnerrelation.</span><span class="sxs-lookup"><span data-stu-id="2600b-107">Partners send an email request to customers to establish a partner relationship.</span></span>
3. <span data-ttu-id="2600b-108">Kunderna accepterar inbjudan i Microsoft 365 administrationscenter och börjar arbeta med partnern.</span><span class="sxs-lookup"><span data-stu-id="2600b-108">Customers accept the invitation in Microsoft 365 admin center and start working with the partner.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="2600b-109">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="2600b-109">Before you begin</span></span>

<span data-ttu-id="2600b-110">Du måste vara antingen global administratör eller faktureringsadministratör för att kunna göra följande.</span><span class="sxs-lookup"><span data-stu-id="2600b-110">You must be either a Global or Billing admin to do these steps.</span></span> <span data-ttu-id="2600b-111">Mer information finns i [Om administratörsroller](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="2600b-111">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-can-a-partner-do-for-my-organization-or-school"></a><span data-ttu-id="2600b-112">Vad kan en partner göra för min organisation eller skola?</span><span class="sxs-lookup"><span data-stu-id="2600b-112">What can a partner do for my organization or school?</span></span>

<span data-ttu-id="2600b-113">En partner kan arbeta med dig på flera olika sätt.</span><span class="sxs-lookup"><span data-stu-id="2600b-113">There are several ways that a partner can work with you.</span></span> <span data-ttu-id="2600b-114">Beroende på dina specifika affärsbehov väljer de någon av dessa typer när de skickar sin begäran att arbeta med dig.</span><span class="sxs-lookup"><span data-stu-id="2600b-114">Based on your stated business needs, they choose one of these types when they send their request to work with you.</span></span>

| <span data-ttu-id="2600b-115">Partnertyp</span><span class="sxs-lookup"><span data-stu-id="2600b-115">Partner type</span></span> | <span data-ttu-id="2600b-116">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="2600b-116">Description</span></span> |
| ------ | ------------------- |
| <span data-ttu-id="2600b-117">Återförsäljare</span><span class="sxs-lookup"><span data-stu-id="2600b-117">Reseller</span></span> | <span data-ttu-id="2600b-118">Partners som säljer Microsoft-produkter till din organisation eller skola.</span><span class="sxs-lookup"><span data-stu-id="2600b-118">Partners that sell Microsoft products to your organization or school.</span></span> |
| <span data-ttu-id="2600b-119">Delegerad administratör</span><span class="sxs-lookup"><span data-stu-id="2600b-119">Delegated administrator</span></span> | <span data-ttu-id="2600b-120">Partner som hanterar produkter och tjänster för din organisation eller skola.</span><span class="sxs-lookup"><span data-stu-id="2600b-120">Partners that manage products and services for your organization or school.</span></span> <span data-ttu-id="2600b-121">I Azure Active Directory (AD) är partnern global administratör för klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="2600b-121">In Azure Active Directory (AD), the partner is a Global Administrator for your tenant.</span></span> <span data-ttu-id="2600b-122">Med den här rollen kan de hantera tjänster som att skapa användarkonton, tilldela och hantera licenser och lösenordsåterställningar.</span><span class="sxs-lookup"><span data-stu-id="2600b-122">This role lets them manage services like creating user accounts, assigning and managing licenses, and password resets.</span></span> |
| <span data-ttu-id="2600b-123">Återförsäljare & delegerad administratör</span><span class="sxs-lookup"><span data-stu-id="2600b-123">Reseller & delegated administrator</span></span> | <span data-ttu-id="2600b-124">Partners som säljer och hanterar Microsofts produkter och tjänster till din organisation eller skola.</span><span class="sxs-lookup"><span data-stu-id="2600b-124">Partners that sell and manage Microsoft products and services to your organization or school.</span></span> |
| <span data-ttu-id="2600b-125">Partner</span><span class="sxs-lookup"><span data-stu-id="2600b-125">Partner</span></span> | <span data-ttu-id="2600b-126">Du ger din partner ett användarkonto i klientorganisationen och de arbetar med andra Microsoft-tjänster åt dig.</span><span class="sxs-lookup"><span data-stu-id="2600b-126">You give your partner a user account in your tenant, and they work with other Microsoft services on your behalf.</span></span> |
| <span data-ttu-id="2600b-127">Rådgivare</span><span class="sxs-lookup"><span data-stu-id="2600b-127">Advisor</span></span> | <span data-ttu-id="2600b-128">Partner kan återställa lösenord och hantera supportärenden för dig.</span><span class="sxs-lookup"><span data-stu-id="2600b-128">Partners can reset passwords and handle support incidents for you.</span></span> |
| <span data-ttu-id="2600b-129">MPSA-& Products & Services Agreement (MPSA)</span><span class="sxs-lookup"><span data-stu-id="2600b-129">Microsoft Products & Services Agreement (MPSA) partner</span></span> | <span data-ttu-id="2600b-130">Om du har arbetat med flera partner via MPSA-programmet kan du låta dem se köp som gjorts av varandra.</span><span class="sxs-lookup"><span data-stu-id="2600b-130">If you've worked with multiple partners through the MPSA program, you can allow them to see purchases made by each other.</span></span> |
| <span data-ttu-id="2600b-131">LOB-partner</span><span class="sxs-lookup"><span data-stu-id="2600b-131">Line-of-business (LOB) partner</span></span> | <span data-ttu-id="2600b-132">Partners kan utveckla, skicka in och hantera verksamhetsspecifika appar för din organisation eller skola.</span><span class="sxs-lookup"><span data-stu-id="2600b-132">Partners can develop, submit, and manage LOB apps specific for your organization or school.</span></span> |

## <a name="find-a-partner"></a><span data-ttu-id="2600b-133">Hitta en partner</span><span class="sxs-lookup"><span data-stu-id="2600b-133">Find a partner</span></span>

1. <span data-ttu-id="2600b-134">Gå till <a href="https://www.microsoft.com/en-us/solution-providers/home" target="_blank">https://www.microsoft.com/en-us/solution-providers/home</a>.</span><span class="sxs-lookup"><span data-stu-id="2600b-134">Go to <a href="https://www.microsoft.com/en-us/solution-providers/home" target="_blank">https://www.microsoft.com/en-us/solution-providers/home</a>.</span></span>
2. <span data-ttu-id="2600b-135">Ange din plats, välj organisationens storlek, lägg till nyckelord för typen av tjänster du behöver och välj sedan **Gå**.</span><span class="sxs-lookup"><span data-stu-id="2600b-135">Enter your location, choose your organization size, add keywords for the type of services you need, then select **Go**.</span></span>
3. <span data-ttu-id="2600b-136">Välj en eller flera partner och välj sedan **Kontakta valda leverantörer.**</span><span class="sxs-lookup"><span data-stu-id="2600b-136">Choose one or more partners, then select **Contact selected providers**.</span></span>
4. <span data-ttu-id="2600b-137">Fyll i formuläret för att beskriva dina affärsbehov och välj sedan **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="2600b-137">Complete the form to describe your business needs, then select **Send**.</span></span>

<span data-ttu-id="2600b-138">Partnerkontakterna du och ger dig möjlighet att få mer information om dem.</span><span class="sxs-lookup"><span data-stu-id="2600b-138">The partner contacts you and gives you a chance to learn more about them.</span></span> <span data-ttu-id="2600b-139">Om du bestämmer dig för att arbeta med dem skickar de en inbjudan via e-post för att upprätta en partnerrelation.</span><span class="sxs-lookup"><span data-stu-id="2600b-139">If you decide to work with them, they send you an email invitation to establish a partner relationship.</span></span>

## <a name="review-and-accept-a-partner-relationship-and-microsoft-customer-agreement"></a><span data-ttu-id="2600b-140">Granska och acceptera en partnerrelation och Microsofts kundavtal</span><span class="sxs-lookup"><span data-stu-id="2600b-140">Review and accept a partner relationship and Microsoft Customer Agreement</span></span>

<span data-ttu-id="2600b-141">När du har hittat en partner och bestämmer dig för att arbeta med partnern skickar de en e-postinbjudan till dig.</span><span class="sxs-lookup"><span data-stu-id="2600b-141">After you find a partner and decide to work with them, they send you an email invitation.</span></span>

1. <span data-ttu-id="2600b-142">I e-postmeddelandet väljer du länken för att gå till Microsoft 365 administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="2600b-142">In the email, select the link to go to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="2600b-143">På sidan **Acceptera avtal & partner,** väljer du länken till **Microsofts kundavtal** och läser dokumentet.</span><span class="sxs-lookup"><span data-stu-id="2600b-143">On the **Accept agreement & authorize partner** page, select the link for the **Microsoft Customer Agreement**, and read the document.</span></span>
3. <span data-ttu-id="2600b-144">Markera rutan för att bekräfta att du läst avtalet.</span><span class="sxs-lookup"><span data-stu-id="2600b-144">Check the box to acknowledge that you read the agreement.</span></span>
4. <span data-ttu-id="2600b-145">Välj **Godkänn & Godkänn**.</span><span class="sxs-lookup"><span data-stu-id="2600b-145">Select **Accept & Authorize**.</span></span>
5. <span data-ttu-id="2600b-146">Listan över partners som du arbetar med visas.</span><span class="sxs-lookup"><span data-stu-id="2600b-146">The list of partners that you’re working with is displayed.</span></span> <span data-ttu-id="2600b-147">Välj en partner för att se mer information.</span><span class="sxs-lookup"><span data-stu-id="2600b-147">Select any partner to see details.</span></span>

## <a name="review-and-accept-a-microsoft-customer-agreement"></a><span data-ttu-id="2600b-148">Granska och acceptera ett Microsoft-kundavtal</span><span class="sxs-lookup"><span data-stu-id="2600b-148">Review and accept a Microsoft Customer Agreement</span></span>

<span data-ttu-id="2600b-149">Om du redan har en partner, men ännu inte har signerat ett Microsoft-kundavtal, måste du acceptera avtalet innan de kan köpa eller hantera dina prenumerationer för din räkning.</span><span class="sxs-lookup"><span data-stu-id="2600b-149">If you already have a partner but haven’t yet signed a Microsoft Customer Agreement, you must accept the agreement before they can make purchases or manage your subscriptions on your behalf.</span></span>

1. <span data-ttu-id="2600b-150">Om du får ett e-postmeddelande från din partner väljer du länken för att gå Microsoft 365 administrationscentret eller gå till <a href="https://go.microsoft.com/fwlink/?linkid=2116573" target="_blank">sidan Acceptera</a> avtal.</span><span class="sxs-lookup"><span data-stu-id="2600b-150">If you receive an email from your partner, select the link to go to the Microsoft 365 admin center, or go to the <a href="https://go.microsoft.com/fwlink/?linkid=2116573" target="_blank">Accept agreement</a> page.</span></span>
2. <span data-ttu-id="2600b-151">Välj länken för **Microsofts kundavtal** och läs dokumentet.</span><span class="sxs-lookup"><span data-stu-id="2600b-151">Select the link for the **Microsoft Customer Agreement** and read the document.</span></span>
3. <span data-ttu-id="2600b-152">Markera rutan för att bekräfta att du läst avtalet.</span><span class="sxs-lookup"><span data-stu-id="2600b-152">Check the box to acknowledge that you read the agreement.</span></span>
4. <span data-ttu-id="2600b-153">Välj **Acceptera**.</span><span class="sxs-lookup"><span data-stu-id="2600b-153">Select **Accept**.</span></span>
5. <span data-ttu-id="2600b-154">Listan över partners som du arbetar med visas.</span><span class="sxs-lookup"><span data-stu-id="2600b-154">The list of partners that you’re working with is displayed.</span></span> <span data-ttu-id="2600b-155">Välj en partner för att se mer information.</span><span class="sxs-lookup"><span data-stu-id="2600b-155">Select any partner to see details.</span></span>

## <a name="remove-partner-admin-roles"></a><span data-ttu-id="2600b-156">Ta bort partneradministratörsroller</span><span class="sxs-lookup"><span data-stu-id="2600b-156">Remove partner admin roles</span></span>

<span data-ttu-id="2600b-157">När du accepterar inbjudan samtycker du till att ge partnern global administratörsroll och support,beroende på partnerns begäran.</span><span class="sxs-lookup"><span data-stu-id="2600b-157">Depending on the request made by the partner, when you accept the invitation, you agree to give them Global and Helpdesk admin roles.</span></span> <span data-ttu-id="2600b-158">När du ger de här administratörsrollerna till en partner beviljar du dem automatiskt delegerade administratörsbehörigheter i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2600b-158">When you give these admin roles to a partner, you automatically grant them delegated admin privileges in Azure AD.</span></span> <span data-ttu-id="2600b-159">Mer information finns i [Delegerade administratörsbehörigheter i Azure AD.](/partner-center/customers_revoke_admin_privileges#delegated-admin-privileges-in-azure-ad)</span><span class="sxs-lookup"><span data-stu-id="2600b-159">To learn more, see [Delegated admin privileges in Azure AD](/partner-center/customers_revoke_admin_privileges#delegated-admin-privileges-in-azure-ad).</span></span>

<span data-ttu-id="2600b-160">Om du inte vill ge partnern administratörsroller avbryter du inbjudan i stället för att acceptera den.</span><span class="sxs-lookup"><span data-stu-id="2600b-160">If you don't want to give the admin roles to the partner, cancel the invitation instead of accepting it.</span></span>

<span data-ttu-id="2600b-161">Du kan när som helst ta bort administratörsroller från en partner.</span><span class="sxs-lookup"><span data-stu-id="2600b-161">You can remove admin roles from a partner at any time.</span></span> <span data-ttu-id="2600b-162">Partnerrelationen tas inte bort om du tar bort administratörsrollerna.</span><span class="sxs-lookup"><span data-stu-id="2600b-162">Removing the admin roles doesn’t remove the partner relationship.</span></span> <span data-ttu-id="2600b-163">De kan fortfarande arbeta med dig i en annan kapacitet, till exempel som återförsäljare.</span><span class="sxs-lookup"><span data-stu-id="2600b-163">They can still work with you in a different capacity, such as a Reseller.</span></span> <span data-ttu-id="2600b-164">Om du bestämmer dig för att du inte längre vill arbeta med en partner kontaktar du din partner för att avsluta relationen.</span><span class="sxs-lookup"><span data-stu-id="2600b-164">If you decide that you don’t want to work with a partner anymore, contact your partner to end the relationship.</span></span>

1. <span data-ttu-id="2600b-165">I administrationscentret går du till sidan **Inställningar**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">Partnerrelationer.</a></span><span class="sxs-lookup"><span data-stu-id="2600b-165">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">Partner relationships</a> page.</span></span>
2. <span data-ttu-id="2600b-166">På sidan **Partnerrelationer** markerar du den rad som innehåller namnet på den partner som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="2600b-166">On the **Partner relationships** page, select the row that contains the name of the partner that you want to remove.</span></span>
3. <span data-ttu-id="2600b-167">Markera raden som innehåller namnet på partnern.</span><span class="sxs-lookup"><span data-stu-id="2600b-167">Select the row that contains the name of the partner.</span></span>
4. <span data-ttu-id="2600b-168">Välj Ta bort roller på **partnersidan.**</span><span class="sxs-lookup"><span data-stu-id="2600b-168">On the partner page, select **Remove roles**.</span></span>
5. <span data-ttu-id="2600b-169">I dialogrutan **Ta bort roller?** väljer du **Ja.**</span><span class="sxs-lookup"><span data-stu-id="2600b-169">In the **Remove roles?** dialog box, select **Yes**.</span></span>
