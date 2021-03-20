---
title: SKOS formatreferens för SharePoint-taxonomi
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: SKOS formatreferens för SharePoint-taxonomi
ms.openlocfilehash: 6a565de9598706e998206304093ed86a1a55704d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911180"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a><span data-ttu-id="ded87-103">SKOS formatreferens för SharePoint-taxonomi</span><span class="sxs-lookup"><span data-stu-id="ded87-103">SKOS format reference for SharePoint taxonomy</span></span>

<span data-ttu-id="ded87-104">I den här artikeln finns ordlista för RDF som används för att representera [SharePoint-taxonomi](/dotnet/api/microsoft.sharepoint.taxonomy) och som baseras på [SKOS](https://www.w3.org/TR/skos-primer/).</span><span class="sxs-lookup"><span data-stu-id="ded87-104">This article includes RDF vocabulary used to represent [SharePoint taxonomy](/dotnet/api/microsoft.sharepoint.taxonomy) and is based on [SKOS](https://www.w3.org/TR/skos-primer/).</span></span> <span data-ttu-id="ded87-105">Om du vill serialisera RDF använder du RDF [Sköldpadda](https://www.w3.org/TR/turtle/).</span><span class="sxs-lookup"><span data-stu-id="ded87-105">For serialization of this RDF syntax, use RDF [TURTLE](https://www.w3.org/TR/turtle/).</span></span>

<span data-ttu-id="ded87-106">I följande tabell visas de [SKOS](https://www.w3.org/TR/skos-primer/) motsvarigheter till vokabulär i [SharePoint-taxonomi](/dotnet/api/microsoft.sharepoint.taxonomy).</span><span class="sxs-lookup"><span data-stu-id="ded87-106">The following table shows the [SKOS](https://www.w3.org/TR/skos-primer/) equivalents for the [SharePoint taxonomy](/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary.</span></span> <span data-ttu-id="ded87-107">SharePoint har inte stöd för [SKOS](https://www.w3.org/TR/skos-primer/)-värden som inte har någon motsvarighet i SharePoint-taxonomi.</span><span class="sxs-lookup"><span data-stu-id="ded87-107">SharePoint does not support [SKOS](https://www.w3.org/TR/skos-primer/) values that have no SharePoint taxonomy equivalent.</span></span>

|<span data-ttu-id="ded87-108">SharePoint-taxonomi</span><span class="sxs-lookup"><span data-stu-id="ded87-108">SharePoint taxonomy</span></span>|<span data-ttu-id="ded87-109">Motsvarighet i SKOS</span><span class="sxs-lookup"><span data-stu-id="ded87-109">SKOS equivalent</span></span>|
|:-----------------|:--------------|
|<span data-ttu-id="ded87-110">sharepoint-taxonomi:Term</span><span class="sxs-lookup"><span data-stu-id="ded87-110">sharepoint-taxonomy:Term</span></span>|<span data-ttu-id="ded87-111">skos:Concept</span><span class="sxs-lookup"><span data-stu-id="ded87-111">skos:Concept</span></span>|
|<span data-ttu-id="ded87-112">sharepoint-taxonomi:TermSet</span><span class="sxs-lookup"><span data-stu-id="ded87-112">sharepoint-taxonomy:TermSet</span></span>|<span data-ttu-id="ded87-113">skos:ConceptScheme</span><span class="sxs-lookup"><span data-stu-id="ded87-113">skos:ConceptScheme</span></span>|
|<span data-ttu-id="ded87-114">sharepoint-taxonomi:inTermSet</span><span class="sxs-lookup"><span data-stu-id="ded87-114">sharepoint-taxonomy:inTermSet</span></span>|<span data-ttu-id="ded87-115">skos:inSchema</span><span class="sxs-lookup"><span data-stu-id="ded87-115">skos:inScheme</span></span>|
|<span data-ttu-id="ded87-116">sharepoint-taxonomi:hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="ded87-116">sharepoint-taxonomy:hasTopLevelTerm</span></span>|<span data-ttu-id="ded87-117">skos:hasTopConcept</span><span class="sxs-lookup"><span data-stu-id="ded87-117">skos:hasTopConcept</span></span>|
|<span data-ttu-id="ded87-118">sharepoint-taxonomi:topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="ded87-118">sharepoint-taxonomy:topLevelTermOf</span></span>|<span data-ttu-id="ded87-119">skos:topConceptOf</span><span class="sxs-lookup"><span data-stu-id="ded87-119">skos:topConceptOf</span></span>|
|<span data-ttu-id="ded87-120">SharePoint-taxonomi:defaultLabel</span><span class="sxs-lookup"><span data-stu-id="ded87-120">sharepoint-taxonomy:defaultLabel</span></span>|<span data-ttu-id="ded87-121">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="ded87-121">skos:prefLabel</span></span>|
|<span data-ttu-id="ded87-122">sharepoint-taxonomi:termSetName</span><span class="sxs-lookup"><span data-stu-id="ded87-122">sharepoint-taxonomy:termSetName</span></span>|<span data-ttu-id="ded87-123">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="ded87-123">skos:prefLabel</span></span>|
|<span data-ttu-id="ded87-124">sharepoint-taxonomi:propertyName</span><span class="sxs-lookup"><span data-stu-id="ded87-124">sharepoint-taxonomy:propertyName</span></span>|<span data-ttu-id="ded87-125">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="ded87-125">skos:prefLabel</span></span>|
|<span data-ttu-id="ded87-126">sharepoint-taxonomi:otherLabel</span><span class="sxs-lookup"><span data-stu-id="ded87-126">sharepoint-taxonomy:otherLabel</span></span>|<span data-ttu-id="ded87-127">skos:altLabel</span><span class="sxs-lookup"><span data-stu-id="ded87-127">skos:altLabel</span></span>|
|<span data-ttu-id="ded87-128">sharepoint-taxonomi:description</span><span class="sxs-lookup"><span data-stu-id="ded87-128">sharepoint-taxonomy:description</span></span>|<span data-ttu-id="ded87-129">skos:definition</span><span class="sxs-lookup"><span data-stu-id="ded87-129">skos:definition</span></span>|
|<span data-ttu-id="ded87-130">sharepoint-taxonomi:parent</span><span class="sxs-lookup"><span data-stu-id="ded87-130">sharepoint-taxonomy:parent</span></span>|<span data-ttu-id="ded87-131">skos:broader</span><span class="sxs-lookup"><span data-stu-id="ded87-131">skos:broader</span></span>|
|<span data-ttu-id="ded87-132">sharepoint-taxonomi:child</span><span class="sxs-lookup"><span data-stu-id="ded87-132">sharepoint-taxonomy:child</span></span>|<span data-ttu-id="ded87-133">skos:narrower</span><span class="sxs-lookup"><span data-stu-id="ded87-133">skos:narrower</span></span>|

<span data-ttu-id="ded87-134">I följande tabell visas de enheter i SharePoint-taxonomivokabulär som härleddes från [OWL](https://www.w3.org/TR/owl2-primer/).</span><span class="sxs-lookup"><span data-stu-id="ded87-134">The following table displays the entities of the SharePoint taxonomy vocabulary derived from [OWL](https://www.w3.org/TR/owl2-primer/).</span></span>

|<span data-ttu-id="ded87-135">SharePoint-taxonomivokabulär</span><span class="sxs-lookup"><span data-stu-id="ded87-135">SharePoint taxonomy vocabulary</span></span>|<span data-ttu-id="ded87-136">Härledd från OWL</span><span class="sxs-lookup"><span data-stu-id="ded87-136">Derived from OWL</span></span>|
|:-----------------------------|:----------------------|
|<span data-ttu-id="ded87-137">sharepoint-taxonomi:isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="ded87-137">sharepoint-taxonomy:isAvailableForTagging</span></span>|<span data-ttu-id="ded87-138">owl:datatypeproperty</span><span class="sxs-lookup"><span data-stu-id="ded87-138">owl:datatypeproperty</span></span>|
|<span data-ttu-id="ded87-139">sharepoint-taxonomi:SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="ded87-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="ded87-140">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="ded87-140">owl:ObjectProperty</span></span>|
|<span data-ttu-id="ded87-141">sharepoint-taxonomi:LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="ded87-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="ded87-142">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="ded87-142">owl:ObjectProperty</span></span>|
|<span data-ttu-id="ded87-143">sharepoint-taxonomi:CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="ded87-143">sharepoint-taxonomy:CustomPropertyForTermSet</span></span>|<span data-ttu-id="ded87-144">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="ded87-144">owl:ObjectProperty</span></span>|

## <a name="sharepoint-taxonomy-vocabulary"></a><span data-ttu-id="ded87-145">SharePoint-taxonomivokabulär</span><span class="sxs-lookup"><span data-stu-id="ded87-145">SharePoint taxonomy vocabulary</span></span>

<span data-ttu-id="ded87-146">En taxonomi är ett formellt klassificeringssystem.</span><span class="sxs-lookup"><span data-stu-id="ded87-146">A taxonomy is a formal classification system.</span></span> <span data-ttu-id="ded87-147">En taxonomi grupperar ord, etiketter och termer som beskriver något och sedan ordnar grupper i en hierarki.</span><span class="sxs-lookup"><span data-stu-id="ded87-147">A taxonomy groups the words, labels, and terms that describe something, and then arranges the groups into a hierarchy.</span></span>

<span data-ttu-id="ded87-148">**sharepoint-taxonomi:Term**</span><span class="sxs-lookup"><span data-stu-id="ded87-148">**sharepoint-taxonomy:Term**</span></span>

<span data-ttu-id="ded87-149">Representerar en term eller ett nyckelord i en hierarki med hanterade metadata.</span><span class="sxs-lookup"><span data-stu-id="ded87-149">Represents a Term or a Keyword in a managed metadata hierarchy.</span></span>

<span data-ttu-id="ded87-150">En [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) är den atomiska enheten i en SharePoint [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span><span class="sxs-lookup"><span data-stu-id="ded87-150">A [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) is the atomic unit of a SharePoint [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span></span> <span data-ttu-id="ded87-151">Varje [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) tillhör en [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) som tillhör ett [TermGroup](/dotnet/api/microsoft.sharepoint.taxonomy.group).</span><span class="sxs-lookup"><span data-stu-id="ded87-151">Each [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) belongs to a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) that belongs to a [TermGroup](/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> 

<span data-ttu-id="ded87-152">Syntaxen för att definiera en [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) är följande:</span><span class="sxs-lookup"><span data-stu-id="ded87-152">The syntax to define a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) is as follows:</span></span>

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="ded87-153">En [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) existerar obligatoriskt i ett [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="ded87-153">A [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) compulsorily exists within a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="ded87-154">DefaultLabel är namnet på [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)en som det visas i den visuella presentationen.</span><span class="sxs-lookup"><span data-stu-id="ded87-154">DefaultLabel is the name of the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) as it appears in the visual representation.</span></span> <span data-ttu-id="ded87-155">De obligatoriska fälten för att definiera en [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) inkluderar:</span><span class="sxs-lookup"><span data-stu-id="ded87-155">The required fields for defining a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) include:</span></span>

- <span data-ttu-id="ded87-156">SharePoint-taxonomi:defaultLabel</span><span class="sxs-lookup"><span data-stu-id="ded87-156">sharepoint-taxonomy:defaultLabel</span></span>
- <span data-ttu-id="ded87-157">sharepoint-taxonomi:inTermSet</span><span class="sxs-lookup"><span data-stu-id="ded87-157">sharepoint-taxonomy:inTermSet</span></span>

<span data-ttu-id="ded87-158">En [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) kan:</span><span class="sxs-lookup"><span data-stu-id="ded87-158">A [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) can:</span></span>

- <span data-ttu-id="ded87-159">Vara hierarkiskt relaterad till en annan [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) om båda [Termerna](/dotnet/api/microsoft.sharepoint.taxonomy.term) tillhör samma [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="ded87-159">Be hierarchically related to another [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) that is provided both the [Terms](/dotnet/api/microsoft.sharepoint.taxonomy.term) belong to the same [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="ded87-160">Ha flera underordnade [Termer](/dotnet/api/microsoft.sharepoint.taxonomy.term) men bara en överordnad [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="ded87-160">Have multiple child [Terms](/dotnet/api/microsoft.sharepoint.taxonomy.term), but only a single parent [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>
- <span data-ttu-id="ded87-161">Inte har någon överordnad [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) definierad om det är en topLevelTermOf ett [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="ded87-161">Not have a parent [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) defined, if it is a topLevelTermOf a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="ded87-162">Ha en defaultLabel, per [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) arbetsspråk.</span><span class="sxs-lookup"><span data-stu-id="ded87-162">Have one defaultLabel, per [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>
- <span data-ttu-id="ded87-163">Inte finnas om den varken innehåller en överordnad [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) eller är topLevelTermOf ett [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="ded87-163">Not exist if it neither contains a parent [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term), nor is the topLevelTermOf a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> 
- <span data-ttu-id="ded87-164">Har bara ett unikt defaultLabel på samma hierarkiska nivå.</span><span class="sxs-lookup"><span data-stu-id="ded87-164">Have only a unique defaultLabel in the same hierarchical level.</span></span>

<span data-ttu-id="ded87-165">**sharepoint-taxonomi:TermSet**</span><span class="sxs-lookup"><span data-stu-id="ded87-165">**sharepoint-taxonomy:TermSet**</span></span>

<span data-ttu-id="ded87-166">Representerar en hierarkisk eller platt uppsättning termobjekt som kallas "TermSet".</span><span class="sxs-lookup"><span data-stu-id="ded87-166">Represents a hierarchical or flat set of Term objects known as a "TermSet".</span></span>

<span data-ttu-id="ded87-167">Som namnet antyder är TermSet en uppsättning [Termer](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="ded87-167">As the name suggests, TermSet is a set of [Terms](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="ded87-168">En [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) i en [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) måste tillhöra ett [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="ded87-168">A [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) must belong to a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="ded87-169">Ingen [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) kan finnas oberoende.</span><span class="sxs-lookup"><span data-stu-id="ded87-169">No [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) can exist independently.</span></span> 

<span data-ttu-id="ded87-170">Syntaxen för att definiera en [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) är:</span><span class="sxs-lookup"><span data-stu-id="ded87-170">The syntax to define a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

<span data-ttu-id="ded87-171">[TermSets](/dotnet/api/microsoft.sharepoint.taxonomy.termset) är logiskt grupperade i [TermGroups](/dotnet/api/microsoft.sharepoint.taxonomy.group).</span><span class="sxs-lookup"><span data-stu-id="ded87-171">[TermSets](/dotnet/api/microsoft.sharepoint.taxonomy.termset) are logically grouped together in [TermGroups](/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> <span data-ttu-id="ded87-172">Det obligatoriska fältet för att definiera en [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) är:</span><span class="sxs-lookup"><span data-stu-id="ded87-172">The required field for defining a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

- <span data-ttu-id="ded87-173">sharepoint-taxonomi:termSetName</span><span class="sxs-lookup"><span data-stu-id="ded87-173">sharepoint-taxonomy:termSetName</span></span>

<span data-ttu-id="ded87-174">Om den termSetName som anges inte är unik i [TermGroup](/dotnet/api/microsoft.sharepoint.taxonomy.group) lägger SharePoint till en siffra i slutet av namnet för att upprätthålla unikheten i termSetName(s).</span><span class="sxs-lookup"><span data-stu-id="ded87-174">In the case of the termSetName provided is not unique within the [TermGroup](/dotnet/api/microsoft.sharepoint.taxonomy.group), SharePoint appends a number at the end of the name to maintain the uniqueness of termSetName(s).</span></span>

<span data-ttu-id="ded87-175">**sharepoint-taxonomi:hasTopLevelTerm**</span><span class="sxs-lookup"><span data-stu-id="ded87-175">**sharepoint-taxonomy:hasTopLevelTerm**</span></span>

<span data-ttu-id="ded87-176">I SharePoint används den här egenskapen för att avbilda den översta [Termen](/dotnet/api/microsoft.sharepoint.taxonomy.term) i [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) som är startpunkten i hierarkin för [Termer](/dotnet/api/microsoft.sharepoint.taxonomy.term) i ett [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="ded87-176">SharePoint uses this property to map the top most [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) in the [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset), which is the entry point to the hierarchy of [Terms](/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="ded87-177">Det här är en inverterad relation till sharepoint-taxonomi:topLevelTermOf.</span><span class="sxs-lookup"><span data-stu-id="ded87-177">This is an inverse relation to sharepoint-taxonomy:topLevelTermOf.</span></span> 

<span data-ttu-id="ded87-178">Syntaxen för att definiera detta är:</span><span class="sxs-lookup"><span data-stu-id="ded87-178">The syntax to define this is:</span></span>

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> <span data-ttu-id="ded87-179">Det går inte att definiera [Term på översta nivån](/dotnet/api/microsoft.sharepoint.taxonomy.term) för en överordnad [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="ded87-179">You cannot define the top level [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) of a parent [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="ded87-180">**sharepoint-taxonomi:topLevelTermOf**</span><span class="sxs-lookup"><span data-stu-id="ded87-180">**sharepoint-taxonomy:topLevelTermOf**</span></span>

<span data-ttu-id="ded87-181">SharePoint-taxonomi:topLevelTermOf är inversen till sharepoint-taxonomi:hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="ded87-181">Sharepoint-taxonomy:topLevelTermOf is the inverse of sharepoint-taxonomy:hasTopLevelTerm</span></span>

<span data-ttu-id="ded87-182">Syntaxen för att definiera detta är:</span><span class="sxs-lookup"><span data-stu-id="ded87-182">The syntax to define this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

<span data-ttu-id="ded87-183">**sharepoint-taxonomi:inTermSet**</span><span class="sxs-lookup"><span data-stu-id="ded87-183">**sharepoint-taxonomy:inTermSet**</span></span>

<span data-ttu-id="ded87-184">Använd det här alternativet om du vill mappen en [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) till ett [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="ded87-184">Use this to map a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) to a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="ded87-185">En [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) kan bara finnas i en enda [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="ded87-185">A [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) can only exist in a single [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="ded87-186">SharePoint kräver den här egenskapen vi [definiering av en term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span><span class="sxs-lookup"><span data-stu-id="ded87-186">SharePoint requires this property when [defining a term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span></span>

## <a name="required-labels"></a><span data-ttu-id="ded87-187">Obligatoriska etiketter</span><span class="sxs-lookup"><span data-stu-id="ded87-187">Required labels</span></span>

<span data-ttu-id="ded87-188">Din organisation kanske vill göra noggrann planering innan du börjar använda hanterade metadata.</span><span class="sxs-lookup"><span data-stu-id="ded87-188">Your organization may want to do careful planning before you start to use managed metadata.</span></span> <span data-ttu-id="ded87-189">Hur mycket planering du måste utföra beror på hur formell din taxonomi är.</span><span class="sxs-lookup"><span data-stu-id="ded87-189">The amount of planning that you must do depends on how formal your taxonomy is.</span></span> <span data-ttu-id="ded87-190">Det beror även på hur mycket kontroll som du vill använda för metadata.</span><span class="sxs-lookup"><span data-stu-id="ded87-190">It also depends on how much control that you want to impose on metadata.</span></span> <span data-ttu-id="ded87-191">På varje nivå i hierarkin måste du konfigurera obligatoriska etiketter för en Term eller ett TermSet.</span><span class="sxs-lookup"><span data-stu-id="ded87-191">At each level of the hierarchy, you need to configure required labels for a Term or TermSet.</span></span>

<span data-ttu-id="ded87-192">En Term kan ha en eller flera etiketter i standardspråket och noll eller fler etiketter på ett annat språk än standardspråket.</span><span class="sxs-lookup"><span data-stu-id="ded87-192">A Term can have one or more labels in the default language, and zero or more labels in the non-default language.</span></span> <span data-ttu-id="ded87-193">Om termen har etiketter på ett språk måste en av etiketterna vara standardetiketten.</span><span class="sxs-lookup"><span data-stu-id="ded87-193">If the term has labels in a language, one of the labels must be the default label.</span></span>

<span data-ttu-id="ded87-194">**sharepoint-taxonomi:defaultLabel**</span><span class="sxs-lookup"><span data-stu-id="ded87-194">**sharepoint-taxonomy:defaultLabel**</span></span>

<span data-ttu-id="ded87-195">Använd den här lexikala standardetiketten för en [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) som är en obligatorisk parameter för en [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="ded87-195">Use this default lexical label for a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) that is a required parameter for a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="ded87-196">Används för att visuellt representera [Termen](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="ded87-196">Use to visually representing the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="ded87-197">Syntaxen för att definiera en defaultLabel är:</span><span class="sxs-lookup"><span data-stu-id="ded87-197">The syntax to define a defaultLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="ded87-198">DefaultLabel innehåller två delar – strängen och språktaggen.</span><span class="sxs-lookup"><span data-stu-id="ded87-198">The defaultLabel contains two parts to it – the string and the language tag.</span></span> <span data-ttu-id="ded87-199">Språket måste vara något av [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) arbetsspråk.</span><span class="sxs-lookup"><span data-stu-id="ded87-199">The language must be one of the [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working languages.</span></span> <span data-ttu-id="ded87-200">DefaultLabel måste vara unika för alla [Termer](/dotnet/api/microsoft.sharepoint.taxonomy.term) i samma [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset), på samma hierarkiska nivå.</span><span class="sxs-lookup"><span data-stu-id="ded87-200">The defaultLabel must be unique for all [Terms](/dotnet/api/microsoft.sharepoint.taxonomy.term) in the same [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset), at the same hierarchical level.</span></span>

<span data-ttu-id="ded87-201">**sharepoint-taxonomi:termSetName**</span><span class="sxs-lookup"><span data-stu-id="ded87-201">**sharepoint-taxonomy:termSetName**</span></span>

<span data-ttu-id="ded87-202">Hämtar och anger namnet på det aktuella TermSet-objektet.</span><span class="sxs-lookup"><span data-stu-id="ded87-202">Gets and sets the name for the current TermSet object.</span></span>

<span data-ttu-id="ded87-203">Det här är en lexikalisk etikett för en [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset)i en [termStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) arbetsspråk.</span><span class="sxs-lookup"><span data-stu-id="ded87-203">This the lexical label for a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset), in a [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span> <span data-ttu-id="ded87-204">Det här är en obligatorisk parameter för ett [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="ded87-204">This is a required parameter for a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="ded87-205">Används för att visuellt representera en [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="ded87-205">Use to visually representing a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>

<span data-ttu-id="ded87-206">Syntaxen för att definiera en termSetName är:</span><span class="sxs-lookup"><span data-stu-id="ded87-206">The syntax to define a termSetName is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

<span data-ttu-id="ded87-207">**sharepoint-taxonomi:propertyName**</span><span class="sxs-lookup"><span data-stu-id="ded87-207">**sharepoint-taxonomy:propertyName**</span></span>

<span data-ttu-id="ded87-208">Hämtar och anger namnet på den aktuella TermSet-objektet.</span><span class="sxs-lookup"><span data-stu-id="ded87-208">Gets and sets the property name for the current TermSet object.</span></span>

<span data-ttu-id="ded87-209">Det här är en lexikalisk etikett för en sharepoint-taxonomi:SharedCustomPropertyForTerm, sharepoint-taxonomi:LocalCustomPropertyForTerm och sharepoint-taxonomi:CustomPropertyForTermSet i en [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) arbetsspråk.</span><span class="sxs-lookup"><span data-stu-id="ded87-209">This is the lexical label for a sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm and sharepoint-taxonomy:CustomPropertyForTermSet in a [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>

<span data-ttu-id="ded87-210">SharePoint-taxonomi:propertyName behandlas som nyckel för CustomProperty.</span><span class="sxs-lookup"><span data-stu-id="ded87-210">The sharepoint-taxonomy:propertyName is treated as the key of the CustomProperty.</span></span>

<span data-ttu-id="ded87-211">Syntaxen för att definiera en propetyName är:</span><span class="sxs-lookup"><span data-stu-id="ded87-211">The syntax to define a propetyName is:</span></span>

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a><span data-ttu-id="ded87-212">Valfria etiketter</span><span class="sxs-lookup"><span data-stu-id="ded87-212">Optional labels</span></span>

<span data-ttu-id="ded87-213">Du kan även lägga till valfria etiketter i din taxonomi.</span><span class="sxs-lookup"><span data-stu-id="ded87-213">You can also add optional labels to your taxonomy.</span></span>

<span data-ttu-id="ded87-214">**sharepoint-taxonomi:otherLabel**</span><span class="sxs-lookup"><span data-stu-id="ded87-214">**sharepoint-taxonomy:otherLabel**</span></span>

<span data-ttu-id="ded87-215">Det här är den alternativa lexikala etiketten för en [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="ded87-215">This is the alternate lexical label for a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="ded87-216">Syntaxen för att definiera en otherLabel är:</span><span class="sxs-lookup"><span data-stu-id="ded87-216">The syntax to define an otherLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a><span data-ttu-id="ded87-217">Semantiska relationer</span><span class="sxs-lookup"><span data-stu-id="ded87-217">Semantic relationships</span></span>

<span data-ttu-id="ded87-218">Taxonomier har hierarkiska och ibland en enkel "relaterad term" som associerande relation men vissa har "semantiska relationer" eller egendefinierade relationer.</span><span class="sxs-lookup"><span data-stu-id="ded87-218">Taxonomies have hierarchical and sometimes a simple “related term” associative relationship, but some have "semantic relationships" or custom-created relationships.</span></span> 

<span data-ttu-id="ded87-219">**sharepoint-taxonomi:parent**</span><span class="sxs-lookup"><span data-stu-id="ded87-219">**sharepoint-taxonomy:parent**</span></span>

<span data-ttu-id="ded87-220">Den här hierarkiska relationen relaterar en [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) till en annan [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="ded87-220">This hierarchically relates a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="ded87-221">En [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) kan vara en toppnivå [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) av ett [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset), men om det inte måste det finnas en överordnad [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="ded87-221">A [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) could be a top level [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) of a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset), but in case it doesn’t it must have a parent [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="ded87-222">Syntaxen för att definiera en parent är:</span><span class="sxs-lookup"><span data-stu-id="ded87-222">The syntax to define a parent is:</span></span>

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

<span data-ttu-id="ded87-223">Det innebär att TermA är det överordnade objektet och TermA är det underordnade.</span><span class="sxs-lookup"><span data-stu-id="ded87-223">This means that TermA is the parent and  TermA is the child.</span></span>

<span data-ttu-id="ded87-224">**sharepoint-taxonomi:child**</span><span class="sxs-lookup"><span data-stu-id="ded87-224">**sharepoint-taxonomy:child**</span></span>

<span data-ttu-id="ded87-225">Objektet innehåller ett eller flera underordnade TermSet-instanser och du kan komma åt dessa via TermSets egenskaper.</span><span class="sxs-lookup"><span data-stu-id="ded87-225">The object contains one or more child TermSet instances, and these can be accessed through the TermSets property.</span></span> <span data-ttu-id="ded87-226">I den här klassen finns också metoder för att skapa nya underordnade TermSet-objekt.</span><span class="sxs-lookup"><span data-stu-id="ded87-226">This class also provides methods for creating new child TermSet objects.</span></span> <span data-ttu-id="ded87-227">Behörigheter för att redigera underordnad Term och TermSet-instanser anges i gruppen.</span><span class="sxs-lookup"><span data-stu-id="ded87-227">Permissions for editing child Term and TermSet instances is specified on the group.</span></span> 

<span data-ttu-id="ded87-228">Den här hierarkiska relationen relaterar en [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) till en annan [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="ded87-228">This hierarchically relates a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="ded87-229">Syntaxen för att definiera ett child är:</span><span class="sxs-lookup"><span data-stu-id="ded87-229">The syntax to define a child is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

<span data-ttu-id="ded87-230">Det innebär att TermA är det överordnade objektet och TermA är det underordnade.</span><span class="sxs-lookup"><span data-stu-id="ded87-230">This means that TermA is the parent and  TermA is the child.</span></span>

## <a name="documentation-notes"></a><span data-ttu-id="ded87-231">Dokumentationskommentarer</span><span class="sxs-lookup"><span data-stu-id="ded87-231">Documentation notes</span></span>

<span data-ttu-id="ded87-232">I det här avsnittet beskrivs taxonomin detaljerad i Microsoft. SharePoint. taxonomins namnrymd.</span><span class="sxs-lookup"><span data-stu-id="ded87-232">This section discusses the taxonomy detailed in the Microsoft.SharePoint.Taxonomy Namespace.</span></span>

<span data-ttu-id="ded87-233">**sharepoint-taxonomi:description**</span><span class="sxs-lookup"><span data-stu-id="ded87-233">**sharepoint-taxonomy:description**</span></span>

<span data-ttu-id="ded87-234">Det här är en detaljerad beskrivning av alla vokabulära enheter i [SharePoint-taxonomi](/dotnet/api/microsoft.sharepoint.taxonomy).</span><span class="sxs-lookup"><span data-stu-id="ded87-234">This is a detailed explanation of any [SharePoint taxonomy](/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary entity.</span></span> 

<span data-ttu-id="ded87-235">Syntaxen för att lägga till en beskrivning är:</span><span class="sxs-lookup"><span data-stu-id="ded87-235">The syntax to add a description is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a><span data-ttu-id="ded87-236">Anpassade egenskaper</span><span class="sxs-lookup"><span data-stu-id="ded87-236">Custom properties</span></span>

<span data-ttu-id="ded87-237">Hämtar en samling egna egenskapsobjekt för det aktuella Termobjektet från den skrivskyddade ordlistan.</span><span class="sxs-lookup"><span data-stu-id="ded87-237">Gets the collection of custom property objects for the current Term object from the read-only dictionary.</span></span>

<span data-ttu-id="ded87-238">Anpassade egenskaper är nyckelvärdespar som kan definieras för en [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) eller [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) för att få en beskrivning av [Termen](/dotnet/api/microsoft.sharepoint.taxonomy.term) eller [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="ded87-238">Custom Properties are key-values pairs that can be defined for a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset), to further the description of the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="ded87-239">I SharePoint anges nyckel för den anpassade egenskapen med hjälp av propertyName.</span><span class="sxs-lookup"><span data-stu-id="ded87-239">SharePoint specifies the key of the custom property with the help of propertyName.</span></span>

<span data-ttu-id="ded87-240">**sharepoint-taxonomi:CustomPropertyForTermSet**</span><span class="sxs-lookup"><span data-stu-id="ded87-240">**sharepoint-taxonomy:CustomPropertyForTermSet**</span></span>

<span data-ttu-id="ded87-241">Syntaxen för att definiera detta är:</span><span class="sxs-lookup"><span data-stu-id="ded87-241">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

<span data-ttu-id="ded87-242">**sharepoint-taxonomi:SharedCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="ded87-242">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span></span>

<span data-ttu-id="ded87-243">Om den anpassade egenskapen för en [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) måste följa med [Termen](/dotnet/api/microsoft.sharepoint.taxonomy.term) när du återanvänder [Termen](/dotnet/api/microsoft.sharepoint.taxonomy.term) någon annanstans måste du definiera den under SharedCustomPropertyForTerm.</span><span class="sxs-lookup"><span data-stu-id="ded87-243">If the custom property for a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) needs to be carried along with the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to be define it under SharedCustomPropertyForTerm.</span></span>

<span data-ttu-id="ded87-244">Syntaxen för att definiera detta är:</span><span class="sxs-lookup"><span data-stu-id="ded87-244">The syntax to define this is:</span></span>

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
<span data-ttu-id="ded87-245">**sharepoint-taxonomi:LocalCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="ded87-245">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span></span>

<span data-ttu-id="ded87-246">Om den anpassade egenskapen för en [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) inte behöver följa med [Termen](/dotnet/api/microsoft.sharepoint.taxonomy.term) när du återanvänder [Termen](/dotnet/api/microsoft.sharepoint.taxonomy.term) någon annanstans, måste du definiera den under LocalCustomPropertyForTerm.</span><span class="sxs-lookup"><span data-stu-id="ded87-246">If the custom property for a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) does not need to be carried along with the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to define it under LocalCustomPropertyForTerm.</span></span>

<span data-ttu-id="ded87-247">Syntaxen för att definiera detta är:</span><span class="sxs-lookup"><span data-stu-id="ded87-247">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a><span data-ttu-id="ded87-248">Dataegenskaper</span><span class="sxs-lookup"><span data-stu-id="ded87-248">Data properties</span></span>

<span data-ttu-id="ded87-249">På varje nivå i hierarkin kan du konfigurera vissa dataegenskaper för en Term eller TermSet.</span><span class="sxs-lookup"><span data-stu-id="ded87-249">At each level of the hierarchy, you can configure specific data properties for a Term or TermSet.</span></span>

<span data-ttu-id="ded87-250">**sharepoint-taxonomi:isAvailableForTagging**</span><span class="sxs-lookup"><span data-stu-id="ded87-250">**sharepoint-taxonomy:isAvailableForTagging**</span></span>

<span data-ttu-id="ded87-251">Använd det här alternativet om du vill ange om en [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) eller [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) tillgänglig i SharePoint-listor och -bibliotek.</span><span class="sxs-lookup"><span data-stu-id="ded87-251">Use this to specify if a [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) available in SharePoint Lists and Libraries.</span></span>  

<span data-ttu-id="ded87-252">Syntaxen för det här är:</span><span class="sxs-lookup"><span data-stu-id="ded87-252">The syntax for this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a><span data-ttu-id="ded87-253">Domän och område</span><span class="sxs-lookup"><span data-stu-id="ded87-253">Domain and range</span></span>

<span data-ttu-id="ded87-254">I tabellen nedan beskrivs domänen och intervallet för SharePoint-taxonomivokabulär.</span><span class="sxs-lookup"><span data-stu-id="ded87-254">The table below describes the domain and range of SharePoint taxonomy vocabulary.</span></span>

|<span data-ttu-id="ded87-255">Predikat/verb</span><span class="sxs-lookup"><span data-stu-id="ded87-255">Predicates/verb</span></span>|<span data-ttu-id="ded87-256">Betydelse</span><span class="sxs-lookup"><span data-stu-id="ded87-256">Meaning</span></span>|<span data-ttu-id="ded87-257">Domän</span><span class="sxs-lookup"><span data-stu-id="ded87-257">Domain</span></span>|<span data-ttu-id="ded87-258">Område</span><span class="sxs-lookup"><span data-stu-id="ded87-258">Range</span></span>|
|:--------------|:------|:-----|:----|
<span data-ttu-id="ded87-259">inTermSet</span><span class="sxs-lookup"><span data-stu-id="ded87-259">inTermSet</span></span>|<span data-ttu-id="ded87-260">I termuppsättning</span><span class="sxs-lookup"><span data-stu-id="ded87-260">In term set</span></span>|<span data-ttu-id="ded87-261">Term</span><span class="sxs-lookup"><span data-stu-id="ded87-261">Term</span></span>|<span data-ttu-id="ded87-262">Termuppsättning</span><span class="sxs-lookup"><span data-stu-id="ded87-262">Term Set</span></span>|
<span data-ttu-id="ded87-263">inTermGroup</span><span class="sxs-lookup"><span data-stu-id="ded87-263">inTermGroup</span></span>|<span data-ttu-id="ded87-264">I termgruppen</span><span class="sxs-lookup"><span data-stu-id="ded87-264">In term group</span></span>|<span data-ttu-id="ded87-265">TermSet</span><span class="sxs-lookup"><span data-stu-id="ded87-265">TermSet</span></span>|<span data-ttu-id="ded87-266">TermGroup</span><span class="sxs-lookup"><span data-stu-id="ded87-266">TermGroup</span></span>|
<span data-ttu-id="ded87-267">topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="ded87-267">topLevelTermOf</span></span>|<span data-ttu-id="ded87-268">Är toppnivåterm för</span><span class="sxs-lookup"><span data-stu-id="ded87-268">Is Top Level Term Of</span></span>|<span data-ttu-id="ded87-269">Term</span><span class="sxs-lookup"><span data-stu-id="ded87-269">Term</span></span>|<span data-ttu-id="ded87-270">TermSet</span><span class="sxs-lookup"><span data-stu-id="ded87-270">TermSet</span></span>|
<span data-ttu-id="ded87-271">hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="ded87-271">hasTopLevelTerm</span></span>|<span data-ttu-id="ded87-272">Har en topnivåterm</span><span class="sxs-lookup"><span data-stu-id="ded87-272">Has top level term</span></span>|<span data-ttu-id="ded87-273">Termuppsättning</span><span class="sxs-lookup"><span data-stu-id="ded87-273">Term Set</span></span>|<span data-ttu-id="ded87-274">Term</span><span class="sxs-lookup"><span data-stu-id="ded87-274">Term</span></span>|
<span data-ttu-id="ded87-275">termSetName</span><span class="sxs-lookup"><span data-stu-id="ded87-275">termSetName</span></span>|<span data-ttu-id="ded87-276">Termuppsättning har namn</span><span class="sxs-lookup"><span data-stu-id="ded87-276">Term set has Name</span></span>|<span data-ttu-id="ded87-277">Term</span><span class="sxs-lookup"><span data-stu-id="ded87-277">Term</span></span>|<span data-ttu-id="ded87-278">Enkel literal</span><span class="sxs-lookup"><span data-stu-id="ded87-278">Plain literal</span></span>|
<span data-ttu-id="ded87-279">defaultLabel</span><span class="sxs-lookup"><span data-stu-id="ded87-279">defaultLabel</span></span>|<span data-ttu-id="ded87-280">Term har standardetikett</span><span class="sxs-lookup"><span data-stu-id="ded87-280">Term has default label</span></span>|<span data-ttu-id="ded87-281">Term</span><span class="sxs-lookup"><span data-stu-id="ded87-281">Term</span></span>|<span data-ttu-id="ded87-282">Enkel literal</span><span class="sxs-lookup"><span data-stu-id="ded87-282">Plain literal</span></span>|
<span data-ttu-id="ded87-283">otherLabel</span><span class="sxs-lookup"><span data-stu-id="ded87-283">otherLabel</span></span>|<span data-ttu-id="ded87-284">Term har annan etikett</span><span class="sxs-lookup"><span data-stu-id="ded87-284">Term has other label</span></span>|<span data-ttu-id="ded87-285">Term</span><span class="sxs-lookup"><span data-stu-id="ded87-285">Term</span></span>|<span data-ttu-id="ded87-286">Enkel literal</span><span class="sxs-lookup"><span data-stu-id="ded87-286">Plain literal</span></span>|
<span data-ttu-id="ded87-287">PropertyName</span><span class="sxs-lookup"><span data-stu-id="ded87-287">propertyName</span></span>|<span data-ttu-id="ded87-288">Har egenskapsetikett</span><span class="sxs-lookup"><span data-stu-id="ded87-288">Has Property Label</span></span>|<span data-ttu-id="ded87-289">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="ded87-289">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span></span> |<span data-ttu-id="ded87-290">Boolesk, sträng, heltal, decimal, dubbel</span><span class="sxs-lookup"><span data-stu-id="ded87-290">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="ded87-291">description</span><span class="sxs-lookup"><span data-stu-id="ded87-291">description</span></span>|<span data-ttu-id="ded87-292">Har beskrivning</span><span class="sxs-lookup"><span data-stu-id="ded87-292">Has Description</span></span>|<span data-ttu-id="ded87-293">Alla</span><span class="sxs-lookup"><span data-stu-id="ded87-293">All</span></span>|<span data-ttu-id="ded87-294">Enkel literal</span><span class="sxs-lookup"><span data-stu-id="ded87-294">Plain literal</span></span>|
|<span data-ttu-id="ded87-295">parent</span><span class="sxs-lookup"><span data-stu-id="ded87-295">parent</span></span>|<span data-ttu-id="ded87-296">Har överordnad</span><span class="sxs-lookup"><span data-stu-id="ded87-296">Has parent</span></span>|<span data-ttu-id="ded87-297">Term</span><span class="sxs-lookup"><span data-stu-id="ded87-297">Term</span></span>|<span data-ttu-id="ded87-298">Term</span><span class="sxs-lookup"><span data-stu-id="ded87-298">Term</span></span>|
|<span data-ttu-id="ded87-299">child</span><span class="sxs-lookup"><span data-stu-id="ded87-299">child</span></span>|<span data-ttu-id="ded87-300">Har underordnad</span><span class="sxs-lookup"><span data-stu-id="ded87-300">Has Child</span></span>|<span data-ttu-id="ded87-301">Term</span><span class="sxs-lookup"><span data-stu-id="ded87-301">Term</span></span>|<span data-ttu-id="ded87-302">Term</span><span class="sxs-lookup"><span data-stu-id="ded87-302">Term</span></span>|
|<span data-ttu-id="ded87-303">isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="ded87-303">isAvailableForTagging</span></span>|<span data-ttu-id="ded87-304">Är tillgängligt för märkning</span><span class="sxs-lookup"><span data-stu-id="ded87-304">Is available for tagging</span></span>|<span data-ttu-id="ded87-305">Term, Termuppsättning</span><span class="sxs-lookup"><span data-stu-id="ded87-305">Term, Term Set</span></span>|<span data-ttu-id="ded87-306">Boolesk</span><span class="sxs-lookup"><span data-stu-id="ded87-306">Boolean</span></span>|
|<span data-ttu-id="ded87-307">SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="ded87-307">SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="ded87-308">Har delad anpassad egenskap</span><span class="sxs-lookup"><span data-stu-id="ded87-308">Has shared custom property</span></span>|<span data-ttu-id="ded87-309">Term</span><span class="sxs-lookup"><span data-stu-id="ded87-309">Term</span></span>|<span data-ttu-id="ded87-310">Boolesk, sträng, heltal, decimal, dubbel</span><span class="sxs-lookup"><span data-stu-id="ded87-310">Boolean, string, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="ded87-311">LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="ded87-311">LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="ded87-312">Har lokal anpassad egenskap</span><span class="sxs-lookup"><span data-stu-id="ded87-312">Has local custom property</span></span>|<span data-ttu-id="ded87-313">Term</span><span class="sxs-lookup"><span data-stu-id="ded87-313">Term</span></span>|<span data-ttu-id="ded87-314">Boolesk, sträng, heltal, decimal, dubbel</span><span class="sxs-lookup"><span data-stu-id="ded87-314">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="ded87-315">CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="ded87-315">CustomPropertyForTermSet</span></span>|<span data-ttu-id="ded87-316">Har anpassad egenskap</span><span class="sxs-lookup"><span data-stu-id="ded87-316">Has Custom Property</span></span>|<span data-ttu-id="ded87-317">TermSet</span><span class="sxs-lookup"><span data-stu-id="ded87-317">TermSet</span></span>|<span data-ttu-id="ded87-318">Boolesk, sträng, heltal, decimal, dubbel</span><span class="sxs-lookup"><span data-stu-id="ded87-318">Boolean, String, Integer, Decimal, Double</span></span>|

<span data-ttu-id="ded87-319">[SKOS](https://www.w3.org/TR/skos-primer/) giltiga scenarier som [SharePoint-taxonomi](/dotnet/api/microsoft.sharepoint.taxonomy) inte tillåter:</span><span class="sxs-lookup"><span data-stu-id="ded87-319">[SKOS](https://www.w3.org/TR/skos-primer/) valid scenarios that [SharePoint taxonomy](/dotnet/api/microsoft.sharepoint.taxonomy) does not allow:</span></span>

- <span data-ttu-id="ded87-320">Hierarkisk redundans – ett [SKOS](https://www.w3.org/TR/skos-primer/)-konceptet kan kopplas till flera mer omfattande begrepp samtidigt men en sharepoint-taxonomi:Term kan bara ha en SharePoint-taxonomi:parent och därför är det inte heller tillåtet att använda cykliska beroenden för Termer.</span><span class="sxs-lookup"><span data-stu-id="ded87-320">Hierarchical redundancy - A [SKOS](https://www.w3.org/TR/skos-primer/) concept can be attached to several broader concepts at the same time, but a sharepoint-taxonomy:Term can have only one sharepoint-taxonomy:parent, hence cyclic dependency, of Terms is also not allowed.</span></span>
- <span data-ttu-id="ded87-321">Du kan inte använda ägarlösa termer i SharePoint-taxonomi.</span><span class="sxs-lookup"><span data-stu-id="ded87-321">Orphaned terms are not allowed in SharePoint taxonomy.</span></span> <span data-ttu-id="ded87-322">Alla sharepoint-taxonomier:Term ska antingen ha en sharepoint-taxonomi:parent eller så bör den vara sharepoint-taxonomi:topLevelTermOf ett TermSet.</span><span class="sxs-lookup"><span data-stu-id="ded87-322">Every sharepoint-taxonomy:Term should either have a sharepoint-taxonomy:parent or it should be the sharepoint-taxonomy:topLevelTermOf a TermSet.</span></span>
- <span data-ttu-id="ded87-323">SharePoint-taxonomi saknar stöd för associeringsrelationer.</span><span class="sxs-lookup"><span data-stu-id="ded87-323">SharePoint taxonomy does not support associative relations.</span></span>
- <span data-ttu-id="ded87-324">I SharePoint kan du bara använda 2 typer av hierarkiska relationer – sharepoint-taxonomi:parent and sharepoint-taxonomi:child.</span><span class="sxs-lookup"><span data-stu-id="ded87-324">SharePoint taxonomy only allows 2 types of Hierarchical relations – sharepoint-taxonomy:parent and sharepoint-Taxonomy:child.</span></span> 
- <span data-ttu-id="ded87-325">Till skillnad från [SKOS](https://www.w3.org/TR/skos-primer/) kan den hierarkiska relationen i SharePoint-taxonomivokabulär bara upprättas med Termer i samma TermSet.</span><span class="sxs-lookup"><span data-stu-id="ded87-325">Unlike [SKOS](https://www.w3.org/TR/skos-primer/) the hierarchical relationship in SharePoint taxonomy vocabulary, can only be established with Terms within the same TermSet.</span></span>

## <a name="see-also"></a><span data-ttu-id="ded87-326">Se även</span><span class="sxs-lookup"><span data-stu-id="ded87-326">See also</span></span>

[<span data-ttu-id="ded87-327">Importera en termuppsättning med ett SKOS-baserat format</span><span class="sxs-lookup"><span data-stu-id="ded87-327">Import a term set using a SKOS-based format</span></span>](import-term-set-skos.md)