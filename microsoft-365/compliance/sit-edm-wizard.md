---
title: Använd Exact Data Match-schemat och guiden för typ av känslig information
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Läs mer om att använda Exact Data Match-schemat och guiden för typ av känslig information.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2081de887e09794350222dac3527bb3ff932837a
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/16/2020
ms.locfileid: "52161642"
---
# <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a><span data-ttu-id="4a8e1-103">Använd Exact Data Match-schemat och guiden för typ av känslig information</span><span class="sxs-lookup"><span data-stu-id="4a8e1-103">Use the Exact Data Match Schema and Sensitive Information Type Wizard</span></span>

<span data-ttu-id="4a8e1-104">[Att skapa en anpassad typ av känslig information med EDM-baserad (Exact Data Match) klassificering](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) innefattar flera steg.</span><span class="sxs-lookup"><span data-stu-id="4a8e1-104">[Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)  involves many steps.</span></span>  <span data-ttu-id="4a8e1-105">Du kan använda guiden till att skapa mönsterfiler för schemat och typen av känslig information (regelpaket) som förenklar processen.</span><span class="sxs-lookup"><span data-stu-id="4a8e1-105">You can use this wizard to create your schema and sensitive information type pattern (rule package) files to help simplify the process.</span></span>

> [!NOTE]
> <span data-ttu-id="4a8e1-106">Exact Data Match-schemat och guiden för typ av känslig information är endast tillgänglig för World Wide- och GCC-molnen.</span><span class="sxs-lookup"><span data-stu-id="4a8e1-106">The Exact Data Match Schema and Sensitive Information Type Wizard is only available for the World Wide and GCC clouds only.</span></span>

<span data-ttu-id="4a8e1-107">Guiden kan användas i stället för:</span><span class="sxs-lookup"><span data-stu-id="4a8e1-107">This wizard can be used instead of the:</span></span>

- [<span data-ttu-id="4a8e1-108">Definiera schemat för databasen med känslig information</span><span class="sxs-lookup"><span data-stu-id="4a8e1-108">Define the schema for your database of sensitive information</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#define-the-schema-for-your-database-of-sensitive-information)
- [<span data-ttu-id="4a8e1-109">Konfigurera ett mönster (regelpaket)</span><span class="sxs-lookup"><span data-stu-id="4a8e1-109">Set up a pattern (rule package)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#set-up-a-rule-package)

<span data-ttu-id="4a8e1-110">steg i [del 1: Konfigurera EDM-baserad klassificering](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span><span class="sxs-lookup"><span data-stu-id="4a8e1-110">steps in [Part 1: Set up EDM-based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="4a8e1-111">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="4a8e1-111">Pre-requisites</span></span>

1. <span data-ttu-id="4a8e1-112">Bekanta dig med stegen för att skapa en anpassad typ av känslig information med EDM:s [arbetsflöde i korthet](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance).</span><span class="sxs-lookup"><span data-stu-id="4a8e1-112">Familiarize yourself with the steps to create a custom sensitive information type with EDM [work flow at a glance](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance).</span></span>

2. <span data-ttu-id="4a8e1-113">Utför stegen i avsnittet [Spara känsliga data i .csv-format](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format).</span><span class="sxs-lookup"><span data-stu-id="4a8e1-113">Perform the steps in the [Save sensitive data in .csv format](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format) section.</span></span>

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a><span data-ttu-id="4a8e1-114">Använda Exact Data Match-schemat och mönsterguiden för typ av känslig information</span><span class="sxs-lookup"><span data-stu-id="4a8e1-114">Use the exact data match schema and sensitive information type pattern wizard</span></span>

1. <span data-ttu-id="4a8e1-115">I Microsoft 365 Efterlevnadscenter för klientorganisationen går du till **Dataklassificering** > **Exakta datamatchningar**.</span><span class="sxs-lookup"><span data-stu-id="4a8e1-115">In the Microsoft 365 Compliance center for your tenant go to **Data classification** > **Exact data matches**.</span></span>

2. <span data-ttu-id="4a8e1-116">Välj **Skapa EDM-schema** för att öppna schemaguidens utfällbara konfiguration.</span><span class="sxs-lookup"><span data-stu-id="4a8e1-116">Choose **Create EDM schema** to open the schema wizard configuration flyout.</span></span>

![Utfällbar konfigurationsguide för att skapa ett EDM-schema](../media/edm-schema-wizard-1.png)

3. <span data-ttu-id="4a8e1-118">Fyll i **Namn** och **Beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="4a8e1-118">Fill in an appropriate **Name** and **Description**.</span></span>

4. <span data-ttu-id="4a8e1-119">Välj **Ignorera avgränsare och skiljetecken för alla schemafält** om du vill ha den funktionen.</span><span class="sxs-lookup"><span data-stu-id="4a8e1-119">Choose **Ignore delimiters and punctuations for all schema fields** if you want that behavior.</span></span> <span data-ttu-id="4a8e1-120">Mer information om hur du konfigurerar att EDM ignorerar skiftlägen eller avgränsare finns i [Skapa en anpassad typ av känslig information med EDM-baserad (Exact Data Match) klassificering](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="4a8e1-120">To learn more about configuring EDM to ignore case or delimitere, see [Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

5. <span data-ttu-id="4a8e1-121">Fyll i önskade värden i **schemafältet och #1** lägg till fler fält efter behov.</span><span class="sxs-lookup"><span data-stu-id="4a8e1-121">Fill in your desired values for your **Schema field #1** and add more fields as needed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="4a8e1-122">Minst ett men inte fler än fem av schemafälten måste anges som sökbara.</span><span class="sxs-lookup"><span data-stu-id="4a8e1-122">At least one, but no more than five of your schema fields must be designated as searchable.</span></span>

6. <span data-ttu-id="4a8e1-123">Välj Spara.</span><span class="sxs-lookup"><span data-stu-id="4a8e1-123">Choose save.</span></span> <span data-ttu-id="4a8e1-124">Schemat finns nu i listan.</span><span class="sxs-lookup"><span data-stu-id="4a8e1-124">Your schema will now be listed.</span></span>

7. <span data-ttu-id="4a8e1-125">Välj **EDM-typer av känslig information** och **Skapa EDM-typ av känslig information** för att öppna konfigurationsguiden för känsliga informationstyper.</span><span class="sxs-lookup"><span data-stu-id="4a8e1-125">Choose **EDM sensitive info types** and **Create EDM sensitive info type** to open the sensitive info type configuration wizard.</span></span>

8. <span data-ttu-id="4a8e1-126">Välj **Välj ett befintligt EDM-schema** och välj det schema som du skapade i steg 2–6 i listan.</span><span class="sxs-lookup"><span data-stu-id="4a8e1-126">Choose **Choose an existing EDM schema** and choose the schema you created in steps 2-6 from the list.</span></span>

9. <span data-ttu-id="4a8e1-127">Välj **Nästa** och **Skapa mönster**.</span><span class="sxs-lookup"><span data-stu-id="4a8e1-127">Choose **Next** and choose **Create pattern**.</span></span>

10. <span data-ttu-id="4a8e1-128">Välj **Konfidensnivå** och **Primärt element**.</span><span class="sxs-lookup"><span data-stu-id="4a8e1-128">Choose the **Confidence level** and **Primary element**.</span></span>  <span data-ttu-id="4a8e1-129">Mer information om hur du konfigurerar ett mönster finns i [Skapa en anpassad typ av känslig information i Microsoft 365 Efterlevnadscenter](create-a-custom-sensitive-information-type.md)</span><span class="sxs-lookup"><span data-stu-id="4a8e1-129">To learn more about configuring a pattern, see [Create a custom sensitive information type in the Compliance Center](create-a-custom-sensitive-information-type.md)</span></span>

11.  <span data-ttu-id="4a8e1-130">Välj **Det primära elementets typ av känslig information** att associera det med.</span><span class="sxs-lookup"><span data-stu-id="4a8e1-130">Choose the **Primary element's sensitive info type** to associate it with.</span></span> <span data-ttu-id="4a8e1-131">Se [Entitetsdefinitioner för typ av känslig information](sensitive-information-type-entity-definitions.md) för läsa mer om de tillgängliga typerna av känslig information.</span><span class="sxs-lookup"><span data-stu-id="4a8e1-131">See [Sensitive Information Type Entity Definitions](sensitive-information-type-entity-definitions.md) to learn more about the available sensitive information types.</span></span>

12. <span data-ttu-id="4a8e1-132">Välj **Klar**.</span><span class="sxs-lookup"><span data-stu-id="4a8e1-132">Choose **Done**.</span></span>

13. <span data-ttu-id="4a8e1-133">Välj önskad **Konfidensnivå och teckennärhet**.</span><span class="sxs-lookup"><span data-stu-id="4a8e1-133">Choose your desired **Confidence level and character proximity**.</span></span>  <span data-ttu-id="4a8e1-134">Detta blir standardvärdet för hela den EDM-känsliga informationstypen</span><span class="sxs-lookup"><span data-stu-id="4a8e1-134">This will be the default value for the whole EDM sensitive info type</span></span>

13. <span data-ttu-id="4a8e1-135">Välj **Skapa mönster** om du vill skapa fler mönster för din EDM-känsliga informationstyp.</span><span class="sxs-lookup"><span data-stu-id="4a8e1-135">Choose **Create pattern** if you want to creaet additional patterns for your EDM sensitive info type.</span></span>

14. <span data-ttu-id="4a8e1-136">Välj **Nästa** och fyll i ett **Namn** och en **Beskrivning för administratörer**.</span><span class="sxs-lookup"><span data-stu-id="4a8e1-136">Choose **Next** and fill in a **Name** and **Description for admins**.</span></span>

15. <span data-ttu-id="4a8e1-137">Granska och välj **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="4a8e1-137">Review and choose **Submit**.</span></span>

<span data-ttu-id="4a8e1-138">Du kan ta bort eller redigera mönstret för den känsliga informationstypen genom att markera det som visar redigerings- och borttagningskontrollerna.</span><span class="sxs-lookup"><span data-stu-id="4a8e1-138">You can delete or edit the sensitive information type pattern by selecting it which surfaces the edit and delete controls.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4a8e1-139">Om du vill ta bort ett schema som redan är associerat med en EDM-känslig informationstyp, måste du först ta bort den EDM-känsliga informationstypen. Sedan kan du ta bort schemat.</span><span class="sxs-lookup"><span data-stu-id="4a8e1-139">If you want to remove a schema, and it is already associated with an EDM sensitive info type, you must first delete the EDM sensitive info type, then you can delete the schema.</span></span>

## <a name="post-steps"></a><span data-ttu-id="4a8e1-140">Publicera steg</span><span class="sxs-lookup"><span data-stu-id="4a8e1-140">Post steps</span></span>

<span data-ttu-id="4a8e1-141">När du har använt den här guiden för att skapa dina filer för EDM-schemat och mönstret (regelpaket), måste du fortfarande utföra stegen i [Del 2: Hasha och ladda upp känsliga data](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) innan du kan använda den anpassade EDM-känsliga informationstypen.</span><span class="sxs-lookup"><span data-stu-id="4a8e1-141">After you have used this wizard to create your EDM schema and pattern (rule package) files, you still have to perform the steps in [Part 2: Hash and upload the sensitive data](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) before you can use the EDM custom sensitive information type.</span></span>