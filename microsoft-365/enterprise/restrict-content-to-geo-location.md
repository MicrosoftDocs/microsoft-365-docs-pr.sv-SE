---
title: Begränsa SharePoint-webbplatsinnehåll till en geoplats
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
ms.collection: Strat_SP_gtc
localization_priority: Normal
description: I den här artikeln lär du dig hur du begränsar SharePoint-webbplatser till en viss geoplats i en geomiljö med flera platser.
ms.openlocfilehash: 74255db19b2ecf9b333d33208c63da260b2bd747
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927270"
---
# <a name="restrict-sharepoint-site-content-to-a-geo-location"></a><span data-ttu-id="2d5ae-103">Begränsa SharePoint-webbplatsinnehåll till en geoplats</span><span class="sxs-lookup"><span data-stu-id="2d5ae-103">Restrict SharePoint site content to a geo location</span></span>

<span data-ttu-id="2d5ae-104">I vissa fall kan du välja att tillämpa en webbplats och dess filinnehåll på den geoplats där webbplatsen skapades, antingen genom att förhindra att webbplatsen flyttas eller genom att förhindra cachelagring av webbplatsens filinnehåll på en annan geoplats.</span><span class="sxs-lookup"><span data-stu-id="2d5ae-104">Under some circumstances you may choose to enforce a site and its file content to remain in the geo location where the site was created, either by preventing the site from being moved or by preventing the caching of the site's file content in another geo location.</span></span>

<span data-ttu-id="2d5ae-105">Det kan du göra genom att använda cmdleten [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) med **parametern RestrictedToGeo.**</span><span class="sxs-lookup"><span data-stu-id="2d5ae-105">You can do this by using the [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) cmdlet with the **RestrictedToGeo** parameter.</span></span> <span data-ttu-id="2d5ae-106">Den här parametern har standardvärdet NULL, men du kan ändra den till något av följande:</span><span class="sxs-lookup"><span data-stu-id="2d5ae-106">This parameter has a default value of NULL, but you can change it to one of the following:</span></span>

|<span data-ttu-id="2d5ae-107">Begränsning</span><span class="sxs-lookup"><span data-stu-id="2d5ae-107">Restriction</span></span>|<span data-ttu-id="2d5ae-108">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="2d5ae-108">Description</span></span>|
|:----------|:----------|
|<span data-ttu-id="2d5ae-109">NoRestriction</span><span class="sxs-lookup"><span data-stu-id="2d5ae-109">NoRestriction</span></span>|<span data-ttu-id="2d5ae-110">Webbplatsen kan flyttas till en annan geoplats.</span><span class="sxs-lookup"><span data-stu-id="2d5ae-110">The site can be moved to another geo location.</span></span>|
|<span data-ttu-id="2d5ae-111">BlockMoveOnly</span><span class="sxs-lookup"><span data-stu-id="2d5ae-111">BlockMoveOnly</span></span>|<span data-ttu-id="2d5ae-112">Webbplatsen kan inte flyttas till en annan geoplats, men webbplatsinnehållet kan cachelagras på andra geoplatser.</span><span class="sxs-lookup"><span data-stu-id="2d5ae-112">Site cannot be moved to another geo location, but site content can be cached in other geo locations.</span></span>|
|<span data-ttu-id="2d5ae-113">BlockFull</span><span class="sxs-lookup"><span data-stu-id="2d5ae-113">BlockFull</span></span>|<span data-ttu-id="2d5ae-114">Webbplatsen kan inte flyttas till en annan geoplats och fullständigt filinnehåll cachelagras inte på andra geoplatser.</span><span class="sxs-lookup"><span data-stu-id="2d5ae-114">Site cannot be moved to another geo location, and full file content is not cached in other geo locations.</span></span> <span data-ttu-id="2d5ae-115">Filernas namn (som inlagrats från innehållet), filnamnet och andra egenskaper för filen kan fortfarande cachelagras på andra geoplatser.</span><span class="sxs-lookup"><span data-stu-id="2d5ae-115">Files' title (harvested from the content), file name, and other properties of the file can still be cached in other geo-locations.</span></span><br><span data-ttu-id="2d5ae-116">Innehåll som lagrats på webbplatsen innan den konfigurerades på BlockFull kan fortsätta att cachelagras på andra geoplatser.</span><span class="sxs-lookup"><span data-stu-id="2d5ae-116">Content stored in the site before it was configured to BlockFull, may continue to be cached in other geo locations.</span></span>|

<span data-ttu-id="2d5ae-117">Använd följande syntax:</span><span class="sxs-lookup"><span data-stu-id="2d5ae-117">Use the following syntax:</span></span>

`Set-SPOSite -Identity <siteURL> -RestrictedToGeo <restriction>`

<span data-ttu-id="2d5ae-118">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="2d5ae-118">For example:</span></span>

`Set-SPOSite -Identity https://contoso.sharepoint.com/sites/RegionRestrictedTeamSite -RestrictedToGeo BlockFull`