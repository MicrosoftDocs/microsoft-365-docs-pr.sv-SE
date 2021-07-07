---
title: Referens för anpassade typer av känslig information
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: I den här artikeln visas en lista med filter som kan kodas i anpassade typer av känslig information.
ms.openlocfilehash: 6dfa562d581f14c0b1ac41c4ce803e2367a94636
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322967"
---
# <a name="custom-sensitive-information-type-filters-reference"></a><span data-ttu-id="99b33-103">Referens för anpassade typer av känslig information</span><span class="sxs-lookup"><span data-stu-id="99b33-103">Custom sensitive information type filters reference</span></span>

<span data-ttu-id="99b33-104">I Microsoft kan du definiera filter eller ytterligare kontroller när du skapar anpassade typer av känslig information (SIT).</span><span class="sxs-lookup"><span data-stu-id="99b33-104">In Microsoft you can define filters or additional checks while creating a custom sensitive information types (SIT).</span></span>

## <a name="list-of-supported-filters-and-use-cases"></a><span data-ttu-id="99b33-105">Lista över filter som stöds och användningsfall</span><span class="sxs-lookup"><span data-stu-id="99b33-105">List of supported filters and use cases</span></span>

### <a name="alldigitssame-exclude"></a><span data-ttu-id="99b33-106">AllDigitsSame Exclude</span><span class="sxs-lookup"><span data-stu-id="99b33-106">AllDigitsSame Exclude</span></span>

<span data-ttu-id="99b33-107">Beskrivning: Tillåter dig att utesluta matchningar som har alla siffror som dubblettsiffror, t.ex. 111111111 eller 111-111-111-111</span><span class="sxs-lookup"><span data-stu-id="99b33-107">Description: Allows you to exclude matches which have all digits as duplicate digits, like 111111111 or 111-111-111</span></span>

<span data-ttu-id="99b33-108">Definiera filter</span><span class="sxs-lookup"><span data-stu-id="99b33-108">Defining filters</span></span>
```xml
<Filters id="ssn_filters">
    <Filter type="AllDigitsSameFilter"></Filter>
</Filters>
```

<span data-ttu-id="99b33-109">Använda det i regelpaket på entitetsnivån</span><span class="sxs-lookup"><span data-stu-id="99b33-109">Using it in rule package at the entity level</span></span>
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85"  filters="ssn_filters">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

<span data-ttu-id="99b33-110">Använda det i regelpaket på mönsternivån</span><span class="sxs-lookup"><span data-stu-id="99b33-110">Using it in rule package at the pattern level</span></span>
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="ssn_filters">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

### <a name="textmatchfilter-startswith"></a><span data-ttu-id="99b33-111">TextMatchFilter StartsWith</span><span class="sxs-lookup"><span data-stu-id="99b33-111">TextMatchFilter StartsWith</span></span> 

<span data-ttu-id="99b33-112">Beskrivning: Med den här funktionen kan du definiera starttecken för entiteten.</span><span class="sxs-lookup"><span data-stu-id="99b33-112">Description: Allows you to define the starting characters for the entity.</span></span> <span data-ttu-id="99b33-113">Den har två varianter, inkluderar och exkluderar.</span><span class="sxs-lookup"><span data-stu-id="99b33-113">It has two variants, include and exclude.</span></span>

<span data-ttu-id="99b33-114">Om du till exempel vill utesluta tal som börjar med 0500, 91, 091, 010 i en lista som den här:</span><span class="sxs-lookup"><span data-stu-id="99b33-114">For example to exclude the numbers starting with 0500, 91, 091, 010 in a list like this:</span></span>

- <span data-ttu-id="99b33-115">0500-4500-027</span><span class="sxs-lookup"><span data-stu-id="99b33-115">0500-4500-027</span></span>
- <span data-ttu-id="99b33-116">91564721450</span><span class="sxs-lookup"><span data-stu-id="99b33-116">91564721450</span></span>
- <span data-ttu-id="99b33-117">91-8523697410</span><span class="sxs-lookup"><span data-stu-id="99b33-117">91-8523697410</span></span>
- <span data-ttu-id="99b33-118">700-8956-7844</span><span class="sxs-lookup"><span data-stu-id="99b33-118">700-8956-7844</span></span>
- <span data-ttu-id="99b33-119">1000-3265-9874</span><span class="sxs-lookup"><span data-stu-id="99b33-119">1000-3265-9874</span></span>
- <span data-ttu-id="99b33-120">0100-7892-3012</span><span class="sxs-lookup"><span data-stu-id="99b33-120">0100-7892-3012</span></span>

<span data-ttu-id="99b33-121">kan du använda den här xml-koden</span><span class="sxs-lookup"><span data-stu-id="99b33-121">you can use this xml</span></span>

```xml
<Filters id="phone_number_filters_exc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Exclude" textProcessorId="Keyword_false_positives_sw">
</Filter>
</Filters>

  <Keyword id="Keyword_false_positives_sw">
    <Group matchStyle="string">
      <Term>0500</Term>
      <Term>91</Term>
      <Term>091</Term>
      <Term>0100</Term>
    </Group>
  </Keyword>
```
<span data-ttu-id="99b33-122">Om du till exempel vill ta med tal som börjar med 0500, 91, 091, 0100 i en lista så här:</span><span class="sxs-lookup"><span data-stu-id="99b33-122">For example, to include the numbers starting with 0500, 91, 091, 0100 in a list like this:</span></span> 

- <span data-ttu-id="99b33-123">0500-4500-027</span><span class="sxs-lookup"><span data-stu-id="99b33-123">0500-4500-027</span></span>
- <span data-ttu-id="99b33-124">91564721450</span><span class="sxs-lookup"><span data-stu-id="99b33-124">91564721450</span></span>
- <span data-ttu-id="99b33-125">91-8523697410</span><span class="sxs-lookup"><span data-stu-id="99b33-125">91-8523697410</span></span>
- <span data-ttu-id="99b33-126">700-8956-7844</span><span class="sxs-lookup"><span data-stu-id="99b33-126">700-8956-7844</span></span>
- <span data-ttu-id="99b33-127">1000-3265-9874</span><span class="sxs-lookup"><span data-stu-id="99b33-127">1000-3265-9874</span></span>
- <span data-ttu-id="99b33-128">0100-7892-3012</span><span class="sxs-lookup"><span data-stu-id="99b33-128">0100-7892-3012</span></span>

<span data-ttu-id="99b33-129">kan du använda den här xml-koden</span><span class="sxs-lookup"><span data-stu-id="99b33-129">you can use this xml</span></span>

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-endswith"></a><span data-ttu-id="99b33-130">TextMatchFilter EndsWith</span><span class="sxs-lookup"><span data-stu-id="99b33-130">TextMatchFilter EndsWith</span></span> 

<span data-ttu-id="99b33-131">Beskrivning: Med den här funktionen kan du definiera sluttecken för entiteten.</span><span class="sxs-lookup"><span data-stu-id="99b33-131">Description: Allows you to define the ending characters for the entity.</span></span> 

<span data-ttu-id="99b33-132">Om du till exempel vill utesluta tal som slutar med 0500 91 091, 0100 i en lista som den här:</span><span class="sxs-lookup"><span data-stu-id="99b33-132">For example, to exclude the numbers ending with 0500,91,091, 0100 in a list like this:</span></span>

- <span data-ttu-id="99b33-133">1234567891</span><span class="sxs-lookup"><span data-stu-id="99b33-133">1234567891</span></span>
- <span data-ttu-id="99b33-134">1234-5678-0091</span><span class="sxs-lookup"><span data-stu-id="99b33-134">1234-5678-0091</span></span>
- <span data-ttu-id="99b33-135">1234.4567.7091</span><span class="sxs-lookup"><span data-stu-id="99b33-135">1234.4567.7091</span></span>
- <span data-ttu-id="99b33-136">1234-8091-4564</span><span class="sxs-lookup"><span data-stu-id="99b33-136">1234-8091-4564</span></span>

<span data-ttu-id="99b33-137">kan du använda den här xml-koden</span><span class="sxs-lookup"><span data-stu-id="99b33-137">you can use this xml</span></span>

```xml
<Filters id="phone_number_filters_exc">
    <Filter type="TextMatchFilter" direction="EndsWith" logic="Exclude" textProcessorId="Keyword_false_positives_sw">
</Filter>

  <Keyword id="Keyword_false_positives_sw">
    <Group matchStyle="string">
      <Term>0500</Term>
      <Term>91</Term>
      <Term>091</Term>
      <Term>0100</Term>
    </Group>
  </Keyword>
```

<span data-ttu-id="99b33-138">Om du till exempel vill ta med tal som slutar med 0500, 91, 091, 0100 i en lista som den här:</span><span class="sxs-lookup"><span data-stu-id="99b33-138">For example, to include the numbers ending with 0500, 91, 091, 0100, in a list like this:</span></span>

- <span data-ttu-id="99b33-139">1234567891</span><span class="sxs-lookup"><span data-stu-id="99b33-139">1234567891</span></span>
- <span data-ttu-id="99b33-140">1234-5678-0091</span><span class="sxs-lookup"><span data-stu-id="99b33-140">1234-5678-0091</span></span>
- <span data-ttu-id="99b33-141">1234.4567.7091</span><span class="sxs-lookup"><span data-stu-id="99b33-141">1234.4567.7091</span></span>
- <span data-ttu-id="99b33-142">1234-8091-4564</span><span class="sxs-lookup"><span data-stu-id="99b33-142">1234-8091-4564</span></span>

<span data-ttu-id="99b33-143">kan du använda den här xml-koden</span><span class="sxs-lookup"><span data-stu-id="99b33-143">you can use this xml</span></span>

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction=" EndsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-full"></a><span data-ttu-id="99b33-144">TextMatchFilter Full</span><span class="sxs-lookup"><span data-stu-id="99b33-144">TextMatchFilter Full</span></span>

<span data-ttu-id="99b33-145">Beskrivning: Tillåter att du förhindrar vissa matchningar för att förhindra att de utlöser regeln.</span><span class="sxs-lookup"><span data-stu-id="99b33-145">Description: Allows you to prohibit certain matches to prevent them from triggering the rule.</span></span> <span data-ttu-id="99b33-146">Exempel: exkludera 41111111111111111 i listan med giltiga kreditkortsmatcher.</span><span class="sxs-lookup"><span data-stu-id="99b33-146">For example, exclude 4111111111111111 from the list of valid credit card matches.</span></span>

<span data-ttu-id="99b33-147">Om du till exempel vill utesluta kreditkortsnummer som 411111111111111 och 3241891031113111 i en lista så här:</span><span class="sxs-lookup"><span data-stu-id="99b33-147">For example, to exclude credit card numbers like 4111111111111111 and 3241891031113111 in a list like this:</span></span>

- <span data-ttu-id="99b33-148">4485 3647 3952 7352</span><span class="sxs-lookup"><span data-stu-id="99b33-148">4485 3647 3952 7352</span></span>
- <span data-ttu-id="99b33-149">4111111111111111</span><span class="sxs-lookup"><span data-stu-id="99b33-149">4111111111111111</span></span>
- <span data-ttu-id="99b33-150">3241891031113111</span><span class="sxs-lookup"><span data-stu-id="99b33-150">3241891031113111</span></span>

<span data-ttu-id="99b33-151">kan du använda den här xml-koden</span><span class="sxs-lookup"><span data-stu-id="99b33-151">you can use this xml</span></span>

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Full" logic="Exclude" textProcessorId="Keyword_false_positives_full">
</Filter>

  <Keyword id="Keyword_false_positives_full">
    <Group matchStyle="string">
      <Term>4111111111111111</Term>
      <Term>3241891031113111</Term>
    </Group>
  </Keyword>
```

<span data-ttu-id="99b33-152">Om du till exempel vill ta med kreditkortsnummer som 411111111111111 och 3241891031113111 i en lista så här:</span><span class="sxs-lookup"><span data-stu-id="99b33-152">For example, to include credit card numbers like 4111111111111111 and 3241891031113111 in a list like this:</span></span>

- <span data-ttu-id="99b33-153">4485 3647 3952 7352</span><span class="sxs-lookup"><span data-stu-id="99b33-153">4485 3647 3952 7352</span></span>
- <span data-ttu-id="99b33-154">4111111111111111</span><span class="sxs-lookup"><span data-stu-id="99b33-154">4111111111111111</span></span>
- <span data-ttu-id="99b33-155">3241891031113111</span><span class="sxs-lookup"><span data-stu-id="99b33-155">3241891031113111</span></span>

<span data-ttu-id="99b33-156">kan du använda den här xml-koden</span><span class="sxs-lookup"><span data-stu-id="99b33-156">you can use this xml</span></span>

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_false_positives_full">
</Filter>
```

### <a name="textmatchfilter-prefix"></a><span data-ttu-id="99b33-157">TextMatchfilter-prefix</span><span class="sxs-lookup"><span data-stu-id="99b33-157">TextMatchFilter Prefix</span></span>

<span data-ttu-id="99b33-158">Beskrivning: Med den här funktionen kan du definiera de föregående tecknen som alltid ska tas med eller utelämnas.</span><span class="sxs-lookup"><span data-stu-id="99b33-158">Description: Allows you to define the preceding characters that should be always included or excluded.</span></span> <span data-ttu-id="99b33-159">Om kreditkortsnummer föregås av Order-ID tar du bort matchningen från de giltiga matchningarna.</span><span class="sxs-lookup"><span data-stu-id="99b33-159">For example, if Credit card number is preceded by ‘Order ID:’ then remove the match from the valid matches.</span></span>

<span data-ttu-id="99b33-160">Om du till exempel vill utesluta förekomster av telefonnummer  som har **Telefon och** ringer mig på strängar före telefonnumret, i en lista som den här:</span><span class="sxs-lookup"><span data-stu-id="99b33-160">For example, to exclude occurrences of phone numbers which have **Phone number** and **call me at** strings before the phone number, in a list like this:</span></span>

- <span data-ttu-id="99b33-161">telefonnummer 091-8974-653278</span><span class="sxs-lookup"><span data-stu-id="99b33-161">phone number 091-8974-653278</span></span>
- <span data-ttu-id="99b33-162">Telefon 45 124576532-123</span><span class="sxs-lookup"><span data-stu-id="99b33-162">Phone 45-124576532-123</span></span>
- <span data-ttu-id="99b33-163">45-124576532-123</span><span class="sxs-lookup"><span data-stu-id="99b33-163">45-124576532-123</span></span>

<span data-ttu-id="99b33-164">kan du använda den här xml-koden</span><span class="sxs-lookup"><span data-stu-id="99b33-164">you can use this xml</span></span>

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_prefix">
</Filter>
  <Keyword id="Keyword_false_positives_prefix">
    <Group matchStyle="string">
      <Term>phone number</Term>
      <Term>call me at</Term>
    </Group>
  </Keyword>
```

<span data-ttu-id="99b33-165">Om du till exempel vill ta med **förekomster** som har kreditkorts- och **kortnummersträngar** före kreditkortsnumret, i en lista som den här:</span><span class="sxs-lookup"><span data-stu-id="99b33-165">For example, to include occurrences that have **credit card** and **card #** strings before the credit card number, in a list like this:</span></span>

- <span data-ttu-id="99b33-166">Kreditkort 45-124576532-123</span><span class="sxs-lookup"><span data-stu-id="99b33-166">Credit card 45-124576532-123</span></span> 
- <span data-ttu-id="99b33-167">45-124576532-123 (vilket kan vara telefonnummer)</span><span class="sxs-lookup"><span data-stu-id="99b33-167">45-124576532-123  (which could be phone number)</span></span>

<span data-ttu-id="99b33-168">kan du använda den här xml-koden</span><span class="sxs-lookup"><span data-stu-id="99b33-168">you can use this xml</span></span>

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_true_positives_prefix">
</Filter>

  <Keyword id="Keyword_true_positives_prefix">
    <Group matchStyle="string">
      <Term>credit card</Term>
      <Term>card #</Term>
    </Group>
  </Keyword
```

### <a name="textmatchfilter-suffix"></a><span data-ttu-id="99b33-169">TextMatchFilter-suffix</span><span class="sxs-lookup"><span data-stu-id="99b33-169">TextMatchFilter Suffix</span></span>

<span data-ttu-id="99b33-170">Beskrivning: Med den här beskrivningen kan du definiera följande tecken som alltid ska inkluderas eller undantas.</span><span class="sxs-lookup"><span data-stu-id="99b33-170">Description: Allows you to define the following characters that should be always included or excluded.</span></span> <span data-ttu-id="99b33-171">Om kreditkortsnummer följs av "/xuid" tar du bort matchningen från de giltiga matchningarna.</span><span class="sxs-lookup"><span data-stu-id="99b33-171">For example, if Credit card number is followed by ‘/xuid’ then remove the match from the valid matches.</span></span>

<span data-ttu-id="99b33-172">Till exempel översta exkludera förekomster om det finns ytterligare 5 förekomster av fyra siffror som suffix i en lista som den här:</span><span class="sxs-lookup"><span data-stu-id="99b33-172">For example, top exclude occurrences if there are 5 more instances of four digits as suffix in a list like this:</span></span>

- <span data-ttu-id="99b33-173">1234-5678-9321 4500 9870 6321 48925566</span><span class="sxs-lookup"><span data-stu-id="99b33-173">1234-5678-9321 4500 9870 6321 48925566</span></span>
- <span data-ttu-id="99b33-174">1234-5678-9321</span><span class="sxs-lookup"><span data-stu-id="99b33-174">1234-5678-9321</span></span>

<span data-ttu-id="99b33-175">kan du använda den här xml-koden</span><span class="sxs-lookup"><span data-stu-id="99b33-175">you can use this xml</span></span>

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Regex_false_positives_suffix">
</Filter>

  <Regexid="Regex_false_positives_suffix">(\d{4}){5,}</Regex>
```
<span data-ttu-id="99b33-176">Om du till exempel vill utesluta förekomster om de följs av **/xuidsuffix**, som ett i den här listan:</span><span class="sxs-lookup"><span data-stu-id="99b33-176">For example, to exclude occurrences if they are followed by **/xuidsuffix**, like one in this list:</span></span>

- <span data-ttu-id="99b33-177">1234-5678-9321 /xuid</span><span class="sxs-lookup"><span data-stu-id="99b33-177">1234-5678-9321 /xuid</span></span>
- <span data-ttu-id="99b33-178">1234-5678-9321</span><span class="sxs-lookup"><span data-stu-id="99b33-178">1234-5678-9321</span></span>

<span data-ttu-id="99b33-179">kan du använda den här xml-koden</span><span class="sxs-lookup"><span data-stu-id="99b33-179">you can use this xml</span></span>

<span data-ttu-id="99b33-180">''xml <Filters id="cc_number_filters_exc"></span><span class="sxs-lookup"><span data-stu-id="99b33-180">\`\`xml <Filters id="cc_number_filters_exc"></span></span>
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_suffix">
</Filter>

  <span data-ttu-id="99b33-181"><Keyword id="Keyword_false_positives_suffix"> <Group matchStyle="string">
      </span><span class="sxs-lookup"><span data-stu-id="99b33-181"><Keyword id="Keyword_false_positives_suffix"> <Group matchStyle="string">
      </span></span><Term><span data-ttu-id="99b33-182">/xuid</span><span class="sxs-lookup"><span data-stu-id="99b33-182">/xuid</span></span></Term>
    <span data-ttu-id="99b33-183"></Group> </Keyword></span><span class="sxs-lookup"><span data-stu-id="99b33-183"></Group> </Keyword></span></span>
```

For example, to include an occurrence only if it is followed by **cvv** or **expires**, like two in this list:

- 45-124576532-123 
- 45-124576532-123  cvv 966
- 45-124576532-123  expires 03/23

you can use this xml

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_true_positives_suffix">
</Filter>

  <Keyword id="Keyword_true_positives_suffix">
    <Group matchStyle="string">
      <Term>cvv</Term>
      <Term>expires</Term>
    </Group>
  </Keyword>
```

## <a name="using-filters-in-rule-packages"></a><span data-ttu-id="99b33-184">Använda filter i regelpaket</span><span class="sxs-lookup"><span data-stu-id="99b33-184">Using filters in rule packages</span></span>

<span data-ttu-id="99b33-185">Filter kan definieras på hela SIT eller på ett mönster.</span><span class="sxs-lookup"><span data-stu-id="99b33-185">Filters can be defined on the entire SIT or on a pattern.</span></span> <span data-ttu-id="99b33-186">Här är några exempel på kodavsnitt.</span><span class="sxs-lookup"><span data-stu-id="99b33-186">Here are some code snippets examples.</span></span> 

### <a name="at-sensitive-information-type-level"></a><span data-ttu-id="99b33-187">På nivå med känslig information</span><span class="sxs-lookup"><span data-stu-id="99b33-187">At sensitive information type level</span></span>

<span data-ttu-id="99b33-188">Filter hos Entitet – täcker alla underordnade mönster</span><span class="sxs-lookup"><span data-stu-id="99b33-188">Filters at Entity - will cover all child patterns</span></span>

<span data-ttu-id="99b33-189">Filtren används på alla **instanser** som klassificeras av något av mönster i den enheten/den känsliga typen</span><span class="sxs-lookup"><span data-stu-id="99b33-189">The filters will be applied on **all** the instances classified by any of the patterns in that entity / sensitive type</span></span>

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
```

### <a name="at-the-individual-pattern-of-the-sensitive-information-type-level"></a><span data-ttu-id="99b33-190">På det enskilda mönstret i typnivån för känslig information</span><span class="sxs-lookup"><span data-stu-id="99b33-190">At the individual pattern of the sensitive information type level</span></span>

<span data-ttu-id="99b33-191">Filtrerar bara på mönsternivån.</span><span class="sxs-lookup"><span data-stu-id="99b33-191">Filters only at the pattern level.</span></span>

<span data-ttu-id="99b33-192">Filtret används för de instanser som matchas av mönstret.</span><span class="sxs-lookup"><span data-stu-id="99b33-192">The filter will be applied on the instances matched by the pattern.</span></span>

```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Keyword_cc_verification" />
      </Pattern>
</Entity>
```


### <a name="at-sensitive-information-type-level-and-an-additional-filter-on-some-of-the-patterns-of-that-entity"></a><span data-ttu-id="99b33-193">På typsnivå för känslig information och ett ytterligare filter på vissa av mönster i entiteten</span><span class="sxs-lookup"><span data-stu-id="99b33-193">At sensitive information type level and an additional filter on some of the patterns of that entity</span></span>

<span data-ttu-id="99b33-194">Filter för Entitet + mönster</span><span class="sxs-lookup"><span data-stu-id="99b33-194">Filters at Entity + pattern</span></span>

<span data-ttu-id="99b33-195">Filtren används på alla **instanser** som klassificeras av något av mönster i den enheten/den känsliga typen.</span><span class="sxs-lookup"><span data-stu-id="99b33-195">The filters will be applied on **all** the instances classified by any of the patterns in that entity / sensitive type.</span></span> <span data-ttu-id="99b33-196">Filtret på mönsternivån filtrerar de instanser som matchas av det mönstret.</span><span class="sxs-lookup"><span data-stu-id="99b33-196">The pattern level filter will filter the instances matched by that pattern.</span></span>

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85" filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
``` 

 

## <a name="more-information"></a><span data-ttu-id="99b33-197">Mer information</span><span class="sxs-lookup"><span data-stu-id="99b33-197">More information</span></span>

- [<span data-ttu-id="99b33-198">Mer information om skydd mot dataförlust</span><span class="sxs-lookup"><span data-stu-id="99b33-198">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)

- [<span data-ttu-id="99b33-199">Entitetsdefinitioner för typer av känslig information</span><span class="sxs-lookup"><span data-stu-id="99b33-199">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="99b33-200">Vad DLP-funktionerna letar efter</span><span class="sxs-lookup"><span data-stu-id="99b33-200">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
