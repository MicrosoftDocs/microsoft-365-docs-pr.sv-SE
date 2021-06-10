---
title: Viktig information för dataklassificering
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: normal
recommendations: false
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Information om dataklassificering.
ms.openlocfilehash: bbce01555367c6151a7b16b551d5580ebcaf9d43
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/29/2021
ms.locfileid: "52162914"
---
# <a name="data-classification-release-notes"></a><span data-ttu-id="c9de3-103">Viktig information för dataklassificering</span><span class="sxs-lookup"><span data-stu-id="c9de3-103">Data classification release notes</span></span>


## <a name="exchange-mailbox-count"></a><span data-ttu-id="c9de3-104">Exchange postlådans antal</span><span class="sxs-lookup"><span data-stu-id="c9de3-104">Exchange mailbox count</span></span>

<span data-ttu-id="c9de3-105">Du ser att en liten verktygstips visas när du går in på detaljgranskning Exchange postlådor.</span><span class="sxs-lookup"><span data-stu-id="c9de3-105">You will notice a small tool tip appear when you drill into Exchange mailboxes.</span></span> <span data-ttu-id="c9de3-106">Detta för att visa att det samlade antalet som visas för typ av känslig information, känslighetsetikett och bevarandeetikett kanske inte exakt matchar antalet objekt som du hittar i postlådan.</span><span class="sxs-lookup"><span data-stu-id="c9de3-106">This is to call out the fact that the aggregate count displayed for sensitive information type, sensitivity label and retention label may not exactly match the number of items that you will find inside the mailbox.</span></span> <span data-ttu-id="c9de3-107">Det beror på att den granska nedåt i mappen hämtar live-vy av innehåll, som klassificeras, medan det samlade antalet beräknas.</span><span class="sxs-lookup"><span data-stu-id="c9de3-107">This is because the drill-down into the folder fetches the live view of content, which is classified, while the aggregated count is calculated.</span></span>


## <a name="rendering-of-encrypted-documents"></a><span data-ttu-id="c9de3-108">Återgivning av krypterade dokument</span><span class="sxs-lookup"><span data-stu-id="c9de3-108">Rendering of encrypted documents</span></span>

<span data-ttu-id="c9de3-109">SharePoint, Exchange och OneDrive som är krypterade återges inte i innehållsutforskaren.</span><span class="sxs-lookup"><span data-stu-id="c9de3-109">SharePoint, Exchange, and OneDrive files that are encrypted don't render in the content explorer.</span></span> <span data-ttu-id="c9de3-110">Det här är ett känsligt problem som kräver en balans mellan behovet av att se filinnehåll i Innehållsutforskaren och behovet av att hålla innehållet krypterat.</span><span class="sxs-lookup"><span data-stu-id="c9de3-110">This is a sensitive issue that requires a balance between the need to see file contents in content explorer and the need to keep the contents encrypted.</span></span> <span data-ttu-id="c9de3-111">Med de behörigheter som beviljas av  Visningsprogram för innehållsutforskaren och med rollgrupperna Innehållsvisningsprogram för innehållsutforskaren visas en listvy över filerna, filernas metadata och en länk som du kan använda för att komma åt innehållet via webbklienten.</span><span class="sxs-lookup"><span data-stu-id="c9de3-111">With the permissions granted by **Content Explorer List Viewer**, and **Content Explorer Content Viewer** role groups, you will see a list view of the files, the file  metadata, and a link you can use to access the content via the web client.</span></span>

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a><span data-ttu-id="c9de3-112">Tecken som stöds i namn på bevarandeetiketter SharePoint sökning</span><span class="sxs-lookup"><span data-stu-id="c9de3-112">Supported characters in retention label names in SharePoint search</span></span>

<span data-ttu-id="c9de3-113">SharePoint inte har stöd för bevarandeetikettnamn med `-` eller `_` i dem.</span><span class="sxs-lookup"><span data-stu-id="c9de3-113">SharePoint search doesn't support retention label names with `-`, or `_` in them.</span></span> <span data-ttu-id="c9de3-114">Till `Label-MIP` exempel, `Label_MIP` och stöds inte.</span><span class="sxs-lookup"><span data-stu-id="c9de3-114">For example, `Label-MIP` and `Label_MIP` aren't supported.</span></span> <span data-ttu-id="c9de3-115">SharePoint sökningen stöder dessa tecken i känslighetsetikettnamn och namn på typer av känslig information.</span><span class="sxs-lookup"><span data-stu-id="c9de3-115">SharePoint search does support those characters in sensitivity label names and sensitive information type names.</span></span>

## <a name="onedrive-remains-in-preview"></a><span data-ttu-id="c9de3-116">OneDrive förblir i förhandsgranskning</span><span class="sxs-lookup"><span data-stu-id="c9de3-116">OneDrive remains in preview</span></span>

<span data-ttu-id="c9de3-117">Tack för din värdefulla feedback om OneDrive integration under vårt förhandsversionsprogram.</span><span class="sxs-lookup"><span data-stu-id="c9de3-117">Thanks for your valuable feedback on OneDrive integration during our preview program.</span></span> <span data-ttu-id="c9de3-118">När vi går igenom de specifika uppgifterna kan du få inkonsekventa data/flöden.</span><span class="sxs-lookup"><span data-stu-id="c9de3-118">As we work through the specifics, you may run into inconsistent data / flows.</span></span> <span data-ttu-id="c9de3-119">Vi fortsätter att visa upp OneDrive i förhandsgranskningen tills alla korrigeringar är på plats.</span><span class="sxs-lookup"><span data-stu-id="c9de3-119">We'll continue to showcase OneDrive in preview until all fixes are in place.</span></span> <span data-ttu-id="c9de3-120">Vi uppskattar din fortsatta support.</span><span class="sxs-lookup"><span data-stu-id="c9de3-120">We appreciate your continued support.</span></span>


## <a name="see-also"></a><span data-ttu-id="c9de3-121">Se även</span><span class="sxs-lookup"><span data-stu-id="c9de3-121">See also</span></span>

- [<span data-ttu-id="c9de3-122">Komma igång med dataklassificering (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="c9de3-122">Get started with data classification (preview)</span></span>](data-classification-overview.md)
- [<span data-ttu-id="c9de3-123">Visa aktivitet med etiketter (förhandsvisning)</span><span class="sxs-lookup"><span data-stu-id="c9de3-123">View label activity (preview)</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="c9de3-124">Visa märkt innehåll (förhandsvisning)</span><span class="sxs-lookup"><span data-stu-id="c9de3-124">View labeled content (preview)</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="c9de3-125">Mer information om känslighetsetiketter</span><span class="sxs-lookup"><span data-stu-id="c9de3-125">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="c9de3-126">Mer information om kvarhållningsprinciper och kvarhållningsetiketter</span><span class="sxs-lookup"><span data-stu-id="c9de3-126">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="c9de3-127">Entitetsdefinitioner för typer av känslig information</span><span class="sxs-lookup"><span data-stu-id="c9de3-127">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)