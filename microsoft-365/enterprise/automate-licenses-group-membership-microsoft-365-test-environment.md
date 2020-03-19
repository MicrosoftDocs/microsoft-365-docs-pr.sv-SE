---
title: Automatisera licensiering och gruppmedlemskap för microsoft 365 Enterprise-testmiljön
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
description: Konfigurera gruppbaserad licensiering och dynamiskt gruppmedlemskap i microsoft 365 Enterprise-testmiljön.
ms.openlocfilehash: 266ae8cb133eccf74ea75382b400ca8241782ec5
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42809331"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="ce8ba-103">Automatisera licensiering och gruppmedlemskap för microsoft 365 Enterprise-testmiljön</span><span class="sxs-lookup"><span data-stu-id="ce8ba-103">Automate licensing and group membership for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="ce8ba-104">*Den här testlabbet-guiden kan endast användas för Microsoft 365 Enterprise-testmiljöer.*</span><span class="sxs-lookup"><span data-stu-id="ce8ba-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="ce8ba-105">Gruppbaserad licensiering tilldelar eller tar automatiskt bort licenser för ett användarkonto baserat på gruppmedlemskap.</span><span class="sxs-lookup"><span data-stu-id="ce8ba-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="ce8ba-106">Dynamiskt gruppmedlemskap lägger till eller tar bort medlemmar i en grupp baserat på användarkontoegenskaper, till exempel Avdelning eller Land.</span><span class="sxs-lookup"><span data-stu-id="ce8ba-106">Dynamic group membership adds or removes members to a group based on user account properties, such as Department or Country.</span></span> <span data-ttu-id="ce8ba-107">I den här artikeln beskrivs en demonstration av båda i microsoft 365 Enterprise-testmiljön.</span><span class="sxs-lookup"><span data-stu-id="ce8ba-107">This article steps you through a demonstration of both in your Microsoft 365 Enterprise test environment.</span></span>

<span data-ttu-id="ce8ba-108">Det finns två faser för att konfigurera automatisk licensiering och dynamiskt gruppmedlemskap i microsoft 365 Enterprise-testmiljön:</span><span class="sxs-lookup"><span data-stu-id="ce8ba-108">There are two phases to setting up auto-licensing and dynamic group membership in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="ce8ba-109">Skapa testmiljön för Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="ce8ba-109">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="ce8ba-110">Konfigurera och testa dynamiskt gruppmedlemskap och automatisk licensiering.</span><span class="sxs-lookup"><span data-stu-id="ce8ba-110">Configure and test dynamic group membership and automatic licensing.</span></span>

![Testlabbguider för Microsoft-molnet](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="ce8ba-112">Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill ha en visuell karta till alla artiklar i Microsoft 365 Enterprise Test Lab Guide-stacken.</span><span class="sxs-lookup"><span data-stu-id="ce8ba-112">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="ce8ba-113">Fas 1: Bygg ut testmiljön för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ce8ba-113">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="ce8ba-114">Om du bara vill testa automatiserad licensiering och gruppmedlemskap på ett lätt väg med minimikraven följer du instruktionerna i [Lightweight base-konfigurationen](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="ce8ba-114">If you just want to test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="ce8ba-115">Om du vill testa automatiserad licensiering och gruppmedlemskap i ett simulerat företag följer du instruktionerna i [Direktautentisering](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="ce8ba-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ce8ba-116">Testning av automatiserad licensiering och gruppmedlemskap kräver inte den simulerade företagstestmiljön, som innehåller ett simulerat intranät som är anslutet till Internet och katalogsynkronisering för en AD DS-skog (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="ce8ba-116">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="ce8ba-117">Det finns här som ett alternativ så att du kan testa automatiserad licensiering och gruppmedlemskap och experimentera med det i en miljö som representerar en typisk organisation.</span><span class="sxs-lookup"><span data-stu-id="ce8ba-117">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="ce8ba-118">Fas 2: Konfigurera och testa dynamiskt gruppmedlemskap och automatisk licensiering</span><span class="sxs-lookup"><span data-stu-id="ce8ba-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="ce8ba-119">Först skapar du en ny försäljningsgrupp och lägger till en dynamisk gruppmedlemskapsregel så att användarkonton med avdelningen som försäljning läggs automatiskt till i gruppen Försäljning.</span><span class="sxs-lookup"><span data-stu-id="ce8ba-119">First, you create a new Sales group and add a dynamic group membership rule so that user accounts with the Department set to Sales are automatically added to the Sales group.</span></span>

1. <span data-ttu-id="ce8ba-120">Logga in på Office 365-portalen med det [https://portal.office.com](https://portal.office.com) globala administratörskontot för din Microsoft 365 E5-testlabbprenumeration med en privat instans av webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="ce8ba-120">Using a private instance of your Internet browser, sign in to the Office 365 portal at [https://portal.office.com](https://portal.office.com) with the global administrator account of your Microsoft 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="ce8ba-121">På en separat flik i webbläsaren går [https://portal.azure.com](https://portal.azure.com)du till Azure-portalen på .</span><span class="sxs-lookup"><span data-stu-id="ce8ba-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="ce8ba-122">Skriv **grupper** i sökrutan i Azure-portalen och klicka sedan på **Grupper**.</span><span class="sxs-lookup"><span data-stu-id="ce8ba-122">In the Azure portal, type **groups** in the search box, and then click **Groups**.</span></span>
4. <span data-ttu-id="ce8ba-123">Klicka på **Ny grupp**i fönstret **Alla grupper** .</span><span class="sxs-lookup"><span data-stu-id="ce8ba-123">in the **All groups** pane, click **New group**.</span></span>
5. <span data-ttu-id="ce8ba-124">Välj **Office 365**i **Grupptyp**.</span><span class="sxs-lookup"><span data-stu-id="ce8ba-124">In **Group type**, select **Office 365**.</span></span>
6. <span data-ttu-id="ce8ba-125">Skriv **Försäljning**i **Gruppnamn**.</span><span class="sxs-lookup"><span data-stu-id="ce8ba-125">In **Group name**, type **Sales**.</span></span>
7. <span data-ttu-id="ce8ba-126">I **medlemstyp**väljer du **Dynamisk användare**.</span><span class="sxs-lookup"><span data-stu-id="ce8ba-126">In **Membership type**, select **Dynamic user**.</span></span>
8. <span data-ttu-id="ce8ba-127">Klicka på **Dynamiska användare.**</span><span class="sxs-lookup"><span data-stu-id="ce8ba-127">Click **Dynamic user members**.</span></span>
9. <span data-ttu-id="ce8ba-128">I fönstret **Regler för dynamiskt medlemskap:**</span><span class="sxs-lookup"><span data-stu-id="ce8ba-128">In the **Dynamic membership rules** pane:</span></span> 
   - <span data-ttu-id="ce8ba-129">Välj **egenskapen avdelning.**</span><span class="sxs-lookup"><span data-stu-id="ce8ba-129">Select the **department** property.</span></span>
   - <span data-ttu-id="ce8ba-130">Välj operatorn **Lika med.**</span><span class="sxs-lookup"><span data-stu-id="ce8ba-130">Select the **Equals** operator.</span></span>
   - <span data-ttu-id="ce8ba-131">Skriv **Försäljning** i **värde**.</span><span class="sxs-lookup"><span data-stu-id="ce8ba-131">Type **Sales** in **Value**.</span></span>
10. <span data-ttu-id="ce8ba-132">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ce8ba-132">Click **Save**.</span></span>
11. <span data-ttu-id="ce8ba-133">Klicka på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="ce8ba-133">Click **Create**.</span></span>

<span data-ttu-id="ce8ba-134">Därefter konfigurerar du försäljningsgruppen så att medlemmarna tilldelas Microsoft 365 E5-licensen automatiskt.</span><span class="sxs-lookup"><span data-stu-id="ce8ba-134">Next, you configure the Sales group so that members are automatically assigned the Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="ce8ba-135">Klicka på gruppen **Försäljning** och sedan på **Licenser**.</span><span class="sxs-lookup"><span data-stu-id="ce8ba-135">Click the **Sales** group, and then click **Licenses**.</span></span>
2. <span data-ttu-id="ce8ba-136">Välj **Microsoft 365 E5**i fönstret **Uppdatera licenstilldelningar** och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ce8ba-136">In the **Update license assignments** pane, select **Microsoft 365 E5**, and then click **Save**.</span></span>
3. <span data-ttu-id="ce8ba-137">Stäng fliken Azure-portal i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="ce8ba-137">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="ce8ba-138">Därefter testar du dynamiskt gruppmedlemskap och automatisk licensiering på User 4-kontot.</span><span class="sxs-lookup"><span data-stu-id="ce8ba-138">Next, you test dynamic group membership and automatic licensing on the User 4 account.</span></span> 

1. <span data-ttu-id="ce8ba-139">Klicka på **Admin**på fliken **Start för Microsoft Office** i webbläsaren .</span><span class="sxs-lookup"><span data-stu-id="ce8ba-139">From the **Microsoft Office Home** tab in your browser, click **Admin**.</span></span>
2. <span data-ttu-id="ce8ba-140">Klicka på **Aktiva användare**på fliken Administrationscenter för **Microsoft 365** .</span><span class="sxs-lookup"><span data-stu-id="ce8ba-140">From the **Microsoft 365 admin center** tab, click **Active users**.</span></span>
3. <span data-ttu-id="ce8ba-141">Klicka på kontot Användare **4** på sidan **Aktiva användare.**</span><span class="sxs-lookup"><span data-stu-id="ce8ba-141">On the **Active users** page, click the **User 4** account.</span></span>
4. <span data-ttu-id="ce8ba-142">Klicka på **Redigera** för **produktlicenser**i fönstret **Användare 4** .</span><span class="sxs-lookup"><span data-stu-id="ce8ba-142">On the **User 4** pane, click **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="ce8ba-143">Inaktivera **Microsoft 365 E5-licensen** i fönstret **Produktlicenser** och klicka sedan på **Spara > Stäng**.</span><span class="sxs-lookup"><span data-stu-id="ce8ba-143">On the **Product licenses** pane, disable the **Microsoft 365 E5** license, and then click **Save > Close**.</span></span>
6. <span data-ttu-id="ce8ba-144">I egenskaperna för User 4-kontot kontrollerar du att inga produktlicenser har tilldelats och att det inte finns några gruppmedlemskap.</span><span class="sxs-lookup"><span data-stu-id="ce8ba-144">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="ce8ba-145">Klicka på **Redigera** för **kontaktinformation**.</span><span class="sxs-lookup"><span data-stu-id="ce8ba-145">Click **Edit** for **Contact information**.</span></span>
8. <span data-ttu-id="ce8ba-146">Klicka på Kontaktinformation i fönstret **Redigera kontaktinformation.** **Contact information**</span><span class="sxs-lookup"><span data-stu-id="ce8ba-146">In the **Edit Contact information** pane, click **Contact information**.</span></span>
9. <span data-ttu-id="ce8ba-147">Skriv **Försäljning**i fältet **Avdelning** och klicka sedan på Spara **> Stäng**.</span><span class="sxs-lookup"><span data-stu-id="ce8ba-147">In the **Department** field, type **Sales**, and then click **Save > Close**.</span></span>
10. <span data-ttu-id="ce8ba-148">Vänta några minuter och klicka sedan regelbundet på uppdateringsikonen längst upp till höger i fönstret Användare 4-konto.</span><span class="sxs-lookup"><span data-stu-id="ce8ba-148">Wait a few minutes, and then periodically click the refresh icon in the upper-right of the User 4 account pane.</span></span> 

<span data-ttu-id="ce8ba-149">Med tiden bör du se:</span><span class="sxs-lookup"><span data-stu-id="ce8ba-149">In time you should see the:</span></span>

- <span data-ttu-id="ce8ba-150">**Egenskapen Gruppmedlemskap** har uppdaterats med gruppen **Försäljning.**</span><span class="sxs-lookup"><span data-stu-id="ce8ba-150">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="ce8ba-151">**Egenskapen Product licenses** har uppdaterats med **Microsoft 365** E5-licensen.</span><span class="sxs-lookup"><span data-stu-id="ce8ba-151">**Product licenses** property updated with the **Microsoft 365 E5** license.</span></span>

<span data-ttu-id="ce8ba-152">Se de här stegen i identitetsfasen för information och länkar för att distribuera dynamiskt gruppmedlemskap och automatisk licensiering i produktion:</span><span class="sxs-lookup"><span data-stu-id="ce8ba-152">See these steps in the Identity phase for information and links to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="ce8ba-153">Konfigurera automatisk licensiering</span><span class="sxs-lookup"><span data-stu-id="ce8ba-153">Set up automatic licensing</span></span>](identity-use-group-management.md#identity-group-license)
- [<span data-ttu-id="ce8ba-154">Konfigurera dynamiskt gruppmedlemskap</span><span class="sxs-lookup"><span data-stu-id="ce8ba-154">Set up dynamic group membership</span></span>](identity-use-group-management.md#identity-dyn-groups)

## <a name="next-step"></a><span data-ttu-id="ce8ba-155">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="ce8ba-155">Next step</span></span>

<span data-ttu-id="ce8ba-156">Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) och funktioner i testmiljön.</span><span class="sxs-lookup"><span data-stu-id="ce8ba-156">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="ce8ba-157">Se även</span><span class="sxs-lookup"><span data-stu-id="ce8ba-157">See also</span></span>

[<span data-ttu-id="ce8ba-158">Fas 2: Identitet</span><span class="sxs-lookup"><span data-stu-id="ce8ba-158">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="ce8ba-159">Testlaboratorikguider för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ce8ba-159">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="ce8ba-160">Distribution av Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ce8ba-160">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="ce8ba-161">Dokumentation från Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ce8ba-161">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
