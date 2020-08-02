---
title: Skapa ett innehållscenter (förhandsgranska)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Läs om hur du skapar ett innehållscenter.
ms.openlocfilehash: ced47f8029079910479dd9aa5c43b39870a56aea
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537902"
---
# <a name="create-a-content-center-preview"></a><span data-ttu-id="d4201-103">Skapa ett innehållscenter (förhandsgranska)</span><span class="sxs-lookup"><span data-stu-id="d4201-103">Create a content center (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="d4201-104">Innehållet i den här artikeln är för Project Cortex Private Preview.</span><span class="sxs-lookup"><span data-stu-id="d4201-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="d4201-105">[Läs mer om Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="d4201-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span></br>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="d4201-106">Om du vill skapa och hantera dokumentförståelsemodeller behöver du först ett innehållscenter.</span><span class="sxs-lookup"><span data-stu-id="d4201-106">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="d4201-107">Innehållscentret är gränssnittet för att skapa modeller och innehåller även information om vilka dokumentbibliotek publicerade modeller som har tillämpats.</span><span class="sxs-lookup"><span data-stu-id="d4201-107">The content center is the model creation interface and also contains information about which document libraries published models have been applied.</span></span></br>

   ![Välj ett dokumentbibliotek](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="d4201-109">Ett första innehållscenter skapas under [installationen,](set-up-content-understanding.md)men en SharePoint-administratör kan välja att skapa ytterligare som behövs.</span><span class="sxs-lookup"><span data-stu-id="d4201-109">An initial content center is created during [setup](set-up-content-understanding.md), but a SharePoint admin can choose to create additional ones as needed.</span></span> <span data-ttu-id="d4201-110">Även om ett enda innehållscenter kan vara bra för miljöer där du vill se en sammanslagning av all modellaktivitet, kanske du vill ha ytterligare om du har flera avdelningar inom organisationen som kan ha olika behov och krav för sina modeller.</span><span class="sxs-lookup"><span data-stu-id="d4201-110">While a single content center may be fine for environments in which you want to see a roll-up of all model activity, you may want to have additional ones if your have multiple departments within your organization that may have different needs and requirements for their models.</span></span>

<span data-ttu-id="d4201-111">En SharePoint-administratör kan skapa en webbplats för innehållscentret på samma sätt som de skulle [skapa en annan SharePoint-webbplats](https://docs.microsoft.com/sharepoint/create-site-collection) – via en webbplatsmall.</span><span class="sxs-lookup"><span data-stu-id="d4201-111">A SharePoint admin can create a content center site like they would [create any other SharePoint site](https://docs.microsoft.com/sharepoint/create-site-collection) - through a site template.</span></span>

<span data-ttu-id="d4201-112">Så här skapar du ett nytt innehållscenter:</span><span class="sxs-lookup"><span data-stu-id="d4201-112">To create a new content center:</span></span>

1. <span data-ttu-id="d4201-113">Gå till administrationscentret för SharePoint i Administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d4201-113">On the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>
2. <span data-ttu-id="d4201-114">Välj **Aktiva webbplatser**under **Webbplatser**i Administrationscentret för SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d4201-114">On the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>
3. <span data-ttu-id="d4201-115">Klicka på **Skapa**på sidan **Aktiva webbplatser** och välj sedan **Andra alternativ**.</span><span class="sxs-lookup"><span data-stu-id="d4201-115">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>
4. <span data-ttu-id="d4201-116">Välj **Content Center**på menyn Välj **en mall** .</span><span class="sxs-lookup"><span data-stu-id="d4201-116">On the **Choose a template** menu, select **Content Center**.</span></span>
5. <span data-ttu-id="d4201-117">För den nya webbplatsen anger du ett **webbplatsnamn,** **primär administratör**och ett **språk**.</span><span class="sxs-lookup"><span data-stu-id="d4201-117">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

> [!Note] 
> <span data-ttu-id="d4201-118">Du kan välja en content center-webbplats som du vill återge på något av de tillgängliga språken, men observera att modeller för närvarande bara kan skapas för engelska filer.</span><span class="sxs-lookup"><span data-stu-id="d4201-118">You can select a content center site to render in any of the available languages, but note that currently models can only be created for English files.</span></span></br>

6. <span data-ttu-id="d4201-119">Klicka på **Klar**.</span><span class="sxs-lookup"><span data-stu-id="d4201-119">Click **Finished**.</span></span>

### <a name="give-access-to-additional-users"></a><span data-ttu-id="d4201-120">Ge åtkomst till ytterligare användare</span><span class="sxs-lookup"><span data-stu-id="d4201-120">Give access to additional users</span></span>
 
<span data-ttu-id="d4201-121">När webbplatsen har skapats kan du ge ytterligare användare åtkomst till webbplatsen via [standardmodellen för SharePoint-webbplatsbehörigheter](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span><span class="sxs-lookup"><span data-stu-id="d4201-121">After the site is created, you can give additional users access to the site through the standard [SharePoint site permissions model](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span>





## <a name="see-also"></a><span data-ttu-id="d4201-122">Se även</span><span class="sxs-lookup"><span data-stu-id="d4201-122">See Also</span></span>
[<span data-ttu-id="d4201-123">Skapa en klassificerare</span><span class="sxs-lookup"><span data-stu-id="d4201-123">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="d4201-124">Skapa en utsutorn</span><span class="sxs-lookup"><span data-stu-id="d4201-124">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="d4201-125">[Skapa ett innehållscenter](create-a-content-center.md) 
 [Översikt över dokuments förståelse](document-understanding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d4201-125">[Create a content center](create-a-content-center.md)
[Document understanding overview](document-understanding-overview.md)</span></span></br>
[<span data-ttu-id="d4201-126">Skapa en formulärbearbetningsmodell</span><span class="sxs-lookup"><span data-stu-id="d4201-126">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="d4201-127">Använda en modell</span><span class="sxs-lookup"><span data-stu-id="d4201-127">Apply a model</span></span>](apply-a-model.md)    




