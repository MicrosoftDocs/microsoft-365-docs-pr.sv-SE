---
title: Automatisera licensiering och gruppmedlemskap för din Microsoft 365 för företagstestmiljö
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
description: Konfigurera gruppbaserad licensiering och dynamiskt gruppmedlemskap i din Microsoft 365 för företagstestmiljö.
ms.openlocfilehash: 26840e2884202a0fa9c4bb563f3d7c653482ef87
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905374"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="8cdb4-103">Automatisera licensiering och gruppmedlemskap för din Microsoft 365 för företagstestmiljö</span><span class="sxs-lookup"><span data-stu-id="8cdb4-103">Automate licensing and group membership for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="8cdb4-104">*Den här testlabbguiden kan endast användas Microsoft 365 för företagstestmiljöer.*</span><span class="sxs-lookup"><span data-stu-id="8cdb4-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="8cdb4-105">Gruppbaserad licensiering tilldelar eller tar automatiskt bort licenser för ett användarkonto baserat på gruppmedlemskap.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="8cdb4-106">Dynamiskt gruppmedlemskap lägger till eller tar bort medlemmar i en grupp baserat på egenskaper för användarkonton, t.ex. **Avdelning** eller **Land.**</span><span class="sxs-lookup"><span data-stu-id="8cdb4-106">Dynamic group membership adds or removes members to a group based on user account properties, such as **Department** or **Country**.</span></span> <span data-ttu-id="8cdb4-107">I den här artikeln får du demonstrationer av att lägga till och ta bort gruppmedlemmar i Microsoft 365 för företagstestmiljö.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-107">This article steps you through demonstrations of both adding and removing group members in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="8cdb4-108">Att konfigurera automatisk licensiering och dynamiskt gruppmedlemskap i din Microsoft 365 för företagstestmiljö omfattar två faser:</span><span class="sxs-lookup"><span data-stu-id="8cdb4-108">Setting up auto-licensing and dynamic group membership in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="8cdb4-109">Fas 1: Bygg ut din Microsoft 365 för företagstestmiljö</span><span class="sxs-lookup"><span data-stu-id="8cdb4-109">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="8cdb4-110">Fas 2: Konfigurera och testa dynamiskt gruppmedlemskap och automatisk licensiering</span><span class="sxs-lookup"><span data-stu-id="8cdb4-110">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="8cdb4-112">En visuell karta till alla artiklar i Microsoft 365 för företags testlabbguide stack finns i [Microsoft 365 för företags testlabbguide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="8cdb4-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="8cdb4-113">Fas 1: Bygg ut din Microsoft 365 för företagstestmiljö</span><span class="sxs-lookup"><span data-stu-id="8cdb4-113">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="8cdb4-114">Om du bara vill testa automatisk licensiering och gruppmedlemskap på ett lätt sätt med minimikraven följer du anvisningarna i [Lätt baskonfiguration.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="8cdb4-114">If you want to only test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="8cdb4-115">Om du vill testa automatisk licensiering och gruppmedlemskap i ett simulerat företag följer du anvisningarna i [Direktautentisering](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="8cdb4-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="8cdb4-116">Om du testar automatiserad licensiering och gruppmedlemskap krävs inte den simulerade företagstestmiljön, som omfattar en simulerad intranätansluten till Internet och katalogsynkronisering för en AD DS-skog (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="8cdb4-116">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="8cdb4-117">Här finns ett alternativ så att du kan testa automatisk licensiering och gruppmedlemskap och experimentera med det i en miljö som representerar en vanlig organisation.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-117">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="8cdb4-118">Fas 2: Konfigurera och testa dynamiskt gruppmedlemskap och automatisk licensiering</span><span class="sxs-lookup"><span data-stu-id="8cdb4-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="8cdb4-119">Skapa först en ny grupp med namnet Försäljning och lägg till  en dynamisk  regel för gruppmedlemskap så att användarkonton med Department inställt på Försäljning automatiskt ska gå med i gruppen Försäljning.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-119">First, create a new group named Sales, and add a dynamic group membership rule so that user accounts with the **Department** set to **Sales** automatically join the Sales group.</span></span>

1. <span data-ttu-id="8cdb4-120">I en privat instans av webbläsaren loggar du in på [Microsoft 365 administrationscenter](https://admin.microsoft.com) med det globala administratörskontot för Microsoft 365 E5 testlabbprenumerationen.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-120">In a private instance of your internet browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with the global administrator account of your Microsoft 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="8cdb4-121">På en separat flik i webbläsaren går du till Azure Portal på [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="8cdb4-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="8cdb4-122">I Azure Portal anger du **grupper** i sökrutan och väljer sedan **Grupper**.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-122">In the Azure portal, enter **groups** in the search box, and then select **Groups**.</span></span>
4. <span data-ttu-id="8cdb4-123">i fönstret **Alla grupper** väljer du **Ny grupp**.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-123">in the **All groups** pane, select **New group**.</span></span>
5. <span data-ttu-id="8cdb4-124">I **Grupptyp** väljer du **Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-124">In **Group type**, select **Microsoft 365**.</span></span>
6. <span data-ttu-id="8cdb4-125">Ange **Försäljning i** **Gruppnamn.**</span><span class="sxs-lookup"><span data-stu-id="8cdb4-125">In **Group name**, enter **Sales**.</span></span>
7. <span data-ttu-id="8cdb4-126">Välj **Dynamisk användare** i **Medlemskapstyp.**</span><span class="sxs-lookup"><span data-stu-id="8cdb4-126">In **Membership type**, select **Dynamic user**.</span></span>
8. <span data-ttu-id="8cdb4-127">Välj **Dynamiska användarmedlemmar.**</span><span class="sxs-lookup"><span data-stu-id="8cdb4-127">Select **Dynamic user members**.</span></span>
9. <span data-ttu-id="8cdb4-128">I fönstret **Regler för dynamiskt** medlemskap:</span><span class="sxs-lookup"><span data-stu-id="8cdb4-128">In the **Dynamic membership rules** pane:</span></span> 
   - <span data-ttu-id="8cdb4-129">Välj **avdelningsegenskapen.**</span><span class="sxs-lookup"><span data-stu-id="8cdb4-129">Select the **department** property.</span></span>
   - <span data-ttu-id="8cdb4-130">Välj **operatorn Lika med.**</span><span class="sxs-lookup"><span data-stu-id="8cdb4-130">Select the **Equals** operator.</span></span>
   - <span data-ttu-id="8cdb4-131">I rutan **Värde** anger du **Försäljning.**</span><span class="sxs-lookup"><span data-stu-id="8cdb4-131">In the **Value** box, enter **Sales**.</span></span>
10. <span data-ttu-id="8cdb4-132">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-132">Select **Save**.</span></span>
11. <span data-ttu-id="8cdb4-133">Välj **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-133">Select **Create**.</span></span>

<span data-ttu-id="8cdb4-134">Sedan konfigurerar du gruppen Försäljning så att medlemmarna automatiskt tilldelas Microsoft 365 E5 licens.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-134">Next, configure the Sales group so that members are automatically assigned the Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="8cdb4-135">Välj **gruppen** Försäljning och välj sedan **Licenser**.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-135">Select the **Sales** group, and then select **Licenses**.</span></span>
2. <span data-ttu-id="8cdb4-136">I fönstret **Uppdatera licenstilldelningar** väljer du **Microsoft 365 E5** och sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-136">In the **Update license assignments** pane, select **Microsoft 365 E5**, and then select **Save**.</span></span>
3. <span data-ttu-id="8cdb4-137">Stäng fliken Azure Portal i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-137">In your browser, close the Azure portal tab.</span></span>

<span data-ttu-id="8cdb4-138">Testa sedan dynamiskt gruppmedlemskap och automatisk licensiering på User 4-kontot:</span><span class="sxs-lookup"><span data-stu-id="8cdb4-138">Next, test dynamic group membership and automatic licensing on the User 4 account:</span></span>

1. <span data-ttu-id="8cdb4-139">På **Microsoft Office Start** i webbläsaren väljer du **Admin**.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-139">From the **Microsoft Office Home** tab in your browser, select **Admin**.</span></span>
2. <span data-ttu-id="8cdb4-140">På Microsoft 365 **i administrationscentret** väljer du **Aktiva användare.**</span><span class="sxs-lookup"><span data-stu-id="8cdb4-140">From the **Microsoft 365 admin center** tab, select **Active users**.</span></span>
3. <span data-ttu-id="8cdb4-141">Välj **Användare** **4-kontot** på sidan Aktiva användare.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-141">On the **Active users** page, select the **User 4** account.</span></span>
4. <span data-ttu-id="8cdb4-142">I fönstret **Användare 4** väljer du **Redigera** för **produktlicenser.**</span><span class="sxs-lookup"><span data-stu-id="8cdb4-142">On the **User 4** pane, select **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="8cdb4-143">I fönstret **Produktlicenser** inaktiverar du **Microsoft 365 E5** licens och väljer sedan **Spara**  >  **stäng.**</span><span class="sxs-lookup"><span data-stu-id="8cdb4-143">On the **Product licenses** pane, disable the **Microsoft 365 E5** license, and then select **Save** > **Close**.</span></span>
6. <span data-ttu-id="8cdb4-144">I egenskaperna för Användarkontot 4 kontrollerar du att inga produktlicenser har tilldelats och att det inte finns några gruppmedlemskap.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-144">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="8cdb4-145">För **Kontaktinformation** väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-145">For **Contact information**, select **Edit**.</span></span>
8. <span data-ttu-id="8cdb4-146">Välj **Kontaktinformation i** fönstret Redigera **kontaktinformation.**</span><span class="sxs-lookup"><span data-stu-id="8cdb4-146">In the **Edit Contact information** pane, select **Contact information**.</span></span>
9. <span data-ttu-id="8cdb4-147">I rutan **Avdelning** anger du **Försäljning** och väljer sedan **Spara**  >  **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="8cdb4-147">In the **Department** box, enter **Sales**, and then select **Save** > **Close**.</span></span>
10. <span data-ttu-id="8cdb4-148">Vänta några minuter och välj sedan regelbundet ikonen **Uppdatera** i det övre högra hörnet av fönstret Användare 4-konto.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-148">Wait a few minutes, and then periodically select the **Refresh** icon in the upper-right of the User 4 account pane.</span></span>

<span data-ttu-id="8cdb4-149">Med tiden bör du se:</span><span class="sxs-lookup"><span data-stu-id="8cdb4-149">In time, you should see the:</span></span>

- <span data-ttu-id="8cdb4-150">**Egenskapen Gruppmedlemskap** uppdaterad med **gruppen** Försäljning.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-150">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="8cdb4-151">**Produktlicensegenskap** som **uppdaterats Microsoft 365 E5** licens.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-151">**Product licenses** property updated with the **Microsoft 365 E5** license.</span></span>

<span data-ttu-id="8cdb4-152">Läs följande artiklar om hur du distribuerar dynamiskt gruppmedlemskap och automatisk licensiering i produktionen:</span><span class="sxs-lookup"><span data-stu-id="8cdb4-152">See these articles to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="8cdb4-153">Gruppbaserad licensiering i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="8cdb4-153">Group-based licensing in Azure Active Directory</span></span>](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [<span data-ttu-id="8cdb4-154">Dynamiska grupper i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="8cdb4-154">Dynamic groups in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a><span data-ttu-id="8cdb4-155">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="8cdb4-155">Next step</span></span>

<span data-ttu-id="8cdb4-156">Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="8cdb4-156">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="8cdb4-157">Se även</span><span class="sxs-lookup"><span data-stu-id="8cdb4-157">See also</span></span>

[<span data-ttu-id="8cdb4-158">Identitetsöversikt</span><span class="sxs-lookup"><span data-stu-id="8cdb4-158">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="8cdb4-159">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="8cdb4-159">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="8cdb4-160">Översikt över Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="8cdb4-160">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="8cdb4-161">Dokumentation om Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="8cdb4-161">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)