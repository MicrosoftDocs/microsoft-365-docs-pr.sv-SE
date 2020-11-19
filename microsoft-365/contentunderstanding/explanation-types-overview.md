---
title: Förklaringstyper
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Mer information om olika typer av förklaringar i Microsoft SharePoint Syntex
ms.openlocfilehash: f01529199bf4dea0a14c7dc30b39fcaa5078931b
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087649"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="e92ef-103">Introduktion till förklaringstyper</span><span class="sxs-lookup"><span data-stu-id="e92ef-103">Introduction to explanation types</span></span>

<span data-ttu-id="e92ef-p101">Förklaringar används för att definiera den information som du vill använda för att ge etiketter och utdrag i dina modeller för dokumenttolkning i Microsoft SharePoint Syntex. När du skapar en förklaring måste du välja en förklaringstyp. Den här artikeln hjälper dig förstå olika förklaringstyper och hur de används.</span><span class="sxs-lookup"><span data-stu-id="e92ef-p101">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex. When creating an explanation, you need to select an explanation type. This article helps you understand the different explanation types and how they are used.</span></span> 

   ![Förklaringstyper](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="e92ef-108">Följande förklaringstyper är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="e92ef-108">These explanation types are available:</span></span>

- <span data-ttu-id="e92ef-p102">**Fraslista**: lista med ord, fraser, siffror eller andra tecken som du kan använda i det dokument eller den information du extraherar. Till exempel, textsträngen **Hänvisande läkare** är i alla medicinska referensdokument som du identifierar.</span><span class="sxs-lookup"><span data-stu-id="e92ef-p102">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting. For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span></br>

- <span data-ttu-id="e92ef-p103">**Mönsterlista**: listar mönster med siffror, bokstäver eller andra tecken som du kan använda för att identifiera den information som du extraherar. Du kan till exempel extrahera hämvisande läkarens **telefonnumret** alla medicinska referensdokument som du identifierar..</span><span class="sxs-lookup"><span data-stu-id="e92ef-p103">**Pattern list**: List patterns of numbers, letters, or other characters that you can use to identify the information that you are extracting. For example, you can extract the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span></br>

- <span data-ttu-id="e92ef-p104">**Närhet**: beskriver hur nära förklaringar är för varandra. Till exempel: en *gatunummer* mönsterlista går direkt före *gatu namn* fraslistan, utan tokens i mitten (du får lära dig mer om tokens senare i den här artikeln).Med närhetstypen måste du ha minst två förklaringar i modellen, annars är alternativet inaktiverat.</span><span class="sxs-lookup"><span data-stu-id="e92ef-p104">**Proximity**: Describes how close explanations are to each other. For example, a *street number* pattern list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article). Using the proximity type requires you to have at least two explanations in your model or the option will be disabled.</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="e92ef-116">Fraslista</span><span class="sxs-lookup"><span data-stu-id="e92ef-116">Phrase list</span></span>

<span data-ttu-id="e92ef-p105">Förklaringstypen fraslista används vanligtvis för att identifiera och klassificera ett dokument via modellen.Så som det beskrivs i exemplet med etikett för *Hänvisande läkare* är det en sträng med ord, fraser, siffror eller tecken är konsekventa i de dokument som du identifierar.</span><span class="sxs-lookup"><span data-stu-id="e92ef-p105">A phrase list explanation type is typically used to identify and classify a document through your model. As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="e92ef-p106">Även om det inte är obligatoriskt kan du få mer framgång med din förklaring om frasen du hämtar finns på en konsekvent plats i ditt dokument. Till exempel kan etiketten *Hänvisande läkare* konsekvent finnas i det första stycket i dokumentet.</span><span class="sxs-lookup"><span data-stu-id="e92ef-p106">While not a requirement, you can achieve better success with your explanation if the phrase you are capturing is located in a consistent location in your document. For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span>

<span data-ttu-id="e92ef-121">Om skifteslägeskänslighet är obligatorisk för att identifiera din etikett tillåter användning av fraslista dig att ange det i förklaringen genom att markera kryssrutan **Endast exakta versaler**.</span><span class="sxs-lookup"><span data-stu-id="e92ef-121">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

   ![Skifteslägeskänslighet](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a><span data-ttu-id="e92ef-123">Mönsterlistor</span><span class="sxs-lookup"><span data-stu-id="e92ef-123">Pattern lists</span></span>

<span data-ttu-id="e92ef-p107">Typen mönsterlista är särskilt användbar när du skapar en förklaring som identifierar och hämtar information från ett dokument. Den visas vanligtvis i olika format, till exempel datum, telefonnummer och kreditkortsnummer. Ett datum kan till exempel visas i flera olika format (1/1 2020, 2020-01-01, 1 januari 2020 osv.). Genom att definiera en mönsterlista blir förklaringen mer effektiv genom att fånga alla möjliga variationer i de data som du försöker identifiera och extrahera.</span><span class="sxs-lookup"><span data-stu-id="e92ef-p107">A pattern list type is especially useful when you create an explanation that identifies and extracts information from a document. It is typically presented in different formats, such as dates, phone numbers, and credit card numbers. For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.). Defining a pattern list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="e92ef-p108">För exemplet **Telefonnummer** extraheras telefonnumret till varje hänvisande läkare från alla medicinska referensdokument som modellen identifierar. När du skapar förklaringen väljer du typen mönsterlista för att tillåta de olika format som du kan förvänta dig returneras.</span><span class="sxs-lookup"><span data-stu-id="e92ef-p108">For the **Phone number** example, you extract the phone number for each referring doctor from all Medical Referral documents that the model identifies. When you create the explanation, select the Pattern list type to allow the different formats that you may expect to be returned.</span></span>

   ![Mönsterlista för telefonnummer](../media/content-understanding/pattern-list.png)

<span data-ttu-id="e92ef-131">I det här exemplet väljer du kryssrutan **Alla siffror mellan 0-9** för att känna igen alla "0"-värden som används i mönsterlistan som alla siffror mellan 0 och 9.</span><span class="sxs-lookup"><span data-stu-id="e92ef-131">For this example, select the **Any digit from 0-9** checkbox to recognize each "0" value used in your pattern list to be any digit from 0 through 9.</span></span>

   ![Alla siffror mellan 0-9](../media/content-understanding/digit-identity.png)

<span data-ttu-id="e92ef-133">Om du på liknande sätt skapar en mönsterlista som innehåller texttecken markerar du kryssrutan **Alla bokstäver mellan a-ö** för att känna igen alla "a"-tecken som används i mönsterlistan som alla tecken mellan "a" till "ö".</span><span class="sxs-lookup"><span data-stu-id="e92ef-133">Similarly, if you create a pattern list that includes text characters, select the **Any letter from a-z** checkbox to recognize each "a" character used in the pattern list to be any character from "a" to "z".</span></span>

<span data-ttu-id="e92ef-134">Om du till exempel skapar en mönsterlista för **Datum** och vill se till att ett datumformat som *1 januari 2020* känns igen måste du:</span><span class="sxs-lookup"><span data-stu-id="e92ef-134">For example, if you create a **Date** pattern list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="e92ef-135">Lägga till *0 aaaaaaa 0000* och *00 aaaaaaa 0000* i din mönsterlista.</span><span class="sxs-lookup"><span data-stu-id="e92ef-135">Add *aaa 0, 0000* and *aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="e92ef-136">Kontrollera att **Valfri bokstav från a-ö** också är markerad.</span><span class="sxs-lookup"><span data-stu-id="e92ef-136">Make sure that **Any letter from a-z** is also selected.</span></span>

   ![Valfri bokstav från a till ö](../media/content-understanding/any-letter.png)

<span data-ttu-id="e92ef-p109">Om du även har krav på stor begynnelsebokstav i din mönsterlista kan du välja kryssrutan **Endast exakta versaler**. Om du kräver att den första bokstaven i månaden för datumexemplet har stor begynnelsebokstav behöver du:</span><span class="sxs-lookup"><span data-stu-id="e92ef-p109">Additionally, if you have capitalization requirements in your pattern list, you have the option to select the **Only exact capitalization** checkbox. For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="e92ef-140">Lägga till *0 Aaaaaaa 0000* och *00 Aaaaaaa 0000* i din mönsterlista.</span><span class="sxs-lookup"><span data-stu-id="e92ef-140">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="e92ef-141">Kontrollera att **Endast exakta versaler** också är markerad.</span><span class="sxs-lookup"><span data-stu-id="e92ef-141">Make sure that **Only exact capitalization** is also selected.</span></span>

   ![Endast exakta versaler](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="e92ef-143">I stället för att manuellt skapa en förklaring för en mönsterlista kan du använda [förklaringsbiblioteket](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) för att använda färdiga mönsterlistmallar för vanliga mönsterlistor, till exempel *datum*, *telefonnummer*, *kreditkortsnummer* osv.</span><span class="sxs-lookup"><span data-stu-id="e92ef-143">Instead of manually creating a pattern list explanation, use the [explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) to use pattern list templates for a common pattern list, such as *date*, *phone number*, *credit card number*, etc.</span></span>

## <a name="proximity"></a><span data-ttu-id="e92ef-144">Närhet</span><span class="sxs-lookup"><span data-stu-id="e92ef-144">Proximity</span></span> 

<span data-ttu-id="e92ef-p110">Typen närhetsförklaring hjälper modellen att lättare identifiera data genom att definiera hur nära ett annat data kommer till den. I din modell har du till exempel två förklaringar som etiketterar både kundens *gatunummer* och *telefonnummer*.</span><span class="sxs-lookup"><span data-stu-id="e92ef-p110">The proximity explanation type helps your model identify data by defining how close another piece of data is to it. For example, in your model say you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="e92ef-147">Notera att kundens telefonnummer alltid visas före gatunumret.</span><span class="sxs-lookup"><span data-stu-id="e92ef-147">Notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="e92ef-148">Christian Forsberg</span><span class="sxs-lookup"><span data-stu-id="e92ef-148">Alex Wilburn</span></span><br>
<span data-ttu-id="e92ef-149">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="e92ef-149">555-555-5555</span></span><br>
<span data-ttu-id="e92ef-150">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="e92ef-150">One Microsoft Way</span></span><br>
<span data-ttu-id="e92ef-151">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="e92ef-151">Redmond, WA 98034</span></span><br>

<span data-ttu-id="e92ef-152">Använd närhetsförklaringen för att definiera hur långt bort det är för att bättre identifiera gatunumret i dina dokument.</span><span class="sxs-lookup"><span data-stu-id="e92ef-152">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

   ![Närhetsförklaring](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a><span data-ttu-id="e92ef-154">Vad är tokens?</span><span class="sxs-lookup"><span data-stu-id="e92ef-154">What are tokens?</span></span>

<span data-ttu-id="e92ef-p111">Om du vill använda förklaringstypen närhet måste du förstå vad en token är eftersom antalet tokens är hur närhetsförklaringen mäter avståndet från en förklaring till en annan. En token är ett sammanhängande intervall (exklusive blanksteg eller skiljetecken) för bokstäver och siffror.</span><span class="sxs-lookup"><span data-stu-id="e92ef-p111">In order to use the proximity explanation type, you need to understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another. A token is a continuous span (not including spaces or punctuation) of letters and numbers.</span></span> 

<span data-ttu-id="e92ef-157">I tabellen nedan visas exempel på hur du kan ta reda på antalet tokens i en fras.</span><span class="sxs-lookup"><span data-stu-id="e92ef-157">The following table shows examples for how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="e92ef-158">Fras</span><span class="sxs-lookup"><span data-stu-id="e92ef-158">Phrase</span></span>|<span data-ttu-id="e92ef-159">Antal tokens</span><span class="sxs-lookup"><span data-stu-id="e92ef-159">Number of tokens</span></span>|<span data-ttu-id="e92ef-160">Förklaring</span><span class="sxs-lookup"><span data-stu-id="e92ef-160">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="e92ef-161">1</span><span class="sxs-lookup"><span data-stu-id="e92ef-161">1</span></span>|<span data-ttu-id="e92ef-162">Ett enstaka ord utan skiljetecken eller blanksteg.</span><span class="sxs-lookup"><span data-stu-id="e92ef-162">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="e92ef-163">1</span><span class="sxs-lookup"><span data-stu-id="e92ef-163">1</span></span>|<span data-ttu-id="e92ef-p112">Ett lokaliseringsnummer för posten. Det kan innehålla siffror och bokstäver men inga skiljetecken.</span><span class="sxs-lookup"><span data-stu-id="e92ef-p112">A record locator number. It may include numbers and letters, but does not have punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="e92ef-166">5</span><span class="sxs-lookup"><span data-stu-id="e92ef-166">5</span></span>|<span data-ttu-id="e92ef-p113">Ett telefonnummer. Varje skiljetecken är ett enda token, så `425-555-5555` är 5 tokens:</span><span class="sxs-lookup"><span data-stu-id="e92ef-p113">A phone number. Each punctuation mark is a single token, so `425-555-5555` is 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="e92ef-169">7</span><span class="sxs-lookup"><span data-stu-id="e92ef-169">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="e92ef-170">Konfigurera typen närhetsförklaring</span><span class="sxs-lookup"><span data-stu-id="e92ef-170">Configure the proximity explanation type</span></span>

<span data-ttu-id="e92ef-p114">Konfigurera inställningen närhet för detta exempel att definiera intervallet för antalet tokens i förklaringen för *Telefonnummer* från förklaringen *Gatunummer*.Notera att det minsta intervallet är "0" eftersom det inte finns några tokens mellan telefonnumret och gatunumret.</span><span class="sxs-lookup"><span data-stu-id="e92ef-p114">For the example, configure the proximity setting to define the range of the number of tokens in the *Phone number* explanation from the *Street address number* explanation. Notice that the minimum range is "0", because there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="e92ef-173">Men vissa telefonnummer i urvalsdokumenten har tillägget *(mobil)*.</span><span class="sxs-lookup"><span data-stu-id="e92ef-173">But some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="e92ef-174">Viktor Magnusson</span><span class="sxs-lookup"><span data-stu-id="e92ef-174">Nestor Wilke</span></span><br>
<span data-ttu-id="e92ef-175">111-111-1111 (mobil)</span><span class="sxs-lookup"><span data-stu-id="e92ef-175">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="e92ef-176">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="e92ef-176">One Microsoft Way</span></span><br>
<span data-ttu-id="e92ef-177">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="e92ef-177">Redmond, WA 98034</span></span><br>

<span data-ttu-id="e92ef-178">Det finns tre tokens i *(mobil)*:</span><span class="sxs-lookup"><span data-stu-id="e92ef-178">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="e92ef-179">Fras</span><span class="sxs-lookup"><span data-stu-id="e92ef-179">Phrase</span></span>|<span data-ttu-id="e92ef-180">Antal tokens</span><span class="sxs-lookup"><span data-stu-id="e92ef-180">Token count</span></span>|
|--|--|
|<span data-ttu-id="e92ef-181">(</span><span class="sxs-lookup"><span data-stu-id="e92ef-181">(</span></span>|<span data-ttu-id="e92ef-182">1</span><span class="sxs-lookup"><span data-stu-id="e92ef-182">1</span></span>|
|<span data-ttu-id="e92ef-183">mobil</span><span class="sxs-lookup"><span data-stu-id="e92ef-183">mobile</span></span>|<span data-ttu-id="e92ef-184">2</span><span class="sxs-lookup"><span data-stu-id="e92ef-184">2</span></span>|
|<span data-ttu-id="e92ef-185">)</span><span class="sxs-lookup"><span data-stu-id="e92ef-185">)</span></span>|<span data-ttu-id="e92ef-186">3</span><span class="sxs-lookup"><span data-stu-id="e92ef-186">3</span></span>|

<span data-ttu-id="e92ef-187">Konfigurera inställningen för närhet så att den har ett område med 0 till 3.</span><span class="sxs-lookup"><span data-stu-id="e92ef-187">Configure the proximity setting to have a range of 0 through 3.</span></span>

   ![Exempel på närhet](../media/content-understanding/proximity-example.png)</br>

## <a name="use-explanation-templates"></a><span data-ttu-id="e92ef-189">Använda förklaringsmallar</span><span class="sxs-lookup"><span data-stu-id="e92ef-189">Use explanation templates</span></span>

<span data-ttu-id="e92ef-190">Även om du kan lägga till olika mönsterlistvärden för dina förklaringar manuellt kan det vara mycket enklare att använda de färdiga mallar som har skapats åt dig i förklaringsbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="e92ef-190">While you can manually add various pattern list values for your explanation, it can be easier to use the templates provided to you in the explanation library.</span></span>

<span data-ttu-id="e92ef-191">I stället för att exempelvis manuellt lägga till alla variationer för *Datum* kan du använda mönsterlistmallen för *Datum*, som redan har ett antal mönsterlistvärden:</span><span class="sxs-lookup"><span data-stu-id="e92ef-191">For example, instead of manually adding all the variations for *Date*, you can use the pattern list template for *Date* as it already includes a number of pattern lists values:</span></span></br>

   ![Förklaringsbiblioteket](../media/content-understanding/explanation-template.png)</br>
 
<span data-ttu-id="e92ef-193">I förklaringsbiblioteket finns flera vanliga förklaringar för mönsterlistor, till exempel:</span><span class="sxs-lookup"><span data-stu-id="e92ef-193">The explanation library includes commonly used pattern list explanations, including:</span></span></br>

- <span data-ttu-id="e92ef-194">Datum</span><span class="sxs-lookup"><span data-stu-id="e92ef-194">Date</span></span></br>
- <span data-ttu-id="e92ef-195">Datum (numeriskt)</span><span class="sxs-lookup"><span data-stu-id="e92ef-195">Date (numeric)</span></span></br>
- <span data-ttu-id="e92ef-196">Tid</span><span class="sxs-lookup"><span data-stu-id="e92ef-196">Time</span></span></br>
- <span data-ttu-id="e92ef-197">Siffra</span><span class="sxs-lookup"><span data-stu-id="e92ef-197">Number</span></span></br>
- <span data-ttu-id="e92ef-198">Telefonnummer</span><span class="sxs-lookup"><span data-stu-id="e92ef-198">Phone number</span></span></br>
- <span data-ttu-id="e92ef-199">Postnummer</span><span class="sxs-lookup"><span data-stu-id="e92ef-199">Zip code</span></span></br>
- <span data-ttu-id="e92ef-200">Första ord i mening</span><span class="sxs-lookup"><span data-stu-id="e92ef-200">First word of sentence</span></span></br>
- <span data-ttu-id="e92ef-201">Kontokort</span><span class="sxs-lookup"><span data-stu-id="e92ef-201">Credit card</span></span></br>
- <span data-ttu-id="e92ef-202">Personnummer</span><span class="sxs-lookup"><span data-stu-id="e92ef-202">Social security number</span></span></br>

<span data-ttu-id="e92ef-203">Observera att förklaringsbiblioteket även innehåller mallar för fraslistförklaringar:</span><span class="sxs-lookup"><span data-stu-id="e92ef-203">Note that the explanation library also includes templates for phrase list explanations:</span></span>
- <span data-ttu-id="e92ef-204">Slutet av meningen</span><span class="sxs-lookup"><span data-stu-id="e92ef-204">End of sentence</span></span>
- <span data-ttu-id="e92ef-205">Valuta</span><span class="sxs-lookup"><span data-stu-id="e92ef-205">Currency</span></span>

#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="e92ef-206">Använda en mall från förklaringsbiblioteket</span><span class="sxs-lookup"><span data-stu-id="e92ef-206">To use a template from the explanation library</span></span>

1. <span data-ttu-id="e92ef-207">Välj **Ny** i avsnittet **Förklaringar** på modellens sida **Träna** och välj **Från en mall**.</span><span class="sxs-lookup"><span data-stu-id="e92ef-207">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span></br>

   ![Skapa från mall](../media/content-understanding/from-template.png)</br>

2.  <span data-ttu-id="e92ef-209">På sidan **Förklaringsmallar** väljer du den förklaring du vill använda och väljer sedan **Lägga till**.</span><span class="sxs-lookup"><span data-stu-id="e92ef-209">On the **Explanation templates** page, select the explanation you want to use, then select **Add**.</span></span></br>

       ![Välj en mall](../media/content-understanding/phone-template.png)</br>

3. <span data-ttu-id="e92ef-p115">Informationen för den mall som du valde visas på sidan **Skapa en förklaring**. Om det behövs kan du redigera namnet på förklaringen och lägga till eller ta bort objekt från mönsterlistan.</span><span class="sxs-lookup"><span data-stu-id="e92ef-p115">The information for the template you selected displays on the **Create an explanation** page. If needed, edit the explanation name and add or remove items from the pattern list. </span></span></br> 

   ![Redigera mall](../media/content-understanding/phone-template-live.png)</br>

4. <span data-ttu-id="e92ef-214">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="e92ef-214">When finished, select **Save**.</span></span>
