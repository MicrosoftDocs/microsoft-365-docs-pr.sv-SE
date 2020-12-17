---
title: Ämne upplever säkerhets trimning (för hands version)
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Översikt över hur säkerhet används för att Visa ämnen.
ms.openlocfilehash: 7e503082494d27f9418b8e09b8d20d01e4708fe9
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49699062"
---
# <a name="topic-experiences-security-trimming-preview"></a><span data-ttu-id="91501-103">Ämne upplever säkerhets trimning (för hands version)</span><span class="sxs-lookup"><span data-stu-id="91501-103">Topic Experiences security trimming (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="91501-104">Innehållet i den här artikeln gäller för projekt cortex privat för hands version.</span><span class="sxs-lookup"><span data-stu-id="91501-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="91501-105">[Läs mer om Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="91501-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="91501-106">Ämnen som gör att användarna inte kan se information om ämnen som de befintliga Office 365-behörigheterna hindrar dem från att se.</span><span class="sxs-lookup"><span data-stu-id="91501-106">Topic experiences users will not be able to view information in topics that their existing Office 365 permissions prevents them from seeing.</span></span> <span data-ttu-id="91501-107">Allt som en användare ser på en ämnes sida (till exempel SharePoint-webbplatser, dokument, filer) kommer att vara information som de redan är tillåtna för att visas.</span><span class="sxs-lookup"><span data-stu-id="91501-107">Everything a user sees on a topic page (for example, SharePoint sites, documents, files) will be information they are already allowed to see.</span></span> <span data-ttu-id="91501-108">Avsnitts upplevelser ändrar inte befintliga behörigheter.</span><span class="sxs-lookup"><span data-stu-id="91501-108">Topic experiences does not make changes to any existing permissions.</span></span>

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a><span data-ttu-id="91501-109">Varför två användare kan ha olika vyer av samma ämne</span><span class="sxs-lookup"><span data-stu-id="91501-109">Why two users may have different views of the same topic</span></span>

<span data-ttu-id="91501-110">När ett ämne skapas via AI eller manuell bevarande kan det innehålla en beskrivning av ämnet, alternativa namn, personer som är kopplade till ämnet, samt webbplatser, sidor och filer relaterade till avsnittet.</span><span class="sxs-lookup"><span data-stu-id="91501-110">When a topic is created through AI or manual curation, it can contain a description of the topic, alternative names, people associated with the topic, as well as sites, pages, and files related to the topic.</span></span> <span data-ttu-id="91501-111">När den här informationen visas på en ämnes sida är det möjligt att två användare som visar samma ämne inte ser samma information.</span><span class="sxs-lookup"><span data-stu-id="91501-111">When this information is viewed on a topic page, it is possible that two users who are viewing the same topic my not see the same information.</span></span>
  
<span data-ttu-id="91501-112">Om till exempel en användare 1 visar sidan Neptune, är detta det här som de kan se.</span><span class="sxs-lookup"><span data-stu-id="91501-112">For example, when User 1 views the Neptune topic page, this is what they might see.</span></span>

![Neptune-avsnitt för användare 1](../media/knowledge-management/user2-topic-view.png) </br> 

<span data-ttu-id="91501-114">Men när användare 2 tittar på samma Neptune visas en vy från användare 1.</span><span class="sxs-lookup"><span data-stu-id="91501-114">However, when User 2 looks at the same Neptune topic page, her view differs from User 1.</span></span>  <span data-ttu-id="91501-115">Användare 2 kan se *produkt översikts filen DG-2000* i avsnittet **fästa filer och sidor** på sidan ämne, som inte visas för användare 1.</span><span class="sxs-lookup"><span data-stu-id="91501-115">User 2 is able to see the *DG-2000 Product Overview* file in the **Pinned files and pages** section of the topic page, which does not appear for User 1.</span></span> 

![Neptune-avsnitt för användare 2](../media/knowledge-management/user1-topic-view.png) </br> 

<span data-ttu-id="91501-117">Skillnaden i vad användarna kan se i samma avsnitt är att användarna kanske inte har Office 365-behörighet för att visa en relaterad webbplats eller fil.</span><span class="sxs-lookup"><span data-stu-id="91501-117">The difference in what users may see on the same topic is because users may not have the Office 365 permissions to view a related site or file.</span></span>  <span data-ttu-id="91501-118">Avsnitts erfarenheten respekterar de behörigheter som är inställda för objekt i ett ämne och kan inte ändra åtkomsten till dem.</span><span class="sxs-lookup"><span data-stu-id="91501-118">Topic experiences respects the permissions that are set on items in a topic, and cannot change access to them.</span></span> <span data-ttu-id="91501-119">I vårt exempel kan inte användare 1 Visa *produkt översikts filen DG-2000* på sidan för Neptune eftersom användare 1 inte har Office 365-behörighet för att visa filen.</span><span class="sxs-lookup"><span data-stu-id="91501-119">In our example, User 1 is not able to view the *DG-2000 Product Overview* file in their topic page for Neptune because User 1 does not have Office 365 permissions to view the file.</span></span>

<span data-ttu-id="91501-120">Om en användare inte kan se tillräckligt med information i ett ämne för att den ska vara användbar, är avsnittet inte tillgängligt för användaren.</span><span class="sxs-lookup"><span data-stu-id="91501-120">If a user is not able to see enough information in a topic for it to be useful, the topic will not be available to the user.</span></span> <span data-ttu-id="91501-121">I den här instansen visas inte det markerade avsnittet.</span><span class="sxs-lookup"><span data-stu-id="91501-121">In this instance, the user will not see the highlighted topic.</span></span> <span data-ttu-id="91501-122">Men en annan användare som har behörighet till mer information i ämnet för att det ska vara användbart kan se avsnittet.</span><span class="sxs-lookup"><span data-stu-id="91501-122">However, a different user who has permissions to more information in the topic for it to be useful, will be able to see the topic.</span></span>


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a><span data-ttu-id="91501-123">Behörigheter för ämne för kunskaps chefer och ämnes deltagare</span><span class="sxs-lookup"><span data-stu-id="91501-123">Topic permissions for knowledge managers and topic contributors</span></span>

<span data-ttu-id="91501-124">Användare som har tilldelats behörigheter för att hantera ämnen – kunskaps chefer-kommer bara att kunna visa information som de har behörighet att se i avsnitt.</span><span class="sxs-lookup"><span data-stu-id="91501-124">Users that are assigned permissions to manage topics - knowledge managers - will only be able to view information they have permissions to see within topics.</span></span>

<span data-ttu-id="91501-125">På liknande sätt kan användare som har behörigheten Skapa och redigera ämne-ämnes deltagare-bara visa information som de har behörighet att se i ämnen.</span><span class="sxs-lookup"><span data-stu-id="91501-125">Similarly, users who have create and edit topic permissions - topic contributors - will only be able to view information they have permissions to see within topics.</span></span> 


## <a name="ai-versus-manually-curated-topic-information"></a><span data-ttu-id="91501-126">AI och manuellt underavsnitts information</span><span class="sxs-lookup"><span data-stu-id="91501-126">AI versus manually curated topic information</span></span>

<span data-ttu-id="91501-127">Ämnen kan innehålla information som genererats av AI och information som lagts till eller redigerats av ämnes deltagare eller kunskaps chefer.</span><span class="sxs-lookup"><span data-stu-id="91501-127">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

 - <span data-ttu-id="91501-128">Information i ett ämne som lagts till av AI visas bara för personer som har till gång till käll innehållet.</span><span class="sxs-lookup"><span data-stu-id="91501-128">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
 - <span data-ttu-id="91501-129">Information som har lagts till manuellt eller redigerats av en ämnes deltagare eller kunskaps chef visas för alla som kan se avsnittet.</span><span class="sxs-lookup"><span data-stu-id="91501-129">Information that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>

<span data-ttu-id="91501-130">I följande tabell beskrivs vad användare – avsnitts läsare, deltagare och kunskaps chefer – kan se i ett visst ämne baserat på deras behörigheter.</span><span class="sxs-lookup"><span data-stu-id="91501-130">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="91501-131">Ämnes objekt</span><span class="sxs-lookup"><span data-stu-id="91501-131">Topic item</span></span>|<span data-ttu-id="91501-132">Vad användarna kan se</span><span class="sxs-lookup"><span data-stu-id="91501-132">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="91501-133">Namn på avsnitt</span><span class="sxs-lookup"><span data-stu-id="91501-133">Topic name</span></span>|<span data-ttu-id="91501-134">Användare kan se ämnes namnet i alla ämnen i ämnes centret.</span><span class="sxs-lookup"><span data-stu-id="91501-134">Users can see the topic name of all topics in the topic center.</span></span> <span data-ttu-id="91501-135">Vissa ämnen kanske inte visas om de har en liten sökrelevans till användaren.</span><span class="sxs-lookup"><span data-stu-id="91501-135">Some topics may not be visible if they have a low relevancy to the user.</span></span>|
|<span data-ttu-id="91501-136">Beskrivning av ämnet</span><span class="sxs-lookup"><span data-stu-id="91501-136">Topic description</span></span>|<span data-ttu-id="91501-137">AI-genererade beskrivningar visas endast för användare som har behörighet till käll innehållet.</span><span class="sxs-lookup"><span data-stu-id="91501-137">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="91501-138">Manuellt angivna eller redigerade beskrivningar visas för alla användare.</span><span class="sxs-lookup"><span data-stu-id="91501-138">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="91501-139">Kontakter</span><span class="sxs-lookup"><span data-stu-id="91501-139">People</span></span>|<span data-ttu-id="91501-140">Fästa personer visas för alla användare.</span><span class="sxs-lookup"><span data-stu-id="91501-140">Pinned people are visible to all users.</span></span> <span data-ttu-id="91501-141">Föreslagna personer visas bara för användare som har behörighet till käll innehållet.</span><span class="sxs-lookup"><span data-stu-id="91501-141">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="91501-142">Hjälpfiler</span><span class="sxs-lookup"><span data-stu-id="91501-142">Files</span></span>|<span data-ttu-id="91501-143">Filer visas endast för användare som har behörighet till käll innehållet.</span><span class="sxs-lookup"><span data-stu-id="91501-143">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="91501-144">Målsidor</span><span class="sxs-lookup"><span data-stu-id="91501-144">Pages</span></span>|<span data-ttu-id="91501-145">Sidor visas bara för användare som har behörighet till käll innehållet.</span><span class="sxs-lookup"><span data-stu-id="91501-145">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="91501-146">Sidor</span><span class="sxs-lookup"><span data-stu-id="91501-146">Sites</span></span>|<span data-ttu-id="91501-147">Webbplatser visas bara för användare som har behörighet till käll innehållet.</span><span class="sxs-lookup"><span data-stu-id="91501-147">Sites are only visible to users who have permissions to the source content.</span></span>|




## <a name="see-also"></a><span data-ttu-id="91501-148">Se även</span><span class="sxs-lookup"><span data-stu-id="91501-148">See also</span></span>

