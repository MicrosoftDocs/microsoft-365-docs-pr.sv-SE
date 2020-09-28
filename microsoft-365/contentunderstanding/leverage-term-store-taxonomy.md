---
title: Använda term lagrings taxonomi när du skapar en Extractor
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Använda term lagrings platsen när du skapar en Extractor i dokumentet förstås i Microsoft SharePoint Syntex.
ms.openlocfilehash: 94f7a0389d2f06e0f8c1a60a341a02e43dfb2071
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296222"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a><span data-ttu-id="ef083-103">Använda term lagrings taxonomi när du skapar en Extractor</span><span class="sxs-lookup"><span data-stu-id="ef083-103">Leverage term store taxonomy when creating an extractor</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="ef083-104">När du skapar en Extractor i din dokument kunskaps modell i SharePoint Syntex kan du utnyttja den här [termen för](https://docs.microsoft.com/sharepoint/managed-metadata#terms) att Visa önskade villkor för data som du extraherar.</span><span class="sxs-lookup"><span data-stu-id="ef083-104">When you create an extractor in your document understanding model in SharePoint Syntex, you can take advantage of [Managed Metadata services](https://docs.microsoft.com/sharepoint/managed-metadata#terms) term store taxonomy to display preferred terms for data that you extract.</span></span>  

<span data-ttu-id="ef083-105">Som exempel identifieras och klassificeras alla **kontrakts** dokument som laddas upp till dokument biblioteket.</span><span class="sxs-lookup"><span data-stu-id="ef083-105">As an example, your model identifies and classifies all **Contract** documents that are uploaded to the document library.</span></span>  <span data-ttu-id="ef083-106">Dessutom extraherar modellen också ett **kontrakts tjänst** värde från varje kontrakt och visas i en kolumn i vyn bibliotek.</span><span class="sxs-lookup"><span data-stu-id="ef083-106">Additionally, the model also extracts a **Contract Service** value from each contract, and will display it in a column in your library view.</span></span> <span data-ttu-id="ef083-107">Bland de olika kontrakts tjänstens värden finns det flera äldre värden som företaget inte längre använder och har bytt namn.</span><span class="sxs-lookup"><span data-stu-id="ef083-107">Among the various Contract Services values in the contracts, there are several older values that your company no longer uses and have been renamed.</span></span> <span data-ttu-id="ef083-108">Till exempel ska alla referenser till *design*-, *grafik*-och *topografi* -tjänster nu vara *kreativa*.</span><span class="sxs-lookup"><span data-stu-id="ef083-108">For example, all references to the terms *Design*, *Graphics*, or *Topography* contract services should now be called *Creative*.</span></span> <span data-ttu-id="ef083-109">När din modell extraherar ett av de föråldrade villkoren från ett kontrakts dokument vill du att den ska visas i din Library-vy.</span><span class="sxs-lookup"><span data-stu-id="ef083-109">Whenever your model extracts one of the outdated terms from a contract document, you want it to display the current term - Creative - in your library view.</span></span> <span data-ttu-id="ef083-110">I exemplet nedan, och utbildning för modellen ser vi att ett exempel dokument innehåller den inaktuella *designens layout*.</span><span class="sxs-lookup"><span data-stu-id="ef083-110">In the example below, while training the model we see that one sample document contains the outdated term of *Design*.</span></span>

   ![Term lagrings plats](../media/content-understanding/design.png)</br>


## <a name="term-set-synonyms"></a><span data-ttu-id="ef083-112">Synonymer för term uppsättning</span><span class="sxs-lookup"><span data-stu-id="ef083-112">Term set synonyms</span></span> 

<span data-ttu-id="ef083-113">Term uppsättningar konfigureras i term lagrings platsen för hanterade metadata i administrations centret för SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ef083-113">Term sets are configured in the Managed Metadata services term store in the SharePoint admin center.</span></span> <span data-ttu-id="ef083-114">I exemplet nedan är [termen uppsättning](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) för *kontrakt tjänster* konfigurerat till att omfatta flera villkor, inklusive *Creative*.</span><span class="sxs-lookup"><span data-stu-id="ef083-114">In the the example below, the *Contract Services* [term set](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) is configured to include a number of terms, including *Creative*.</span></span>  <span data-ttu-id="ef083-115">Informationen för det visar att termen har tre synonymer (*design*, *grafik*och *topografi*) och synonymerna bör översättas till *kreativ*.</span><span class="sxs-lookup"><span data-stu-id="ef083-115">The details for it show that the term has three synonyms (*Design*, *Graphics*, and *Topography*) and the synonyms should be translated to *Creative*.</span></span>

   ![Term uppsättning](../media/content-understanding/term-store.png)</br>

<span data-ttu-id="ef083-117"><Mike, här är jag osäker på hur du beskriver detta.</span><span class="sxs-lookup"><span data-stu-id="ef083-117"><Mike, here is where I am unsure about how to describe this.</span></span>  <span data-ttu-id="ef083-118">Vilken åtgärd visar modellen när jag skapar en kolumn för att extrahera och visa kolumnen kontrakt tjänster, hur är att kolumnen "märkt" används för att använda term uppsättningen hanterade metadata för Creative Services? ></span><span class="sxs-lookup"><span data-stu-id="ef083-118">What action tells the model that when I create an extractor to extract and display a Contract Services column, how is that column "marked" to use the managed metadata term set for Creative Services?></span></span>

## <a name="configure-your-document-library-site-column-for-a-managed-metadata-field"></a><span data-ttu-id="ef083-119">Konfigurera kolumnen webbplats för dokument bibliotek för ett fält med hanterade metadata</span><span class="sxs-lookup"><span data-stu-id="ef083-119">Configure your document library site column for a managed metadata field</span></span>


   ![Skapa hanterade metadata](../media/content-understanding/creative.png)</br>

## <a name="see-also"></a><span data-ttu-id="ef083-121">Se även</span><span class="sxs-lookup"><span data-stu-id="ef083-121">See Also</span></span>
[<span data-ttu-id="ef083-122">Introduktion till hanterade metadata</span><span class="sxs-lookup"><span data-stu-id="ef083-122">Introduction to Managed Metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata#terms)</br>
[<span data-ttu-id="ef083-123">Skapa en Extractor</span><span class="sxs-lookup"><span data-stu-id="ef083-123">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="ef083-124">Skapa en kolumn med hanterade metadata</span><span class="sxs-lookup"><span data-stu-id="ef083-124">Create a managed metadata column</span></span>](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)</br>





