---
title: Kör en utvärderingsversion av Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris; jaeccles
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
description: Lär dig hur du planerar och kör ett testpilotprogram för SharePoint Syntex i organisationen.
ms.openlocfilehash: 2668c0c85d6b8c73d377ac9efffc7f777fc7add6
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327148"
---
# <a name="run-a-trial-of-microsoft-sharepoint-syntex"></a><span data-ttu-id="0dc73-103">Kör en utvärderingsversion av Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="0dc73-103">Run a trial of Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="0dc73-104">I den här artikeln beskrivs hur du set up and run a trial pilot program to deploy SharePoint Syntex in your organization.</span><span class="sxs-lookup"><span data-stu-id="0dc73-104">This article describes how to set up and run a trial pilot program to deploy SharePoint Syntex in your organization.</span></span> <span data-ttu-id="0dc73-105">Vi rekommenderar även metodtips för utvärderingsversionen.</span><span class="sxs-lookup"><span data-stu-id="0dc73-105">It also recommends best practices for the trial.</span></span>

## <a name="sign-up-for-a-trial"></a><span data-ttu-id="0dc73-106">Registrera dig för en utvärderingsversion</span><span class="sxs-lookup"><span data-stu-id="0dc73-106">Sign up for a trial</span></span>

<span data-ttu-id="0dc73-107">Utvärderingsversionen SharePoint Syntex 300 användare i 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="0dc73-107">The trial of SharePoint Syntex gives access to 300 users for 30 days.</span></span>

> [!NOTE]
> <span data-ttu-id="0dc73-108">Upp till 300 användare ingår i utvärderingsversionen för att säkerställa att 1 miljon AI Builder-krediter automatiskt tillräknas.</span><span class="sxs-lookup"><span data-stu-id="0dc73-108">Up to 300 users are included in the trial to ensure the automatic addition of 1 million AI Builder credits.</span></span> <span data-ttu-id="0dc73-109">Du behöver inte inkludera 300 användare för att en utvärderingsversion ska lyckas.</span><span class="sxs-lookup"><span data-stu-id="0dc73-109">You do not have to include 300 users for a trial to succeed.</span></span>

<span data-ttu-id="0dc73-110">Du kan hämta utvärderingsversionen från någon av följande källor:</span><span class="sxs-lookup"><span data-stu-id="0dc73-110">You can get the trial version from one of the following sources:</span></span>

- <span data-ttu-id="0dc73-111">Sidan [SharePoint Syntex produkt](https://www.microsoft.com/microsoft-365/enterprise/sharepoint-syntex?activetab=pivot:overviewtab)</span><span class="sxs-lookup"><span data-stu-id="0dc73-111">The [SharePoint Syntex product page](https://www.microsoft.com/microsoft-365/enterprise/sharepoint-syntex?activetab=pivot:overviewtab)</span></span>

- <span data-ttu-id="0dc73-112">Administrationscenter för Microsoft 365 [](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="0dc73-112">The [Microsoft 365 admin center](https://admin.microsoft.com)</span></span>
    1.  <span data-ttu-id="0dc73-113">Logga in på [Administrationscenter för Microsoft 365](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="0dc73-113">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
    2.  <span data-ttu-id="0dc73-114">Gå till **Tjänster för**  >  **faktureringsköp.**</span><span class="sxs-lookup"><span data-stu-id="0dc73-114">Go to **Billing** > **Purchase Services**.</span></span>
    3.  <span data-ttu-id="0dc73-115">Rulla ned till **avsnittet** Tillägg.</span><span class="sxs-lookup"><span data-stu-id="0dc73-115">Scroll down to the **Add-Ons** section.</span></span>
    4.  <span data-ttu-id="0dc73-116">På panelen SharePoint Syntex väljer du **Information**.</span><span class="sxs-lookup"><span data-stu-id="0dc73-116">On the SharePoint Syntex tile, select **Details**.</span></span>
    5.  <span data-ttu-id="0dc73-117">Välj **Hämta kostnadsfri utvärderingsversion**.</span><span class="sxs-lookup"><span data-stu-id="0dc73-117">Select **Get free trial**.</span></span>
    6.  <span data-ttu-id="0dc73-118">Bekräfta utvärderingsversionen genom att följa de återstående stegen i guiden.</span><span class="sxs-lookup"><span data-stu-id="0dc73-118">To confirm the trial, follow the remaining wizard steps.</span></span>

<span data-ttu-id="0dc73-119">Du måste vara global Microsoft 365 eller faktureringsadministratör för att aktivera en utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="0dc73-119">You must be a Microsoft 365 global administrator or billing administrator to activate a trial.</span></span>

### <a name="who-should-be-involved-in-a-trial"></a><span data-ttu-id="0dc73-120">Vem bör vara involverad i en utvärderingsversion</span><span class="sxs-lookup"><span data-stu-id="0dc73-120">Who should be involved in a trial</span></span>

|<span data-ttu-id="0dc73-121">Roll</span><span class="sxs-lookup"><span data-stu-id="0dc73-121">Role</span></span>  |<span data-ttu-id="0dc73-122">Aktivitet</span><span class="sxs-lookup"><span data-stu-id="0dc73-122">Activity</span></span>  |
|---------|---------|
|<span data-ttu-id="0dc73-123">Microsoft 365 global administratör eller faktureringsadministratör</span><span class="sxs-lookup"><span data-stu-id="0dc73-123">Microsoft 365 global admin or billing admin</span></span>    |     <span data-ttu-id="0dc73-124">Aktivera utvärderingsversionen och tilldela licenser</span><span class="sxs-lookup"><span data-stu-id="0dc73-124">Activate the trial and assign licenses</span></span>    |
|<span data-ttu-id="0dc73-125">Microsoft 365 global administratör SharePoint administratör</span><span class="sxs-lookup"><span data-stu-id="0dc73-125">Microsoft 365 global admin or SharePoint admin</span></span>     |   <span data-ttu-id="0dc73-126">Konfigurera SharePoint Syntex och skapa innehållscenter</span><span class="sxs-lookup"><span data-stu-id="0dc73-126">Configure SharePoint Syntex and create content centers</span></span>      |
|<span data-ttu-id="0dc73-127">Företagsanvändare</span><span class="sxs-lookup"><span data-stu-id="0dc73-127">Business users</span></span>     |    <span data-ttu-id="0dc73-128">Skapa och testa modeller</span><span class="sxs-lookup"><span data-stu-id="0dc73-128">Model building and testing</span></span>     |

### <a name="before-you-activate-a-trial"></a><span data-ttu-id="0dc73-129">Innan du aktiverar en utvärderingsversion</span><span class="sxs-lookup"><span data-stu-id="0dc73-129">Before you activate a trial</span></span>

<span data-ttu-id="0dc73-130">Om du vill planera SharePoint Syntex utvärderingsversion bör du tänka på följande:</span><span class="sxs-lookup"><span data-stu-id="0dc73-130">To successfully plan a SharePoint Syntex trial, consider the following factors:</span></span>

- <span data-ttu-id="0dc73-131">De mest meningsfulla testerna slutförs på verkliga scenarier och data.</span><span class="sxs-lookup"><span data-stu-id="0dc73-131">The most meaningful testing is completed on “real world” scenarios and data.</span></span>
- <span data-ttu-id="0dc73-132">Du kan bara aktivera en SharePoint Syntex en gång per klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="0dc73-132">You can only activate a SharePoint Syntex trial once per tenant.</span></span>

<span data-ttu-id="0dc73-133">En test- eller demoklientorganisation kan användas som "torr körning" för att gå igenom aktiveringsstegen och administrativa kontroller.</span><span class="sxs-lookup"><span data-stu-id="0dc73-133">A test or demo tenant can be used as a “dry run” to walk through the activation steps and administrative controls.</span></span> <span data-ttu-id="0dc73-134">Men det är förmodligen bäst att utvärdera modellbygget på en produktionsklientorganisation.</span><span class="sxs-lookup"><span data-stu-id="0dc73-134">But it’s probably best to evaluate model building on a production tenant.</span></span>

<span data-ttu-id="0dc73-135">För att maximera värdet för en utvärderingsversion av en produktionsklient är det viktigt att planera och engagera företaget.</span><span class="sxs-lookup"><span data-stu-id="0dc73-135">To maximize the value of a trial on a production tenant, planning and business engagement are essential.</span></span> <span data-ttu-id="0dc73-136">Du bör engagera ett eller flera affärsområden för att identifiera tre till sex användningsfall som potentiellt skulle kunna hanteras av SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="0dc73-136">You should engage one or more business areas to identify three-to-six use cases that could potentially be addressed by SharePoint Syntex.</span></span> <span data-ttu-id="0dc73-137">Dessa användningsfall bör:</span><span class="sxs-lookup"><span data-stu-id="0dc73-137">These use cases should:</span></span>

- <span data-ttu-id="0dc73-138">Inkludera scenarier som kan lösas med hjälp av antingen formulärbearbetnings- eller dokument förstå modellen.</span><span class="sxs-lookup"><span data-stu-id="0dc73-138">Include scenarios that could be solved by either the forms processing or document understanding model.</span></span>
- <span data-ttu-id="0dc73-139">Förstå tydligt syftet med extraherade metadata. Visa till exempel formatering eller automatisering genom att använda Power Automate.</span><span class="sxs-lookup"><span data-stu-id="0dc73-139">Have a clear understanding of the purpose for any extracted metadata; for example, view formatting or automation by using Power Automate.</span></span> <span data-ttu-id="0dc73-140">Medan SharePoint Syntex fokuserar på att klassificera dokument och extrahera metadata, är det värde som ska mätas vad dessa metadata möjliggör.</span><span class="sxs-lookup"><span data-stu-id="0dc73-140">While SharePoint Syntex is focused on classifying documents and extracting metadata, the value to quantify is what this metadata enables.</span></span>
- <span data-ttu-id="0dc73-141">Baseras på en definierad uppsättning data. till exempel specifika SharePoint webbplatser eller bibliotek.</span><span class="sxs-lookup"><span data-stu-id="0dc73-141">Be based on a defined set of data; for example, specific SharePoint sites or libraries.</span></span> <span data-ttu-id="0dc73-142">En vanlig missuppfattning av SharePoint Syntex är att modeller av allmänna ändamål kan tillämpas i hela organisationens innehåll.</span><span class="sxs-lookup"><span data-stu-id="0dc73-142">A common misconception of SharePoint Syntex is that general purpose models can be applied across all organization content.</span></span> <span data-ttu-id="0dc73-143">En mer exakt vy är att modeller är byggda för att hjälpa till att lösa specifika affärsproblem på riktade platser.</span><span class="sxs-lookup"><span data-stu-id="0dc73-143">A more accurate view is that models are built to help solve specific business problems in targeted locations.</span></span>

<span data-ttu-id="0dc73-144">Alla dessa användningsfall kanske inte passar bra för SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="0dc73-144">All of these use cases might not be a good fit for SharePoint Syntex.</span></span> <span data-ttu-id="0dc73-145">Syftet med en kvalitets utvärderingsversion är inte att bevisa att SharePoint Syntex kommer att passa alla scenarier.</span><span class="sxs-lookup"><span data-stu-id="0dc73-145">The goal of a quality trial isn't to prove that SharePoint Syntex will fit all the scenarios.</span></span> <span data-ttu-id="0dc73-146">I stället bör utvärderingsversionen hjälpa dig att bättre förstå produktvärdet.</span><span class="sxs-lookup"><span data-stu-id="0dc73-146">Instead, the trial should help you better understand the value of product.</span></span>

<span data-ttu-id="0dc73-147">Identifiera användare som är ämnesexperter i relaterat innehåll eller relaterad process för vart och ett av de planerade användningsfallen.</span><span class="sxs-lookup"><span data-stu-id="0dc73-147">For each of the planned use cases, identify users who are subject matter experts in the related content or process.</span></span> <span data-ttu-id="0dc73-148">Skapandet av SharePoint Syntex är fokuserat på domänexperter i innehållet i stället för på IT-personal eller utvecklarresurser.</span><span class="sxs-lookup"><span data-stu-id="0dc73-148">The creation of SharePoint Syntex models is focused on domain experts in the content, rather than on IT professionals or developer resources.</span></span>

## <a name="activate-a-trial"></a><span data-ttu-id="0dc73-149">Aktivera en utvärderingsversion</span><span class="sxs-lookup"><span data-stu-id="0dc73-149">Activate a trial</span></span>

<span data-ttu-id="0dc73-150">När du påbörjar en utvärderingsversion måste du:</span><span class="sxs-lookup"><span data-stu-id="0dc73-150">When you initiate a trial, you need to:</span></span>

- <span data-ttu-id="0dc73-151">Tilldela licenser till relevanta användare.</span><span class="sxs-lookup"><span data-stu-id="0dc73-151">Assign licenses to the relevant users.</span></span>
- <span data-ttu-id="0dc73-152">Utför [ytterligare konfiguration av SharePoint Syntex](set-up-content-understanding.md).</span><span class="sxs-lookup"><span data-stu-id="0dc73-152">Perform [additional setup of SharePoint Syntex](set-up-content-understanding.md).</span></span>
    - <span data-ttu-id="0dc73-153">Du kanske vill skapa [ytterligare innehållscenter](create-a-content-center.md).</span><span class="sxs-lookup"><span data-stu-id="0dc73-153">You might want to [create additional content centers](create-a-content-center.md).</span></span>

<span data-ttu-id="0dc73-154">När utvärderingsversionen har aktiverats kan du skapa modeller och processfiler.</span><span class="sxs-lookup"><span data-stu-id="0dc73-154">After the trial is activated, you can create models and process files.</span></span> <span data-ttu-id="0dc73-155">Se [vägledning för att skapa modeller.](create-a-content-center.md)</span><span class="sxs-lookup"><span data-stu-id="0dc73-155">See [guidance for model creation](create-a-content-center.md).</span></span>

## <a name="during-a-trial"></a><span data-ttu-id="0dc73-156">Under en utvärderingsversion</span><span class="sxs-lookup"><span data-stu-id="0dc73-156">During a trial</span></span>

<span data-ttu-id="0dc73-157">Utvärderingsperioder är begränsade, så det är bäst att först fokusera på SharePoint Syntex kan klassificera dokument och extrahera metadata för de definierade användningsfallen.</span><span class="sxs-lookup"><span data-stu-id="0dc73-157">Trial periods are limited, so it’s best to focus initially on whether SharePoint Syntex models can classify documents and extract metadata for the defined use cases.</span></span> <span data-ttu-id="0dc73-158">När utvärderingsperioden är slut kan du utvärdera hur metadata kan utnyttjas.</span><span class="sxs-lookup"><span data-stu-id="0dc73-158">After the trial period is over, you can evaluate how the metadata can be exploited.</span></span>

## <a name="after-a-trial"></a><span data-ttu-id="0dc73-159">Efter en utvärderingsversion</span><span class="sxs-lookup"><span data-stu-id="0dc73-159">After a trial</span></span>

<span data-ttu-id="0dc73-160">Baserat på resultatet av utvärderingsversionen kan du bestämma om du vill fortsätta med produktionsanvändningen av SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="0dc73-160">Based on the outcome of the trial, you can decide whether to proceed to production use of SharePoint Syntex.</span></span>

### <a name="proceed-to-production-use"></a><span data-ttu-id="0dc73-161">Fortsätt till produktionsanvändning</span><span class="sxs-lookup"><span data-stu-id="0dc73-161">Proceed to production use</span></span>

<span data-ttu-id="0dc73-162">För att säkerställa kontinuiteten i tjänsten behöver du köpa antalet licenser som krävs och tilldela licenserna till användarna.</span><span class="sxs-lookup"><span data-stu-id="0dc73-162">To ensure continuity of service, you need to purchase the required number of licenses and assign those licenses to users.</span></span> <span data-ttu-id="0dc73-163">Utvärderingsanvändare som inte har en fullständig licens i slutet av utvärderingsperioden kommer inte att kunna använda hela SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="0dc73-163">Trial users who don’t have a full license at the end of the trial period won’t be able to fully utilize SharePoint Syntex.</span></span>

<span data-ttu-id="0dc73-164">Du kan behöva uppskatta din beräknade användning av formulärbearbetning och planera för det förväntade antalet AI Builder-krediter.</span><span class="sxs-lookup"><span data-stu-id="0dc73-164">You might have to estimate your projected use of forms processing and plan for the expected amount of AI Builder credits.</span></span> <span data-ttu-id="0dc73-165">Mer information finns i [Uppskatta den AI Builder-kapacitet som är rätt för dig.](https://powerapps.microsoft.com/ai-builder-calculator/)</span><span class="sxs-lookup"><span data-stu-id="0dc73-165">For help, see [Estimate the AI Builder capacity that’s right for you](https://powerapps.microsoft.com/ai-builder-calculator/).</span></span>

### <a name="dont-proceed-to-production-use"></a><span data-ttu-id="0dc73-166">Fortsätt inte till produktionsanvändning</span><span class="sxs-lookup"><span data-stu-id="0dc73-166">Don't proceed to production use</span></span>

<span data-ttu-id="0dc73-167">Om du inte köper licenser efter utvärderingsversionen:</span><span class="sxs-lookup"><span data-stu-id="0dc73-167">If you don’t purchase licenses following the trial:</span></span>

- <span data-ttu-id="0dc73-168">Du kommer inte att kunna skapa nya modeller.</span><span class="sxs-lookup"><span data-stu-id="0dc73-168">You won’t be able to create new models.</span></span>
- <span data-ttu-id="0dc73-169">Bibliotek som körde modeller kommer inte längre att automatiskt klassificera filer eller extrahera modeller.</span><span class="sxs-lookup"><span data-stu-id="0dc73-169">Libraries that were running models will no longer automatically classify files or extract models.</span></span>
- <span data-ttu-id="0dc73-170">Tidigare klassificerade filer eller extraherade metadata påverkas inte.</span><span class="sxs-lookup"><span data-stu-id="0dc73-170">Any previously classified files or extracted metadata won’t be affected.</span></span> 
- <span data-ttu-id="0dc73-171">Innehållscenter och dokumentförståelsemodeller tas inte bort automatiskt.</span><span class="sxs-lookup"><span data-stu-id="0dc73-171">Content centers and any document-understanding models won’t be automatically deleted.</span></span> <span data-ttu-id="0dc73-172">De kommer att vara tillgängliga för användning om du bestämmer dig för att köpa licenser i framtiden.</span><span class="sxs-lookup"><span data-stu-id="0dc73-172">These will remain available for use if you decide to purchase licenses in the future.</span></span>
- <span data-ttu-id="0dc73-173">Modeller som bearbetas i formulär lagras i CDS-instansen (Common Data Services) av standardmiljön för Power Platform.</span><span class="sxs-lookup"><span data-stu-id="0dc73-173">Forms-processing models will be stored in the Common Data Services (CDS) instance of the default Power Platform environment.</span></span> <span data-ttu-id="0dc73-174">De kan användas med framtida licensiering för SharePoint Syntex eller med AI Builder-funktioner i Power-plattformen.</span><span class="sxs-lookup"><span data-stu-id="0dc73-174">These could be used with future licensing for SharePoint Syntex or with AI Builder capabilities in the Power Platform.</span></span>

## <a name="see-also"></a><span data-ttu-id="0dc73-175">Se även</span><span class="sxs-lookup"><span data-stu-id="0dc73-175">See also</span></span>

[<span data-ttu-id="0dc73-176">Införande av Microsoft SharePoint Syntex: Kom igång</span><span class="sxs-lookup"><span data-stu-id="0dc73-176">Microsoft SharePoint Syntex adoption: Get started</span></span>](adoption-getstarted.md)
