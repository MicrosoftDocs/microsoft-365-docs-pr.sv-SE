---
title: Skapa ett B2B-extranät med hanterade gäster
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom: ''
localization_priority: Normal
f1.keywords: NOCSH
description: Lär dig hur du skapar en B2B extranätwebbplats eller team med hanterade gästanvändare från en partnerorganisation.
ms.openlocfilehash: 4f8eb33ad9b41f552975d4158a61ec4cedcfa9cc
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46526988"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a><span data-ttu-id="68492-103">Skapa ett B2B-extranät med hanterade gäster</span><span class="sxs-lookup"><span data-stu-id="68492-103">Create a B2B extranet with managed guests</span></span>

<span data-ttu-id="68492-104">Du kan använda [Azure Active Directory Entitlement Management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) för att skapa ett B2B-extranät för att samarbeta med en partnerorganisation som använder Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="68492-104">You can use [Azure Active Directory Entitlement Management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) to create a B2B extranet to collaborate with a partner organization that uses Azure Active Directory.</span></span> <span data-ttu-id="68492-105">Detta gör det möjligt för användare att själv registrera sig på extranätswebbplatsen eller teamet och få åtkomst via ett arbetsflöde för godkännande.</span><span class="sxs-lookup"><span data-stu-id="68492-105">This allows users to self-enroll in the extranet site or team and receive access via an approval workflow.</span></span>

<span data-ttu-id="68492-106">Med den här metoden för att dela resurser för samarbete kan partnerorganisationen hjälpa till att underhålla och godkänna gästanvändarna på slutet, vilket minskar belastningen på IT-avdelningen och gör det möjligt för de mest bekanta med samarbetsavtalet att hantera användaråtkomst.</span><span class="sxs-lookup"><span data-stu-id="68492-106">With this method of sharing resources for collaboration, the partner organization can help maintain and approve the guest users on their end, reducing the burden on your IT department and allowing those most familiar with the collaboration agreement to manage user access.</span></span>

<span data-ttu-id="68492-107">Den här artikeln går igenom stegen för att skapa ett paket med resurser (i det här fallet en webbplats eller ett team) som du kan dela med en partnerorganisation via en självbetjäningsregistreringsmodell.</span><span class="sxs-lookup"><span data-stu-id="68492-107">This article walks through the steps to create a package of resources (in this case, a site or team) that you can share with a partner organization through a self-service access registration model.</span></span> 

<span data-ttu-id="68492-108">Innan du börjar skapar du den webbplats eller det team som du vill dela med partnerorganisationen och aktiverar den för gästdelning.</span><span class="sxs-lookup"><span data-stu-id="68492-108">Before you begin, create the site or team that you want to share with the partner organization and enable it for guest sharing.</span></span> <span data-ttu-id="68492-109">Mer information [finns i Samarbeta med gäster](collaborate-in-site.md) på en webbplats eller Samarbeta med gäster i ett [team.](collaborate-as-team.md)</span><span class="sxs-lookup"><span data-stu-id="68492-109">See [Collaborate with guests in a site](collaborate-in-site.md) or [Collaborate with guests in a team](collaborate-as-team.md) for more information.</span></span> <span data-ttu-id="68492-110">Vi rekommenderar också att du granskar [Skapa en säker gästdelningsmiljö](create-secure-guest-sharing-environment.md) för information om säkerhets- och efterlevnadsfunktioner som du kan använda för att underhålla dina styrningsprinciper när du samarbetar med gäster.</span><span class="sxs-lookup"><span data-stu-id="68492-110">We also recommend that you review [Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) for information about security and compliance features that you can use to help maintain your governance policies when collaborating with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="68492-111">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="68492-111">Video demonstration</span></span>

<span data-ttu-id="68492-112">Den här videon visar de procedurer som beskrivs i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="68492-112">This video demonstrates the procedures covered in this article.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a><span data-ttu-id="68492-113">Anslut partnerorganisationen</span><span class="sxs-lookup"><span data-stu-id="68492-113">Connect the partner organization</span></span>

<span data-ttu-id="68492-114">För att kunna bjuda in gäster från en partnerorganisation måste du lägga till partnerns domän som en ansluten organisation i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="68492-114">In order to invite guests from a partner organization, you need to add the partner's domain as a connected organization in Azure Active Directory.</span></span>

<span data-ttu-id="68492-115">Så här lägger du till en ansluten organisation</span><span class="sxs-lookup"><span data-stu-id="68492-115">To add a connected organization</span></span>
1. <span data-ttu-id="68492-116">Klicka på **Identitetsstyrning**i [Azure Active Directory](https://aad.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="68492-116">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="68492-117">Klicka på **Anslutna organisationer**.</span><span class="sxs-lookup"><span data-stu-id="68492-117">Click **Connected organizations**.</span></span>
4. <span data-ttu-id="68492-118">Klicka på **Lägg till ansluten organisation**.</span><span class="sxs-lookup"><span data-stu-id="68492-118">Click **Add connected organization**.</span></span>
5. <span data-ttu-id="68492-119">Skriv ett namn och en beskrivning för organisationen och klicka sedan på **Nästa: Katalog + domän**.</span><span class="sxs-lookup"><span data-stu-id="68492-119">Type a name and description for the organization, and then click **Next: Directory + domain**.</span></span>
6. <span data-ttu-id="68492-120">Klicka på **Lägg till katalog + domän**.</span><span class="sxs-lookup"><span data-stu-id="68492-120">Click **Add directory + domain**.</span></span>
7. <span data-ttu-id="68492-121">Skriv domänen för den organisation som du vill ansluta och klicka sedan på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="68492-121">Type the domain for the organization that you want to connect, and then click **Add**.</span></span>
8. <span data-ttu-id="68492-122">Klicka på **Anslut**och sedan på **Nästa: Sponsorer.**</span><span class="sxs-lookup"><span data-stu-id="68492-122">Click **Connect**, and then click **Next: Sponsors**.</span></span>
9. <span data-ttu-id="68492-123">Lägg till personer från din organisation eller organisationen som du ansluter till och som du vill godkänna åtkomst för gästanvändare.</span><span class="sxs-lookup"><span data-stu-id="68492-123">Add people from your organization or the organization that you're connecting to who you want to approve access for guest users.</span></span>
10. <span data-ttu-id="68492-124">Klicka på **Nästa: Granska + Skapa**.</span><span class="sxs-lookup"><span data-stu-id="68492-124">Click **Next: Review + Create**.</span></span>
11. <span data-ttu-id="68492-125">Granska de inställningar som du har valt och klicka sedan på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="68492-125">Review the settings that you've chosen and then click **Create**.</span></span>

    ![Skärmbild av sidan anslutna organisationer i Azure Active Directory](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a><span data-ttu-id="68492-127">Välj de resurser som ska delas</span><span class="sxs-lookup"><span data-stu-id="68492-127">Choose the resources to share</span></span>

<span data-ttu-id="68492-128">Det första steget i att välja resurser att dela med en partnerorganisation är att skapa en katalog som innehåller dem.</span><span class="sxs-lookup"><span data-stu-id="68492-128">The first step in selecting resources to share with a partner organization is to create a catalog to contain them.</span></span>

<span data-ttu-id="68492-129">Så här skapar du en katalog</span><span class="sxs-lookup"><span data-stu-id="68492-129">To create a catalog</span></span>
1. <span data-ttu-id="68492-130">Klicka på **Identitetsstyrning**i [Azure Active Directory](https://aad.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="68492-130">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="68492-131">Klicka på **Kataloger**.</span><span class="sxs-lookup"><span data-stu-id="68492-131">Click **Catalogs**.</span></span>
3. <span data-ttu-id="68492-132">Klicka på **Ny katalog**.</span><span class="sxs-lookup"><span data-stu-id="68492-132">Click **New catalog**.</span></span>
4. <span data-ttu-id="68492-133">Skriv ett namn och en beskrivning för katalogen och se till att **Aktiverade** och **Aktiverade för externa användare** båda är inställda på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="68492-133">Type a name and description for the catalog and ensure that **Enabled** and **Enabled for external users** are both set to **Yes**.</span></span>
5. <span data-ttu-id="68492-134">Klicka på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="68492-134">Click **Create**.</span></span>

   ![Skärmbild av katalogsidan i Azure Active Directory Identity Governance](../media/identity-governance-catalogs.png)

<span data-ttu-id="68492-136">När katalogen har skapats lägger du till den SharePoint-webbplats eller det SharePoint-team som du vill dela med partnerorganisationen.</span><span class="sxs-lookup"><span data-stu-id="68492-136">Once the catalog has been created, you add the SharePoint site or team that you want to share with the partner organization.</span></span>

<span data-ttu-id="68492-137">Så här lägger du till resurser i en katalog</span><span class="sxs-lookup"><span data-stu-id="68492-137">To add resources to a catalog</span></span>
1. <span data-ttu-id="68492-138">I Azure AD Identity Governance klickar du på **Kataloger**och sedan på den katalog där du vill lägga till resurser.</span><span class="sxs-lookup"><span data-stu-id="68492-138">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to add resources.</span></span>
2. <span data-ttu-id="68492-139">Klicka på **Resurser** och sedan på **Lägg till resurser**.</span><span class="sxs-lookup"><span data-stu-id="68492-139">Click **Resources** and then click **Add resources**.</span></span>
3. <span data-ttu-id="68492-140">Markera de team eller SharePoint-webbplatser som du vill inkludera i extranätet och klicka sedan på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="68492-140">Select the teams or SharePoint sites that you want to include in your extranet, and then click **Add**.</span></span>

   ![Skärmbild av sidan katalogresurser i Azure Active Directory Identity Governance](../media/identity-governance-catalog-resource.png)

<span data-ttu-id="68492-142">När du har definierat de resurser som du vill dela är nästa steg att skapa ett åtkomstpaket som definierar vilken typ av åtkomst som partneranvändare beviljas och godkännandeprocessen för nya partneranvändare som begär åtkomst.</span><span class="sxs-lookup"><span data-stu-id="68492-142">Once you've defined the resources that you want to share, the next step is to create an access package, which defines the type of access that partner users are granted and the approval process for new partner users requesting access.</span></span>

<span data-ttu-id="68492-143">Så här skapar du ett åtkomstpaket</span><span class="sxs-lookup"><span data-stu-id="68492-143">To create an access package</span></span>
1. <span data-ttu-id="68492-144">I Azure AD Identity Governance klickar du på **Kataloger**och sedan på den katalog där du vill skapa ett åtkomstpaket.</span><span class="sxs-lookup"><span data-stu-id="68492-144">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to create an access package.</span></span>
2. <span data-ttu-id="68492-145">Klicka på **Access-paket**och sedan på **Nytt åtkomstpaket**.</span><span class="sxs-lookup"><span data-stu-id="68492-145">Click **Access packages**, and then click **New access package**.</span></span>
3. <span data-ttu-id="68492-146">Skriv ett namn och en beskrivning för åtkomstpaketet och klicka sedan på **Nästa: Resursroller**.</span><span class="sxs-lookup"><span data-stu-id="68492-146">Type a name and description for the access package, and then click **Next: Resource roles**.</span></span>
4. <span data-ttu-id="68492-147">Välj de resurser från katalogen som du vill använda för extranätet.</span><span class="sxs-lookup"><span data-stu-id="68492-147">Choose the resources from the catalog that you want to use for your extranet.</span></span>
5. <span data-ttu-id="68492-148">För varje resurs väljer du den användarroll som du vill bevilja gästanvändare som använder extranätet i kolumnen **Roll.**</span><span class="sxs-lookup"><span data-stu-id="68492-148">For each resource, in the **Role** column, choose the user role you want to grant to the guest users who use the extranet.</span></span>
6. <span data-ttu-id="68492-149">Klicka på **Nästa: Förfrågningar**.</span><span class="sxs-lookup"><span data-stu-id="68492-149">Click **Next: Requests**.</span></span>
7. <span data-ttu-id="68492-150">Under **Användare som kan begära åtkomst**väljer du För användare som inte finns i **katalogen**.</span><span class="sxs-lookup"><span data-stu-id="68492-150">Under **Users who can request access**, choose **For users not in your directory**.</span></span>
8. <span data-ttu-id="68492-151">Kontrollera att alternativet **Specifika anslutna organisationer** är markerat och klicka sedan på Lägg till **kataloger**.</span><span class="sxs-lookup"><span data-stu-id="68492-151">Ensure that the **Specific connected organizations** option is selected, and then click **Add directories**.</span></span>
9. <span data-ttu-id="68492-152">Välj den anslutna organisation som du lägger till tidigare och klicka sedan på **Välj**</span><span class="sxs-lookup"><span data-stu-id="68492-152">Choose the connected organization that you add earlier, and then click **Select**</span></span>
10. <span data-ttu-id="68492-153">Under **Godkännande**väljer du **Ja** för **Kräv godkännande**.</span><span class="sxs-lookup"><span data-stu-id="68492-153">Under **Approval**, choose **Yes** for **Require approval**.</span></span>
11. <span data-ttu-id="68492-154">Under **Första godkännaren**väljer du en av sponsorerna som du har lagt till tidigare eller väljer en viss användare.</span><span class="sxs-lookup"><span data-stu-id="68492-154">Under **First approver**, choose one of the sponsors that you added earlier or choose a specific user.</span></span>
12. <span data-ttu-id="68492-155">Klicka på **Lägg till reservstöd** och välj en reserv godkännare.</span><span class="sxs-lookup"><span data-stu-id="68492-155">Click **Add fallback** and select a fallback approver.</span></span>
13. <span data-ttu-id="68492-156">Under **Aktivera**väljer du **Ja**.</span><span class="sxs-lookup"><span data-stu-id="68492-156">Under **Enable**, choose **Yes**.</span></span>
14. <span data-ttu-id="68492-157">Klicka på **Nästa: Livscykel**.</span><span class="sxs-lookup"><span data-stu-id="68492-157">Click **Next: Lifecycle**.</span></span>
15. <span data-ttu-id="68492-158">Välj de inställningar för förfallodatum och åtkomstgranskning som du vill använda och klicka sedan på **Nästa: Granska + Skapa**.</span><span class="sxs-lookup"><span data-stu-id="68492-158">Choose the expiration and access review settings that you want to use, and then click **Next: Review + Create**.</span></span>
16. <span data-ttu-id="68492-159">Granska inställningarna och klicka sedan på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="68492-159">Review your settings, and then click **Create**.</span></span>

    ![Skärmbild av skärmen åtkomstpaket i Azure Active Directory Identity Governance](../media/identity-governance-access-packages.png)

<span data-ttu-id="68492-161">Om du samarbetar med en stor organisation kanske du vill dölja åtkomstpaketet.</span><span class="sxs-lookup"><span data-stu-id="68492-161">If you're partnering with a large organization, you may want to hide the access package.</span></span> <span data-ttu-id="68492-162">Om paketet är dolt ser användarna i partnerorganisationen inte paketet på portalen *Min Åtkomst.*</span><span class="sxs-lookup"><span data-stu-id="68492-162">If the package is hidden, then users in the partner organization will not see the package on their *My Access* portal.</span></span> <span data-ttu-id="68492-163">I stället måste de skickas en direktlänk för att registrera sig för paketet.</span><span class="sxs-lookup"><span data-stu-id="68492-163">Instead, they must be sent a direct link to sign up for the package.</span></span> <span data-ttu-id="68492-164">Om du döljer åtkomstpaketet kan du minska antalet olämpliga åtkomstbegäranden och kan också hjälpa till att hålla tillgängliga åtkomstpaket organiserade i partnerorganisationens portal.</span><span class="sxs-lookup"><span data-stu-id="68492-164">Hiding the access package can reduce the number of inappropriate access requests and can also help keep available access packages organized in the partner organization's portal.</span></span>

<span data-ttu-id="68492-165">Så här ställer du in ett åtkomstpaket på dolda</span><span class="sxs-lookup"><span data-stu-id="68492-165">To set an access package to hidden</span></span>
1. <span data-ttu-id="68492-166">I Azure AD Identity Governance klickar du på **Åtkomstpaket**och sedan på ditt åtkomstpaket.</span><span class="sxs-lookup"><span data-stu-id="68492-166">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="68492-167">Klicka på **Redigera**på sidan **Översikt.**</span><span class="sxs-lookup"><span data-stu-id="68492-167">On the **Overview** page, click **Edit**.</span></span>
3. <span data-ttu-id="68492-168">Under **Egenskaper**väljer du **Ja** för **Dold**och klickar sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="68492-168">Under **Properties**, choose **Yes** for **Hidden**, and then click **Save**.</span></span>

   ![Skärmbild av en redigera åtkomstpaketegenskaper skärm](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a><span data-ttu-id="68492-170">Bjud in partneranvändare</span><span class="sxs-lookup"><span data-stu-id="68492-170">Invite partner users</span></span>

<span data-ttu-id="68492-171">Om du anger åtkomstpaketet till dolda måste du skicka en direktlänk till partnerorganisationen så att de kan begära åtkomst till din webbplats eller ditt team.</span><span class="sxs-lookup"><span data-stu-id="68492-171">If you set the access package to hidden, you need to send a direct link to the partner organization so that they can request access to your site or team.</span></span>

<span data-ttu-id="68492-172">Så här hittar du länken till åtkomstportalen</span><span class="sxs-lookup"><span data-stu-id="68492-172">To find the access portal link</span></span>
1. <span data-ttu-id="68492-173">I Azure AD Identity Governance klickar du på **Åtkomstpaket**och sedan på ditt åtkomstpaket.</span><span class="sxs-lookup"><span data-stu-id="68492-173">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="68492-174">Klicka på Kopiera **till urklippslänk** för **länken Min Access på**sidan **Översikt** .</span><span class="sxs-lookup"><span data-stu-id="68492-174">On the **Overview** page, click **Copy to clipboard** link for the **My Access portal link**.</span></span>

   ![Skärmbild av åtkomstpaketegenskaper med åtkomstportallänk](../media/identity-governance-access-portal-link.png)

<span data-ttu-id="68492-176">När du har kopierat länken kan du dela den med din kontakt i partnerorganisationen och de kan skicka den till användarna i deras samarbetsteam.</span><span class="sxs-lookup"><span data-stu-id="68492-176">Once you have copied the link, you can share it with your contact at the partner organization and they can send it to the users on their collaboration team.</span></span>

## <a name="see-also"></a><span data-ttu-id="68492-177">Se även</span><span class="sxs-lookup"><span data-stu-id="68492-177">See Also</span></span>

[<span data-ttu-id="68492-178">Skapa en säker miljö för gästdelning</span><span class="sxs-lookup"><span data-stu-id="68492-178">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

