---
title: Vanliga frågor och svar om centraliserad distribution
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Läs svaren på vanliga frågor om centraliserad distribution från administrationscentret för Microsoft 365.
ms.openlocfilehash: 60d7a91da738803976b6823009450124d7b57814
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579308"
---
# <a name="centralized-deployment-faq"></a><span data-ttu-id="ecc60-103">Vanliga frågor och svar om centraliserad distribution</span><span class="sxs-lookup"><span data-stu-id="ecc60-103">Centralized Deployment FAQ</span></span>

<span data-ttu-id="ecc60-104">Centraliserad distribution är det rekommenderade sättet för Office 365-administratörer att distribuera Office-tillägg (Word, Excel, PowerPoint och Outlook) till användare och grupper inom en organisation, förutsatt att organisationen uppfyller alla krav för användning av centraliserad distribution som beskrivs i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="ecc60-104">Centralized Deployment is the recommended way for an Office 365 admin to deploy Office add-ins (Word, Excel, PowerPoint, and Outlook) to users and groups within an organization, provided the organization meets all requirements for using Centralized Deployment as outlined in this article.</span></span>   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a><span data-ttu-id="ecc60-105">Hur vet jag om min organisation är konfigurerad för centraliserad distribution?</span><span class="sxs-lookup"><span data-stu-id="ecc60-105">How do I know if my organization is set up for Centralized Deployment?</span></span>  

<span data-ttu-id="ecc60-106">Centraliserad distribution av tillägg kräver att användarna använder Microsoft 365-program för företag (och är inloggade på Office med inloggningsuppgifter för organisationen) och har Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="ecc60-106">Centralized deployment of add-ins requires that users are using Microsoft 365 Apps for enterprise (and are signed into Office using their organizational log-in credentials) and have Exchange Online mailboxes.</span></span> <span data-ttu-id="ecc60-107">Prenumerationskatalogen måste finnas i eller vara extern till Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ecc60-107">Your subscription directory must either be in, or federated to, Azure Active Directory.</span></span>  
 
<span data-ttu-id="ecc60-108">Centraliserad distribution stöds endast för onlinepostlådor.</span><span class="sxs-lookup"><span data-stu-id="ecc60-108">Centralized Deployment is only supported for online mailboxes.</span></span> <span data-ttu-id="ecc60-109">Den har inte stöd för distribution till lokala Exchange-postlådor.</span><span class="sxs-lookup"><span data-stu-id="ecc60-109">It does not support deployment to on-premises Exchange mailboxes.</span></span>

<span data-ttu-id="ecc60-110">Du kan använda [kompatibilitetskontrollen för centraliserad distribution för att](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)   avgöra om din prenumeration är berättigad.</span><span class="sxs-lookup"><span data-stu-id="ecc60-110">You can use the [Centralized Deployment Compatibility Checker](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker) to determine if your subscription is eligible.</span></span> 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a><span data-ttu-id="ecc60-111">Hur riktar du användartilldelningar för tillägg med centraliserad distribution?</span><span class="sxs-lookup"><span data-stu-id="ecc60-111">How do you target add-in user assignments with Centralized Deployment?</span></span>  

<span data-ttu-id="ecc60-112">Centraliserad distribution har stöd för tilldelningar till enskilda användare, grupper och alla i klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="ecc60-112">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="ecc60-113">Centraliserad distribution kan användas för användare i grupper på översta nivå eller grupper utan överordnade grupper, men inte för användare i kapslade grupper eller grupper som har överordnade grupper.</span><span class="sxs-lookup"><span data-stu-id="ecc60-113">Centralized Deployment can be used for users in top-level groups or groups without parent groups, but not for users in nested groups or groups that have parent groups.</span></span> <span data-ttu-id="ecc60-114">Centraliserad distribution ingår också i de flesta Azure Active Directory-grupper, inklusive Office 365-grupper, distributionslistor och säkerhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="ecc60-114">Centralized Deployment is also part of most Azure Active Directory groups, including Office 365 Groups, distribution lists, and security groups.</span></span>  

<span data-ttu-id="ecc60-115">Det är bättre att använda grupptilldelningar i stället för tilldelning av enskilda användare för att underlätta hanteringen.</span><span class="sxs-lookup"><span data-stu-id="ecc60-115">It is better to use groups assignments instead of individual user assignment for easier management.</span></span>
 
<span data-ttu-id="ecc60-116">Mer information finns i [Användar- och grupptilldelningar.](./centralized-deployment-of-add-ins.md?view=o365-worldwide#user-and-group-assignments)</span><span class="sxs-lookup"><span data-stu-id="ecc60-116">For more details, see [User and Group assignments](./centralized-deployment-of-add-ins.md?view=o365-worldwide#user-and-group-assignments).</span></span>  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a><span data-ttu-id="ecc60-117">Hur lång tid tar det innan tillägg visas för alla användare?</span><span class="sxs-lookup"><span data-stu-id="ecc60-117">How long does it take for add-ins to show up for all users?</span></span>  

<span data-ttu-id="ecc60-118">Det kan ta upp till 24 timmar innan ett tillägg visas för alla användare.</span><span class="sxs-lookup"><span data-stu-id="ecc60-118">It can take up to 24 hours for an add-in to show up for all users.</span></span> <span data-ttu-id="ecc60-119">Det kan ta lika lång tid för tilläggsuppdateringar, ändringar från att aktivera eller inaktivera, eller att ta bort tillägg.</span><span class="sxs-lookup"><span data-stu-id="ecc60-119">It can take the same amount of time for add-in updates, changes from turn on or turn off, or add-in removals.</span></span> 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a><span data-ttu-id="ecc60-120">Hur hanterar jag användaråtkomst som administratör till tillägg för min organisation?</span><span class="sxs-lookup"><span data-stu-id="ecc60-120">As an administrator, how do I manage the user access to add-ins for my organization?</span></span>

<span data-ttu-id="ecc60-121">För enkel distribution av tillägg till användare, grupper eller till hela organisationen rekommenderar vi att administratörer använder centraliserad distribution.</span><span class="sxs-lookup"><span data-stu-id="ecc60-121">For easy deployment of add-ins to users, groups, or to your entire organization, we recommend administrators use Centralized Deployment.</span></span>

<span data-ttu-id="ecc60-122">Mer information om hur du hanterar användaråtkomst finns i:</span><span class="sxs-lookup"><span data-stu-id="ecc60-122">For more information about managing user access, see:</span></span>
 - [<span data-ttu-id="ecc60-123">Förhindra tilläggsnedladdningar genom att inaktivera Office Store för alla klienter (utom Outlook)</span><span class="sxs-lookup"><span data-stu-id="ecc60-123">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>](./manage-addins-in-the-admin-center.md#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)
 - [<span data-ttu-id="ecc60-124">Ange de administratörer och användare som kan installera och hantera tillägg för Outlook</span><span class="sxs-lookup"><span data-stu-id="ecc60-124">Specify the administrators and users who can install and manage add-ins for Outlook</span></span>](/Exchange/specify-who-can-install-and-manage-add-ins-2013-help)

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a><span data-ttu-id="ecc60-125">Ger centraliserad distribution administratörer flexibiliteten att välja distributionsmetod för Outlook-tillägg?</span><span class="sxs-lookup"><span data-stu-id="ecc60-125">Will Centralized Deployment provide admins the flexibility to choose the deployment method for Outlook add-ins?</span></span>  

<span data-ttu-id="ecc60-126">Ja.</span><span class="sxs-lookup"><span data-stu-id="ecc60-126">Yes.</span></span> <span data-ttu-id="ecc60-127">Centraliserad distribution ger administratörer möjlighet att välja någon av tre distributionsmetoder för Outlook-tillägg under distributionen:</span><span class="sxs-lookup"><span data-stu-id="ecc60-127">Centralized Deployment provides admins the flexibility to choose one of three deployment methods for Outlook add-ins during add-in deployment:</span></span>

<span data-ttu-id="ecc60-128">**Fast (standard)**   Tillägget distribueras automatiskt till de tilldelade användarna och de kan inte ta bort det.</span><span class="sxs-lookup"><span data-stu-id="ecc60-128">**Fixed (Default)**  The add-in is deployed automatically to the assigned users, and they cannot remove it.</span></span>  
 
<span data-ttu-id="ecc60-129">**Tillgänglig** Användarna kan installera tillägget i Outlook genom att välja Start > Hämta fler tillägg och **> administratör hanterade.**</span><span class="sxs-lookup"><span data-stu-id="ecc60-129">**Available** Users can install the add-in in Outlook by choosing **Home > Get More add-ins > Admin-managed**.</span></span>
 
<span data-ttu-id="ecc60-130">**Valfritt** Tillägget distribueras automatiskt till de tilldelade användarna, men de kan välja att ta bort det.</span><span class="sxs-lookup"><span data-stu-id="ecc60-130">**Optional** The add-in is deployed automatically to the assigned users, but they can choose to remove it.</span></span>  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a><span data-ttu-id="ecc60-131">Kan administratörer uppdatera verksamhetsbaserade tillägg?</span><span class="sxs-lookup"><span data-stu-id="ecc60-131">Can admins update Line-of-Business (LOB) add-ins?</span></span>  

<span data-ttu-id="ecc60-132">Ja.</span><span class="sxs-lookup"><span data-stu-id="ecc60-132">Yes.</span></span> <span data-ttu-id="ecc60-133">Administratörer kan ladda upp en ny manifestfil för att stödja metadataändringar för administratörs deployerade LOB-tillägg. Tillägget uppdateras nästa gång Office-programmen startas.</span><span class="sxs-lookup"><span data-stu-id="ecc60-133">Admins can upload a new manifest file to support metadata changes for admin-deployed LOB add-ins. The add-in updates the next time the Office applications starts.</span></span> <span data-ttu-id="ecc60-134">Webbprogrammet kan ändras när som helst.</span><span class="sxs-lookup"><span data-stu-id="ecc60-134">The web application can change at any time.</span></span>  
 
<span data-ttu-id="ecc60-135">Mer information finns [i verksamhets tillägg.](./manage-addins-in-the-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="ecc60-135">For more information, see [line-of-business add-in](./manage-addins-in-the-admin-center.md).</span></span>  

## <a name="can-admins-turn-off-add-ins"></a><span data-ttu-id="ecc60-136">Kan administratörer inaktivera tillägg?</span><span class="sxs-lookup"><span data-stu-id="ecc60-136">Can admins turn off add-ins?</span></span>  

<span data-ttu-id="ecc60-137">Ja.</span><span class="sxs-lookup"><span data-stu-id="ecc60-137">Yes.</span></span> <span data-ttu-id="ecc60-138">Administratörer kan aktivera eller inaktivera tillägg som de distribuerar för alla användare i administrationscentret för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ecc60-138">Admins can turn on or off the add-ins they deploy for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="ecc60-139">Mer information finns i [Tilläggsstater](./manage-addins-in-the-admin-center.md#add-in-states).</span><span class="sxs-lookup"><span data-stu-id="ecc60-139">For more information, see [Add-in states](./manage-addins-in-the-admin-center.md#add-in-states).</span></span>  

##  <a name="can-admins-delete-or-remove-add-ins"></a><span data-ttu-id="ecc60-140">Kan administratörer ta bort eller ta bort tillägg?</span><span class="sxs-lookup"><span data-stu-id="ecc60-140">Can admins delete or remove add-ins?</span></span>

<span data-ttu-id="ecc60-141">Ja.</span><span class="sxs-lookup"><span data-stu-id="ecc60-141">Yes.</span></span> <span data-ttu-id="ecc60-142">Administratörer kan ta bort tillägg som de har distribuerat för alla användare från Microsofts administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="ecc60-142">Admins can delete add-ins they deployed for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="ecc60-143">Mer information finns i [Ta bort ett tillägg.](./manage-addins-in-the-admin-center.md#delete-an-add-in)</span><span class="sxs-lookup"><span data-stu-id="ecc60-143">For more information, see [Delete an add-in](./manage-addins-in-the-admin-center.md#delete-an-add-in).</span></span> 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a><span data-ttu-id="ecc60-144">Kan administratörer distribuera betalda tillägg från Office Store med centraliserad distribution?</span><span class="sxs-lookup"><span data-stu-id="ecc60-144">Can admins deploy paid add-ins from the Office Store using Centralized Deployment?</span></span> 

<span data-ttu-id="ecc60-145">Nej.</span><span class="sxs-lookup"><span data-stu-id="ecc60-145">No.</span></span> <span data-ttu-id="ecc60-146">Du kan för stunden inte distribuera betalda tillägg från Office Store med centraliserad distribution.</span><span class="sxs-lookup"><span data-stu-id="ecc60-146">You can't deploy paid add-ins from the Office Store using Centralized Deployment at this time.</span></span>  
 
<span data-ttu-id="ecc60-147">Vi föreslår att ISV-utvecklaren tar del av det betalda tillägget för att begära en manifestfil eller en URL.</span><span class="sxs-lookup"><span data-stu-id="ecc60-147">We suggest reaching out to the ISV Developer for the paid add-in to request a manifest file or a URL.</span></span> <span data-ttu-id="ecc60-148">Klientorganisationens administratör kan sedan distribuera tillägget som ett LOB-tillägg med hjälp av centraliserad distribution.</span><span class="sxs-lookup"><span data-stu-id="ecc60-148">The tenant admin can then deploy the add-in as a LOB add-in using Centralized Deployment.</span></span>
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a><span data-ttu-id="ecc60-149">Vilken administratörsroll behöver jag för att hantera tillägg för min organisation?</span><span class="sxs-lookup"><span data-stu-id="ecc60-149">Which admin role do I need to manage add-ins for my organization?</span></span>  

<span data-ttu-id="ecc60-150">Global administratör är den rekommenderade rollen med fullständig åtkomst till livscykeln för hantering av tillägg.</span><span class="sxs-lookup"><span data-stu-id="ecc60-150">Global Admin is the recommended role with complete access to add-in management lifecycle.</span></span> <span data-ttu-id="ecc60-151">Andra administratörsroller har begränsad åtkomst till livscykeln för distribution av tillägg.</span><span class="sxs-lookup"><span data-stu-id="ecc60-151">Other Admin roles have a limited access to add-in deployment lifecycle.</span></span> <span data-ttu-id="ecc60-152">Om du är den person som köpte Microsoft 365 för företag-prenumerationen är du global administratör.</span><span class="sxs-lookup"><span data-stu-id="ecc60-152">If you're the person who purchased your Microsoft 365 for business subscription, you are the Global admin.</span></span> 
 
<span data-ttu-id="ecc60-153">Din prenumeration levereras med en uppsättning administratörsroller som du kan tilldela andra användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="ecc60-153">Your subscription comes with a set of admin roles that you can assign to other users in your organization.</span></span> <span data-ttu-id="ecc60-154">Varje administratörsroll mappar till vanliga affärsfunktioner och ger personerna i organisationen behörighet att utföra särskilda uppgifter i administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ecc60-154">Each admin role maps to common business functions and gives people in your organization permissions to perform specific tasks in the Microsoft 365 admin center.</span></span>  
 
<span data-ttu-id="ecc60-155">Mer information finns i Tilldela [administratörsroller.](../add-users/assign-admin-roles.md?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="ecc60-155">For more information, see [Assign admin roles](../add-users/assign-admin-roles.md?view=o365-worldwide).</span></span> 