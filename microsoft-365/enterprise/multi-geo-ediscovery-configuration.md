---
title: Konfigurera Microsoft 365 Multi-Geo eDiscovery
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
ms.collection: Strat_SP_gtc
description: Lär dig hur du använder parametern Region för att konfigurera eDiscovery för användning i satellitplatser i Microsoft 365 Multi-Geo.
ms.openlocfilehash: 4d3481fe8b72bb970893ce065293a7a2cc717331
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923726"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a><span data-ttu-id="8ec22-103">Microsoft 365 Multi-Geo eDiscovery-konfiguration</span><span class="sxs-lookup"><span data-stu-id="8ec22-103">Microsoft 365 Multi-Geo eDiscovery configuration</span></span>

<span data-ttu-id="8ec22-104">[Advanced eDiscovery här](../compliance/overview-ediscovery-20.md) funktionerna kan en eDiscovery-administratör med flera funktioner söka i alla geos utan att behöva använda ett säkerhetsfilter för "Region".</span><span class="sxs-lookup"><span data-stu-id="8ec22-104">[Advanced eDiscovery capabilities](../compliance/overview-ediscovery-20.md) allow a multi-geo eDiscovery administrator to search all of the geos without needing to utilize a "Region" security filter.</span></span> <span data-ttu-id="8ec22-105">Data exporteras till Azure-instansen av den centrala platsen för den geoa klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="8ec22-105">Data is exported to the Azure instance of the central location of the multi-geo tenant.</span></span> 

<span data-ttu-id="8ec22-106">Utan avancerade eDiscovery-funktioner kan en eDiscovery-hanterare eller administratör för en geoklient för flera geoklienter utföra eDiscovery endast på den centrala platsen för innehavaren.</span><span class="sxs-lookup"><span data-stu-id="8ec22-106">Without advanced eDiscovery capabilities, an eDiscovery manager or administrator of a multi-geo tenant will be able to conduct eDiscovery only in the central location of that tenant.</span></span> <span data-ttu-id="8ec22-107">För att stödja möjligheten att utföra eDiscovery för satellitplatser är en ny säkerhetsfilterparameter för efterlevnad med namnet Region tillgänglig via PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8ec22-107">To support the ability to conduct eDiscovery for satellite locations, a new compliance security filter parameter named "Region" is available via PowerShell.</span></span> <span data-ttu-id="8ec22-108">Den här parametern kan användas av klientorganisationen vars centrala plats är i Nordamerika, Europa eller Asien och Stilla havet.</span><span class="sxs-lookup"><span data-stu-id="8ec22-108">This parameter can be used by tenants whose central location is in North America, Europe, or Asia Pacific.</span></span> <span data-ttu-id="8ec22-109">Advanced eDiscovery för klientorganisation vars centrala plats inte finns i Nordamerika, Europa eller Asien och Stilla havet och som behöver utföra eDiscovery över satellitgeoplatser.</span><span class="sxs-lookup"><span data-stu-id="8ec22-109">Advanced eDiscovery is recommended for tenants whose central location is not in North America, Europe, or Asia Pacific and who need to perform eDiscovery across satellite geo locations.</span></span> 

<span data-ttu-id="8ec22-110">Den globala Microsoft 365-administratören måste tilldela eDiscovery Manager-behörigheter så att andra kan utföra eDiscovery och tilldela en "Region"-parameter i sitt tillämpliga säkerhetsfilter för efterlevnad för att ange området för eDiscovery som satellitplats, annars utförs ingen eDiscovery för satellitplatsen.</span><span class="sxs-lookup"><span data-stu-id="8ec22-110">The Microsoft 365 global administrator must assign eDiscovery Manager permissions to allow others to perform eDiscovery and assign a "Region" parameter in their applicable Compliance Security Filter to specify the region for conducting eDiscovery as satellite location, otherwise no eDiscovery will be carried out for the satellite location.</span></span>

<span data-ttu-id="8ec22-111">När rollen eDiscovery-hanterare eller administratör har angetts för en viss satellitplats kan eDiscovery-hanteraren eller administratören bara utföra eDiscovery-sökåtgärder mot SharePoint-webbplatserna och OneDrive-webbplatserna på satellitplatsen.</span><span class="sxs-lookup"><span data-stu-id="8ec22-111">When the eDiscovery Manager or Administrator role is set for a particular satellite location, the eDiscovery Manager or Administrator will only be able to perform eDiscovery search actions against the SharePoint sites and OneDrive sites located in that satellite location.</span></span> <span data-ttu-id="8ec22-112">Om en eDiscovery-hanterare eller administratör försöker söka efter SharePoint eller OneDrive platser utanför den angivna satellitplatsen returneras inga resultat.</span><span class="sxs-lookup"><span data-stu-id="8ec22-112">If an eDiscovery Manager or Administrator attempts to search SharePoint or OneDrive sites outside the specified satellite location, no results will be returned.</span></span> <span data-ttu-id="8ec22-113">Och när eDiscovery-hanteraren eller administratören för en satellitplats utlöser en export exporteras data till Azure-instansen av den regionen.</span><span class="sxs-lookup"><span data-stu-id="8ec22-113">Also, when the eDiscovery Manager or Administrator for a satellite location triggers an export, data is exported to the Azure instance of that region.</span></span> <span data-ttu-id="8ec22-114">På så sätt ser du till att organisationer följer reglerna genom att inte tillåta att innehåll exporteras över styrda kantlinjer.</span><span class="sxs-lookup"><span data-stu-id="8ec22-114">This helps organizations stay in compliance by not allowing content to be exported across controlled borders.</span></span>

> [!NOTE]
> <span data-ttu-id="8ec22-115">Om det är nödvändigt för en eDiscovery-hanterare att söka på flera SharePoint-satellitplatser måste ett annat användarkonto skapas för eDiscovery-hanteraren som anger den alternativa satellitplats där OneDrive- eller SharePoint-webbplatserna finns.</span><span class="sxs-lookup"><span data-stu-id="8ec22-115">If it's necessary for an eDiscovery Manager to search across multiple SharePoint satellite locations, another user account will need to be created for the eDiscovery Manager which specifies the alternate satellite location where the OneDrive or SharePoint sites are located.</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

<span data-ttu-id="8ec22-116">Så här ställer du in säkerhetsfiltret för efterlevnad för en region:</span><span class="sxs-lookup"><span data-stu-id="8ec22-116">To set the Compliance Security Filter for a Region:</span></span>

1. [<span data-ttu-id="8ec22-117">Anslut att Microsoft 365 Säkerhets- & Efterlevnadscenter PowerShell</span><span class="sxs-lookup"><span data-stu-id="8ec22-117">Connect to Microsoft 365 Security & Compliance Center PowerShell</span></span>](/powershell/exchange/connect-to-scc-powershell)

2. <span data-ttu-id="8ec22-118">Använd följande syntax:</span><span class="sxs-lookup"><span data-stu-id="8ec22-118">Use the following syntax:</span></span>

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName <TheNameYouWantToAssign> -Region <RegionValue> -Users <UserPrincipalName>
   ```

   <span data-ttu-id="8ec22-119">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="8ec22-119">For example:</span></span>

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName "NAM eDiscovery Managers" -Region NAM -Users adwood@contoso.onmicrosoft.com
   ```

<span data-ttu-id="8ec22-120">Fler parametrar och syntax finns i artikeln [New-ComplianceSecurityFilter.](/powershell/module/exchange/new-compliancesecurityfilter)</span><span class="sxs-lookup"><span data-stu-id="8ec22-120">See the [New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter) article for additional parameters and syntax.</span></span>