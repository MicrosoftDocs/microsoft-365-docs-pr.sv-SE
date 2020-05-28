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
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Lär dig hur du använder cmdleten AllowSelfServicePurchase PowerShell för att aktivera eller inaktivera självbetjäningsköp.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: ec5ebe814066916de5cafc176cdcd82bfd416a57
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403696"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a><span data-ttu-id="ed96b-103">Använd AllowSelfServicePurchase för MSCommerce PowerShell-modulen</span><span class="sxs-lookup"><span data-stu-id="ed96b-103">Use AllowSelfServicePurchase for the MSCommerce PowerShell module</span></span>

<span data-ttu-id="ed96b-104">**MSCommerce** PowerShell-modulen är nu tillgänglig på [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span><span class="sxs-lookup"><span data-stu-id="ed96b-104">The **MSCommerce** PowerShell module is now available on [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span> <span data-ttu-id="ed96b-105">Modulen innehåller ett **PolicyID-parametervärde** för **AllowSelfServicePurchase** som låter dig styra om användare i organisationen kan göra självbetjäningsköp.</span><span class="sxs-lookup"><span data-stu-id="ed96b-105">The module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases.</span></span>

<span data-ttu-id="ed96b-106">Du kan använda **MSCommerce** PowerShell-modulen för att:</span><span class="sxs-lookup"><span data-stu-id="ed96b-106">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="ed96b-107">Visa standardtillståndet för parametervärdet **AllowSelfServicePurchase** – oavsett om det är aktiverat eller inaktiverat</span><span class="sxs-lookup"><span data-stu-id="ed96b-107">View the default state of the **AllowSelfServicePurchase** parameter value — whether it's enabled or disabled</span></span>
- <span data-ttu-id="ed96b-108">Visa en lista över tillämpliga produkter och om självbetjäningsköp är aktiverat eller inaktiverat</span><span class="sxs-lookup"><span data-stu-id="ed96b-108">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="ed96b-109">Visa eller ändra den aktuella inställningen för en viss produkt för att antingen aktivera eller inaktivera den</span><span class="sxs-lookup"><span data-stu-id="ed96b-109">View or modify the current setting for a specific product to either enable or disable it</span></span>

## <a name="requirements"></a><span data-ttu-id="ed96b-110">Krav</span><span class="sxs-lookup"><span data-stu-id="ed96b-110">Requirements</span></span>

<span data-ttu-id="ed96b-111">Om du vill använda **MSCommerce** PowerShell-modulen behöver du:</span><span class="sxs-lookup"><span data-stu-id="ed96b-111">To use the **MSCommerce** PowerShell module, you need:</span></span>

- <span data-ttu-id="ed96b-112">En Windows 10-enhet</span><span class="sxs-lookup"><span data-stu-id="ed96b-112">A Windows 10 device</span></span>
- <span data-ttu-id="ed96b-113">Administratörsbehörighet för enheten</span><span class="sxs-lookup"><span data-stu-id="ed96b-113">Administrator permission for the device</span></span>
- <span data-ttu-id="ed96b-114">Global eller faktureringsadministratörsroll för din klientorganisation</span><span class="sxs-lookup"><span data-stu-id="ed96b-114">Global or Billing Admin role for your tenant</span></span>

## <a name="install-the-mscommerce-powershell-module"></a><span data-ttu-id="ed96b-115">Installera MSCommerce PowerShell-modulen</span><span class="sxs-lookup"><span data-stu-id="ed96b-115">Install the MSCommerce PowerShell module</span></span>

<span data-ttu-id="ed96b-116">Du installerar **MSCommerce** PowerShell-modulen på din Windows 10-enhet en gång och importerar den sedan till varje PowerShell-session som du startar.</span><span class="sxs-lookup"><span data-stu-id="ed96b-116">You install the **MSCommerce** PowerShell module on your Windows 10 device once and then import it into each PowerShell session you start.</span></span> <span data-ttu-id="ed96b-117">Hämta **MSCommerce** PowerShell-modulen från [PowerShell-galleriet](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span><span class="sxs-lookup"><span data-stu-id="ed96b-117">Download the **MSCommerce** PowerShell module from the [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span>

<span data-ttu-id="ed96b-118">Så här installerar du **MSCommerce** PowerShell-modulen med **PowerShellGet**kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="ed96b-118">To install the **MSCommerce** PowerShell module with **PowerShellGet**, run the following command:</span></span>

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a><span data-ttu-id="ed96b-119">Importera MS-handel till PowerShell-sessionen</span><span class="sxs-lookup"><span data-stu-id="ed96b-119">Import MSCommerce into the PowerShell session</span></span>

<span data-ttu-id="ed96b-120">När du har installerat modulen på din Windows 10-enhet importerar du den sedan till varje PowerShell-session som du startar.</span><span class="sxs-lookup"><span data-stu-id="ed96b-120">After you install the module on your Windows 10 device, you then import it into each PowerShell session that you start.</span></span> <span data-ttu-id="ed96b-121">Om du vill importera den till en PowerShell-session kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="ed96b-121">To import it into a PowerShell session, run the following command:</span></span>

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a><span data-ttu-id="ed96b-122">Ansluta till MS-handel med dina autentiseringsuppgifter</span><span class="sxs-lookup"><span data-stu-id="ed96b-122">Connect to MSCommerce with your credentials</span></span>

<span data-ttu-id="ed96b-123">Om du vill ansluta till PowerShell-modulen med dina autentiseringsuppgifter kör du följande kommando.</span><span class="sxs-lookup"><span data-stu-id="ed96b-123">To connect to the PowerShell module with your credentials, run the following command.</span></span>

```powershell
Connect-MSCommerce
```

<span data-ttu-id="ed96b-124">Det här kommandot ansluter den aktuella PowerShell-sessionen till en Azure Active Directory-klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="ed96b-124">This command connects the current PowerShell session to an Azure Active Directory tenant.</span></span> <span data-ttu-id="ed96b-125">Kommandot frågar dig för ett användarnamn och lösenord för den klient som du vill ansluta till.</span><span class="sxs-lookup"><span data-stu-id="ed96b-125">The command prompts you for a username and password for the tenant you want to connect to.</span></span> <span data-ttu-id="ed96b-126">Om multifaktorautentisering är aktiverat för dina autentiseringsuppgifter använder du det interaktiva alternativet för att logga in.</span><span class="sxs-lookup"><span data-stu-id="ed96b-126">If multi-factor authentication is enabled for your credentials, you use the interactive option to log in.</span></span>

## <a name="view-details-for-allowselfservicepurchase"></a><span data-ttu-id="ed96b-127">Visa information för AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="ed96b-127">View details for AllowSelfServicePurchase</span></span>

<span data-ttu-id="ed96b-128">Om du vill visa en beskrivning av parametervärdet **AllowSelfServicePurchase** och standardstatus, baserat på din organisation, kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="ed96b-128">To view a description of the **AllowSelfServicePurchase** parameter value and the default status, based on your organization, run the following command:</span></span>

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a><span data-ttu-id="ed96b-129">Visa en lista över självbetjäningsköpsprodukter och deras status</span><span class="sxs-lookup"><span data-stu-id="ed96b-129">View a list of self-service purchase products and their status</span></span>

<span data-ttu-id="ed96b-130">Om du vill visa en lista över alla tillgängliga självbetjäningsprodukter och status för varje kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="ed96b-130">To view a list of all available self-service purchase products and the status of each, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

<span data-ttu-id="ed96b-131">I följande tabell visas tillgängliga produkter och deras **ProductId**.</span><span class="sxs-lookup"><span data-stu-id="ed96b-131">The following table lists the available products and their **ProductId**.</span></span>

| <span data-ttu-id="ed96b-132">Produkt</span><span class="sxs-lookup"><span data-stu-id="ed96b-132">Product</span></span> | <span data-ttu-id="ed96b-133">Produktionen</span><span class="sxs-lookup"><span data-stu-id="ed96b-133">ProductId</span></span> |
|-----------------------------|--------------|
| <span data-ttu-id="ed96b-134">Power Apps per användare</span><span class="sxs-lookup"><span data-stu-id="ed96b-134">Power Apps per user</span></span> | <span data-ttu-id="ed96b-135">CFQ7TTC0KP0P</span><span class="sxs-lookup"><span data-stu-id="ed96b-135">CFQ7TTC0KP0P</span></span> |
| <span data-ttu-id="ed96b-136">Power Automate per användare</span><span class="sxs-lookup"><span data-stu-id="ed96b-136">Power Automate per user</span></span> | <span data-ttu-id="ed96b-137">CFQ7TTC0KP0N</span><span class="sxs-lookup"><span data-stu-id="ed96b-137">CFQ7TTC0KP0N</span></span> |
| <span data-ttu-id="ed96b-138">Power BI Pro</span><span class="sxs-lookup"><span data-stu-id="ed96b-138">Power BI Pro</span></span> | <span data-ttu-id="ed96b-139">CFQ7TTC0L3PB</span><span class="sxs-lookup"><span data-stu-id="ed96b-139">CFQ7TTC0L3PB</span></span> |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a><span data-ttu-id="ed96b-140">Visa eller ange status för AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="ed96b-140">View or set the status for AllowSelfServicePurchase</span></span>

<span data-ttu-id="ed96b-141">När du har visat listan över produkter som är tillgängliga för självbetjäningsköp kan du visa eller ändra inställningen för en viss produkt.</span><span class="sxs-lookup"><span data-stu-id="ed96b-141">After you view the list of products available for self-service purchase, you can view or modify the setting for a specific product.</span></span>

<span data-ttu-id="ed96b-142">Om du vill hämta principinställningen för en viss produkt kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="ed96b-142">To get the policy setting for a specific product, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

<span data-ttu-id="ed96b-143">Om du vill aktivera principinställningen för en viss produkt kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="ed96b-143">To enable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

<span data-ttu-id="ed96b-144">Om du vill inaktivera principinställningen för en viss produkt kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="ed96b-144">To disable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a><span data-ttu-id="ed96b-145">Exempel skript för att inaktivera AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="ed96b-145">Example script to disable AllowSelfServicePurchase</span></span>

<span data-ttu-id="ed96b-146">I följande exempel går du igenom hur du importerar **MS-handelsmodulen,** loggar in med ditt konto, hämtar **ProductId** för Power Automate och inaktiverar sedan **AllowSelfServicePurchase** för den produkten.</span><span class="sxs-lookup"><span data-stu-id="ed96b-146">The following example walks you through how to import the **MSCommerce** module, sign in with your account, get the **ProductId** for Power Automate, and then disable **AllowSelfServicePurchase** for that product.</span></span>

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a><span data-ttu-id="ed96b-147">Felsökning</span><span class="sxs-lookup"><span data-stu-id="ed96b-147">Troubleshooting</span></span>

<span data-ttu-id="ed96b-148">**Problem**</span><span class="sxs-lookup"><span data-stu-id="ed96b-148">**Problem**</span></span>

<span data-ttu-id="ed96b-149">Följande felmeddelande visas:</span><span class="sxs-lookup"><span data-stu-id="ed96b-149">You see the following error message:</span></span>

    HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying
    connection was closed: An unexpected error occurred on a send.

<span data-ttu-id="ed96b-150">Detta kan bero på en äldre version av Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="ed96b-150">This may be due to an older version of Transport Layer Security (TLS).</span></span> <span data-ttu-id="ed96b-151">För att ansluta den här tjänsten måste du använda TLS 1.2 eller mer</span><span class="sxs-lookup"><span data-stu-id="ed96b-151">To connect this service you need to use TLS 1.2 or greater</span></span>

<span data-ttu-id="ed96b-152">**Lösning**</span><span class="sxs-lookup"><span data-stu-id="ed96b-152">**Solution**</span></span>

<span data-ttu-id="ed96b-153">Uppgradera till TLS 1.2:[https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span><span class="sxs-lookup"><span data-stu-id="ed96b-153">Upgrade to TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span></span>

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
