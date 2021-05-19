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
ms.openlocfilehash: 012874a8794e006d97c4f74014e92e1f7f3c2709
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52536136"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a><span data-ttu-id="25232-103">Använd AllowSelfServicePurchase för modulen MSCommerce PowerShell</span><span class="sxs-lookup"><span data-stu-id="25232-103">Use AllowSelfServicePurchase for the MSCommerce PowerShell module</span></span>

<span data-ttu-id="25232-104">**MODULEN MSCommerce** PowerShell finns nu tillgänglig på [PowerShell-galleriet.](https://aka.ms/allowselfservicepurchase-powershell-gallery)</span><span class="sxs-lookup"><span data-stu-id="25232-104">The **MSCommerce** PowerShell module is now available on [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span> <span data-ttu-id="25232-105">Modulen innehåller parametervärdet **PolicyID** för **AllowSelfServicePurchase** som gör att du kan styra om användare i organisationen kan göra köp via självbetjäning.</span><span class="sxs-lookup"><span data-stu-id="25232-105">The module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases.</span></span>

<span data-ttu-id="25232-106">Du kan använda **modulen MSCommerce** PowerShell för att:</span><span class="sxs-lookup"><span data-stu-id="25232-106">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="25232-107">Visa standardtillståndet för **parametervärdet AllowSelfServicePurchase** – oavsett om det är aktiverat eller inaktiverat</span><span class="sxs-lookup"><span data-stu-id="25232-107">View the default state of the **AllowSelfServicePurchase** parameter value — whether it's enabled or disabled</span></span>
- <span data-ttu-id="25232-108">Visa en lista över tillämpliga produkter och om självbetjäning för köp är aktiverat eller inaktiverat</span><span class="sxs-lookup"><span data-stu-id="25232-108">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="25232-109">Visa eller ändra den aktuella inställningen för en viss produkt för att antingen aktivera eller inaktivera den</span><span class="sxs-lookup"><span data-stu-id="25232-109">View or modify the current setting for a specific product to either enable or disable it</span></span>

## <a name="requirements"></a><span data-ttu-id="25232-110">Krav</span><span class="sxs-lookup"><span data-stu-id="25232-110">Requirements</span></span>

<span data-ttu-id="25232-111">Om du vill använda **modulen MSCommerce** PowerShell behöver du:</span><span class="sxs-lookup"><span data-stu-id="25232-111">To use the **MSCommerce** PowerShell module, you need:</span></span>

- <span data-ttu-id="25232-112">En Windows 10 enhet</span><span class="sxs-lookup"><span data-stu-id="25232-112">A Windows 10 device</span></span>
- <span data-ttu-id="25232-113">PowerShell 5 eller lägre.</span><span class="sxs-lookup"><span data-stu-id="25232-113">PowerShell 5 or below.</span></span> <span data-ttu-id="25232-114">För närvarande stöds inte PowerShell 6.x/7.x med den här modulen.</span><span class="sxs-lookup"><span data-stu-id="25232-114">Currently, PowerShell 6.x/7.x isn't supported with this module.</span></span>
- <span data-ttu-id="25232-115">Administratörsbehörighet för enheten</span><span class="sxs-lookup"><span data-stu-id="25232-115">Administrator permission for the device</span></span>
- <span data-ttu-id="25232-116">Rollen global administratör eller faktureringsadministratör för klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="25232-116">Global or Billing Admin role for your tenant</span></span>

## <a name="install-the-mscommerce-powershell-module"></a><span data-ttu-id="25232-117">Installera modulen MSCommerce PowerShell</span><span class="sxs-lookup"><span data-stu-id="25232-117">Install the MSCommerce PowerShell module</span></span>

<span data-ttu-id="25232-118">Du installerar **MSCommerce** PowerShell-modulen på din Windows 10 en gång och importerar den sedan till varje PowerShell-session du startar.</span><span class="sxs-lookup"><span data-stu-id="25232-118">You install the **MSCommerce** PowerShell module on your Windows 10 device once and then import it into each PowerShell session you start.</span></span> <span data-ttu-id="25232-119">Ladda ned **MODULEN MSCommerce** PowerShell från [PowerShell-galleriet](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span><span class="sxs-lookup"><span data-stu-id="25232-119">Download the **MSCommerce** PowerShell module from the [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span>

<span data-ttu-id="25232-120">Installera **MSCommerce** PowerShell-modulen med **PowerShellGet** genom att köra följande kommando:</span><span class="sxs-lookup"><span data-stu-id="25232-120">To install the **MSCommerce** PowerShell module with **PowerShellGet**, run the following command:</span></span>

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a><span data-ttu-id="25232-121">Importera MSCommerce till PowerShell-sessionen</span><span class="sxs-lookup"><span data-stu-id="25232-121">Import MSCommerce into the PowerShell session</span></span>

<span data-ttu-id="25232-122">När du har installerat modulen på din Windows 10 importerar du den sedan till varje PowerShell-session som du startar.</span><span class="sxs-lookup"><span data-stu-id="25232-122">After you install the module on your Windows 10 device, you then import it into each PowerShell session that you start.</span></span> <span data-ttu-id="25232-123">Om du vill importera den till en PowerShell-session kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="25232-123">To import it into a PowerShell session, run the following command:</span></span>

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a><span data-ttu-id="25232-124">Anslut till MSCommerce med dina autentiseringsuppgifter</span><span class="sxs-lookup"><span data-stu-id="25232-124">Connect to MSCommerce with your credentials</span></span>

<span data-ttu-id="25232-125">Om du vill ansluta till PowerShell-modulen med dina autentiseringsuppgifter kör du följande kommando.</span><span class="sxs-lookup"><span data-stu-id="25232-125">To connect to the PowerShell module with your credentials, run the following command.</span></span>

```powershell
Connect-MSCommerce
```

<span data-ttu-id="25232-126">Det här kommandot ansluter den aktuella PowerShell-sessionen till en Azure Active Directory klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="25232-126">This command connects the current PowerShell session to an Azure Active Directory tenant.</span></span> <span data-ttu-id="25232-127">Kommandot uppmanar dig att ange ett användarnamn och lösenord för den klientorganisation som du vill ansluta till.</span><span class="sxs-lookup"><span data-stu-id="25232-127">The command prompts you for a username and password for the tenant you want to connect to.</span></span> <span data-ttu-id="25232-128">Om multifaktorautentisering är aktiverat för dina autentiseringsuppgifter använder du det interaktiva alternativet för att logga in.</span><span class="sxs-lookup"><span data-stu-id="25232-128">If multi-factor authentication is enabled for your credentials, you use the interactive option to log in.</span></span>

## <a name="view-details-for-allowselfservicepurchase"></a><span data-ttu-id="25232-129">Visa information om AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="25232-129">View details for AllowSelfServicePurchase</span></span>

<span data-ttu-id="25232-130">Om du vill visa en beskrivning **av parametervärdet AllowSelfServicePurchase** och standardstatusen, baserat på din organisation, kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="25232-130">To view a description of the **AllowSelfServicePurchase** parameter value and the default status, based on your organization, run the following command:</span></span>

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a><span data-ttu-id="25232-131">Visa en lista över självbetjäningsprodukter och deras status</span><span class="sxs-lookup"><span data-stu-id="25232-131">View a list of self-service purchase products and their status</span></span>

<span data-ttu-id="25232-132">Om du vill visa en lista över alla tillgängliga produkter för självköp och status för varje produkt kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="25232-132">To view a list of all available self-service purchase products and the status of each, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

<span data-ttu-id="25232-133">I följande tabell visas de tillgängliga produkterna och deras **Produkt-ID.**</span><span class="sxs-lookup"><span data-stu-id="25232-133">The following table lists the available products and their **ProductId**.</span></span>

| <span data-ttu-id="25232-134">Produkt</span><span class="sxs-lookup"><span data-stu-id="25232-134">Product</span></span> | <span data-ttu-id="25232-135">Produkt-ID</span><span class="sxs-lookup"><span data-stu-id="25232-135">ProductId</span></span> |
|-----------------------------|--------------|
| <span data-ttu-id="25232-136">Power Apps per användare</span><span class="sxs-lookup"><span data-stu-id="25232-136">Power Apps per user</span></span> | <span data-ttu-id="25232-137">CFQ7TTC0KP0P</span><span class="sxs-lookup"><span data-stu-id="25232-137">CFQ7TTC0KP0P</span></span> |
| <span data-ttu-id="25232-138">Power Automate per användare</span><span class="sxs-lookup"><span data-stu-id="25232-138">Power Automate per user</span></span> | <span data-ttu-id="25232-139">CFQ7TTC0KP0N</span><span class="sxs-lookup"><span data-stu-id="25232-139">CFQ7TTC0KP0N</span></span> |
| <span data-ttu-id="25232-140">Power Automate RPA</span><span class="sxs-lookup"><span data-stu-id="25232-140">Power Automate RPA</span></span> | <span data-ttu-id="25232-141">CFQ7TTC0KXG6</span><span class="sxs-lookup"><span data-stu-id="25232-141">CFQ7TTC0KXG6</span></span>  |
| <span data-ttu-id="25232-142">Power BI Premium (fristående)</span><span class="sxs-lookup"><span data-stu-id="25232-142">Power BI Premium (standalone)</span></span> | <span data-ttu-id="25232-143">CFQ7TTC0KXG7</span><span class="sxs-lookup"><span data-stu-id="25232-143">CFQ7TTC0KXG7</span></span>  |
| <span data-ttu-id="25232-144">Power BI Pro</span><span class="sxs-lookup"><span data-stu-id="25232-144">Power BI Pro</span></span> | <span data-ttu-id="25232-145">CFQ7TTC0L3PB</span><span class="sxs-lookup"><span data-stu-id="25232-145">CFQ7TTC0L3PB</span></span> |
| <span data-ttu-id="25232-146">Project Abonnemang 1</span><span class="sxs-lookup"><span data-stu-id="25232-146">Project Plan 1</span></span> | <span data-ttu-id="25232-147">CFQ7TTC0KXND</span><span class="sxs-lookup"><span data-stu-id="25232-147">CFQ7TTC0KXND</span></span> |
| <span data-ttu-id="25232-148">Project Abonnemang 3</span><span class="sxs-lookup"><span data-stu-id="25232-148">Project Plan 3</span></span> | <span data-ttu-id="25232-149">CFQ7TTC0KXNC</span><span class="sxs-lookup"><span data-stu-id="25232-149">CFQ7TTC0KXNC</span></span> |
| <span data-ttu-id="25232-150">Visio Abonnemang 1</span><span class="sxs-lookup"><span data-stu-id="25232-150">Visio Plan 1</span></span> | <span data-ttu-id="25232-151">CFQ7TTC0KXN9</span><span class="sxs-lookup"><span data-stu-id="25232-151">CFQ7TTC0KXN9</span></span> |
| <span data-ttu-id="25232-152">Visio Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="25232-152">Visio Plan 2</span></span> | <span data-ttu-id="25232-153">CFQ7TTC0KXN8</span><span class="sxs-lookup"><span data-stu-id="25232-153">CFQ7TTC0KXN8</span></span> |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a><span data-ttu-id="25232-154">Visa eller ange status för AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="25232-154">View or set the status for AllowSelfServicePurchase</span></span>

<span data-ttu-id="25232-155">När du har tittat på listan över produkter som kan köpas via självbetjäning kan du visa eller ändra inställningen för en viss produkt.</span><span class="sxs-lookup"><span data-stu-id="25232-155">After you view the list of products available for self-service purchase, you can view or modify the setting for a specific product.</span></span>

<span data-ttu-id="25232-156">Kör följande kommando för att få principinställningen för en viss produkt:</span><span class="sxs-lookup"><span data-stu-id="25232-156">To get the policy setting for a specific product, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

<span data-ttu-id="25232-157">Du aktiverar principinställningen för en viss produkt genom att köra följande kommando:</span><span class="sxs-lookup"><span data-stu-id="25232-157">To enable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

<span data-ttu-id="25232-158">Om du vill inaktivera principinställningen för en viss produkt kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="25232-158">To disable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a><span data-ttu-id="25232-159">Exempelskript för att inaktivera AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="25232-159">Example script to disable AllowSelfServicePurchase</span></span>

<span data-ttu-id="25232-160">I följande exempel får du veta hur du importerar **MSCommerce-modulen,** loggar in med ditt konto, hämtar **ProductId** för Power Automate och inaktiverar **sedan AllowSelfServicePurchase** för den produkten.</span><span class="sxs-lookup"><span data-stu-id="25232-160">The following example walks you through how to import the **MSCommerce** module, sign in with your account, get the **ProductId** for Power Automate, and then disable **AllowSelfServicePurchase** for that product.</span></span>

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a><span data-ttu-id="25232-161">Felsökning</span><span class="sxs-lookup"><span data-stu-id="25232-161">Troubleshooting</span></span>

### <a name="problem"></a><span data-ttu-id="25232-162">Problem</span><span class="sxs-lookup"><span data-stu-id="25232-162">Problem</span></span>

<span data-ttu-id="25232-163">Du ser följande felmeddelande:</span><span class="sxs-lookup"><span data-stu-id="25232-163">You see the following error message:</span></span>

> <span data-ttu-id="25232-164">HandleError: Det gick inte att hämta principen med PolicyId 'AllowSelfServicePurchase', ErrorMessage – Den underliggande anslutningen stängdes: Ett oväntat fel uppstod vid ett skicka-meddelande.</span><span class="sxs-lookup"><span data-stu-id="25232-164">HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying connection was closed: An unexpected error occurred on a send.</span></span>

<span data-ttu-id="25232-165">Det här kan bero på en äldre version av TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="25232-165">This may be due to an older version of Transport Layer Security (TLS).</span></span> <span data-ttu-id="25232-166">Du måste använda TLS 1.2 eller högre för att kunna ansluta den här tjänsten</span><span class="sxs-lookup"><span data-stu-id="25232-166">To connect this service you need to use TLS 1.2 or greater</span></span>

### <a name="solution"></a><span data-ttu-id="25232-167">Lösning</span><span class="sxs-lookup"><span data-stu-id="25232-167">Solution</span></span>

<span data-ttu-id="25232-168">Uppgradera till TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span><span class="sxs-lookup"><span data-stu-id="25232-168">Upgrade to TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span></span>

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->

## <a name="related-content"></a><span data-ttu-id="25232-169">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="25232-169">Related content</span></span>

<span data-ttu-id="25232-170">[Hantera köp via självbetjäning (administratör)](manage-self-service-purchases-admins.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="25232-170">[Manage self-service purchases (Admin)](manage-self-service-purchases-admins.md) (article)</span></span>

<span data-ttu-id="25232-171">[Vanliga frågor och svar om självbetjäning](self-service-purchase-faq.yml) för köp (artikel)</span><span class="sxs-lookup"><span data-stu-id="25232-171">[Self-service purchase FAQ](self-service-purchase-faq.yml) (article)</span></span>