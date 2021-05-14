---
title: Starta kvarhållning när en händelse inträffar
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-may2020
- seo-marvel-jun2020
description: Vanligtvis kan du som en del av en lösning för hantering av arkivhandlingar konfigurera en kvarhållningsetikett för att starta kvarhållningsperioden baserat på en händelse som du identifierar.
ms.openlocfilehash: ee828b6852440f5be07fdf34df2fb6a11253ae1c
ms.sourcegitcommit: 8998f70d3f7bd673f93f8d1cf12ce981b1b771c3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "52162331"
---
# <a name="start-retention-when-an-event-occurs"></a><span data-ttu-id="b0ab7-103">Starta kvarhållning när en händelse inträffar</span><span class="sxs-lookup"><span data-stu-id="b0ab7-103">Start retention when an event occurs</span></span>

><span data-ttu-id="b0ab7-104">*[Vägledning för säkerhet och efterlevnad med licensiering i Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="b0ab7-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="b0ab7-105">När du behåller innehåll baseras kvarhållningsperioden ofta på innehållets ålder.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-105">When you retain content, the retention period is often based on the age of the content.</span></span> <span data-ttu-id="b0ab7-106">Du kan till exempel hålla kvar dokument i sju år efter att de har skapats och sedan ta bort dem.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-106">For example, you might retain documents for seven years after they're created and then delete them.</span></span> <span data-ttu-id="b0ab7-107">Men när du konfigurerar [kvarhållningsetiketter](retention.md#retention-labels) kan du också basera en kvarhållningsperiod på när en specifik typ av händelse inträffar.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-107">But when you configure [retention labels](retention.md#retention-labels), you can also base a retention period on when a specific type of event occurs.</span></span> <span data-ttu-id="b0ab7-108">Händelsen utlöser start av kvarhållningsperioden, och allt innehåll med en kvarhållningsetikett för den typen av händelse tillämpad behandlas enligt etikettens kvarhållningsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-108">The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.</span></span>
  
<span data-ttu-id="b0ab7-109">Exempel på användning av händelsebaserad kvarhållning:</span><span class="sxs-lookup"><span data-stu-id="b0ab7-109">Examples for using event-based retention:</span></span>
  
- <span data-ttu-id="b0ab7-110">**Anställda som lämnar organisationen** Anta att handlingar för anställda måste behållas i tio år från det att en anställd lämnar organisationen.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-110">**Employees leaving the organization** Suppose that employee records must be retained for 10 years from the time an employee leaves the organization.</span></span> <span data-ttu-id="b0ab7-111">Efter tio år måste alla dokument som är relaterade till anställning, prestanda och uppsägning av den medarbetaren förstöras.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-111">After 10 years elapse, all documents related to the hiring, performance, and termination of that employee must be disposed.</span></span> <span data-ttu-id="b0ab7-112">Händelsen som utlöser kvarhållningsperioden på tio år är att den anställde lämnar organisationen.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-112">The event that triggers the 10-year retention period is the employee leaving the organization.</span></span> 
    
- <span data-ttu-id="b0ab7-113">**Avtal som upphör att gälla** Anta att alla arkivhandlingar som är relaterade till avtal måste behållas i fem år från det att avtalet upphör att gälla.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-113">**Contract expiration** Suppose that all records related to contracts must be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="b0ab7-114">Den händelse som utlöser kvarhållningsperioden på fem år är avtalets upphörande.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-114">The event that triggers the five-year retention period is the expiration of the contract.</span></span> 
    
- <span data-ttu-id="b0ab7-115">**Produktlivslängd** Organisationen kan ha kvarhållningskrav relaterade till senaste tillverkningsdatum för produkter för innehåll som exempelvis tekniska specifikationer.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-115">**Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications.</span></span> <span data-ttu-id="b0ab7-116">I så fall är sista tillverkningsdatum den händelse som utlöser kvarhållningsperioden.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-116">In this case, the last manufacturing date is the event that triggers the retention period.</span></span> 
    
<span data-ttu-id="b0ab7-117">Händelsebaserad kvarhållning används vanligtvis som en del av en process för hantering av arkivhandlingar.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-117">Event-based retention is typically used as part of a records-management process.</span></span> <span data-ttu-id="b0ab7-118">Det innebär följande:</span><span class="sxs-lookup"><span data-stu-id="b0ab7-118">This means that:</span></span>
  
- <span data-ttu-id="b0ab7-119">Kvarhållningsetiketter baserade på händelser markerar vanligtvis också objekt som en post, som en del av en lösning för hantering av arkivhandlingar.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-119">Retention labels based on events also usually mark items as a record, as a part of a records management solution.</span></span> <span data-ttu-id="b0ab7-120">Mer information finns i [Läs mer om hantering av arkivhandlingar](records-management.md).</span><span class="sxs-lookup"><span data-stu-id="b0ab7-120">For more information, see [Learn about records management](records-management.md).</span></span>

- <span data-ttu-id="b0ab7-121">Ett dokument som har deklarerats som en post men vars händelseutlösare ännu inte har inträffat, behålls på obestämd tid (arkivhandlingar kan inte tas bort permanent) förrän en händelse utlöser dokumentets kvarhållningsperiod.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-121">A document that's been declared a record but whose event trigger has not yet happened is retained indefinitely (records can't be permanently deleted), until an event triggers that document's retention period.</span></span>
    
- <span data-ttu-id="b0ab7-122">Kvarhållningsetiketter baserade på händelser utlöser vanligtvis en borttagningsgranskning i slutet av kvarhållningsperioden så att den ansvariga för arkivhandlingar kan granska och förstöra innehållet manuellt.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-122">Retention labels based on events usually trigger a disposition review at the end of the retention period, so that a records manager can manually review and dispose of the content.</span></span> <span data-ttu-id="b0ab7-123">Mer information finns i [Borttagning av innehåll](disposition.md).</span><span class="sxs-lookup"><span data-stu-id="b0ab7-123">For more information, see [Disposition of content](disposition.md).</span></span>
    

<span data-ttu-id="b0ab7-124">En kvarhållningsetikett som är baserad på en händelse har samma funktioner som kvarhållningsetiketter i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-124">A retention label based on an event has the same capabilities as any retention label in Microsoft 365.</span></span> <span data-ttu-id="b0ab7-125">Mer information finns i [Mer information om kvarhållningsprinciper och kvarhållningsetiketter](retention.md).</span><span class="sxs-lookup"><span data-stu-id="b0ab7-125">For more information, see [Learn about retention policies and retention labels](retention.md).</span></span>

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a><span data-ttu-id="b0ab7-126">Förstå förhållandet mellan händelsetyper, etiketter, händelser och tillgångs-ID</span><span class="sxs-lookup"><span data-stu-id="b0ab7-126">Understanding the relationship between event types, labels, events, and asset IDs</span></span>

<span data-ttu-id="b0ab7-127">Om du vill använda händelsebaserad kvarhållning är det viktigt att förstå förhållandet mellan händelsetyper, kvarhållningsetiketter, händelser och tillgångs-ID, som illustreras i diagrammen och den förklaring som följer:</span><span class="sxs-lookup"><span data-stu-id="b0ab7-127">To successfully use event-based retention, it's important to understand the relationship between event types, retention labels, events, and asset IDs as illustrated in the diagrams and the explanation that follows:</span></span> 
  
![Diagram 1 av 2: Händelsetyp, etiketter, händelser och tillgångs-ID](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![Diagram 2 av 2: Händelsetyp, etiketter, händelser och tillgångs-ID](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. <span data-ttu-id="b0ab7-130">Du skapar kvarhållningsetiketter för olika typer av innehåll och kopplar dem sedan till en typ av händelse.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-130">You create retention labels for different types of content and then associate them with a type of event.</span></span> <span data-ttu-id="b0ab7-131">Kvarhållningsetiketter för olika typer av produktfiler och -poster är till exempel kopplade till en händelsetyp som heter Produktlivslängd eftersom de posterna måste behållas i tio år från det att produkten når slutet av produktens livscykel.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-131">For example, retention labels for different types of product files and records are associated with an event type named Product Lifetime because those records must be retained for 10 years from the time the product reaches its end of life.</span></span>
    
2. <span data-ttu-id="b0ab7-132">Användare (vanligtvis personer som hanterar arkivhandlingar) tillämpar dessa kvarhållningsetiketter på innehåll och (för dokument i SharePoint och OneDrive) anger ett tillgångs-ID för varje objekt.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-132">Users (typically records managers) apply those retention labels to content and (for documents in SharePoint and OneDrive) enter an asset ID for each item.</span></span> <span data-ttu-id="b0ab7-133">I det här exemplet är tillgångs-ID ett produktnamn eller en kod som används av organisationen.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-133">In this example, the asset ID is a product name or code used by the organization.</span></span> <span data-ttu-id="b0ab7-134">Varje produkts poster tilldelas sedan en kvarhållningsetikett och varje post har en egenskap som innehåller ett tillgångs-ID.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-134">Then, each product's records are assigned a retention label, and each record has a property that contains an asset ID.</span></span> <span data-ttu-id="b0ab7-135">Diagrammet representerar **allt innehåll** för alla produktposter i en organisation och varje objekt innehar tillgångs-ID:t för produkten som posten hör till.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-135">The diagram represents **all the content** for all product records in an organization, and each item bears the asset ID of the product whose record it is.</span></span> 
    
3. <span data-ttu-id="b0ab7-136">Produktlivslängd är händelsetypen. När en specifik produkt når slutet av livscykeln är det en händelse.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-136">Product Lifetime is the event type; a specific product reaching end of life is an event.</span></span> <span data-ttu-id="b0ab7-137">När en händelse av den händelsetypen inträffar – i det här fallet när en produkt når slutet av sin livslängd – skapar du en händelse som anger:</span><span class="sxs-lookup"><span data-stu-id="b0ab7-137">When an event of that event type occurs—in this case, when a product reaches its end of life—you create an event that specifies:</span></span>
    
   - <span data-ttu-id="b0ab7-138">Ett tillgångs-ID (för SharePoint- och OneDrive-dokument)</span><span class="sxs-lookup"><span data-stu-id="b0ab7-138">An asset ID (for SharePoint and OneDrive documents)</span></span>
    
   - <span data-ttu-id="b0ab7-139">Nyckelord (för Exchange-objekt).</span><span class="sxs-lookup"><span data-stu-id="b0ab7-139">Keywords (for Exchange items).</span></span> <span data-ttu-id="b0ab7-140">I det här exemplet använder organisationen en produktkod i meddelanden som innehåller produktposter, så nyckelordet för Exchange-objekt fungerar på samma sätt som tillgångs-ID:t för SharePoint- och OneDrive-dokument.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-140">In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is functionally the same as the asset ID for SharePoint and OneDrive documents.</span></span>
    
   - <span data-ttu-id="b0ab7-141">Datumet när händelsen inträffade.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-141">The date when the event occurred.</span></span> <span data-ttu-id="b0ab7-142">Det här datumet används som start för kvarhållningsperioden.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-142">This date is used as the start of the retention period.</span></span> <span data-ttu-id="b0ab7-143">Datumet kan vara det aktuella, ett tidigare eller ett framtida datum.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-143">This date can be the current, a past, or a future date.</span></span>

4. <span data-ttu-id="b0ab7-144">När du har skapat en händelse synkroniseras händelsedatumet med allt innehåll som har en kvarhållningsetikett för den händelsetypen och som innehåller det angivna tillgångs-ID:t eller nyckelordet.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-144">After you create an event, that event date is synchronized to all the content that has a retention label of that event type and that contains the specified asset ID or keyword.</span></span> <span data-ttu-id="b0ab7-145">Precis som alla kvarhållningsetiketter kan den här synkroniseringen ta upp till sju dagar.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-145">Like any retention label, this synchronization can take up to seven days.</span></span> <span data-ttu-id="b0ab7-146">I det föregående diagrammet utlöses kvarhållningsperioden av den här händelsen för alla objekt som ringats in i rött.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-146">In the previous diagram, all the items circled in red have their retention period triggered by this event.</span></span> <span data-ttu-id="b0ab7-147">När produkten når slutet av sin livslängd utlöser händelsen med andra ord kvarhållningsperioden för den produktens poster.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-147">In other words, when this product reaches its end of life, that event triggers the retention period for that product's records.</span></span>

<span data-ttu-id="b0ab7-148">Det är viktigt att förstå att om du inte anger ett tillgångs-ID eller nyckelord för en händelse, utlöser händelsen kvarhållningsperioden för **allt innehåll** med en etikett av den händelsetypen.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-148">It's important to understand that if you don't specify an asset ID or keywords for an event, **all content** with a retention label of that event type will have its retention period triggered by the event.</span></span> <span data-ttu-id="b0ab7-149">Det innebär att kvarhållningen för allt innehåll i det föregående diagrammet skulle startas..</span><span class="sxs-lookup"><span data-stu-id="b0ab7-149">This means that in the previous diagram, all content would start being retained.</span></span> <span data-ttu-id="b0ab7-150">Det kanske inte är vad du avsåg.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-150">This might not be what you intend.</span></span>

<span data-ttu-id="b0ab7-151">Slutligen måste du komma ihåg att varje kvarhållningsetikett har egna kvarhållningsinställningar.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-151">Finally, remember that each retention label has its own retention settings.</span></span> <span data-ttu-id="b0ab7-152">I det här exemplet anges alla som tio år, men en händelse kan utlösa kvarhållningsetiketter där varje etikett har olika kvarhållningsperioder.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-152">In this example, they all specify 10 years, but it's possible for an event to trigger retention labels where each label has a different retention period.</span></span>
  
## <a name="how-to-set-up-event-driven-retention"></a><span data-ttu-id="b0ab7-153">Konfigurera händelseutlöst kvarhållning</span><span class="sxs-lookup"><span data-stu-id="b0ab7-153">How to set up event-driven retention</span></span>

<span data-ttu-id="b0ab7-154">Arbetsflöde på hög nivå för händelseberoende kvarhållning:</span><span class="sxs-lookup"><span data-stu-id="b0ab7-154">High-level workflow for event-driven retention:</span></span>
  
![Diagram över arbetsflödet för att konfigurera händelseutlöst kvarhållning](../media/event-based-retention-process.png)
  
> [!TIP]
> <span data-ttu-id="b0ab7-156">I [Hantera livscykeln för dokument som lagras i SharePoint med hjälp av kvarhållningsetiketter](auto-apply-retention-labels-scenario.md) finns ett exempelscenario om hur du använder hanterade egenskaper i SharePoint för att automatiskt tillämpa kvarhållningsetiketter och implementera händelseutlöst kvarhållning.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-156">See [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md) for a detailed scenario about using managed properties in SharePoint to auto-apply retention labels and implement event-driven retention.</span></span>

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a><span data-ttu-id="b0ab7-157">Steg 1: Skapa en etikett vars kvarhållningstid baseras på en händelse.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-157">Step 1: Create a label whose retention period is based on an event</span></span>

<span data-ttu-id="b0ab7-158">Anvisningar för hur du skapar och konfigurerar kvarhållningsetiketter finns i [Skapa kvarhållningsetiketter](./create-apply-retention-labels.md#step-1-create-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="b0ab7-158">To create and configure your retention label, see the instructions for [Create retention labels](./create-apply-retention-labels.md#step-1-create-retention-labels).</span></span> <span data-ttu-id="b0ab7-159">När det gäller händelsebaserad kvarhållning går du till sidan **Definiera kvarhållningsinställningar** i guiden Skapa kvarhållningsetikett. Efter **Starta kvarhållningsperioden baserat på** väljer du någon av standardhändelsetyperna i listrutan eller skapar en egen genom att välja **Skapa ny händelsetyp**:</span><span class="sxs-lookup"><span data-stu-id="b0ab7-159">But specific to event-based retention, on the **Define retention settings** page of the Create retention label wizard, after **Start the retention period based on**, select one of the default event types from the dropdown list, or create your own by selecting **Create new event type**:</span></span>

![Skapa en ny händelsetyp för en kvarhållningsetikett](../media/SPRetention6.png)

<span data-ttu-id="b0ab7-161">En händelsetyp är bara en allmän beskrivning av en händelse som du vill associera med en kvarhållningsetikett.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-161">An event type is simply a general description of an event that you want to associate with a retention label.</span></span>

<span data-ttu-id="b0ab7-162">Standardhändelsetyperna har **(händelsetyp)** efter namnet i listrutan för enklare identifiering, och du kan även visa och skapa händelsetyp från fliken **Hantering av arkivhandlingar** > **Händelser** > **Hantera händelsetyper**.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-162">The default event types have **(event type)** after their name in the dropdown list for easier identification, and you can also see and create event type from the **Records management** > **Events** tab > **Manage event types**.</span></span>

<span data-ttu-id="b0ab7-163">För händelsebaserad kvarhållning krävs inställningar för kvarhållning som:</span><span class="sxs-lookup"><span data-stu-id="b0ab7-163">Event-based retention requires retention settings that:</span></span>
  
- <span data-ttu-id="b0ab7-164">Behåller innehållet.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-164">Retain the content.</span></span>
    
- <span data-ttu-id="b0ab7-165">Tar bort innehållet automatiskt eller utlöser en borttagningsgranskning i slutet av kvarhållningsperioden.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-165">Delete the content automatically or trigger a disposition review at the end of the retention period.</span></span>
  
<span data-ttu-id="b0ab7-166">Händelsebaserad kvarhållning används vanligtvis för innehåll som deklarerar en arkivpost. Det är därför ett bra tillfälle att kontrollera om du även behöver välja det alternativ som markerar innehåll som en [post](records-management.md#records).</span><span class="sxs-lookup"><span data-stu-id="b0ab7-166">Event-based retention is typically used for content that's declared a record, so this is a good time to check whether you also need to select the option that marks content as a [record](records-management.md#records).</span></span>

<span data-ttu-id="b0ab7-167">Om du använder en befintlig händelsetyp i stället för att skapa en ny händelsetyp går du vidare till steg 3.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-167">If you're using an existing event type rather than creating a new event type, skip to step 3.</span></span>

> [!NOTE]
> <span data-ttu-id="b0ab7-168">När du väljer en händelsetyp och sparar kvarhållningsetiketten kan händelsetypen inte ändras.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-168">After you choose an event type and save the retention label, the event type cannot be changed.</span></span>

### <a name="step-2-create-a-new-event-type-for-your-label"></a><span data-ttu-id="b0ab7-169">Steg 2: Skapa en ny händelsetyp för en kvarhållningsetikett</span><span class="sxs-lookup"><span data-stu-id="b0ab7-169">Step 2: Create a new event type for your label</span></span>

<span data-ttu-id="b0ab7-170">Om du har valt **Skapa ny händelsetyp** anger du ett namn och en beskrivning för kvarhållningsinställningarna.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-170">For the retention settings, if you selected **Create new event type**, enter a name and description for your event type.</span></span> <span data-ttu-id="b0ab7-171">Välj sedan **Nästa**, **Skicka** och **Klart**.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-171">Then select **Next**, **Submit**, and **Done**.</span></span>

<span data-ttu-id="b0ab7-172">Tillbaka på sidan **Definiera kvarhållningsinställningar** väljer du händelsetypen som du skapade i listrutan i **Starta kvarhållningsperioden baserat på**.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-172">Back on the **Define retention settings** page, for **Start the retention period based on**, use the dropdown list to select the event type that you created.</span></span>

  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a><span data-ttu-id="b0ab7-173">Steg 3: Publicera eller tillämpa de händelsebaserade kvarhållningsetiketterna automatiskt</span><span class="sxs-lookup"><span data-stu-id="b0ab7-173">Step 3: Publish or auto-apply the event-based retention labels</span></span>

<span data-ttu-id="b0ab7-174">Precis som för alla kvarhållningsetiketter måste du publicera eller tillämpa en händelsebaserad etikett automatiskt för att den ska kunna användas manuellt eller automatiskt på innehåll:</span><span class="sxs-lookup"><span data-stu-id="b0ab7-174">Just like any retention label, you need to publish or auto-apply an event-based label, for it to be manually or automatically applied to content:</span></span>
- [<span data-ttu-id="b0ab7-175">Skapa kvarhållningsetiketter och använda dem i appar</span><span class="sxs-lookup"><span data-stu-id="b0ab7-175">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="b0ab7-176">Använda en kvarhållningsetikett på innehåll automatiskt</span><span class="sxs-lookup"><span data-stu-id="b0ab7-176">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

### <a name="step-4-enter-an-asset-id"></a><span data-ttu-id="b0ab7-177">Steg 4: Ange ett tillgångs-ID</span><span class="sxs-lookup"><span data-stu-id="b0ab7-177">Step 4: Enter an asset ID</span></span>

<span data-ttu-id="b0ab7-178">När en händelsebaserad etikett används på innehåll kan du ange ett tillgångs-ID för varje objekt.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-178">After an event-based label is applied to content, you can enter an asset ID for each item.</span></span> <span data-ttu-id="b0ab7-179">Din organisation kan till exempel använda:</span><span class="sxs-lookup"><span data-stu-id="b0ab7-179">For example, your organization might use:</span></span>
  
- <span data-ttu-id="b0ab7-180">Produktkoder som du kan använda för att hålla kvar innehåll för endast en specifik produkt.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-180">Product codes that you can use to retain content for only a specific product.</span></span>
    
- <span data-ttu-id="b0ab7-181">Projektkoder som du kan använda för att hålla kvar innehåll för endast ett specifikt projekt.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-181">Project codes that you can use to retain content for only a specific project.</span></span>
    
- <span data-ttu-id="b0ab7-182">Anställnings-ID:n som du kan använda för att hålla kvar innehåll för endast en specifik person.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-182">Employee IDs that you can use to retain content for only a specific person.</span></span>
    
<span data-ttu-id="b0ab7-183">Tillgångs-ID är bara ytterligare en dokumentegenskap som är tillgänglig i SharePoint och OneDrive.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-183">Asset ID is simply another document property that's available in SharePoint and OneDrive.</span></span> <span data-ttu-id="b0ab7-184">Organisationen kanske redan använder andra dokumentegenskaper och ID:n för att klassificera innehåll.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-184">Your organization might already use other document properties and IDs to classify content.</span></span> <span data-ttu-id="b0ab7-185">I så fall kan du även använda de egenskaperna och värdena när du skapar en händelse – se steg 6 som följer.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-185">If so, you can also use those properties and values when you create an event—see step 6 that follows.</span></span> <span data-ttu-id="b0ab7-186">Det viktiga är att du måste använda en *egenskap:värde*-kombination i dokumentegenskaperna för att associera objektet med en händelsetyp.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-186">The important point is that you must use some *property:value* combination in the document properties to associate that item with an event type.</span></span>
  
![Textruta för att ange ett tillgångs-ID](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a><span data-ttu-id="b0ab7-188">Steg 5: Skapa en händelse</span><span class="sxs-lookup"><span data-stu-id="b0ab7-188">Step 5: Create an event</span></span>

<span data-ttu-id="b0ab7-189">När en viss instans av den händelsetypen inträffar, till exempel när en produkt når slutet av sin livslängd, går du till sidan **Hantering av arkivhandlingar** > **Händelser** i efterlevnadscentret för Microsoft 365 och väljer **+ Skapa** för att skapa en händelse.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-189">When a particular instance of that event type occurs, such as a product reaches its end of life, go to the **Records management** > **Events** page in the Microsoft 365 compliance center, and select **+ Create** to create an event.</span></span> <span data-ttu-id="b0ab7-190">Du utlöser händelsen genom att skapa den här.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-190">You trigger the event by creating it, here.</span></span>

![Skapa en händelse för att utlösa start av kvarhållningsperioden för händelsebaserade kvarhållningsetiketter](../media/create-event-records-management.png)

<span data-ttu-id="b0ab7-192">Upp till en miljon händelser stöds per klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-192">Up to one million events are supported per tenant.</span></span>

### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a><span data-ttu-id="b0ab7-193">Steg 6: Välj samma händelsetyp som används av etiketten i steg 2</span><span class="sxs-lookup"><span data-stu-id="b0ab7-193">Step 6: Choose the same event type used by the label in step 2</span></span>

<span data-ttu-id="b0ab7-194">När du skapar händelsen väljer du samma händelsetyp som anges i inställningarna för kvarhållningsetiketten i steg 2.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-194">When you create the event, choose the same event type specified in the retention label settings in step 2.</span></span> <span data-ttu-id="b0ab7-195">Om du till exempel valde **Produktlivslängd** som händelsetyp för etikettinställningarna väljer du **Produktlivslängd** när du skapar händelsen.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-195">For example, if you selected **Product Lifetime** as your event type for the label settings, select **Product Lifetime** when you create the event.</span></span> <span data-ttu-id="b0ab7-196">Kvarhållningsperioden utlöses bara för innehåll med kvarhållningsetiketter av den händelsetypen.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-196">Only content with retention labels applied to it of that event type will have its retention period triggered.</span></span>

![Alternativ i Händelseinställningar för att välja en händelsetyp](../media/choose-event-type-records-management.png)

<span data-ttu-id="b0ab7-198">Om du behöver skapa en händelse för flera kvarhållningsetiketter som har olika händelsetyper väljer du alternativet **Välj befintliga etiketter**.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-198">Alternatively, if you need to create an event for multiple retention labels that have different event types, select the **Choose Existing Labels** option.</span></span> <span data-ttu-id="b0ab7-199">Välj sedan de etiketter som är konfigurerade för de händelsetyper som du vill associera med händelsen.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-199">Then, select the labels that are configured for the event types you want to associate with this event.</span></span>

### <a name="step-7-enter-keywords-or-an-asset-id"></a><span data-ttu-id="b0ab7-200">Steg 7: Ange nyckelord eller ett tillgångs-ID</span><span class="sxs-lookup"><span data-stu-id="b0ab7-200">Step 7: Enter keywords or an asset ID</span></span>

<span data-ttu-id="b0ab7-201">Nu kan du begränsa innehållets omfång genom att ange tillgångs-ID:n för SharePoint- och OneDrive-innehåll, eller nyckelord för Exchange-innehåll.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-201">Now you narrow the scope of the content by specifying asset IDs for SharePoint and OneDrive content, or keywords for Exchange content.</span></span> <span data-ttu-id="b0ab7-202">För tillgångs-ID:n kommer kvarhållning endast att tillämpas på innehåll med angiven kombination av *egenskap:värde*.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-202">For asset IDs, retention will be enforced only on content with the specified *property:value* pair.</span></span> <span data-ttu-id="b0ab7-203">Om ett tillgångs-ID inte anges får allt innehåll med etiketter av den händelsetypen samma kvarhållningsdatum.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-203">If an asset ID is not entered, all content with labels of that event type get the same retention date applied to them.</span></span>

<span data-ttu-id="b0ab7-204">Om du till exempel använder egenskapen tillgångs-ID anger du `ComplianceAssetID:<value>` i rutan för tillgångs-ID:n som visas nedan.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-204">For example: If you're using the Asset ID property, enter `ComplianceAssetID:<value>` in the box for asset IDs shown below.</span></span>
  
<span data-ttu-id="b0ab7-205">Din organisation kan ha använt andra egenskaper och ID:n för dokument relaterade till den här händelsetypen.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-205">Your organization might have applied other properties and IDs to the documents related to this event type.</span></span> <span data-ttu-id="b0ab7-206">Om du till exempel behöver identifiera en specifik produkts poster kan ID:t vara en kombination av ditt anpassade produkt-ID och värdet ”XYZ”.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-206">For example, if you need to detect a specific product's records, the ID might be a combination of your custom property ProductID and the value "XYZ".</span></span> <span data-ttu-id="b0ab7-207">I det här fallet anger du `ProductID:XYZ` i rutan för tillgångs-ID:n som visas i följande bild.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-207">In this case, you'd enter `ProductID:XYZ` in the box for asset IDs shown in the following picture.</span></span>
  
<span data-ttu-id="b0ab7-208">För Exchange-objekt använder du nyckelord.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-208">For Exchange items, use keywords.</span></span> <span data-ttu-id="b0ab7-209">Du kan använda en fråga med hjälp av sökoperatorer som AND, OR och NOT (OCH, ELLER och INTE).</span><span class="sxs-lookup"><span data-stu-id="b0ab7-209">You can use a query by using search operators such as AND, OR, and NOT.</span></span> <span data-ttu-id="b0ab7-210">Mer information finns i [Nyckelordsfrågor och sökvillkor för innehållssökning](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="b0ab7-210">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="b0ab7-211">Välj slutligen datumet då händelsen inträffade. Det här datumet används som start för kvarhållningsperioden.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-211">Finally, choose the date when the event occurred; this date is used as the start of the retention period.</span></span> <span data-ttu-id="b0ab7-212">När du har skapat en händelse synkroniseras händelsedatumet med allt innehåll med en kvarhållningsetikett för den händelsetypen, tillgångs-ID:t och nyckelorden.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-212">After you create an event, that event date is synchronized to all the content with a retention label of that event type, asset ID, and keywords.</span></span> <span data-ttu-id="b0ab7-213">Precis som för alla kvarhållningsetiketter kan den här synkroniseringen ta upp till sju dagar.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-213">As with any retention label, this synchronization can take up to seven days.</span></span>
  
![Sidan Händelseinställningar](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)

<span data-ttu-id="b0ab7-215">När en händelse har skapats används kvarhållningsinställningarna för innehåll som redan har etiketter och indexerats.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-215">After creating an event, the retention settings take effect for the content that's already labeled and indexed.</span></span> <span data-ttu-id="b0ab7-216">Om kvarhållningsetiketten läggs till i nytt innehåll efter det att händelsen har skapats måste du skapa en ny händelse med samma information.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-216">If the retention label is added to new content after the event is created, you must create a new event with the same details.</span></span>

<span data-ttu-id="b0ab7-217">När en händelse tas bort avbryts inte kvarhållningsinställningarna som nu tillämpas för innehåll som redan har etiketter.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-217">Deleting an event doesn't cancel the retention settings that are now in effect for the content that's already labeled.</span></span> <span data-ttu-id="b0ab7-218">Det gör du genom att skapa en ny händelse med samma information, men lämna datumet tomt.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-218">To do that, create a new event with the same details, but leave the date blank.</span></span> 

## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a><span data-ttu-id="b0ab7-219">Använda innehållssökning för att hitta allt innehåll med en viss etikett eller ett visst tillgångs-ID</span><span class="sxs-lookup"><span data-stu-id="b0ab7-219">Use Content Search to find all content with a specific label or asset ID</span></span>

<span data-ttu-id="b0ab7-220">När kvarhållningsetiketter har tilldelats till innehåll kan du använda innehållssökning för att hitta allt innehåll som klassificeras med en specifik kvarhållningsetikett eller som innehåller ett specifikt tillgångs-ID:</span><span class="sxs-lookup"><span data-stu-id="b0ab7-220">After retention labels are assigned to content, you can use content search to find all content that's classified with a specific retention label or that contains a specific asset ID:</span></span>
  
- <span data-ttu-id="b0ab7-221">Om du vill söka efter allt innehåll med en specifik kvarhållningsetikett väljer du villkoret **Kvarhållningsetikett** och anger sedan hela etikettnamnet eller en del av det och använder ett jokertecken.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-221">To find all content with a specific retention label, choose the **Retention label** condition, and then enter the complete label name or part of the label name and use a wildcard.</span></span> 
    
- <span data-ttu-id="b0ab7-222">Om du vill hitta allt innehåll med ett specifikt tillgångs-ID anger du egenskapen **ComplianceAssetID** och ett värde med hjälp av formatet `ComplianceAssetID:<value>`.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-222">To find all content with a specific asset ID, enter the **ComplianceAssetID** property and a value, using the format `ComplianceAssetID:<value>`.</span></span> 
    
<span data-ttu-id="b0ab7-223">Mer information finns i [Nyckelordsfrågor och sökvillkor för innehållssökning](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="b0ab7-223">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>

## <a name="automate-events-by-using-powershell"></a><span data-ttu-id="b0ab7-224">Automatisera händelser med hjälp av PowerShell</span><span class="sxs-lookup"><span data-stu-id="b0ab7-224">Automate events by using PowerShell</span></span>

<span data-ttu-id="b0ab7-225">Du kan använda ett PowerShell-skript för att automatisera händelsebaserad kvarhållning från dina affärsprogram.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-225">You can use a PowerShell script to automate event-based retention from your business applications.</span></span> <span data-ttu-id="b0ab7-226">PowerShell-cmdletarna som är tillgängliga för händelsebaserad kvarhållning:</span><span class="sxs-lookup"><span data-stu-id="b0ab7-226">The PowerShell cmdlets available for event-based retention:</span></span>
  
- [<span data-ttu-id="b0ab7-227">Get-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="b0ab7-227">Get-ComplianceRetentionEventType</span></span>](/powershell/module/exchange/get-complianceretentioneventtype)
    
- [<span data-ttu-id="b0ab7-228">New-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="b0ab7-228">New-ComplianceRetentionEventType</span></span>](/powershell/module/exchange/new-complianceretentioneventtype)
    
- [<span data-ttu-id="b0ab7-229">Remove-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="b0ab7-229">Remove-ComplianceRetentionEventType</span></span>](/powershell/module/exchange/remove-complianceretentioneventtype)
    
- [<span data-ttu-id="b0ab7-230">Set-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="b0ab7-230">Set-ComplianceRetentionEventType</span></span>](/powershell/module/exchange/set-complianceretentioneventtype)
    
- [<span data-ttu-id="b0ab7-231">Get-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="b0ab7-231">Get-ComplianceRetentionEvent</span></span>](/powershell/module/exchange/get-complianceretentionevent)
    
- [<span data-ttu-id="b0ab7-232">New-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="b0ab7-232">New-ComplianceRetentionEvent</span></span>](/powershell/module/exchange/new-complianceretentionevent)
    

## <a name="automate-events-by-using-a-rest-api"></a><span data-ttu-id="b0ab7-233">Automatisera händelser med hjälp av ett REST-API</span><span class="sxs-lookup"><span data-stu-id="b0ab7-233">Automate events by using a REST API</span></span>

<span data-ttu-id="b0ab7-234">Du kan använda ett REST-API för att automatiskt skapa händelser som utlöser starten av kvarhållningsperioden.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-234">You can use a REST API to automatically create the events that trigger the start of the retention time.</span></span>

<span data-ttu-id="b0ab7-235">Ett REST-API är en tjänsteslutpunkt som stöder uppsättningar av HTTP-åtgärder (metoder), som ger åtkomst till tjänstens resurser för att skapa/hämta/uppdatera/ta bort.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-235">A REST API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources.</span></span> <span data-ttu-id="b0ab7-236">Mer information finns i [Komponenter i en REST-API-begäran/ett REST-API-svar](/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span><span class="sxs-lookup"><span data-stu-id="b0ab7-236">For more information, see [Components of a REST API request/response](/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span></span> <span data-ttu-id="b0ab7-237">Med hjälp av REST-API för Microsoft 365 kan händelser skapas och hämtas med hjälp av metoderna POST och GET.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-237">By using the Microsoft 365 REST API, events can be created and retrieved using the POST and GET methods.</span></span>

<span data-ttu-id="b0ab7-238">Det finns två alternativ för att använda REST-API:</span><span class="sxs-lookup"><span data-stu-id="b0ab7-238">There are two options for using the REST API:</span></span>

- <span data-ttu-id="b0ab7-239">**Microsoft Power Automate eller ett liknande program** för att utlösa förekomsten av en händelse automatiskt.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-239">**Microsoft Power Automate or a similar application** to trigger the occurrence of an event automatically.</span></span> <span data-ttu-id="b0ab7-240">Microsoft Power Automate är en orkestrator för anslutning till andra system, så du behöver inte skriva en anpassad lösning.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-240">Microsoft Power Automate is an orchestrator for connecting to other systems, so you don't need to write a custom solution.</span></span> <span data-ttu-id="b0ab7-241">Mer information finns på [webbplatsen Power Automate](https://flow.microsoft.com/sv-SE/).</span><span class="sxs-lookup"><span data-stu-id="b0ab7-241">For more information, see the [Power Automate website](https://flow.microsoft.com/sv-SE/).</span></span>

- <span data-ttu-id="b0ab7-242">**PowerShell eller en HTTP-klient för att anropa REST-API** för att skapa händelser med hjälp av PowerShell (version 6 eller senare), som är en del av en anpassad lösning.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-242">**PowerShell or an HTTP client to call the REST API** to create events by using PowerShell (version 6 or later), which is part of a custom solution.</span></span>

<span data-ttu-id="b0ab7-243">Innan du använder REST-API, som global administratör, bekräftar du URL-adressen som ska användas för kvarhållningshändelseanrop.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-243">Before you use the REST API, as a global administrator, confirm the URL to use for the retention event call.</span></span> <span data-ttu-id="b0ab7-244">Det gör du genom att köra ett GET-anrop för kvarhållningshändelse med hjälp av REST-API-URL:en:</span><span class="sxs-lookup"><span data-stu-id="b0ab7-244">To do this, run a GET retention event call by using the REST API URL:</span></span>

```http
https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent
```

<span data-ttu-id="b0ab7-245">Kontrollera svarskoden.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-245">Check the response code.</span></span> <span data-ttu-id="b0ab7-246">Om den är 302 hämtar du den omdirigerade URL-adressen från egenskapen Plats för svarshuvudet och använder den URL-adressen i stället för `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent` i anvisningarna nedan.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-246">If it's 302, get the redirected URL from the Location property of the response header and use that URL instead of `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent` in the instructions that follow.</span></span>

<span data-ttu-id="b0ab7-247">Händelser som skapas automatiskt kan bekräftas genom att de visas i Efterlevnadscenter för Microsoft 365 > **Hantering av arkivhandlingar** >  **Händelser**.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-247">The events that get automatically created can be confirmed by viewing them in the Microsoft 365 compliance center > **Records management** >  **Events**.</span></span>

### <a name="use-microsoft-power-automate-to-create-the-event"></a><span data-ttu-id="b0ab7-248">Använda Microsoft Power Automate för att skapa händelsen</span><span class="sxs-lookup"><span data-stu-id="b0ab7-248">Use Microsoft Power Automate to create the event</span></span>

<span data-ttu-id="b0ab7-249">Skapa ett flöde som skapar en händelse med hjälp av REST-API för Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="b0ab7-249">Create a flow that creates an event using the Microsoft 365 REST API:</span></span>

![Använda Flow för att skapa en händelse](../media/automate-event-driven-retention-flow-1.png)

![Använda Flow för att anropa REST-API](../media/automate-event-driven-retention-flow-2.png)

#### <a name="create-an-event"></a><span data-ttu-id="b0ab7-252">Skapa en händelse</span><span class="sxs-lookup"><span data-stu-id="b0ab7-252">Create an event</span></span>

<span data-ttu-id="b0ab7-253">Exempelkod som anropar REST API:et:</span><span class="sxs-lookup"><span data-stu-id="b0ab7-253">Sample code to call the REST API:</span></span>

- <span data-ttu-id="b0ab7-254">**Method**: POST</span><span class="sxs-lookup"><span data-stu-id="b0ab7-254">**Method**: POST</span></span>
- <span data-ttu-id="b0ab7-255">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="b0ab7-255">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>
- <span data-ttu-id="b0ab7-256">**Headers**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="b0ab7-256">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>
- <span data-ttu-id="b0ab7-257">**Body**:</span><span class="sxs-lookup"><span data-stu-id="b0ab7-257">**Body**:</span></span>
    
    ```xml
    <?xml version='1.0' encoding='utf-8' standalone='yes'?>
    
    <entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'
    
    xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'
    
    xmlns='http://www.w3.org/2005/Atom'>
    
    <category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />
    
    <updated>9/9/2017 10:50:00 PM</updated>
    
    <content type='application/xml'>
    
    <m:properties>
    
    <d:Name>Employee Termination </d:Name>
    
    <d:EventType>99e0ae64-a4b8-40bb-82ed-645895610f56</d:EventType>
    
    <d:SharePointAssetIdQuery>1234</d:SharePointAssetIdQuery>
    
    <d:EventDateTime>2018-12-01T00:00:00Z </d:EventDateTime>
    
    </m:properties>
    
    </content>
    
    </entry>
    ```
    
- <span data-ttu-id="b0ab7-258">**Authentication**: Basic</span><span class="sxs-lookup"><span data-stu-id="b0ab7-258">**Authentication**: Basic</span></span>
- <span data-ttu-id="b0ab7-259">**Username**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="b0ab7-259">**Username**: "Complianceuser"</span></span>
- <span data-ttu-id="b0ab7-260">**Password**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="b0ab7-260">**Password**: "Compliancepassword"</span></span>


##### <a name="available-parameters"></a><span data-ttu-id="b0ab7-261">Tillgängliga parametrar</span><span class="sxs-lookup"><span data-stu-id="b0ab7-261">Available parameters</span></span>


|<span data-ttu-id="b0ab7-262">Parametrar</span><span class="sxs-lookup"><span data-stu-id="b0ab7-262">Parameters</span></span>|<span data-ttu-id="b0ab7-263">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b0ab7-263">Description</span></span>|<span data-ttu-id="b0ab7-264">Kommentar</span><span class="sxs-lookup"><span data-stu-id="b0ab7-264">Notes</span></span>|
|--- |--- |--- |
|<span data-ttu-id="b0ab7-265"><d:Name></d:Name></span><span class="sxs-lookup"><span data-stu-id="b0ab7-265"><d:Name></d:Name></span></span>|<span data-ttu-id="b0ab7-266">Ange ett unikt namn för händelsen</span><span class="sxs-lookup"><span data-stu-id="b0ab7-266">Provide a unique name for the event,</span></span>|<span data-ttu-id="b0ab7-267">Får inte innehålla avslutande blanksteg eller följande tecken: % \* \ & < \> \| # ?</span><span class="sxs-lookup"><span data-stu-id="b0ab7-267">Cannot contain trailing spaces or the following characters: % \* \ & < \> \| # ?</span></span> <span data-ttu-id="b0ab7-268">, : ;</span><span class="sxs-lookup"><span data-stu-id="b0ab7-268">, : ;</span></span>|
|<span data-ttu-id="b0ab7-269"><d:EventType></d:EventType></span><span class="sxs-lookup"><span data-stu-id="b0ab7-269"><d:EventType></d:EventType></span></span>|<span data-ttu-id="b0ab7-270">Ange namn på händelsetyp (eller GUID),</span><span class="sxs-lookup"><span data-stu-id="b0ab7-270">Enter event type name (or Guid),</span></span>|<span data-ttu-id="b0ab7-271">Exempel: ”Anställds uppsägning”.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-271">Example: "Employee termination".</span></span> <span data-ttu-id="b0ab7-272">Händelsetypen måste associeras med en kvarhållningsetikett.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-272">Event type has to be associated with a retention label.</span></span>|
|<span data-ttu-id="b0ab7-273"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span><span class="sxs-lookup"><span data-stu-id="b0ab7-273"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span></span>|<span data-ttu-id="b0ab7-274">Ange "ComplianceAssetId:" + anställnings-ID</span><span class="sxs-lookup"><span data-stu-id="b0ab7-274">Enter "ComplianceAssetId:" + employee ID</span></span>|<span data-ttu-id="b0ab7-275">Exempel: "ComplianceAssetId:12345"</span><span class="sxs-lookup"><span data-stu-id="b0ab7-275">Example: "ComplianceAssetId:12345"</span></span>|
|<span data-ttu-id="b0ab7-276"><d:EventDateTime></d:EventDateTime></span><span class="sxs-lookup"><span data-stu-id="b0ab7-276"><d:EventDateTime></d:EventDateTime></span></span>|<span data-ttu-id="b0ab7-277">Datum och tid för händelse</span><span class="sxs-lookup"><span data-stu-id="b0ab7-277">Event Date and Time</span></span>|<span data-ttu-id="b0ab7-278">Format: åååå-MM-ddTHH:mm:ssZ, Exempel: 2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="b0ab7-278">Format: yyyy-MM-ddTHH:mm:ssZ, Example: 2018-12-01T00:00:00Z</span></span>
|

###### <a name="response-codes"></a><span data-ttu-id="b0ab7-279">Svarskoder</span><span class="sxs-lookup"><span data-stu-id="b0ab7-279">Response codes</span></span>

| <span data-ttu-id="b0ab7-280">Svarskod</span><span class="sxs-lookup"><span data-stu-id="b0ab7-280">Response Code</span></span> | <span data-ttu-id="b0ab7-281">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b0ab7-281">Description</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="b0ab7-282">302</span><span class="sxs-lookup"><span data-stu-id="b0ab7-282">302</span></span>               | <span data-ttu-id="b0ab7-283">Omdirigera</span><span class="sxs-lookup"><span data-stu-id="b0ab7-283">Redirect</span></span>              |
| <span data-ttu-id="b0ab7-284">201</span><span class="sxs-lookup"><span data-stu-id="b0ab7-284">201</span></span>               | <span data-ttu-id="b0ab7-285">Skapades</span><span class="sxs-lookup"><span data-stu-id="b0ab7-285">Created</span></span>               |
| <span data-ttu-id="b0ab7-286">403</span><span class="sxs-lookup"><span data-stu-id="b0ab7-286">403</span></span>               | <span data-ttu-id="b0ab7-287">Auktorisering misslyckades</span><span class="sxs-lookup"><span data-stu-id="b0ab7-287">Authorization Failed</span></span>  |
| <span data-ttu-id="b0ab7-288">401</span><span class="sxs-lookup"><span data-stu-id="b0ab7-288">401</span></span>               | <span data-ttu-id="b0ab7-289">Autentisering misslyckades</span><span class="sxs-lookup"><span data-stu-id="b0ab7-289">Authentication Failed</span></span> |

##### <a name="get-events-based-on-a-time-range"></a><span data-ttu-id="b0ab7-290">Hämta händelser baserat på ett tidsintervall</span><span class="sxs-lookup"><span data-stu-id="b0ab7-290">Get events based on a time range</span></span>

- <span data-ttu-id="b0ab7-291">**Method**: GET</span><span class="sxs-lookup"><span data-stu-id="b0ab7-291">**Method**: GET</span></span>

- <span data-ttu-id="b0ab7-292">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span><span class="sxs-lookup"><span data-stu-id="b0ab7-292">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span></span>

- <span data-ttu-id="b0ab7-293">**Headers**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="b0ab7-293">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="b0ab7-294">**Authentication**: Basic</span><span class="sxs-lookup"><span data-stu-id="b0ab7-294">**Authentication**: Basic</span></span>

- <span data-ttu-id="b0ab7-295">**Username**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="b0ab7-295">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="b0ab7-296">**Password**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="b0ab7-296">**Password**: "Compliancepassword"</span></span>


###### <a name="response-codes"></a><span data-ttu-id="b0ab7-297">Svarskoder</span><span class="sxs-lookup"><span data-stu-id="b0ab7-297">Response codes</span></span>

| <span data-ttu-id="b0ab7-298">Svarskod</span><span class="sxs-lookup"><span data-stu-id="b0ab7-298">Response Code</span></span> | <span data-ttu-id="b0ab7-299">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b0ab7-299">Description</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="b0ab7-300">200</span><span class="sxs-lookup"><span data-stu-id="b0ab7-300">200</span></span>               | <span data-ttu-id="b0ab7-301">OK, en lista över händelser i atom+ xml</span><span class="sxs-lookup"><span data-stu-id="b0ab7-301">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="b0ab7-302">404</span><span class="sxs-lookup"><span data-stu-id="b0ab7-302">404</span></span>               | <span data-ttu-id="b0ab7-303">Hittades inte</span><span class="sxs-lookup"><span data-stu-id="b0ab7-303">Not found</span></span>                         |
| <span data-ttu-id="b0ab7-304">302</span><span class="sxs-lookup"><span data-stu-id="b0ab7-304">302</span></span>               | <span data-ttu-id="b0ab7-305">Omdirigera</span><span class="sxs-lookup"><span data-stu-id="b0ab7-305">Redirect</span></span>                          |
| <span data-ttu-id="b0ab7-306">401</span><span class="sxs-lookup"><span data-stu-id="b0ab7-306">401</span></span>               | <span data-ttu-id="b0ab7-307">Auktorisering misslyckades</span><span class="sxs-lookup"><span data-stu-id="b0ab7-307">Authorization Failed</span></span>              |
| <span data-ttu-id="b0ab7-308">403</span><span class="sxs-lookup"><span data-stu-id="b0ab7-308">403</span></span>               | <span data-ttu-id="b0ab7-309">Autentisering misslyckades</span><span class="sxs-lookup"><span data-stu-id="b0ab7-309">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="b0ab7-310">Hämta en händelse med hjälp av ID</span><span class="sxs-lookup"><span data-stu-id="b0ab7-310">Get an event by ID</span></span>

- <span data-ttu-id="b0ab7-311">**Method**: GET</span><span class="sxs-lookup"><span data-stu-id="b0ab7-311">**Method**: GET</span></span>

- <span data-ttu-id="b0ab7-312">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span><span class="sxs-lookup"><span data-stu-id="b0ab7-312">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span></span>

- <span data-ttu-id="b0ab7-313">**Headers**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="b0ab7-313">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="b0ab7-314">**Authentication**: Basic</span><span class="sxs-lookup"><span data-stu-id="b0ab7-314">**Authentication**: Basic</span></span>

- <span data-ttu-id="b0ab7-315">**Username**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="b0ab7-315">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="b0ab7-316">**Password**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="b0ab7-316">**Password**: "Compliancepassword"</span></span>

###### <a name="response-codes"></a><span data-ttu-id="b0ab7-317">Svarskoder</span><span class="sxs-lookup"><span data-stu-id="b0ab7-317">Response codes</span></span>

| <span data-ttu-id="b0ab7-318">Svarskod</span><span class="sxs-lookup"><span data-stu-id="b0ab7-318">Response Code</span></span> | <span data-ttu-id="b0ab7-319">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b0ab7-319">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="b0ab7-320">200</span><span class="sxs-lookup"><span data-stu-id="b0ab7-320">200</span></span>               | <span data-ttu-id="b0ab7-321">OK, svarets brödtext innehåller händelsen i atom+xml</span><span class="sxs-lookup"><span data-stu-id="b0ab7-321">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="b0ab7-322">404</span><span class="sxs-lookup"><span data-stu-id="b0ab7-322">404</span></span>               | <span data-ttu-id="b0ab7-323">Hittades inte</span><span class="sxs-lookup"><span data-stu-id="b0ab7-323">Not found</span></span>                                            |
| <span data-ttu-id="b0ab7-324">302</span><span class="sxs-lookup"><span data-stu-id="b0ab7-324">302</span></span>               | <span data-ttu-id="b0ab7-325">Omdirigera</span><span class="sxs-lookup"><span data-stu-id="b0ab7-325">Redirect</span></span>                                             |
| <span data-ttu-id="b0ab7-326">401</span><span class="sxs-lookup"><span data-stu-id="b0ab7-326">401</span></span>               | <span data-ttu-id="b0ab7-327">Auktorisering misslyckades</span><span class="sxs-lookup"><span data-stu-id="b0ab7-327">Authorization Failed</span></span>                                 |
| <span data-ttu-id="b0ab7-328">403</span><span class="sxs-lookup"><span data-stu-id="b0ab7-328">403</span></span>               | <span data-ttu-id="b0ab7-329">Autentisering misslyckades</span><span class="sxs-lookup"><span data-stu-id="b0ab7-329">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="b0ab7-330">Hämta en händelse med hjälp av namnet</span><span class="sxs-lookup"><span data-stu-id="b0ab7-330">Get an event by name</span></span>

- <span data-ttu-id="b0ab7-331">**Method**: GET</span><span class="sxs-lookup"><span data-stu-id="b0ab7-331">**Method**: GET</span></span>

- <span data-ttu-id="b0ab7-332">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="b0ab7-332">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>

- <span data-ttu-id="b0ab7-333">**Headers**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="b0ab7-333">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="b0ab7-334">**Authentication**: Basic</span><span class="sxs-lookup"><span data-stu-id="b0ab7-334">**Authentication**: Basic</span></span>

- <span data-ttu-id="b0ab7-335">**Username**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="b0ab7-335">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="b0ab7-336">**Password**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="b0ab7-336">**Password**: "Compliancepassword"</span></span>


###### <a name="response-codes"></a><span data-ttu-id="b0ab7-337">Svarskoder</span><span class="sxs-lookup"><span data-stu-id="b0ab7-337">Response codes</span></span>

| <span data-ttu-id="b0ab7-338">Svarskod</span><span class="sxs-lookup"><span data-stu-id="b0ab7-338">Response Code</span></span> | <span data-ttu-id="b0ab7-339">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b0ab7-339">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="b0ab7-340">200</span><span class="sxs-lookup"><span data-stu-id="b0ab7-340">200</span></span>               | <span data-ttu-id="b0ab7-341">OK, svarets brödtext innehåller händelsen i atom+xml</span><span class="sxs-lookup"><span data-stu-id="b0ab7-341">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="b0ab7-342">404</span><span class="sxs-lookup"><span data-stu-id="b0ab7-342">404</span></span>               | <span data-ttu-id="b0ab7-343">Hittades inte</span><span class="sxs-lookup"><span data-stu-id="b0ab7-343">Not found</span></span>                                            |
| <span data-ttu-id="b0ab7-344">302</span><span class="sxs-lookup"><span data-stu-id="b0ab7-344">302</span></span>               | <span data-ttu-id="b0ab7-345">Omdirigera</span><span class="sxs-lookup"><span data-stu-id="b0ab7-345">Redirect</span></span>                                             |
| <span data-ttu-id="b0ab7-346">401</span><span class="sxs-lookup"><span data-stu-id="b0ab7-346">401</span></span>               | <span data-ttu-id="b0ab7-347">Auktorisering misslyckades</span><span class="sxs-lookup"><span data-stu-id="b0ab7-347">Authorization Failed</span></span>                                 |
| <span data-ttu-id="b0ab7-348">403</span><span class="sxs-lookup"><span data-stu-id="b0ab7-348">403</span></span>               | <span data-ttu-id="b0ab7-349">Autentisering misslyckades</span><span class="sxs-lookup"><span data-stu-id="b0ab7-349">Authentication Failed</span></span>                                |

### <a name="use-powershell-or-any-http-client-to-create-the-event"></a><span data-ttu-id="b0ab7-350">Använda PowerShell eller någon HTTP-klient för att skapa händelsen</span><span class="sxs-lookup"><span data-stu-id="b0ab7-350">Use PowerShell or any HTTP client to create the event</span></span>

<span data-ttu-id="b0ab7-351">PowerShell måste vara version 6 eller senare.</span><span class="sxs-lookup"><span data-stu-id="b0ab7-351">PowerShell must be version 6 or later.</span></span>

<span data-ttu-id="b0ab7-352">Kör följande skript i en PowerShell-session:</span><span class="sxs-lookup"><span data-stu-id="b0ab7-352">In a PowerShell session, run the following script:</span></span>

```powershell
param([string]$baseUri)

$userName = "UserName"

$password = "Password"

$securePassword = ConvertTo-SecureString $password -AsPlainText -Force

$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)

$EventName="EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))"

Write-Host "Start to create an event with name: $EventName"

$body = "<?xml version='1.0' encoding='utf-8' standalone='yes'?>

<entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'

xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'

xmlns='http://www.w3.org/2005/Atom'>

<category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />

<updated>7/14/2017 2:03:36 PM</updated>

<content type='application/xml'>

<m:properties>

<d:Name>$EventName</d:Name>

<d:EventType>e823b782-9a07-4e30-8091-034fc01f9347</d:EventType>

<d:SharePointAssetIdQuery>'ComplianceAssetId:123'</d:SharePointAssetIdQuery>

</m:properties>

</content>

</entry>"

$event = $null

try

{

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri "$baseUri/ComplianceRetentionEvent" -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

catch

{

$response = $_.Exception.Response

if($response.StatusCode -eq "Redirect")

{

$url = $response.Headers.Location

Write-Host "redirected to $url"

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

}

$event | fl *

```
