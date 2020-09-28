---
title: Förklaringar
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Läs mer om förklarings typer i Microsoft SharePoint Syntex
ms.openlocfilehash: f4f5dbc24bef57b1801f7df1b7e2fc7ef9b08116
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296218"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="3dff2-103">Introduktion till förklarings typer</span><span class="sxs-lookup"><span data-stu-id="3dff2-103">Introduction to explanation types</span></span>

<span data-ttu-id="3dff2-104">Använd förklaringar för att definiera informationen som du vill lägga till och extrahera i dokumentet förstå modellerna för Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="3dff2-104">Use explanations to help to define the information that you want to label, and extract in your document the understanding models for Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="3dff2-105">När du skapar en förklaring bör du välja en typ av förklaring.</span><span class="sxs-lookup"><span data-stu-id="3dff2-105">When you create an explanation, be sure to select an explanation type.</span></span> 

<span data-ttu-id="3dff2-106">Den här artikeln hjälper dig att förstå olika typer av förklaringar och hur de används.</span><span class="sxs-lookup"><span data-stu-id="3dff2-106">This article helps you understand the different explanation types and how they are used.</span></span>

   ![Förklaringar](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="3dff2-108">Följande förklaringar är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="3dff2-108">These explanation types are available:</span></span>

- <span data-ttu-id="3dff2-109">**Fras lista**: lista över ord, fraser, tal eller andra tecken som du kan använda i dokumentet eller informationen som du extraherar.</span><span class="sxs-lookup"><span data-stu-id="3dff2-109">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="3dff2-110">Text strängen som **refererar till läkare** är till exempel i alla medicinska hänvisnings dokument som du identifierar.</span><span class="sxs-lookup"><span data-stu-id="3dff2-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span></br>

- <span data-ttu-id="3dff2-111">**Mönster lista**: lista med tecken mönster med siffror, bokstäver eller andra specialtecken som du kan använda för att identifiera informationen som du extraherar.</span><span class="sxs-lookup"><span data-stu-id="3dff2-111">**Pattern list**: List patterns of numbers, letters, or other characters that you can use to identify the information that you are extracting.</span></span> <span data-ttu-id="3dff2-112">Du kan till exempel extrahera **telefonnumret** från det dokument för medicinsk hänvisning som du identifierar.</span><span class="sxs-lookup"><span data-stu-id="3dff2-112">For example, you can extract the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span></br>

- <span data-ttu-id="3dff2-113">**Närhet**: beskriver hur nära förklaringar är till varandra.</span><span class="sxs-lookup"><span data-stu-id="3dff2-113">**Proximity**: Describes how close explanations are to each other.</span></span> <span data-ttu-id="3dff2-114">Till exempel kan en lista med *gatu nummer* mönster placeras direkt före *gatu namns* frasen, med inga tokens mellan (du lär dig mer om tokens längre fram i den här artikeln).</span><span class="sxs-lookup"><span data-stu-id="3dff2-114">For example, a *street number* pattern list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="3dff2-115">Fras lista</span><span class="sxs-lookup"><span data-stu-id="3dff2-115">Phrase list</span></span>

<span data-ttu-id="3dff2-116">En förklarings typ för en fras lista används vanligt vis för att identifiera och klassificera ett dokument genom modellen.</span><span class="sxs-lookup"><span data-stu-id="3dff2-116">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="3dff2-117">Enligt beskrivningen i exemplet *hänvisar* till exempel är det en sträng med ord, fraser, tal eller tecken som är konsekvent i de dokument som du identifierar.</span><span class="sxs-lookup"><span data-stu-id="3dff2-117">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="3dff2-118">Men inte ett krav kan du få bättre framgång med din förklaring om den fras du hämtar finns på en konsekvent plats i dokumentet.</span><span class="sxs-lookup"><span data-stu-id="3dff2-118">While not a requirement, you can acheive better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="3dff2-119">Etiketten för den *refererande läkaren* kan till exempel finnas konsekvent i det första stycket i dokumentet.</span><span class="sxs-lookup"><span data-stu-id="3dff2-119">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span>

<span data-ttu-id="3dff2-120">Om SKIFT läges känslighet är ett krav för att identifiera din etikett kan du använda fras listans typ för att ange den i din förklaring genom att markera kryss rutan **endast exakta versaler** .</span><span class="sxs-lookup"><span data-stu-id="3dff2-120">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

   ![Skift läges känslighet](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a><span data-ttu-id="3dff2-122">Mönster listor</span><span class="sxs-lookup"><span data-stu-id="3dff2-122">Pattern lists</span></span>

<span data-ttu-id="3dff2-123">En typ av en mönster lista är särskilt användbar när du skapar en förklaring som identifierar och hämtar information från ett dokument.</span><span class="sxs-lookup"><span data-stu-id="3dff2-123">A pattern list type is especially useful when you create an explanation that identifies and extracts information from a document.</span></span> <span data-ttu-id="3dff2-124">Det visas normalt i olika format, till exempel datum, telefonnummer eller kreditkorts nummer.</span><span class="sxs-lookup"><span data-stu-id="3dff2-124">It is typically presented in different formats, such as dates, phone numbers, or credit card numbers.</span></span> <span data-ttu-id="3dff2-125">Ett datum kan till exempel visas i ett antal olika format (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, 1 januari 2020 osv.).</span><span class="sxs-lookup"><span data-stu-id="3dff2-125">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="3dff2-126">Om du definierar en mönster lista blir din förklaring mer effektiv genom att fånga eventuella variationer i de data som du försöker identifiera och extrahera.</span><span class="sxs-lookup"><span data-stu-id="3dff2-126">Defining a pattern list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="3dff2-127">Extrahera **telefonnumret** för varje referent från alla dokument för medicinsk hänvisning som identifieras av modellen.</span><span class="sxs-lookup"><span data-stu-id="3dff2-127">For the **Phone number** sample, extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="3dff2-128">När du skapar en förklaring väljer du typen av mönster lista för att tillåta de olika format som du kan förvänta dig att returneras.</span><span class="sxs-lookup"><span data-stu-id="3dff2-128">When you create the explanation, select the Pattern list type to allow the different formats that you may expect to be returned.</span></span>

   ![Telefon nummer mönster lista](../media/content-understanding/pattern-list.png)

<span data-ttu-id="3dff2-130">För det här exemplet markerar du kryss rutan **valfri siffra från 0-9** .</span><span class="sxs-lookup"><span data-stu-id="3dff2-130">For this sample, select the **Any digit from 0-9** checkbox.</span></span> <span data-ttu-id="3dff2-131">Om du väljer det här alternativet tolkas varje "0"-värde som används i din mönster lista som valfri siffra mellan 0 och 9.</span><span class="sxs-lookup"><span data-stu-id="3dff2-131">Selecting this recognizes each "0" value used in your pattern list to be any digit from 0 through 9.</span></span>

   ![Valfri siffra från 0-9](../media/content-understanding/digit-identity.png)

<span data-ttu-id="3dff2-133">Om du skapar en mönster lista som innehåller text tecken markerar du rutan **valfri bokstav från en-z** .</span><span class="sxs-lookup"><span data-stu-id="3dff2-133">Similarly, if you create a pattern list that includes text characters, select the **Any letter from a-z** checkbox.</span></span> <span data-ttu-id="3dff2-134">Om du väljer det här alternativet tolkas varje "a"-tecken som används i listan mönster som ett tecken från "a" till "z".</span><span class="sxs-lookup"><span data-stu-id="3dff2-134">Selecting this recognizes each "a" character used in the pattern list to be any character from "a" to "z".</span></span>

<span data-ttu-id="3dff2-135">Om du till exempel skapar en **datum** mönster lista och vill vara säker på att ett datum format som *1 januari 2020* känns igen, måste du:</span><span class="sxs-lookup"><span data-stu-id="3dff2-135">For example, if you create a **Date** pattern list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="3dff2-136">Lägg till *AAA 0, 0000* och *AAA 00, 0000* i din mönster lista.</span><span class="sxs-lookup"><span data-stu-id="3dff2-136">Add *aaa 0, 0000* and *aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="3dff2-137">Se till att **alla bokstäver från a-z** också är markerade.</span><span class="sxs-lookup"><span data-stu-id="3dff2-137">Make sure that **Any letter from a-z** is also selected.</span></span>

   ![Valfri bokstav från a-z](../media/content-understanding/any-letter.png)

<span data-ttu-id="3dff2-139">Om du har behov av villkor i din Pattern-lista kan du välja att markera kryss rutan **endast exakta versaler** .</span><span class="sxs-lookup"><span data-stu-id="3dff2-139">Additionally, if you have capitalization requirements in your pattern list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="3dff2-140">Om du behöver den första bokstaven i månaden för att ange ett datum-exempel måste du göra följande:</span><span class="sxs-lookup"><span data-stu-id="3dff2-140">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="3dff2-141">Lägg till *AAA 0, 0000* och *AAA 00, 0000* i din mönster lista.</span><span class="sxs-lookup"><span data-stu-id="3dff2-141">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="3dff2-142">Kontrol lera att **endast exakta Skift läge** är markerat.</span><span class="sxs-lookup"><span data-stu-id="3dff2-142">Make sure that **Only exact capitalization** is also selected.</span></span>

   ![Endast exakta versaler](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="3dff2-144">I stället för att manuellt skapa mönster listans förklaring kan du använda [förklaringen]() för att använda mallarna för färdiga mönster listor för vanliga mönster listor, till exempel *datum*, *telefonnummer*, *kreditkorts nummer*etc..</span><span class="sxs-lookup"><span data-stu-id="3dff2-144">Instead of manually creating pattern list explanation, use the [explanation library]() to use pre-made pattern list templates for common pattern list, such as *date*, *phone number*, *credit card number*, etc..</span></span> 

## <a name="proximity"></a><span data-ttu-id="3dff2-145">Närhet</span><span class="sxs-lookup"><span data-stu-id="3dff2-145">Proximity</span></span> 

<span data-ttu-id="3dff2-146">Med hjälp av den här typen av förklaringar kan modellen identifiera data genom att definiera hur nära en annan del av data ska vara.</span><span class="sxs-lookup"><span data-stu-id="3dff2-146">The proximity explanation type helps your model identify data through defining how close another piece of data is to it.</span></span> <span data-ttu-id="3dff2-147">I din modell har du till exempel två förklaringar som Märk både kundens *gatuadress* och *telefonnummer*.</span><span class="sxs-lookup"><span data-stu-id="3dff2-147">For example, in your model, you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="3dff2-148">Du märker också att kundernas telefonnummer alltid visas före gatuadress.</span><span class="sxs-lookup"><span data-stu-id="3dff2-148">You also notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="3dff2-149">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="3dff2-149">Alex Wilburn</span></span><br>
<span data-ttu-id="3dff2-150">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="3dff2-150">555-555-5555</span></span><br>
<span data-ttu-id="3dff2-151">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="3dff2-151">One Microsoft Way</span></span><br>
<span data-ttu-id="3dff2-152">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="3dff2-152">Redmond, WA 98034</span></span><br>

<span data-ttu-id="3dff2-153">Använd närhets förklaringen för att definiera hur långt bort det aktuella telefonnumret är för att bättre identifiera gatuadressen i dina dokument.</span><span class="sxs-lookup"><span data-stu-id="3dff2-153">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

   ![Närhets förklaring](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a><span data-ttu-id="3dff2-155">Vad är tokens?</span><span class="sxs-lookup"><span data-stu-id="3dff2-155">What are tokens?</span></span>

<span data-ttu-id="3dff2-156">För att använda funktionen för närhets förklaringar kan du förstå vad en token är, eftersom antalet tokens är hur avståndet mellan två förklaringar mäter avstånd från en förklaring till en annan.</span><span class="sxs-lookup"><span data-stu-id="3dff2-156">In order to use the proximity explanation type, understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span>  

<span data-ttu-id="3dff2-157">Ett token är ett sammanhängande intervall (inga blank steg eller skiljetecken) av bokstäver och siffror.</span><span class="sxs-lookup"><span data-stu-id="3dff2-157">A token is a continuous span (no spaces or punctuation) of letters and numbers.</span></span> <span data-ttu-id="3dff2-158">Ett blank steg är inte ett token.</span><span class="sxs-lookup"><span data-stu-id="3dff2-158">A space is NOT a token.</span></span> <span data-ttu-id="3dff2-159">Varje skiljetecken är ett token.</span><span class="sxs-lookup"><span data-stu-id="3dff2-159">Each punctuation character is a token.</span></span> <span data-ttu-id="3dff2-160">Följande tabell visar några exempel på hur du kan avgöra antalet tokens i en fras.</span><span class="sxs-lookup"><span data-stu-id="3dff2-160">The following table shows some examples of how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="3dff2-161">Verbfras</span><span class="sxs-lookup"><span data-stu-id="3dff2-161">Phrase</span></span>|<span data-ttu-id="3dff2-162">Antal token</span><span class="sxs-lookup"><span data-stu-id="3dff2-162">Number of tokens</span></span>|<span data-ttu-id="3dff2-163">Förklaring</span><span class="sxs-lookup"><span data-stu-id="3dff2-163">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="3dff2-164">9.1</span><span class="sxs-lookup"><span data-stu-id="3dff2-164">1</span></span>|<span data-ttu-id="3dff2-165">Ett enstaka ord utan skiljetecken eller blank steg.</span><span class="sxs-lookup"><span data-stu-id="3dff2-165">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="3dff2-166">9.1</span><span class="sxs-lookup"><span data-stu-id="3dff2-166">1</span></span>|<span data-ttu-id="3dff2-167">Ett post nummer.</span><span class="sxs-lookup"><span data-stu-id="3dff2-167">A record locator number.</span></span> <span data-ttu-id="3dff2-168">Den kan ha siffror och bokstäver, men har inte skiljetecken.</span><span class="sxs-lookup"><span data-stu-id="3dff2-168">It may have numbers and letters, but does not have any punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="3dff2-169">T5</span><span class="sxs-lookup"><span data-stu-id="3dff2-169">5</span></span>|<span data-ttu-id="3dff2-170">Ett telefonnummer.</span><span class="sxs-lookup"><span data-stu-id="3dff2-170">A phone number.</span></span> <span data-ttu-id="3dff2-171">Varje skiljetecken är en enda token så  `425-555-5555` att den blir 5 tokens:</span><span class="sxs-lookup"><span data-stu-id="3dff2-171">Each punctuation mark is a single token so  `425-555-5555` would be 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="3dff2-172">borttagning</span><span class="sxs-lookup"><span data-stu-id="3dff2-172">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="3dff2-173">Konfigurera typ av en närhet</span><span class="sxs-lookup"><span data-stu-id="3dff2-173">Configure the proximity explanation type</span></span>

<span data-ttu-id="3dff2-174">För det här exemplet ska du konfigurera inställningen för närhet så att vi kan definiera intervallet för antalet *tokens som kundens förklaring är* från rikt *nummer* förklaringen.</span><span class="sxs-lookup"><span data-stu-id="3dff2-174">For the sample, configure the proximity setting so that we can define the range of the number of tokens the *Phone number* explanation is from the *Street address number* explanation.</span></span>

<span data-ttu-id="3dff2-175">Du bör se att det minsta intervallet är "0" eftersom det inte finns några tokens mellan telefonnumret och gatuadressen.</span><span class="sxs-lookup"><span data-stu-id="3dff2-175">You should see that the minimum range is "0" since there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="3dff2-176">Men vissa telefonnummer i exempel dokumenten läggs till med *(mobil)*.</span><span class="sxs-lookup"><span data-stu-id="3dff2-176">However, some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="3dff2-177">Nestor Wilke</span><span class="sxs-lookup"><span data-stu-id="3dff2-177">Nestor Wilke</span></span><br>
<span data-ttu-id="3dff2-178">111-111-1111 (mobil)</span><span class="sxs-lookup"><span data-stu-id="3dff2-178">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="3dff2-179">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="3dff2-179">One Microsoft Way</span></span><br>
<span data-ttu-id="3dff2-180">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="3dff2-180">Redmond, WA 98034</span></span><br>

<span data-ttu-id="3dff2-181">Det finns tre tokens i *(mobil)*:</span><span class="sxs-lookup"><span data-stu-id="3dff2-181">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="3dff2-182">Verbfras</span><span class="sxs-lookup"><span data-stu-id="3dff2-182">Phrase</span></span>|<span data-ttu-id="3dff2-183">Antal token</span><span class="sxs-lookup"><span data-stu-id="3dff2-183">Token count</span></span>|
|--|--|
|<span data-ttu-id="3dff2-184">(</span><span class="sxs-lookup"><span data-stu-id="3dff2-184">(</span></span>|<span data-ttu-id="3dff2-185">9.1</span><span class="sxs-lookup"><span data-stu-id="3dff2-185">1</span></span>|
|<span data-ttu-id="3dff2-186">mobilvy</span><span class="sxs-lookup"><span data-stu-id="3dff2-186">mobile</span></span>|<span data-ttu-id="3dff2-187">två</span><span class="sxs-lookup"><span data-stu-id="3dff2-187">2</span></span>|
|<span data-ttu-id="3dff2-188">)</span><span class="sxs-lookup"><span data-stu-id="3dff2-188">)</span></span>|<span data-ttu-id="3dff2-189">amp;3D</span><span class="sxs-lookup"><span data-stu-id="3dff2-189">3</span></span>|

<span data-ttu-id="3dff2-190">Konfigurera inställningen för närhet till att ha ett område på mellan 0 och 3.</span><span class="sxs-lookup"><span data-stu-id="3dff2-190">Configure the proximity setting to have a range of 0 through 3.</span></span>

   ![Exempel på närhet](../media/content-understanding/proximity-example.png)</br>

## <a name="use-the-explanation-library"></a><span data-ttu-id="3dff2-192">Använda förklarings biblioteket</span><span class="sxs-lookup"><span data-stu-id="3dff2-192">Use the explanation library</span></span>

<span data-ttu-id="3dff2-193">Du kan lägga till olika värden för dina förklaringar manuellt, det är mycket enklare att använda de färdiga mallarna som finns i förklarings biblioteket.</span><span class="sxs-lookup"><span data-stu-id="3dff2-193">While you can manually add various pattern list values for your explanation, it's much easier to use the pre-created templates provided to you in the explanation library.</span></span>

<span data-ttu-id="3dff2-194">I stället för att lägga till alla variationer för *datum*kan du använda mallen mönster lista för *datum*, som redan innehåller ett antal mönster listor:</span><span class="sxs-lookup"><span data-stu-id="3dff2-194">For example, instead of manually adding all the variations for *Date*, use the pattern list template for *Date*, that already includes a number of pattern lists values:</span></span></br>

   ![Förklarings bibliotek](../media/content-understanding/explanation-template.png)</br>
 
<span data-ttu-id="3dff2-196">I förklarings biblioteket finns många förklaringar som ofta används, bland annat:</span><span class="sxs-lookup"><span data-stu-id="3dff2-196">The explanation library includes a number of commonly used pattern list explanations, including:</span></span></br>

- <span data-ttu-id="3dff2-197">Datum</span><span class="sxs-lookup"><span data-stu-id="3dff2-197">Date</span></span></br>
- <span data-ttu-id="3dff2-198">Datum (numeriskt)</span><span class="sxs-lookup"><span data-stu-id="3dff2-198">Date (numeric)</span></span></br>
- <span data-ttu-id="3dff2-199">Tider</span><span class="sxs-lookup"><span data-stu-id="3dff2-199">Time</span></span></br>
- <span data-ttu-id="3dff2-200">Tal</span><span class="sxs-lookup"><span data-stu-id="3dff2-200">Number</span></span></br>
- <span data-ttu-id="3dff2-201">Telefonnummer</span><span class="sxs-lookup"><span data-stu-id="3dff2-201">Phone number</span></span></br>
- <span data-ttu-id="3dff2-202">Postnummer</span><span class="sxs-lookup"><span data-stu-id="3dff2-202">Zip code</span></span></br>
- <span data-ttu-id="3dff2-203">Första ord med mening</span><span class="sxs-lookup"><span data-stu-id="3dff2-203">First word of sentence</span></span></br>
- <span data-ttu-id="3dff2-204">Kredit kort</span><span class="sxs-lookup"><span data-stu-id="3dff2-204">Credit card</span></span></br>
- <span data-ttu-id="3dff2-205">Person nummer</span><span class="sxs-lookup"><span data-stu-id="3dff2-205">Social security number</span></span></br>

<span data-ttu-id="3dff2-206">Observera att förklarings biblioteket också innehåller mallar för förklarings listor, inklusive:</span><span class="sxs-lookup"><span data-stu-id="3dff2-206">Note that the explanation library also includes templates for phrase list explanations as well, including:</span></span>
- <span data-ttu-id="3dff2-207">Slutet av meningen</span><span class="sxs-lookup"><span data-stu-id="3dff2-207">End of sentence</span></span>
- <span data-ttu-id="3dff2-208">Valuta</span><span class="sxs-lookup"><span data-stu-id="3dff2-208">Currency</span></span>

#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="3dff2-209">Så här använder du en mall från förklarings biblioteket</span><span class="sxs-lookup"><span data-stu-id="3dff2-209">To use a template from the explanation library</span></span>

1. <span data-ttu-id="3dff2-210">Välj **nytt**i avsnittet **förklaringar** på modellens **tåg** sida och välj sedan **från en mall**.</span><span class="sxs-lookup"><span data-stu-id="3dff2-210">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span></br>

   ![Skapa från mall](../media/content-understanding/from-template.png)</br>

2.  <span data-ttu-id="3dff2-212">På sidan **förklaringar** väljer du den förklaring du vill använda och väljer sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="3dff2-212">On the **Explanation templates** page, select the explanation you want to use, and then select **Add**.</span></span></br>

       ![Välj en mall](../media/content-understanding/phone-template.png)</br>

3. <span data-ttu-id="3dff2-214">Informationen för den mall som du valde visas på sidan **skapa en förklaring** .</span><span class="sxs-lookup"><span data-stu-id="3dff2-214">The information for the template you selected will display on the **Create an explanation** page.</span></span> <span data-ttu-id="3dff2-215">Om det behövs redigerar du förklarings namnet och lägger till eller tar bort objekt från listan med mönster.</span><span class="sxs-lookup"><span data-stu-id="3dff2-215">If needed, edit the explanation name, and add or remove items from the pattern list.</span></span> </br> 

   ![Redigera mall](../media/content-understanding/phone-template-live.png)</br>

4. <span data-ttu-id="3dff2-217">När du är klar väljer du **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3dff2-217">When finished, select **Save**.</span></span>
