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
description: Lär dig hur du skapar en Microsoft 365-grupp med angiven önskad data plats i en multi-geo-miljö.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5af32827d11289f7a966311080d2c15197786799
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547740"
---
# <a name="create-a-microsoft-365-group-with-a-specific-pdl"></a>Skapa en Microsoft 365-grupp med en viss PDL

När användare i en multi-geo-miljö skapar en Microsoft 365-grupp, anges den inställda gruppens data plats automatiskt till den användaren. Administratörer för global, SharePoint och Exchange kan skapa grupper i vilken region de väljer. 

Om du behöver skapa en grupp med en viss PDL kan du göra det från administrations centret för SharePoint eller genom Exchange Online-Unifiedgrouphttps Microsoft PowerShell cmdlet. När du gör det etableras både gruppens post låda och SharePoint-webbplats som är kopplade till gruppen i den angivna PDL.

Om du vill skapa en Microsoft 365-grupp med den PDL som du anger går du till administrations centret för SharePoint på den Geo-plats där du vill skapa grupp webbplatsen.

Ett exempel:

Om du vill skapa en grupp webbplats på din Australien-plats kan du gå till https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement

1. Välj **+ skapa**.
2. Följ processen för att skapa en grupp webbplats.

Grupp webbplatsen etableras på den Geo-plats som motsvarar det SharePoint-administrationsobjekt som du initierade begäran om att skapa webbplatser från. 

Använda Exchange PowerShell 

Anslut till Exchange Online PowerShell och överför parametern *-MailBoxRegion* till geo-platsens kod.

Ett exempel: 

```PowerShell
New-UnifiedGroup -DisplayName MultiGeoEUR -Alias "MultiGeoEUR" -AccessType Public -MailboxRegion EUR 
```

![Skärm bild av New-Unifiedgrouphttps PowerShell cmdlet med syntax](../media/multi-geo-new-group-with-pdl-powershell.png)

Observera att etableringen av SharePoint-gruppwebbplatsen är på begäran. Webbplatsen etableras första gången en grupp ägare eller medlem försöker komma åt den.

## <a name="geo-location-codes"></a>Geo-plats koder

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="related-topics"></a>Relaterade ämnen

[Ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)
