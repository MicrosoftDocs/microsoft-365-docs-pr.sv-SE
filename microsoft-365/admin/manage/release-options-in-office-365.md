---
title: Konfigurera alternativen Standard eller Riktad version
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: Lär dig konfigurera alternativet för nya produkter och uppdateringar av funktioner i administrationscentret för Microsoft 365.
ms.openlocfilehash: f500aac89495c55d27fc4afb699254653786422d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915212"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a><span data-ttu-id="6751b-103">Konfigurera alternativen Standard eller Riktad version</span><span class="sxs-lookup"><span data-stu-id="6751b-103">Set up the Standard or Targeted release options</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="6751b-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="6751b-104">The admin center is changing.</span></span> <span data-ttu-id="6751b-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="6751b-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

> [!IMPORTANT]
> <span data-ttu-id="6751b-106">De Microsoft 365-uppdateringar som beskrivs i den här artikeln gäller för Microsoft 365, SharePoint Online och Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6751b-106">The Microsoft 365 updates described in this article apply to Microsoft 365, SharePoint Online, and Exchange Online.</span></span> <span data-ttu-id="6751b-107">De här versionsalternativen är riktade och bästa möjliga sätt att släppa ändringar i Microsoft 365, men kan inte alltid garanteras för alla uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="6751b-107">These release options are targeted, best effort ways to release changes to Microsoft 365 but cannot be guaranteed at all times or for all updates.</span></span> <span data-ttu-id="6751b-108">De gäller inte för Microsoft 365-appar, Skype för företag, Microsoft Teams eller relaterade tjänster.</span><span class="sxs-lookup"><span data-stu-id="6751b-108">They do not apply to Microsoft 365 Apps, Skype for Business, Microsoft Teams, and related services.</span></span> <span data-ttu-id="6751b-109">Information om versionsalternativ för Microsoft 365-appar finns i Översikt över [uppdateringskanaler för Microsoft 365-appar.](/deployoffice/overview-update-channels)</span><span class="sxs-lookup"><span data-stu-id="6751b-109">For information about release options for Microsoft 365 Apps, see [Overview of update channels for Microsoft 365 Apps](/deployoffice/overview-update-channels).</span></span>

<span data-ttu-id="6751b-110">Med Microsoft 365 får du tillgång till nya produktuppdateringar och funktioner allt eftersom de blir tillgängliga i stället för att göra dyra uppdateringar med några års hjälp.</span><span class="sxs-lookup"><span data-stu-id="6751b-110">With Microsoft 365, you receive new product updates and features as they become available instead of doing costly updates every few years.</span></span> <span data-ttu-id="6751b-111">Du kan styra hur organisationen ska få tillgång till uppdateringarna.</span><span class="sxs-lookup"><span data-stu-id="6751b-111">You can manage how your organization receives these updates.</span></span> <span data-ttu-id="6751b-112">Du kan till exempel registrera dig för en tidig version, så att organisationen blir bland de första som får uppdateringarna.</span><span class="sxs-lookup"><span data-stu-id="6751b-112">For example, you can sign up for an early release so that your organization receives updates first.</span></span> <span data-ttu-id="6751b-113">Du kan ange att bara vissa personer ska ta emot uppdateringarna.</span><span class="sxs-lookup"><span data-stu-id="6751b-113">You can designate that only certain individuals receive the updates.</span></span> <span data-ttu-id="6751b-114">Du kan också välja att behålla standardschemat för nya versioner och få uppdateringarna senare.</span><span class="sxs-lookup"><span data-stu-id="6751b-114">Or, you can remain on the default release schedule and receive the updates later.</span></span> <span data-ttu-id="6751b-115">I den här artikeln förklaras de olika versionsalternativen och hur du kan använda dem för din organisation.</span><span class="sxs-lookup"><span data-stu-id="6751b-115">This article explains the different release options and how you can use them for your organization.</span></span>

## <a name="how-it-works---release-validation"></a><span data-ttu-id="6751b-116">Så här fungerar det - versionsvalidering</span><span class="sxs-lookup"><span data-stu-id="6751b-116">How it works - release validation</span></span>

<span data-ttu-id="6751b-117">Alla nya versioner testas och valideras först av funktionsteamet och sedan av hela Microsoft 365-funktionsteamet, följt av hela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6751b-117">Any new release is first tested and validated by the feature team, then by the entire Microsoft 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="6751b-118">Efter intern testning och validering är nästa steg en **Riktad version** (tidigare kallad första version) till kunder som anmält sig för detta.</span><span class="sxs-lookup"><span data-stu-id="6751b-118">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="6751b-119">För varje version samlar Microsoft in feedback och validerar kvalitet genom att övervaka viktig användningsstatistik.</span><span class="sxs-lookup"><span data-stu-id="6751b-119">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="6751b-120">Det här arbetssättet med progressiv validering är avsedd att göra den version som släpps till allmänheten så robust som möjligt.</span><span class="sxs-lookup"><span data-stu-id="6751b-120">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="6751b-121">Versionerna beskrivs i bilden nedan.</span><span class="sxs-lookup"><span data-stu-id="6751b-121">The releases are pictured in the following figure.</span></span> 
  
![Versionsvalideringsringar för Microsoft 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="6751b-123">Kunder meddelas först om större uppdateringar via Översikt över [Microsoft 365.](https://products.office.com/business/office-365-roadmap)</span><span class="sxs-lookup"><span data-stu-id="6751b-123">For significant updates, customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="6751b-124">När en uppdatering är nära att lanseras meddelas den via meddelandecentret i [Microsoft 365.](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)</span><span class="sxs-lookup"><span data-stu-id="6751b-124">As an update gets closer to rolling out, it is communicated through your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="6751b-125">Du behöver ett Microsoft 365- eller Azure AD-konto för att få åtkomst till meddelandecentret via [administrationscentret.](/office365/admin/admin-overview/about-the-admin-center)</span><span class="sxs-lookup"><span data-stu-id="6751b-125">You need a Microsoft 365 or Azure AD account to access your Message center through the [admin center](/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="6751b-126">Användare av Microsoft 365-abonnemanget har inget administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="6751b-126">Microsoft 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="6751b-127">Standardversion</span><span class="sxs-lookup"><span data-stu-id="6751b-127">Standard release</span></span>

<span data-ttu-id="6751b-128">Det här är standardalternativet där du och användarna får de senaste uppdateringarna när de släpps för alla kunder.</span><span class="sxs-lookup"><span data-stu-id="6751b-128">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="6751b-129">En bra metod är att lämna de flesta användare i  **Standard-** och IT-proffs och avancerade användare i en riktad version som ger möjlighet att utvärdera nya funktioner och förbereda team som ger support till företagsanvändare och chefer.</span><span class="sxs-lookup"><span data-stu-id="6751b-129">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6751b-130">Om du växlar från riktad version tillbaka till standardversionen kan det hända att vissa användare förlorar åtkomst till funktioner som inte har inkluderats i standardversionen än.</span><span class="sxs-lookup"><span data-stu-id="6751b-130">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="6751b-131">Riktad version</span><span class="sxs-lookup"><span data-stu-id="6751b-131">Targeted release</span></span>

<span data-ttu-id="6751b-p107">Om du väljer det här alternativet kan du och andra användare i organisationen vara bland de första att ta del av de allra senaste uppdateringarna och bidra till att utforma produkter genom att ge återkoppling i ett tidigt skede. Du kan välja om du vill att bara vissa personer, eller alla i organisationen ska få dessa tidiga uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="6751b-p107">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6751b-p108">Stora eller komplexa uppdateringar kan genomföras under en längre tid, så att inga användare påverkas negativt. Det finns ingen garanti för att en versionsuppdatering ska följa en exakt tidslinje.</span><span class="sxs-lookup"><span data-stu-id="6751b-p108">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="6751b-136">Riktad version för hela organisationen</span><span class="sxs-lookup"><span data-stu-id="6751b-136">Targeted release for entire organization</span></span>

<span data-ttu-id="6751b-137">Om du [ställer in alternativet Version i administrationscentret](#set-up-the-release-option-in-the-admin-center) för det här alternativet får alla användare den riktade versionen.</span><span class="sxs-lookup"><span data-stu-id="6751b-137">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="6751b-138">Om organisationen har fler än 300 användare rekommenderar vi att en provprenumeration används för det här alternativet.</span><span class="sxs-lookup"><span data-stu-id="6751b-138">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="6751b-139">Kontakta Microsoft om du behöver information om provprenumerationer.</span><span class="sxs-lookup"><span data-stu-id="6751b-139">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="6751b-140">Riktad version för valda användare</span><span class="sxs-lookup"><span data-stu-id="6751b-140">Targeted release for selected users</span></span>

<span data-ttu-id="6751b-141">Om du [ställer in](#set-up-the-release-option-in-the-admin-center) alternativet Version i administrationscentret för det här alternativet kan du definiera specifika användare, vanligtvis avancerade användare, för att få tidig åtkomst till funktioner.</span><span class="sxs-lookup"><span data-stu-id="6751b-141">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="6751b-142">Fördelar med Riktad version</span><span class="sxs-lookup"><span data-stu-id="6751b-142">Benefits of Targeted release</span></span>

<span data-ttu-id="6751b-143">Riktad version ger administratörer, ändringshanterare och alla andra som ansvarar för Microsoft 365-uppdateringar möjlighet att förbereda sig för kommande ändringar genom att låta dem:</span><span class="sxs-lookup"><span data-stu-id="6751b-143">Targeted release allows admins, change managers, or anyone else responsible for Microsoft 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="6751b-144">Testa och validera nya uppdateringar innan de släpps till alla användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="6751b-144">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="6751b-145">Förbereda användarmeddelanden och dokumentation innan uppdateringar släpps i hela världen.</span><span class="sxs-lookup"><span data-stu-id="6751b-145">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="6751b-146">Förbereda den interna supporten på kommande ändringar.</span><span class="sxs-lookup"><span data-stu-id="6751b-146">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="6751b-147">Genomföra efterlevnads- och säkerhetsgranskningar.</span><span class="sxs-lookup"><span data-stu-id="6751b-147">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="6751b-148">Använda funktionskontroller och styra när användare får uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="6751b-148">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="6751b-149">Konfigurera alternativet för släppta versioner i administrationscentret</span><span class="sxs-lookup"><span data-stu-id="6751b-149">Set up the release option in the admin center</span></span>

<span data-ttu-id="6751b-150">Du kan ändra hur organisationen får Microsoft 365-uppdateringar genom att följa de här stegen.</span><span class="sxs-lookup"><span data-stu-id="6751b-150">You can change how your organization receives Microsoft 365 updates by following these steps.</span></span> <span data-ttu-id="6751b-151">Du måste vara global administratör i Microsoft 365 för att anmäla dig.</span><span class="sxs-lookup"><span data-stu-id="6751b-151">You have to be a global admin in Microsoft 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6751b-152">Det kan ta upp till 24 timmar innan nedanstående ändringar verkställs i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6751b-152">It can take up to 24 hours for the below changes to take effect in Microsoft 365.</span></span> <span data-ttu-id="6751b-153">Om organisationen tidigare har använt riktad version och du vill inaktivera detta kan det hända att vissa användare förlorar tillgång till funktioner som inte ingår i standardversionen än.</span><span class="sxs-lookup"><span data-stu-id="6751b-153">If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="6751b-154">I administrationscentret går du till Inställningar  >  **Organisationsinställning och** under fliken **Organisationsprofil** väljer du **Inställningar för släppta inställningar.**</span><span class="sxs-lookup"><span data-stu-id="6751b-154">In the admin center, go to the **Settings** > **Org Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="6751b-155">Om du vill inaktivera riktad version väljer **du Standard** och sedan **Spara ändringar.**</span><span class="sxs-lookup"><span data-stu-id="6751b-155">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="6751b-156">Om du vill aktivera den riktade versionen för alla användare i organisationen väljer du **Riktad version för alla** och sedan Spara **ändringar.**</span><span class="sxs-lookup"><span data-stu-id="6751b-156">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="6751b-157">Om du vill aktivera riktad version för vissa användare i organisationen väljer du **Riktad version för valda användare** och sedan Spara **ändringar.**</span><span class="sxs-lookup"><span data-stu-id="6751b-157">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="6751b-158">Välj **Välj användare för** att lägga till en användare i taget eller Ladda upp användare **för** att lägga till dem i grupp.</span><span class="sxs-lookup"><span data-stu-id="6751b-158">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="6751b-159">När du har lagt till alla användare väljer du **Spara ändringar.**</span><span class="sxs-lookup"><span data-stu-id="6751b-159">When you're done adding users, select **Save changes**.</span></span>


  
## <a name="learn-more"></a><span data-ttu-id="6751b-160">Mer information</span><span class="sxs-lookup"><span data-stu-id="6751b-160">Learn more</span></span>

<span data-ttu-id="6751b-161">Upptäck hur du [hanterar meddelanden](/office365/admin/manage/message-center) i Meddelandecenter för [Microsoft 365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) för att få aviseringar om kommande uppdateringar och versioner för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6751b-161">Discover how to [manage messages](/office365/admin/manage/message-center) in your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Microsoft 365 updates and releases.</span></span>