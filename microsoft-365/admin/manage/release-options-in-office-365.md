---
title: Ställ in alternativen standard eller riktad utgåva
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
description: Lär dig hur du konfigurerar utgivningsalternativet för nya produkter och funktioner i administrationscentret för Microsoft 365.
ms.openlocfilehash: 3baec050f33893357b25c832552643cf3a6d10d0
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/28/2020
ms.locfileid: "46502885"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a><span data-ttu-id="a3739-103">Ställ in alternativen standard eller riktad utgåva</span><span class="sxs-lookup"><span data-stu-id="a3739-103">Set up the Standard or Targeted release options</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="a3739-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="a3739-104">The admin center is changing.</span></span> <span data-ttu-id="a3739-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="a3739-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="a3739-106">Med Microsoft 365 får du nya produktuppdateringar och funktioner när de blir tillgängliga i stället för att göra kostsamma uppdateringar med några års mellanrum.</span><span class="sxs-lookup"><span data-stu-id="a3739-106">With Microsoft 365, you receive new product updates and features as they become available instead of doing costly updates every few years.</span></span> <span data-ttu-id="a3739-107">Du kan styra hur organisationen ska få tillgång till uppdateringarna.</span><span class="sxs-lookup"><span data-stu-id="a3739-107">You can manage how your organization receives these updates.</span></span> <span data-ttu-id="a3739-108">Du kan till exempel registrera dig för en tidig version, så att organisationen blir bland de första som får uppdateringarna.</span><span class="sxs-lookup"><span data-stu-id="a3739-108">For example, you can sign up for an early release so that your organization receives updates first.</span></span> <span data-ttu-id="a3739-109">Du kan ange att bara vissa personer ska ta emot uppdateringarna.</span><span class="sxs-lookup"><span data-stu-id="a3739-109">You can designate that only certain individuals receive the updates.</span></span> <span data-ttu-id="a3739-110">Du kan också välja att behålla standardschemat för nya versioner och få uppdateringarna senare.</span><span class="sxs-lookup"><span data-stu-id="a3739-110">Or, you can remain on the default release schedule and receive the updates later.</span></span> <span data-ttu-id="a3739-111">I den här artikeln beskrivs de olika frisläppningsalternativen och hur du kan använda dem för din organisation.</span><span class="sxs-lookup"><span data-stu-id="a3739-111">This article explains the different release options and how you can use them for your organization.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a3739-112">De Microsoft 365-uppdateringar som beskrivs i den här artikeln gäller Microsoft 365, SharePoint Online och Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a3739-112">The Microsoft 365 updates described in this article apply to Microsoft 365, SharePoint Online, and Exchange Online.</span></span> <span data-ttu-id="a3739-113">De gäller inte för Skype för företag och relaterade tjänster.</span><span class="sxs-lookup"><span data-stu-id="a3739-113">They do not apply to Skype for Business and related services.</span></span> <span data-ttu-id="a3739-114">Dessa utgivningsalternativ är riktade, bästa möjliga sätt att släppa ändringar i Microsoft 365 men kan inte garanteras hela tiden eller för alla uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="a3739-114">These release options are targeted, best effort ways to release changes to Microsoft 365 but cannot be guaranteed at all times or for all updates.</span></span> 

> [!NOTE]
> <span data-ttu-id="a3739-115">Information om uppdateringskanaler för program finns i [Översikt över uppdateringskanaler för Microsoft 365 Apps](https://docs.microsoft.com/deployoffice/overview-update-channels).</span><span class="sxs-lookup"><span data-stu-id="a3739-115">For information about update channels for applications, see [Overview of update channels for Microsoft 365 Apps](https://docs.microsoft.com/deployoffice/overview-update-channels).</span></span> 
  
## <a name="how-it-works---release-validation"></a><span data-ttu-id="a3739-116">Så här fungerar det - versionsvalidering</span><span class="sxs-lookup"><span data-stu-id="a3739-116">How it works - release validation</span></span>

<span data-ttu-id="a3739-117">Alla nya versionen testas och valideras först av funktionsteamet, sedan av hela Microsoft 365-funktionsteamet, följt av hela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a3739-117">Any new release is first tested and validated by the feature team, then by the entire Microsoft 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="a3739-118">Efter intern testning och validering är nästa steg en **Riktad version** (tidigare kallad första version) till kunder som anmält sig för detta.</span><span class="sxs-lookup"><span data-stu-id="a3739-118">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="a3739-119">För varje version samlar Microsoft in feedback och validerar kvalitet genom att övervaka viktig användningsstatistik.</span><span class="sxs-lookup"><span data-stu-id="a3739-119">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="a3739-120">Det här arbetssättet med progressiv validering är avsedd att göra den version som släpps till allmänheten så robust som möjligt.</span><span class="sxs-lookup"><span data-stu-id="a3739-120">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="a3739-121">Versionerna beskrivs i bilden nedan.</span><span class="sxs-lookup"><span data-stu-id="a3739-121">The releases are pictured in the following figure.</span></span> 
  
![Släpp valideringsringar för Microsoft 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="a3739-123">För viktiga uppdateringar meddelas kunderna inledningsvis av [Microsoft 365-översikten](https://products.office.com/business/office-365-roadmap).</span><span class="sxs-lookup"><span data-stu-id="a3739-123">For significant updates, customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="a3739-124">När en uppdatering närmar sig utrullningen kommuniceras den via [ditt Microsoft 365 Message Center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span><span class="sxs-lookup"><span data-stu-id="a3739-124">As an update gets closer to rolling out, it is communicated through your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="a3739-125">Du behöver ett Microsoft 365- eller Azure AD-konto för att komma åt ditt meddelandecenter via [administrationscentret](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center).</span><span class="sxs-lookup"><span data-stu-id="a3739-125">You need a Microsoft 365 or Azure AD account to access your Message center through the [admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="a3739-126">Microsoft 365-hemabonnemangsanvändare har inget administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="a3739-126">Microsoft 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="a3739-127">Standardversion</span><span class="sxs-lookup"><span data-stu-id="a3739-127">Standard release</span></span>

<span data-ttu-id="a3739-128">Det här är standardalternativet där du och dina användare får de senaste uppdateringarna när de släpps brett till alla kunder.</span><span class="sxs-lookup"><span data-stu-id="a3739-128">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="a3739-129">En god praxis är att lämna majoriteten av användarna i **Standard release** och IT-proffs och avancerade användare i **Riktad utgåva** för att utvärdera nya funktioner och förbereda team för att stödja företagsanvändare och chefer.</span><span class="sxs-lookup"><span data-stu-id="a3739-129">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a3739-130">Om du växlar från riktad version tillbaka till standardversionen kan det hända att vissa användare förlorar åtkomst till funktioner som inte har inkluderats i standardversionen än.</span><span class="sxs-lookup"><span data-stu-id="a3739-130">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="a3739-131">Riktad version</span><span class="sxs-lookup"><span data-stu-id="a3739-131">Targeted release</span></span>

<span data-ttu-id="a3739-p107">Om du väljer det här alternativet kan du och andra användare i organisationen vara bland de första att ta del av de allra senaste uppdateringarna och bidra till att utforma produkter genom att ge återkoppling i ett tidigt skede. Du kan välja om du vill att bara vissa personer, eller alla i organisationen ska få dessa tidiga uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="a3739-p107">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a3739-p108">Stora eller komplexa uppdateringar kan genomföras under en längre tid, så att inga användare påverkas negativt. Det finns ingen garanti för att en versionsuppdatering ska följa en exakt tidslinje.</span><span class="sxs-lookup"><span data-stu-id="a3739-p108">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="a3739-136">Riktad version för hela organisationen</span><span class="sxs-lookup"><span data-stu-id="a3739-136">Targeted release for entire organization</span></span>

<span data-ttu-id="a3739-137">Om du [konfigurerar utgivningsalternativet i administrationscentret](#set-up-the-release-option-in-the-admin-center) för det här alternativet får alla användare upplevelsen riktad.</span><span class="sxs-lookup"><span data-stu-id="a3739-137">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="a3739-138">Om organisationen har fler än 300 användare rekommenderar vi att en provprenumeration används för det här alternativet.</span><span class="sxs-lookup"><span data-stu-id="a3739-138">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="a3739-139">Kontakta Microsoft om du behöver information om provprenumerationer.</span><span class="sxs-lookup"><span data-stu-id="a3739-139">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="a3739-140">Riktad version för valda användare</span><span class="sxs-lookup"><span data-stu-id="a3739-140">Targeted release for selected users</span></span>

<span data-ttu-id="a3739-141">Om du [konfigurerar utgivningsalternativet i administrationscentret](#set-up-the-release-option-in-the-admin-center) för det här alternativet kan du definiera specifika användare, vanligtvis avancerade användare, för att få tidig åtkomst till funktioner och funktioner.</span><span class="sxs-lookup"><span data-stu-id="a3739-141">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="a3739-142">Fördelar med Riktad version</span><span class="sxs-lookup"><span data-stu-id="a3739-142">Benefits of Targeted release</span></span>

<span data-ttu-id="a3739-143">Riktad utgåva gör det möjligt för administratörer, ändringshanterare eller någon annan som ansvarar för Microsoft 365-uppdateringar att förbereda sig för de kommande ändringarna genom att låta dem:</span><span class="sxs-lookup"><span data-stu-id="a3739-143">Targeted release allows admins, change managers, or anyone else responsible for Microsoft 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="a3739-144">Testa och validera nya uppdateringar innan de släpps till alla användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="a3739-144">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="a3739-145">Förbereda användarmeddelanden och dokumentation innan uppdateringar släpps i hela världen.</span><span class="sxs-lookup"><span data-stu-id="a3739-145">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="a3739-146">Förbereda den interna supporten på kommande ändringar.</span><span class="sxs-lookup"><span data-stu-id="a3739-146">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="a3739-147">Genomföra efterlevnads- och säkerhetsgranskningar.</span><span class="sxs-lookup"><span data-stu-id="a3739-147">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="a3739-148">Använda funktionskontroller och styra när användare får uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="a3739-148">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="a3739-149">Konfigurera utgivningsalternativet i administrationscentret</span><span class="sxs-lookup"><span data-stu-id="a3739-149">Set up the release option in the admin center</span></span>

<span data-ttu-id="a3739-150">Du kan ändra hur din organisation tar emot Microsoft 365-uppdateringar genom att följa dessa steg.</span><span class="sxs-lookup"><span data-stu-id="a3739-150">You can change how your organization receives Microsoft 365 updates by following these steps.</span></span> <span data-ttu-id="a3739-151">Du måste vara global administratör i Microsoft 365 för att kunna anmäla dig.</span><span class="sxs-lookup"><span data-stu-id="a3739-151">You have to be a global admin in Microsoft 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a3739-152">Det kan ta upp till 24 timmar innan ändringarna nedan börjar gälla i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a3739-152">It can take up to 24 hours for the below changes to take effect in Microsoft 365.</span></span> <span data-ttu-id="a3739-153">Om organisationen tidigare har använt riktad version och du vill inaktivera detta kan det hända att vissa användare förlorar tillgång till funktioner som inte ingår i standardversionen än.</span><span class="sxs-lookup"><span data-stu-id="a3739-153">If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="a3739-154">Gå till **Settings**  >  **inställningen Inställningars organisationsorganisation**i administrationscentret och välj **Utgivningsinställningar**under fliken **Organisationsprofil** .</span><span class="sxs-lookup"><span data-stu-id="a3739-154">In the admin center, go to the **Settings** > **Org Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="a3739-155">Om du vill inaktivera riktad frisättning väljer du **Standardversion**och väljer sedan **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="a3739-155">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="a3739-156">Om du vill aktivera riktad publicering för alla användare i organisationen väljer du **Riktad version för alla**och väljer sedan Spara **ändringar**.</span><span class="sxs-lookup"><span data-stu-id="a3739-156">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="a3739-157">Om du vill aktivera riktad publicering för vissa personer i organisationen väljer du **Riktad version för valda användare**och väljer sedan Spara **ändringar**.</span><span class="sxs-lookup"><span data-stu-id="a3739-157">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="a3739-158">Välj **Välj användare** om du vill lägga till användare en i taget eller Ladda upp **användare** om du vill lägga till dem i grupp.</span><span class="sxs-lookup"><span data-stu-id="a3739-158">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="a3739-159">När du är klar med att lägga till användare väljer du **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="a3739-159">When you're done adding users, select **Save changes**.</span></span>


  
## <a name="learn-more"></a><span data-ttu-id="a3739-160">Mer information</span><span class="sxs-lookup"><span data-stu-id="a3739-160">Learn more</span></span>

<span data-ttu-id="a3739-161">Upptäck hur du [hanterar meddelanden](https://docs.microsoft.com/office365/admin/manage/message-center) i ditt [Microsoft 365-meddelandecenter](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) för att få aviseringar om kommande uppdateringar och utgåvor från Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a3739-161">Discover how to [manage messages](https://docs.microsoft.com/office365/admin/manage/message-center) in your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Microsoft 365 updates and releases.</span></span>
