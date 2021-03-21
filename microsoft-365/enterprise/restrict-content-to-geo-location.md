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
# <a name="restrict-sharepoint-site-content-to-a-geo-location"></a>Begränsa SharePoint-webbplatsinnehåll till en geoplats

I vissa fall kan du välja att tillämpa en webbplats och dess filinnehåll på den geoplats där webbplatsen skapades, antingen genom att förhindra att webbplatsen flyttas eller genom att förhindra cachelagring av webbplatsens filinnehåll på en annan geoplats.

Det kan du göra genom att använda cmdleten [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) med **parametern RestrictedToGeo.** Den här parametern har standardvärdet NULL, men du kan ändra den till något av följande:

|Begränsning|Beskrivning|
|:----------|:----------|
|NoRestriction|Webbplatsen kan flyttas till en annan geoplats.|
|BlockMoveOnly|Webbplatsen kan inte flyttas till en annan geoplats, men webbplatsinnehållet kan cachelagras på andra geoplatser.|
|BlockFull|Webbplatsen kan inte flyttas till en annan geoplats och fullständigt filinnehåll cachelagras inte på andra geoplatser. Filernas namn (som inlagrats från innehållet), filnamnet och andra egenskaper för filen kan fortfarande cachelagras på andra geoplatser.<br>Innehåll som lagrats på webbplatsen innan den konfigurerades på BlockFull kan fortsätta att cachelagras på andra geoplatser.|

Använd följande syntax:

`Set-SPOSite -Identity <siteURL> -RestrictedToGeo <restriction>`

Till exempel:

`Set-SPOSite -Identity https://contoso.sharepoint.com/sites/RegionRestrictedTeamSite -RestrictedToGeo BlockFull`