---
title: Minderåriga och förvärva tillägg från Store
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
description: Läs mer om de allmänna dataskyddsförordningen (GDPR) som reglerar minderårigas personuppgifter.
ms.openlocfilehash: dcf2c98906830e0007747e2dd90e67b9dc85a5bb
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/11/2020
ms.locfileid: "45103118"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a><span data-ttu-id="9be72-103">Minderåriga och förvärva tillägg från Store</span><span class="sxs-lookup"><span data-stu-id="9be72-103">Minors and acquiring add-ins from the Store</span></span>

<span data-ttu-id="9be72-104">Den allmänna dataskyddsförordningen (GDPR) är en EU-förordning som träder i kraft den 25 maj 2018.</span><span class="sxs-lookup"><span data-stu-id="9be72-104">The General Data Protection Regulation (GDPR) is a European Union regulation that becomes effective May 25, 2018.</span></span> <span data-ttu-id="9be72-105">Det ger användarna rätt till och skydd av sina uppgifter.</span><span class="sxs-lookup"><span data-stu-id="9be72-105">It gives users rights to and protection of their data.</span></span> <span data-ttu-id="9be72-106">En av aspekterna av GDPR är att minderåriga inte kan få sina personuppgifter skickade till parter som deras förälder eller vårdnadshavare inte har godkänt.</span><span class="sxs-lookup"><span data-stu-id="9be72-106">One of the aspects of the GDPR is that minors cannot have their personal data sent to parties that their parent or guardian hasn't approved.</span></span> <span data-ttu-id="9be72-107">Den specifika ålder som definieras som minderårig beror på den region där personen är belägen.</span><span class="sxs-lookup"><span data-stu-id="9be72-107">The specific age defined as a minor depends on the region where the individual is located.</span></span>
  
<span data-ttu-id="9be72-108">Regioner som har lagstadgade bestämmelser om föräldrarnas samtycke inkluderar USA, Sydkorea, Storbritannien och Eu ropeiska unionen.</span><span class="sxs-lookup"><span data-stu-id="9be72-108">Regions that have statutory regulations about parental consent include the United States, South Korea, the United Kingdom, and the European Union.</span></span> <span data-ttu-id="9be72-109">För dessa regioner blockeras en minderårig (via Azure Active Directory) från att hämta nya Office-tillägg från Store och köra tillägg som tidigare har förvärvats.</span><span class="sxs-lookup"><span data-stu-id="9be72-109">For those regions, a minor will be blocked (via Azure Active Directory) from getting any new Office add-ins from the Store and running add-ins that were previously acquired.</span></span> <span data-ttu-id="9be72-110">För länder utan lagstadgade bestämmelser kommer det inte att finnas några nedladdningsrestriktioner.</span><span class="sxs-lookup"><span data-stu-id="9be72-110">For countries without statutory regulations, there will be no download restrictions.</span></span>
  
<span data-ttu-id="9be72-111">En användare bedöms vara en minderårig baserat på data som anges i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9be72-111">A user is determined to be a minor based on data specified in Azure Active Directory.</span></span> <span data-ttu-id="9be72-112">Organisationsadministratören ansvarar för att deklarera den juridiska åldersgruppen och föräldrarnas samtycke för den användaren.</span><span class="sxs-lookup"><span data-stu-id="9be72-112">The organization admin is responsible for declaring the legal age group and the parental consent for that user.</span></span>
  
<span data-ttu-id="9be72-113">Om föräldern/vårdnadshavaren samtycker till en minderårig med hjälp av ett specifikt tillägg kan organisationsadministratören använda centraliserad distribution för att distribuera tillägget till alla minderåriga som har medgivande.</span><span class="sxs-lookup"><span data-stu-id="9be72-113">If the parent/guardian consents to a minor using a specific add-In, then the organization admin can use centralized deployment to deploy that add-In to all minors who have consent.</span></span>
  
<span data-ttu-id="9be72-114">För att vara GDPR-kompatibel för minderåriga måste du se till att en av följande versioner av Office distribueras i din skola/organisation.</span><span class="sxs-lookup"><span data-stu-id="9be72-114">To be GDPR compliant for minors you need to ensure that one of following builds of Office is deployed in your school/organization.</span></span>
 
 <span data-ttu-id="9be72-115">**För Word, Excel, PowerPoint och Project:**</span><span class="sxs-lookup"><span data-stu-id="9be72-115">**For Word, Excel, PowerPoint, and Project**:</span></span> 

|<span data-ttu-id="9be72-116">**Plattform**</span><span class="sxs-lookup"><span data-stu-id="9be72-116">**Platform**</span></span> <br/> |<span data-ttu-id="9be72-117">**Bygg nummer**</span><span class="sxs-lookup"><span data-stu-id="9be72-117">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="9be72-118">Microsoft 365-appar för företag (aktuell kanal)</span><span class="sxs-lookup"><span data-stu-id="9be72-118">Microsoft 365 Apps for enterprise (Current Channel)</span></span>  <br/> |<span data-ttu-id="9be72-119">9001.2138</span><span class="sxs-lookup"><span data-stu-id="9be72-119">9001.2138</span></span>   <br/> |
|<span data-ttu-id="9be72-120">Microsoft 365 Apps for enterprise (Halvårsvis Företagskanal)</span><span class="sxs-lookup"><span data-stu-id="9be72-120">Microsoft 365 Apps for enterprise (Semi-Annual Enterprise Channel)</span></span>  <br/> |<span data-ttu-id="9be72-121">8431.2159</span><span class="sxs-lookup"><span data-stu-id="9be72-121">8431.2159</span></span>  <br/> |
|<span data-ttu-id="9be72-122">Office 2016 för Windows</span><span class="sxs-lookup"><span data-stu-id="9be72-122">Office 2016 for Windows</span></span>  <br/> |<span data-ttu-id="9be72-123">16.0.4672.1000</span><span class="sxs-lookup"><span data-stu-id="9be72-123">16.0.4672.1000</span></span>  <br/> |
|<span data-ttu-id="9be72-124">Office 2013 för Windows</span><span class="sxs-lookup"><span data-stu-id="9be72-124">Office 2013 for Windows</span></span>  <br/> |<span data-ttu-id="9be72-125">15.0.5023.1000</span><span class="sxs-lookup"><span data-stu-id="9be72-125">15.0.5023.1000</span></span>  <br/> |
|<span data-ttu-id="9be72-126">Office 2016 för Mac</span><span class="sxs-lookup"><span data-stu-id="9be72-126">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="9be72-127">16.11.18020200</span><span class="sxs-lookup"><span data-stu-id="9be72-127">16.11.18020200</span></span>  <br/> |
|<span data-ttu-id="9be72-128">Office för webben</span><span class="sxs-lookup"><span data-stu-id="9be72-128">Office for the web</span></span>  <br/> |<span data-ttu-id="9be72-129">EJ TILLÄMPLIGT</span><span class="sxs-lookup"><span data-stu-id="9be72-129">N/A</span></span>  <br/> |
   
 <span data-ttu-id="9be72-130">**För Outlook:**</span><span class="sxs-lookup"><span data-stu-id="9be72-130">**For Outlook**:</span></span> 
  
|<span data-ttu-id="9be72-131">**Plattform**</span><span class="sxs-lookup"><span data-stu-id="9be72-131">**Platform**</span></span> <br/> |<span data-ttu-id="9be72-132">**Bygg nummer**</span><span class="sxs-lookup"><span data-stu-id="9be72-132">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="9be72-133">Outlook 2016 för Windows (MSI)</span><span class="sxs-lookup"><span data-stu-id="9be72-133">Outlook 2016 for Windows (MSI)</span></span>  <br/> |<span data-ttu-id="9be72-134">Skapa ingen TBD</span><span class="sxs-lookup"><span data-stu-id="9be72-134">Build No TBD</span></span>  <br/> |
|<span data-ttu-id="9be72-135">Outlook 2016 för Windows (C2R)</span><span class="sxs-lookup"><span data-stu-id="9be72-135">Outlook 2016 for Windows (C2R)</span></span>  <br/> |<span data-ttu-id="9be72-136">16.0.9323.1000</span><span class="sxs-lookup"><span data-stu-id="9be72-136">16.0.9323.1000</span></span>  <br/> |
|<span data-ttu-id="9be72-137">Office 2016 för Mac</span><span class="sxs-lookup"><span data-stu-id="9be72-137">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="9be72-138">16.0.9318.1000</span><span class="sxs-lookup"><span data-stu-id="9be72-138">16.0.9318.1000</span></span>  <br/> |
|<span data-ttu-id="9be72-139">Outlook Mobile för iOS</span><span class="sxs-lookup"><span data-stu-id="9be72-139">Outlook mobile for iOS</span></span>  <br/> |<span data-ttu-id="9be72-140">2.75.0</span><span class="sxs-lookup"><span data-stu-id="9be72-140">2.75.0</span></span>  <br/> |
|<span data-ttu-id="9be72-141">Outlook mobile för Android</span><span class="sxs-lookup"><span data-stu-id="9be72-141">Outlook mobile for Android</span></span>  <br/> |<span data-ttu-id="9be72-142">2.2.145</span><span class="sxs-lookup"><span data-stu-id="9be72-142">2.2.145</span></span>  <br/> |
|<span data-ttu-id="9be72-143">Outlook.com</span><span class="sxs-lookup"><span data-stu-id="9be72-143">Outlook.com</span></span>  <br/> |<span data-ttu-id="9be72-144">EJ TILLÄMPLIGT</span><span class="sxs-lookup"><span data-stu-id="9be72-144">N/A</span></span>  <br/> |

 <span data-ttu-id="9be72-145">**Office 2013-krav**</span><span class="sxs-lookup"><span data-stu-id="9be72-145">**Office 2013 requirements**</span></span>
  
<span data-ttu-id="9be72-146">Word, Excel och PowerPoint 2013 för Windows stöder samma mindre kontroller om Active Directory Authentication Library (ADAL) är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="9be72-146">Word, Excel, and PowerPoint 2013 for Windows will support the same minors checks if Active Directory Authentication Library (ADAL) is enabled.</span></span> <span data-ttu-id="9be72-147">Det finns två alternativ för efterlevnad, som förklaras härnäst.</span><span class="sxs-lookup"><span data-stu-id="9be72-147">There are two options for compliance, as explained next.</span></span>
  
- <span data-ttu-id="9be72-148">**Aktivera ADAL**.</span><span class="sxs-lookup"><span data-stu-id="9be72-148">**Enable ADAL**.</span></span> <span data-ttu-id="9be72-149">I den hÃ¤r artikeln beskrivs hur du aktiverar ADAL för Office 2013: [HÃ¤r Ã¤ger microsoft 365 modern autentisering med Office-klienter](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).</span><span class="sxs-lookup"><span data-stu-id="9be72-149">This article explains how to enable ADAL for Office 2013: [Using Microsoft 365 modern authentication with Office clients](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).</span></span><br/><span data-ttu-id="9be72-150">Du måste också ange registernycklarna så att de aktiverar ADAL enligt beskrivningen i [Aktivera modern autentisering för Office 2013 på Windows-enheter](../security-and-compliance/enable-modern-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="9be72-150">You also need to set the registry keys to enable ADAL as explained in [Enable Modern Authentication for Office 2013 on Windows devices](../security-and-compliance/enable-modern-authentication.md).</span></span><br/><span data-ttu-id="9be72-151">Dessutom måste du installera följande apriluppdateringar för Office 2013:</span><span class="sxs-lookup"><span data-stu-id="9be72-151">Additionally, you need to install the following April updates for Office 2013:</span></span>
    
  - [<span data-ttu-id="9be72-152">Beskrivning av säkerhetsuppdateringen för Office 2013: 10 april 2018</span><span class="sxs-lookup"><span data-stu-id="9be72-152">Description of the security update for Office 2013: April 10, 2018</span></span>](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [<span data-ttu-id="9be72-153">3 april 2018, uppdatering för Office 2013 (KB4018333)</span><span class="sxs-lookup"><span data-stu-id="9be72-153">April 3, 2018, update for Office 2013 (KB4018333)</span></span>](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- <span data-ttu-id="9be72-154">**Aktivera inte ADAL**.</span><span class="sxs-lookup"><span data-stu-id="9be72-154">**Don't enable ADAL**.</span></span> <span data-ttu-id="9be72-155">Om du inte kan aktivera ADAL i Office 2013 är vår rekommendation att använda Grupprincip för att stänga av Store för Office-klienterna.</span><span class="sxs-lookup"><span data-stu-id="9be72-155">If you're unable to enable ADAL in Office 2013, then our recommendation is to use Group Policy to turn off the Store for the Office clients.</span></span> <span data-ttu-id="9be72-156">Information om hur du inaktiverar appen för Office-inställningar finns [här](https://technet.microsoft.com/library/cc178992.aspx).</span><span class="sxs-lookup"><span data-stu-id="9be72-156">Information on how to turn off the app for Office settings is located [here](https://technet.microsoft.com/library/cc178992.aspx).</span></span>

## <a name="related-articles"></a><span data-ttu-id="9be72-157">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="9be72-157">Related articles</span></span>

[<span data-ttu-id="9be72-158">Distribuera tillägg i administrationscentret</span><span class="sxs-lookup"><span data-stu-id="9be72-158">Deploy add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

[<span data-ttu-id="9be72-159">Hantera tillägg i administrationscentret</span><span class="sxs-lookup"><span data-stu-id="9be72-159">Manage add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center)
    
