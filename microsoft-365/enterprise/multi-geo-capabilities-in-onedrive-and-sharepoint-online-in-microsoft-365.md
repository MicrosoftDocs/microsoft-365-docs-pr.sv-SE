---
title: Multi-Geo Capabilities i OneDrive och SharePoint Online
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
localization_priority: Normal
ms.assetid: 094e86f2-9ff0-40ac-af31-28fcaba00c1d
description: Utöka din Microsoft 365 närvaro till flera geografiska områden med flera geofunktioner i OneDrive Online.
ms.openlocfilehash: 8f42b071abef0602304f1a468190c33700fe3e82
ms.sourcegitcommit: 321610fd312e5c54ae8a757a71ab0c9fd2f1ac03
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/11/2020
ms.locfileid: "48995915"
---
# <a name="multi-geo-capabilities-in-onedrive-and-sharepoint-online"></a>Multi-Geo Capabilities i OneDrive och SharePoint Online

Multi-Geo capabilities in OneDrive and SharePoint Online enables control of shared resources like SharePoint team sites and Microsoft 365 Group mailboxes stored at rest in a country or region.

Varje användare, grupppostlåda och SharePoint-webbplats har en PDL-plats (Preferred Data Location) som betecknar den geografiska plats där relaterade data ska lagras. Användarnas personliga data (Exchange-postlådan och OneDrive) tillsammans med eventuella Microsoft 365-grupper eller SharePoint-webbplatser som de skapar kan lagras på den angivna geoplatsen för att uppfylla krav på datalagring. Du kan [ange olika administratörer för varje geoplats.](add-a-sharepoint-geo-admin.md)

Användarna får en smidig upplevelse när de Microsoft 365-tjänster, Office program, OneDrive och sökning. Mer [information finns i Användarupplevelse i en geomiljö](multi-geo-user-experience.md) med flera miljön.

## <a name="onedrive"></a>OneDrive

Varje användares OneDrive kan etableras i eller flyttas av en [administratör](move-onedrive-between-geo-locations.md) till en satellitplats i enlighet med användarens PDL. Personliga filer sparas sedan på den geoplatsen, men de kan delas med användare på andra geoplatser.

## <a name="sharepoint-sites-and-groups"></a>SharePoint Webbplatser och grupper

Hantering av Multi-Geo-funktionen är tillgänglig via SharePoint administrationscenter. Detaljerad information finns i [motsvarande blogginlägg.](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)

När en användare skapar en SharePoint gruppansluten webbplats i en geomiljö används deras PDL för att fastställa den geografiska plats där webbplatsen och dess tillhörande grupppostlåda skapas. (Om användarens PDL-värde inte har angetts, eller har angetts till en geoplats som inte har konfigurerats som en satellitplats, skapas webbplatsen och postlådan på den centrala platsen.)

Microsoft 365 andra tjänster än Exchange, OneDrive och SharePoint inte är Multi-Geo. Men Microsoft 365 Grupper som skapas av dessa tjänster stämplas med PDL för skaparen och deras Exchange-grupppostlåda och SharePoint O365-gruppwebbplats etableras i motsvarande geo. 

## <a name="managing-the-multi-geo-environment"></a>Hantera multigeobaserade miljöer

Du kan konfigurera och hantera din multigeobaserade miljö via SharePoint administrationscenter. 

![Skärmbild av sidan geoplatser i SharePoint administrationscenter](../media/sharepoint-multi-geo-admin-center.png)

(Vissa åtgärder, till exempel för att flytta SharePoint webbplats eller en OneDrive-webbplats, kräver Microsoft PowerShell.)

## <a name="see-also"></a>Se även

[Multi-Geo i SharePoint och Microsoft 365 Grupper](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)

[Administrera en Multi-Geo-Miljö](administering-a-multi-geo-environment.md)

[SharePoint för flera geografiska miljöer](sharepoint-multi-geo-storage-quota.md)

[Administrera Exchange Online postlådor i en miljö med flera geografiska miljöer](administering-exchange-online-multi-geo.md)
