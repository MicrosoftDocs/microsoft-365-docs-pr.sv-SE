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
ms.openlocfilehash: 216012791473776395d27821293e8fc565568c2c
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547956"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a>Microsoft 365 multi-geo eDiscovery-konfiguration

Som standard kan en eDiscovery-chef eller administratör för en multi-geo-klient leda en eDiscovery endast på den centrala platsen för denna klient organisation. För att stöda möjligheten att genomföra eDiscovery för satellit platser är en ny parameter för reglerad säkerhets filter med namnet "region" tillgänglig via PowerShell.

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
