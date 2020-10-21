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
description: Lär dig hur du använder parametern region för att konfigurera eDiscovery för användning på satellit platser i Microsoft 365 multi-geo.
ms.openlocfilehash: d1d66a9e7953b540e318c8364bdcb8d72654b482
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48636811"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a><span data-ttu-id="fdc8b-103">Microsoft 365 multi-geo eDiscovery-konfiguration</span><span class="sxs-lookup"><span data-stu-id="fdc8b-103">Microsoft 365 Multi-Geo eDiscovery configuration</span></span>

<span data-ttu-id="fdc8b-104">[Avancerade eDiscovery-funktioner](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) tillåter en multi-geo eDiscovery-administratör för att söka i alla geos utan att behöva använda ett "region"-säkerhets filter.</span><span class="sxs-lookup"><span data-stu-id="fdc8b-104">[Advanced eDiscovery capabilities](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) allow a multi-geo eDiscovery administrator to search all of the geos without needing to utilize a "Region" security filter.</span></span> <span data-ttu-id="fdc8b-105">Data exporteras till Azure-instansen av den centrala platsen för multi-geo-klienten.</span><span class="sxs-lookup"><span data-stu-id="fdc8b-105">Data is exported to the Azure instance of the central location of the multi-geo tenant.</span></span> 

<span data-ttu-id="fdc8b-106">Utan avancerade eDiscovery-funktioner kan en eDiscovery Manager eller administratör av en multi-geo-klient leda en eDiscovery endast på den centrala platsen för denna klient organisation.</span><span class="sxs-lookup"><span data-stu-id="fdc8b-106">Without advanced eDiscovery capabilities, an eDiscovery manager or administrator of a multi-geo tenant will be able to conduct eDiscovery only in the central location of that tenant.</span></span> <span data-ttu-id="fdc8b-107">För att stödja möjligheten att genomföra eDiscovery för satellit platser är en ny parameter för säkerhets filter med namnet "region" tillgänglig via PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fdc8b-107">To support the ability to conduct eDiscovery for satellite locations, a new compliance security filter parameter named "Region" is available via PowerShell.</span></span> <span data-ttu-id="fdc8b-108">Denna parameter kan användas av klient organisationer vars centrala plats är i Nord Amerika, Europa eller Asien Stilla havet.</span><span class="sxs-lookup"><span data-stu-id="fdc8b-108">This parameter can be used by tenants whose central location is in North America, Europe, or Asia Pacific.</span></span> <span data-ttu-id="fdc8b-109">Avancerad eDiscovery rekommenderas för innehavare vars centrala plats inte är i Nord Amerika, Europa eller Asien och som måste genomföra en eDiscovery-geo-platser.</span><span class="sxs-lookup"><span data-stu-id="fdc8b-109">Advanced eDiscovery is recommended for tenants whose central location is not in North America, Europe, or Asia Pacific and who need to perform eDiscovery across satellite geo locations.</span></span> 

<span data-ttu-id="fdc8b-110">Den globala administratören för Microsoft 365 måste tilldela eDiscovery Manager-behörigheter för att tillåta att andra utför eDiscovery och tilldela en "region"-parameter i sitt tillämpliga säkerhets filter för efterlevnad för att ange regionen för att genomföra eDiscovery som satellit plats, annars utförs ingen eDiscovery för satellit platsen.</span><span class="sxs-lookup"><span data-stu-id="fdc8b-110">The Microsoft 365 global administrator must assign eDiscovery Manager permissions to allow others to perform eDiscovery and assign a "Region" parameter in their applicable Compliance Security Filter to specify the region for conducting eDiscovery as satellite location, otherwise no eDiscovery will be carried out for the satellite location.</span></span>

<span data-ttu-id="fdc8b-111">När rollen eDiscovery Manager eller administratör anges för en viss satellit plats kan eDiscovery Manager eller administratören bara utföra eDiscovery-sökåtgärder mot SharePoint-webbplatser och OneDrive-webbplatser på den satellit platsen.</span><span class="sxs-lookup"><span data-stu-id="fdc8b-111">When the eDiscovery Manager or Administrator role is set for a particular satellite location, the eDiscovery Manager or Administrator will only be able to perform eDiscovery search actions against the SharePoint sites and OneDrive sites located in that satellite location.</span></span> <span data-ttu-id="fdc8b-112">Om en eDiscovery Manager eller administratör försöker söka i SharePoint-eller OneDrive-webbplatser utanför angiven satellit plats returneras inga resultat.</span><span class="sxs-lookup"><span data-stu-id="fdc8b-112">If an eDiscovery Manager or Administrator attempts to search SharePoint or OneDrive sites outside the specified satellite location, no results will be returned.</span></span> <span data-ttu-id="fdc8b-113">När eDiscovery Manager eller administratören för en satellit plats utlöser en export, exporteras data till Azure-instansen av den regionen.</span><span class="sxs-lookup"><span data-stu-id="fdc8b-113">Also, when the eDiscovery Manager or Administrator for a satellite location triggers an export, data is exported to the Azure instance of that region.</span></span> <span data-ttu-id="fdc8b-114">Detta hjälper organisationer att hålla sig à jour genom att inte tillåta att innehåll exporteras över kontrollerade kant linjer.</span><span class="sxs-lookup"><span data-stu-id="fdc8b-114">This helps organizations stay in compliance by not allowing content to be exported across controlled borders.</span></span>

> [!NOTE]
> <span data-ttu-id="fdc8b-115">Om det är nödvändigt för en eDiscovery Manager att söka på flera platser för SharePoint-satellit måste ett annat användar konto skapas för eDiscovery Manager som anger den alternativa satellit platsen där OneDrive-eller SharePoint-webbplatserna finns.</span><span class="sxs-lookup"><span data-stu-id="fdc8b-115">If it's necessary for an eDiscovery Manager to search across multiple SharePoint satellite locations, another user account will need to be created for the eDiscovery Manager which specifies the alternate satellite location where the OneDrive or SharePoint sites are located.</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

<span data-ttu-id="fdc8b-116">Så här anger du säkerhets filter för efterlevnad för en region:</span><span class="sxs-lookup"><span data-stu-id="fdc8b-116">To set the Compliance Security Filter for a Region:</span></span>

1. [<span data-ttu-id="fdc8b-117">Ansluta till Microsoft 365 Security & Compliance Center PowerShell</span><span class="sxs-lookup"><span data-stu-id="fdc8b-117">Connect to Microsoft 365 Security & Compliance Center PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)

2. <span data-ttu-id="fdc8b-118">Använd följande syntax:</span><span class="sxs-lookup"><span data-stu-id="fdc8b-118">Use the following syntax:</span></span>

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName <TheNameYouWantToAssign> -Region <RegionValue> -Users <UserPrincipalName>
   ```

   <span data-ttu-id="fdc8b-119">Ett exempel:</span><span class="sxs-lookup"><span data-stu-id="fdc8b-119">For example:</span></span>

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName "NAM eDiscovery Managers" -Region NAM -Users adwood@contoso.onmicrosoft.com
   ```

<span data-ttu-id="fdc8b-120">Se artikeln [ny ComplianceSecurityFilter](https://docs.microsoft.com/powershell/module/exchange/new-compliancesecurityfilter) för ytterligare parametrar och syntax.</span><span class="sxs-lookup"><span data-stu-id="fdc8b-120">See the [New-ComplianceSecurityFilter](https://docs.microsoft.com/powershell/module/exchange/new-compliancesecurityfilter) article for additional parameters and syntax.</span></span>
