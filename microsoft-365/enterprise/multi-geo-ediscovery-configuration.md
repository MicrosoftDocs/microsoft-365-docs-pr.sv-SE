---
title: Konfigurera Microsoft 365 multi-geo eDiscovery
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
description: Lär dig hur du använder parametern region för att konfigurera eDiscovery för användning på satellit platser i Microsoft 365 multi-geo.
ms.openlocfilehash: 83141f824c76ca5531e1b390b91adcdb4f3874de
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694485"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a><span data-ttu-id="f6968-103">Microsoft 365 multi-geo eDiscovery-konfiguration</span><span class="sxs-lookup"><span data-stu-id="f6968-103">Microsoft 365 Multi-Geo eDiscovery configuration</span></span>

<span data-ttu-id="f6968-104">Som standard kan en eDiscovery-chef eller administratör för en multi-geo-klient leda en eDiscovery endast på den centrala platsen för denna klient organisation.</span><span class="sxs-lookup"><span data-stu-id="f6968-104">By default, an eDiscovery Manager or Administrator of a multi-geo tenant will be able to conduct eDiscovery only in the central location of that tenant.</span></span> <span data-ttu-id="f6968-105">För att stöda möjligheten att genomföra eDiscovery för satellit platser är en ny parameter för reglerad säkerhets filter med namnet "region" tillgänglig via PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6968-105">To support the ability to conduct eDiscovery for satellite locations, a new Compliance Security Filter parameter called "Region" is available via PowerShell.</span></span>

<span data-ttu-id="f6968-106">Den globala administratören för Microsoft 365 måste tilldela eDiscovery Manager-behörigheter för att tillåta att andra utför eDiscovery och tilldela en "region"-parameter i sitt tillämpliga säkerhets filter för efterlevnad för att ange regionen för att genomföra eDiscovery som satellit plats, annars utförs ingen eDiscovery för satellit platsen.</span><span class="sxs-lookup"><span data-stu-id="f6968-106">The Microsoft 365 global administrator must assign eDiscovery Manager permissions to allow others to perform eDiscovery and assign a "Region" parameter in their applicable Compliance Security Filter to specify the region for conducting eDiscovery as satellite location, otherwise no eDiscovery will be carried out for the satellite location.</span></span>

<span data-ttu-id="f6968-107">När rollen eDiscovery Manager eller administratör anges för en viss satellit plats kan eDiscovery Manager eller administratören bara utföra eDiscovery-sökåtgärder mot SharePoint-webbplatser och OneDrive-webbplatser på den satellit platsen.</span><span class="sxs-lookup"><span data-stu-id="f6968-107">When the eDiscovery Manager or Administrator role is set for a particular satellite location, the eDiscovery Manager or Administrator will only be able to perform eDiscovery search actions against the SharePoint sites and OneDrive sites located in that satellite location.</span></span> <span data-ttu-id="f6968-108">Om en eDiscovery Manager eller administratör försöker söka i SharePoint-eller OneDrive-webbplatser utanför angiven satellit plats returneras inga resultat.</span><span class="sxs-lookup"><span data-stu-id="f6968-108">If an eDiscovery Manager or Administrator attempts to search SharePoint or OneDrive sites outside the specified satellite location, no results will be returned.</span></span> <span data-ttu-id="f6968-109">När eDiscovery Manager eller administratören för en satellit plats utlöser en export, exporteras data till Azure-instansen av den regionen.</span><span class="sxs-lookup"><span data-stu-id="f6968-109">Also, when the eDiscovery Manager or Administrator for a satellite location triggers an export, data is exported to the Azure instance of that region.</span></span> <span data-ttu-id="f6968-110">Detta hjälper organisationer att hålla sig à jour genom att inte tillåta att innehåll exporteras över kontrollerade kant linjer.</span><span class="sxs-lookup"><span data-stu-id="f6968-110">This helps organizations stay in compliance by not allowing content to be exported across controlled borders.</span></span>

> [!NOTE]
> <span data-ttu-id="f6968-111">Om det är nödvändigt för en eDiscovery Manager att söka på flera platser för SharePoint-satellit måste ett annat användar konto skapas för eDiscovery Manager som anger den alternativa satellit platsen där OneDrive-eller SharePoint-webbplatserna finns.</span><span class="sxs-lookup"><span data-stu-id="f6968-111">If it's necessary for an eDiscovery Manager to search across multiple SharePoint satellite locations, another user account will need to be created for the eDiscovery Manager which specifies the alternate satellite location where the OneDrive or SharePoint sites are located.</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

<span data-ttu-id="f6968-112">Så här anger du säkerhets filter för efterlevnad för en region:</span><span class="sxs-lookup"><span data-stu-id="f6968-112">To set the Compliance Security Filter for a Region:</span></span>

1. [<span data-ttu-id="f6968-113">Ansluta till Microsoft 365 Security & Compliance Center PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6968-113">Connect to Microsoft 365 Security & Compliance Center PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)

2. <span data-ttu-id="f6968-114">Använd följande syntax:</span><span class="sxs-lookup"><span data-stu-id="f6968-114">Use the following syntax:</span></span>

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName <TheNameYouWantToAssign> -Region <RegionValue> -Users <UserPrincipalName>
   ```

   <span data-ttu-id="f6968-115">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="f6968-115">For example:</span></span>

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName "NAM eDiscovery Managers" -Region NAM -Users adwood@contoso.onmicrosoft.com
   ```

<span data-ttu-id="f6968-116">Se artikeln [ny ComplianceSecurityFilter](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesecurityfilter) för ytterligare parametrar och syntax.</span><span class="sxs-lookup"><span data-stu-id="f6968-116">See the [New-ComplianceSecurityFilter](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesecurityfilter) article for additional parameters and syntax.</span></span>
