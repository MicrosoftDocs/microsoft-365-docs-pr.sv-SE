---
title: Ställa in alternativen Standard eller Riktad version i Office 365
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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: Läs om hur du konfigurerar utgivningsalternativet för nya produkt- och funktionsuppdateringar i administrationscentret för Microsoft 365.
ms.openlocfilehash: d6c2eab340f4401fb31e4d9e814fbd326573569a
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42810683"
---
# <a name="set-up-the-standard-or-targeted-release-options-in-office-365"></a><span data-ttu-id="ef0e4-103">Ställa in alternativen Standard eller Riktad version i Office 365</span><span class="sxs-lookup"><span data-stu-id="ef0e4-103">Set up the Standard or Targeted release options in Office 365</span></span>

<span data-ttu-id="ef0e4-p101">Med Office 365 kan du ta del av produktuppdateringar och funktioner när de blir tillgängliga i stället för att göra dyra uppdateringar med några års mellanrum. Du kan styra hur organisationen ska få tillgång till uppdateringarna. Du kan till exempel registrera dig för en tidig version, så att organisationen blir bland de första som får uppdateringarna. Du kan ange att bara vissa personer ska ta emot uppdateringarna. Du kan också välja att behålla standardschemat för nya versioner och få uppdateringarna senare. I den här artikeln beskrivs vilka olika alternativ som finns för att ta emot nya versioner och hur du kan använda dem för organisationen.</span><span class="sxs-lookup"><span data-stu-id="ef0e4-p101">With Office 365, you receive new product updates and features as they become available instead of doing costly updates every few years. You can manage how your organization receives these updates. For example, you can sign up for an early release so that your organization receives updates first. You can designate that only certain individuals receive the updates. Or, you can remain on the default release schedule and receive the updates later. This article explain the different release options and how you can use them for your organization.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ef0e4-p102">De Office 365-uppdateringar som beskrivs i den här artikeln gäller för Office 365, SharePoint Online och Exchange Online. De gäller inte för Skype för företag och relaterade tjänster. De här versionsalternativen utgör en målinriktad strävan efter att skapa förbättringar för Office 365, men detta kan inte alltid garanteras för alla uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="ef0e4-p102">The Office 365 updates described in this article apply to Office 365, SharePoint Online, and Exchange Online. They do not apply to Skype for Business and related services. These release options are targeted, best effort ways to release changes to Office 365 but cannot be guaranteed at all times or for all updates.</span></span> 
  
## <a name="how-it-works---release-validation"></a><span data-ttu-id="ef0e4-113">Så här fungerar det - versionsvalidering</span><span class="sxs-lookup"><span data-stu-id="ef0e4-113">How it works - release validation</span></span>

<span data-ttu-id="ef0e4-114">Alla nya versionen testas och valideras först av funktionsteamet, sedan av hela Office 365-funktionsteamet, följt av hela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ef0e4-114">Any new release is first tested and validated by the feature team, then by the entire Office 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="ef0e4-115">Efter intern testning och validering är nästa steg en **Riktad version** (tidigare kallad första version) till kunder som anmält sig för detta.</span><span class="sxs-lookup"><span data-stu-id="ef0e4-115">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="ef0e4-116">För varje version samlar Microsoft in feedback och validerar kvalitet genom att övervaka viktig användningsstatistik.</span><span class="sxs-lookup"><span data-stu-id="ef0e4-116">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="ef0e4-117">Det här arbetssättet med progressiv validering är avsedd att göra den version som släpps till allmänheten så robust som möjligt.</span><span class="sxs-lookup"><span data-stu-id="ef0e4-117">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="ef0e4-118">Versionerna beskrivs i bilden nedan.</span><span class="sxs-lookup"><span data-stu-id="ef0e4-118">The releases are pictured in the following figure.</span></span> 
  
![Släpp valideringsringar för Office 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="ef0e4-120">För viktiga uppdateringar meddelas Office-kunder inledningsvis av [Microsoft 365-färdplanen](https://products.office.com/business/office-365-roadmap).</span><span class="sxs-lookup"><span data-stu-id="ef0e4-120">For significant updates, Office customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="ef0e4-121">När en uppdatering närmar sig utbyggnaden kommuniceras den via [ditt Meddelandecenter för Office 365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span><span class="sxs-lookup"><span data-stu-id="ef0e4-121">As an update gets closer to rolling out, it is communicated through your [Office 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="ef0e4-122">Du behöver ett Office 365- eller Azure AD-konto för att komma åt ditt meddelandecenter via [administrationscentret](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center).</span><span class="sxs-lookup"><span data-stu-id="ef0e4-122">You need an Office 365 or Azure AD account to access your Message center through the [admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="ef0e4-123">Office 365 hemplan användare har inte ett administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="ef0e4-123">Office 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="ef0e4-124">Standardversion</span><span class="sxs-lookup"><span data-stu-id="ef0e4-124">Standard release</span></span>

<span data-ttu-id="ef0e4-125">Detta är standardalternativet där du och dina användare får de senaste uppdateringarna när de släpps i stort sett till alla kunder.</span><span class="sxs-lookup"><span data-stu-id="ef0e4-125">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="ef0e4-126">En god praxis är att lämna majoriteten av användarna i **Standard release** och IT-proffs och avancerade användare i **Riktad release** för att utvärdera nya funktioner och förbereda team för att stödja företagsanvändare och chefer.</span><span class="sxs-lookup"><span data-stu-id="ef0e4-126">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ef0e4-127">Om du växlar från riktad version tillbaka till standardversionen kan det hända att vissa användare förlorar åtkomst till funktioner som inte har inkluderats i standardversionen än.</span><span class="sxs-lookup"><span data-stu-id="ef0e4-127">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="ef0e4-128">Riktad version</span><span class="sxs-lookup"><span data-stu-id="ef0e4-128">Targeted release</span></span>

<span data-ttu-id="ef0e4-p106">Om du väljer det här alternativet kan du och andra användare i organisationen vara bland de första att ta del av de allra senaste uppdateringarna och bidra till att utforma produkter genom att ge återkoppling i ett tidigt skede. Du kan välja om du vill att bara vissa personer, eller alla i organisationen ska få dessa tidiga uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="ef0e4-p106">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ef0e4-p107">Stora eller komplexa uppdateringar kan genomföras under en längre tid, så att inga användare påverkas negativt. Det finns ingen garanti för att en versionsuppdatering ska följa en exakt tidslinje.</span><span class="sxs-lookup"><span data-stu-id="ef0e4-p107">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="ef0e4-133">Riktad version för hela organisationen</span><span class="sxs-lookup"><span data-stu-id="ef0e4-133">Targeted release for entire organization</span></span>

<span data-ttu-id="ef0e4-134">Om du [konfigurerar utgivningsalternativet i administrationscentret](#set-up-the-release-option-in-the-admin-center) för det här alternativet får alla användare upplevelsen av riktad frigöring.</span><span class="sxs-lookup"><span data-stu-id="ef0e4-134">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="ef0e4-135">Om organisationen har fler än 300 användare rekommenderar vi att en provprenumeration används för det här alternativet.</span><span class="sxs-lookup"><span data-stu-id="ef0e4-135">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="ef0e4-136">Kontakta Microsoft om du behöver information om provprenumerationer.</span><span class="sxs-lookup"><span data-stu-id="ef0e4-136">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="ef0e4-137">Riktad version för valda användare</span><span class="sxs-lookup"><span data-stu-id="ef0e4-137">Targeted release for selected users</span></span>

<span data-ttu-id="ef0e4-138">Om du [konfigurerar versionsalternativet i administrationscentret](#set-up-the-release-option-in-the-admin-center) för det här alternativet kan du definiera specifika användare, vanligtvis avancerade användare, för att få tidig åtkomst till funktioner och funktioner.</span><span class="sxs-lookup"><span data-stu-id="ef0e4-138">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="ef0e4-139">Fördelar med Riktad version</span><span class="sxs-lookup"><span data-stu-id="ef0e4-139">Benefits of Targeted release</span></span>

<span data-ttu-id="ef0e4-140">Riktad version ger administratörer, ändringshanterare och alla andra som är ansvariga för Office 365-uppdateringar möjlighet att förbereda sig på de kommande ändringarna genom att låta dem:</span><span class="sxs-lookup"><span data-stu-id="ef0e4-140">Targeted release allows admins, change managers, or anyone else responsible for Office 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="ef0e4-141">Testa och validera nya uppdateringar innan de släpps till alla användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="ef0e4-141">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="ef0e4-142">Förbereda användarmeddelanden och dokumentation innan uppdateringar släpps i hela världen.</span><span class="sxs-lookup"><span data-stu-id="ef0e4-142">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="ef0e4-143">Förbereda den interna supporten på kommande ändringar.</span><span class="sxs-lookup"><span data-stu-id="ef0e4-143">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="ef0e4-144">Genomföra efterlevnads- och säkerhetsgranskningar.</span><span class="sxs-lookup"><span data-stu-id="ef0e4-144">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="ef0e4-145">Använda funktionskontroller och styra när användare får uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="ef0e4-145">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="ef0e4-146">Konfigurera utgivningsalternativet i administrationscentret</span><span class="sxs-lookup"><span data-stu-id="ef0e4-146">Set up the release option in the admin center</span></span>

<span data-ttu-id="ef0e4-p109">Du kan ändra hur organisationen får Office 365-uppdateringar genom att följa de här stegen. Du måste vara global administratör i Office 365 för att anmäla dig.</span><span class="sxs-lookup"><span data-stu-id="ef0e4-p109">You can change how your organization receives Office 365 updates by following these steps. You have to be a global admin in Office 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ef0e4-p110">Det kan ta upp till ett dygn innan nedanstående ändringar verkställs i Office 365. Om organisationen tidigare har använt riktad version och du vill inaktivera detta kan det hända att vissa användare förlorar tillgång till funktioner som inte ingår i standardversionen än.</span><span class="sxs-lookup"><span data-stu-id="ef0e4-p110">It can take up to 24 hours for the below changes to take effect in Office 365. If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="ef0e4-151">I administrationscentret går du > till**inställningsinställningen** **Inställningar**och väljer **Frigörinställningar**under fliken **Organisationsprofil** .</span><span class="sxs-lookup"><span data-stu-id="ef0e4-151">In the admin center, go to the **Settings** > **Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="ef0e4-152">Om du vill inaktivera riktad version väljer du **Standard-release**och väljer sedan **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="ef0e4-152">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="ef0e4-153">Om du vill aktivera riktad version för alla användare i organisationen väljer du **Riktad version för alla**och väljer sedan Spara **ändringar**.</span><span class="sxs-lookup"><span data-stu-id="ef0e4-153">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="ef0e4-154">Om du vill aktivera riktad version för vissa personer i organisationen väljer du **Riktad version för valda användare**och väljer sedan Spara **ändringar**.</span><span class="sxs-lookup"><span data-stu-id="ef0e4-154">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="ef0e4-155">Välj **Välj användare** om du vill lägga till användare en i taget eller Ladda upp **användare** om du vill lägga till dem i grupp.</span><span class="sxs-lookup"><span data-stu-id="ef0e4-155">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="ef0e4-156">När du är klar med att lägga till användare väljer du **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="ef0e4-156">When you're done adding users, select **Save changes**.</span></span>



## <a name="get-the-targeted-release-version-of-office"></a><span data-ttu-id="ef0e4-157">Skaffa den riktade versionen av Office</span><span class="sxs-lookup"><span data-stu-id="ef0e4-157">Get the Targeted release version of Office</span></span>

<span data-ttu-id="ef0e4-p111">Du kan installera en riktad version av Office med hjälp av de här [anvisningarna](https://support.office.com/article/4dd8ba40-73c0-4468-b778-c7b744d03ead). Detta ger dig snabb åtkomst till de nya funktionerna i Office 2016 för Windows-datorer.</span><span class="sxs-lookup"><span data-stu-id="ef0e4-p111">To install a targeted release build of Office, [follow these steps](https://support.office.com/article/4dd8ba40-73c0-4468-b778-c7b744d03ead). This gives you early access to the new features of Office 2016 for Windows desktops.</span></span>
  
## <a name="learn-more"></a><span data-ttu-id="ef0e4-160">Mer information</span><span class="sxs-lookup"><span data-stu-id="ef0e4-160">Learn more</span></span>

<span data-ttu-id="ef0e4-161">Upptäck hur du [hanterar meddelanden](https://docs.microsoft.com/office365/admin/manage/message-center) i Ditt [Office 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) för att få aviseringar om kommande Office 365-uppdateringar och versioner.</span><span class="sxs-lookup"><span data-stu-id="ef0e4-161">Discover how to [manage messages](https://docs.microsoft.com/office365/admin/manage/message-center) in your [Office 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Office 365 updates and releases.</span></span>
