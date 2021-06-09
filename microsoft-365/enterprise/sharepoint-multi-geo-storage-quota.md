---
title: SharePoint för flera geografiska miljöer
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
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: Läs mer SharePoint om lagringskvoter i geomiljöer och hur kvoter kan hanteras av SharePoint Online-administratören.
ms.openlocfilehash: ec736a6bd6061f8b028fca7a1c34d5278a84db89
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694940"
---
# <a name="sharepoint-storage-quotas-in-multi-geo-environments"></a><span data-ttu-id="3b0b4-103">SharePoint för flera geografiska miljöer</span><span class="sxs-lookup"><span data-stu-id="3b0b4-103">SharePoint storage quotas in multi-geo environments</span></span>

<span data-ttu-id="3b0b4-104">Som standard delar alla geoplatser i en multigeomiljö den tillgängliga lagringskvoten för klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="3b0b4-104">By default, all geo locations of a multi-geo environment share the available tenant storage quota.</span></span>

<span data-ttu-id="3b0b4-105">Med de SharePoint för geolagringskvot kan du hantera lagringskvoten för varje geoplats.</span><span class="sxs-lookup"><span data-stu-id="3b0b4-105">With the SharePoint geo storage quota setting, you can manage the storage quota for each geo location.</span></span> <span data-ttu-id="3b0b4-106">När du tilldelar en lagringskvot för en geoplats blir den största tillgängliga lagringsmängden för den geoplatsen och dras av från den tillgängliga klientorganisationens lagringskvot.</span><span class="sxs-lookup"><span data-stu-id="3b0b4-106">When you allocate a storage quota for a geo location, it becomes the maximum amount of storage available for that geo location, and is deducted from the available tenant storage quota.</span></span> <span data-ttu-id="3b0b4-107">Den återstående tillgängliga lagringskvoten för klientorganisationen delas sedan över de konfigurerade geoplatser som inte har tilldelats en viss lagringskvot.</span><span class="sxs-lookup"><span data-stu-id="3b0b4-107">The remaining available tenant storage quota is then shared across the configured geo locations for which a specific storage quota has not been allocated.</span></span>

<span data-ttu-id="3b0b4-108">Lagringskvoten SharePoint geoplats kan tilldelas av SharePoint Online-administratören genom att ansluta till den centrala platsen.</span><span class="sxs-lookup"><span data-stu-id="3b0b4-108">The SharePoint storage quota for any geo location can be allocated by the SharePoint Online administrator by connecting to the central location.</span></span> <span data-ttu-id="3b0b4-109">Geoadministratörer för satellitplatser kan visa lagringskvoten men kan inte tilldela den.</span><span class="sxs-lookup"><span data-stu-id="3b0b4-109">Geo administrators for satellite locations can view the storage quota but cannot allocate it.</span></span>

## <a name="configure-a-storage-quota-for-a-geo-location"></a><span data-ttu-id="3b0b4-110">Konfigurera en lagringskvot för en geoplats</span><span class="sxs-lookup"><span data-stu-id="3b0b4-110">Configure a storage quota for a geo location</span></span>

<span data-ttu-id="3b0b4-111">Använd Microsoft Office SharePoint Online [och anslut](https://www.microsoft.com/download/details.aspx?id=35588 ) till den centrala platsen för att tilldela lagringskvoten för en geoplats.</span><span class="sxs-lookup"><span data-stu-id="3b0b4-111">Use the [Microsoft SharePoint Online Module](https://www.microsoft.com/download/details.aspx?id=35588 ) and connect to the central location to allocate the storage quota for a geo location.</span></span> 

<span data-ttu-id="3b0b4-112">För att tilldela Storage för en plats kör du cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3b0b4-112">To allocate Storage Quota for a location, run cmdlet:</span></span>

`Set-SPOGeoStorageQuota -GeoLocation <geolocationcode> -StorageQuotaMB <value>`

<span data-ttu-id="3b0b4-113">Visa Storage för den aktuella geoplatsen genom att köra:</span><span class="sxs-lookup"><span data-stu-id="3b0b4-113">To view Storage Quota for the current geo location, run:</span></span>

`Get-SPOGeoStorageQuota`

![Skärmbild av PowerShell-fönstret med Get-SPOGeoStorageQuota cmdlet](../media/multi-geo-storage-quota.png)

<span data-ttu-id="3b0b4-115">Visa Storage för alla geografiska platser genom att köra:</span><span class="sxs-lookup"><span data-stu-id="3b0b4-115">To view Storage Quota for all geo locations, run:</span></span>

`Get-SPOGeoStorageQuota -AllLocations`

<span data-ttu-id="3b0b4-116">Ta bort den tilldelade lagringskvoten för en geoplats genom att `StorageQuota value = 0` ange:</span><span class="sxs-lookup"><span data-stu-id="3b0b4-116">To remove the allocated storage quota for a geo location, set `StorageQuota value = 0`:</span></span>

`Set-SPOGeoStorageQuota -GeoLocation <geolocationcode> -StorageQuotaMB 0`
