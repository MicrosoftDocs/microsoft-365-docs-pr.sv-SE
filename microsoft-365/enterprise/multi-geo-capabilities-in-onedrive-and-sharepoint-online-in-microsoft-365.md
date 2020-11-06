---
title: Multi-geo-funktioner i OneDrive och SharePoint Online
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
description: Utöka din Microsoft 365-närvaro till flera geografiska regioner med flera geo-funktioner i OneDrive online.
ms.openlocfilehash: 84abfc01d5073889e998347f58d4a3e8bb29ea33
ms.sourcegitcommit: 5a355bde865369f64ea1788a378da23c65b1d249
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2020
ms.locfileid: "48930183"
---
# <a name="multi-geo-capabilities-in-onedrive-and-sharepoint-online"></a>Multi-geo-funktioner i OneDrive och SharePoint Online

Multi-geo-funktioner i OneDrive och SharePoint Online möjliggör kontroll över det land eller den region där delade resurser som SharePoint-gruppwebbplatser och Microsoft 365-grupppost lådor lagras på resten.

Varje användare, grupp post låda och SharePoint-webbplats har en önskad data plats (PDL) som anger den Geo-plats där relaterade data ska lagras. Användares person uppgifter (Exchange-postlåda och OneDrive) tillsammans med alla Microsoft 365-grupper eller SharePoint-webbplatser som de skapar kan lagras på angiven Geo-plats för att uppfylla data de kraven. Du kan [ange olika administratörer för varje Geo-plats](add-a-sharepoint-geo-admin.md).

Användarna får en sömlös upplevelse när de använder Microsoft 365-tjänster, inklusive Office-program, OneDrive och sökning. Mer information finns [i användar miljön i en multi-geo-miljö](multi-geo-user-experience.md) .

## <a name="onedrive"></a>OneDrive

Varje användares OneDrive kan etableras i eller [flyttas av en administratör](move-onedrive-between-geo-locations.md) till en satellit plats i enlighet med användarens PDL. Personliga filer behålls i den geo platsen, även om de kan delas med användarna på andra geo platser.

## <a name="sharepoint-sites-and-groups"></a>SharePoint-webbplatser och-grupper

Hanteringen av multi-geo-funktionen är tillgänglig via administrations centret för SharePoint. Detaljerad information finns i [motsvarande blogg inlägg](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302).

När en användare skapar en SharePoint-gruppansluten webbplats i en multi-geo-miljö används deras PDL för att bestämma den Geo-plats där webbplatsen och dess tillhör ande grupp post låda skapas. (Om användarens PDL-värde inte har ställts in, eller har ställts in på Geo-platsen som inte har kon figurer ATS som en satellit plats, skapas webbplatsen och post lådan på den centrala platsen.)

Microsoft 365-tjänster som inte är Exchange, OneDrive och SharePoint är inte Multi-geo. Men Microsoft 365-grupper som skapas av de här tjänsterna stämplas med den som har skapat den och Exchange-gruppwebbplatsen och SharePoint O365-grupp webbplatsen som tillhandahålls i motsvarande geo. 

## <a name="managing-the-multi-geo-environment"></a>Hantera multi-geo-miljön

Konfigurering och hantering av multi-geo-miljön sker via administrations centret för SharePoint. 

![Skärm bild av sidan geo locations i administrations centret för SharePoint](../media/sharepoint-multi-geo-admin-center.png)

(Vissa åtgärder, till exempel att flytta en SharePoint-webbplats eller en OneDrive-webbplats, kräver Microsoft PowerShell.)

## <a name="see-also"></a>Se även

[Multi-geo i SharePoint-och Microsoft 365-grupper](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)

[Administrera en Multi-Geo-Miljö](administering-a-multi-geo-environment.md)

[SharePoint-lagringslösningar i multi-geo-miljöer](sharepoint-multi-geo-storage-quota.md)

[Administrera Exchange Online-postlådor i en multi-geo-miljö](administering-exchange-online-multi-geo.md)
