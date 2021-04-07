---
title: Förklaringstyper
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
description: Mer information om olika typer av förklaringar i Microsoft SharePoint Syntex
ms.openlocfilehash: a5404230a59d1740a2b855527229a7aca92195a8
ms.sourcegitcommit: dc1ac43a57fac6f57438859dd668f927d94fdf34
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/07/2021
ms.locfileid: "51604411"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="100a6-103">Introduktion till förklaringstyper</span><span class="sxs-lookup"><span data-stu-id="100a6-103">Introduction to explanation types</span></span>

<span data-ttu-id="100a6-104">Förklaringar används för att definiera den information som du vill använda för att ge etiketter och utdrag i dina modeller för dokumenttolkning i Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="100a6-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="100a6-105">När du skapar en förklaring måste du välja en förklaringstyp.</span><span class="sxs-lookup"><span data-stu-id="100a6-105">When creating an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="100a6-106">Den här artikeln hjälper dig förstå olika förklaringstyper och hur de används.</span><span class="sxs-lookup"><span data-stu-id="100a6-106">This article helps you understand the different explanation types and how they are used.</span></span> 

![Förklaringstyper](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="100a6-108">Följande förklaringstyper är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="100a6-108">These explanation types are available:</span></span>

- <span data-ttu-id="100a6-109">**Fraslista**: lista med ord, fraser, siffror eller andra tecken som du kan använda i det dokument eller den information du extraherar.</span><span class="sxs-lookup"><span data-stu-id="100a6-109">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="100a6-110">Exempel: textsträngen **Hänvisande läkare** finns i alla medicinska referensdokument som du identifierar.</span><span class="sxs-lookup"><span data-stu-id="100a6-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span> <span data-ttu-id="100a6-111">Eller den hänvisande läkarens **Telefonnummer** i alla medicinsk referensdokument som du identifierar.</span><span class="sxs-lookup"><span data-stu-id="100a6-111">Or the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span>

- <span data-ttu-id="100a6-112">**Närhet**: beskriver hur nära förklaringar är med varandra.</span><span class="sxs-lookup"><span data-stu-id="100a6-112">**Proximity**: Describes how close explanations are to each other.</span></span> <span data-ttu-id="100a6-113">Till exempel: en fraslista för *gatunummer* ska ligga precis innan fraslistan för *gatunamn* utan tokens emellan (du får lära dig mer om tokens senare i den här artikeln).</span><span class="sxs-lookup"><span data-stu-id="100a6-113">For example, a *street number* phrase list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="100a6-114">Med närhetstypen måste du ha minst två förklaringar i modellen, annars är alternativet inaktiverat.</span><span class="sxs-lookup"><span data-stu-id="100a6-114">Using the proximity type requires you to have at least two explanations in your model or the option will be disabled.</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="100a6-115">Fraslista</span><span class="sxs-lookup"><span data-stu-id="100a6-115">Phrase list</span></span>

<span data-ttu-id="100a6-116">Förklaringstypen fraslista används vanligtvis för att identifiera och klassificera ett dokument via modellen.</span><span class="sxs-lookup"><span data-stu-id="100a6-116">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="100a6-117">Så som det beskrivs i exemplet med etikett för *Hänvisande läkare* är det en sträng med ord, fraser, siffror eller tecken är konsekventa i de dokument som du identifierar.</span><span class="sxs-lookup"><span data-stu-id="100a6-117">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="100a6-118">Även om det inte är obligatoriskt kan du få mer framgång med din förklaring om frasen du hämtar finns på en konsekvent plats i ditt dokument.</span><span class="sxs-lookup"><span data-stu-id="100a6-118">While not a requirement, you can achieve better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="100a6-119">Till exempel kan etiketten *Hänvisande läkare* konsekvent finnas i det första stycket i dokumentet.</span><span class="sxs-lookup"><span data-stu-id="100a6-119">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span> <span data-ttu-id="100a6-120">Du kan också använda avancerad inställning för **[Konfigurera var fraser ska visas i dokumentet](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#configure-where-phrases-occur-in-the-document)** för att markera specifika områden där frasen finns, särskilt om det finns en möjlighet att frasen förekommer på flera platser i ditt dokument.</span><span class="sxs-lookup"><span data-stu-id="100a6-120">You can also use the **[Configure where phrases occur in the document](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#configure-where-phrases-occur-in-the-document)** advanced setting to select specific areas where the phrase is located, especially if there is a chance that the phrase might occur in multiple locations in your document.</span></span>

<span data-ttu-id="100a6-121">Om skifteslägeskänslighet är obligatorisk för att identifiera din etikett tillåter användning av fraslista dig att ange det i förklaringen genom att markera kryssrutan **Endast exakta versaler**.</span><span class="sxs-lookup"><span data-stu-id="100a6-121">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

![Skifteslägeskänslighet](../media/content-understanding/case-sensitivity.png) 

<span data-ttu-id="100a6-123">En frastyp är särskilt användbar när du skapar en förklaring som identifierar och extraherar information i olika format, till exempel datum, telefonnummer och kreditkortsnummer.</span><span class="sxs-lookup"><span data-stu-id="100a6-123">A phrase type is especially useful when you create an explanation that identifies and extracts information in different formats, such as dates, phone numbers, and credit card numbers.</span></span> <span data-ttu-id="100a6-124">Till exempel kan ett datum visas i flera olika format (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, o.s.v.).</span><span class="sxs-lookup"><span data-stu-id="100a6-124">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="100a6-125">Genom att definiera en fraslista blir förklaringen mer effektiv genom att fånga alla möjliga variationer i de data som du försöker identifiera och extrahera.</span><span class="sxs-lookup"><span data-stu-id="100a6-125">Defining a phrase list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="100a6-126">För exemplet **Telefonnummer** extraherar du telefonnumret till varje hänvisande läkare från alla medicinska referensdokument som modellen identifierar.</span><span class="sxs-lookup"><span data-stu-id="100a6-126">For the **Phone number** example, you extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="100a6-127">När du skapar förklaringen skriver du de olika formaten som ett telefonnummer kan visa i ditt dokument så att du kan fånga upp möjliga variationer.</span><span class="sxs-lookup"><span data-stu-id="100a6-127">When you create the explanation, type the different formats a phone number might display in your document so that you are able to capture possible variations.</span></span> 

![Mönster för telefonnummerfraser](../media/content-understanding/pattern-list.png)

<span data-ttu-id="100a6-129">I det här exemplet i **Avancerad Inställningar** väljer du **Valfri siffra mellan 0-9** i kryssrutan för att känna igen alla "0"-värden som används i din fraslista som valfri siffra mellan 0 och 9.</span><span class="sxs-lookup"><span data-stu-id="100a6-129">For this example, in **Advanced Settings** select the **Any digit from 0-9** checkbox to recognize each "0" value used in your phrase list to be any digit from 0 through 9.</span></span>

![Valfri siffra mellan 0-9](../media/content-understanding/digit-identity.png)

<span data-ttu-id="100a6-131">Om du på liknande sätt skapar en fraslista som innehåller texttecken markerar du kryssrutan **Valfri bokstav mellan a-ö** för att känna igen alla "a"-tecken som används i fraslistan att vara valfri tecken mellan "a" till "ö".</span><span class="sxs-lookup"><span data-stu-id="100a6-131">Similarly, if you create a phrase list that includes text characters, select the **Any letter from a-z** checkbox to recognize each "a" character used in the phrase list to be any character from "a" to "z".</span></span>

<span data-ttu-id="100a6-132">Om du, till exempel, skapar en fraslista för **Datum** och vill se till att ett datumformat som *1 januari 2020* känns igen, måste du:</span><span class="sxs-lookup"><span data-stu-id="100a6-132">For example, if you create a **Date** phrase list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="100a6-133">Lägga till *0 aaaaaaa 0000* och *00 aaaaaaa 0000* i din fraslista.</span><span class="sxs-lookup"><span data-stu-id="100a6-133">Add *aaa 0, 0000* and *aaa 00, 0000* to your phrase list.</span></span>
- <span data-ttu-id="100a6-134">Kontrollera att **Valfri bokstav från a-ö** också är markerad.</span><span class="sxs-lookup"><span data-stu-id="100a6-134">Make sure that **Any letter from a-z** is also selected.</span></span>

![Valfri bokstav från a till ö](../media/content-understanding/any-letter.png)

<span data-ttu-id="100a6-136">Om du även har kapitaliseringskrav i din fraslista kan du välja kryssrutan **Endast exakta kapitalisering**.</span><span class="sxs-lookup"><span data-stu-id="100a6-136">Additionally, if you have capitalization requirements in your phrase list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="100a6-137">Om du kräver att den första bokstaven i månaden för datumexemplet ska kapitaliseras behöver du:</span><span class="sxs-lookup"><span data-stu-id="100a6-137">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="100a6-138">Lägga till *Aaa 0, 0000* och *Aaa 00 0000* till din fraslista.</span><span class="sxs-lookup"><span data-stu-id="100a6-138">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your phrase list.</span></span>
- <span data-ttu-id="100a6-139">Kontrollera att **Endast exakta versaler** också är markerad.</span><span class="sxs-lookup"><span data-stu-id="100a6-139">Make sure that **Only exact capitalization** is also selected.</span></span>

![Endast exakta versaler](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="100a6-141">I stället för att manuellt skapa en förklaring för en fraslista kan du använda [förklaringsbiblioteket](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) för att använda mallar för en vanlig fraslista, till exempel *datum*, *telefonnummer*, *kreditkortsnummer* o.s.v.</span><span class="sxs-lookup"><span data-stu-id="100a6-141">Instead of manually creating a phrase list explanation, use the [explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) to use phrase list templates for a common phrase list, such as *date*, *phone number*, *credit card number*, etc.</span></span>

## <a name="proximity"></a><span data-ttu-id="100a6-142">Närhet</span><span class="sxs-lookup"><span data-stu-id="100a6-142">Proximity</span></span> 

<span data-ttu-id="100a6-143">Typen närhetsförklaring hjälper modellen att lättare identifiera data genom att definiera hur nära ett annat data kommer till den.</span><span class="sxs-lookup"><span data-stu-id="100a6-143">The proximity explanation type helps your model identify data by defining how close another piece of data is to it.</span></span> <span data-ttu-id="100a6-144">I din modell har du till exempel två förklaringar som etiketterar både kundens *gatunummer* och *telefonnummer*.</span><span class="sxs-lookup"><span data-stu-id="100a6-144">For example, in your model say you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="100a6-145">Notera att kundens telefonnummer alltid visas före gatunumret.</span><span class="sxs-lookup"><span data-stu-id="100a6-145">Notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="100a6-146">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="100a6-146">Alex Wilburn</span></span><br>
<span data-ttu-id="100a6-147">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="100a6-147">555-555-5555</span></span><br>
<span data-ttu-id="100a6-148">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="100a6-148">One Microsoft Way</span></span><br>
<span data-ttu-id="100a6-149">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="100a6-149">Redmond, WA 98034</span></span><br>

<span data-ttu-id="100a6-150">Använd närhetsförklaringen för att definiera hur långt bort det är för att bättre identifiera gatunumret i dina dokument.</span><span class="sxs-lookup"><span data-stu-id="100a6-150">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

![Närhetsförklaring](../media/content-understanding/proximity.png)

#### <a name="what-are-tokens"></a><span data-ttu-id="100a6-152">Vad är tokens?</span><span class="sxs-lookup"><span data-stu-id="100a6-152">What are tokens?</span></span>

<span data-ttu-id="100a6-153">Om du vill använda närhetsförklaringstypen behöver du förstå vad en token är eftersom antalet tokens är hur närhetsförklaringen mäter avståndet från en förklaring till en annan.</span><span class="sxs-lookup"><span data-stu-id="100a6-153">In order to use the proximity explanation type, you need to understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span> <span data-ttu-id="100a6-154">En token är ett sammanhängande intervall (exklusive blanksteg eller skiljetecken) för bokstäver och siffror.</span><span class="sxs-lookup"><span data-stu-id="100a6-154">A token is a continuous span (not including spaces or punctuation) of letters and numbers.</span></span> 

<span data-ttu-id="100a6-155">I tabellen nedan visas exempel på hur du kan ta reda på antalet tokens i en fras.</span><span class="sxs-lookup"><span data-stu-id="100a6-155">The following table shows examples for how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="100a6-156">Fras</span><span class="sxs-lookup"><span data-stu-id="100a6-156">Phrase</span></span>|<span data-ttu-id="100a6-157">Antal tokens</span><span class="sxs-lookup"><span data-stu-id="100a6-157">Number of tokens</span></span>|<span data-ttu-id="100a6-158">Förklaring</span><span class="sxs-lookup"><span data-stu-id="100a6-158">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="100a6-159">1</span><span class="sxs-lookup"><span data-stu-id="100a6-159">1</span></span>|<span data-ttu-id="100a6-160">Ett enstaka ord utan skiljetecken eller blanksteg.</span><span class="sxs-lookup"><span data-stu-id="100a6-160">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="100a6-161">1</span><span class="sxs-lookup"><span data-stu-id="100a6-161">1</span></span>|<span data-ttu-id="100a6-162">Ett lokaliseringsnummer för posten.</span><span class="sxs-lookup"><span data-stu-id="100a6-162">A record locator number.</span></span> <span data-ttu-id="100a6-163">Det kan innehålla siffror och bokstäver men inga skiljetecken.</span><span class="sxs-lookup"><span data-stu-id="100a6-163">It may include numbers and letters, but does not have punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="100a6-164">5</span><span class="sxs-lookup"><span data-stu-id="100a6-164">5</span></span>|<span data-ttu-id="100a6-165">Ett telefonnummer.</span><span class="sxs-lookup"><span data-stu-id="100a6-165">A phone number.</span></span> <span data-ttu-id="100a6-166">Varje skiljetecken är ett enda token, så `425-555-5555` är 5 tokens:</span><span class="sxs-lookup"><span data-stu-id="100a6-166">Each punctuation mark is a single token, so `425-555-5555` is 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="100a6-167">7</span><span class="sxs-lookup"><span data-stu-id="100a6-167">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="100a6-168">Konfigurera typen närhetsförklaring</span><span class="sxs-lookup"><span data-stu-id="100a6-168">Configure the proximity explanation type</span></span>

<span data-ttu-id="100a6-169">Konfigurera inställningen närhet för detta exempel att definiera intervallet för antalet tokens i förklaringen för *Telefonnummer* från förklaringen *Gatunummer*.</span><span class="sxs-lookup"><span data-stu-id="100a6-169">For the example, configure the proximity setting to define the range of the number of tokens in the *Phone number* explanation from the *Street address number* explanation.</span></span> <span data-ttu-id="100a6-170">Notera att det minsta intervallet är "0" eftersom det inte finns några tokens mellan telefonnumret och gatunumret.</span><span class="sxs-lookup"><span data-stu-id="100a6-170">Notice that the minimum range is "0", because there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="100a6-171">Men vissa telefonnummer i urvalsdokumenten har tillägget *(mobil)*.</span><span class="sxs-lookup"><span data-stu-id="100a6-171">But some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="100a6-172">Viktor Magnusson</span><span class="sxs-lookup"><span data-stu-id="100a6-172">Nestor Wilke</span></span><br>
<span data-ttu-id="100a6-173">111-111-1111 (mobil)</span><span class="sxs-lookup"><span data-stu-id="100a6-173">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="100a6-174">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="100a6-174">One Microsoft Way</span></span><br>
<span data-ttu-id="100a6-175">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="100a6-175">Redmond, WA 98034</span></span><br>

<span data-ttu-id="100a6-176">Det finns tre tokens i *(mobil)*:</span><span class="sxs-lookup"><span data-stu-id="100a6-176">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="100a6-177">Fras</span><span class="sxs-lookup"><span data-stu-id="100a6-177">Phrase</span></span>|<span data-ttu-id="100a6-178">Antal tokens</span><span class="sxs-lookup"><span data-stu-id="100a6-178">Token count</span></span>|
|--|--|
|<span data-ttu-id="100a6-179">(</span><span class="sxs-lookup"><span data-stu-id="100a6-179">(</span></span>|<span data-ttu-id="100a6-180">1</span><span class="sxs-lookup"><span data-stu-id="100a6-180">1</span></span>|
|<span data-ttu-id="100a6-181">mobil</span><span class="sxs-lookup"><span data-stu-id="100a6-181">mobile</span></span>|<span data-ttu-id="100a6-182">2</span><span class="sxs-lookup"><span data-stu-id="100a6-182">2</span></span>|
|<span data-ttu-id="100a6-183">)</span><span class="sxs-lookup"><span data-stu-id="100a6-183">)</span></span>|<span data-ttu-id="100a6-184">3</span><span class="sxs-lookup"><span data-stu-id="100a6-184">3</span></span>|

<span data-ttu-id="100a6-185">Konfigurera inställningen för närhet så att den har ett område med 0 till 3.</span><span class="sxs-lookup"><span data-stu-id="100a6-185">Configure the proximity setting to have a range of 0 through 3.</span></span>

![Exempel på närhet](../media/content-understanding/proximity-example.png)


## <a name="configure-where-phrases-occur-in-the-document"></a><span data-ttu-id="100a6-187">Konfigurera var fraser förekommer i dokumentet</span><span class="sxs-lookup"><span data-stu-id="100a6-187">Configure where phrases occur in the document</span></span>

<span data-ttu-id="100a6-188">När du skapar en förklaring söks som standard hela dokumentet efter frasen du försöker extrahera.</span><span class="sxs-lookup"><span data-stu-id="100a6-188">When you create an explanation, by default the entire document is searched for the phrase you are trying to extract.</span></span> <span data-ttu-id="100a6-189">Du kan dock använda inställningen **Där fraserna förekommer** avancerade inställning för att hjälpa till att isolera en specifik plats i dokumentet som en fras förekommer på.</span><span class="sxs-lookup"><span data-stu-id="100a6-189">However, you can use the **Where these phrases occur** advanced setting to help in isolating a specific location in the document that a phrase occurs.</span></span> <span data-ttu-id="100a6-190">Detta är användbart i situationer där liknande förekomster av en fras kan förekomma någon annanstans i dokumentet, och du vill kontrollera att rätt förekomst är markerad.</span><span class="sxs-lookup"><span data-stu-id="100a6-190">This is useful in situations where similar instances of a phrase might appear somewhere else in the document, and you want to make sure that the correct one is selected.</span></span> <span data-ttu-id="100a6-191">Med hänvisning till vårt exempel på medicinsk remiss nämns alltid den **hänvisande läkaren** i första stycket i dokumentet.</span><span class="sxs-lookup"><span data-stu-id="100a6-191">Referring to our Medical Referral document example, the **Referring Doctor** is always mentioned in the first paragraph of the document.</span></span> <span data-ttu-id="100a6-192">Med inställningen Var dessa fraser förekommer kan du i det här exemplet konfigurera din förklaring så att den bara söker efter den här etiketten i början av dokumentet, eller på någon annan plats där den kan förekomma.</span><span class="sxs-lookup"><span data-stu-id="100a6-192">With the \*\*Where these phrases occur setting, in this example you can configure your explanation to search for this label only in the beginning section of the document, or any other location in which it might occur.</span></span>

![Var dessa fraser förekommer inställning](../media/content-understanding/phrase-location.png)

<span data-ttu-id="100a6-194">Du kan välja följande alternativ för den här inställningen:</span><span class="sxs-lookup"><span data-stu-id="100a6-194">You can choose the following options for this setting:</span></span>

- <span data-ttu-id="100a6-195">Var som helst i filen: Hela dokumentet söks efter frasen.</span><span class="sxs-lookup"><span data-stu-id="100a6-195">Anywhere in the file: The entire document is searched for the phrase.</span></span>

- <span data-ttu-id="100a6-196">Början av filen: Dokumentet genomsöks från början till frasen plats.</span><span class="sxs-lookup"><span data-stu-id="100a6-196">Beginning of the file:  The document is searched from the beginning to the phrase location.</span></span>

   ![Början på filen](../media/content-understanding/beginning-of-file.png)

    <span data-ttu-id="100a6-198">I visningsprogrammet kan du manuellt justera urvalsrutan så att den inkluderar platsen där fasen inträffar.</span><span class="sxs-lookup"><span data-stu-id="100a6-198">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="100a6-199">Den **slutpositionens** värde uppdateras för att visa antalet tokens som ditt valda område innehåller.</span><span class="sxs-lookup"><span data-stu-id="100a6-199">The **End position** value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="100a6-200">Observera att du också kan uppdatera slutpositionsvärdet för att justera det valda området.</span><span class="sxs-lookup"><span data-stu-id="100a6-200">Note that you can update the End position value as well to adjust the selected area.</span></span>

   ![Början på filens positionsruta](../media/content-understanding/beginning-box.png)

- <span data-ttu-id="100a6-202">Slutet av filen: Dokumentet genomsöks från slutet till frasens plats.</span><span class="sxs-lookup"><span data-stu-id="100a6-202">End of the file:  The document is searched from the end to the phrase location.</span></span>

   ![Slutet av filen](../media/content-understanding/end-of-file.png)

    <span data-ttu-id="100a6-204">I visningsprogrammet kan du manuellt justera urvalsrutan så att den inkluderar platsen där fasen inträffar.</span><span class="sxs-lookup"><span data-stu-id="100a6-204">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="100a6-205">Värdet **startposition** uppdateras för att visa antalet tokens som ditt valda område innehåller.</span><span class="sxs-lookup"><span data-stu-id="100a6-205">The **Starting position** value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="100a6-206">Observera att du också kan uppdatera startpositionens värde för att justera det markerade området.</span><span class="sxs-lookup"><span data-stu-id="100a6-206">Note that you can update the Starting position value as well to adjust the selected area.</span></span>

   ![Slutet på filens slutruta](../media/content-understanding/end-box.png)

- <span data-ttu-id="100a6-208">Anpassat intervall: Dokumentet genomsöks inom ett angivet intervall inom det för frasplatsen.</span><span class="sxs-lookup"><span data-stu-id="100a6-208">Custom range:  The document is searched in a specified range within the it for the phrase location.</span></span>

   ![Anpassat intervall](../media/content-understanding/custom-file.png)

    <span data-ttu-id="100a6-210">I visningsprogrammet kan du manuellt justera urvalsrutan så att den inkluderar platsen där fasen inträffar.</span><span class="sxs-lookup"><span data-stu-id="100a6-210">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="100a6-211">För den här inställningen måste du välja en **start**- och en **slut** position.</span><span class="sxs-lookup"><span data-stu-id="100a6-211">For this setting, you need to select a **Start** and an **End** position.</span></span> <span data-ttu-id="100a6-212">De här värdena representerar antalet tokens från början av dokumentet.</span><span class="sxs-lookup"><span data-stu-id="100a6-212">These values represent the number of tokens from the begging of the document.</span></span> <span data-ttu-id="100a6-213">Även om du kan ange dessa värden manuellt är det enklare att justera urvalsrutan i visningsprogrammet manuellt.</span><span class="sxs-lookup"><span data-stu-id="100a6-213">While you can manually enter in these values, it is easier to manually adjust the select box in the viewer.</span></span> 
   
## <a name="use-explanation-templates"></a><span data-ttu-id="100a6-214">Använda förklaringsmallar</span><span class="sxs-lookup"><span data-stu-id="100a6-214">Use explanation templates</span></span>

<span data-ttu-id="100a6-215">Medan du manuellt kan lägga till olika fraslistvärden för din förklaring kan det vara lättare att använda mallarna som du har fått i förklaringsbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="100a6-215">While you can manually add various phrase list values for your explanation, it can be easier to use the templates provided to you in the explanation library.</span></span>

<span data-ttu-id="100a6-216">Till exempel, istället för att manuellt lägga till alla variationer för *Datum*, kan du använda fraslistmallen för *Datum* eftersom den redan innehåller ett antal värden för fraslistor:</span><span class="sxs-lookup"><span data-stu-id="100a6-216">For example, instead of manually adding all the variations for *Date*, you can use the phrase list template for *Date* as it already includes a number of phrase lists values:</span></span>

![Förklaringsbiblioteket](../media/content-understanding/explanation-template.png)
 
<span data-ttu-id="100a6-218">I förklaringsbiblioteket finns flera vanliga förklaringar för mönsterlistor, till exempel:</span><span class="sxs-lookup"><span data-stu-id="100a6-218">The explanation library includes commonly used phrase list explanations, including:</span></span>

- <span data-ttu-id="100a6-219">Datum: kalenderdatum, alla format.</span><span class="sxs-lookup"><span data-stu-id="100a6-219">Date: Calendar dates, all formats.</span></span> <span data-ttu-id="100a6-220">Innehåller text och tal (till exempel "9 dec 2020").</span><span class="sxs-lookup"><span data-stu-id="100a6-220">Includes text and numbers (for example, "Dec 9, 2020").</span></span>
- <span data-ttu-id="100a6-221">Datum (numeriskt): kalenderdatum, alla format.</span><span class="sxs-lookup"><span data-stu-id="100a6-221">Date (numeric): Calendar dates, all formats.</span></span> <span data-ttu-id="100a6-222">Inkluderar tal (till exempel 1-11-2020).</span><span class="sxs-lookup"><span data-stu-id="100a6-222">Includes numbers (for example 1-11-2020).</span></span>
- <span data-ttu-id="100a6-223">Tid: 12- och 24-timmarsformat.</span><span class="sxs-lookup"><span data-stu-id="100a6-223">Time: 12 and 24 hour formats.</span></span>
- <span data-ttu-id="100a6-224">Tal: positiva och negativa tal upp till 2 decimaler.</span><span class="sxs-lookup"><span data-stu-id="100a6-224">Number: Positive and negative numbers up to 2 decimals.</span></span> 
- <span data-ttu-id="100a6-225">Procent: en lista över mönster som representerar en procentsats.</span><span class="sxs-lookup"><span data-stu-id="100a6-225">Percentage: A list of patterns representing a percentage.</span></span> <span data-ttu-id="100a6-226">Till exempel: 1%, 11%, 100%, 11.11%, osv.</span><span class="sxs-lookup"><span data-stu-id="100a6-226">For example, 1%, 11%, 100%, 11.11%, etc.</span></span>
- <span data-ttu-id="100a6-227">Telefonnummer: Vanliga amerikanska och internationella format.</span><span class="sxs-lookup"><span data-stu-id="100a6-227">Phone number: Common US and International formats.</span></span> <span data-ttu-id="100a6-228">Till exempel: 000 000 0000, 000-000-0000, (000)000-0000, (000) 000-0000, osv.</span><span class="sxs-lookup"><span data-stu-id="100a6-228">For example, 000 000 0000, 000-000-0000, (000)000-0000, (000) 000-0000, etc.</span></span>
- <span data-ttu-id="100a6-229">Postnummer: amerikanska postnummerformat.</span><span class="sxs-lookup"><span data-stu-id="100a6-229">Zip code: US Zip code formats.</span></span> <span data-ttu-id="100a6-230">Till exempel: 11111, 11111-1111.</span><span class="sxs-lookup"><span data-stu-id="100a6-230">For example, 11111, 11111-1111.</span></span>
- <span data-ttu-id="100a6-231">Första ordet i meningen: vanliga mönster för ord upp till 9 tecken.</span><span class="sxs-lookup"><span data-stu-id="100a6-231">First word of sentence: Common patterns for words up to 9 characters.</span></span> 
- <span data-ttu-id="100a6-232">Slutet av mening: vanligt skiljetecken för slutet av en mening</span><span class="sxs-lookup"><span data-stu-id="100a6-232">End of sentence: Common punctuation for end of a sentence</span></span>
- <span data-ttu-id="100a6-233">Kreditkort: vanliga talformat för kreditkort.</span><span class="sxs-lookup"><span data-stu-id="100a6-233">Credit card: Common credit card number formats.</span></span> <span data-ttu-id="100a6-234">Till exempel: 1111-1111-1111-1111.</span><span class="sxs-lookup"><span data-stu-id="100a6-234">For example, 1111-1111-1111-1111.</span></span> 
- <span data-ttu-id="100a6-235">Personnummer: US personnummer-format.</span><span class="sxs-lookup"><span data-stu-id="100a6-235">Social security number: US Social Security Number format.</span></span> <span data-ttu-id="100a6-236">Till exempel: 111-11-1111.</span><span class="sxs-lookup"><span data-stu-id="100a6-236">For example, 111-11-1111.</span></span> 
- <span data-ttu-id="100a6-237">Kryssruta: en fraslista som representerar variationer på en ifylld kryssruta.</span><span class="sxs-lookup"><span data-stu-id="100a6-237">Checkbox: A phrase list representing variations on a filled in checkbox.</span></span> <span data-ttu-id="100a6-238">Till exempel _X_, _ _X_ osv.</span><span class="sxs-lookup"><span data-stu-id="100a6-238">For example, _X_, _ _X_, etc.</span></span>
- <span data-ttu-id="100a6-239">Valuta: vanligaste internationella symboler.</span><span class="sxs-lookup"><span data-stu-id="100a6-239">Currency: Major international symbols.</span></span> <span data-ttu-id="100a6-240">Exempel: $.</span><span class="sxs-lookup"><span data-stu-id="100a6-240">For example, $.</span></span> 
- <span data-ttu-id="100a6-241">Kopia i e-post: en fraslista med termen "CC:" som ofta finns nära namnen eller e-postadresserna till ytterligare personer eller grupper som meddelandet skickades till.</span><span class="sxs-lookup"><span data-stu-id="100a6-241">Email CC: A phrase list with the term 'CC:', often found near the names or email addresses of additional people or groups the message was sent to.</span></span>
- <span data-ttu-id="100a6-242">E-postdatum: en fraslista med termen "Skickat den:" förekommer ofta nära det datum då meddelandet skickades.</span><span class="sxs-lookup"><span data-stu-id="100a6-242">Email date: A phrase list with the term 'Sent on:', often found near the date the email was sent.</span></span>
- <span data-ttu-id="100a6-243">E-posthälsning: vanliga inledande rader för e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="100a6-243">Email greeting: Common opening lines for emails.</span></span>
- <span data-ttu-id="100a6-244">E-postmottagare: en fraslista med termen "Till:" som ofta finns nära namnen eller e-postadresserna till personer eller grupper som meddelandet skickades till.</span><span class="sxs-lookup"><span data-stu-id="100a6-244">Email recipient: A phrase list with the term 'To:', often found near the names or email addresses of people or groups the message was sent to.</span></span> 
- <span data-ttu-id="100a6-245">E-postavsändare: en fraslista med termen "Från:" förekommer ofta nära avsändarens namn eller e-postadress.</span><span class="sxs-lookup"><span data-stu-id="100a6-245">Email sender: A phrase list with the term 'From:', often found near the sender's name or email address.</span></span> 
- <span data-ttu-id="100a6-246">Ämne för e-post: en fraslista med termen "Ämne:" som ofta finns nära e-postmeddelandets ämne.</span><span class="sxs-lookup"><span data-stu-id="100a6-246">Email subject: A phrase list with the term 'Subject:', often found near the email's subject.</span></span> 

<span data-ttu-id="100a6-247">I förklaringsbiblioteket finns också tre automatiska malltyper som fungerar med de data som du har märkt i exempelfilerna:</span><span class="sxs-lookup"><span data-stu-id="100a6-247">The explanation library also includes three automatic template types that work with the data you've labeled in your example files:</span></span>

- <span data-ttu-id="100a6-248">Efter etikett: De ord eller tecken som förekommer efter etiketterna i exempelfilerna.</span><span class="sxs-lookup"><span data-stu-id="100a6-248">After label: The words or characters that occur after the labels in the example files.</span></span>
- <span data-ttu-id="100a6-249">Före etikett: De ord eller tecken som förekommer före etiketterna i exempelfilerna.</span><span class="sxs-lookup"><span data-stu-id="100a6-249">Before label: The words or characters that occur before the labels in the example files.</span></span>
- <span data-ttu-id="100a6-250">Etiketter: Upp till de första 10 etiketterna från exempelfilerna.</span><span class="sxs-lookup"><span data-stu-id="100a6-250">Labels: Up to the first 10 labels from the example files.</span></span>

<span data-ttu-id="100a6-251">Om du vill ge dig ett exempel på hur automatiska mallar fungerar, i följande exempelfil, kommer vi att använda förklaringsmallen före etikett för att ge modellen mer information för att få en mer exakt matchning.</span><span class="sxs-lookup"><span data-stu-id="100a6-251">To give you an example of how automatic templates work, in the following example file, we will use the Before Label explanation template to help give the model more information to get a more accurate match.</span></span>

![Exempelfil](../media/content-understanding/before-label.png)

<span data-ttu-id="100a6-253">När du väljer mallen Före etikettförklaring letar den efter den första uppsättningen ord som visas före etiketten i dina exempelfiler.</span><span class="sxs-lookup"><span data-stu-id="100a6-253">When you select the Before Label explanation template, it will look for the first set of words that appear before the label in your example files.</span></span> <span data-ttu-id="100a6-254">I exemplet är orden som identifierats i den första exempelfilen "Från och med".</span><span class="sxs-lookup"><span data-stu-id="100a6-254">In the example, the words that are identified in the first example file is "As of".</span></span>

![Före etikettmall](../media/content-understanding/before-label-explanation.png)

<span data-ttu-id="100a6-256">Du kan välja **Lägg** om du vill skapa en förklaring från mallen.</span><span class="sxs-lookup"><span data-stu-id="100a6-256">You can select **Add** to create an explanation from the template.</span></span>  <span data-ttu-id="100a6-257">När du lägger till fler exempelfiler identifieras och läggs ytterligare ord till i fraslistan.</span><span class="sxs-lookup"><span data-stu-id="100a6-257">As you add more example files, additional words will be identified and added to the phrase list.</span></span>

![Lägga till etiketten](../media/content-understanding/before-label-add.png)
 
#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="100a6-259">Använda en mall från förklaringsbiblioteket</span><span class="sxs-lookup"><span data-stu-id="100a6-259">To use a template from the explanation library</span></span>

1. <span data-ttu-id="100a6-260">Välj **Ny** i avsnittet **Förklaringar** på modellens sida **Träna** och välj **Från en mall**.</span><span class="sxs-lookup"><span data-stu-id="100a6-260">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span>

   ![Lägg till före etikett](../media/content-understanding/from-template.png)

2.  <span data-ttu-id="100a6-262">På sidan **Förklaringsmallar** väljer du den förklaring du vill använda och väljer sedan **Lägga till**.</span><span class="sxs-lookup"><span data-stu-id="100a6-262">On the **Explanation templates** page, select the explanation you want to use, then select **Add**.</span></span>

    ![Välj en mall](../media/content-understanding/phone-template.png)

3. <span data-ttu-id="100a6-264">Informationen för den mall som du valde visas på sidan **Skapa en förklaring**.</span><span class="sxs-lookup"><span data-stu-id="100a6-264">The information for the template you selected displays on the **Create an explanation** page.</span></span> <span data-ttu-id="100a6-265">Om det behövs kan du redigera namnet på förklaringen och lägga till eller ta bort objekt från fraslistan.</span><span class="sxs-lookup"><span data-stu-id="100a6-265">If needed, edit the explanation name and add or remove items from the phrase list.</span></span>  

    ![Redigera mall](../media/content-understanding/phone-template-live.png)

4. <span data-ttu-id="100a6-267">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="100a6-267">When finished, select **Save**.</span></span>