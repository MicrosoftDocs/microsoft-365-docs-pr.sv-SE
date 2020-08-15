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
ms.openlocfilehash: 99aa86b1b58b15c63803e1b71d071cbde5c38492
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694644"
---
# <a name="use-powershell-to-create-reports-for-microsoft-365"></a><span data-ttu-id="44be9-103">Använda PowerShell för att skapa rapporter för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="44be9-103">Use PowerShell to create reports for Microsoft 365</span></span>

<span data-ttu-id="44be9-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="44be9-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="44be9-105">Det finns många olika rapporter i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="44be9-105">There are many different reports available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="44be9-106">Rapporterna ger emellertid bara så mycket information och ibland behövs det.</span><span class="sxs-lookup"><span data-stu-id="44be9-106">However, these reports only provide so much information and sometimes you need more.</span></span> <span data-ttu-id="44be9-107">Det är när du behöver PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="44be9-107">That's when you need PowerShell for Microsoft 365</span></span>
  
<span data-ttu-id="44be9-108">I de här artiklarna beskrivs hur du använder PowerShell för Microsoft 365 för att få information från din Microsoft 365-klient organisation:</span><span class="sxs-lookup"><span data-stu-id="44be9-108">These articles that describe how to use PowerShell for Microsoft 365 to obtain information from your Microsoft 365 tenant:</span></span>
  
- <span data-ttu-id="44be9-109">Komma igång med rapportering med PowerShell för Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="44be9-109">Getting started with reporting using PowerShell for Microsoft 365:</span></span>
    
  - [<span data-ttu-id="44be9-110">PowerShell för Microsoft 365 kan visa ytterligare information som inte kan visas i administrations centret</span><span class="sxs-lookup"><span data-stu-id="44be9-110">PowerShell for Microsoft 365 can reveal additional information that you cannot see with the Admin center</span></span>](https://technet.microsoft.com/library/dn568034.aspx#reveal)
    
  - [<span data-ttu-id="44be9-111">PowerShell för Microsoft 365 är ett bra sätt att filtrera data</span><span class="sxs-lookup"><span data-stu-id="44be9-111">PowerShell for Microsoft 365 is great at filtering data</span></span>](https://technet.microsoft.com/library/dn568034.aspx#filter)
    
  - [<span data-ttu-id="44be9-112">Med PowerShell för Microsoft 365 blir det enkelt att skriva ut eller spara data</span><span class="sxs-lookup"><span data-stu-id="44be9-112">PowerShell for Microsoft 365 makes it easy to print or save data</span></span>](https://technet.microsoft.com/library/dn568034.aspx#printsave)
    
- <span data-ttu-id="44be9-113">Rapporter för användar konton och licenser:</span><span class="sxs-lookup"><span data-stu-id="44be9-113">Reports for user accounts and licenses:</span></span>
    
  - [<span data-ttu-id="44be9-114">Visa Microsoft 365-licenser och-tjänster med PowerShell</span><span class="sxs-lookup"><span data-stu-id="44be9-114">View Microsoft 365 licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="44be9-115">Visa Microsoft 365-licensierade och olicensierade användare med PowerShell</span><span class="sxs-lookup"><span data-stu-id="44be9-115">View Microsoft 365 licensed and unlicensed users with PowerShell</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="44be9-116">Visa Microsoft 365-konto och tjänste uppgifter med PowerShell</span><span class="sxs-lookup"><span data-stu-id="44be9-116">View Microsoft 365 account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="44be9-117">Visa Microsoft 365-användarkonton med PowerShell</span><span class="sxs-lookup"><span data-stu-id="44be9-117">View Microsoft 365 user accounts with PowerShell</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
    
- <span data-ttu-id="44be9-118">Rapporter för SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="44be9-118">Reports for SharePoint Online:</span></span>
    
  - [<span data-ttu-id="44be9-119">Komma igång med SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="44be9-119">Get started with SharePoint Online Management Shell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
    
  - [<span data-ttu-id="44be9-120">Hantera webbplats grupper för SharePoint Online med PowerShell</span><span class="sxs-lookup"><span data-stu-id="44be9-120">Manage SharePoint Online site groups with PowerShell</span></span>](https://technet.microsoft.com/library/122f4099-c78d-4cce-bab0-4343b04596ae.aspx)
    
- <span data-ttu-id="44be9-121">Rapporter för Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="44be9-121">Reports for Exchange Online:</span></span>
    
  - [<span data-ttu-id="44be9-122">Visa information om Exchange Online-postlådor med PowerShell</span><span class="sxs-lookup"><span data-stu-id="44be9-122">Display Exchange Online mailbox information with PowerShell</span></span>](https://technet.microsoft.com/library/13843002-56ca-4b75-81c5-84386522b01b.aspx)
    
  - [<span data-ttu-id="44be9-123">Visa Exchange Online-rapporter med PowerShell</span><span class="sxs-lookup"><span data-stu-id="44be9-123">Display Exchange Online reports with PowerShell</span></span>](https://technet.microsoft.com/library/4873a063-9fc4-4ed9-826a-6e935fef61d4.aspx)
    
## <a name="related-topics"></a><span data-ttu-id="44be9-124">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="44be9-124">Related topics</span></span>

[<span data-ttu-id="44be9-125">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="44be9-125">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="44be9-126">Komma igång med PowerShell för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="44be9-126">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="44be9-127">Hantera SharePoint Online med PowerShell</span><span class="sxs-lookup"><span data-stu-id="44be9-127">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="44be9-128">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="44be9-128">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
