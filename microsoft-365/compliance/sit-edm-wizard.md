---
title: Använd Exact Data Match-schemat och guiden för typ av känslig information
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Läs mer om att använda Exact Data Match-schemat och guiden för typ av känslig information.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5fdf289c403d8c09342a1eac1434c4219bb7b13c
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861665"
---
# <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a><span data-ttu-id="9b8f5-103">Använd Exact Data Match-schemat och guiden för typ av känslig information</span><span class="sxs-lookup"><span data-stu-id="9b8f5-103">Use the Exact Data Match Schema and Sensitive Information Type Wizard</span></span>

<span data-ttu-id="9b8f5-104">[Att skapa en anpassad typ av känslig information med EDM-baserad (Exact Data Match) klassificering](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) innefattar flera steg.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-104">[Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)  involves many steps.</span></span>  <span data-ttu-id="9b8f5-105">Du kan använda den här guiden till att skapa schema- och SIT-mönsterfiler (rule package) för att förenkla processen.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-105">You can use this wizard to create your schema and sensitive information type (SIT) pattern (rule package) files to help simplify the process.</span></span>

> [!NOTE]
> <span data-ttu-id="9b8f5-106">Exact Data Match-schemat och guiden för typ av känslig information är endast tillgänglig för World Wide- och GCC-molnen.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-106">The Exact Data Match Schema and Sensitive Information Type Wizard is only available for the World Wide and GCC clouds only.</span></span>

<span data-ttu-id="9b8f5-107">Guiden kan användas i stället för:</span><span class="sxs-lookup"><span data-stu-id="9b8f5-107">This wizard can be used instead of the:</span></span>

- [<span data-ttu-id="9b8f5-108">Definiera schemat för databasen med känslig information</span><span class="sxs-lookup"><span data-stu-id="9b8f5-108">Define the schema for your database of sensitive information</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#define-the-schema-for-your-database-of-sensitive-information)
- [<span data-ttu-id="9b8f5-109">Konfigurera ett mönster (regelpaket)</span><span class="sxs-lookup"><span data-stu-id="9b8f5-109">Set up a pattern (rule package)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#set-up-a-rule-package)

<span data-ttu-id="9b8f5-110">steg i [del 1: Konfigurera EDM-baserad klassificering](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span><span class="sxs-lookup"><span data-stu-id="9b8f5-110">steps in [Part 1: Set up EDM-based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="9b8f5-111">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="9b8f5-111">Pre-requisites</span></span>

1. <span data-ttu-id="9b8f5-112">Bekanta dig med stegen för att skapa en anpassad typ av känslig information med EDM:s [arbetsflöde i korthet](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance).</span><span class="sxs-lookup"><span data-stu-id="9b8f5-112">Familiarize yourself with the steps to create a custom sensitive information type with EDM [work flow at a glance](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance).</span></span>

2. <span data-ttu-id="9b8f5-113">Utför stegen i avsnittet [Spara känsliga data i .csv-format](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format).</span><span class="sxs-lookup"><span data-stu-id="9b8f5-113">Perform the steps in the [Save sensitive data in .csv format](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format) section.</span></span>

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a><span data-ttu-id="9b8f5-114">Använda Exact Data Match-schemat och mönsterguiden för typ av känslig information</span><span class="sxs-lookup"><span data-stu-id="9b8f5-114">Use the exact data match schema and sensitive information type pattern wizard</span></span>

1. <span data-ttu-id="9b8f5-115">I Microsoft 365 Efterlevnadscenter för klientorganisationen går du till **Dataklassificering** > **Exakta datamatchningar**.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-115">In the Microsoft 365 Compliance center for your tenant go to **Data classification** > **Exact data matches**.</span></span>

2. <span data-ttu-id="9b8f5-116">Välj **Skapa EDM-schema** för att öppna schemaguidens utfällbara konfiguration.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-116">Choose **Create EDM schema** to open the schema wizard configuration flyout.</span></span>

![Utfällbar konfigurationsguide för att skapa ett EDM-schema](../media/edm-schema-wizard-1.png)

3. <span data-ttu-id="9b8f5-118">Fyll i **Namn** och **Beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-118">Fill in an appropriate **Name** and **Description**.</span></span>

4. <span data-ttu-id="9b8f5-119">Välj **Ignorera avgränsare och skiljetecken för alla schemafält om** du vill ha det beteendet.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-119">Choose **Ignore delimiters and punctuation for all schema fields** if you want that behavior.</span></span> <span data-ttu-id="9b8f5-120">Mer information om hur du konfigurerar EDM för att ignorera fall eller avgränsare finns i Skapa en anpassad typ av känslig information med [EDM-baserad klassificering (Exact Data Match).](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)</span><span class="sxs-lookup"><span data-stu-id="9b8f5-120">To learn more about configuring EDM to ignore case or delimiters, see [Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

5. <span data-ttu-id="9b8f5-121">Fyll i önskade värden i **schemafältet och #1** lägg till fler fält efter behov.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-121">Fill in your desired values for your **Schema field #1** and add more fields as needed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="9b8f5-122">Minst ett men inte fler än fem av schemafälten måste anges som sökbara.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-122">At least one, but no more than five of your schema fields must be designated as searchable.</span></span>

6. <span data-ttu-id="9b8f5-123">Välj Spara.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-123">Choose save.</span></span> <span data-ttu-id="9b8f5-124">Schemat finns nu i listan.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-124">Your schema will now be listed.</span></span>

7. <span data-ttu-id="9b8f5-125">Välj **EDM-typer av känslig information** och **Skapa EDM-typ av känslig information** för att öppna konfigurationsguiden för känsliga informationstyper.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-125">Choose **EDM sensitive info types** and **Create EDM sensitive info type** to open the sensitive info type configuration wizard.</span></span>

8. <span data-ttu-id="9b8f5-126">Välj **Välj ett befintligt EDM-schema** och välj det schema som du skapade i steg 2–6 i listan.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-126">Choose **Choose an existing EDM schema** and choose the schema you created in steps 2-6 from the list.</span></span>

9. <span data-ttu-id="9b8f5-127">Välj **Nästa** och **Skapa mönster**.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-127">Choose **Next** and choose **Create pattern**.</span></span>

10. <span data-ttu-id="9b8f5-128">Välj **Konfidensnivå** och **Primärt element**.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-128">Choose the **Confidence level** and **Primary element**.</span></span>  <span data-ttu-id="9b8f5-129">Mer information om hur du konfigurerar ett mönster finns i [Skapa en anpassad typ av känslig information i Microsoft 365 Efterlevnadscenter](create-a-custom-sensitive-information-type.md)</span><span class="sxs-lookup"><span data-stu-id="9b8f5-129">To learn more about configuring a pattern, see [Create a custom sensitive information type in the Compliance Center](create-a-custom-sensitive-information-type.md)</span></span>

11.  <span data-ttu-id="9b8f5-130">Välj **Det primära elementets typ av känslig information** att associera det med.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-130">Choose the **Primary element's sensitive info type** to associate it with.</span></span> <span data-ttu-id="9b8f5-131">Se [Entitetsdefinitioner för typ av känslig information](sensitive-information-type-entity-definitions.md) för läsa mer om de tillgängliga typerna av känslig information.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-131">See [Sensitive Information Type Entity Definitions](sensitive-information-type-entity-definitions.md) to learn more about the available sensitive information types.</span></span>

12. <span data-ttu-id="9b8f5-132">Välj **Klar**.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-132">Choose **Done**.</span></span>

13. <span data-ttu-id="9b8f5-133">Välj önskad **Konfidensnivå och teckennärhet**.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-133">Choose your desired **Confidence level and character proximity**.</span></span>  <span data-ttu-id="9b8f5-134">Detta blir standardvärdet för hela den EDM-känsliga informationstypen</span><span class="sxs-lookup"><span data-stu-id="9b8f5-134">This will be the default value for the whole EDM sensitive info type</span></span>

13. <span data-ttu-id="9b8f5-135">Välj **Skapa mönster** om du vill skapa ytterligare mönster för din typ av EDM-känslig information.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-135">Choose **Create pattern** if you want to create additional patterns for your EDM sensitive info type.</span></span>

14. <span data-ttu-id="9b8f5-136">Välj **Nästa** och fyll i ett **Namn** och en **Beskrivning för administratörer**.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-136">Choose **Next** and fill in a **Name** and **Description for admins**.</span></span>

15. <span data-ttu-id="9b8f5-137">Granska och välj **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-137">Review and choose **Submit**.</span></span>

<span data-ttu-id="9b8f5-138">Du kan ta bort eller redigera mönstret för den känsliga informationstypen genom att markera det som visar redigerings- och borttagningskontrollerna.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-138">You can delete or edit the sensitive information type pattern by selecting it which surfaces the edit and delete controls.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9b8f5-139">Om du vill ta bort ett schema som redan är associerat med en EDM-känslig informationstyp, måste du först ta bort den EDM-känsliga informationstypen. Sedan kan du ta bort schemat.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-139">If you want to remove a schema, and it is already associated with an EDM sensitive info type, you must first delete the EDM sensitive info type, then you can delete the schema.</span></span>

## <a name="post-creation-steps"></a><span data-ttu-id="9b8f5-140">Steg efter skapande</span><span class="sxs-lookup"><span data-stu-id="9b8f5-140">Post creation steps</span></span>

<span data-ttu-id="9b8f5-141">När du har använt den här guiden för att skapa dina filer för EDM-schemat och mönstret (regelpaket), måste du fortfarande utföra stegen i [Del 2: Hasha och ladda upp känsliga data](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) innan du kan använda den anpassade EDM-känsliga informationstypen.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-141">After you have used this wizard to create your EDM schema and pattern (rule package) files, you still have to perform the steps in [Part 2: Hash and upload the sensitive data](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) before you can use the EDM custom sensitive information type.</span></span>

<span data-ttu-id="9b8f5-142">När du har verifierat att tabellen med känslig information har överförts korrekt kan du testa att den fungerar som den ska.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-142">After verifying that your sensitive information table has correctly been uploaded, you can test that it's working properly.</span></span>

1. <span data-ttu-id="9b8f5-143">Öppna **klassificeringscenter**  >  **för dataklassificering**  >  **av känsliga informationstyper.**</span><span class="sxs-lookup"><span data-stu-id="9b8f5-143">Open **Compliance center** > **Data classification** > **Sensitive Information Types**.</span></span>
2. <span data-ttu-id="9b8f5-144">Välj din EDM SIT i listan och välj sedan **Testa** i det utfällbara fönstret.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-144">Select your EDM SIT from the list and then select **Test** in the flyout pane.</span></span> 
3. <span data-ttu-id="9b8f5-145">Upload ett objekt som innehåller data som du vill identifiera, till exempel skapa ett objekt som innehåller en del av informationen i tabellen över känslig information.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-145">Upload an item that contains data you want to detect, for example create an item that contains some of the data in your sensitive information table.</span></span> <span data-ttu-id="9b8f5-146">Om du har använt funktionen för konfigurerbar matchning i schemat för att definiera ignorerade avgränsare ska du se till att objektet innehåller exempel med och utan de avgränsare.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-146">If you used the configurable match feature in your schema to define ignored delimiters, make sure the item includes examples with and without those delimiters.</span></span>
4. <span data-ttu-id="9b8f5-147">När filen har laddats upp och sökts igenom kontrollerar du om det finns matchningar för din EDM SIT.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-147">After the file has been uploaded and scanned, check for matches to your EDM SIT.</span></span>
5. <span data-ttu-id="9b8f5-148">Om funktionen **Test** i SIT upptäcker en matchning kontrollerar du att den inte trimmar den eller extraherar den felaktigt.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-148">If the **Test** function in the SIT detects a match, check that it is not trimming it or extracting it incorrectly.</span></span> <span data-ttu-id="9b8f5-149">Genom att exempelvis bara extrahera en understräng av hela strängen ska den identifiera eller bara hämta det första ordet i en sträng med flera ord, eller inkludera extra symboler eller tecken i extrahering.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-149">For example by extracting only a substring of the full string it is supposed to detect, or picking up only the first word in a multi-word string, or including extra symbols or characters in the extraction.</span></span> <span data-ttu-id="9b8f5-150">Se [Reguljära uttryck – snabbreferens för](/dotnet/standard/base-types/regular-expression-language-quick-reference) referensen till reguljära uttryck.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-150">See [Regular Expression Language - Quick Reference](/dotnet/standard/base-types/regular-expression-language-quick-reference) for the regular expression language reference.</span></span> 

### <a name="troubleshooting"></a><span data-ttu-id="9b8f5-151">Felsökning</span><span class="sxs-lookup"><span data-stu-id="9b8f5-151">Troubleshooting</span></span>

<span data-ttu-id="9b8f5-152">Om du inte hittar några matchningar kan du prova följande:</span><span class="sxs-lookup"><span data-stu-id="9b8f5-152">If you don't find any matches, try the following:</span></span>
- <span data-ttu-id="9b8f5-153">Kontrollera att känsliga data har laddats upp på rätt sätt med de kommandon som beskrivs i vägledning av känsliga data med hjälp av [EDM-verktyget.](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)</span><span class="sxs-lookup"><span data-stu-id="9b8f5-153">Confirm that your sensitive data was uploaded correctly using the commands explained in [the guidance for uploading your sensitive data using the EDM tool](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>
- <span data-ttu-id="9b8f5-154">Kontrollera att de exempel som du har angett i objektet finns i tabellen för känslig information och att ignorerade avgränsare är korrekta.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-154">Check that the examples you entered in the item are present in your sensitive information table and that the ignored delimiters are correct.</span></span>
- <span data-ttu-id="9b8f5-155">**Testa** den SIT du använde när du konfigurerade det primära elementet i vart och ett av dina mönster.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-155">**Test** the SIT you used when you configured the primary element in each of your patterns.</span></span> <span data-ttu-id="9b8f5-156">Detta bekräftar att SIT kan matcha exemplen i objektet.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-156">This will confirm that the SIT is able to match the examples in the item.</span></span> 
  -  <span data-ttu-id="9b8f5-157">Om det SIT du valde för ett primärt element i EDM-typen inte hittar en matchning i objektet eller hittar färre matchningar än du väntat dig, kontrollerar du att det har stöd för avgränsare som finns i innehållet.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-157">If the SIT you selected for a primary element in the EDM type doesn't find a match in the item or finds fewer matches than you expected, check that it supports separators and delimiters that exist in the content.</span></span> <span data-ttu-id="9b8f5-158">Se till att ta med de ignorerade avgränsare som definierats i schemat.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-158">Be sure to include the ignored delimiters defined in your schema.</span></span> 
  -  <span data-ttu-id="9b8f5-159">Om funktionen **Test** inte hittar något innehåll alls kontrollerar du om den SIT du valde innehåller krav för ytterligare nyckelord eller andra valideringar.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-159">If the **Test** function does not detect any content at all, check if the SIT you selected includes requirements for additional keywords or other validations.</span></span> <span data-ttu-id="9b8f5-160">Information om inbyggda SIT:er finns i [Definitioner av](sensitive-information-type-entity-definitions.md) entitetsdefinitioner för typer av känslig information och kontrollera vilka minimikraven är för att matcha varje typ.</span><span class="sxs-lookup"><span data-stu-id="9b8f5-160">For the built-in SITs, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md) to verify what the minimum requirements are for matching each type.</span></span>
