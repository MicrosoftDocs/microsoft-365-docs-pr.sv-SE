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
description: Lär dig hur du skapar en Microsoft 365-grupp med angiven önskad data plats i en multi-geo-miljö.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5af32827d11289f7a966311080d2c15197786799
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547740"
---
# <a name="create-a-microsoft-365-group-with-a-specific-pdl"></a><span data-ttu-id="f3df2-103">Skapa en Microsoft 365-grupp med en viss PDL</span><span class="sxs-lookup"><span data-stu-id="f3df2-103">Create a Microsoft 365 Group with a specific PDL</span></span>

<span data-ttu-id="f3df2-104">När användare i en multi-geo-miljö skapar en Microsoft 365-grupp, anges den inställda gruppens data plats automatiskt till den användaren.</span><span class="sxs-lookup"><span data-stu-id="f3df2-104">When users in a multi-geo environment create a Microsoft 365 Group, the group preferred data location is automatically set to that of the user.</span></span> <span data-ttu-id="f3df2-105">Administratörer för global, SharePoint och Exchange kan skapa grupper i vilken region de väljer.</span><span class="sxs-lookup"><span data-stu-id="f3df2-105">Global, SharePoint, and Exchange Administrators can create groups in any region they select.</span></span> 

<span data-ttu-id="f3df2-106">Om du behöver skapa en grupp med en viss PDL kan du göra det från administrations centret för SharePoint eller genom Exchange Online-Unifiedgrouphttps Microsoft PowerShell cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f3df2-106">If you need to create a group with a specific PDL, you can do that using from the SharePoint admin center or through the Exchange Online New-UnifiedGroup Microsoft PowerShell cmdlet.</span></span> <span data-ttu-id="f3df2-107">När du gör det etableras både gruppens post låda och SharePoint-webbplats som är kopplade till gruppen i den angivna PDL.</span><span class="sxs-lookup"><span data-stu-id="f3df2-107">When you do this, both the group mailbox and SharePoint site associated with the group will be provisioned in the specified PDL.</span></span>

<span data-ttu-id="f3df2-108">Om du vill skapa en Microsoft 365-grupp med den PDL som du anger går du till administrations centret för SharePoint på den Geo-plats där du vill skapa grupp webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="f3df2-108">To create a Microsoft 365 Group with the PDL that you specify, go to the SharePoint admin center in the geo location where you want to create the group site.</span></span>

<span data-ttu-id="f3df2-109">Ett exempel:</span><span class="sxs-lookup"><span data-stu-id="f3df2-109">For example:</span></span>

<span data-ttu-id="f3df2-110">Om du vill skapa en grupp webbplats på din Australien-plats kan du gå till https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement</span><span class="sxs-lookup"><span data-stu-id="f3df2-110">If you want to create a group site in your Australia location, you can go to https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement</span></span>

1. <span data-ttu-id="f3df2-111">Välj **+ skapa**.</span><span class="sxs-lookup"><span data-stu-id="f3df2-111">Select **+ Create**.</span></span>
2. <span data-ttu-id="f3df2-112">Följ processen för att skapa en grupp webbplats.</span><span class="sxs-lookup"><span data-stu-id="f3df2-112">Follow the process to create a group site.</span></span>

<span data-ttu-id="f3df2-113">Grupp webbplatsen etableras på den Geo-plats som motsvarar det SharePoint-administrationsobjekt som du initierade begäran om att skapa webbplatser från.</span><span class="sxs-lookup"><span data-stu-id="f3df2-113">Your group site will be provisioned in the geo location corresponding to the SharePoint admin center from which you initiated the site creation request.</span></span> 

<span data-ttu-id="f3df2-114">Använda Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3df2-114">Using Exchange PowerShell</span></span> 

<span data-ttu-id="f3df2-115">Anslut till Exchange Online PowerShell och överför parametern *-MailBoxRegion* till geo-platsens kod.</span><span class="sxs-lookup"><span data-stu-id="f3df2-115">Connect to Exchange Online PowerShell and pass the parameter *-MailBoxRegion* with the geo location code.</span></span>

<span data-ttu-id="f3df2-116">Ett exempel:</span><span class="sxs-lookup"><span data-stu-id="f3df2-116">For example:</span></span> 

```PowerShell
New-UnifiedGroup -DisplayName MultiGeoEUR -Alias "MultiGeoEUR" -AccessType Public -MailboxRegion EUR 
```

![Skärm bild av New-Unifiedgrouphttps PowerShell cmdlet med syntax](../media/multi-geo-new-group-with-pdl-powershell.png)

<span data-ttu-id="f3df2-118">Observera att etableringen av SharePoint-gruppwebbplatsen är på begäran.</span><span class="sxs-lookup"><span data-stu-id="f3df2-118">Note that SharePoint group site provisioning is on-demand.</span></span> <span data-ttu-id="f3df2-119">Webbplatsen etableras första gången en grupp ägare eller medlem försöker komma åt den.</span><span class="sxs-lookup"><span data-stu-id="f3df2-119">The site will be provisioned the first time a group owner or member attempts to access it.</span></span>

## <a name="geo-location-codes"></a><span data-ttu-id="f3df2-120">Geo-plats koder</span><span class="sxs-lookup"><span data-stu-id="f3df2-120">Geo location codes</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="related-topics"></a><span data-ttu-id="f3df2-121">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="f3df2-121">Related topics</span></span>

[<span data-ttu-id="f3df2-122">Ansluta till Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3df2-122">Connect to Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)
