---
title: Skapa en Microsoft 365-grupp med en viss PDL
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.collection: Strat_SP_gtc
localization_priority: Normal
description: Lär dig hur du skapar en Microsoft 365-grupp med en angiven dataplats i en miljö med flera geodata.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7f02a5eb6d8b30e8381c65d4735812675d35af2b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923750"
---
# <a name="create-a-microsoft-365-group-with-a-specific-pdl"></a>Skapa en Microsoft 365-grupp med en viss PDL

När användare i en geomiljö skapar en Microsoft 365-grupp ställs den önskade dataplatsen automatiskt in på användarens plats. Globala administratörer, SharePoint- och Exchange-administratörer kan skapa grupper i valfri region. 

Om du behöver skapa en grupp med en viss PDL kan du göra det med hjälp av administrationscentret för SharePoint eller via Exchange Online New-UnifiedGroup Microsoft PowerShell-cmdleten. När du gör det etableras både grupppostlådan och SharePoint-webbplatsen som är kopplad till gruppen i det angivna PDL-et.

Om du vill skapa en Microsoft 365-grupp med den PDL som du anger går du till administrationscentret för SharePoint på den geoplats där du vill skapa gruppwebbplatsen.

Ett exempel:

Om du vill skapa en gruppwebbplats på din australiensiska plats kan du gå till https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement

1. Välj **+ Skapa.**
2. Följ processen för att skapa en gruppwebbplats.

Gruppwebbplatsen etableras på den geoplats som motsvarar administrationscentret för SharePoint där du initierade begäran om att skapa webbplatsen. 

Använda Exchange PowerShell 

Anslut till Exchange Online PowerShell och skicka parametern *-MailBoxRegion* med geoplatskoden.

Ett exempel: 

```PowerShell
New-UnifiedGroup -DisplayName MultiGeoEUR -Alias "MultiGeoEUR" -AccessType Public -MailboxRegion EUR 
```

![Skärmbild av New-UnifiedGroup PowerShell-cmdlet med syntax](../media/multi-geo-new-group-with-pdl-powershell.png)

Observera att SharePoint-gruppwebbplatsetablering finns på begäran. Webbplatsen etableras första gången en gruppägare eller medlem försöker komma åt den.

## <a name="geo-location-codes"></a>Geoplatskoder

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="related-topics"></a>Relaterade ämnen

[Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)