---
title: Minderåriga och köp av tillägg från Store
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
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Läs mer om dataskyddsförordningen (GDPR) som styr personuppgifter om minderåriga.
ms.openlocfilehash: e7f53a5a6b64f29f5029f0080fef44439c926edb
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580924"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a><span data-ttu-id="bd608-103">Minderåriga och köp av tillägg från Store</span><span class="sxs-lookup"><span data-stu-id="bd608-103">Minors and acquiring add-ins from the Store</span></span>

<span data-ttu-id="bd608-104">Allmänna Dataskyddsförordningen (GDPR) är en EU-bestämmelse som blir gällande den 25 maj 2018.</span><span class="sxs-lookup"><span data-stu-id="bd608-104">The General Data Protection Regulation (GDPR) is a European Union regulation that becomes effective May 25, 2018.</span></span> <span data-ttu-id="bd608-105">Det ger användare rättigheter till och skydd av sina data.</span><span class="sxs-lookup"><span data-stu-id="bd608-105">It gives users rights to and protection of their data.</span></span> <span data-ttu-id="bd608-106">En av GDPR:s aspekter är att minderåriga inte kan få sina personliga data skickade till parter som deras föräldrar eller vårdnadshavare inte har godkänt.</span><span class="sxs-lookup"><span data-stu-id="bd608-106">One of the aspects of the GDPR is that minors cannot have their personal data sent to parties that their parent or guardian hasn't approved.</span></span> <span data-ttu-id="bd608-107">Vilken ålder som definierar en minderårig beror på var personen befinner sig.</span><span class="sxs-lookup"><span data-stu-id="bd608-107">The specific age defined as a minor depends on the region where the individual is located.</span></span>
  
<span data-ttu-id="bd608-108">Regioner som har lagstadgade föreskrifter om målsmans medgivande är bland annat USA, Sydkorea, Storbritannien och EU.</span><span class="sxs-lookup"><span data-stu-id="bd608-108">Regions that have statutory regulations about parental consent include the United States, South Korea, the United Kingdom, and the European Union.</span></span> <span data-ttu-id="bd608-109">En minderårig i sådana regioner kommer att blockeras (via Azure Active Directory) från att få nya Office-tillägg från Store och att köra tillägg som har förvärvats tidigare.</span><span class="sxs-lookup"><span data-stu-id="bd608-109">For those regions, a minor will be blocked (via Azure Active Directory) from getting any new Office add-ins from the Store and running add-ins that were previously acquired.</span></span> <span data-ttu-id="bd608-110">För länder utan lagstadgade föreskrifter kommer det inte att finnas några begränsningar för nedladdning.</span><span class="sxs-lookup"><span data-stu-id="bd608-110">For countries without statutory regulations, there will be no download restrictions.</span></span>
  
<span data-ttu-id="bd608-111">En användare avgörs som minderårig baserat på data som anges i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="bd608-111">A user is determined to be a minor based on data specified in Azure Active Directory.</span></span> <span data-ttu-id="bd608-112">Organisationens administratör är ansvarig för att deklarera åldersgruppen och målsmans medgivande för användaren.</span><span class="sxs-lookup"><span data-stu-id="bd608-112">The organization admin is responsible for declaring the legal age group and the parental consent for that user.</span></span>
  
<span data-ttu-id="bd608-113">Om föräldern/målsman samtycker till att en minderårig använder ett specifikt tillägg kan organisationsadministratören använda centraliserad distribution för att distribuera tillägget till alla minderåriga som har medgivande.</span><span class="sxs-lookup"><span data-stu-id="bd608-113">If the parent/guardian consents to a minor using a specific add-In, then the organization admin can use centralized deployment to deploy that add-In to all minors who have consent.</span></span>
  
<span data-ttu-id="bd608-114">För att uppfylla GDPR för minderåriga måste du se till att en av följande Office distribueras i skolan/organisationen.</span><span class="sxs-lookup"><span data-stu-id="bd608-114">To be GDPR compliant for minors you need to ensure that one of following builds of Office is deployed in your school/organization.</span></span>
 
 <span data-ttu-id="bd608-115">**För Word, Excel, PowerPoint och Project:**</span><span class="sxs-lookup"><span data-stu-id="bd608-115">**For Word, Excel, PowerPoint, and Project**:</span></span> 

|<span data-ttu-id="bd608-116">**Plattform**</span><span class="sxs-lookup"><span data-stu-id="bd608-116">**Platform**</span></span> <br/> |<span data-ttu-id="bd608-117">**Versionsnummer**</span><span class="sxs-lookup"><span data-stu-id="bd608-117">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="bd608-118">Microsoft 365-appar för företag (Aktuell kanal)</span><span class="sxs-lookup"><span data-stu-id="bd608-118">Microsoft 365 Apps for enterprise (Current Channel)</span></span>  <br/> |<span data-ttu-id="bd608-119">9001.2138</span><span class="sxs-lookup"><span data-stu-id="bd608-119">9001.2138</span></span>   <br/> |
|<span data-ttu-id="bd608-120">Microsoft 365-appar för företag (Halvårskanal för företag)</span><span class="sxs-lookup"><span data-stu-id="bd608-120">Microsoft 365 Apps for enterprise (Semi-Annual Enterprise Channel)</span></span>  <br/> |<span data-ttu-id="bd608-121">8431.2159</span><span class="sxs-lookup"><span data-stu-id="bd608-121">8431.2159</span></span>  <br/> |
|<span data-ttu-id="bd608-122">Office 2016 för Windows</span><span class="sxs-lookup"><span data-stu-id="bd608-122">Office 2016 for Windows</span></span>  <br/> |<span data-ttu-id="bd608-123">16.0.4672.1000</span><span class="sxs-lookup"><span data-stu-id="bd608-123">16.0.4672.1000</span></span>  <br/> |
|<span data-ttu-id="bd608-124">Office 2013 för Windows</span><span class="sxs-lookup"><span data-stu-id="bd608-124">Office 2013 for Windows</span></span>  <br/> |<span data-ttu-id="bd608-125">15.0.5023.1000</span><span class="sxs-lookup"><span data-stu-id="bd608-125">15.0.5023.1000</span></span>  <br/> |
|<span data-ttu-id="bd608-126">Office 2016 för Mac</span><span class="sxs-lookup"><span data-stu-id="bd608-126">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="bd608-127">16.11.18020200</span><span class="sxs-lookup"><span data-stu-id="bd608-127">16.11.18020200</span></span>  <br/> |
|<span data-ttu-id="bd608-128">Office på webben</span><span class="sxs-lookup"><span data-stu-id="bd608-128">Office for the web</span></span>  <br/> |<span data-ttu-id="bd608-129">Uppgift saknas</span><span class="sxs-lookup"><span data-stu-id="bd608-129">N/A</span></span>  <br/> |
   
 <span data-ttu-id="bd608-130">**För Outlook:**</span><span class="sxs-lookup"><span data-stu-id="bd608-130">**For Outlook**:</span></span> 
  
|<span data-ttu-id="bd608-131">**Plattform**</span><span class="sxs-lookup"><span data-stu-id="bd608-131">**Platform**</span></span> <br/> |<span data-ttu-id="bd608-132">**Versionsnummer**</span><span class="sxs-lookup"><span data-stu-id="bd608-132">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="bd608-133">Outlook 2016 för Windows (MSI)</span><span class="sxs-lookup"><span data-stu-id="bd608-133">Outlook 2016 for Windows (MSI)</span></span>  <br/> |<span data-ttu-id="bd608-134">Version nr TBD</span><span class="sxs-lookup"><span data-stu-id="bd608-134">Build No TBD</span></span>  <br/> |
|<span data-ttu-id="bd608-135">Outlook 2016 för Windows (C2R)</span><span class="sxs-lookup"><span data-stu-id="bd608-135">Outlook 2016 for Windows (C2R)</span></span>  <br/> |<span data-ttu-id="bd608-136">16.0.9323.1000</span><span class="sxs-lookup"><span data-stu-id="bd608-136">16.0.9323.1000</span></span>  <br/> |
|<span data-ttu-id="bd608-137">Office 2016 för Mac</span><span class="sxs-lookup"><span data-stu-id="bd608-137">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="bd608-138">16.0.9318.1000</span><span class="sxs-lookup"><span data-stu-id="bd608-138">16.0.9318.1000</span></span>  <br/> |
|<span data-ttu-id="bd608-139">Outlook för iOS</span><span class="sxs-lookup"><span data-stu-id="bd608-139">Outlook mobile for iOS</span></span>  <br/> |<span data-ttu-id="bd608-140">2.75.0</span><span class="sxs-lookup"><span data-stu-id="bd608-140">2.75.0</span></span>  <br/> |
|<span data-ttu-id="bd608-141">Outlook mobil för Android</span><span class="sxs-lookup"><span data-stu-id="bd608-141">Outlook mobile for Android</span></span>  <br/> |<span data-ttu-id="bd608-142">2.2.145</span><span class="sxs-lookup"><span data-stu-id="bd608-142">2.2.145</span></span>  <br/> |
|<span data-ttu-id="bd608-143">Outlook.com</span><span class="sxs-lookup"><span data-stu-id="bd608-143">Outlook.com</span></span>  <br/> |<span data-ttu-id="bd608-144">Uppgift saknas</span><span class="sxs-lookup"><span data-stu-id="bd608-144">N/A</span></span>  <br/> |

 <span data-ttu-id="bd608-145">**Office för 2013**</span><span class="sxs-lookup"><span data-stu-id="bd608-145">**Office 2013 requirements**</span></span>
  
<span data-ttu-id="bd608-146">Word, Excel och PowerPoint 2013 för Windows stöder samma minderåriga kontroller om Active Directory Authentication Library (ADAL) är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="bd608-146">Word, Excel, and PowerPoint 2013 for Windows will support the same minors checks if Active Directory Authentication Library (ADAL) is enabled.</span></span> <span data-ttu-id="bd608-147">Det finns två alternativ för efterlevnad, som beskrivs härnäst.</span><span class="sxs-lookup"><span data-stu-id="bd608-147">There are two options for compliance, as explained next.</span></span>
  
- <span data-ttu-id="bd608-148">**Aktivera ADAL.**</span><span class="sxs-lookup"><span data-stu-id="bd608-148">**Enable ADAL**.</span></span> <span data-ttu-id="bd608-149">Den här artikeln förklarar hur du aktiverar ADAL för Office 2013: Använda [Microsoft 365 modern autentisering med Office klienter.](../../enterprise/modern-auth-for-office-2013-and-2016.md)</span><span class="sxs-lookup"><span data-stu-id="bd608-149">This article explains how to enable ADAL for Office 2013: [Using Microsoft 365 modern authentication with Office clients](../../enterprise/modern-auth-for-office-2013-and-2016.md).</span></span><br/><span data-ttu-id="bd608-150">Du måste också ange registernycklarna för att aktivera ADAL enligt förklaras i Aktivera modern autentisering för [Office 2013 på Windows enheter.](../security-and-compliance/enable-modern-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="bd608-150">You also need to set the registry keys to enable ADAL as explained in [Enable Modern Authentication for Office 2013 on Windows devices](../security-and-compliance/enable-modern-authentication.md).</span></span><br/><span data-ttu-id="bd608-151">Dessutom måste du installera följande uppdateringar för april för Office 2013:</span><span class="sxs-lookup"><span data-stu-id="bd608-151">Additionally, you need to install the following April updates for Office 2013:</span></span>
    
  - [<span data-ttu-id="bd608-152">Beskrivning av säkerhetsuppdateringen för Office 2013: 10 april 2018</span><span class="sxs-lookup"><span data-stu-id="bd608-152">Description of the security update for Office 2013: April 10, 2018</span></span>](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [<span data-ttu-id="bd608-153">Uppdatering för den 3 april 2018 Office 2013 (KB4018333)</span><span class="sxs-lookup"><span data-stu-id="bd608-153">April 3, 2018, update for Office 2013 (KB4018333)</span></span>](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- <span data-ttu-id="bd608-154">**ADAL kan inte aktiveras.**</span><span class="sxs-lookup"><span data-stu-id="bd608-154">**Don't enable ADAL**.</span></span> <span data-ttu-id="bd608-155">Om du inte kan aktivera ADAL i Office 2013 rekommenderas du att använda Grupprincip för att stänga av Store för Office-klienter.</span><span class="sxs-lookup"><span data-stu-id="bd608-155">If you're unable to enable ADAL in Office 2013, then our recommendation is to use Group Policy to turn off the Store for the Office clients.</span></span> <span data-ttu-id="bd608-156">Information om hur du inaktiverar appen för Office finns [här](/previous-versions/office/office-2013-resource-kit/cc178992(v=office.15)).</span><span class="sxs-lookup"><span data-stu-id="bd608-156">Information on how to turn off the app for Office settings is located [here](/previous-versions/office/office-2013-resource-kit/cc178992(v=office.15)).</span></span>

## <a name="related-articles"></a><span data-ttu-id="bd608-157">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="bd608-157">Related articles</span></span>

[<span data-ttu-id="bd608-158">Distribuera tillägg i administrations centret för</span><span class="sxs-lookup"><span data-stu-id="bd608-158">Deploy add-ins in the admin center</span></span>](./manage-deployment-of-add-ins.md)

[<span data-ttu-id="bd608-159">Hantera tillägg i administrationscentret</span><span class="sxs-lookup"><span data-stu-id="bd608-159">Manage add-ins in the admin center</span></span>](./manage-addins-in-the-admin-center.md)
