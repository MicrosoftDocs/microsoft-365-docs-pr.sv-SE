---
title: Granska konversationer i Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Lär dig mer om den aktuella konversationsfunktionen i Advanced eDiscovery (kallad konversationstrådning) för att återskapa, granska och exportera chattkonversationer i Microsoft Teams och Yammer konversationsgrupper.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9848280a7d6dbcbd6128fff06f150c8458f09701
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227193"
---
# <a name="conversation-threading-in-advanced-ediscovery"></a><span data-ttu-id="5a75e-103">Konversationstrådning i Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="5a75e-103">Conversation threading in Advanced eDiscovery</span></span>

<span data-ttu-id="5a75e-104">Snabbmeddelanden är ett bekvämt sätt att ställa frågor, dela idéer eller snabbt kommunicera med en stor publik.</span><span class="sxs-lookup"><span data-stu-id="5a75e-104">Instant messaging is a convenient way to ask questions, share ideas, or quickly communicate across large audiences.</span></span> <span data-ttu-id="5a75e-105">Som snabbmeddelandeplattformar, till exempel Microsoft Teams- och Yammer-grupper, blir grundläggande för samarbete inom företaget måste organisationer utvärdera hur deras eDiscovery-arbetsflöden hanterar dessa nya former av kommunikation och samarbete.</span><span class="sxs-lookup"><span data-stu-id="5a75e-105">As instant messaging platforms, like Microsoft Teams and Yammer groups, become core to enterprise collaboration, organizations must evaluate how their eDiscovery workflow addresses these new forms of communication and collaboration.</span></span>

<span data-ttu-id="5a75e-106">Funktionen Konversationsbyggnad i Advanced eDiscovery är utformad för att hjälpa dig att identifiera sammanhangsberoende innehåll och skapa unika konversationsvyer.</span><span class="sxs-lookup"><span data-stu-id="5a75e-106">The Conversation Reconstruction feature in Advanced eDiscovery is designed to help you identify contextual content and produce distinct conversation views.</span></span> <span data-ttu-id="5a75e-107">Med den här funktionen kan du snabbt och effektivt granska fullständiga snabbmeddelandekonversationer (även kallade trådade konversationer) som genereras på plattformar som Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5a75e-107">This capability allows you to efficiently and rapidly review complete instant message conversations (also called *threaded conversations*) that are generated in platforms like Microsoft Teams.</span></span>

<span data-ttu-id="5a75e-108">Med Konversationsbyggnad kan du använda inbyggda funktioner för att återskapa, granska och exportera trådade konversationer.</span><span class="sxs-lookup"><span data-stu-id="5a75e-108">With Conversation Reconstruction, you can use built-in capabilities to reconstruct, review, and export threaded conversations.</span></span> <span data-ttu-id="5a75e-109">Använd Advanced eDiscovery konversation och se till att:</span><span class="sxs-lookup"><span data-stu-id="5a75e-109">Use Advanced eDiscovery Conversation Reconstruction to:</span></span>

- <span data-ttu-id="5a75e-110">Bevara unika metadata på meddelandenivå för alla meddelanden i en konversation.</span><span class="sxs-lookup"><span data-stu-id="5a75e-110">Preserve unique message-level metadata across all messages within a conversation.</span></span>

- <span data-ttu-id="5a75e-111">Samla in sammanhangsbaserade meddelanden runt sökresultaten.</span><span class="sxs-lookup"><span data-stu-id="5a75e-111">Collect contextual messages around your search results.</span></span>

- <span data-ttu-id="5a75e-112">Granska, kommentera och redactera trådade konversationer.</span><span class="sxs-lookup"><span data-stu-id="5a75e-112">Review, annotate, and redact threaded conversations.</span></span>

- <span data-ttu-id="5a75e-113">Exportera enskilda meddelanden eller trådade konversationer</span><span class="sxs-lookup"><span data-stu-id="5a75e-113">Export individual messages or threaded conversations</span></span>

## <a name="terminology"></a><span data-ttu-id="5a75e-114">Terminologi</span><span class="sxs-lookup"><span data-stu-id="5a75e-114">Terminology</span></span>

<span data-ttu-id="5a75e-115">Här är några definitioner som hjälper dig att komma igång med konversationsbyggnad.</span><span class="sxs-lookup"><span data-stu-id="5a75e-115">Here are few definitions to help you get start using Conversation Reconstruction.</span></span>

- <span data-ttu-id="5a75e-116">**Meddelanden:** Representerar den minsta enheten i en konversation.</span><span class="sxs-lookup"><span data-stu-id="5a75e-116">**Messages:** Represent the smallest unit of a conversation.</span></span> <span data-ttu-id="5a75e-117">Meddelanden kan variera i storlek, struktur och metadata.</span><span class="sxs-lookup"><span data-stu-id="5a75e-117">Messages may vary in size, structure, and metadata.</span></span>

- <span data-ttu-id="5a75e-118">**Konversation:** Representerar en gruppering av ett eller flera meddelanden.</span><span class="sxs-lookup"><span data-stu-id="5a75e-118">**Conversation:** Represents a grouping of one or more messages.</span></span> <span data-ttu-id="5a75e-119">Konversationer kan representeras på olika sätt i olika program.</span><span class="sxs-lookup"><span data-stu-id="5a75e-119">Across different applications, conversations may be represented in different ways.</span></span> <span data-ttu-id="5a75e-120">I vissa program finns det en explicit åtgärd som resulterar i att svara på ett befintligt meddelande.</span><span class="sxs-lookup"><span data-stu-id="5a75e-120">In some applications, there is an explicit action that results from replying to an existing message.</span></span> <span data-ttu-id="5a75e-121">Konversationer skapas explicit som ett resultat av den här användaråtgärden.</span><span class="sxs-lookup"><span data-stu-id="5a75e-121">Conversations are formed explicitly as a result of this user action.</span></span> <span data-ttu-id="5a75e-122">Här är till exempel en skärmbild av en kanalkonversation i Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5a75e-122">For example, here is a screenshot of a channel conversation in Microsoft Teams.</span></span>

   ![Microsoft Teams Kanalkonversation](../media/threadedchat.png)

   <span data-ttu-id="5a75e-124">I andra program (till exempel 1xN-chattmeddelanden i Teams) finns det inte en formell svarskedjan utan i stället visas meddelanden som en "platt flod av meddelanden" i en enda tråd.</span><span class="sxs-lookup"><span data-stu-id="5a75e-124">In other apps (such as 1xN chat messages in Teams), there is not a formal reply chain and instead messages appear as a "flat river of messages" within a single thread.</span></span> <span data-ttu-id="5a75e-125">I de här typerna av appar härförs konversationer från en grupp meddelanden som inträffar inom en viss tid.</span><span class="sxs-lookup"><span data-stu-id="5a75e-125">In these types apps, conversations are inferred from a group of messages that occur within a certain time.</span></span> <span data-ttu-id="5a75e-126">Den här "mjuka gruppering" av meddelanden (i motsats till en svarskedjan) representerar "fram och tillbaka"-konversationen om ett särskilt intresse.</span><span class="sxs-lookup"><span data-stu-id="5a75e-126">This "soft-grouping" of messages (as opposed to a reply chain) represent the "back and forth" conversation about a specific topic of interest.</span></span>

## <a name="step-1-create-a-draft-collection"></a><span data-ttu-id="5a75e-127">Steg 1: Skapa ett utkast</span><span class="sxs-lookup"><span data-stu-id="5a75e-127">Step 1: Create a draft collection</span></span>

<span data-ttu-id="5a75e-128">När du har identifierat relevanta sökfunktionen och innehållsplatser kan du skapa en sökning för att hitta potentiellt relevant innehåll.</span><span class="sxs-lookup"><span data-stu-id="5a75e-128">After you have identified relevant custodians and content locations, you can create a search to find potentially relevant content.</span></span> <span data-ttu-id="5a75e-129">På fliken **Samlingar** i det Advanced eDiscovery ärende kan du skapa en samling genom att klicka på **Ny samling** och följa guiden.</span><span class="sxs-lookup"><span data-stu-id="5a75e-129">On the **Collections** tab in the Advanced eDiscovery case, you can create a collection by clicking **New collection** and following the wizard.</span></span> <span data-ttu-id="5a75e-130">Mer information om hur du kan skapa en samling, skapa en sökfråga och förhandsgranska sökresultaten finns i [Skapa en utkastsamling](create-draft-collection.md).</span><span class="sxs-lookup"><span data-stu-id="5a75e-130">For information about how you can create a collection, build a search query, and preview the search results, see [Create a draft collection](create-draft-collection.md).</span></span>

## <a name="step-2-commit-a-draft-collection-to-a-review-set"></a><span data-ttu-id="5a75e-131">Steg 2: Spara ett utkast till en granskningsuppsättning</span><span class="sxs-lookup"><span data-stu-id="5a75e-131">Step 2: Commit a draft collection to a review set</span></span>

<span data-ttu-id="5a75e-132">När du har granskat och färdigställt sökfrågan i en samling kan du lägga till sökresultatet i en granskningsuppsättning.</span><span class="sxs-lookup"><span data-stu-id="5a75e-132">After you have reviewed and finalized the search query in a collection, you can add the search results to a review set.</span></span> <span data-ttu-id="5a75e-133">När du lägger till dina sökresultat i en granskningsuppsättning kopieras ursprungliga data till ett Azure Storage för att underlätta gransknings- och analysprocessen.</span><span class="sxs-lookup"><span data-stu-id="5a75e-133">When you add your search results into a review set, the original data is copied to an Azure Storage area to facilitate the review and analysis process.</span></span> <span data-ttu-id="5a75e-134">Mer information om hur du lägger till sökresultat i en granskningsuppsättning finns i [Spara ett utkast till en granskningsuppsättning.](commit-draft-collection.md)</span><span class="sxs-lookup"><span data-stu-id="5a75e-134">For more information about adding search results to a review set, see [Commit a draft collection to a review set](commit-draft-collection.md).</span></span>

<span data-ttu-id="5a75e-135">När du lägger till objekt från konversationer i en granskningsuppsättning kan du använda alternativet trådade konversationer för att samla in sammanhangsbaserade meddelanden från konversationer som innehåller objekt som matchar sökvillkoren i samlingen.</span><span class="sxs-lookup"><span data-stu-id="5a75e-135">When you add items from conversations to a review set, you can use the threaded conversations option to collect contextual messages from conversations that contain items that match the search criteria of the collection.</span></span> <span data-ttu-id="5a75e-136">När du har valt alternativet trådkonversationer kan följande saker hända:</span><span class="sxs-lookup"><span data-stu-id="5a75e-136">After you select the thread conversations option, the following things can happen:</span></span>

  ![Hämtning av konversation](../media/messagesandconversations.png)

1. <span data-ttu-id="5a75e-138">Med hjälp av ett nyckelord och en datumintervallfråga returnerade sökningen en träff *i meddelande 3.*</span><span class="sxs-lookup"><span data-stu-id="5a75e-138">Using a keyword and date range query, the search returned a hit on *Message 3*.</span></span> <span data-ttu-id="5a75e-139">Det här meddelandet var en del av en större konversation, illustrerad av *CRC1*.</span><span class="sxs-lookup"><span data-stu-id="5a75e-139">This message was part of a larger conversation, illustrated by *CRC1*.</span></span>

2. <span data-ttu-id="5a75e-140">När du lägger till data i en granskningsuppsättning och aktiverar alternativ för konversationshämtning går Advanced eDiscovery tillbaka och samlar in andra objekt i *CRC1.*</span><span class="sxs-lookup"><span data-stu-id="5a75e-140">When you add the data into a review set and enable the conversation retrieval options, Advanced eDiscovery will go back and collect other items in *CRC1*.</span></span>

3. <span data-ttu-id="5a75e-141">När objekten har lagts till i granskningsuppsättningen kan du granska alla enskilda meddelanden från *CRC1.*</span><span class="sxs-lookup"><span data-stu-id="5a75e-141">After the items have been added to the review set, you can review all the individual messages from *CRC1*.</span></span>

<span data-ttu-id="5a75e-142">Information om hur du aktiverar alternativet trådade konversationer finns i [Spara ett utkast till en granskningsuppsättning](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set).</span><span class="sxs-lookup"><span data-stu-id="5a75e-142">To enabled the threaded conversations option, see [Commit a draft collection to a review set](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set).</span></span>

## <a name="step-3-review-and-export-threaded-conversations"></a><span data-ttu-id="5a75e-143">Steg 3: Granska och exportera trådade konversationer</span><span class="sxs-lookup"><span data-stu-id="5a75e-143">Step 3: Review and export threaded conversations</span></span>

<span data-ttu-id="5a75e-144">När innehållet har bearbetats och lagts till i granskningsuppsättningen kan du börja granska data i granskningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="5a75e-144">After the content has been processed and added to the review set, you can start reviewing the data in the review set.</span></span> <span data-ttu-id="5a75e-145">Granskningsfunktionerna skiljer sig åt beroende på om innehållet har lagts till i en standardgranskningsuppsättning eller en uppsättning konversationsgranskningar.</span><span class="sxs-lookup"><span data-stu-id="5a75e-145">The review capabilities are different depending on whether the content was added to a standard review set or a conversation review set.</span></span>

### <a name="reviewing-conversations-in-a-standard-review-set"></a><span data-ttu-id="5a75e-146">Granska konversationer i en standardgranskningsuppsättning</span><span class="sxs-lookup"><span data-stu-id="5a75e-146">Reviewing conversations in a standard review set</span></span>

<span data-ttu-id="5a75e-147">I en standardgranskningsuppsättning bearbetas och visas meddelanden som enskilda objekt, ungefär på samma sätt som de lagras i en postlådemapp.</span><span class="sxs-lookup"><span data-stu-id="5a75e-147">In a standard review set, messages are processed and displayed as individual items, similar to how they're stored in a mailbox folder.</span></span> <span data-ttu-id="5a75e-148">I det här arbetsflödet behandlas varje meddelande som ett separat objekt.</span><span class="sxs-lookup"><span data-stu-id="5a75e-148">In this workflow, each message is processed as a separate item.</span></span> <span data-ttu-id="5a75e-149">Därför är de trådade sammanfattnings- och exportalternativen inte tillgängliga i en standarduppsättning för granskning.</span><span class="sxs-lookup"><span data-stu-id="5a75e-149">As a result, the threaded summary and export options aren't available in a standard review set.</span></span>

  ![Standardgranskningsuppsättning](../media/standardrs.PNG)

### <a name="reviewing-conversations-in-a-conversation-review-set"></a><span data-ttu-id="5a75e-151">Granska konversationer i en uppsättning med konversationsgranskning</span><span class="sxs-lookup"><span data-stu-id="5a75e-151">Reviewing conversations in a conversation review set</span></span>

<span data-ttu-id="5a75e-152">När en konversationsgranskning har ställts in trådas enskilda meddelanden samman och visas som konversationer.</span><span class="sxs-lookup"><span data-stu-id="5a75e-152">In a conversation review set, individual messages are threaded together and presented as conversations.</span></span> <span data-ttu-id="5a75e-153">På så sätt kan du granska och exportera sammanhangsberoende konversationer.</span><span class="sxs-lookup"><span data-stu-id="5a75e-153">This lets you review and export contextual conversations.</span></span>

  ![Uppsättning med konversationsgranskning](../media/ConversationRSOptions.PNG)

<span data-ttu-id="5a75e-155">I följande avsnitt beskrivs hur du granskar och exporterar konversationer i en uppsättning konversationsgranskning.</span><span class="sxs-lookup"><span data-stu-id="5a75e-155">The following sections describe reviewing and exporting conversations in a conversation review set.</span></span>

#### <a name="reviewing-conversations"></a><span data-ttu-id="5a75e-156">Granska konversationer</span><span class="sxs-lookup"><span data-stu-id="5a75e-156">Reviewing conversations</span></span>

<span data-ttu-id="5a75e-157">I en uppsättning med konversationsgranskning kan du använda följande alternativ för att underlätta granskningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="5a75e-157">In a conversation review set, you can use the following options to facilitate the review process.</span></span>

- <span data-ttu-id="5a75e-158">**Gruppera efter konversation:** Grupperar meddelanden i samma konversation tillsammans för att hjälpa användare att förenkla och underlätta granskningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="5a75e-158">**Group by conversation:** Groups messages within the same conversation together to help users simplify and expedite their review process.</span></span>

- <span data-ttu-id="5a75e-159">**Sammanfattningsvy:** Visar den trådade konversationen.</span><span class="sxs-lookup"><span data-stu-id="5a75e-159">**Summary view:** Displays the threaded conversation.</span></span> <span data-ttu-id="5a75e-160">I den här vyn kan du se hela konversationen och även komma åt metadata för varje enskilt meddelande.</span><span class="sxs-lookup"><span data-stu-id="5a75e-160">In this view, you can see the entire conversation and also access the metadata for each individual message.</span></span>

   - <span data-ttu-id="5a75e-161">Visa metadata för enskilda meddelanden</span><span class="sxs-lookup"><span data-stu-id="5a75e-161">View metadata for individual messages</span></span>

   - <span data-ttu-id="5a75e-162">Ladda ned enskilda meddelanden</span><span class="sxs-lookup"><span data-stu-id="5a75e-162">Download individual messages</span></span>

- <span data-ttu-id="5a75e-163">**Textvy:** Ger extraherad text för hela konversationen.</span><span class="sxs-lookup"><span data-stu-id="5a75e-163">**Text view:** Provides the extracted text for the entire conversation.</span></span>

- <span data-ttu-id="5a75e-164">**Kommentera vyn:** Med det här alternativet kan du markera en trådad vy av konversationen.</span><span class="sxs-lookup"><span data-stu-id="5a75e-164">**Annotate view:** Lets you markup a threaded view of the conversation.</span></span> <span data-ttu-id="5a75e-165">Alla meddelanden i konversationen delar samma kommenterade dokument.</span><span class="sxs-lookup"><span data-stu-id="5a75e-165">All messages in the conversation share the same annotated document.</span></span>

- <span data-ttu-id="5a75e-166">**Märkning:** När du visar konversationer i en granskningsuppsättning kan du visa och använda taggar genom att klicka **på Taggningspanel** i panelen Kodning.</span><span class="sxs-lookup"><span data-stu-id="5a75e-166">**Tagging:** When viewing conversations in a review set, you can view and apply tags by clicking **Tagging panel** in the Coding panel.</span></span>

- <span data-ttu-id="5a75e-167">**Kör konversationskonvertering igen:** När meddelanden läggs till i en uppsättning med konversationsgranskning körs ett konverteringsjobb automatiskt för att skapa den trådade sammanfattningen och kommentera vyerna.</span><span class="sxs-lookup"><span data-stu-id="5a75e-167">**Rerun conversation conversion:** When messages are added to a conversation review set, a conversion job is automatically run to create the threaded summary and annotate views.</span></span> <span data-ttu-id="5a75e-168">Om jobbet Konversationsbyggnad inte fungerar kan du köra det här jobbet igen genom att klicka på Åtgärd **> Skapa konversations-PDF-filer** i granskningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="5a75e-168">If the Conversation Reconstruction job fails, you can rerun this job by clicking **Action > Create conversation PDFs** in the review set.</span></span>

#### <a name="exporting-conversations"></a><span data-ttu-id="5a75e-169">Exportera konversationer</span><span class="sxs-lookup"><span data-stu-id="5a75e-169">Exporting conversations</span></span>

<span data-ttu-id="5a75e-170">I en konversationsgranskning kan du ange följande alternativ för att exportera konversationer:</span><span class="sxs-lookup"><span data-stu-id="5a75e-170">In a conversation review set, you can set the following options to export conversations:</span></span>

![Exportera alternativ för konversationer](../media/export.png)

1. <span data-ttu-id="5a75e-172">Metadataalternativ:</span><span class="sxs-lookup"><span data-stu-id="5a75e-172">Metadata options:</span></span>
   - <span data-ttu-id="5a75e-173">**Läs in fil:** Metadata ingår för varje enskilt meddelande, e-postmeddelande och dokument.</span><span class="sxs-lookup"><span data-stu-id="5a75e-173">**Load file:** Metadata is included for each individual message, email, and document.</span></span> <span data-ttu-id="5a75e-174">Det finns en rad för varje meddelande i en konversation.</span><span class="sxs-lookup"><span data-stu-id="5a75e-174">There is one row for each message in a conversation.</span></span>
   - <span data-ttu-id="5a75e-175">**Taggar:** Taggar från din granskningsprocess ingår i metadatafilen.</span><span class="sxs-lookup"><span data-stu-id="5a75e-175">**Tags:** Tags from your review process are included in the metadata file.</span></span> <span data-ttu-id="5a75e-176">Meddelanden i en konversation har samma taggar.</span><span class="sxs-lookup"><span data-stu-id="5a75e-176">Messages in a conversation share the same tags.</span></span>

2. <span data-ttu-id="5a75e-177">Konversationsalternativ:</span><span class="sxs-lookup"><span data-stu-id="5a75e-177">Conversation options:</span></span>
   - <span data-ttu-id="5a75e-178">**Konversationsfiler:** När du exporterar konversationsfiler konverteras den kommenterade vyn till en PDF-fil och laddas ned till exportmappen.</span><span class="sxs-lookup"><span data-stu-id="5a75e-178">**Conversation files:** When you export conversation files, the annotated view is converted to a PDF file and downloaded to the export folder.</span></span> <span data-ttu-id="5a75e-179">Meddelanden i en konversationsfil pekar på PDF-versionen av samma konversationsfil.</span><span class="sxs-lookup"><span data-stu-id="5a75e-179">Messages in one conversation file point to the PDF version of the same conversation file.</span></span>
   - <span data-ttu-id="5a75e-180">**Enskilda chattmeddelanden:** När du exporterar enskilda meddelanden exporteras varje unikt meddelande i konversationen som ett fristående objekt.</span><span class="sxs-lookup"><span data-stu-id="5a75e-180">**Individual chat messages:** When you export individual messages, each unique message in the conversation is exported as a standalone item.</span></span> <span data-ttu-id="5a75e-181">Filen exporteras i samma format som den sparades som i postlådan.</span><span class="sxs-lookup"><span data-stu-id="5a75e-181">The file is exported in the same format that it was saved as in the mailbox.</span></span> <span data-ttu-id="5a75e-182">För en viss konversation får du flera MSG-filer.</span><span class="sxs-lookup"><span data-stu-id="5a75e-182">For a specific conversation, you receive multiple .msg files.</span></span>

     > [!NOTE]
     > <span data-ttu-id="5a75e-183">Om du har använt anteckningar i konversationsfilen överförs inte de här anteckningarna till de enskilda meddelandena.</span><span class="sxs-lookup"><span data-stu-id="5a75e-183">If you applied annotations to the conversation file, these annotations won't be transferred to the individual messages.</span></span>

3. <span data-ttu-id="5a75e-184">Andra alternativ:</span><span class="sxs-lookup"><span data-stu-id="5a75e-184">Other options:</span></span>
   - <span data-ttu-id="5a75e-185">**Generera textfiler för allt exporterat innehåll:** Genererar en textfil för varje konversation som exporteras från granskningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="5a75e-185">**Generate text files for all exported content:** Generates a text file for each conversation exported from the review set.</span></span>
   - <span data-ttu-id="5a75e-186">**Ersätta exporterat innehåll med pdf-filer som har omaktiverats:** Om omaktade konversationsfiler genereras under granskningsprocessen är dessa filer tillgängliga under exporten.</span><span class="sxs-lookup"><span data-stu-id="5a75e-186">**Replace exported content with redacted PDFs:** If redacted conversation files are generated during the review process, then these files are available during export.</span></span> <span data-ttu-id="5a75e-187">Du kan bestämma dig för om du bara vill exportera originalfilerna (genom att inte välja det här alternativet) eller ersätta de ursprungliga filerna med de omdrekventa versionerna av de ursprungliga filerna (genom att välja det här alternativet), som exporteras som PDF-filer.</span><span class="sxs-lookup"><span data-stu-id="5a75e-187">You can decided whether to export only the native files (by not selecting this option) or to replace the native files with the redacted versions of the native files (by selecting this option), which are exported as PDF files.</span></span>

## <a name="more-information"></a><span data-ttu-id="5a75e-188">Mer information</span><span class="sxs-lookup"><span data-stu-id="5a75e-188">More information</span></span>

<span data-ttu-id="5a75e-189">Mer information om hur du granskar ärendedata i Advanced eDiscovery finns i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="5a75e-189">To learn more about how to review case data in Advanced eDiscovery, see the following articles:</span></span>

- [<span data-ttu-id="5a75e-190">Visa ärendedata</span><span class="sxs-lookup"><span data-stu-id="5a75e-190">View case data</span></span>](view-documents-in-review-set.md)
- [<span data-ttu-id="5a75e-191">Analysera ärendedata</span><span class="sxs-lookup"><span data-stu-id="5a75e-191">Analyze case data</span></span>](analyzing-data-in-review-set.md)
- [<span data-ttu-id="5a75e-192">Exportera ärendedata</span><span class="sxs-lookup"><span data-stu-id="5a75e-192">Export case data</span></span>](exporting-data-ediscover20.md)
