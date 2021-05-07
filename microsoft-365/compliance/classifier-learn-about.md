---
title: Mer information om utbildningsbara klassificerare
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: En Microsoft 365 utbildare är ett verktyg som du kan träna för att identifiera olika typer av innehåll genom att ge den positiva och negativa prover att titta på. När klassificeraren har utbildning kan du bekräfta att dess resultat är korrekta. Sedan använder du det för att söka igenom organisationens innehåll och klassificera det för att tillämpa bevarande- eller känslighetsetiketter eller inkludera det i DLP (data loss prevention) eller kvarhållningsprinciper.
ms.openlocfilehash: 1881e4de87fd41f21bb1f2236d46391b3a1ed785
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52162980"
---
# <a name="learn-about-trainable-classifiers"></a><span data-ttu-id="a654d-105">Mer information om utbildningsbara klassificerare</span><span class="sxs-lookup"><span data-stu-id="a654d-105">Learn about trainable classifiers</span></span>

<span data-ttu-id="a654d-106">Att klassificera och märka innehåll så att det kan skyddas och hanteras korrekt är startpunkten för informationsskyddsgrenen.</span><span class="sxs-lookup"><span data-stu-id="a654d-106">Classifying and labeling content so it can be protected and handled properly is the starting place for the information protection discipline.</span></span> <span data-ttu-id="a654d-107">Microsoft 365 finns tre sätt att klassificera innehåll.</span><span class="sxs-lookup"><span data-stu-id="a654d-107">Microsoft 365 has three ways to classify content.</span></span>

## <a name="manually"></a><span data-ttu-id="a654d-108">Manuellt</span><span class="sxs-lookup"><span data-stu-id="a654d-108">Manually</span></span>

<span data-ttu-id="a654d-109">Den här metoden kräver en mänsklig bedömning och åtgärd.</span><span class="sxs-lookup"><span data-stu-id="a654d-109">This method requires human judgment and action.</span></span> <span data-ttu-id="a654d-110">En administratör kan antingen använda befintliga etiketter och typer av känslig information eller skapa egna och sedan publicera dem.</span><span class="sxs-lookup"><span data-stu-id="a654d-110">An admin may either use the pre-existing labels and sensitive information types or create their own and then publish them.</span></span> <span data-ttu-id="a654d-111">Användare och administratörer tillämpar dem på innehåll när de stöter på det.</span><span class="sxs-lookup"><span data-stu-id="a654d-111">Users and admins apply them to content as they encounter it.</span></span> <span data-ttu-id="a654d-112">Sedan kan du skydda innehållet och hantera dess disposition.</span><span class="sxs-lookup"><span data-stu-id="a654d-112">You can then protect the content and manage its disposition.</span></span>

## <a name="automated-pattern-matching"></a><span data-ttu-id="a654d-113">Automatiserad mönstermatchning</span><span class="sxs-lookup"><span data-stu-id="a654d-113">Automated pattern matching</span></span>

<span data-ttu-id="a654d-114">Den här kategori av klassificeringsmetoder omfattar att söka efter innehåll genom:</span><span class="sxs-lookup"><span data-stu-id="a654d-114">This category of classification mechanisms include finding content by:</span></span>

- <span data-ttu-id="a654d-115">Nyckelord eller metadatavärden (frågespråk för nyckelord).</span><span class="sxs-lookup"><span data-stu-id="a654d-115">Keywords or metadata values (keyword query language).</span></span>
- <span data-ttu-id="a654d-116">Använda tidigare identifierade mönster för känslig information som personnummer, kreditkortsnummer och bankkontonummer (definitioner av [typ av känslig information).](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="a654d-116">Using previously identified patterns of sensitive information like social security, credit card or bank account numbers [(Sensitive information type entity definitions)](sensitive-information-type-entity-definitions.md).</span></span>
- <span data-ttu-id="a654d-117">Känna igen ett objekt eftersom det är en variant på en mall [(fingerutskrift av dokument)](document-fingerprinting.md).</span><span class="sxs-lookup"><span data-stu-id="a654d-117">Recognizing an item because it's a variation on a template [(document finger printing)](document-fingerprinting.md).</span></span>
- <span data-ttu-id="a654d-118">Använda närvaro av exakta strängar [(exakta datamatchningar).](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)</span><span class="sxs-lookup"><span data-stu-id="a654d-118">Using the presence of exact strings [(exact data match)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

<span data-ttu-id="a654d-119">Känslighets- och bevarandeetiketter kan sedan tillämpas automatiskt för att göra innehållet tillgängligt för användning i Läs mer om skydd mot [dataförlust](dlp-learn-about-dlp.md)) och tillämpa automatiskt [bevarandeprinciper för bevarandeetiketter.](apply-retention-labels-automatically.md)</span><span class="sxs-lookup"><span data-stu-id="a654d-119">Sensitivity and retention labels can then be automatically applied to make the content available for use in [Learn about data loss prevention](dlp-learn-about-dlp.md)) and [auto-apply polices for retention labels](apply-retention-labels-automatically.md).</span></span>

## <a name="classifiers"></a><span data-ttu-id="a654d-120">Klassificerare</span><span class="sxs-lookup"><span data-stu-id="a654d-120">Classifiers</span></span>

<span data-ttu-id="a654d-121">Den här klassificeringsmetoden är särskilt väl lämpad för innehåll som inte lätt kan identifieras med de manuella eller automatiserade mönstermatchningsmetoderna.</span><span class="sxs-lookup"><span data-stu-id="a654d-121">This classification method is particularly well suited to content that isn't easily identified by either the manual or automated pattern matching methods.</span></span> <span data-ttu-id="a654d-122">Den här klassificeringsmetoden handlar mer om att utbilda en klassificerare att identifiera ett objekt baserat på vad objektet är, inte efter element som finns i objektet (mönstermatchning).</span><span class="sxs-lookup"><span data-stu-id="a654d-122">This method of classification is more about training a classifier to identify an item based on what the item is, not by elements that are in the item (pattern matching).</span></span> <span data-ttu-id="a654d-123">En klassificerare lär sig att identifiera en typ av innehåll genom att titta på hundratals exempel på innehåll som du är intresserad av att klassificera.</span><span class="sxs-lookup"><span data-stu-id="a654d-123">A classifier learns how to identify a type of content by looking at hundreds of examples of the content you're interested in classifying.</span></span> <span data-ttu-id="a654d-124">Du börjar med att mata in exempel som definitivt ligger i kategorin.</span><span class="sxs-lookup"><span data-stu-id="a654d-124">You start by feeding it examples that are definitely in the category.</span></span> <span data-ttu-id="a654d-125">När de har bearbetars testar du det genom att ge det en blandning av både matchande och icke-matchande exempel.</span><span class="sxs-lookup"><span data-stu-id="a654d-125">Once it processes those, you test it by giving it a mix of both matching and non-matching examples.</span></span> <span data-ttu-id="a654d-126">Klassificeraren gör sedan prognoser om huruvida ett visst objekt faller inom den kategori som du skapar.</span><span class="sxs-lookup"><span data-stu-id="a654d-126">The classifier then makes predictions as to whether any given item falls into the category you're building.</span></span> <span data-ttu-id="a654d-127">Sedan bekräftar du resultaten, sorterar sant positiva tal, sant negativa, falskt negativa och falskt negativa för att öka noggrannheten i dess prognoser.</span><span class="sxs-lookup"><span data-stu-id="a654d-127">You then confirm its results, sorting out the true positives, true negatives, false positives, and false negatives to help increase the accuracy of its predictions.</span></span> 

<span data-ttu-id="a654d-128">När du publicerar klassificeraren sorteras objekten på platser som SharePoint Online, Exchange och OneDrive, och klassificerar innehållet.</span><span class="sxs-lookup"><span data-stu-id="a654d-128">When you publish the classifier, it sorts through items in locations like SharePoint Online, Exchange, and OneDrive, and classifies the content.</span></span> <span data-ttu-id="a654d-129">När du har publicerat klassificeraren kan du fortsätta att utbilda den med hjälp av en feedbackprocess som liknar den första utbildningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="a654d-129">After you publish the classifier, you can continue to train it using a feedback process that is similar to the initial training process.</span></span>

### <a name="where-you-can-use-trainable-classifiers"></a><span data-ttu-id="a654d-130">Här kan du använda utbildande klassificerare</span><span class="sxs-lookup"><span data-stu-id="a654d-130">Where you can use trainable classifiers</span></span>
<span data-ttu-id="a654d-131">Både inbyggda klassificerare och utbildare finns tillgängliga som ett villkor för [Office automatisk](apply-sensitivity-label-automatically.md)etiketter med känslighetsetiketter [,](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) tillämpa bevarandeprincip automatiskt baserat på ett villkor och i [kommunikationsefterlevnad.](communication-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="a654d-131">Both built-in classifiers and trainable classifiers are available as a condition for [Office autolabeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [communication compliance](communication-compliance.md).</span></span> 

<span data-ttu-id="a654d-132">Känslighetsetiketter kan använda klassificerare som villkor, se [Använda en känslighetsetikett på innehållet automatiskt.](apply-sensitivity-label-automatically.md)</span><span class="sxs-lookup"><span data-stu-id="a654d-132">Sensitivity labels can use classifiers as conditions, see [Apply a sensitivity label to content automatically](apply-sensitivity-label-automatically.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a654d-133">Klassificerare fungerar bara med objekt som inte är krypterade och är på engelska.</span><span class="sxs-lookup"><span data-stu-id="a654d-133">Classifiers only work with items that are not encrypted and are in English.</span></span>

## <a name="types-of-classifiers"></a><span data-ttu-id="a654d-134">Typer av klassificerare</span><span class="sxs-lookup"><span data-stu-id="a654d-134">Types of classifiers</span></span>

- <span data-ttu-id="a654d-135">**förskapade klassificerare** – Microsoft har skapat och i förväg utbildat ett antal klassificerare som du kan börja använda utan att ha utbildat dem.</span><span class="sxs-lookup"><span data-stu-id="a654d-135">**pre-trained classifiers** - Microsoft has created and pre-trained a number of classifiers that you can start using without training them.</span></span> <span data-ttu-id="a654d-136">De här klassificerarna visas med statusen `Ready to use` för .</span><span class="sxs-lookup"><span data-stu-id="a654d-136">These classifiers will appear with the status of `Ready to use`.</span></span>
- <span data-ttu-id="a654d-137">**Anpassade klassificerare** – Om du har klassificeringsbehov som omfattar mer än vad de i förväg utbildade klassificerarna omfattar kan du skapa och utbilda egna klassificerare.</span><span class="sxs-lookup"><span data-stu-id="a654d-137">**custom classifiers** - If you have classification needs that extend beyond what the pre-trained classifiers cover, you can create and train your own classifiers.</span></span>

### <a name="pre-trained-classifiers"></a><span data-ttu-id="a654d-138">Förbaserade klassificerare</span><span class="sxs-lookup"><span data-stu-id="a654d-138">Pre-trained classifiers</span></span>

<span data-ttu-id="a654d-139">Microsoft 365 levereras med fem försorterade klassificerare:</span><span class="sxs-lookup"><span data-stu-id="a654d-139">Microsoft 365 comes with five pre-trained classifiers:</span></span>

> [!CAUTION]
> <span data-ttu-id="a654d-140">Vi använder inte längre  den förinlärde klassificeraren för anstötligt språk eftersom det har ökat ett stort antal falska positiva resultat.</span><span class="sxs-lookup"><span data-stu-id="a654d-140">We are deprecating the **Offensive Language** pre-trained classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="a654d-141">Använd den inte och om du använder den just nu bör du flytta bort dina affärsprocesser från den.</span><span class="sxs-lookup"><span data-stu-id="a654d-141">Don't use it and if you are currently using it, you should move your business processes off of it.</span></span> <span data-ttu-id="a654d-142">Vi rekommenderar att du i stället **använder** de förinpassade klassarna **Threat** , **Svoritet** och trakasserier.</span><span class="sxs-lookup"><span data-stu-id="a654d-142">We recommend using the **Threat**, **Profanity**, and **Harassment** pre-trained classifiers instead.</span></span>

- <span data-ttu-id="a654d-143">**Meritförteckningar:** identifierar objekt som är textbaserade konton för en sökandes personliga, utbildningsrelaterade, kvalifikationer, yrkeserfarenhet och annan personlig information</span><span class="sxs-lookup"><span data-stu-id="a654d-143">**Resumes**: detects items that are textual accounts of an applicant's personal, educational, professional qualifications, work experience, and other personally identifying information</span></span>
- <span data-ttu-id="a654d-144">**Källkod:** identifierar objekt som innehåller en uppsättning instruktioner och uttryck som skrivs på de 25 översta använda datorprogrammeringsspråken på GitHub</span><span class="sxs-lookup"><span data-stu-id="a654d-144">**Source Code**: detects items that contain a set of instructions and statements written in the top 25 used computer programming languages on GitHub</span></span>
    - <span data-ttu-id="a654d-145">ActionScript</span><span class="sxs-lookup"><span data-stu-id="a654d-145">ActionScript</span></span>
    - <span data-ttu-id="a654d-146">C</span><span class="sxs-lookup"><span data-stu-id="a654d-146">C</span></span>
    - <span data-ttu-id="a654d-147">C #</span><span class="sxs-lookup"><span data-stu-id="a654d-147">C#</span></span>
    - <span data-ttu-id="a654d-148">C++</span><span class="sxs-lookup"><span data-stu-id="a654d-148">C++</span></span>
    - <span data-ttu-id="a654d-149">Clojure</span><span class="sxs-lookup"><span data-stu-id="a654d-149">Clojure</span></span>
    - <span data-ttu-id="a654d-150">CoffeeScript</span><span class="sxs-lookup"><span data-stu-id="a654d-150">CoffeeScript</span></span>
    - <span data-ttu-id="a654d-151">Gå till</span><span class="sxs-lookup"><span data-stu-id="a654d-151">Go</span></span>
    - <span data-ttu-id="a654d-152">Haskell</span><span class="sxs-lookup"><span data-stu-id="a654d-152">Haskell</span></span>
    - <span data-ttu-id="a654d-153">Java</span><span class="sxs-lookup"><span data-stu-id="a654d-153">Java</span></span>
    - <span data-ttu-id="a654d-154">JavaScript</span><span class="sxs-lookup"><span data-stu-id="a654d-154">JavaScript</span></span>
    - <span data-ttu-id="a654d-155">Lua</span><span class="sxs-lookup"><span data-stu-id="a654d-155">Lua</span></span>
    - <span data-ttu-id="a654d-156">MATLAB</span><span class="sxs-lookup"><span data-stu-id="a654d-156">MATLAB</span></span>
    - <span data-ttu-id="a654d-157">Objective-C</span><span class="sxs-lookup"><span data-stu-id="a654d-157">Objective-C</span></span>
    - <span data-ttu-id="a654d-158">Perl</span><span class="sxs-lookup"><span data-stu-id="a654d-158">Perl</span></span>
    - <span data-ttu-id="a654d-159">PHP</span><span class="sxs-lookup"><span data-stu-id="a654d-159">PHP</span></span>
    - <span data-ttu-id="a654d-160">Python</span><span class="sxs-lookup"><span data-stu-id="a654d-160">Python</span></span>
    - <span data-ttu-id="a654d-161">R</span><span class="sxs-lookup"><span data-stu-id="a654d-161">R</span></span>
    - <span data-ttu-id="a654d-162">Ruby</span><span class="sxs-lookup"><span data-stu-id="a654d-162">Ruby</span></span>
    - <span data-ttu-id="a654d-163">Scala</span><span class="sxs-lookup"><span data-stu-id="a654d-163">Scala</span></span>
    - <span data-ttu-id="a654d-164">Shell</span><span class="sxs-lookup"><span data-stu-id="a654d-164">Shell</span></span>
    - <span data-ttu-id="a654d-165">Swift</span><span class="sxs-lookup"><span data-stu-id="a654d-165">Swift</span></span>
    - <span data-ttu-id="a654d-166">Tex</span><span class="sxs-lookup"><span data-stu-id="a654d-166">Tex</span></span>
    - <span data-ttu-id="a654d-167">Vim Script</span><span class="sxs-lookup"><span data-stu-id="a654d-167">Vim Script</span></span>

> [!NOTE]
> <span data-ttu-id="a654d-168">Källkod används för att identifiera när större delen av texten är källkod.</span><span class="sxs-lookup"><span data-stu-id="a654d-168">Source Code is trained to detect when the bulk of the text is source code.</span></span> <span data-ttu-id="a654d-169">Den identifierar inte källkodstext som är översedd med oformaterad text.</span><span class="sxs-lookup"><span data-stu-id="a654d-169">It does not detect source code text that is interspersed with plain text.</span></span>

- <span data-ttu-id="a654d-170">**Trakasserier:** Upptäcker en specifik kategori med stötande språktextobjekt som är relaterade till stötande uppförande som är riktad mot en eller flera personer baserat på följande egenskaper: etnicitet, religion, nationella ursprung, kön, sexuell orientering, ålder, funktionshinder</span><span class="sxs-lookup"><span data-stu-id="a654d-170">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability</span></span>
- <span data-ttu-id="a654d-171">**Svordomar:** identifierar en specifik kategori med stötande språktextobjekt som innehåller uttryck som är försämnande för de flesta</span><span class="sxs-lookup"><span data-stu-id="a654d-171">**Profanity**: detects a specific category of offensive language text items that contain expressions that embarrass most people</span></span>
- <span data-ttu-id="a654d-172">**Hot:** upptäcker en specifik kategori av anstötliga språktextobjekt som är relaterade till hot om våld eller att utföra fysisk skada eller skada en person eller egendom</span><span class="sxs-lookup"><span data-stu-id="a654d-172">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property</span></span>

<span data-ttu-id="a654d-173">De visas i **Microsoft 365 dataklassificeringsvyn** För utbildare  >    >   med statusen `Ready to use` .</span><span class="sxs-lookup"><span data-stu-id="a654d-173">These appear in the **Microsoft 365 compliance center** > **Data classification** > **Trainable classifiers** view with the status of `Ready to use`.</span></span>

![klassifierare som är förinsorterade](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> <span data-ttu-id="a654d-175">Observera att det stötande språket, trakasserier, svordomar och hotklassare endast fungerar med sökbar text inte är uttömmande eller fullständig.</span><span class="sxs-lookup"><span data-stu-id="a654d-175">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text are not exhaustive or complete.</span></span>  <span data-ttu-id="a654d-176">Ytterligare, språk och kulturstandarder ändras kontinuerligt, och mot bakgrund av dessa omotiv, förbehåller sig Microsoft rätten att uppdatera dessa klassificerare enligt eget gottfinnande.</span><span class="sxs-lookup"><span data-stu-id="a654d-176">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers in its discretion.</span></span> <span data-ttu-id="a654d-177">Klassificerarna kan hjälpa organisationen att övervaka anstötligt och annat språk som används, men klassificerarna tar inte itu med konsekvenserna av ett sådant språk och är inte avsedda att ge din organisation enbart möjlighet att övervaka eller svara på användning av ett sådant språk.</span><span class="sxs-lookup"><span data-stu-id="a654d-177">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization's sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="a654d-178">Din organisation, och inte Microsoft eller dess dotterbolag, förblir ansvarig för alla beslut som rör övervakning, tillämpning, blockering, borttagning och lagring av innehåll som identifierats av en i förväg utbildad klassificerare.</span><span class="sxs-lookup"><span data-stu-id="a654d-178">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal and retention of any content identified by a pre-trained classifier.</span></span>

### <a name="custom-classifiers"></a><span data-ttu-id="a654d-179">Anpassade klassificerare</span><span class="sxs-lookup"><span data-stu-id="a654d-179">Custom classifiers</span></span>

<span data-ttu-id="a654d-180">Om de i förväg utbildade klassificerarna inte uppfyller dina behov kan du skapa och utbilda dina egna klassificerare.</span><span class="sxs-lookup"><span data-stu-id="a654d-180">When the pre-trained classifiers don't meet your needs, you can create and train your own classifiers.</span></span> <span data-ttu-id="a654d-181">Det finns avsevärt mer arbete att skapa egna, men de kommer att bli mycket bättre skräddarsydda efter organisationens behov.</span><span class="sxs-lookup"><span data-stu-id="a654d-181">There's significantly more work involved with creating your own, but they'll be much better tailored to your organizations needs.</span></span> 

<span data-ttu-id="a654d-182">Du kan till exempel skapa utbildare för:</span><span class="sxs-lookup"><span data-stu-id="a654d-182">For example you could create trainable classifiers for:</span></span>
 
- <span data-ttu-id="a654d-183">Juridiska dokument – t.ex. juristklientbehörighet, avslutande uppsättningar, arbetsutdrag</span><span class="sxs-lookup"><span data-stu-id="a654d-183">Legal documents - such as attorney client privilege, closing sets, statement of work</span></span>
- <span data-ttu-id="a654d-184">Strategiska affärsdokument – t.e. pressmeddelanden, sammanslagningar och förvärv, avtal, affärsplaner, immateriell egendom, patent, designdokument</span><span class="sxs-lookup"><span data-stu-id="a654d-184">Strategic business documents - like press releases, merger and acquisition, deals, business or marketing plans, intellectual property, patents, design docs</span></span>
- <span data-ttu-id="a654d-185">Prisinformation – som fakturor, prisuppgifter, arbetsorder, dokument med hög prissättning</span><span class="sxs-lookup"><span data-stu-id="a654d-185">Pricing information - like invoices, price quotes, work orders, bidding documents</span></span> 
- <span data-ttu-id="a654d-186">Ekonomisk information – till exempel investeringar i organisationen, kvartalsvisa eller årliga resultat</span><span class="sxs-lookup"><span data-stu-id="a654d-186">Financial information - such as organizational investments, quarterly or annual results</span></span>    

#### <a name="process-flow-for-creating-custom-classifiers"></a><span data-ttu-id="a654d-187">Processflöde för att skapa anpassade klassificerare</span><span class="sxs-lookup"><span data-stu-id="a654d-187">Process flow for creating custom classifiers</span></span>

<span data-ttu-id="a654d-188">Genom att skapa och publicera en klassificerare för användning i efterlevnadslösningar, till exempel kvarhållningsprinciper och kommunikations överanvändning, följer du det här flödet.</span><span class="sxs-lookup"><span data-stu-id="a654d-188">Creating and publishing a classifier for use in compliance solutions, such as retention policies and communication supervision, follows this flow.</span></span> <span data-ttu-id="a654d-189">Mer information om hur du skapar en egen utbildare finns i [Skapa en anpassad klassificerare](classifier-get-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="a654d-189">For more detail on creating a custom trainable classifier see, [Creating a custom classifier](classifier-get-started-with.md).</span></span>

![Anpassad klassificerare för processflöde](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a><span data-ttu-id="a654d-191">Omklassning av klassificerare</span><span class="sxs-lookup"><span data-stu-id="a654d-191">Retraining classifiers</span></span>

<span data-ttu-id="a654d-192">Du kan förbättra noggrannheten för alla anpassade klassificerare och vissa i förväg utbildade klassificerare genom att ge dem feedback om hur korrekt klassificeringen de utför.</span><span class="sxs-lookup"><span data-stu-id="a654d-192">You can help improve the accuracy of all custom classifiers and some pre-trained classifiers by providing them with feedback on the accuracy of the classification that they perform.</span></span> <span data-ttu-id="a654d-193">Det kallas för att begränsa och följa det här arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="a654d-193">This is called retraining and follow this workflow.</span></span>

![arbetsflöde för omsämring av klassificerare](../media/classifier-retraining-workflow.png)

## <a name="see-also"></a><span data-ttu-id="a654d-195">Se även</span><span class="sxs-lookup"><span data-stu-id="a654d-195">See also</span></span>

- [<span data-ttu-id="a654d-196">Kvarhållningsetiketter</span><span class="sxs-lookup"><span data-stu-id="a654d-196">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="a654d-197">Mer information om skydd mot dataförlust</span><span class="sxs-lookup"><span data-stu-id="a654d-197">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="a654d-198">Känslighetsetiketter</span><span class="sxs-lookup"><span data-stu-id="a654d-198">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="a654d-199">Entitetsdefinitioner för typer av känslig information</span><span class="sxs-lookup"><span data-stu-id="a654d-199">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="a654d-200">Dokumentutskrift med finger</span><span class="sxs-lookup"><span data-stu-id="a654d-200">Document finger printing</span></span>](document-fingerprinting.md)
- [<span data-ttu-id="a654d-201">Exakt datamatchning</span><span class="sxs-lookup"><span data-stu-id="a654d-201">Exact data match</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
