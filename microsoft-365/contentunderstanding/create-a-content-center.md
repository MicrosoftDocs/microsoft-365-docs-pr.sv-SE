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
ms.openlocfilehash: 4377cbfbda8572fe9e08a079a05146961105298b
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976537"
---
# <a name="create-a-content-center-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="792f1-103">Skapa ett innehållscenter i Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="792f1-103">Create a content center in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="792f1-104">Om du vill skapa och hantera modeller för dokumenttolkning måste du först ha ett innehållscenter.</span><span class="sxs-lookup"><span data-stu-id="792f1-104">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="792f1-105">Innehållscentret är gränssnittet för skapande av modeller och innehåller även information om vilka dokumentbibliotek som publicerade modeller använts på.</span><span class="sxs-lookup"><span data-stu-id="792f1-105">The content center is the model creation interface and also contains information about which document libraries published models have been applied to.</span></span></br>

   ![Välj ett dokumentbibliotek](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="792f1-107">Du skapar ett standardinnehållscenter under [konfiguration](set-up-content-understanding.md).</span><span class="sxs-lookup"><span data-stu-id="792f1-107">You create a default content center during [setup](set-up-content-understanding.md).</span></span> <span data-ttu-id="792f1-108">Men en SharePoint-administratör kan också välja att skapa fler center efter behov.</span><span class="sxs-lookup"><span data-stu-id="792f1-108">But a SharePoint admin can also choose to create additional centers as needed.</span></span> <span data-ttu-id="792f1-109">Även om det kan vara bra att skapa ett enda innehållscenter för miljöer där du vill samla alla modellaktiviteter kanske du vill ha ytterligare center för olika avdelningar i organisationen, som kan ha olika behov och behörighetskrav för sina modeller.</span><span class="sxs-lookup"><span data-stu-id="792f1-109">While a single content center may be fine for environments for which you want a roll-up of all model activity, you may want to have additional centers for multiple departments within your organization, which may have different needs and permission requirements for their models.</span></span>

> [!NOTE]
> <span data-ttu-id="792f1-110">En SharePoint-administratör kan skapa en webbplats för innehållscentret precis som de [skapar andra SharePoint-webbplatser](https://docs.microsoft.com/sharepoint/create-site-collection) via administrationscentrets panel för webbplatsetablering.</span><span class="sxs-lookup"><span data-stu-id="792f1-110">A SharePoint admin can create a content center site like they would [create any other SharePoint site](https://docs.microsoft.com/sharepoint/create-site-collection) through the admin center site provisioning panel.</span></span>

<span data-ttu-id="792f1-111">För att skapa ett nytt innehållscenter:</span><span class="sxs-lookup"><span data-stu-id="792f1-111">To create a new content center:</span></span>

1. <span data-ttu-id="792f1-112">Gå till administrationscenter för SharePoint i administrationscenter för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="792f1-112">On the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>
2. <span data-ttu-id="792f1-113">I administrationscentret för SharePoint, under **Webbplatser**, väljer du **Aktiva webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="792f1-113">On the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>
3. <span data-ttu-id="792f1-114">På sidan **Aktiva webbplatser** klickar du på **Skapa** och väljer **Andra alternativ**.</span><span class="sxs-lookup"><span data-stu-id="792f1-114">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>
4. <span data-ttu-id="792f1-115">Välj **Innehållscenter** i menyn **Välj en mall**.</span><span class="sxs-lookup"><span data-stu-id="792f1-115">On the **Choose a template** menu, select **Content Center**.</span></span>
5. <span data-ttu-id="792f1-116">Ange **Webbplatsnamn**, **primär administratör** och **Språk** för den nya webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="792f1-116">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

> [!NOTE] 
> <span data-ttu-id="792f1-117">Du kan välja en webbplats för innehållscenter i något av de tillgängliga språken, men observera att modeller för närvarande endast kan skapas för engelska filer.</span><span class="sxs-lookup"><span data-stu-id="792f1-117">You can select a content center site to render in any of the available languages, but note that currently models can only be created for English files.</span></span> <span data-ttu-id="792f1-118">Observera också att precis som med andra webbplatsmallar kan standardwebbplatsens språk inte redigeras när webbplatsen har skapats.</span><span class="sxs-lookup"><span data-stu-id="792f1-118">Also note that like other site templates, the default site language isn't editable after the site is created.</span></span></br>

6. <span data-ttu-id="792f1-119">Välj **Färdig**.</span><span class="sxs-lookup"><span data-stu-id="792f1-119">Select **Finished**.</span></span>
 
<span data-ttu-id="792f1-120">När du har skapat en webbplats för innehållscentret visas den på sidan **Aktiva webbplatser** i administrationscenter för SharePoint.</span><span class="sxs-lookup"><span data-stu-id="792f1-120">After you create a content center site, you will see it listed on the **Active sites** page in the SharePoint admin center.</span></span> 

### <a name="give-access-to-additional-users"></a><span data-ttu-id="792f1-121">Ge behörighet till ytterligare användare</span><span class="sxs-lookup"><span data-stu-id="792f1-121">Give access to additional users</span></span>
 
<span data-ttu-id="792f1-122">När du har skapat webbplatsen kan du ge fler användare åtkomst till den via standard[modellen för SharePoint-webbplatsbehörigheter](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span><span class="sxs-lookup"><span data-stu-id="792f1-122">After you create the site, you can give additional users access to the site through the standard [SharePoint site permissions model](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span>

## <a name="see-also"></a><span data-ttu-id="792f1-123">Se även</span><span class="sxs-lookup"><span data-stu-id="792f1-123">See Also</span></span>
[<span data-ttu-id="792f1-124">Skapa en klassificerare</span><span class="sxs-lookup"><span data-stu-id="792f1-124">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="792f1-125">Skapa en extraktor</span><span class="sxs-lookup"><span data-stu-id="792f1-125">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="792f1-126">Skapa ett innehållscenter</span><span class="sxs-lookup"><span data-stu-id="792f1-126">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="792f1-127">Översikt av dokumenttolkning</span><span class="sxs-lookup"><span data-stu-id="792f1-127">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="792f1-128">Skapa en modell för formulärbearbetning</span><span class="sxs-lookup"><span data-stu-id="792f1-128">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="792f1-129">Använda en modell</span><span class="sxs-lookup"><span data-stu-id="792f1-129">Apply a model</span></span>](apply-a-model.md)    
