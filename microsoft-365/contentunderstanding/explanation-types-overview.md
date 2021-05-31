---
title: Olika typer av förklaringar i Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Mer information om olika typer av förklaringar i Microsoft SharePoint Syntex.
ms.openlocfilehash: 515fd8af289ec7c64e14eb6d54b236ba3a8aa9f6
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706582"
---
# <a name="explanation-types-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="453c1-103">Olika typer av förklaringar i Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="453c1-103">Explanation types in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="453c1-104">Förklaringar används för att definiera den information som du vill använda för att ge etiketter och utdrag i dina modeller för dokumenttolkning i Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="453c1-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="453c1-105">När du skapar en förklaring måste du välja en förklaringstyp.</span><span class="sxs-lookup"><span data-stu-id="453c1-105">When you create an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="453c1-106">Den här artikeln hjälper dig förstå olika förklaringstyper och hur de används.</span><span class="sxs-lookup"><span data-stu-id="453c1-106">This article helps you understand the different explanation types and how they're used.</span></span>

![Skärmbild av panelen Skapa en förklaring med de tre förklaringstyperna.](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="453c1-108">Följande förklaringstyper är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="453c1-108">These explanation types are available:</span></span>

- <span data-ttu-id="453c1-109">[**Fraslista**](#phrase-list): lista med ord, fraser, siffror eller andra tecken som du kan använda i det dokument eller den information du extraherar. </span><span class="sxs-lookup"><span data-stu-id="453c1-109">[**Phrase list**](#phrase-list): List of words, phrases, numbers, or other characters you can use in the document or information that you're extracting.</span></span> <span data-ttu-id="453c1-110">Exempel: textsträngen *hänvisande läkare* finns i alla medicinska referensdokument som du identifierar.</span><span class="sxs-lookup"><span data-stu-id="453c1-110">For example, the text string *referring doctor* is in all Medical Referral documents you're identifying.</span></span> <span data-ttu-id="453c1-111">Eller den hänvisande läkarens *telefonnummer* i alla medicinsk referensdokument som du identifierar.</span><span class="sxs-lookup"><span data-stu-id="453c1-111">Or the *phone number* of the referring doctor from all Medical Referral documents that you're identifying.</span></span>

- <span data-ttu-id="453c1-112">[**Ett reguljärt uttryck**](#regular-expression): använder en notation för mönstermatchning för att hitta specifika teckenmönster.</span><span class="sxs-lookup"><span data-stu-id="453c1-112">[**Regular expression**](#regular-expression): Uses a pattern-matching notation to find specific character patterns.</span></span> <span data-ttu-id="453c1-113">Du kan till exempel använda ett reguljärt uttryck för att hitta alla förekomster av ett *postadresmönstret* i en uppsättning dokument.</span><span class="sxs-lookup"><span data-stu-id="453c1-113">For example, you can use a regular expression to find all instances of an *email address* pattern in a set of documents.</span></span>

- <span data-ttu-id="453c1-114">[**Närhet**](#proximity): beskriver hur nära förklaringar är med varandra.</span><span class="sxs-lookup"><span data-stu-id="453c1-114">[**Proximity**](#proximity): Describes how close explanations are to each other.</span></span> <span data-ttu-id="453c1-115">Till exempel: en fraslista för *gatunummer* ska ligga precis innan fraslistan för *gatunamn* utan tokens emellan (du får lära dig mer om tokens senare i den här artikeln).</span><span class="sxs-lookup"><span data-stu-id="453c1-115">For example, a *street number* phrase list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="453c1-116">Med närhetstypen måste du ha minst två förklaringar i modellen, annars är alternativet inaktiverat.</span><span class="sxs-lookup"><span data-stu-id="453c1-116">Using the proximity type requires you to have at least two explanations in your model or the option will be disabled.</span></span> 

## <a name="phrase-list"></a><span data-ttu-id="453c1-117">Fraslista</span><span class="sxs-lookup"><span data-stu-id="453c1-117">Phrase list</span></span>

<span data-ttu-id="453c1-118">Förklaringstypen fraslista används vanligtvis för att identifiera och klassificera ett dokument via modellen.</span><span class="sxs-lookup"><span data-stu-id="453c1-118">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="453c1-119">Så som det beskrivs i exemplet med etikett för *hänvisande läkare* är det en sträng med ord, fraser, siffror eller tecken är konsekventa i de dokument som du identifierar.</span><span class="sxs-lookup"><span data-stu-id="453c1-119">As described in the *referring doctor* label example, it's a string of words, phrases, numbers, or characters that is consistently in the documents that you're identifying.</span></span>

<span data-ttu-id="453c1-120">Även om det inte är obligatoriskt kan du få mer framgång med din förklaring om frasen du hämtar finns på en konsekvent plats i ditt dokument.</span><span class="sxs-lookup"><span data-stu-id="453c1-120">While not a requirement, you can achieve better success with your explanation if the phrase you're capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="453c1-121">Till exempel kan etiketten *hänvisande läkare* konsekvent finnas i det första stycket i dokumentet.</span><span class="sxs-lookup"><span data-stu-id="453c1-121">For example, the *referring doctor* label might be consistently located in the first paragraph of the document.</span></span> <span data-ttu-id="453c1-122">Du kan också använda avancerad inställning för **[Konfigurera var fraser ska visas i dokumentet](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#configure-where-phrases-occur-in-the-document)** för att markera specifika områden där frasen finns, särskilt om det finns en möjlighet att frasen förekommer på flera platser i ditt dokument.</span><span class="sxs-lookup"><span data-stu-id="453c1-122">You can also use the **[Configure where phrases occur in the document](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#configure-where-phrases-occur-in-the-document)** advanced setting to select specific areas where the phrase is located, especially if there's a chance that the phrase might occur in multiple locations in your document.</span></span>

<span data-ttu-id="453c1-123">Om skifteslägeskänslighet är obligatorisk för att identifiera din etikett tillåter användning av fraslista dig att ange det i förklaringen genom att markera kryssrutan **Endast exakta versaler**.</span><span class="sxs-lookup"><span data-stu-id="453c1-123">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

![Skifteslägeskänslighet](../media/content-understanding/case-sensitivity.png) 

<span data-ttu-id="453c1-125">En frastyp är särskilt användbar när du skapar en förklaring som identifierar och extraherar information i olika format, till exempel datum, telefonnummer och kreditkortsnummer.</span><span class="sxs-lookup"><span data-stu-id="453c1-125">A phrase type is especially useful when you create an explanation that identifies and extracts information in different formats, such as dates, phone numbers, and credit card numbers.</span></span> <span data-ttu-id="453c1-126">Till exempel kan ett datum visas i flera olika format (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, eller Jan 1, 2020).</span><span class="sxs-lookup"><span data-stu-id="453c1-126">For example, a date can be displayed in many different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, or Jan 1,2020).</span></span> <span data-ttu-id="453c1-127">Genom att definiera en fraslista blir förklaringen mer effektiv genom att fånga alla möjliga variationer i de data som du försöker identifiera och extrahera.</span><span class="sxs-lookup"><span data-stu-id="453c1-127">Defining a phrase list makes your explanation more efficient by capturing any possible variations in the data that you're trying to identify and extract.</span></span> 

<span data-ttu-id="453c1-128">För exemplet *telefonnummer* extraherar du telefonnumret till varje hänvisande läkare från alla medicinska referensdokument som modellen identifierar.</span><span class="sxs-lookup"><span data-stu-id="453c1-128">For the *phone number* example, you extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="453c1-129">När du skapar förklaringen skriver du de olika formaten som ett telefonnummer kan visa i ditt dokument så att du kan fånga upp möjliga variationer.</span><span class="sxs-lookup"><span data-stu-id="453c1-129">When you create the explanation, type the different formats a phone number might display in your document so that you're able to capture possible variations.</span></span> 

![Mönster för telefonnummerfraser](../media/content-understanding/pattern-list.png)

<span data-ttu-id="453c1-131">I det här exemplet i **Avancerad Inställningar** väljer du **Valfri siffra mellan 0-9** i kryssrutan för att känna igen alla "0"-värden som används i din fraslista som valfri siffra mellan 0 och 9.</span><span class="sxs-lookup"><span data-stu-id="453c1-131">For this example, in **Advanced Settings** select the **Any digit from 0-9** checkbox to recognize each "0" value used in your phrase list to be any digit from 0 through 9.</span></span>

![Valfri siffra mellan 0-9](../media/content-understanding/digit-identity.png)

<span data-ttu-id="453c1-133">Om du på liknande sätt skapar en fraslista som innehåller texttecken markerar du kryssrutan **Valfri bokstav mellan a-ö** för att känna igen alla "a"-tecken som används i fraslistan att vara valfri tecken mellan "a" till "ö".</span><span class="sxs-lookup"><span data-stu-id="453c1-133">Similarly, if you create a phrase list that includes text characters, select the **Any letter from a-z** checkbox to recognize each "a" character used in the phrase list to be any character from "a" to "z".</span></span>

<span data-ttu-id="453c1-134">Om du, till exempel, skapar en fraslista för **Datum** och vill se till att ett datumformat som *1 januari 2020* känns igen, måste du:</span><span class="sxs-lookup"><span data-stu-id="453c1-134">For example, if you create a **Date** phrase list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>

- <span data-ttu-id="453c1-135">Lägga till *0 aaaaaaa 0000* och *00 aaaaaaa 0000* i din fraslista.</span><span class="sxs-lookup"><span data-stu-id="453c1-135">Add *aaa 0, 0000* and *aaa 00, 0000* to your phrase list.</span></span>
- <span data-ttu-id="453c1-136">Kontrollera att **Valfri bokstav från a-ö** också är markerad.</span><span class="sxs-lookup"><span data-stu-id="453c1-136">Make sure that **Any letter from a-z** is also selected.</span></span>

![Valfri bokstav från a till ö](../media/content-understanding/any-letter.png)

<span data-ttu-id="453c1-138">Om du har kapitaliseringskrav i din fraslista kan du välja kryssrutan **Endast exakta kapitalisering**.</span><span class="sxs-lookup"><span data-stu-id="453c1-138">If you have capitalization requirements in your phrase list, you can select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="453c1-139">Om du kräver att den första bokstaven i månaden för datumexemplet ska kapitaliseras behöver du:</span><span class="sxs-lookup"><span data-stu-id="453c1-139">For the date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="453c1-140">Lägga till *Aaa 0, 0000* och *Aaa 00 0000* till din fraslista.</span><span class="sxs-lookup"><span data-stu-id="453c1-140">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your phrase list.</span></span>
- <span data-ttu-id="453c1-141">Kontrollera att **Endast exakta versaler** också är markerad.</span><span class="sxs-lookup"><span data-stu-id="453c1-141">Make sure that **Only exact capitalization** is also selected.</span></span>

![Endast exakta versaler](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="453c1-143">I stället för att manuellt skapa en förklaring för en fraslista kan du använda [förklaringsbiblioteket](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) för att använda mallar för en vanlig fraslista, till exempel *datum*, *telefonnummer* eller *kreditkortsnummer*.</span><span class="sxs-lookup"><span data-stu-id="453c1-143">Instead of manually creating a phrase list explanation, use the [explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) to use phrase list templates for a common phrase list, such as *date*, *phone number*, or *credit card number*.</span></span>

## <a name="regular-expression"></a><span data-ttu-id="453c1-144">Reguljärt uttryck</span><span class="sxs-lookup"><span data-stu-id="453c1-144">Regular expression</span></span>

<span data-ttu-id="453c1-145">Med en förklaringstyp för reguljära uttryck kan du skapa mönster som hjälper dig att hitta och identifiera vissa textsträngar i dokumenten.</span><span class="sxs-lookup"><span data-stu-id="453c1-145">A regular expression explanation type allows you to create patterns that help find and identify certain text strings in documents.</span></span> <span data-ttu-id="453c1-146">Du kan använda reguljära uttryck för att snabbt tolka stora mängder text för att:</span><span class="sxs-lookup"><span data-stu-id="453c1-146">You can use regular expressions to quickly parse large amounts of text to:</span></span>

- <span data-ttu-id="453c1-147">Söka efter specifika teckenmönster.</span><span class="sxs-lookup"><span data-stu-id="453c1-147">Find specific character patterns.</span></span>
- <span data-ttu-id="453c1-148">Verifiera text för att säkerställa att den matchar ett fördefinierat mönster (till exempel en e-postadress).</span><span class="sxs-lookup"><span data-stu-id="453c1-148">Validate text to ensure that it matches a predefined pattern (such as an email address).</span></span>
- <span data-ttu-id="453c1-149">Extrahera, redigera, ersätta eller ta bort textundersträngar.</span><span class="sxs-lookup"><span data-stu-id="453c1-149">Extract, edit, replace, or delete text substrings.</span></span>

<span data-ttu-id="453c1-150">En typ av reguljära uttryck är särskilt användbar när du skapar en förklaring som identifierar och extraherar information i liknande format, till exempel e-postadresser, bankkontonummer eller url-adresser.</span><span class="sxs-lookup"><span data-stu-id="453c1-150">A regular expression type is especially useful when you create an explanation that identifies and extracts information in similar formats, such as email addresses, bank account numbers, or URLs.</span></span> <span data-ttu-id="453c1-151">En e-postadress, till exempel megan@contoso.com, visas i ett visst mönster ("megan" är den första delen, och "com" är den sista delen).</span><span class="sxs-lookup"><span data-stu-id="453c1-151">For example, an email address, such as megan@contoso.com, is displayed in a certain pattern ("megan" is the first part, and "com" is the last part).</span></span> 

<span data-ttu-id="453c1-152">Det vanliga uttrycket för en e-postadress är: **[A-Basist-z0-9._%-]+@[A-An-z0-9.-]+. [A-<3>-z]{2,6}**.</span><span class="sxs-lookup"><span data-stu-id="453c1-152">The regular expression for an email address is: **[A-Za-z0-9._%-]+@[A-Za-z0-9.-]+.[A-Za-z]{2,6}**.</span></span>

<span data-ttu-id="453c1-153">Det här uttrycket består av fem delar, i denna ordning:</span><span class="sxs-lookup"><span data-stu-id="453c1-153">This expression consists of five parts, in this order:</span></span>

1. <span data-ttu-id="453c1-154">några av följande tecken:</span><span class="sxs-lookup"><span data-stu-id="453c1-154">Any amount of the following characters:</span></span>

   <span data-ttu-id="453c1-155">a.</span><span class="sxs-lookup"><span data-stu-id="453c1-155">a.</span></span> <span data-ttu-id="453c1-156">Bokstäver från a till z</span><span class="sxs-lookup"><span data-stu-id="453c1-156">Letters from a to z</span></span>

   <span data-ttu-id="453c1-157">b.</span><span class="sxs-lookup"><span data-stu-id="453c1-157">b.</span></span> <span data-ttu-id="453c1-158">Siffror från 0 till 9</span><span class="sxs-lookup"><span data-stu-id="453c1-158">Numbers from 0-9</span></span>

   <span data-ttu-id="453c1-159">c.</span><span class="sxs-lookup"><span data-stu-id="453c1-159">c.</span></span> <span data-ttu-id="453c1-160">Punkt, understreck, procent eller tankstreck</span><span class="sxs-lookup"><span data-stu-id="453c1-160">Period, underscore, percent, or dash</span></span>

2. <span data-ttu-id="453c1-161">@-symbol</span><span class="sxs-lookup"><span data-stu-id="453c1-161">The @ symbol</span></span>

3. <span data-ttu-id="453c1-162">Några tecken från den första delen av e-postadressen</span><span class="sxs-lookup"><span data-stu-id="453c1-162">Any amount of the same characters as the first part of the email address</span></span>

4. <span data-ttu-id="453c1-163">En punkt</span><span class="sxs-lookup"><span data-stu-id="453c1-163">A period</span></span>

5. <span data-ttu-id="453c1-164">Två till sex bokstäver</span><span class="sxs-lookup"><span data-stu-id="453c1-164">Two to six letters</span></span>

<span data-ttu-id="453c1-165">Så här lägger du till en förklaringstyp för reguljära uttryck:</span><span class="sxs-lookup"><span data-stu-id="453c1-165">To add a regular expression explanation type:</span></span>

1. <span data-ttu-id="453c1-166">På panelen **Skapa en förklaring** går du till panelen **Förklaringstyp** och väljer **Reguljärt uttryck**.</span><span class="sxs-lookup"><span data-stu-id="453c1-166">From the **Create an explanation** panel, under **Explanation type**, select **Regular expression**.</span></span>

   ![Skärmbild som visar panelen Skapa en förklaring med Reguljärt uttryck markerat.](../media/content-understanding/create-regular-expression.png)

2. <span data-ttu-id="453c1-168">Du kan antingen skriva ett uttryck i textrutan **Reguljära uttryck** eller välja **Lägg till ett reguljärt uttryck från en mall**.</span><span class="sxs-lookup"><span data-stu-id="453c1-168">You can either type an expression in the **Regular expression** text box or select **Add a regular expression from a template**.</span></span>

   <span data-ttu-id="453c1-169">När du lägger till ett reguljärt uttryck med hjälp av en mall läggs namnet och det reguljära uttrycket automatiskt till i textrutan.</span><span class="sxs-lookup"><span data-stu-id="453c1-169">When you add a regular expression by using a template, it automatically adds the name and the regular expression to the text box.</span></span> <span data-ttu-id="453c1-170">Om du till exempel väljer mallen **e-postadress** populeras **panelen Lägg till en förklaring**.</span><span class="sxs-lookup"><span data-stu-id="453c1-170">For example, if you choose the **Email address** template, the **Create an explanation** panel will be populated.</span></span>

   ![Skärmbild som visar panelen Skapa en förklaring med mallen E-postadress markerat.](../media/content-understanding/create-regular-expression-email.png)

## <a name="proximity"></a><span data-ttu-id="453c1-172">Närhet</span><span class="sxs-lookup"><span data-stu-id="453c1-172">Proximity</span></span> 

<span data-ttu-id="453c1-173">Typen närhetsförklaring hjälper modellen att lättare identifiera data genom att definiera hur nära ett annat data kommer till den.</span><span class="sxs-lookup"><span data-stu-id="453c1-173">The proximity explanation type helps your model identify data by defining how close another piece of data is to it.</span></span> <span data-ttu-id="453c1-174">I din modell har du till exempel två förklaringar som etiketterar både kundens *gatunummer* och *telefonnummer*.</span><span class="sxs-lookup"><span data-stu-id="453c1-174">For example, in your model say you have defined two explanations that label both the customer *street address number* and *phone number*.</span></span> 

<span data-ttu-id="453c1-175">Notera att kundens telefonnummer alltid visas före gatunumret.</span><span class="sxs-lookup"><span data-stu-id="453c1-175">Notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="453c1-176">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="453c1-176">Alex Wilburn</span></span><br>
<span data-ttu-id="453c1-177">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="453c1-177">555-555-5555</span></span><br>
<span data-ttu-id="453c1-178">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="453c1-178">One Microsoft Way</span></span><br>
<span data-ttu-id="453c1-179">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="453c1-179">Redmond, WA 98034</span></span><br>

<span data-ttu-id="453c1-180">Använd närhetsförklaringen för att definiera hur långt bort det är för att bättre identifiera gatunumret i dina dokument.</span><span class="sxs-lookup"><span data-stu-id="453c1-180">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

![Närhetsförklaring](../media/content-understanding/proximity.png)

#### <a name="what-are-tokens"></a><span data-ttu-id="453c1-182">Vad är tokens?</span><span class="sxs-lookup"><span data-stu-id="453c1-182">What are tokens?</span></span>

<span data-ttu-id="453c1-183">Om du vill använda typen för närhetsförklaring måste du förstå vad en token är.</span><span class="sxs-lookup"><span data-stu-id="453c1-183">To use the proximity explanation type, you need to understand what a token is.</span></span> <span data-ttu-id="453c1-184">Antalet tokens är hur närhetsförklaringen mäter avståndet från en förklaring till en annan.</span><span class="sxs-lookup"><span data-stu-id="453c1-184">The number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span> <span data-ttu-id="453c1-185">En token är ett sammanhängande intervall (exklusive blanksteg eller skiljetecken) för bokstäver och siffror.</span><span class="sxs-lookup"><span data-stu-id="453c1-185">A token is a continuous span (not including spaces or punctuation) of letters and numbers.</span></span> 

<span data-ttu-id="453c1-186">I tabellen nedan visas exempel på hur du kan ta reda på antalet tokens i en fras.</span><span class="sxs-lookup"><span data-stu-id="453c1-186">The following table shows examples for how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="453c1-187">Fras</span><span class="sxs-lookup"><span data-stu-id="453c1-187">Phrase</span></span>|<span data-ttu-id="453c1-188">Antal tokens</span><span class="sxs-lookup"><span data-stu-id="453c1-188">Number of tokens</span></span>|<span data-ttu-id="453c1-189">Förklaring</span><span class="sxs-lookup"><span data-stu-id="453c1-189">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="453c1-190">1</span><span class="sxs-lookup"><span data-stu-id="453c1-190">1</span></span>|<span data-ttu-id="453c1-191">Ett enstaka ord utan skiljetecken eller blanksteg.</span><span class="sxs-lookup"><span data-stu-id="453c1-191">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="453c1-192">1</span><span class="sxs-lookup"><span data-stu-id="453c1-192">1</span></span>|<span data-ttu-id="453c1-193">Ett lokaliseringsnummer för posten.</span><span class="sxs-lookup"><span data-stu-id="453c1-193">A record locator number.</span></span> <span data-ttu-id="453c1-194">Det kan innehålla siffror och bokstäver men inga skiljetecken.</span><span class="sxs-lookup"><span data-stu-id="453c1-194">It might include numbers and letters, but doesn't have punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="453c1-195">5</span><span class="sxs-lookup"><span data-stu-id="453c1-195">5</span></span>|<span data-ttu-id="453c1-196">Ett telefonnummer.</span><span class="sxs-lookup"><span data-stu-id="453c1-196">A phone number.</span></span> <span data-ttu-id="453c1-197">Varje skiljetecken är ett enda token, så `425-555-5555` är 5 tokens:</span><span class="sxs-lookup"><span data-stu-id="453c1-197">Each punctuation mark is a single token, so `425-555-5555` is 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="453c1-198">7</span><span class="sxs-lookup"><span data-stu-id="453c1-198">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="453c1-199">Konfigurera typen närhetsförklaring</span><span class="sxs-lookup"><span data-stu-id="453c1-199">Configure the proximity explanation type</span></span>

<span data-ttu-id="453c1-200">Konfigurera inställningen närhet för detta exempel att definiera intervallet för antalet tokens i förklaringen för *telefonnummer* från förklaringen *gatunummer*.</span><span class="sxs-lookup"><span data-stu-id="453c1-200">For the example, configure the proximity setting to define the range of the number of tokens in the *phone number* explanation from the *street address number* explanation.</span></span> <span data-ttu-id="453c1-201">Notera att det minsta intervallet är "0" eftersom det inte finns några tokens mellan telefonnumret och gatunumret.</span><span class="sxs-lookup"><span data-stu-id="453c1-201">Notice that the minimum range is "0", because there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="453c1-202">Men vissa telefonnummer i urvalsdokumenten har tillägget *(mobil)*.</span><span class="sxs-lookup"><span data-stu-id="453c1-202">But some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="453c1-203">Viktor Magnusson</span><span class="sxs-lookup"><span data-stu-id="453c1-203">Nestor Wilke</span></span><br>
<span data-ttu-id="453c1-204">111-111-1111 (mobil)</span><span class="sxs-lookup"><span data-stu-id="453c1-204">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="453c1-205">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="453c1-205">One Microsoft Way</span></span><br>
<span data-ttu-id="453c1-206">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="453c1-206">Redmond, WA 98034</span></span><br>

<span data-ttu-id="453c1-207">Det finns tre tokens i *(mobil)*:</span><span class="sxs-lookup"><span data-stu-id="453c1-207">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="453c1-208">Fras</span><span class="sxs-lookup"><span data-stu-id="453c1-208">Phrase</span></span>|<span data-ttu-id="453c1-209">Antal tokens</span><span class="sxs-lookup"><span data-stu-id="453c1-209">Token count</span></span>|
|--|--|
|<span data-ttu-id="453c1-210">(</span><span class="sxs-lookup"><span data-stu-id="453c1-210">(</span></span>|<span data-ttu-id="453c1-211">1</span><span class="sxs-lookup"><span data-stu-id="453c1-211">1</span></span>|
|<span data-ttu-id="453c1-212">mobil</span><span class="sxs-lookup"><span data-stu-id="453c1-212">mobile</span></span>|<span data-ttu-id="453c1-213">2</span><span class="sxs-lookup"><span data-stu-id="453c1-213">2</span></span>|
|<span data-ttu-id="453c1-214">)</span><span class="sxs-lookup"><span data-stu-id="453c1-214">)</span></span>|<span data-ttu-id="453c1-215">3</span><span class="sxs-lookup"><span data-stu-id="453c1-215">3</span></span>|

<span data-ttu-id="453c1-216">Konfigurera inställningen för närhet så att den har ett område med 0 till 3.</span><span class="sxs-lookup"><span data-stu-id="453c1-216">Configure the proximity setting to have a range of 0 through 3.</span></span>

![Exempel på närhet](../media/content-understanding/proximity-example.png)

## <a name="configure-where-phrases-occur-in-the-document"></a><span data-ttu-id="453c1-218">Konfigurera var fraser förekommer i dokumentet</span><span class="sxs-lookup"><span data-stu-id="453c1-218">Configure where phrases occur in the document</span></span>

<span data-ttu-id="453c1-219">När du skapar en förklaring söks som standard hela dokumentet efter frasen du försöker extrahera.</span><span class="sxs-lookup"><span data-stu-id="453c1-219">When you create an explanation, by default the entire document is searched for the phrase you're trying to extract.</span></span> <span data-ttu-id="453c1-220">Du kan dock använda inställningen **Där fraserna förekommer** avancerade inställning för att hjälpa till att isolera en specifik plats i dokumentet som en fras förekommer på.</span><span class="sxs-lookup"><span data-stu-id="453c1-220">However, you can use the **Where these phrases occur** advanced setting to help in isolating a specific location in the document that a phrase occurs.</span></span> <span data-ttu-id="453c1-221">Den här inställningen är användbart i situationer där liknande förekomster av en fras kan förekomma någon annanstans i dokumentet, och du vill kontrollera att rätt förekomst är markerad.</span><span class="sxs-lookup"><span data-stu-id="453c1-221">This setting is useful in situations where similar instances of a phrase might appear somewhere else in the document, and you want to make sure that the correct one is selected.</span></span>

<span data-ttu-id="453c1-222">Med hänvisning till vårt exempel på medicinsk remiss nämns alltid den *hänvisande läkaren* i första stycket i dokumentet.</span><span class="sxs-lookup"><span data-stu-id="453c1-222">Referring to our Medical Referral document example, the *referring doctor* is always mentioned in the first paragraph of the document.</span></span> <span data-ttu-id="453c1-223">Med inställningen **Var dessa fraser förekommer** kan du i det här exemplet konfigurera förklaringen så att den bara söker efter den här etiketten i början av dokumentet eller någon annan plats där den kan förekomma.</span><span class="sxs-lookup"><span data-stu-id="453c1-223">With the **Where these phrases occur** setting, in this example you can configure your explanation to search for this label only in the beginning section of the document, or any other location in which it might occur.</span></span>

![Var dessa fraser förekommer inställning](../media/content-understanding/phrase-location.png)

<span data-ttu-id="453c1-225">Du kan välja följande alternativ för den här inställningen:</span><span class="sxs-lookup"><span data-stu-id="453c1-225">You can choose the following options for this setting:</span></span>

- <span data-ttu-id="453c1-226">Var som helst i filen: Hela dokumentet söks efter frasen.</span><span class="sxs-lookup"><span data-stu-id="453c1-226">Anywhere in the file: The entire document is searched for the phrase.</span></span>

- <span data-ttu-id="453c1-227">Början av filen: Dokumentet genomsöks från början till frasen plats.</span><span class="sxs-lookup"><span data-stu-id="453c1-227">Beginning of the file:  The document is searched from the beginning to the phrase location.</span></span>

   ![Början på filen](../media/content-understanding/beginning-of-file.png)

    <span data-ttu-id="453c1-229">I visningsprogrammet kan du manuellt justera urvalsrutan så att den inkluderar platsen där fasen inträffar.</span><span class="sxs-lookup"><span data-stu-id="453c1-229">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="453c1-230">Den **slutpositionens** värde uppdateras för att visa antalet tokens som ditt valda område innehåller.</span><span class="sxs-lookup"><span data-stu-id="453c1-230">The **End position** value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="453c1-231">Du kan uppdatera **slutpositionsvärdet** för att justera det valda området.</span><span class="sxs-lookup"><span data-stu-id="453c1-231">You can update the **End position** value as well to adjust the selected area.</span></span>

   ![Början på filens positionsruta](../media/content-understanding/beginning-box.png)

- <span data-ttu-id="453c1-233">Slutet av filen: dokumentet genomsöks från slutet till frasens plats.</span><span class="sxs-lookup"><span data-stu-id="453c1-233">End of the file: The document is searched from the end to the phrase location.</span></span>

   ![Slutet av filen](../media/content-understanding/end-of-file.png)

    <span data-ttu-id="453c1-235">I visningsprogrammet kan du manuellt justera urvalsrutan så att den inkluderar platsen där fasen inträffar.</span><span class="sxs-lookup"><span data-stu-id="453c1-235">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="453c1-236">Värdet **startposition** uppdateras för att visa antalet tokens som ditt valda område innehåller.</span><span class="sxs-lookup"><span data-stu-id="453c1-236">The **Starting position** value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="453c1-237">Observera att du också kan uppdatera startpositionens värde för att justera det markerade området.</span><span class="sxs-lookup"><span data-stu-id="453c1-237">You can update the Starting position value as well to adjust the selected area.</span></span>

   ![Slutet på filens slutruta](../media/content-understanding/end-box.png)

- <span data-ttu-id="453c1-239">Anpassat intervall: Dokumentet genomsöks inom ett angivet intervall för frasplatsen.</span><span class="sxs-lookup"><span data-stu-id="453c1-239">Custom range: The document is searched within a specified range for the phrase location.</span></span>

   ![Anpassat intervall](../media/content-understanding/custom-file.png)

    <span data-ttu-id="453c1-241">I visningsprogrammet kan du manuellt justera urvalsrutan så att den inkluderar platsen där fasen inträffar.</span><span class="sxs-lookup"><span data-stu-id="453c1-241">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="453c1-242">För den här inställningen måste du välja en **start**- och en **slut** position.</span><span class="sxs-lookup"><span data-stu-id="453c1-242">For this setting, you need to select a **Start** and an **End** position.</span></span> <span data-ttu-id="453c1-243">De här värdena representerar antalet tokens från början av dokumentet.</span><span class="sxs-lookup"><span data-stu-id="453c1-243">These values represent the number of tokens from the beginning of the document.</span></span> <span data-ttu-id="453c1-244">Även om du kan ange dessa värden manuellt är det enklare att justera urvalsrutan i visningsprogrammet manuellt.</span><span class="sxs-lookup"><span data-stu-id="453c1-244">While you can manually enter in these values, it's easier to manually adjust the select box in the viewer.</span></span> 
   
## <a name="use-explanation-templates"></a><span data-ttu-id="453c1-245">Använda förklaringsmallar</span><span class="sxs-lookup"><span data-stu-id="453c1-245">Use explanation templates</span></span>

<span data-ttu-id="453c1-246">Medan du manuellt kan lägga till olika fraslistvärden för din förklaring kan det vara lättare att använda mallarna som du har fått i förklaringsbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="453c1-246">While you can manually add various phrase list values for your explanation, it can be easier to use the templates provided to you in the explanation library.</span></span>

<span data-ttu-id="453c1-247">Till exempel, istället för att manuellt lägga till alla variationer för *datum*, kan du använda fraslistmallen för *datum* eftersom den redan innehåller många värden för fraslistor:</span><span class="sxs-lookup"><span data-stu-id="453c1-247">For example, instead of manually adding all the variations for *date*, you can use the phrase list template for *date* because it already includes many phrase lists values:</span></span>

![Förklaringsbiblioteket](../media/content-understanding/explanation-template.png)
 
<span data-ttu-id="453c1-249&quot;>I förklaringsbiblioteket finns flera vanliga förklaringar för *fraslistor*, till exempel:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;453c1-249&quot;>The explanation library includes commonly used *phrase list* explanations, including:</span></span>

- <span data-ttu-id=&quot;453c1-250&quot;>Datum: kalenderdatum, alla format.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;453c1-250&quot;>Date: Calendar dates, all formats.</span></span> <span data-ttu-id=&quot;453c1-251&quot;>Innehåller text och tal (till exempel &quot;9 dec 2020").</span><span class="sxs-lookup"><span data-stu-id="453c1-251">Includes text and numbers (for example, "Dec 9, 2020").</span></span>
- <span data-ttu-id="453c1-252">Datum (numeriskt): kalenderdatum, alla format.</span><span class="sxs-lookup"><span data-stu-id="453c1-252">Date (numeric): Calendar dates, all formats.</span></span> <span data-ttu-id="453c1-253">Inkluderar tal (till exempel 1-11-2020).</span><span class="sxs-lookup"><span data-stu-id="453c1-253">Includes numbers (for example, 1-11-2020).</span></span>
- <span data-ttu-id="453c1-254">Tid: 12- och 24-timmarsformat.</span><span class="sxs-lookup"><span data-stu-id="453c1-254">Time: 12 and 24 hour formats.</span></span>
- <span data-ttu-id="453c1-255">Tal: positiva och negativa tal upp till två decimaler.</span><span class="sxs-lookup"><span data-stu-id="453c1-255">Number: Positive and negative numbers up to two decimals.</span></span> 
- <span data-ttu-id="453c1-256">Procent: en lista över mönster som representerar en procentsats.</span><span class="sxs-lookup"><span data-stu-id="453c1-256">Percentage: A list of patterns representing a percentage.</span></span> <span data-ttu-id="453c1-257">Till exempel, 1 %, 11 %, 100 %, eller 11,11 %.</span><span class="sxs-lookup"><span data-stu-id="453c1-257">For example, 1%, 11%, 100%, or 11.11%.</span></span>
- <span data-ttu-id="453c1-258">Telefonnummer: Vanliga amerikanska och internationella format.</span><span class="sxs-lookup"><span data-stu-id="453c1-258">Phone number: Common US and International formats.</span></span> <span data-ttu-id="453c1-259">Till exempel, 000 000 0000, 000-000-0000, (000)000-0000, eller (000) 000-0000.</span><span class="sxs-lookup"><span data-stu-id="453c1-259">For example, 000 000 0000, 000-000-0000, (000)000-0000, or (000) 000-0000.</span></span>
- <span data-ttu-id="453c1-260">Postnummer: amerikanska postnummerformat.</span><span class="sxs-lookup"><span data-stu-id="453c1-260">Zip code: US Zip code formats.</span></span> <span data-ttu-id="453c1-261">Till exempel: 11111, 11111-1111.</span><span class="sxs-lookup"><span data-stu-id="453c1-261">For example, 11111, 11111-1111.</span></span>
- <span data-ttu-id="453c1-262">Första ordet i meningen: vanliga mönster för ord upp till nio tecken.</span><span class="sxs-lookup"><span data-stu-id="453c1-262">First word of sentence: Common patterns for words up to nine characters.</span></span> 
- <span data-ttu-id="453c1-263">Slutet av mening: vanligt skiljetecken för slutet av en mening.</span><span class="sxs-lookup"><span data-stu-id="453c1-263">End of sentence: Common punctuation for end of a sentence.</span></span>
- <span data-ttu-id="453c1-264">Kreditkort: vanliga talformat för kreditkort.</span><span class="sxs-lookup"><span data-stu-id="453c1-264">Credit card: Common credit card number formats.</span></span> <span data-ttu-id="453c1-265">Till exempel: 1111-1111-1111-1111.</span><span class="sxs-lookup"><span data-stu-id="453c1-265">For example, 1111-1111-1111-1111.</span></span> 
- <span data-ttu-id="453c1-p132">Personnummer: US personnummer-format, till exempel, 111-11-1111.</span><span class="sxs-lookup"><span data-stu-id="453c1-p132">Social security number: US Social Security Number format. For example, 111-11-1111.</span></span> 
- <span data-ttu-id="453c1-268">Kryssruta: en fraslista som representerar variationer på en ifylld kryssruta.</span><span class="sxs-lookup"><span data-stu-id="453c1-268">Checkbox: A phrase list representing variations on a filled in checkbox.</span></span> <span data-ttu-id="453c1-269">Till exempel, _X_, _ _X_.</span><span class="sxs-lookup"><span data-stu-id="453c1-269">For example, _X_, _ _X_.</span></span>
- <span data-ttu-id="453c1-270">Valuta: vanligaste internationella symboler.</span><span class="sxs-lookup"><span data-stu-id="453c1-270">Currency: Major international symbols.</span></span> <span data-ttu-id="453c1-271">Exempel: $.</span><span class="sxs-lookup"><span data-stu-id="453c1-271">For example, $.</span></span> 
- <span data-ttu-id="453c1-272">Kopia i e-post: en fraslista med termen "CC:" som ofta finns nära namnen eller e-postadresserna till andra personer eller grupper som meddelandet skickades till.</span><span class="sxs-lookup"><span data-stu-id="453c1-272">Email CC: A phrase list with the term 'CC:', often found near the names or email addresses of other people or groups the message was sent to.</span></span>
- <span data-ttu-id="453c1-273">E-postdatum: en fraslista med termen "Skickat den:" förekommer ofta nära det datum då meddelandet skickades.</span><span class="sxs-lookup"><span data-stu-id="453c1-273">Email date: A phrase list with the term 'Sent on:', often found near the date the email was sent.</span></span>
- <span data-ttu-id="453c1-274">E-posthälsning: vanliga inledande rader för e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="453c1-274">Email greeting: Common opening lines for emails.</span></span>
- <span data-ttu-id="453c1-275">E-postmottagare: en fraslista med termen "Till:" som ofta finns nära namnen eller e-postadresserna till personer eller grupper som meddelandet skickades till.</span><span class="sxs-lookup"><span data-stu-id="453c1-275">Email recipient: A phrase list with the term 'To:', often found near the names or email addresses of people or groups the message was sent to.</span></span> 
- <span data-ttu-id="453c1-276">E-postavsändare: en fraslista med termen "Från:" förekommer ofta nära avsändarens namn eller e-postadress.</span><span class="sxs-lookup"><span data-stu-id="453c1-276">Email sender: A phrase list with the term 'From:', often found near the sender's name or email address.</span></span> 
- <span data-ttu-id="453c1-277">Ämne för e-post: en fraslista med termen "Ämne:" som ofta finns nära e-postmeddelandets ämne.</span><span class="sxs-lookup"><span data-stu-id="453c1-277">Email subject: A phrase list with the term 'Subject:', often found near the email's subject.</span></span>

<span data-ttu-id="453c1-278">I förklaringsbiblioteket finns också flera vanliga förklaringar för *reguljära* uttryck, till exempel:</span><span class="sxs-lookup"><span data-stu-id="453c1-278">The explanation library also includes commonly used *regular expression* explanations, including:</span></span>

- <span data-ttu-id="453c1-279">6 till 17 siffror: Matchar ett tal mellan 6 och 17 siffror.</span><span class="sxs-lookup"><span data-stu-id="453c1-279">6 to 17 digit numbers: Matches any number from 6 to 17 digits long.</span></span> <span data-ttu-id="453c1-280">Bankkontonummer medborgare i USA passar det här mönstret.</span><span class="sxs-lookup"><span data-stu-id="453c1-280">US bank account numbers fit this pattern.</span></span>
- <span data-ttu-id="453c1-281">E-postadress: matchar en gemensam typ av e-postadress som meganb@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="453c1-281">Email address: Matches a common type of email address like meganb@contoso.com.</span></span>
- <span data-ttu-id="453c1-282">ID-nummer för skatteskyldig medborgare i USA: matchar ett 9-siffrigt nummer som börjar med 6 följt av ett 7-siffigt nummer som börjar med 8 eller 8</span><span class="sxs-lookup"><span data-stu-id="453c1-282">US taxpayer ID number: Matches a three-digit number starting with 9 followed by a 6 digit number starting with 7 or 8.</span></span> 
- <span data-ttu-id="453c1-283">Webbadress (URL): Matchar formatet på en webbadress, som börjar med http:// eller https://.</span><span class="sxs-lookup"><span data-stu-id="453c1-283">Web address (URL): Matches the format of a web address, starting with http:// or https://.</span></span>

<span data-ttu-id="453c1-284">Dessutom finns i förklaringsbiblioteket tre automatiska malltyper som fungerar med de data som du har märkt i exempelfilerna:</span><span class="sxs-lookup"><span data-stu-id="453c1-284">In addition, the explanation library includes three automatic template types that work with the data you've labeled in your example files:</span></span>

- <span data-ttu-id="453c1-285">Efter etikett: De ord eller tecken som förekommer efter etiketterna i exempelfilerna.</span><span class="sxs-lookup"><span data-stu-id="453c1-285">After label: The words or characters that occur after the labels in the example files.</span></span>
- <span data-ttu-id="453c1-286">Före etikett: De ord eller tecken som förekommer före etiketterna i exempelfilerna.</span><span class="sxs-lookup"><span data-stu-id="453c1-286">Before label: The words or characters that occur before the labels in the example files.</span></span>
- <span data-ttu-id="453c1-287">Etiketter: Upp till de första 10 etiketterna från exempelfilerna.</span><span class="sxs-lookup"><span data-stu-id="453c1-287">Labels: Up to the first 10 labels from the example files.</span></span>

<span data-ttu-id="453c1-288">Om du vill ge dig ett exempel på hur automatiska mallar fungerar, i följande exempelfil, kommer vi att använda förklaringsmallen Före etikett för att ge modellen mer information för att få en mer exakt matchning.</span><span class="sxs-lookup"><span data-stu-id="453c1-288">To give you an example of how automatic templates work, in the following example file, we'll use the Before label explanation template to help give the model more information to get a more accurate match.</span></span>

![Exempelfil](../media/content-understanding/before-label.png)

<span data-ttu-id="453c1-290">När du väljer mallen förklaringsmallen Före etikett letar den efter den första uppsättningen ord som visas före etiketten i dina exempelfiler.</span><span class="sxs-lookup"><span data-stu-id="453c1-290">When you select the Before label explanation template, it will look for the first set of words that appear before the label in your example files.</span></span> <span data-ttu-id="453c1-291">I exemplet är orden som identifierats i den första exempelfilen "Från och med".</span><span class="sxs-lookup"><span data-stu-id="453c1-291">In the example, the words that are identified in the first example file is "As of".</span></span>

![Före etikettmall](../media/content-understanding/before-label-explanation.png)

<span data-ttu-id="453c1-293">Du kan välja **Lägg** om du vill skapa en förklaring från mallen.</span><span class="sxs-lookup"><span data-stu-id="453c1-293">You can select **Add** to create an explanation from the template.</span></span>  <span data-ttu-id="453c1-294">När du lägger till fler exempelfiler identifieras och läggs ytterligare ord till i fraslistan.</span><span class="sxs-lookup"><span data-stu-id="453c1-294">As you add more example files, additional words will be identified and added to the phrase list.</span></span>

![Lägga till etiketten](../media/content-understanding/before-label-add.png)
 
#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="453c1-296">Använda en mall från förklaringsbiblioteket</span><span class="sxs-lookup"><span data-stu-id="453c1-296">To use a template from the explanation library</span></span>

1. <span data-ttu-id="453c1-297">Välj **Ny** i avsnittet **Förklaringar** på modellens sida **Träna** och välj **Från en mall**.</span><span class="sxs-lookup"><span data-stu-id="453c1-297">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span>

   ![Lägg till före etikett](../media/content-understanding/from-template.png)

2.  <span data-ttu-id="453c1-299">På sidan **Förklaringsmallar** väljer du den förklaring du vill använda och väljer sedan **Lägga till**.</span><span class="sxs-lookup"><span data-stu-id="453c1-299">On the **Explanation templates** page, select the explanation you want to use, then select **Add**.</span></span>

    ![Välj en mall](../media/content-understanding/phone-template.png)

3. <span data-ttu-id="453c1-301">Informationen för den mall som du valde visas på sidan **Skapa en förklaring**.</span><span class="sxs-lookup"><span data-stu-id="453c1-301">The information for the template you selected displays on the **Create an explanation** page.</span></span> <span data-ttu-id="453c1-302">Om det behövs kan du redigera namnet på förklaringen och lägga till eller ta bort objekt från fraslistan.</span><span class="sxs-lookup"><span data-stu-id="453c1-302">If needed, edit the explanation name and add or remove items from the phrase list.</span></span>  

    ![Redigera mall](../media/content-understanding/phone-template-live.png)

4. <span data-ttu-id="453c1-304">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="453c1-304">When finished, select **Save**.</span></span>