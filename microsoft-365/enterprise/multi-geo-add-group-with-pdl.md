---
title: Skapa en Microsoft 365 grupp med en viss önskad dataplats
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
description: Lär dig hur du skapar Microsoft 365 grupp med en angiven dataplats i en geomiljö med flera platser.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41984dc24e0f30e5e7b7eb0f9672c75b6d65388f
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086831"
---
# <a name="create-a-microsoft-365-group-with-a-specific-preferred-data-location"></a>Skapa en Microsoft 365 grupp med en viss önskad dataplats

När användare i en geomiljö skapar en Microsoft 365 grupp ställs den önskade dataplatsen (PDL) automatiskt in på användarens plats. Globala, SharePoint och Exchange Administratörer kan skapa grupper i valfri region. 

Om du behöver skapa en grupp med en viss PDL kan du göra det med hjälp av administrationscentret i SharePoint eller via Exchange Online New-UnifiedGroup Microsoft PowerShell-cmdleten. När du gör det etableras både grupppostlådan och den SharePoint som är kopplad till gruppen i den angivna PDL-webbplatsen.

Om du vill Microsoft 365 grupp med den PDL som du anger går du till administrationscentret SharePoint på den geoplats där du vill skapa gruppwebbplatsen.

Till exempel:

Om du vill skapa en gruppwebbplats på din australiensiska plats kan du gå till https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement

1. Välj **+ Skapa.**
2. Följ processen för att skapa en gruppwebbplats.

Gruppwebbplatsen etableras på den geoplats som motsvarar det SharePoint administrationscenter som du initierade begäran om att skapa webbplatsen från. 

Använda Exchange PowerShell 

Anslut att Exchange Online powershell och överföra parametern *-MailBoxRegion* med geoplatskoden.

Till exempel: 

```PowerShell
New-UnifiedGroup -DisplayName MultiGeoEUR -Alias "MultiGeoEUR" -AccessType Public -MailboxRegion EUR 
```

![Skärmbild av New-UnifiedGroup PowerShell-cmdlet med syntax](../media/multi-geo-new-group-with-pdl-powershell.png)

Observera SharePoint om gruppwebbplatsetablering är på begäran. Webbplatsen etableras första gången en gruppägare eller medlem försöker komma åt den.

## <a name="geo-location-codes"></a>Geoplatskoder

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="related-topics"></a>Relaterade ämnen

[Anslut till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)
