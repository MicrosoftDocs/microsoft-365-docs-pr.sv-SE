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
description: Sammanfattning Använd PowerShell för Microsoft 365 för att skapa rapporter som du inte kan skapa i administrationscentret för Microsoft 365.
ms.openlocfilehash: dc183ae8a315bf788befc85474d0647802ac91ee
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222785"
---
# <a name="use-powershell-to-create-reports-for-microsoft-365"></a><span data-ttu-id="65910-103">Använda PowerShell för att skapa rapporter för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="65910-103">Use PowerShell to create reports for Microsoft 365</span></span>

<span data-ttu-id="65910-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="65910-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="65910-105">Många olika rapporter är tillgängliga i administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="65910-105">Many different reports are available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="65910-106">Men de här rapporterna ger bara så mycket information och ibland behöver du mer.</span><span class="sxs-lookup"><span data-stu-id="65910-106">But these reports only provide so much information, and sometimes you need more.</span></span> <span data-ttu-id="65910-107">Det är då du behöver PowerShell för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="65910-107">That's when you need PowerShell for Microsoft 365.</span></span>
  
<span data-ttu-id="65910-108">I de här artiklarna beskrivs hur du använder PowerShell för Microsoft 365 för att få information från Microsoft 365-klienten:</span><span class="sxs-lookup"><span data-stu-id="65910-108">These articles describe how to use PowerShell for Microsoft 365 to get information from your Microsoft 365 tenant:</span></span>
  
- <span data-ttu-id="65910-109">Kom igång med rapportering med PowerShell för Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="65910-109">Get started with reporting using PowerShell for Microsoft 365:</span></span>
    
  - [<span data-ttu-id="65910-110">Varför du behöver använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="65910-110">Why you need to use PowerShell for Microsoft 365</span></span>](./why-you-need-to-use-microsoft-365-powershell.md)
    
    
- <span data-ttu-id="65910-111">Rapporter för användarkonton och licenser:</span><span class="sxs-lookup"><span data-stu-id="65910-111">Reports for user accounts and licenses:</span></span>
    
  - [<span data-ttu-id="65910-112">Visa Microsoft 365-licenser och -tjänster med PowerShell</span><span class="sxs-lookup"><span data-stu-id="65910-112">View Microsoft 365 licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="65910-113">Visa licensierade och olicensierade Microsoft 365-användare med PowerShell</span><span class="sxs-lookup"><span data-stu-id="65910-113">View Microsoft 365 licensed and unlicensed users with PowerShell</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="65910-114">Visa Microsoft 365-kontolicens och tjänstinformation med PowerShell</span><span class="sxs-lookup"><span data-stu-id="65910-114">View Microsoft 365 account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="65910-115">Visa Microsoft 365-användarkonton med PowerShell</span><span class="sxs-lookup"><span data-stu-id="65910-115">View Microsoft 365 user accounts with PowerShell</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
    
- <span data-ttu-id="65910-116">Rapporter för SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="65910-116">Reports for SharePoint Online:</span></span>
    
  - [<span data-ttu-id="65910-117">Komma igång med SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="65910-117">Get started with SharePoint Online Management Shell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
    
  - [<span data-ttu-id="65910-118">Get-SPOSiteGroup – Hämtar alla grupper i en viss webbplatssamling</span><span class="sxs-lookup"><span data-stu-id="65910-118">Get-SPOSiteGroup - Gets all the groups on a specified site collection</span></span>](/powershell/module/sharepoint-online/get-spositegroup)
    
- <span data-ttu-id="65910-119">Rapporter för Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="65910-119">Reports for Exchange Online:</span></span>
    
  - [<span data-ttu-id="65910-120">Använda Exchange Online PowerShell för att visa postlådan</span><span class="sxs-lookup"><span data-stu-id="65910-120">Use Exchange Online PowerShell to display mailbox</span></span>](/exchange/recipients-in-exchange-online/manage-user-mailboxes/use-powershell-to-display-mailbox-information)
    
    
## <a name="related-articlesl"></a><span data-ttu-id="65910-121">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="65910-121">Related articlesl</span></span>

[<span data-ttu-id="65910-122">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="65910-122">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="65910-123">Börja använda PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="65910-123">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="65910-124">Hantera SharePoint med PowerShell</span><span class="sxs-lookup"><span data-stu-id="65910-124">Manage SharePoint with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="65910-125">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="65910-125">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
