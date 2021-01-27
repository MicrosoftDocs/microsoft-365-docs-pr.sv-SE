---
title: Skillnader mellan modeller för dokumenttolkning och modeller för formulärbearbetning
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
description: Beskriver viktiga skillnader mellan modeller för dokumenttolkning och modeller för formulärbearbetning
ms.openlocfilehash: f57d220eb77a783de5ac352f3cf684364252a163
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/25/2021
ms.locfileid: "49975883"
---
# <a name="difference-between-document-understanding-and-form-processing-models"></a><span data-ttu-id="587ea-103">Skillnader mellan modeller för dokumenttolkning och modeller för formulärbearbetning</span><span class="sxs-lookup"><span data-stu-id="587ea-103">Difference between document understanding and form processing models</span></span> 


<span data-ttu-id="587ea-104">Med innehållstolkning i Microsoft SharePoint Syntex kan du identifiera och klassificera dokument som har laddats upp till SharePoints dokumentbibliotek och extrahera relevant information från varje fil.</span><span class="sxs-lookup"><span data-stu-id="587ea-104">Content understanding in Microsoft SharePoint Syntex allows you to identify and classify documents that are uploaded to SharePoint document libraries, and extract relevant information from each file.</span></span>  <span data-ttu-id="587ea-105">När filer till exempel överförs till ett dokumentbibliotek i SharePoint kan alla filer som identifieras som *Inköpsordrar* klassificeras som sådana och sedan visas i en anpassad vy för dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="587ea-105">For example, as files are uploaded to a SharePoint document library, all files that are identified as *Purchase Orders* are classified as such, and then displayed in a custom document library view.</span></span> <span data-ttu-id="587ea-106">Du kan också hämta särskild information från varje fil (till exempel *Inköpsordernummer* och *Summa*) och visa den som en kolumn i vyn för dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="587ea-106">Additionally, you can pull specific information from each file (for example, *PO Number* and *Total*) and display it as a column in your document library view.</span></span> 

<span data-ttu-id="587ea-107">Med innehållstolkning kan du skapa *modeller* för att identifiera och hämta den information du behöver.</span><span class="sxs-lookup"><span data-stu-id="587ea-107">Content understanding lets you create *models* to identify and extract the information you need.</span></span> <span data-ttu-id="587ea-108">Modeller har ett värde som hjälper dig att lösa affärsproblem för sökningar, affärsprocesser, regelefterlevnad och många andra.</span><span class="sxs-lookup"><span data-stu-id="587ea-108">Models have value in helping to resolve business issues for search, business processes, compliance, and many others.</span></span>

<span data-ttu-id="587ea-109">Det finns två modell typer som du kan använda:</span><span class="sxs-lookup"><span data-stu-id="587ea-109">There are two model types that you can use:</span></span>

- [<span data-ttu-id="587ea-110">Modeller för dokumenttolkning</span><span class="sxs-lookup"><span data-stu-id="587ea-110">Document understanding models</span></span>](document-understanding-overview.md)
- [<span data-ttu-id="587ea-111">Modeller för formulärbearbetning</span><span class="sxs-lookup"><span data-stu-id="587ea-111">Form processing models</span></span>](form-processing-overview.md)

<span data-ttu-id="587ea-112">Båda modellerna används vanligtvis för samma syfte och de viktigaste skillnaderna som anges nedan påverkar vilka som du kan använda.</span><span class="sxs-lookup"><span data-stu-id="587ea-112">While both models are generally used for the same purpose, the key differences listed below affect which ones you can use.</span></span>

> [!NOTE]
> <span data-ttu-id="587ea-113">Mer information om formulärbearbetning och scenarioexempel på dokumenttolkning finns i [Införande av SharePoint Syntex: kom igång-guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example).</span><span class="sxs-lookup"><span data-stu-id="587ea-113">See the [SharePoint Syntex adoption: Get started guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example) for more information about form processing and document understanding scenario examples.</span></span>


## <a name="structured-versus-unstructured-and-semi-structured-content"></a><span data-ttu-id="587ea-114">Strukturerat jämfört med ostrukturerat och halvstrukturerat innehåll</span><span class="sxs-lookup"><span data-stu-id="587ea-114">Structured versus unstructured and semi-structured content</span></span>

<span data-ttu-id="587ea-115">Använd modeller för dokumenttolkning till att identifiera och hämta data från ostrukturerade dokument, till exempel brev eller kontrakt, där de textenheter som du vill extrahera finns i meningar eller i vissa områden i dokumentet.</span><span class="sxs-lookup"><span data-stu-id="587ea-115">Use document understanding models to identify and extract data from unstructured documents, such as letters or contracts, where the text entities you want to extract is in sentences or specific regions of the document.</span></span> <span data-ttu-id="587ea-116">Ett ostrukturerat dokument kan till exempel vara ett avtal om förnyelse som kan skrivas ut på olika sätt.</span><span class="sxs-lookup"><span data-stu-id="587ea-116">For example, an unstructured document could be a contract renewal letter that can be written in different ways.</span></span> <span data-ttu-id="587ea-117">Informationen finns dock konsekvent i brödtexten i varje avtal om förnyelse, till exempel textsträngen *tjänstens startdatum* följt av ett faktiskt datum.</span><span class="sxs-lookup"><span data-stu-id="587ea-117">However, information exists consistently in the body of each contract renewal document, such as the text string *Service start date of* followed by an actual date.</span></span>

<span data-ttu-id="587ea-118">Använd modeller för formulärbearbetning för att identifiera filer och hämta data från strukturerade eller halvstrukturerade dokument, t. ex. formulär och fakturor.</span><span class="sxs-lookup"><span data-stu-id="587ea-118">Use form processing models to identify files and extract data from structured or semi-structured documents, such as forms or invoices.</span></span> <span data-ttu-id="587ea-119">Modeller för formulärbearbetning är utbildade för att förstå layouten av ditt formulär från t. ex. dokument och lär sig att leta efter de data du behöver extrahera från liknande platser.</span><span class="sxs-lookup"><span data-stu-id="587ea-119">Form processing models are trained to understand the layout of your form from example documents, and learn to look for the data you need to extract from similar locations.</span></span> <span data-ttu-id="587ea-120">Formulär har vanligtvis en mer strukturerad layout där enheter är på samma plats (till exempel ett personnummer i ett momsformulär).</span><span class="sxs-lookup"><span data-stu-id="587ea-120">Forms usually have a more structured layout where entities are in the same location (for example, a social security number in a tax form).</span></span>

> [!NOTE]
> <span data-ttu-id="587ea-121">För att skapa en modell för dokumenttolkning eller för att använda den i ett dokumentbibliotek i SharePoint måste du ha tillgång till en webbplats för innehållscenter.</span><span class="sxs-lookup"><span data-stu-id="587ea-121">You must have access to a content center site to create a document understanding model or to apply one to a SharePoint document library.</span></span> 


## <a name="where-models-are-created"></a><span data-ttu-id="587ea-122">Var modellerna skapas</span><span class="sxs-lookup"><span data-stu-id="587ea-122">Where models are created</span></span>

<span data-ttu-id="587ea-123">Modeller för dokumenttolkning skapas och hanteras på en SharePoint-webbplats för innehållscenter.</span><span class="sxs-lookup"><span data-stu-id="587ea-123">Document understanding models are created and managed in a SharePoint content center site.</span></span> 

> [!NOTE]
> <span data-ttu-id="587ea-124">Mer information om indatafiler finns i [Krav och begränsningar för modeller för formulärbearbetning](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span><span class="sxs-lookup"><span data-stu-id="587ea-124">For more information about input documents, see [Form processing model requirements and limitations](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span></span> 

<span data-ttu-id="587ea-125">Modeller för formulärbearbetning skapas i PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), men skapandet startas direkt från ett dokumentbibliotek i SharePoint.</span><span class="sxs-lookup"><span data-stu-id="587ea-125">Form processing models are created in PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), but the creation starts directly from a SharePoint document library.</span></span> <span data-ttu-id="587ea-126">Ett dokumentbibliotek måste ha en modell för formulärbearbetning aktiverad för att en användare ska kunna skapa en modell för formulärbearbetning för den.</span><span class="sxs-lookup"><span data-stu-id="587ea-126">A document library must have form processing model creation enabled before a user can create a form processing model for it.</span></span> <span data-ttu-id="587ea-127">Administratörer kan aktivera skapande av modell för formulärbearbetning i de administratörsinställningar som gäller för innehållstolkning.</span><span class="sxs-lookup"><span data-stu-id="587ea-127">Admins can enable form processing model creation in the content understanding admin settings.</span></span> <span data-ttu-id="587ea-128">Modeller för formulärbearbetning använder PowerAutomate-flöden för att bearbeta filer när de överförs till dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="587ea-128">Form processing models use PowerAutomate flows to process files when they're uploaded to the document library.</span></span>

<span data-ttu-id="587ea-129">När du skapar en modell för dokumenttolkning skapar du en ny [innehållstyp för SharePoint](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) som sparas i galleriet för innehållstyper i SharePoint.</span><span class="sxs-lookup"><span data-stu-id="587ea-129">When you create a document understanding model, you create a new [SharePoint content type](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) that is saved to the SharePoint Content Types gallery.</span></span> <span data-ttu-id="587ea-130">Du kan också använda befintliga innehållstyper för att definiera din modell om det behövs.</span><span class="sxs-lookup"><span data-stu-id="587ea-130">Or you can use existing content types to define your model if needed.</span></span>

<span data-ttu-id="587ea-131">Modeller för formulärbearbetning skapar också nya [innehållstyper för SharePoint](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) och lagras även i galleriet för innehållstyper i SharePoint.</span><span class="sxs-lookup"><span data-stu-id="587ea-131">Form processing models also create new [SharePoint content types](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978), and are also stored in the SharePoint Content Types gallery.</span></span>

## <a name="where-they-can-be-applied"></a><span data-ttu-id="587ea-132">Var de kan användas</span><span class="sxs-lookup"><span data-stu-id="587ea-132">Where they can be applied</span></span>

<span data-ttu-id="587ea-133">Du kan använda modeller för dokumenttolkning för dokumentbibliotek i SharePoint som du har åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="587ea-133">You can apply document understanding models to SharePoint document libraries that you have access to.</span></span> <span data-ttu-id="587ea-134">Använd innehållscentret för att skapa en modell för dokumenttolkning och använd det i olika dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="587ea-134">Use the content center to create a document understanding model, and apply it to different document libraries.</span></span> <span data-ttu-id="587ea-135">I innehållscentret får du en mer central kontroll för hur modeller för dokumenttolkning används och var de används.</span><span class="sxs-lookup"><span data-stu-id="587ea-135">The content center gives you a more central control for how document understanding models are used and where they're applied.</span></span> <span data-ttu-id="587ea-136">OBS! den här informationen måste också sammanställas till ett innehållscenter.</span><span class="sxs-lookup"><span data-stu-id="587ea-136">Note this information must also roll up to a content center.</span></span>

<span data-ttu-id="587ea-137">Modeller för formulärbearbetning kan för närvarande bara användas för dokumentbiblioteket i SharePoint som du skapade dem från.</span><span class="sxs-lookup"><span data-stu-id="587ea-137">Form processing models can currently only be applied to the SharePoint document library from which you created them.</span></span> <span data-ttu-id="587ea-138">Det gör att licensierade användare med åtkomst till webbplatsen kan skapa en modell för formulärbearbetning.</span><span class="sxs-lookup"><span data-stu-id="587ea-138">This allows licensed users with access to the site to create a form processing model.</span></span> <span data-ttu-id="587ea-139">Observera att en administratör måste aktivera formulärbearbetning i ett dokumentbibliotek i SharePoint för att den ska vara tillgänglig för licensierade användare.</span><span class="sxs-lookup"><span data-stu-id="587ea-139">Note that an admin needs to enable form processing on a SharePoint document library for it to be available to licensed users.</span></span>

 ## <a name="see-also"></a><span data-ttu-id="587ea-140">Se även</span><span class="sxs-lookup"><span data-stu-id="587ea-140">See Also</span></span>
[<span data-ttu-id="587ea-141">Utbildning: Förbättra affärsprestanda med AI Builder</span><span class="sxs-lookup"><span data-stu-id="587ea-141">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)



[<span data-ttu-id="587ea-142">Översikt för dokumenttolkning</span><span class="sxs-lookup"><span data-stu-id="587ea-142">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="587ea-143">Översikt för formulärbearbetning</span><span class="sxs-lookup"><span data-stu-id="587ea-143">Form processing overview</span></span>](form-processing-overview.md)

[<span data-ttu-id="587ea-144">Introduktion till SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="587ea-144">Introduction to SharePoint Syntex</span></span>](index.md)
