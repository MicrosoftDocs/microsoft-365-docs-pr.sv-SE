---
title: Använd AllowSelfServicePurchase för modulen MSCommerce PowerShell
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
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce
search.appverid:
- MET150
description: Lär dig hur du använder powerShell-cmdleten AllowSelfServicePurchase för att aktivera eller inaktivera självbetjäning för köp.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 9fb5593855f9523198a3d70548e444a831e82c80
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918248"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a><span data-ttu-id="872d3-103">Använd AllowSelfServicePurchase för modulen MSCommerce PowerShell</span><span class="sxs-lookup"><span data-stu-id="872d3-103">Use AllowSelfServicePurchase for the MSCommerce PowerShell module</span></span>

<span data-ttu-id="872d3-104">**MODULEN MSCommerce** PowerShell finns nu tillgänglig på [PowerShell-galleriet.](https://aka.ms/allowselfservicepurchase-powershell-gallery)</span><span class="sxs-lookup"><span data-stu-id="872d3-104">The **MSCommerce** PowerShell module is now available on [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span> <span data-ttu-id="872d3-105">Modulen innehåller parametervärdet **PolicyID** för **AllowSelfServicePurchase** som gör att du kan styra om användare i organisationen kan göra köp via självbetjäning.</span><span class="sxs-lookup"><span data-stu-id="872d3-105">The module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases.</span></span>

<span data-ttu-id="872d3-106">Du kan använda **modulen MSCommerce** PowerShell för att:</span><span class="sxs-lookup"><span data-stu-id="872d3-106">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="872d3-107">Visa standardtillståndet för **parametervärdet AllowSelfServicePurchase** – oavsett om det är aktiverat eller inaktiverat</span><span class="sxs-lookup"><span data-stu-id="872d3-107">View the default state of the **AllowSelfServicePurchase** parameter value — whether it's enabled or disabled</span></span>
- <span data-ttu-id="872d3-108">Visa en lista över tillämpliga produkter och om självbetjäning för köp är aktiverat eller inaktiverat</span><span class="sxs-lookup"><span data-stu-id="872d3-108">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="872d3-109">Visa eller ändra den aktuella inställningen för en viss produkt för att antingen aktivera eller inaktivera den</span><span class="sxs-lookup"><span data-stu-id="872d3-109">View or modify the current setting for a specific product to either enable or disable it</span></span>

## <a name="requirements"></a><span data-ttu-id="872d3-110">Krav</span><span class="sxs-lookup"><span data-stu-id="872d3-110">Requirements</span></span>

<span data-ttu-id="872d3-111">Om du vill använda **modulen MSCommerce** PowerShell behöver du:</span><span class="sxs-lookup"><span data-stu-id="872d3-111">To use the **MSCommerce** PowerShell module, you need:</span></span>

- <span data-ttu-id="872d3-112">En Windows 10-enhet</span><span class="sxs-lookup"><span data-stu-id="872d3-112">A Windows 10 device</span></span>
- <span data-ttu-id="872d3-113">Administratörsbehörighet för enheten</span><span class="sxs-lookup"><span data-stu-id="872d3-113">Administrator permission for the device</span></span>
- <span data-ttu-id="872d3-114">Rollen global administratör eller faktureringsadministratör för klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="872d3-114">Global or Billing Admin role for your tenant</span></span>

## <a name="install-the-mscommerce-powershell-module"></a><span data-ttu-id="872d3-115">Installera modulen MSCommerce PowerShell</span><span class="sxs-lookup"><span data-stu-id="872d3-115">Install the MSCommerce PowerShell module</span></span>

<span data-ttu-id="872d3-116">Du installerar **MSCommerce** PowerShell-modulen på din Windows 10-enhet en gång och importerar den sedan till varje PowerShell-session du startar.</span><span class="sxs-lookup"><span data-stu-id="872d3-116">You install the **MSCommerce** PowerShell module on your Windows 10 device once and then import it into each PowerShell session you start.</span></span> <span data-ttu-id="872d3-117">Ladda ned **MODULEN MSCommerce** PowerShell från [PowerShell-galleriet](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span><span class="sxs-lookup"><span data-stu-id="872d3-117">Download the **MSCommerce** PowerShell module from the [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span>

<span data-ttu-id="872d3-118">Installera **MSCommerce** PowerShell-modulen med **PowerShellGet** genom att köra följande kommando:</span><span class="sxs-lookup"><span data-stu-id="872d3-118">To install the **MSCommerce** PowerShell module with **PowerShellGet**, run the following command:</span></span>

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a><span data-ttu-id="872d3-119">Importera MSCommerce till PowerShell-sessionen</span><span class="sxs-lookup"><span data-stu-id="872d3-119">Import MSCommerce into the PowerShell session</span></span>

<span data-ttu-id="872d3-120">När du har installerat modulen på din Windows 10-enhet importerar du den till varje PowerShell-session som du startar.</span><span class="sxs-lookup"><span data-stu-id="872d3-120">After you install the module on your Windows 10 device, you then import it into each PowerShell session that you start.</span></span> <span data-ttu-id="872d3-121">Om du vill importera den till en PowerShell-session kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="872d3-121">To import it into a PowerShell session, run the following command:</span></span>

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a><span data-ttu-id="872d3-122">Ansluta till MSCommerce med dina autentiseringsuppgifter</span><span class="sxs-lookup"><span data-stu-id="872d3-122">Connect to MSCommerce with your credentials</span></span>

<span data-ttu-id="872d3-123">Om du vill ansluta till PowerShell-modulen med dina autentiseringsuppgifter kör du följande kommando.</span><span class="sxs-lookup"><span data-stu-id="872d3-123">To connect to the PowerShell module with your credentials, run the following command.</span></span>

```powershell
Connect-MSCommerce
```

<span data-ttu-id="872d3-124">Det här kommandot ansluter den aktuella PowerShell-sessionen till en Azure Active Directory-klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="872d3-124">This command connects the current PowerShell session to an Azure Active Directory tenant.</span></span> <span data-ttu-id="872d3-125">Kommandot uppmanar dig att ange ett användarnamn och lösenord för den klientorganisation som du vill ansluta till.</span><span class="sxs-lookup"><span data-stu-id="872d3-125">The command prompts you for a username and password for the tenant you want to connect to.</span></span> <span data-ttu-id="872d3-126">Om multifaktorautentisering är aktiverat för dina autentiseringsuppgifter använder du det interaktiva alternativet för att logga in.</span><span class="sxs-lookup"><span data-stu-id="872d3-126">If multi-factor authentication is enabled for your credentials, you use the interactive option to log in.</span></span>

## <a name="view-details-for-allowselfservicepurchase"></a><span data-ttu-id="872d3-127">Visa information om AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="872d3-127">View details for AllowSelfServicePurchase</span></span>

<span data-ttu-id="872d3-128">Om du vill visa en beskrivning **av parametervärdet AllowSelfServicePurchase** och standardstatusen, baserat på din organisation, kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="872d3-128">To view a description of the **AllowSelfServicePurchase** parameter value and the default status, based on your organization, run the following command:</span></span>

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a><span data-ttu-id="872d3-129">Visa en lista över självbetjäningsprodukter och deras status</span><span class="sxs-lookup"><span data-stu-id="872d3-129">View a list of self-service purchase products and their status</span></span>

<span data-ttu-id="872d3-130">Om du vill visa en lista över alla tillgängliga produkter för självköp och status för varje produkt kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="872d3-130">To view a list of all available self-service purchase products and the status of each, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

<span data-ttu-id="872d3-131">I följande tabell visas de tillgängliga produkterna och deras **Produkt-ID.**</span><span class="sxs-lookup"><span data-stu-id="872d3-131">The following table lists the available products and their **ProductId**.</span></span>

| <span data-ttu-id="872d3-132">Produkt</span><span class="sxs-lookup"><span data-stu-id="872d3-132">Product</span></span> | <span data-ttu-id="872d3-133">Produkt-ID</span><span class="sxs-lookup"><span data-stu-id="872d3-133">ProductId</span></span> |
|-----------------------------|--------------|
| <span data-ttu-id="872d3-134">Power Apps per användare</span><span class="sxs-lookup"><span data-stu-id="872d3-134">Power Apps per user</span></span> | <span data-ttu-id="872d3-135">CFQ7TTC0KP0P</span><span class="sxs-lookup"><span data-stu-id="872d3-135">CFQ7TTC0KP0P</span></span> |
| <span data-ttu-id="872d3-136">Power Automate per användare</span><span class="sxs-lookup"><span data-stu-id="872d3-136">Power Automate per user</span></span> | <span data-ttu-id="872d3-137">CFQ7TTC0KP0N</span><span class="sxs-lookup"><span data-stu-id="872d3-137">CFQ7TTC0KP0N</span></span> |
| <span data-ttu-id="872d3-138">Power Automate RPA</span><span class="sxs-lookup"><span data-stu-id="872d3-138">Power Automate RPA</span></span> | <span data-ttu-id="872d3-139">CFQ7TTC0KXG6</span><span class="sxs-lookup"><span data-stu-id="872d3-139">CFQ7TTC0KXG6</span></span>  |
| <span data-ttu-id="872d3-140">Power BI Premium (fristående)</span><span class="sxs-lookup"><span data-stu-id="872d3-140">Power BI Premium (standalone)</span></span> | <span data-ttu-id="872d3-141">CFQ7TTC0KXG7</span><span class="sxs-lookup"><span data-stu-id="872d3-141">CFQ7TTC0KXG7</span></span>  |
| <span data-ttu-id="872d3-142">Power BI Pro</span><span class="sxs-lookup"><span data-stu-id="872d3-142">Power BI Pro</span></span> | <span data-ttu-id="872d3-143">CFQ7TTC0L3PB</span><span class="sxs-lookup"><span data-stu-id="872d3-143">CFQ7TTC0L3PB</span></span> |
| <span data-ttu-id="872d3-144">Projektplan 1</span><span class="sxs-lookup"><span data-stu-id="872d3-144">Project Plan 1</span></span> | <span data-ttu-id="872d3-145">CFQ7TTC0KXND</span><span class="sxs-lookup"><span data-stu-id="872d3-145">CFQ7TTC0KXND</span></span> |
| <span data-ttu-id="872d3-146">Projektplan 3</span><span class="sxs-lookup"><span data-stu-id="872d3-146">Project Plan 3</span></span> | <span data-ttu-id="872d3-147">CFQ7TTC0KXNC</span><span class="sxs-lookup"><span data-stu-id="872d3-147">CFQ7TTC0KXNC</span></span> |
| <span data-ttu-id="872d3-148">Visio abonnemang 1</span><span class="sxs-lookup"><span data-stu-id="872d3-148">Visio Plan 1</span></span> | <span data-ttu-id="872d3-149">CFQ7TTC0KXN9</span><span class="sxs-lookup"><span data-stu-id="872d3-149">CFQ7TTC0KXN9</span></span> |
| <span data-ttu-id="872d3-150">Visio abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="872d3-150">Visio Plan 2</span></span> | <span data-ttu-id="872d3-151">CFQ7TTC0KXN8</span><span class="sxs-lookup"><span data-stu-id="872d3-151">CFQ7TTC0KXN8</span></span> |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a><span data-ttu-id="872d3-152">Visa eller ange status för AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="872d3-152">View or set the status for AllowSelfServicePurchase</span></span>

<span data-ttu-id="872d3-153">När du har tittat på listan över produkter som kan köpas via självbetjäning kan du visa eller ändra inställningen för en viss produkt.</span><span class="sxs-lookup"><span data-stu-id="872d3-153">After you view the list of products available for self-service purchase, you can view or modify the setting for a specific product.</span></span>

<span data-ttu-id="872d3-154">Kör följande kommando för att få principinställningen för en viss produkt:</span><span class="sxs-lookup"><span data-stu-id="872d3-154">To get the policy setting for a specific product, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

<span data-ttu-id="872d3-155">Du aktiverar principinställningen för en viss produkt genom att köra följande kommando:</span><span class="sxs-lookup"><span data-stu-id="872d3-155">To enable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

<span data-ttu-id="872d3-156">Om du vill inaktivera principinställningen för en viss produkt kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="872d3-156">To disable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a><span data-ttu-id="872d3-157">Exempelskript för att inaktivera AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="872d3-157">Example script to disable AllowSelfServicePurchase</span></span>

<span data-ttu-id="872d3-158">I följande exempel får du veta hur du importerar **MSCommerce-modulen,** loggar in med ditt konto, hämtar **ProductId** för Power Automate och inaktiverar **sedan AllowSelfServicePurchase** för produkten.</span><span class="sxs-lookup"><span data-stu-id="872d3-158">The following example walks you through how to import the **MSCommerce** module, sign in with your account, get the **ProductId** for Power Automate, and then disable **AllowSelfServicePurchase** for that product.</span></span>

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a><span data-ttu-id="872d3-159">Felsökning</span><span class="sxs-lookup"><span data-stu-id="872d3-159">Troubleshooting</span></span>

### <a name="problem"></a><span data-ttu-id="872d3-160">Problem</span><span class="sxs-lookup"><span data-stu-id="872d3-160">Problem</span></span>

<span data-ttu-id="872d3-161">Du ser följande felmeddelande:</span><span class="sxs-lookup"><span data-stu-id="872d3-161">You see the following error message:</span></span>

> <span data-ttu-id="872d3-162">HandleError: Det gick inte att hämta principen med PolicyId 'AllowSelfServicePurchase', ErrorMessage – Den underliggande anslutningen stängdes: Ett oväntat fel uppstod vid ett skicka-meddelande.</span><span class="sxs-lookup"><span data-stu-id="872d3-162">HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying connection was closed: An unexpected error occurred on a send.</span></span>

<span data-ttu-id="872d3-163">Det här kan bero på en äldre version av TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="872d3-163">This may be due to an older version of Transport Layer Security (TLS).</span></span> <span data-ttu-id="872d3-164">Du måste använda TLS 1.2 eller högre för att kunna ansluta den här tjänsten</span><span class="sxs-lookup"><span data-stu-id="872d3-164">To connect this service you need to use TLS 1.2 or greater</span></span>

### <a name="solution"></a><span data-ttu-id="872d3-165">Lösning</span><span class="sxs-lookup"><span data-stu-id="872d3-165">Solution</span></span>

<span data-ttu-id="872d3-166">Uppgradera till TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span><span class="sxs-lookup"><span data-stu-id="872d3-166">Upgrade to TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span></span>

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->