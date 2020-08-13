---
title: Använda AllowSelfServicePurchase för modulen MSCommerce PowerShell
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Lär dig hur du använder PowerShell-cmdleten AllowSelfServicePurchase för att aktivera eller inaktivera självbetjäningen.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 79ee2d96fa1ae6f49f0402f49ddec34e69257082
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653719"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a>Använda AllowSelfServicePurchase för modulen MSCommerce PowerShell

**MSCommerce** PowerShell-modulen är nu tillgänglig i [PowerShell-galleriet](https://aka.ms/allowselfservicepurchase-powershell-gallery). Modulen innehåller ett **PolicyID** parameter värde för **AllowSelfServicePurchase** som låter dig kontrol lera om användare i organisationen kan göra inköp via egen behållning.

Du kan använda **MSCommerce** PowerShell-modulen till att:

- Visa standard tillståndet för värdet på parametern **AllowSelfServicePurchase** – vare sig det är aktiverat eller inaktiverat
- Visa en lista över tillämpliga produkter och om självbetjänings inköp är aktiverat eller inaktiverat
- Visa eller ändra den aktuella inställningen för en viss produkt för att aktivera eller inaktivera den

## <a name="requirements"></a>Krav

För att använda **MSCommerce** PowerShell-modulen behöver du:

- En Windows 10-enhet
- Administratörs behörighet för enheten
- Rollen global eller fakturerings administratör för din klient organisation

## <a name="install-the-mscommerce-powershell-module"></a>Installera MSCommerce PowerShell-modulen

Du kan installera **MSCommerce** PowerShell-modulen på din Windows 10-enhet och sedan importera den till varje PowerShell-session du startar. Ladda ned **MSCommerce** PowerShell-modulen från [PowerShell-galleriet](https://aka.ms/allowselfservicepurchase-powershell-gallery).

Om du vill installera **MSCommerce** PowerShell-modulen med **PowerShellGet**kör du följande kommando:

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a>Importera MSCommerce till PowerShell-sessionen

När du har installerat modulen på din Windows 10-enhet kan du importera den till varje PowerShell-session som du startar. Om du vill importera den till en PowerShell-session kör du följande kommando:

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a>Anslut till MSCommerce med dina autentiseringsuppgifter

Om du vill ansluta till PowerShell-modulen med dina autentiseringsuppgifter kör du följande kommando.

```powershell
Connect-MSCommerce
```

Det här kommandot ansluter den aktuella PowerShell-sessionen till en Azure Active Directory-klient organisation. Kommandot frågar efter användar namn och lösen ord för den klient organisation som du vill ansluta till. Om multifaktorautentisering är aktiverat för dina autentiseringsuppgifter använder du alternativet interaktiv för att logga in.

## <a name="view-details-for-allowselfservicepurchase"></a>Visa information om AllowSelfServicePurchase

Om du vill visa en beskrivning av värdet på parametern **AllowSelfServicePurchase** och standard statusen baserad på din organisation kör du följande kommando:

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a>Visa en lista över självbetjänings köp produkter och deras status

Om du vill visa en lista över alla tillgängliga inköps produkter för självbetjäning och status för respektive kör du följande kommando:

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

I följande tabell finns de tillgängliga produkterna och deras **Produktnr**.

| Produkt | Produktnr |
|-----------------------------|--------------|
| Power Apps per användare | CFQ7TTC0KP0P |
| Automatisk uppstart per användare | CFQ7TTC0KP0N |
| Power BI Pro | CFQ7TTC0L3PB |
| Project-abonnemang 1 | CFQ7TTC0KXND |
| Project-plan 3 | CFQ7TTC0KXNC |
| Visio abonnemang 1 | CFQ7TTC0KXN9 |
| Visio abonnemang 2 | CFQ7TTC0KXN8 |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a>Visa eller ange status för AllowSelfServicePurchase

När du har tittat på listan över produkter som är tillgängliga för självbetjänings köp kan du Visa eller ändra inställningen för en viss produkt.

Om du vill hämta princip inställningen för en viss produkt kör du följande kommando:

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

Om du vill aktivera princip inställningen för en viss produkt kör du följande kommando:

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

Om du vill inaktivera princip inställningen för en viss produkt kör du följande kommando:

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a>Exempel skript för att inaktivera AllowSelfServicePurchase

I följande exempel får du hjälp med att importera **MSCommerce** -modulen, logga in med ditt konto, få **ProductID** för Power autoautomatisera och sedan inaktivera **AllowSelfServicePurchase** för produkten.

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a>Felsökning

### <a name="problem"></a>Vara

Följande fel meddelande visas:

> HandleError: det gick inte att hämta princip med PolicyId ' AllowSelfServicePurchase ', ErrorMessage-den underliggande anslutningen avslutades: ett oväntat fel uppstod vid sändning.

Detta kan bero på att en äldre version av Transport Layer Security (TLS). För att ansluta den här tjänsten måste du använda TLS 1,2 eller senare

### <a name="solution"></a>Lösning

Uppgradera till TLS 1,2:[https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
