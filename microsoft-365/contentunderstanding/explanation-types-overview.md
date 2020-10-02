---
title: Förklaringstyper
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Mer information om olika typer av förklaringar i Microsoft SharePoint Syntex
ms.openlocfilehash: 7d78337fd91bc7e5a71bccd4867f019ae663417a
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321803"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="e7779-103">Introduktion till förklaringstyper</span><span class="sxs-lookup"><span data-stu-id="e7779-103">Introduction to explanation types</span></span>

<span data-ttu-id="e7779-104">Förklaringar används för att definiera den information som du vill använda för att ge etiketter och utdrag i dina modeller för dokumenttolkning i Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="e7779-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="e7779-105">När du skapar en förklaring måste du välja en förklaringstyp.</span><span class="sxs-lookup"><span data-stu-id="e7779-105">When creating an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="e7779-106">I den här artikeln får du hjälp att lära dig mer för att bättre förstå olika förklaringstyper och hur de används.</span><span class="sxs-lookup"><span data-stu-id="e7779-106">This article will help you learn more to better understand the different explanation types and how they are used.</span></span> 

   ![Förklaringstyper](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="e7779-108">Följande förklaringstyper är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="e7779-108">These explanation types are available:</span></span>

- <span data-ttu-id="e7779-109">**Fraslista**: lista med ord, fraser, siffror eller andra tecken som du kan använda i det dokument eller den information du extraherar.</span><span class="sxs-lookup"><span data-stu-id="e7779-109">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="e7779-110">Exempel: textsträngen **Hänvisande läkare** finns i alla medicinska referensdokument som du identifierar.</span><span class="sxs-lookup"><span data-stu-id="e7779-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span></br>

- <span data-ttu-id="e7779-111">**Mönsterlista**: listar mönster med siffror, bokstäver eller andra tecken som du kan använda för att identifiera den information som du extraherar.</span><span class="sxs-lookup"><span data-stu-id="e7779-111">**Pattern list**: List patterns of numbers, letters, or other characters that you can use to identify the information that you are extracting.</span></span> <span data-ttu-id="e7779-112">Till exempel kan du extrahera den hänvisande läkarens **Telefonnumret** i alla medicinsk referensdokument som du identifierar.</span><span class="sxs-lookup"><span data-stu-id="e7779-112">For example, you can extract the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span></br>

- <span data-ttu-id="e7779-113">**Närhet**: beskriver hur nära förklaringar är för varandra.</span><span class="sxs-lookup"><span data-stu-id="e7779-113">**Proximity**: Describes how close explanations are to each other.</span></span> <span data-ttu-id="e7779-114">Exempel: en mönsterlista för *gatunummer* ska ligga precis efter fraslistan för *gatunamn* utan tokens i mellan (du får lära dig mer om tokens senare i den här artikeln).</span><span class="sxs-lookup"><span data-stu-id="e7779-114">For example, a *street number* pattern list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="e7779-115">Med närhetstypen måste du ha minst två förklaringar i modellen eller så är alternativet inaktiverat.</span><span class="sxs-lookup"><span data-stu-id="e7779-115">Using the proximity type requires you to have at least two explanations in your model, or the option will be disabled.</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="e7779-116">Fraslista</span><span class="sxs-lookup"><span data-stu-id="e7779-116">Phrase list</span></span>

<span data-ttu-id="e7779-117">Förklaringstypen fraslista används vanligtvis för att identifiera och klassificera ett dokument via modellen.</span><span class="sxs-lookup"><span data-stu-id="e7779-117">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="e7779-118">Så som det beskrivs i exemplet med etikett för *Hänvisande läkare* är det en sträng med ord, fraser, siffror eller tecken är konsekventa i de dokument som du identifierar.</span><span class="sxs-lookup"><span data-stu-id="e7779-118">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="e7779-119">Även om det inte är obligatoriskt kan du få bättre framgång med din förklaring om frasen du hämtar finns på en konsekvent plats i dokumentet.</span><span class="sxs-lookup"><span data-stu-id="e7779-119">While not a requirement, you can acheive better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="e7779-120">Till exempel kan etiketten *Hänvisande läkare* konsekvent finnas i det första stycket i dokumentet.</span><span class="sxs-lookup"><span data-stu-id="e7779-120">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span>

<span data-ttu-id="e7779-121">Om skifteslägeskänslighet är obligatorisk för att identifiera din etikett tillåter användning av fraslista dig att ange det i förklaringen genom att markera kryssrutan **Endast exakta versaler**.</span><span class="sxs-lookup"><span data-stu-id="e7779-121">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

   ![Skifteslägeskänslighet](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a><span data-ttu-id="e7779-123">Mönsterlistor</span><span class="sxs-lookup"><span data-stu-id="e7779-123">Pattern lists</span></span>

<span data-ttu-id="e7779-124">Typen mönsterlista är särskilt användbar när du skapar en förklaring som identifierar och hämtar information från ett dokument.</span><span class="sxs-lookup"><span data-stu-id="e7779-124">A pattern list type is especially useful when you create an explanation that identifies and extracts information from a document.</span></span> <span data-ttu-id="e7779-125">Den visas vanligtvis i olika format, till exempel datum, telefonnummer eller kreditkortsnummer.</span><span class="sxs-lookup"><span data-stu-id="e7779-125">It is typically presented in different formats, such as dates, phone numbers, or credit card numbers.</span></span> <span data-ttu-id="e7779-126">Ett datum kan till exempel visas i flera olika format (1/1 2020, 2020-01-01, 1 januari 2020 osv.).</span><span class="sxs-lookup"><span data-stu-id="e7779-126">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="e7779-127">Genom att definiera en mönsterlista blir förklaringen mer effektiv genom att fånga alla möjliga variationer i de data som du försöker identifiera och extrahera.</span><span class="sxs-lookup"><span data-stu-id="e7779-127">Defining a pattern list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="e7779-128">För exemplet **Telefonnummer** extraheras telefonnumret till varje hänvisande läkare från alla medicinska referensdokument som modellen identifierar.</span><span class="sxs-lookup"><span data-stu-id="e7779-128">For the **Phone number** sample, extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="e7779-129">När du skapar förklaringen väljer du typen mönsterlista för att tillåta de olika format som du kan förvänta dig returneras.</span><span class="sxs-lookup"><span data-stu-id="e7779-129">When you create the explanation, select the Pattern list type to allow the different formats that you may expect to be returned.</span></span>

   ![Mönsterlista för telefonnummer](../media/content-understanding/pattern-list.png)

<span data-ttu-id="e7779-131">I det här exemplet väljer du kryssrutan **Valfri siffra från 0-9**.</span><span class="sxs-lookup"><span data-stu-id="e7779-131">For this sample, select the **Any digit from 0-9** checkbox.</span></span> <span data-ttu-id="e7779-132">Att välja det här alternativet känner igen varje "0"-värde som används i mönsterlistan som valfri siffra mellan 0 och 9.</span><span class="sxs-lookup"><span data-stu-id="e7779-132">Selecting this recognizes each "0" value used in your pattern list to be any digit from 0 through 9.</span></span>

   ![Alla siffror från 0-9](../media/content-understanding/digit-identity.png)

<span data-ttu-id="e7779-134">Om du skapar en mönsterlista som innehåller texttecken markerar du kryssrutan **Valfri bokstav från a-ö**.</span><span class="sxs-lookup"><span data-stu-id="e7779-134">Similarly, if you create a pattern list that includes text characters, select the **Any letter from a-z** checkbox.</span></span> <span data-ttu-id="e7779-135">Om du väljer det här alternativet tolkas alla "a"-tecken som används i mönsterlistan som valfritt tecken från "a" till "ö".</span><span class="sxs-lookup"><span data-stu-id="e7779-135">Selecting this recognizes each "a" character used in the pattern list to be any character from "a" to "z".</span></span>

<span data-ttu-id="e7779-136">Om du till exempel skapar en mönsterlista för **Datum** och vill se till att ett datumformat som *1 januari 2020* känns igen måste du:</span><span class="sxs-lookup"><span data-stu-id="e7779-136">For example, if you create a **Date** pattern list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="e7779-137">Lägga till *0 aaaaaaa 0000* och *00 aaaaaaa 0000* i din mönsterlista.</span><span class="sxs-lookup"><span data-stu-id="e7779-137">Add *aaa 0, 0000* and *aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="e7779-138">Kontrollera att **Valfri bokstav från a-ö** också är markerad.</span><span class="sxs-lookup"><span data-stu-id="e7779-138">Make sure that **Any letter from a-z** is also selected.</span></span>

   ![Valfri bokstav från a till ö](../media/content-understanding/any-letter.png)

<span data-ttu-id="e7779-140">Om du även har krav på stor begynnelsebokstav i din mönsterlista kan du välja kryssrutan **Endast exakta versaler**.</span><span class="sxs-lookup"><span data-stu-id="e7779-140">Additionally, if you have capitalization requirements in your pattern list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="e7779-141">Om du kräver att den första bokstaven i månaden för datumexemplet har stor begynnelsebokstav behöver du:</span><span class="sxs-lookup"><span data-stu-id="e7779-141">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="e7779-142">Lägga till *0 Aaaaaaa 0000* och *00 Aaaaaaa 0000* i din mönsterlista.</span><span class="sxs-lookup"><span data-stu-id="e7779-142">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="e7779-143">Kontrollera att **Endast exakta versaler** också är markerad.</span><span class="sxs-lookup"><span data-stu-id="e7779-143">Make sure that **Only exact capitalization** is also selected.</span></span>

   ![Endast exakta versaler](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="e7779-145">I stället för att manuellt skapa en förklaring för mönsterlista kan du använda [förklaringsbiblioteket]() för att använda färdiga mönsterlistmallar för vanliga mönsterlistor, till exempel *datum*, *telefonnummer*, *kreditkortsnummer*osv..</span><span class="sxs-lookup"><span data-stu-id="e7779-145">Instead of manually creating pattern list explanation, use the [explanation library]() to use pre-made pattern list templates for common pattern list, such as *date*, *phone number*, *credit card number*, etc..</span></span> 

## <a name="proximity"></a><span data-ttu-id="e7779-146">Närhet</span><span class="sxs-lookup"><span data-stu-id="e7779-146">Proximity</span></span> 

<span data-ttu-id="e7779-147">Typen närhetsförklaring hjälper modellen att lättare identifiera data genom att definiera hur nära ett annat data kommer till den.</span><span class="sxs-lookup"><span data-stu-id="e7779-147">The proximity explanation type helps your model identify data through defining how close another piece of data is to it.</span></span> <span data-ttu-id="e7779-148">I din modell har du till exempel två förklaringar som etiketterar både kundens *gatunummer* och *telefonnummer*.</span><span class="sxs-lookup"><span data-stu-id="e7779-148">For example, in your model, you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="e7779-149">Du ser också att kundens telefonnummer alltid visas före gatunumret.</span><span class="sxs-lookup"><span data-stu-id="e7779-149">You also notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="e7779-150">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="e7779-150">Alex Wilburn</span></span><br>
<span data-ttu-id="e7779-151">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="e7779-151">555-555-5555</span></span><br>
<span data-ttu-id="e7779-152">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="e7779-152">One Microsoft Way</span></span><br>
<span data-ttu-id="e7779-153">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="e7779-153">Redmond, WA 98034</span></span><br>

<span data-ttu-id="e7779-154">Använd närhetsförklaringen för att definiera hur långt bort det är för att bättre identifiera gatunumret i dina dokument.</span><span class="sxs-lookup"><span data-stu-id="e7779-154">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

   ![Närhetsförklaring](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a><span data-ttu-id="e7779-156">Vad är tokens?</span><span class="sxs-lookup"><span data-stu-id="e7779-156">What are tokens?</span></span>

<span data-ttu-id="e7779-157">Om du vill använda förklaringstypen närhet måste du förstå vad en token är eftersom antalet tokens är hur närhetsförklaringen mäter avståndet från en förklaring till en annan.</span><span class="sxs-lookup"><span data-stu-id="e7779-157">In order to use the proximity explanation type, understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span>  

<span data-ttu-id="e7779-158">En token är ett sammanhängande intervall (inga blanksteg eller skiljetecken) för bokstäver och siffror.</span><span class="sxs-lookup"><span data-stu-id="e7779-158">A token is a continuous span (no spaces or punctuation) of letters and numbers.</span></span> <span data-ttu-id="e7779-159">Ett blanksteg är INTE en token.</span><span class="sxs-lookup"><span data-stu-id="e7779-159">A space is NOT a token.</span></span> <span data-ttu-id="e7779-160">Varje skiljetecken är en token.</span><span class="sxs-lookup"><span data-stu-id="e7779-160">Each punctuation character is a token.</span></span> <span data-ttu-id="e7779-161">I tabellen nedan visas några exempel på hur du kan ta reda på antalet tokens i en fras.</span><span class="sxs-lookup"><span data-stu-id="e7779-161">The following table shows some examples of how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="e7779-162">Fras</span><span class="sxs-lookup"><span data-stu-id="e7779-162">Phrase</span></span>|<span data-ttu-id="e7779-163">Antal tokens</span><span class="sxs-lookup"><span data-stu-id="e7779-163">Number of tokens</span></span>|<span data-ttu-id="e7779-164">Förklaring</span><span class="sxs-lookup"><span data-stu-id="e7779-164">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="e7779-165">1</span><span class="sxs-lookup"><span data-stu-id="e7779-165">1</span></span>|<span data-ttu-id="e7779-166">Ett enstaka ord utan skiljetecken eller blanksteg.</span><span class="sxs-lookup"><span data-stu-id="e7779-166">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="e7779-167">1</span><span class="sxs-lookup"><span data-stu-id="e7779-167">1</span></span>|<span data-ttu-id="e7779-168">Ett lokaliseringsnummer för posten.</span><span class="sxs-lookup"><span data-stu-id="e7779-168">A record locator number.</span></span> <span data-ttu-id="e7779-169">Det kan finnas siffror och bokstäver men inga skiljetecken.</span><span class="sxs-lookup"><span data-stu-id="e7779-169">It may have numbers and letters, but does not have any punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="e7779-170">5</span><span class="sxs-lookup"><span data-stu-id="e7779-170">5</span></span>|<span data-ttu-id="e7779-171">Ett telefonnummer.</span><span class="sxs-lookup"><span data-stu-id="e7779-171">A phone number.</span></span> <span data-ttu-id="e7779-172">Varje skiljetecken är ett enda token, så  `425-555-5555` blir 5 tokens:</span><span class="sxs-lookup"><span data-stu-id="e7779-172">Each punctuation mark is a single token so  `425-555-5555` would be 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="e7779-173">7</span><span class="sxs-lookup"><span data-stu-id="e7779-173">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="e7779-174">Konfigurera typen närhetsförklaring</span><span class="sxs-lookup"><span data-stu-id="e7779-174">Configure the proximity explanation type</span></span>

<span data-ttu-id="e7779-175">Konfigurera inställningen närhet för urvalet så att vi kan definiera intervallet för antalet tokens som förklaringen för *telefonnummer* är från förklaringen *gatunummer*.</span><span class="sxs-lookup"><span data-stu-id="e7779-175">For the sample, configure the proximity setting so that we can define the range of the number of tokens the *Phone number* explanation is from the *Street address number* explanation.</span></span>

<span data-ttu-id="e7779-176">Du bör se att det minsta intervallet är "0" eftersom det inte finns några tokens mellan telefonnumret och gatunumret.</span><span class="sxs-lookup"><span data-stu-id="e7779-176">You should see that the minimum range is "0" since there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="e7779-177">För vissa telefonnummer i urvalsdokumenten läggs emellertid till *(mobil)*.</span><span class="sxs-lookup"><span data-stu-id="e7779-177">However, some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="e7779-178">Viktor Magnusson</span><span class="sxs-lookup"><span data-stu-id="e7779-178">Nestor Wilke</span></span><br>
<span data-ttu-id="e7779-179">111-111-1111 (mobil)</span><span class="sxs-lookup"><span data-stu-id="e7779-179">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="e7779-180">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="e7779-180">One Microsoft Way</span></span><br>
<span data-ttu-id="e7779-181">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="e7779-181">Redmond, WA 98034</span></span><br>

<span data-ttu-id="e7779-182">Det finns tre tokens i *(mobil)*:</span><span class="sxs-lookup"><span data-stu-id="e7779-182">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="e7779-183">Fras</span><span class="sxs-lookup"><span data-stu-id="e7779-183">Phrase</span></span>|<span data-ttu-id="e7779-184">Antal tokens</span><span class="sxs-lookup"><span data-stu-id="e7779-184">Token count</span></span>|
|--|--|
|<span data-ttu-id="e7779-185">(</span><span class="sxs-lookup"><span data-stu-id="e7779-185">(</span></span>|<span data-ttu-id="e7779-186">1</span><span class="sxs-lookup"><span data-stu-id="e7779-186">1</span></span>|
|<span data-ttu-id="e7779-187">mobil</span><span class="sxs-lookup"><span data-stu-id="e7779-187">mobile</span></span>|<span data-ttu-id="e7779-188">2</span><span class="sxs-lookup"><span data-stu-id="e7779-188">2</span></span>|
|<span data-ttu-id="e7779-189">)</span><span class="sxs-lookup"><span data-stu-id="e7779-189">)</span></span>|<span data-ttu-id="e7779-190">3</span><span class="sxs-lookup"><span data-stu-id="e7779-190">3</span></span>|

<span data-ttu-id="e7779-191">Konfigurera inställningen för närhet så att den har ett område med 0 till 3.</span><span class="sxs-lookup"><span data-stu-id="e7779-191">Configure the proximity setting to have a range of 0 through 3.</span></span>

   ![Exempel på närhet](../media/content-understanding/proximity-example.png)</br>

## <a name="use-explanation-templates"></a><span data-ttu-id="e7779-193">Använda förklaringsmallar</span><span class="sxs-lookup"><span data-stu-id="e7779-193">Use explanation templates</span></span>

<span data-ttu-id="e7779-194">Även om du kan lägga till olika mönsterlistvärden för dina förklaringar manuellt kan det vara mycket enklare att använda de färdiga mallar som har skapat år dig i förklaringsbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="e7779-194">While you can manually add various pattern list values for your explanation, it can be much easier to use the pre-created templates provided to you in the explanation library.</span></span>

<span data-ttu-id="e7779-195">I stället för att manuellt lägga till alla variationer för *datum* kan du använda mönsterlistmallen för *datum*, som redan har ett antal mönsterlistvärden:</span><span class="sxs-lookup"><span data-stu-id="e7779-195">For example, instead of manually adding all the variations for *Date*, you can use the pattern list template for *Date*, that already includes a number of pattern lists values:</span></span></br>

   ![Förklaringsbiblioteket](../media/content-understanding/explanation-template.png)</br>
 
<span data-ttu-id="e7779-197">I förklaringsbiblioteket finns flera vanliga förklaringar för mönsterlistor, t. ex.:</span><span class="sxs-lookup"><span data-stu-id="e7779-197">The explanation library includes a number of commonly used pattern list explanations, including:</span></span></br>

- <span data-ttu-id="e7779-198">Datum</span><span class="sxs-lookup"><span data-stu-id="e7779-198">Date</span></span></br>
- <span data-ttu-id="e7779-199">Datum (numeriskt)</span><span class="sxs-lookup"><span data-stu-id="e7779-199">Date (numeric)</span></span></br>
- <span data-ttu-id="e7779-200">Tid</span><span class="sxs-lookup"><span data-stu-id="e7779-200">Time</span></span></br>
- <span data-ttu-id="e7779-201">Siffra</span><span class="sxs-lookup"><span data-stu-id="e7779-201">Number</span></span></br>
- <span data-ttu-id="e7779-202">Telefonnummer</span><span class="sxs-lookup"><span data-stu-id="e7779-202">Phone number</span></span></br>
- <span data-ttu-id="e7779-203">Postnummer</span><span class="sxs-lookup"><span data-stu-id="e7779-203">Zip code</span></span></br>
- <span data-ttu-id="e7779-204">Första ord i mening</span><span class="sxs-lookup"><span data-stu-id="e7779-204">First word of sentence</span></span></br>
- <span data-ttu-id="e7779-205">Kontokort</span><span class="sxs-lookup"><span data-stu-id="e7779-205">Credit card</span></span></br>
- <span data-ttu-id="e7779-206">Personnummer</span><span class="sxs-lookup"><span data-stu-id="e7779-206">Social security number</span></span></br>

<span data-ttu-id="e7779-207">Observera att förklaringsbiblioteket även innehåller mallar för frasllistförklaringar, t. ex.:</span><span class="sxs-lookup"><span data-stu-id="e7779-207">Note that the explanation library also includes templates for phrase list explanations as well, including:</span></span>
- <span data-ttu-id="e7779-208">Slutet av meningen</span><span class="sxs-lookup"><span data-stu-id="e7779-208">End of sentence</span></span>
- <span data-ttu-id="e7779-209">Valuta</span><span class="sxs-lookup"><span data-stu-id="e7779-209">Currency</span></span>

#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="e7779-210">Använda en mall från förklaringsbiblioteket</span><span class="sxs-lookup"><span data-stu-id="e7779-210">To use a template from the explanation library</span></span>

1. <span data-ttu-id="e7779-211">Välj **Ny** i avsnittet **Förklaringar** på modellens sida **Träna** och välj **Från en mall**.</span><span class="sxs-lookup"><span data-stu-id="e7779-211">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span></br>

   ![Skapa från mall](../media/content-understanding/from-template.png)</br>

2.  <span data-ttu-id="e7779-213">På sidan **Förklaringsmallar** väljer du den förklaring du vill använda och väljer sedan **Lägga till**.</span><span class="sxs-lookup"><span data-stu-id="e7779-213">On the **Explanation templates** page, select the explanation you want to use, and then select **Add**.</span></span></br>

       ![Välj en mall](../media/content-understanding/phone-template.png)</br>

3. <span data-ttu-id="e7779-215">Informationen för den mall som du valde visas på sidan **Skapa en förklaring**.</span><span class="sxs-lookup"><span data-stu-id="e7779-215">The information for the template you selected will display on the **Create an explanation** page.</span></span> <span data-ttu-id="e7779-216">Om det behövs kan du redigera namnet på förklaringen och lägga till eller ta bort objekt från mönsterlistan.</span><span class="sxs-lookup"><span data-stu-id="e7779-216">If needed, edit the explanation name, and add or remove items from the pattern list.</span></span> </br> 

   ![Redigera mall](../media/content-understanding/phone-template-live.png)</br>

4. <span data-ttu-id="e7779-218">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="e7779-218">When finished, select **Save**.</span></span>
