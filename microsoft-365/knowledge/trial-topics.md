---
title: Köra en utvärderingsversion av Microsoft Viva Topics
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris; jaeccles
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: ''
search.appverid: ''
localization_priority: Normal
description: Lär dig hur du planerar och kör ett testpilotprogram för Microsoft Viva Topics i organisationen.
ms.openlocfilehash: 128e82e7664a76baa55d37e983319c9f344624fd
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327147"
---
# <a name="run-a-trial-of-microsoft-viva-topics"></a><span data-ttu-id="02bac-103">Köra en utvärderingsversion av Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="02bac-103">Run a trial of Microsoft Viva Topics</span></span>

<span data-ttu-id="02bac-104">I den här artikeln beskrivs hur du set up and run a trial pilot program to deploy Viva Topics to your organization.</span><span class="sxs-lookup"><span data-stu-id="02bac-104">This article describes how to set up and run a trial pilot program to deploy Viva Topics to your organization.</span></span> <span data-ttu-id="02bac-105">Den här artikeln rekommenderar även metodtips för utvärderingsversionen.</span><span class="sxs-lookup"><span data-stu-id="02bac-105">This article also recommends best practices for the trial.</span></span>

## <a name="sign-up-for-a-trial"></a><span data-ttu-id="02bac-106">Registrera dig för en utvärderingsversion</span><span class="sxs-lookup"><span data-stu-id="02bac-106">Sign up for a trial</span></span>

<span data-ttu-id="02bac-107">Försök är offentligt tillgängliga från någon av följande källor.</span><span class="sxs-lookup"><span data-stu-id="02bac-107">Trials are publicly available from one of the following sources.</span></span> <span data-ttu-id="02bac-108">Utvärderingsversioner ger 25 användare tillgång till Viva Topics i 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="02bac-108">These trials offer 25 users access to Viva Topics for 30 days.</span></span>

- <span data-ttu-id="02bac-109">Produktsidan [Viva Topics](https://www.microsoft.com/microsoft-viva/topics?activetab=pivot:overviewtab)</span><span class="sxs-lookup"><span data-stu-id="02bac-109">The [Viva Topics product page](https://www.microsoft.com/microsoft-viva/topics?activetab=pivot:overviewtab)</span></span>

- <span data-ttu-id="02bac-110">Administrationscenter för Microsoft 365 [](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="02bac-110">The [Microsoft 365 admin center](https://admin.microsoft.com)</span></span>
    1.  <span data-ttu-id="02bac-111">Logga in på [Administrationscenter för Microsoft 365](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="02bac-111">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
    2.  <span data-ttu-id="02bac-112">Gå till **Tjänster för**  >  **faktureringsköp.**</span><span class="sxs-lookup"><span data-stu-id="02bac-112">Go to **Billing** > **Purchase Services**.</span></span>
    3.  <span data-ttu-id="02bac-113">Rulla ned till **avsnittet** Tillägg.</span><span class="sxs-lookup"><span data-stu-id="02bac-113">Scroll down to the **Add-Ons** section.</span></span>
    4.  <span data-ttu-id="02bac-114">På panelen **Ämnesupplevelser** väljer du **Detaljer**.</span><span class="sxs-lookup"><span data-stu-id="02bac-114">On the **Topic Experiences** tile, select **Details**.</span></span>
    5.  <span data-ttu-id="02bac-115">Välj **Hämta kostnadsfri utvärderingsversion**.</span><span class="sxs-lookup"><span data-stu-id="02bac-115">Select **Get free trial**.</span></span>
    6.  <span data-ttu-id="02bac-116">Bekräfta utvärderingsversionen genom att följa anvisningarna i guiden.</span><span class="sxs-lookup"><span data-stu-id="02bac-116">Follow the remaining wizard steps to confirm the trial.</span></span>

<span data-ttu-id="02bac-117">Du måste vara global Microsoft 365 eller faktureringsadministratör för att aktivera en utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="02bac-117">You must be a Microsoft 365 global administrator or billing administrator to activate a trial.</span></span>

> [!NOTE]
> <span data-ttu-id="02bac-118">Offentliga utvärderingsversioner kan bara läggas till en gång för Microsoft 365 klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="02bac-118">Public trials can only be added once for each Microsoft 365 tenant.</span></span>

### <a name="who-should-be-involved-in-a-trial"></a><span data-ttu-id="02bac-119">Vem bör vara involverad i en utvärderingsversion</span><span class="sxs-lookup"><span data-stu-id="02bac-119">Who should be involved in a trial</span></span>

|<span data-ttu-id="02bac-120">Roll</span><span class="sxs-lookup"><span data-stu-id="02bac-120">Role</span></span>  |<span data-ttu-id="02bac-121">Aktivitet</span><span class="sxs-lookup"><span data-stu-id="02bac-121">Activity</span></span>  |
|---------|---------|
|<span data-ttu-id="02bac-122">Microsoft 365 global administratör eller faktureringsadministratör</span><span class="sxs-lookup"><span data-stu-id="02bac-122">Microsoft 365 global admin or billing admin</span></span>  |   <span data-ttu-id="02bac-123">Aktivera utvärderingsversionen och tilldela licenser</span><span class="sxs-lookup"><span data-stu-id="02bac-123">Activate the trial and assign licenses</span></span>      |
|<span data-ttu-id="02bac-124">Microsoft 365 global administratör SharePoint administratör</span><span class="sxs-lookup"><span data-stu-id="02bac-124">Microsoft 365 global admin or SharePoint admin</span></span>    |       <span data-ttu-id="02bac-125">Konfigurera Viva Ämnen och skapa ämnescentra</span><span class="sxs-lookup"><span data-stu-id="02bac-125">Configure  Viva Topics and create topic centers</span></span>  |
|<span data-ttu-id="02bac-126">Företagsanvändare</span><span class="sxs-lookup"><span data-stu-id="02bac-126">Business user</span></span>     |   <span data-ttu-id="02bac-127">Utföra knowledge manager, ämnesdeltagare och ämneskonsumentroller</span><span class="sxs-lookup"><span data-stu-id="02bac-127">Perform knowledge manager, topic contributor, and topic consumer roles</span></span>      |

### <a name="before-you-activate-a-trial"></a><span data-ttu-id="02bac-128">Innan du aktiverar en utvärderingsversion</span><span class="sxs-lookup"><span data-stu-id="02bac-128">Before you activate a trial</span></span>

<span data-ttu-id="02bac-129">Det är viktigt att planera för en effektiv utvärderingsversion av Viva Topics.</span><span class="sxs-lookup"><span data-stu-id="02bac-129">Planning is essential for an effective trial of Viva Topics.</span></span> <span data-ttu-id="02bac-130">Utvärderingsperioden är begränsad och måste omfatta upptäckt av ämnen och utforska ämneskvalitet, hantering och slutanvändarupplevelser.</span><span class="sxs-lookup"><span data-stu-id="02bac-130">The trial period is limited and must include topic discovery and exploring topic quality, management, and end-user experiences.</span></span>

#### <a name="discovery"></a><span data-ttu-id="02bac-131">Upptäckt</span><span class="sxs-lookup"><span data-stu-id="02bac-131">Discovery</span></span>

<span data-ttu-id="02bac-132">Det finns två strategialternativ på hög nivå för konfiguration av ämnesidentifieringen under en utvärderingsversion:</span><span class="sxs-lookup"><span data-stu-id="02bac-132">There are two high-level strategy options for configuration of topic discovery during a trial:</span></span>

- <span data-ttu-id="02bac-133">Indexera allt eller större delen av ditt SharePoint Online-innehåll.</span><span class="sxs-lookup"><span data-stu-id="02bac-133">Index all or most of your SharePoint Online content.</span></span>
   - <span data-ttu-id="02bac-134">Stora klientorganisationar kan ta upp till två veckor att helt indexera.</span><span class="sxs-lookup"><span data-stu-id="02bac-134">Large tenants can take up to two weeks to fully index.</span></span> <span data-ttu-id="02bac-135">Även om ämnen genereras stegvis under hela den här perioden kan fullständig indexering ta upp till hälften av utvärderingsperioden.</span><span class="sxs-lookup"><span data-stu-id="02bac-135">While topics will be generated incrementally throughout this period, full indexing could consume up to half the trial period.</span></span>
   - <span data-ttu-id="02bac-136">För klientorganisationar med en stor mängd data kan det här alternativet producera ett mycket stort antal ämnen, kanske tusentals.</span><span class="sxs-lookup"><span data-stu-id="02bac-136">For tenants with a significant volume of data, this option can produce a very large number of topics, perhaps tens of thousands.</span></span>

- <span data-ttu-id="02bac-137">Identifiera en delmängd av dina SharePoint webbplatser för indexering.</span><span class="sxs-lookup"><span data-stu-id="02bac-137">Identify a subset of your SharePoint sites for indexing.</span></span>

<span data-ttu-id="02bac-138">Dessa strategier ger en balans mellan följande två faktorer:</span><span class="sxs-lookup"><span data-stu-id="02bac-138">The choice of these strategies is a balance of the following two factors:</span></span>

- <span data-ttu-id="02bac-139">Ha tillräckligt med data för att skapa meningsfulla ämnen.</span><span class="sxs-lookup"><span data-stu-id="02bac-139">Having enough data to generate meaningful topics.</span></span> <span data-ttu-id="02bac-140">AI i Viva-ämnen anpassas för att fungera med stora datamängder, helst sådana som har fler än 10 000 dokument.</span><span class="sxs-lookup"><span data-stu-id="02bac-140">The AI in Viva Topics is tuned to work on large datasets, ideally ones that have more than 10,000 documents.</span></span>
- <span data-ttu-id="02bac-141">Det är överväldigande att inte generera så många ämnen under utvärderingsperioden som utvärderar dem under den tillgängliga tidsperioden.</span><span class="sxs-lookup"><span data-stu-id="02bac-141">Not generating so many topics during the trial period that evaluating them during the available time period is overwhelming.</span></span>

<span data-ttu-id="02bac-142">För de flesta organisationer ger den andra strategin bästa resultat.</span><span class="sxs-lookup"><span data-stu-id="02bac-142">For most organizations, the second strategy produces the best outcome.</span></span>

> [!NOTE]
> <span data-ttu-id="02bac-143">På grund av antalet dokument som krävs av AI:n rekommenderar vi att du kör Viva Topics-försök på en produktionsklientorganisation.</span><span class="sxs-lookup"><span data-stu-id="02bac-143">Due to the number of documents required by the AI, we recommend that you run Viva Topics trials on a production tenant.</span></span> <span data-ttu-id="02bac-144">Det påverkar inte klientorganisationens prestanda under den här perioden.</span><span class="sxs-lookup"><span data-stu-id="02bac-144">There’s no impact on the performance of the tenant during this period.</span></span> <span data-ttu-id="02bac-145">Endast användare som har en utvärderingslicens kan komma åt användarupplevelsen i Viva Topics.</span><span class="sxs-lookup"><span data-stu-id="02bac-145">Only users who have a trial license can access Viva Topics user experiences.</span></span>

#### <a name="roles"></a><span data-ttu-id="02bac-146">Roller</span><span class="sxs-lookup"><span data-stu-id="02bac-146">Roles</span></span>

<span data-ttu-id="02bac-147">Under utvärderingsperioden finns det tre roller som måste vara aktiva, vilket beskrivs i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="02bac-147">During the trial, there are three roles that must be active, which are described in the following table.</span></span>

|<span data-ttu-id="02bac-148">Roll</span><span class="sxs-lookup"><span data-stu-id="02bac-148">Role</span></span>  |<span data-ttu-id="02bac-149">Aktivitet</span><span class="sxs-lookup"><span data-stu-id="02bac-149">Activity</span></span>  |
|---------|---------|
|<span data-ttu-id="02bac-150">Knowledge Manager</span><span class="sxs-lookup"><span data-stu-id="02bac-150">Knowledge manager</span></span>     |   <span data-ttu-id="02bac-151">Styra livscykelfasen för ämnen. bekräfta och ta bort ämnen; agera som community-hanterare för ämnesdeltagare</span><span class="sxs-lookup"><span data-stu-id="02bac-151">Control the lifecycle stages of topics; confirm and remove topics; act as a community manager for topic contributors</span></span>      |
|<span data-ttu-id="02bac-152">Ämnesdeltagare</span><span class="sxs-lookup"><span data-stu-id="02bac-152">Topic contributor</span></span>    |      <span data-ttu-id="02bac-153">Ämnesexperter som kan:</span><span class="sxs-lookup"><span data-stu-id="02bac-153">Content subject matter experts, who can:</span></span><br> <span data-ttu-id="02bac-154">Granska ämnen för att utvärdera kvaliteten på AI-definierat innehåll</span><span class="sxs-lookup"><span data-stu-id="02bac-154">Review topics to evaluate the quality of AI-defined content</span></span><br><span data-ttu-id="02bac-155">Curate discovered topics with additional content</span><span class="sxs-lookup"><span data-stu-id="02bac-155">Curate discovered topics with additional content</span></span><br><span data-ttu-id="02bac-156">Skapa ytterligare ämnen som inte identifierats av AI</span><span class="sxs-lookup"><span data-stu-id="02bac-156">Create additional topics that weren’t discovered by AI</span></span>   |
|<span data-ttu-id="02bac-157">Ämneskonsument</span><span class="sxs-lookup"><span data-stu-id="02bac-157">Topic consumer</span></span>    |     <span data-ttu-id="02bac-158">Använda ämnen genom att markera och söka på sidor</span><span class="sxs-lookup"><span data-stu-id="02bac-158">Consume topics through page highlights and search</span></span><br><span data-ttu-id="02bac-159">Ge feedback om värdet för de ämnen som presenteras</span><span class="sxs-lookup"><span data-stu-id="02bac-159">Provide feedback on the value of the topics presented</span></span>    |

#### <a name="expected-topics"></a><span data-ttu-id="02bac-160">Förväntade ämnen</span><span class="sxs-lookup"><span data-stu-id="02bac-160">Expected topics</span></span>

<span data-ttu-id="02bac-161">Det kan vara bra att dokumentera de ämnen som du förväntar dig att genereras av AI, även om det bara baseras på antaganden.</span><span class="sxs-lookup"><span data-stu-id="02bac-161">It can be useful to document the topics you expect to be generated by the AI, even if this is based only on assumptions.</span></span> <span data-ttu-id="02bac-162">Den här uppgiften slutförs enkelt när du indexerar en definierad delmängd av dina SharePoint webbplatser som företag kan enkelt identifiera sig för.</span><span class="sxs-lookup"><span data-stu-id="02bac-162">This task is most easily completed when you index a defined subset of your SharePoint sites for which SMEs can be easily identified.</span></span>

<span data-ttu-id="02bac-163">Om du har en dokumenterad lista kan du:</span><span class="sxs-lookup"><span data-stu-id="02bac-163">Having a documented list will help you to:</span></span>

- <span data-ttu-id="02bac-164">Granska listan med AI-genererade ämnen, som kan vara större än du förväntar dig.</span><span class="sxs-lookup"><span data-stu-id="02bac-164">Review the list of AI-generated topics, which might be larger than you expect.</span></span>
- <span data-ttu-id="02bac-165">Ta del av de ämnen som du kan behöva skapa manuellt eller som är prioriteringar för läroplanen.</span><span class="sxs-lookup"><span data-stu-id="02bac-165">Know the topics you might need to manually create or that are priorities for curation.</span></span>

<span data-ttu-id="02bac-166">Det finns alltid ett behov av en blandning av AI-definierade ämnen och ämnen som skapats av människor i en lyckad distribution eller utvärdering av Viva-ämnen.</span><span class="sxs-lookup"><span data-stu-id="02bac-166">There will always be a need for a mixture of AI-defined and human-created topics in a successful deployment or trial of Viva Topics.</span></span>

## <a name="activate-a-trial"></a><span data-ttu-id="02bac-167">Aktivera en utvärderingsversion</span><span class="sxs-lookup"><span data-stu-id="02bac-167">Activate a trial</span></span>

<span data-ttu-id="02bac-168">När du påbörjar en utvärderingsversion måste du:</span><span class="sxs-lookup"><span data-stu-id="02bac-168">When you initiate a trial, you need to:</span></span>

- <span data-ttu-id="02bac-169">Tilldela licenser till relevanta användare.</span><span class="sxs-lookup"><span data-stu-id="02bac-169">Assign licenses to the relevant users.</span></span>
- <span data-ttu-id="02bac-170">Utför [ytterligare konfiguration av](set-up-topic-experiences.md) Viva Ämnen.</span><span class="sxs-lookup"><span data-stu-id="02bac-170">Perform [additional setup](set-up-topic-experiences.md) of Viva Topics.</span></span>

<span data-ttu-id="02bac-171">När utvärderingsversionen aktiveras påbörjas identifieringsprocessen för ämnen.</span><span class="sxs-lookup"><span data-stu-id="02bac-171">When the trial is activated, the topic discovery process begins.</span></span>

## <a name="during-a-trial"></a><span data-ttu-id="02bac-172">Under en utvärderingsversion</span><span class="sxs-lookup"><span data-stu-id="02bac-172">During a trial</span></span>

<span data-ttu-id="02bac-173">Utvärderingsperioden ska användas för att utvärdera följande komponenter i Viva Topics:</span><span class="sxs-lookup"><span data-stu-id="02bac-173">The trial period should be used to evaluate the following components of Viva Topics:</span></span>

- <span data-ttu-id="02bac-174">AI-föreslagna ämnen och ämnesinnehåll</span><span class="sxs-lookup"><span data-stu-id="02bac-174">The AI-suggested topics and topic content</span></span>
- <span data-ttu-id="02bac-175">Slutanvändarupplevelserna, att visa ämneskort på moderna SharePoint sidor och i Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="02bac-175">The end-user experiences, surfacing topic cards on modern SharePoint pages and in Microsoft Search</span></span>

<span data-ttu-id="02bac-176">Tänk på följande faktorer:</span><span class="sxs-lookup"><span data-stu-id="02bac-176">Consider these factors:</span></span>

- <span data-ttu-id="02bac-177">För att Viva Topics ska kunna ge maximalt värde måste innehållet i ämnena vara en kombination av AI-definierat innehåll och humant innehåll.</span><span class="sxs-lookup"><span data-stu-id="02bac-177">For Viva Topics to deliver the maximum value, the content in topics needs to be a combination of AI-defined content and human-curated content.</span></span>
- <span data-ttu-id="02bac-178">Alla användarupplevelser "behörighets trimmas" (inklusive vyn knowledge manager på sidan **Hantera ämnen).**</span><span class="sxs-lookup"><span data-stu-id="02bac-178">All user experiences are “permission trimmed” (including the knowledge manager’s view on the **Manage topics** page).</span></span> <span data-ttu-id="02bac-179">Användare ser bara ett ämne om de har behörighet att visa en del av de resurser som användes för att generera ämnet.</span><span class="sxs-lookup"><span data-stu-id="02bac-179">Users will only see a topic if they have permissions to view some of the resources that were used to generate the topic.</span></span> <span data-ttu-id="02bac-180">Det innebär att olika användare kan se olika innehåll på samma ämnessida.</span><span class="sxs-lookup"><span data-stu-id="02bac-180">This means that different users might see different content on the same topic page.</span></span>
- <span data-ttu-id="02bac-181">Användare kan se flera avsnitt som har samma namn på **sidan Hantera ämnen.**</span><span class="sxs-lookup"><span data-stu-id="02bac-181">Users might see multiple topics that have the same name in the **Manage topics** page.</span></span> <span data-ttu-id="02bac-182">De här avsnitten är inte nödvändigtvis dubbletter, men kan vara på grund av en term som används i flera sammanhang i dina data, till exempel ett projektkodsnamn som används av två olika projekt.</span><span class="sxs-lookup"><span data-stu-id="02bac-182">These topics aren't necessarily duplicates but might be because of a single term that’s used in multiple contexts in the data, such as a project code name that’s used by two distinct projects.</span></span>

## <a name="after-a-trial"></a><span data-ttu-id="02bac-183">Efter en utvärderingsversion</span><span class="sxs-lookup"><span data-stu-id="02bac-183">After a trial</span></span>

<span data-ttu-id="02bac-184">Baserat på resultatet av utvärderingsversionen kan du bestämma om du vill fortsätta med produktionsanvändningen av Viva Topics.</span><span class="sxs-lookup"><span data-stu-id="02bac-184">Based on the outcome of the trial, you can decide whether to proceed to production use of Viva Topics.</span></span>

### <a name="proceed-to-production-use"></a><span data-ttu-id="02bac-185">Fortsätt till produktionsanvändning</span><span class="sxs-lookup"><span data-stu-id="02bac-185">Proceed to production use</span></span>

<span data-ttu-id="02bac-186">För att säkerställa kontinuiteten i tjänsten måste du köpa antalet licenser som krävs och tilldela licenserna till användarna.</span><span class="sxs-lookup"><span data-stu-id="02bac-186">To ensure continuity of service, you must purchase the required number of licenses and assign those licenses to users.</span></span> <span data-ttu-id="02bac-187">Utvärderingsanvändare som inte har en fullständig licens i slutet av utvärderingsperioden kommer inte att kunna komma åt Viva Topics-upplevelserna.</span><span class="sxs-lookup"><span data-stu-id="02bac-187">Trial users who don’t have a full license at the end of the trial period won’t be able to access any Viva Topics experiences.</span></span>

### <a name="dont-proceed-to-production-use"></a><span data-ttu-id="02bac-188">Fortsätt inte till produktionsanvändning</span><span class="sxs-lookup"><span data-stu-id="02bac-188">Don’t proceed to production use</span></span>

<span data-ttu-id="02bac-189">Om du inte köper licenser efter utvärderingsversionen:</span><span class="sxs-lookup"><span data-stu-id="02bac-189">If you don’t purchase licenses following the trial:</span></span>

- <span data-ttu-id="02bac-190">Ämnesidentifieringen avbryts.</span><span class="sxs-lookup"><span data-stu-id="02bac-190">Topic discovery will stop.</span></span>
- <span data-ttu-id="02bac-191">Användarna kommer inte längre att se höjdpunkter eller kort för ämnen.</span><span class="sxs-lookup"><span data-stu-id="02bac-191">Users will no longer see topic highlights or cards.</span></span>
- <span data-ttu-id="02bac-192">Ämnescentret tas inte bort, men de föreslagna ämnena och hantera ämnen är inte tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="02bac-192">The topic center won’t be deleted, but the suggested topics and manage topics experiences won’t be available.</span></span>
- <span data-ttu-id="02bac-193">Alla AI-definierade ämnen går förlorade.</span><span class="sxs-lookup"><span data-stu-id="02bac-193">Any AI-defined topics will be lost.</span></span>
- <span data-ttu-id="02bac-194">Ämnen som har redigerats av en ämnesdeltagare finns kvar i biblioteket med ämnescentersidor.</span><span class="sxs-lookup"><span data-stu-id="02bac-194">Topics that have been edited by a topic contributor will remain in the topic center pages library.</span></span> <span data-ttu-id="02bac-195">Endast manuellt tillhandahållet innehåll kommer att finnas kvar på dessa sidor, inte något AI-föreslaget innehåll.</span><span class="sxs-lookup"><span data-stu-id="02bac-195">Only the manually provided content will remain on these pages, not any AI-suggested content.</span></span>

## <a name="see-also"></a><span data-ttu-id="02bac-196">Se även</span><span class="sxs-lookup"><span data-stu-id="02bac-196">See also</span></span>

[<span data-ttu-id="02bac-197">Kom igång med införandet av Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="02bac-197">Get started driving adoption of Microsoft Viva Topics</span></span>](topics-adoption-getstarted.md)

