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
description: Lär dig hur du använder parametern region för att konfigurera eDiscovery för användning på satellit platser i Microsoft 365 multi-geo.
ms.openlocfilehash: d1d66a9e7953b540e318c8364bdcb8d72654b482
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48636811"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a>Microsoft 365 multi-geo eDiscovery-konfiguration

[Avancerade eDiscovery-funktioner](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) tillåter en multi-geo eDiscovery-administratör för att söka i alla geos utan att behöva använda ett "region"-säkerhets filter. Data exporteras till Azure-instansen av den centrala platsen för multi-geo-klienten. 

Utan avancerade eDiscovery-funktioner kan en eDiscovery Manager eller administratör av en multi-geo-klient leda en eDiscovery endast på den centrala platsen för denna klient organisation. För att stödja möjligheten att genomföra eDiscovery för satellit platser är en ny parameter för säkerhets filter med namnet "region" tillgänglig via PowerShell. Denna parameter kan användas av klient organisationer vars centrala plats är i Nord Amerika, Europa eller Asien Stilla havet. Avancerad eDiscovery rekommenderas för innehavare vars centrala plats inte är i Nord Amerika, Europa eller Asien och som måste genomföra en eDiscovery-geo-platser. 

Den globala administratören för Microsoft 365 måste tilldela eDiscovery Manager-behörigheter för att tillåta att andra utför eDiscovery och tilldela en "region"-parameter i sitt tillämpliga säkerhets filter för efterlevnad för att ange regionen för att genomföra eDiscovery som satellit plats, annars utförs ingen eDiscovery för satellit platsen.

När rollen eDiscovery Manager eller administratör anges för en viss satellit plats kan eDiscovery Manager eller administratören bara utföra eDiscovery-sökåtgärder mot SharePoint-webbplatser och OneDrive-webbplatser på den satellit platsen. Om en eDiscovery Manager eller administratör försöker söka i SharePoint-eller OneDrive-webbplatser utanför angiven satellit plats returneras inga resultat. När eDiscovery Manager eller administratören för en satellit plats utlöser en export, exporteras data till Azure-instansen av den regionen. Detta hjälper organisationer att hålla sig à jour genom att inte tillåta att innehåll exporteras över kontrollerade kant linjer.

> [!NOTE]
> Om det är nödvändigt för en eDiscovery Manager att söka på flera platser för SharePoint-satellit måste ett annat användar konto skapas för eDiscovery Manager som anger den alternativa satellit platsen där OneDrive-eller SharePoint-webbplatserna finns.

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

Så här anger du säkerhets filter för efterlevnad för en region:

1. [Ansluta till Microsoft 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)

2. Använd följande syntax:

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName <TheNameYouWantToAssign> -Region <RegionValue> -Users <UserPrincipalName>
   ```

   Ett exempel:

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName "NAM eDiscovery Managers" -Region NAM -Users adwood@contoso.onmicrosoft.com
   ```

Se artikeln [ny ComplianceSecurityFilter](https://docs.microsoft.com/powershell/module/exchange/new-compliancesecurityfilter) för ytterligare parametrar och syntax.
