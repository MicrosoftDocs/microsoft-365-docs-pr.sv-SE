---
title: Skapa ett innehålls Center i Microsoft SharePoint Syntex
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Lär dig hur du skapar ett innehålls Center.
ms.openlocfilehash: 62977bc5a34b041e9e958ff46e0dbc010d6bd822
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295438"
---
# <a name="create-a-content-center-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="1db74-103">Skapa ett innehålls Center i Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="1db74-103">Create a content center in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="1db74-104">Innehållet i den här artikeln gäller för projekt cortex privat för hands version.</span><span class="sxs-lookup"><span data-stu-id="1db74-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="1db74-105">[Lär dig mer om Project cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="1db74-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span></br>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="1db74-106">För att skapa och hantera dokument förståelse modeller behöver du först ett innehålls Center.</span><span class="sxs-lookup"><span data-stu-id="1db74-106">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="1db74-107">Innehålls centret är gränssnittet för skapande av modell och innehåller information om vilka dokument bibliotek som har publicerats till modeller.</span><span class="sxs-lookup"><span data-stu-id="1db74-107">The content center is the model creation interface and also contains information about which document libraries published models have been applied to.</span></span></br>

   ![Välj ett dokument bibliotek](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="1db74-109">Du skapar ett första innehålls Center under [installationen](set-up-content-understanding.md).</span><span class="sxs-lookup"><span data-stu-id="1db74-109">You create an initial content center during [setup](set-up-content-understanding.md).</span></span> <span data-ttu-id="1db74-110">Men en SharePoint-administratör kan också välja att skapa ytterligare Center efter behov.</span><span class="sxs-lookup"><span data-stu-id="1db74-110">But a SharePoint admin can also choose to create additional centers as needed.</span></span> <span data-ttu-id="1db74-111">Det kan hända att ett enskilt innehålls Center fungerar bra för de miljöer som du vill samla in alla modell aktiviteter för och du kanske vill ha ytterligare Center för flera avdelningar i organisationen, som kan ha olika behov och krav för deras modeller.</span><span class="sxs-lookup"><span data-stu-id="1db74-111">While a single content center may be fine for environments for which you want a roll-up of all model activity, you may want to have additional centers for multiple departments within your organization, which may have different needs and requirements for their models.</span></span>

> [!NOTE]
> <span data-ttu-id="1db74-112">En SharePoint-administratör kan skapa en innehålls Center-webbplats som de [skapar andra SharePoint-webbplatser](https://docs.microsoft.com/sharepoint/create-site-collection) med hjälp av en webbplatsmall.</span><span class="sxs-lookup"><span data-stu-id="1db74-112">A SharePoint admin can create a content center site like they would [create any other SharePoint site](https://docs.microsoft.com/sharepoint/create-site-collection) by using a site template.</span></span>

<span data-ttu-id="1db74-113">Så här skapar du ett nytt innehålls Center:</span><span class="sxs-lookup"><span data-stu-id="1db74-113">To create a new content center:</span></span>

1. <span data-ttu-id="1db74-114">Gå till administrations centret för SharePoint i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1db74-114">From the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>
2. <span data-ttu-id="1db74-115">I administrations centret för SharePoint, under **webbplatser**, väljer du **aktiva webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="1db74-115">In the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>
3. <span data-ttu-id="1db74-116">På sidan **aktiva webbplatser** klickar du på **skapa**och väljer sedan **andra alternativ**.</span><span class="sxs-lookup"><span data-stu-id="1db74-116">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>
4. <span data-ttu-id="1db74-117">Gå till menyn **Välj en mall** och välj **innehålls Center**.</span><span class="sxs-lookup"><span data-stu-id="1db74-117">On the **Choose a template** menu, select **Content Center**.</span></span>
5. <span data-ttu-id="1db74-118">Ange ett **namn**, en **primär administratör**och ett **språk**för den nya webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="1db74-118">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

> [!NOTE] 
> <span data-ttu-id="1db74-119">Du kan också välja en innehålls Center webbplats som ska återges på något av de tillgängliga språken.</span><span class="sxs-lookup"><span data-stu-id="1db74-119">You can optionally select a content center site to render in any of the available languages.</span></span> <span data-ttu-id="1db74-120">Endast aktuella modeller kan skapas för engelska filer.</span><span class="sxs-lookup"><span data-stu-id="1db74-120">Only current models can be created for English files.</span></span></br>

6. <span data-ttu-id="1db74-121">Välj **avslutad**.</span><span class="sxs-lookup"><span data-stu-id="1db74-121">Select **Finished**.</span></span>

### <a name="give-access-to-additional-users"></a><span data-ttu-id="1db74-122">Ge till gång till ytterligare användare</span><span class="sxs-lookup"><span data-stu-id="1db74-122">Give access to additional users</span></span>
 
<span data-ttu-id="1db74-123">När du har skapat webbplatsen kan du ge ytterligare användare åtkomst till webbplatsen via standard [modell för SharePoint-webbplatsens behörigheter](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span><span class="sxs-lookup"><span data-stu-id="1db74-123">After you create the site, you can give additional users access to the site through the standard [SharePoint site permissions model](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span>

## <a name="see-also"></a><span data-ttu-id="1db74-124">Se även</span><span class="sxs-lookup"><span data-stu-id="1db74-124">See Also</span></span>
[<span data-ttu-id="1db74-125">Skapa en klassificerare</span><span class="sxs-lookup"><span data-stu-id="1db74-125">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="1db74-126">Skapa en Extractor</span><span class="sxs-lookup"><span data-stu-id="1db74-126">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="1db74-127">[Skapa ett innehålls Center](create-a-content-center.md) 
 [Översikt över dokument förståelse](document-understanding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="1db74-127">[Create a content center](create-a-content-center.md)
[Document understanding overview](document-understanding-overview.md)</span></span></br>
[<span data-ttu-id="1db74-128">Skapa en modell för formulär bearbetning</span><span class="sxs-lookup"><span data-stu-id="1db74-128">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="1db74-129">Använda en modell</span><span class="sxs-lookup"><span data-stu-id="1db74-129">Apply a model</span></span>](apply-a-model.md)    
