---
title: Begränsningar i grundläggande e-dataidentifieringsfall
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: I den här artikeln beskrivs gränserna för grundläggande e-dataidentifieringsfall i Microsoft 365.
ms.openlocfilehash: e7b1013abd9fd94748baf3b83dd04efbc3831a1d
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311430"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="1c6d5-103">Begränsningar i bas-e-dataidentifiering</span><span class="sxs-lookup"><span data-stu-id="1c6d5-103">Limits in Core eDiscovery</span></span>

<span data-ttu-id="1c6d5-104">I följande tabell finns begränsningar för grundläggande eDiscovery-ärenden och kvarstående information som är kopplade till ett grundläggande eDiscovery-ärende.</span><span class="sxs-lookup"><span data-stu-id="1c6d5-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="1c6d5-105">Mer information om bas-eDiscovery finns i [Översikt över bas-eDiscovery.](./get-started-core-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="1c6d5-105">For more information about Core eDiscovery, see [Overview of Core eDiscovery](./get-started-core-ediscovery.md).</span></span>
    
  | <span data-ttu-id="1c6d5-106">Beskrivning av gräns</span><span class="sxs-lookup"><span data-stu-id="1c6d5-106">Description of limit</span></span> | <span data-ttu-id="1c6d5-107">Gräns</span><span class="sxs-lookup"><span data-stu-id="1c6d5-107">Limit</span></span> |
  |:-----|:-----|
  |<span data-ttu-id="1c6d5-108">Maximalt antal ärenden för en organisation.</span><span class="sxs-lookup"><span data-stu-id="1c6d5-108">Maximum number of cases for an organization.</span></span>  <br/> |<span data-ttu-id="1c6d5-109">Ingen gräns</span><span class="sxs-lookup"><span data-stu-id="1c6d5-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="1c6d5-110">Maximalt antal spärrade ärende för en organisation.</span><span class="sxs-lookup"><span data-stu-id="1c6d5-110">Maximum number of case holds for an organization.</span></span>  <br/> |<span data-ttu-id="1c6d5-111">10 000</span><span class="sxs-lookup"><span data-stu-id="1c6d5-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="1c6d5-112">Maximalt antal postlådor för ett enskilt ärende håll.</span><span class="sxs-lookup"><span data-stu-id="1c6d5-112">Maximum number of mailboxes in a single case hold.</span></span> <span data-ttu-id="1c6d5-113">Den här gränsen omfattar totalt antal användarpostlådor och postlådorna som är kopplade Microsoft 365 grupper, Microsoft Teams och Yammer grupper.</span><span class="sxs-lookup"><span data-stu-id="1c6d5-113">This limit includes the combined total of user mailboxes, and the mailboxes associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="1c6d5-114">1 000</span><span class="sxs-lookup"><span data-stu-id="1c6d5-114">1,000</span></span>  <br/> |
  |<span data-ttu-id="1c6d5-115">Maximalt antal webbplatser i ett enskilt ärende.</span><span class="sxs-lookup"><span data-stu-id="1c6d5-115">Maximum number of sites in a single case hold.</span></span> <span data-ttu-id="1c6d5-116">Den här gränsen omfattar det totala antalet OneDrive för företag, SharePoint webbplatser och webbplatser som är kopplade till grupper Microsoft 365, Microsoft Teams och Yammer grupper.</span><span class="sxs-lookup"><span data-stu-id="1c6d5-116">This limit includes the combined total of OneDrive for Business sites, SharePoint sites, and the sites associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="1c6d5-117">100</span><span class="sxs-lookup"><span data-stu-id="1c6d5-117">100</span></span>  <br/> |
  |<span data-ttu-id="1c6d5-118">Maximalt antal ärenden som visas på eDiscovery-huvudsidan och det maximala antalet objekt som visas på flikarna Spärrar, Sökningar och Exportera i ett ärende.</span><span class="sxs-lookup"><span data-stu-id="1c6d5-118">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="1c6d5-119"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1c6d5-119"><sup>1</sup></span></span> |<span data-ttu-id="1c6d5-120">1 000</span><span class="sxs-lookup"><span data-stu-id="1c6d5-120">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="1c6d5-121"><sup>1</sup> Om du vill visa en lista över mer än 1 000 ärenden, som sätts i, sätts i sökningar eller exporteras kan du använda motsvarande PowerShell-Office 365-cmdlets för säkerhet och &- och efterlevnad:</span><span class="sxs-lookup"><span data-stu-id="1c6d5-121"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlets:</span></span>
   > 
   > - [<span data-ttu-id="1c6d5-122">Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="1c6d5-122">Get-ComplianceCase</span></span>](/powershell/module/exchange/get-compliancecase)
   > - [<span data-ttu-id="1c6d5-123">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="1c6d5-123">Get-CaseHoldPolicy</span></span>](/powershell/module/exchange/get-caseholdpolicy)
   > - [<span data-ttu-id="1c6d5-124">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="1c6d5-124">Get-ComplianceSearch</span></span>](/powershell/module/exchange/get-compliancesearch)
   > - [<span data-ttu-id="1c6d5-125">Get-ComplianceSearchAction</span><span class="sxs-lookup"><span data-stu-id="1c6d5-125">Get-ComplianceSearchAction</span></span>](/powershell/module/exchange/get-compliancesearchaction)

<span data-ttu-id="1c6d5-126">Mer information om begränsningar relaterade till sökningar och exporter som är kopplade till en bas-e-dataidentifieringsfall finns i Begränsningar för innehållssökning och [bas-eDiscovery.](limits-for-content-search.md)</span><span class="sxs-lookup"><span data-stu-id="1c6d5-126">For more information about limits related to searches and exports associated with a Core eDiscovery case, see [Limits for Content search and Core eDiscovery](limits-for-content-search.md).</span></span>