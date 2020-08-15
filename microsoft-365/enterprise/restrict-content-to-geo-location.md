---
title: Begränsa SharePoint-webbplatsens innehåll till en Geo-plats
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
description: I den här artikeln lär du dig hur du begränsar SharePoint-webbplatser till en angiven Geo-plats i en multi-geo-miljö.
ms.openlocfilehash: f2a09f177c68d30121c207287e053b2b25405fbc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694384"
---
# <a name="restrict-sharepoint-site-content-to-a-geo-location"></a><span data-ttu-id="dc39d-103">Begränsa SharePoint-webbplatsens innehåll till en Geo-plats</span><span class="sxs-lookup"><span data-stu-id="dc39d-103">Restrict SharePoint site content to a geo location</span></span>

<span data-ttu-id="dc39d-104">Under vissa omständigheter kan du välja att tvinga en webbplats och dess fil innehåll att finnas kvar på den Geo-plats där webbplatsen skapades, antingen genom att förhindra att webbplatsen flyttas eller genom att förhindra att webbplats innehållet cachelagras på en annan Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="dc39d-104">Under some circumstances you may choose to enforce a site and its file content to remain in the geo location where the site was created, either by preventing the site from being moved or by preventing the caching of the site's file content in another geo location.</span></span>

<span data-ttu-id="dc39d-105">Du kan göra det genom att använda cmdleten [set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) med parametern **RestrictedToGeo** .</span><span class="sxs-lookup"><span data-stu-id="dc39d-105">You can do this by using the [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) cmdlet with the **RestrictedToGeo** parameter.</span></span> <span data-ttu-id="dc39d-106">Den här parametern har standardvärdet NULL men du kan ändra den till något av följande:</span><span class="sxs-lookup"><span data-stu-id="dc39d-106">This parameter has a default value of NULL, but you can change it to one of the following:</span></span>

|<span data-ttu-id="dc39d-107">Av</span><span class="sxs-lookup"><span data-stu-id="dc39d-107">Restriction</span></span>|<span data-ttu-id="dc39d-108">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="dc39d-108">Description</span></span>|
|:----------|:----------|
|<span data-ttu-id="dc39d-109">Begränsning</span><span class="sxs-lookup"><span data-stu-id="dc39d-109">NoRestriction</span></span>|<span data-ttu-id="dc39d-110">Webbplatsen kan flyttas till en annan Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="dc39d-110">The site can be moved to another geo location.</span></span>|
|<span data-ttu-id="dc39d-111">BlockMoveOnly</span><span class="sxs-lookup"><span data-stu-id="dc39d-111">BlockMoveOnly</span></span>|<span data-ttu-id="dc39d-112">Webbplatsen kan inte flyttas till en annan Geo-plats, men webbplats innehållet kan cachelagras på andra geo platser.</span><span class="sxs-lookup"><span data-stu-id="dc39d-112">Site cannot be moved to another geo location, but site content can be cached in other geo locations.</span></span>|
|<span data-ttu-id="dc39d-113">BlockFull</span><span class="sxs-lookup"><span data-stu-id="dc39d-113">BlockFull</span></span>|<span data-ttu-id="dc39d-114">Webbplatsen kan inte flyttas till en annan Geo-plats och fullständig fil innehåll lagras inte i andra geo-platser.</span><span class="sxs-lookup"><span data-stu-id="dc39d-114">Site cannot be moved to another geo location, and full file content is not cached in other geo locations.</span></span> <span data-ttu-id="dc39d-115">Filernas titel (skördad från innehållet), fil namnet och andra egenskaper för filen kan fortfarande lagras i andra geo-platser.</span><span class="sxs-lookup"><span data-stu-id="dc39d-115">Files' title (harvested from the content), file name, and other properties of the file can still be cached in other geo-locations.</span></span><br><span data-ttu-id="dc39d-116">Innehåll som lagras på webbplatsen innan det var konfigurerat till BlockFull kan fortsätta att cachelagras på andra geo platser.</span><span class="sxs-lookup"><span data-stu-id="dc39d-116">Content stored in the site before it was configured to BlockFull, may continue to be cached in other geo locations.</span></span>|

<span data-ttu-id="dc39d-117">Använd följande syntax:</span><span class="sxs-lookup"><span data-stu-id="dc39d-117">Use the following syntax:</span></span>

`Set-SPOSite -Identity <siteURL> -RestrictedToGeo <restriction>`

<span data-ttu-id="dc39d-118">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="dc39d-118">For example:</span></span>

`Set-SPOSite -Identity https://contoso.sharepoint.com/sites/RegionRestrictedTeamSite -RestrictedToGeo BlockFull`
