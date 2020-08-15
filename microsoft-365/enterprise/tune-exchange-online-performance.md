---
title: Justera prestanda för Exchange Online
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
description: Den här artikeln innehåller allmänna tips och länkar till andra resurser som beskriver hur du kan förbättra prestanda för Exchange Online.
ms.openlocfilehash: 495b662aa6ef247a5751febbf2d50e1c1f21a44e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694759"
---
# <a name="tune-exchange-online-performance"></a><span data-ttu-id="de1c5-103">Justera prestanda för Exchange Online</span><span class="sxs-lookup"><span data-stu-id="de1c5-103">Tune Exchange Online performance</span></span>

<span data-ttu-id="de1c5-104">Den här artikeln innehåller allmänna tips och länkar till andra resurser som beskriver hur du kan förbättra prestanda för Exchange Online, särskilt framför en migrering.</span><span class="sxs-lookup"><span data-stu-id="de1c5-104">This article contains general tips and links to other resources that tell you how to improve performance of Exchange Online, particularly in front of a migration.</span></span> <span data-ttu-id="de1c5-105">Den här artikeln är en del av [nätverks planering och prestanda justering för Office 365](https://aka.ms/tune) Project.</span><span class="sxs-lookup"><span data-stu-id="de1c5-105">This article is part of the [Network planning and performance tuning for Office 365](https://aka.ms/tune) project.</span></span>
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a><span data-ttu-id="de1c5-106">Saker att tänka på för att förbättra Exchange Online-prestanda</span><span class="sxs-lookup"><span data-stu-id="de1c5-106">Things to consider in order to improve Exchange Online performance</span></span>

<span data-ttu-id="de1c5-107">För att förbättra migreringens hastighet och minska din organisations bandbredds begränsningar för Exchange Online bör du tänka på följande:</span><span class="sxs-lookup"><span data-stu-id="de1c5-107">To improve the speed of migration and reduce your organization's bandwidth constraints for Exchange Online, consider the following:</span></span>
  
- <span data-ttu-id="de1c5-108">**Minska storleken på post lådan.**</span><span class="sxs-lookup"><span data-stu-id="de1c5-108">**Reduce mailbox sizes.**</span></span> <span data-ttu-id="de1c5-109">Mindre storlek på post lådan förbättrar migrations hastigheten.</span><span class="sxs-lookup"><span data-stu-id="de1c5-109">Smaller mailbox size improves migration speed.</span></span> 
    
- <span data-ttu-id="de1c5-110">**Använd flytt brev låde funktionen med en Exchange hybrid distribution.**</span><span class="sxs-lookup"><span data-stu-id="de1c5-110">**Use the mailbox move capabilities with an Exchange hybrid deployment.**</span></span> <span data-ttu-id="de1c5-111">Med en Exchange hybrid distribution, offline mail (i form av. OST-filer) behöver inte laddas ned igen när du migrerar till Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="de1c5-111">With an Exchange hybrid deployment, offline mail (in the form of .OST files) does not require re-download when migrating to Exchange Online.</span></span> <span data-ttu-id="de1c5-112">Detta minskar avsevärt bandbredds kraven.</span><span class="sxs-lookup"><span data-stu-id="de1c5-112">This significantly reduces your download bandwidth requirements.</span></span> 
    
- <span data-ttu-id="de1c5-113">**Schemalägga att post lådorna ska inträffa under perioder med låg Internet trafik och lokal Exchange-användning.**</span><span class="sxs-lookup"><span data-stu-id="de1c5-113">**Schedule mailbox moves to occur during periods of low Internet traffic and low on-premises Exchange use.**</span></span> <span data-ttu-id="de1c5-114">När du schemalägger flyttningar skickas migreringsåtgärder till post lådans replikeringstopologi och kanske inte sker omedelbart.</span><span class="sxs-lookup"><span data-stu-id="de1c5-114">When scheduling moves, migration requests are submitted to the mailbox replication proxy and may not take place immediately.</span></span> 
    
- <span data-ttu-id="de1c5-115">**Använd Lean-popouts för Outlook på webben.**</span><span class="sxs-lookup"><span data-stu-id="de1c5-115">**Use lean popouts for Outlook on the web.**</span></span> <span data-ttu-id="de1c5-116">Lean popouts ger mindre, mindre minnes krävande versioner av vissa e-postmeddelanden i Microsoft Edge eller Internet Explorer genom att återge vissa komponenter på servern.</span><span class="sxs-lookup"><span data-stu-id="de1c5-116">Lean popouts provide smaller, less memory-intensive versions of certain email messages in Microsoft Edge or Internet Explorer by rendering some components on the server.</span></span> <span data-ttu-id="de1c5-117">Mer information finns i [använda Lean popouts för att minska mängden minne som används för att läsa e-postmeddelanden](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf).</span><span class="sxs-lookup"><span data-stu-id="de1c5-117">For more information, see [Use lean popouts to reduce memory used when reading mail messages](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf).</span></span>


## <a name="general-advice"></a><span data-ttu-id="de1c5-118">Allmänna råd</span><span class="sxs-lookup"><span data-stu-id="de1c5-118">General advice</span></span>

- <span data-ttu-id="de1c5-119">Kontrol lera att DNS-sökning för outlook.office.com anger MS-datacenter på en logisk start plats för platsen.</span><span class="sxs-lookup"><span data-stu-id="de1c5-119">Make certain that DNS lookup for outlook.office.com enters the MS-datacenter at a logical entry location for your location.</span></span>

- <span data-ttu-id="de1c5-120">Sök efter e-postcache och Välj lämpliga alternativ (Re.</span><span class="sxs-lookup"><span data-stu-id="de1c5-120">Research mailbox caching and choose the appropriate options (re.</span></span> <span data-ttu-id="de1c5-121">cachelagring period, cachelagring av delade post lådor, et osv).</span><span class="sxs-lookup"><span data-stu-id="de1c5-121">caching period, shared mailbox caching, et cetera).</span></span>

- <span data-ttu-id="de1c5-122">Håll dina Outlook-data från att skicka via VPN-anslutningar (till ett centralt kontor) innan det går via Internet.</span><span class="sxs-lookup"><span data-stu-id="de1c5-122">Keep your Outlook data from passing over VPN connections (to a central office) before it goes over the Internet.</span></span>

- <span data-ttu-id="de1c5-123">Kontrol lera att dina post lådors data stämmer överens med mapparna begränsningar och objekt.</span><span class="sxs-lookup"><span data-stu-id="de1c5-123">Be sure your mailbox data adheres to the limitations on folder, and item, amounts.</span></span>
    
<span data-ttu-id="de1c5-124">Mer information om prestanda för Exchange-migrering finns i [Office 365-migreringens prestanda och metod tips](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57).</span><span class="sxs-lookup"><span data-stu-id="de1c5-124">For more information about Exchange migration performance, see [Office 365 migration performance and best practices](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57).</span></span>
  

