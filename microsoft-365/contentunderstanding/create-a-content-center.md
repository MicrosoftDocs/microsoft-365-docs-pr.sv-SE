---
title: Skapa ett innehållscenter i Microsoft SharePoint Syntex
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
description: Lär dig att skapa ett innehållscenter.
ms.openlocfilehash: 34ba45cd62214743e5a6784893e0f24e9815fdfb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905830"
---
# <a name="create-a-content-center-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="251d7-103">Skapa ett innehållscenter i Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="251d7-103">Create a content center in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="251d7-104">Om du vill skapa och hantera modeller för dokumenttolkning måste du först ha ett innehållscenter.</span><span class="sxs-lookup"><span data-stu-id="251d7-104">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="251d7-105">Innehållscentret är gränssnittet för skapande av modeller och innehåller även information om vilka dokumentbibliotek som publicerade modeller använts på.</span><span class="sxs-lookup"><span data-stu-id="251d7-105">The content center is the model creation interface and also contains information about which document libraries published models have been applied to.</span></span></br>

   ![Välj ett dokumentbibliotek](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="251d7-107">Du skapar ett standardinnehållscenter under [konfiguration](set-up-content-understanding.md).</span><span class="sxs-lookup"><span data-stu-id="251d7-107">You create a default content center during [setup](set-up-content-understanding.md).</span></span> <span data-ttu-id="251d7-108">Men en SharePoint-administratör kan också välja att skapa fler center efter behov.</span><span class="sxs-lookup"><span data-stu-id="251d7-108">But a SharePoint admin can also choose to create additional centers as needed.</span></span> <span data-ttu-id="251d7-109">Även om det kan vara bra att skapa ett enda innehållscenter för miljöer där du vill samla alla modellaktiviteter kanske du vill ha ytterligare center för olika avdelningar i organisationen, som kan ha olika behov och behörighetskrav för sina modeller.</span><span class="sxs-lookup"><span data-stu-id="251d7-109">While a single content center may be fine for environments for which you want a roll-up of all model activity, you may want to have additional centers for multiple departments within your organization, which may have different needs and permission requirements for their models.</span></span>

> [!NOTE]
> <span data-ttu-id="251d7-110">I en [Microsoft 365 Multi-Geo-miljö](../enterprise/microsoft-365-multi-geo.md)kan du, om du har ett enda standardinnehållscenter på den centrala platsen, endast tillhandahålla en sammanslagning av modellaktivitet från denna plats.</span><span class="sxs-lookup"><span data-stu-id="251d7-110">In a [Microsoft 365 Multi-Geo environment](../enterprise/microsoft-365-multi-geo.md), if you have a single default content center in your central location, you can only provide a roll-up of model activity from within that location.</span></span> <span data-ttu-id="251d7-111">För närvarande kan du inte få en sammanslagning av modellaktivitet över servergruppsgränser i Multi-Geo-miljö.</span><span class="sxs-lookup"><span data-stu-id="251d7-111">You currently cannot get a roll-up of model activity across farm-boundaries in Multi-Geo environment.</span></span> 


## <a name="create-a-content-center"></a><span data-ttu-id="251d7-112">Skapa ett innehållscenter</span><span class="sxs-lookup"><span data-stu-id="251d7-112">Create a content center</span></span>

<span data-ttu-id="251d7-113">En SharePoint-administratör kan skapa en webbplats för innehållscentret precis som de [skapar andra SharePoint-webbplatser](/sharepoint/create-site-collection) via administrationscentrets panel för webbplatsetablering.</span><span class="sxs-lookup"><span data-stu-id="251d7-113">A SharePoint admin can create a content center site like they would [create any other SharePoint site](/sharepoint/create-site-collection) through the admin center site provisioning panel.</span></span>

<span data-ttu-id="251d7-114">För att skapa ett nytt innehållscenter:</span><span class="sxs-lookup"><span data-stu-id="251d7-114">To create a new content center:</span></span>

1. <span data-ttu-id="251d7-115">Gå till administrationscenter för SharePoint i administrationscenter för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="251d7-115">On the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>

2. <span data-ttu-id="251d7-116">I administrationscentret för SharePoint, under **Webbplatser**, väljer du **Aktiva webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="251d7-116">On the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>

3. <span data-ttu-id="251d7-117">På sidan **Aktiva webbplatser** klickar du på **Skapa** och väljer **Andra alternativ**.</span><span class="sxs-lookup"><span data-stu-id="251d7-117">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>

4. <span data-ttu-id="251d7-118">Välj **Innehållscenter** i menyn **Välj en mall**.</span><span class="sxs-lookup"><span data-stu-id="251d7-118">On the **Choose a template** menu, select **Content Center**.</span></span>

5. <span data-ttu-id="251d7-119">Ange **Webbplatsnamn**, **primär administratör** och **Språk** för den nya webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="251d7-119">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

   > [!NOTE] 
   > <span data-ttu-id="251d7-120">Du kan välja en webbplats för innehållscenter i något av de tillgängliga språken, men observera att modeller för närvarande endast kan skapas för engelska filer.</span><span class="sxs-lookup"><span data-stu-id="251d7-120">You can select a content center site to render in any of the available languages, but note that currently models can only be created for English files.</span></span> <span data-ttu-id="251d7-121">Observera också att precis som med andra webbplatsmallar kan standardwebbplatsens språk inte redigeras när webbplatsen har skapats.</span><span class="sxs-lookup"><span data-stu-id="251d7-121">Also note that like other site templates, the default site language isn't editable after the site is created.</span></span></br>

6. <span data-ttu-id="251d7-122">Välj **Färdig**.</span><span class="sxs-lookup"><span data-stu-id="251d7-122">Select **Finished**.</span></span>
 
<span data-ttu-id="251d7-123">När du har skapat en webbplats för innehållscentret visas den på sidan **Aktiva webbplatser** i administrationscenter för SharePoint.</span><span class="sxs-lookup"><span data-stu-id="251d7-123">After you create a content center site, you will see it listed on the **Active sites** page in the SharePoint admin center.</span></span> 

### <a name="give-access-to-additional-users"></a><span data-ttu-id="251d7-124">Ge behörighet till ytterligare användare</span><span class="sxs-lookup"><span data-stu-id="251d7-124">Give access to additional users</span></span>
 
<span data-ttu-id="251d7-125">När du har skapat webbplatsen kan du ge fler användare åtkomst till den via standard[modellen för SharePoint-webbplatsbehörigheter](/sharepoint/modern-experience-sharing-permissions).</span><span class="sxs-lookup"><span data-stu-id="251d7-125">After you create the site, you can give additional users access to the site through the standard [SharePoint site permissions model](/sharepoint/modern-experience-sharing-permissions).</span></span>

## <a name="see-also"></a><span data-ttu-id="251d7-126">Se även</span><span class="sxs-lookup"><span data-stu-id="251d7-126">See Also</span></span>
[<span data-ttu-id="251d7-127">Skapa en klassificerare</span><span class="sxs-lookup"><span data-stu-id="251d7-127">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="251d7-128">Skapa en extraktor</span><span class="sxs-lookup"><span data-stu-id="251d7-128">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="251d7-129">Skapa ett innehållscenter</span><span class="sxs-lookup"><span data-stu-id="251d7-129">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="251d7-130">Översikt av dokumenttolkning</span><span class="sxs-lookup"><span data-stu-id="251d7-130">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="251d7-131">Skapa en modell för formulärbearbetning</span><span class="sxs-lookup"><span data-stu-id="251d7-131">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="251d7-132">Använda en modell</span><span class="sxs-lookup"><span data-stu-id="251d7-132">Apply a model</span></span>](apply-a-model.md)