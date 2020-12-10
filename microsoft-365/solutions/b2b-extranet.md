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
description: Lär dig hur du skapar en webbplats eller ett B2B-team med hanterade gäster från en partner organisation.
ms.openlocfilehash: cfb7cc4310cb83f9ce7761c95f021724b7d75faf
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613602"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a><span data-ttu-id="b39e3-103">Skapa ett B2B-extranät med hanterade gäster</span><span class="sxs-lookup"><span data-stu-id="b39e3-103">Create a B2B extranet with managed guests</span></span>

<span data-ttu-id="b39e3-104">Du kan använda [Azure Active Directory-hanteringen](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) för att skapa ett B2B-extra nät för att samar beta med en partner organisation som använder Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b39e3-104">You can use [Azure Active Directory Entitlement Management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) to create a B2B extranet to collaborate with a partner organization that uses Azure Active Directory.</span></span> <span data-ttu-id="b39e3-105">Detta gör att användare själv kan registrera sig på extra nätet eller teamet och få åtkomst via ett arbets flöde för godkännande.</span><span class="sxs-lookup"><span data-stu-id="b39e3-105">This allows users to self-enroll in the extranet site or team and receive access via an approval workflow.</span></span>

<span data-ttu-id="b39e3-106">Med den här metoden för att dela resurser för samarbete kan partner organisationen hjälpa till att underhålla och godkänna gästerna, vilket minskar belastningen på IT-avdelningen och gör dem mest bekanta med samarbets avtalet för att hantera användar åtkomst.</span><span class="sxs-lookup"><span data-stu-id="b39e3-106">With this method of sharing resources for collaboration, the partner organization can help maintain and approve the guests on their end, reducing the burden on your IT department and allowing those most familiar with the collaboration agreement to manage user access.</span></span>

<span data-ttu-id="b39e3-107">Den här artikeln innehåller anvisningar för hur du skapar ett paket med resurser (i det här fallet en webbplats eller ett team) som du kan dela med en partner organisation via en självbetjänings registrerings modell.</span><span class="sxs-lookup"><span data-stu-id="b39e3-107">This article walks through the steps to create a package of resources (in this case, a site or team) that you can share with a partner organization through a self-service access registration model.</span></span> 

<span data-ttu-id="b39e3-108">Innan du börjar ska du skapa en webbplats eller ett team som du vill dela med partner organisationen och aktivera den för gäst delning.</span><span class="sxs-lookup"><span data-stu-id="b39e3-108">Before you begin, create the site or team that you want to share with the partner organization and enable it for guest sharing.</span></span> <span data-ttu-id="b39e3-109">Se [samar beta med gäster på en webbplats](collaborate-in-site.md) eller [samar beta med gäster i ett team](collaborate-as-team.md) för mer information.</span><span class="sxs-lookup"><span data-stu-id="b39e3-109">See [Collaborate with guests in a site](collaborate-in-site.md) or [Collaborate with guests in a team](collaborate-as-team.md) for more information.</span></span> <span data-ttu-id="b39e3-110">Vi rekommenderar också att du går igenom [skapa en säker gäst delnings miljö](create-secure-guest-sharing-environment.md) för information om säkerhets-och efterföljandekrav som du kan använda för att hjälpa till att underhålla dina styrnings principer när du samarbetar med gäster.</span><span class="sxs-lookup"><span data-stu-id="b39e3-110">We also recommend that you review [Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) for information about security and compliance features that you can use to help maintain your governance policies when collaborating with guests.</span></span>

## <a name="license-requirements"></a><span data-ttu-id="b39e3-111">Licens krav</span><span class="sxs-lookup"><span data-stu-id="b39e3-111">License requirements</span></span>

<span data-ttu-id="b39e3-112">För att använda den här funktionen krävs en Azure AD Premium P2-licens.</span><span class="sxs-lookup"><span data-stu-id="b39e3-112">Using this feature requires an Azure AD Premium P2 license.</span></span> 

<span data-ttu-id="b39e3-113">Specialiserade moln, till exempel Azure Germany och Azure Kina 21Vianet, är för närvarande inte tillgängliga för användning.</span><span class="sxs-lookup"><span data-stu-id="b39e3-113">Specialized clouds, such as Azure Germany and Azure China 21Vianet, are not currently available for use.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="b39e3-114">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="b39e3-114">Video demonstration</span></span>

<span data-ttu-id="b39e3-115">Den här videon visar de procedurer som beskrivs i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="b39e3-115">This video demonstrates the procedures covered in this article.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a><span data-ttu-id="b39e3-116">Ansluta partner organisationen</span><span class="sxs-lookup"><span data-stu-id="b39e3-116">Connect the partner organization</span></span>

<span data-ttu-id="b39e3-117">För att kunna bjuda in gäster från en partner organisation måste du lägga till partners domän som ansluten organisation i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b39e3-117">In order to invite guests from a partner organization, you need to add the partner's domain as a connected organization in Azure Active Directory.</span></span>

<span data-ttu-id="b39e3-118">Lägga till en ansluten organisation</span><span class="sxs-lookup"><span data-stu-id="b39e3-118">To add a connected organization</span></span>
1. <span data-ttu-id="b39e3-119">Klicka på **identitets styrning** i [Azure Active Directory](https://aad.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="b39e3-119">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="b39e3-120">Klicka på **anslutna organisationer**.</span><span class="sxs-lookup"><span data-stu-id="b39e3-120">Click **Connected organizations**.</span></span>
4. <span data-ttu-id="b39e3-121">Klicka på **Lägg till ansluten organisation**.</span><span class="sxs-lookup"><span data-stu-id="b39e3-121">Click **Add connected organization**.</span></span>
5. <span data-ttu-id="b39e3-122">Ange ett namn och en beskrivning för organisationen och klicka sedan på **Nästa: Katalog + domän**.</span><span class="sxs-lookup"><span data-stu-id="b39e3-122">Type a name and description for the organization, and then click **Next: Directory + domain**.</span></span>
6. <span data-ttu-id="b39e3-123">Klicka på **Lägg till katalog + domän**.</span><span class="sxs-lookup"><span data-stu-id="b39e3-123">Click **Add directory + domain**.</span></span>
7. <span data-ttu-id="b39e3-124">Skriv domänen för den organisation som du vill ansluta till och klicka sedan på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="b39e3-124">Type the domain for the organization that you want to connect, and then click **Add**.</span></span>
8. <span data-ttu-id="b39e3-125">Klicka på **Anslut** och sedan på **Nästa: sponsorer**.</span><span class="sxs-lookup"><span data-stu-id="b39e3-125">Click **Connect**, and then click **Next: Sponsors**.</span></span>
9. <span data-ttu-id="b39e3-126">Lägg till personer från din organisation eller den organisation som du ansluter till och som du vill godkänna åtkomst för gäster.</span><span class="sxs-lookup"><span data-stu-id="b39e3-126">Add people from your organization or the organization that you're connecting to who you want to approve access for guests.</span></span>
10. <span data-ttu-id="b39e3-127">Klicka på **Nästa: granska + skapa**.</span><span class="sxs-lookup"><span data-stu-id="b39e3-127">Click **Next: Review + Create**.</span></span>
11. <span data-ttu-id="b39e3-128">Granska de inställningar du har valt och klicka sedan på **skapa**.</span><span class="sxs-lookup"><span data-stu-id="b39e3-128">Review the settings that you've chosen and then click **Create**.</span></span>

    ![Skärm bild av sidan anslutna organisationer i Azure Active Directory](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a><span data-ttu-id="b39e3-130">Välj vilka resurser du vill dela</span><span class="sxs-lookup"><span data-stu-id="b39e3-130">Choose the resources to share</span></span>

<span data-ttu-id="b39e3-131">Det första steget när du väljer resurser som du vill dela med en partner organisation är att skapa en katalog som innehåller dem.</span><span class="sxs-lookup"><span data-stu-id="b39e3-131">The first step in selecting resources to share with a partner organization is to create a catalog to contain them.</span></span>

<span data-ttu-id="b39e3-132">Skapa en katalog</span><span class="sxs-lookup"><span data-stu-id="b39e3-132">To create a catalog</span></span>
1. <span data-ttu-id="b39e3-133">Klicka på **identitets styrning** i [Azure Active Directory](https://aad.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="b39e3-133">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="b39e3-134">Klicka på **kataloger**.</span><span class="sxs-lookup"><span data-stu-id="b39e3-134">Click **Catalogs**.</span></span>
3. <span data-ttu-id="b39e3-135">Klicka på **ny katalog**.</span><span class="sxs-lookup"><span data-stu-id="b39e3-135">Click **New catalog**.</span></span>
4. <span data-ttu-id="b39e3-136">Ange ett namn och en beskrivning för katalogen och kontrol lera att **aktiverat** och **aktiverat för externa användare** båda är inställda på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="b39e3-136">Type a name and description for the catalog and ensure that **Enabled** and **Enabled for external users** are both set to **Yes**.</span></span>
5. <span data-ttu-id="b39e3-137">Klicka på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="b39e3-137">Click **Create**.</span></span>

   ![Skärm bild av sidan kataloger i Azure Active Directory Identity styrelse](../media/identity-governance-catalogs.png)

<span data-ttu-id="b39e3-139">När du har skapat katalogen lägger du till den SharePoint-webbplats eller det team som du vill dela med partner organisationen.</span><span class="sxs-lookup"><span data-stu-id="b39e3-139">Once the catalog has been created, you add the SharePoint site or team that you want to share with the partner organization.</span></span>

<span data-ttu-id="b39e3-140">Lägga till resurser i en katalog</span><span class="sxs-lookup"><span data-stu-id="b39e3-140">To add resources to a catalog</span></span>
1. <span data-ttu-id="b39e3-141">I Azure AD Identity styrelse klickar du på **kataloger** och sedan på den katalog där du vill lägga till resurser.</span><span class="sxs-lookup"><span data-stu-id="b39e3-141">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to add resources.</span></span>
2. <span data-ttu-id="b39e3-142">Klicka på **resurser** och sedan på **Lägg till resurser**.</span><span class="sxs-lookup"><span data-stu-id="b39e3-142">Click **Resources** and then click **Add resources**.</span></span>
3. <span data-ttu-id="b39e3-143">Välj de team-eller SharePoint-webbplatser som du vill ta med i extra nätet och klicka sedan på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="b39e3-143">Select the teams or SharePoint sites that you want to include in your extranet, and then click **Add**.</span></span>

   ![Skärm bild av sidan katalog resurser i Azure Active Directory Identity styrelse](../media/identity-governance-catalog-resource.png)

<span data-ttu-id="b39e3-145">När du har angett de resurser som du vill dela är nästa steg att skapa ett Access-paket, som definierar den typ av åtkomst som partner användare beviljar och godkännande processen för nya partner användare som begär åtkomst.</span><span class="sxs-lookup"><span data-stu-id="b39e3-145">Once you've defined the resources that you want to share, the next step is to create an access package, which defines the type of access that partner users are granted and the approval process for new partner users requesting access.</span></span>

<span data-ttu-id="b39e3-146">Så här skapar du ett Access-paket</span><span class="sxs-lookup"><span data-stu-id="b39e3-146">To create an access package</span></span>
1. <span data-ttu-id="b39e3-147">I Azure AD Identity styrelse klickar du på **kataloger** och sedan på den katalog där du vill skapa ett Access-paket.</span><span class="sxs-lookup"><span data-stu-id="b39e3-147">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to create an access package.</span></span>
2. <span data-ttu-id="b39e3-148">Klicka på **Access-paket** och sedan på **nytt Access-paket**.</span><span class="sxs-lookup"><span data-stu-id="b39e3-148">Click **Access packages**, and then click **New access package**.</span></span>
3. <span data-ttu-id="b39e3-149">Ange ett namn och en beskrivning för Access-paketet och klicka sedan på **Nästa: resurs roller**.</span><span class="sxs-lookup"><span data-stu-id="b39e3-149">Type a name and description for the access package, and then click **Next: Resource roles**.</span></span>
4. <span data-ttu-id="b39e3-150">Välj de resurser från katalogen som du vill använda för extra nätet.</span><span class="sxs-lookup"><span data-stu-id="b39e3-150">Choose the resources from the catalog that you want to use for your extranet.</span></span>
5. <span data-ttu-id="b39e3-151">För varje resurs, i kolumnen **Role** , väljer du den användar roll du vill ge till gästerna som använder extra nätet.</span><span class="sxs-lookup"><span data-stu-id="b39e3-151">For each resource, in the **Role** column, choose the user role you want to grant to the guests who use the extranet.</span></span>
6. <span data-ttu-id="b39e3-152">Klicka på **Nästa: förfrågningar**.</span><span class="sxs-lookup"><span data-stu-id="b39e3-152">Click **Next: Requests**.</span></span>
7. <span data-ttu-id="b39e3-153">Under **användare som kan begära åtkomst** väljer du **för användare som inte finns i katalogen**.</span><span class="sxs-lookup"><span data-stu-id="b39e3-153">Under **Users who can request access**, choose **For users not in your directory**.</span></span>
8. <span data-ttu-id="b39e3-154">Kontrol lera att alternativet **specifika anslutna organisationer** är markerat och klicka sedan på **Lägg till kataloger**.</span><span class="sxs-lookup"><span data-stu-id="b39e3-154">Ensure that the **Specific connected organizations** option is selected, and then click **Add directories**.</span></span>
9. <span data-ttu-id="b39e3-155">Välj den anslutna organisation du lägger till tidigare och klicka sedan på **Välj**</span><span class="sxs-lookup"><span data-stu-id="b39e3-155">Choose the connected organization that you add earlier, and then click **Select**</span></span>
10. <span data-ttu-id="b39e3-156">Under **godkännande** väljer du **Ja** för att **begära godkännande**.</span><span class="sxs-lookup"><span data-stu-id="b39e3-156">Under **Approval**, choose **Yes** for **Require approval**.</span></span>
11. <span data-ttu-id="b39e3-157">Under den **första god kännaren** väljer du något av sponsorerna som du lade till tidigare eller väljer en specifik användare.</span><span class="sxs-lookup"><span data-stu-id="b39e3-157">Under **First approver**, choose one of the sponsors that you added earlier or choose a specific user.</span></span>
12. <span data-ttu-id="b39e3-158">Klicka på **Lägg till reserv** och välj en reserv god kännare.</span><span class="sxs-lookup"><span data-stu-id="b39e3-158">Click **Add fallback** and select a fallback approver.</span></span>
13. <span data-ttu-id="b39e3-159">Under **Aktivera** väljer du **Ja**.</span><span class="sxs-lookup"><span data-stu-id="b39e3-159">Under **Enable**, choose **Yes**.</span></span>
14. <span data-ttu-id="b39e3-160">Klicka på **Nästa: livs cykel**.</span><span class="sxs-lookup"><span data-stu-id="b39e3-160">Click **Next: Lifecycle**.</span></span>
15. <span data-ttu-id="b39e3-161">Välj de inställningar för förfallo datum och åtkomst granskning du vill använda och klicka sedan på **Nästa: granska + skapa**.</span><span class="sxs-lookup"><span data-stu-id="b39e3-161">Choose the expiration and access review settings that you want to use, and then click **Next: Review + Create**.</span></span>
16. <span data-ttu-id="b39e3-162">Granska inställningarna och klicka sedan på **skapa**.</span><span class="sxs-lookup"><span data-stu-id="b39e3-162">Review your settings, and then click **Create**.</span></span>

    ![Skärm bild av skärmen med åtkomst paket i Azure Active Directory-Identity styrelse](../media/identity-governance-access-packages.png)

<span data-ttu-id="b39e3-164">Om du samarbetar med en stor organisation kanske du vill dölja Access-paketet.</span><span class="sxs-lookup"><span data-stu-id="b39e3-164">If you're partnering with a large organization, you may want to hide the access package.</span></span> <span data-ttu-id="b39e3-165">Om paketet är dolt kommer användare i partner organisationen inte att se paketet på sin *åtkomst* -Portal.</span><span class="sxs-lookup"><span data-stu-id="b39e3-165">If the package is hidden, then users in the partner organization will not see the package on their *My Access* portal.</span></span> <span data-ttu-id="b39e3-166">I stället måste de skicka en direkt länk för att kunna registrera sig för paketet.</span><span class="sxs-lookup"><span data-stu-id="b39e3-166">Instead, they must be sent a direct link to sign up for the package.</span></span> <span data-ttu-id="b39e3-167">Om du döljer Access-paketet kan du minska antalet olämpliga åtkomst begär Anden och du kan även hålla tillgängliga paket organiserade i partner organisationens Portal.</span><span class="sxs-lookup"><span data-stu-id="b39e3-167">Hiding the access package can reduce the number of inappropriate access requests and can also help keep available access packages organized in the partner organization's portal.</span></span>

<span data-ttu-id="b39e3-168">Så här anger du att ett Access-paket ska döljas</span><span class="sxs-lookup"><span data-stu-id="b39e3-168">To set an access package to hidden</span></span>
1. <span data-ttu-id="b39e3-169">I Azure AD Identity styrelse klickar du på **Access-paket** och sedan på ditt Access-paket.</span><span class="sxs-lookup"><span data-stu-id="b39e3-169">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="b39e3-170">Klicka på **Redigera** på sidan **Översikt** .</span><span class="sxs-lookup"><span data-stu-id="b39e3-170">On the **Overview** page, click **Edit**.</span></span>
3. <span data-ttu-id="b39e3-171">Under **Egenskaper** väljer du **Ja** för **dold** och klickar sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b39e3-171">Under **Properties**, choose **Yes** for **Hidden**, and then click **Save**.</span></span>

   ![Skärm bild av skärmen egenskaper för redigera Access-paket](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a><span data-ttu-id="b39e3-173">Bjuda in partner användare</span><span class="sxs-lookup"><span data-stu-id="b39e3-173">Invite partner users</span></span>

<span data-ttu-id="b39e3-174">Om du anger att Access-paketet ska döljas måste du skicka en direkt länk till partner organisationen så att de kan begära åtkomst till webbplatsen eller teamet.</span><span class="sxs-lookup"><span data-stu-id="b39e3-174">If you set the access package to hidden, you need to send a direct link to the partner organization so that they can request access to your site or team.</span></span>

<span data-ttu-id="b39e3-175">Så här hittar du Access Portal-länken</span><span class="sxs-lookup"><span data-stu-id="b39e3-175">To find the access portal link</span></span>
1. <span data-ttu-id="b39e3-176">I Azure AD Identity styrelse klickar du på **Access-paket** och sedan på ditt Access-paket.</span><span class="sxs-lookup"><span data-stu-id="b39e3-176">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="b39e3-177">På sidan **Översikt** klickar du på **Kopiera till Urklipp** -länken för **länken My Access-portalen**.</span><span class="sxs-lookup"><span data-stu-id="b39e3-177">On the **Overview** page, click **Copy to clipboard** link for the **My Access portal link**.</span></span>

   ![Skärm bild av egenskaper för Access-paket med åtkomst Portal länk](../media/identity-governance-access-portal-link.png)

<span data-ttu-id="b39e3-179">När du har kopierat länken kan du dela den med din kontakt i partner organisationen och de kan skicka den till användarna i samarbets gruppen.</span><span class="sxs-lookup"><span data-stu-id="b39e3-179">Once you have copied the link, you can share it with your contact at the partner organization and they can send it to the users on their collaboration team.</span></span>

## <a name="see-also"></a><span data-ttu-id="b39e3-180">Se även</span><span class="sxs-lookup"><span data-stu-id="b39e3-180">See Also</span></span>

[<span data-ttu-id="b39e3-181">Skapa en säker miljö för gästdelning</span><span class="sxs-lookup"><span data-stu-id="b39e3-181">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)
