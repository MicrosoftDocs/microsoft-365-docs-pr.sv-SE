---
title: SKOS format referens för SharePoint-taxonomi
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
description: SKOS format referens för SharePoint-taxonomi
ms.openlocfilehash: eb228394b06b6e6027937ab105df7c0079875226
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296235"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a><span data-ttu-id="378c5-103">SKOS format referens för SharePoint-taxonomi</span><span class="sxs-lookup"><span data-stu-id="378c5-103">SKOS format reference for SharePoint taxonomy</span></span>

<span data-ttu-id="378c5-104">Den här artikeln innehåller RDF vokabulär som används för att representera [SharePoint-taxonomi](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) och är baserad på [SKOS](https://www.w3.org/TR/skos-primer/).</span><span class="sxs-lookup"><span data-stu-id="378c5-104">This article includes RDF vocabulary used to represent [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) and is based on [SKOS](https://www.w3.org/TR/skos-primer/).</span></span> <span data-ttu-id="378c5-105">För serialisering av denna RDF-syntax, Använd RDF [sköldning](https://www.w3.org/TR/turtle/).</span><span class="sxs-lookup"><span data-stu-id="378c5-105">For serialization of this RDF syntax, use RDF [TURTLE](https://www.w3.org/TR/turtle/).</span></span>

<span data-ttu-id="378c5-106">I följande tabell visas [SKOS](https://www.w3.org/TR/skos-primer/) motsvarande [SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) -vokabulär.</span><span class="sxs-lookup"><span data-stu-id="378c5-106">The following table shows the [SKOS](https://www.w3.org/TR/skos-primer/) equivalents for the [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary.</span></span> <span data-ttu-id="378c5-107">SharePoint har inte stöd för [SKOS](https://www.w3.org/TR/skos-primer/) -värden som inte har någon motsvarande SharePoint-taxonomi.</span><span class="sxs-lookup"><span data-stu-id="378c5-107">SharePoint does not support [SKOS](https://www.w3.org/TR/skos-primer/) values that have no SharePoint taxonomy equivalent.</span></span>

|<span data-ttu-id="378c5-108">SharePoint-taxonomi</span><span class="sxs-lookup"><span data-stu-id="378c5-108">SharePoint taxonomy</span></span>|<span data-ttu-id="378c5-109">SKOS motsvarande</span><span class="sxs-lookup"><span data-stu-id="378c5-109">SKOS equivalent</span></span>|
|:-----------------|:--------------|
|<span data-ttu-id="378c5-110">SharePoint-taxonomi: term</span><span class="sxs-lookup"><span data-stu-id="378c5-110">sharepoint-taxonomy:Term</span></span>|<span data-ttu-id="378c5-111">skos: begrepp</span><span class="sxs-lookup"><span data-stu-id="378c5-111">skos:Concept</span></span>|
|<span data-ttu-id="378c5-112">SharePoint-taxonomi: TermSet</span><span class="sxs-lookup"><span data-stu-id="378c5-112">sharepoint-taxonomy:TermSet</span></span>|<span data-ttu-id="378c5-113">skos:ConceptScheme</span><span class="sxs-lookup"><span data-stu-id="378c5-113">skos:ConceptScheme</span></span>|
|<span data-ttu-id="378c5-114">SharePoint-taxonomi: inTermSet</span><span class="sxs-lookup"><span data-stu-id="378c5-114">sharepoint-taxonomy:inTermSet</span></span>|<span data-ttu-id="378c5-115">skos: inschema</span><span class="sxs-lookup"><span data-stu-id="378c5-115">skos:inScheme</span></span>|
|<span data-ttu-id="378c5-116">SharePoint-taxonomi: hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="378c5-116">sharepoint-taxonomy:hasTopLevelTerm</span></span>|<span data-ttu-id="378c5-117">skos:hasTopConcept</span><span class="sxs-lookup"><span data-stu-id="378c5-117">skos:hasTopConcept</span></span>|
|<span data-ttu-id="378c5-118">SharePoint-taxonomi: topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="378c5-118">sharepoint-taxonomy:topLevelTermOf</span></span>|<span data-ttu-id="378c5-119">skos:topConceptOf</span><span class="sxs-lookup"><span data-stu-id="378c5-119">skos:topConceptOf</span></span>|
|<span data-ttu-id="378c5-120">SharePoint-taxonomi: defaultLabel</span><span class="sxs-lookup"><span data-stu-id="378c5-120">sharepoint-taxonomy:defaultLabel</span></span>|<span data-ttu-id="378c5-121">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="378c5-121">skos:prefLabel</span></span>|
|<span data-ttu-id="378c5-122">SharePoint-taxonomi: termSetName</span><span class="sxs-lookup"><span data-stu-id="378c5-122">sharepoint-taxonomy:termSetName</span></span>|<span data-ttu-id="378c5-123">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="378c5-123">skos:prefLabel</span></span>|
|<span data-ttu-id="378c5-124">SharePoint-taxonomi: propertyName</span><span class="sxs-lookup"><span data-stu-id="378c5-124">sharepoint-taxonomy:propertyName</span></span>|<span data-ttu-id="378c5-125">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="378c5-125">skos:prefLabel</span></span>|
|<span data-ttu-id="378c5-126">SharePoint-taxonomi: otherLabel</span><span class="sxs-lookup"><span data-stu-id="378c5-126">sharepoint-taxonomy:otherLabel</span></span>|<span data-ttu-id="378c5-127">skos:altLabel</span><span class="sxs-lookup"><span data-stu-id="378c5-127">skos:altLabel</span></span>|
|<span data-ttu-id="378c5-128">SharePoint-taxonomi: Beskrivning</span><span class="sxs-lookup"><span data-stu-id="378c5-128">sharepoint-taxonomy:description</span></span>|<span data-ttu-id="378c5-129">skos: definition</span><span class="sxs-lookup"><span data-stu-id="378c5-129">skos:definition</span></span>|
|<span data-ttu-id="378c5-130">SharePoint-taxonomi: överordnad</span><span class="sxs-lookup"><span data-stu-id="378c5-130">sharepoint-taxonomy:parent</span></span>|<span data-ttu-id="378c5-131">skos: bredare</span><span class="sxs-lookup"><span data-stu-id="378c5-131">skos:broader</span></span>|
|<span data-ttu-id="378c5-132">SharePoint-taxonomi: underordnad</span><span class="sxs-lookup"><span data-stu-id="378c5-132">sharepoint-taxonomy:child</span></span>|<span data-ttu-id="378c5-133">skos: smalare</span><span class="sxs-lookup"><span data-stu-id="378c5-133">skos:narrower</span></span>|

<span data-ttu-id="378c5-134">I följande tabell visas de enheter i SharePoint-taxonomin som härleds från [Owl](https://www.w3.org/TR/owl2-primer/).</span><span class="sxs-lookup"><span data-stu-id="378c5-134">The following table displays the entities of the SharePoint taxonomy vocabulary derived from [OWL](https://www.w3.org/TR/owl2-primer/).</span></span>

|<span data-ttu-id="378c5-135">SharePoint-vokabulär</span><span class="sxs-lookup"><span data-stu-id="378c5-135">SharePoint taxonomy vocabulary</span></span>|<span data-ttu-id="378c5-136">Härlett från OWL</span><span class="sxs-lookup"><span data-stu-id="378c5-136">Derived from OWL</span></span>|
|:-----------------------------|:----------------------|
|<span data-ttu-id="378c5-137">SharePoint-taxonomi: isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="378c5-137">sharepoint-taxonomy:isAvailableForTagging</span></span>|<span data-ttu-id="378c5-138">owl:datatypeproperty</span><span class="sxs-lookup"><span data-stu-id="378c5-138">owl:datatypeproperty</span></span>|
|<span data-ttu-id="378c5-139">SharePoint-taxonomi: SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="378c5-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="378c5-140">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="378c5-140">owl:ObjectProperty</span></span>|
|<span data-ttu-id="378c5-141">SharePoint-taxonomi: LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="378c5-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="378c5-142">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="378c5-142">owl:ObjectProperty</span></span>|
|<span data-ttu-id="378c5-143">SharePoint-taxonomi: CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="378c5-143">sharepoint-taxonomy:CustomPropertyForTermSet</span></span>|<span data-ttu-id="378c5-144">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="378c5-144">owl:ObjectProperty</span></span>|

## <a name="sharepoint-taxonomy-vocabulary"></a><span data-ttu-id="378c5-145">SharePoint-vokabulär</span><span class="sxs-lookup"><span data-stu-id="378c5-145">SharePoint taxonomy vocabulary</span></span>

<span data-ttu-id="378c5-146">En taxonomi är ett formellt klassificerings system.</span><span class="sxs-lookup"><span data-stu-id="378c5-146">A taxonomy is a formal classification system.</span></span> <span data-ttu-id="378c5-147">En taxonomi grupperar orden, etiketterna och termerna som beskriver något och sorterar sedan grupperna i en hierarki.</span><span class="sxs-lookup"><span data-stu-id="378c5-147">A taxonomy groups the words, labels, and terms that describe something, and then arranges the groups into a hierarchy.</span></span>

<span data-ttu-id="378c5-148">**SharePoint-taxonomi: term**</span><span class="sxs-lookup"><span data-stu-id="378c5-148">**sharepoint-taxonomy:Term**</span></span>

<span data-ttu-id="378c5-149">Representerar en term eller ett nyckelord i en hierarki med hanterade metadata.</span><span class="sxs-lookup"><span data-stu-id="378c5-149">Represents a Term or a Keyword in a managed metadata hierarchy.</span></span>

<span data-ttu-id="378c5-150">En [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) är en Atomic-enhet i en SharePoint- [postlagring](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span><span class="sxs-lookup"><span data-stu-id="378c5-150">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is the atomic unit of a SharePoint [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span></span> <span data-ttu-id="378c5-151">Varje [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) tillhör en [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) som tillhör en [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span><span class="sxs-lookup"><span data-stu-id="378c5-151">Each [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belongs to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) that belongs to a [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> 

<span data-ttu-id="378c5-152">Syntaxen för att definiera en [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) är följande:</span><span class="sxs-lookup"><span data-stu-id="378c5-152">The syntax to define a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is as follows:</span></span>

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="378c5-153">En [period](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) är obligatorisk i en [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="378c5-153">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) compulsorily exists within a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="378c5-154">DefaultLabel är namnet på [termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) som det visas i den visuella presentationen.</span><span class="sxs-lookup"><span data-stu-id="378c5-154">DefaultLabel is the name of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) as it appears in the visual representation.</span></span> <span data-ttu-id="378c5-155">De obligatoriska fälten för definiering av en [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) är:</span><span class="sxs-lookup"><span data-stu-id="378c5-155">The required fields for defining a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) include:</span></span>

- <span data-ttu-id="378c5-156">SharePoint-taxonomi: defaultLabel</span><span class="sxs-lookup"><span data-stu-id="378c5-156">sharepoint-taxonomy:defaultLabel</span></span>
- <span data-ttu-id="378c5-157">SharePoint-taxonomi: inTermSet</span><span class="sxs-lookup"><span data-stu-id="378c5-157">sharepoint-taxonomy:inTermSet</span></span>

<span data-ttu-id="378c5-158">En [period](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) kan:</span><span class="sxs-lookup"><span data-stu-id="378c5-158">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can:</span></span>

- <span data-ttu-id="378c5-159">Vara hierarkiskt relaterad till en annan [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) som tillhandahålls båda [villkoren](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) tillhör samma [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="378c5-159">Be hierarchically related to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is provided both the [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belong to the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="378c5-160">Har flera underordnade [termer](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), men bara en enda överordnad [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="378c5-160">Have multiple child [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), but only a single parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>
- <span data-ttu-id="378c5-161">Inte en definierad överordnad [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) , om den är en TopLevelTermOf en [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="378c5-161">Not have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) defined, if it is a topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="378c5-162">Ha en defaultLabel [, per arbets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) postspråk.</span><span class="sxs-lookup"><span data-stu-id="378c5-162">Have one defaultLabel, per [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>
- <span data-ttu-id="378c5-163">Inte finnas om den inte innehåller en överordnad [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)och inte heller TopLevelTermOf en [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="378c5-163">Not exist if it neither contains a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), nor is the topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> 
- <span data-ttu-id="378c5-164">Har bara ett unikt defaultLabel på samma hierarkiska nivå.</span><span class="sxs-lookup"><span data-stu-id="378c5-164">Have only a unique defaultLabel in the same hierarchical level.</span></span>

<span data-ttu-id="378c5-165">**SharePoint-taxonomi: TermSet**</span><span class="sxs-lookup"><span data-stu-id="378c5-165">**sharepoint-taxonomy:TermSet**</span></span>

<span data-ttu-id="378c5-166">Representerar en hierarkisk eller platt uppsättning med term objekt som kallas "TermSet".</span><span class="sxs-lookup"><span data-stu-id="378c5-166">Represents a hierarchical or flat set of Term objects known as a "TermSet".</span></span>

<span data-ttu-id="378c5-167">När namnet föreslås är TermSet en uppsättning [termer](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="378c5-167">As the name suggests, TermSet is a set of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="378c5-168">En [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) i en [lagrings](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) tid måste tillhöra en [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="378c5-168">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) must belong to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="378c5-169">Ingen [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) kan existera oberoende.</span><span class="sxs-lookup"><span data-stu-id="378c5-169">No [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can exist independently.</span></span> 

<span data-ttu-id="378c5-170">Syntaxen för att definiera en [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) är:</span><span class="sxs-lookup"><span data-stu-id="378c5-170">The syntax to define a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

<span data-ttu-id="378c5-171">[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) grupperas logiskt i [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span><span class="sxs-lookup"><span data-stu-id="378c5-171">[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) are logically grouped together in [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> <span data-ttu-id="378c5-172">Det obligatoriska fältet för att definiera en [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) är:</span><span class="sxs-lookup"><span data-stu-id="378c5-172">The required field for defining a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

- <span data-ttu-id="378c5-173">SharePoint-taxonomi: termSetName</span><span class="sxs-lookup"><span data-stu-id="378c5-173">sharepoint-taxonomy:termSetName</span></span>

<span data-ttu-id="378c5-174">Om den termSetName som anges inte är unik i [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), lägger SharePoint ett nummer i slutet av namnet så att det är unikt för termSetName.</span><span class="sxs-lookup"><span data-stu-id="378c5-174">In the case of the termSetName provided is not unique within the [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), SharPoint appends a number at the end of the name to maintain the uniqueness of termSetName(s).</span></span>

<span data-ttu-id="378c5-175">**SharePoint-taxonomi: hasTopLevelTerm**</span><span class="sxs-lookup"><span data-stu-id="378c5-175">**sharepoint-taxonomy:hasTopLevelTerm**</span></span>

<span data-ttu-id="378c5-176">SharePoint använder den här egenskapen för att mappa den översta [termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) i [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), vilket är start punkten för [termernas](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) hierarki i ett [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="378c5-176">SharePoint uses this property to map the top most [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), which is the entry point to the hierarchy of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="378c5-177">Det här är en inverterad relation till SharePoint-taxonomi: topLevelTermOf.</span><span class="sxs-lookup"><span data-stu-id="378c5-177">This is an inverse relation to sharepoint-taxonomy:topLevelTermOf.</span></span> 

<span data-ttu-id="378c5-178">Syntaxen för att definiera detta är:</span><span class="sxs-lookup"><span data-stu-id="378c5-178">The syntax to define this is:</span></span>

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> <span data-ttu-id="378c5-179">Du kan inte ange [termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) på den översta nivån för en överordnad [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="378c5-179">You cannot define the top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="378c5-180">**SharePoint-taxonomi: topLevelTermOf**</span><span class="sxs-lookup"><span data-stu-id="378c5-180">**sharepoint-taxonomy:topLevelTermOf**</span></span>

<span data-ttu-id="378c5-181">SharePoint-taxonomi: topLevelTermOf är inversen till SharePoint-taxonomi: hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="378c5-181">Sharepoint-taxonomy:topLevelTermOf is the inverse of sharepoint-taxonomy:hasTopLevelTerm</span></span>

<span data-ttu-id="378c5-182">Syntaxen för att definiera detta är:</span><span class="sxs-lookup"><span data-stu-id="378c5-182">The syntax to define this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

<span data-ttu-id="378c5-183">**SharePoint-taxonomi: inTermSet**</span><span class="sxs-lookup"><span data-stu-id="378c5-183">**sharepoint-taxonomy:inTermSet**</span></span>

<span data-ttu-id="378c5-184">Använd den här för att mappa en [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) till en [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="378c5-184">Use this to map a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="378c5-185">En [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) kan bara finnas i en enda [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="378c5-185">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can only exist in a single [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="378c5-186">SharePoint kräver den här egenskapen när du [definierar en term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span><span class="sxs-lookup"><span data-stu-id="378c5-186">SharePoint requires this property when [defining a term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span></span>

## <a name="required-labels"></a><span data-ttu-id="378c5-187">Obligatoriska etiketter</span><span class="sxs-lookup"><span data-stu-id="378c5-187">Required labels</span></span>

<span data-ttu-id="378c5-188">Din organisation kanske vill göra omsorgsfull planering innan du börjar använda hanterade metadata.</span><span class="sxs-lookup"><span data-stu-id="378c5-188">Your organization may want to do careful planning before you start to use managed metadata.</span></span> <span data-ttu-id="378c5-189">Hur mycket planering som måste göras beror på hur formell din taxonomi är.</span><span class="sxs-lookup"><span data-stu-id="378c5-189">The amount of planning that you must do depends on how formal your taxonomy is.</span></span> <span data-ttu-id="378c5-190">Det beror också på hur många kontroller du vill använda för metadata.</span><span class="sxs-lookup"><span data-stu-id="378c5-190">It also depends on how much control that you want to impose on metadata.</span></span> <span data-ttu-id="378c5-191">På varje nivå i hierarkin måste du konfigurera obligatoriska LABLES för en term eller TermSet.</span><span class="sxs-lookup"><span data-stu-id="378c5-191">At each level of the hierarchy, you need to configure required lables for a Term or TermSet.</span></span>

<span data-ttu-id="378c5-192">En term kan ha en eller flera etiketter på standard språket och noll eller fler etiketter i ett språk som inte är standard.</span><span class="sxs-lookup"><span data-stu-id="378c5-192">A Term can have one or more labels in the default language, and zero or more labels in the non-default language.</span></span> <span data-ttu-id="378c5-193">Om termen har etiketter på ett språk måste en av etiketterna vara standard etiketten.</span><span class="sxs-lookup"><span data-stu-id="378c5-193">If the term has labels in a language, one of the labels must be the default label.</span></span>

<span data-ttu-id="378c5-194">**SharePoint-taxonomi: defaultLabel**</span><span class="sxs-lookup"><span data-stu-id="378c5-194">**sharepoint-taxonomy:defaultLabel**</span></span>

<span data-ttu-id="378c5-195">Använd den här vanliga standard etiketten för en [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) som är en obligatorisk parameter för en [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="378c5-195">Use this default lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is a required parameter for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="378c5-196">Används för att visuellt representera [termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="378c5-196">Use to visually representing the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="378c5-197">Syntaxen för att definiera en defaultLabel är:</span><span class="sxs-lookup"><span data-stu-id="378c5-197">The syntax to define a defaultLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="378c5-198">DefaultLabel innehåller två delar för den – strängen och språkmärkningen.</span><span class="sxs-lookup"><span data-stu-id="378c5-198">The defaultLabel contains two parts to it – the string and the language tag.</span></span> <span data-ttu-id="378c5-199">Språket måste vara ett av arbets postspråken för [lagrings platsen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) .</span><span class="sxs-lookup"><span data-stu-id="378c5-199">The language must be one of the [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working languages.</span></span> <span data-ttu-id="378c5-200">DefaultLabel måste vara unikt för alla [termer](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) i samma [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), på samma hierarkiska nivå.</span><span class="sxs-lookup"><span data-stu-id="378c5-200">The defaultLabel must be unique for all [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), at the same hierarchical level.</span></span>

<span data-ttu-id="378c5-201">**SharePoint-taxonomi: termSetName**</span><span class="sxs-lookup"><span data-stu-id="378c5-201">**sharepoint-taxonomy:termSetName**</span></span>

<span data-ttu-id="378c5-202">Hämtar och anger namnet på det aktuella TermSet-objektet.</span><span class="sxs-lookup"><span data-stu-id="378c5-202">Gets and sets the name for the current TermSet object.</span></span>

<span data-ttu-id="378c5-203">Den här lexikala etiketten för en [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)på ett språk för [lagrings platsen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) .</span><span class="sxs-lookup"><span data-stu-id="378c5-203">This the lexical label for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span> <span data-ttu-id="378c5-204">Det här är en obligatorisk parameter för en [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="378c5-204">This is a required parameter for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="378c5-205">Används för att visuellt representera en [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="378c5-205">Use to visually representing a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>

<span data-ttu-id="378c5-206">Syntaxen för att definiera en termSetName är:</span><span class="sxs-lookup"><span data-stu-id="378c5-206">The syntax to define a termSetName is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

<span data-ttu-id="378c5-207">**SharePoint-taxonomi: propertyName**</span><span class="sxs-lookup"><span data-stu-id="378c5-207">**sharepoint-taxonomy:propertyName**</span></span>

<span data-ttu-id="378c5-208">Hämtar och anger egenskaps namnet för det aktuella TermSet-objektet.</span><span class="sxs-lookup"><span data-stu-id="378c5-208">Gets and sets the property name for the current TermSet object.</span></span>

<span data-ttu-id="378c5-209">Det här är lexikalisk etikett för en SharePoint-taxonomi: SharedCustomPropertyForTerm, SharePoint-taxonomi: LocalCustomPropertyForTerm och SharePoint-taxonomi: CustomPropertyForTermSet på ett arbets språk för [lagrings platsen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) .</span><span class="sxs-lookup"><span data-stu-id="378c5-209">This is the lexical label for a sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm and sharepoint-taxonomy:CustomPropertyForTermSet in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>

<span data-ttu-id="378c5-210">SharePoint-taxonomin: propertyName behandlas som CustomProperty.</span><span class="sxs-lookup"><span data-stu-id="378c5-210">The sharepoint-taxonomy:propertyName is treated as the key of the CustomProperty.</span></span>

<span data-ttu-id="378c5-211">Syntaxen för att definiera en propetyName är:</span><span class="sxs-lookup"><span data-stu-id="378c5-211">The syntax to define a propetyName is:</span></span>

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a><span data-ttu-id="378c5-212">Valfria etiketter</span><span class="sxs-lookup"><span data-stu-id="378c5-212">Optional labels</span></span>

<span data-ttu-id="378c5-213">Du kan också lägga till valfria etiketter i taxonomin.</span><span class="sxs-lookup"><span data-stu-id="378c5-213">You can also add optional labels to your taxonomy.</span></span>

<span data-ttu-id="378c5-214">**SharePoint-taxonomi: otherLabel**</span><span class="sxs-lookup"><span data-stu-id="378c5-214">**sharepoint-taxonomy:otherLabel**</span></span>

<span data-ttu-id="378c5-215">Det här är den alternativa lexikala etiketten för en [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="378c5-215">This is the alternate lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="378c5-216">Syntaxen för att definiera en otherLabel är:</span><span class="sxs-lookup"><span data-stu-id="378c5-216">The syntax to define an otherLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a><span data-ttu-id="378c5-217">Semantiska relationer</span><span class="sxs-lookup"><span data-stu-id="378c5-217">Semantic relationships</span></span>

<span data-ttu-id="378c5-218">Taxonomier har hierarkiskt och ibland en enkel "relaterad termen", men vissa har "semantiska relationer" eller egna relationer.</span><span class="sxs-lookup"><span data-stu-id="378c5-218">Taxonomies have hierarchical and sometimes a simple “related term” associative relationship, but some have "semantic relationships" or custom-created relationships.</span></span> 

<span data-ttu-id="378c5-219">**SharePoint-taxonomi: överordnad**</span><span class="sxs-lookup"><span data-stu-id="378c5-219">**sharepoint-taxonomy:parent**</span></span>

<span data-ttu-id="378c5-220">Det här hierarkiskt relaterar en [period](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) till [en annan.](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)</span><span class="sxs-lookup"><span data-stu-id="378c5-220">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="378c5-221">En [period](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) kan vara en top level- [period](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) på en [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), men om den inte måste ha en överordnad [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="378c5-221">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) could be a top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), but in case it doesn’t it must have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="378c5-222">Syntaxen för att definiera en överordnad är:</span><span class="sxs-lookup"><span data-stu-id="378c5-222">The syntax to define a parent is:</span></span>

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

<span data-ttu-id="378c5-223">Det innebär att TermA1 har ett överordnat sökord.</span><span class="sxs-lookup"><span data-stu-id="378c5-223">This means that TermA1 has parent TermA.</span></span> <span data-ttu-id="378c5-224">Det innebär också att TermA1 är underordnat.</span><span class="sxs-lookup"><span data-stu-id="378c5-224">Inversely it also means that TermA1 is the child of TermA.</span></span> <span data-ttu-id="378c5-225">Relation mellan över-och underordnade objekt är inversible-relationer.</span><span class="sxs-lookup"><span data-stu-id="378c5-225">Parent-child relationship is an inversible relationship.</span></span>

<span data-ttu-id="378c5-226">**SharePoint-taxonomi: underordnad**</span><span class="sxs-lookup"><span data-stu-id="378c5-226">**sharepoint-taxonomy:child**</span></span>

<span data-ttu-id="378c5-227">Objektet innehåller en eller flera underordnade TermSet-instanser och dessa kan nås via egenskapen TermSets.</span><span class="sxs-lookup"><span data-stu-id="378c5-227">The object contains one or more child TermSet instances, and these can be accessed through the TermSets property.</span></span> <span data-ttu-id="378c5-228">Den här klassen innehåller också metoder för att skapa nya underordnade TermSet-objekt.</span><span class="sxs-lookup"><span data-stu-id="378c5-228">This class also provides methods for creating new child TermSet objects.</span></span> <span data-ttu-id="378c5-229">Behörigheter för redigering av underordnade termer och TermSet-instanser anges i gruppen.</span><span class="sxs-lookup"><span data-stu-id="378c5-229">Permissions for editing child Term and TermSet instances is specified on the group.</span></span> 

<span data-ttu-id="378c5-230">Det här hierarkiskt relaterar en [period](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) till [en annan.](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)</span><span class="sxs-lookup"><span data-stu-id="378c5-230">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="378c5-231">Syntaxen för att definiera ett barn är:</span><span class="sxs-lookup"><span data-stu-id="378c5-231">The syntax to define a child is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

<span data-ttu-id="378c5-232">Det innebär att termen bara har underordnade TermA1.</span><span class="sxs-lookup"><span data-stu-id="378c5-232">This means that TermA has child TermA1.</span></span> <span data-ttu-id="378c5-233">Det innebär också att den termen är moder för TermA1 överordnade-underordnad relation är ett inversible-förhållande.</span><span class="sxs-lookup"><span data-stu-id="378c5-233">Inversely it also means that TermA is the parent of TermA1 parent-child relationship is an inversible relationship.</span></span>

## <a name="documentation-notes"></a><span data-ttu-id="378c5-234">Dokumentations anteckningar</span><span class="sxs-lookup"><span data-stu-id="378c5-234">Documentation notes</span></span>

<span data-ttu-id="378c5-235">I det här avsnittet beskrivs taxonomin i Microsoft. SharePoint. taxonomi-namnrymd.</span><span class="sxs-lookup"><span data-stu-id="378c5-235">This section discusses the taxonomy detailed in the Microsoft.SharePoint.Taxonomy Namespace.</span></span>

<span data-ttu-id="378c5-236">**SharePoint-taxonomi: Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="378c5-236">**sharepoint-taxonomy:description**</span></span>

<span data-ttu-id="378c5-237">Det här är en detaljerad förklaring av en [SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) -vokabulär för ord lista.</span><span class="sxs-lookup"><span data-stu-id="378c5-237">This is a detailed explanation of any [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary entity.</span></span> 

<span data-ttu-id="378c5-238">Syntaxen för att lägga till en beskrivning är:</span><span class="sxs-lookup"><span data-stu-id="378c5-238">The syntax to add a description is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a><span data-ttu-id="378c5-239">Anpassade egenskaper</span><span class="sxs-lookup"><span data-stu-id="378c5-239">Custom properties</span></span>

<span data-ttu-id="378c5-240">Hämtar de egna egenskaps objekten för det aktuella term objekt från den skrivskyddade ord listan.</span><span class="sxs-lookup"><span data-stu-id="378c5-240">Gets the collection of custom property objects for the current Term object from the read-only dictionary.</span></span>

<span data-ttu-id="378c5-241">Anpassade egenskaper är par med nyckelord som du kan definiera för en [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) eller en [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), för att få mer information om [termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) eller en [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="378c5-241">Custom Properties are key-values pairs that can be defined for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), to further the description of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="378c5-242">SharePoint anger nyckel för den anpassade egenskapen med hjälp av propertyName.</span><span class="sxs-lookup"><span data-stu-id="378c5-242">SharePoint specifies the key of the custom property with the help of propertyName.</span></span>

<span data-ttu-id="378c5-243">**SharePoint-taxonomi: CustomPropertyForTermSet**</span><span class="sxs-lookup"><span data-stu-id="378c5-243">**sharepoint-taxonomy:CustomPropertyForTermSet**</span></span>

<span data-ttu-id="378c5-244">Syntaxen för att definiera detta är:</span><span class="sxs-lookup"><span data-stu-id="378c5-244">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

<span data-ttu-id="378c5-245">**SharePoint-taxonomi: SharedCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="378c5-245">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span></span>

<span data-ttu-id="378c5-246">Om den anpassade egenskapen för en [period](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) måste flyttas tillsammans med [termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)när du återanvänder [termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) någon annan, måste du ange den under SharedCustomPropertyForTerm.</span><span class="sxs-lookup"><span data-stu-id="378c5-246">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) needs to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to be define it under SharedCustomPropertyForTerm.</span></span>

<span data-ttu-id="378c5-247">Syntaxen för att definiera detta är:</span><span class="sxs-lookup"><span data-stu-id="378c5-247">The syntax to define this is:</span></span>

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
<span data-ttu-id="378c5-248">**SharePoint-taxonomi: LocalCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="378c5-248">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span></span>

<span data-ttu-id="378c5-249">Om den anpassade egenskapen för en [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) inte behöver transporteras tillsammans med [termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)när du återanvänder [termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) någon annan, måste du definiera den under LocalCustomPropertyForTerm.</span><span class="sxs-lookup"><span data-stu-id="378c5-249">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) does not need to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to define it under LocalCustomPropertyForTerm.</span></span>

<span data-ttu-id="378c5-250">Syntaxen för att definiera detta är:</span><span class="sxs-lookup"><span data-stu-id="378c5-250">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a><span data-ttu-id="378c5-251">Data egenskaper</span><span class="sxs-lookup"><span data-stu-id="378c5-251">Data properties</span></span>

<span data-ttu-id="378c5-252">På varje nivå i hierarkin kan du konfigurera särskilda data egenskaper för en term eller TermSet.</span><span class="sxs-lookup"><span data-stu-id="378c5-252">At each level of the hierarchy, you can configure specific data properties for a Term or TermSet.</span></span>

<span data-ttu-id="378c5-253">**SharePoint-taxonomi: isAvailableForTagging**</span><span class="sxs-lookup"><span data-stu-id="378c5-253">**sharepoint-taxonomy:isAvailableForTagging**</span></span>

<span data-ttu-id="378c5-254">Använd det här alternativet för att ange om en [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) eller en [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) ska vara tillgänglig i SharePoint-listor och-bibliotek.</span><span class="sxs-lookup"><span data-stu-id="378c5-254">Use this to specify if a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) available in SharePoint Lists and Libraries.</span></span>  

<span data-ttu-id="378c5-255">Syntaxen för det här är:</span><span class="sxs-lookup"><span data-stu-id="378c5-255">The syntax for this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a><span data-ttu-id="378c5-256">Domän och område</span><span class="sxs-lookup"><span data-stu-id="378c5-256">Domain and range</span></span>

<span data-ttu-id="378c5-257">Tabellen nedan beskriver domän och räckvidd för SharePoint-taxonomi.</span><span class="sxs-lookup"><span data-stu-id="378c5-257">The table below describes the domain and range of SharePoint taxonomy vocabulary.</span></span>

|<span data-ttu-id="378c5-258">Predikat/verb</span><span class="sxs-lookup"><span data-stu-id="378c5-258">Predicates/verb</span></span>|<span data-ttu-id="378c5-259">Särdirektiv</span><span class="sxs-lookup"><span data-stu-id="378c5-259">Meaning</span></span>|<span data-ttu-id="378c5-260">Domän</span><span class="sxs-lookup"><span data-stu-id="378c5-260">Domain</span></span>|<span data-ttu-id="378c5-261">Område</span><span class="sxs-lookup"><span data-stu-id="378c5-261">Range</span></span>|
|:--------------|:------|:-----|:----|
<span data-ttu-id="378c5-262">inTermSet</span><span class="sxs-lookup"><span data-stu-id="378c5-262">inTermSet</span></span>|<span data-ttu-id="378c5-263">I term uppsättning</span><span class="sxs-lookup"><span data-stu-id="378c5-263">In term set</span></span>|<span data-ttu-id="378c5-264">Kortsiktig</span><span class="sxs-lookup"><span data-stu-id="378c5-264">Term</span></span>|<span data-ttu-id="378c5-265">Term uppsättning</span><span class="sxs-lookup"><span data-stu-id="378c5-265">Term Set</span></span>|
<span data-ttu-id="378c5-266">inTermGroup</span><span class="sxs-lookup"><span data-stu-id="378c5-266">inTermGroup</span></span>|<span data-ttu-id="378c5-267">Gruppen term</span><span class="sxs-lookup"><span data-stu-id="378c5-267">In term group</span></span>|<span data-ttu-id="378c5-268">TermSet</span><span class="sxs-lookup"><span data-stu-id="378c5-268">TermSet</span></span>|<span data-ttu-id="378c5-269">TermGroup</span><span class="sxs-lookup"><span data-stu-id="378c5-269">TermGroup</span></span>|
<span data-ttu-id="378c5-270">topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="378c5-270">topLevelTermOf</span></span>|<span data-ttu-id="378c5-271">Är den översta nivån för</span><span class="sxs-lookup"><span data-stu-id="378c5-271">Is Top Level Term Of</span></span>|<span data-ttu-id="378c5-272">Kortsiktig</span><span class="sxs-lookup"><span data-stu-id="378c5-272">Term</span></span>|<span data-ttu-id="378c5-273">TermSet</span><span class="sxs-lookup"><span data-stu-id="378c5-273">TermSet</span></span>|
<span data-ttu-id="378c5-274">hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="378c5-274">hasTopLevelTerm</span></span>|<span data-ttu-id="378c5-275">Har den översta nivån</span><span class="sxs-lookup"><span data-stu-id="378c5-275">Has top level term</span></span>|<span data-ttu-id="378c5-276">Term uppsättning</span><span class="sxs-lookup"><span data-stu-id="378c5-276">Term Set</span></span>|<span data-ttu-id="378c5-277">Kortsiktig</span><span class="sxs-lookup"><span data-stu-id="378c5-277">Term</span></span>|
<span data-ttu-id="378c5-278">termSetName</span><span class="sxs-lookup"><span data-stu-id="378c5-278">termSetName</span></span>|<span data-ttu-id="378c5-279">Term uppsättningen har namn</span><span class="sxs-lookup"><span data-stu-id="378c5-279">Term set has Name</span></span>|<span data-ttu-id="378c5-280">Kortsiktig</span><span class="sxs-lookup"><span data-stu-id="378c5-280">Term</span></span>|<span data-ttu-id="378c5-281">Vanlig literal</span><span class="sxs-lookup"><span data-stu-id="378c5-281">Plain literal</span></span>|
<span data-ttu-id="378c5-282">defaultLabel</span><span class="sxs-lookup"><span data-stu-id="378c5-282">defaultLabel</span></span>|<span data-ttu-id="378c5-283">Termen har standard etikett</span><span class="sxs-lookup"><span data-stu-id="378c5-283">Term has default label</span></span>|<span data-ttu-id="378c5-284">Kortsiktig</span><span class="sxs-lookup"><span data-stu-id="378c5-284">Term</span></span>|<span data-ttu-id="378c5-285">Vanlig literal</span><span class="sxs-lookup"><span data-stu-id="378c5-285">Plain literal</span></span>|
<span data-ttu-id="378c5-286">otherLabel</span><span class="sxs-lookup"><span data-stu-id="378c5-286">otherLabel</span></span>|<span data-ttu-id="378c5-287">Termen har en annan etikett</span><span class="sxs-lookup"><span data-stu-id="378c5-287">Term has other label</span></span>|<span data-ttu-id="378c5-288">Kortsiktig</span><span class="sxs-lookup"><span data-stu-id="378c5-288">Term</span></span>|<span data-ttu-id="378c5-289">Vanlig literal</span><span class="sxs-lookup"><span data-stu-id="378c5-289">Plain literal</span></span>|
<span data-ttu-id="378c5-290">propertyName</span><span class="sxs-lookup"><span data-stu-id="378c5-290">propertyName</span></span>|<span data-ttu-id="378c5-291">Har egenskaps etikett</span><span class="sxs-lookup"><span data-stu-id="378c5-291">Has Property Label</span></span>|<span data-ttu-id="378c5-292">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="378c5-292">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span></span> |<span data-ttu-id="378c5-293">Boolesk, sträng, heltal, decimal, dubbel</span><span class="sxs-lookup"><span data-stu-id="378c5-293">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="378c5-294">beskrivning</span><span class="sxs-lookup"><span data-stu-id="378c5-294">description</span></span>|<span data-ttu-id="378c5-295">Har Beskrivning</span><span class="sxs-lookup"><span data-stu-id="378c5-295">Has Description</span></span>|<span data-ttu-id="378c5-296">Alla</span><span class="sxs-lookup"><span data-stu-id="378c5-296">All</span></span>|<span data-ttu-id="378c5-297">Vanlig literal</span><span class="sxs-lookup"><span data-stu-id="378c5-297">Plain literal</span></span>|
|<span data-ttu-id="378c5-298">objektet</span><span class="sxs-lookup"><span data-stu-id="378c5-298">parent</span></span>|<span data-ttu-id="378c5-299">Har förälder</span><span class="sxs-lookup"><span data-stu-id="378c5-299">Has parent</span></span>|<span data-ttu-id="378c5-300">Kortsiktig</span><span class="sxs-lookup"><span data-stu-id="378c5-300">Term</span></span>|<span data-ttu-id="378c5-301">Kortsiktig</span><span class="sxs-lookup"><span data-stu-id="378c5-301">Term</span></span>|
|<span data-ttu-id="378c5-302">element</span><span class="sxs-lookup"><span data-stu-id="378c5-302">child</span></span>|<span data-ttu-id="378c5-303">Har underordnade</span><span class="sxs-lookup"><span data-stu-id="378c5-303">Has Child</span></span>|<span data-ttu-id="378c5-304">Kortsiktig</span><span class="sxs-lookup"><span data-stu-id="378c5-304">Term</span></span>|<span data-ttu-id="378c5-305">Kortsiktig</span><span class="sxs-lookup"><span data-stu-id="378c5-305">Term</span></span>|
|<span data-ttu-id="378c5-306">isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="378c5-306">isAvailableForTagging</span></span>|<span data-ttu-id="378c5-307">Är tillgängligt för taggning</span><span class="sxs-lookup"><span data-stu-id="378c5-307">Is available for tagging</span></span>|<span data-ttu-id="378c5-308">Period, term uppsättning</span><span class="sxs-lookup"><span data-stu-id="378c5-308">Term, Term Set</span></span>|<span data-ttu-id="378c5-309">Boolesk</span><span class="sxs-lookup"><span data-stu-id="378c5-309">Boolean</span></span>|
|<span data-ttu-id="378c5-310">SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="378c5-310">SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="378c5-311">Har en delad egenskap</span><span class="sxs-lookup"><span data-stu-id="378c5-311">Has shared custom property</span></span>|<span data-ttu-id="378c5-312">Kortsiktig</span><span class="sxs-lookup"><span data-stu-id="378c5-312">Term</span></span>|<span data-ttu-id="378c5-313">Boolesk, sträng, heltal, decimal, dubbel</span><span class="sxs-lookup"><span data-stu-id="378c5-313">Boolean, string, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="378c5-314">LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="378c5-314">LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="378c5-315">Har lokal anpassad egenskap</span><span class="sxs-lookup"><span data-stu-id="378c5-315">Has local custom property</span></span>|<span data-ttu-id="378c5-316">Kortsiktig</span><span class="sxs-lookup"><span data-stu-id="378c5-316">Term</span></span>|<span data-ttu-id="378c5-317">Boolesk, sträng, heltal, decimal, dubbel</span><span class="sxs-lookup"><span data-stu-id="378c5-317">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="378c5-318">CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="378c5-318">CustomPropertyForTermSet</span></span>|<span data-ttu-id="378c5-319">Har anpassad egenskap</span><span class="sxs-lookup"><span data-stu-id="378c5-319">Has Custom Property</span></span>|<span data-ttu-id="378c5-320">TermSet</span><span class="sxs-lookup"><span data-stu-id="378c5-320">TermSet</span></span>|<span data-ttu-id="378c5-321">Boolesk, sträng, heltal, decimal, dubbel</span><span class="sxs-lookup"><span data-stu-id="378c5-321">Boolean, String, Integer, Decimal, Double</span></span>|

<span data-ttu-id="378c5-322">[SKOS](https://www.w3.org/TR/skos-primer/) giltiga scenarier som [SharePoint-taxonomi](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) inte tillåter:</span><span class="sxs-lookup"><span data-stu-id="378c5-322">[SKOS](https://www.w3.org/TR/skos-primer/) valid scenarios that [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) does not allow:</span></span>

- <span data-ttu-id="378c5-323">Hierarkisk redundans-ett [SKOS](https://www.w3.org/TR/skos-primer/) koncept kan kopplas till flera bredare koncept samtidigt, men en SharePoint-taxonomi: termen kan bara innehålla en SharePoint-taxonomi: Parent, och därför är cykliskt beroende av termer inte tillåtet.</span><span class="sxs-lookup"><span data-stu-id="378c5-323">Hierarchical redundancy - A [SKOS](https://www.w3.org/TR/skos-primer/) concept can be attached to several broader concepts at the same time, but a sharepoint-taxonomy:Term can have only one sharepoint-taxonomy:parent, hence cyclic dependency, of Terms is also not allowed.</span></span>
- <span data-ttu-id="378c5-324">Det går inte att använda ägarlösa termer i SharePoint-taxonomi.</span><span class="sxs-lookup"><span data-stu-id="378c5-324">Orphaned terms are not allowed in SharePoint taxonomy.</span></span> <span data-ttu-id="378c5-325">Varje SharePoint-taxonomi: termen ska ha en SharePoint-taxonomi: Parent eller så ska den vara SharePoint-taxonomi: topLevelTermOf en TermSet.</span><span class="sxs-lookup"><span data-stu-id="378c5-325">Every sharepoint-taxonomy:Term should either have a sharepoint-taxonomy:parent or it should be the sharepoint-taxonomy:topLevelTermOf a TermSet.</span></span>
- <span data-ttu-id="378c5-326">SharePoint-taxonomi stöder inte associerade relationer.</span><span class="sxs-lookup"><span data-stu-id="378c5-326">SharePoint taxonomy does not support associative relations.</span></span>
- <span data-ttu-id="378c5-327">SharePoint-taxonomi tillåter bara två typer av hierarkiska relationer – SharePoint-taxonomi: Parent och SharePoint-taxonomi: underordnad.</span><span class="sxs-lookup"><span data-stu-id="378c5-327">SharePoint taxonomy only allows 2 types of Hierarchical relations – sharepoint-taxonomy:parent and sharepoint-Taxonomy:child.</span></span> 
- <span data-ttu-id="378c5-328">Till skillnad från [SKOS](https://www.w3.org/TR/skos-primer/) i hierarkin i SharePoint är det bara möjligt att fastställa villkor i samma termset.</span><span class="sxs-lookup"><span data-stu-id="378c5-328">Unlike [SKOS](https://www.w3.org/TR/skos-primer/) the hierarchical relationship in SharePoint taxonomy vocabulary, can only be established with Terms within the same TermSet.</span></span>

## <a name="see-also"></a><span data-ttu-id="378c5-329">Se även</span><span class="sxs-lookup"><span data-stu-id="378c5-329">See also</span></span>

[<span data-ttu-id="378c5-330">Importera en term uppsättning med ett SKOSt format</span><span class="sxs-lookup"><span data-stu-id="378c5-330">Import a term set using a SKOS-based format</span></span>](import-term-set-skos.md)

