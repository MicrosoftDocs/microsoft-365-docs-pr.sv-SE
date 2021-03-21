---
title: Använda termlagringstaxonomi vid skapande av extraktor
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Använd en termlagringstaxonomi vid skapande av extraktor i modellen för dokumenttolkning i Microsoft SharePoint Syntex.
ms.openlocfilehash: b8dfc028e0a18f3345fec466ec5e0079ed2d11ce
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925350"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a><span data-ttu-id="22bf4-103">Använda termlagringstaxonomi vid skapande av extraktor</span><span class="sxs-lookup"><span data-stu-id="22bf4-103">Leverage term store taxonomy when creating an extractor</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GpJJ]  

</br>

<span data-ttu-id="22bf4-104">När du skapar en extraherare i din dokumentförståelsemodell med SharePoint Syntex kan du dra nytta av globala termuppsättningar i [term lagringsplats](/sharepoint/managed-metadata) för att visa föredragna termer för data som du extraherar.</span><span class="sxs-lookup"><span data-stu-id="22bf4-104">When you create an extractor in your document understanding model using SharePoint Syntex, you can take advantage of global term sets in the [term store](/sharepoint/managed-metadata) to display preferred terms for data that you extract.</span></span>  

<span data-ttu-id="22bf4-105">Som exempel identifierar och klassificerar din modell alla **Kontrakt** som har laddats upp till dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="22bf4-105">As an example, your model identifies and classifies all **Contract** documents that are uploaded to the document library.</span></span>  <span data-ttu-id="22bf4-106">Dessutom extraherar modellen också värdet **Kontraktstjänst** från varje kontrakt. Det visas i en kolumn i din biblioteksvy.</span><span class="sxs-lookup"><span data-stu-id="22bf4-106">Additionally, the model also extracts a **Contract Service** value from each contract, and will display it in a column in your library view.</span></span> <span data-ttu-id="22bf4-107">Bland de olika värdena för kontraktstjänster i kontrakten finns det flera äldre värden som företaget inte längre använder och som har bytt namn.</span><span class="sxs-lookup"><span data-stu-id="22bf4-107">Among the various Contract Services values in the contracts, there are several older values that your company no longer uses and have been renamed.</span></span> <span data-ttu-id="22bf4-108">Exempel: alla hänvisningar till termernas *Design*, *Grafik* eller *Topografi* i kontraktstjänsterna ska nu kallas *Kreativa*.</span><span class="sxs-lookup"><span data-stu-id="22bf4-108">For example, all references to the terms *Design*, *Graphics*, or *Topography* contract services should now be called *Creative*.</span></span> <span data-ttu-id="22bf4-109">När din modell hämtar en inaktuell term från ett kontrakt vill du att det ska visa den aktuella termen – Kreativ – i din biblioteksvy.</span><span class="sxs-lookup"><span data-stu-id="22bf4-109">Whenever your model extracts one of the outdated terms from a contract document, you want it to display the current term - Creative - in your library view.</span></span> <span data-ttu-id="22bf4-110">I exemplet nedan ser vi medan vi tränar modellen att ett exempeldokument innehåller inaktuella villkor för *Design*.</span><span class="sxs-lookup"><span data-stu-id="22bf4-110">In the example below, while training the model we see that one sample document contains the outdated term of *Design*.</span></span>

   ![Termlagring](../media/content-understanding/design.png)</br>

## <a name="use-a-managed-metadata-column-in-your-extractor"></a><span data-ttu-id="22bf4-112">Använda en kolumn med hanterade metadata i din extraktor</span><span class="sxs-lookup"><span data-stu-id="22bf4-112">Use a Managed metadata column in your extractor</span></span>

<span data-ttu-id="22bf4-113">Uppsättningar med termer konfigureras i hanterade metadatatjänstens (MMS) termarkiv i administrationscenter för SharePoint.</span><span class="sxs-lookup"><span data-stu-id="22bf4-113">Term sets are configured in the Managed Metadata services (MMS) term store in the SharePoint admin center.</span></span> <span data-ttu-id="22bf4-114">I exemplet nedan är *Kontraktstjänsters* [termuppsättning](/sharepoint/managed-metadata#term-set) konfigurerad att innehålla flera termer, bland annat *Kreativa*.</span><span class="sxs-lookup"><span data-stu-id="22bf4-114">In the example below, the *Contract Services* [term set](/sharepoint/managed-metadata#term-set) is configured to include several terms, including *Creative*.</span></span>  <span data-ttu-id="22bf4-115">Informationen för den visar att termen har tre synonymer (*Design*, *Grafik* och *Topografi*) och att synonymerna ska översätta till *Kreativa*.</span><span class="sxs-lookup"><span data-stu-id="22bf4-115">The details for it show that the term has three synonyms (*Design*, *Graphics*, and *Topography*) and the synonyms should be translated to *Creative*.</span></span> 

   ![Termuppsättning](../media/content-understanding/term-store.png)</br>

<span data-ttu-id="22bf4-117">Det kan finnas flera anledningar till att du vill använda en synonym i termuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="22bf4-117">There could be many reasons why you might want to use a synonym in your term set.</span></span> <span data-ttu-id="22bf4-118">Det kan till exempel röra sig om föråldrade termer, termer som fått nya namn eller skillnader mellan företagets olika avdelningar.</span><span class="sxs-lookup"><span data-stu-id="22bf4-118">For example, there could be outdated terms, renamed terms, or variations between your organizations departments on naming.</span></span>

<span data-ttu-id="22bf4-119">Om du vill att fältet för hanterade metadata ska vara tillgängligt att välja när du skapar din extraktor i modellen måste du [lägga till det som en webbplatskolumn med hanterade metadata](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f).</span><span class="sxs-lookup"><span data-stu-id="22bf4-119">To make the managed metadata field available to select when you create your extractor in your model, you need to [add it as a managed-metadata site column](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f).</span></span> <span data-ttu-id="22bf4-120">När du har lagt till webbplatskolumnen kan du välja när du skapar extraktorn för din modell.</span><span class="sxs-lookup"><span data-stu-id="22bf4-120">After you add the site column, you can select it when you create the extractor for your model.</span></span>

   ![Kontraktstjänst](../media/content-understanding/contract-services.png)</br>


<span data-ttu-id="22bf4-122">Efter att ha använt modellen på dokumentbiblioteket, när dokumenten är uppladda till biblioteket, kommer kolumnen *Kreativa tjänster* att visa föredragen term (*Kreativ*) när extraktorn hittar något av synonymvärdena (*Design*, *Grafik* och *Topografi*).</span><span class="sxs-lookup"><span data-stu-id="22bf4-122">After applying your model to the document library, when documents are uploaded to library, the *Creative Services* column will display the preferred term (*Creative*) when the extractor finds any of the synonym values (*Design*, *Graphics*, and *Topography*).</span></span>

   ![Kontraktstjänstkolumnen](../media/content-understanding/creative.png)</br>


## <a name="see-also"></a><span data-ttu-id="22bf4-124">Se även</span><span class="sxs-lookup"><span data-stu-id="22bf4-124">See Also</span></span>
[<span data-ttu-id="22bf4-125">Introduktion till hanterad metadata</span><span class="sxs-lookup"><span data-stu-id="22bf4-125">Introduction to Managed Metadata</span></span>](/sharepoint/managed-metadata#terms)

[<span data-ttu-id="22bf4-126">Skapa en extraktor</span><span class="sxs-lookup"><span data-stu-id="22bf4-126">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="22bf4-127">Skapa en kolumn med hanterade metadata</span><span class="sxs-lookup"><span data-stu-id="22bf4-127">Create a managed metadata column</span></span>](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)