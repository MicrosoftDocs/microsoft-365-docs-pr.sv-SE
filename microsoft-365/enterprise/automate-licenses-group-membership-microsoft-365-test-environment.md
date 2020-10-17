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
ms.openlocfilehash: d770e7be3b0b55855f1fee26a45d55260c3074cb
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487582"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="31703-103">Automatisera licensierings-och grupp medlemskap för test miljön av Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="31703-103">Automate licensing and group membership for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="31703-104">*Den här test laboratorie guiden kan endast användas för test miljöer med Microsoft 365 för företags nätverk.*</span><span class="sxs-lookup"><span data-stu-id="31703-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="31703-105">Gruppbaserade licenser tilldelar eller tar bort licenser automatiskt för ett användar konto baserat på grupp medlemskap.</span><span class="sxs-lookup"><span data-stu-id="31703-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="31703-106">Dynamiskt grupp medlemskap lägger till eller tar bort medlemmar i en grupp baserat på Egenskaper för användar konton, till exempel **avdelning** eller **land**.</span><span class="sxs-lookup"><span data-stu-id="31703-106">Dynamic group membership adds or removes members to a group based on user account properties, such as **Department** or **Country**.</span></span> <span data-ttu-id="31703-107">I den här artikeln beskrivs hur du gör demonstrationer av både att lägga till och ta bort grupp medlemmar i test miljön för Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="31703-107">This article steps you through demonstrations of both adding and removing group members in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="31703-108">Att konfigurera automatisk licensiering och dynamiskt grupp medlemskap i test miljön för Microsoft 365 för företag omfattar två faser:</span><span class="sxs-lookup"><span data-stu-id="31703-108">Setting up auto-licensing and dynamic group membership in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="31703-109">Fas 1: bygga ut test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="31703-109">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="31703-110">Fas 2: Konfigurera och testa dynamiskt grupp medlemskap och automatisk licensiering</span><span class="sxs-lookup"><span data-stu-id="31703-110">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="31703-112">Om du vill visa en visuell karta till alla artiklar i gruppen Microsoft 365 för Enterprise-testlabbet går du till [Microsoft 365 för Enterprise Test Lab-guide](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="31703-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="31703-113">Fas 1: bygga ut test miljön för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="31703-113">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="31703-114">Om du bara vill testa automatiserade licensierings-och grupp medlemskap på ett enkelt sätt med minimi kraven följer du anvisningarna i [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="31703-114">If you want to only test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="31703-115">Om du vill testa automatiserade licensierings-och grupp medlemskap i ett simulerat företag följer du anvisningarna i [vidarekoppling](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="31703-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="31703-116">För testning av automatiserade licensierings-och grupp medlemskap krävs inte den simulerade företags test miljön, som innehåller ett simulerat intranät som är kopplat till Internet och Directory-synkronisering för en AD DS-skog (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="31703-116">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="31703-117">Det finns här som ett alternativ så att du kan testa automatiserad licensiering och grupp medlemskap och experimentera med den i en miljö som representerar en typisk organisation.</span><span class="sxs-lookup"><span data-stu-id="31703-117">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="31703-118">Fas 2: Konfigurera och testa dynamiskt grupp medlemskap och automatisk licensiering</span><span class="sxs-lookup"><span data-stu-id="31703-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="31703-119">Börja med att skapa en ny grupp med namnet försäljning och Lägg till en regel för dynamiskt grupp medlemskap så att användar kontona med **avdelningen** angett till **försäljning** automatiskt ansluter till Sälj gruppen.</span><span class="sxs-lookup"><span data-stu-id="31703-119">First, create a new group named Sales, and add a dynamic group membership rule so that user accounts with the **Department** set to **Sales** automatically join the Sales group.</span></span>

1. <span data-ttu-id="31703-120">Logga in på [administrations centret för microsoft 365](https://admin.microsoft.com) i en privat instans av din webbläsare med det globala administratörs kontot för ditt Microsoft 365 E5 test labb-abonnemang.</span><span class="sxs-lookup"><span data-stu-id="31703-120">In a private instance of your internet browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with the global administrator account of your Microsoft 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="31703-121">Gå till Azure Portal på en separat flik i webbläsaren [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="31703-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="31703-122">I Azure-portalen anger du **grupper** i sökrutan och väljer sedan **grupper**.</span><span class="sxs-lookup"><span data-stu-id="31703-122">In the Azure portal, enter **groups** in the search box, and then select **Groups**.</span></span>
4. <span data-ttu-id="31703-123">Välj **ny grupp**i fönstret **alla grupper** .</span><span class="sxs-lookup"><span data-stu-id="31703-123">in the **All groups** pane, select **New group**.</span></span>
5. <span data-ttu-id="31703-124">Välj **Microsoft 365**i **grupptyp**.</span><span class="sxs-lookup"><span data-stu-id="31703-124">In **Group type**, select **Microsoft 365**.</span></span>
6. <span data-ttu-id="31703-125">Ange **försäljning**i **grupp namn**.</span><span class="sxs-lookup"><span data-stu-id="31703-125">In **Group name**, enter **Sales**.</span></span>
7. <span data-ttu-id="31703-126">Välj **dynamisk användare**i **typ av medlemskap**.</span><span class="sxs-lookup"><span data-stu-id="31703-126">In **Membership type**, select **Dynamic user**.</span></span>
8. <span data-ttu-id="31703-127">Välj **dynamiska användar medlemmar**.</span><span class="sxs-lookup"><span data-stu-id="31703-127">Select **Dynamic user members**.</span></span>
9. <span data-ttu-id="31703-128">I fönstret **regler för dynamisk medlemskap** :</span><span class="sxs-lookup"><span data-stu-id="31703-128">In the **Dynamic membership rules** pane:</span></span> 
   - <span data-ttu-id="31703-129">Välj egenskapen **avdelning** .</span><span class="sxs-lookup"><span data-stu-id="31703-129">Select the **department** property.</span></span>
   - <span data-ttu-id="31703-130">Välj operatorn **Equal** .</span><span class="sxs-lookup"><span data-stu-id="31703-130">Select the **Equals** operator.</span></span>
   - <span data-ttu-id="31703-131">I rutan **värde** anger du **Sales**.</span><span class="sxs-lookup"><span data-stu-id="31703-131">In the **Value** box, enter **Sales**.</span></span>
10. <span data-ttu-id="31703-132">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="31703-132">Select **Save**.</span></span>
11. <span data-ttu-id="31703-133">Välj **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="31703-133">Select **Create**.</span></span>

<span data-ttu-id="31703-134">Konfigurera sedan Sälj gruppen så att medlemmar tilldelas automatiskt Microsoft 365 E5-licensen.</span><span class="sxs-lookup"><span data-stu-id="31703-134">Next, configure the Sales group so that members are automatically assigned the Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="31703-135">Välj **Sälj** gruppen och sedan **licenser**.</span><span class="sxs-lookup"><span data-stu-id="31703-135">Select the **Sales** group, and then select **Licenses**.</span></span>
2. <span data-ttu-id="31703-136">I fönstret **Uppdatera licens tilldelningar** väljer du **Microsoft 365 E5**och väljer sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="31703-136">In the **Update license assignments** pane, select **Microsoft 365 E5**, and then select **Save**.</span></span>
3. <span data-ttu-id="31703-137">I webbläsaren stänger du Azure Portal-fliken.</span><span class="sxs-lookup"><span data-stu-id="31703-137">In your browser, close the Azure portal tab.</span></span>

<span data-ttu-id="31703-138">Testa sedan dynamiskt grupp medlemskap och automatisk licensiering på användare 4-kontot:</span><span class="sxs-lookup"><span data-stu-id="31703-138">Next, test dynamic group membership and automatic licensing on the User 4 account:</span></span>

1. <span data-ttu-id="31703-139">Välj **admin**på fliken **Microsoft Office Home** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="31703-139">From the **Microsoft Office Home** tab in your browser, select **Admin**.</span></span>
2. <span data-ttu-id="31703-140">På fliken **administrations Center för Microsoft 365** väljer **du aktiva användare**.</span><span class="sxs-lookup"><span data-stu-id="31703-140">From the **Microsoft 365 admin center** tab, select **Active users**.</span></span>
3. <span data-ttu-id="31703-141">På sidan **aktiva användare** väljer du kontot **användare 4** .</span><span class="sxs-lookup"><span data-stu-id="31703-141">On the **Active users** page, select the **User 4** account.</span></span>
4. <span data-ttu-id="31703-142">I fönstret **användare 4** väljer du **Redigera** för **produkt licenser**.</span><span class="sxs-lookup"><span data-stu-id="31703-142">On the **User 4** pane, select **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="31703-143">I fönstret **produkt licenser** inaktiverar du **Microsoft 365 E5** -licensen och väljer sedan **Spara**  >  **stängning**.</span><span class="sxs-lookup"><span data-stu-id="31703-143">On the **Product licenses** pane, disable the **Microsoft 365 E5** license, and then select **Save** > **Close**.</span></span>
6. <span data-ttu-id="31703-144">I egenskaperna för användare 4-kontot kontrollerar du att inga produkt licenser har tilldelats och att det inte finns några grupp medlemskap.</span><span class="sxs-lookup"><span data-stu-id="31703-144">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="31703-145">För **kontakt information**väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="31703-145">For **Contact information**, select **Edit**.</span></span>
8. <span data-ttu-id="31703-146">Välj **kontakt information**i fönstret **Redigera kontakt information** .</span><span class="sxs-lookup"><span data-stu-id="31703-146">In the **Edit Contact information** pane, select **Contact information**.</span></span>
9. <span data-ttu-id="31703-147">I rutan **avdelning** anger du **försäljning**och väljer sedan **Spara**  >  **stängning**.</span><span class="sxs-lookup"><span data-stu-id="31703-147">In the **Department** box, enter **Sales**, and then select **Save** > **Close**.</span></span>
10. <span data-ttu-id="31703-148">Vänta några minuter och välj sedan **Uppdatera** ikonen i det övre högra hörnet i konto fönstret för användare 4.</span><span class="sxs-lookup"><span data-stu-id="31703-148">Wait a few minutes, and then periodically select the **Refresh** icon in the upper-right of the User 4 account pane.</span></span>

<span data-ttu-id="31703-149">I tid bör du se:</span><span class="sxs-lookup"><span data-stu-id="31703-149">In time, you should see the:</span></span>

- <span data-ttu-id="31703-150">**Grupp medlemskaps** egenskapen har uppdaterats med **Sälj** gruppen.</span><span class="sxs-lookup"><span data-stu-id="31703-150">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="31703-151">Egenskapen **produkt licenser** har uppdaterats med **Microsoft 365 E5** -licensen.</span><span class="sxs-lookup"><span data-stu-id="31703-151">**Product licenses** property updated with the **Microsoft 365 E5** license.</span></span>

<span data-ttu-id="31703-152">Se dessa artiklar för att distribuera dynamiskt grupp medlemskap och automatisk licensiering i produktion:</span><span class="sxs-lookup"><span data-stu-id="31703-152">See these articles to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="31703-153">Gruppbaserad licensiering i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="31703-153">Group-based licensing in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [<span data-ttu-id="31703-154">Dynamiska grupper i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="31703-154">Dynamic groups in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a><span data-ttu-id="31703-155">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="31703-155">Next step</span></span>

<span data-ttu-id="31703-156">Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="31703-156">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="31703-157">Se även</span><span class="sxs-lookup"><span data-stu-id="31703-157">See also</span></span>

[<span data-ttu-id="31703-158">Identitets översikt</span><span class="sxs-lookup"><span data-stu-id="31703-158">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="31703-159">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="31703-159">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="31703-160">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="31703-160">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="31703-161">Microsoft 365 för företags dokumentation</span><span class="sxs-lookup"><span data-stu-id="31703-161">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
