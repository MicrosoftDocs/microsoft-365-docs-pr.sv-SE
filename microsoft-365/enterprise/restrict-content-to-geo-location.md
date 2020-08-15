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
# <a name="restrict-sharepoint-site-content-to-a-geo-location"></a>Begränsa SharePoint-webbplatsens innehåll till en Geo-plats

Under vissa omständigheter kan du välja att tvinga en webbplats och dess fil innehåll att finnas kvar på den Geo-plats där webbplatsen skapades, antingen genom att förhindra att webbplatsen flyttas eller genom att förhindra att webbplats innehållet cachelagras på en annan Geo-plats.

Du kan göra det genom att använda cmdleten [set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) med parametern **RestrictedToGeo** . Den här parametern har standardvärdet NULL men du kan ändra den till något av följande:

|Av|Beskrivning|
|:----------|:----------|
|Begränsning|Webbplatsen kan flyttas till en annan Geo-plats.|
|BlockMoveOnly|Webbplatsen kan inte flyttas till en annan Geo-plats, men webbplats innehållet kan cachelagras på andra geo platser.|
|BlockFull|Webbplatsen kan inte flyttas till en annan Geo-plats och fullständig fil innehåll lagras inte i andra geo-platser. Filernas titel (skördad från innehållet), fil namnet och andra egenskaper för filen kan fortfarande lagras i andra geo-platser.<br>Innehåll som lagras på webbplatsen innan det var konfigurerat till BlockFull kan fortsätta att cachelagras på andra geo platser.|

Använd följande syntax:

`Set-SPOSite -Identity <siteURL> -RestrictedToGeo <restriction>`

Till exempel:

`Set-SPOSite -Identity https://contoso.sharepoint.com/sites/RegionRestrictedTeamSite -RestrictedToGeo BlockFull`
