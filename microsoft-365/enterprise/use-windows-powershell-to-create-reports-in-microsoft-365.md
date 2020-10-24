---
title: Använda PowerShell för att skapa rapporter för Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: 1ea4d4ec-af89-496f-9678-701867f5a6fc
description: 'Sammanfattning: Använd PowerShell för Microsoft 365 för att skapa rapporter som inte kan visas i administrations centret för Microsoft 365.'
ms.openlocfilehash: 10000f62b1d6a747cf0373623c6038b080666e1a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753984"
---
# <a name="use-powershell-to-create-reports-for-microsoft-365"></a><span data-ttu-id="1b3c7-103">Använda PowerShell för att skapa rapporter för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1b3c7-103">Use PowerShell to create reports for Microsoft 365</span></span>

<span data-ttu-id="1b3c7-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="1b3c7-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="1b3c7-105">Många olika rapporter är tillgängliga i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1b3c7-105">Many different reports are available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="1b3c7-106">Men dessa rapporter ger bara så mycket information och ibland behövs det.</span><span class="sxs-lookup"><span data-stu-id="1b3c7-106">But these reports only provide so much information, and sometimes you need more.</span></span> <span data-ttu-id="1b3c7-107">Det är när du behöver PowerShell för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1b3c7-107">That's when you need PowerShell for Microsoft 365.</span></span>
  
<span data-ttu-id="1b3c7-108">I de här artiklarna beskrivs hur du använder PowerShell för Microsoft 365 för att hämta information från din Microsoft 365-klient organisation:</span><span class="sxs-lookup"><span data-stu-id="1b3c7-108">These articles describe how to use PowerShell for Microsoft 365 to get information from your Microsoft 365 tenant:</span></span>
  
- <span data-ttu-id="1b3c7-109">Komma igång med rapportering med PowerShell för Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="1b3c7-109">Get started with reporting using PowerShell for Microsoft 365:</span></span>
    
  - [<span data-ttu-id="1b3c7-110">Därför måste du använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1b3c7-110">Why you need to use PowerShell for Microsoft 365</span></span>](https://technet.microsoft.com/library/dn568034.aspx#reveal)
    
    
- <span data-ttu-id="1b3c7-111">Rapporter för användar konton och licenser:</span><span class="sxs-lookup"><span data-stu-id="1b3c7-111">Reports for user accounts and licenses:</span></span>
    
  - [<span data-ttu-id="1b3c7-112">Visa Microsoft 365-licenser och-tjänster med PowerShell</span><span class="sxs-lookup"><span data-stu-id="1b3c7-112">View Microsoft 365 licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="1b3c7-113">Visa Microsoft 365-licensierade och olicensierade användare med PowerShell</span><span class="sxs-lookup"><span data-stu-id="1b3c7-113">View Microsoft 365 licensed and unlicensed users with PowerShell</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="1b3c7-114">Visa Microsoft 365-konto och tjänste uppgifter med PowerShell</span><span class="sxs-lookup"><span data-stu-id="1b3c7-114">View Microsoft 365 account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="1b3c7-115">Visa Microsoft 365-användarkonton med PowerShell</span><span class="sxs-lookup"><span data-stu-id="1b3c7-115">View Microsoft 365 user accounts with PowerShell</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
    
- <span data-ttu-id="1b3c7-116">Rapporter för SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="1b3c7-116">Reports for SharePoint Online:</span></span>
    
  - [<span data-ttu-id="1b3c7-117">Komma igång med SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="1b3c7-117">Get started with SharePoint Online Management Shell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
    
  - [<span data-ttu-id="1b3c7-118">Get-SPOSiteGroup – hämtar alla grupper på en viss webbplats samling</span><span class="sxs-lookup"><span data-stu-id="1b3c7-118">Get-SPOSiteGroup - Gets all the groups on a specified site collection</span></span>](https://technet.microsoft.com/library/122f4099-c78d-4cce-bab0-4343b04596ae.aspx)
    
- <span data-ttu-id="1b3c7-119">Rapporter för Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="1b3c7-119">Reports for Exchange Online:</span></span>
    
  - [<span data-ttu-id="1b3c7-120">Använd Exchange Online PowerShell för att visa post lådan</span><span class="sxs-lookup"><span data-stu-id="1b3c7-120">Use Exchange Online PowerShell to display mailbox</span></span>](https://technet.microsoft.com/library/13843002-56ca-4b75-81c5-84386522b01b.aspx)
    
    
## <a name="related-articlesl"></a><span data-ttu-id="1b3c7-121">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="1b3c7-121">Related articlesl</span></span>

[<span data-ttu-id="1b3c7-122">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="1b3c7-122">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="1b3c7-123">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1b3c7-123">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="1b3c7-124">Hantera SharePoint med PowerShell</span><span class="sxs-lookup"><span data-stu-id="1b3c7-124">Manage SharePoint with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="1b3c7-125">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="1b3c7-125">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  