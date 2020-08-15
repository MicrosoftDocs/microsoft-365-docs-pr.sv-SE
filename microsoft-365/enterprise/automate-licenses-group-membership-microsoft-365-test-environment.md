---
title: Automatisera licensierings-och grupp medlemskap för test miljön av Microsoft 365 för företag
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Konfigurera gruppbaserade licensierings-och dynamiskt grupp medlemskap i test miljön för Microsoft 365 för företag.
ms.openlocfilehash: a25a47b81ce8c119e7aeb44660af32bb9cafb08a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685564"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="a6e30-103">Automatisera licensierings-och grupp medlemskap för test miljön av Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="a6e30-103">Automate licensing and group membership for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="a6e30-104">*Den här test laboratorie guiden kan endast användas för test miljöer med Microsoft 365 för företags nätverk.*</span><span class="sxs-lookup"><span data-stu-id="a6e30-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="a6e30-105">Gruppbaserade licenser tilldelar eller tar bort licenser automatiskt för ett användar konto baserat på grupp medlemskap.</span><span class="sxs-lookup"><span data-stu-id="a6e30-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="a6e30-106">Dynamiskt grupp medlemskap lägger till eller tar bort medlemmar i en grupp baserat på Egenskaper för användar konton, till exempel avdelning eller land.</span><span class="sxs-lookup"><span data-stu-id="a6e30-106">Dynamic group membership adds or removes members to a group based on user account properties, such as Department or Country.</span></span> <span data-ttu-id="a6e30-107">I den här artikeln beskrivs en demonstration av båda test miljöerna i Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="a6e30-107">This article steps you through a demonstration of both in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="a6e30-108">Det finns två faser för att konfigurera automatisk licensiering och dynamiskt grupp medlemskap i test miljön för Microsoft 365 för företag:</span><span class="sxs-lookup"><span data-stu-id="a6e30-108">There are two phases to setting up auto-licensing and dynamic group membership in your Microsoft 365 for enterprise test environment:</span></span>

1. <span data-ttu-id="a6e30-109">Skapa test miljön för Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="a6e30-109">Create the Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="a6e30-110">Konfigurera och testa dynamiskt grupp medlemskap och automatisk licensiering.</span><span class="sxs-lookup"><span data-stu-id="a6e30-110">Configure and test dynamic group membership and automatic licensing.</span></span>

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="a6e30-112">Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med testlabbguider för Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="a6e30-112">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="a6e30-113">Fas 1: bygga ut test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="a6e30-113">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="a6e30-114">Om du bara vill testa automatiserade licensierings-och grupp medlemskap på ett enkelt sätt med minimi kraven följer du anvisningarna i [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="a6e30-114">If you just want to test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="a6e30-115">Om du vill testa automatiserade licensierings-och grupp medlemskap i ett simulerat företag följer du anvisningarna i [vidarekoppling](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="a6e30-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a6e30-116">För testning av automatiserade licensierings-och grupp medlemskap krävs inte den simulerade företags test miljön, som innehåller ett simulerat intranät som är kopplat till Internet och Directory-synkronisering för en AD DS-skog (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="a6e30-116">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="a6e30-117">Det tillhandahålls här som ett alternativ så att du kan testa automatiserad licensiering och grupp medlemskap och experimentera med den i en miljö som representerar en typisk organisation.</span><span class="sxs-lookup"><span data-stu-id="a6e30-117">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="a6e30-118">Fas 2: Konfigurera och testa dynamiskt grupp medlemskap och automatisk licensiering</span><span class="sxs-lookup"><span data-stu-id="a6e30-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="a6e30-119">Först skapar du en ny Sälj grupp och lägger till en regel för dynamiskt grupp medlemskap så att användar konton med avdelningen satt till Sales läggs till automatiskt i Sälj gruppen.</span><span class="sxs-lookup"><span data-stu-id="a6e30-119">First, you create a new Sales group and add a dynamic group membership rule so that user accounts with the Department set to Sales are automatically added to the Sales group.</span></span>

1. <span data-ttu-id="a6e30-120">Använd en privat instans av webbläsaren och logga in på [administrations centret för microsoft 365](https://admin.microsoft.com) med det globala administratörs kontot för ditt Microsoft 365 E5 test labb-abonnemang.</span><span class="sxs-lookup"><span data-stu-id="a6e30-120">Using a private instance of your Internet browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with the global administrator account of your Microsoft 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="a6e30-121">Gå till Azure Portal på en separat flik i webbläsaren [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="a6e30-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="a6e30-122">I Azure-portalen skriver du **grupper** i sökrutan och klickar sedan på **grupper**.</span><span class="sxs-lookup"><span data-stu-id="a6e30-122">In the Azure portal, type **groups** in the search box, and then click **Groups**.</span></span>
4. <span data-ttu-id="a6e30-123">i fönstret **alla grupper** klickar du på **ny grupp**.</span><span class="sxs-lookup"><span data-stu-id="a6e30-123">in the **All groups** pane, click **New group**.</span></span>
5. <span data-ttu-id="a6e30-124">Välj **Microsoft 365**i **grupptyp**.</span><span class="sxs-lookup"><span data-stu-id="a6e30-124">In **Group type**, select **Microsoft 365**.</span></span>
6. <span data-ttu-id="a6e30-125">I **grupp namn**skriver du **Sales**.</span><span class="sxs-lookup"><span data-stu-id="a6e30-125">In **Group name**, type **Sales**.</span></span>
7. <span data-ttu-id="a6e30-126">Välj **dynamisk användare**i **typ av medlemskap**.</span><span class="sxs-lookup"><span data-stu-id="a6e30-126">In **Membership type**, select **Dynamic user**.</span></span>
8. <span data-ttu-id="a6e30-127">Klicka på **dynamiska användar medlemmar**.</span><span class="sxs-lookup"><span data-stu-id="a6e30-127">Click **Dynamic user members**.</span></span>
9. <span data-ttu-id="a6e30-128">I fönstret **regler för dynamisk medlemskap** :</span><span class="sxs-lookup"><span data-stu-id="a6e30-128">In the **Dynamic membership rules** pane:</span></span> 
   - <span data-ttu-id="a6e30-129">Välj egenskapen **avdelning** .</span><span class="sxs-lookup"><span data-stu-id="a6e30-129">Select the **department** property.</span></span>
   - <span data-ttu-id="a6e30-130">Välj operatorn **Equal** .</span><span class="sxs-lookup"><span data-stu-id="a6e30-130">Select the **Equals** operator.</span></span>
   - <span data-ttu-id="a6e30-131">Ange **försäljning** i **värde**.</span><span class="sxs-lookup"><span data-stu-id="a6e30-131">Type **Sales** in **Value**.</span></span>
10. <span data-ttu-id="a6e30-132">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a6e30-132">Click **Save**.</span></span>
11. <span data-ttu-id="a6e30-133">Klicka på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="a6e30-133">Click **Create**.</span></span>

<span data-ttu-id="a6e30-134">Sedan konfigurerar du Sälj gruppen så att medlemmar tilldelas automatiskt Microsoft 365 E5-licensen.</span><span class="sxs-lookup"><span data-stu-id="a6e30-134">Next, you configure the Sales group so that members are automatically assigned the Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="a6e30-135">Klicka på **försäljnings** gruppen och sedan på **licenser**.</span><span class="sxs-lookup"><span data-stu-id="a6e30-135">Click the **Sales** group, and then click **Licenses**.</span></span>
2. <span data-ttu-id="a6e30-136">I fönstret **Uppdatera licens tilldelningar** väljer du **Microsoft 365 E5**och klickar sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a6e30-136">In the **Update license assignments** pane, select **Microsoft 365 E5**, and then click **Save**.</span></span>
3. <span data-ttu-id="a6e30-137">Stäng fliken för Azure-portalen i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="a6e30-137">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="a6e30-138">Sedan testar du dynamiskt grupp medlemskap och automatisk licensiering på användare 4-kontot.</span><span class="sxs-lookup"><span data-stu-id="a6e30-138">Next, you test dynamic group membership and automatic licensing on the User 4 account.</span></span> 

1. <span data-ttu-id="a6e30-139">Klicka på **admin**på fliken **Microsoft Office Home** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="a6e30-139">From the **Microsoft Office Home** tab in your browser, click **Admin**.</span></span>
2. <span data-ttu-id="a6e30-140">På fliken **administrations Center för Microsoft 365** klickar du på **aktiva användare**.</span><span class="sxs-lookup"><span data-stu-id="a6e30-140">From the **Microsoft 365 admin center** tab, click **Active users**.</span></span>
3. <span data-ttu-id="a6e30-141">På sidan **aktiva användare** klickar du på kontot **användare 4** .</span><span class="sxs-lookup"><span data-stu-id="a6e30-141">On the **Active users** page, click the **User 4** account.</span></span>
4. <span data-ttu-id="a6e30-142">Klicka på **Redigera** för **produkt licenser**i fönstret **användare 4** .</span><span class="sxs-lookup"><span data-stu-id="a6e30-142">On the **User 4** pane, click **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="a6e30-143">I fönstret **produkt licenser** inaktiverar du **Microsoft 365 E5** -licensen och klickar sedan på **Spara > Stäng**.</span><span class="sxs-lookup"><span data-stu-id="a6e30-143">On the **Product licenses** pane, disable the **Microsoft 365 E5** license, and then click **Save > Close**.</span></span>
6. <span data-ttu-id="a6e30-144">I egenskaperna för användare 4-kontot kontrollerar du att inga produkt licenser har tilldelats och att det inte finns några grupp medlemskap.</span><span class="sxs-lookup"><span data-stu-id="a6e30-144">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="a6e30-145">Klicka på **redigera** för **kontakt information**.</span><span class="sxs-lookup"><span data-stu-id="a6e30-145">Click **Edit** for **Contact information**.</span></span>
8. <span data-ttu-id="a6e30-146">Klicka på **kontakt information**i fönstret **Redigera kontakt information** .</span><span class="sxs-lookup"><span data-stu-id="a6e30-146">In the **Edit Contact information** pane, click **Contact information**.</span></span>
9. <span data-ttu-id="a6e30-147">I fältet **avdelning** skriver du **försäljning**och klickar sedan på **Spara > Stäng**.</span><span class="sxs-lookup"><span data-stu-id="a6e30-147">In the **Department** field, type **Sales**, and then click **Save > Close**.</span></span>
10. <span data-ttu-id="a6e30-148">Vänta några minuter och klicka sedan på ikonen uppdatera längst upp till höger i användarens konto fönster.</span><span class="sxs-lookup"><span data-stu-id="a6e30-148">Wait a few minutes, and then periodically click the refresh icon in the upper-right of the User 4 account pane.</span></span> 

<span data-ttu-id="a6e30-149">I tid bör du se:</span><span class="sxs-lookup"><span data-stu-id="a6e30-149">In time you should see the:</span></span>

- <span data-ttu-id="a6e30-150">**Grupp medlemskaps** egenskapen har uppdaterats med **Sälj** gruppen.</span><span class="sxs-lookup"><span data-stu-id="a6e30-150">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="a6e30-151">Egenskapen **produkt licenser** har uppdaterats med **Microsoft 365 E5** -licensen.</span><span class="sxs-lookup"><span data-stu-id="a6e30-151">**Product licenses** property updated with the **Microsoft 365 E5** license.</span></span>

<span data-ttu-id="a6e30-152">Se dessa artiklar för att distribuera dynamiskt grupp medlemskap och automatisk licensiering i produktion:</span><span class="sxs-lookup"><span data-stu-id="a6e30-152">See these articles to deploy dynamic group membership and automatic licensing in production:</span></span>

- <span data-ttu-id="a6e30-153">LÄNKA TBD</span><span class="sxs-lookup"><span data-stu-id="a6e30-153">LINK TBD</span></span>
- <span data-ttu-id="a6e30-154">LÄNKA TBD</span><span class="sxs-lookup"><span data-stu-id="a6e30-154">LINK TBD</span></span>

## <a name="next-step"></a><span data-ttu-id="a6e30-155">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="a6e30-155">Next step</span></span>

<span data-ttu-id="a6e30-156">Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="a6e30-156">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="a6e30-157">Se även</span><span class="sxs-lookup"><span data-stu-id="a6e30-157">See also</span></span>

[<span data-ttu-id="a6e30-158">Identitets översikt</span><span class="sxs-lookup"><span data-stu-id="a6e30-158">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="a6e30-159">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="a6e30-159">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="a6e30-160">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="a6e30-160">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="a6e30-161">Microsoft 365 för företags dokumentation</span><span class="sxs-lookup"><span data-stu-id="a6e30-161">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
