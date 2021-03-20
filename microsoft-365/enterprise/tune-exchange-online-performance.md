---
title: Justera Exchange Online-prestanda
ms.author: krowley
author: tracyp
manager: laurawi
ms.date: 12/14/2017
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.assetid: 026e83cb-a945-4543-97b0-a8af6e80ac61
description: Den här artikeln innehåller allmänna tips och länkar till andra resurser som beskriver hur du förbättrar prestandan i Exchange Online.
ms.openlocfilehash: a7d3268f9f3cf1922319b03cf69d3f044272b27f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909448"
---
# <a name="tune-exchange-online-performance"></a><span data-ttu-id="29e01-103">Justera Exchange Online-prestanda</span><span class="sxs-lookup"><span data-stu-id="29e01-103">Tune Exchange Online performance</span></span>

<span data-ttu-id="29e01-104">Den här artikeln innehåller allmänna tips och länkar till andra resurser som beskriver hur du förbättrar prestanda för Exchange Online, särskilt före migreringen.</span><span class="sxs-lookup"><span data-stu-id="29e01-104">This article contains general tips and links to other resources that tell you how to improve performance of Exchange Online, particularly in front of a migration.</span></span> <span data-ttu-id="29e01-105">Den här artikeln är en del [av projektet Nätverksplanering och prestandajustering för Office 365.](./network-planning-and-performance.md)</span><span class="sxs-lookup"><span data-stu-id="29e01-105">This article is part of the [Network planning and performance tuning for Office 365](./network-planning-and-performance.md) project.</span></span>
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a><span data-ttu-id="29e01-106">Saker att tänka på för att förbättra prestandan i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="29e01-106">Things to consider in order to improve Exchange Online performance</span></span>

<span data-ttu-id="29e01-107">För att förbättra migreringens hastighet och minska organisationens bandbreddsbegränsningar för Exchange Online ska du tänka på följande:</span><span class="sxs-lookup"><span data-stu-id="29e01-107">To improve the speed of migration and reduce your organization's bandwidth constraints for Exchange Online, consider the following:</span></span>
  
- <span data-ttu-id="29e01-108">**Minska postlådestorleken.**</span><span class="sxs-lookup"><span data-stu-id="29e01-108">**Reduce mailbox sizes.**</span></span> <span data-ttu-id="29e01-109">Mindre postlådestorlek förbättrar migreringshastigheten.</span><span class="sxs-lookup"><span data-stu-id="29e01-109">Smaller mailbox size improves migration speed.</span></span> 
    
- <span data-ttu-id="29e01-110">**Använd postlådans flyttfunktioner med en Exchange-hybriddistribution.**</span><span class="sxs-lookup"><span data-stu-id="29e01-110">**Use the mailbox move capabilities with an Exchange hybrid deployment.**</span></span> <span data-ttu-id="29e01-111">Offline-e-post (i form av en Exchange-hybriddistribution) OST-filer) behöver inte hämtas igen vid migrering till Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="29e01-111">With an Exchange hybrid deployment, offline mail (in the form of .OST files) does not require re-download when migrating to Exchange Online.</span></span> <span data-ttu-id="29e01-112">Det här minskar avsevärt bandbreddskraven för hämtning.</span><span class="sxs-lookup"><span data-stu-id="29e01-112">This significantly reduces your download bandwidth requirements.</span></span> 
    
- <span data-ttu-id="29e01-113">**Schemalägg postlådeflyttningar vid tider med låg Internettrafik och låg lokal Exchange-användning.**</span><span class="sxs-lookup"><span data-stu-id="29e01-113">**Schedule mailbox moves to occur during periods of low Internet traffic and low on-premises Exchange use.**</span></span> <span data-ttu-id="29e01-114">När du schemalägger flyttningar skickas migreringsbegäranden till postlådereplikeringsproxyn och sker kanske inte omedelbart.</span><span class="sxs-lookup"><span data-stu-id="29e01-114">When scheduling moves, migration requests are submitted to the mailbox replication proxy and may not take place immediately.</span></span> 
    
- <span data-ttu-id="29e01-115">**Använd magera popup-fönster för Outlook på webben.**</span><span class="sxs-lookup"><span data-stu-id="29e01-115">**Use lean popouts for Outlook on the web.**</span></span> <span data-ttu-id="29e01-116">Med Microsoft Edge och Internet Explorer kan du göra så att vissa e-postmeddelanden tar upp mindre plats genom att återge vissa komponenter på servern.</span><span class="sxs-lookup"><span data-stu-id="29e01-116">Lean popouts provide smaller, less memory-intensive versions of certain email messages in Microsoft Edge or Internet Explorer by rendering some components on the server.</span></span> <span data-ttu-id="29e01-117">Mer information finns i Använda [mindre använda popup-fönster för att använda mindre minne när du läser e-postmeddelanden.](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf)</span><span class="sxs-lookup"><span data-stu-id="29e01-117">For more information, see [Use lean popouts to reduce memory used when reading mail messages](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf).</span></span>


## <a name="general-advice"></a><span data-ttu-id="29e01-118">Allmänna råd</span><span class="sxs-lookup"><span data-stu-id="29e01-118">General advice</span></span>

- <span data-ttu-id="29e01-119">Kontrollera att DNS-uppslag för outlook.office.com anger MS-datacentret på en logisk postplats för din plats.</span><span class="sxs-lookup"><span data-stu-id="29e01-119">Make certain that DNS lookup for outlook.office.com enters the MS-datacenter at a logical entry location for your location.</span></span>

- <span data-ttu-id="29e01-120">Undersöka postlådans cachelagring och välj lämpliga alternativ (åter.</span><span class="sxs-lookup"><span data-stu-id="29e01-120">Research mailbox caching and choose the appropriate options (re.</span></span> <span data-ttu-id="29e01-121">cachelagringsperiod, cachelagring av delad postlåda och osv.</span><span class="sxs-lookup"><span data-stu-id="29e01-121">caching period, shared mailbox caching, et cetera).</span></span>

- <span data-ttu-id="29e01-122">Se till att dina Outlook-data inte passerar över VPN-anslutningar (till ett centralt kontor) innan de passerar via Internet.</span><span class="sxs-lookup"><span data-stu-id="29e01-122">Keep your Outlook data from passing over VPN connections (to a central office) before it goes over the Internet.</span></span>

- <span data-ttu-id="29e01-123">Se till att dina postlådedata följer begränsningarna för mapp- och artikelbelopp.</span><span class="sxs-lookup"><span data-stu-id="29e01-123">Be sure your mailbox data adheres to the limitations on folder, and item, amounts.</span></span>
    
<span data-ttu-id="29e01-124">Mer information om prestanda för Exchange-migrering finns i [Migreringsprestanda för Office 365 och rekommendationer.](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57)</span><span class="sxs-lookup"><span data-stu-id="29e01-124">For more information about Exchange migration performance, see [Office 365 migration performance and best practices](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57).</span></span>
