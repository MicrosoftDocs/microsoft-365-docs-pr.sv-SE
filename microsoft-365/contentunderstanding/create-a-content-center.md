---
title: Skapa ett innehålls Center (för hands version)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Lär dig hur du skapar ett innehålls Center.
ms.openlocfilehash: 5332ffa195519aebd5ae8dd2c26d7d62fd9b3267
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612756"
---
# <a name="create-a-content-center-preview"></a><span data-ttu-id="95430-103">Skapa ett innehålls Center (för hands version)</span><span class="sxs-lookup"><span data-stu-id="95430-103">Create a content center (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="95430-104">Innehållet i den här artikeln gäller för projekt cortex privat för hands version.</span><span class="sxs-lookup"><span data-stu-id="95430-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="95430-105">[Lär dig mer om Project cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="95430-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span></br>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="95430-106">För att skapa och hantera dokument förståelse modeller behöver du först ett innehålls Center.</span><span class="sxs-lookup"><span data-stu-id="95430-106">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="95430-107">Innehålls centret är gränssnittet för skapande av modell och innehåller information om vilka dokument bibliotek som har publicerats.</span><span class="sxs-lookup"><span data-stu-id="95430-107">The content center is the model creation interface and also contains information about which document libraries published models have been applied.</span></span></br>

   ![Välj ett dokument bibliotek](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="95430-109">Ett ursprungligt innehålls Center skapas under [installationen](set-up-content-understanding.md), men en SharePoint-administratör kan välja att skapa fler som behövs.</span><span class="sxs-lookup"><span data-stu-id="95430-109">An initial content center is created during [setup](set-up-content-understanding.md), but a SharePoint admin can choose to create additional ones as needed.</span></span> <span data-ttu-id="95430-110">Även om det kan vara bra att använda ett enda innehålls Center för miljöer där du vill se en sammanfattning av alla modell aktiviteter, kanske du vill få ytterligare information om din organisation har flera avdelningar som kan ha olika behov och krav för sina modeller.</span><span class="sxs-lookup"><span data-stu-id="95430-110">While a single content center may be fine for environments in which you want to see a roll-up of all model activity, you may want to have additional ones if your have multiple departments within your organization that may have different needs and requirements for their models.</span></span>

<span data-ttu-id="95430-111">En SharePoint-administratör kan skapa en innehålls Center-webbplats som de [skapar andra SharePoint-webbplatser](https://docs.microsoft.com/sharepoint/create-site-collection) – genom en webbplatsmall.</span><span class="sxs-lookup"><span data-stu-id="95430-111">A SharePoint admin can create a content center site like they would [create any other SharePoint site](https://docs.microsoft.com/sharepoint/create-site-collection) - through a site template.</span></span>

<span data-ttu-id="95430-112">Så här skapar du ett nytt innehålls Center:</span><span class="sxs-lookup"><span data-stu-id="95430-112">To create a new content center:</span></span>

1. <span data-ttu-id="95430-113">Gå till administrations centret för SharePoint i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="95430-113">On the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>
2. <span data-ttu-id="95430-114">Gå till administrations centret för SharePoint och välj **aktiva webbplatser**under **webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="95430-114">On the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>
3. <span data-ttu-id="95430-115">På sidan **aktiva webbplatser** klickar du på **skapa**och väljer sedan **andra alternativ**.</span><span class="sxs-lookup"><span data-stu-id="95430-115">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>
4. <span data-ttu-id="95430-116">Gå till menyn **Välj en mall** och välj **innehålls Center**.</span><span class="sxs-lookup"><span data-stu-id="95430-116">On the **Choose a template** menu, select **Content Center**.</span></span>
5. <span data-ttu-id="95430-117">Ange ett **namn**, en **primär administratör**och ett **språk**för den nya webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="95430-117">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

> [!Note] 
> <span data-ttu-id="95430-118">Du kan välja en innehålls Center webbplats som ska återges på något av de tillgängliga språken, men det går bara att skapa en anteckning för att för engelska filer.</span><span class="sxs-lookup"><span data-stu-id="95430-118">You can select a content center site to render in any of the available languages, but note that currently models can only be created for English files.</span></span></br>

6. <span data-ttu-id="95430-119">Klicka på **klar**.</span><span class="sxs-lookup"><span data-stu-id="95430-119">Click **Finished**.</span></span>

### <a name="give-access-to-additional-users"></a><span data-ttu-id="95430-120">Ge till gång till ytterligare användare</span><span class="sxs-lookup"><span data-stu-id="95430-120">Give access to additional users</span></span>
 
<span data-ttu-id="95430-121">När webbplatsen har skapats kan du ge ytterligare användare åtkomst till webbplatsen via standard modell för SharePoint- [webbplatsens behörigheter](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span><span class="sxs-lookup"><span data-stu-id="95430-121">After the site is created, you can give additional users access to the site through the standard [SharePoint site permissions model](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span>





## <a name="see-also"></a><span data-ttu-id="95430-122">Se även</span><span class="sxs-lookup"><span data-stu-id="95430-122">See Also</span></span>
[<span data-ttu-id="95430-123">Skapa en klassificerare</span><span class="sxs-lookup"><span data-stu-id="95430-123">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="95430-124">Skapa en Extractor</span><span class="sxs-lookup"><span data-stu-id="95430-124">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="95430-125">[Skapa ett innehålls Center](create-a-content-center.md) 
 [Översikt över dokument förståelse](document-understanding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="95430-125">[Create a content center](create-a-content-center.md)
[Document understanding overview](document-understanding-overview.md)</span></span></br>
[<span data-ttu-id="95430-126">Skapa en modell för formulär bearbetning</span><span class="sxs-lookup"><span data-stu-id="95430-126">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="95430-127">Använda en modell</span><span class="sxs-lookup"><span data-stu-id="95430-127">Apply a model</span></span>](apply-a-model.md)    




