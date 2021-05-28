---
title: 'Införande av Microsoft SharePoint Syntex: Komma igång'
description: Lär dig hur du använder och implementerar SharePoint Syntex i din organisation för att hjälpa dig att lösa affärsproblem.
ms.author: samanro
author: samanro
manager: pamgreen
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
ms.openlocfilehash: 9a73f14662deb0fc68ac6c2a8552d988efc1d351
ms.sourcegitcommit: a3359982fea01339c7377e3ee89f223788cee0bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/28/2021
ms.locfileid: "52696472"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a><span data-ttu-id="fe6ae-103">Införande av Microsoft SharePoint Syntex: Komma igång</span><span class="sxs-lookup"><span data-stu-id="fe6ae-103">Microsoft SharePoint Syntex adoption: Get started</span></span>

<span data-ttu-id="fe6ae-104">Tänk på att de intelligenta innehållstjänster som finns SharePoint Syntex har tre delar:</span><span class="sxs-lookup"><span data-stu-id="fe6ae-104">Think of the intelligent content services available in SharePoint Syntex as having three parts:</span></span>

- <span data-ttu-id="fe6ae-105">**Innehållsförståelse:** Skapa AI-modeller utan kod för att klassificera och extrahera information från innehåll för att automatiskt tillämpa metadata för upptäckt och återanvändning av kunskap.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-105">**Content understanding:** Create no-code AI models to classify and extract information from content to automatically apply metadata for knowledge discovery and reuse.</span></span> <span data-ttu-id="fe6ae-106">Läs mer om [innehållsförståelse.](document-understanding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="fe6ae-106">Learn more about [content understanding](document-understanding-overview.md).</span></span>
- <span data-ttu-id="fe6ae-107">**Innehållsbearbetning:** Automatisera insamling, påtagande och kategorisering av innehåll och effektivisera innehållscentrerade processer med hjälp av Power Automate.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-107">**Content processing:** Automate capture, ingestion, and categorization of content and streamline content-centric processes using Power Automate.</span></span> <span data-ttu-id="fe6ae-108">Läs mer om [innehållsbearbetning](form-processing-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fe6ae-108">Learn more about [content processing](form-processing-overview.md).</span></span>
- <span data-ttu-id="fe6ae-109">**Innehållsefterlevnad:** Kontrollera och hantera innehåll för att förbättra säkerhet och styrning med integrering med Microsoft Information Protection.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-109">**Content compliance:** Control and manage content to improve security and governance with integration to Microsoft Information Protection.</span></span>

<span data-ttu-id="fe6ae-110">Med nya AI-tjänster och funktioner kan du bygga in innehållsförståelse och klassificeringsappar direkt i innehållshanteringsflödet med hjälp av SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-110">With new AI services and capabilities, you can build content understanding and classification apps directly into the content management flow using SharePoint Syntex.</span></span> <span data-ttu-id="fe6ae-111">Det finns två olika sätt att förstå innehållet.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-111">There are two different ways of understanding your content.</span></span> <span data-ttu-id="fe6ae-112">Den modelltyp du använder baseras på filformat och användningsfall:</span><span class="sxs-lookup"><span data-stu-id="fe6ae-112">The model type you use is based on file format and use case:</span></span>

| <span data-ttu-id="fe6ae-113">Formulärbearbetning</span><span class="sxs-lookup"><span data-stu-id="fe6ae-113">Form processing</span></span> | <span data-ttu-id="fe6ae-114">Dokumenttolkning</span><span class="sxs-lookup"><span data-stu-id="fe6ae-114">Document understanding</span></span> |
|:-------|:-------|
| <span data-ttu-id="fe6ae-115">Skapad från dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-115">Created from document library.</span></span> | <span data-ttu-id="fe6ae-116">Skapad i innehållscentret, en del av SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-116">Created in the content center, part of SharePoint Syntex.</span></span> |
| <span data-ttu-id="fe6ae-117">Modell skapad i AI-verktyget.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-117">Model created in AI builder.</span></span> | <span data-ttu-id="fe6ae-118">Modell som skapats i gränssnittet.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-118">Model created in native interface.</span></span> |
| <span data-ttu-id="fe6ae-119">Används för semistrukturerade filformat.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-119">Used for semi-structured file formats.</span></span> | <span data-ttu-id="fe6ae-120">Används för ostrukturerade filformat.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-120">Used for unstructured file formats.</span></span> |
| <span data-ttu-id="fe6ae-121">Infogbar klassificerare.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-121">Settable classifier.</span></span> | <span data-ttu-id="fe6ae-122">Utbildare med valfria extraherare.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-122">Trainable classifier with optional extractors.</span></span> |
| <span data-ttu-id="fe6ae-123">Begränsad till ett enskilt bibliotek.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-123">Restricted to a single library.</span></span> | <span data-ttu-id="fe6ae-124">Kan tillämpas på flera bibliotek.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-124">Can be applied to multiple libraries.</span></span> |
| <span data-ttu-id="fe6ae-125">Utbilda i PDF, JPG, PNG-format, totalt 50 MB/500 pp.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-125">Train on PDF, JPG, PNG format, total 50 MB/500 pp.</span></span> | <span data-ttu-id="fe6ae-126">Träna på 5-10 PDF-, Office- eller e-postfiler, inklusive negativa exempel.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-126">Train on 5-10 PDF, Office, or email files, including negative examples.</span></span> |

<span data-ttu-id="fe6ae-127">En mer fullständig jämförelse av funktionerna finns i Skillnaden [mellan dokumentförståelse och formbearbetningsmodeller.](difference-between-document-understanding-and-form-processing-model.md)</span><span class="sxs-lookup"><span data-stu-id="fe6ae-127">For a more complete comparison of the capabilities, see [Difference between document understanding and form processing models](difference-between-document-understanding-and-form-processing-model.md).</span></span>

## <a name="identify-pilot-business-scenarios-to-optimize"></a><span data-ttu-id="fe6ae-128">Identifiera pilotscenarion för att optimera</span><span class="sxs-lookup"><span data-stu-id="fe6ae-128">Identify pilot business scenarios to optimize</span></span>

<span data-ttu-id="fe6ae-129">För att förbereda för SharePoint och Syntex i organisationen måste du först förstå scenarier som kan vara användbara.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-129">To prepare for using SharePoint Syntex in your organization, you first need to understand the scenarios in which it will be useful.</span></span> <span data-ttu-id="fe6ae-130">Med hjälp av "varför" kan du avgöra vilken modell som kommer att användas och hur du strukturerar organisationen baserat på var modellen ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-130">The "why" helps determine what model will be needed, and how to structure your org based on where the model will be applied.</span></span> <span data-ttu-id="fe6ae-131">Här är några scenarier där dokument förstå kan hjälpa din organisation:</span><span class="sxs-lookup"><span data-stu-id="fe6ae-131">Here are a few scenarios where document understanding can help your organization:</span></span>

- <span data-ttu-id="fe6ae-132">**Innehållsbearbetning:** Bearbeta kontrakt, arbetsutdrag och andra formulärliknande dokument.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-132">**Content processing:** Process contracts, statements of work, and other form-like documents.</span></span> <span data-ttu-id="fe6ae-133">Sköta formulären, utbilda modellen för att förstå och mappa fälten och kör sedan dina formulär för att automatiskt samla in data.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-133">Intake the forms, train the model to understand and map the fields, and then run your forms through to automatically collect the data.</span></span> <span data-ttu-id="fe6ae-134">Mer information finns i [Översikt över formulärbearbetning](form-processing-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fe6ae-134">For more information, see [Form processing overview](form-processing-overview.md).</span></span>
- <span data-ttu-id="fe6ae-135">**Fakturaanalys:** Hämta relevant information från dina fakturor och kontrollera att de följer principen eller behandlas på rätt sätt.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-135">**Invoice analysis:** Pull out the relevant details from your invoices and make sure they're complying with policy or are being processed appropriately.</span></span>

<span data-ttu-id="fe6ae-136">Tänk på olika sätt som SharePoint Syntex kan hjälpa din organisation:</span><span class="sxs-lookup"><span data-stu-id="fe6ae-136">Think about ways that SharePoint Syntex can help your organization:</span></span>

- <span data-ttu-id="fe6ae-137">Automatisera affärsprocesser</span><span class="sxs-lookup"><span data-stu-id="fe6ae-137">Automate business processes</span></span>
- <span data-ttu-id="fe6ae-138">Förbättra sökprecisionen</span><span class="sxs-lookup"><span data-stu-id="fe6ae-138">Improve search accuracy</span></span>
- <span data-ttu-id="fe6ae-139">Hantera efterlevnadsrisker</span><span class="sxs-lookup"><span data-stu-id="fe6ae-139">Manage compliance risk</span></span>

<span data-ttu-id="fe6ae-140">När du funderar på vilka affärsscenarier du ska tänka på bör du ställa dig följande frågor:</span><span class="sxs-lookup"><span data-stu-id="fe6ae-140">When thinking about which business scenarios to consider, ask yourself the following questions:</span></span>

- <span data-ttu-id="fe6ae-141">Löser det ett verkligt problem?</span><span class="sxs-lookup"><span data-stu-id="fe6ae-141">Does it solve a real problem?</span></span>
- <span data-ttu-id="fe6ae-142">Kommer den att användas ofta eller ha stor påverkan?</span><span class="sxs-lookup"><span data-stu-id="fe6ae-142">Will it be widely used or have broad impact?</span></span>
- <span data-ttu-id="fe6ae-143">Går det att få tag i den?</span><span class="sxs-lookup"><span data-stu-id="fe6ae-143">Is it obtainable?</span></span>
- <span data-ttu-id="fe6ae-144">Kan du mäta framgång?</span><span class="sxs-lookup"><span data-stu-id="fe6ae-144">Can you measure success?</span></span>

<span data-ttu-id="fe6ae-145">Prioritera scenarier utifrån påverkan och enkelhet vid implementering.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-145">Prioritize scenarios based on impact and ease of implementation.</span></span> <span data-ttu-id="fe6ae-146">Gör ditt första fokusområde mer effekt scenarier som också kan enkelt implementeras.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-146">Make your initial focus area higher impact scenarios that can also be easily implemented.</span></span> <span data-ttu-id="fe6ae-147">Av prioritera scenarier med lägre effekt som är svåra att implementera.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-147">De-prioritize lower impact scenarios that are hard to implement.</span></span>

<span data-ttu-id="fe6ae-148">Använd [exempelscenarier och använd ärenden](adoption-scenarios.md) för att visa en uppmaning om hur du kan SharePoint Syntex i organisationen.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-148">Use the [example scenarios and use cases](adoption-scenarios.md) to prompt ideas about how you can use SharePoint Syntex in your organization.</span></span>

## <a name="identify-roles--responsibilities"></a><span data-ttu-id="fe6ae-149">Identifiera roller & ansvarsområden</span><span class="sxs-lookup"><span data-stu-id="fe6ae-149">Identify roles & responsibilities</span></span>

<span data-ttu-id="fe6ae-150">Vem i organisationen ska skapa och hantera modeller?</span><span class="sxs-lookup"><span data-stu-id="fe6ae-150">Determine who in your organization will build and manage the models?</span></span> <span data-ttu-id="fe6ae-151">Följande roller kan vara inblandade:</span><span class="sxs-lookup"><span data-stu-id="fe6ae-151">The following roles might be involved:</span></span>

| <span data-ttu-id="fe6ae-152">SharePoint-/Knowledge-administratör</span><span class="sxs-lookup"><span data-stu-id="fe6ae-152">SharePoint/Knowledge admin</span></span> | <span data-ttu-id="fe6ae-153">Administratör för Power-plattformen</span><span class="sxs-lookup"><span data-stu-id="fe6ae-153">Power Platform admin</span></span> | <span data-ttu-id="fe6ae-154">Knowledge Manager</span><span class="sxs-lookup"><span data-stu-id="fe6ae-154">Knowledge manager</span></span> | <span data-ttu-id="fe6ae-155">Modellägare</span><span class="sxs-lookup"><span data-stu-id="fe6ae-155">Model owner</span></span> |
|:-------|:-------|:-------|:-------|
| <span data-ttu-id="fe6ae-156">AAD-roll</span><span class="sxs-lookup"><span data-stu-id="fe6ae-156">AAD role</span></span>| <span data-ttu-id="fe6ae-157">AAD-roll</span><span class="sxs-lookup"><span data-stu-id="fe6ae-157">AAD role</span></span> | <span data-ttu-id="fe6ae-158">AAD-roll</span><span class="sxs-lookup"><span data-stu-id="fe6ae-158">AAD role</span></span> | <span data-ttu-id="fe6ae-159">Mästare</span><span class="sxs-lookup"><span data-stu-id="fe6ae-159">Champions</span></span> |
| <span data-ttu-id="fe6ae-160">Konfigurera formulärbearbetning</span><span class="sxs-lookup"><span data-stu-id="fe6ae-160">Configure form processing</span></span> | <span data-ttu-id="fe6ae-161">Konfigurera common data service environment for form processing</span><span class="sxs-lookup"><span data-stu-id="fe6ae-161">Configure Common data service environment for form processing</span></span> | <span data-ttu-id="fe6ae-162">Samla in användningsfall</span><span class="sxs-lookup"><span data-stu-id="fe6ae-162">Gather use cases</span></span> | <span data-ttu-id="fe6ae-163">Samla in användningsfall för företag</span><span class="sxs-lookup"><span data-stu-id="fe6ae-163">Gather business use cases</span></span> |
| <span data-ttu-id="fe6ae-164">Hantera innehållscenter och behörigheter</span><span class="sxs-lookup"><span data-stu-id="fe6ae-164">Manage content centers and permissions</span></span>| <span data-ttu-id="fe6ae-165">Köpa och tilldela AIB-krediter</span><span class="sxs-lookup"><span data-stu-id="fe6ae-165">Purchase and allocate AIB credits</span></span> | <span data-ttu-id="fe6ae-166">Upprätta metodtips och granska modellanalyser</span><span class="sxs-lookup"><span data-stu-id="fe6ae-166">Establish best practices and review model analytics</span></span> | <span data-ttu-id="fe6ae-167">Skapa och använda modeller</span><span class="sxs-lookup"><span data-stu-id="fe6ae-167">Create and apply models</span></span> |

<span data-ttu-id="fe6ae-168">Knowledge Manager, Business Process Owner och ägare av innehållsmodeller skapar exempelmodeller och är mästare på införandet i organisationen.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-168">Knowledge manager, Business Process Owner and Content model owner create sample models and champion adoption in the organization.</span></span>
<span data-ttu-id="fe6ae-169">Andra som kan vara inblandade: efterlevnadsadministratörer, taxonomihanterare.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-169">Others who may be involved: Compliance admin, Taxonomy managers.</span></span>

<span data-ttu-id="fe6ae-170">Var ska modeller byggas och användas?</span><span class="sxs-lookup"><span data-stu-id="fe6ae-170">Where will they build and apply the models?</span></span> <span data-ttu-id="fe6ae-171">Finns det befintliga processer eller lagringsplatsen som kan förbättras?</span><span class="sxs-lookup"><span data-stu-id="fe6ae-171">Are there existing processes or repositories that could be enhanced?</span></span>

- <span data-ttu-id="fe6ae-172">Formulärbearbetning: Bestäm vilka webbplatser som ska få åtgärden Formulärbearbetning.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-172">Form processing: Decide which sites will get Form processing action.</span></span>
- <span data-ttu-id="fe6ae-173">Dokumentförståelse: Du kan skapa flera innehållscenter för olika affärsområden.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-173">Document understanding: You can create multiple content centers for different business areas.</span></span>

## <a name="strategic-positioning"></a><span data-ttu-id="fe6ae-174">Strategiska positionering</span><span class="sxs-lookup"><span data-stu-id="fe6ae-174">Strategic positioning</span></span>

<span data-ttu-id="fe6ae-175">Arbeta med intressenter för att se till att de är i linje med strategin för att SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-175">Work with stakeholders to make sure they are aligned on the strategy for using SharePoint Syntex.</span></span> <span data-ttu-id="fe6ae-176">Gör efterforskningar och ge följande resurser som hjälp med den här positionen:</span><span class="sxs-lookup"><span data-stu-id="fe6ae-176">Research and provide the following resources to help with this positioning:</span></span>

- <span data-ttu-id="fe6ae-177">Affärsresultat:</span><span class="sxs-lookup"><span data-stu-id="fe6ae-177">Business outcomes:</span></span>
  - <span data-ttu-id="fe6ae-178">Möjliga räkenskapsresultat</span><span class="sxs-lookup"><span data-stu-id="fe6ae-178">Potential fiscal outcomes</span></span>
  - <span data-ttu-id="fe6ae-179">Möjliga smidiga resultat</span><span class="sxs-lookup"><span data-stu-id="fe6ae-179">Potential agility outcomes</span></span>
  - <span data-ttu-id="fe6ae-180">Mall för affärsresultat</span><span class="sxs-lookup"><span data-stu-id="fe6ae-180">Business outcome template</span></span>
- <span data-ttu-id="fe6ae-181">Intressenter/Exec-sponsor, köp/justering</span><span class="sxs-lookup"><span data-stu-id="fe6ae-181">Stakeholders/Exec sponsor buy-in/alignment</span></span>
  - <span data-ttu-id="fe6ae-182">Affärsfalls bildspel</span><span class="sxs-lookup"><span data-stu-id="fe6ae-182">Business case decks</span></span>
  - <span data-ttu-id="fe6ae-183">Finansmodeller</span><span class="sxs-lookup"><span data-stu-id="fe6ae-183">Financial models</span></span>
  - <span data-ttu-id="fe6ae-184">Företagsberedskap – kultur</span><span class="sxs-lookup"><span data-stu-id="fe6ae-184">Company readiness - culture</span></span>

## <a name="identify-stakeholders"></a><span data-ttu-id="fe6ae-185">Identifiera intressenter</span><span class="sxs-lookup"><span data-stu-id="fe6ae-185">Identify stakeholders</span></span>

<span data-ttu-id="fe6ae-186">Identifiera projektets intressenter.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-186">Identify the stakeholders for your project.</span></span>

|<span data-ttu-id="fe6ae-187">Roll</span><span class="sxs-lookup"><span data-stu-id="fe6ae-187">Role</span></span> |<span data-ttu-id="fe6ae-188">Ansvarsområden</span><span class="sxs-lookup"><span data-stu-id="fe6ae-188">Responsibilities</span></span> |<span data-ttu-id="fe6ae-189">Department</span><span class="sxs-lookup"><span data-stu-id="fe6ae-189">Department</span></span> |
|:-------|:-------|:--------|
| <span data-ttu-id="fe6ae-190">Sponsor(er)</span><span class="sxs-lookup"><span data-stu-id="fe6ae-190">Executive sponsor(s)</span></span>   | <span data-ttu-id="fe6ae-191">Kommunicera visioner och värden på hög nivå till företaget</span><span class="sxs-lookup"><span data-stu-id="fe6ae-191">Communicate high-level vision and values to the company</span></span>   |  <span data-ttu-id="fe6ae-192">Ledning</span><span class="sxs-lookup"><span data-stu-id="fe6ae-192">Executive leadership</span></span>   |
| <span data-ttu-id="fe6ae-193">Project eller lead</span><span class="sxs-lookup"><span data-stu-id="fe6ae-193">Project lead(s)</span></span> | <span data-ttu-id="fe6ae-194">Övervaka hela startkörningen och lanseringsprocessen</span><span class="sxs-lookup"><span data-stu-id="fe6ae-194">Oversee the entire launch execution and rollout process</span></span> | <span data-ttu-id="fe6ae-195">Project hantering</span><span class="sxs-lookup"><span data-stu-id="fe6ae-195">Project management</span></span> |
| <span data-ttu-id="fe6ae-196">Kunskapsadministratörer</span><span class="sxs-lookup"><span data-stu-id="fe6ae-196">Knowledge administrators</span></span>| <span data-ttu-id="fe6ae-197">Skapa och hantera innehållscenter</span><span class="sxs-lookup"><span data-stu-id="fe6ae-197">Create and manage the content centers</span></span> | <span data-ttu-id="fe6ae-198">IT eller annan avdelning</span><span class="sxs-lookup"><span data-stu-id="fe6ae-198">IT or other department</span></span>|
| <span data-ttu-id="fe6ae-199">Innehållshanterare och modellägare</span><span class="sxs-lookup"><span data-stu-id="fe6ae-199">Content managers and model owners</span></span>| <span data-ttu-id="fe6ae-200">Samla in användningsfall och skapa och använda modeller</span><span class="sxs-lookup"><span data-stu-id="fe6ae-200">Gather use cases and create and apply models</span></span> | <span data-ttu-id="fe6ae-201">Alla avdelningar</span><span class="sxs-lookup"><span data-stu-id="fe6ae-201">Any department</span></span>|
| <span data-ttu-id="fe6ae-202">Mästare</span><span class="sxs-lookup"><span data-stu-id="fe6ae-202">Champions</span></span> | <span data-ttu-id="fe6ae-203">Hjälpa till att sprida och hantera stötande hantering</span><span class="sxs-lookup"><span data-stu-id="fe6ae-203">Help evangelize and manage objection handling</span></span> | <span data-ttu-id="fe6ae-204">Alla avdelningar (personal)</span><span class="sxs-lookup"><span data-stu-id="fe6ae-204">Any department (staff)</span></span> |
| <span data-ttu-id="fe6ae-205">Innehavaradministratör</span><span class="sxs-lookup"><span data-stu-id="fe6ae-205">Tenant administrator</span></span> | <span data-ttu-id="fe6ae-206">Konfigurera inställningar på klientnivå</span><span class="sxs-lookup"><span data-stu-id="fe6ae-206">Configure tenant-level settings</span></span> | <span data-ttu-id="fe6ae-207">IT-avdelning</span><span class="sxs-lookup"><span data-stu-id="fe6ae-207">IT department</span></span>|
| <span data-ttu-id="fe6ae-208">Power Platform-administratör</span><span class="sxs-lookup"><span data-stu-id="fe6ae-208">Power Platform administrator</span></span>| <span data-ttu-id="fe6ae-209">Konfigurera en vanlig miljö för datatjänster</span><span class="sxs-lookup"><span data-stu-id="fe6ae-209">Configure common data services environment</span></span> | <span data-ttu-id="fe6ae-210">IT-avdelning</span><span class="sxs-lookup"><span data-stu-id="fe6ae-210">IT department</span></span>|

> [!Note]
> <span data-ttu-id="fe6ae-211">Vi rekommenderar att alla de här rollerna har uppfyllts under hela utrullningen, men du kanske upptäcker att du inte behöver dem alla för att komma igång med din identifierade lösning.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-211">Though we recommend having each of these roles fulfilled throughout your rollout, you may find that you don't require them all to get started with your identified solution.</span></span>

## <a name="readiness-checklist"></a><span data-ttu-id="fe6ae-212">Checklista för beredskap</span><span class="sxs-lookup"><span data-stu-id="fe6ae-212">Readiness checklist</span></span>

<span data-ttu-id="fe6ae-213">För att förbereda dig för SharePoint Syntex måste du:</span><span class="sxs-lookup"><span data-stu-id="fe6ae-213">To get ready for implementing SharePoint Syntex, you need to:</span></span>

![Beredskap för innehållsförståelse](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. <span data-ttu-id="fe6ae-215">Planera sluttillståndet</span><span class="sxs-lookup"><span data-stu-id="fe6ae-215">Plan the end state</span></span>
    - <span data-ttu-id="fe6ae-216">Dokument förstå modeller är medel och inte slutet.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-216">Document understanding models are the means, not the end.</span></span>
    - <span data-ttu-id="fe6ae-217">Planera hur du utnyttjar värdet på extraherade metadata med:</span><span class="sxs-lookup"><span data-stu-id="fe6ae-217">Plan for harnessing the value of extracted metadata with:</span></span>
      - <span data-ttu-id="fe6ae-218">Söka</span><span class="sxs-lookup"><span data-stu-id="fe6ae-218">Search</span></span>
      - <span data-ttu-id="fe6ae-219">Filtrera och visa formatering</span><span class="sxs-lookup"><span data-stu-id="fe6ae-219">Filtering and view formatting</span></span>
      - <span data-ttu-id="fe6ae-220">Efterlevnad</span><span class="sxs-lookup"><span data-stu-id="fe6ae-220">Compliance</span></span>
      - <span data-ttu-id="fe6ae-221">Automation</span><span class="sxs-lookup"><span data-stu-id="fe6ae-221">Automation</span></span>
2. <span data-ttu-id="fe6ae-222">Identifiera</span><span class="sxs-lookup"><span data-stu-id="fe6ae-222">Identify</span></span>
    - <span data-ttu-id="fe6ae-223">Förstå befintlig informationsarkitektur och användning av innehållshanteringsfunktion.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-223">Understand existing information architecture and content management feature use.</span></span>
    - <span data-ttu-id="fe6ae-224">Finns det några befintliga innehållstyper som tänkbara modeller?</span><span class="sxs-lookup"><span data-stu-id="fe6ae-224">Are any existing content types good candidates for models?</span></span>
    - <span data-ttu-id="fe6ae-225">Vilka befintliga processer skulle förbättras med metadata?</span><span class="sxs-lookup"><span data-stu-id="fe6ae-225">What existing processes would be improved by metadata?</span></span>
3. <span data-ttu-id="fe6ae-226">Design</span><span class="sxs-lookup"><span data-stu-id="fe6ae-226">Design</span></span>
    - <span data-ttu-id="fe6ae-227">Utforma din metod för informationsarkitektur, hanterade metadata och innehållstyper</span><span class="sxs-lookup"><span data-stu-id="fe6ae-227">Design your approach to information architecture, managed metadata and content types</span></span>
    - <span data-ttu-id="fe6ae-228">Utforma processen för definition, skapande och hantering.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-228">Design the process for definition, creation, management.</span></span>

## <a name="engage-your-organization"></a><span data-ttu-id="fe6ae-229">Engagera organisationen</span><span class="sxs-lookup"><span data-stu-id="fe6ae-229">Engage your organization</span></span>

1. <span data-ttu-id="fe6ae-230">Identifiera innehavarna, bekräfta scenarier och utveckla projektplanen.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-230">Identify stake holders, confirm scenarios, and develop project plan.</span></span>
1. <span data-ttu-id="fe6ae-231">Konfigurera inställningar och använd licenser.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-231">Configure settings and apply licenses.</span></span>
1. <span data-ttu-id="fe6ae-232">Börja informera och utbilda – rekrytera mästare.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-232">Begin awareness and training – Recruit Champions.</span></span>
1. <span data-ttu-id="fe6ae-233">Distribuera stegvis.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-233">Roll out in stages.</span></span>  
1. <span data-ttu-id="fe6ae-234">Samla in feedback och iterera.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-234">Gather feedback and iterate.</span></span>
1. <span data-ttu-id="fe6ae-235">Allt eftersom användningen växer planerar vi för AI Builder-krediter efter behov.</span><span class="sxs-lookup"><span data-stu-id="fe6ae-235">As usage grows plan for any AI Builder credits as needed.</span></span>

## <a name="see-also"></a><span data-ttu-id="fe6ae-236">Se även</span><span class="sxs-lookup"><span data-stu-id="fe6ae-236">See also</span></span>

[<span data-ttu-id="fe6ae-237">Scenarier och användningsfall i SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="fe6ae-237">Scenarios and use cases in SharePoint Syntex</span></span>](adoption-scenarios.md)