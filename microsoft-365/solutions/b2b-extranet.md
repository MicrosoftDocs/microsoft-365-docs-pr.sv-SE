---
title: Skapa ett B2B-extranät med hanterade gäster
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom: ''
localization_priority: Normal
f1.keywords: NOCSH
description: Lär dig hur du skapar en B2B-extranätwebbplats eller ett B2B-team med hanterade gäster från en partnerorganisation.
ms.openlocfilehash: f9b8d9326f302233ed85c9d168fdf6f343dc6cbf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904762"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a><span data-ttu-id="24b6b-103">Skapa ett B2B-extranät med hanterade gäster</span><span class="sxs-lookup"><span data-stu-id="24b6b-103">Create a B2B extranet with managed guests</span></span>

<span data-ttu-id="24b6b-104">Du kan använda [Azure Active Directory berättigandeshantering](/azure/active-directory/governance/entitlement-management-overview) för att skapa ett B2B-extranät för att samarbeta med en partnerorganisation som använder Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="24b6b-104">You can use [Azure Active Directory Entitlement Management](/azure/active-directory/governance/entitlement-management-overview) to create a B2B extranet to collaborate with a partner organization that uses Azure Active Directory.</span></span> <span data-ttu-id="24b6b-105">På så sätt kan användarna registrera sig själva på extranätwebbplatsen eller i teamet och få åtkomst via ett arbetsflöde för godkännande.</span><span class="sxs-lookup"><span data-stu-id="24b6b-105">This allows users to self-enroll in the extranet site or team and receive access via an approval workflow.</span></span>

<span data-ttu-id="24b6b-106">Med den här metoden för att dela resurser för samarbete kan partnerorganisationen hjälpa till att underhålla och godkänna gästerna på slutet, vilket minskar IT-avdelningens belastning och gör att de som känner till samarbetsavtalet kan hantera användaråtkomst.</span><span class="sxs-lookup"><span data-stu-id="24b6b-106">With this method of sharing resources for collaboration, the partner organization can help maintain and approve the guests on their end, reducing the burden on your IT department and allowing those most familiar with the collaboration agreement to manage user access.</span></span>

<span data-ttu-id="24b6b-107">Den här artikeln går igenom stegen för att skapa ett resurspaket (i det här fallet en webbplats eller ett team) som du kan dela med en partnerorganisation via en självbetjäning för åtkomstregistrering.</span><span class="sxs-lookup"><span data-stu-id="24b6b-107">This article walks through the steps to create a package of resources (in this case, a site or team) that you can share with a partner organization through a self-service access registration model.</span></span> 

<span data-ttu-id="24b6b-108">Innan du börjar skapar du den webbplats eller det team som du vill dela med partnerorganisationen och aktiverar den för gästdelning.</span><span class="sxs-lookup"><span data-stu-id="24b6b-108">Before you begin, create the site or team that you want to share with the partner organization and enable it for guest sharing.</span></span> <span data-ttu-id="24b6b-109">Mer information [finns i Samarbeta med gäster](collaborate-in-site.md) på en webbplats eller Samarbeta med [gäster](collaborate-as-team.md) i ett team.</span><span class="sxs-lookup"><span data-stu-id="24b6b-109">See [Collaborate with guests in a site](collaborate-in-site.md) or [Collaborate with guests in a team](collaborate-as-team.md) for more information.</span></span> <span data-ttu-id="24b6b-110">Vi rekommenderar även [](create-secure-guest-sharing-environment.md) att du går igenom Skapa en säker gästdelningsmiljö för information om säkerhets- och efterlevnadsfunktioner som du kan använda för att bevara dina styrningsprinciper när du samarbetar med gäster.</span><span class="sxs-lookup"><span data-stu-id="24b6b-110">We also recommend that you review [Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) for information about security and compliance features that you can use to help maintain your governance policies when collaborating with guests.</span></span>

## <a name="license-requirements"></a><span data-ttu-id="24b6b-111">Licenskrav</span><span class="sxs-lookup"><span data-stu-id="24b6b-111">License requirements</span></span>

<span data-ttu-id="24b6b-112">Om du använder den här funktionen krävs en Azure AD Premium P2-licens.</span><span class="sxs-lookup"><span data-stu-id="24b6b-112">Using this feature requires an Azure AD Premium P2 license.</span></span> 

<span data-ttu-id="24b6b-113">Specialiserade moln, till exempel Azure Germany och Azure China 21Vianet, är för närvarande inte tillgängliga för användning.</span><span class="sxs-lookup"><span data-stu-id="24b6b-113">Specialized clouds, such as Azure Germany and Azure China 21Vianet, are not currently available for use.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="24b6b-114">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="24b6b-114">Video demonstration</span></span>

<span data-ttu-id="24b6b-115">Den här videon visar hur man går till i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="24b6b-115">This video demonstrates the procedures covered in this article.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a><span data-ttu-id="24b6b-116">Anslut partnerorganisationen</span><span class="sxs-lookup"><span data-stu-id="24b6b-116">Connect the partner organization</span></span>

<span data-ttu-id="24b6b-117">Om du vill bjuda in gäster från en partnerorganisation måste du lägga till partnerdomänen som en ansluten organisation i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="24b6b-117">In order to invite guests from a partner organization, you need to add the partner's domain as a connected organization in Azure Active Directory.</span></span>

<span data-ttu-id="24b6b-118">Så här lägger du till en ansluten organisation</span><span class="sxs-lookup"><span data-stu-id="24b6b-118">To add a connected organization</span></span>
1. <span data-ttu-id="24b6b-119">Klicka [på Identitetsstyrning](https://aad.portal.azure.com)i Azure Active **Directory.**</span><span class="sxs-lookup"><span data-stu-id="24b6b-119">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="24b6b-120">Klicka **på Anslutna organisationer.**</span><span class="sxs-lookup"><span data-stu-id="24b6b-120">Click **Connected organizations**.</span></span>
4. <span data-ttu-id="24b6b-121">Klicka **på Lägg till ansluten organisation.**</span><span class="sxs-lookup"><span data-stu-id="24b6b-121">Click **Add connected organization**.</span></span>
5. <span data-ttu-id="24b6b-122">Skriv ett namn och en beskrivning för organisationen och klicka sedan på **Nästa: Katalog + domän.**</span><span class="sxs-lookup"><span data-stu-id="24b6b-122">Type a name and description for the organization, and then click **Next: Directory + domain**.</span></span>
6. <span data-ttu-id="24b6b-123">Klicka **på Lägg till katalog + domän.**</span><span class="sxs-lookup"><span data-stu-id="24b6b-123">Click **Add directory + domain**.</span></span>
7. <span data-ttu-id="24b6b-124">Ange domänen för den organisation som du vill ansluta till och klicka sedan på Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="24b6b-124">Type the domain for the organization that you want to connect, and then click **Add**.</span></span>
8. <span data-ttu-id="24b6b-125">Klicka **på Anslut** och sedan på **Nästa: Sponsorer.**</span><span class="sxs-lookup"><span data-stu-id="24b6b-125">Click **Connect**, and then click **Next: Sponsors**.</span></span>
9. <span data-ttu-id="24b6b-126">Lägg till personer från organisationen eller organisationen som du ansluter till som du vill godkänna åtkomst för gäster.</span><span class="sxs-lookup"><span data-stu-id="24b6b-126">Add people from your organization or the organization that you're connecting to who you want to approve access for guests.</span></span>
10. <span data-ttu-id="24b6b-127">Klicka **Nästa: Granska + Skapa**.</span><span class="sxs-lookup"><span data-stu-id="24b6b-127">Click **Next: Review + Create**.</span></span>
11. <span data-ttu-id="24b6b-128">Granska de inställningar som du har valt och klicka sedan på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="24b6b-128">Review the settings that you've chosen and then click **Create**.</span></span>

    ![Skärmbild av sidan anslutna organisationer i Azure Active Directory](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a><span data-ttu-id="24b6b-130">Välj resurser att dela</span><span class="sxs-lookup"><span data-stu-id="24b6b-130">Choose the resources to share</span></span>

<span data-ttu-id="24b6b-131">Det första steget när du väljer resurser att dela med en partnerorganisation är att skapa en katalog för att innehålla dem.</span><span class="sxs-lookup"><span data-stu-id="24b6b-131">The first step in selecting resources to share with a partner organization is to create a catalog to contain them.</span></span>

<span data-ttu-id="24b6b-132">Så här skapar du en katalog</span><span class="sxs-lookup"><span data-stu-id="24b6b-132">To create a catalog</span></span>
1. <span data-ttu-id="24b6b-133">Klicka [på Identitetsstyrning](https://aad.portal.azure.com)i Azure Active **Directory.**</span><span class="sxs-lookup"><span data-stu-id="24b6b-133">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="24b6b-134">Klicka **på Kataloger.**</span><span class="sxs-lookup"><span data-stu-id="24b6b-134">Click **Catalogs**.</span></span>
3. <span data-ttu-id="24b6b-135">Klicka **på Ny katalog**.</span><span class="sxs-lookup"><span data-stu-id="24b6b-135">Click **New catalog**.</span></span>
4. <span data-ttu-id="24b6b-136">Ange ett namn och en beskrivning för katalogen och kontrollera att **Både Aktiverad** och Aktiverad för **externa användare** är inställda på **Ja.**</span><span class="sxs-lookup"><span data-stu-id="24b6b-136">Type a name and description for the catalog and ensure that **Enabled** and **Enabled for external users** are both set to **Yes**.</span></span>
5. <span data-ttu-id="24b6b-137">Klicka på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="24b6b-137">Click **Create**.</span></span>

   ![Skärmbild av katalogsidan i Azure Active Directory-identitetsstyrning](../media/identity-governance-catalogs.png)

<span data-ttu-id="24b6b-139">När katalogen har skapats lägger du till den SharePoint-webbplats eller det team som du vill dela med partnerorganisationen.</span><span class="sxs-lookup"><span data-stu-id="24b6b-139">Once the catalog has been created, you add the SharePoint site or team that you want to share with the partner organization.</span></span>

<span data-ttu-id="24b6b-140">Lägga till resurser i en katalog</span><span class="sxs-lookup"><span data-stu-id="24b6b-140">To add resources to a catalog</span></span>
1. <span data-ttu-id="24b6b-141">I Azure AD-identitetsstyrning **klickar du på Kataloger** och sedan på den katalog där du vill lägga till resurser.</span><span class="sxs-lookup"><span data-stu-id="24b6b-141">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to add resources.</span></span>
2. <span data-ttu-id="24b6b-142">Klicka **på Resurser** och sedan på Lägg till **resurser.**</span><span class="sxs-lookup"><span data-stu-id="24b6b-142">Click **Resources** and then click **Add resources**.</span></span>
3. <span data-ttu-id="24b6b-143">Välj de team eller SharePoint-webbplatser som du vill inkludera i extranätet och klicka sedan på Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="24b6b-143">Select the teams or SharePoint sites that you want to include in your extranet, and then click **Add**.</span></span>

   ![Skärmbild av sidan Katalogresurser i Azure Active Directory-identitetsstyrning](../media/identity-governance-catalog-resource.png)

<span data-ttu-id="24b6b-145">När du har definierat vilka resurser du vill dela är nästa steg att skapa ett åtkomstpaket, som definierar vilken typ av åtkomst som partneranvändare beviljas och godkännandeprocessen för nya partneranvändare som begär åtkomst.</span><span class="sxs-lookup"><span data-stu-id="24b6b-145">Once you've defined the resources that you want to share, the next step is to create an access package, which defines the type of access that partner users are granted and the approval process for new partner users requesting access.</span></span>

<span data-ttu-id="24b6b-146">Skapa ett åtkomstpaket</span><span class="sxs-lookup"><span data-stu-id="24b6b-146">To create an access package</span></span>
1. <span data-ttu-id="24b6b-147">I Azure AD-identitetsstyrning **klickar du på Kataloger** och sedan på den katalog där du vill skapa ett åtkomstpaket.</span><span class="sxs-lookup"><span data-stu-id="24b6b-147">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to create an access package.</span></span>
2. <span data-ttu-id="24b6b-148">Klicka **på Access-paket** och klicka sedan på **Nytt åtkomstpaket**.</span><span class="sxs-lookup"><span data-stu-id="24b6b-148">Click **Access packages**, and then click **New access package**.</span></span>
3. <span data-ttu-id="24b6b-149">Skriv ett namn och en beskrivning för åtkomstpaketet och klicka sedan på **Nästa: Resursroller**.</span><span class="sxs-lookup"><span data-stu-id="24b6b-149">Type a name and description for the access package, and then click **Next: Resource roles**.</span></span>
4. <span data-ttu-id="24b6b-150">Välj resurserna i katalogen som du vill använda för extranätet.</span><span class="sxs-lookup"><span data-stu-id="24b6b-150">Choose the resources from the catalog that you want to use for your extranet.</span></span>
5. <span data-ttu-id="24b6b-151">För varje resurs, i **kolumnen** Roll, väljer du den användarroll som du vill tilldela till gästerna som använder extranätet.</span><span class="sxs-lookup"><span data-stu-id="24b6b-151">For each resource, in the **Role** column, choose the user role you want to grant to the guests who use the extranet.</span></span>
6. <span data-ttu-id="24b6b-152">Klicka **på Nästa: Begäranden**.</span><span class="sxs-lookup"><span data-stu-id="24b6b-152">Click **Next: Requests**.</span></span>
7. <span data-ttu-id="24b6b-153">Under **Användare som kan begära åtkomst** väljer du För användare som inte finns i **katalogen.**</span><span class="sxs-lookup"><span data-stu-id="24b6b-153">Under **Users who can request access**, choose **For users not in your directory**.</span></span>
8. <span data-ttu-id="24b6b-154">Kontrollera att alternativet **Specifika anslutna organisationer** är markerat och klicka sedan på Lägg till **kataloger.**</span><span class="sxs-lookup"><span data-stu-id="24b6b-154">Ensure that the **Specific connected organizations** option is selected, and then click **Add directories**.</span></span>
9. <span data-ttu-id="24b6b-155">Välj den anslutna organisationen du lägger till tidigare och klicka sedan på **Välj**</span><span class="sxs-lookup"><span data-stu-id="24b6b-155">Choose the connected organization that you add earlier, and then click **Select**</span></span>
10. <span data-ttu-id="24b6b-156">Under **Godkännande** väljer du **Ja för** **Kräv godkännande.**</span><span class="sxs-lookup"><span data-stu-id="24b6b-156">Under **Approval**, choose **Yes** for **Require approval**.</span></span>
11. <span data-ttu-id="24b6b-157">Under **Förste godkännare** väljer du en av de huvudsponsorer som du lagt till tidigare eller väljer en viss användare.</span><span class="sxs-lookup"><span data-stu-id="24b6b-157">Under **First approver**, choose one of the sponsors that you added earlier or choose a specific user.</span></span>
12. <span data-ttu-id="24b6b-158">Klicka **på Lägg till reserv** och välj en reserv godkännare.</span><span class="sxs-lookup"><span data-stu-id="24b6b-158">Click **Add fallback** and select a fallback approver.</span></span>
13. <span data-ttu-id="24b6b-159">Välj **Ja** under **Aktivera.**</span><span class="sxs-lookup"><span data-stu-id="24b6b-159">Under **Enable**, choose **Yes**.</span></span>
14. <span data-ttu-id="24b6b-160">Klicka **på Nästa: Livscykel.**</span><span class="sxs-lookup"><span data-stu-id="24b6b-160">Click **Next: Lifecycle**.</span></span>
15. <span data-ttu-id="24b6b-161">Välj inställningar för förfallotid och åtkomstgranskning som du vill använda och klicka sedan på **Nästa: Granska + Skapa.**</span><span class="sxs-lookup"><span data-stu-id="24b6b-161">Choose the expiration and access review settings that you want to use, and then click **Next: Review + Create**.</span></span>
16. <span data-ttu-id="24b6b-162">Granska inställningarna och klicka sedan på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="24b6b-162">Review your settings, and then click **Create**.</span></span>

    ![Skärmbild av skärmen åtkomstpaket i Azure Active Directory-identitetsstyrning](../media/identity-governance-access-packages.png)

<span data-ttu-id="24b6b-164">Om du samarbetar med en stor organisation kanske du vill dölja åtkomstpaketet.</span><span class="sxs-lookup"><span data-stu-id="24b6b-164">If you're partnering with a large organization, you may want to hide the access package.</span></span> <span data-ttu-id="24b6b-165">Om paketet är dolt kommer användare i partnerorganisationen inte att se paketet på Min *Access-portalen.*</span><span class="sxs-lookup"><span data-stu-id="24b6b-165">If the package is hidden, then users in the partner organization will not see the package on their *My Access* portal.</span></span> <span data-ttu-id="24b6b-166">I stället måste de skickas en direktlänk för att registrera sig för paketet.</span><span class="sxs-lookup"><span data-stu-id="24b6b-166">Instead, they must be sent a direct link to sign up for the package.</span></span> <span data-ttu-id="24b6b-167">Genom att dölja åtkomstpaketet kan du minska antalet olämpliga åtkomstförfrågningar och även hålla tillgängliga åtkomstpaket organiserade i partnerorganisationens portal.</span><span class="sxs-lookup"><span data-stu-id="24b6b-167">Hiding the access package can reduce the number of inappropriate access requests and can also help keep available access packages organized in the partner organization's portal.</span></span>

<span data-ttu-id="24b6b-168">Så här anger du att ett åtkomstpaket ska vara dolt</span><span class="sxs-lookup"><span data-stu-id="24b6b-168">To set an access package to hidden</span></span>
1. <span data-ttu-id="24b6b-169">I Azure AD Identity Governance klickar du **på Access-paket** och sedan på ditt åtkomstpaket.</span><span class="sxs-lookup"><span data-stu-id="24b6b-169">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="24b6b-170">Klicka på **Redigera** på sidan **Översikt.**</span><span class="sxs-lookup"><span data-stu-id="24b6b-170">On the **Overview** page, click **Edit**.</span></span>
3. <span data-ttu-id="24b6b-171">Under **Egenskaper** väljer du **Ja** för **Dolda** och klickar sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="24b6b-171">Under **Properties**, choose **Yes** for **Hidden**, and then click **Save**.</span></span>

   ![Skärmbild av skärmen med egenskaper för redigering av åtkomstpaket](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a><span data-ttu-id="24b6b-173">Bjud in partneranvändare</span><span class="sxs-lookup"><span data-stu-id="24b6b-173">Invite partner users</span></span>

<span data-ttu-id="24b6b-174">Om du ställer in åtkomstpaketet på dolt måste du skicka en direktlänk till partnerorganisationen så att de kan begära åtkomst till din webbplats eller ditt team.</span><span class="sxs-lookup"><span data-stu-id="24b6b-174">If you set the access package to hidden, you need to send a direct link to the partner organization so that they can request access to your site or team.</span></span>

<span data-ttu-id="24b6b-175">Så här hittar du länken till åtkomstportalen</span><span class="sxs-lookup"><span data-stu-id="24b6b-175">To find the access portal link</span></span>
1. <span data-ttu-id="24b6b-176">I Azure AD Identity Governance klickar du **på Access-paket** och sedan på ditt åtkomstpaket.</span><span class="sxs-lookup"><span data-stu-id="24b6b-176">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="24b6b-177">På sidan **Översikt** klickar du på **Kopiera till Urklipp-länken** för länken **Min Access-portal.**</span><span class="sxs-lookup"><span data-stu-id="24b6b-177">On the **Overview** page, click **Copy to clipboard** link for the **My Access portal link**.</span></span>

   ![Skärmbild av egenskaper för åtkomstpaket med länken till åtkomstportalen](../media/identity-governance-access-portal-link.png)

<span data-ttu-id="24b6b-179">När du har kopierat länken kan du dela den med din kontakt på partnerorganisationen och de kan skicka den till användarna i deras samarbetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="24b6b-179">Once you have copied the link, you can share it with your contact at the partner organization and they can send it to the users on their collaboration team.</span></span>

## <a name="see-also"></a><span data-ttu-id="24b6b-180">Se även</span><span class="sxs-lookup"><span data-stu-id="24b6b-180">See Also</span></span>

[<span data-ttu-id="24b6b-181">Skapa en säker miljö för gästdelning</span><span class="sxs-lookup"><span data-stu-id="24b6b-181">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)