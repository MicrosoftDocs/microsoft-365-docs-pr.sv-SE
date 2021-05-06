---
title: Avancerad indexering av dokumentägardata
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: När en vårdnadshavare läggs till i ett Advanced eDiscovery ärende bearbetas allt innehåll som anses vara delvis indexerat på nytt så att det blir sökbart.
ms.openlocfilehash: 904c8fe626ce8ece8f4b48bd5504e4011e9f4fb2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161991"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="e9623-103">Avancerad indexering av dokumentägardata</span><span class="sxs-lookup"><span data-stu-id="e9623-103">Advanced indexing of custodian data</span></span>

<span data-ttu-id="e9623-104">När en vårdnadshavare läggs till i ett Advanced eDiscovery ärende bearbetas allt innehåll som anses vara delvis indexerat på nytt så att det blir sökbart.</span><span class="sxs-lookup"><span data-stu-id="e9623-104">When a custodian is added to an Advanced eDiscovery case, any content that was deemed as partially indexed is reprocessed to make it fully searchable.</span></span>  <span data-ttu-id="e9623-105">Den här processen kallas *Avancerad indexering.*</span><span class="sxs-lookup"><span data-stu-id="e9623-105">This process is called *Advanced indexing*.</span></span> <span data-ttu-id="e9623-106">Innehåll kan indexeras delvis av flera olika anledningar, till exempel att det finns bilder, filtyper som inte stöds eller när begränsning av filstorlek för indexering påträffas.</span><span class="sxs-lookup"><span data-stu-id="e9623-106">Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span>

<span data-ttu-id="e9623-107">Mer information om att bearbeta stöd och delvis indexerade objekt finns i:</span><span class="sxs-lookup"><span data-stu-id="e9623-107">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="e9623-108">Filtyper som stöds i Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="e9623-108">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)

- [<span data-ttu-id="e9623-109">Delvis indexerade objekt i innehållssökning i Office 365</span><span class="sxs-lookup"><span data-stu-id="e9623-109">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="e9623-110">Filformat som indexeras av Exchange Search</span><span class="sxs-lookup"><span data-stu-id="e9623-110">File formats indexed by Exchange Search</span></span>](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="e9623-111">Förvalda filnamnstillägg och filtyper som crawlas och analyseras i SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="e9623-111">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="e9623-112">Visa avancerade indexeringsresultat</span><span class="sxs-lookup"><span data-stu-id="e9623-112">Viewing Advanced indexing results</span></span>

<span data-ttu-id="e9623-113">När indexeringsprocessen Avancerat är klar får du en förståelse för hur effektiv ombearbetningen är.</span><span class="sxs-lookup"><span data-stu-id="e9623-113">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of reprocessing.</span></span>  <span data-ttu-id="e9623-114">I vyn Avancerat indexeringsresultat på fliken **Bearbetning** för ett ärende visar diagrammet antalet objekt som lagts till i *hybridindexet.*</span><span class="sxs-lookup"><span data-stu-id="e9623-114">In the Advanced indexing results view on the **Processing** tab for a case, the graph lists the number of items added to the *hybrid index*.</span></span>  <span data-ttu-id="e9623-115">I hybridindexet lagras Advanced eDiscovery bearbetat innehåll.</span><span class="sxs-lookup"><span data-stu-id="e9623-115">The hybrid index is where Advanced eDiscovery stores the reprocessed content.</span></span>

<span data-ttu-id="e9623-116">Den här vyn innehåller också antalet objekt som kräver åtgärd och ett annat diagram med fel efter filtyp.</span><span class="sxs-lookup"><span data-stu-id="e9623-116">This view  also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="e9623-117">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="e9623-117">For more information, see:</span></span>

- [<span data-ttu-id="e9623-118">Åtgärda fel vid bearbetning av data</span><span class="sxs-lookup"><span data-stu-id="e9623-118">Error remediation when processing data</span></span>](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [<span data-ttu-id="e9623-119">Felåtgärder för enskilt objekt</span><span class="sxs-lookup"><span data-stu-id="e9623-119">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a><span data-ttu-id="e9623-120">Uppdatera Avancerat index för bibliotek</span><span class="sxs-lookup"><span data-stu-id="e9623-120">Updating the Advanced index for custodians</span></span>

<span data-ttu-id="e9623-121">När en vårdnadshavare läggs till i Advanced eDiscovery fall bearbetas alla delvis indexerade objekt.</span><span class="sxs-lookup"><span data-stu-id="e9623-121">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are reprocessed.</span></span> <span data-ttu-id="e9623-122">Men allt eftersom det går kan mer delvis indexerade objekt läggas till i en användares postlåda eller OneDrive konto.</span><span class="sxs-lookup"><span data-stu-id="e9623-122">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="e9623-123">Om det behövs kan du uppdatera indexet för specifik vårdnadshavare.</span><span class="sxs-lookup"><span data-stu-id="e9623-123">If necessary, you can update the index for specific custodian.</span></span> <span data-ttu-id="e9623-124">Mer information finns i Hantera [vårdnadshavare i ett Advanced eDiscovery fall.](manage-new-custodians.md#re-index-custodian-data)</span><span class="sxs-lookup"><span data-stu-id="e9623-124">For more information, see [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data).</span></span> <span data-ttu-id="e9623-125">Du kan även uppdatera indexet för alla informaterade i ett fall genom att klicka **på Uppdateringsindex** på **fliken** Bearbetning.</span><span class="sxs-lookup"><span data-stu-id="e9623-125">You can also update the index for all custodians in a case by clicking the **Update index** on the **Processing** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="e9623-126">Uppdatering av katalogindex är en process som redan pågår.</span><span class="sxs-lookup"><span data-stu-id="e9623-126">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="e9623-127">Vi rekommenderar att du inte uppdaterar index mer än en gång om dagen.</span><span class="sxs-lookup"><span data-stu-id="e9623-127">It's recommended that you don't update indexes more than once a day in a case.</span></span>