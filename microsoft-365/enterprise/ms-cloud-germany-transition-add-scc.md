---
title: Information om eDiscovery-upplevelsen under migreringen från Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Sammanfattning: eDiscovery-migreringssteg för migreringen från Microsoft Cloud Deutschland.'
ms.openlocfilehash: 16da6e6d1994ae107b62ff1f915454568a35344d
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51592145"
---
# <a name="information-about-the-ediscovery-experience-during-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="6d934-103">Information om eDiscovery-upplevelsen under migreringen från Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="6d934-103">Information about the eDiscovery experience during the migration from Microsoft Cloud Deutschland</span></span>
<span data-ttu-id="6d934-104">Följande avsnitt innehåller ytterligare information om eDiscovery-upplevelsen när du flyttar från Microsoft Cloud Germany (Microsoft Cloud Deutschland) till Office 365-tjänster i den nya tyska datacenterområdet.</span><span class="sxs-lookup"><span data-stu-id="6d934-104">The following sections provide additional information about the eDiscovery experience when moving from Microsoft Cloud Germany (Microsoft Cloud Deutschland) to Office 365 services in the new German datacenter region.</span></span>

## <a name="ediscovery-administration-until-phase-4"></a><span data-ttu-id="6d934-105">eDiscovery-administration fram till fas 4</span><span class="sxs-lookup"><span data-stu-id="6d934-105">eDiscovery administration until phase 4</span></span>
<span data-ttu-id="6d934-106">Fram till fas 4 är Säkerhets- och efterlevnadscenter helt tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="6d934-106">Until phase 4, the Security and Compliance Center will be fully available.</span></span> <span data-ttu-id="6d934-107">Allt innehåll finns kvar i Microsoft Cloud Germany och kan hanteras av Säkerhets- och efterlevnadscenter för Microsoft Cloud Germany ( https://protection.office.de/) .</span><span class="sxs-lookup"><span data-stu-id="6d934-107">All content still remains in the Microsoft Cloud Germany and is manageable by the Microsoft Cloud Germany Security and Compliance Center (https://protection.office.de/).</span></span>

## <a name="ediscovery-experience-between-phase-4-until-the-the-end-of-phase-9"></a><span data-ttu-id="6d934-108">eDiscovery-upplevelsen mellan fas 4 till slutet av fas 9</span><span class="sxs-lookup"><span data-stu-id="6d934-108">eDiscovery experience between phase 4 until the the end of phase 9</span></span>
<span data-ttu-id="6d934-109">Från början av fas 4 tills fas 9 är slutförd kommer eDiscovery-sökningar att misslyckas eller returnera 0 resultat för SharePoint Online-, OneDrive för företag- och Exchange Online-platser som har migrerats.</span><span class="sxs-lookup"><span data-stu-id="6d934-109">From the beginning of phase 4 until phase 9 is completed, eDiscovery searches will fail or return 0 results for SharePoint Online, OneDrive for Business, and Exchange Online locations that have been migrated.</span></span>

> [!NOTE]
> <span data-ttu-id="6d934-110">Under migreringen kan kunder fortsätta att skapa ärenden, innehåll, sökningar och exporter i Säkerhets- [&,](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)inklusive [Innehållssökning.](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)</span><span class="sxs-lookup"><span data-stu-id="6d934-110">During migration, customers can continue to create cases, holds, searches, and exports in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations), including [Content Search](https://docs.microsoft.com/microsoft-365/compliance/search-for-content).</span></span> <span data-ttu-id="6d934-111">Men sökningar mot SharePoint Online-, OneDrive för företag- och Exchange Online-platser som har migrerats returnerar antingen 0 resultat eller resulterar i ett fel.</span><span class="sxs-lookup"><span data-stu-id="6d934-111">However, searches against SharePoint Online, OneDrive for Business, and Exchange Online locations that have been migrated will either return 0 results or produce an error.</span></span>

<span data-ttu-id="6d934-112">Om en sökning returnerar noll resultat eller ett fel under migreringen kan du vidta följande åtgärd för SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="6d934-112">In the event that a search returns zero results or an error during migration, please take the following action for SharePoint Online:</span></span> 
- <span data-ttu-id="6d934-113">Ladda ned webbplatser direkt från SharePoint Online- eller OneDrive för företag-webbplatsen genom att följa anvisningarna i Ladda ned filer och [mappar från OneDrive eller SharePoint.](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)</span><span class="sxs-lookup"><span data-stu-id="6d934-113">Download sites directly from the SharePoint Online or OneDrive for Business site by following the instructions in [Download files and folders from OneDrive or SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05).</span></span> <span data-ttu-id="6d934-114">Den här metoden kräver administratörsbehörigheter för SharePoint Online eller skrivskyddsbehörigheter på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="6d934-114">This method will require SharePoint Online administrator permissions or read-only permissions on the site.</span></span>
- <span data-ttu-id="6d934-115">Om gränserna överskrids, vilket förklaras i Ladda ned filer och mappar från OneDrive eller [SharePoint,](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)kan kunder använda synkroniseringsklienten för OneDrive för företag genom att följa vägledning i Synkronisera [SharePoint-](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)och Teams-filer med din dator.</span><span class="sxs-lookup"><span data-stu-id="6d934-115">If limits are exceeded, as explained in [Download files and folders from OneDrive or SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05), customers can use the OneDrive for Business sync client by following the guidance in [Sync SharePoint and Teams files with your computer](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88).</span></span>

- <span data-ttu-id="6d934-116">Mer information finns i [EDiscovery på plats i Exchange Server.](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery)</span><span class="sxs-lookup"><span data-stu-id="6d934-116">For more information, see  [In-Place eDiscovery in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery).</span></span>


## <a name="ediscovery-administration-after-phase-9"></a><span data-ttu-id="6d934-117">eDiscovery-administration efter fas 9</span><span class="sxs-lookup"><span data-stu-id="6d934-117">eDiscovery administration after phase 9</span></span>

<span data-ttu-id="6d934-118">**Gäller för:** Alla kunder som använder eDiscovery</span><span class="sxs-lookup"><span data-stu-id="6d934-118">**Applies to:** All customers using eDiscovery</span></span>

<span data-ttu-id="6d934-119">I fas 9 slutförs de sista stegen för att flytta över till det nya tyska datacentret.</span><span class="sxs-lookup"><span data-stu-id="6d934-119">In phase 9, the final steps for moving to the new German datacenter region will be completed.</span></span> <span data-ttu-id="6d934-120">I den här fasen migreras alla återstående tjänstkomponenter.</span><span class="sxs-lookup"><span data-stu-id="6d934-120">In this phase, all remaining service components will be migrated.</span></span> <span data-ttu-id="6d934-121">Efter fas 9 stöds inte längre användning av säkerhets- och efterlevnadscentret i Microsoft Cloud Germany (protection.office.de).</span><span class="sxs-lookup"><span data-stu-id="6d934-121">After phase 9, using the Security and Compliance Center in Microsoft Cloud Germany (protection.office.de) is no longer supported.</span></span> <span data-ttu-id="6d934-122">Använd det nya [säkerhetscentret eller](https://security.microsoft.com/) [efterlevnadscentret i](https://compliance.microsoft.com/) stället.</span><span class="sxs-lookup"><span data-stu-id="6d934-122">Please use the new [Security Center](https://security.microsoft.com/) or [Compliance Center](https://compliance.microsoft.com/) instead.</span></span> <span data-ttu-id="6d934-123">Alla data har migrerats till de nya administrationsportalerna.</span><span class="sxs-lookup"><span data-stu-id="6d934-123">All data have been migrated to the new admin portals.</span></span> 

| <span data-ttu-id="6d934-124">Steg</span><span class="sxs-lookup"><span data-stu-id="6d934-124">Step(s)</span></span> | <span data-ttu-id="6d934-125">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6d934-125">Description</span></span> | <span data-ttu-id="6d934-126">Påverkan</span><span class="sxs-lookup"><span data-stu-id="6d934-126">Impact</span></span> |
|:-------|:-------|:-------|
|  <span data-ttu-id="6d934-127">Alla SharePoint Online-, OneDrive för företag- och Exchange Online-platser har migrerats tillsammans med Säkerhets- och efterlevnadscenter (SCC).</span><span class="sxs-lookup"><span data-stu-id="6d934-127">All SharePoint Online, OneDrive for Business, and Exchange Online locations have been migrated along with the Security and Compliance Center (SCC).</span></span> | <span data-ttu-id="6d934-128">All eDiscovery-aktivitet bör köras från den globala klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="6d934-128">All eDiscovery activity should be run from the worldwide tenant.</span></span> <span data-ttu-id="6d934-129">Sökningarna lyckas nu till 100 %.</span><span class="sxs-lookup"><span data-stu-id="6d934-129">Searches will now be 100% successful.</span></span> <span data-ttu-id="6d934-130">Eventuella fel bör följa vanliga supportkanaler.</span><span class="sxs-lookup"><span data-stu-id="6d934-130">Any failures or errors should follow normal support channels.</span></span> | <span data-ttu-id="6d934-131">Ingen</span><span class="sxs-lookup"><span data-stu-id="6d934-131">None</span></span> |
||||

### <a name="ediscovery-retention-policy"></a><span data-ttu-id="6d934-132">eDiscovery-bevarandeprincip</span><span class="sxs-lookup"><span data-stu-id="6d934-132">eDiscovery Retention Policy</span></span>
<span data-ttu-id="6d934-133">**Gäller för:**  Alla kunder som har tillämpat en bevarandeprincip som en del av före migreringen</span><span class="sxs-lookup"><span data-stu-id="6d934-133">**Applies to:**  All customers who applied a retention policy as part of the pre-migration steps</span></span>

| <span data-ttu-id="6d934-134">Steg</span><span class="sxs-lookup"><span data-stu-id="6d934-134">Step(s)</span></span> | <span data-ttu-id="6d934-135">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6d934-135">Description</span></span> | <span data-ttu-id="6d934-136">Påverkan</span><span class="sxs-lookup"><span data-stu-id="6d934-136">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="6d934-137">Ta bort bevarandeprinciper för hela organisationen som skapades före migreringen</span><span class="sxs-lookup"><span data-stu-id="6d934-137">Remove organization-wide retention policies that were created during pre-migration steps</span></span> | <span data-ttu-id="6d934-138">Kunder kan ta bort de organisationsomfattande bevarandeprinciper som skapades under kundernas arbete före migreringen.</span><span class="sxs-lookup"><span data-stu-id="6d934-138">Customers can remove the organization-wide retention policies that were created during the customers' pre-migration work.</span></span> | <span data-ttu-id="6d934-139">Ingen</span><span class="sxs-lookup"><span data-stu-id="6d934-139">None</span></span> |
||||
