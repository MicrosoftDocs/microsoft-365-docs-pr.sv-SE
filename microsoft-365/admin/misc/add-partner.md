---
title: Lägga till, ändra eller ta bort en partner för abonnemangsrådgivning
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f86e8177-936e-491e-9024-44dea2b296ff
description: Lägg till en postpartner när du köper Microsoft 365, ändrar partnern eller tar bort en partner från en prenumeration.
ms.openlocfilehash: e21c324bc84e360b80deae2abeec610e73834819
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624531"
---
# <a name="add-change-or-delete-a-subscription-advisor-partner"></a><span data-ttu-id="e93ed-103">Lägga till, ändra eller ta bort en partner för abonnemangsrådgivning</span><span class="sxs-lookup"><span data-stu-id="e93ed-103">Add, change, or delete a subscription advisor partner</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="e93ed-104">Den här artikeln gäller Office 365 som drivs av 21Vianet i Kina.</span><span class="sxs-lookup"><span data-stu-id="e93ed-104">This article applies to Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="e93ed-105">Det är till för organisationer som vill tillåta att en 21Vianet-partner administrerar Office 365-prenumerationen åt dem.</span><span class="sxs-lookup"><span data-stu-id="e93ed-105">It is for organizations who want to allow a 21Vianet Partner to administer their Office 365 subscription for them.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="e93ed-106">En auktoriserad Microsoft-partner fungerar som din abonnemangsrådgivare och hjälper dig med expertkunskaper inom försäljning, support och teknik, som behövs för att konfigurera och underhålla ditt abonnemang.</span><span class="sxs-lookup"><span data-stu-id="e93ed-106">An authorized partner of Microsoft who serves as your subscription advisor provides the sales, support, and technical expertise you need to help you set up and maintain your subscription.</span></span> <span data-ttu-id="e93ed-107">Du kan lägga till en abonnemangsrådgivare som en partner av post när du köper Microsoft 365 eller vid en annan tidpunkt.</span><span class="sxs-lookup"><span data-stu-id="e93ed-107">You can add a subscription advisor partner as a partner of record when you purchase Microsoft 365 or at another time.</span></span> <span data-ttu-id="e93ed-108">Om du inte har någon partner kan du hitta en på webbplatsen [Microsoft Pinpoint](https://pinpoint.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="e93ed-108">If you're not currently working with a partner, you can also find one on the [Microsoft Pinpoint](https://pinpoint.microsoft.com) website.</span></span>

::: moniker-end

## <a name="before-you-begin"></a><span data-ttu-id="e93ed-109">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="e93ed-109">Before you begin</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="e93ed-110">Vilken partner du väljer beror på Microsoft-tjänster du använder och landet eller regionen där du kommer att använda tjänsterna.</span><span class="sxs-lookup"><span data-stu-id="e93ed-110">The partner you choose depends on the Microsoft services you use and the country or region where you'll use those services.</span></span> <span data-ttu-id="e93ed-111">Om du lägger till eller ändrar en partner för ditt abonnemang behöver du först be om partnerns Microsoft partner-ID.</span><span class="sxs-lookup"><span data-stu-id="e93ed-111">If you are adding a partner, or changing the partner for your subscription, first you need to get the partner's Microsoft Partner ID by asking the partner for it.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="e93ed-p104">En auktoriserad Microsoft-partner fungerar som din abonnemangsrådgivare och hjälper dig med expertkunskaper inom försäljning, support och teknik, som behövs för att konfigurera och underhålla ditt abonnemang. Du kan lägga till en auktoriserad partner när du köper Office 365, eller vid en senare tidpunkt. Om du inte har någon partner kan du hitta en på webbplatsen [Microsoft Pinpoint](https://pinpoint.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="e93ed-p104">An authorized partner of Microsoft who serves as your subscription advisor provides the sales, support, and technical expertise you need to help you set up and maintain your subscription. You can add a subscription advisor partner as a partner of record when you purchase Office 365 or at another time. If you're not currently working with a partner, you can also find one on the [Microsoft Pinpoint](https://pinpoint.microsoft.com) website.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="e93ed-p105">Vilken partner du väljer beror på vilka Office 365-tjänster du använder och var någonstans du kommer att använda tjänsterna. Om du lägger till eller ändrar en partner för ditt abonnemang behöver du först be om partnerns Microsoft partner-ID.</span><span class="sxs-lookup"><span data-stu-id="e93ed-p105">The partner you choose depends on the Office 365 services you use and the country or region where you'll use those services. If you are adding a partner, or changing the partner for your subscription, first you need to get the partner's Microsoft Partner ID by asking the partner for it.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="e93ed-117">Som administratör för Office 365 kan du bland annat skapa eller redigera användare, återställa användarlösenord, hantera användarlicenser, hantera domäner och tilldela administratörsbehörigheter till andra användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="e93ed-117">As an admin for Office 365, you can create or edit users, reset user passwords, manage user licenses, manage domains, and assign admin permissions to other users in your organization, among other things.</span></span> <span data-ttu-id="e93ed-118">Men om du vill att någon annan ska utföra de här administrativa uppgifterna kan du delegera den här rollen till en auktoriserad partner för 21Vianet genom att skapa en partnerrelation.</span><span class="sxs-lookup"><span data-stu-id="e93ed-118">However, if you want someone else to do these administrative tasks, you can delegate this role to an authorized partner of 21Vianet by creating a partner relationship.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="add-a-partner-at-the-time-of-purchase"></a><span data-ttu-id="e93ed-119">Lägga till en partner vid köptillfället</span><span class="sxs-lookup"><span data-stu-id="e93ed-119">Add a partner at the time of purchase</span></span>

1. <span data-ttu-id="e93ed-120">I administrationscentret går du  till sidan \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Faktureringsköpstjänster.</a></span><span class="sxs-lookup"><span data-stu-id="e93ed-120">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="e93ed-121">Välj den produkt som du vill köpa och välj sedan **Köp**.</span><span class="sxs-lookup"><span data-stu-id="e93ed-121">Select the product that you want to purchase, and then select **Buy**.</span></span>
3. <span data-ttu-id="e93ed-122">Om du vill lägga till en ny partner **expanderar du Behöver du hjälp** med din beställning? och väljer Få hjälp från en **Microsoft-partner.**</span><span class="sxs-lookup"><span data-stu-id="e93ed-122">To add a new partner, expand **Need help with your order?** and select **Get assistance from a Microsoft Partner**.</span></span><br>
<span data-ttu-id="e93ed-123">Följ stegen på leverantörssidan för att antingen söka efter eller matchas med en partner.</span><span class="sxs-lookup"><span data-stu-id="e93ed-123">Follow the steps on the providers page to either search for, or to get matched with a partner.</span></span>
4. <span data-ttu-id="e93ed-124">Om du redan har en partner väljer du Lägg till i det andra steget i utcheckningsguiden, under Partnerinformation i det **högra fönstret.**</span><span class="sxs-lookup"><span data-stu-id="e93ed-124">If you already have a partner, in the second step of the checkout wizard, in the right pane, under Partner information, select **Add**.</span></span>
5. <span data-ttu-id="e93ed-p107">Skriv Microsoft partner-ID för partnern du vill lägga till. Microsoft partner-ID får du reda på genom att fråga partnern.</span><span class="sxs-lookup"><span data-stu-id="e93ed-p107">Type the Microsoft Partner ID for the partner you're adding. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>
6. <span data-ttu-id="e93ed-127">Slutför guiden om du vill genomföra köpet av abonnemang.</span><span class="sxs-lookup"><span data-stu-id="e93ed-127">Complete the rest of the wizard to finish buying your subscriptions.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="add-a-partner-at-the-time-of-purchase"></a><span data-ttu-id="e93ed-128">Lägga till en partner vid köptillfället</span><span class="sxs-lookup"><span data-stu-id="e93ed-128">Add a partner at the time of purchase</span></span>

1. <span data-ttu-id="e93ed-129">I [administrationscentret går](https://go.microsoft.com/fwlink/p/?linkid=848041)du till sidan  \> **Faktureringsköpstjänster.**</span><span class="sxs-lookup"><span data-stu-id="e93ed-129">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), go to the **Billing** \> **Purchase services**  page.</span></span>
2. <span data-ttu-id="e93ed-130">Välj den produkt som du vill köpa och välj sedan **Köp**.</span><span class="sxs-lookup"><span data-stu-id="e93ed-130">Select the product that you want to purchase, and then select **Buy**.</span></span>
3. <span data-ttu-id="e93ed-131">Om du vill lägga till en ny partner **expanderar du Behöver du hjälp** med din beställning? och väljer Få hjälp från en **Microsoft-partner.**</span><span class="sxs-lookup"><span data-stu-id="e93ed-131">To add a new partner, expand **Need help with your order?** and select **Get assistance from a Microsoft Partner**.</span></span><br>
<span data-ttu-id="e93ed-132">Följ stegen på leverantörssidan för att antingen söka efter eller matchas med en partner.</span><span class="sxs-lookup"><span data-stu-id="e93ed-132">Follow the steps on the providers page to either search for, or to get matched with a partner.</span></span>
4. <span data-ttu-id="e93ed-133">Om du redan har en partner väljer du Lägg till i det andra steget i utcheckningsguiden, under Partnerinformation i det **högra fönstret.**</span><span class="sxs-lookup"><span data-stu-id="e93ed-133">If you already have a partner, in the second step of the checkout wizard, in the right pane, under Partner information, select **Add**.</span></span>
5. <span data-ttu-id="e93ed-p108">Skriv Microsoft partner-ID för partnern du vill lägga till. Microsoft partner-ID får du reda på genom att fråga partnern.</span><span class="sxs-lookup"><span data-stu-id="e93ed-p108">Type the Microsoft Partner ID for the partner you're adding. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>
6. <span data-ttu-id="e93ed-136">Slutför guiden om du vill genomföra köpet av abonnemang.</span><span class="sxs-lookup"><span data-stu-id="e93ed-136">Complete the rest of the wizard to finish buying your subscriptions.</span></span>

::: moniker-end

## <a name="add-a-partner-to-an-existing-subscription"></a><span data-ttu-id="e93ed-137">Lägga till en partner till ett befintligt abonnemang</span><span class="sxs-lookup"><span data-stu-id="e93ed-137">Add a partner to an existing subscription</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e93ed-138">I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.</span><span class="sxs-lookup"><span data-stu-id="e93ed-138">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="e93ed-139">På **fliken** Produkter väljer du den prenumeration som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="e93ed-139">On the **Products** tab, select the subscription that you want to edit.</span></span>
3. <span data-ttu-id="e93ed-140">På sidan med prenumerationsinformation, under **Partnerinformation,** skriver du **partnernätverks-ID.**</span><span class="sxs-lookup"><span data-stu-id="e93ed-140">On the subscription details page, under **Partner information**, type the **Partner Network ID**.</span></span> <span data-ttu-id="e93ed-141">Du kan få partnerns Microsoft Partner Network-ID genom att fråga partnern.</span><span class="sxs-lookup"><span data-stu-id="e93ed-141">You can get the partner's Microsoft Partner Network ID by asking the partner for it.</span></span>
4. <span data-ttu-id="e93ed-142">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e93ed-142">Select **Add**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e93ed-143">Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Prenumerationer</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="e93ed-143">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>
2. <span data-ttu-id="e93ed-144">Om du har fler än en prenumeration väljer du den prenumeration som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="e93ed-144">If you have more than one subscription, select the subscription that you want to edit.</span></span>
3. <span data-ttu-id="e93ed-145">Under prenumerationskostnaden till höger väljer du de tre punkterna (fler åtgärder) > **Lägg till partner av post**.</span><span class="sxs-lookup"><span data-stu-id="e93ed-145">On the right, under the subscription cost, select the three dots (more actions) > **Add partner of record**.</span></span>
4. <span data-ttu-id="e93ed-p110">Skriv Microsoft partner-ID för partnern du vill lägga till och klicka på **Kontrollera ID** och sedan på **Skicka**. Rätt Microsoft partner-ID får du reda på genom att fråga partnern.</span><span class="sxs-lookup"><span data-stu-id="e93ed-p110">Type the Microsoft Partner ID for the partner you're adding, select **Check ID**, and then **Submit**. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>
5. <span data-ttu-id="e93ed-148">Partner-ID:t som visas på sidan **Prenumerationer**.</span><span class="sxs-lookup"><span data-stu-id="e93ed-148">The partner ID displays on the **Subscriptions** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="e93ed-149">Den här processen initieras av din auktoriserade partner.</span><span class="sxs-lookup"><span data-stu-id="e93ed-149">This process is initiated by your authorized partner.</span></span> <span data-ttu-id="e93ed-150">Partnern skickar ett e-postmeddelande till dig med en fråga om du vill ge dem tillstånd att fungera som en partner av post.</span><span class="sxs-lookup"><span data-stu-id="e93ed-150">The partner sends you an email to ask you if you want to give them permission to act as a partner of record.</span></span>
  
<span data-ttu-id="e93ed-151">Om du vill acceptera det här erbjudandet</span><span class="sxs-lookup"><span data-stu-id="e93ed-151">To accept this offer</span></span>
  
1. <span data-ttu-id="e93ed-152">Läs partnerns villkor i e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="e93ed-152">Read the partner's terms in the email.</span></span>
2. <span data-ttu-id="e93ed-153">Godkänn avtalet genom att välja länken, som går till en auktoriseringssida i Office 365.</span><span class="sxs-lookup"><span data-stu-id="e93ed-153">To authorize the agreement, select the link, which goes to an authorization page in Office 365.</span></span>
3. <span data-ttu-id="e93ed-154">Under **Partnerrelationer** väljer **du Ja** för att ge partnern behörighet som delegerad administratör och väljer sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="e93ed-154">Under **Partner Relationships**, select **Yes** to authorize the partner to be your delegated admin, and then select **Next**.</span></span>
4. <span data-ttu-id="e93ed-155">Om erbjudandet för partnerrelationen ingår i en utvärderingsprenumeration eller ett köperbjudande skapar du ett konto för utvärderingsversionen eller prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="e93ed-155">If the offer for partner relationship came with a trial subscription or a purchase offer, create your trial or subscription account.</span></span>

::: moniker-end

## <a name="change-the-partner-for-a-subscription"></a><span data-ttu-id="e93ed-156">Ändra partner för en prenumeration</span><span class="sxs-lookup"><span data-stu-id="e93ed-156">Change the partner for a subscription</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e93ed-157">I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.</span><span class="sxs-lookup"><span data-stu-id="e93ed-157">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="e93ed-158">Välj Ta bort under Partnerinformation **på sidan** med **prenumerationsinformation.**</span><span class="sxs-lookup"><span data-stu-id="e93ed-158">On the subscriptions details page, under **Partner information**, select **Remove**.</span></span>
3. <span data-ttu-id="e93ed-159">Skriv **Microsoft Partner Network-ID** för den nya partnern.</span><span class="sxs-lookup"><span data-stu-id="e93ed-159">Type the **Microsoft Partner Network ID** for the new partner.</span></span> <span data-ttu-id="e93ed-160">Du kan få partnerns Microsoft partner-ID genom att fråga dem om det.</span><span class="sxs-lookup"><span data-stu-id="e93ed-160">You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>
4. <span data-ttu-id="e93ed-161">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e93ed-161">Select **Add**.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e93ed-162">Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Prenumerationer</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="e93ed-162">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>
2. <span data-ttu-id="e93ed-163">Om du har flera prenumerationer väljer du namnet på den prenumeration som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="e93ed-163">If you have multiple subscriptions, select the name of the subscription that you want to edit.</span></span>
3. <span data-ttu-id="e93ed-164">Under **Partner-ID** väljer du **Redigera auktoriserad partner**.</span><span class="sxs-lookup"><span data-stu-id="e93ed-164">Under the **Partner ID**, select **Edit partner of record**.</span></span>
4. <span data-ttu-id="e93ed-p113">Skriv det nya Microsoft partner-ID:t för partnern du vill lägga till och klicka på **Kontrollera ID** och sedan på **Skicka**. Rätt Microsoft partner-ID får du reda på genom att fråga partnern.</span><span class="sxs-lookup"><span data-stu-id="e93ed-p113">Type the new Microsoft Partner ID for the partner you're adding, select **Check ID**, and then **Submit**. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e93ed-167">Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Prenumerationer</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="e93ed-167">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>
2. <span data-ttu-id="e93ed-168">Om du har flera prenumerationer väljer du namnet på den prenumeration som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="e93ed-168">If you have multiple subscriptions, select the name of the subscription that you want to edit.</span></span>
3. <span data-ttu-id="e93ed-169">Under **Partner-ID** väljer du **Redigera auktoriserad partner**.</span><span class="sxs-lookup"><span data-stu-id="e93ed-169">Under the **Partner ID**, select **Edit partner of record**.</span></span>
4. <span data-ttu-id="e93ed-p114">Skriv det nya Microsoft partner-ID:t för partnern du vill lägga till och klicka på **Kontrollera ID** och sedan på **Skicka**. Rätt Microsoft partner-ID får du reda på genom att fråga partnern.</span><span class="sxs-lookup"><span data-stu-id="e93ed-p114">Type the new Microsoft Partner ID for the partner you're adding, select **Check ID**, and then **Submit**. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>

::: moniker-end

## <a name="view-your-partner-relationships"></a><span data-ttu-id="e93ed-172">Visa dina partnerrelationer</span><span class="sxs-lookup"><span data-stu-id="e93ed-172">View your partner relationships</span></span>

- <span data-ttu-id="e93ed-173">I administrationscentret går du till sidan **Inställningar**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">Partnerrelationer.</a></span><span class="sxs-lookup"><span data-stu-id="e93ed-173">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">Partner relationships</a> page.</span></span> <span data-ttu-id="e93ed-174">Dina partner visas på den här sidan.</span><span class="sxs-lookup"><span data-stu-id="e93ed-174">Your partners are listed on this page.</span></span>

  <span data-ttu-id="e93ed-175">Om du inte har en partner visas ett meddelande om att det inte finns något här.</span><span class="sxs-lookup"><span data-stu-id="e93ed-175">If you don't have a partner, you'll see a message that says "There's nothing here."</span></span>
  
## <a name="delete-a-partner-from-a-subscription"></a><span data-ttu-id="e93ed-176">Ta bort en partner från ett prenumeration</span><span class="sxs-lookup"><span data-stu-id="e93ed-176">Delete a partner from a subscription</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e93ed-177">I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.</span><span class="sxs-lookup"><span data-stu-id="e93ed-177">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="e93ed-178">På **fliken** Produkter väljer du den prenumeration som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="e93ed-178">On the **Products** tab, select the subscription that you want to edit.</span></span>
3. <span data-ttu-id="e93ed-179">Välj Ta bort under Partnerinformation **på sidan** **prenumerationsinformation.**</span><span class="sxs-lookup"><span data-stu-id="e93ed-179">On the subscription details page, under **Partner information**, select **Remove**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e93ed-180">Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Prenumerationer</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="e93ed-180">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>
2. <span data-ttu-id="e93ed-181">Om du har flera prenumerationer väljer du namnet på den prenumeration som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="e93ed-181">If you have multiple subscriptions, select the name of the subscription that you want to edit.</span></span>
3. <span data-ttu-id="e93ed-182">Under **Partner-ID** väljer du **Redigera auktoriserad partner**.</span><span class="sxs-lookup"><span data-stu-id="e93ed-182">Under the **Partner ID**, select **Edit partner of record**.</span></span>
4. <span data-ttu-id="e93ed-183">On the **Partner information** page, clear the **partner ID** box, and then select **Submit**.</span><span class="sxs-lookup"><span data-stu-id="e93ed-183">On the **Partner information** page, clear the **partner ID** box, and then select **Submit**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e93ed-184">Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Prenumerationer</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="e93ed-184">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>
2. <span data-ttu-id="e93ed-185">Om du har flera prenumerationer väljer du namnet på den prenumeration som du vill redigera.</span><span class="sxs-lookup"><span data-stu-id="e93ed-185">If you have multiple subscriptions, select the name of the subscription that you want to edit.</span></span>
3. <span data-ttu-id="e93ed-186">Under **Partner-ID** väljer du **Redigera auktoriserad partner**.</span><span class="sxs-lookup"><span data-stu-id="e93ed-186">Under the **Partner ID**, select **Edit partner of record**.</span></span>
4. <span data-ttu-id="e93ed-187">On the **Partner information** page, clear the **partner ID** box, and then select **Submit**.</span><span class="sxs-lookup"><span data-stu-id="e93ed-187">On the **Partner information** page, clear the **partner ID** box, and then select **Submit**.</span></span>

::: moniker-end

## <a name="remove-a-reseller-relationship"></a><span data-ttu-id="e93ed-188">Ta bort en återförsäljarrelation</span><span class="sxs-lookup"><span data-stu-id="e93ed-188">Remove a reseller relationship</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="e93ed-189">Du kan inte ta bort en återförsäljarrelation med en dig själv.</span><span class="sxs-lookup"><span data-stu-id="e93ed-189">You can't remove a reseller relationship yourself.</span></span>
  
<span data-ttu-id="e93ed-190">Om du tar bort en återförsäljarrelation är alternativet **Ta bort** nedtonat och du måste be din återförsäljare följa de här anvisningarna: [Ta bort en återförsäljarrelation med en partner](/partner-center/remove-a-relationship).</span><span class="sxs-lookup"><span data-stu-id="e93ed-190">If you are removing a reseller relationship the **Delete** option is grayed out, and you will have to ask your reseller partner to follow these instructions: [Remove a reseller relationship with partner](/partner-center/remove-a-relationship).</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="e93ed-191">Du kan inte ta bort en återförsäljarrelation med en dig själv.</span><span class="sxs-lookup"><span data-stu-id="e93ed-191">You can't remove a reseller relationship yourself.</span></span>
  
<span data-ttu-id="e93ed-192">Om du tar bort en återförsäljarrelation är alternativet **Ta bort** nedtonat och du måste be din återförsäljare följa de här anvisningarna: [Ta bort en återförsäljarrelation med en partner](/partner-center/remove-a-relationship).</span><span class="sxs-lookup"><span data-stu-id="e93ed-192">If you are removing a reseller relationship the **Delete** option is grayed out, and you will have to ask your reseller partner to follow these instructions: [Remove a reseller relationship with partner](/partner-center/remove-a-relationship).</span></span>
  
::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="e93ed-193">Du kan inte ta bort en återförsäljarrelation med en dig själv.</span><span class="sxs-lookup"><span data-stu-id="e93ed-193">You can't remove a reseller relationship yourself.</span></span>
  
<span data-ttu-id="e93ed-194">Du måste be din återförsäljare att följa de här instruktionerna: Ta [bort en återförsäljarrelation med en partner](/partner-center/remove-a-relationship).</span><span class="sxs-lookup"><span data-stu-id="e93ed-194">You will have to ask your reseller partner to follow these instructions: [Remove a reseller relationship with partner](/partner-center/remove-a-relationship).</span></span>
  
::: moniker-end

## <a name="related-content"></a><span data-ttu-id="e93ed-195">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="e93ed-195">Related content</span></span>

<span data-ttu-id="e93ed-196">[Hitta din Microsoft 365 partner eller återförsäljare](../manage/find-your-partner-or-reseller.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="e93ed-196">[Find your Microsoft 365 partner or reseller](../manage/find-your-partner-or-reseller.md) (article)</span></span>\
<span data-ttu-id="e93ed-197">[Planera konfigurationen av Microsoft 365 för företag](../setup/plan-your-setup.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="e93ed-197">[Plan your setup of Microsoft 365 for business](../setup/plan-your-setup.md) (article)</span></span>