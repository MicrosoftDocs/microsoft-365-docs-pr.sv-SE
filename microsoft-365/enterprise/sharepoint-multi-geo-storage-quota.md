---
title: SharePoint-lagringslösningar i multi-geo-miljöer
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
description: Läs mer om SharePoint-lagringslösningar i multi-geo-miljöer och hur kvoter kan hanteras av SharePoint Online-administratören.
ms.openlocfilehash: ec736a6bd6061f8b028fca7a1c34d5278a84db89
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694940"
---
# <a name="sharepoint-storage-quotas-in-multi-geo-environments"></a><span data-ttu-id="a7dca-103">SharePoint-lagringslösningar i multi-geo-miljöer</span><span class="sxs-lookup"><span data-stu-id="a7dca-103">SharePoint storage quotas in multi-geo environments</span></span>

<span data-ttu-id="a7dca-104">Som standard delar alla geo-platser i en multi-geo-miljö den tillgängliga lagrings kvoten för innehavare.</span><span class="sxs-lookup"><span data-stu-id="a7dca-104">By default, all geo locations of a multi-geo environment share the available tenant storage quota.</span></span>

<span data-ttu-id="a7dca-105">Med inställningen för SharePoint geo Storage-lagring kan du hantera lagrings kvoten för varje Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="a7dca-105">With the SharePoint geo storage quota setting, you can manage the storage quota for each geo location.</span></span> <span data-ttu-id="a7dca-106">När du tilldelar en lagrings kvot för en Geo-plats blir den det maximala lagrings utrymmet som är tillgängligt för den geo platsen och den dras från den tillgängliga lagrings kvoten för innehavare.</span><span class="sxs-lookup"><span data-stu-id="a7dca-106">When you allocate a storage quota for a geo location, it becomes the maximum amount of storage available for that geo location, and is deducted from the available tenant storage quota.</span></span> <span data-ttu-id="a7dca-107">Den återstående tillgängliga innehavaren av lagrings kvoten delas sedan på de konfigurerade geo-platserna för vilka en specifik lagrings kvot inte har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="a7dca-107">The remaining available tenant storage quota is then shared across the configured geo locations for which a specific storage quota has not been allocated.</span></span>

<span data-ttu-id="a7dca-108">SharePoint-lagringsplatsen för varje Geo-plats kan tilldelas av SharePoint Online-administratören genom att ansluta till Central platsen.</span><span class="sxs-lookup"><span data-stu-id="a7dca-108">The SharePoint storage quota for any geo location can be allocated by the SharePoint Online administrator by connecting to the central location.</span></span> <span data-ttu-id="a7dca-109">Geo-administratörer för satellit platser kan visa lagrings kvoten men kan inte tilldela den.</span><span class="sxs-lookup"><span data-stu-id="a7dca-109">Geo administrators for satellite locations can view the storage quota but cannot allocate it.</span></span>

## <a name="configure-a-storage-quota-for-a-geo-location"></a><span data-ttu-id="a7dca-110">Konfigurera en lagrings kvot för en Geo-plats</span><span class="sxs-lookup"><span data-stu-id="a7dca-110">Configure a storage quota for a geo location</span></span>

<span data-ttu-id="a7dca-111">Använd [Microsoft SharePoint Online-modulen](https://www.microsoft.com/download/details.aspx?id=35588 ) och Anslut till Central platsen för att tilldela lagrings kvoten för en Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="a7dca-111">Use the [Microsoft SharePoint Online Module](https://www.microsoft.com/download/details.aspx?id=35588 ) and connect to the central location to allocate the storage quota for a geo location.</span></span> 

<span data-ttu-id="a7dca-112">Om du vill tilldela lagrings kvot för en plats kör du cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a7dca-112">To allocate Storage Quota for a location, run cmdlet:</span></span>

`Set-SPOGeoStorageQuota -GeoLocation <geolocationcode> -StorageQuotaMB <value>`

<span data-ttu-id="a7dca-113">Om du vill visa lagrings kvoten för den aktuella geo-platsen kör du:</span><span class="sxs-lookup"><span data-stu-id="a7dca-113">To view Storage Quota for the current geo location, run:</span></span>

`Get-SPOGeoStorageQuota`

![Skärm bild av PowerShell-fönstret med cmdleten Get-SPOGeoStorageQuota](../media/multi-geo-storage-quota.png)

<span data-ttu-id="a7dca-115">Om du vill visa lagrings kvoten för alla geo platser kör du:</span><span class="sxs-lookup"><span data-stu-id="a7dca-115">To view Storage Quota for all geo locations, run:</span></span>

`Get-SPOGeoStorageQuota -AllLocations`

<span data-ttu-id="a7dca-116">Om du vill ta bort den tilldelade lagrings kvoten för en Geo-plats anger du `StorageQuota value = 0` :</span><span class="sxs-lookup"><span data-stu-id="a7dca-116">To remove the allocated storage quota for a geo location, set `StorageQuota value = 0`:</span></span>

`Set-SPOGeoStorageQuota -GeoLocation <geolocationcode> -StorageQuotaMB 0`
