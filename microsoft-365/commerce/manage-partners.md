---
title: Hantera partnerrelationer
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
- commerce
ms.custom: ''
search.appverid:
- MET150
description: Lär dig hur du arbetar med Microsoft-certifierade lösningsleverantörer (partner) för att köpa och hantera produkter och tjänster för din organisation eller skola.
keywords: partner, lösningsleverantör
ms.openlocfilehash: 3ba5a62caf199bf1e111ecf921df0f21568d5257
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2020
ms.locfileid: "44141213"
---
# <a name="manage-partner-relationships"></a><span data-ttu-id="a5745-104">Hantera partnerrelationer</span><span class="sxs-lookup"><span data-stu-id="a5745-104">Manage partner relationships</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="a5745-105">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="a5745-105">The admin center is changing.</span></span> <span data-ttu-id="a5745-106">Om din upplevelse inte stämmer överens med informationen som presenteras här läser du [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="a5745-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="a5745-107">Du kan arbeta med Microsoft-certifierade lösningsleverantörer (partner) för att köpa och hantera produkter och tjänster för din organisation eller skola.</span><span class="sxs-lookup"><span data-stu-id="a5745-107">You can work with Microsoft-certified solution providers (partners) to purchase and manage products and services for your organization or school.</span></span> <span data-ttu-id="a5745-108">Det finns några steg inblandade i att få saker och ting inställda.</span><span class="sxs-lookup"><span data-stu-id="a5745-108">There are a few steps involved in getting things set up.</span></span>

- <span data-ttu-id="a5745-109">Administratörer hitta och kontakta en partner <a href="https://www.microsoft.com/en-us/solution-providers/home" target="_blank">https://www.microsoft.com/en-us/solution-providers/home</a>med hjälp av formuläret på .</span><span class="sxs-lookup"><span data-stu-id="a5745-109">Admins find and contact a partner using the form at <a href="https://www.microsoft.com/en-us/solution-providers/home" target="_blank">https://www.microsoft.com/en-us/solution-providers/home</a>.</span></span>
- <span data-ttu-id="a5745-110">Partner skickar en e-postbegäran till kunder för att upprätta en partnerrelation.</span><span class="sxs-lookup"><span data-stu-id="a5745-110">Partners send an email request to customers to establish a partner relationship.</span></span>
- <span data-ttu-id="a5745-111">Kunderna accepterar inbjudan i Microsoft 365 admincenter och börja arbeta med partnern.</span><span class="sxs-lookup"><span data-stu-id="a5745-111">Customers accept the invitation in Microsoft 365 admin center and start working with the partner.</span></span>

## <a name="what-can-a-partner-do-for-my-organization-or-school"></a><span data-ttu-id="a5745-112">Vad kan en partner göra för min organisation eller skola?</span><span class="sxs-lookup"><span data-stu-id="a5745-112">What can a partner do for my organization or school?</span></span>

<span data-ttu-id="a5745-113">Det finns flera sätt att en partner kan arbeta med dig.</span><span class="sxs-lookup"><span data-stu-id="a5745-113">There are several ways that a partner can work with you.</span></span> <span data-ttu-id="a5745-114">Baserat på dina angivna affärsbehov väljer de en av dessa typer när de skickar sin begäran om att arbeta med dig.</span><span class="sxs-lookup"><span data-stu-id="a5745-114">Based on your stated business needs, they choose one of these types when they send their request to work with you.</span></span>

| <span data-ttu-id="a5745-115">Typ av partner</span><span class="sxs-lookup"><span data-stu-id="a5745-115">Partner type</span></span> | <span data-ttu-id="a5745-116">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="a5745-116">Description</span></span> |
| ------ | ------------------- |
| <span data-ttu-id="a5745-117">Återförsäljare</span><span class="sxs-lookup"><span data-stu-id="a5745-117">Reseller</span></span> | <span data-ttu-id="a5745-118">Partner som säljer Microsoft-produkter till din organisation eller skola.</span><span class="sxs-lookup"><span data-stu-id="a5745-118">Partners that sell Microsoft products to your organization or school.</span></span> |
| <span data-ttu-id="a5745-119">Delegerad administratör</span><span class="sxs-lookup"><span data-stu-id="a5745-119">Delegated administrator</span></span> | <span data-ttu-id="a5745-120">Partner som hanterar produkter och tjänster för din organisation eller skola.</span><span class="sxs-lookup"><span data-stu-id="a5745-120">Partners that manage products and services for your organization or school.</span></span> <span data-ttu-id="a5745-121">I Azure Active Directory (AD) är partnern en global administratör för din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="a5745-121">In Azure Active Directory (AD), the partner is a Global Administrator for your tenant.</span></span> <span data-ttu-id="a5745-122">Med den här rollen kan de hantera tjänster som att skapa användarkonton, tilldela och hantera licenser och återställa lösenord.</span><span class="sxs-lookup"><span data-stu-id="a5745-122">This role lets them manage services like creating user accounts, assigning and managing licenses, and password resets.</span></span> |
| <span data-ttu-id="a5745-123">Återförsäljare & delegerad administratör</span><span class="sxs-lookup"><span data-stu-id="a5745-123">Reseller & delegated administrator</span></span> | <span data-ttu-id="a5745-124">Partner som säljer och hanterar Microsofts produkter och tjänster till din organisation eller skola.</span><span class="sxs-lookup"><span data-stu-id="a5745-124">Partners that sell and manage Microsoft products and services to your organization or school.</span></span> |
| <span data-ttu-id="a5745-125">Partner</span><span class="sxs-lookup"><span data-stu-id="a5745-125">Partner</span></span> | <span data-ttu-id="a5745-126">Du ger din partner ett användarkonto i din klientorganisation och de arbetar med andra Microsoft-tjänster för din räkning.</span><span class="sxs-lookup"><span data-stu-id="a5745-126">You give your partner a user account in your tenant, and they work with other Microsoft services on your behalf.</span></span> |
| <span data-ttu-id="a5745-127">Rådgivare</span><span class="sxs-lookup"><span data-stu-id="a5745-127">Advisor</span></span> | <span data-ttu-id="a5745-128">Partner kan återställa lösenord och hantera supportincidenter åt dig.</span><span class="sxs-lookup"><span data-stu-id="a5745-128">Partners can reset passwords and handle support incidents for you.</span></span> |
| <span data-ttu-id="a5745-129">Mpsa-partner (Microsoft Products & Services Agreement)</span><span class="sxs-lookup"><span data-stu-id="a5745-129">Microsoft Products & Services Agreement (MPSA) partner</span></span> | <span data-ttu-id="a5745-130">Om du har arbetat med flera partner via MPSA-programmet kan du låta dem se köp som görs av varandra.</span><span class="sxs-lookup"><span data-stu-id="a5745-130">If you've worked with multiple partners through the MPSA program, you can allow them to see purchases made by each other.</span></span> |
| <span data-ttu-id="a5745-131">OEM PC-partner</span><span class="sxs-lookup"><span data-stu-id="a5745-131">OEM PC partner</span></span> | <span data-ttu-id="a5745-132">Partner kan ladda upp enhets-ID:n för datorer som du [hanterar med Autopilot](https://docs.microsoft.com/microsoft-store/add-profile-to-devices).</span><span class="sxs-lookup"><span data-stu-id="a5745-132">Partners can upload device IDs for PCs that you're [managing with Autopilot](https://docs.microsoft.com/microsoft-store/add-profile-to-devices).</span></span> |
| <span data-ttu-id="a5745-133">LOB-partner (Line-of-business)</span><span class="sxs-lookup"><span data-stu-id="a5745-133">Line-of-business (LOB) partner</span></span> | <span data-ttu-id="a5745-134">Partner kan utveckla, skicka in och hantera LOB-appar som är specifika för din organisation eller skola.</span><span class="sxs-lookup"><span data-stu-id="a5745-134">Partners can develop, submit, and manage LOB apps specific for your organization or school.</span></span> |

## <a name="find-a-partner"></a><span data-ttu-id="a5745-135">Hitta en partner</span><span class="sxs-lookup"><span data-stu-id="a5745-135">Find a partner</span></span>

1. <span data-ttu-id="a5745-136">Gå till <a href="https://www.microsoft.com/en-us/solution-providers/home" target="_blank">https://www.microsoft.com/en-us/solution-providers/home</a>.</span><span class="sxs-lookup"><span data-stu-id="a5745-136">Go to <a href="https://www.microsoft.com/en-us/solution-providers/home" target="_blank">https://www.microsoft.com/en-us/solution-providers/home</a>.</span></span>
2. <span data-ttu-id="a5745-137">Ange din plats, välj organisationsstorlek, lägg till nyckelord för den typ av tjänster du behöver och välj sedan **Gå**.</span><span class="sxs-lookup"><span data-stu-id="a5745-137">Enter your location, choose your organization size, add keywords for the type of services you need, then select **Go**.</span></span>
3. <span data-ttu-id="a5745-138">Välj en eller flera partner och välj sedan **Kontakta valda leverantörer**.</span><span class="sxs-lookup"><span data-stu-id="a5745-138">Choose one or more partners, then select **Contact selected providers**.</span></span>
4. <span data-ttu-id="a5745-139">Fyll i formuläret för att beskriva dina affärsbehov och välj sedan **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="a5745-139">Complete the form to describe your business needs, then select **Send**.</span></span>

<span data-ttu-id="a5745-140">Partnern kontaktar dig och ger dig en chans att lära dig mer om dem.</span><span class="sxs-lookup"><span data-stu-id="a5745-140">The partner contacts you and gives you a chance to learn more about them.</span></span> <span data-ttu-id="a5745-141">Om du bestämmer dig för att arbeta med dem skickar de en e-postanbjudan för att upprätta en partnerrelation.</span><span class="sxs-lookup"><span data-stu-id="a5745-141">If you decide to work with them, they send you an email invitation to establish a partner relationship.</span></span>

## <a name="review-and-accept-a-partner-relationship-and-microsoft-customer-agreement"></a><span data-ttu-id="a5745-142">Granska och acceptera en partnerrelation och Microsofts kundavtal</span><span class="sxs-lookup"><span data-stu-id="a5745-142">Review and accept a partner relationship and Microsoft Customer Agreement</span></span>

<span data-ttu-id="a5745-143">När du har hittat en partner och bestämmer dig för att arbeta med dem skickar de en e-postanbjudan.</span><span class="sxs-lookup"><span data-stu-id="a5745-143">After you find a partner and decide to work with them, they send you an email invitation.</span></span>

1. <span data-ttu-id="a5745-144">Välj länken i e-postmeddelandet för att gå till microsoft 365-administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="a5745-144">In the email, select the link to go to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="a5745-145">På **sidan Acceptera avtal & auktorisera partner** väljer du länken för **Microsofts kundavtal**och läser dokumentet.</span><span class="sxs-lookup"><span data-stu-id="a5745-145">On the **Accept agreement & authorize partner** page, select the link for the **Microsoft Customer Agreement**, and read the document.</span></span>
3. <span data-ttu-id="a5745-146">Markera rutan för att bekräfta att du har läst avtalet.</span><span class="sxs-lookup"><span data-stu-id="a5745-146">Check the box to acknowledge that you read the agreement.</span></span>
4. <span data-ttu-id="a5745-147">Välj **Acceptera & auktorisera**.</span><span class="sxs-lookup"><span data-stu-id="a5745-147">Select **Accept & Authorize**.</span></span>
5. <span data-ttu-id="a5745-148">Listan över partner som du arbetar med visas.</span><span class="sxs-lookup"><span data-stu-id="a5745-148">The list of partners that you’re working with is displayed.</span></span> <span data-ttu-id="a5745-149">Välj en partner om du vill se information.</span><span class="sxs-lookup"><span data-stu-id="a5745-149">Select any partner to see details.</span></span>

## <a name="review-and-accept-a-microsoft-customer-agreement"></a><span data-ttu-id="a5745-150">Granska och acceptera ett Microsoft-kundavtal</span><span class="sxs-lookup"><span data-stu-id="a5745-150">Review and accept a Microsoft Customer Agreement</span></span>

<span data-ttu-id="a5745-151">Om du redan har en partner men ännu inte har undertecknat ett Microsoft-kundavtal måste du acceptera avtalet innan de kan göra inköp eller hantera dina prenumerationer för din räkning.</span><span class="sxs-lookup"><span data-stu-id="a5745-151">If you already have a partner but haven’t yet signed a Microsoft Customer Agreement, you must accept the agreement before they can make purchases or manage your subscriptions on your behalf.</span></span>

1. <span data-ttu-id="a5745-152">Om du får ett e-postmeddelande från din partner väljer du länken för att gå till administrationscentret för Microsoft 365 eller gå till sidan <a href="https://go.microsoft.com/fwlink/?linkid=2116573" target="_blank">Acceptera avtal.</a></span><span class="sxs-lookup"><span data-stu-id="a5745-152">If you receive an email from your partner, select the link to go to the Microsoft 365 admin center, or go to the <a href="https://go.microsoft.com/fwlink/?linkid=2116573" target="_blank">Accept agreement</a> page.</span></span>
2. <span data-ttu-id="a5745-153">Välj länken för **Microsofts kundavtal** och läs dokumentet.</span><span class="sxs-lookup"><span data-stu-id="a5745-153">Select the link for the **Microsoft Customer Agreement** and read the document.</span></span>
3. <span data-ttu-id="a5745-154">Markera rutan för att bekräfta att du har läst avtalet.</span><span class="sxs-lookup"><span data-stu-id="a5745-154">Check the box to acknowledge that you read the agreement.</span></span>
4. <span data-ttu-id="a5745-155">Välj **Acceptera**.</span><span class="sxs-lookup"><span data-stu-id="a5745-155">Select **Accept**.</span></span>
5. <span data-ttu-id="a5745-156">Listan över partner som du arbetar med visas.</span><span class="sxs-lookup"><span data-stu-id="a5745-156">The list of partners that you’re working with is displayed.</span></span> <span data-ttu-id="a5745-157">Välj en partner om du vill se information.</span><span class="sxs-lookup"><span data-stu-id="a5745-157">Select any partner to see details.</span></span>

## <a name="remove-partner-admin-privileges"></a><span data-ttu-id="a5745-158">Ta bort partneradministratörsbehörighet</span><span class="sxs-lookup"><span data-stu-id="a5745-158">Remove partner admin privileges</span></span>

<span data-ttu-id="a5745-159">Beroende på partnerns begäran ingår att en del av accepterande av inbjudan går med på att ge dem delegerade administratörsbehörighet.</span><span class="sxs-lookup"><span data-stu-id="a5745-159">Depending on the request made by the partner, part of accepting the invitation includes agreeing to give delegated admin privileges to the them.</span></span> <span data-ttu-id="a5745-160">Mer information finns [i Delegerade administratörsbehörigheter i Azure AD](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#delegated-admin-privileges-in-azure-ad).</span><span class="sxs-lookup"><span data-stu-id="a5745-160">For more information, see [Delegated admin privileges in Azure AD](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#delegated-admin-privileges-in-azure-ad).</span></span>

<span data-ttu-id="a5745-161">Om du inte vill delegera administratörsbehörighet till partnern avbryter du inbjudan i stället för att acceptera den.</span><span class="sxs-lookup"><span data-stu-id="a5745-161">If you don't want to delegate admin privileges to the partner, cancel the invitation instead of accepting it.</span></span>

<span data-ttu-id="a5745-162">Om du delegerar administratörsbehörighet till en partner kan du ta bort dessa privilegier när som helst.</span><span class="sxs-lookup"><span data-stu-id="a5745-162">If you delegate admin privileges to a partner, you can remove those privileges at any time.</span></span> <span data-ttu-id="a5745-163">Om du tar bort administratörsbehörighet tas inte partnerrelationen bort.</span><span class="sxs-lookup"><span data-stu-id="a5745-163">Removing admin privileges doesn’t remove the partner relationship.</span></span> <span data-ttu-id="a5745-164">De kan fortfarande arbeta med dig, till exempel som återförsäljare.</span><span class="sxs-lookup"><span data-stu-id="a5745-164">They can still work with you, for example, as a Reseller.</span></span>

1. <span data-ttu-id="a5745-165">Gå till sidan > <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Faktureringskonton</a> i administrationscentret. **Billing**</span><span class="sxs-lookup"><span data-stu-id="a5745-165">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing accounts</a> page.</span></span>
2. <span data-ttu-id="a5745-166">På sidan **Faktureringskonton** väljer du fliken **Partnerrelationer.**</span><span class="sxs-lookup"><span data-stu-id="a5745-166">On the **Billing accounts** page, select the **Partner relationships** tab.</span></span>
3. <span data-ttu-id="a5745-167">Markera raden som innehåller namnet på partnern.</span><span class="sxs-lookup"><span data-stu-id="a5745-167">Select the row that contains the name of the partner.</span></span>
4. <span data-ttu-id="a5745-168">På partnersidan väljer du **Ta bort administratörsroller**.</span><span class="sxs-lookup"><span data-stu-id="a5745-168">On the partner page, select **Remove admin roles**.</span></span>

## <a name="delete-a-partner-relationship"></a><span data-ttu-id="a5745-169">Ta bort en partnerrelation</span><span class="sxs-lookup"><span data-stu-id="a5745-169">Delete a partner relationship</span></span>

<span data-ttu-id="a5745-170">Om du bestämmer dig för att du inte vill arbeta med en partner längre kan du avsluta relationen.</span><span class="sxs-lookup"><span data-stu-id="a5745-170">If you decide that you don’t want to work with a partner anymore, you can end the relationship.</span></span> <span data-ttu-id="a5745-171">Du kan dock bara ta bort relationer där partnern antingen är delegerad administratör eller rådgivare.</span><span class="sxs-lookup"><span data-stu-id="a5745-171">However, you can only delete relationships where the partner is either a Delegated Administrator or an Advisor.</span></span> <span data-ttu-id="a5745-172">För alla andra partnertyper kontaktar du din partner för att avsluta relationen.</span><span class="sxs-lookup"><span data-stu-id="a5745-172">For all other partner types, contact your partner to end the relationship.</span></span>

1. <span data-ttu-id="a5745-173">Gå till sidan > <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Faktureringskonton</a> i administrationscentret. **Billing**</span><span class="sxs-lookup"><span data-stu-id="a5745-173">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing accounts</a> page.</span></span>
2. <span data-ttu-id="a5745-174">På sidan **Faktureringskonton** väljer du fliken **Partnerrelationer.**</span><span class="sxs-lookup"><span data-stu-id="a5745-174">On the **Billing accounts** page, select the **Partner relationships** tab.</span></span>
3. <span data-ttu-id="a5745-175">Markera raden som innehåller namnet på partnern.</span><span class="sxs-lookup"><span data-stu-id="a5745-175">Select the row that contains the name of the partner.</span></span>
4. <span data-ttu-id="a5745-176">På partnerinformationssidan väljer du **Ta bort partner**.</span><span class="sxs-lookup"><span data-stu-id="a5745-176">On the partner detail page, select **Delete partner**.</span></span>
