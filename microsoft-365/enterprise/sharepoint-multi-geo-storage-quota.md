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
# <a name="sharepoint-storage-quotas-in-multi-geo-environments"></a>SharePoint-lagringslösningar i multi-geo-miljöer

Som standard delar alla geo-platser i en multi-geo-miljö den tillgängliga lagrings kvoten för innehavare.

Med inställningen för SharePoint geo Storage-lagring kan du hantera lagrings kvoten för varje Geo-plats. När du tilldelar en lagrings kvot för en Geo-plats blir den det maximala lagrings utrymmet som är tillgängligt för den geo platsen och den dras från den tillgängliga lagrings kvoten för innehavare. Den återstående tillgängliga innehavaren av lagrings kvoten delas sedan på de konfigurerade geo-platserna för vilka en specifik lagrings kvot inte har tilldelats.

SharePoint-lagringsplatsen för varje Geo-plats kan tilldelas av SharePoint Online-administratören genom att ansluta till Central platsen. Geo-administratörer för satellit platser kan visa lagrings kvoten men kan inte tilldela den.

## <a name="configure-a-storage-quota-for-a-geo-location"></a>Konfigurera en lagrings kvot för en Geo-plats

Använd [Microsoft SharePoint Online-modulen](https://www.microsoft.com/download/details.aspx?id=35588 ) och Anslut till Central platsen för att tilldela lagrings kvoten för en Geo-plats. 

Om du vill tilldela lagrings kvot för en plats kör du cmdlet:

`Set-SPOGeoStorageQuota -GeoLocation <geolocationcode> -StorageQuotaMB <value>`

Om du vill visa lagrings kvoten för den aktuella geo-platsen kör du:

`Get-SPOGeoStorageQuota`

![Skärm bild av PowerShell-fönstret med cmdleten Get-SPOGeoStorageQuota](../media/multi-geo-storage-quota.png)

Om du vill visa lagrings kvoten för alla geo platser kör du:

`Get-SPOGeoStorageQuota -AllLocations`

Om du vill ta bort den tilldelade lagrings kvoten för en Geo-plats anger du `StorageQuota value = 0` :

`Set-SPOGeoStorageQuota -GeoLocation <geolocationcode> -StorageQuotaMB 0`
