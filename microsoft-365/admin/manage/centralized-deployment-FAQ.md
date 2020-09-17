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
description: Läs vanliga frågor om centraliserad distribution från administrations centret för Microsoft 365.
ms.openlocfilehash: 555496f15663b6607ebc785498bdc94b5e51b9c9
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948694"
---
# <a name="centralized-deployment-faq"></a><span data-ttu-id="694b5-103">Vanliga frågor och svar om centraliserad distribution</span><span class="sxs-lookup"><span data-stu-id="694b5-103">Centralized Deployment FAQ</span></span>

<span data-ttu-id="694b5-104">Centraliserad distribution är det rekommenderade sättet för en Office 365-administratör att distribuera Office-tillägg (Word, Excel, PowerPoint och Outlook) till användare och grupper inom en organisation, förutsatt att organisationen uppfyller alla krav för centraliserad distribution enligt den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="694b5-104">Centralized Deployment is the recommended way for an Office 365 admin to deploy Office add-ins (Word, Excel, PowerPoint, and Outlook) to users and groups within an organization, provided the organization meets all requirements for using Centralized Deployment as outlined in this article.</span></span>   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a><span data-ttu-id="694b5-105">Hur vet jag om min organisation är konfigurerad för centraliserad distribution?</span><span class="sxs-lookup"><span data-stu-id="694b5-105">How do I know if my organization is set up for Centralized Deployment?</span></span>  

<span data-ttu-id="694b5-106">Centraliserad distribution av tillägg kräver att användarna använder Microsoft 365-appar för företag (och är inloggade på Office med deras organisations inloggnings uppgifter) och har Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="694b5-106">Centralized deployment of add-ins requires that users are using Microsoft 365 Apps for enterprise (and are signed into Office using their organizational log-in credentials) and have Exchange Online mailboxes.</span></span> <span data-ttu-id="694b5-107">Abonnemangs katalogen måste antingen vara i eller federerad till Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="694b5-107">Your subscription directory must either be in, or federated to, Azure Active Directory.</span></span>  
 
<span data-ttu-id="694b5-108">Centraliserad distribution stöds endast för Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="694b5-108">Centralized Deployment is only supported for online mailboxes.</span></span> <span data-ttu-id="694b5-109">Den stöder inte distribution till lokala Exchange-postlådor.</span><span class="sxs-lookup"><span data-stu-id="694b5-109">It does not support deployment to on-premises Exchange mailboxes.</span></span>

<span data-ttu-id="694b5-110">Du kan använda [kompatibilitetskontrollen för centraliserad distribution](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)   för att ta reda på om ditt abonnemang är kvalificerat.</span><span class="sxs-lookup"><span data-stu-id="694b5-110">You can use the [Centralized Deployment Compatibility Checker](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker) to determine if your subscription is eligible.</span></span> 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a><span data-ttu-id="694b5-111">Hur kan du lägga in användar tilldelningar för användare med centraliserad distribution?</span><span class="sxs-lookup"><span data-stu-id="694b5-111">How do you target add-in user assignments with Centralized Deployment?</span></span>  

<span data-ttu-id="694b5-112">Centraliserad distribution stöder tilldelningar till enskilda användare, grupper och alla i klient organisationen.</span><span class="sxs-lookup"><span data-stu-id="694b5-112">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="694b5-113">Centraliserad distribution kan användas för användare i grupper eller grupper som inte är överordnade grupper, men inte för användare i kapslade grupper eller grupper som har överordnade grupper.</span><span class="sxs-lookup"><span data-stu-id="694b5-113">Centralized Deployment can be used for users in top-level groups or groups without parent groups, but not for users in nested groups or groups that have parent groups.</span></span> <span data-ttu-id="694b5-114">Centraliserad distribution är också en del av de flesta Azure Active Directory-grupper, inklusive Office 365-grupper, distributions listor och säkerhets grupper.</span><span class="sxs-lookup"><span data-stu-id="694b5-114">Centralized Deployment is also part of most Azure Active Directory groups, including Office 365 Groups, distribution lists, and security groups.</span></span>  

<span data-ttu-id="694b5-115">Det är bättre att använda grupp tilldelningar i stället för enskilda användar uppgifter för att under lätta hanteringen.</span><span class="sxs-lookup"><span data-stu-id="694b5-115">It is better to use groups assignments instead of individual user assignment for easier management.</span></span>
 
<span data-ttu-id="694b5-116">Mer information finns i [användar-och grupp tilldelningar](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments).</span><span class="sxs-lookup"><span data-stu-id="694b5-116">For more details, see [User and Group assignments](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments).</span></span>  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a><span data-ttu-id="694b5-117">Hur lång tid tar det för tillägg att visas för alla användare?</span><span class="sxs-lookup"><span data-stu-id="694b5-117">How long does it take for add-ins to show up for all users?</span></span>  

<span data-ttu-id="694b5-118">Det kan ta upp till 24 timmar innan tillägget visas för alla användare.</span><span class="sxs-lookup"><span data-stu-id="694b5-118">It can take up to 24 hours for an add-in to show up for all users.</span></span> <span data-ttu-id="694b5-119">Det kan ta samma tid för tilläggs uppdateringar, ändringar som aktive ras eller inaktive ras.</span><span class="sxs-lookup"><span data-stu-id="694b5-119">It can take the same amount of time for add-in updates, changes from turn on or turn off, or add-in removals.</span></span> 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a><span data-ttu-id="694b5-120">Hur hanterar jag användar åtkomst till tillägg för min organisation som administratör?</span><span class="sxs-lookup"><span data-stu-id="694b5-120">As an administrator, how do I manage the user access to add-ins for my organization?</span></span>

<span data-ttu-id="694b5-121">För enkel distribution av tillägg till användare, grupper eller i hela organisationen rekommenderar vi administratörer att använda centraliserad distribution.</span><span class="sxs-lookup"><span data-stu-id="694b5-121">For easy deployment of add-ins to users, groups, or to your entire organization, we recommend administrators use Centralized Deployment.</span></span>

<span data-ttu-id="694b5-122">Mer information om hur du hanterar användar åtkomst finns i:</span><span class="sxs-lookup"><span data-stu-id="694b5-122">For more information about managing user access, see:</span></span>
 - [<span data-ttu-id="694b5-123">Förhindra hämtning av tillägg genom att stänga av Office Store på alla klienter (utom Outlook)</span><span class="sxs-lookup"><span data-stu-id="694b5-123">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)
 - [<span data-ttu-id="694b5-124">Ange administratörer och användare som kan installera och hantera tillägg för Outlook</span><span class="sxs-lookup"><span data-stu-id="694b5-124">Specify the administrators and users who can install and manage add-ins for Outlook</span></span>](https://docs.microsoft.com/Exchange/specify-who-can-install-and-manage-add-ins-2013-help)

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a><span data-ttu-id="694b5-125">Kan centraliserad distribution ge administratörer flexibiliteten att välja distributions metod för Outlook-tillägg?</span><span class="sxs-lookup"><span data-stu-id="694b5-125">Will Centralized Deployment provide admins the flexibility to choose the deployment method for Outlook add-ins?</span></span>  

<span data-ttu-id="694b5-126">Ja.</span><span class="sxs-lookup"><span data-stu-id="694b5-126">Yes.</span></span> <span data-ttu-id="694b5-127">Centraliserad distribution ger administratörer flexibiliteten att välja någon av tre distributions metoder för Outlook-tillägg under distribution av tillägg:</span><span class="sxs-lookup"><span data-stu-id="694b5-127">Centralized Deployment provides admins the flexibility to choose one of three deployment methods for Outlook add-ins during add-in deployment:</span></span>

<span data-ttu-id="694b5-128">**Åtgärdat (standard)**   Tillägget distribueras automatiskt till de tilldelade användarna och kan inte tas bort.</span><span class="sxs-lookup"><span data-stu-id="694b5-128">**Fixed (Default)**  The add-in is deployed automatically to the assigned users, and they cannot remove it.</span></span>  
 
<span data-ttu-id="694b5-129">**Tillgänglig** Användare kan installera tillägget i Outlook genom att välja **Home > skaffa fler tillägg > administratörs hanterat**.</span><span class="sxs-lookup"><span data-stu-id="694b5-129">**Available** Users can install the add-in in Outlook by choosing **Home > Get More add-ins > Admin-managed**.</span></span>
 
<span data-ttu-id="694b5-130">**Valfritt** Tillägget distribueras automatiskt till de tilldelade användarna, men de kan välja att ta bort det.</span><span class="sxs-lookup"><span data-stu-id="694b5-130">**Optional** The add-in is deployed automatically to the assigned users, but they can choose to remove it.</span></span>  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a><span data-ttu-id="694b5-131">Kan administratörer uppdatera LOB-tillägg (Line-of-Business)?</span><span class="sxs-lookup"><span data-stu-id="694b5-131">Can admins update Line-of-Business (LOB) add-ins?</span></span>  

<span data-ttu-id="694b5-132">Ja.</span><span class="sxs-lookup"><span data-stu-id="694b5-132">Yes.</span></span> <span data-ttu-id="694b5-133">Administratörer kan ladda upp en ny manifest fil för att stödja metadata ändringar för tillägg som distribueras med administratör. Tillägget uppdateras nästa gång Office-programmen startas.</span><span class="sxs-lookup"><span data-stu-id="694b5-133">Admins can upload a new manifest file to support metadata changes for admin-deployed LOB add-ins. The add-in updates the next time the Office applications starts.</span></span> <span data-ttu-id="694b5-134">Webb programmet kan ändras när som helst.</span><span class="sxs-lookup"><span data-stu-id="694b5-134">The web application can change at any time.</span></span>  
 
<span data-ttu-id="694b5-135">Mer information finns i avsnittet [line-of-Business](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#more-about-office-add-ins-security).</span><span class="sxs-lookup"><span data-stu-id="694b5-135">For more information, see [line-of-business add-in](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#more-about-office-add-ins-security).</span></span>  

## <a name="can-admins-turn-off-add-ins"></a><span data-ttu-id="694b5-136">Kan administratörer inaktivera tillägg?</span><span class="sxs-lookup"><span data-stu-id="694b5-136">Can admins turn off add-ins?</span></span>  

<span data-ttu-id="694b5-137">Ja.</span><span class="sxs-lookup"><span data-stu-id="694b5-137">Yes.</span></span> <span data-ttu-id="694b5-138">Administratörer kan aktivera och inaktivera tillägg som de distribuerar för alla användare från Microsoft Admin Center.</span><span class="sxs-lookup"><span data-stu-id="694b5-138">Admins can turn on or off the add-ins they deploy for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="694b5-139">Mer information finns i [tillägget](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#add-in-states).</span><span class="sxs-lookup"><span data-stu-id="694b5-139">For more information, see [Add-in states](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#add-in-states).</span></span>  

##  <a name="can-admins-delete-or-remove-add-ins"></a><span data-ttu-id="694b5-140">Kan administratörer ta bort eller ta bort tillägg?</span><span class="sxs-lookup"><span data-stu-id="694b5-140">Can admins delete or remove add-ins?</span></span>

<span data-ttu-id="694b5-141">Ja.</span><span class="sxs-lookup"><span data-stu-id="694b5-141">Yes.</span></span> <span data-ttu-id="694b5-142">Administratörer kan ta bort tillägg som de distribuerat för alla användare från Microsoft Admin Center.</span><span class="sxs-lookup"><span data-stu-id="694b5-142">Admins can delete add-ins they deployed for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="694b5-143">Mer information finns i [ta bort ett tillägg](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#delete-an-add-in).</span><span class="sxs-lookup"><span data-stu-id="694b5-143">For more information, see [Delete an add-in](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#delete-an-add-in).</span></span> 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a><span data-ttu-id="694b5-144">Kan administratörer distribuera betalda tillägg från Office Store med centraliserad distribution?</span><span class="sxs-lookup"><span data-stu-id="694b5-144">Can admins deploy paid add-ins from the Office Store using Centralized Deployment?</span></span> 

<span data-ttu-id="694b5-145">Nej.</span><span class="sxs-lookup"><span data-stu-id="694b5-145">No.</span></span> <span data-ttu-id="694b5-146">Du kan inte distribuera betalda tillägg från Office Store med centraliserad distribution för tillfället.</span><span class="sxs-lookup"><span data-stu-id="694b5-146">You can't deploy paid add-ins from the Office Store using Centralized Deployment at this time.</span></span>  
 
<span data-ttu-id="694b5-147">Vi föreslår att få en manifest fil eller URL till ISV-utvecklare för det betalda tillägget.</span><span class="sxs-lookup"><span data-stu-id="694b5-147">We suggest reaching out to the ISV Developer for the paid add-in to request a manifest file or a URL.</span></span> <span data-ttu-id="694b5-148">Klient organisationens administratör kan sedan distribuera tillägget som ett LOB-tillägg med centraliserad distribution.</span><span class="sxs-lookup"><span data-stu-id="694b5-148">The tenant admin can then deploy the add-in as a LOB add-in using Centralized Deployment.</span></span>
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a><span data-ttu-id="694b5-149">Vilken administratörs roll behöver jag för att hantera tillägg för min organisation?</span><span class="sxs-lookup"><span data-stu-id="694b5-149">Which admin role do I need to manage add-ins for my organization?</span></span>  

<span data-ttu-id="694b5-150">Global admin är den rekommenderade rollen med fullständig åtkomst till livs cykeln för tilläggs hantering.</span><span class="sxs-lookup"><span data-stu-id="694b5-150">Global Admin is the recommended role with complete access to add-in management lifecycle.</span></span> <span data-ttu-id="694b5-151">Andra administratörs roller har begränsad åtkomst till livs cykeln för distribution av tillägg.</span><span class="sxs-lookup"><span data-stu-id="694b5-151">Other Admin roles have a limited access to add-in deployment lifecycle.</span></span> <span data-ttu-id="694b5-152">Om du är den person som köpte ditt Microsoft 365 för företag-abonnemang är du den globala administratören.</span><span class="sxs-lookup"><span data-stu-id="694b5-152">If you're the person who purchased your Microsoft 365 for business subscription, you are the Global admin.</span></span> 
 
<span data-ttu-id="694b5-153">Ditt abonnemang kommer med en uppsättning administrativa roller som du kan tilldela till andra användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="694b5-153">Your subscription comes with a set of admin roles that you can assign to other users in your organization.</span></span> <span data-ttu-id="694b5-154">Varje administratörs roll mappar till vanliga affärs funktioner och ger användare i din organisations behörighet att utföra specifika uppgifter i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="694b5-154">Each admin role maps to common business functions and gives people in your organization permissions to perform specific tasks in the Microsoft 365 admin center.</span></span>  
 
<span data-ttu-id="694b5-155">Mer information finns i [tilldela administratörs roller](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="694b5-155">For more information, see [Assign admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide).</span></span>  


