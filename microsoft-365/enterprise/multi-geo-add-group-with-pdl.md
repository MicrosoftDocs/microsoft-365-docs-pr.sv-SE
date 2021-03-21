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
description: Lär dig hur du skapar en Microsoft 365-grupp med en angiven dataplats i en miljö med flera geodata.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7f02a5eb6d8b30e8381c65d4735812675d35af2b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923750"
---
# <a name="create-a-microsoft-365-group-with-a-specific-pdl"></a><span data-ttu-id="b9766-103">Skapa en Microsoft 365-grupp med en viss PDL</span><span class="sxs-lookup"><span data-stu-id="b9766-103">Create a Microsoft 365 Group with a specific PDL</span></span>

<span data-ttu-id="b9766-104">När användare i en geomiljö skapar en Microsoft 365-grupp ställs den önskade dataplatsen automatiskt in på användarens plats.</span><span class="sxs-lookup"><span data-stu-id="b9766-104">When users in a multi-geo environment create a Microsoft 365 Group, the group preferred data location is automatically set to that of the user.</span></span> <span data-ttu-id="b9766-105">Globala administratörer, SharePoint- och Exchange-administratörer kan skapa grupper i valfri region.</span><span class="sxs-lookup"><span data-stu-id="b9766-105">Global, SharePoint, and Exchange Administrators can create groups in any region they select.</span></span> 

<span data-ttu-id="b9766-106">Om du behöver skapa en grupp med en viss PDL kan du göra det med hjälp av administrationscentret för SharePoint eller via Exchange Online New-UnifiedGroup Microsoft PowerShell-cmdleten.</span><span class="sxs-lookup"><span data-stu-id="b9766-106">If you need to create a group with a specific PDL, you can do that using from the SharePoint admin center or through the Exchange Online New-UnifiedGroup Microsoft PowerShell cmdlet.</span></span> <span data-ttu-id="b9766-107">När du gör det etableras både grupppostlådan och SharePoint-webbplatsen som är kopplad till gruppen i det angivna PDL-et.</span><span class="sxs-lookup"><span data-stu-id="b9766-107">When you do this, both the group mailbox and SharePoint site associated with the group will be provisioned in the specified PDL.</span></span>

<span data-ttu-id="b9766-108">Om du vill skapa en Microsoft 365-grupp med den PDL som du anger går du till administrationscentret för SharePoint på den geoplats där du vill skapa gruppwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="b9766-108">To create a Microsoft 365 Group with the PDL that you specify, go to the SharePoint admin center in the geo location where you want to create the group site.</span></span>

<span data-ttu-id="b9766-109">Ett exempel:</span><span class="sxs-lookup"><span data-stu-id="b9766-109">For example:</span></span>

<span data-ttu-id="b9766-110">Om du vill skapa en gruppwebbplats på din australiensiska plats kan du gå till https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement</span><span class="sxs-lookup"><span data-stu-id="b9766-110">If you want to create a group site in your Australia location, you can go to https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement</span></span>

1. <span data-ttu-id="b9766-111">Välj **+ Skapa.**</span><span class="sxs-lookup"><span data-stu-id="b9766-111">Select **+ Create**.</span></span>
2. <span data-ttu-id="b9766-112">Följ processen för att skapa en gruppwebbplats.</span><span class="sxs-lookup"><span data-stu-id="b9766-112">Follow the process to create a group site.</span></span>

<span data-ttu-id="b9766-113">Gruppwebbplatsen etableras på den geoplats som motsvarar administrationscentret för SharePoint där du initierade begäran om att skapa webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="b9766-113">Your group site will be provisioned in the geo location corresponding to the SharePoint admin center from which you initiated the site creation request.</span></span> 

<span data-ttu-id="b9766-114">Använda Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9766-114">Using Exchange PowerShell</span></span> 

<span data-ttu-id="b9766-115">Anslut till Exchange Online PowerShell och skicka parametern *-MailBoxRegion* med geoplatskoden.</span><span class="sxs-lookup"><span data-stu-id="b9766-115">Connect to Exchange Online PowerShell and pass the parameter *-MailBoxRegion* with the geo location code.</span></span>

<span data-ttu-id="b9766-116">Ett exempel:</span><span class="sxs-lookup"><span data-stu-id="b9766-116">For example:</span></span> 

```PowerShell
New-UnifiedGroup -DisplayName MultiGeoEUR -Alias "MultiGeoEUR" -AccessType Public -MailboxRegion EUR 
```

![Skärmbild av New-UnifiedGroup PowerShell-cmdlet med syntax](../media/multi-geo-new-group-with-pdl-powershell.png)

<span data-ttu-id="b9766-118">Observera att SharePoint-gruppwebbplatsetablering finns på begäran.</span><span class="sxs-lookup"><span data-stu-id="b9766-118">Note that SharePoint group site provisioning is on-demand.</span></span> <span data-ttu-id="b9766-119">Webbplatsen etableras första gången en gruppägare eller medlem försöker komma åt den.</span><span class="sxs-lookup"><span data-stu-id="b9766-119">The site will be provisioned the first time a group owner or member attempts to access it.</span></span>

## <a name="geo-location-codes"></a><span data-ttu-id="b9766-120">Geoplatskoder</span><span class="sxs-lookup"><span data-stu-id="b9766-120">Geo location codes</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="related-topics"></a><span data-ttu-id="b9766-121">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="b9766-121">Related topics</span></span>

[<span data-ttu-id="b9766-122">Ansluta till Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9766-122">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)