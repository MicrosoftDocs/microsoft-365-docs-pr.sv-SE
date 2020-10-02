---
title: SKOS formatreferens för SharePoint-taxonomi
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: SKOS formatreferens för SharePoint-taxonomi
ms.openlocfilehash: f81b618a7c302ce033c4e8ce2f7400e9616f2de0
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321331"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a><span data-ttu-id="081f0-103">SKOS formatreferens för SharePoint-taxonomi</span><span class="sxs-lookup"><span data-stu-id="081f0-103">SKOS format reference for SharePoint taxonomy</span></span>

<span data-ttu-id="081f0-104">I den här artikeln finns ordlista för RDF som används för att representera [SharePoint-taxonomi](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) och som baseras på [SKOS](https://www.w3.org/TR/skos-primer/).</span><span class="sxs-lookup"><span data-stu-id="081f0-104">This article includes RDF vocabulary used to represent [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) and is based on [SKOS](https://www.w3.org/TR/skos-primer/).</span></span> <span data-ttu-id="081f0-105">Om du vill serialisera RDF använder du RDF [Sköldpadda](https://www.w3.org/TR/turtle/).</span><span class="sxs-lookup"><span data-stu-id="081f0-105">For serialization of this RDF syntax, use RDF [TURTLE](https://www.w3.org/TR/turtle/).</span></span>

<span data-ttu-id="081f0-106">I följande tabell visas de [SKOS](https://www.w3.org/TR/skos-primer/) motsvarigheter till vokabulär i [SharePoint-taxonomi](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy).</span><span class="sxs-lookup"><span data-stu-id="081f0-106">The following table shows the [SKOS](https://www.w3.org/TR/skos-primer/) equivalents for the [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary.</span></span> <span data-ttu-id="081f0-107">SharePoint har inte stöd för [SKOS](https://www.w3.org/TR/skos-primer/)-värden som inte har någon motsvarighet i SharePoint-taxonomi.</span><span class="sxs-lookup"><span data-stu-id="081f0-107">SharePoint does not support [SKOS](https://www.w3.org/TR/skos-primer/) values that have no SharePoint taxonomy equivalent.</span></span>

|<span data-ttu-id="081f0-108">SharePoint-taxonomi</span><span class="sxs-lookup"><span data-stu-id="081f0-108">SharePoint taxonomy</span></span>|<span data-ttu-id="081f0-109">Motsvarighet i SKOS</span><span class="sxs-lookup"><span data-stu-id="081f0-109">SKOS equivalent</span></span>|
|:-----------------|:--------------|
|<span data-ttu-id="081f0-110">sharepoint-taxonomi:Term</span><span class="sxs-lookup"><span data-stu-id="081f0-110">sharepoint-taxonomy:Term</span></span>|<span data-ttu-id="081f0-111">skos:Concept</span><span class="sxs-lookup"><span data-stu-id="081f0-111">skos:Concept</span></span>|
|<span data-ttu-id="081f0-112">sharepoint-taxonomi:TermSet</span><span class="sxs-lookup"><span data-stu-id="081f0-112">sharepoint-taxonomy:TermSet</span></span>|<span data-ttu-id="081f0-113">skos:ConceptScheme</span><span class="sxs-lookup"><span data-stu-id="081f0-113">skos:ConceptScheme</span></span>|
|<span data-ttu-id="081f0-114">sharepoint-taxonomi:inTermSet</span><span class="sxs-lookup"><span data-stu-id="081f0-114">sharepoint-taxonomy:inTermSet</span></span>|<span data-ttu-id="081f0-115">skos:inSchema</span><span class="sxs-lookup"><span data-stu-id="081f0-115">skos:inScheme</span></span>|
|<span data-ttu-id="081f0-116">sharepoint-taxonomi:hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="081f0-116">sharepoint-taxonomy:hasTopLevelTerm</span></span>|<span data-ttu-id="081f0-117">skos:hasTopConcept</span><span class="sxs-lookup"><span data-stu-id="081f0-117">skos:hasTopConcept</span></span>|
|<span data-ttu-id="081f0-118">sharepoint-taxonomi:topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="081f0-118">sharepoint-taxonomy:topLevelTermOf</span></span>|<span data-ttu-id="081f0-119">skos:topConceptOf</span><span class="sxs-lookup"><span data-stu-id="081f0-119">skos:topConceptOf</span></span>|
|<span data-ttu-id="081f0-120">SharePoint-taxonomi:defaultLabel</span><span class="sxs-lookup"><span data-stu-id="081f0-120">sharepoint-taxonomy:defaultLabel</span></span>|<span data-ttu-id="081f0-121">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="081f0-121">skos:prefLabel</span></span>|
|<span data-ttu-id="081f0-122">sharepoint-taxonomi:termSetName</span><span class="sxs-lookup"><span data-stu-id="081f0-122">sharepoint-taxonomy:termSetName</span></span>|<span data-ttu-id="081f0-123">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="081f0-123">skos:prefLabel</span></span>|
|<span data-ttu-id="081f0-124">sharepoint-taxonomi:propertyName</span><span class="sxs-lookup"><span data-stu-id="081f0-124">sharepoint-taxonomy:propertyName</span></span>|<span data-ttu-id="081f0-125">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="081f0-125">skos:prefLabel</span></span>|
|<span data-ttu-id="081f0-126">sharepoint-taxonomi:otherLabel</span><span class="sxs-lookup"><span data-stu-id="081f0-126">sharepoint-taxonomy:otherLabel</span></span>|<span data-ttu-id="081f0-127">skos:altLabel</span><span class="sxs-lookup"><span data-stu-id="081f0-127">skos:altLabel</span></span>|
|<span data-ttu-id="081f0-128">sharepoint-taxonomi:description</span><span class="sxs-lookup"><span data-stu-id="081f0-128">sharepoint-taxonomy:description</span></span>|<span data-ttu-id="081f0-129">skos:definition</span><span class="sxs-lookup"><span data-stu-id="081f0-129">skos:definition</span></span>|
|<span data-ttu-id="081f0-130">sharepoint-taxonomi:parent</span><span class="sxs-lookup"><span data-stu-id="081f0-130">sharepoint-taxonomy:parent</span></span>|<span data-ttu-id="081f0-131">skos:broader</span><span class="sxs-lookup"><span data-stu-id="081f0-131">skos:broader</span></span>|
|<span data-ttu-id="081f0-132">sharepoint-taxonomi:child</span><span class="sxs-lookup"><span data-stu-id="081f0-132">sharepoint-taxonomy:child</span></span>|<span data-ttu-id="081f0-133">skos:narrower</span><span class="sxs-lookup"><span data-stu-id="081f0-133">skos:narrower</span></span>|

<span data-ttu-id="081f0-134">I följande tabell visas de enheter i SharePoint-taxonomivokabulär som härleddes från [OWL](https://www.w3.org/TR/owl2-primer/).</span><span class="sxs-lookup"><span data-stu-id="081f0-134">The following table displays the entities of the SharePoint taxonomy vocabulary derived from [OWL](https://www.w3.org/TR/owl2-primer/).</span></span>

|<span data-ttu-id="081f0-135">SharePoint-taxonomivokabulär</span><span class="sxs-lookup"><span data-stu-id="081f0-135">SharePoint taxonomy vocabulary</span></span>|<span data-ttu-id="081f0-136">Härledd från OWL</span><span class="sxs-lookup"><span data-stu-id="081f0-136">Derived from OWL</span></span>|
|:-----------------------------|:----------------------|
|<span data-ttu-id="081f0-137">sharepoint-taxonomi:isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="081f0-137">sharepoint-taxonomy:isAvailableForTagging</span></span>|<span data-ttu-id="081f0-138">owl:datatypeproperty</span><span class="sxs-lookup"><span data-stu-id="081f0-138">owl:datatypeproperty</span></span>|
|<span data-ttu-id="081f0-139">sharepoint-taxonomi:SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="081f0-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="081f0-140">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="081f0-140">owl:ObjectProperty</span></span>|
|<span data-ttu-id="081f0-141">sharepoint-taxonomi:LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="081f0-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="081f0-142">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="081f0-142">owl:ObjectProperty</span></span>|
|<span data-ttu-id="081f0-143">sharepoint-taxonomi:CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="081f0-143">sharepoint-taxonomy:CustomPropertyForTermSet</span></span>|<span data-ttu-id="081f0-144">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="081f0-144">owl:ObjectProperty</span></span>|

## <a name="sharepoint-taxonomy-vocabulary"></a><span data-ttu-id="081f0-145">SharePoint-taxonomivokabulär</span><span class="sxs-lookup"><span data-stu-id="081f0-145">SharePoint taxonomy vocabulary</span></span>

<span data-ttu-id="081f0-146">En taxonomi är ett formellt klassificeringssystem.</span><span class="sxs-lookup"><span data-stu-id="081f0-146">A taxonomy is a formal classification system.</span></span> <span data-ttu-id="081f0-147">En taxonomi grupperar ord, etiketter och termer som beskriver något och sedan ordnar grupper i en hierarki.</span><span class="sxs-lookup"><span data-stu-id="081f0-147">A taxonomy groups the words, labels, and terms that describe something, and then arranges the groups into a hierarchy.</span></span>

<span data-ttu-id="081f0-148">**sharepoint-taxonomi:Term**</span><span class="sxs-lookup"><span data-stu-id="081f0-148">**sharepoint-taxonomy:Term**</span></span>

<span data-ttu-id="081f0-149">Representerar en term eller ett nyckelord i en hierarki med hanterade metadata.</span><span class="sxs-lookup"><span data-stu-id="081f0-149">Represents a Term or a Keyword in a managed metadata hierarchy.</span></span>

<span data-ttu-id="081f0-150">En [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) är den atomiska enheten i en SharePoint [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span><span class="sxs-lookup"><span data-stu-id="081f0-150">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is the atomic unit of a SharePoint [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span></span> <span data-ttu-id="081f0-151">Varje [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) tillhör en [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) som tillhör ett [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span><span class="sxs-lookup"><span data-stu-id="081f0-151">Each [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belongs to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) that belongs to a [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> 

<span data-ttu-id="081f0-152">Syntaxen för att definiera en [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) är följande:</span><span class="sxs-lookup"><span data-stu-id="081f0-152">The syntax to define a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is as follows:</span></span>

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="081f0-153">En [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) existerar obligatoriskt i ett [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="081f0-153">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) compulsorily exists within a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="081f0-154">DefaultLabel är namnet på [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)en som det visas i den visuella presentationen.</span><span class="sxs-lookup"><span data-stu-id="081f0-154">DefaultLabel is the name of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) as it appears in the visual representation.</span></span> <span data-ttu-id="081f0-155">De obligatoriska fälten för att definiera en [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) inkluderar:</span><span class="sxs-lookup"><span data-stu-id="081f0-155">The required fields for defining a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) include:</span></span>

- <span data-ttu-id="081f0-156">SharePoint-taxonomi:defaultLabel</span><span class="sxs-lookup"><span data-stu-id="081f0-156">sharepoint-taxonomy:defaultLabel</span></span>
- <span data-ttu-id="081f0-157">sharepoint-taxonomi:inTermSet</span><span class="sxs-lookup"><span data-stu-id="081f0-157">sharepoint-taxonomy:inTermSet</span></span>

<span data-ttu-id="081f0-158">En [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) kan:</span><span class="sxs-lookup"><span data-stu-id="081f0-158">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can:</span></span>

- <span data-ttu-id="081f0-159">Vara hierarkiskt relaterad till en annan [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) om båda [Termerna](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) tillhör samma [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="081f0-159">Be hierarchically related to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is provided both the [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belong to the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="081f0-160">Ha flera underordnade [Termer](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) men bara en överordnad [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="081f0-160">Have multiple child [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), but only a single parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>
- <span data-ttu-id="081f0-161">Inte har någon överordnad [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) definierad om det är en topLevelTermOf ett [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="081f0-161">Not have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) defined, if it is a topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="081f0-162">Ha en defaultLabel, per [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) arbetsspråk.</span><span class="sxs-lookup"><span data-stu-id="081f0-162">Have one defaultLabel, per [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>
- <span data-ttu-id="081f0-163">Inte finnas om den varken innehåller en överordnad [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) eller är topLevelTermOf ett [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="081f0-163">Not exist if it neither contains a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), nor is the topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> 
- <span data-ttu-id="081f0-164">Har bara ett unikt defaultLabel på samma hierarkiska nivå.</span><span class="sxs-lookup"><span data-stu-id="081f0-164">Have only a unique defaultLabel in the same hierarchical level.</span></span>

<span data-ttu-id="081f0-165">**sharepoint-taxonomi:TermSet**</span><span class="sxs-lookup"><span data-stu-id="081f0-165">**sharepoint-taxonomy:TermSet**</span></span>

<span data-ttu-id="081f0-166">Representerar en hierarkisk eller platt uppsättning termobjekt som kallas "TermSet".</span><span class="sxs-lookup"><span data-stu-id="081f0-166">Represents a hierarchical or flat set of Term objects known as a "TermSet".</span></span>

<span data-ttu-id="081f0-167">Som namnet antyder är TermSet en uppsättning [Termer](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="081f0-167">As the name suggests, TermSet is a set of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="081f0-168">En [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) i en [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) måste tillhöra ett [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="081f0-168">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) must belong to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="081f0-169">Ingen [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) kan finnas oberoende.</span><span class="sxs-lookup"><span data-stu-id="081f0-169">No [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can exist independently.</span></span> 

<span data-ttu-id="081f0-170">Syntaxen för att definiera en [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) är:</span><span class="sxs-lookup"><span data-stu-id="081f0-170">The syntax to define a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

<span data-ttu-id="081f0-171">[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) är logiskt grupperade i [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span><span class="sxs-lookup"><span data-stu-id="081f0-171">[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) are logically grouped together in [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> <span data-ttu-id="081f0-172">Det obligatoriska fältet för att definiera en [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) är:</span><span class="sxs-lookup"><span data-stu-id="081f0-172">The required field for defining a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

- <span data-ttu-id="081f0-173">sharepoint-taxonomi:termSetName</span><span class="sxs-lookup"><span data-stu-id="081f0-173">sharepoint-taxonomy:termSetName</span></span>

<span data-ttu-id="081f0-174">Om den termSetName som anges inte är unik i [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group) lägger SharePoint till en siffra i slutet av namnet för att upprätthålla unikheten i termSetName(s).</span><span class="sxs-lookup"><span data-stu-id="081f0-174">In the case of the termSetName provided is not unique within the [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), SharePoint appends a number at the end of the name to maintain the uniqueness of termSetName(s).</span></span>

<span data-ttu-id="081f0-175">**sharepoint-taxonomi:hasTopLevelTerm**</span><span class="sxs-lookup"><span data-stu-id="081f0-175">**sharepoint-taxonomy:hasTopLevelTerm**</span></span>

<span data-ttu-id="081f0-176">I SharePoint används den här egenskapen för att avbilda den översta [Termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) i [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) som är startpunkten i hierarkin för [Termer](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) i ett [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="081f0-176">SharePoint uses this property to map the top most [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), which is the entry point to the hierarchy of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="081f0-177">Det här är en inverterad relation till sharepoint-taxonomi:topLevelTermOf.</span><span class="sxs-lookup"><span data-stu-id="081f0-177">This is an inverse relation to sharepoint-taxonomy:topLevelTermOf.</span></span> 

<span data-ttu-id="081f0-178">Syntaxen för att definiera detta är:</span><span class="sxs-lookup"><span data-stu-id="081f0-178">The syntax to define this is:</span></span>

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> <span data-ttu-id="081f0-179">Det går inte att definiera [Term på översta nivån](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) för en överordnad [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="081f0-179">You cannot define the top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="081f0-180">**sharepoint-taxonomi:topLevelTermOf**</span><span class="sxs-lookup"><span data-stu-id="081f0-180">**sharepoint-taxonomy:topLevelTermOf**</span></span>

<span data-ttu-id="081f0-181">SharePoint-taxonomi:topLevelTermOf är inversen till sharepoint-taxonomi:hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="081f0-181">Sharepoint-taxonomy:topLevelTermOf is the inverse of sharepoint-taxonomy:hasTopLevelTerm</span></span>

<span data-ttu-id="081f0-182">Syntaxen för att definiera detta är:</span><span class="sxs-lookup"><span data-stu-id="081f0-182">The syntax to define this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

<span data-ttu-id="081f0-183">**sharepoint-taxonomi:inTermSet**</span><span class="sxs-lookup"><span data-stu-id="081f0-183">**sharepoint-taxonomy:inTermSet**</span></span>

<span data-ttu-id="081f0-184">Använd det här alternativet om du vill mappen en [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) till ett [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="081f0-184">Use this to map a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="081f0-185">En [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) kan bara finnas i en enda [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="081f0-185">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can only exist in a single [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="081f0-186">SharePoint kräver den här egenskapen vi [definiering av en term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span><span class="sxs-lookup"><span data-stu-id="081f0-186">SharePoint requires this property when [defining a term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span></span>

## <a name="required-labels"></a><span data-ttu-id="081f0-187">Obligatoriska etiketter</span><span class="sxs-lookup"><span data-stu-id="081f0-187">Required labels</span></span>

<span data-ttu-id="081f0-188">Din organisation kanske vill göra noggrann planering innan du börjar använda hanterade metadata.</span><span class="sxs-lookup"><span data-stu-id="081f0-188">Your organization may want to do careful planning before you start to use managed metadata.</span></span> <span data-ttu-id="081f0-189">Hur mycket planering du måste utföra beror på hur formell din taxonomi är.</span><span class="sxs-lookup"><span data-stu-id="081f0-189">The amount of planning that you must do depends on how formal your taxonomy is.</span></span> <span data-ttu-id="081f0-190">Det beror även på hur mycket kontroll som du vill använda för metadata.</span><span class="sxs-lookup"><span data-stu-id="081f0-190">It also depends on how much control that you want to impose on metadata.</span></span> <span data-ttu-id="081f0-191">På varje nivå i hierarkin måste du konfigurera obligatoriska etiketter för en Term eller ett TermSet.</span><span class="sxs-lookup"><span data-stu-id="081f0-191">At each level of the hierarchy, you need to configure required labels for a Term or TermSet.</span></span>

<span data-ttu-id="081f0-192">En Term kan ha en eller flera etiketter i standardspråket och noll eller fler etiketter på ett annat språk än standardspråket.</span><span class="sxs-lookup"><span data-stu-id="081f0-192">A Term can have one or more labels in the default language, and zero or more labels in the non-default language.</span></span> <span data-ttu-id="081f0-193">Om termen har etiketter på ett språk måste en av etiketterna vara standardetiketten.</span><span class="sxs-lookup"><span data-stu-id="081f0-193">If the term has labels in a language, one of the labels must be the default label.</span></span>

<span data-ttu-id="081f0-194">**sharepoint-taxonomi:defaultLabel**</span><span class="sxs-lookup"><span data-stu-id="081f0-194">**sharepoint-taxonomy:defaultLabel**</span></span>

<span data-ttu-id="081f0-195">Använd den här lexikala standardetiketten för en [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) som är en obligatorisk parameter för en [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="081f0-195">Use this default lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is a required parameter for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="081f0-196">Används för att visuellt representera [Termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="081f0-196">Use to visually representing the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="081f0-197">Syntaxen för att definiera en defaultLabel är:</span><span class="sxs-lookup"><span data-stu-id="081f0-197">The syntax to define a defaultLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="081f0-198">DefaultLabel innehåller två delar – strängen och språktaggen.</span><span class="sxs-lookup"><span data-stu-id="081f0-198">The defaultLabel contains two parts to it – the string and the language tag.</span></span> <span data-ttu-id="081f0-199">Språket måste vara något av [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) arbetsspråk.</span><span class="sxs-lookup"><span data-stu-id="081f0-199">The language must be one of the [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working languages.</span></span> <span data-ttu-id="081f0-200">DefaultLabel måste vara unika för alla [Termer](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) i samma [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), på samma hierarkiska nivå.</span><span class="sxs-lookup"><span data-stu-id="081f0-200">The defaultLabel must be unique for all [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), at the same hierarchical level.</span></span>

<span data-ttu-id="081f0-201">**sharepoint-taxonomi:termSetName**</span><span class="sxs-lookup"><span data-stu-id="081f0-201">**sharepoint-taxonomy:termSetName**</span></span>

<span data-ttu-id="081f0-202">Hämtar och anger namnet på det aktuella TermSet-objektet.</span><span class="sxs-lookup"><span data-stu-id="081f0-202">Gets and sets the name for the current TermSet object.</span></span>

<span data-ttu-id="081f0-203">Det här är en lexikalisk etikett för en [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)i en [termStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) arbetsspråk.</span><span class="sxs-lookup"><span data-stu-id="081f0-203">This the lexical label for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span> <span data-ttu-id="081f0-204">Det här är en obligatorisk parameter för ett [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="081f0-204">This is a required parameter for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="081f0-205">Används för att visuellt representera en [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="081f0-205">Use to visually representing a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>

<span data-ttu-id="081f0-206">Syntaxen för att definiera en termSetName är:</span><span class="sxs-lookup"><span data-stu-id="081f0-206">The syntax to define a termSetName is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

<span data-ttu-id="081f0-207">**sharepoint-taxonomi:propertyName**</span><span class="sxs-lookup"><span data-stu-id="081f0-207">**sharepoint-taxonomy:propertyName**</span></span>

<span data-ttu-id="081f0-208">Hämtar och anger namnet på den aktuella TermSet-objektet.</span><span class="sxs-lookup"><span data-stu-id="081f0-208">Gets and sets the property name for the current TermSet object.</span></span>

<span data-ttu-id="081f0-209">Det här är en lexikalisk etikett för en sharepoint-taxonomi:SharedCustomPropertyForTerm, sharepoint-taxonomi:LocalCustomPropertyForTerm och sharepoint-taxonomi:CustomPropertyForTermSet i en [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) arbetsspråk.</span><span class="sxs-lookup"><span data-stu-id="081f0-209">This is the lexical label for a sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm and sharepoint-taxonomy:CustomPropertyForTermSet in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>

<span data-ttu-id="081f0-210">SharePoint-taxonomi:propertyName behandlas som nyckel för CustomProperty.</span><span class="sxs-lookup"><span data-stu-id="081f0-210">The sharepoint-taxonomy:propertyName is treated as the key of the CustomProperty.</span></span>

<span data-ttu-id="081f0-211">Syntaxen för att definiera en propetyName är:</span><span class="sxs-lookup"><span data-stu-id="081f0-211">The syntax to define a propetyName is:</span></span>

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a><span data-ttu-id="081f0-212">Valfria etiketter</span><span class="sxs-lookup"><span data-stu-id="081f0-212">Optional labels</span></span>

<span data-ttu-id="081f0-213">Du kan även lägga till valfria etiketter i din taxonomi.</span><span class="sxs-lookup"><span data-stu-id="081f0-213">You can also add optional labels to your taxonomy.</span></span>

<span data-ttu-id="081f0-214">**sharepoint-taxonomi:otherLabel**</span><span class="sxs-lookup"><span data-stu-id="081f0-214">**sharepoint-taxonomy:otherLabel**</span></span>

<span data-ttu-id="081f0-215">Det här är den alternativa lexikala etiketten för en [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="081f0-215">This is the alternate lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="081f0-216">Syntaxen för att definiera en otherLabel är:</span><span class="sxs-lookup"><span data-stu-id="081f0-216">The syntax to define an otherLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a><span data-ttu-id="081f0-217">Semantiska relationer</span><span class="sxs-lookup"><span data-stu-id="081f0-217">Semantic relationships</span></span>

<span data-ttu-id="081f0-218">Taxonomier har hierarkiska och ibland en enkel "relaterad term" som associerande relation men vissa har "semantiska relationer" eller egendefinierade relationer.</span><span class="sxs-lookup"><span data-stu-id="081f0-218">Taxonomies have hierarchical and sometimes a simple “related term” associative relationship, but some have "semantic relationships" or custom-created relationships.</span></span> 

<span data-ttu-id="081f0-219">**sharepoint-taxonomi:parent**</span><span class="sxs-lookup"><span data-stu-id="081f0-219">**sharepoint-taxonomy:parent**</span></span>

<span data-ttu-id="081f0-220">Den här hierarkiska relationen relaterar en [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) till en annan [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="081f0-220">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="081f0-221">En [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) kan vara en toppnivå [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) av ett [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), men om det inte måste det finnas en överordnad [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="081f0-221">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) could be a top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), but in case it doesn’t it must have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="081f0-222">Syntaxen för att definiera en parent är:</span><span class="sxs-lookup"><span data-stu-id="081f0-222">The syntax to define a parent is:</span></span>

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

<span data-ttu-id="081f0-223">Det innebär att TermA är det överordnade objektet och TermA är det underordnade.</span><span class="sxs-lookup"><span data-stu-id="081f0-223">This means that TermA is the parent and  TermA is the child.</span></span>

<span data-ttu-id="081f0-224">**sharepoint-taxonomi:child**</span><span class="sxs-lookup"><span data-stu-id="081f0-224">**sharepoint-taxonomy:child**</span></span>

<span data-ttu-id="081f0-225">Objektet innehåller ett eller flera underordnade TermSet-instanser och du kan komma åt dessa via TermSets egenskaper.</span><span class="sxs-lookup"><span data-stu-id="081f0-225">The object contains one or more child TermSet instances, and these can be accessed through the TermSets property.</span></span> <span data-ttu-id="081f0-226">I den här klassen finns också metoder för att skapa nya underordnade TermSet-objekt.</span><span class="sxs-lookup"><span data-stu-id="081f0-226">This class also provides methods for creating new child TermSet objects.</span></span> <span data-ttu-id="081f0-227">Behörigheter för att redigera underordnad Term och TermSet-instanser anges i gruppen.</span><span class="sxs-lookup"><span data-stu-id="081f0-227">Permissions for editing child Term and TermSet instances is specified on the group.</span></span> 

<span data-ttu-id="081f0-228">Den här hierarkiska relationen relaterar en [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) till en annan [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="081f0-228">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="081f0-229">Syntaxen för att definiera ett child är:</span><span class="sxs-lookup"><span data-stu-id="081f0-229">The syntax to define a child is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

<span data-ttu-id="081f0-230">Det innebär att TermA är det överordnade objektet och TermA är det underordnade.</span><span class="sxs-lookup"><span data-stu-id="081f0-230">This means that TermA is the parent and  TermA is the child.</span></span>

## <a name="documentation-notes"></a><span data-ttu-id="081f0-231">Dokumentationskommentarer</span><span class="sxs-lookup"><span data-stu-id="081f0-231">Documentation notes</span></span>

<span data-ttu-id="081f0-232">I det här avsnittet beskrivs taxonomin detaljerad i Microsoft. SharePoint. taxonomins namnrymd.</span><span class="sxs-lookup"><span data-stu-id="081f0-232">This section discusses the taxonomy detailed in the Microsoft.SharePoint.Taxonomy Namespace.</span></span>

<span data-ttu-id="081f0-233">**sharepoint-taxonomi:description**</span><span class="sxs-lookup"><span data-stu-id="081f0-233">**sharepoint-taxonomy:description**</span></span>

<span data-ttu-id="081f0-234">Det här är en detaljerad beskrivning av alla vokabulära enheter i [SharePoint-taxonomi](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy).</span><span class="sxs-lookup"><span data-stu-id="081f0-234">This is a detailed explanation of any [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary entity.</span></span> 

<span data-ttu-id="081f0-235">Syntaxen för att lägga till en beskrivning är:</span><span class="sxs-lookup"><span data-stu-id="081f0-235">The syntax to add a description is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a><span data-ttu-id="081f0-236">Anpassade egenskaper</span><span class="sxs-lookup"><span data-stu-id="081f0-236">Custom properties</span></span>

<span data-ttu-id="081f0-237">Hämtar en samling egna egenskapsobjekt för det aktuella Termobjektet från den skrivskyddade ordlistan.</span><span class="sxs-lookup"><span data-stu-id="081f0-237">Gets the collection of custom property objects for the current Term object from the read-only dictionary.</span></span>

<span data-ttu-id="081f0-238">Anpassade egenskaper är nyckelvärdespar som kan definieras för en [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) eller [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) för att få en beskrivning av [Termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) eller [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="081f0-238">Custom Properties are key-values pairs that can be defined for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), to further the description of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="081f0-239">I SharePoint anges nyckel för den anpassade egenskapen med hjälp av propertyName.</span><span class="sxs-lookup"><span data-stu-id="081f0-239">SharePoint specifies the key of the custom property with the help of propertyName.</span></span>

<span data-ttu-id="081f0-240">**sharepoint-taxonomi:CustomPropertyForTermSet**</span><span class="sxs-lookup"><span data-stu-id="081f0-240">**sharepoint-taxonomy:CustomPropertyForTermSet**</span></span>

<span data-ttu-id="081f0-241">Syntaxen för att definiera detta är:</span><span class="sxs-lookup"><span data-stu-id="081f0-241">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

<span data-ttu-id="081f0-242">**sharepoint-taxonomi:SharedCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="081f0-242">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span></span>

<span data-ttu-id="081f0-243">Om den anpassade egenskapen för en [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) måste följa med [Termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) när du återanvänder [Termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) någon annanstans måste du definiera den under SharedCustomPropertyForTerm.</span><span class="sxs-lookup"><span data-stu-id="081f0-243">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) needs to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to be define it under SharedCustomPropertyForTerm.</span></span>

<span data-ttu-id="081f0-244">Syntaxen för att definiera detta är:</span><span class="sxs-lookup"><span data-stu-id="081f0-244">The syntax to define this is:</span></span>

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
<span data-ttu-id="081f0-245">**sharepoint-taxonomi:LocalCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="081f0-245">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span></span>

<span data-ttu-id="081f0-246">Om den anpassade egenskapen för en [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) inte behöver följa med [Termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) när du återanvänder [Termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) någon annanstans, måste du definiera den under LocalCustomPropertyForTerm.</span><span class="sxs-lookup"><span data-stu-id="081f0-246">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) does not need to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to define it under LocalCustomPropertyForTerm.</span></span>

<span data-ttu-id="081f0-247">Syntaxen för att definiera detta är:</span><span class="sxs-lookup"><span data-stu-id="081f0-247">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a><span data-ttu-id="081f0-248">Dataegenskaper</span><span class="sxs-lookup"><span data-stu-id="081f0-248">Data properties</span></span>

<span data-ttu-id="081f0-249">På varje nivå i hierarkin kan du konfigurera vissa dataegenskaper för en Term eller TermSet.</span><span class="sxs-lookup"><span data-stu-id="081f0-249">At each level of the hierarchy, you can configure specific data properties for a Term or TermSet.</span></span>

<span data-ttu-id="081f0-250">**sharepoint-taxonomi:isAvailableForTagging**</span><span class="sxs-lookup"><span data-stu-id="081f0-250">**sharepoint-taxonomy:isAvailableForTagging**</span></span>

<span data-ttu-id="081f0-251">Använd det här alternativet om du vill ange om en [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) eller [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) tillgänglig i SharePoint-listor och -bibliotek.</span><span class="sxs-lookup"><span data-stu-id="081f0-251">Use this to specify if a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) available in SharePoint Lists and Libraries.</span></span>  

<span data-ttu-id="081f0-252">Syntaxen för det här är:</span><span class="sxs-lookup"><span data-stu-id="081f0-252">The syntax for this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a><span data-ttu-id="081f0-253">Domän och område</span><span class="sxs-lookup"><span data-stu-id="081f0-253">Domain and range</span></span>

<span data-ttu-id="081f0-254">I tabellen nedan beskrivs domänen och intervallet för SharePoint-taxonomivokabulär.</span><span class="sxs-lookup"><span data-stu-id="081f0-254">The table below describes the domain and range of SharePoint taxonomy vocabulary.</span></span>

|<span data-ttu-id="081f0-255">Predikat/verb</span><span class="sxs-lookup"><span data-stu-id="081f0-255">Predicates/verb</span></span>|<span data-ttu-id="081f0-256">Betydelse</span><span class="sxs-lookup"><span data-stu-id="081f0-256">Meaning</span></span>|<span data-ttu-id="081f0-257">Domän</span><span class="sxs-lookup"><span data-stu-id="081f0-257">Domain</span></span>|<span data-ttu-id="081f0-258">Område</span><span class="sxs-lookup"><span data-stu-id="081f0-258">Range</span></span>|
|:--------------|:------|:-----|:----|
<span data-ttu-id="081f0-259">inTermSet</span><span class="sxs-lookup"><span data-stu-id="081f0-259">inTermSet</span></span>|<span data-ttu-id="081f0-260">I termuppsättning</span><span class="sxs-lookup"><span data-stu-id="081f0-260">In term set</span></span>|<span data-ttu-id="081f0-261">Term</span><span class="sxs-lookup"><span data-stu-id="081f0-261">Term</span></span>|<span data-ttu-id="081f0-262">Termuppsättning</span><span class="sxs-lookup"><span data-stu-id="081f0-262">Term Set</span></span>|
<span data-ttu-id="081f0-263">inTermGroup</span><span class="sxs-lookup"><span data-stu-id="081f0-263">inTermGroup</span></span>|<span data-ttu-id="081f0-264">I termgruppen</span><span class="sxs-lookup"><span data-stu-id="081f0-264">In term group</span></span>|<span data-ttu-id="081f0-265">TermSet</span><span class="sxs-lookup"><span data-stu-id="081f0-265">TermSet</span></span>|<span data-ttu-id="081f0-266">TermGroup</span><span class="sxs-lookup"><span data-stu-id="081f0-266">TermGroup</span></span>|
<span data-ttu-id="081f0-267">topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="081f0-267">topLevelTermOf</span></span>|<span data-ttu-id="081f0-268">Är toppnivåterm för</span><span class="sxs-lookup"><span data-stu-id="081f0-268">Is Top Level Term Of</span></span>|<span data-ttu-id="081f0-269">Term</span><span class="sxs-lookup"><span data-stu-id="081f0-269">Term</span></span>|<span data-ttu-id="081f0-270">TermSet</span><span class="sxs-lookup"><span data-stu-id="081f0-270">TermSet</span></span>|
<span data-ttu-id="081f0-271">hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="081f0-271">hasTopLevelTerm</span></span>|<span data-ttu-id="081f0-272">Har en topnivåterm</span><span class="sxs-lookup"><span data-stu-id="081f0-272">Has top level term</span></span>|<span data-ttu-id="081f0-273">Termuppsättning</span><span class="sxs-lookup"><span data-stu-id="081f0-273">Term Set</span></span>|<span data-ttu-id="081f0-274">Term</span><span class="sxs-lookup"><span data-stu-id="081f0-274">Term</span></span>|
<span data-ttu-id="081f0-275">termSetName</span><span class="sxs-lookup"><span data-stu-id="081f0-275">termSetName</span></span>|<span data-ttu-id="081f0-276">Termuppsättning har namn</span><span class="sxs-lookup"><span data-stu-id="081f0-276">Term set has Name</span></span>|<span data-ttu-id="081f0-277">Term</span><span class="sxs-lookup"><span data-stu-id="081f0-277">Term</span></span>|<span data-ttu-id="081f0-278">Enkel literal</span><span class="sxs-lookup"><span data-stu-id="081f0-278">Plain literal</span></span>|
<span data-ttu-id="081f0-279">defaultLabel</span><span class="sxs-lookup"><span data-stu-id="081f0-279">defaultLabel</span></span>|<span data-ttu-id="081f0-280">Term har standardetikett</span><span class="sxs-lookup"><span data-stu-id="081f0-280">Term has default label</span></span>|<span data-ttu-id="081f0-281">Term</span><span class="sxs-lookup"><span data-stu-id="081f0-281">Term</span></span>|<span data-ttu-id="081f0-282">Enkel literal</span><span class="sxs-lookup"><span data-stu-id="081f0-282">Plain literal</span></span>|
<span data-ttu-id="081f0-283">otherLabel</span><span class="sxs-lookup"><span data-stu-id="081f0-283">otherLabel</span></span>|<span data-ttu-id="081f0-284">Term har annan etikett</span><span class="sxs-lookup"><span data-stu-id="081f0-284">Term has other label</span></span>|<span data-ttu-id="081f0-285">Term</span><span class="sxs-lookup"><span data-stu-id="081f0-285">Term</span></span>|<span data-ttu-id="081f0-286">Enkel literal</span><span class="sxs-lookup"><span data-stu-id="081f0-286">Plain literal</span></span>|
<span data-ttu-id="081f0-287">PropertyName</span><span class="sxs-lookup"><span data-stu-id="081f0-287">propertyName</span></span>|<span data-ttu-id="081f0-288">Har egenskapsetikett</span><span class="sxs-lookup"><span data-stu-id="081f0-288">Has Property Label</span></span>|<span data-ttu-id="081f0-289">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="081f0-289">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span></span> |<span data-ttu-id="081f0-290">Boolesk, sträng, heltal, decimal, dubbel</span><span class="sxs-lookup"><span data-stu-id="081f0-290">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="081f0-291">description</span><span class="sxs-lookup"><span data-stu-id="081f0-291">description</span></span>|<span data-ttu-id="081f0-292">Har beskrivning</span><span class="sxs-lookup"><span data-stu-id="081f0-292">Has Description</span></span>|<span data-ttu-id="081f0-293">Alla</span><span class="sxs-lookup"><span data-stu-id="081f0-293">All</span></span>|<span data-ttu-id="081f0-294">Enkel literal</span><span class="sxs-lookup"><span data-stu-id="081f0-294">Plain literal</span></span>|
|<span data-ttu-id="081f0-295">parent</span><span class="sxs-lookup"><span data-stu-id="081f0-295">parent</span></span>|<span data-ttu-id="081f0-296">Har överordnad</span><span class="sxs-lookup"><span data-stu-id="081f0-296">Has parent</span></span>|<span data-ttu-id="081f0-297">Term</span><span class="sxs-lookup"><span data-stu-id="081f0-297">Term</span></span>|<span data-ttu-id="081f0-298">Term</span><span class="sxs-lookup"><span data-stu-id="081f0-298">Term</span></span>|
|<span data-ttu-id="081f0-299">child</span><span class="sxs-lookup"><span data-stu-id="081f0-299">child</span></span>|<span data-ttu-id="081f0-300">Har underordnad</span><span class="sxs-lookup"><span data-stu-id="081f0-300">Has Child</span></span>|<span data-ttu-id="081f0-301">Term</span><span class="sxs-lookup"><span data-stu-id="081f0-301">Term</span></span>|<span data-ttu-id="081f0-302">Term</span><span class="sxs-lookup"><span data-stu-id="081f0-302">Term</span></span>|
|<span data-ttu-id="081f0-303">isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="081f0-303">isAvailableForTagging</span></span>|<span data-ttu-id="081f0-304">Är tillgängligt för märkning</span><span class="sxs-lookup"><span data-stu-id="081f0-304">Is available for tagging</span></span>|<span data-ttu-id="081f0-305">Term, Termuppsättning</span><span class="sxs-lookup"><span data-stu-id="081f0-305">Term, Term Set</span></span>|<span data-ttu-id="081f0-306">Boolesk</span><span class="sxs-lookup"><span data-stu-id="081f0-306">Boolean</span></span>|
|<span data-ttu-id="081f0-307">SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="081f0-307">SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="081f0-308">Har delad anpassad egenskap</span><span class="sxs-lookup"><span data-stu-id="081f0-308">Has shared custom property</span></span>|<span data-ttu-id="081f0-309">Term</span><span class="sxs-lookup"><span data-stu-id="081f0-309">Term</span></span>|<span data-ttu-id="081f0-310">Boolesk, sträng, heltal, decimal, dubbel</span><span class="sxs-lookup"><span data-stu-id="081f0-310">Boolean, string, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="081f0-311">LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="081f0-311">LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="081f0-312">Har lokal anpassad egenskap</span><span class="sxs-lookup"><span data-stu-id="081f0-312">Has local custom property</span></span>|<span data-ttu-id="081f0-313">Term</span><span class="sxs-lookup"><span data-stu-id="081f0-313">Term</span></span>|<span data-ttu-id="081f0-314">Boolesk, sträng, heltal, decimal, dubbel</span><span class="sxs-lookup"><span data-stu-id="081f0-314">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="081f0-315">CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="081f0-315">CustomPropertyForTermSet</span></span>|<span data-ttu-id="081f0-316">Har anpassad egenskap</span><span class="sxs-lookup"><span data-stu-id="081f0-316">Has Custom Property</span></span>|<span data-ttu-id="081f0-317">TermSet</span><span class="sxs-lookup"><span data-stu-id="081f0-317">TermSet</span></span>|<span data-ttu-id="081f0-318">Boolesk, sträng, heltal, decimal, dubbel</span><span class="sxs-lookup"><span data-stu-id="081f0-318">Boolean, String, Integer, Decimal, Double</span></span>|

<span data-ttu-id="081f0-319">[SKOS](https://www.w3.org/TR/skos-primer/) giltiga scenarier som [SharePoint-taxonomi](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) inte tillåter:</span><span class="sxs-lookup"><span data-stu-id="081f0-319">[SKOS](https://www.w3.org/TR/skos-primer/) valid scenarios that [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) does not allow:</span></span>

- <span data-ttu-id="081f0-320">Hierarkisk redundans – ett [SKOS](https://www.w3.org/TR/skos-primer/)-konceptet kan kopplas till flera mer omfattande begrepp samtidigt men en sharepoint-taxonomi:Term kan bara ha en SharePoint-taxonomi:parent och därför är det inte heller tillåtet att använda cykliska beroenden för Termer.</span><span class="sxs-lookup"><span data-stu-id="081f0-320">Hierarchical redundancy - A [SKOS](https://www.w3.org/TR/skos-primer/) concept can be attached to several broader concepts at the same time, but a sharepoint-taxonomy:Term can have only one sharepoint-taxonomy:parent, hence cyclic dependency, of Terms is also not allowed.</span></span>
- <span data-ttu-id="081f0-321">Du kan inte använda ägarlösa termer i SharePoint-taxonomi.</span><span class="sxs-lookup"><span data-stu-id="081f0-321">Orphaned terms are not allowed in SharePoint taxonomy.</span></span> <span data-ttu-id="081f0-322">Alla sharepoint-taxonomier:Term ska antingen ha en sharepoint-taxonomi:parent eller så bör den vara sharepoint-taxonomi:topLevelTermOf ett TermSet.</span><span class="sxs-lookup"><span data-stu-id="081f0-322">Every sharepoint-taxonomy:Term should either have a sharepoint-taxonomy:parent or it should be the sharepoint-taxonomy:topLevelTermOf a TermSet.</span></span>
- <span data-ttu-id="081f0-323">SharePoint-taxonomi saknar stöd för associeringsrelationer.</span><span class="sxs-lookup"><span data-stu-id="081f0-323">SharePoint taxonomy does not support associative relations.</span></span>
- <span data-ttu-id="081f0-324">I SharePoint kan du bara använda 2 typer av hierarkiska relationer – sharepoint-taxonomi:parent and sharepoint-taxonomi:child.</span><span class="sxs-lookup"><span data-stu-id="081f0-324">SharePoint taxonomy only allows 2 types of Hierarchical relations – sharepoint-taxonomy:parent and sharepoint-Taxonomy:child.</span></span> 
- <span data-ttu-id="081f0-325">Till skillnad från [SKOS](https://www.w3.org/TR/skos-primer/) kan den hierarkiska relationen i SharePoint-taxonomivokabulär bara upprättas med Termer i samma TermSet.</span><span class="sxs-lookup"><span data-stu-id="081f0-325">Unlike [SKOS](https://www.w3.org/TR/skos-primer/) the hierarchical relationship in SharePoint taxonomy vocabulary, can only be established with Terms within the same TermSet.</span></span>

## <a name="see-also"></a><span data-ttu-id="081f0-326">Se även</span><span class="sxs-lookup"><span data-stu-id="081f0-326">See also</span></span>

[<span data-ttu-id="081f0-327">Importera en termuppsättning med ett SKOS-baserat format</span><span class="sxs-lookup"><span data-stu-id="081f0-327">Import a term set using a SKOS-based format</span></span>](import-term-set-skos.md)

