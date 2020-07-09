---
title: Vanliga frågor och svar om centraliserad distribution
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Granska svaren på vanliga frågor om centraliserad distribution från administrationscentret för Microsoft 365.
ms.openlocfilehash: 2d9a3c6f2cfe9418cc83cbd0f29537e5533c4257
ms.sourcegitcommit: 3951147f74510e2ead6c11ceab92854f0937426b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083568"
---
# <a name="centralized-deployment-faq"></a><span data-ttu-id="43e91-103">Vanliga frågor och svar om centraliserad distribution</span><span class="sxs-lookup"><span data-stu-id="43e91-103">Centralized Deployment FAQ</span></span>

<span data-ttu-id="43e91-104">Centraliserad distribution är det rekommenderade sättet för en Office 365-administratör att distribuera Office-tillägg (Word, Excel, PowerPoint och Outlook) till användare och grupper inom en organisation, förutsatt att organisationen uppfyller alla krav för att använda centraliserad distribution enligt beskrivningen i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="43e91-104">Centralized Deployment is the recommended way for an Office 365 admin to deploy Office add-ins (Word, Excel, PowerPoint, and Outlook) to users and groups within an organization, provided the organization meets all requirements for using Centralized Deployment as outlined in this article.</span></span>   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a><span data-ttu-id="43e91-105">Hur vet jag om min organisation har konfigurerats för centraliserad distribution?</span><span class="sxs-lookup"><span data-stu-id="43e91-105">How do I know if my organization is set up for Centralized Deployment?</span></span>  

<span data-ttu-id="43e91-106">Centraliserad distribution av tillägg kräver att användare använder Microsoft 365 Apps för företag (och är inloggade på Office med hjälp av sina organisationslogguppgifter) och har Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="43e91-106">Centralized deployment of add-ins requires that users are using Microsoft 365 Apps for enterprise (and are signed into Office using their organizational log-in credentials) and have Exchange Online mailboxes.</span></span> <span data-ttu-id="43e91-107">Din prenumerationskatalog måste antingen vara i eller federerade till Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="43e91-107">Your subscription directory must either be in, or federated to, Azure Active Directory.</span></span>  
 
<span data-ttu-id="43e91-108">Centraliserad distribution stöds endast för onlinepostlådor.</span><span class="sxs-lookup"><span data-stu-id="43e91-108">Centralized Deployment is only supported for online mailboxes.</span></span> <span data-ttu-id="43e91-109">Det stöder inte distribution till lokala Exchange-postlådor.</span><span class="sxs-lookup"><span data-stu-id="43e91-109">It does not support deployment to on-premises Exchange mailboxes.</span></span>
 
<span data-ttu-id="43e91-110">Du kan använda den [centraliserade kompatibilitetskontrollen](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)för distribution   för att avgöra om din prenumeration är kvalificerad.</span><span class="sxs-lookup"><span data-stu-id="43e91-110">You can use the [Centralized Deployment Compatibility Checker](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker) to determine if your subscription is eligible.</span></span> 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a><span data-ttu-id="43e91-111">Hur inriktar du dig på tilläggsanvändartilldelningar med centraliserad distribution?</span><span class="sxs-lookup"><span data-stu-id="43e91-111">How do you target add-in user assignments with Centralized Deployment?</span></span>  

<span data-ttu-id="43e91-112">Centraliserad distribution stöder tilldelningar till enskilda användare, grupper och alla i klienten.</span><span class="sxs-lookup"><span data-stu-id="43e91-112">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="43e91-113">Centraliserad distribution kan användas för användare i grupper eller grupper på den högsta nivån utan överordnade grupper, men inte för användare i kapslade grupper eller grupper som har överordnade grupper.</span><span class="sxs-lookup"><span data-stu-id="43e91-113">Centralized Deployment can be used for users in top-level groups or groups without parent groups, but not for users in nested groups or groups that have parent groups.</span></span> <span data-ttu-id="43e91-114">Centraliserad distribution är också en del av de flesta Azure Active Directory-grupper, inklusive Office 365-grupper, distributionslistor och säkerhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="43e91-114">Centralized Deployment is also part of most Azure Active Directory groups, including Office 365 Groups, distribution lists, and security groups.</span></span>  

<span data-ttu-id="43e91-115">Det är bättre att använda grupptilldelningar i stället för enskilda användartilldelning för enklare hantering.</span><span class="sxs-lookup"><span data-stu-id="43e91-115">It is better to use groups assignments instead of individual user assignment for easier management.</span></span>
 
<span data-ttu-id="43e91-116">Mer information finns i [Användar- och grupptilldelningar](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments).</span><span class="sxs-lookup"><span data-stu-id="43e91-116">For more details, see [User and Group assignments](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments).</span></span>  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a><span data-ttu-id="43e91-117">Hur lång tid tar det för tillägg att visas för alla användare?</span><span class="sxs-lookup"><span data-stu-id="43e91-117">How long does it take for add-ins to show up for all users?</span></span>  

<span data-ttu-id="43e91-118">Det kan ta upp till 24 timmar innan ett tillägg visas för alla användare.</span><span class="sxs-lookup"><span data-stu-id="43e91-118">It can take up to 24 hours for an add-in to show up for all users.</span></span> <span data-ttu-id="43e91-119">Det kan ta lika lång tid för tilläggsuppdateringar, ändringar från aktivera eller inaktivera eller tilläggsborttagningar.</span><span class="sxs-lookup"><span data-stu-id="43e91-119">It can take the same amount of time for add-in updates, changes from turn on or turn off, or add-in removals.</span></span> 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a><span data-ttu-id="43e91-120">Hur hanterar jag användaråtkomst till tillägg för min organisation som administratör?</span><span class="sxs-lookup"><span data-stu-id="43e91-120">As an administrator, how do I manage the user access to add-ins for my organization?</span></span>

<span data-ttu-id="43e91-121">För enkel distribution av tillägg till användare, grupper eller till hela organisationen rekommenderar vi administratörer att använda centraliserad distribution.</span><span class="sxs-lookup"><span data-stu-id="43e91-121">For easy deployment of add-ins to users, groups, or to your entire organization, we recommend administrators use Centralized Deployment.</span></span>

<span data-ttu-id="43e91-122">Mer information om hur du hanterar användaråtkomst finns i</span><span class="sxs-lookup"><span data-stu-id="43e91-122">For more information about managing user access, see</span></span> </br><span data-ttu-id="43e91-123">[Förhindra hämtning av tillägg genom att stänga av Office Store för alla klienter (utom Outlook)](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook) och</span><span class="sxs-lookup"><span data-stu-id="43e91-123">[Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook) and</span></span> </br><span data-ttu-id="43e91-124">[Ange de administratörer och användare som kan installera och hantera tillägg för Outlook](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins?redirectedfrom=MSDN).</span><span class="sxs-lookup"><span data-stu-id="43e91-124">[Specify the administrators and users who can install and manage add-ins for Outlook](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins?redirectedfrom=MSDN).</span></span>

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a><span data-ttu-id="43e91-125">Ger centraliserad distribution administratörer flexibiliteten att välja distributionsmetod för Outlook-tillägg?</span><span class="sxs-lookup"><span data-stu-id="43e91-125">Will Centralized Deployment provide admins the flexibility to choose the deployment method for Outlook add-ins?</span></span>  

<span data-ttu-id="43e91-126">Ja.</span><span class="sxs-lookup"><span data-stu-id="43e91-126">Yes.</span></span> <span data-ttu-id="43e91-127">Centraliserad distribution ger administratörer flexibiliteten att välja en av tre distributionsmetoder för Outlook-tillägg under tilläggsdistributionen:</span><span class="sxs-lookup"><span data-stu-id="43e91-127">Centralized Deployment provides admins the flexibility to choose one of three deployment methods for Outlook add-ins during add-in deployment:</span></span>

<span data-ttu-id="43e91-128">**Fast (standard)**   Tillägget distribueras automatiskt till de tilldelade användarna och de kan inte ta bort det.</span><span class="sxs-lookup"><span data-stu-id="43e91-128">**Fixed (Default)**  The add-in is deployed automatically to the assigned users, and they cannot remove it.</span></span>  
 
<span data-ttu-id="43e91-129">**Tillgänglig** Användare kan installera tillägget i Outlook genom att välja Hem > Få fler tillägg > Admin-hanterade.</span><span class="sxs-lookup"><span data-stu-id="43e91-129">**Available** Users can install the add-in in Outlook by choosing Home > Get More add-ins > Admin-managed.</span></span>   
 
<span data-ttu-id="43e91-130">**Valfritt** Tillägget distribueras automatiskt till de tilldelade användarna, men de kan välja att ta bort det.</span><span class="sxs-lookup"><span data-stu-id="43e91-130">**Optional** The add-in is deployed automatically to the assigned users, but they can choose to remove it.</span></span>  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a><span data-ttu-id="43e91-131">Kan administratörer uppdatera LOB-tillägg (Line-of-Business)?</span><span class="sxs-lookup"><span data-stu-id="43e91-131">Can admins update Line-of-Business (LOB) add-ins?</span></span>  

<span data-ttu-id="43e91-132">Ja.</span><span class="sxs-lookup"><span data-stu-id="43e91-132">Yes.</span></span> <span data-ttu-id="43e91-133">Administratörer kan ladda upp en ny manifestfil för att stödja metadataändringar för administratörsbe distribuerade LOB-tillägg. Tillägget uppdateras nästa gång Office-programmen startas.</span><span class="sxs-lookup"><span data-stu-id="43e91-133">Admins can upload a new manifest file to support metadata changes for admin-deployed LOB add-ins. The add-in updates the next time the Office applications starts.</span></span> <span data-ttu-id="43e91-134">Webbprogrammet kan ändras när som helst.</span><span class="sxs-lookup"><span data-stu-id="43e91-134">The web application can change at any time.</span></span>  
 
<span data-ttu-id="43e91-135">Mer information finns [i tillägg för företagslinje](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#security-of-office-add-ins).</span><span class="sxs-lookup"><span data-stu-id="43e91-135">For more information, see [line-of-business add-in](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#security-of-office-add-ins).</span></span>  

## <a name="can-admins-turn-off-add-ins"></a><span data-ttu-id="43e91-136">Kan administratörer stänga av tillägg?</span><span class="sxs-lookup"><span data-stu-id="43e91-136">Can admins turn off add-ins?</span></span>  

<span data-ttu-id="43e91-137">Ja.</span><span class="sxs-lookup"><span data-stu-id="43e91-137">Yes.</span></span> <span data-ttu-id="43e91-138">Administratörer kan aktivera eller inaktivera de tillägg som de distribuerar för alla användare från Microsofts administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="43e91-138">Admins can turn on or off the add-ins they deploy for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="43e91-139">Mer information finns [i Tilläggstillstånd](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#add-in-states).</span><span class="sxs-lookup"><span data-stu-id="43e91-139">For more information, see [Add-in states](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#add-in-states).</span></span>  

##  <a name="can-admins-delete-or-remove-add-ins"></a><span data-ttu-id="43e91-140">Kan administratörer ta bort eller ta bort tillägg?</span><span class="sxs-lookup"><span data-stu-id="43e91-140">Can admins delete or remove add-ins?</span></span>

<span data-ttu-id="43e91-141">Ja.</span><span class="sxs-lookup"><span data-stu-id="43e91-141">Yes.</span></span> <span data-ttu-id="43e91-142">Administratörer kan ta bort tillägg som de har distribuerat för alla användare från Microsofts administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="43e91-142">Admins can delete add-ins they deployed for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="43e91-143">Mer information finns [i Ta bort tillägget](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#delete-the-add-in).</span><span class="sxs-lookup"><span data-stu-id="43e91-143">For more information, see [Delete the add-in](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#delete-the-add-in).</span></span> 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a><span data-ttu-id="43e91-144">Kan administratörer distribuera betalda tillägg från Office Store med centraliserad distribution?</span><span class="sxs-lookup"><span data-stu-id="43e91-144">Can admins deploy paid add-ins from the Office Store using Centralized Deployment?</span></span> 

<span data-ttu-id="43e91-145">Nej.</span><span class="sxs-lookup"><span data-stu-id="43e91-145">No.</span></span> <span data-ttu-id="43e91-146">Du kan inte distribuera betalda tillägg från Office Store med centraliserad distribution just nu.</span><span class="sxs-lookup"><span data-stu-id="43e91-146">You can't deploy paid add-ins from the Office Store using Centralized Deployment at this time.</span></span>  
 
<span data-ttu-id="43e91-147">Vi föreslår att du når ut till ISV-utvecklaren för det betalda tillägget för att begära en manifestfil eller en URL.</span><span class="sxs-lookup"><span data-stu-id="43e91-147">We suggest reaching out to the ISV Developer for the paid add-in to request a manifest file or a URL.</span></span> <span data-ttu-id="43e91-148">Klientadministratören kan sedan distribuera tillägget som ett LOB-tillägg med centraliserad distribution.</span><span class="sxs-lookup"><span data-stu-id="43e91-148">The tenant admin can then deploy the add-in as a LOB add-in using Centralized Deployment.</span></span>
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a><span data-ttu-id="43e91-149">Vilken administratörsroll behöver jag hantera tillägg för min organisation?</span><span class="sxs-lookup"><span data-stu-id="43e91-149">Which admin role do I need to manage add-ins for my organization?</span></span>  

<span data-ttu-id="43e91-150">Du måste ha rollen Global administratör för att hantera tillägg. Om du är den person som köpte din Microsoft 365 för företag-prenumeration är du global administratör.</span><span class="sxs-lookup"><span data-stu-id="43e91-150">You must have the Global admin role to manage add-ins. If you're the person who purchased your Microsoft 365 for business subscription, you are the Global admin.</span></span> 
 
<span data-ttu-id="43e91-151">Din prenumeration levereras med en uppsättning administratörsroller som du kan tilldela andra användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="43e91-151">Your subscription comes with a set of admin roles that you can assign to other users in your organization.</span></span> <span data-ttu-id="43e91-152">Varje administratörsroll mappar till vanliga affärsfunktioner och ger personer i organisationen behörighet att utföra specifika uppgifter i Microsoft 365-administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="43e91-152">Each admin role maps to common business functions and gives people in your organization permissions to perform specific tasks in the Microsoft 365 admin center.</span></span>  
 
<span data-ttu-id="43e91-153">Mer information finns i [Tilldela administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="43e91-153">For more information, see [Assign admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide).</span></span>  