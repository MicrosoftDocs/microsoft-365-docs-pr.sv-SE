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
ms.openlocfilehash: 0843407e7926027e28cdd1f5893c4aafec4e1cd5
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53230097"
---
# <a name="sharepoint-storage-quotas-in-multi-geo-environments"></a>SharePoint för flera geografiska miljöer

Som standard delar alla geoplatser i en multigeomiljö den tillgängliga lagringskvoten för klientorganisationen.

Med de SharePoint för geolagringskvot kan du hantera lagringskvoten för varje geoplats. När du tilldelar en lagringskvot för en geoplats blir den största tillgängliga lagringsmängden för den geoplatsen och dras av från den tillgängliga klientorganisationens lagringskvot. Den återstående tillgängliga lagringskvoten för klientorganisationen delas sedan över de konfigurerade geoplatser som inte har tilldelats en viss lagringskvot.

Lagringskvoten SharePoint geoplats kan tilldelas av SharePoint Online-administratören genom att ansluta till den centrala platsen. Geoadministratörer för satellitplatser kan visa lagringskvoten men kan inte tilldela den.

## <a name="configure-a-storage-quota-for-a-geo-location"></a>Konfigurera en lagringskvot för en geoplats

Använd Microsoft Office SharePoint Online [och anslut](https://www.microsoft.com/download/details.aspx?id=35588) till den centrala platsen för att tilldela lagringskvoten för en geoplats.

För att tilldela Storage för en plats kör du cmdlet:

```powershell
Set-SPOGeoStorageQuota -GeoLocation <geolocationcode> -StorageQuotaMB <value>
```

Visa Storage för den aktuella geoplatsen genom att köra:

```powershell
Get-SPOGeoStorageQuota
```

![Skärmbild av PowerShell-fönstret med Get-SPOGeoStorageQuota cmdlet](../media/multi-geo-storage-quota.png)

Visa Storage för alla geografiska platser genom att köra:

```powershell
Get-SPOGeoStorageQuota -AllLocations
```

Ta bort den tilldelade lagringskvoten för en geoplats genom att `StorageQuota value = 0` ange:

```powershell
Set-SPOGeoStorageQuota -GeoLocation <geolocationcode> -StorageQuotaMB 0
```
