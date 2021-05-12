---
title: Använd AllowSelfServicePurchase för modulen MSCommerce PowerShell
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: mijeffer, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_ssp
search.appverid:
- MET150
description: Lär dig hur du använder powerShell-cmdleten AllowSelfServicePurchase för att aktivera eller inaktivera självbetjäning för köp.
ROBOTS: NOINDEX, NOFOLLOW
ms.date: 03/18/2021
ms.openlocfilehash: 09161f69e72babe8270b339243d73444b93d9959
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333380"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a>Använd AllowSelfServicePurchase för modulen MSCommerce PowerShell

**MODULEN MSCommerce** PowerShell finns nu tillgänglig på [PowerShell-galleriet.](https://aka.ms/allowselfservicepurchase-powershell-gallery) Modulen innehåller parametervärdet **PolicyID** för **AllowSelfServicePurchase** som gör att du kan styra om användare i organisationen kan göra köp via självbetjäning.

Du kan använda **modulen MSCommerce** PowerShell för att:

- Visa standardtillståndet för **parametervärdet AllowSelfServicePurchase** – oavsett om det är aktiverat eller inaktiverat
- Visa en lista över tillämpliga produkter och om självbetjäning för köp är aktiverat eller inaktiverat
- Visa eller ändra den aktuella inställningen för en viss produkt för att antingen aktivera eller inaktivera den

## <a name="requirements"></a>Krav

Om du vill använda **modulen MSCommerce** PowerShell behöver du:

- En Windows 10-enhet
- Administratörsbehörighet för enheten
- Rollen global administratör eller faktureringsadministratör för klientorganisationen

## <a name="install-the-mscommerce-powershell-module"></a>Installera modulen MSCommerce PowerShell

Du installerar **MSCommerce** PowerShell-modulen på din Windows 10-enhet en gång och importerar den sedan till varje PowerShell-session du startar. Ladda ned **MODULEN MSCommerce** PowerShell från [PowerShell-galleriet](https://aka.ms/allowselfservicepurchase-powershell-gallery).

Installera **MSCommerce** PowerShell-modulen med **PowerShellGet** genom att köra följande kommando:

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a>Importera MSCommerce till PowerShell-sessionen

När du har installerat modulen på din Windows 10-enhet importerar du den till varje PowerShell-session som du startar. Om du vill importera den till en PowerShell-session kör du följande kommando:

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a>Ansluta till MSCommerce med dina autentiseringsuppgifter

Om du vill ansluta till PowerShell-modulen med dina autentiseringsuppgifter kör du följande kommando.

```powershell
Connect-MSCommerce
```

Det här kommandot ansluter den aktuella PowerShell-sessionen till en Azure Active Directory-klientorganisation. Kommandot uppmanar dig att ange ett användarnamn och lösenord för den klientorganisation som du vill ansluta till. Om multifaktorautentisering är aktiverat för dina autentiseringsuppgifter använder du det interaktiva alternativet för att logga in.

## <a name="view-details-for-allowselfservicepurchase"></a>Visa information om AllowSelfServicePurchase

Om du vill visa en beskrivning **av parametervärdet AllowSelfServicePurchase** och standardstatusen, baserat på din organisation, kör du följande kommando:

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a>Visa en lista över självbetjäningsprodukter och deras status

Om du vill visa en lista över alla tillgängliga produkter för självköp och status för varje produkt kör du följande kommando:

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

I följande tabell visas de tillgängliga produkterna och deras **Produkt-ID.**

| Produkt | Produkt-ID |
|-----------------------------|--------------|
| Power Apps per användare | CFQ7TTC0KP0P |
| Power Automate per användare | CFQ7TTC0KP0N |
| Power Automate RPA | CFQ7TTC0KXG6  |
| Power BI Premium (fristående) | CFQ7TTC0KXG7  |
| Power BI Pro | CFQ7TTC0L3PB |
| Projektplan 1 | CFQ7TTC0KXND |
| Projektplan 3 | CFQ7TTC0KXNC |
| Visio abonnemang 1 | CFQ7TTC0KXN9 |
| Visio abonnemang 2 | CFQ7TTC0KXN8 |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a>Visa eller ange status för AllowSelfServicePurchase

När du har tittat på listan över produkter som kan köpas via självbetjäning kan du visa eller ändra inställningen för en viss produkt.

Kör följande kommando för att få principinställningen för en viss produkt:

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

Du aktiverar principinställningen för en viss produkt genom att köra följande kommando:

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

Om du vill inaktivera principinställningen för en viss produkt kör du följande kommando:

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a>Exempelskript för att inaktivera AllowSelfServicePurchase

I följande exempel får du veta hur du importerar **MSCommerce-modulen,** loggar in med ditt konto, hämtar **ProductId** för Power Automate och inaktiverar **sedan AllowSelfServicePurchase** för produkten.

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a>Felsökning

### <a name="problem"></a>Problem

Du ser följande felmeddelande:

> HandleError: Det gick inte att hämta principen med PolicyId 'AllowSelfServicePurchase', ErrorMessage – Den underliggande anslutningen stängdes: Ett oväntat fel uppstod vid ett skicka-meddelande.

Det här kan bero på en äldre version av TLS (Transport Layer Security). Du måste använda TLS 1.2 eller högre för att kunna ansluta den här tjänsten

### <a name="solution"></a>Lösning

Uppgradera till TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](/mem/configmgr/core/plan-design/security/enable-tls-1-2)

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
