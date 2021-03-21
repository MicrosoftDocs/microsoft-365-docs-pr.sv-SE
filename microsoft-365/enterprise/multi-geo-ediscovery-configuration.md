---
title: Konfigurera Microsoft 365 Multi-Geo eDiscovery
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
localization_priority: Normal
ms.collection: Strat_SP_gtc
description: Lär dig hur du använder parametern Region för att konfigurera eDiscovery för användning i satellitplatser i Microsoft 365 Multi-Geo.
ms.openlocfilehash: 4d3481fe8b72bb970893ce065293a7a2cc717331
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923726"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a>Microsoft 365 Multi-Geo eDiscovery-konfiguration

[Med avancerade eDiscovery-funktioner](../compliance/overview-ediscovery-20.md) kan en eDiscovery-administratör med flera funktioner söka i alla geos utan att behöva använda ett "Region"-säkerhetsfilter. Data exporteras till Azure-instansen av den centrala platsen för den geoa klientorganisationen. 

Utan avancerade eDiscovery-funktioner kan en eDiscovery-hanterare eller administratör för en geoklient för flera geoklienter utföra eDiscovery endast på den centrala platsen för innehavaren. För att stödja möjligheten att utföra eDiscovery för satellitplatser är en ny säkerhetsfilterparameter för efterlevnad med namnet Region tillgänglig via PowerShell. Den här parametern kan användas av klientorganisationen vars centrala plats är i Nordamerika, Europa eller Asien och Stilla havet. Advanced eDiscovery rekommenderas för klientorganisationen vars centrala plats inte finns i Nordamerika, Europa eller Asien och Stilla havet och som behöver utföra eDiscovery över satellitgeoplatser. 

Den globala Microsoft 365-administratören måste tilldela eDiscovery Manager-behörigheter så att andra kan utföra eDiscovery och tilldela en "Region"-parameter i sitt tillämpliga säkerhetsfilter för efterlevnad för att ange området för eDiscovery som satellitplats, annars utförs ingen eDiscovery för satellitplatsen.

När rollen eDiscovery-hanterare eller administratör har angetts för en viss satellitplats kan eDiscovery-hanteraren eller administratören bara utföra eDiscovery-sökåtgärder mot SharePoint-webbplatserna och OneDrive-webbplatserna på den satellitplatsen. Om en eDiscovery-hanterare eller administratör försöker söka efter SharePoint- eller OneDrive-webbplatser utanför den angivna satellitplatsen returneras inga resultat. Och när eDiscovery-hanteraren eller administratören för en satellitplats utlöser en export exporteras data till Azure-instansen av den regionen. På så sätt ser du till att organisationer följer reglerna genom att inte tillåta att innehåll exporteras över styrda kantlinjer.

> [!NOTE]
> Om det är nödvändigt för en eDiscovery-hanterare att söka i flera SharePoint-satellitplatser måste ett annat användarkonto skapas för eDiscovery-hanteraren, som anger den alternativa satellitplats där OneDrive- eller SharePoint-webbplatserna finns.

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

Så här ställer du in säkerhetsfiltret för efterlevnad för en region:

1. [Ansluta till Microsoft 365 Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell)

2. Använd följande syntax:

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName <TheNameYouWantToAssign> -Region <RegionValue> -Users <UserPrincipalName>
   ```

   Ett exempel:

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName "NAM eDiscovery Managers" -Region NAM -Users adwood@contoso.onmicrosoft.com
   ```

Fler parametrar och syntax finns i artikeln [New-ComplianceSecurityFilter.](/powershell/module/exchange/new-compliancesecurityfilter)