---
title: Nästan dubblettidentifiering – eDiscovery
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
description: Använd nästan dubblettidentifiering om du vill gruppera dokument som liknar varandra när du analyserar ärendedata i Advanced eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 255531897a1706904005034c56cab00d0032b7f3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/26/2020
ms.locfileid: "52161625"
---
# <a name="near-duplicate-detection-in-advanced-ediscovery"></a><span data-ttu-id="1ad89-103">Nästan dubblettidentifiering i Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="1ad89-103">Near duplicate detection in Advanced eDiscovery</span></span>

<span data-ttu-id="1ad89-104">Överväg att granska en uppsättning dokument där en delmängd baseras på samma mall och oftast har samma exempelspråk, med några skillnader här och där.</span><span class="sxs-lookup"><span data-stu-id="1ad89-104">Consider a set of documents to be reviewed in which a subset is based on the same template and has mostly the same boilerplate language, with a few differences here and there.</span></span> <span data-ttu-id="1ad89-105">Om granskare skulle kunna identifiera den här deluppsättningen granskar du en av dem noggrant och granskar skillnaderna för resten. Då hade de inte missat någon unik information medan det tog endast en del tid som skulle ha tagit dem att läsa alla dokument omslag.</span><span class="sxs-lookup"><span data-stu-id="1ad89-105">If a reviewer could identify this subset, review one of them thoroughly, and review the differences for the rest, they would not have missed any unique information while taking only a fraction of time that would have taken them to read all documents cover to cover.</span></span> <span data-ttu-id="1ad89-106">Med en text som liknar varandra i närheten av dubblettidentifieringsgrupper blir granskningsprocessen effektivare.</span><span class="sxs-lookup"><span data-stu-id="1ad89-106">Near duplicate detection groups textually similar documents together to help you make your review process more efficient.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="1ad89-107">Hur fungerar det?</span><span class="sxs-lookup"><span data-stu-id="1ad89-107">How does it work?</span></span>

<span data-ttu-id="1ad89-108">När identifiering av nästan dubbletter körs parsar systemet alla dokument med text.</span><span class="sxs-lookup"><span data-stu-id="1ad89-108">When near duplicate detection is run, the system parses every document with text.</span></span> <span data-ttu-id="1ad89-109">Sedan jämförs alla dokument med varandra för att avgöra om deras likhet är större än det inställt tröskelvärdet.</span><span class="sxs-lookup"><span data-stu-id="1ad89-109">Then, it compares every document against each other to determine whether their similarity is greater than the set threshold.</span></span> <span data-ttu-id="1ad89-110">Om den är det grupperas dokumenten tillsammans.</span><span class="sxs-lookup"><span data-stu-id="1ad89-110">If it is, the documents are grouped together.</span></span> <span data-ttu-id="1ad89-111">När alla dokument har jämförts och grupperats markeras ett dokument från varje grupp som "pivot". När du granskar dina dokument kan du granska en pivot först och granska de andra dokumenten i samma nästan dubblettuppsättning, med fokus på skillnaden mellan pivot och det dokument som granskas.</span><span class="sxs-lookup"><span data-stu-id="1ad89-111">Once all documents have been compared and grouped, a document from each group is marked as the "pivot"; in reviewing your documents, you can review a pivot first and review the other documents in the same near duplicate set, focusing on the difference between the pivot and the document that is in review.</span></span>
