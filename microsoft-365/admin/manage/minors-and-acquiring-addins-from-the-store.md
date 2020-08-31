---
title: Minderåriga och förvärvade tillägg från Store
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
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Lär dig mer om de regler för förordning (General Data Protection GDPR) som styr person uppgifter om minderåriga.
ms.openlocfilehash: a738e22a0ac0b995c8e44fcf4cc5a2eb47375be5
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306557"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a><span data-ttu-id="a931a-103">Minderåriga och förvärvade tillägg från Store</span><span class="sxs-lookup"><span data-stu-id="a931a-103">Minors and acquiring add-ins from the Store</span></span>

<span data-ttu-id="a931a-104">Den allmänna data skydds förordningen (GDPR) är en europeisk unions förordning som träder i kraft 25 maj 2018.</span><span class="sxs-lookup"><span data-stu-id="a931a-104">The General Data Protection Regulation (GDPR) is a European Union regulation that becomes effective May 25, 2018.</span></span> <span data-ttu-id="a931a-105">Den ger användare rättigheter att och skyddar sina data.</span><span class="sxs-lookup"><span data-stu-id="a931a-105">It gives users rights to and protection of their data.</span></span> <span data-ttu-id="a931a-106">En av fördelarna med GDPR är att minderåriga inte kan ha sina person uppgifter skickade till parter som inte har godkänt sin förälder eller vårdnadshavare.</span><span class="sxs-lookup"><span data-stu-id="a931a-106">One of the aspects of the GDPR is that minors cannot have their personal data sent to parties that their parent or guardian hasn't approved.</span></span> <span data-ttu-id="a931a-107">Den specifika åldern som definieras som en del beror på regionen där personen finns.</span><span class="sxs-lookup"><span data-stu-id="a931a-107">The specific age defined as a minor depends on the region where the individual is located.</span></span>
  
<span data-ttu-id="a931a-108">Regioner som har lagstadgade förordningar om föräldra godkännande inkluderar USA, Sydkorea, Storbritannien och Europeiska unionen.</span><span class="sxs-lookup"><span data-stu-id="a931a-108">Regions that have statutory regulations about parental consent include the United States, South Korea, the United Kingdom, and the European Union.</span></span> <span data-ttu-id="a931a-109">För dessa regioner blockeras en del (via Azure Active Directory) från att få nya Office-tillägg från Store och via tillägg som tidigare har skaffats.</span><span class="sxs-lookup"><span data-stu-id="a931a-109">For those regions, a minor will be blocked (via Azure Active Directory) from getting any new Office add-ins from the Store and running add-ins that were previously acquired.</span></span> <span data-ttu-id="a931a-110">För länder utan lagstadgade bestämmelser finns inga nedladdnings begränsningar.</span><span class="sxs-lookup"><span data-stu-id="a931a-110">For countries without statutory regulations, there will be no download restrictions.</span></span>
  
<span data-ttu-id="a931a-111">En användare anses vara en del baserad på data som anges i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a931a-111">A user is determined to be a minor based on data specified in Azure Active Directory.</span></span> <span data-ttu-id="a931a-112">Organisationens administratör ansvarar för att deklarera gruppen Legal ålder och förälderns medgivande.</span><span class="sxs-lookup"><span data-stu-id="a931a-112">The organization admin is responsible for declaring the legal age group and the parental consent for that user.</span></span>
  
<span data-ttu-id="a931a-113">Om föräldern/vårdnadshavare samtycker till en mindre med ett specifikt tillägg kan organisationens administratör använda centraliserad distribution för att distribuera tillägget till alla minderåriga som har godkänt.</span><span class="sxs-lookup"><span data-stu-id="a931a-113">If the parent/guardian consents to a minor using a specific add-In, then the organization admin can use centralized deployment to deploy that add-In to all minors who have consent.</span></span>
  
<span data-ttu-id="a931a-114">För att vara GDPR-kompatibel för minderåriga måste du kontrol lera att någon av följande versioner av Office distribueras i din skola/organisation.</span><span class="sxs-lookup"><span data-stu-id="a931a-114">To be GDPR compliant for minors you need to ensure that one of following builds of Office is deployed in your school/organization.</span></span>
 
 <span data-ttu-id="a931a-115">**För Word, Excel, PowerPoint och Project**:</span><span class="sxs-lookup"><span data-stu-id="a931a-115">**For Word, Excel, PowerPoint, and Project**:</span></span> 

|<span data-ttu-id="a931a-116">**Plattform**</span><span class="sxs-lookup"><span data-stu-id="a931a-116">**Platform**</span></span> <br/> |<span data-ttu-id="a931a-117">**Versions nummer**</span><span class="sxs-lookup"><span data-stu-id="a931a-117">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="a931a-118">Microsoft 365-appar för Enterprise (aktuell kanal)</span><span class="sxs-lookup"><span data-stu-id="a931a-118">Microsoft 365 Apps for enterprise (Current Channel)</span></span>  <br/> |<span data-ttu-id="a931a-119">9001,2138</span><span class="sxs-lookup"><span data-stu-id="a931a-119">9001.2138</span></span>   <br/> |
|<span data-ttu-id="a931a-120">Microsoft 365-appar för företag (halvårs kanal för Enterprise)</span><span class="sxs-lookup"><span data-stu-id="a931a-120">Microsoft 365 Apps for enterprise (Semi-Annual Enterprise Channel)</span></span>  <br/> |<span data-ttu-id="a931a-121">8431,2159</span><span class="sxs-lookup"><span data-stu-id="a931a-121">8431.2159</span></span>  <br/> |
|<span data-ttu-id="a931a-122">Office 2016 för Windows</span><span class="sxs-lookup"><span data-stu-id="a931a-122">Office 2016 for Windows</span></span>  <br/> |<span data-ttu-id="a931a-123">16.0.4672.1000</span><span class="sxs-lookup"><span data-stu-id="a931a-123">16.0.4672.1000</span></span>  <br/> |
|<span data-ttu-id="a931a-124">Office 2013 för Windows</span><span class="sxs-lookup"><span data-stu-id="a931a-124">Office 2013 for Windows</span></span>  <br/> |<span data-ttu-id="a931a-125">15.0.5023.1000</span><span class="sxs-lookup"><span data-stu-id="a931a-125">15.0.5023.1000</span></span>  <br/> |
|<span data-ttu-id="a931a-126">Office 2016 för Mac</span><span class="sxs-lookup"><span data-stu-id="a931a-126">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="a931a-127">16.11.18020200</span><span class="sxs-lookup"><span data-stu-id="a931a-127">16.11.18020200</span></span>  <br/> |
|<span data-ttu-id="a931a-128">Office för webben</span><span class="sxs-lookup"><span data-stu-id="a931a-128">Office for the web</span></span>  <br/> |<span data-ttu-id="a931a-129">Saknas</span><span class="sxs-lookup"><span data-stu-id="a931a-129">N/A</span></span>  <br/> |
   
 <span data-ttu-id="a931a-130">**För Outlook**:</span><span class="sxs-lookup"><span data-stu-id="a931a-130">**For Outlook**:</span></span> 
  
|<span data-ttu-id="a931a-131">**Plattform**</span><span class="sxs-lookup"><span data-stu-id="a931a-131">**Platform**</span></span> <br/> |<span data-ttu-id="a931a-132">**Versions nummer**</span><span class="sxs-lookup"><span data-stu-id="a931a-132">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="a931a-133">Outlook 2016 för Windows (MSI)</span><span class="sxs-lookup"><span data-stu-id="a931a-133">Outlook 2016 for Windows (MSI)</span></span>  <br/> |<span data-ttu-id="a931a-134">Bygg inget TBD</span><span class="sxs-lookup"><span data-stu-id="a931a-134">Build No TBD</span></span>  <br/> |
|<span data-ttu-id="a931a-135">Outlook 2016 för Windows (C2R)</span><span class="sxs-lookup"><span data-stu-id="a931a-135">Outlook 2016 for Windows (C2R)</span></span>  <br/> |<span data-ttu-id="a931a-136">16.0.9323.1000</span><span class="sxs-lookup"><span data-stu-id="a931a-136">16.0.9323.1000</span></span>  <br/> |
|<span data-ttu-id="a931a-137">Office 2016 för Mac</span><span class="sxs-lookup"><span data-stu-id="a931a-137">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="a931a-138">16.0.9318.1000</span><span class="sxs-lookup"><span data-stu-id="a931a-138">16.0.9318.1000</span></span>  <br/> |
|<span data-ttu-id="a931a-139">Outlook Mobile för iOS</span><span class="sxs-lookup"><span data-stu-id="a931a-139">Outlook mobile for iOS</span></span>  <br/> |<span data-ttu-id="a931a-140">2.75.0</span><span class="sxs-lookup"><span data-stu-id="a931a-140">2.75.0</span></span>  <br/> |
|<span data-ttu-id="a931a-141">Outlook Mobile för Android</span><span class="sxs-lookup"><span data-stu-id="a931a-141">Outlook mobile for Android</span></span>  <br/> |<span data-ttu-id="a931a-142">2.2.145</span><span class="sxs-lookup"><span data-stu-id="a931a-142">2.2.145</span></span>  <br/> |
|<span data-ttu-id="a931a-143">Outlook.com</span><span class="sxs-lookup"><span data-stu-id="a931a-143">Outlook.com</span></span>  <br/> |<span data-ttu-id="a931a-144">Saknas</span><span class="sxs-lookup"><span data-stu-id="a931a-144">N/A</span></span>  <br/> |

 <span data-ttu-id="a931a-145">**Krav för Office 2013**</span><span class="sxs-lookup"><span data-stu-id="a931a-145">**Office 2013 requirements**</span></span>
  
<span data-ttu-id="a931a-146">Word, Excel och PowerPoint 2013 för Windows stöder samma minderåriga om Active Directory-autentiseringsschemat (ADAL) är aktive rad.</span><span class="sxs-lookup"><span data-stu-id="a931a-146">Word, Excel, and PowerPoint 2013 for Windows will support the same minors checks if Active Directory Authentication Library (ADAL) is enabled.</span></span> <span data-ttu-id="a931a-147">Det finns två alternativ för efterlevnad, enligt förklarat nästa.</span><span class="sxs-lookup"><span data-stu-id="a931a-147">There are two options for compliance, as explained next.</span></span>
  
- <span data-ttu-id="a931a-148">**Aktivera ADAL**.</span><span class="sxs-lookup"><span data-stu-id="a931a-148">**Enable ADAL**.</span></span> <span data-ttu-id="a931a-149">I den här artikeln förklaras hur du aktiverar ADAL för Office 2013: [använda den moderna verifierade Microsoft 365 med Office-klienter](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016).</span><span class="sxs-lookup"><span data-stu-id="a931a-149">This article explains how to enable ADAL for Office 2013: [Using Microsoft 365 modern authentication with Office clients](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016).</span></span><br/><span data-ttu-id="a931a-150">Du måste också ange register nycklarna för att aktivera ADAL enligt beskrivningen i [Aktivera modern auktorisering för Office 2013 på Windows-enheter](../security-and-compliance/enable-modern-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="a931a-150">You also need to set the registry keys to enable ADAL as explained in [Enable Modern Authentication for Office 2013 on Windows devices](../security-and-compliance/enable-modern-authentication.md).</span></span><br/><span data-ttu-id="a931a-151">Dessutom måste du installera följande uppdateringar för april för Office 2013:</span><span class="sxs-lookup"><span data-stu-id="a931a-151">Additionally, you need to install the following April updates for Office 2013:</span></span>
    
  - [<span data-ttu-id="a931a-152">Beskrivning av säkerhets uppdateringen för Office 2013:10 april 2018</span><span class="sxs-lookup"><span data-stu-id="a931a-152">Description of the security update for Office 2013: April 10, 2018</span></span>](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [<span data-ttu-id="a931a-153">3 april 2018, uppdatering för Office 2013 (KB4018333)</span><span class="sxs-lookup"><span data-stu-id="a931a-153">April 3, 2018, update for Office 2013 (KB4018333)</span></span>](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- <span data-ttu-id="a931a-154">**Aktivera inte ADAL**.</span><span class="sxs-lookup"><span data-stu-id="a931a-154">**Don't enable ADAL**.</span></span> <span data-ttu-id="a931a-155">Om du inte kan aktivera ADAL i Office 2013 är vår rekommendation att använda grup princip för att inaktivera butiken för Office-klienter.</span><span class="sxs-lookup"><span data-stu-id="a931a-155">If you're unable to enable ADAL in Office 2013, then our recommendation is to use Group Policy to turn off the Store for the Office clients.</span></span> <span data-ttu-id="a931a-156">Information om hur du inaktiverar programmet för Office-inställningar finns [här](https://technet.microsoft.com/library/cc178992.aspx).</span><span class="sxs-lookup"><span data-stu-id="a931a-156">Information on how to turn off the app for Office settings is located [here](https://technet.microsoft.com/library/cc178992.aspx).</span></span>

## <a name="related-articles"></a><span data-ttu-id="a931a-157">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="a931a-157">Related articles</span></span>

[<span data-ttu-id="a931a-158">Distribuera tillägg i administrations centret för</span><span class="sxs-lookup"><span data-stu-id="a931a-158">Deploy add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

[<span data-ttu-id="a931a-159">Hantera tillägg i administrationscentret</span><span class="sxs-lookup"><span data-stu-id="a931a-159">Manage add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center)
    
