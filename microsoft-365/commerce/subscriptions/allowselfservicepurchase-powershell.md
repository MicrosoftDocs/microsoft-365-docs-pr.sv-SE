---
title: Använd AllowSelfServicePurchase för MSCommerce PowerShell-modulen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: Lär dig hur du använder cmdleten AllowSelfServicePurchase PowerShell för att aktivera eller inaktivera självbetjäningsköp.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 6c0bcec70eab4266674ca2a22f1b2054807a26e8
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011681"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a>Använd AllowSelfServicePurchase för MSCommerce PowerShell-modulen

**MSCommerce** PowerShell-modulen är nu tillgänglig på [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery). Modulen innehåller ett **PolicyID-parametervärde** för **AllowSelfServicePurchase** som låter dig styra om användare i organisationen kan göra självbetjäningsköp.

Du kan använda **MSCommerce** PowerShell-modulen för att:

- Visa standardtillståndet för parametervärdet **AllowSelfServicePurchase** – oavsett om det är aktiverat eller inaktiverat
- Visa en lista över tillämpliga produkter och om självbetjäningsköp är aktiverat eller inaktiverat
- Visa eller ändra den aktuella inställningen för en viss produkt för att antingen aktivera eller inaktivera den

## <a name="requirements"></a>Krav

Om du vill använda **MSCommerce** PowerShell-modulen behöver du:

- En Windows 10-enhet
- Administratörsbehörighet för enheten
- Global eller faktureringsadministratörsroll för din klientorganisation

## <a name="install-the-mscommerce-powershell-module"></a>Installera MSCommerce PowerShell-modulen

Du installerar **MSCommerce** PowerShell-modulen på din Windows 10-enhet en gång och importerar den sedan till varje PowerShell-session som du startar. Hämta **MSCommerce** PowerShell-modulen från [PowerShell-galleriet](https://aka.ms/allowselfservicepurchase-powershell-gallery).

Så här installerar du **MSCommerce** PowerShell-modulen med **PowerShellGet**kör du följande kommando:

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a>Importera MS-handel till PowerShell-sessionen

När du har installerat modulen på din Windows 10-enhet importerar du den sedan till varje PowerShell-session som du startar. Om du vill importera den till en PowerShell-session kör du följande kommando:

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a>Ansluta till MS-handel med dina autentiseringsuppgifter

Om du vill ansluta till PowerShell-modulen med dina autentiseringsuppgifter kör du följande kommando.

```powershell
Connect-MSCommerce
```

Det här kommandot ansluter den aktuella PowerShell-sessionen till en Azure Active Directory-klientorganisation. Kommandot frågar dig för ett användarnamn och lösenord för den klient som du vill ansluta till. Om multifaktorautentisering är aktiverat för dina autentiseringsuppgifter använder du det interaktiva alternativet för att logga in.

## <a name="view-details-for-allowselfservicepurchase"></a>Visa information för AllowSelfServicePurchase

Om du vill visa en beskrivning av parametervärdet **AllowSelfServicePurchase** och standardstatus, baserat på din organisation, kör du följande kommando:

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a>Visa en lista över självbetjäningsköpsprodukter och deras status

Om du vill visa en lista över alla tillgängliga självbetjäningsprodukter och status för varje kör du följande kommando:

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

I följande tabell visas tillgängliga produkter och deras **ProductId**.

| Produkt | Produktionen |
|-----------------------------|--------------|
| Power Apps per användare | CFQ7TTC0KP0P |
| Power Automate per användare | CFQ7TTC0KP0N |
| Power BI Pro | CFQ7TTC0L3PB |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a>Visa eller ange status för AllowSelfServicePurchase

När du har visat listan över produkter som är tillgängliga för självbetjäningsköp kan du visa eller ändra inställningen för en viss produkt.

Om du vill hämta principinställningen för en viss produkt kör du följande kommando:

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

Om du vill aktivera principinställningen för en viss produkt kör du följande kommando:

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

Om du vill inaktivera principinställningen för en viss produkt kör du följande kommando:

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a>Exempel skript för att inaktivera AllowSelfServicePurchase

I följande exempel går du igenom hur du importerar **MS-handelsmodulen,** loggar in med ditt konto, hämtar **ProductId** för Power Automate och inaktiverar sedan **AllowSelfServicePurchase** för den produkten.

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a>Felsökning

**Problem**

Följande felmeddelande visas:

    HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying
    connection was closed: An unexpected error occurred on a send.

Detta kan bero på en äldre version av Transport Layer Security (TLS). För att ansluta den här tjänsten måste du använda TLS 1.2 eller mer

**Lösning**

Uppgradera till TLS 1.2:[https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
